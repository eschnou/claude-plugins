# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This repository is a Claude Code plugins marketplace — a collection of independently installable plugins. Structured following the `anthropics/claude-plugins-official` pattern.

## Repository Structure

```
claude-plugins/
├── .claude-plugin/
│   └── marketplace.json           # Root registry of all plugins
├── plugins/
│   └── spec-driven-development/
│       ├── .claude-plugin/
│       │   └── plugin.json        # Plugin metadata
│       ├── commands/
│       │   ├── requirements.md    # /requirements [slug] [description]
│       │   ├── design.md          # /design [slug] [focus]
│       │   └── implement.md       # /implement [slug] [focus]
│       └── README.md
├── CLAUDE.md
├── README.md
├── LICENSE
└── .gitignore
```

No build system, package manager, or tests — this is a pure markdown/JSON plugin definitions repository.

## Adding a New Plugin

1. Create `plugins/<plugin-name>/` with a `commands/` folder and `.claude-plugin/plugin.json`
2. Register it in `.claude-plugin/marketplace.json` under the `plugins` array
3. Add a `README.md` to the plugin folder

## SDD Plugin (spec-driven-development)

The three commands form a sequential pipeline, each producing a document in the target project's `specs/[slug]/`:

1. **Requirements** — Defines WHAT to build and WHY. Creates user stories with acceptance criteria.
2. **Design** — Defines HOW to architect it. Covers components, data models, error handling, testing, security, and observability.
3. **Implementation** — Defines the STEPS to build it. Organized as testable phases containing tasks.

## Writing Conventions for Commands

- Documents target AI agent consumption: concise, no superfluous language, no estimates/timelines.
- Every command includes a research phase (codebase + online docs) before writing.
- Commands reference `@/specs/` folder structure in the target project, not in this repo.
