# Realtime, Voice, and Multimodal API Experiences

## Slide 1/48 - Title

Realtime, Voice, and Multimodal API Experiences

Created July 2026

## Slide 2/48 - Introduction

Introduction

A great API experience is not always just a text box. Customers may need to speak in their preferred language, hear guidance aloud, upload a document or image, or move through a task in real time without stopping to type.

Realtime, voice, speech, image, and multimodal API experiences can make these moments more natural and useful, but they also add complexity.

This course treats non-text API experiences as workflow and risk design. You will learn when a non-text modality is relevant, how key modality patterns differ, and how to design experiences with safeguards, fallback paths, and review expectations.

## Slide 3/48 - What you'll learn

What you'll learn

By the end of this course, you'll be able to:

Decide when realtime, voice, speech, image, or multimodal interaction is relevant and when a simpler text or structured-output pattern is enough.
Compare a speech-to-speech Realtime architecture with a chained voice pipeline that uses speech-to-text, a text agent, and text-to-speech.
Select a modality and, for Realtime audio, a WebRTC, WebSocket, or SIP connection method, based on workflow need and other factors.
Design an interaction flow with user control, confirmation, escalation, fallback, and channel handoff.
Identify modality-specific safety, privacy, accessibility, consent, production, and observability checks.

## Slide 4/48 - What you'll produce

What you'll produce

Your course output is a Realtime and Multimodal Experience Blueprint, including:

Your blueprint will answer six questions:

What is the user moment?
Which modality fits?
How should the interaction flow?
What controls and safeguards are needed?
What needs to be verified and monitored?
What is the recommendation?

You'll optionally create this blueprint by completing the recommended exercises across this course.

## Slide 5/48 - Key definitions

Key definitions

These are a few of the key terms you'll need as you move through the course.

**Modality**

A modality is a type of input or output, such as text, speech, audio, image, or generated visual content.

**Multimodal pattern**

A multimodal pattern combines more than one input or output type. For example, a field-support workflow might combine voice input, image input, text guidance, and optional spoken output.

**Fallback**

Fallback is the safe alternate path when the preferred interaction cannot continue. A fallback might switch from voice to text, ask the user to upload a clearer image, route to human support, or stop an action until consent or confidence is resolved.

**Channel handoff**

Channel handoff means moving the interaction from one channel to another, such as from voice to text, from an app to human chat support, or from a live call to an emailed summary.

**Consent and media retention**

Consent means the user has appropriate notice or permission before audio, images, transcripts, or other media are captured or used. Media retention means how long media or derived artifacts are stored, where they are stored, who can access them, and when they are deleted.

**Observability**

Observability means how the business monitors, controls, and improves AI activity. In this course, the focus is modality-specific observability: latency, turn-taking, audio or image quality, transcription or interpretation errors, fallback use, human handoff, user correction, safety flags, consent issues, and quality review.

## Slide 6/48 - Introduction (Module: Deciding when multimodality is relevant)

Deciding when multimodality is relevant

Before choosing realtime, voice, speech, image, or multimodal interaction, you need to decide whether the workflow truly needs a non-text modality.

These experiences can be powerful, but they also introduce extra design, reliability, accessibility, privacy, consent, and fallback considerations.

In this module, you'll start with the user moment: what the user is trying to do, what they can realistically provide, what output they need, and what would fail if the experience stayed text-only.

By the end of the module, you should be able to explain whether a non-text modality is justified, whether text is enough, or whether the team needs more validation before moving forward.

## Slide 7/48 - Start with the workflow need

Start with the workflow need

Before choosing a modality, you need to define your specific workflow need.

That means determining what exactly you need your API to achieve. A workflow need explains clearly what the user is trying to accomplish, what information they can provide, what output they need, and what would fail if the experience stayed text-only.

Start by asking these questions:

What is the user trying to do?
Where is the user?
What input can they provide?
What output do they need?
How quickly do they need it?
What environment affects the interaction?
What would fail if the experience stayed text-only?

These questions prevent a common design mistake: starting with "Let's add voice," "Let's add image upload," or "Let's make it realtime," before proving that the modality actually improves the workflow.

For example, a back-office analyst reviewing policy documents may not need voice at all.

Text may be more searchable, reviewable, and auditable. A warehouse worker wearing gloves may need hands-free input.

A technician diagnosing equipment may need to show a photo. A customer in a live support moment may need spoken guidance because they cannot easily read or type while completing the task.

The right question is not simply "Can we make this multimodal?" It is "What does this user moment require, and how could multimodality better serve that requirement?"

## Slide 8/48 - Decide when a non-text modality may be justified

Decide when a non-text modality may be justified

A non-text modality is justified when it solves a real workflow problem that text alone cannot solve well. That decision should start with the user moment.

It might be useful to use a non-text modality when at least one of these conditions is true:

The user cannot type easily.
The user needs hands-free interaction.
The task depends on spoken language.
The task depends on visual evidence.
The user needs live interaction or low-latency back-and-forth.
The workflow requires multiple input or output types.
Accessibility needs make another modality more effective.

A non-text modality is never justified just because it feels more advanced. Text may still be the better choice when the workflow needs strong reviewability, auditability, accessibility, or reliability.

Text can also be the safer default when latency cannot be supported, media privacy or consent is unresolved, audio or image quality is unreliable, or a text fallback would meet the user need with lower risk.

A helpful decision rule when deciding on multimodality is:

Choose the simplest modality that meets the workflow need safely.

That may be text-only. It may be text plus image input. It may be STT for spoken intake without a full voice agent. It may be TTS for accessible spoken output.

It may be a realtime voice-to-action experience, but only when the workflow needs live spoken interaction and the team can support the latency, safety, consent, confirmation, and fallback requirements.

## Slide 9/48 - Real-world example: Choosing the right modality for a travel disruption workflow

Real-world example: Choosing the right modality for a travel disruption workflow

A travel company wants to add AI assistance to its mobile app for itinerary changes during flight disruptions.

A traveler may be walking through an airport, unable to type easily, and under time pressure. They may need to understand a delay, find a new gate, change a hotel reservation, or ask whether they can still make a connection.

A weak recommendation would be:

"Build a voice assistant because voice is more natural."

That recommendation is not specific enough. It does not explain why voice is needed, what the voice experience should do, or what risks must be addressed.

A stronger recommendation starts with the user moment:

The traveler is mobile and may not be able to type.
The task is time-sensitive.
The system may need to use itinerary context, flight status, airport routing, and booking rules.
The output must be short, clear, and actionable.
Some actions, such as changing a booking, require confirmation before execution.

From that workflow need, the team may recommend a mixed experience:

Systems-to-voice for urgent spoken updates, such as "Your gate changed, and you still have enough time to make the connection."
Voice-to-action for user requests, such as "Find a later hotel check-in and show me the options."
Text fallback for reviewable details, such as the final itinerary, confirmation number, policy terms, or options that require comparison.
Human handoff if the traveler is distressed, the request involves payment or policy exceptions, or the system cannot resolve the trip change safely.

The recommendation should also name what would block the modality:

If latency is too high, realtime voice may frustrate the traveler.
If consent or recording rules are unresolved, voice capture should not launch.
If the system cannot confirm before taking booking actions, voice-to-action is not ready.
If the app can meet the workflow need through a lower-risk text interaction, full realtime voice may not be justified for the first version.

The result is not "voice because voice is cool." It is a modality decision tied to user context, time pressure, action boundaries, confirmation, fallback, and readiness evidence.

## Slide 10/48 - Recommended exercise: Decide when multimodality is relevant

Recommended exercise: Decide when multimodality is relevant

This is an optional practice activity to help you apply what you just learned.

