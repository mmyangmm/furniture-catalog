# 傢俱目錄 — Personal Furniture Catalog

> 🇹🇼 [繁體中文](#繁體中文) ・ 🇬🇧 [English](#english)

**Live Demo:** https://mmyangmm.github.io/furniture-catalog/

---

## 繁體中文

# 打造屬於你的傢俱目錄，記錄你的居家風格故事

> 每一件傢俱的選擇，都是你品味與生活方式的延伸。  
> 不只是收藏，而是策展——策劃一個專屬於你的居家風格宇宙。

每個人對「家」的想像都不一樣。有人偏愛北歐極簡的冷靜，有人鍾情日式侘寂的質樸，有人追求工業風的粗獷，也有人享受混搭各種風格帶來的衝突美感。**傢俱目錄**讓你把這些靈感、偏好與選擇，系統性地累積成一本只屬於你的視覺目錄——不是別人的推薦清單，不是演算法決定的 feed，而是你自己審視過、篩選過、真正喜歡的每一件物品。

---

### 你的目錄，你的風格主張

**傢俱目錄**不只是一個工具，它是你居家風格的私人檔案庫。

- **自訂分類**：預設分類不夠用？建立「日式餐廚」「書房計畫」「療癒角落」等完全由你命名的分類，讓目錄結構反映你的思維方式
- **備註欄位**：記下「這張椅子的橡木色和客廳地板完美搭配」「等特價再買」等只有你懂的脈絡
- **顏色 × 材質追蹤**：獨立的顏色與材質欄位，讓你一眼掌握目錄裡的色調傾向——原來你一直在收藏暖棕色系的木質傢俱
- **年份紀錄**：知道哪些是當代設計、哪些是經典款，建立跨越時代的風格觀點
- **圖片優先**：卡片式版面以圖片為主角，視覺直觀——因為傢俱的風格感受，眼睛說了算

---

### 簡介

**傢俱目錄**是一個完全在瀏覽器端運行的個人傢俱收藏管理工具，無需安裝、無需伺服器，直接開啟 `index.html` 或造訪線上版本即可使用。所有資料儲存於瀏覽器的 `localStorage`，完全本機，不會上傳至任何伺服器。

**適合對象：**
- 正在規劃新家、裝修或重新佈置，想系統整理所有選項的人
- 有獨特品味、想把自己的風格偏好記錄下來的傢俱愛好者
- 室內設計師或相關從業者，需要管理大量產品參考資料
- 任何想把分散的靈感碎片，整合成一本專屬風格目錄的人

---

### 功能特色

| 功能 | 說明 |
|------|------|
| 📦 **卡片式目錄** | 響應式 Grid 版面，每張卡片顯示圖片、品名、品牌、顏色、材質、價格等資訊 |
| ✍️ **手動新增** | 上傳本機圖片（base64）並填寫完整品項資訊 |
| 🔗 **網址一鍵擷取** | 貼入產品頁網址，自動解析名稱、品牌、價格、圖片等欄位 |
| 🔍 **全文搜尋** | 即時搜尋品名、品牌、顏色、材質、說明 |
| 🗂️ **側邊欄篩選** | 依傢俱類型、品牌篩選；支援**完全自訂分類** |
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

在新增表單的類型下拉選單選擇 **＋ 自訂分類...** 可新增個人化分類，例如「書房計畫」「療癒角落」「廚房升級」——完全按你的方式組織。

### 本機使用方式

```bash
# 下載後直接用瀏覽器開啟
open index.html
```

無需 npm、無需伺服器，所有程式碼皆內嵌於單一 `index.html` 檔案。

### 這個專案是為了解決什麼問題？

在規劃居家佈置時，你是否有過這樣的經驗：

- 在 IKEA、無印良品、各大品牌官網東看西看，喜歡的東西卻只能「複製網址貼到 Notes」
- 收藏在瀏覽器書籤的產品頁，過了幾個月卻找不到、或下架了
- 想比較不同品牌的沙發價格，卻得一個個打開分頁重新確認
- 去實體店看到喜歡的傢俱，想拍照記錄卻散落在相機膠卷裡，沒有品牌、尺寸、價格等資訊
- 想和家人討論要買哪張桌子，但資訊零散、難以整理成一覽表

**傢俱目錄**就是為了解決這些日常痛點而生。它讓你把「看到喜歡的傢俱」這個動作，變成一個有系統的收藏與比較過程。

### 注意事項

- 資料儲存於瀏覽器 localStorage，清除瀏覽器資料前請先匯出備份
- 不同裝置的資料各自獨立，目前不支援跨裝置同步
- 網址擷取透過第三方 CORS Proxy，部分網站可能無法解析
- 上傳的圖片以 base64 格式儲存，大量高解析度圖片可能佔用較多 localStorage 空間

---

## English

# Build Your Own Furniture Catalog — Curate Your Home Style

> Every piece of furniture you choose is an extension of your taste and the way you live.  
> This isn't just a collection — it's curation. A personal universe of the things you actually love.

Everyone's idea of "home" is different. Some gravitate toward Scandinavian minimalism, others toward Japanese wabi-sabi, industrial rawness, or the bold beauty of mixing styles. **Furniture Catalog** lets you accumulate those inspirations, preferences, and choices into a visual catalog that is entirely yours — not someone else's recommendation list, not an algorithm-curated feed, but every item you've personally reviewed, filtered, and genuinely want.

---

### Your catalog. Your style.

**Furniture Catalog** is more than a utility — it's a private archive of your design sensibility.

- **Custom categories**: Default categories not enough? Create your own — "Kitchen Refresh," "Reading Nook," "Statement Pieces" — so the structure of your catalog reflects how you actually think
- **Notes field**: Record context only you understand: "the oak tone matches the living room floor perfectly," or "wait for a sale"
- **Color × Material tracking**: Dedicated fields for color and material let you spot patterns in your own taste — maybe you've been gravitating toward warm-toned wood all along
- **Year field**: Know which pieces are contemporary designs and which are timeless classics — build a style perspective that spans eras
- **Image-first layout**: The card grid puts photos front and center, because when it comes to furniture aesthetics, your eyes know first

---

### Introduction

**Furniture Catalog** is a personal furniture collection manager that runs entirely in the browser — no installation, no server required. Simply open `index.html` or visit the live demo. All data is stored in your browser's `localStorage`, completely local and never uploaded anywhere.

**Who is this for?**
- Anyone planning a new home, renovation, or room refresh who wants to organize all their options in one place
- People with a strong personal aesthetic who want to document and refine their style over time
- Interior designers or professionals managing large product reference libraries
- Anyone who wants to turn scattered inspiration into one coherent, curated style catalog

---

### Features

| Feature | Description |
|---------|-------------|
| 📦 **Card Grid View** | Responsive grid layout showing image, name, brand, color, material, price, and more |
| ✍️ **Manual Entry** | Upload a local image (stored as base64) and fill in item details |
| 🔗 **URL Auto-Import** | Paste a product page URL to automatically extract name, brand, price, and images |
| 🔍 **Full-text Search** | Instantly filter by name, brand, color, material, or description |
| 🗂️ **Sidebar Filters** | Filter by furniture type or brand; supports **fully custom categories** |
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

Select **＋ 自訂分類...** (Custom Category) in the type dropdown to add your own — "Reading Nook," "Kitchen Refresh," "Statement Pieces" — organized entirely the way you think.

### Local Usage

```bash
# Download and open directly in your browser
open index.html
```

No npm, no server needed. Everything is self-contained in a single `index.html` file.

### What problem does this solve?

When planning a home interior, you've probably experienced this:

- Browsing IKEA, Muji, or brand websites and saving links you like — only to paste them into Notes with zero context
- Bookmarking product pages that disappear or go out of stock months later
- Wanting to compare sofa prices across brands, but having to open every tab again
- Taking photos in a furniture store with no record of the brand, dimensions, or price
- Trying to discuss furniture options with a partner, but your "research" is scattered across browser tabs, screenshots, and chat messages

**Furniture Catalog** was built to solve exactly these frustrations. It turns the act of "finding furniture you like" into an organized, searchable, visual database.

### Notes & Limitations

- Data lives in browser localStorage — export a backup before clearing browser data
- Each device has its own independent catalog; cross-device sync is not supported
- URL import relies on third-party CORS proxies, which may not work for all websites
- Images uploaded manually are stored as base64; many high-resolution images may consume significant localStorage space

---

<p align="center">Made with ☕ for people who care about how their home feels</p>
