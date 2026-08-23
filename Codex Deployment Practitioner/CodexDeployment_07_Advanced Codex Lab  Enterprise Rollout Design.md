# Advanced Codex Lab - Enterprise Rollout Design

## Slide 1/10 - Title

고급 Codex 랩

태스크 트래커 코딩 태스크

Created March 2026

## Slide 2/10 - 소개 (Introduction)

이 랩은 고급 코덱스 과정을 위한 실용적인 코딩 연습입니다.

Codex를 사용하여 익숙하지 않은 저장소를 검사하고, 문제를 진단하며, 기능을 구현하고, 검토 가능한 Git 변경 사항을 준비하게 됩니다. 초점은 수동 코딩 속도가 아닙니다. 초점은 Codex를 효과적으로 활용하고, diff를 검토하며, 결과를 검증하는 데 있습니다.

**정식 저장소**

https://github.com/pavlinhristov/CodexLab

**예상 소요 시간**

30분에서 45분.

## Slide 3/10 - 개요 (Overview)

**모든 단계에서 코덱스 사용**

- 코드 변경 전 Codex로 검사 요청.
- 설정 및 검증 명령어 실행을 Codex에 요청하십시오.
- 패치하기 전에 Codex에 발견 사항을 설명하도록 요청하십시오.
- 변경 사항을 수락하기 전에 Codex diff를 검토하십시오.
- 각 변경 후 검증 재실행을 요청하십시오.

이를 수동 코딩 작업으로 취급하지 마십시오. 코덱스를 구현 팀원으로 여기고 본인은 검토자 역할에 머무르십시오.

**필수 사항**

- Git
- Codex 앱 또는 Codex 클라우드 접근 권한
- Python 3.9 이상

## Slide 4/10 - 저장소 설정 (Repository Setup)

표준 랩 저장소에서 시작:

```bash
git clone https://github.com/pavlinhristov/CodexLab.git
cd CodexLab
```

가상 환경 생성 및 활성화:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

의존성 설치:

```bash
pip install -r requirements.txt
```

앱 실행:

```
uvicorn app.main:app --reload
```

예상되는 로컬 엔드포인트:

- http://127.0.0.1:8000
- http://127.0.0.1:8000/docs

권장 설정 프롬프트:

- 개발용으로 이 저장소를 설정하세요. 가상 환경을 생성하고, 종속성을 설치하고, FastAPI 앱을 시작한 후 정확히 실행한 내용을 알려주세요.

## Slide 5/10 - 작업 1 - 코드베이스 이해하기 (Task 1 - Understanding the Codebase)

변경하기 전에 Codex에 리포지토리를 설명해 달라고 요청하고 GET /tasks 흐름을 추적하세요.

**권장 프롬프트:**

- 이 저장소의 기능을 설명하고 주요 파일의 위치를 파악하세요.
- GET /tasks 요청을 라우팅부터 저장소까지 추적하고 필터링 로직이 위치한 곳을 확인하세요.
- 오늘 팀에 합류하는 엔지니어를 위해 이 코드베이스를 요약하세요.

이 작업을 완료한 후에는 다음과 같은 명확한 개념적 모델을 갖춰야 합니다:

- app/main.py는 경로를 정의합니다
- app/schemas.py는 요청/응답 모델을 정의합니다.
- app/service.py는 비즈니스 로직을 담습니다
- app/store.py는 JSON 지속성을 처리합니다
- data/tasks.json에는 샘플 데이터가 포함됩니다

## Slide 6/10 - 작업 2 - 두 개의 버그 수정 (Task 2 - Fix Two Bugs)

이 저장소에는 의도적으로 두 개의 버그가 포함되어 있습니다. 각 버그에 대해 Codex에 전체 루프 실행을 요청하세요:

1. 재현
2. 진단
3. 수정
4. 차이점 표시
5. 검증

**버그 A: 상태 필터링이 깨짐**

재현:

```bash
curl http://127.0.0.1:8000/tasks
curl "http://127.0.0.1:8000/tasks?status=open"
```

수정 후 예상 결과:

- status=open은 열려 있는 작업만 반환합니다.

권장 프롬프트:

- GET /tasks 상태 필터 버그 재현, 근본 원인 설명, 최소한의 깔끔한 수정 구현, 결과 검증.

**버그 B: 완료 상태가 유지되지 않음**

재현:

```bash
curl -X POST http://127.0.0.1:8000/tasks/1/complete
curl http://127.0.0.1:8000/tasks/1
```

수정 후 예상 결과:

- 다시 조회 시 작업이 완료된 상태로 유지됨.
- completed_at 필드가 null이 아님.

권장 프롬프트:

- 완료된 작업의 지속성 문제를 재현하고, 저장소/비즈니스 로직 경계에서 수정하며, 지속성을 입증하기 위해 API 호출을 재실행하십시오.

## Slide 7/10 - 작업 3 - 검색 기능 추가 (Task 3 - Add Search Feature)

GET /tasks에 선택적 q 쿼리 매개변수를 구현합니다.

**요구 사항:**

- 대소문자 구분 없는 일치.
- 제목과 설명 모두에 대해 일치.
- 상태 필터와 함께 작동.
- q가 생략된 경우 기존 동작은 변경되지 않습니다.

**검증 예시:**

