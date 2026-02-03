## What is This?

This is a set of knowledge base files (aka prompts) that helps Claude Code understand our development preferences, coding standards, and project-specific practices. Instead of repeating instructions in every session, we have created a set of reference documents that Claude reads as needed.

Think of it as teaching Claude how we want to work — philosophy, rhythm, patterns.

## CLAUDE.md
Claude code automatically reads this file at the start of every session. So it basically tells Claude to also read the rest of the files that we want it too.

## Core Files (Read at Session Start)

- **[index.md](.claude/index.md)** - Start here! Navigation and usage guide
- **[style-guide.md](.claude/style-guide.md)** - Coding standards and Unit Testing conventions
- **[working-agreement.md](.claude/working-agreement.md)** - Partnership charter


## Agents
There are two agents, a planning agent and a implementing agent.
- [typescript-planner.md](.claude/agents/typescript-planner.md) - This agent will be used to build the plan
- [test-first-partner.md](.claude/agents/test-first-partner.md) - This agent will be used when implementing the plan.

## Installation
- Copy the .claude folder to your repo
- Put the CLAUDE.md file in the root of the repo.



### Bibliography
- https://github.com/VoltAgent/awesome-claude-code-subagents
- https://github.com/ThePassionateProgrammer/knowledge-base-starter
