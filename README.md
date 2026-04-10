# Muggle Zoo｜麻瓜婆婆動物園

> **給下一個 AI 看的工作手冊。**  
> 這個 repo 是 Muggle Zoo 的主網站。讀完這份 README，就能接手繼續做。

---

## 網站資訊

| 項目 | 內容 |
|------|------|
| 網站名稱 | Muggle Zoo｜麻瓜婆婆動物園 |
| Live URL | https://mugglezoomi-web.github.io/muggle.zoo/ |
| GitHub Repo | https://github.com/mugglezoomi-web/muggle.zoo |
| 帳號 | `mugglezoomi-web`（Muggle Zoo 所有前台內容都在這個帳號下）|

---

## Muggle Zoo 完整架構（三個獨立 Repo）

```
mugglezoomi-web/
├── muggle.zoo              ← 主網站（你現在在這裡）
├── muggle-zoo-newletter    ← 電子報
└── muggle-zoo-tools        ← 小工具
```

三個 repo 各自獨立，壞了只影響自己，方便 debug。主網站用連結串接其他兩個，讀者不會看到 repo 結構。

### Repo 1：主網站 `muggle.zoo`

| | |
|--|--|
| Live URL | https://mugglezoomi-web.github.io/muggle.zoo/ |
| Repo | https://github.com/mugglezoomi-web/muggle.zoo |
| 更新方式 | 手動上傳到 GitHub |

### Repo 2：電子報 `muggle-zoo-newletter`

| | |
|--|--|
| Live URL | https://mugglezoomi-web.github.io/muggle-zoo-newletter/ |
| Repo | https://github.com/mugglezoomi-web/muggle-zoo-newletter |
| 更新方式 | 每期新增一個 `00X.html`，手動上傳 |

### Repo 3：小工具 `muggle-zoo-tools`

| | |
|--|--|
| Live URL | https://mugglezoomi-web.github.io/muggle-zoo-tools/dashboard.html |
| Repo | https://github.com/mugglezoomi-web/muggle-zoo-tools |
| Actions | https://github.com/mugglezoomi-web/muggle-zoo-tools/actions/workflows/pages/pages-build-deployment |
| 更新方式 | 桌機 Python 腳本自動 push（見 Tools README）|

---

## 主網站檔案結構

```
muggle.zoo/
├── README.md              ← 你現在讀的這份
├── index.html             ← 主頁（唯一頁面，single-page）
├── logo-mugglezoo.png     ← 英文 logo（nav 用，約 110px）
├── logo-chinese.png       ← 中文 logo「麻瓜婆婆動物園」
├── headkv.png             ← Hero 區塊的 KV 插圖（麻瓜婆婆和 AI 獸們）
├── sky.png                ← Hero 星空背景
├── icon-newsletter.png    ← 電子報功能 icon
├── icon-tool.png          ← 小工具功能 icon
├── icon-market.png        ← 市場分析功能 icon
└── icon-auto.png          ← 自動化功能 icon
```

---

## 設計系統（Design Tokens）

主網站、電子報、工具三個 repo 共用同一套，**不能單獨改，要改就三邊同步**。

```css
--night:       #050d1a   /* 深夜藍，主背景 */
--night-card:  #0d1a2e   /* 卡片背景 */
--gold:        #f5c842   /* 金色，主 accent */
--gold-dim:    #c9a235   /* 金色暗版，副標 */
--gold-glow:   rgba(245,200,66,.15)
--cream:       #f8f7f2   /* 奶油白，淺色區塊 */
--text-light:  #e8dcc8   /* 深色背景上的文字 */
--text-dim:    #a09480   /* 說明文字 */
--border-dark: #1a2a45   /* 深色邊框 */
```

### 字體

```
標題：  Noto Serif TC（加粗，大標題用）
內文：  Noto Sans TC（所有內文）
數字：  JetBrains Mono（工具頁數字/代號）
```

---

## 主網站頁面結構（index.html）

```
Nav（固定頂部）
  └── Logo | 影片 | 定位 | 訂閱 | Mi's Marketing

Hero（星空背景）
  └── 中文 Logo + tagline + CTA 按鈕（看最新影片 / 看小工具）

Latest Episode（奶油白底）
  └── 本週影片 iframe + YouTube 連結

Content Pillars（深夜藍底）
  └── 三個定位支柱（市場 / 工具 / 自動化）

Newsletter（奶油白底）
  └── 訂閱說明 + 連結

About（深夜藍底）
  └── 麻瓜婆婆簡介

Footer
  └── YouTube / Threads / Mi's Marketing
```

---

## 重要連結（主網站對外連結）

| 用途 | URL |
|------|-----|
| YouTube 頻道 | https://youtube.com/@muggle-zoo |
| Threads | https://www.threads.com/@muggle.zoo |
| 電子報頁 | https://mugglezoomi-web.github.io/muggle-zoo-newletter/ |
| 台股評估地圖 | https://mugglezoomi-web.github.io/muggle-zoo-tools/dashboard.html |
| Mi's Marketing | https://mismkt.com/zh/home/ |

---

## 每週更新 Checklist

### 影片上線後（週六）

- [ ] 把最新 YouTube 影片 ID 填入 `index.html` 的 iframe `src`
  ```html
  <iframe src="https://www.youtube.com/embed/【VIDEO_ID】" ...>
  ```
- [ ] 上傳更新的 `index.html` 到 GitHub

### 電子報發出後（週日）

- [ ] 確認 `muggle-zoo-newletter` repo 已有最新期 `00X.html`
- [ ] 主網站電子報區塊的連結是否需要更新

---

## 相關 README

每個 repo 都有自己的 README，包含完整的架構說明和操作指南：

- 主網站：你現在在這裡
- 電子報：[muggle-zoo-newletter/README.md](https://github.com/mugglezoomi-web/muggle-zoo-newletter)
- 小工具：[muggle-zoo-tools/README.md](https://github.com/mugglezoomi-web/muggle-zoo-tools)

---

## 投資工具後台（背後，讀者看不到）

Muggle Zoo 的投資分析工具由另一個 GitHub 帳號 `mis23ms` 維護，獨立運作。小工具的資料由桌機 Python 腳本自動更新並 push 到 `muggle-zoo-tools`，主網站只負責展示，不需要動到 `mis23ms` 的任何 repo。

---

*Content IP under Mi's Marketing*  
*Muggle Zoo 麻瓜婆婆動物園*
