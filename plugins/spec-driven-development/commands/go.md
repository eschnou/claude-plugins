---
argument-hint: [slug] [focus]
description: Implement the plan
---

# Context
- Every complex feature we build is first documented using spec-driven-development in a folder in @/specs/
- This command executes the implementation described in the `tasks.md` document, phase by phase
- The implementation must comply with the `design.md` document
- Prior to writing any code you must read the requirements, design, and tasks documents to fully understand what to build

# Implementation guidelines

## Setup
- Read @/specs/index.md to find the spec folder matching `$0` (match by slug, e.g., `$0` matches `001-$0`)
- Read `requirements.md`, `design.md`, and `tasks.md` in the matching spec folder
- If the project is a git repository, create and checkout a feature branch before any change:
  - If a ticket number is known (from the slug, tasks document, or user input), name it `feature/<ticket-number>`
  - Otherwise name it `feature/NNN-slug` (the same name as the spec folder)
  - If the branch already exists, checkout it instead of recreating it
- Update @/specs/index.md to reflect that implementation is now in progress
- If the Jira ticket is known and the Jira MCP is available, transition the ticket to "In Development"

## Execution
- Implement the plan one phase at a time, in order
- Do not start a phase until the previous phase passes its tests and verification
- For each phase:
  1. Implement every task in the phase, validating each coding task with unit tests
  2. Run the phase's integration tests and verification action to confirm the increment works
     - If the Playwright MCP is available, you may launch the application and test the phase output visually. Do not waste resources trying to make Playwright work — if it is unavailable or fails to start, skip it and rely on the other tests
  3. Update `tasks.md` to mark the phase and its tasks complete (update at end of phase)
  4. Only then move to the next phase

## Design compliance
- The implementation must comply with `design.md`
- If an issue forces a deviation from the design, make a reasonable common-sense decision, then:
  - Document the deviation in `tasks.md`
  - Flag every deviation to the user when the implementation is complete

## Completion
- Update documentation in @/documentation to reflect the implementation (see CLAUDE.md documentation guidelines)
- Update @/specs/index.md to reflect that implementation is complete
- Run the `simplify` skill to simplify and clean up the work
- Do NOT create a commit — this will be done later
- Report a summary to the user, including any design deviations that were flagged

Additional details provided by the user:
$ARGUMENTS
