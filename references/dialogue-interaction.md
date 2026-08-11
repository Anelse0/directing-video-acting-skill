# Dialogue, Listening, and Interaction

Use only the modules the exchange needs. Ordinary speech and stable listening do not require an emotional turn.

## Assign ownership when it can become ambiguous

For a solo line or obvious two-person exchange, a stable character name beside the exact line is enough. Build an explicit ownership note only for multiple characters, interruptions, overlapping reactions, or unclear attribution. Include only roles the exchange actually uses, such as:

```text
current action or line owner; speaker; listener; interruption owner;
affected reaction owner; holder of the cut state
```

One character may hold several roles. Describe a non-owner only when that person is likely to mouth the line, react at the wrong time, block another subject, or materially affect the composition. Do not give every background character an animation task.

Use stable, unique names. In a multi-character prompt, do not alternate among names, pronouns, clothing labels, and generic roles when identity could drift.

## Direct listening as purposeful attention

Listening may be sustained or event-driven.

- **Sustained:** the listener remains oriented to the speaker or a relevant task, with no invented reaction beat.
- **Event-driven:** a particular word, tone, omission, gesture, or object changes what the listener does next.

Select only the useful function; these are options, not a required sequence:

```text
sustain attention; redirect attention to a relevant target; continue or resume a task;
prepare to speak or interrupt; choose silence
```

Do not force a gaze break. A listener may hold the speaker's gaze, inspect relevant evidence once, keep working while listening, or disengage. Name the target whenever gaze moves. Avoid periodic gaze cycling, repeated nodding, and generic `listens naturally`.

Examples of bounded listening:

```text
She continues labeling the boxes while he gives the instructions; at the address, her marker stops on the cardboard.
He faces her through the whole short answer, then waits without nodding or preparing a reply.
He leans in to interrupt, but her next sentence resolves the question; the inhale releases and he sits back.
```

The second example is intentionally stable: absence of a transition is valid when nothing changes during the shot.

## Coordinate speech and action

Keep the stable speaker name, delivery that matters, and exact line adjacent:

```text
Mara places the receipt flat between them. Mara, quiet and controlled: “You knew.”
```

Add a pre-speech action only when the shot begins before the turn and that action matters. Do not add a pause or preparatory breath to a line that begins immediately, enters mid-sentence, or is an interruption.

Keep speaking behavior focused on the scene function. A contradiction can carry subtext when the scene supplies one:

```text
His volume remains courteous while he returns her key to the table.
```

Do not specify pitch, pace, volume, accent, gaze, hand choreography, posture, and breath all at once unless the duration and workflow can carry them. Preserve the user's punctuation and dialogue language; translate only when asked.

## Interruption, false starts, and silence

Show the causal boundary rather than writing `dramatic pause`:

```text
She begins, “If you had—” The line stops there. She sets the envelope between them.

Leo starts, “I was trying—” Aya's off-screen “You were leaving” cuts him off. Leo stops articulating and lets her finish.

He inhales to answer, notices her hand on the exit latch, and lets the breath go without speaking.
```

For an interrupted line, identify who owns the first line, what interrupts it, and who owns the next audible speech. For chosen silence, show the abandoned speech action or the task that replaces speech. Do not fill silence with blinking, swallowing, or fidgeting by default.

## Stage several characters

When a responsibility map is needed, make causality explicit without requiring every character to change:

```text
A speaks.
B changes behavior only if the relevant phrase affects B.
C may continue a relevant baseline because this beat does not belong to C.
If B answers, place the answer at the intended overlap or after A finishes.
```

Simultaneous reactions are valid when an event truly reaches everyone at once. Otherwise, stagger them by access and relationship: one character may understand the words, while another reacts later to that character. Keep positions legible and reduce crossings, occlusion, overlapping speech, and ambiguous pronouns when identity or lip sync matters.

## Choose the shot structure

Prefer a continuous shot when one unfolding reaction or a legible two-shot is the point. Prefer separate reaction shots when attribution repeatedly fails, two faces require close inspection, several turns overload one shot, or the model offers useful shot-level controls.

Carry the held state across cuts. A hand resting on the receipt, a body blocking the doorway, or an unfinished task should not reset silently in the next shot.

## Failure-specific repair

- **Everyone mouths the line:** shorten the exchange, keep each line beside one named speaker, and isolate turns if needed. Constrain a listener's mouth only after observing this failure.
- **NPC staring:** replace generic attention with the actual listening task, a supplied key phrase when one exists, or a purposeful gaze decision.
- **Mechanical turn-taking:** let a received line change, delay, or cancel the next action.
- **Frozen dialogue:** attach a relevant low-amplitude task, distance decision, or partner consequence when the scene needs it.
- **Gesture noise:** establish a hand baseline and retain only motivated actions.
- **Undefined cut point:** state who holds the final silence, line, look, task, or movement. Add aftermath only if the shot continues beyond a threshold.
