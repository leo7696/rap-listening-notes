# CLAUDE.md — 我的饒舌聽歌筆記（專案協作與擴充規範）

本文件定義此靜態網站的架構、視覺系統、檔案規則與資料維護標準。任何 AI 代理或協作者在修改或新增頁面時，必須嚴格遵守以下規範。

---

## 一、專案目的

- **核心定位**：個人饒舌（Hip-Hop / Rap）聽歌筆記與音樂收藏庫，依「國家」分類收錄歌手。
- **記錄維度**：每位歌手的專輯（依年份由舊到新）、完整曲目（點擊歌名可前往 YouTube 搜尋聆聽）、個人最愛歌曲（`★` 標記）、合作對象。
- **語言規範**：介面、說明與介紹使用**繁體中文**；歌手名、專輯名、曲目名稱一律**保留原文**（如英文、韓文、日文）。

---

## 二、整體風格：深色街頭感（Dark Streetwear / Tape Aesthetic）

1. **色彩系統（嚴禁寫死色碼）**
   - 頁面 HTML 與 CSS 中所有顏色必須透過 `assets/style.css` 的 `:root` 變數引用，不可出現任何裸寫的 Hex / RGB 色碼：
     - `--bg`: `#0d0d0d`（主背景黑）
     - `--panel`: `#161616`（卡片與區塊底色）
     - `--ink`: `#f2f2f2`（主要文字）
     - `--muted`: `#9e9e9e`（次要資訊、年份、序號）
     - `--line`: `#2e2e2e`（細分隔線與邊框）
     - `--accent`: `#ffd400`（唯一強調色：警示膠帶黃）
2. **標誌性視覺元素（僅限兩個，其餘保持安靜克制）**
   - **頁首黃黑斜紋膠帶**：全站頂部固定裝飾條（`.hazard-tape`）。
   - **歌手名大標題**：`<h1>` 採用粗黑體（`Impact` 系列字型堆疊）、全大寫（`text-transform: uppercase`）、微傾斜（`transform: skewX(-4deg)`）、警示黃偏移陰影（`text-shadow: 4px 4px 0 var(--accent)`）。
3. **強調色（`--accent`）使用白名單**
   - 僅允許出現在：**頁首斜紋膠帶**、**大標題陰影**、**基本資料標籤（`<dt>`）**、**最愛歌曲標記（`.fav` 與 `★`）**、**互動元素的 `:hover` / `:focus-visible` / `<details[open]>` 狀態**。
4. **字型與無障礙**
   - 標題：`Impact, 'Arial Black', 'Noto Sans TC', sans-serif`
   - 內文：系統預設無襯線字型（`system-ui, -apple-system, 'Segoe UI', 'Noto Sans TC', sans-serif`）
   - 必須保留 `:focus-visible` 鍵盤外框樣式與 `@media (prefers-reduced-motion: reduce)` 動態減弱規則。

---

## 三、頁面結構（三層單向階層）

```text
index.html                  （第一層：首頁／國家目錄）
  └── countries/xx.html     （第二層：國家頁／僅列該國歌手目錄，不放專輯）
        └── artists/slug.html （第三層：歌手頁／所有專輯、曲目、合作紀錄皆在此）