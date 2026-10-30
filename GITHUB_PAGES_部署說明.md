# EMOTION / SYSTEM — GitHub Pages 部署說明

## 上傳
1. 解壓縮本 ZIP。
2. 將解壓後資料夾**裡面的所有檔案及資料夾**上傳至原 GitHub 儲存庫的根目錄（不是再包一層資料夾）。
3. 請保留 `.github/workflows/deploy-pages.yml`，這是自動部署設定；GitHub 網頁上傳隱藏資料夾可能較不方便，建議透過 GitHub Desktop 將解壓檔案複製到已 Clone 的儲存庫，Commit 並 Push。
4. GitHub 儲存庫 → Settings → Pages → Build and deployment → Source 選 **GitHub Actions**。
5. GitHub → Actions → Deploy EMOTION SYSTEM to GitHub Pages，確認執行成功。
6. 網址通常是 `https://<使用者名稱>.github.io/<儲存庫名稱>/`。儲存庫名稱由工作流程自動讀取。

## 注意
- 這是完整原始碼與部署設定，**不是已編譯的 dist 網站**。首次發布由 GitHub Actions 執行 pnpm 安裝與 Vite 建置。
- GitHub Pages 不提供 Node.js/Express 後端；此部署只發布 `artifacts/emotion-system` 的前端。
- 影片/攝影機需要瀏覽器 HTTPS 權限。請在實際發布後測試模型、Shader、錄影、下載、手機瀏覽器。
- 已加入 404.html 作為 SPA 直接連結的回退頁面；GitHub Pages 對深層路由可能短暫顯示 404 HTTP 狀態，但前端仍可載入。
- 如果 GitHub Actions 安裝或建置失敗，請提供 Actions 紅色失敗步驟的完整 log，不要猜測成功。
- **將 GitHub 儲存庫設成 Public 會公開原始碼**；請先確認沒有敏感金鑰與隱私資料。
- 新網址成功後，才關閉 Replit 原本的付費 Deployment。停止部署和刪除 Replit 專案不同。
