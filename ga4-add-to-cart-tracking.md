# GA4 加購事件追蹤紀錄

## 變更內容
- 在首頁的「加入購物車」按鈕點擊事件中加入 GA4 的 `add_to_cart` 事件追蹤。
- 事件包含商品資訊與價格欄位，方便後續在 Google Analytics 中分析加購行為。

## 事件範例
```javascript
gtag("event", "add_to_cart", {
  currency: "新台幣",
  value: 1200,
  items: [
    {
      item_id: "SKU_12345",
      item_name: "Stan and Friends Tee",
      affiliation: "Google Merchandise Store",
      coupon: "SUMMER_FUN",
      discount: 2.22,
      index: 0,
      item_brand: "Google",
      item_category: "Apparel",
      item_category2: "Adult",
      item_category3: "Shirts",
      item_category4: "Crew",
      item_category5: "Short sleeve",
      item_list_id: "related_products",
      item_list_name: "Related Products",
      item_variant: "green",
      location_id: "ChIJIQBpAG2ahYAR_6128GcTUEo",
      price: 10.01,
      google_business_vertical: "retail",
      quantity: 3
    }
  ]
});
```

## 相關檔案
- [index.html](index.html)
