# Entry Gate

## Route

### No Escalation

Return to ordinary work only when all are true:

- the task is routine, local, and reversible;
- the cause is directly evidenced or diagnosis is not needed;
- there is no repeated failure, contradictory evidence, governance drift, or
  meaningful safety impact;
- the user did not explicitly invoke this skill.

Examples: translation, formatting, simple lookup, or a proven one-line local
correction.

### Standard

Use when at least two plausible mechanism families require comparison, the
problem can recur, or coverage is uncertain, but impact and ambiguity remain
bounded.

Minimum:

- two distinct mechanism families;
- evidence and hypothesis separation;
- one discriminating test for each important candidate;
- solution-to-cause mapping;
- explicit stopping decision.

### Deep

Use when any applies:

- repeated failure after an earlier fix or verification;
- high-impact, irreversible, data-loss, authorization, privacy, financial,
  physical-safety, or loss-of-control risk;
- governance or control-system failure;
- multiple causes may interact across systems;
- user explicitly requests full/deep analysis.

Minimum:

- three distinct mechanism families;
- Deep blocking confirmation;
- blind independent cause generation when available;
- independent flaw review when available;
- defense coverage and residual-risk review.

## Explicit Invocation

When the user explicitly invokes this skill, `no escalation` is forbidden.
Route to at least Standard. Explicit invocation does not automatically waive
the Deep confirmation.

## Current-Task Preauthorization

Before the gate has been shown, skip the confirmation only when both are true:

1. the current request explicitly says to skip the gate, not repeat the
   confirmation, or begin Deep without another question; and
2. the current request lists the capability limits it accepts, or those limits
   were already shown in the current task.

These phrases alone are not waivers:

- "analyze completely";
- "perform Deep analysis";
- "find the full root cause";
- "continue";
- "use the current conditions";
- "do not ask unnecessary questions";
- an older approval or a general preference.

They trigger Deep but do not prove the user saw and accepted this gate.

After the gate has been shown in the current task, a direct reply selecting
`accept these limits and continue Deep` is explicit authorization to proceed.
Do not ask for an additional skip phrase or repeat the same gate. A bare
`continue` remains ambiguous unless it clearly selects that displayed option.

## Deep Gate Template

Use plain language:

> This case needs Deep analysis because [observable triggers]. Before I begin,
> switching to the highest reasoning capability currently available and raising
> reasoning effort may improve [multi-path tracking, long causal chains,
> counterexamples]. It cannot create missing evidence, unlock unavailable
> tools, or substitute for an independent check.
>
> Current conditions:
> - Another agent can independently generate causes: [yes/no/unknown]
> - Another agent can independently search for flaws: [yes/no/unknown]
> - Missing evidence: [...]
> - Required files/tools are accessible: [...]
>
> Continuing now means [concrete limitation].
>
> Choose: switch then continue; accept these limits and continue Deep; or use a
> limited analysis.

Do not include findings or a recommended root cause before confirmation.
