# API Deployment Practitioner

OpenAI API를 활용한 커스텀 솔루션을 설계·구축·검증·배포하는 방법을 다루는 기술 배포 실무자 과정입니다. API Expert 트랙의 핵심 과정으로, 총 12개 차시(강의 영상 12편 + 강의 노트 12편)로 구성되어 있으며 마지막 차시는 최종 시험입니다.

## 차시 구성

| 차시 | 제목 | 강의 노트 | 강의 영상 |
| --- | --- | --- | --- |
| API01 | API Deployment Foundations | `API01_API Deployment Foundations.md` | `01_API_배포의_기초__실행,_구축_및_검증.mp4` |
| API02 | API Solution Architecture | `API02_API Solution Architecture.md` | `02_API_솔루션_아키텍처.mp4` |
| API03 | API Contracts and Core Interfaces | `API03_API Contracts and Core Interfaces.md` | `03_API_계약과_핵심_인터페이스.mp4` |
| API04 | Model and Capability Selection for API Solutions | `API04_Model and Capability Selection for API Solutions.md` | `04_API_솔루션을_위한_모델_및_기능_선택.mp4` |
| API05 | API Security, Data Handling and Access Controls | `API05_API Security Data Handling and Access Controls.md` | `05_API_보안_데이터_처리_및_접근_제어.mp4` |
| API06 | Context, Data and Retrieval for Grounded API Solutions | `API06_Context Data and Retrieval for Grounded API Solutions.md` | `06_근거_있는_API를_위한_검색.mp4` |
| API07 | Prompt Design, Evals, Moderation, Guardrails and Human Review | `API07_Prompt Design Evals Moderation Guardrails and Human Review.md` | `07_API_동작_검증_및_배포_제어.mp4` |
| API08 | DevOps, Observability and Production Readiness for APIs | `API08_DevOps Observability and Production Readiness for APIs.md` | `08_API_데브옵스와_프로덕션_준비도.mp4` |
| API09 | Realtime, Voice and Multimodal API Experiences | `API09_Realtime Voice and Multimodal API Experiences.md` | `09_텍스트_상자를_넘어선_멀티모달_AI_설계법.mp4` |
| API10 | Deep Research, Images, Distillation and Specialized API Pattern Fit | `API10_Deep Research Images Distillation and Specialized API Pattern Fit.md` | `10__특화된_API_패턴_적합성_평가.mp4` |
| API11 | API Deployment Practice Application | `API11_API Deployment Practice Application.md` | `11_API_배포_준비도__노스스타_사례.mp4` |
| API12 | Final Exam | `API12_API Deployment Practitioner  Final Exam.md` | `12_새벽_3시_재앙을_막는_AI_API_설계.mp4` |

## 차시별 핵심 내용

### API01 — API Deployment Foundations

전체 아키텍처를 설계하기 전에 API를 실제로 호출·구축·검증할 수 있는 기초 역량을 다집니다. 기존 API 호출, 헬스/비즈니스 엔드포인트가 있는 미니멀 로컬 API 구축, 성공/실패 동작 검증을 실습하고 API Foundation Evidence Pack을 만듭니다.

### API02 — API Solution Architecture

고객 문제를 워크플로우·사용자·시스템·데이터 소스로 구성된 아키텍처 요구사항으로 번역합니다. 솔루션 범위(포함/제외/미결정)와 통합 요구사항, 애플리케이션 패턴을 정의해 API Solution Architecture Brief를 작성합니다.

### API03 — API Contracts and Core Interfaces

Responses API와 Chat Completions API를 추론 인터페이스로 비교하고, Conversations API를 활용한 상태 유지 방식을 검토합니다. 요청/응답 형태, 구조화 출력, 오류 처리, 검증 테스트를 정의해 Core Interface and API Contract Plan을 만듭니다.

### API04 — Model and Capability Selection for API Solutions