**Purpose:** Practice deciding whether realtime, speech, image, or multimodal design is justified.

**Task:** Review the four workflow examples below and decide whether each should use text-only, realtime, STT, TTS, voice, image input, image output, multimodal, or no deployment until risks are resolved.

An internal legal team wants employees to ask policy questions and receive answers that can be reviewed later.
A technician repairing equipment needs to describe symptoms while uploading a photo of the control panel.
A customer support team wants live captions and notes during service calls.
A product team wants customers to upload photos and voice descriptions for claims intake, but consent, retention, and human-review rules are unresolved.

For each example, explain the workflow need, the modality decision, the main risk or blocker, and the lower-complexity fallback if relevant.

**Estimated time:** 8–10 minutes

**Suggested output and reflection:** Modality relevance decision section of the blueprint.

## Slide 11/48 - Knowledge check

**Question:** A team wants to add voice input and image upload to a customer claims workflow. The first pilot could collect the required information through a text form. Consent and media-retention rules for audio and images are not yet approved. What is the best modality decision?

- Choose to launch with image upload, but only because photos are usually less sensitive than voice recordings.
- Use voice only and remove the image upload.
- Use a lower-complexity text workflow for first pilot, pause multimodal version until consent and retention rules are resolved. **✓ Correct**
- Launch the multimodal workflow because customers will probably prefer it.

A non-text modality should be justified by the workflow and supported by resolved readiness conditions. If text can satisfy the pilot with lower risk and media handling is unresolved, the safer decision is to use the lower-complexity path while validating the multimodal requirements.

## Slide 12/48 - Summary

Summary

Multimodality is valuable when it fits the user moment. It is not automatically better than text, and it should not be selected just because the experience feels more advanced or interactive.

Before selecting voice, realtime, image, or multimodal interaction, define what the user is trying to do, what they can provide, what output they need, how quickly they need it, and what would fail if the experience stayed text-only.

Always remember to use the simplest modality that meets the workflow need safely.

## Slide 13/48 - Introduction (Module: Compare realtime, speech, voice, image, and multimodal patterns)

Compare realtime, speech, voice, image, and multimodal patterns

Once you know a non-text modality may be useful, the next step is to choose the right pattern. Realtime interaction, speech-to-text, text-to-speech, voice-to-action, systems-to-voice, voice-to-voice, image input, image output, and multimodal patterns each solve different workflow problems.

In this module, you'll compare these patterns by what they help the user do, not by how advanced they seem. You'll learn to identify the primary modality, supporting modality, fallback option, and risk tradeoffs so your recommendation is grounded in workflow need rather than feature preference.

## Slide 14/48 - Modalities overview

Modalities overview

This module compares the main interaction patterns used in realtime, speech, voice, image, and multimodal API experiences.

Use this table as a quick reference before you explore each pattern in more detail.

| Pattern | What it means | When it is useful | Key design considerations |
|---|---|---|---|
| Realtime interaction | A low-latency experience where the user and system interact back and forth in the moment. | Use when timing, turn-taking, interruptions, or live responsiveness matter. | Latency, interruption handling, fallback, user control, and monitoring. |
| Speech-to-text (STT) | Converts spoken input into text. | Use when the user can speak more easily than type, typing is difficult, or the task depends on spoken language. | Transcription quality, accents, background noise, consent, correction, and review. |
| Text-to-speech (TTS) | Turns text output into spoken audio. | Use when the user needs to listen instead of read, such as in hands-free or accessibility-supported workflows. | Clarity, pacing, captions or transcript, repeat controls, and text fallback. |
| Voice patterns | Use speech as part of the user experience, including voice-to-action, systems-to-voice, and voice-to-voice flows. | Use when speech better fits the user moment, such as live support, guided tasks, or hands-free workflows. | Turn-taking, interruptions, confirmation, consent, transcription quality, fallback, and user control. |
| Image input | The user provides an image for the system to interpret or reason about. | Use when the workflow depends on visual evidence that would be difficult, slow, or unreliable to describe in text. | Image quality, missing context, privacy, sensitive content, and unclear or incomplete images. |
| Image output | The system creates or transforms visual content. | Use for visual drafts, creative exploration, design mockups, product imagery, or visual communication. | Review criteria, brand fit, rights, safety, accessibility, and human approval. |
| Multimodal patterns | Combine more than one input or output type, such as text, speech, audio, image, or realtime interaction. | Use when the workflow genuinely requires multiple channels to complete the task well. | Added complexity, fallback, monitoring, privacy, accessibility, and whether each modality is truly needed. |

Some of these patterns can overlap.

For example, a voice experience may use speech-to-text, text-to-speech, realtime interaction, tools, and fallback to text. A multimodal experience may combine image input with text output, or spoken input with visual evidence. In this module, you'll look at the patterns separately first so you can combine them more deliberately later.

Remember as you learn more about each modality that the key decision rule is always: Choose the simplest modality that meets the workflow need safely.

## Slide 15/48 - Realtime interaction

Realtime interaction

Use realtime patterns when users need low-latency back-and-forth. Realtime interaction is useful when the experience depends on conversational flow, rapid clarification, or immediate response.

A user may interrupt, correct themselves, pause, or change direction. The system may need to acknowledge that it is working, call a tool, ask a clarifying question, or hand off to another channel.

Realtime design should account for:

**Turn-taking:** Can the system handle natural pauses, overlap, and interruptions?
**Latency:** Is the response fast enough for the user moment?
**Tool-use delays:** What should the user hear or see while the system checks information?
**Corrections:** Can the user correct a misheard word, number, name, or instruction?
**Fallback:** What happens if realtime interaction becomes too slow, unclear, or unreliable?

Realtime is not the same as "the model answers quickly." It is an experience pattern where timing and interaction behavior are part of the design.

A realtime support assistant, for example, may need to say "Let me check that," while a tool call runs.

A realtime field assistant may need to pause while the technician moves or asks it to repeat a step.

Use realtime only when low-latency interaction matters to the workflow. If the user can wait for a structured written response, a simpler asynchronous or text-based pattern may be easier to review, test, and support.

## Slide 16/48 - Speech-to-text

Speech-to-text

Speech-to-text, or STT, turns spoken input into text. Use STT when the workflow needs to capture speech as text, such as:

Transcribing a customer call
Capturing spoken intake from a mobile worker
Creating live notes during a meeting
Generating captions for an event or training session
Letting users dictate information hands-free

STT is often the right pattern when the primary need is input capture, not a full voice conversation. For example, a service agent may dictate case notes after a customer call. The system does not need to talk back; it needs to capture the spoken note accurately, make it editable, and preserve a reviewable record.

Validate STT assumptions before recommending it:

Is the audio quality good enough?
Which languages, accents, or domain terms must be supported?
How will users correct transcription errors?
What privacy, consent, and retention rules apply?
Should transcripts be stored, summarized, reviewed, or deleted?
What happens when confidence is low or the transcript is incomplete?

A transcript is useful because it is reviewable, but it is not automatically correct. For workflows involving customer records, regulated content, names, dates, quantities, or commitments, the design should include correction and confirmation paths.

## Slide 17/48 - Text-to-speech

Text-to-speech

Text-to-speech, or TTS, turns text output into spoken audio. Use TTS when the workflow needs spoken guidance, accessibility support, hands-free output, or a voice response.

For example:

A technician hears troubleshooting steps while using both hands.
A traveler receives a spoken update while moving through an airport.
A user with a visual accessibility need receives spoken output.
A customer hears a short status update while staying in a live support flow.

TTS is not the same as a full voice agent. It may simply be a spoken version of a written response. That distinction matters because a TTS workflow may still rely on text input, structured output, or a non-realtime process behind the scenes.

