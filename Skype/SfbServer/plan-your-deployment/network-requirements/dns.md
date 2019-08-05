---
title: 商務用 Skype Server 的 DNS 需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: '摘要: 在執行商務用 Skype Server 前, 請先查看本主題中的 DNS 考慮事項。'
ms.openlocfilehash: 5e6bb5866cfc52dc02a1fc48c19b1f43af6077f7
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2019
ms.locfileid: "36193946"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>商務用 Skype Server 的 DNS 需求

**摘要:** 在執行商務用 Skype Server 前, 請先複習本主題中的 DNS 考慮事項。

本文只會針對組織內部部署網路上的商務用 Skype Server 部署進行 DNS 規劃。 如果是商務用 Skype Online, 請參閱「Office 365 Url 與 IP 位址範圍[https://aka.ms/o365ips](https://aka.ms/o365ips)」。

功能變數名稱服務 (DNS) 伺服器對應主機名稱 (例如 www)。<span> </span>contoso<span></span>.com (大概是 web 伺服器) 至 IP 位址 (例如 10.10.10.10)。 它可協助用戶端和相互獨立的伺服器彼此通訊在網路上。 當您設定商務用 Skype Server 2015 的實施時, 您必須確認新伺服器名稱的對應 (通常會反映其所做的角色) 符合指派給它們的 IP 位址。

雖然這看起來可能相當令人望而生畏, 但開始使用[商務用 Skype Server 2015 規劃工具](https://www.microsoft.com/en-us/download/details.aspx?id=50357)完成這項工作的繁重動作。 當您完成您打算使用之功能的嚮導問題之後, 針對您定義的每個網站, 您都可以在 Edge 管理報表中查看 DNS 報表, 並使用這裡列出的資訊來建立您的 DNS 記錄。 您也可以調整所使用的許多名稱和 IP 位址, 如需詳細資訊, 請參閱[查看 DNS 報告](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report)。 請記住, 您可以將 Edge 系統管理報表匯出為 Excel 試算表, 而 DNS 報表則是檔案中的其中一個工作表。 雖然此工具組含已[從商務用 Skype Server 2019 中棄用](../../../SfBServer2019/deprecated.md)的功能, 但如果未選取這些功能, 仍可使用它來建立初始方案

如果您按照在[建立商務用 Skype server 的 DNS 記錄](../../deploy/install/create-dns-records.md)及建立商務用 skype server 的拓撲中所述的方式來安裝新的實現, 我們就會認識到, 您可以選擇使用 Windows Server 內建的 dns 功能2016或協力廠商的 DNS 套件, 所以我們將在本文中繼續進行, 而不是特定的討論。 我們會詳細說明所需的專案, 以及您符合該需求的方式是您的決定。

經驗豐富的商務用 Skype、Lync 和 Office 通訊套件管理員可能會發現下清單格對您有所説明。 如果表格對您造成混淆, 後續章節或文章將會 shed 下列概念的一些小部分:

## <a name="summary-tables"></a>摘要表格
<a name="BK_Summary"> </a>

下表顯示商務用 Skype Server 用 Skype 伺服器用來提供服務給使用者的 DNS 記錄。 有些是選擇性的, 因為它們只需要支援特定功能, 而且如果不想要的話, 也可以略過這些功能。 僅限內部存取所需的 DNS 記錄位於第一個資料表中, 而且允許內部和外部存取的部署需要來自兩個數據表的記錄。

**內部 DNS 對應**

|記錄類型|值|解析為|特殊|必要|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |前端池 FQDN  <br/> *FE-池子。<span> </span>contoso<span> </span>*   |前端池伺服器 IP 位址  <br/>  DNS LB to *192.168.21.122 192.168.21.123 192.168.21.124*   |前端池的 DNS 負載平衡。 將前端池名稱對應到一組 IP 位址。  <br/> 請參閱[在前端池和控制器池上部署 DNS 負載平衡](load-balancing.md#BK_FE_Dir)  |是   |
|A/AAAA   | 在池或獨立伺服器中, 每個前端伺服器或標準版伺服器的 FQDN <br/>  *FE01.<span> </span>contoso。<span> </span>[com FE02]。<span> </span>contoso<span></span>FE03。<span> </span>contoso<span> </span>*   |每個伺服器對應的 IP  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |將伺服器名稱對應至它的 IP 位址。   |是   |
|A/AAAA   |企業版池內部 Web 服務會覆寫 FQDN  <br/> *Web int<span></span><span></span>.com*   |HLB 前端伺服器內端 Web 服務的 VIP  <br/> *192.168.21.120*   |需要啟用用戶端到伺服器網路流量 (例如下載商務用 Skype Web App)。 對於行動用戶端也是必要的。   |是   |
|A/AAAA   |企業版池外部 Web 服務會覆寫 FQDN  <br/> *網站-ext<span></span><span></span>. .com*   |HLB 前端伺服器外部 Web 服務的 VIP  <br/>*68.123.56.90*   |需要啟用用戶端到伺服器網路流量 (例如下載商務用 Skype Web App)。 如果行動用戶端將在內部解析 DNS, 則為必要。 可以解析成 DMZ 反向 Proxy IP 或網際網路 IP。   ||
|A/AAAA   | 後端伺服器 SQL Server FQDN <br/> *SQL1.<span> </span>contoso<span> </span>*   |伺服器 IP 位址  <br/> *192.168.11.90*   |將使用 [前端] 池的後端 SQL server 的伺服器名稱對應到其 IP 位址   ||
|A/AAAA   |後端伺服器鏡像 SQL Server FQDN  <br/> *SQL2.<span> </span>contoso<span> </span>*   |伺服器 IP 位址  <br/> *192.168.11.91*   |將使用 [前端] 池的後端 SQL 鏡像伺服器的伺服器名稱對應到其 IP 位址   ||
|A/AAAA   |控制器池 FQDN  <br/>**注意:** 使用獨立的控制器伺服器時不適用 <br/> *DirPool.<span> </span>contoso<span> </span>*   |控制器池 IP 位址  <br/> DNS LB to *192.168.21.132、192.168.21.133、192.168.21.134*   |控制器池伺服器的 DNS 負載平衡。 將主管池的 [池名稱] 對應至 IP 位址, 請參閱[在前端池和控制器池上部署 DNS 負載平衡](load-balancing.md#BK_FE_Dir) <br/> 控制器可以驗證使用者, 且是選擇性的。   ||
|A/AAAA   |控制器 FQDN   |每個控制器伺服器的伺服器 IP 位址   |將主管的 [池名稱] 對應至 IP 位址, 請參閱[在前端池和控制器池上部署 DNS 負載平衡](load-balancing.md#BK_FE_Dir)  ||
|A/AAAA   |中繼伺服器池 FQDN   |池 IP 位址   |中繼伺服器角色是選擇性的。 您可以將中繼伺服器提供的服務與前端伺服器或池共同定位。 請參閱[在中繼伺服器池上使用 DNS 負載平衡](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |中繼伺服器 FQDN   |伺服器 IP 位址   |您可以將中繼伺服器提供的服務與前端伺服器或池共同定位。 請參閱[在中繼伺服器池上使用 DNS 負載平衡](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |持續聊天伺服器 FQDN   |持續聊天伺服器 IP 位址   |持續聊天功能需要持久的聊天伺服器, 否則是選擇性的。   ||
|A/AAAA   |lyncdiscoverinternal.* \<sipdomain\>* <br/> lyncdiscoverinternal.* <span> </span>contoso<span> </span>*   |HLB 前部端池 VIP 或控制器 IP  <br/>  192.168.21.121  |內部自動探索 Service1, 行動支援所需。 如果內部 DNS 是用來解析行動裝置, 它應該指向 [外部 IP] 或 [DMZ VIP]。  <br/> 針對 Web 服務, 我們需要 HLB 在前端池中, 因為 HTTPS 無法利用 DNS。 對於前端池或控制器池, 這應該解析為 HLB VIP, 或是標準版伺服器或獨立控制器伺服器的一般 IP。   |是   |
|CNAME   |lyncdiscoverinternal.* \<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>contoso<span> </span>*   |HLB FE 池 FQDN 或控制器 FQDN  <br/> Web int<span></span><span></span>.com   |內部自動探索 Service1 <br/> 如有需要, 您可以將此實現為 CNAME, 而不是 A 記錄。   ||
|A/AAAA   |呼吸.* \<sipdomain\>* <br/> 呼吸.* <span> </span>contoso<span> </span>*  |前端池伺服器 IP 位址 (或每個控制器 IP 位址)  <br/>  DNS LB to *192.168.21.122 192.168.21.123 192.168.21.124*   |自動設定所需, 請參閱[商務用 Skype 用戶端尋找服務的逐步](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)解說 <br/> 在用戶端是外部的記錄或記錄, 指向內部網路上的前端池伺服器或控制器伺服器, 或存取邊緣服務   |&#x2777;  |
|A/AAAA   |ucupdates-r2。* \<sipdomain\>* <br/> ucupdates-r2。* <span> </span>contoso<span> </span>*  |HLB FE Pool VIP 或主管池 HLB VIP 或 SE/控制器伺服器 IP  <br/>  192.168.21.121  |部署此記錄是選擇性的 &#x2778;  ||
|DNS-SRV   |\_sipinternaltls.\_tcp。* \<sipdomain\> * <br/>埠5061 <br/>\_sipinternaltls.\_tcp。* <span> </span>contoso<span> </span> * <br/>埠5061  |前端池 FQDN  <br/>*FE-池子。<span> </span>contoso<span> </span>*  |允許內部使用者自動登入1到前端伺服器/池或 SE 伺服器/池, 以驗證並重新導向客戶登入的要求。  |&#x2777; |
|A/AAAA |sipinternal.* \<sipdomain\>* <br/>sipinternal.<span></span> *contoso<span> </span> *  |前端池 FQDN  <br/>_FE-池子。<span> </span>contoso<span> </span>_  |內部使用者存取 &#x2776;  |&#x2777;  |
|DNS-SRV   | \_ntp.\_udp。* \<sipdomain\> * <br/> \_ntp.\_udp。<span></span> *contoso<span> </span> *  |TimeServer FQDN  <br/> north-america.pool.ntp.org   |Lync Phone Edition 裝置所需的 NTP 來源   |這是支援桌面手機所需的功能。   |
|DNS-SRV   |\_sipfederationtls.\_tcp。* \<sipdomain\> * <br/>\_sipfederationtls.\_tcp。<span></span> *contoso<span> </span> *  | 存取邊緣服務 FQDN <br/> EdgePool-int<span></span>*<span></span>. .com*  |針對有 IOS 或 Windows phone 行動用戶端的每個 SIP 網域, 建立一個 SRV 記錄。   |行動用戶端支援   |
|A/AAAA   |管理 URL  <br/>*Web int<span></span><span></span>.com*  |HLB FE 池子 VIP  <br/> 192.168.21.121   |商務用 Skype Server 的 [控制台], 請參閱[簡易 url](dns.md#BK_Simple)  ||
|A/AAAA   |[認識 URL]  <br/>*Web int<span></span><span></span>.com*  |HLB FE 池子 VIP  <br/> 192.168.21.121   |線上會議, 請參閱[簡易 url](dns.md#BK_Simple)  ||
|A/AAAA   |電話撥入式 URL  <br/>*Web int<span></span><span></span>.com*  |HLB FE 池子 VIP  <br/> 192.168.21.121   |電話撥入式會議, 請參閱[簡易 url](dns.md#BK_Simple)  ||
|A/AAAA   |內部 Web 服務 FQDN  <br/>*Web int<span></span><span></span>.com*  |HLB FE 池子 VIP  <br/> 192.168.21.121   |商務用 Skype Web App 所使用的商務用 skype Web 服務   ||
|A/AAAA   |Office Web Apps 伺服器池 FQDN  <br/> OWA.<span> </span>contoso<span> </span>   | Office Web Apps 伺服器池 VIP 位址 <br/> 192.168.1.5   |定義 Office Web Apps 伺服器池 FQDN   ||
|A/AAAA   | 內部網站 FQDN <br/> Web int<span></span><span></span>.com   | 前臺端池 VIP 位址 <br/> 192.168.21.121   |定義商務用 Skype Web App 所使用的內部網頁 FQDN  <br/> 如果您使用的是此 pool 的 DNS 負載平衡, 您的前臺池和內部網路集群伺服器不能有相同的 FQDN。   ||

用戶端用來探索前端伺服器或前端池的 &#x2776;, 並以使用者身分驗證並登入。 更多關於此操作的詳細資料, 請在[商務用 Skype 用戶端尋找服務的逐步](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)解說中。

&#x2777; 只有在 Lync 2013 和桌面手機之前支援舊版用戶端, 才需要這麼做。

&#x2778; 在已開啟整合通訊裝置, 但使用者從未登入裝置的情況下, A 記錄可讓裝置探索託管裝置更新 Web 服務的伺服器, 並取得更新。 否則, 在使用者第一次登入時, 裝置會透過頻帶內的設定來取得伺服器資訊。

下圖顯示包含內部和外部 DNS 記錄的範例, 以及周圍表格中顯示的許多記錄:

**使用公用 IPv4 位址的邊緣網狀圖**

![DNS network 圖表範例](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**周邊網路 DNS 對應 (內部和外部介面)**

|記錄類型|值|解析為|特殊|必要|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |內部邊緣池 FQDN  <br/>*EdgePool-int<span></span><span></span>. .com*  |內部方邊緣池 IP 位址  <br/> 172.25.33.10, 172.25.33.11   |整合的邊緣池內部介面 IP 位址   |是   |
|A/AAAA   |Edge 伺服器 FQDN  <br/>*缺點-1。<span> </span>contoso<span> </span>*  |邊緣池中伺服器的內部方伺服器 IP  <br/> 172.25.33.10   |針對池中的每個伺服器建立記錄, 並將伺服器 FQDN 指向其在池中的內部伺服器節點 IP, 請參閱[Edge 伺服器池中的 DNS 負載平衡](load-balancing.md#BK_Edge)。   |是   |
|A/AAAA   |存取邊緣服務池 FQDN  <br/>*Access1.<span> </span>contoso<span> </span>*  |Access Edge 服務池外部 IP 位址  <br/> 131.107.16.10, 131.107.16.11   |Access Edge 服務為輸出與輸入會話初始通訊協定 (SIP) 流量提供單一、受信任的連接點。   |是   |
|A/AAAA   |網路會議 Edge 服務池 FQDN  <br/>*Webcon1.<span> </span>contoso<span> </span>*  |網路會議 Edge 服務外部 IP 位址  <br/> 131.107.16.90, 131.107.16.91   |網路會議 Edge 服務可讓外部使用者加入託管在內部商務用 Skype Server 環境中的會議。   |是   |
|A/AAAA   |*av.\<sip-網域\> *池 FQDN <br/>*AV1.<span> </span>contoso<span> </span>*  |A/V 邊緣的外部 IP 位址  <br/> 131.107.16.170, 131.107.16.171   |A/V 邊緣服務可讓外部使用者使用音訊、影片、應用程式共用和檔案傳輸。   |是   |
|CNAME   |呼吸.* \<sipdomain\>* <br/> 呼吸.* <span> </span>contoso<span> </span>*  |外部存取邊緣池 FQDN  <br/>*Access1.<span> </span>contoso<span> </span>*  |尋找邊緣伺服器池。 請參閱[商務用 Skype 用戶端尋找服務的逐步](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)解說  |是   |
|DNS-SRV   |\_呼吸.\_tls。* \<sipdomain\> * <br/>\_呼吸.\_tls。<span></span> *contoso<span> </span> *  |外部存取邊緣 FQDN  <br/>_Access1.<span> </span>contoso<span> </span>_  |用於外部使用者存取。 請參閱[商務用 Skype 用戶端尋找服務的逐步](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)解說  |是   |
|DNS-SRV   |\_sipfederationtls.\_tcp。* \<sipdomain\> * <br/>\_sipfederationtls.\_tcp。<span></span> *contoso<span> </span> *  |外部存取邊緣 FQDN  <br/>*Access1.<span> </span>contoso<span> </span>*  |用於同盟與公用 IM 連線   |&#x2776;  |
|DNS-SRV   |\_xmpp-伺服器。\_tcp。*<sipdomain\> * <br/>\_xmpp-伺服器。\_tcp。* <span> </span>contoso<span> </span> *  |外部存取邊緣 FQDN  <br/>*Access1.<span> </span>contoso<span> </span>*  |XMPP Proxy 服務在已設定的 XMPP 聯盟夥伴中, 接受並傳送可擴展的訊息和目前狀態通訊協定 (XMPP) 訊息。   |Y, 若要部署同盟, 請選用其他選項  <br/> 在商務用 Skype Server 2019 中無法使用。|
|DNS-SRV   |\_sipfederationtls.\_tcp。* \<sipdomain\> * <br/>\_sipfederationtls.\_tcp。* <span> </span>contoso<span> </span> *  |外部存取邊緣 FQDN  <br/>*Access1.<span> </span>contoso<span> </span>*  |若要支援推播通知服務和 Apple 推播通知服務, 您可以為每個 SIP 網域建立一個 SRV 記錄。 &#x2778;  ||
|A/AAAA   |外部前端池 web 服務 FQDN  <br/>*網站-ext<span></span><span></span>. .com*  |反向 proxy 公用 IP 位址、代理至外部 Web 服務 VIP 的代理 &#x2776; <br/> 131.107.155.1 proxy 至192.168.21.120   |商務用 Skype Web App 使用的前端池外部介面   |是   |
|A/AAAA/CNAME   |lyncdiscover.* \<sipdomain\>* <br/> lyncdiscover.* <span> </span>contoso<span> </span>*  |反向 proxy 公用 IP 位址、解析您的主管池的外部 Web 服務 VIP (如果有的話), 如果您沒有控制器 &#x2777; <br/> 131.107.155.1 proxy 至192.168.21.120   | 用戶端自動探索的外部記錄, 也可由行動性、商務用 Skype Web App 以及排程器 Web 應用程式 (由反向 proxy 伺服器解決) 來解析 <br/> 若要支援推播通知服務和 Apple 推播通知服務, 您可以為擁有 Microsoft Lync 行動用戶端的每個 SIP 網域建立一個 SRV 記錄。 3  |是   |
|A/AAAA   |符合.* \<sipdomain\>* <br/> 符合.* <span> </span>contoso<span> </span>*  |反向 proxy 公用 IP 位址, 解析為前端池的外部網頁介面  <br/> 131.107.155.1 proxy 至192.168.21.120   |Proxy 到商務用 Skype Web 服務  <br/> 請參閱[簡易 url](dns.md#BK_Simple)  |是   |
|A/AAAA   |[撥入]*\<sipdomain\>* <br/> * <span> </span>contoso<span></span>. .com*  |[反向 proxy 公用 IP 位址]、[外部網頁介面] 的 [代理程式] 到 [前端] 池  <br/> 131.107.155.1 proxy 至192.168.21.120   |Proxy 到商務用 Skype Web 服務  <br/> 請參閱[簡易 url](dns.md#BK_Simple)  |是   |
|A/AAAA   |Office Web Apps 伺服器池 FQDN  <br/> OWA.<span> </span>contoso<span> </span>   | [反向 proxy 公用 IP 位址]、[Office Web Apps] 伺服器外部網頁介面的代理 <br/> 131.107.155.1 proxy 至192.168.1。5   | Office Web Apps 伺服器池 VIP 位址 <br/> 192.168.1.5   |定義 Office Web Apps 伺服器池 FQDN   |

若要部署同盟, 請 &#x2776; 必要, 否則請選用其他選項。

用戶端用來探索前端伺服器或前端池的 &#x2777;, 並以使用者身分驗證並登入。

&#x2778; 這個需求只適用于 Apple 或 Microsoft 的行動裝置上的用戶端。 Android 和 Nokia Symbian 裝置不使用推播通知。

 如需邊緣伺服器與周邊網路的詳細資訊, 請參閱 Edge 伺服器[DNS 規劃](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan)內容。

> [!IMPORTANT]
> 商務用 Skype 伺服器支援 IPv6 定址的使用。 如需詳細資訊, 請參閱[在商務用 Skype 中規劃 IPv6](ipv6.md) 。

> [!IMPORTANT]
> 如需 Fqdn 的詳細資訊, 請參閱[DNS 基本概念](basics.md)。

**分割大腦 DNS** 
 <a name="BK_split"></a>

分割大腦 DNS 是一種 DNS 配置, 您可以在其中有兩個具有相同命名空間的 DNS 區域。 第一個 DNS 區域會處理內部要求, 而第二個 DNS 區域會處理外部要求, 如這些表格所述。 如需更多相關資訊, 請參閱[分割大腦 DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)。

## <a name="hybrid-considerations"></a>混合式考慮
<a name="BK_Hybrid"> </a>

如果您打算讓一些使用者駐留在線上, 且有一些駐留在內部部署, 請參閱混合式連接規劃一文[商務用 Skype server 2019](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)。 您將需要針對商務用 Skype Server 2015 將 DNS 設定為 normal, 同時也會新增額外的 DNS 記錄。

您也應該參閱「Office 365 Url 與 IP 位址範圍」 [https://aka.ms/o365ips](https://aka.ms/o365ips) , 確認您的使用者能夠存取他們所需的線上資源。

## <a name="simple-urls"></a>簡單 URL
<a name="BK_Simple"> </a>

統一資源定位器 (URL) 是對網路資源的參照, 可在電腦網路上指定其位置, 以及用來進行檢索的通訊協定。

商務用 Skype 伺服器支援使用三個「簡單」 Url 來存取服務:

- [**開會**] 是用來做為網站中所有會議的基本 URL。 [符合簡單 URL] 的範例為 HTTPs:<span></span>//<span></span>[開會]。<span> </span>contoso<span></span>。 特定會議的 URL 可能是 HTTPs:<span></span>//<span></span>[開會]。<span> </span>contoso<span></span>/_username_/7322994。

    使用 [符合簡單的 URL], 加入會議的連結就很容易理解且易於溝通。

- [**撥**入] 可讓您存取 [電話撥入式會議] 設定網頁。 此頁面會以其可用語言、指派的會議資訊 (也就是不需要排程的會議) 及會議中的 DTMF 控制來顯示會議撥入號碼, 並支援個人身分識別號碼的管理 (PIN) 及指派的會議資訊。 [撥入] 簡單 URL 包含在所有會議邀請中, 讓想要撥入會議的使用者可以存取必要的電話號碼和 PIN 資訊。 撥入式簡單 URL 的範例是 HTTPs://<span></span>撥入。<span> </span>contoso<span></span>。

- [系統**管理**] 可讓您快速存取商務用 Skype Server 的 [控制台]。 從組織防火牆內的任何電腦, 管理員都可以在瀏覽器中輸入 [管理員] 簡單 URL, 以開啟商務用 Skype Server 的 [控制台]。 系統管理員簡易 URL 是貴組織的內部。 [管理員] 簡單 URL 的範例是 HTTPs://<span></span>[管理員]。<span> </span>contoso<span></span>。

在[商務用 Skype Server 的簡單 url 的 DNS 需求](simple-urls.md)中, 會深入討論簡單的 url。

## <a name="dns-by-server-role"></a>DNS (依伺服器角色)
<a name="BK_Servers"> </a>

您可以視需要設定這些池和伺服器的名稱, 但讓它們更容易記憶並反映其在系統中的功能。

### <a name="dns-records-for-individual-servers-or-pools"></a>個別伺服器或池的 DNS 記錄

這些一般記錄需求適用于商務用 Skype 所使用的任何伺服器角色。 「池」是一組伺服器, 可執行相同的服務, 共同處理透過負載平衡器導向給它們的用戶端要求。 如需詳細資訊, 請參閱[商務用 Skype 的負載平衡需求](load-balancing.md)

**伺服器/池角色的 DNS 記錄需求 (假設 DNS 負載平衡)**

|部署案例|DNS 需求|
|:-----|:-----|
|一台伺服器:  <br/> 持續聊天、控制器、中繼伺服器、前端伺服器   |將伺服器的完整功能變數名稱 (FQDN) 解析成其 IP 位址的內部 A 記錄。  <br/> ServerRole.<span> </span>contoso<span></span>10.10.10。0   |
|共  <br/> 持續聊天、控制器、邊緣伺服器、中繼伺服器、前端   |內部 A 記錄, 可將池中每個伺服器節點的完整功能變數名稱 (FQDN) 解析為它的 IP 位址。  <br/>**範例** <br/> ServerRole01.<span> </span>contoso<span></span>(.com) 10.10.10。1  <br/> ServerRole02.<span> </span>contoso<span></span>10.10.10。2  <br/> 多個內部 A 記錄, 可將池的完整功能變數名稱 (FQDN) 解析為池中伺服器節點的 IP 位址。  <br/>**範例** <br/> ServerPool.<span> </span>contoso<span></span>(.com) 10.10.10。1  <br/> ServerPool.<span> </span>contoso<span></span>10.10.10。2   |

### <a name="edge-server-specific-dns-topics"></a>邊緣伺服器的特定 DNS 主題

 若要規劃 edge 伺服器部署, 請[在商務用 Skype server 2015 中查看 Edge 伺服器部署的規劃](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md), 以及[針對商務用 skype Server 2015 的高級邊緣伺服器 DNS 規劃](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md)(含下列各節)

- [DNS 災害復原](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [DNS 負載平衡](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [不含分裂的 DNS 的自動設定](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [分割大腦 DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [商務用 Skype 用戶端尋找服務的逐步解說](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)


