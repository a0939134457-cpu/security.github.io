# HW1 資訊安全新聞紀錄

**學號：411280918**  
**整理與新增日期：2026-11-16**  
**本次新增：15 則**

本頁參考老師的 [The Security News](https://hackmd.io/@chiounan/security-news)，整理資訊安全事件與技術報導，並附上來源、內容摘要與閱讀心得。以下 15 則均於 2026-11-16 整理，依來源發布日期由新到舊排列，屬歷史事件選讀，不代表已完成 15 週的更新。後續仍須依課程要求每週至少新增一則。

報導日期指所列來源的發布日期，與事件發生日期可能不同。摘要描述來源所述情況；「心得與防護觀點」為閱讀後的整理，不表示曾實際遭遇或測試該攻擊。修補版本與處置方式應以廠商最新公告為準。

## 01 React2Shell 漏洞遭多個攻擊群體利用

- **報導日期：**2025-12-12
- **整理日期：**2026-11-16
- **來源：**Google Threat Intelligence Group，[Multiple Threat Actors Exploit React2Shell](https://cloud.google.com/blog/topics/threat-intelligence/threat-actors-exploit-react2shell-cve-2025-55182/)
- **類別：**網站框架漏洞、遠端程式碼執行

**內容摘要：**Google 指出，React Server Components 的 CVE-2025-55182 在 2025 年 12 月公開後，迅速被多個攻擊群體利用。未修補的受影響服務可能讓未登入的攻擊者執行程式碼；觀察到的後續活動包括安裝後門與挖礦程式。

**心得與防護觀點：**常見框架也可能有重大漏洞，不能只更新自己撰寫的程式碼。開發者應盤點實際部署的相依套件，追蹤官方修補公告，並檢查主機是否已遭入侵。

## 02 ClickFix 用假修復與驗證畫面誘導執行惡意指令

- **報導日期：**2025-08-21
- **整理日期：**2026-11-16
- **來源：**Microsoft，[Think before you Click Fix](https://www.microsoft.com/en-us/security/blog/2025/08/21/think-before-you-clickfix-analyzing-the-clickfix-social-engineering-technique/)
- **類別：**社交工程、惡意程式

**內容摘要：**Microsoft 分析 ClickFix 手法：攻擊者假冒錯誤修復、人機驗證或其他通知，誘導使用者將指令貼到終端機執行。攻擊入口可能是釣魚信、惡意廣告或遭入侵的網站，後續則可能安裝竊密程式與遠端控制工具。

**心得與防護觀點：**看到驗證畫面不代表安全。一般網頁驗證不應要求執行系統指令；遇到這類要求應停止操作，向可信任的管理人員確認。

## 03 CISA 公布 SharePoint ToolShell 相關惡意程式分析

- **報導日期：**2025-08-06
- **整理日期：**2026-11-16
- **來源：**CISA，[Malware Analysis Report Associated with Microsoft SharePoint Vulnerabilities](https://content.govdelivery.com/accounts/USDHSCISA/bulletins/3ecbd7d)
- **類別：**企業協作平台、漏洞串接

**內容摘要：**CISA 分析與 SharePoint 漏洞有關的六個惡意檔案，包括 Web shell、DLL 與加密金鑰竊取工具。攻擊者利用稱為 ToolShell 的漏洞串接取得地端 SharePoint 伺服器存取權，再進行資料竊取等活動。

**心得與防護觀點：**修補漏洞與清除入侵痕跡是不同工作。管理員除更新軟體，也應參考公告的入侵指標與偵測規則，檢查是否已有惡意檔案或金鑰外洩。

## 04 Chrome 已遭利用漏洞促使安全更新

- **報導日期：**2025-06-03
- **整理日期：**2026-11-16
- **來源：**加拿大資安中心，[Google Chrome security advisory AV25-314](https://www.cyber.gc.ca/en/alerts-advisories/google-chrome-security-advisory-av25-314)
- **類別：**瀏覽器漏洞、零日攻擊

**內容摘要：**加拿大資安中心轉述 Google 的 Chrome 安全公告，指出 CVE-2025-5419 已有實際利用活動，並提醒使用者與管理員安裝安全更新。公告列出當時 Windows、macOS 與 Linux 桌面版本的修補範圍。

**心得與防護觀點：**瀏覽器經常接觸不受信任的網頁，是重要的修補對象。應維持自動更新並適時重新啟動瀏覽器，確認更新已生效。

## 05 RoundPress 以郵件中的 XSS 竊取信箱資料

- **報導日期：**2025-05-15
- **整理日期：**2026-11-16
- **來源：**ESET，[ESET Research uncovers Operation RoundPress](https://www.eset.com/us/about/newsroom/research/eset-research-uncovers-operation-roundpress-russia-aligned-sednit-targets-entities-linked-to-the-ukraine-war-to-steal-confidential-data/)
- **類別：**網頁郵件、跨網站腳本攻擊

**內容摘要：**ESET 揭露 RoundPress 間諜活動，攻擊者透過魚叉式釣魚郵件利用 webmail 的 XSS 漏洞，在受害者的郵件頁面執行 JavaScript。目標軟體包括 Roundcube、Horde、MDaemon 與 Zimbra，可能遭竊的資料包含憑證、聯絡人與郵件。

**心得與防護觀點：**風險不只來自附件，開啟含惡意內容的郵件也可能觸發漏洞。郵件系統應持續更新，並限制不可信內容在登入環境中的執行能力。

## 06 Windows CLFS 零日漏洞被用於勒索攻擊

- **報導日期：**2025-04-08
- **整理日期：**2026-11-16
- **來源：**Microsoft，[Exploitation of CLFS zero day leads to ransomware activity](https://www.microsoft.com/en-us/security/blog/2025/04/08/exploitation-of-clfs-zero-day-leads-to-ransomware-activity/)
- **類別：**權限提升、勒索軟體

**內容摘要：**Microsoft 發現攻擊者利用 Windows Common Log File System 驅動程式漏洞 CVE-2025-29824，從一般使用者權限提升權限，並在部分目標系統觀察到勒索活動。Microsoft 於報導當日發布修補更新。

**心得與防護觀點：**一般帳號不等於完全安全，攻擊者仍可能串接權限提升漏洞。防護需結合系統更新、端點監控、最小權限與可驗證的離線備份。

## 07 BADBOX 2.0 將未認證裝置變成殭屍網路

- **報導日期：**2025-03-05
- **整理日期：**2026-11-16
- **來源：**HUMAN Security，[HUMAN Exposes BADBOX 2.0 Scheme](https://www.humansecurity.com/newsroom/human-exposes-badbox-2-0-scheme/)
- **類別：**物聯網、供應鏈、廣告詐欺

**內容摘要：**HUMAN 與合作夥伴揭露 BADBOX 2.0，當時辨識出超過一百萬臺遭感染裝置。受影響者包括部分非知名品牌、未認證且使用 Android 開源系統的連網設備，被利用進行廣告詐欺、代理流量轉送等活動；不能據此推論所有 Android 裝置都受影響。

**心得與防護觀點：**購買連網設備時應考慮來源、認證與更新支援。家中物聯網設備也可與主要電腦分開使用網路，降低單一設備遭入侵後的影響。

## 08 Salt Typhoon 入侵電信業網路設備

- **報導日期：**2025-02-20
- **整理日期：**2026-11-16
- **來源：**Cisco Talos，[Weathering the storm In the midst of a Typhoon](https://blog.talosintelligence.com/salt-typhoon-analysis/)
- **類別：**網路設備、帳號濫用、間諜活動

**內容摘要：**Cisco Talos 分析 Salt Typhoon 對電信業的入侵。在其調查的多數 Cisco 設備案例中，攻擊者透過取得合法登入憑證進入，並利用設備既有功能維持存取；僅一個案例有證據顯示可能利用特定 Cisco 漏洞。

**心得與防護觀點：**設備安全不只依靠修補漏洞，也需要保護管理憑證。應限制管理介面來源、避免共用帳號，並監控設定變更與異常登入。

## 09 Storm 2372 濫用裝置代碼登入流程

- **報導日期：**2025-02-13
- **整理日期：**2026-11-16
- **來源：**Microsoft，[Storm 2372 conducts device code phishing campaign](https://www.microsoft.com/en-us/security/blog/2025/02/13/storm-2372-conducts-device-code-phishing-campaign/)
- **類別：**釣魚、驗證權杖、帳號接管

**內容摘要：**Microsoft 揭露攻擊者假冒會議邀請，誘騙受害者在真正的登入頁輸入攻擊者提供的裝置代碼。完成授權後，攻擊者可取得有效權杖並存取帳號資料。這是濫用合法驗證流程，不是單純架設假登入頁。

**心得與防護觀點：**只確認網址正確仍不夠，還要確認授權的是哪個應用程式與裝置。組織可限制不必要的裝置代碼流程，並在疑似入侵時撤銷登入工作階段與權杖。

## 10 FortiOS 與 FortiProxy 驗證繞過漏洞遭利用

- **報導日期：**2025-01-14
- **整理日期：**2026-11-16
- **來源：**NHS England，[Active Exploitation of CVE-2024-55591](https://digital.nhs.uk/cyber-alerts/2025/cc-4604)
- **類別：**防火牆、驗證繞過

**內容摘要：**NHS England 公告指出，CVE-2024-55591 影響部分 FortiOS 與 FortiProxy 版本，未驗證的遠端攻擊者可能透過特製請求取得超級管理員權限。Fortinet 已觀察到實際利用，公告建議更新並檢查入侵指標。

**心得與防護觀點：**防火牆本身也是需要維護的系統。管理介面應限制可連線來源，更新後也要檢查是否存在不明管理帳號或設定變更。

## 11 Ivanti Connect Secure VPN 零日漏洞被用於入侵

- **報導日期：**2025-01-08
- **整理日期：**2026-11-16
- **來源：**Mandiant，[Ivanti Connect Secure VPN Targeted in New Zero Day Exploitation](https://cloud.google.com/blog/topics/threat-intelligence/ivanti-connect-secure-vpn-zero-day)
- **類別：**VPN、緩衝區溢位

**內容摘要：**Mandiant 指出，Ivanti Connect Secure 的 CVE-2025-0282 自 2024 年 12 月中旬起已有零日利用活動。此漏洞屬於未驗證的堆疊緩衝區溢位，成功利用可能造成遠端程式碼執行，並進一步危及內部網路。

**心得與防護觀點：**VPN 是企業對外的重要入口，應優先納入資產盤點與修補。疑似遭入侵時，除了套用更新，也需依廠商指引檢查完整性與相關日誌。

## 12 Firefox 動畫時間軸記憶體漏洞遭實際利用

- **報導日期：**2024-10-09
- **整理日期：**2026-11-16
- **來源：**Mozilla，[Mozilla Foundation Security Advisory 2024 51](https://www.mozilla.org/en-US/security/advisories/mfsa2024-51/)
- **類別：**瀏覽器、記憶體安全

**內容摘要：**Mozilla 修補 CVE-2024-9680，此漏洞位於動畫時間軸處理，屬於釋放後使用記憶體問題。攻擊者可能在瀏覽器內容程序中執行程式碼，且 Mozilla 已收到實際利用的回報。

**心得與防護觀點：**網頁的動畫處理也可能成為攻擊面。瀏覽器應維持在受支援且已更新的版本；內容程序被利用與完整接管作業系統仍是不同層次的影響。

## 13 OpenSSH 修補 regreSSHion 競爭條件漏洞

- **報導日期：**2024-07-01
- **整理日期：**2026-11-16
- **來源：**OpenSSH，[OpenSSH 9.8 release notes](https://www.openssh.org/txt/release-9.8)
- **類別：**遠端登入、競爭條件

**內容摘要：**OpenSSH 9.8 修補 sshd 的重大競爭條件漏洞，影響 Portable OpenSSH 8.5p1 至 9.7p1，可能造成以 root 權限執行程式碼。公告描述當時已在特定 32 位元 Linux/glibc 實驗環境中展示成功利用，不能概括為所有系統都能立即被接管。

**心得與防護觀點：**修補過的問題也可能因後續修改再次出現。維護伺服器時應確認發行版的安全更新狀態，並限制不必要的 SSH 對外存取。

## 14 PAN OS GlobalProtect 命令注入漏洞

- **報導日期：**2024-04-12
- **整理日期：**2026-11-16
- **來源：**Palo Alto Networks，[CVE-2024-3400 security advisory](https://security.paloaltonetworks.com/CVE-2024-3400)
- **類別：**邊界設備、命令注入

**內容摘要：**Palo Alto Networks 公告 CVE-2024-3400，特定 PAN-OS 版本與 GlobalProtect 設定可能讓未驗證攻擊者以 root 權限執行程式碼。廠商已觀察到實際攻擊，並指出關閉裝置遙測並不是有效的緩解方式。

**心得與防護觀點：**緩解建議可能隨調查而變動，不能只看最初的新聞。管理員應持續追蹤官方公告，確認修補完成，並調查是否已有入侵跡象。

## 15 XZ Utils 後門揭露開源供應鏈風險

- **報導日期：**2024-03-30
- **整理日期：**2026-11-16
- **來源：**OpenSSF，[xz Backdoor CVE-2024-3094](https://openssf.org/blog/2024/03/30/xz-backdoor-cve-2024-3094/)
- **類別：**開源軟體、供應鏈攻擊

**內容摘要：**OpenSSF 說明 XZ Utils 5.6.0 與 5.6.1 中遭植入的後門，編號為 CVE-2024-3094。惡意修改針對特定建置環境，可能破壞 sshd 驗證並造成未授權遠端存取；當時受影響版本主要出現在部分預發布發行版，不能解讀為所有 Linux 都已遭入侵。

**心得與防護觀點：**開源程式碼可被檢視，仍需要審查與可信任的建置流程。應關注套件來源、相依關係與發行版公告，將供應鏈風險納入日常維護。

## 16 Cisco IOS 與 IOS XE 修補 SNMP 漏洞

- **報導日期：**2025-09-24
- **整理日期：**2026-11-23
- **來源：**[Cisco 安全公告](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-snmp-x4LPhte)、[CERT-EU 安全公告](https://cert.europa.eu/publications/security-advisories/2025-035/)
- **類別：**網路設備、SNMP、阻斷服務

**內容摘要：**Cisco 公告 IOS 與 IOS XE 的 SNMP 子系統存在堆疊緩衝區溢位漏洞 CVE-2025-20352，評分為 CVSS 7.7。在受影響的設備上，具有低權限 SNMP 憑證的遠端使用者可能讓設備重新啟動，造成服務中斷。Cisco 也指出，在特定高權限條件下，受影響的 IOS XE 設備可能遭遠端執行程式碼。

**心得與防護觀點：**唯讀監控權限也可能影響設備可用性。我認為應先盤點啟用 SNMP 的設備與版本，依官方公告安排更新，並檢查管理介面的可達範圍及 SNMP 憑證的存取權限。

---

## 更新紀錄

| 更新日期 | 本次新增 | 累計則數 | 說明 |
|---|---:|---:|---|
| 2026-11-16 | 15 | 15 | 首次整理歷史事件與技術報導 |
| 2026-11-23 | 1 | 16 | 新增 Cisco IOS 與 IOS XE 的 SNMP 漏洞報告 |

後續每週新增時，請保留既有內容，在此表加入實際更新日期、當次新增數量與累計數量。
