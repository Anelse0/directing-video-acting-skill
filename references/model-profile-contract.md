# Model Profile Contract

Use this contract to add or revise a video-model adapter without changing the acting compiler.

## Core invariants

Every adapter receives the same model-agnostic acting plan:

```text
scene facts + supplied identity/reference facts + available shot/duration facts
+ temporal path + objective/task + optional trigger/counterforce/display choice
+ user-required observable actions or referenced performance source, when applicable
+ dialogue/interaction when present + cut point or held state
+ known generation failures, when supplied or observed
```

The temporal path may be event-driven or sustained. For a motion-driving workflow, the source performance may own the path and actions, leaving no text-authored acting sequence to expand. An adapter must not manufacture a trigger, transition, duration, framing, or aftermath when the core plan omits it.

An adapter may change packaging, supported control surfaces, density, shot allocation, reference mapping, and evidence disclosures. It must not replace the scene objective, map an emotion to a fixed body pattern, or invent new acting merely to make the model “feel different.”

## Required profile sections

Create one file directly under `references/` named for the model and major version. Include:

1. **Evidence snapshot** — last review date, exact version scope, official versus independent evidence boundary.
2. **Workflow routing** — text-led, image-led, reference-led, multi-shot, motion-driving, or other distinct modes; never transfer evidence between modes.
3. **Configuration versus prompt** — which values belong in UI/API fields and which belong in prose.
4. **Renderer delta** — only the ordering, phrasing, or density that differs from the core and has evidence or repeated practical value.
5. **Timing** — total duration, shot-level controls, and limits of intra-shot timing claims.
6. **References and identity** — binding syntax, reference roles, voice or performance references, and entry-specific caveats.
7. **Dialogue/interaction** — speaker assignment, audio support, known language or lip-sync boundaries.
8. **Failure escalation** — simplify, split, change workflow, or use a stronger control surface.
9. **Unsupported assumptions** — explicit insufficient-evidence items and marketing claims that must not become rules.

Avoid repeating the full observable-acting method, dialogue state machine, climax architecture, or generic anti-pattern list. Link routing from `SKILL.md`; keep all references one level deep.

If a partner or deployment entry has fields that are not portable across the model's other entries, put them in a separate entry-specific reference. Load that note only when the user names the entry.

## Evidence rule

Hard-code a model difference only when at least one of these holds:

- official documentation exposes a distinct control surface or syntax;
- official guidance clearly recommends a model-specific workflow;
- repeated independent tests show a stable difference with comparable inputs and disclosed sampling.

Label vendor benchmarks as vendor-authored. Treat a narrow independent study only within its task domain. Treat community observations as debugging hypotheses, not default brand behavior.

Do not encode:

- a model personality inferred from a few showcase clips;
- an optimal prompt length without a quality curve;
- exact negative-prompt compliance without controlled tests;
- an API field from one partner as universal platform syntax;
- reference-driven or motion-driven performance evidence as text-only capability.

## Registration and validation

1. Add the profile file under `references/`.
2. Add one conditional routing line in `SKILL.md`; do not make every task load every profile.
3. Validate at least one simple prompt-led request and one request exercising the profile's unique control surface. Do not reuse a worked example from the references.
4. Run the host platform's Skill validator and verify discovery paths.
5. Compare the new adapter against the generic renderer. Keep only differences that improve executability, preserve constraints, or correctly separate configuration.
