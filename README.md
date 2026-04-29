# 傢俱目錄 — Personal Furniture Catalog

> 🇹🇼 [繁體中文](#繁體中文) ・ 🇬🇧 [English](#english)

**Live Demo:** https://mmyangmm.github.io/furniture-catalog/

---

## 繁體中文

### 這個專案是為了解決什麼問題？

在規劃居家佈置時，你是否有過這樣的經驗：

- 在 IKEA、無印良品、各大品牌官網東看西看，喜歡的東西卻只能「複製網址貼到 Notes」
- 收藏在瀏覽器書籤的產品頁，過了幾個月卻找不到、或下架了
- 想比較不同品牌的沙發價格，卻得一個個打開分頁重新確認
- 去實體店看到喜歡的傢俱，想拍照記錄卻散落在相機膠卷裡，沒有品牌、尺寸、價格等資訊
- 想和家人討論要買哪張桌子，但資訊零散、難以整理成一覽表

**傢俱目錄**就是為了解決這些日常痛點而生。它讓你把「看到喜歡的傢俱」這個動作，變成一個有系統的收藏與比較過程。

---

### 為什麼要用這個，而不是其他工具？

#### 和記事本、書籤相比
普通書籤只存網址，打開後還要重新閱讀整頁找資訊。**傢俱目錄**把你需要的欄位（品名、品牌、顏色、材質、尺寸、價格）一次整理好，視覺化呈現，一目瞭然。

#### 和試算表相比
Excel / Google Sheets 需要手動輸入每格，圖片處理麻煩，手機瀏覽體驗差。**傢俱目錄**只要貼入產品網址，系統自動擷取資訊；圖片直接顯示在卡片上，支援手機滑動瀏覽。

#### 和 Pinterest、Instagram 收藏相比
社群平台的收藏是「靈感板」，沒有價格、尺寸、品牌等結構化資料，也無法做比較或篩選。**傢俱目錄**是有欄位、可搜尋、可排序的個人資料庫。

#### 為什麼不需要帳號、不需要伺服器？
- **零設定**：下載即用，不需要申請帳號、不需要訂閱費
- **隱私安全**：所有資料存在自己的瀏覽器裡，不會上傳到任何雲端
- **不依賴服務存活**：不怕服務關閉、帳號被停用或付費牆
- **完全離線可用**：出門在外沒網路，資料仍然看得到

---

### 簡介

**傢俱目錄**是一個完全在瀏覽器端運行的個人傢俱收藏管理工具，無需安裝、無需伺服器，直接開啟 `index.html` 或造訪線上版本即可使用。所有資料儲存於瀏覽器的 `localStorage`，完全本機，不會上傳至任何伺服器。

**適合對象：**
- 正在規劃新家、裝修或重新佈置的人
- 傢俱愛好者，習慣比較不同品牌與款式
- 室內設計師或相關從業者，需要管理大量產品資訊
- 任何想把「傢俱 wishlist」整理得更有系統的人

### 功能特色

| 功能 | 說明 |
|------|------|
| 📦 **卡片式目錄** | 響應式 Grid 版面，每張卡片顯示圖片、品名、品牌、顏色、材質、價格等資訊 |
| ✍️ **手動新增** | 上傳本機圖片（base64）並填寫完整品項資訊 |
| 🔗 **網址一鍵擷取** | 貼入產品頁網址，自動解析名稱、品牌、價格、圖片等欄位 |
| 🔍 **全文搜尋** | 即時搜尋品名、品牌、顏色、材質、說明 |
| 🗂️ **側邊欄篩選** | 依傢俱類型、品牌篩選；支援自訂分類 |
| 🔄 **多種排序** | 最新新增、價格低→高、價格高→低、年份新→舊、品名 |
| 🖼️ **產品照片瀏覽** | 從來源頁面抓取最多 10 張產品圖（需有來源網址） |
| 💾 **資料匯出** | 一鍵匯出所有資料為 JSON 檔案備份 |
| 🤖 **AI 備援擷取** | 設定 Anthropic API Key 後，網頁解析失敗時自動啟用 Claude 搜尋補充 |

### 操作說明

#### 新增品項

**方式一：手動新增**
1. 點擊右上角 **＋ 手動新增** 按鈕
2. 點擊或拖曳圖片區域上傳產品照片
3. 填寫品名、品牌、年份、顏色、材質、尺寸、傢俱類型、價格（NT$）、備註
4. 點擊 **儲存** 完成新增
5. 若要取消，點擊 **✕** 或取消按鈕（點視窗外不會關閉）

**方式二：網址新增**
1. 點擊 **🔗 網址新增** 按鈕
2. 貼入產品頁網址（支援各大電商、品牌官網）
3. 等待系統自動抓取：連線 → 讀取 → 解析 → AI補充（備援）
4. 在確認頁面核對或修改擷取到的資訊
5. 點擊 **儲存** 完成新增

#### 瀏覽與搜尋

- **搜尋**：在頂部搜尋欄輸入關鍵字，即時過濾結果
- **篩選**：點擊 **篩選** 按鈕（或從螢幕左緣向右滑）開啟側邊欄，依類型或品牌篩選
- **排序**：點擊排序下拉選單，切換顯示順序
- **關閉側邊欄**：向左滑動或點擊遮罩區域

#### 查看與編輯

- **查看詳情**：點擊任意卡片開啟詳情視窗
- **編輯**：滑鼠移至卡片右上角出現 ✏️ 按鈕，或在詳情視窗內點編輯
- **刪除**：滑鼠移至卡片右上角出現 🗑️ 按鈕，或在詳情視窗內點刪除（需二次確認）
- **瀏覽產品照片**：詳情視窗中點擊 **🖼 顯示產品照片**（僅網址新增的品項可用）

#### 設定

點擊右上角 **⚙️** 開啟設定面板：
- 輸入 **Anthropic API Key** 以啟用 AI 備援擷取功能
- **匯出資料**：下載所有品項為 JSON 檔案
- **清空資料**：刪除所有品項（不可復原，需確認）

### 傢俱分類

預設分類：`沙發` `椅子` `桌子` `床架` `層架` `收納` `燈具` `地毯` `戶外傢俱` `裝飾品` `其他`

在新增表單的類型下拉選單選擇 **＋ 自訂分類...** 可新增個人化分類。

### 本機使用方式

```bash
# 下載後直接用瀏覽器開啟
open index.html
```

無需 npm、無需伺服器，所有程式碼皆內嵌於單一 `index.html` 檔案。

### 注意事項

- 資料儲存於瀏覽器 localStorage，清除瀏覽器資料前請先匯出備份
- 不同裝置的資料各自獨立，目前不支援跨裝置同步
- 網址擷取透過第三方 CORS Proxy，部分網站可能無法解析
- 上傳的圖片以 base64 格式儲存，大量高解析度圖片可能佔用較多 localStorage 空間

---

## English

### What problem does this solve?

When planning a home interior, you've probably experienced this:

- Browsing IKEA, Muji, or brand websites and saving links you like — only to paste them into Notes with zero context
- Bookmarking product pages that disappear or go out of stock months later
- Wanting to compare sofa prices across brands, but having to open every tab again
- Taking photos in a furniture store with no record of the brand, dimensions, or price
- Trying to discuss furniture options with a partner, but your "research" is scattered across browser tabs, screenshots, and chat messages

**Furniture Catalog** was built to solve exactly these frustrations. It turns the act of "finding furniture you like" into an organized, searchable, visual database.

---

### Why use this instead of other tools?

#### vs. Bookmarks or Notes
Regular bookmarks only save a URL — you still have to re-read the whole page to find the info you need. **Furniture Catalog** extracts the fields you actually care about (name, brand, color, material, size, price) and displays them in a clean card layout.

#### vs. Spreadsheets (Excel / Google Sheets)
Spreadsheets require manual data entry for every cell, image handling is cumbersome, and the mobile experience is poor. **Furniture Catalog** lets you paste a URL and auto-imports the data; images appear directly on cards and the layout works great on mobile.

#### vs. Pinterest or Instagram Collections
Social platforms are great for mood boards, but they lack structured data — no price, no dimensions, no brand filter. **Furniture Catalog** is a queryable personal database with fields, search, and sorting.

#### Why no account, no server?
- **Zero setup**: Download and open — no sign-up, no subscription
- **Privacy first**: All data stays in your own browser, never uploaded to any cloud
- **No service dependency**: No risk of the service shutting down, account suspension, or paywalls
- **Fully offline**: Your catalog is always available, even without an internet connection

---

### Introduction

**Furniture Catalog** is a personal furniture collection manager that runs entirely in the browser — no installation, no server required. Simply open `index.html` or visit the live demo. All data is stored in your browser's `localStorage`, completely local and never uploaded anywhere.

**Who is this for?**
- Anyone planning a new home, renovation, or room refresh
- Furniture enthusiasts who like to compare brands and styles
- Interior designers or professionals managing large product reference libraries
- Anyone who wants a more organized "furniture wishlist" than a pile of browser tabs

### Features

| Feature | Description |
|---------|-------------|
| 📦 **Card Grid View** | Responsive grid layout showing image, name, brand, color, material, price, and more |
| ✍️ **Manual Entry** | Upload a local image (stored as base64) and fill in item details |
| 🔗 **URL Auto-Import** | Paste a product page URL to automatically extract name, brand, price, and images |
| 🔍 **Full-text Search** | Instantly filter by name, brand, color, material, or description |
| 🗂️ **Sidebar Filters** | Filter by furniture type or brand; supports custom categories |
| 🔄 **Multiple Sort Orders** | Newest, price low→high, price high→low, year newest, name A→Z |
| 🖼️ **Product Photo Viewer** | Fetches up to 10 product images from the source page |
| 💾 **Data Export** | Export all items as a JSON backup with one click |
| 🤖 **AI Fallback** | Set an Anthropic API Key to enable Claude-powered search as a parsing fallback |

### How to Use

#### Adding Items

**Option 1 — Manual Entry**
1. Click **＋ 手動新增** (Manual Add) in the top-right corner
2. Click or drag-and-drop a photo onto the image area
3. Fill in: name, brand, year, color, material, size, type, price (NT$), and notes
4. Click **儲存** (Save) to finish
5. To cancel, click **✕** or the cancel button (clicking outside the modal does NOT close it)

**Option 2 — Import from URL**
1. Click **🔗 網址新增** (Add from URL)
2. Paste a product page URL (works with major e-commerce sites and brand pages)
3. Wait for the 4-step auto-fetch: connecting → reading → parsing → AI supplement (fallback)
4. Review and edit the extracted fields on the confirmation screen
5. Click **儲存** (Save) to finish

#### Browsing & Searching

- **Search**: Type a keyword in the top search bar for real-time filtering
- **Filter**: Click the **篩選** (Filter) button (or swipe right from the left edge) to open the sidebar, then filter by furniture type or brand
- **Sort**: Use the sort dropdown to change the display order
- **Close sidebar**: Swipe left or tap the overlay

#### Viewing & Editing

- **View details**: Click any card to open its detail modal
- **Edit**: Hover a card to reveal the ✏️ button (top-right), or click Edit inside the detail modal
- **Delete**: Hover a card for the 🗑️ button, or click Delete in the detail modal (requires confirmation)
- **Browse product photos**: Click **🖼 顯示產品照片** in the detail modal (only available for URL-imported items)

#### Settings

Click **⚙️** in the top-right corner to open Settings:
- Enter your **Anthropic API Key** to enable the AI fallback for URL parsing
- **Export Data**: Download all items as a JSON file
- **Clear All Data**: Permanently delete all items (requires confirmation, irreversible)

### Furniture Categories

Default categories: `Sofa` `Chair` `Table` `Bed Frame` `Shelf` `Storage` `Lighting` `Rug` `Outdoor` `Decoration` `Other`

Select **＋ 自訂分類...** (Custom Category) in the type dropdown to add your own categories.

### Local Usage

```bash
# Download and open directly in your browser
open index.html
```

No npm, no server needed. Everything is self-contained in a single `index.html` file.

### Notes & Limitations

- Data lives in browser localStorage — export a backup before clearing browser data
- Each device has its own independent catalog; cross-device sync is not supported
- URL import relies on third-party CORS proxies, which may not work for all websites
- Images uploaded manually are stored as base64; many high-resolution images may consume significant localStorage space

---

<p align="center">Made with ☕ for furniture lovers</p>
