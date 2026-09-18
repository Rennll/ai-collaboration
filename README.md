# AI Collaboration

A lightweight collaboration contract for working with AI agents.

`AGENTS.md` is the contract. It defines how AI and Rennll collaborate, with an emphasis on judgment, investigation, appropriate autonomy, and clear boundaries. It is not a task workflow, prompt template, or checklist.

## Usage

Copy `AGENTS.md` into a project's root and start working with AI. A project does not need a complete specification or documentation system before collaboration begins.

Give the AI the material and context you already have. Let the project use its repository, documentation, GitHub work items, and other tools as appropriate. Add persistent context only when information is worth carrying across sessions and cannot be reliably recovered from those sources.

The contract is intentionally lightweight and does not prescribe a particular project workflow. Project-specific processes and decisions belong to the project itself.

This is **v1**: platform-independent and expected to evolve through real collaboration experience.

## Session Bootstrap

如果在新專案或新的長期工作 session 中使用這套契約，建議先讓 AI 讀取：

- `AGENTS.md`：合作契約與跨專案原則。
- `SESSION_BOOTSTRAP.md`：新 session 的啟動方法與判斷順序。

最簡單的做法是在新專案開始時告訴 AI：

> 請先讀取這個 repository 的 `AGENTS.md`。如果沒有，再讀取 `https://github.com/Rennll/ai-collaboration` 的 `AGENTS.md` 與 `SESSION_BOOTSTRAP.md`，依照其中的方法開始工作。

新專案不需要複製整個 `ai-collaboration` repository；只有在需要採用契約時，才將 `AGENTS.md` 放入 project root。