Validate TTS assumptions before recommending it:

Is spoken output appropriate for the user environment?
Should the user be able to pause, replay, slow down, or switch to text?
Is the spoken response short enough to be useful?
Is a readable text version also available?
Does the voice, tone, and delivery fit the workflow?
Does the content require review before it is spoken?
Will users receive clear disclosure that the TTS voice is AI-generated and not a human voice?

TTS is powerful when the user cannot easily read, but it can be risky when the output is long, complex, sensitive, or likely to be misheard.

Important details such as policy terms, prices, dates, medical-adjacent guidance, legal language, or confirmation numbers should generally be available in text as well.

## Slide 18/48 - Voice-to-action, systems-to-voice, and voice-to-voice

Voice-to-action, systems-to-voice, and voice-to-voice

Voice patterns are useful when spoken interaction is central to the workflow. The three patterns you'll compare most often are voice-to-action, systems-to-voice, and voice-to-voice.

Before choosing a voice interaction pattern, choose the voice architecture. Architecture defines how the application processes audio; the interaction pattern defines what the experience helps the user do.

**Speech-to-speech Realtime:** The model handles live audio input and output directly. Use this architecture when the workflow needs natural, low-latency conversation, interruptions, turn-taking, or realtime tool use.

**Chained voice pipeline:** The application explicitly sequences speech-to-text, a text agent, and text-to-speech. Use this architecture when the workflow needs visible intermediate text, durable transcripts, deterministic checks or approvals, or reuse of an existing text agent.

For Realtime audio, choose the connection method based on where the application captures and plays audio:

Use WebRTC for browser and mobile clients that capture or play audio directly.
Use WebSocket when a server already receives raw audio from a media pipeline, call system, or worker.
Use SIP for telephony voice agents. Confirm current model support before using SIP for translation or transcription.

Connection methods and supported model behavior are volatile. Validate the current OpenAI documentation immediately before implementation.

**Voice-to-action:** The user speaks a request, and the system reasons through it, may use tools, and may complete a bounded task. This pattern can support workflows such as scheduling, looking up account status, routing a request, or preparing a task handoff. Use voice-to-action when the user needs to get work done by speaking and the system can safely complete or prepare the action. This pattern requires strong boundaries. Sensitive or irreversible actions should require confirmation before execution.

**Systems-to-voice:** The system turns context into spoken guidance or alerts. This pattern can support workflows such as live travel updates, equipment alerts, accessibility guidance, or operational notifications. Use systems-to-voice when users need timely spoken context from existing systems. The design should avoid overwhelming users with unnecessary audio, and it should define when a spoken alert is helpful versus intrusive.

**Voice-to-voice:** Spoken interaction continues across language, task, or context changes. This may include live translation or a voice experience where the user speaks naturally and hears a spoken response. Use voice-to-voice when the workflow depends on spoken continuity. This pattern requires careful attention to language, latency, turn-taking, consent, clarification, and escalation.

All three patterns require safeguards:

Provide clear disclosure that the TTS voice is AI-generated and not a human voice. Confirm any additional notice requirements with the appropriate owner or legal reviewer.
Tell users when the system is checking information or using a tool.
Ask for confirmation before sensitive or consequential actions.
Provide a way to pause, stop, correct, or switch channels.
Route to human support when the conversation becomes unsafe, sensitive, or unresolved.

## Slide 19/48 - Image input

Image input

Image input lets a workflow use visual evidence.

Common image inputs include:

Photos of damaged items, products, equipment, rooms, or documents
Screenshots from software workflows
Diagrams or forms
Visual context from a worksite
Images of labels, serial numbers, panels, or receipts

Use image input when the workflow genuinely depends on something visible.

For example, a field technician may need to show the state of an equipment panel.

A support team may need a screenshot of an error. An insurance workflow may need photos to support claims intake.

Validate image input assumptions before recommending it:

Is the image quality likely to be good enough?
What should happen if the image is blurry, incomplete, or poorly lit?
Does the image contain personal, sensitive, confidential, or regulated information?
Does the user have permission to upload the image?
Should the model ask for clarification before interpreting the image?
What should be reviewed by a human before action is taken?

Image input can make a workflow more grounded, but it can also create false confidence. A model may interpret a visible detail incorrectly or miss context outside the image. Use image input as evidence, not as the only basis for high-risk decisions.

## Slide 20/48 - Image output

Image output

Image output creates or transforms visual content. In this course, image output matters when it is part of a realtime, voice, or multimodal experience.

For example, a user might describe a design change by voice, receive a generated visual draft, and then refine it.

Or a support workflow might produce a simple visual guide that shows where to click next.

Validate image output assumptions before recommending it:

Is image output needed, or would text, a diagram, or a structured checklist be enough?
Does the output require brand, legal, accessibility, or human review?
Are rights and approved-use expectations clear?
Can users access a non-visual alternative?
Could the image be misleading, unsafe, or mistaken for an official output?
Is the image being created for internal ideation, customer-facing use, training, or operational guidance?

Do not treat image output as a default enhancement. Visual content can carry brand, rights, representation, accessibility, and safety concerns. For many workflows, a structured text output or a simple human-authored visual may be the safer first version.

## Slide 21/48 - Multimodal patterns

Multimodal patterns

Multimodal patterns combine more than one input or output type.

Here are some examples of combined multimodal patterns, a real-world situation they might apply to, and why the combination fits that situation:

| Multimodal pattern | Real-world situation | Why this combination fits |
|---|---|---|
| Voice input plus text output | A sales rep leaves a spoken account update after a customer call and receives a structured text summary for CRM review. | Speaking is faster in the moment, but text is easier to review, edit, audit, and store. |
| Voice input plus image input | A field technician takes a photo of damaged equipment and verbally describes what they are seeing. | The image provides visual evidence, while the spoken note adds context that may not be obvious from the image alone. |
| Image input plus spoken guidance | A warehouse worker shows a damaged shipment label or package condition and receives spoken next-step guidance while their hands are occupied. | The image helps the system inspect the situation, while spoken output supports hands-free action. |
| Text input plus generated image output | A marketing team enters a short campaign concept and receives visual mockups to compare creative directions. | Text captures the intent, while image output helps the team explore visual options quickly. |
| Realtime voice plus tool use plus written confirmation | A travel support agent speaks with a customer, checks available rebooking options through a tool, and sends a written confirmation before changes are finalized. | Realtime voice supports live conversation, tool use retrieves or prepares the action, and written confirmation creates a reviewable approval step. |
| Image upload plus STT transcript plus structured case summary | An insurance adjuster uploads property-damage photos, dictates observations, and receives a structured claim summary for review. | The image captures visual evidence, the transcript captures spoken context, and the structured summary supports downstream case handling. |

Use multimodal patterns only when the workflow genuinely requires multiple modalities. A good multimodal design explains how the modalities interact.

To deploy multimodal patterns you must first capture:

**Primary modality:** Which modality carries the main workflow?
**Supporting modality:** Which modality adds evidence, accessibility, speed, or context?
**Switch point:** When should the user move from one modality to another?
**Failure path:** What happens if one modality fails?
**Confirmation point:** What must be confirmed before action?
**Review path:** What should be visible to a human or downstream system?

For example, in a retail returns workflow, image input may show product damage, voice input may capture the associate's quick note, and written confirmation may preserve the refund or exchange decision.

## Slide 22/48 - Recommended exercise: Match workflows to modality patterns

Recommended exercise: Match workflows to modality patterns

This is an optional practice activity to help you apply what you just learned.

**Purpose:** Practice identifying the right realtime, speech, image, or multimodal pattern.

