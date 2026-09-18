# Session Bootstrap

這份文件定義 AI 在「新專案」或「新的長期需求」開始時，如何快速建立正確的工作上下文。

## 目的

不要要求 Rennll 重複提供已存在於 repository、GitHub、文件或 tooling 中的資訊。

AI 應先自行調查，再開始實作；只有在調查後仍存在需要人類決定的選擇時才詢問。

## 啟動順序

### 1. 先找本地契約

在 project root 檢查：

- `AGENTS.md`
- `README.md`
- 專案自己的 contributor/development instructions
- 相關的 canonical documentation

如果存在本地 `AGENTS.md`，先讀它。

如果不存在，而且需要採用 Rennll 的跨專案合作契約，讀取：

`https://github.com/Rennll/ai-collaboration/blob/main/AGENTS.md`

以及本文件。

### 2. 先理解 repository，再問問題

先檢查：

- repository 結構
- README
- 現有 tests
- CI/CD
- issue / PR（若可取得）
- 現有實作與設定

不要因為需求描述很短，就立刻要求 Rennll 補規格。

先從現有證據推導可以推導的部分。

### 3. 區分「可推導」與「需要決定」

如果下一步可以由既有需求、程式碼、測試或架構合理推導：

直接做，不要升級成問題。

如果存在多個合理方向，而且沒有現有資訊可以決定：

整理選項、影響與取捨，請 Rennll 決定。

也就是：

**不要詢問推導；詢問選擇。**

### 4. 對新需求的處理

收到新需求時，依序判斷：

1. 這是在修改現有功能，還是新的 project？
2. 現有 repository 是否已經有相關實作？
3. 是否已有測試、文件或 GitHub work item 定義行為？
4. 哪些部分可以直接實作？
5. 哪些部分真的需要 Rennll 的決策？

先處理可以確定的部分。

### 5. 建立持久資訊前先找 canonical source

不要因為「以後可能有用」就建立 context 文件。

優先使用：

- repository code
- README / canonical documentation
- tests
- GitHub issues / PRs
- tooling

只有資訊值得跨 session 保存，而且無法從上述來源可靠恢復時，才建立額外 persistent context。

### 6. 完成前驗證

不要只確認「程式改了」。

至少確認：

- 需求是否真的達成
- 相關 tests 是否通過
- CI 是否通過（如果專案有 CI）
- 是否引入不必要的複雜度
- 是否有未處理的風險

如果無法驗證，要明確說明尚未驗證的部分。

## 新專案的最小啟動提示

如果 AI 沒有自動讀取 repository instructions，可以直接使用：

> 請先讀取這個 repository 的 AGENTS.md、README 與相關專案文件。若沒有 AGENTS.md，請讀取 https://github.com/Rennll/ai-collaboration 的 AGENTS.md 與 SESSION_BOOTSTRAP.md。先調查現有程式碼、測試、CI 與文件，再開始處理需求；能推導的不要問我，需要我做取捨的再問。

## 與 AGENTS.md 的關係

`AGENTS.md` 是跨專案合作契約本身。

`SESSION_BOOTSTRAP.md` 是啟動方法。

前者回答「AI 應如何與 Rennll 合作」，後者回答「新的 session 開始時，AI 應該先做什麼」。

不要把單一專案的技術決策、臨時需求或 session-only 資訊寫進這份文件。
