# 林瑞德競選網站｜GitHub Pages 上架說明

這是可直接發布的純靜態網站，不需要安裝 Node.js、套件或執行建置指令。

## 壓縮檔內容

```text
index.html
assets/
  burnfont-title.otf
  campaign-banner.webp
  candidate-poster.webp
  donation-qrcode.png
  policy-dm.webp
  ray-portrait.webp
  script.js
  styles.css
.nojekyll
README.md
```

- `index.html`：完整網頁內容與區塊結構
- `assets/styles.css`：桌機版、平板與手機版視覺
- `assets/script.js`：手機選單、投票日倒數、進場動畫與帳號複製功能
- `assets/burnfont-title.otf`：網站主標題使用的激燃體
- `assets/` 內其他圖片：主視覺、人物照、最新版政見單與政治獻金 QR Code
- `.nojekyll`：告訴 GitHub Pages 直接發布靜態檔案

## 方法一：用 GitHub 網頁上傳（建議）

### 1. 解壓縮

先解壓縮下載的 ZIP。請確認解壓後最外層直接看得到 `index.html` 與 `assets` 資料夾。

### 2. 建立 Repository

1. 登入 GitHub。
2. 點右上角 `＋`，選擇 `New repository`。
3. Repository name 建議填入：`zhubei-ray-2026`。
4. Visibility 選擇 `Public`。
5. 不要勾選額外建立 README、.gitignore 或 License，避免和本壓縮檔內的檔案衝突。
6. 點擊 `Create repository`。

### 3. 上傳網站檔案

1. 進入剛建立的 Repository。
2. 選擇 `Add file` → `Upload files`。
3. 將「解壓後資料夾裡面的所有檔案」拖曳至上傳區：
   - `index.html`
   - `assets` 資料夾
   - `README.md`
   - `.nojekyll`
4. Commit message 可填：`Publish Ray Lin campaign website`。
5. 選擇提交至 `main` 分支並完成 Commit。

> 請勿只上傳 ZIP，也不要把外層資料夾整層變成 Repository 的子資料夾；`index.html` 必須位於 Repository 根目錄。

### 4. 開啟 GitHub Pages

1. 在 Repository 上方選擇 `Settings`。
2. 左側選單找到 `Pages`。
3. 在 `Build and deployment` 的 `Source` 選擇 `Deploy from a branch`。
4. Branch 選擇 `main`。
5. Folder 選擇 `/ (root)`。
6. 點擊 `Save`。

GitHub 完成發布後，Pages 設定頁會顯示網站網址。若使用帳號 `jackraymay6-crypto` 且 Repository 名稱為 `zhubei-ray-2026`，預計網址為：

```text
https://jackraymay6-crypto.github.io/zhubei-ray-2026/
```

## 方法二：使用 Git 指令上傳

先在 GitHub 建立一個空的 `zhubei-ray-2026` Repository，再於解壓後的網站資料夾開啟 Git Bash 或 Terminal：

```bash
git init
git add .
git commit -m "Publish Ray Lin campaign website"
git branch -M main
git remote add origin https://github.com/你的GitHub帳號/zhubei-ray-2026.git
git push -u origin main
```

完成後，仍需前往 Repository 的 `Settings` → `Pages`，設定：

- Source：`Deploy from a branch`
- Branch：`main`
- Folder：`/ (root)`

## 日後如何更新網站

### 使用 GitHub 網頁

1. 進入 Repository。
2. 選擇 `Add file` → `Upload files`。
3. 上傳修改後的同名檔案。
4. 確認取代舊檔並 Commit。

### 使用 Git

```bash
git add .
git commit -m "Update campaign website"
git push
```

只要更新已設定的 `main` 分支，GitHub Pages 就會自動重新發布。

## 常見問題

### 網站出現 404

- 確認 `index.html` 位於 Repository 根目錄。
- 確認 Pages 使用 `main` 與 `/ (root)`。
- 到 Repository 的 `Actions` 頁面確認 Pages 部署是否完成。

### 圖片或字型沒有出現

- 確認完整上傳 `assets` 資料夾。
- 不要更改 `assets` 內的檔名或資料夾層級。

### 更新後仍看到舊畫面

- 等待 Pages 重新部署完成。
- Windows 可按 `Ctrl + F5` 強制重新整理；Mac 可按 `Command + Shift + R`。

### 想使用自己的網域

可在 Repository 的 `Settings` → `Pages` → `Custom domain` 設定，但還需要到網域商調整 DNS。沒有自訂網域也不影響網站使用。

## 上架前最後檢查

- [ ] Repository 根目錄看得到 `index.html`
- [ ] `assets` 資料夾完整存在
- [ ] Pages 來源是 `main` 與 `/ (root)`
- [ ] 首頁照片、政見單與政治獻金 QR Code 正常顯示
- [ ] Facebook、Instagram、Threads、YouTube、作品集與線上捐款連結可開啟
- [ ] 手機版選單與政治獻金帳號複製功能正常