**Task:** Identify when the workflow examples below should map to STT, TTS, voice-to-action, systems-to-voice, voice-to-voice, image input, image output, realtime, multimodal, or text-only patterns.

A support center wants live transcripts of customer calls for review.
A logistics worker needs spoken route updates while driving.
A customer wants to describe a request by voice and have the system check account status.
A technician needs to upload a photo of an equipment panel and ask for troubleshooting guidance hands-free.
A design team wants to generate internal concept visuals after a voice brainstorming session.

**Estimated time:** 10–12 minutes

**Suggested output and reflection:** Selected modality pattern and rationale.

## Slide 23/48 - Knowledge check

**Question:** Match each workflow need to the best-fit modality pattern.

- Let a user speak a request that may trigger a bounded tool action → Voice-to-action **✓ Correct**
- Combine voice input, photo upload, and written confirmation → Multimodal pattern **✓ Correct**
- Capture spoken customer calls as editable text → Speech-to-text **✓ Correct**
- Use a photo or screenshot as evidence in the workflow → Image input **✓ Correct**
- Provide spoken guidance from system context → Systems-to-voice **✓ Correct**

All pairs matched correctly!

## Slide 24/48 - Summary

Summary

You've now compared realtime, speech, voice, image, and multimodal patterns as workflow choices, not just technical features. For voice, you also compared speech-to-speech Realtime with a chained pipeline of speech-to-text, a text agent, and text-to-speech. You also matched WebRTC, WebSocket, or SIP to where audio is captured and played.

The key lesson is to choose the simplest pattern that meets the workflow need safely. A strong recommendation explains why the modality is justified, what complexity it adds, and how the team will manage latency, privacy, consent, accessibility, fallback, reliability, and monitoring before deployment. Multimodal design is most valuable when each modality has a clear purpose in helping the user complete the task.

## Slide 25/48 - Introduction (Module: Design the interaction flow)

Design the interaction flow

After selecting a modality, you need to design how the experience actually works from start to finish.

Realtime, voice, image, and multimodal workflows often include more decision points than text-only experiences because the system may need to handle unclear audio, incomplete context, image quality issues, interruptions, confirmation, fallback, or handoff.

In this module, you'll map the interaction flow as a design and readiness artifact. You'll define how the interaction starts, what the user provides, how the system clarifies or responds, where the user keeps control, and when the experience should confirm, fall back, escalate, or stop.

## Slide 26/48 - Map the interaction

Map the interaction

Once the modality is justified, your next step is to map the interaction flow.

An interaction flow explains how the user and system move through the multimodal experience. It should show what happens at the start, what input the user provides, what context the system uses, how the system responds, where confirmation happens, and how fallback or escalation works.

| Flow question | What to capture | Example |
|---|---|---|
| How does the interaction begin? | The start of the interaction and what the user is trying to do. | A field technician opens a voice assistant and asks for help diagnosing equipment damage. |
| What does the user provide? | The user input and any context the system needs to interpret it. | The technician speaks a symptom description and uploads a photo of the equipment panel. |
| How does the system respond? | Whether the model can answer directly, needs a clarifying question, or should ask for confirmation. | The system asks which machine model is affected before giving troubleshooting steps. |
| What happens next? | Whether the flow ends with a response, human review, escalation, fallback, or a system or tool action. | The system gives spoken guidance, creates a draft service ticket, and asks the technician to confirm before submission. |

The flow should be specific enough that another team could test the experience. For example, "the user asks for help" is too vague.

A stronger flow says:

1. The user starts a voice interaction in the mobile app.
2. The system gives a short greeting and asks what the user needs.
3. The user describes the issue by voice.
4. The system transcribes the request and asks for missing details if needed.
5. The system retrieves approved context or checks a tool if the workflow requires it.
6. The system provides a short spoken response and a written summary.
7. If the response requires action, the system asks for explicit confirmation.
8. If audio is unclear, latency is high, or the request is sensitive, the system switches to text or routes to human support.

A strong flow helps the team test more than the ideal path. It makes the experience's controls, failure points, and handoffs visible.

The exact implementation for an interaction flow will then depend on the application, interface, and API pattern.

The important design principle is that the team should define the flow before building the experience. That means the application should know what stage the user is in, what context has been captured, whether clarification is needed, whether confirmation is required, and what fallback or escalation path applies.

The simplified example below shows a field-support interaction where a technician speaks a symptom and the application decides what should happen next:

```typescript
type FlowStage = "start" | "capture_symptom" | "clarify" | "respond" | "complete";

type InteractionFlow = {
  stage: FlowStage;
  symptom?: string;
  clarificationNeeded?: boolean;
};

function handleUserInput(flow: InteractionFlow, spokenInput: string): InteractionFlow {
  // Move from start into the first capture step.
  // The same call can then continue processing the spoken input.
  if (flow.stage === "start") {
    flow.stage = "capture_symptom";
  }

  if (flow.stage === "capture_symptom") {
    flow.symptom = spokenInput;

    if (needsClarification(spokenInput)) {
      flow.stage = "clarify";
      flow.clarificationNeeded = true;
      return flow;
    }

    flow.stage = "respond";
    return flow;
  }

  if (flow.stage === "clarify") {
    flow.symptom = `${flow.symptom ?? ""} ${spokenInput}`.trim();
    flow.clarificationNeeded = false;
    flow.stage = "respond";
    return flow;
  }

  if (flow.stage === "respond") {
    createTroubleshootingGuidance(flow.symptom ?? "");
    flow.stage = "complete";
    return flow;
  }

  return flow;
}

function needsClarification(input: string): boolean {
  return input.trim().length < 10;
}

function createTroubleshootingGuidance(symptom: string): void {
  console.log(`Create guidance for: ${symptom}`);
}
```

This example is intentionally simple. It shows that an interaction flow is not just a sequence of messages. It is a decision path.

The application captures the technician's spoken symptom, checks whether the input is specific enough, asks for clarification if needed, provides guidance when the context is sufficient, and routes to fallback when it is not.

## Slide 27/48 - Define user control

Define user control

User control is essential in realtime, voice, and multimodal experiences.

Because these interactions can feel more immediate than text, users need clear ways to pause, stop, correct, confirm, or switch channels. This is especially important when the system is recording audio, interpreting images, speaking aloud, using tools, or preparing an action.

User control should be designed into the flow, not added as an afterthought.

For example:

A voice assistant should not continue speaking through a long explanation if the user says "pause" or "stop."
A claims intake workflow should let the customer remove or replace an uploaded photo.
A field-support workflow should let the technician say "That's not what I meant," or switch to text if the environment is noisy.

Confirmation is especially important for tool actions and sensitive steps.

The system may help prepare an action, but it should not take a consequential step such as sending a message, updating a record, changing a booking, filing a claim, or approving a recommendation unless the approved workflow allows it and the required confirmation or human review has occurred.

The exact implementation for adding user controls depends on the application, interface, and API pattern.

The important design principle is that user controls should be handled by the application layer before the system continues speaking, recording, storing media, or taking action.

The simplified example below shows how an application might add basic pause and stop controls to a realtime, voice, or multimodal interaction:

