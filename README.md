# AI Collaboration

A lightweight collaboration contract for working with AI agents.

`AGENTS.md` is the contract. It defines how the AI and Rennll collaborate; it is not a task workflow, prompt template, or checklist.

Project-specific context is optional. If used, `context/` holds only information worth carrying across sessions that cannot be reliably derived from the project itself. Session-only instructions and preferences do not belong there.

This is **v1**: intentionally small, platform-independent, and expected to evolve from real collaboration experience.

## For humans

Copy `AGENTS.md` into a project to adopt the contract. Nothing else is required. Add project context only when there is a real need for persistent information outside the repository's canonical sources.

The contract is designed around judgment rather than rigid procedures. It does not attempt to encode every preference, decision, or mistake into permanent instructions.
