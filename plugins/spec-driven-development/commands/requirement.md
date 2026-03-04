---
argument-hint: [slug] [description]
description: Create a requirements document
---

# Context
- Every complex feature we build is firt documented using spec-driven-devleopment in a folder in @/specs/
- The requirement document act as a bridge between business needs from the customer and a design document detailing the implementation architecture
- Prior to writing the document you must proceed to extensive research to understand how to detail requirements that match the applicqtion business goal and design patterns

# Requirements document guidelines

## Structure of the document
1. Introduction: Provide a brief overview of the feature, its purpose, and its value to users
2. Alignement with product vision: Explain how this feature supports the goals outlined in @/specs/product.md
3. Requirements: A list of requirements. Each requirement as a User Story (As a [role], I want [feature], so that [benefit]) and a set of acceptance criteria
3. Non funtcional requirements: with respect to architecture,  performance, security, reliability and usability

## Style of the requirement document
This document is meant to be consumed by a coding agent. Therefore, you have to write for your own consumption:
- No superflous language, keep it concise
- No unnecessary information
- No estimates, timelines, etc.

## Tasks
- Read @/specs/index.md to determine the next sequential number (NNN format, e.g., 001, 002, 003)
- Create a new folder under ./specs/ named `NNN-$1` (e.g., `001-auth-flow`)
- Research the codebase to understand the feature request in the context of the application
- Lookup for latest documentation online when needed
- Producte the requirements.md file in the target folder
- Update @/specs/index.md to add the new spec entry

# User request
Feature name: $1

Feature description:
$2
