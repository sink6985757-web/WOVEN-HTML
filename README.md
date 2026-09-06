# Woven Prompt HTML

## 2026-09-06 更新

目前版本為 **2.1.0（44）**，由最新 App 的相符來源建立：新增繁體中文／English 切換、四區進階生成流程與共用使用說明。既有永久 License 繼續有效；新版與舊版檔案分開保存。

## 開工與收工

1. 首次使用或治理缺件才執行 `initial`；既有專案平日直接 `startup`。
2. 開工讀取 [manifest](.agents/project-lifecycle.json)、[AGENTS.md](AGENTS.md)、[handoff.md](handoff.md)，確認 Git root 與 `origin`，fetch 後分別比較目前 upstream 和 default branch `main`。fetch 不會同步工作樹。
3. 在已確認範圍內修改與驗證。未提交內容、版本分叉與 unknown untracked 先保全、辨識，不直接覆蓋或整包 stage。
4. 收工更新 [CHANGELOG.md](CHANGELOG.md) 與 handoff；使用 `manual` checkpoint，沿用當次已確認工作單的 commit／push 授權。只有遠端 SHA 回讀一致才算 GitHub 同步完成；Drive 同步另行回讀。

固定 authority commit、專案 identity 與窄範圍文件 allowlist 見 manifest。一般開工不執行安裝、部署或外部帳號動作；既有 tag／Release、封存來源與私人設定依各自邊界維持。

**一個固定連結，讓你不用安裝 App，也能從電腦或手機瀏覽器開啟 Woven Prompt。**

[🌐 立即開啟 Woven Prompt HTML](https://sink6985757-web.github.io/WOVEN-HTML/)　[⬇️ 下載目前離線單檔](https://sink6985757-web.github.io/WOVEN-HTML/woven-prompt-mobile-2.1.0-v44.html)

這是 Woven Prompt 官方 HTML 的公開入口。只要記住同一個網址，就能回到目前推薦版本；你也可以把單檔 HTML 下載到自己的裝置，在需要時離線開啟。

> 入口公開給所有人，但正式離線版仍需匯入透過 Woven Prompt APK 流程核發給你的個人 License。請勿公開或轉傳個人 License。

## 為什麼這個入口更方便

- **不用另外安裝**：開啟連結就能進入，適合臨時換電腦、平板或手機使用。
- **固定網址、持續更新**：之後版本更新仍從同一個首頁進入，不必每次尋找新的下載位置。
- **線上與離線都可以**：平常直接從 GitHub Pages 開啟，也能下載成單一 HTML 保存。
- **延續 App 的使用權**：先前取得的官方永久 License 可繼續匯入新版 HTML，不需要因版本更新再次購買。
- **資料由自己掌握**：Prompt、詞庫、設定與 License 主要保存在目前瀏覽器本機；需要換裝置時，可使用 WOVEN Backup v3 搬移資料，新版也能讀取 v2／v1 備份。

## 第一次使用

1. 準備先前透過官方流程取得的個人 License 檔案。新版 Android App 目前未提供離線 HTML 購買入口。
2. 若已有使用資料，先從舊版匯出 WOVEN Backup，保留原始 License 與備份檔。
3. 開啟 [Woven Prompt HTML 公開入口](https://sink6985757-web.github.io/WOVEN-HTML/)，按下「立即開啟 Woven Prompt」。
4. 在 HTML 畫面中匯入個人 License；驗證成功後即可開始使用。

同一瀏覽器會在本機保存 License 與使用資料。若更換瀏覽器、切換網站來源、使用無痕模式或清除網站資料，可能需要重新匯入 License 與備份。

## 你可以用它做什麼

- 繁體中文／English 介面切換，重新開啟後沿用，保留使用者原文
- 快速版與四區進階 Prompt 組合：主題、工作深度與背景、輸出形式、專家模組
- 智囊團角色協作與收斂
- Knowledge Master 路由設定
- 提示詞庫、搜尋、最愛與內容版本
- 日間、夜間、護眼與跟隨系統顯示
- WOVEN Backup v3 完整備份與還原（相容 v2／v1）
- 將完成的 Prompt 複製或帶往 ChatGPT、Gemini、Claude、DeepSeek

Woven Prompt 負責整理與組合 Prompt，**不內嵌 AI API Key，也不會自動替你呼叫付費 AI API**。只有當你主動選擇外部 AI 目的地時，瀏覽器才會開啟對應網站。

## 隱私與使用提醒

- Prompt、設定、詞庫與個人 License 主要儲存在目前瀏覽器本機。
- 請勿把個人 License、私人 Prompt 或完整備份貼到 GitHub Issues。
- Chrome／Edge 的語音辨識可能由瀏覽器或系統服務透過網路處理；不使用語音時，所有核心流程仍可用鍵盤完成。
- 換裝置或清除瀏覽器資料前，請先匯出 WOVEN Backup v3 完整備份。

## 建議環境

建議使用最新版 Chrome 或 Edge。手機與桌面瀏覽器都能開啟，但畫面、語音支援、下載行為與本機儲存空間會依瀏覽器而異。

## 目前版本

| 項目 | 內容 |
| --- | --- |
| 版本 | Woven Prompt 2.1.0（44） |
| HTML | [`woven-prompt-mobile-2.1.0-v44.html`](woven-prompt-mobile-2.1.0-v44.html) |
| 檔案大小 | 1,044,506 bytes |
| SHA-256 | `03BD1203B578A394B6DE24842B30A7C05E6C099E3A2E2E7BEB1AB2ED4531F91D` |

## 版本驗證與限制

本版通過 TypeScript、227 項功能測試與 4 項版本測試；發佈前另驗證 Chrome／Edge、License 狀態、離線啟動、雙語介面、資料保存及瀏覽器備份匯出／重新匯入。公開 HTML 只含編譯成品與公鑰，沒有 Mobile 私有原始碼、APK／AAB 或個人 License。

Android 實機升級、實際 APK 匯出備份轉入 HTML、Play 測試購買仍是獨立待驗項目。Web 備份測試不等同實機 APK 往返；原生廣告與購買不在 HTML 執行。

## 問題回報

若遇到問題，請在 GitHub Issues 提供 HTML 版本、瀏覽器版本、作業系統與重現步驟。請先移除私人 Prompt、Email、訂單資料、API Key、完整備份及個人 License。

開發者與版本維護流程請見 [`PUBLISHING.md`](PUBLISHING.md)。

## License

本倉庫發布的程式成品依 [Apache License 2.0](LICENSE) 授權；第三方元件仍適用各自的授權條款。HTML 內的個人 License 驗證用於官方成品與交付服務識別，不改寫 Apache-2.0 所授予的程式使用、修改與再散布權利。

`WOVEN`、`Woven Prompt`、專案圖示與「官方版本」識別不因 Apache-2.0 自動授予商標或官方背書權利，詳見 [`NOTICE`](NOTICE)。
