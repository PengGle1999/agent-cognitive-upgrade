# Mode Gate

## Routing Precedence
- If any `Deep` trigger is present, route to `Deep`
- `Light` is allowed only when all `Light` conditions are satisfied
- Otherwise route to `Standard`
- `Standard` is the default catch-all for anything that is not all-Light and not any-Deep
- Exclusion rule: do not down-route a case to `Light` just because one symptom looks small if recurrence, ambiguity, or elevated risk is still present

## Light
- All Light conditions must be true:
- First-time
- Low-risk
- Single-point
- Clear local scope with no active recurrence or governance-drift signal
- Must still perform one round of root-cause validation
- Boundary notes:
- A typo in one file with no workflow impact can stay `Light`
- A small local fix is not `Light` if the same defect already happened before
- A single-file issue is not `Light` if it can still cause data loss or policy drift

## Standard
- Default when the case is neither all-Light nor any-Deep
- Typical triggers:
- Multi-file or multi-step
- Recurrence possible
- Shared workflow or repeated entry point
- Some ambiguity remains, but no forced Deep trigger is present
- Boundary notes:
- A recurring bug across two tasks is `Standard`
- A doc-and-code mismatch without irreversible risk is `Standard`
- Use `Standard` when the scope is broader than a one-shot local fix, even if the failure is not catastrophic

## Deep
- Any one of these triggers is enough:
- System crash risk
- Financial/property loss risk
- Data loss risk
- Data leakage risk
- Agent loss-of-control risk
- Boundary notes:
- Potential overwrite of the only recoverable source is `Deep`
- Repeated governance drift after multiple explicit corrections is `Deep`
- A workflow that can expose secrets or sensitive notes is `Deep`
