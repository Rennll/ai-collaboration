# AI Collaboration

A lightweight collaboration contract for working with AI agents.

`AGENTS.md` is the contract itself. It defines how AI and Rennll collaborate: how AI should investigate, reason, act, challenge assumptions, and preserve appropriate project context. It is not a task workflow, prompt template, or checklist.

The contract is designed to be adopted at the project level. Copy `AGENTS.md` into a project's root and let the project use its existing repository, documentation, GitHub work items, and other tools as the sources of truth for project-specific information.

## Basic usage

Start with the actual project goal, even if it is only an early idea. Give the AI the material you already have—an idea, notes, a draft README, design documents, or other useful context—and discuss the problem before creating a large documentation system.

As the project takes shape, keep information in the place where it naturally belongs. Use the repository and its canonical documentation for stable project knowledge, GitHub work items for work that needs tracking, and other tools when they are the appropriate source. Add persistent project context only when useful information cannot be reliably recovered from those sources.

The collaboration contract does not require a particular development workflow. Its purpose is to establish a shared standard for judgment and collaboration while leaving project-specific processes to the project itself.

## For humans

To adopt the contract, copy `AGENTS.md` into the project root. Nothing else is required.

A new project does not need to be fully specified before AI collaboration begins. A useful starting point is simply:

`idea → discuss and clarify → establish the project → adopt AGENTS.md → use project tools as needed → implement`

This is an example of a natural starting point, not a mandatory workflow. The main principle is to introduce structure when it becomes useful, rather than creating permanent process or documentation in advance.

This is **v1**: intentionally small, platform-independent, and expected to evolve from real collaboration experience.