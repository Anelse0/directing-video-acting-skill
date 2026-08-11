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

## Performance judgment audit

Do not pass a prompt merely because it is concrete, ordered, and detailed. Test the director's choices:

1. **Psychological chain:** Can you state the fact, the character's interpretation, immediate objective, tactic, counterforce, and turn without contradicting the prompt? Omit absent components; do not invent them to fill a schema.
2. **Subtext:** When public behavior differs from private pressure, does one action carry both readings? Does the listener receive the intended meaning, a mistaken meaning, or a chosen refusal?
3. **Restraint:** Is stillness, omission, continuation, or delayed action considered before adding a leak? Does the prompt avoid proving emotion through activity?
4. **Necessity:** Remove each optional behavior mentally. If the relationship, decision, and cut read the same, delete it.
5. **Specificity:** Could the performance survive a name and emotion swap into an unrelated scene? If yes, replace stock cues with the scene's task, object, space, status, or exact line.
6. **Listening:** Does the listener have something specific to hear, seek, resist, or misunderstand? If the listener changes, does that change occur when meaning lands rather than by turn-taking convention?
7. **Contradiction:** Are mixed states resolved into competing objectives or readings instead of alternating facial labels?
8. **Climax:** Does the peak change a tactic, function, decision, or relationship? Greater volume or more symptoms alone fails.
9. **Aftermath:** If the shot continues, does the threshold create a new condition rather than generic fatigue or a reset?
10. **Character:** Do supplied personality, power, relationship, prior state, and role materially affect the tactic? Do not invent them when absent.

Fail character specificity if a trait is either ignored or demonstrated through a pile of synonymous actions. One consequential tactic is enough.

Compare against a literal baseline: if the Skill version is merely longer or more anatomically explicit, it fails. It must add a playable choice, knowledge gap, tactic, consequence, or scene-specific carrier that changes how the audience understands the character.

Stock cues such as `smile fades`, `looks away`, `lips part then close`, `breath catches`, `jaw tightens`, and `reaches then stops` are not prohibited. Flag them when they substitute for a performance decision or appear in interchangeable combinations.

Also flag invented partner behavior that exists only to trigger the protagonist, routine social acknowledgments that do not change the exchange, and claims about what another character internally understands. Replace them with supplied communication, a neutral partner baseline, or an observable consequence.

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
