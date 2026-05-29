# talentismin · iOS Studio

公開的 App 介紹 / 隱私權 / 支援頁面集合。透過 GitHub Pages 部署到
<https://talentismin.github.io/studio/>。

## 結構

```
studio/
├── index.html              # 工作室首頁（列出所有 App）
├── shared-assets/
│   └── styles.css          # 跨 App 共用 CSS
├── novalreader/
│   ├── index.html          # 產品介紹頁
│   ├── privacy-policy.html # 隱私權政策（從舊 novalreader-privacy 搬入）
│   └── support.html
├── runninghero/
│   ├── index.html
│   ├── privacy-policy.html
│   └── support.html
└── README.md
```

## 新增一個 App

1. `mkdir <appname>` 在根目錄建子資料夾
2. 從現有 app 子目錄複製 `index.html / privacy-policy.html / support.html` 三檔，
   改名稱與內容（CSS 直接吃 `/shared-assets/styles.css` 不用動）
3. 在根 `index.html` 的 `.app-grid` 新增一張 `.app-card`
4. push 即上線

## 本地預覽

```sh
python3 -m http.server 8000
open http://localhost:8000/
```

## 注意

- `.nojekyll` 檔避免 GitHub Pages 把資料夾名稱以 `_` 開頭的東西過濾掉，並關閉 Jekyll 處理
- 每個 `<a href="/shared-assets/styles.css">` 預期 site 部署在 user.github.io/studio/ 根；
  若改部署位置需更新絕對路徑
