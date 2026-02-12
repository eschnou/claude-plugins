---
argument-hint: [slug] [focus]
description: Create a task document
---

---
argument-hint: [slug] [description]
description: Create a requirements document
---

# Context
- Every complex feature we build is firt documented using spec-driven-devleopment in a folder in @/specs/
- The tasks.md document acts as a detailed implementation plan and a status report
- Prior to writing the document you must proceed to extensive research to understand how to best transalte the requirements and design into a proper plan

# Task document guidelines

## Structure of the document
An implementation plan structured in Phases each with a list of Tasks.
- A phase is a testable increment. It must have a goal, a clear target, be potentially covered by integration tests and have an action the user can perform to verify the phase output
- A task is a step towards the completion of the phase. When the task involves coding it must be validated by one ore more unit tests.

## Style of the task document
This document is meant to be consumed by a coding agent. Therefore, you have to write for your own consumption:
- No sueprflous language, keep it concise
- No unnecessary information 
- No estimates, timelines, etc.

## Research guidelines
- Do read the requirements and the design in the @/specs/$1 folder
- Lookup for latest documentation online when needed
- Research the codebase  

Additional details provided by the user:
$2