```typescript
type SessionStatus = "listening" | "paused" | "stopped";

const session = {
  status: "listening" as SessionStatus,
};

// Check for user control commands before continuing the interaction.
function handleUserInput(userInput: string): string {
  const command = userInput.toLowerCase().trim();

  if (command.includes("pause")) {
    return pauseSession();
  }

  if (command.includes("stop") || command.includes("cancel")) {
    return stopSession();
  }

  // Continue the normal interaction if no control command is detected.
  return continueInteraction(userInput);
}

function pauseSession(): string {
  stopRecording();
  stopSpeaking();

  session.status = "paused";

  return "Paused. You can resume when you are ready, or say stop to end the interaction.";
}

function stopSession(): string {
  stopRecording();
  stopSpeaking();

  session.status = "stopped";

  return "Stopped. The interaction has ended, and no further action will be taken.";
}

function continueInteraction(userInput: string): string {
  return `Continuing with: ${userInput}`;
}

// Placeholder functions for the application's actual implementation.
function stopRecording() {
  // Stop capturing audio input.
}

function stopSpeaking() {
  // Stop any spoken output currently playing.
}
```

Once again, this example is intentionally simple. It shows that user control should be checked before the system continues the interaction.

In a production workflow, the application may also need to clear pending actions, save a transcript, update the session state, or route the user to a different channel.

But the core pattern stays the same: pause and stop controls should interrupt the flow immediately and predictably.

## Slide 28/48 - Define fallback paths

Define fallback paths

A fallback path is the safe alternate route when the preferred experience cannot continue.

Realtime, voice, and multimodal experiences have more ways to fail than text-only workflows. The design should name the most likely failure paths and what the system should do.

Plan fallback for situations like poor audio, transcription errors, unclear images, or high latency. The flow should also define when the user should switch to text or human support.

Fallback does not always mean failure. Sometimes it is the best way to preserve trust.

If an image is unclear, the system can ask for a clearer image or switch to a text description.
If spoken input is misheard, the system can repeat what it understood and ask the user to confirm.
If the user asks for a sensitive action, the system can route to a human reviewer.
If latency becomes too high for a live voice interaction, the system can switch to a written update.

A useful fallback statement is:

"When [condition] happens, the system will [safe behavior], and the user can [next action]."

In different multimodal contexts, some examples might be:

When audio is unclear, the system repeats what it heard and asks the user to confirm or type the key detail.
When image quality is too low, the system explains that it cannot interpret the image confidently and asks for a clearer image or text description.
When a requested action is sensitive, the system prepares a draft and routes it to human review instead of executing it.
When consent is unresolved, the system does not capture media and offers a text-only path.

As with other implementations, the exact process will depend on the application and API pattern.

The important design principle here is that the application should know when the experience can continue, when it should ask for clarification, and when it should fall back or escalate instead of guessing.

The simplified example below builds on the previous one, where a technician speaks a symptom in a field-support workflow. The application checks whether the input is usable and decides whether to respond, ask for more detail, switch to fallback, or escalate to support:

```typescript
type NextStep = "respond" | "clarify" | "fallback" | "escalate";

type SupportInput = {
  spokenSymptom: string;
  inputQualityScore: number; // Application-defined signal, not a required API field.
  userCanContinueByVoice: boolean;
  safetyRiskDetected: boolean;
};

function decideNextStep(input: SupportInput): NextStep {
  // Escalate if the request appears unsafe or outside the approved support path.
  if (input.safetyRiskDetected) {
    return "escalate";
  }

  // Switch channels if voice is not working for the user.
  if (!input.userCanContinueByVoice) {
    return "fallback";
  }

  // Ask for clarification when the input is too short, vague, or low quality.
  if (
    input.spokenSymptom.trim().length < 10 ||
    input.inputQualityScore < 0.7
  ) {
    return "clarify";
  }

  // Continue when the input is clear enough for the approved workflow.
  return "respond";
}

function handleSupportInput(input: SupportInput): string {
  const nextStep = decideNextStep(input);

  if (nextStep === "clarify") {
    return "I need one more detail before I continue. What is the main issue you want help with?";
  }

  if (nextStep === "fallback") {
    return "Voice does not seem to be working well here. Let's switch to text or another approved channel.";
  }

  if (nextStep === "escalate") {
    return "This needs review by a support owner before I provide guidance.";
  }

  return "I can continue with the approved troubleshooting flow.";
}
```

This intentionally simple example shows that fallback and escalation should be part of the interaction logic, not improvised after the experience fails.

The application checks whether the spoken input is empty, unclear, too vague, or low confidence before deciding what to do next.

## Slide 29/48 - Real-world example: Designing a safe travel-support interaction flow

Real-world example: Designing a safe travel-support interaction flow

An airline wants a disruption-support assistant for travelers whose flights are delayed or canceled. A traveler can speak to the assistant while moving through the airport, upload a boarding pass or itinerary screenshot, and receive rebooking options.

Because this workflow may affect a real booking, the flow needs clear confirmation, fallback, and escalation points.

A weak interaction flow might be:

"The traveler talks to the assistant, uploads their itinerary, and gets rebooked."

That flow is too vague. It does not explain how the system handles a blurry screenshot, misheard travel details, unavailable rebooking options, policy exceptions, or confirmation before changing a reservation.

A stronger interaction flow might look like this:

| Flow moment | What the experience does |
|---|---|
| Start of interaction | The assistant explains that it can help compare rebooking options, but it will not change the booking without confirmation. |
| User input and context capture | The traveler describes the issue by voice and may upload a boarding pass or itinerary screenshot. The assistant confirms key details, such as traveler name, flight number, destination, and travel date. |
| Clarification | If the screenshot is unclear or the spoken input is misheard, the assistant asks a short follow-up question instead of guessing. |
| Response | The assistant presents a small set of eligible options, such as the next available flight, a later same-day flight, or instructions to speak with an agent if no suitable option is available. |
| Confirmation or human review | Before changing the booking, the assistant summarizes the selected option in text and asks the traveler to confirm. If the change involves an exception, special assistance, payment issue, or policy uncertainty, it routes to a human agent. |
| Fallback | If latency is too high, inventory is unavailable, the uploaded image cannot be interpreted, or the traveler says "stop," the assistant pauses the flow and offers a text path or human handoff. |

The stronger flow does not assume that voice, image input, or tool actions will always work perfectly. It gives the traveler control, confirms important details, prevents unapproved booking changes, and defines when the experience should clarify, fall back, or escalate.

## Slide 30/48 - Recommended exercise: Design a safe multimodal interaction flow

Recommended exercise: Design a safe multimodal interaction flow

This is an optional practice activity to help you apply what you just learned.

**Purpose:** Practice designing a safe interaction flow.

**Task:** Draft an interaction flow for this field-support workflow:

A technician in a noisy plant uses voice to describe an equipment symptom, uploads a photo of the control panel, and needs short spoken troubleshooting guidance plus a written summary.

The assistant should ask for clarification when audio or image input is unclear, should not recommend unsafe steps, and should not submit a service ticket without confirmation or review.

Include:

User control
Confirmation
Fallback
Channel handoff
Escalation points

**Estimated time:** 8–10 minutes

**Suggested output and reflection:** Interaction flow section of the blueprint, including user control, confirmation, fallback, and escalation points.

## Slide 31/48 - Knowledge check

**Question:** A field-support assistant accepts voice input and image uploads. The proposed flow lets the technician ask for help, upload a photo, and receive spoken troubleshooting steps. The flow does not explain how the technician can stop the interaction, correct a misheard detail, switch to text, or escalate to a human reviewer. What is the biggest gap in the interaction flow?

- It should automatically execute every recommended troubleshooting step.
- It does not include enough product features.
- It should remove all written text because the workflow is hands-free.
- It is missing user control, correction, channel handoff, and escalation points. **✓ Correct**

A safe multimodal flow should show how users pause, stop, correct transcription or image interpretation, switch channels, and escalate when the experience becomes unclear, unsafe, or unresolved.

## Slide 32/48 - Summary

Summary

A strong multimodal experience is not defined by how many modalities it uses. It is defined by how clearly the workflow guides the user from need to outcome while preserving control, safety, and trust.

