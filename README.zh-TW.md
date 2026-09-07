# AI Collaboration

一份輕量、以 AI agent 為對象的合作契約，用來定義 Rennll 與 AI 如何共同工作。

`AGENTS.md` 就是契約本身。它定義合作時的判斷方式與邊界，不是一套 task workflow、prompt template 或 checklist。

這份契約的使用方式很簡單：把 `AGENTS.md` 放進 project root，然後直接開始和 AI 合作。不需要先建立一套 context、workflow 或 onboarding 文件。

## 給人類

如果你有一個新的 project 構想，不需要先把想法整理成正式規格。可以直接把構想、README 草稿、設計筆記、截圖或其他現有資料交給 AI，先一起討論。

AI 應先理解你真正想解決的問題，整理需求、假設、風險與需要做的決策；能從現有資料或工具取得的資訊，應先自行調查，而不是把問題全部丟回來。當需要人類判斷、涉及重大取捨，或後果難以逆轉時，再請你決定。

當 project 開始落地後，依需要使用 repository 本身、GitHub Issues、討論區與其他適合的工具保存資訊。穩定且屬於 project 的知識應放在 project 的 canonical documentation；工作事項放在 GitHub work items；不要為了讓 AI「記得」而另外建立大量 context 文件。

`context/` 是可選的 fallback。只有當某些資訊值得跨 session 延續，而且無法可靠從 repository、GitHub 或其他可用工具恢復時，才值得保存。只適用於當前 session 的指示、偏好、觀察或授權，不需要變成永久文件。

因此，一個新的 project 可以從很簡單的流程開始：

「構想 → 與 AI 討論與釐清 → 建立 project → 放入 `AGENTS.md` → 視需要建立 GitHub work items / canonical docs → 開始實作」

這不是強制 workflow，而只是最自然的使用方式。重點是不要在真正需要之前，先建立一套文件系統。

這是 **v1**：刻意保持精簡、與平台無關，並預期從實際合作經驗中逐步演進。

這份契約以判斷而非固定程序為核心。不試圖把每個偏好、決定或錯誤都變成永久規則。