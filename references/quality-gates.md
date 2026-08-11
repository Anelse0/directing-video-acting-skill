# Quality Gates and Failure Repair

Use this file to audit a finished prompt, debug a failed generation, or design a benchmark. Do not print the audit unless asked.

## Preserve the contract first

Confirm target model/workflow, identities, reference roles, quoted dialogue and order, duration, shot count, framing/camera, ending, and user constraints. Do not improve acting by changing plot, relationship, line, or outcome.

## Prompt audit

Pass only the applicable checks:

1. **Path:** an event-driven scene has a supplied or implied trigger; a sustained scene has no invented trigger or change.
2. **Playable:** behavior pursues an objective, continues a task, responds, or chooses; it is not only a facial label.
3. **Observable:** each instruction can appear in pixels or sound at the available framing.
4. **Bounded:** gaze, gesture, breath, speech, or stillness has a target, onset, direction, count, contrast, or completion.
5. **Temporal:** required actions are ordered and not accidentally simultaneous.
6. **Density:** the shot's responsibilities remain legible; optional support does not become an anatomy inventory or compete with required beats.
7. **Interactive:** only necessary speaker, listener, and reaction ownership is specified, with no ambiguous line attribution.
8. **Ending:** the prompt defines a cut point or held state without requiring an aftermath.
9. **Model-valid:** configuration is separate from prose and entry-specific fields are not generalized.
10. **Evidence-safe:** no promise of exact micro-timing, perfect lip sync, negative compliance, or brand superiority.

If all user-required beats do not plausibly fit, merge or split before dropping anything. Disclose any remaining tradeoff.

Delete a sentence that only repeats an emotion adjective or decorative style word without changing what can be generated.

## Positive-first constraints

First define the desired resting state and allowed action:

```text
Weak: no blinking, no nodding, no hand gestures, no head movement
Better: her hands remain around the cup; her head stays level while her gaze moves once to the receipt
```

Keep a negative only when it preserves a user constraint, targets an observed failure, or handles an entry-specific risk. There is no universal correct number of negatives. With no such risk, omit the section.

## Failure repair

| Failure | Likely prompt cause | First repair |
|---|---|---|
| Overacting | Peak adjectives or too many channels | Remove intensity words; keep the decisive action and justified support |
| Emotional jump | Event-driven prompt lacks a causal onset or grounded trigger | Clarify the scene's actual onset; do not add a neutral baseline or delay unless motivated |
| Invented transition | Sustained scene forced through a reaction arc | Keep the task or objective continuous and define the cut |
| Dead eyes | Stillness has no target, task, or contrast | Give attention a person/object/task or let another action carry the shot |
| Constant staring | Unbounded eye-contact instruction | Use a motivated hold, relevant glance, withdrawal, or no gaze instruction |
| Mechanical blinking | Blink used as generic emotion | Delete it unless that single blink is the requested beat |
| Repeated nodding | Generic listening/agreeing | Define one acknowledgment or none |
| Random hands | No resting state or objective | Establish a baseline; connect one action to a prop/person/task |
| Frozen body | Global no-movement wording | Keep the body quiet while a task, gaze, voice, weight, or prop carries meaning |
| Facial morphing | Extreme face, turn, occlusion, or reference conflict | Lower amplitude; stabilize framing and reference responsibilities |
| Mouth always moving | Ambiguous speaker or overloaded exchange | Name one speaker; shorten or isolate turns |
| Rigid dialogue | Line has no scene function | Add a purposeful entry or consequence only when needed |
| Everyone reacts together | No causal ownership | Stagger by access/relationship or split reaction shots |
| Theatrical crying | Peak treated as a maximum pose | Choose the threshold action and explicit cut state |
| Meaningless movement | Gesture has no object or purpose | Attach it to a task/person/space or remove it |
| Character drift | Weak binding, crossing, occlusion, or ambiguity | Stabilize names/positions and reduce simultaneous action |
| Ending reset | Cut state undefined | State what remains, settles, transfers, or reaches the edit |
| Later beats missing | Prompt overload | Preserve required beats; remove optional support or allocate shots |

Change one variable per regeneration when diagnosing. A beautiful result that ignores a required beat is a failed result.

## Production evaluation

For rendered-video comparison, generate repeated samples and score trigger clarity where applicable, beat order, listening purpose, body/action congruence, threshold/cut, speaker attribution and lip sync, identity/artifacts, and perceived naturalness. Record requested behavior as `executed`, `partial`, `missing`, or `reversed`. Keep Standard, Omni, Motion Control, single-shot, and Multi-Shot as separate conditions. One prompt answer or one curated video cannot establish a model rule.

Record requested behavior as `executed`, `partial`, `missing`, or `reversed`. Keep Standard, Omni, Motion Control, single-shot, and Multi-Shot as separate conditions.
