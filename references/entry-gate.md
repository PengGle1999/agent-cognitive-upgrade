# Entry Gate

## Route

### No Escalation

Return to ordinary work only for routine, local, reversible work with an
evidenced cause or no diagnosis needed, no recurrence, conflicting evidence,
governance drift or meaningful safety impact, and no explicit skill invocation.
Examples: translation, formatting, lookup, proven one-line correction.

### Standard

Use for bounded ambiguity/impact when competing mechanisms need comparison,
recurrence is possible, or coverage is uncertain. Require at least two distinct
mechanism families, evidence/hypothesis separation, a discriminating test for
each important candidate, solution-to-cause mapping, and a stopping decision.

### Deep

Use after a fix/verification fails again; for governance/control-system failure,
interacting cross-system causes, explicit full/deep requests, or high-impact,
irreversible, data-loss, authorization, privacy, financial, physical-safety or
loss-of-control risk. Require at least three distinct families, blocking
confirmation, blind independent cause generation and flaw review when available,
plus defense coverage and residual-risk review.

## Explicit Invocation

Explicit invocation requires at least Standard, never `no escalation`; it does
not waive Deep confirmation.

## Current-Task Preauthorization

Before showing the gate, skip it only if the current request explicitly says
to skip/not repeat it or begin Deep without another question, AND lists the
accepted capability limits or those limits were already shown in this task.
Full/deep analysis, finding all roots, "continue", "use current conditions",
avoiding unnecessary questions, old approval, or general preferences alone
are not waivers.

After showing it, direct selection of `accept these limits and continue Deep`
authorizes proceeding. Do not demand an additional skip phrase or reconfirm.
A bare `continue` is ambiguous unless it clearly selects that displayed option.

## Deep Gate Template

The gate lets the user upgrade the model as difficulty rises, not merely ask
for longer reasoning. Report model identity only if verifiable, else unknown.
Never self-certify sufficiency or silently change the model.

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
