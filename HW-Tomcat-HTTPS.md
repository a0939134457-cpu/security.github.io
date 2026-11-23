# Tomcat 7 HTTPS 憑證實驗

## 實驗目標

在 Tomcat-RH7 虛擬機上建立實驗用 Root CA，簽發含正確 IP 位址的伺服器憑證，並驗證 Tomcat 在 8443 提供可信任的 HTTPS。

## 環境與問題

| 項目 | 實際結果 |
| --- | --- |
| 伺服器 | CentOS 7、Apache Tomcat 7.0.76 |
| 實驗網址 | `https://192.168.56.101:8443/` |
| 原憑證 | CN 為 `192.168.56.102`，檢查輸出未顯示 SAN |
| 新憑證 | CN 為 `192.168.56.101`，SAN 包含 `IP Address:192.168.56.101` |
| 新簽發者 | `Tomcat RH7 Lab Root CA` |

## 設定過程

1. 建立 RSA 4096 位元的實驗 Root CA，以及 RSA 2048 位元的 Tomcat 私鑰與 CSR。
2. 由新 Root CA 簽發伺服器憑證，加入 IP SAN 與 `serverAuth` 用途。
3. 將伺服器憑證、私鑰與 CA 憑證封裝成 PKCS#12，再匯入 `/etc/tomcat/keystore-101.jks`。
4. 備份 `/etc/tomcat/server.xml`，更新 8443 Connector 的 keystore 路徑，並重啟 Tomcat。
5. 將公開 Root CA 憑證複製到 Windows，並從瀏覽器開啟 HTTPS 首頁。

## 實測結果

| 檢查 | 結果 |
| --- | --- |
| OpenSSL 憑證鏈驗證 | `tomcat.crt: OK` |
| IP SAN | `IP Address:192.168.56.101` |
| `curl --cacert` 驗證 | `HTTP/1.1 200 OK` |
| 瀏覽器驗收 | 正常顯示 Apache Tomcat/7.0.76 首頁 |
| 講義的 Nmap 憑證與加密套件檢查 | 尚未取得實測輸出 |

```bash
openssl verify -CAfile rootCA.pem tomcat.crt
curl --cacert rootCA.pem -I https://192.168.56.101:8443/
```

本次實驗確認瀏覽器能透過 HTTPS 開啟 Tomcat，且客戶端能使用新 Root CA 驗證憑證。連線使用 IP 位址時，伺服器憑證的 SAN 必須包含該 IP。

[實驗講義](https://hackmd.io/V7VikaDmT928w_vMxDHaWQ)
