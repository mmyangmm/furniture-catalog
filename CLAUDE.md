# 傢俱目錄 — CLAUDE.md

## 專案概述

單一 HTML 檔案的個人傢俱目錄網頁應用，直接用瀏覽器開啟即可使用，無需伺服器或安裝。

- **檔案**：`index.html`（唯一檔案，CSS + JS 全部內嵌）
- **資料儲存**：瀏覽器 `localStorage`（key: `furniture_catalog_v1`）
- **自訂分類**：`localStorage`（key: `furniture_custom_categories`，JSON array）
- **語言**：繁體中文 UI

## 功能清單

### 目錄顯示
- 卡片式 Grid 版面（`minmax(280px, 1fr)`，響應式）
- 每張卡片顯示：圖片（contain 不裁切）、傢俱類型標籤、品名、品牌、顏色、材質、價格、推出年份
- 圖片支援 base64（使用者上傳）或外部 URL（網址擷取取得）
- 滑鼠 hover 卡片右上角出現編輯／刪除按鈕

### 新增品項（兩種方式）

**1. 手動新增（＋ 手動新增按鈕）**
- 上傳圖片（點擊或拖曳，轉成 base64 存入 localStorage）
- 欄位：品名、品牌、推出年份、顏色（獨立）、材質（獨立）、尺寸、傢俱類型、價格（NT$）、備註說明
- **點視窗外不關閉**，只有叉叉或取消按鈕才關閉

**2. 網址新增（🔗 網址新增按鈕）**
- 貼入產品頁 URL → 自動擷取資訊 → 確認/修改後儲存
- 4 步驟 loading：連線 → 讀取 → 解析 → AI補充搜尋（備援）
- 確認頁所有欄位可直接編輯，空白表示網頁未提供
- **點視窗外不關閉**

### 瀏覽與篩選
- **左側隱藏式側邊欄**：點「篩選」按鈕或從左緣右滑開啟；向左滑或點遮罩關閉
- 側邊欄包含：傢俱類型分類 + 品牌篩選（只顯示目錄內已有的）
- 全文搜尋（品名、品牌、顏色、材質、說明）
- 排序：最新新增、價格低→高、價格高→低、年份新→舊、品名

### 品項管理
- 點擊卡片：開啟詳情 Modal
- 詳情 Modal 內可跳至編輯或刪除；圖片 contain 顯示不裁切
- 有 `sourceUrl` 的品項顯示「🖼 顯示產品照片」按鈕（最多 10 張）
- 刪除需 confirm 確認

### 設定（⚙️）
- 儲存 Anthropic API Key 至 localStorage（key: `furniture_anthropic_key`）
- 匯出全部資料（JSON 下載）
- 清空全部資料

## 資料結構

每筆品項物件：

```js
{
  id: string,         // Date.now().toString()
  name: string,
  brand: string,
  year: string,
  color: string,      // 顏色（獨立欄位）
  material: string,   // 材質（獨立欄位，新增於 2026-04）
  size: string,       // 尺寸
  type: string,       // 見下方分類清單
  price: string,      // 數字字串，NT$
  desc: string,
  image: string,      // base64 data URL（手動上傳）或 null
  imageUrl: string,   // 外部圖片 URL 或空字串
  sourceUrl: string,  // 來源網址（網址新增時存入）
  createdAt: number   // timestamp
}
```

## 傢俱分類清單

預設固定：`沙發 / 椅子 / 桌子 / 床架 / 層架 / 收納 / 燈具 / 地毯 / 戶外傢俱 / 裝飾品 / 其他`

支援自訂分類：在表單下拉選單選「＋ 自訂分類...」輸入後按 Enter 建立，存入 `furniture_custom_categories`。

## 網址擷取技術細節

### CORS Proxy（依序嘗試）
1. `https://api.allorigins.win/get?url=`
2. `https://corsproxy.io/?`
3. `https://api.codetabs.com/v1/proxy?quest=`

### 解析優先順序
1. **JSON-LD** `<script type="application/ld+json">` Product 結構化資料
2. **Open Graph** meta 標籤（`og:title`, `og:image`, `og:description`）
3. **`extractSpec(labelRe)`** 規格表格擷取：
   - Strategy 1：label 元素 → 相鄰 sibling（`th/td`, `dt/dd`, `[class*="label"]` 等）
   - Strategy 2：同行文字 `label：value` pattern（`(?:^|\n)\s*label[\s:：]+value`）
   - `extractValueText()`：偵測 WooCommerce `<select>` 取 option；偵測色塊 `<li title>` 取 title
4. **Claude AI 備援**（僅 proxy 全失敗且有 API Key 時啟動）

### 文字清洗 `cleanText()`
- 移除零寬字元（`\u200b` 等）
- 合併多餘空白
- 去除開頭/結尾符號噪音（`-`, `：`, `,`, `.` 等）

### 類別判斷 `inferType(name, fallbackText)`
- 先用**品名**判斷，品名無結果才用描述文字
- **無法辨識回傳 `''`**，確認頁保持「請選擇」，使用者手動選

### 價格擷取
1. JSON-LD `offers.price`
2. `meta[property="product:price:amount"]`
3. `.woocommerce-Price-amount` span
4. 頁面文字掃描：`NT$` / `NTD` / `TWD` / `$` / `元` / `円`（合理性過濾 100~10,000,000）

### Claude AI 備援（`searchWithClaude`）
- **API endpoint**：`https://api.anthropic.com/v1/messages`
- **Model**：`claude-haiku-4-5-20251001`
- **Tool**：`web_search_20250305`（`max_uses: 3`）
- **必要 header**：`anthropic-dangerous-direct-browser-access: true`
- prompt 要求：找不到的欄位填空字串，不猜測

### 產品照片（詳情 Modal）
來源優先順序（最多取 10 張）：
1. JSON-LD `Product.image`
2. WooCommerce `data-product_variations` JSON（各顏色變體）
3. `.woocommerce-product-gallery` 等 gallery img
4. `og:image`

## 設計規範

CSS variables：
- `--accent: #8b6f47`（主色，木質棕）
- `--accent-light: #f0e8dc`
- `--bg: #f7f5f2`（暖白背景）
- `--surface: #ffffff`
- `--border: #e8e2d9`
- 網址新增按鈕：`linear-gradient(135deg, #667eea, #764ba2)`（紫藍漸層）
- 側邊欄寬：240px，動畫：`cubic-bezier(0.4,0,0.2,1)` 280ms

## 開啟方式

```bash
open /Users/yanghaohsiang/Desktop/傢俱目錄/index.html
```

## 已知限制 / 注意事項

- CORS proxy 不穩定，三個都失敗才報錯
- 手動新增的品項（無 `sourceUrl`）不顯示產品照片按鈕
- 尺寸擷取依賴網站有規格表或 `WxDxH` 格式文字
- 共享目錄（多人同步）尚未開發，目前各裝置 localStorage 各自獨立
- 舊資料無 `material` 欄位仍相容（顯示時各自為空）
