---
argument-hint: [slug] [focus]
description: Create a design document
---

# Context
- Every complex feature we build is firt documented using spec-driven-devleopment in a folder in @/specs/
- The design.md document acts as a detailed softare architecture and design document
- Prior to writing the document you must proceed to extensive research to understand how to best transalte the requirements into a proper design

# Design document guidelines

## Structure of the document
- Overview: A summary of the feature goal and high level design
- Architecture: A high level architecture diagram of the solution
- Compoments and Interfaces: A description of key componments and interfaces to be added or changed
- Data Models: covering new and updated entities and DTOs
- Error Handling: how the system will manage errors and exceptions
- Testing strategy
- Performance considerations
- Security considerations
- Monitoring and Observability


## Style of the design document
This document is meant to be consumed by a coding agent. Therefore, you have to write for your own consumption:
- No sueprflous language, keep it concise
- No unnecessary information
- No estimates, timelines, etc.

## Research guidelines
- Read @/specs/index.md to find the spec folder matching `$1` (match by slug, e.g., `$1` matches `001-$1`)
- Do read the requirements in the matching spec folder
- Lookup for latest documentation online when needed
- Research the codebase
- Update @/specs/index.md to reflect that design is now in progress/complete

Additional details provided by the user:
$2
