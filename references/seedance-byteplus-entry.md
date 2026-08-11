# Seedance 2.0: BytePlus ModelArk Entry

Entry snapshot: 2026-08-10. Read this file only when the target is BytePlus ModelArk's Seedance 2.0 video-generation API. Recheck the live documentation before emitting a production payload.

Source: [Create a video generation task](https://docs.byteplus.com/en/docs/modelark/1520757)

These are BytePlus entry fields and limits, not universal Seedance syntax.

## Model and workflow routing

- Reviewed model ID: `dreamina-seedance-2-0-260128`.
- First-frame or first-and-last-frame I2V and multimodal-reference generation are distinct, mutually exclusive request scenarios. Do not mix their role fields in one request.
- A multimodal-reference request cannot contain audio alone; include at least one supported image or video reference.
- Treat editing/continuation as a separate entry workflow rather than evidence for de novo T2V or I2V.

## Configuration and reference objects

- Put the model ID, supported total duration, aspect ratio, resolution, audio generation switch, watermark, and uploaded media roles in request fields rather than prompt prose.
- BytePlus represents uploaded references as content objects. Do not paste `@Image1`, `@Video1`, or another UI's token syntax into this API by default.
- Bind each content object to one declared role—identity, appearance, movement/performance rhythm, scene, or voice/audio—and avoid conflicting responsibilities.
- The reviewed schema contains `camera_fixed` and `seed`, but marks both unsupported for Seedance 2.0. Do not send them as if they controlled this model.
- Because this entry cannot lock the reviewed model with `seed`, use repeated generations and record the returned task metadata for comparative evaluation.
- Later endpoint output resolutions may differ from the model report's native 480p/720p values; verify the live entry before selecting a resolution.

## Prompt, dialogue, and audio

- The reviewed entry recommends keeping prompts below 1000 words because long text can scatter attention. This is a recommendation, not an optimum or a portable hard limit.
- Put exact dialogue in straight double quotes for this entry.
- Launch/model-report materials describe dual-channel or binaural audio, while the reviewed BytePlus entry documents mono output. Treat the selected entry as authoritative for payload expectations and do not promise universal stereo.

## Entry-specific failure escalation

- **Frame-led and multimodal roles collide:** choose one request scenario and rebuild the media-role list; do not work around the conflict in prose.
- **Audio-only reference is rejected:** add the required supported visual reference or use a different audio workflow.
- **Static composition drifts:** retain one plain camera intention in prose; do not add unsupported `camera_fixed`.
- **Reproducibility is required:** run repeated samples and log outputs; do not claim deterministic replay through unsupported `seed`.
- **Prompt tail disappears:** reduce decorative and competing detail while preserving the acting contract; do not treat 1000 words as a quality target.

## Portability boundary

Do not reuse BytePlus content-object roles, field support, quoting conventions, word guidance, model ID, resolution menu, or audio layout as claims about Volcano Engine, Dreamina/Jimeng, another partner API, or a later Seedance version.
