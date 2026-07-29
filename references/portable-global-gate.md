# Optional Portable Global Gate

This is a generic pre-skill trigger for users who want earlier detection. It is
optional and does not replace this skill.

## Suggested Rule

Before proposing a fix, quickly check whether any signal suggests that a
surface-level answer may be unsafe:

- the same problem happened before;
- an earlier fix or verification failed;
- the user corrected the causal explanation;
- evidence conflicts or several causes may interact;
- solution coverage is uncertain;
- the issue crosses systems or has serious impact;
- the user requests root cause, 5 Why, coverage, or deep verification.

If no signal exists, continue ordinary work. If a signal exists, load
`agent-cognitive-upgrade` and use its entry gate. Do not perform the full
analysis in this global rule.

## Installation Guidance

- Put the rule in the user's global agent instructions only if they want a
  persistent early trigger.
- Keep project-specific details in project rules.
- Do not duplicate the analysis workflow, thresholds, or truth source here.
