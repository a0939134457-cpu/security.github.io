# Nmap 安全調查實驗報告

## 實驗環境

掃描端為 Tomcat-RH7，使用 Nmap 6.40。目標為 Metasploitable 2。所有測試在 VirtualBox 實驗網段內進行。

## A．HTTP 服務辨識與網頁路徑列舉

Nmap 確認 80/tcp 開放，首頁標題為 **Metasploitable2 - Linux**。HTTP 標頭顯示伺服器為 Apache/2.2.8 (Ubuntu) DAV/2，PHP 版本為 5.2.4-2ubuntu5.10。

http-enum 列出 `/tikiwiki/`、`/test/`、`/phpinfo.php`、`/phpMyAdmin/`、`/doc/`、`/icons/` 和 `/index/`。另以 curl 查詢 `/admin`、`/login` 和 `/robots.txt`，三者皆回傳 HTTP 404。目標主機的 Apache 設定顯示網站根目錄為 `/var/www/`。

## B．NetBIOS 主機資訊

Nmap 確認 137/udp 開放，服務為 netbios-ns。nbstat 回傳主機名稱 **METASPLOITABLE** 與工作群組 **WORKGROUP**。nbstat 的 MAC 欄位為 `<unknown>`。Nmap 掃描摘要另有辨識到網卡 MAC，與目標機 eth1 的本機查詢結果一致。

## C．FTP 本機查核

TCP 21 由 xinetd 監聽。`/etc/xinetd.d/vsftpd` 內的 FTP 服務指向 `/usr/sbin/vsftpd`。該執行檔存在且可執行，dpkg 查不到其套件歸屬。

執行檔 SHA-256 為 `01c115bd2b95eee4327f08066381121597891e5d9fba9475e1cdb2874aafa205`。雜湊尚未與可信參考樣本比對，**後門狀態未驗證**。

[實驗講義](https://hackmd.io/nBzHSM_NTECSBC9gs3KgdQ?view)
