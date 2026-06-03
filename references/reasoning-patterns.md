# Reasoning Patterns

## Root Cause
- User-Stated Causal Chain: extract the user's claimed mechanism as subject -> missing trigger -> downstream failure -> recurrence risk, then test the proposed solution against each link
- Ask why until the controlling failure is found
- Tie the proposed root cause back to explicit evidence
- Distinguish containment from root cause
- Distinguish corrective from preventive action

## Self-Challenge
- Did the solution answer the user's actual causal mechanism, or only a nearby symptom?
- What if this root cause is wrong?
- What competing hypothesis still explains the evidence?
- What evidence is still missing?

## Reverse Verification
- One normal scenario
- One extreme scenario
- One upstream-failure question: "What if the solution itself becomes the next source of drift?"
