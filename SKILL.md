---
name: directing-video-acting
description: Converts character intent, relationships, plot, inner state, dialogue, duration, references, and shot constraints into production-ready observable acting prompts for AI video. Use for character performance, micro-acting, listening, dialogue, restraint, escalation, climax, or multi-character interaction, including Seedance 2.0 and Kling Video 3.0 Standard/Omni, Custom Multi-Shot, and Kling Motion Control. Also use to adapt, debug, or benchmark an existing acting prompt. Do not use for story writing with no video-acting or prompt deliverable.
---

# Directing Video Acting

Turn dramatic intent into behavior a camera and microphone can observe. Deliver a usable generation prompt first. Do not default to theory, a fixed emotion template, or an intake form.

## Route the task

Read only the references required by the request, and read each selected file completely before drafting:

- Layered, contradictory, ambiguous, or unfamiliar states: [acting-core.md](references/acting-core.md)
- Dialogue, listening, interruption, reaction shots, or multiple characters: [dialogue-interaction.md](references/dialogue-interaction.md)
- Climax, confrontation, threshold crossing, failed control, or a shot continuing after a peak: [climax-control.md](references/climax-control.md)
- Seedance 2.0: [seedance-2.md](references/seedance-2.md)
- BytePlus ModelArk's Seedance 2.0 entry specifically: also read [seedance-byteplus-entry.md](references/seedance-byteplus-entry.md)
- Kling Video 3.0 Standard/Omni, Custom Multi-Shot, or Motion Control: [kling-3.md](references/kling-3.md)
- Alibaba Cloud's Kling entry specifically: also read [kling-alibaba-entry.md](references/kling-alibaba-entry.md)
- Debugging, prompt overload, benchmark design, or final audit: [quality-gates.md](references/quality-gates.md)
- Adding a model/version: [model-profile-contract.md](references/model-profile-contract.md)

Do not load irrelevant model profiles. The Skill does not use a runtime emotion library or a finite list of supported states.

## Compile the performance

### 1. Preserve the scene contract

Retain all supplied identity, relationship, event, dialogue, duration, shot, camera, references, model/workflow, ending, and constraints. Keep quoted dialogue verbatim unless rewriting or translation was requested. Do not invent dialogue, backstory, diagnosis, deception, or a plot outcome to add drama.

Treat qualifiers at their stated scope. `Her first reaction is not to cry` constrains the first reaction, not the rest of the scene.

Infer harmless omissions and continue. Ask only when a missing choice would materially alter scene identity, exact dialogue, safety, or required platform configuration.

- No model: output only a model-agnostic prompt. Mention adaptation only if it materially helps.
- No duration: do not invent seconds; keep timing relative and avoid optional beats whose feasibility depends on an unknown runtime.
- No framing: infer it only when the requested behavior would otherwise be invisible or ambiguous.
- State material creative assumptions only when necessary, and keep them brief.

### 2. Find the playable action

Use emotion words as context, not as a lookup key. Infer in free text:

- what each relevant character is trying to accomplish now;
- what event, line, object, or ongoing task governs the shot;
- what competes with that objective, if anything;
- what the character reveals, contains, redirects, tests, completes, abandons, or refuses;
- what must be true at the cut.

For mixed or invented states, resolve competing objectives rather than stacking stock expressions. Suppression, leakage, escalation, release, and aftermath are optional dramatic functions, never mandatory stages.

### 3. Choose the temporal path

Use the smallest path that fits the scene:

```text
Event-driven: start -> trigger -> response or choice -> cut
Sustained: objective or task -> bounded ongoing behavior -> optional change -> cut
```

These arrows express causal order, not mandatory beats. Merge or omit components when the event happens at the opening frame, the response is immediate, the shot is already at its intended level, or the user specifies another structure.

Use the event-driven path only when something changes the character during the shot. Use the sustained path for ordinary speech, stable listening, continuing tasks, direct address, or a scene already at its intended level. Never invent a trigger or emotional transition to satisfy a formula.

Add orientation, processing, control, redirection, failed recovery, threshold, release, or aftermath only when causally useful. Immediate reaction can be truthful; do not force a pause. If the shot cuts at a threshold, make that cut explicit and do not append aftermath.

Prefer only the relative-order terms the scene needs. Avoid choreographing every second. Treat exact intra-shot micro-timing as best-effort unless a documented control surface provides it; never promise frame accuracy.

### 4. Select observable evidence