In this module, you learned to treat the interaction flow as a design and readiness artifact. An effective flow shows where the experience can continue, where it needs clarification, where the user must confirm, and where the system should fall back or escalate instead of guessing.

When those decision points are clear, the experience becomes easier to test, monitor, support, and hand off to implementation teams.

## Slide 33/48 - Introduction (Module: Add safety, privacy, accessibility, consent, and production checks)

Add safety, privacy, accessibility, consent, and production checks

A realtime, voice, image, or multimodal experience is not ready just because the interaction flow looks useful. These modalities can capture sensitive audio, images, transcripts, metadata, and user context, and they can feel immediate or persuasive in ways that increase risk.

In this module, you'll identify the checks that should surround the experience before it moves toward prototype, pilot, or broader use.

You'll focus on safety boundaries, human review, privacy and media handling, accessibility, consent, fallback, and modality-specific observability signals that help the team understand whether the experience is working responsibly.

## Slide 34/48 - Safety and human review

Safety and human review

Safety and human review define what the experience can do on its own, what it must not do, and when a person needs to step in.

This matters because realtime, voice, image, and multimodal workflows can feel immediate and action-oriented, even when inputs are incomplete or uncertain.

Your safety and review needs define what a multimodal experience is allowed to do on its own, what it should never do, and when a human needs to step in.

To answer that, define three things:

| Safety decision | Guiding question | What to capture |
|---|---|---|
| Allowed actions | What can the experience do on its own? | Low-risk responses, routine guidance, information collection, summaries, or draft outputs that fit the approved workflow. |
| Hard boundaries | What should the experience never do? | Advice, inferences, decisions, or actions that are unsafe, unsupported, outside policy, or beyond the system's approved role. |
| Review and escalation points | When does a human need to step in? | Moments that require confirmation, human review, live escalation, or takeover because the interaction is sensitive, high-impact, uncertain, or unresolved. |

Once this has been established, you can then use these further questions to create a simple decision path:

| Situation | Safer response pattern |
|---|---|
| The request is clear, low-risk, and within scope. | Respond normally using the approved workflow. |
| The input is incomplete, unclear, or low confidence. | Ask a clarifying question before continuing. |
| The output may affect a customer, record, system, or business decision. | Require confirmation, human review, or both. |
| The request is outside the approved workflow or asks for unsafe guidance. | Refuse, safely redirect, or provide only allowed information. |
| The situation remains sensitive, high-risk, or unresolved. | Escalate to the approved human owner or handoff path. |

For example, a photo-based claims intake assistant might help collect information, summarize visible damage, and explain next steps.

It should not make a final coverage decision unless the approved workflow, controls, and human-review process allow it.

If the photo is unclear, the assistant should ask for a clearer image or route the case for review instead of guessing.

Similarly, a travel rebooking assistant might compare available options and prepare a change for review.

It should not change a booking, charge a fee, or apply a policy exception unless the user has confirmed the action and the workflow allows it.

If the request involves special assistance, payment uncertainty, or policy ambiguity, the safer path is escalation.

Exact safety implementations will depend on the application and workflow. The important design principle is that safety and review checks should happen before the system gives guidance, updates a record, or takes an action.

This simplified example shows how a claims intake assistant might decide whether to continue, ask for clarification, require review, escalate, or refuse:

```typescript
type Decision = "continue" | "clarify" | "review" | "escalate" | "refuse";

type IntakeRequest = {
  intent: "collect_info" | "summarize_next_steps" | "update_record" | "decide_coverage" | "estimate_payout";
  confidence: number;
  imageIsClear: boolean;
  isSensitive: boolean;
};

function safetyGate(request: IntakeRequest): Decision {
  // Hard boundary: the assistant must not make final claim decisions.
  if (request.intent === "decide_coverage" || request.intent === "estimate_payout") {
    return "refuse";
  }

  // Low-confidence or unclear media needs clarification before continuing.
  if (request.confidence < 0.7 || !request.imageIsClear) {
    return "clarify";
  }

  // Record updates need human review or explicit approval.
  if (request.intent === "update_record") {
    return "review";
  }

  // Sensitive cases should route to a human owner.
  if (request.isSensitive) {
    return "escalate";
  }

  // Low-risk intake and summaries can continue.
  return "continue";
}
```

This example shows the core pattern: define what the system can do, what it must not do, and when a person needs to step in.

In this case, the assistant can collect information and summarize next steps, but it cannot decide coverage or estimate payout.

If the image is unclear, confidence is low, the case is sensitive, or a record may be affected, the workflow changes before the assistant continues.

Remember that human review does not need to appear after every step. It should appear at the points where risk, uncertainty, policy sensitivity, or business impact increases. It should keep the experience useful while making sure the system does not overstep its approved role.

## Slide 35/48 - Privacy and media handling

Privacy and media handling

Media handling defines what happens to audio, images, transcripts, screenshots, video frames, or other non-text inputs once a user provides them.

This matters because multimodal experiences often capture more than the user's direct request.

A photo may include background information, a voice recording may include another person, and a transcript may become a record that needs to be stored, reviewed, or deleted according to customer policy.

A useful media-handling review should answer five practical questions:

| Review area | What to clarify |
|---|---|
| Purpose | What media is captured, and why is it needed for the workflow? |
| Access and storage | Who can access the media, where is it stored, and how long is it retained? |
| User control | Can the user remove, replace, or correct the media or its interpretation? |
| Derived artifacts and logs | What artifacts are created from the media, such as transcripts, summaries, embeddings, labels, or structured fields, and what must not appear in logs? |
| Prohibited capture or reuse | What should never be recorded, stored, replayed, logged, reused, or retained? |

The team should also identify which customer policy, privacy, legal, security, or accessibility reviews are needed before the experience moves forward.

Accessibility belongs in this readiness review also; a multimodal experience should not assume every user can speak, hear, see, type, or interpret visual output in the same way.

The design should include a workable path for users who cannot use the preferred modality or do not want to use it.

A practical accessibility review asks whether the experience gives users another way to receive, review, or control important information:

| Accessibility need | Design response |
|---|---|
| The user cannot hear or does not want audio. | Provide captions, transcripts, or readable text alternatives. |
| The user cannot rely on visual output. | Provide non-visual fallback or text description where appropriate. |
| Spoken details are important. | Make those details available in text so they can be reviewed later. |
| The interaction is moving too quickly. | Let the user pause, repeat, slow down, or switch channels. |
| Visual output is used. | Use readable formatting, clear contrast, and accessible layout expectations. |
| The proposed modality does not work for the user. | Provide a fallback path, such as text, human handoff, or another approved channel. |

A modality that helps one user may exclude another if fallback and accessibility are not designed from the start.

For example, spoken guidance may help a user who is working hands-free, but it may not work for a user in a noisy environment or for someone who needs written instructions for review.

Image output may support visual exploration, but it may need a text alternative for users who cannot rely on the image alone.

The exact implementation for this will depend on the interface and workflow. The important design principle is that a multimodal experience should not assume every user can speak, hear, see, or use the same channel.

This simplified example shows how an application might choose accessible output options for a multimodal response:

