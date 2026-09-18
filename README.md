# AI Collaboration

A lightweight, AI-agent-oriented collaboration contract defining how Rennll and AI work together.

`AGENTS.md` is the contract itself. It defines collaboration judgment and boundaries, not a task workflow, prompt template, or checklist.

## Usage

Copy `AGENTS.md` into the project root and start collaborating with AI. You do not need to prepare a complete specification or build a documentation system first.

If you only have a project idea, give the idea, drafts, design notes, or whatever material you already have to AI. AI should first understand the goal, investigate available information, organize requirements and risks, and involve the human when human judgment is needed.

Once a project is being implemented, keep information where it belongs. Stable project knowledge belongs in the repository or canonical documentation; work that needs tracking belongs in GitHub work items. Only information worth preserving across sessions that cannot be reliably recovered from existing sources needs additional persistent context.

## Principles

- Understand the real goal before deciding how to implement it.
- Investigate what can be investigated before asking the human for answers.
- AI may autonomously handle reasonable and reversible work; significant trade-offs or irreversible decisions belong to the human.
- Do not create extensive documentation, processes, or context merely because they might be useful later.
- Stable rules and project knowledge should live in the appropriate canonical source instead of being duplicated.
- Keep the collaboration contract lightweight; do not turn every mistake or preference into a permanent rule.

This is **v1**: platform-independent and expected to evolve through real collaboration experience.
