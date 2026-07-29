# Analysis Workflow

## 1. Define The Observation

Record the observed result, timeline, scope, impact, constraints, and what is
not yet known. Preserve the user's causal chain verbatim enough to test each
link; label it as evidence, inference, or hypothesis.

## 2. Build The Cause Space

Generate distinct mechanism families before selecting a path:

- Standard: at least two.
- Deep: at least three.
- If the user supplied a causal chain in Deep, retain it and add at least two
  alternatives.

Classify relationships as OR, AND, shared upstream, or amplifier. Reject
duplicate wording that describes the same mechanism.

### Blind Independent Generation

For Deep, when another agent is available, give it only:

- observed symptoms;
- verified facts;
- timeline;
- constraints and impact.

Do not give it the user's suspected cause, the primary analysis, or a preferred
solution. Ask for mechanism families and distinguishing evidence, not a final
verdict. If no independent agent is available, perform a separated second pass
and explicitly lower breadth confidence.

Unless isolation from files, memory, and other side channels was also verified,
describe this as `independent dispatch with prompt-blind context`, not as fully
independent reasoning.

When reconciling the independent output:

- preserve the exact boundary of the user's hypothesis;
- treat producer, delivery, consumer, and downstream invalidation failures as
  adjacent mechanisms unless evidence establishes one causal chain;
- inventory every distinct mechanism from the independent output, then retain
  it, explicitly group it as equivalent, or defer it with a reason;
- label provenance as `user`, `independent dispatch`, or `primary synthesis`;
- do not treat independent agreement as new observation evidence or as a reason
  by itself to increase a hypothesis's priority;
- treat missing logs, events, or acknowledgements as discriminating evidence
  only after instrumentation, retention, routing, query window, and source
  completeness are verified.

## 3. Rank And Deepen

Rank candidates by likelihood, impact, and testability. Apply 5 Why, a causal
graph, fault tree, or timeline separately to high-priority branches. Allow
multiple roots and shared upstream controls.

## 4. Hypothesis-Evidence Matrix

For each important candidate record:

| Candidate | Support | Conflict | Discriminating test | Impact if true | Status |
|---|---|---|---|---|---|

Allowed status:

- confirmed;
- more credible;
- ruled out;
- insufficient evidence;
- unverified hypothesis.

Do not promote an inference to confirmed merely because it is coherent.

## 5. Adversarial Review

For Deep, ask another Agent with isolated context to find:

- evidence the leading conclusion ignored;
- an alternative that explains the same facts;
- invalid assumptions;
- solution gaps and new failure modes.

Do not ask it to oppose the user by default. Its job is discrimination, not
contrarianism. A second pass by the same Agent is only `staged self-review`; it
is not independent review. If another isolated Agent did not perform the pass,
state that independent flaw review did not occur.

Feed valid review findings back into the cause map, provenance labels,
discriminating tests, and stop decision. Recording a review without revising
the affected analysis is not a completed review loop.

## 6. Design The Solution

Use only applicable layers:

- containment: reduce current impact;
- correction: remove the active cause;
- prevention: block recurrence;
- detection: make recurrence observable;
- recovery: restore a safe state.

Map each control to a causal link. State when a control treats only a symptom or
downstream layer.