```typescript
type UserNeeds = {
  prefersText: boolean;
  needsCaptions: boolean;
  needsImageDescription: boolean;
};

type MultimodalResponse = {
  spokenGuidance?: string;
  textSummary?: string;
  imageUrl?: string;
  imageDescription?: string;
  captions?: string;
};

function prepareAccessibleResponse(
  response: MultimodalResponse,
  userNeeds: UserNeeds
): MultimodalResponse {
  const accessible = { ...response };

  // Provide text when the user cannot or does not want to rely on audio.
  if (userNeeds.prefersText && response.spokenGuidance) {
    accessible.textSummary = response.textSummary ?? response.spokenGuidance;
  }

  // Provide captions or transcript for spoken output.
  if (userNeeds.needsCaptions && response.spokenGuidance) {
    accessible.captions = response.spokenGuidance;
  }

  // Provide a non-visual alternative for image output.
  if (userNeeds.needsImageDescription && response.imageUrl) {
    accessible.imageDescription =
      response.imageDescription ?? "Image description is required before showing this result.";
  }

  return accessible;
}
```

This example shows the core pattern: keep the multimodal experience flexible.

If the system speaks, provide a text alternative. If it shows an image, provide a non-visual alternative. If the user needs captions, transcripts, or another channel, the application should make that path available instead of forcing one modality.

## Slide 36/48 - Identify modality-specific production and observability signals

Identify modality-specific production and observability signals

Observability helps the team monitor, control, and improve AI activity.

For realtime, voice, image, and multimodal workflows, that means looking beyond basic API health.

The API may be reachable, but the experience can still fail if users are interrupted at the wrong time, audio is misheard, images are unclear, fallback is overused, or users cannot complete the task safely.

A useful observability review answers one practical question:

Can the team see whether the modality is helping the workflow, or creating new friction, risk, or support burdens?

To answer that, group modality-specific signals into a few areas.

| Signal area | What to monitor | What it helps the team decide |
|---|---|---|
| Responsiveness and flow | Latency, response timing, turn-taking, pauses, interruptions, overlaps, and corrections. | Is the experience fast and natural enough for the user moment, or should the team adjust the flow, slow it down, add clearer controls, or use a simpler fallback? |
| Input quality and interpretation | Audio quality, image quality, transcription errors, interpretation errors, low-confidence inputs, unclear images, or misread visual evidence. | Can the system continue safely, or should it ask for clarification, request a new image, switch channels, or route to a human? |
| Workflow and dependency delays | Tool-call delay, system-action delay, retrieval delay, or downstream system latency. | Are connected steps creating unacceptable delays, especially in realtime or live support workflows? |
| Fallback and handoff behavior | How often users switch to text, retry, ask for human support, abandon the interaction, pause, stop, correct, or take over. | Is fallback working as intended, or is high fallback use revealing a design, reliability, accessibility, or trust problem? |
| Safety, privacy, accessibility, and consent flags | Unresolved media-handling issues, missing consent, accessibility blockers, unsafe requests, sensitive actions, or human-review triggers. | Should the experience continue to prototype or pilot, or does it need review, remediation, escalation, or a pause before broader use? |
| Quality and improvement evidence | User feedback, reviewer notes, repeated failure patterns, escalation reasons, or post-interaction quality review. | What should the team improve before expanding the experience? |

For example:

A travel rebooking assistant might monitor how often users interrupt spoken options, how often booking changes require written confirmation, and how often policy exceptions route to a human agent.

A photo-based claims intake assistant might monitor unclear-image rate, image replacement rate, interpretation corrections, and adjuster handoff rate.

A retail returns assistant might monitor voice correction rate, refund-confirmation abandonment, policy-exception escalation, and text fallback usage.

These signals help the blueprint show whether the experience is ready to test, needs tighter controls, should use a simpler modality, or requires review before moving forward.

## Slide 37/48 - Real-world example: Identifying multimodal readiness blockers

Real-world example: Identifying multimodal readiness blockers

An insurance company wants a photo-and-voice claims intake experience. Customers can upload photos of vehicle damage, describe what happened by voice, and receive next-step guidance.

This could be a strong multimodal fit because the workflow depends on both visual evidence and spoken description.

Customers may find it easier to explain what happened by voice while uploading photos from a mobile device.

But the modality is not automatically ready.

A readiness review should identify blockers such as:

**Safety and human review**
The system should not make final coverage, liability, or payout decisions unless the approved workflow supports that.
Sensitive claims should route to a human reviewer.
The system should distinguish intake guidance from final determination.

**Privacy and consent**
The customer must receive appropriate notice before audio or photos are captured.
Media retention rules must be defined.
The customer should know whether audio, photos, transcripts, summaries, or metadata are stored.
Photos may contain people, license plates, addresses, or other sensitive information.

**Accessibility**
Customers who cannot or do not want to speak should be able to type.
Customers who cannot upload photos should have an alternate path.
Spoken next steps should also be available in readable text.

**Fallback**
If a photo is unclear, the system should ask for another image or accept a text description.
If the voice transcript is uncertain, the system should repeat the key details and ask the customer to confirm.
If the customer is distressed or the claim is complex, the system should route to human support.

**Observability**
The team should monitor image-quality issue rate.
The team should track transcription errors and user corrections.
The team should review fallback and human-handoff rate.
The team should capture unresolved consent or retention flags before broader rollout.

A weak recommendation in this context would say:

"Proceed because photo and voice make claims intake easier."

A more effective recommendation would instead say:

"This is a plausible multimodal fit, but it is not ready for broader use until consent, retention, accessibility fallback, human-review boundaries, and modality-specific observability signals are defined. A limited prototype may be appropriate with synthetic or approved test data, no final claim decisions, and clear user controls."

## Slide 38/48 - Recommended exercise: Identify multimodal readiness blockers

Recommended exercise: Identify multimodal readiness blockers

This is an optional practice activity to help you apply what you just learned.

**Purpose:** Practice identifying readiness blockers for multimodal deployment.

**Task:** Review a multimodal deployment example and identify safety, privacy, accessibility, consent, and production-readiness blockers.

Use this context: A customer wants to pilot a voice-and-image intake assistant for field incidents. Users can upload photos, describe what happened by voice, and receive next-step guidance.

The team has not yet confirmed media retention rules, accessibility fallback, or what human review is required before guidance affects an incident record.

Identify:

Top safety or human-review blocker
Top privacy, consent, or media-handling blocker
Top accessibility or fallback blocker
One modality-specific observability signal
Recommended next safe step

**Estimated time:** 8–10 minutes

**Suggested output and reflection:** Readiness blocker summary for the blueprint, including the top 2–3 blockers across safety, privacy, accessibility, consent, media handling, or modality-specific observability, plus one recommended next step.

## Slide 39/48 - Knowledge check

**Question:** A team wants to pilot a realtime voice assistant for customer support. The workflow includes account lookup and possible billing adjustments. The team has not defined confirmation before billing actions, has no human-handoff path for frustrated customers, and is not tracking transcription errors or fallback use. What is the safest next step?

- Launch only for customers with simple questions.
- Limit the pilot until confirmation, handoff, and observability are defined. **✓ Correct**
- Launch because realtime voice can reduce handle time.
- Remove observability to protect conversation privacy.

Realtime voice workflows that can affect customer accounts need explicit confirmation, escalation or human handoff, and visibility into modality-specific issues such as transcription errors and fallback use.

## Slide 40/48 - Summary

Summary

In this module, you moved from designing a useful multimodal experience to defining the conditions that make it responsible to test or deploy. Remember that realtime, voice, image, and multimodal workflows need safeguards that match how people actually use them.

A useful readiness review makes the experience more than functional. It clarifies what the system can and cannot do, where confirmation or human review belongs, how media is handled, what accessibility alternatives are available, and which signals the team needs to monitor once real users interact with it.

## Slide 41/48 - Introduction (Module: Complete the Realtime and Multimodal Experience Blueprint)

Complete the Realtime and Multimodal Experience Blueprint

You've now made the major design decisions behind a realtime, voice, image, or multimodal API experience: whether the modality is justified, which pattern fits, how the interaction should flow, and what safeguards are needed.

