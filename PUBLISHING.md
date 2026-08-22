# Woven Prompt HTML：GitHub 上架與維護指南

本指南只處理 `WOVEN HTML` 公開成品倉庫。Mobile 原始碼倉庫保持獨立，不得整包複製、加入 Git 或推送到這個公開倉庫。

## 可直接貼到 GitHub 的文案

Repository description：

> Woven Prompt 官方 HTML 入口：有連結即可從瀏覽器開啟，搭配 APK 流程核發的個人 License 使用，也可下載單檔離線保存。

建議 Topics：

```text
woven-prompt  prompt-tool  offline-html  local-first  github-pages
```

目前 Release 標題：

```text
Woven Prompt HTML 1.2 (28)
```

目前 Release 摘要：

> Woven Prompt 1.2（28）官方單檔 HTML。可由 GitHub Pages 線上開啟，也可下載成單一 HTML 離線保存。本發佈只包含 HTML 成品與公開維護文件，不包含 Mobile 原始碼、APK／AAB、簽章私鑰或個人 License。下載後可用 SHA-256 `77FC9EDAF66E04E76BD6400FCC9123ECA1B4940291215B7CB2BAFBAB71D31DAD` 驗證檔案。

## 1. 公開範圍

可公開的內容：

- 版本化的 `woven-prompt-mobile-*.html` 成品
- GitHub Pages 入口 `index.html`
- `README.md`、`PUBLISHING.md`
- `LICENSE`、`NOTICE`
- `.gitattributes`、`.gitignore`、`.nojekyll`

不可公開的內容：

- Mobile 的 `app/`、`docs/`、scripts、測試、建置資料夾或完整 Git 歷史
- APK、AAB、keystore、憑證、私鑰、`.env` 或帳號資料
- owner License、買家 License、訂單、Email、個人備份或真實 Prompt
- 未通過驗證的測試產物

## 2. 第一次建立公開倉庫

1. 在 GitHub 建立一個空白的 **Public** repository，例如 `WOVEN-HTML`。先不要勾選自動建立 README、License 或 `.gitignore`，避免與本資料夾內容衝突。
2. 在 PowerShell 進入本資料夾並再次確認清單只有預定公開檔案：

   ```powershell
   Set-Location -LiteralPath 'G:\我的雲端硬碟\WOVEN HTML'
   Get-ChildItem -Force
   Get-FileHash -Algorithm SHA256 -LiteralPath '.\woven-prompt-mobile-1.2-v28.html'
   ```

3. 初始化 Git，使用明確 allowlist 加入檔案：

   ```powershell
   git init
   git branch -M main
   git add -- .gitattributes .gitignore .nojekyll LICENSE NOTICE README.md PUBLISHING.md index.html woven-prompt-mobile-1.2-v28.html
   git status --short
   git diff --cached --check
   git commit -m "Publish Woven Prompt HTML 1.2 (28)"
   ```

4. 把下列 `<OWNER>` 與 `<REPOSITORY>` 換成實際值，再連接既有空白倉庫：

   ```powershell
   git remote add origin https://github.com/<OWNER>/<REPOSITORY>.git
   git push -u origin main
   ```

5. 推送後在 GitHub 回讀檔案清單，確認沒有 Mobile 原始碼、私鑰、個人 License、APK 或 AAB。

建立 repository、公開可見性與第一次 push 都會改變外部狀態，應由倉庫擁有者確認後操作。

## 3. 啟用 GitHub Pages

在 repository 內依序開啟：

1. **Settings**
2. 左側 **Pages**
3. **Build and deployment** → **Source** 選擇 **Deploy from a branch**
4. Branch 選擇 `main`
5. Folder 選擇 `/(root)`
6. 按 **Save**

GitHub 完成部署後，請以 Pages 畫面顯示的正式網址為準。專案型網站通常會是：

```text
https://<OWNER>.github.io/<REPOSITORY>/
```

