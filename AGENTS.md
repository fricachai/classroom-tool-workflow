# 班級工具工作模式

## 目的

這個資料夾是班級工具開發流程的總控資料夾，不是單一教學工具。主要規則放在本檔案，供 Codex 與其他 coding agents 讀取。

## 專案位置規則

使用者偏好「一個專案一個資料夾」。所有新工具都直接建立在：

```text
D:\USB_Data\個人研究\實用分析分類\ChatGPT_個人累積\ChatGPT_Codex_專案資料夾\<專案名稱>
```

不要建立成：

```text
班級工具工作模式\tools\<工具名>
```

除非使用者明確要求，否則新專案資料夾與 Obsidian 對應資料夾不要使用 `_` 開頭。

## 重要路徑

- 專案根目錄：`D:\USB_Data\個人研究\實用分析分類\ChatGPT_個人累積\ChatGPT_Codex_專案資料夾`
- 工作模式資料夾：`D:\USB_Data\個人研究\實用分析分類\ChatGPT_個人累積\ChatGPT_Codex_專案資料夾\班級工具工作模式`
- Obsidian vault：`G:\我的雲端硬碟\Obsidian\2ndbrain`
- Obsidian 工作筆記：`G:\我的雲端硬碟\Obsidian\2ndbrain\班級工具工作模式\工作筆記.md`
- Firebase 專案：`my-teaching-tools-aa826`

## 工作模式

- 使用者說「開工」或「上次做到哪」：讀 Obsidian 工作筆記，檢查 git 狀態，摘要進度，建議下一步。不要修改檔案。
- 使用者說「收工」：更新 Obsidian 工作筆記，commit 並 push 相關專案變更。
- 使用者說「我想做一個 XXX 工具」：在專案根目錄下建立獨立資料夾，並為該工具建立自己的 Git repo、README、部署流程與 Obsidian 工作筆記。

## Git 與 GitHub

- 每個工具可以有自己的 GitHub repo。
- commit 訊息要清楚描述做了什麼與為什麼。
- D 槽中文路徑若遇到 dubious ownership，使用 `git config --global --add safe.directory <path>`。
- 在 Google Drive 或同步資料夾內使用 git 時，設定 `git config windows.appendAtomically false`。

## Obsidian

- 使用 Obsidian vault 作為工作筆記累積處。
- 每個專案建議有對應筆記：`<專案名稱>/工作筆記.md`。
- 工作筆記記錄：上次做到哪、最近更動、工具清單、踩坑筆記、下一步。
- 不要把同一份進度同時維護在多個地方，以 Obsidian 工作筆記為進度主檔。

## Firebase

- 目前 Firebase 專案：`my-teaching-tools-aa826`。
- 新增 Firestore collection 時要同步更新 Security Rules。
- Firebase Web config 可以放前端；Admin key、service account、private key 絕不可公開。

## 安全規則

- 學生資料必須去識別化，只使用班級代號與座號，不存真名。
- 不要 commit `.claude/`、`.codex/`、`.env`、金鑰、token、service account。
- 每個專案都要有自己的 `.gitignore`。

## SessionEnd 安全網

已安裝 Windows PowerShell 版 SessionEnd hook：

```text
C:\Users\user\.claude\scripts\session-cleanup.ps1
```

設定檔：

```text
C:\Users\user\.claude\settings.json
```

行為：

- 只處理專案根目錄底下的 Git repo。
- 只自動提交已追蹤檔案的修改。
- 不會自動新增未追蹤檔案，避免把敏感檔誤 commit。

## 現有工具

- Firebase 文字雲
  - 本機：`D:\USB_Data\個人研究\實用分析分類\ChatGPT_個人累積\ChatGPT_Codex_專案資料夾\Test Data`
  - GitHub：https://github.com/fricachai/firebase-wordcloud
  - Hosting：https://my-teaching-tools-aa826.web.app