The final step is to bring those decisions together into one handoff-ready artifact.

In this module, you'll complete the Realtime and Multimodal Experience Blueprint.

The blueprint should help a technical or customer team understand the user moment, selected modality, interaction flow, safety and privacy controls, fallback path, verification needs, observability assumptions, readiness recommendation, and open risks.

## Slide 42/48 - Build the Realtime and Multimodal Experience Blueprint

Build the Realtime and Multimodal Experience Blueprint

The Realtime and Multimodal Experience Blueprint helps you make one design recommendation:

Should this workflow use realtime, voice, speech, image, or multimodal interaction, and under what conditions?

The blueprint should be short, practical, and handoff-ready.

Another team should be able to read it and understand the workflow need, why the modality is justified, how the experience should work, what safeguards are required, what still needs validation, and what next step you recommend.

Instead of treating the blueprint like a long technical checklist, use it to answer six questions.

| Blueprint question | What to capture |
|---|---|
| 1. What is the user moment? | Who the user is, what they are trying to do, where they are, what input they can provide, what output they need, how quickly they need it, and whether text-only would be enough. |
| 2. Which modality fits the workflow? | The recommended pattern, such as text-only, realtime interaction, STT, TTS, voice-to-action, systems-to-voice, voice-to-voice, image input, image output, or multimodal. For voice, also identify the architecture — speech-to-speech Realtime or a chained pipeline — and, for Realtime audio, the connection method: WebRTC, WebSocket, or SIP. Include the primary modality, any supporting modality, fallback option, and rejected alternatives. |
| 3. How should the interaction flow? | The main path from start to finish: user input, context capture, clarification, response, confirmation, tool or system action where relevant, and fallback or escalation. |
| 4. What controls and safeguards are needed? | Safety boundaries, human-review points, confirmations, clear disclosure that the TTS voice is AI-generated — not human — plus any additional notice or consent, accessibility options, media handling, sensitive-data concerns, and prohibited capture, storage, replay, logging, or reuse. |
| 5. What needs to be verified and monitored? | The tests and signals needed before prototype, pilot, or broader release. Include the most important checks for latency, turn-taking, transcription or interpretation quality, image clarity, fallback, accessibility, consent, human handoff, and user feedback. |
| 6. What is the recommendation? | The safest next step, the rationale, the top blocker or condition, the owner of the next action, and the evidence that would change the recommendation. |

Remember that an effective blueprint doesn't strive to be as long as possible. You should clearly answer every question, in a way where it's easy for anyone who reviews it to understand.

## Slide 43/48 - Make the recommendation

Make the recommendation

Your recommendation should explain why the modality fits or why it does not.

Avoid product-tour language. Do not recommend a modality because it is impressive, new, or likely to demo well.

Recommend it only when the workflow need, user context, input and output requirements, and readiness conditions support it.

Choose one recommendation at the end of your blueprint: Your recommendation should be based on the evidence in the blueprint, not on whether the modality feels impressive or engaging.

An effective recommendation connects the workflow need to the selected modality, then names the safeguards, tests, fallback paths, and open risks that determine whether the experience can move forward.

Remember that you need to keep the recommendation practical.

Another team should be able to quickly see the next step, the reason for it, the top condition or blocker, and who owns the next action.

## Slide 44/48 - Recommended exercise: Finalize the Realtime and Multimodal Experience Blueprint

Recommended exercise: Finalize the Realtime and Multimodal Experience Blueprint

This is an optional practice activity to help you apply what you just learned.

**Purpose:** Consolidate prior modality-fit, pattern, interaction-flow, safety, privacy, accessibility, consent, fallback, observability, and readiness decisions into a handoff-ready blueprint.

**Task:** Use the blueprint sections you developed earlier in the course, or use the home-health clinical documentation workflow below, to finalize the Realtime and Multimodal Experience Blueprint.

Use this context: A customer wants to build a clinical documentation assistant for home health nurses.

Nurses need to describe visit observations by voice, upload a photo of wound progression or medical equipment setup when appropriate, and receive a draft visit note while staying focused on patient care.

The assistant may use approved clinical documentation templates and care-team guidance, and it may prepare a structured visit summary. It should not update the patient record, suggest a diagnosis, or recommend a treatment change without confirmation and the required clinical review.

Confirm your blueprint answers six questions:

What is the user moment?
Which modality fits the workflow?
How should the interaction flow?
What controls and safeguards are needed?
What needs to be verified and monitored?
What is the recommendation?

**Estimated time:** 8–10 minutes

**Suggested output and reflection:** A finalized blueprint that explains modality fit, safeguards, fallback option, validation needs, readiness recommendation, and open risks.

**Optional stretch:** Add a lower-complexity fallback version of the experience.

## Slide 45/48 - Knowledge check

**Question:** A retailer wants an assistant for store associates handling damaged-product returns at a busy service counter. Which recommendation is the strongest multimodal design rationale?

- Use text and generated images to make the return workflow more engaging.
- Use voice, image, and written confirmation, with fallback and escalation. **✓ Correct**
- Use voice and image because speed matters; let the assistant choose the refund path automatically.
- Use image and spoken guidance, but continue even when photos are unclear.

A strong multimodal rationale connects the modality to the workflow need and includes controls. Store associates may benefit from hands-free support and visual evidence, but refund or exchange updates need written confirmation, fallback for unclear inputs, and escalation for policy exceptions.

## Slide 46/48 - Summary

Summary

The Realtime and Multimodal Experience Blueprint turns modality selection into a defensible design recommendation.

A strong blueprint explains the user moment, selected modality, interaction flow, input and output assumptions, safety and privacy controls, media-handling assumptions, fallback path, verification tests, observability needs, readiness recommendation, and open risks.

It should help a technical or customer team decide whether to prototype, proceed with conditions, simplify the experience, pause pending validation, or reject the modality as unnecessary.

## Slide 47/48 - Recap

Recap

In this course, you practiced designing realtime, speech, voice, image, and multimodal API experiences as workflow and risk decisions, not feature requests.

You learned how to start with the user moment, decide whether a non-text modality is justified, compare key modality patterns, choose between speech-to-speech Realtime and a chained voice pipeline, match WebRTC, WebSocket, or SIP to the audio path, and design an interaction flow with user control, confirmation, fallback, and escalation. You also identified safety checks needed before a realtime, voice, image, or multimodal experience moves toward prototype, pilot, or broader use.

The key takeaway: specialized modality must be justified by workflow need, user context, risk profile, and readiness evidence.

## Slide 48/48 - Congratulations

Congratulations, you've completed this course!

Use the Realtime and Multimodal Experience Blueprint when a customer asks for voice, image, realtime, or multimodal interaction. Start with the workflow need, then decide whether the modality is justified and what safeguards must surround it.

As you apply this in customer work, keep any multimodal recommendation evidence-led. This discipline helps partners recommend API experiences that are not just impressive in a demo, but useful, safe, reviewable, accessible, and ready for responsible validation.

**Course completed**

Next up in API Deployment Practitioner: "Deep Research, Images, Distillation, and Specialized API Pattern Fit" (Course, 49 min) — Unlock the power of specialized API patterns with a practical, evidence-driven approach to Deep Research, image understanding, image generation/editing, distillation, and optimization. Learn how to assess when advanced workflows are truly needed, weigh tradeoffs, validate fit, and manage operational complexity—always starting with the workflow need and standard-pattern alternatives. Build defensible recommendations with clear validation, review, rights, and governance controls, and practice applying these principles through real-world scenarios and hands-on exercises. Master the Specialized API Pattern Fit Assessment to ensure every solution is justified, reviewable, and ready for responsible deployment.
