# Agent Cognitive Upgrade

A reusable Codex skill for problems that need more than a plausible first
answer. It expands cause breadth before depth, tests competing explanations,
and verifies how far a proposed solution actually defends.

## What v2 Adds

- A fast entry gate so routine work stays routine.
- `Standard` analysis for bounded multi-path problems.
- A blocking `Deep` confirmation for repeated, high-risk, governance, or
  cross-system failures.
- Cause-space expansion before 5 Why or other depth tools.
- Prompt-blind independent cause generation and independent flaw review when
  another agent is available.
- Exact provenance labels for user hypotheses, independent output, and primary
  synthesis.
- Prevention, detection, recovery, likelihood, impact, and residual-risk
  coverage.
- Explicit stop/continue rules so low-impact unknowns do not cause endless
  analysis, while important untested candidates stay open.

Version **v2.1.0** also checks problem framing and test oracles, distinguishes
investigation priority from causal credibility, and binds claims to their
tested environment. Model-upgrade confirmation and the two/three-family floors
remain. Improvement and rule-promotion review is conditional, not a ritual
after every task; its effectiveness needs original, new, and ordinary cases.

## Install

Clone or download this repository into your Codex skills directory:

```text
<CODEX_HOME>/skills/agent-cognitive-upgrade/
```

The installed folder must contain:

```text
agent-cognitive-upgrade/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── analysis-workflow.md
    ├── entry-gate.md
    ├── improvement.md
    ├── portable-global-gate.md
    ├── reasoning-patterns.md
    └── verification-and-coverage.md
```

Restart or reload the Codex client if it does not discover newly installed
skills immediately.

## Use

Invoke the skill explicitly:

```text
Use $agent-cognitive-upgrade to analyze why this problem returned after the
previous fix.
```

The skill may also be selected automatically when a problem repeats, evidence
conflicts, an earlier fix or verification failed, several causes may interact,
or root-cause and coverage analysis is requested.

Explicit invocation guarantees at least `Standard`; it does not automatically
waive the blocking confirmation required before `Deep`.

## Deep Confirmation

Before Deep analysis, the agent must explain:

- why Deep was triggered;
- whether switching to a stronger available model is advisable, with reasoning
  effort considered separately;
- what stronger reasoning cannot provide;
- whether independent agents, evidence, files, and tools are available;
- the concrete limitations of continuing now.

The user then chooses to switch and continue, accept the displayed limits and
continue Deep, or use limited analysis.

## Optional Global Trigger

[`references/portable-global-gate.md`](references/portable-global-gate.md)
contains a generic early-trigger rule. It is optional. Keep project-specific
paths and policies out of the reusable skill, and do not copy the full analysis
workflow into global instructions.

## Validation

At minimum, test:

1. simple translation or formatting does not trigger analysis;
2. explicit invocation runs at least Standard;
3. Deep stops for confirmation;
4. selecting “accept limits and continue Deep” does not repeat the gate;
5. several cause families remain distinct;
6. independent review is not claimed when unavailable;
7. important untested candidates prevent stopping;
8. low-impact unknowns can remain documented without endless analysis;
9. wrong framing and implementation-derived expected results are challenged;
10. successful correction is not relabeled as proven event causation;
11. proposed improvements repair the failed layer, are tested for transfer and
    normal-task regressions, and have revision/withdrawal criteria;
12. ordinary tasks do not load the conditional improvement workflow.

Compare against the prior version with identical evidence and tools. Record
actual reads, clarification burden, and quality; document size alone cannot
prove runtime efficiency. Keep original outputs, baseline passes, failed cases,
and untested claims visible. These are maintenance tests, not a required suite
for every task using the skill.

The v2.1.0 maintenance check covered synthetic framing/oracle cases, bounded
regressions, model-upgrade confirmation, conditional loading, and semantic
review. The prior version also passed the core comparison cases; these results
do not establish improved real-world recurrence rates or general reasoning
ability. Core required text stayed approximately flat, but paired answers grew;
no overall token or time saving has been demonstrated.

## Design Boundary

This skill improves reasoning structure. It cannot create missing evidence,
unlock unavailable tools, prove agent independence that was not established,
or turn a checklist into ground truth.

See [`CHANGELOG.md`](CHANGELOG.md) for release history.
