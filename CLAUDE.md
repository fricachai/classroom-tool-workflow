# _班級工具工作模式 - 班級工具工作模式

## 對話開始時請先讀
進度與最近更動都在 Obsidian：$modeName/工作筆記.md

## 你的專案整理方式
- 所有新工具都採用「一個專案一個資料夾」。
- 新專案直接建立在：$base\<專案名稱>
- 不使用 	ools/<工具名> 這種集中式子資料夾。
- 本資料夾 $modeName 只保存工作模式、規則、技能說明與總工作筆記連結。

## 工作模式
- **加新工具**：使用者說「我想做一個 XXX 工具」時，先在 $base\<專案名稱> 建立獨立資料夾。
- **結束工作**：使用者說「收工」時，更新 Obsidian 工作筆記、commit、push。
- **接續工作**：使用者說「開工」或「上次做到哪」時，讀工作筆記、檢查 git 狀態、建議下一步。

## 三個家
- 本機專案資料夾：$base
- GitHub repo：每個工具可有自己的公開 repo。
- Obsidian 駕駛艙：$vault\_班級工具工作模式\工作筆記.md
- Firebase 專案：my-teaching-tools-aa826

## 新工具命名規則
- 資料夾名稱可用中文或英文，但 GitHub repo 建議用英文小寫加連字號。
- 例：座標獵人 本機資料夾可以叫 座標獵人，GitHub repo 可叫 coordinate-hunter。

## 工具清單
- firebase-wordcloud：Firebase 文字雲，已部署到 Firebase Hosting。

## 工作注意事項
- 學生資料一律去識別化，只用座號與班級代號。
- 每個專案都要有自己的 .gitignore。
- .claude/、.codex/、.env、金鑰、token 不可 commit。
- Firebase Config 可以公開，但 Admin key、service account、private key 絕不可公開。
- 每次新增 Firestore collection 都要同步更新 Security Rules。

## SessionEnd 安全網
- 已安裝 Windows PowerShell 版 SessionEnd hook。
- 腳本：`C:\Users\user\.claude\scripts\session-cleanup.ps1`
- 設定：`C:\Users\user\.claude\settings.json`
- 只處理 `D:\USB_Data\個人研究\實用分析分類\ChatGPT_個人累積\ChatGPT_Codex_專案資料夾` 底下的 Git repo。
- 只自動提交已追蹤檔案的修改，不會把新檔案或敏感檔亂加進 Git。

