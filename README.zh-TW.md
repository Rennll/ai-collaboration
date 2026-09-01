# AI Collaboration

一份輕量、以 AI agent 為對象的合作契約，用來定義 Rennll 與 AI 如何共同工作。

`AGENTS.md` 就是契約本身。它定義合作時的判斷方式與邊界，不是一套 task workflow、prompt template 或 checklist。

Project-specific context 是可選的。若有需要，`context/` 只保存值得跨 session 延續、且無法可靠從 project 本身取得的資訊。只適用於當前 session 的指示與偏好不需要保存。

這是 **v1**：刻意保持精簡、與平台無關，並預期從實際合作經驗中逐步演進。

## 給人類

要在一個 project 採用這份契約，只需要將 `AGENTS.md` 複製到 project root；其他都不是必要的。只有在確實需要保存 repository 本身無法提供的跨 session 資訊時，才建立 `context/`。

這份契約以判斷而非固定程序為核心。不試圖把每個偏好、決定或錯誤都變成永久規則。
