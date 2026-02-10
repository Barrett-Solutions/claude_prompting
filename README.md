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
The general idea of agents (or sub-agents) is that they can have specialized expertise (test-first, planning) and they can be handed a specific task (part of the plan) to accomplish on their own. I beleive they have their own context window and are only given the parts of the plan that are necessary. They don't need to hold the entire context or the entire plan. 
A key trade off is that using an agent is trading direct control for efficiency. Instead of telling the LLM to "create file X that will do ...". The agent is giving relevant information from the plan and then left to complete the task. 

## Installation
- Download the release and unzip it.
- Copy the .claude folder to your repo
- Copy the CLAUDE.md file to the base of your repo

## ToDo 
- Figure out how to share these files (prompts and agents) with other LLMs or IDEs 
    - Antigravity 
    Antigravity allows the use of different LLM models, including Claude. If we choose claude models, we are probably fine.

        - The internet says that Antigravity will read GEMENI.md at the start of every session
        - Does Antigravity have agents?
        - It appears that Antigravity has rules and skills

    - Cursor
        - What files will Cursor read at the beginning of every session?
        - Rules sound like Claudes version of KB files
            - The file is called .cursorrules at the root of the repo.
            - How does one have multiple cursorrules?
        - Something about Agents

- Update style-guide to remove entries about tabs, whitespace, line lengths, etc. **Configure a linter!!**
    Perhaps a skill that will invoke prettier and then fix any problems?

- Update planning to produce a more concise or less verbose plan. I feel that Claude can get a bit wordy when making plans. Concise plans __may__ be better for handing off to sub-agents. 
Maybe just ask the user if they would like a more concise plan?
- 

### Bibliography
- https://github.com/VoltAgent/awesome-claude-code-subagents
- https://github.com/ThePassionateProgrammer/knowledge-base-starter
- https://antigravity.google/docs/agent-modes-settings
