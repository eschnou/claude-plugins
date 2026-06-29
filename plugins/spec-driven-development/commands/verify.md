---
argument-hint: [slug] [focus]
description: Verify the implementation
---

# Context
- Every complex feature we build is first documented using spec-driven-development in a folder in @/specs/
- This command verifies an implementation against its spec and reviews the code, without changing anything
- It produces a report only — it does NOT fix issues automatically

# Verification guidelines

## Setup
- Read @/specs/index.md to find the spec folder matching `$0` (match by slug, e.g., `$0` matches `001-$0`)
- Read `requirements.md`, `design.md`, and `tasks.md` in the matching spec folder
- If the Jira ticket is known and the Jira MCP is available, transition the ticket to "In Review"

## Checks
Run the following two checks. They are independent — run them in parallel.

1. **Code review** — Run the `code-review` skill on the current diff to surface correctness bugs and quality issues.

2. **Spec compliance** — Launch a subagent (general-purpose) that verifies the implementation against the spec:
   - Confirm every requirement and acceptance criterion in `requirements.md` is met
   - Confirm the implementation complies with `design.md` (architecture, components, data models, error handling, security)
   - Confirm every phase and task in `tasks.md` marked complete is actually implemented and tested
   - If the Playwright MCP is available, you may launch the application and verify the feature visually. Do not waste resources trying to make Playwright work — if it is unavailable or fails to start, skip it and rely on the other checks
   - Report gaps, deviations, and unmet criteria — do not fix them

## Report
- Do NOT fix anything. Report only.
- Consolidate findings from both checks into a single report
- Order findings by criticality first, then by effort
- For each finding include: criticality (critical / high / medium / low), effort (low / medium / high), the source (code-review or spec-compliance), and a concise description
- End with an opinionated recommendation: what should be fixed now, and what can reasonably be ignored or deferred — with brief justification

Additional details provided by the user:
$ARGUMENTS