최신·최고성능 모델이 아니라 워크플로우 요구사항에서 출발해 모델과 기능을 선택합니다. 태스크를 생성/요약/분류/추출/추론/변환/검색 등으로 분류하고 후보를 비교·제외하여 Model and Capability Selection Rationale을 산출합니다.

### API05 — API Security, Data Handling and Access Controls

API가 다루는 데이터 민감도·소유권·최소화·로깅·보존을 매핑하고 인증/인가/최소권한/비밀관리를 구분합니다. 데이터, 접근/비밀, 행동 승인 등 여러 영역을 검토하는 API Security and Data Handling Review로 배포 준비도를 판단합니다.

### API06 — Context, Data and Retrieval for Grounded API Solutions

검색(RAG)이 필요한 경우와 불필요한 경우를 판단하고, 소스의 권위성·최신성·완전성·권한을 평가합니다. 임베딩, 벡터 검색, 메타데이터 필터링 개념을 다루며 Context, Knowledge Access, and Retrieval Design Plan을 작성합니다.

### API07 — Prompt Design, Evals, Moderation, Guardrails and Human Review

프롬프트 동작, 평가, 모더레이션, 가드레일, 휴먼 리뷰를 프로덕션 배포 통제 장치로 다룹니다. OpenAI 모더레이션이 다루는 범위와 다루지 못하는 영역(권한, 정책, 소스 신뢰성 등)을 구분해 API Behavior Validation and Guardrail Plan을 만듭니다.

### API08 — DevOps, Observability and Production Readiness for APIs

로컬에서 동작하는 API와 프로덕션 준비가 된 API의 차이를 다룹니다. 환경/설정/비밀 관리, 헬스·로깅·트레이싱·알림, 장애 대응·롤백·에스컬레이션 소유권을 정의해 API Production Readiness Checklist와 릴리스 추천을 산출합니다.

### API09 — Realtime, Voice and Multimodal API Experiences

텍스트 상자를 넘어선 음성·이미지·실시간·멀티모달 경험을 워크플로우·리스크 설계 관점에서 다룹니다. Speech-to-speech Realtime과 체이닝(STT-텍스트-TTS) 방식을 비교하고 연결 방식(WebRTC/WebSocket/SIP)을 선택해 Realtime and Multimodal Experience Blueprint를 만듭니다.

### API10 — Deep Research, Images, Distillation and Specialized API Pattern Fit

Deep Research, 이미지 이해/생성/편집, 증류(distillation)/최적화 같은 특화 패턴이 표준 패턴으로 부족할 때만 정당화됨을 판단합니다. 소스 품질·권한·추적성·검증 부담을 평가해 Specialized API Pattern Fit Assessment를 작성합니다.

### API11 — API Deployment Practice Application

가상 고객 Northstar Retail Group(HR/여행/복지/IT 정책 API 파일럿)의 실제 배포 사례를 검토하는 실습 과정입니다. 배포 증거 스냅샷을 검토해 아키텍처·계약·보안·관찰가능성 등의 준비 격차를 진단하고 API Deployment Practice Recommendation을 산출합니다.

### API12 — Final Exam

API01~11 전체 과정을 종합하는 최종 평가입니다. 각 문항 해설에 근거가 된 차시가 명시되어 있습니다.

## 학습 순서

1. API01 → API10을 순서대로 영상 시청 후 동일 차시 강의 노트로 복습하며, 기초 실행 → 아키텍처 → 계약/인터페이스 → 모델 선택 → 보안 → 검색/컨텍스트 → 프롬프트/가드레일 → 데브옵스/관찰가능성 → 실시간/멀티모달 → 특화 패턴 순으로 각 차시 결과물(Brief/Plan/Review/Checklist 등)을 누적해서 완성합니다.
2. API11 Northstar Retail Group 실습으로 앞선 내용을 통합 적용합니다.
3. API12 최종 시험으로 학습을 마무리합니다.
