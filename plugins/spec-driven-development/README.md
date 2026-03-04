# Spec-Driven Development (SDD)

A structured workflow for creating feature specifications through three sequential commands. Each command produces a document in your project's `specs/[slug]/` folder.

## Commands

### `/requirements [slug] [description]`

Defines **what** to build and **why**. Produces `requirements.md` with:
- Feature overview and alignment with product vision
- User stories with acceptance criteria
- Non-functional requirements

### `/design [slug] [focus]`

Defines **how** to architect it. Produces `design.md` with:
- High-level architecture
- Components and interfaces
- Data models, error handling, testing strategy
- Performance, security, and observability considerations

### `/implement [slug] [focus]`

Defines the **steps** to build it. Produces `tasks.md` with:
- Phases — testable increments with integration-level verification
- Tasks — unit-level steps within each phase

## Usage

Run commands sequentially for a feature:

```
/requirements auth-flow "Add OAuth2 login with Google and GitHub providers"
/design auth-flow "Focus on token refresh and session management"
/implement auth-flow "Start with Google provider, add GitHub in phase 2"
```

## Install

```
/install spec-driven-development@eschnou/claude-plugins
```
