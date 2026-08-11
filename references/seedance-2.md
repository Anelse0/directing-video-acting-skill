# Model Profile: Seedance 2.0

Evidence snapshot: 2026-08-10. Apply only to standard Seedance 2.0, not Fast or later versions. Verify the current endpoint before emitting an exact payload.

Evidence labels: **[Official]** ByteDance/Volcano documentation; **[Vendor benchmark]** model-team evaluation; **[Operational heuristic]** practical but not guaranteed; **[Insufficient evidence]** do not encode as a capability.

## Scope and evidence boundary

- **[Official]** Reviewed identifiers vary by platform; matching date strings do not prove identical weights across entries.
- **[Official]** At the model-report stage, Seedance 2.0 accepted text, image, video, and audio, generated 4–15 seconds, and reported native 480p/720p output. Later endpoints may expose higher output resolutions; query the selected platform.
- **[Vendor benchmark]** Emotion/expression and micro-expression results are relatively strong on SeedVideoBench 2.0, but this is not an independent acting benchmark and does not establish isolated facial-control reliability.
- **[Official]** Multi-subject consistency and multi-speaker lip sync remain acknowledged limitations.

## Workflow routing

- **Text-led T2V:** apply the model-agnostic acting plan; do not borrow performance-reference claims as evidence for text-only control.
- **First-frame or first/last-frame I2V:** place frame roles in configuration and use prose only for the resulting action and camera intention.
- **Multimodal R2V:** bind identity, scene, movement/camera rhythm, voice, and other audio to distinct reference objects.
- When exact movement or performance rhythm is non-negotiable, route to a clean performance-reference video; do not promise frame-by-frame reproduction.
- Treat editing, continuation, and extension as separate workflows; do not transfer their evidence to de novo T2V/I2V.
- Check the selected entry before combining frame-led and multimodal-reference inputs; some APIs expose them as separate request modes.

## Configuration versus prompt

- Put endpoint/variant, total duration, aspect ratio, resolution, audio switch, watermark, workflow mode, and uploaded media roles in UI/API configuration when supported.
- Put ordered visible events, performance behavior, dialogue, sound semantics, and any soft camera intention in prompt prose.

- Do not copy reference syntax or configuration fields across products. Use the selected entry's reference mechanism.
- Treat `static composition` as a soft visual request, never as a deterministic camera lock.

## Renderer delta

- **[Official]** For complex scenes, order events as a storyboard or numbered shots rather than pasting an undifferentiated script.
- **[Operational heuristic]** Continuous causal prose is a useful single-shot package, not a documented Seedance-only grammar; keep the generic renderer when it is already clear.
- **[Official]** Describe the relevant body part and qualify amplitude, speed, or force; concrete physical behavior is preferred to an abstract intensity label.
- **[Official]** Favor slow, gentle, continuous small movements when the intended performance is low amplitude, and include transitions or inertia when they matter.
- **[Official]** When the core plan already requires camera movement, retain only one principal movement per shot. A stable or slowly moving camera for micro-acting is an operational heuristic, not a default framing instruction or hard control.
- **[Operational heuristic]** Do not call Seedance camera planning `Automatic Multi-Shot`. If asking it to plan several shots, avoid simultaneously prescribing dense intra-shot micro-actions.

## Timing and density

- When the workflow already has a total duration, put it in configuration; the adapter must not invent one.
- **[Official]** Strict per-shot time allocation can be unstable, although official examples sometimes use approximate ranges.
- **[Operational heuristic]** Treat `0–3s`, `near 8s`, and similar intra-shot markers as soft targets, never frame-accurate commitments. If exact timestamps are user requirements, preserve them as `Timing targets (best effort)` outside the prose and prefer relative order inside the acting prompt.
- Use a performance-reference video when exact rhythm matters more than text-only flexibility.
- **[Official]** Long, dense prompts can scatter attention; remove decorative or competing detail before deleting required beats.
- Do not encode a universal word-count sweet spot or maximum acting-channel count.

## References and identity

- **[Official]** At the evidence snapshot, multimodal reference accepted up to 9 images, 3 videos, and 3 audio clips; capacity is not a recommended asset count.
- Give each retained reference one explicit role and prioritize functionally distinct assets over filling every slot.
- **[Official guidance]** Prefer separate neutral frontal and full-body identity images over a composite multi-view sheet that may be read as several people.
- Use stable unique character names and explicit bindings; official guidance warns that stability declines as the number of referenced people grows, particularly beyond four.
- Reference video is the documented route for movement, camera behavior, and performance rhythm; no controlled evidence proves it universally superior to text prompting.
- Reduce referenced people and conflicting assets when identity drifts; do not claim that a `no duplicates` phrase guarantees correction.
- Real-person references may require authorization, identity verification, or a trusted-asset workflow at the selected platform.

## Dialogue and audio

- Use the selected interface's documented dialogue quoting convention.
- **[Operational heuristic]** Keep speaker name, delivery, and exact line adjacent; this is prompt packaging, not an official field grammar.
- **[Operational heuristic]** Prefer short, non-overlapping lines when reliability matters.
- **[Official]** Multi-speaker lip-sync errors remain a known limitation; do not promise perfect lip sync or silent-listener mouth compliance.
- If attribution or sync fails, shorten the lines, reduce simultaneous body action, isolate reaction shots, or generate turns separately.
- Audio channel layout is entry-dependent; never infer universal stereo from launch materials.

## Seedance-specific failure escalation

- **Later beats disappear:** remove decorative style, lighting, secondary movement, and extra camera behavior; preserve the core scene contract.
- **Strict timing fails:** replace intra-shot seconds with event order or split the shot.
- **Exact acting path fails:** use a clean performance-reference video instead of expanding the text prompt.
- **Multi-speaker attribution fails:** shorten and isolate turns; use separate reaction shots or generations when necessary.
- **Reference identity drifts:** reduce people and reference conflicts, return to separate face/full-body assets, and strengthen explicit binding.
- **Static framing drifts:** retain one plain text camera intention; use a deterministic lock only if the selected entry documents one for this model.
- **Repeated continuation degrades:** stop chaining extensions and restart from a selected clean frame or reference; repeated continuation may introduce joins, color drift, omissions, duplicates, or face degradation.

## Unsupported assumptions

- **[Insufficient evidence]** Reliable isolated control of swallowing, blink cadence, pupil size, individual facial muscles, exact gaze duration, exact tear timing, or FACS/AU combinations.
- **[Insufficient evidence]** Stable success rates for full restrained-crying, betrayal, panic, or breakdown arcs.
- **[Insufficient evidence]** Acting-specific negative-prompt effectiveness, a universal optimal prompt length, or a fixed acting-channel limit.
- **[Insufficient evidence]** Natural multi-person listening, exact multi-speaker mouth states, or frame-accurate intra-shot timing.
- **[Insufficient evidence]** Frame-by-frame performance-reference reproduction or independent acting superiority over Kling 3.0.

## Evidence anchors

- ByteDance Seed, *Seedance 2.0 Official Launch*, 2026-02-12: https://seed.bytedance.com/en/blog/seedance-2-0-official-launch
- Team Seedance, *Seedance 2.0: Advancing Video Generation for World Complexity*, 2026-04-15: https://arxiv.org/abs/2604.14148
- Volcano Engine, *Doubao Seedance 2.0 系列提示词指南*, updated 2026-06-08: https://www.volcengine.com/docs/82379/2222480?lang=zh
