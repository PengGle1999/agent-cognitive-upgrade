# Verification And Coverage

## Defense Coverage Matrix

Consider relevant scenarios:

- normal flow and boundary values;
- invalid input and corrupt state;
- concurrent people, processes, or agents;
- ordering, delay, cache, and stale data;
- unavailable services, tools, permissions, or rules;
- human error;
- compound low-probability conditions;
- failure modes introduced by the solution.

For every important defense scenario record:

| Scenario | Prevent | Detect | Recover | Likelihood | Impact | Residual-risk decision |
|---|---|---|---|---|---|---|

`Residual-risk decision` must be `accept`, `reduce`, `transfer`, or `reject`,
with a reason. Do not accept irreversible, authorization, high-impact, or
data-loss risk only because likelihood appears low.

All seven columns are required whenever the analysis proposes or evaluates
controls for that scenario, regardless of how the user phrased the request. Do
not collapse likelihood and impact into an unexplained overall judgment.

## Verification Set

1. **Forward:** Does expected behavior occur after the control?
2. **Reverse:** Does the control reject or expose the failure state?
3. **Discriminating:** Does evidence distinguish leading hypotheses?
4. **Causal coverage:** Is every user-stated and high-priority causal link
   corrected, rejected with evidence, or explicitly unresolved?
5. **Solution coverage:** Are prevention, detection, and recovery claims tested
   for the scenarios where they are asserted?
6. **Prior-defense failure:** For recurrence, why did the earlier defense and
   its verification fail to catch this case?

If a check fails, return to the earliest invalid stage: observation, cause
space, hypothesis ranking, solution design, or coverage.

## Stop Or Continue

Stop when all are true:

- major mechanism families have reasonable coverage;
- every still-important testable candidate has been tested, explicitly
  deferred with a risk decision, or shown not to affect the conclusion,
  solution, safety boundary, or verification strategy;
- high-priority candidates explain the observations without unresolved
  contradictions;
- candidates are ranked by likelihood, impact, and testability;
- high-impact scenarios are prevented or have reliable detection and recovery;
- uncovered scenarios and their risk decisions are explicit;
- new branches no longer change the solution, safety boundary, risk, or
  verification strategy.

Continue or escalate when an unknown could:

- overturn the leading conclusion;
- change the safety or authorization boundary;
- change the preferred solution;
- invalidate a high-impact coverage claim.

Low-impact guesses may remain as `unknown`. List them and explain why they do
not block stopping.

## Conclusion Contract

State:

- leading cause or set of causes and status;
- important alternatives and status;
- evidence still missing;
- recommended controls by layer;
- residual risks and decisions;
- verification evidence;
- whether independent generation and review actually occurred;
- stop, continue, or escalate decision.
