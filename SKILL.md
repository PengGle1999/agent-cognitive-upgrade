---
name: agent-cognitive-upgrade
description: Use when a problem repeats, a prior fix or verification failed, the user corrects an earlier causal judgment, evidence conflicts, multiple causes may interact, root cause or 5 Why is requested, solution coverage is uncertain, or failure could cross systems or cause serious harm.
---

# Agent Cognitive Upgrade

## Overview

Increase reasoning breadth before depth, test competing causal paths, and verify
how far a solution actually defends. Do not turn every task into an audit.

## Entry Gate

Read [entry-gate.md](references/entry-gate.md) first.

- Return to ordinary work when the result is `no escalation`.
- Use `Standard` for bounded multi-path analysis.
- Use `Deep` for repeated failure, high risk, governance failure, interacting
  causes, or an explicit request for full analysis.
- An explicit invocation of this skill is at least `Standard`.

## Deep Is A Blocking Gate

Before Deep analysis, stop and obtain user confirmation unless the current
request explicitly authorizes skipping this confirmation. A request for
"complete", "full", or "Deep" analysis is a trigger, not a waiver. A waiver must
explicitly say to skip the gate or begin Deep without another question, and the
current task must already list the accepted capability limits or have shown
them to the user. "Continue with current conditions" alone is not a waiver. Do
not perform Deep analysis in the same response as the confirmation request.

The gate must:

1. explain the trigger in plain language;
2. recommend the highest available reasoning capability and stronger reasoning
   setting without prescribing a permanent model;
3. explain what stronger reasoning can and cannot improve;
4. report whether independent cause generation, independent flaw review,
   required evidence, files, and tools are actually available;
5. state the concrete effect of continuing with current limitations;
6. offer: switch then continue, accept limits and continue, or limited analysis.

If model capability is unknown, say it is unknown. Never self-certify that the
current model is sufficient.

## Analysis

After the gate:

1. Read [analysis-workflow.md](references/analysis-workflow.md).
2. Preserve any user-provided causal chain as a hypothesis.
3. Map distinct mechanism families before using 5 Why.
4. Rank and investigate important branches without forcing one root cause.
5. Separate evidence, inference, and unknowns.
6. Design controls for the causal links they actually cover.
7. Read [verification-and-coverage.md](references/verification-and-coverage.md)
   before concluding.

Use [reasoning-patterns.md](references/reasoning-patterns.md) as a quick
reference. Use [portable-global-gate.md](references/portable-global-gate.md)
only when helping someone install a generic pre-skill trigger.

## Non-Negotiables

- Do not replace an upstream trigger failure with a downstream content fix.
- Do not treat 5 Why as proof that the chosen path is correct.
- Do not claim independent review unless another independent pass occurred.
- Do not treat independent agreement as new observation evidence.
- Do not silently drop distinct mechanism families from independent generation.
- Do not expand the user's causal chain without relabeling adjacent mechanisms.
- Do not hide residual risk or unknowns that could change the conclusion.
- For every important defense scenario, do not omit prevention, detection,
  recovery, likelihood, impact, or residual-risk decision.
- Do not rely on a script, checklist, or confidence label as sole truth.
- Route failed verification back to the earliest invalid stage.

## Common Mistakes

| Mistake | Correction |
|---|---|
| One deep chain only | Expand distinct mechanism families first |
| Every unknown blocks completion | Block only overturning or safety-changing unknowns |
| A shortened table implies coverage | Keep prevention, detection, recovery, likelihood, impact, and risk decision |
| Deep starts immediately | Stop for confirmation unless directly preauthorized |