Start with the smallest observable behavior set that carries the beat. Add support or a motivated contradiction only when it contributes distinct causal information and remains legible in the duration and framing. Choose behavior by objective and context, not from a body-part checklist.

Every retained instruction should be:

- visible in the chosen frame or audible in the track;
- caused by the scene or useful to the ongoing task;
- directed at a person, object, place, or action;
- bounded by onset, target, direction, frequency, or completion;
- capable of distinguishing the intended beat from its surrounding state.

Use an abstract state anchor only when it clarifies intent, and keep it subordinate to playable behavior. Let purposeful gaze, task interruption/completion, distance, a relevant prop, speech timing, or stillness with a visible carrier do the acting. Use breath, swallowing, jaw, blinking, or tears only when the framing/audio can carry them and the scene motivates them. Never treat a cue as a diagnostic fingerprint.

### 5. Control density without losing intent

Identify the shot's dominant responsibility instead of distributing emphasis evenly across every channel. Dialogue may be that responsibility. If the user intentionally requires several coequal tasks or turns, preserve them, then merge compatible actions or split the shot when the model/workflow permits. If the requested duration cannot plausibly hold all required beats, disclose the tradeoff and offer the smallest faithful allocation; never silently delete a requirement.

When trimming optional detail, use this priority:

```text
identity and owner -> required scene facts/task or trigger -> ordered action
-> exact dialogue and interaction -> cut state -> essential prop/space
-> camera/style -> failure-driven guardrail
```

Do not enumerate face, eyes, breath, shoulders, hands, posture, camera, light, and environment merely because those channels exist.

### 6. Render for the selected workflow

Keep the acting logic model-agnostic; then apply only the chosen model profile. Separate UI/API setup from prompt prose. Do not present planning labels such as `Trigger:` or delivery headings as official platform fields unless the interface defines them.

When text prompting is a weak control route for the requested precision—such as reproducing complex full-body timing or a specific performance—recommend the applicable reference-video or motion-driving workflow and preserve the probabilistic boundary.

### 7. Audit and revise

Apply only relevant checks:

- Scene facts, dialogue, references, workflow, duration, ending, and constraints are preserved.
- An event-driven response has an identifiable trigger; a sustained scene has no invented trigger.
- Behavior serves an objective, task, response, or choice and is observable at the implied framing.
- Major actions are ordered; simultaneous reactions occur only when motivated.
- Shot responsibilities remain legible, optional cues do not compete, and the ending is an explicit cut point or held state.
- Dialogue ownership and any listener behavior that matters are unambiguous.
- Configuration is separate from prose; no unsupported promise is made about timing, lip sync, negatives, gaze, or model superiority.
- A negative remains only when the user supplied it, an observed failure justifies it, or an entry-specific risk requires it; use a positive replacement first where possible.

Revise until all applicable checks pass without adding unnecessary detail. If a requirement still exceeds the workflow's control boundary, deliver the closest faithful prompt and disclose that limitation briefly.

## Deliver the result

Use the user's language for headings and explanation unless asked otherwise. Preserve the requested prompt and dialogue language; do not claim English is universally superior.

If the user asks for only or directly usable Prompt text, return the Prompt alone with no heading, wrapper, analysis, or extra note. Otherwise, return only sections that add executable information:

1. **Prompt** — ready to enter, first.
2. **Model setup** — only for values that belong in UI/API configuration, such as workflow, duration, shot fields, references, or voices.
3. **Acting constraints** — only a small, targeted set justified by user requirements, an observed failure, or an entry-specific risk. Omit otherwise.
4. **Assumption or limitation** — briefly, only when material.

Do not expose the internal acting plan, evidence discussion, or alternate versions unless asked. If both Seedance and Kling are requested, compile one acting design and render two genuinely adapted outputs.

## Boundaries

- Never require an emotion enum or match against a finite case list.
- Never infer truth, guilt, deception, or diagnosis from facial or bodily movement.
- Never force restraint, gaze aversion, swallowing, aborted reaching, tears, exhaustion, or aftermath into every scene.
- Never solve overacting with a generic negative list; redesign the positive action first.
- Never turn a local beat constraint into an invented decision for the whole scene.
- Never make every character react at once merely to create activity; use simultaneity only when the same event genuinely reaches them together. Do not prescribe continuous staring or purposeless movement.
- Never replace behavior with empty intensifiers such as `cinematic`, `deeply emotional`, or `realistic`.
- Never hard-code unverified brand personalities such as “Seedance is restrained” or “Kling is theatrical.”
