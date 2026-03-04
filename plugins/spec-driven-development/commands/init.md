---
description: Initialize SDD in the current project
---

# Context
This command initializes spec-driven development in the current project. It sets up the required folder structure and steering documents.

# Tasks

## 1. Create the specs folder
- Create `./specs/` folder at the project root if it doesn't already exist

## 2. Create the specs index
- Create `./specs/index.md` if it doesn't already exist
- Use the following template:

```markdown
# Specs Index

## Steering Documents
- [product.md](./product.md) - Business-level overview of the application

## Feature Specs

| # | Slug | Description | Status |
|---|------|-------------|--------|
```

## 3. Create the product steering document
- Create `./specs/product.md` if it doesn't already exist
- Research the project to infer the product context: read README, CLAUDE.md, package.json, and any other relevant files
- Write a concise business-level overview covering: purpose, target users, core value proposition, and key capabilities

## 4. Update CLAUDE.md
- Open the root `CLAUDE.md` file (create it if it doesn't exist)
- Add the following section if not already present (adapt if a Development Process section already exists):

```markdown
## Development Process

### Steering Documents
The `./specs` folder contains steering documents for the project:
- `./specs/product.md` - Business-level overview of the application
- `./specs/index.md` - Index of all feature specs

### Spec-Driven Development
For each new major feature, create a new folder in `./specs` with sequential numbering (e.g., `001-feature-name`) containing:
- `requirements.md` - Detailed description of the feature requirements
- `design.md` - Detailed design of the feature
- `tasks.md` - List of tasks, grouped by phases, to implement the feature

### Documentation
When a user request is completed, create or update documentation in `./documentation` to reflect the changes:
1. Keep one file per functional or technical domain area
2. **Always update `./documentation/index.md`** when adding new documentation files
3. Before finishing any task that adds or modifies features, check if documentation needs updating
4. Reference `./documentation/index.md` to see existing documentation topics
```

## Important
- Do not overwrite existing content in CLAUDE.md — append or merge the section
- Do not overwrite existing `./specs/product.md` or `./specs/index.md` — warn the user if they already exist
- Keep all output concise and suitable for AI agent consumption
