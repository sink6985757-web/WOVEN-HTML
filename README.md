# Woven Prompt HTML

Woven Prompt HTML 是 **Woven Prompt 官方單檔 HTML 作品的公開發布與維護倉庫**。這個倉庫只保存可直接在瀏覽器執行或下載保存的 HTML 成品，以及公開上架所需的說明與授權文件。

Mobile App 原始碼、APK／AAB、建置工具、簽章私鑰、owner License 與任何使用者個人 License 都不屬於本倉庫，也不會隨 HTML 一起公開。

## 目前版本

| 項目 | 內容 |
| --- | --- |
| 版本 | Woven Prompt 1.2（25） |
| 單檔成品 | [`woven-prompt-mobile-1.2-v25.html`](woven-prompt-mobile-1.2-v25.html) |
| 檔案大小 | 704,275 bytes |
| SHA-256 | `FCF44F0F46E30947994C0F4D433B24C8AE5E2E0F30798CF62DC2335D02A34FA9` |

## 如何使用

- 線上使用：啟用 GitHub Pages 後，從 Pages 顯示的網站網址進入；根目錄的 `index.html` 會開啟目前維護版本。
- 離線使用：下載版本化的 HTML 檔，保存在自己的電腦後，以最新版 Chrome 或 Edge 開啟。
- 更新前備份：若已在瀏覽器保存 Prompt、設定或詞庫，請先從系統設定匯出 **WOVEN Backup v2** 完整備份。

不同瀏覽器、不同網域與本機 `file://` 開啟方式會使用不同的瀏覽器儲存空間。更換使用位置時，請以完整備份搬移資料，不要假設舊資料會自動跟過去。

## 這個 HTML 做什麼

Woven Prompt 是本機優先的 Prompt 編輯與組合工具，提供生成器、智囊團、Knowledge Master 路由、提示詞庫、最愛、主題外觀與備份還原等功能。

- HTML 不內嵌 AI API Key，也不會代替使用者呼叫付費 AI API。
- Prompt 的組合與保存主要在目前瀏覽器內完成。
- 只有在使用者主動選擇傳送目的地時，才會開啟 ChatGPT、Gemini、Claude 或 DeepSeek 等外部網站。
- Chrome／Edge 的語音輸入屬於瀏覽器漸進功能；語音辨識可能由瀏覽器或系統服務透過網路處理。
- 官方離線版的驗證資料只包含公開驗證公鑰；簽章私鑰與個人 License 不包含在 HTML 或本倉庫內。

## 維護原則

本倉庫是「發佈成品倉庫」，不是 Mobile 原始碼鏡像。

1. 新功能與修正先在獨立的 Mobile 專案完成建置與驗證。
2. 每次只帶入通過驗證的版本化單檔 HTML，不複製 Mobile 專案結構。
3. 不直接手動修改 HTML 內壓縮過的 JavaScript bundle；有功能問題時回到來源專案修正後重新建置。
4. 保留舊版檔案以便回退，並更新本頁的版本、大小與 SHA-256。
5. 每次公開前執行敏感資訊、外部資源、License 邊界與瀏覽器功能檢查。

完整首次上架、版本更新、驗證與回退流程請見 [`PUBLISHING.md`](PUBLISHING.md)。

## 問題回報

可透過 GitHub Issues 回報可重現的 HTML 問題。請附上版本、瀏覽器版本、作業系統與重現步驟；不要貼出私人 Prompt、完整備份、訂單資料、Email、API Key 或個人 License。

## License

本倉庫所發布的程式成品依 [Apache License 2.0](LICENSE) 授權；第三方元件仍適用各自的授權條款。HTML 內的離線 License 驗證用於官方成品與交付服務的識別，不改寫 Apache-2.0 所授予的程式使用、修改與再散布權利。

`WOVEN`、`Woven Prompt`、專案圖示與「官方版本」識別不因 Apache-2.0 自動授予商標或官方背書權利，詳見 [`NOTICE`](NOTICE)。
