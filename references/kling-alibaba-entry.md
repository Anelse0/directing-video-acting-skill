# Kling 3.0: Alibaba Cloud Model Studio Entry

Entry snapshot: 2026-08-10. Read this file only when the target is Alibaba Cloud Model Studio's Kling video-generation API. Recheck the live documentation before emitting a production payload.

Source: [Kling video generation API reference](https://help.aliyun.com/en/model-studio/kling-video-generation-api-reference/)

These are partner-entry fields and limits. They are not universal Kling UI syntax.

## Model and quality identifiers

- Video 3.0 Standard model: `kling/kling-v3-video-generation`
- Video 3.0 Omni model: `kling/kling-v3-omni-video-generation`
- `parameters.mode: "pro"` is the default 1080p quality tier.
- `parameters.mode: "std"` is the 720p quality tier.

Do not confuse `parameters.mode: "std"` with the Video 3.0 Standard model. Model family and quality tier are separate fields.

## Prompt and shot fields

- `input.prompt` supports Chinese and English, has a 2,500-character maximum, and excess content is truncated.
- With `shot_type: "intelligence"`, `input.prompt` is required and the model plans shot division.
- With `shot_type: "customize"`, `input.prompt` is ignored; use `input.multi_prompt`.
- Set `input.multi_shot: true` before selecting `shot_type`.
- `input.multi_prompt` is required for customize mode.
- `multi_prompt` contains 1–6 segments; `index` starts at 1.
- Each segment `prompt` supports Chinese and English, has a 512-character maximum, and excess content is truncated.
- Each segment `duration` is an integer from 1 through `parameters.duration`.
- Treat each `multi_prompt[].prompt` as the actual shot content. Keep `index` and `duration` in their fields; do not repeat `Shot N — duration` inside the content.
- Retain a reference or element placeholder inside prompt content when the selected Omni task requires it to identify the subject. Remove only redundant phrases about binding or voice setup, not required prompt syntax.

Minimal structural example:

```json
{
  "model": "kling/kling-v3-video-generation",
  "input": {
    "prompt": "",
    "multi_shot": true,
    "shot_type": "customize",
    "multi_prompt": [
      {"index": 1, "prompt": "First shot content.", "duration": 4},
      {"index": 2, "prompt": "Second shot content.", "duration": 5}
    ],
    "media": [],
    "element_list": []
  },
  "parameters": {
    "mode": "pro",
    "duration": 9,
    "audio": true,
    "aspect_ratio": "16:9"
  }
}
```

Set `parameters.duration` consistently with the segment plan. The reviewed field description bounds each segment by that total but does not explicitly state the endpoint's exact sum-validation rule; verify the current endpoint rather than inventing one.

## Duration and audio

- Both listed 3.0 models accept integer `parameters.duration` from 3–15 seconds; default is 5.
- For Omni `type: "feature"` video reference, output duration is 3–10 seconds.
- For Omni `type: "base"` video editing, output duration follows the input video and `parameters.duration` is ignored.
- `audio` defaults to `false`; enabling it affects cost.
- When a `base` or `feature` video is passed, `audio` must be `false` on this entry.
- `keep_original_sound` is an Omni media option for a passed `base` or `feature` video; valid values are `yes` and `no`.

## Media and element combinations

For `kling/kling-v3-video-generation`:

- media supports one `first_frame`, or one `first_frame` plus one `last_frame`;
- first-frame and first-plus-last-frame tasks support up to three IDs in `element_list`.

For `kling/kling-v3-omni-video-generation`:

- first-frame and first-plus-last-frame combinations are supported;
- `refer` reference-to-video allows reference images plus multi-image entities totaling at most seven;
- `feature` alone requires one reference video;
- `feature + refer` requires one video and allows reference images plus entities totaling at most four;
- `feature + first_frame` accepts one reference video and one first frame;
- video editing uses one `base` video, optionally with references totaling at most four.

For Omni reference-to-video prompts, references use triple-angle placeholders such as `<<<element_1>>>`, `<<<image_1>>>`, and `<<<video_1>>>`, ordered according to the request media.

## Negative fields and portability

- The reviewed request schema does not expose a `negative_prompt` field.
- Do not invent one, and do not translate another provider's negative field into this payload without current endpoint documentation.
- Do not reuse Alibaba media types, limits, placeholder syntax, or quality-tier values as claims about Kling's native UI or another partner.