```bash
curl "http://127.0.0.1:8000/tasks?q=launch"
curl "http://127.0.0.1:8000/tasks?q=report"
curl "http://127.0.0.1:8000/tasks?status=open&q=plan"
```

권장 프롬프트:

- GET /tasks에 대한 q 필터를 구현하여 제목과 설명에 대해 대소문자 구분 없이 일치시키고, q가 누락된 경우 기존 동작을 유지하며, curl로 검증하십시오.

## Slide 8/10 - 작업 4 - 깨끗한 커밋 준비 (Task 4 - Prepare a Clean Commit)

최종 diff를 승인한 후 Codex가 브랜치 생성 및 커밋을 준비하도록 합니다.

커밋 전, data/tasks.json 변경이 런타임 테스트로 인한 것인지 확인하십시오. 해당될 경우, 커밋에 의도된 코드 변경만 포함되도록 해당 변경을 되돌리십시오.

**권장 명령어:**

```bash
git checkout -b codex/lab-fixes
git status
git add .
git commit -m "Fix task bugs and add search filter"
git push origin codex/lab-fixes
```

권장 프롬프트:

- 이 저장소를 PR 검토를 위해 준비하세요: data/tasks.json을 복원해야 하는지 확인하고, 코드 변경 사항을 요약한 후, 내 승인 후 깨끗한 커밋을 생성하세요.

## Slide 9/10 - 최종 검증 체크리스트 (Final Verification Checklist)

실행하거나 Codex에 실행 요청:

```bash
curl "http://127.0.0.1:8000/tasks?status=open"
curl "http://127.0.0.1:8000/tasks?status=done"
curl -X POST http://127.0.0.1:8000/tasks/3/complete
curl http://127.0.0.1:8000/tasks/3
curl "http://127.0.0.1:8000/tasks?q=launch"
curl "http://127.0.0.1:8000/tasks?status=open&q=plan"
```

제안된 검증 프롬프트:

- 이 랩에 대한 검증 단계를 실행하고 저장소가 이제 올바르게 동작하는지 알려주세요.

**수락 검사:**

- [ ] 상태 필터링이 정상입니다.
- [ ] 완료 상태가 유지되며 completed_at이 설정됩니다.
- [ ] 검색은 대소문자를 구분하지 않습니다.
- [ ] 검색 및 상태 필터가 올바르게 조합됩니다.
- [ ] 최종 diff는 검토 가능하며 범위 지정됩니다.

## Slide 10/10 - 제출 (Submission)

**Exercise Instruction:**

제출을 준비하려면 다음 프롬프트를 사용하십시오:

> 이 컨텍스트 창에 있는 모든 메시지를 복사/붙여넣기 가능한 단일 블록으로 내보내십시오. 홈 디렉터리 이름과 같은 개인 식별 정보를 삭제하십시오.

출력물을 텍스트 상자에 붙여넣은 후 제출하십시오.

(This slide requires the learner to paste their own Codex session transcript into a text box and submit it — no additional source content beyond the instruction above.)

---

## 최종 검증 체크리스트 (기록 검증용)

- [x] 총 10개 슬라이드(1/10 ~ 10/10) 모두 순서대로 확인 및 기록 완료 (`grep "^## Slide"` 결과 중복/누락 없음).
- [x] Slide 1: 제목 페이지 (고급 Codex 랩, 2026년 3월 생성) 기록.
- [x] Slide 2: 소개 — 저장소 링크(https://github.com/pavlinhristov/CodexLab), 예상 소요 시간(30~45분) 기록.
- [x] Slide 3: 개요 — Codex 활용 원칙 5가지 및 필수 사항(Git, Codex 앱/클라우드, Python 3.9+) 기록.
- [x] Slide 4: 저장소 설정 — 모든 Bash 명령 블록(clone, venv, pip install, uvicorn 실행) 및 엔드포인트, 권장 프롬프트 원문 그대로 기록.
- [x] Slide 5: 작업 1 — 권장 프롬프트 3개 및 코드베이스 구조(main.py/schemas.py/service.py/store.py/data/tasks.json) 기록.
- [x] Slide 6: 작업 2 — 버그 A(상태 필터링)와 버그 B(완료 상태 미유지) 각각의 재현 curl 명령, 기대 결과, 권장 프롬프트 기록.
- [x] Slide 7: 작업 3 — 검색 기능 요구 사항 4가지, 검증 curl 예시 3개, 권장 프롬프트 기록.
- [x] Slide 8: 작업 4 — 커밋 전 확인 사항, git 명령 5줄, 권장 프롬프트 기록.
- [x] Slide 9: 최종 검증 체크리스트(원본) — curl 검증 명령 6개, 수락 검사 항목 5개 기록.
- [x] Slide 10: 제출 — 제출용 프롬프트 원문 기록 (텍스트 상자 제출은 학습자 개인 세션 데이터이므로 추출 대상 아님).
- [x] 코드 블록(Bash/Plain text)은 원본 명령어를 손실 없이 마크다운 코드 펜스로 변환.
- [x] 지식 점검(퀴즈)이나 드래그앤드롭 매칭형 문항 없음 — 해당 없음.
- [x] 클릭완료형 카드셋 없음 — 해당 없음.
- [x] 이 과정은 "코딩 태스크 트래커" 실습형 랩으로, AI 롤플레이 대화나 시험 문항이 아닌 Codex 활용 실습 가이드 형식임을 확인.
