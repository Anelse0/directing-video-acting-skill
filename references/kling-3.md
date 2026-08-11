# Model Profile: Kling Video 3.0

Evidence snapshot: 2026-08-10. This file contains only Kling-specific renderer deltas. Use the skill's acting core, dialogue, climax, and quality references for model-independent performance design.

Keep Video 3.0 Standard, Video 3.0 Omni, Custom Multi-Shot, and Motion Control evidence separate. Verify configuration against the exact Kling or partner entry before producing a payload.

## Select the workflow

- Use **Video 3.0 Standard** for prompt-led T2V, I2V, start/end-frame, native-audio, and ordinary single- or multi-shot generation.
- Standard can bind character elements—and their configured voices—after a start frame or start/end frames are supplied. Do not route to Omni merely because identity or a bound voice must persist.
- Use **Video 3.0 Omni** when broader independent image, element, or video reference combinations are central, or when the Standard start-frame binding route is insufficient.
- Use **Custom Multi-Shot** when separate shots need their own content and duration. It is a shot-organization mode available to the reviewed 3.0 models, not a separate acting model.
- Use **Motion Control 3.0** when text prompting is insufficient and a real driving performance should provide more direct body, hand, timing, or facial guidance.

Do not select Omni merely because an emotion is complex. Do not use Omni or Motion Control results to claim that Standard text prompting can reproduce the same performance. Motion Control is also probabilistic; recommend it as a more direct reference-driven route, not as frame-exact reproduction.

## Separate configuration from prompt prose

Put model, quality tier, duration, aspect ratio, audio, Multi-Shot mode, start/end frames, references, element IDs, and voice bindings in UI/API configuration when the entry exposes them.

Put only the requested visible scene behavior, event order, dialogue, listening, camera intention, and cut state in prompt prose. `Mode:`, `Trigger:`, `Reaction owner:`, `End state:`, and `Acting guardrail:` are planning labels, not universal Kling fields. A sentence saying `Multi-Shot off` does not replace the corresponding setting.

Keep reference mapping separate from prose when useful:

```text
Reference or element -> identity, voice, scene, or continuity role
```

If the target is Alibaba Cloud Model Studio, read [kling-alibaba-entry.md](kling-alibaba-entry.md) completely before preparing fields or payloads. Do not transfer that partner entry's limits or syntax to Kling's native UI or another API.

## Standard renderer delta

- Submit one concise ordinary prompt for a single shot; do not paste planning labels as a field schema.
- Use stable character names and place each speaker beside the exact line and delivery when multi-character attribution is at risk.
- Reviewed official guidance supports three-or-more-character coreference and dialogue in Chinese, English, Japanese, Korean, and Spanish, including mixed-language and dialect/accent workflows.
- Do not promise arbitrary-language behavior; the reviewed official guide says dialogue in other languages is translated to English.
- Bind an existing character voice through the element/interface. Do not rely on prose alone, and do not add a conflicting pitch, timbre, or accent after binding.
- Treat official advice to use visible action, chronological order, and few competing priorities as editorial guidance, not a guaranteed parser grammar or hard action count.

## Omni renderer delta

- Supply the reference/element mapping separately, then use prose for what happens in the requested shot.
- Use Omni for broader reference-to-video combinations, not as a synonym for Motion Control or exact performance transfer.
- A video reference can guide supported reference features; do not claim that it reproduces the source actor's exact performance unless the selected workflow explicitly provides motion driving.
- An independent study of 20 static psychotherapy interview clips found that Kling 3.0 Omni T2V had lower OpenFace-measured non-verbal feature distance from actor clips than Veo 3.1 Fast in all 20 matched groups and was significantly closer in six of seven feature groups.
- In that study, the actor clips were comparison targets, not Kling inputs; Seedance was not tested, head movement did not differ significantly, and computational similarity did not establish perceived authenticity or high-intensity emotional realism.
- When closer reproduction of a particular performed path is essential, escalate to Motion Control while stating that output remains probabilistic.

## Custom Multi-Shot delta

- Output each shot as a separate duration plus content block when the selected entry exposes per-shot fields.
- `Shot N — duration` is a delivery-format label for the user; it is not text that must be inserted into the shot's content field.
- Keep identity and voice bindings in configuration rather than hiding them in a main prompt that a custom mode may ignore.
- After listing those bindings in setup, remove redundant prose such as `using the bound element` or `with the bound voice` from each shot's content. Retain any reference or element identifier that the selected entry requires inside prompt content to identify the subject; the exception does not authorize repeating voice configuration or other setup prose.
- Use per-shot duration for shot-level pacing only. It does not establish exact intra-shot facial keyframes or second-level micro-action adherence.
- Treat a 2–3 second shot containing a multi-step prop action, a major expression transition, and a long line as high overload risk; reduce its tasks or increase duration rather than declaring it impossible.
- Keep any partner-specific `prompt`, `multi_prompt`, shot-count, character-count, or length limits out of this profile.

## Motion Control delta

Motion Control uses a character reference plus a real driving video to transfer performance. It supplies more direct reference-driven control than text alone but does not guarantee frame-identical output.

When recommending it, specify:

- one continuous driving take without cuts or source camera movement;
- a clearly visible performer moving at a moderate, usable pace;
- compatible body orientation between the reference character and driving performer;
- supplementary neutral, target-expression, and side-face references when complex facial transitions require them;
- one main controlled character at a time.

The Motion Control facial element supplies facial identity information. Do not rely on it to preserve clothing, hair, makeup, or props. If those details matter, anchor them in the start image and the appropriate generation setup.

For several characters requiring tightly controlled peaks, use separately driven reaction shots and edit them together as a workflow heuristic; do not present simultaneous multi-character precision as an official capability.

## Kling-specific failure escalation

- **Identity drift in Standard:** verify start-frame quality and subject binding before considering Omni.
- **Reference requirements exceed Standard binding:** move to Omni and map every reference role explicitly.
- **Bound voice drifts:** verify the configured voice and remove conflicting prose direction.
- **Speaker attribution or turn order fails:** keep stable names and speaker-line-delivery adjacency; isolate turns with Custom Multi-Shot when necessary.
- **Lip sync drifts:** shorten the affected line, keep the speaking face visible, reduce simultaneous complex movement, or isolate the turn. Do not promise that this guarantees a repair.
- **Shot pacing fails:** use Custom Multi-Shot duration rather than adding increasingly exact intra-shot facial timestamps.
- **A particular complex performance path remains essential:** move to Motion Control instead of expanding a text-only anatomical inventory.
- **A negative list fails:** do not infer that another entry's `negative_prompt` field exists; verify the interface and redesign the positive visible state first.

## Unsupported assumptions

Do not claim stable Standard text-only control of isolated micro-expressions, swallowing, blink count, tears, exact gaze, or a complete suppression-to-aftermath arc. Do not promise perfect lip sync, reliable natural overlap or interruption, equal emotional prosody across supported languages, acting-negative compliance, an optimal prompt length, exact intra-shot seconds, Motion Control exactness, or Kling superiority over Seedance without task-specific repeated tests.
