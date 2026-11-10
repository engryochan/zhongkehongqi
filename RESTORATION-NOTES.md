# zhongkehongqi 本機還原紀錄

還原日期：2026-11-10（Asia/Shanghai）
來源：https://github.com/engryochan/zhongkehongqi.git
分支：世博量化研究院
提交：e39898123d1c2f92d8b1cb332aae9cc6a62f6672

## 已完成

- 在原資料夾恢復 Git 資訊及完整歷史，共 1,090 筆提交，非淺層倉庫。
- 本機分支追蹤 origin/世博量化研究院；與遠端比較為 0 ahead / 0 behind。
- 主倉庫共有 7,781 個樹狀項目，包含 7,778 個檔案及 3 個子模組。
- 已下載並檢出 pinyin-pro、xiaozhuan、cnum 的指定版本，三個子模組工作目錄乾淨。
- 初始比對有 45 個原路徑不存在；其中 44 個含 Windows 不支援字元。
- 28 個檔案已有內容相同的相容檔名副本，保留原檔；另補回 17 個檔案。
- 45 個對應檔案皆以 git hash-object --no-filters 核對 Git blob 雜湊一致。
- Git 物件連通性檢查 git fsck --connectivity-only --no-dangling 通過。
- 原有可正常命名的追蹤檔案無內容修改；未提交或推送任何變更。

## Windows 檔名限制

遠端有 44 個檔名包含換行、豎線、冒號、問號等 Windows 不支援的字元。
本機相容名稱以底線替換這些字元；原路徑、相容路徑及雜湊詳見 WINDOWS-FILENAME-MAP.json。
該對照表也包含 1 個以原名補回的普通檔案。

原始 Git 歷史與索引保留遠端名稱，因此 git status 仍會列出 44 個原路徑為刪除，並列出相容名稱等未追蹤檔案。這些項目的內容已保留，並非仍缺少下載。
尚未暫存任何差異。若要讓 Windows 工作目錄完全乾淨且能完整檢出，需要另行將遠端這些名稱改為 Windows 相容名稱，或使用支援原檔名的 Linux 檔案系統。請勿把這批顯示為刪除的路徑當成有意刪除直接提交。

本機已啟用 core.longpaths=true，並設定 core.autocrlf=false 以保留下載檔案的行尾。子模組使用本機 HTTPS URL 設定，未改寫追蹤中的 .gitmodules。

## ZIP 為何沒有 .git

GitHub Download ZIP 是指定版本的檔案快照，不包含 .git 歷史資料，也不會完整下載子模組內容。這不代表專案需要重建。
官方說明：https://docs.github.com/en/repositories/working-with-files/using-files/downloading-source-code-archives
