# 我的饒舌聽歌筆記（Rap Listening Notes）

這是一個以純 HTML 與 CSS 打造的個人饒舌音樂收藏與聽歌筆記靜態網站，採用深色街頭視覺風格，並設計了完整的 `CLAUDE.md` 規範以支援透過 AI 持續擴充內容。

## 專案特色

- **零依賴純靜態架構**：無 JavaScript、無前端框架、無外部 CDN 或遠端字型，可直接部署於 GitHub Pages。
- **三層清晰導覽**：首頁（國家分類）$\rightarrow$ 國家頁（歌手清單）$\rightarrow$ 歌手頁（專輯、曲目、最愛標記、合作網絡）。
- **原生互動體驗**：使用 HTML5 `<details>` / `<summary>` 實現專輯曲目展開與收合，支援鍵盤操作與減少動態偏好設定。
- **AI 友善工作流**：透過 `CLAUDE.md` 與 `templates/` 範本，確保每次新增歌手或國家都能維持一致的版型與連動更新。

## 本機預覽方式

直接用瀏覽器開啟根目錄下的 `index.html`，或使用 VS Code 的 Live Server 套件即可預覽。

## 檔案結構說明

- `CLAUDE.md`：給 AI 閱讀的專案開發與新增內容規範書。
- `index.html`：首頁，顯示各國家入口與收錄人數。
- `countries/`：各國歌手目錄頁（以兩碼小寫 ISO 國碼命名，如 `us.html`）。
- `artists/`：個別歌手的完整聽歌筆記頁（以英文小寫 slug 命名）。
- `templates/`：新增國家與歌手時複製用的 HTML 範本。
- `assets/style.css`：全站樣式表。
- `assets/img/`：存放預設封面 `placeholder.svg` 與專輯封面圖 `covers/`。