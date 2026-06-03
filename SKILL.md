---
name: agent-cognitive-upgrade
description: "Use when a problem may require root-cause analysis, multi-solution exploration, coverage analysis, or forward/reverse verification across normal work and governance work."
---

# Agent Cognitive Upgrade System

## When To Use
- Use when any of these activation rules is true:
- Repeated issue in the same subsystem, workflow, or governance rule
- Governance drift, repeated reminder, or semantic misunderstanding risk
- Cross-project risk, repeat-entry risk, or shared workflow exposure
- High-risk failure modes that may require stronger verification and escalation
- Do not activate for routine one-shot work when no recurrence, no governance drift, and no elevated risk signal is present

## Start Gate
- Before analysis, remind once to switch to a stronger model / reasoning setting if available
- If the user does not switch, continue, but explicitly mark the analysis depth as limited before presenting findings
- Then classify `Light / Standard / Deep`
- Mode precedence is mandatory:
  1. If any Deep trigger is present, use `Deep`
  2. Else use `Light` only if all Light conditions are satisfied
  3. Else use `Standard`
- Default behavior: when the case is not clearly all-Light and not any-Deep, route to `Standard`

## Required Flow
1. Trigger
2. Root Cause
3. Solution
4. Coverage
5. Verification
6. Escalation
7. Learning Promotion

### Trigger
- State which activation signals are present
- State whether analysis depth is full or limited
- Apply mode routing using `assets/mode-gate.md`
- After mode routing, use `assets/output-contract.md` as the required response skeleton

### Root Cause
- Output the most credible root cause
- Tie the root cause back to explicit evidence, not only intuition
- Distinguish evidence, inference, and unverified hypotheses

### Solution
- Produce at least 2 candidate solutions unless only 1 viable option remains, and explicitly state why only 1 remains
- Name the recommended solution and why it is preferred

### Coverage
- Map where the failure can recur: code, docs, workflow, governance, repeat-entry points, or other affected routes

### Verification
- Include forward verification and reverse verification
- Reverse verification must include:
- One normal scenario
- One extreme scenario
- One upstream-failure / self-drift question
- If verification fails, route back to the upstream stage that must be reworked

### Escalation
- Keep escalation open when risk prevention, recovery path, or governance correction is still incomplete

### Learning Promotion
- Decide whether the result should stay local, be promoted into repeatable guidance, or be captured as a reusable learning

## Non-Negotiables
- Do not rely on scripts as sole truth
- Separate evidence from inference
- Separate unverified hypotheses from confirmed findings
- Perform reverse verification
- If verification fails, route back upstream
