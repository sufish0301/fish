# 開胃菜餐酒館網站規格文件

## 專案概述

本專案為 Bootstrap 5 製作的靜態單頁網站，主題為餐酒館 / 義式餐點介紹頁。主要內容包含上方選單、五張輪播圖、酒類警語、開胃菜展示、美味餐點卡片、頁尾公司資訊與隱私權連結。

網站主要入口檔案為 `index.html`。

## 目前檔案結構

```text
website/
├── index.html              # 主要網頁檔案，建議維護此檔
├── index                   # 舊版同步檔，內容目前與 index.html 相同
├── SPEC.md                 # 本規格文件
├── css/
│   └── bootstrap.min.css   # 本地端 Bootstrap 5 CSS
├── js/
│   └── bootstrap.bundle.min.js # 本地端 Bootstrap 5 JS，包含 Carousel 所需功能
└── images/
    ├── logo.jpg
    ├── istockphoto-1319973261-612x612.jpg
    ├── istockphoto-2023102269-612x612.jpg
    ├── istockphoto-1472507423-612x612.jpg
    ├── istockphoto-1144823591-612x612.jpg
    ├── istockphoto-1346128287-612x612.jpg
    ├── istockphoto-938742222-612x612.jpg
    ├── istockphoto-2149017451-612x612.jpg
    └── istockphoto-943449226-612x612.jpg
```

## 技術規格

- HTML5
- CSS3
- Bootstrap 5，本地端引用
- 不使用 CDN
- 不需要後端伺服器
- 可直接用瀏覽器開啟 `index.html`

Bootstrap 引用位置：

```html
<link href="css/bootstrap.min.css" rel="stylesheet">
<script src="js/bootstrap.bundle.min.js"></script>
```

## 頁面區塊

### 1. 上方選單

位置：`<nav class="top-menu">`

選單項目：

- 開胃菜
- 主餐
- 披薩
- 酒水
- 甜點

目前選單為直式排列，點擊後會跳到對應區塊 ID。

### 2. 輪播圖

位置：`<section id="heroCarousel">`

使用 Bootstrap Carousel，共五張圖片：

```text
images/istockphoto-1319973261-612x612.jpg
images/istockphoto-2023102269-612x612.jpg
images/istockphoto-1472507423-612x612.jpg
images/istockphoto-1144823591-612x612.jpg
images/istockphoto-1346128287-612x612.jpg
```

第一張輪播圖有標題與副標：

- 標題：美味餐點
- 副標：精選餐酒搭配，享受放鬆的夜晚。

### 3. 酒類警語

位置：`<div class="drink-warning">`

內容：

```text
禁止酒駕🚫未滿18歲禁止飲酒
```

### 4. 開胃菜區塊

位置：`<section id="appetizer">`

目前圖片：

```text
images/istockphoto-938742222-612x612.jpg
```

### 5. 美味餐點 Card

位置：`<section class="meal-section">`

目前使用 Bootstrap Card 模組，共六張卡片：

| 分類 | 名稱 | 圖片 | 價格 |
| --- | --- | --- | --- |
| 主餐 | 香煎牛排 | `images/istockphoto-1472507423-612x612.jpg` | NT$ 520 |
| 披薩 | 瑪格麗特披薩 | `images/istockphoto-2023102269-612x612.jpg` | NT$ 320 |
| 酒水 | 招牌調酒 | `images/istockphoto-1319973261-612x612.jpg` | NT$ 260 |
| 甜點 | 巧克力熔岩 | `images/istockphoto-1346128287-612x612.jpg` | NT$ 180 |
| 主餐 | 海鮮燉飯 | `images/istockphoto-2149017451-612x612.jpg` | NT$ 360 |
| 披薩 | 分享披薩 | `images/istockphoto-943449226-612x612.jpg` | NT$ 340 |

### 6. 頁尾

位置：`<footer class="footer">`

內容包含：

- Logo：`images/logo.jpg`
- 公司名稱：義式餐飲股份有限公司
- 電話：02-XXXX-XXXX
- 地址：義式市番茄區酒館路
- 隱私權政策連結
- 版權文字

頁尾下方另有安全提醒：

```text
開車不喝酒 安全有保障
```

## CSS 維護重點

自訂樣式目前直接寫在 `index.html` 的 `<style>` 區塊內。

主要 CSS 變數：

```css
:root {
  --brand-brown: #a7652f;
  --brand-orange: #d98443;
  --ink: #1f1714;
  --footer: #5f5653;
}
```

主要自訂 class：

- `.site-shell`：頁面最大寬度與白色主容器
- `.top-menu`：上方黑底選單
- `.hero-carousel`：輪播圖高度與圖片裁切
- `.drink-warning`：上方酒類警語
- `.section-title`：區塊標題
- `.meal-section`：餐點卡片區
- `.meal-card`：餐點卡片樣式
- `.footer`：頁尾資訊
- `.footer-logo`：頁尾 Logo 圖片
- `.safety-banner`：最下方安全提醒

## 圖片替換規則

所有圖片皆放在 `images/` 資料夾。

替換圖片時建議：

1. 保留圖片在 `images/` 資料夾內。
2. 圖片檔名避免空白，可使用英文、數字、連字號。
3. 修改 `index.html` 中對應的 `src="images/檔名"`。
4. 同步檢查 `alt` 文字是否符合圖片內容。
5. 如果仍需維護 `index` 檔，也要同步相同修改。

建議圖片比例：

- 輪播圖：橫式圖片，建議 16:9 或接近方形也可，CSS 會用 `object-fit: cover` 裁切。
- Card 圖片：建議橫式或方形，CSS 固定高度為 210px。
- Logo：建議透明背景 PNG 或 JPG，目前使用 `logo.jpg`。

## 後續維護注意事項

- 建議主要維護 `index.html`，避免同時改 `index` 和 `index.html` 造成版本不同。
- 若使用 VS Code Live Server，請開啟 `index.html`。
- Bootstrap 已改為本地端引用，搬移專案時需一併保留 `css/` 和 `js/` 資料夾。
- 若 Carousel 無法切換，請確認 `js/bootstrap.bundle.min.js` 路徑是否正確。
- 若樣式失效，請確認 `css/bootstrap.min.css` 路徑是否正確。
- 若圖片不顯示，請確認圖片檔名、大小寫與副檔名完全一致。

## 建議改善項目

- 將自訂 CSS 獨立成 `css/style.css`，讓 HTML 更容易閱讀。
- 移除或停止維護無副檔名的 `index`，統一使用 `index.html`。
- 將隱私權政策連結改為實際頁面，例如 `privacy.html`。
- 若要完全正式上線，建議補上真實公司名稱、地址、電話與圖片授權來源。
