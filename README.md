# 隨機抽歌曲網站

這是一個可部署在 GitHub Pages 的靜態網站，會從 Google 試算表即時讀取歌單並隨機抽歌曲。

## 使用方式

1. 建立一個新的 GitHub Repository。
2. 上傳本資料夾內的 `index.html` 和 `README.md`。
3. 到 GitHub Repository 的 `Settings` → `Pages`。
4. `Build and deployment` 選擇：
   - Source：`Deploy from a branch`
   - Branch：`main`
   - Folder：`/root`
5. 儲存後，GitHub 會產生一個網站網址。

## Google 試算表設定

請把試算表權限設成：

> 知道連結的任何人可查看

網站每次開啟或按下「重新載入歌單」時，都會重新讀取 Google 試算表的最新資料。

## 試算表格式

建議第一列放標題，例如：

| 歌曲 | 歌手 | 備註 |
|---|---|---|
| 稻香 | 周杰倫 | 可合唱 |
| 小幸運 | 田馥甄 | 女聲 |

也支援以下欄位名稱：

- 歌曲、歌名、Song、Title、曲名
- 歌手、Artist、Singer、演唱者
- 備註、Note、Memo、說明

如果沒有標題列，網站會自動使用：

- 第一欄：歌曲
- 第二欄：歌手
- 第三欄：備註

## 修改工作表分頁

如果歌曲資料不是在第一個工作表，請打開該分頁，複製網址中 `gid=` 後面的數字，修改 `index.html` 裡這行：

```js
const SHEET_GID = "0";
```
