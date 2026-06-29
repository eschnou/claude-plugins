# Spec-Driven Development (SDD)

A structured workflow for creating feature specifications through three sequential commands. Each command produces a document in your project's `specs/[slug]/` folder.

## Commands

### `/sdd:init`

Initializes SDD in the current project.

### `/sdd:requirement [slug] [description]`

Defines **what** to build and **why**. Produces `requirements.md` with:
- Feature overview and alignment with product vision
- User stories with acceptance criteria
- Non-functional requirements

### `/sdd:design [slug] [focus]`

Defines **how** to architect it. Produces `design.md` with:
- High-level architecture
- Components and interfaces
- Data models, error handling, testing strategy
- Performance, security, and observability considerations

### `/sdd:plan [slug] [focus]`

Defines the **steps** to build it. Produces `tasks.md` with:
- Phases — testable increments with integration-level verification
- Tasks — unit-level steps within each phase

### `/sdd:go [slug] [focus]`

Executes the plan. Implements `tasks.md` phase by phase:
- Creates a `feature/<ticket-or-slug>` branch when in a git repo
- Validates each phase with tests before moving to the next
- Updates `tasks.md` as each phase completes, documenting any design deviations
- Updates documentation and runs `simplify` at the end (no commit)

### `/sdd:verify [slug] [focus]`

Verifies the implementation without changing anything. Runs in parallel:
- The `code-review` skill on the current diff
- A subagent checking compliance with `requirements.md` and `design.md`

Produces a single report ordering findings by criticality and effort, with an opinionated recommendation on what to fix now versus defer. Does **not** auto-fix.

## Usage

Run commands sequentially for a feature:

```
/sdd:init
/sdd:requirement auth-flow "Add OAuth2 login with Google and GitHub providers"
/sdd:design auth-flow "Focus on token refresh and session management"
/sdd:plan auth-flow "Start with Google provider, add GitHub in phase 2"
/sdd:go auth-flow
/sdd:verify auth-flow
```

## Install

Add the marketplace, then install:
```
/plugin marketplace add eschnou/claude-plugins
/plugin install sdd@eschnou-claude-plugins
```
