# AI Collaboration

A lightweight, agent-native collaboration contract and context model for working with AI agents.

The project is designed around principles and judgment rather than a rigid workflow. `AGENTS.md` defines the default collaboration contract between Rennll and AI agents. Project-specific context lives under `context/`, with reusable templates under `templates/`.

## Structure

- `AGENTS.md` — collaboration contract: principles, preferences, constraints, roles, context/memory rules, and contract evolution.
- `context/project.md` — project-specific facts, decisions, constraints, and temporary assumptions.
- `context/environment.md` — relatively stable environment details that materially affect work.
- `templates/` — minimal templates for adopting the context model in other projects.

The repository intentionally avoids platform-specific workflows and does not require every project to adopt every file or section.
