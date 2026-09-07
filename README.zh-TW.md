# AI Collaboration

一份輕量、以 AI agent 為對象的合作契約，用來定義 Rennll 與 AI 如何共同工作。

`AGENTS.md` 就是契約本身。它定義合作時的判斷方式與邊界，不是一套 task workflow、prompt template 或 checklist。

## 使用方式

把 `AGENTS.md` 放進 project root，然後直接開始和 AI 合作。不需要先準備完整規格，也不需要先建立一套文件系統。

如果只是 project 構想，可以直接把想法、草稿、設計筆記或其他已有資料交給 AI。AI 應先理解目標、調查可取得的資訊、整理需求與風險；需要人類判斷的事情，再由人類決定。

Project 開始實作後，讓資訊留在適合它的位置。穩定的 project 知識放在 repository 或 canonical documentation，需要追蹤的工作使用 GitHub work items。只有值得跨 session 保存、又無法從現有來源可靠恢復的資訊，才需要額外的 persistent context。

## 基本原則

- 先理解真正的目標，再決定怎麼做。
- 能自行調查的事情先調查，不要不必要地要求人類提供答案。
- AI 可以自主處理合理且可逆的事情；重大取捨或難以逆轉的決定交由人類判斷。
- 不因為「可能有用」就提前建立大量文件、流程或 context。
- 穩定的規則與 project 知識應放在適合的 canonical source，而不是重複保存。
- 合作契約應保持輕量，不把每一次錯誤或偏好都變成永久規則。

這是 **v1**：刻意保持精簡、與平台無關，並預期從實際合作經驗中逐步演進。