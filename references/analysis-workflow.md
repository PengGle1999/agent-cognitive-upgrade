# Analysis Workflow

## 1. Define The Problem And Observation

Establish the intended outcome and its source, expected versus observed
behavior, and success criteria. Check observation reliability: identity,
version, time window, and actual data source. A reported difference is not yet
a proven defect. Compare a successful and failed case when available.
Record scope, impact, constraints, timeline, and unknowns. Preserve the user's
causal chain precisely as a testable hypothesis; separate evidence and inference.

## 2. Build The Cause Space

Generate distinct mechanism families before selecting a path:

- Standard: at least two.
- Deep: at least three.
- If the user supplied a causal chain in Deep, retain it and add at least two
  alternatives.

These floors prevent premature closure; a count is not proof of sufficient
breadth. Do not shrink them just because one candidate has supporting evidence.
Check whether framing or observation could explain the apparent fault; state
why inapplicable if excluded. Retain the strongest competing explanation and
what the leading one cannot explain. Count different mechanisms and predictions,
not synonyms or adjacent symptoms. Classify OR, AND, shared upstream, or amplifier.

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

Rank causal credibility by evidence alone; without distinguishing evidence,
leave candidates tied. Choose investigation order by decision value, cost,
impact, testability, and reversibility; cheap to test or severe if true does not
mean more likely.
Use 5 Why, a causal graph, fault tree, or timeline on important branches only
after breadth. Allow multiple roots and shared upstream controls.

## 4. Hypothesis-Evidence Matrix

For each important candidate record:

| Candidate | Support | Conflict | Discriminating test and predicted outcomes | Impact if true | Status |
|---|---|---|---|---|---|

Allowed status:

- confirmed;
- more credible;
- ruled out;
- insufficient evidence;
- unverified hypothesis.

Before testing, state how results would distinguish candidates and change the
decision. Afterward, update status from actual results, including contradictions
and inconclusive results. Never invent probabilities or promote a coherent
story to confirmed. Support for one cause does not exclude its competitors.

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

Where the choice materially affects outcomes or tradeoffs, compare a few real
alternatives: repair the mechanism, remove a fragile step/state/dependency,
contain impact with detection/recovery, or retain the current state with an
explicit risk decision. Assess effect, complexity, maintenance, side effects,
and reversibility. Do not invent alternatives for an already clear correction.

Use only applicable layers:

- containment: reduce current impact;
- correction: remove the active cause;
- prevention: block recurrence;
- detection: make recurrence observable;
- recovery: restore a safe state.

Map each control to a causal link. State when a control treats only a symptom or
downstream layer. A reversible control may help across several unresolved
causes: distinguish permission to use that control from confirmation of a root
cause. Recovery after a change alone cannot distinguish co-changes, coincidence,
or competing explanations.