本倉庫的 `index.html` 是公開使用者入口，提供產品說明、License 流程、線上開啟與離線下載按鈕；真正可執行與下載保存的成品仍是版本化的 `woven-prompt-mobile-*.html`。

## 4. 發布新版本

1. 在獨立 Mobile 專案完成來源修改、測試與 standalone HTML 建置。
2. 驗證版本號、WOVEN Backup schema、官方離線 License adapter、兩套公鑰 Authority 與公鑰指紋符合當版規格。
3. 確認 HTML 不含私鑰、owner License、個人 License、Email、API Key 或其他 secret。
4. 只把新的版本化 HTML 複製到本倉庫，例如 `woven-prompt-mobile-1.2-v26.html`。
5. 更新 `index.html` 中所有線上開啟、離線下載按鈕及目前版本文字。
6. 更新 `README.md` 的版本、檔名、大小與 SHA-256。
7. 在瀏覽器驗收新版後，再使用明確檔案清單進行 commit 與 push。
8. GitHub Pages 完成部署後，回讀正式網址並測試根網址、版本檔網址與下載檔案雜湊。

不要覆寫同名舊檔。若內容改變，應使用新版本檔名，讓 Git 記錄、快取與使用者下載都能清楚辨識。

## 5. 每版最低驗證

### 成品與敏感資訊

```powershell
$html = '.\woven-prompt-mobile-1.2-v28.html'
Get-Item -LiteralPath $html | Select-Object Name, Length, LastWriteTime
Get-FileHash -Algorithm SHA256 -LiteralPath $html
rg -n -i 'BEGIN .*PRIVATE KEY|sk-[A-Za-z0-9_-]{20,}|AIza[0-9A-Za-z_-]{30,}|gh[pousr]_[A-Za-z0-9]{20,}|Bearer\s+[A-Za-z0-9._~+/-]{20,}' -- $html
```

最後一個命令預期沒有結果。若找到任何疑似憑證，停止發布並回到來源專案調查，不能只從成品字串中刪除後硬上架。

### 瀏覽器驗收

- 根網址能顯示公開入口，且線上開啟與離線下載按鈕都指向目前版本。
- Chrome 與 Edge 能載入首頁、生成器、智囊團、路由、詞庫與設定頁。
- License 缺少、有效與無效狀態符合預期；測試時不得使用或提交買家個人 License。
- WOVEN Backup v3 能匯出並於同版重新匯入，也能讀取 v2／v1；正式跨 APK／HTML 相容性仍以實際 APK 匯出檔驗收。
- Prompt 生成、保存、搜尋、最愛、初始化與顯示模式可正常使用。
- 點選外部 AI 目的地前會保留 Prompt，且只有使用者主動操作才開啟外部網站。
- 語音不可用時能正常回退鍵盤輸入。

### Git 範圍

```powershell
git status --short
git diff --check
git ls-files
```

`git ls-files` 應只出現本指南第 1 節允許的公開檔案。

## 6. 回退

若新版 Pages 發生問題：

1. 保留問題版本以供調查，不要重寫 Git 歷史。
2. 把 `index.html` 的線上開啟、離線下載按鈕與版本文字改回最後一個已驗證版本。
3. 更新 `README.md` 的目前版本資訊。
4. 提交一個清楚的 rollback commit，推送後重新回讀 Pages。

回退只切換公開入口，不應刪除使用者資料，也不需要 force push。

## 7. 建議的 GitHub Release

每個確認穩定的 HTML 版本可另外建立 GitHub Release，附上：

- 版本號與日期
- HTML 成品
- SHA-256
- 主要變更
- 已知限制
- 是否通過實際 APK → HTML 的 WOVEN Backup v2／v1 相容性驗收

Release 是版本下載與追溯入口；GitHub Pages 則維持指向目前推薦版本。

## GitHub 官方參考

- [Configuring a publishing source for your GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
- [Creating a GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site)
