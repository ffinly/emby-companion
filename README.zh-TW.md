<p><img src="assets/images/app-icon.png" alt="Emby Companion" width="96" height="96"></p>

# Emby Companion

[简体中文](README.md) | **繁體中文** | [English](README.en.md)

---

**發現影視、瀏覽媒體庫、播放與訂閱**

Emby 觀影助手是一款 macOS 應用程式，將影視榜單、TMDB 搜尋、Emby 媒體庫與 MoviePilot 訂閱連接起來。從找片、核對入庫，到外部播放與進度同步，在一個應用程式裡完成。

[下載最新版](https://github.com/ffinly/emby-companion/releases/latest) · [版本記錄](https://github.com/ffinly/emby-companion/releases) · [回報問題](https://github.com/ffinly/emby-companion/issues)

本儲存庫提供安裝包、使用說明與問題回報；應用程式閉源，不提供影視資源、伺服器帳號或第三方服務憑證。

## 主要功能

- **榜單探索**：瀏覽 IMDb、豆瓣、TMDB、影展與獎項等榜單，查看排名和入庫狀態；從作品詳情查看收錄它的榜單。預設榜單隨 [emby-collection-sync](https://github.com/ffinly/emby-collection-sync) 更新，也可新增 TMDB 片單或建立個人片單。
- **搜尋與人物作品**：按名稱、人物或 TMDB 編號搜尋，瀏覽簡介、評分、演職人員與人物作品集；詳情頁可前往豆瓣、IMDb 和 TMDB。
- **媒體庫與合集**：瀏覽 Emby 電影、劇集、合集、季度與分集，查看可播放版本，管理觀看狀態；可暫時隱藏觀看記錄與進度。
- **入庫與缺集核對**：根據已同步的 Emby 資料顯示入庫狀態，並按季度對照 TMDB 集數與 Emby 實際集號。尚未核對或總集數未知時會另行提示。
- **核心榜單入庫率**：預設統計第一至第三梯隊，支援按級別選擇、個別勾選或排除榜單，儲存後更新去重統計。首頁的全部片單作品數與已入庫數量仍按所有片單統計。
- **MoviePilot 整合**：訂閱未入庫電影或缺集季度，自動略過已入庫、集數已齊及已有訂閱的內容；支援搜尋和批次管理訂閱。MoviePilot 為選用服務，下載與入庫由其處理。
- **多線路與外部播放**：同一 Emby 伺服器可分別設定資料同步與播放線路，選擇媒體版本後呼叫 SenPlayer、Infuse 或 VidHub，支援續播與觀看進度回傳。
- **資料與圖片快取**：完整同步媒體庫後自動取得所選語言的 TMDB 影視、人物及整季分集資料，圖片按需載入；可查看同步結果、重試失敗項目，並管理快取或重建本機搜尋索引。
- **備份與還原**：按需選擇設定、片單、快取及使用偏好，匯出加密備份並選擇還原範圍。

## 語言與顯示

在「連接與配置 → 語言」分別設定介面、預設片單、TMDB 中繼資料及海報語言。介面支援跟隨系統、簡體中文、繁體中文與英文；片單和中繼資料可跟隨介面，也可獨立選擇三種語言。

榜單同步會讀取並快取上游的三語名稱，切換已有名稱無需重新下載。影視與人物資料、分集資訊及同步歷史中的作品名稱跟隨 **TMDB 中繼資料語言**，不同語言資料分別快取；缺少對應資料時保留可用的 Emby 內容。資料重新整理只更新本機，不改寫伺服器中繼資料。

海報可選原語言、中文或英文。已有圖片可重複使用，未快取圖片仍需連線。媒體庫名稱支援預設中英對照與自訂顯示名稱，留空保留原名稱，僅影響本應用程式。

## 下載與初次使用

需要 **macOS 14 或更新版本**，通用安裝包支援 **Apple Silicon 與 Intel**。從 [最新 Release](https://github.com/ffinly/emby-companion/releases/latest) 下載 DMG，將 **Emby Companion.app** 拖入「應用程式」；取代舊版前先結束應用程式。

### 首次開啟：macOS 安全提示

目前安裝包使用本機簽署，尚未經過 Apple Developer ID 簽署和公證。確認來源為本儲存庫 Releases 後，先嘗試開啟一次；如遭系統阻擋，前往 **系統設定 → 隱私權與安全性 → 強制打開**，依提示確認。若提示損壞或偵測到惡意軟體，請核對來源並回報具體提示。參見 [Apple 官方說明](https://support.apple.com/zh-tw/102445)；後續安裝包的簽署狀態以 Release 說明為準。

### 連線服務

1. 在「連接與配置」填入 Emby 位址並登入。
2. 在 [TMDB API 設定](https://www.themoviedb.org/settings/api) 申請自己的 API Key，閱讀 [API 使用條款](https://www.themoviedb.org/api-terms-of-use)，再填入應用程式；需要時可設定 TMDB HTTP／SOCKS 代理。
3. 在首頁執行「完整同步媒體庫」並同步榜單，查看進度與結果。
4. 安裝外部播放器。需要訂閱時，再填入 MoviePilot 服務位址與 API 權杖；權杖可從 MoviePilot「設定 → 系統 → 基本設定」複製。

<a id="zh-hant-emby-routes-and-players"></a>

## 線路與播放器

同一伺服器與帳號的多條線路共用媒體庫快取，可分別指定同步主線路與預設播放線路，也可透過 `ecplayer://importserver` 連結預覽並匯入設定。格式見應用程式內「Emby 線路 → 通過鏈接導入 Emby」。

| 外部播放器 | 支援結束播放後回傳進度的版本 |
| --- | --- |
| SenPlayer | 6.1.1 及以上 |
| Infuse | 8.4.7 及以上 |
| VidHub | 2.3.5 及以上 |

啟用「退出播放器後同步觀看進度」，並正常關閉播放器的播放頁面，應用程式收到回呼後將進度同步至 Emby。強制結束或未收到回呼時無法透過此次回呼更新進度；網路異常導致回傳失敗時，可在首頁重試。播放器需自行安裝，回呼能力取決於版本及實際回傳結果。

## 軟體更新

在「連接與配置 → 軟體更新」手動檢查更新，或啟用自動檢查與下載。驗證通過後由更新視窗引導安裝並重新啟動；驗證失敗會停止安裝。

支援多語言的更新日誌隨目前介面語言顯示；舊版單語言日誌保留原文。

## 快取與備份

「連接與配置」提供快取清理、本機搜尋索引重建及加密備份。清理本機快取不刪除 Emby 伺服器內容，連線與登入資訊保留；之後可重新同步。

| 備份內容 | 包含的資料 |
| --- | --- |
| TMDB API 配置 | API 位址與 API Key |
| MoviePilot API 配置 | 服務位址與 API 權杖 |
| TMDB 榜單 | 榜單內容、自建片單、片單設定與核心榜單範圍 |
| TMDB 快取 | 影視與人物資料、海報和人物圖片 |
| Emby 配置 | 伺服器、線路、目前帳號、登入權杖及觀看記錄 |
| Emby 快取 | 媒體庫、合集、分集及 Emby 圖片 |
| 使用偏好 | 語言、名稱對照、播放器與顯示偏好 |

匯出時選擇內容，設定至少 **8 個字元**的密碼，儲存為 `.ecbackup`。還原時可再次選擇範圍：設定、榜單與偏好取代對應內容，快取合併。核心榜單設定隨「TMDB 榜單」備份；觀看記錄隨「Emby 配置」備份，僅包含目前帳號，還原時核對伺服器與帳號並保留較新的記錄。

備份可能包含 API 金鑰與登入資訊，請妥善保管檔案和密碼。

## 隱私與回報

連線資訊與快取儲存在本機。應用程式根據功能向你設定的服務、TMDB 和 GitHub 請求資料；GitHub 榜單設定與更新請求不攜帶 TMDB API Key 或 Emby 登入憑證。

回報時請提供應用程式版本、macOS 版本、操作步驟及錯誤提示，並隱藏截圖或日誌中的位址、帳號、金鑰等私人資訊。

## 📈 Star History

<a href="https://www.star-history.com/?repos=ffinly%2Femby-companion&amp;type=date&amp;legend=top-left">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/chart?repos=ffinly/emby-companion&amp;type=date&amp;theme=dark&amp;legend=top-left" />
    <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/chart?repos=ffinly/emby-companion&amp;type=date&amp;legend=top-left" />
    <img alt="Star History Chart" src="https://api.star-history.com/chart?repos=ffinly/emby-companion&amp;type=date&amp;legend=top-left" />
  </picture>
</a>

## 許可與第三方說明

軟體使用條款見[使用許可](LICENSE.txt)。

影視內容、資料、圖片、人物肖像及第三方標識的權利歸各自權利人所有。應用使用的獨立開源組件適用各自許可，詳見 [第三方說明](THIRD_PARTY_NOTICES.md)。本軟體的使用許可不替代相關服務的使用條款。

## TMDB 署名

<a href="https://www.themoviedb.org"><img src="assets/images/tmdb-logo.svg" alt="TMDB" width="120"></a>

本產品使用 TMDB API，但未經 TMDB 認可或認證。

This product uses the TMDB API but is not endorsed or certified by TMDB.

[The Movie Database](https://www.themoviedb.org) · [API 使用條款](https://www.themoviedb.org/api-terms-of-use)

Emby、MoviePilot、各播放器及 TMDB 的名稱和標識歸各自權利人所有。本應用與這些服務的運營方無隸屬或認證關係。
