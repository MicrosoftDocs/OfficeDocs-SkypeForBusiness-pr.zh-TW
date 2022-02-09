---
title: 商務用 Skype Server 的 DNS 需求
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: 摘要：在實施商務用 Skype Server 之前，請先複查本主題中的 DNS 考慮。
ms.openlocfilehash: 7637a1842c9ebc96eee95aa9e4fac6d3db376240
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62400257"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>商務用 Skype Server 的 DNS 需求

**總結：** 在執行商務用 Skype Server 之前，請先複查本主題中的 DNS 考慮。

本文只討論群組織內部部署網路上的商務用 Skype Server 部署的 DNS 規劃。 如商務用 Skype 線上，請參閱的「Office 365 URLs 和 IP 位址範圍 [https://aka.ms/o365ips](/microsoft-365/enterprise/urls-and-ip-address-ranges) 」。

 (DNS) 伺服器的功能變數名稱服務會對應至 www 等主機名稱 (。 <span></span>contoso <span></span> .com （大概是網頁伺服器) 的 IP 位址 (如 10.10.10.10) ）。 它可協助用戶端和相互關聯的伺服器在網路上彼此通訊。 當您設定商務用 Skype Server 2015 的實施時，您必須確定新伺服器名稱的對應 (通常會反映其所要採取的角色，) 與所指派的 IP 位址相符。

雖然這種方式最初似乎有點令人望而生畏，但使用[商務用 Skype Server 2015 規劃工具](https://www.microsoft.com/download/details.aspx?id=50357)進行規劃是非常繁重的做法。 當您已完成您計畫使用哪些功能的嚮導問題後，針對您所定義的每個網站，您可以在 Edge 管理報告中查看 DNS 報告，並使用這裡所列的資訊來建立您的 DNS 記錄。 您也可以調整所使用的許多名稱及 IP 位址，如需詳細資訊，請參閱 [複查 DNS 報告](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report)。 請記住，您可以將 Edge 系統管理員報告匯出為 Excel 試算表，而且 DNS 報告會是檔案中的其中一個工作表。 雖然此工具組括[商務用 Skype Server 2019 中已被取代的](../../../SfBServer2019/deprecated.md)功能，但如果未選取這些功能，仍然可以用來建立初始計畫。

當您安裝新的實施時，如[建立商務用 Skype Server 的 DNS 記錄](../../deploy/install/create-dns-records.md)及建立商務用 Skype Server 的拓撲所述），我們意識到您可以選擇使用內建的 dns 功能 Windows Server 2016 或是協力廠商的 DNS 套件，所以我們會將討論保留在本文中，而不是具體。 我們會詳細說明所需的專案，以及您應如何符合此需求。

經驗商務用 Skype、Lync 及 Office 通訊套件管理員可能會發現下清單格很有用。 如果資料表令您困惑，後續章節或文章將會 shed 下列概念：

## <a name="summary-tables"></a>摘要表格
<a name="BK_Summary"> </a>

下表顯示商務用 Skype Server 用來為使用者提供服務的 DNS 記錄。 有些選項是選用的，因為它們只是支援某些功能，而且不需要這些功能時，可以略過這些功能。 僅限內部存取所需的 DNS 記錄位於第一個表格中，且允許內部及外部存取的部署需要兩個數據表中的記錄。

**內部 DNS 對應**

|記錄類型|值|解析為|用途|必要|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |前端集區 FQDN  <br/> *FE 集區。 <span></span>contoso <span></span>*   |前端集區伺服器 IP 位址  <br/>  DNS LB to *192.168.21.122 192.168.21.123 192.168.21.124*   |前端集區的 DNS 負載平衡。 將前端集區名稱地圖至一組 IP 位址。  <br/> 請參閱 [在前端集區和 Director 集區上部署 DNS 負載平衡](load-balancing.md#BK_FE_Dir)  |Y   |
|A/AAAA   | 集區中的每一部前端伺服器或 Standard Edition 伺服器的 FQDN，或獨立伺服器的 FQDN <br/>  *FE01。 <span></span>contoso。 <span></span>com FE02。 <span></span>contoso <span></span> .COM FE03。 <span></span>contoso <span></span>*   |每個伺服器對應的 IP  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |將伺服器名稱地圖至它的 IP 位址。   |Y   |
|A/AAAA   |Enterprise 集區內部 Web 服務覆寫 FQDN  <br/> *Web int。 <span></span>contoso <span></span>*   |前端伺服器內部 Web 服務的 HLB VIP  <br/> *192.168.21.120*   |必須啟用用戶端伺服器的 web 流量，例如下載商務用 Skype Web 應用程式。 行動用戶端也是必要的。   |Y   |
|A/AAAA   |Enterprise 集區外部 Web 服務覆寫 FQDN  <br/> *網頁分機 <span></span>contoso <span></span>*   |前端伺服器外部 Web 服務的 HLB VIP  <br/>*68.123.56.90*   |必須啟用用戶端伺服器的 web 流量，例如下載商務用 Skype Web 應用程式。 若行動用戶端會內部解析 DNS，則為必要。 可以解析成 DMZ 反向 Proxy IP 或網際網路 IP。   ||
|A/AAAA   | 後端伺服器 SQL 伺服器 FQDN <br/> *SQL1。 <span></span>contoso <span></span>*   |伺服器 IP 位址  <br/> *192.168.11.90*   |地圖使用前端集區至其 IP 位址的後端 SQL 伺服器的伺服器名稱   ||
|A/AAAA   |後端伺服器鏡像 SQL 伺服器 FQDN  <br/> *SQL2。 <span></span>contoso <span></span>*   |伺服器 IP 位址  <br/> *192.168.11.91*   |地圖使用前端集區的後端 SQL 鏡像伺服器的伺服器名稱至其 IP 位址   ||
|A/AAAA   |Director 集區 FQDN  <br/>**注意：** 使用獨立 Director 伺服器時不適用 <br/> *DirPool。 <span></span>contoso <span></span>*   |Director 集區 IP 位址  <br/> DNS LB to *192.168.21.132，192.168.21.133，192.168.21.134*   |Director 集區伺服器的 DNS 負載平衡。 地圖 Director 集區的集區名稱至 IP 位址，請參閱[在前端集區和 Director 集區上部署 DNS 負載平衡](load-balancing.md#BK_FE_Dir) <br/> Director 可驗證使用者，且是選用的。   ||
|A/AAAA   |Director FQDN   |每個 Director 伺服器的伺服器 IP 位址   |地圖 Director 的集區名稱至 IP 位址，請參閱[在前端集區和 Director 集區上部署 DNS 負載平衡](load-balancing.md#BK_FE_Dir)  ||
|A/AAAA   |轉送伺服器集區 FQDN   |集區 IP 位址   |轉送伺服器角色是選用的。 您可以在前端伺服器或集區中，相互找到轉送伺服器所提供的服務。 請參閱在轉送伺服器集區 [上使用 DNS 負載平衡](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |轉送伺服器 FQDN   |伺服器 IP 位址   |您可以在前端伺服器或集區中，相互找到轉送伺服器所提供的服務。 請參閱在轉送伺服器集區 [上使用 DNS 負載平衡](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |Persistent Chat Server FQDN   |Persistent Chat Server IP 位址   |Persistent chat server 對 Persistent Chat 功能是必要的，另外也是選用的。   ||
|A/AAAA   |lyncdiscoverinternal.*\<sipdomain\>* <br/> lyncdiscoverinternal.*<span></span> contoso <span></span>*   |HLB 前端集區 VIP 或 Director IP  <br/>  192.168.21.121  |行動支援所需的內部 AutoDiscover Service1。 若內部 DNS 是用來解析行動裝置，則應該指向外部 IP 或 DMZ VIP。  <br/> 針對 Web 服務，我們需要前端集區上的 HLB，因為 HTTPS 無法利用 DNS。 對於前端集區或 Director 集區，這應該會解析為 HLB VIP，或是 Standard edition server 或獨立 Director 伺服器的一般 IP。   |Y   |
|CNAME   |lyncdiscoverinternal.*\<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>contoso <span></span>*   |HLB FE 集區 FQDN 或 Director FQDN  <br/> Web int。 <span></span>contoso <span></span>   |內部 AutoDiscover Service1 <br/> 您可以將這種方式當作 CNAME 來執行，而不是像是必要的 A 記錄。   ||
|A/AAAA   |Sip。*\<sipdomain\>* <br/> Sip。*<span></span> contoso <span></span>*  |前端集區伺服器的 IP 位址 (或每個 Director IP 位址)   <br/>  DNS LB to *192.168.21.122 192.168.21.123 192.168.21.124*   |[！注意事項] 如需自動設定，請參閱[商務用 Skype 用戶端尋找服務的逐步](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)解說 <br/> 在用戶端為外部用戶端時，指向內部網路上的前端集區伺服器或 Director 伺服器的記錄或記錄，或 Access Edge service。   |&#x2777;  |
|A/AAAA   |ucupdates-r2-r2。*\<sipdomain\>* <br/> ucupdates-r2-r2。*<span></span> contoso <span></span>*  |HLB FE 集區 VIP 或 Director 集區 HLB VIP，或 SE/Director Server IP  <br/>  192.168.21.121  |部署此記錄是選用的 &#x2778;  ||
|SRV   |\_sipinternaltls。 \_Tcp。*\<sipdomain\>* <br/>埠5061 <br/>\_sipinternaltls。 \_Tcp。*<span></span> contoso <span></span>* <br/>埠5061  |前端集區 FQDN  <br/>*FE 集區。 <span></span>contoso <span></span>*  |讓內部使用者自動登入1能夠驗證及重新導向登入的用戶端要求的前端伺服器/集區或 SE 伺服器/集區。  |&#x2777; |
|A/AAAA |sipinternal.*\<sipdomain\>* <br/>sipinternal。 <span></span>*contoso <span></span>*  |前端集區 FQDN  <br/>_FE 集區。 <span></span>contoso <span></span>_  |內部使用者存取 &#x2776;  |&#x2777;  |
|SRV   | \_Ntp。 \_Udp。*\<sipdomain\>* <br/> \_Ntp。 \_Udp。 <span></span>*contoso <span></span>*  |TimeServer FQDN  <br/> north-america.pool.ntp.org   |Lync 電話 Edition 裝置所需的 NTP 來源   |這是支援 desktop 電話機所需的功能。   |
|SRV   |\_sipfederationtls。 \_Tcp。*\<sipdomain\>* <br/>\_sipfederationtls。 \_Tcp。 <span></span>*contoso <span></span>*  | Access Edge service FQDN <br/> EdgePool-int。 <span></span>*contoso <span></span>*  |針對每個具有 IOS 或 Windows 電話行動用戶端的 SIP 網域，建立一個 SRV 記錄。   |行動用戶端支援   |
|A/AAAA   |管理 URL  <br/>*Web int。 <span></span>contoso <span></span>*  |HLB FE 集區 VIP  <br/> 192.168.21.121   |商務用 Skype Server 控制台，請參閱[簡易 URLs](dns.md#BK_Simple)  ||
|A/AAAA   |符合 URL  <br/>*Web int。 <span></span>contoso <span></span>*  |HLB FE 集區 VIP  <br/> 192.168.21.121   |線上會議，請參閱 [簡易 URLs](dns.md#BK_Simple)  ||
|A/AAAA   |撥入 URL  <br/>*Web int。 <span></span>contoso <span></span>*  |HLB FE 集區 VIP  <br/> 192.168.21.121   |電話撥入式會議，請參閱 [簡易 URLs](dns.md#BK_Simple)  ||
|A/AAAA   |內部 Web 服務 FQDN  <br/>*Web int。 <span></span>contoso <span></span>*  |HLB FE 集區 VIP  <br/> 192.168.21.121   |商務用 Skype Web 應用程式所用的商務用 Skype Web 服務   ||
|A/AAAA   |Office Web Apps Server 集區 FQDN  <br/> OWA。 <span></span>contoso <span></span>   | Office Web Apps Server 集區 VIP 位址 <br/> 192.168.1.5   |定義 Office Web Apps Server 集區 FQDN   ||
|A/AAAA   | 內部 Web FQDN <br/> Web int。 <span></span>contoso <span></span>   | 前端集區 VIP 位址 <br/> 192.168.21.121   |定義商務用 Skype Web 應用程式所使用的內部 Web FQDN  <br/> 如果您是在此集區上使用 DNS 負載平衡，您的前端集區和內部網頁伺服器陣列不能有相同的 FQDN。   ||

用戶端使用 &#x2776; 來探索前端伺服器或前端集區，並以使用者身分驗證和登入。 有關這方面的詳細資訊，請[商務用 Skype 用戶端尋找服務的逐步](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)解說。

&#x2777; 這只需要在 Lync 2013 和桌面手持之前支援舊版用戶端。

&#x2778; 在已開啟整合通訊裝置，但使用者從未登入裝置的情況下，A 記錄可讓裝置探索主控裝置更新 Web 服務的伺服器，並取得更新。 否則，裝置會透過使用者首次登入時的頻內佈建取得伺服器資訊。

下圖顯示一個範例，其中包括內部和外部 DNS 記錄，以及周圍表格中所顯示的許多記錄：

**使用公用 IPv4 位址的 Edge network 圖表**

![DNS network 圖表的範例。](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**內部和外部介面 (周邊網路 DNS 對應)**

|記錄類型|值|解析為|用途|必要|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |內部 Edge 集區 FQDN  <br/>*EdgePool-int。 <span></span>contoso <span></span>*  |內部面向的 Edge 集區 IP 位址  <br/> 172.25.33.10, 172.25.33.11   |合併的 Edge 集區內部介面 IP 位址   |Y   |
|A/AAAA   |Edge Server FQDN  <br/>*缺點-1。 <span></span>contoso <span></span>*  |Edge 集區中的伺服器內部對向伺服器 IP  <br/> 172.25.33.10   |針對集區中的每一部伺服器建立記錄，並將伺服器 FQDN 指向其在集區中的內部伺服器節點 IP，請參閱 [Edge Server pool 上的 DNS 負載平衡](load-balancing.md#BK_Edge)。   |Y   |
|A/AAAA   |Access Edge service 集區 FQDN  <br/>*Access1。 <span></span>contoso <span></span>*  |Access Edge service 集區的外部 IP 位址  <br/> 131.107.16.10, 131.107.16.11   |Access Edge Service 能同時為輸出及輸入的工作階段初始通訊協定 (SIP) 流量提供單一、受信任的連線點。   |Y   |
|A/AAAA   |Web 會議 Edge service 集區 FQDN  <br/>*Webcon1。 <span></span>contoso <span></span>*  |Web 會議 Edge service 外部 IP 位址  <br/> 131.107.16.90, 131.107.16.91   |Web 會議 Edge service 可讓外部使用者加入內部商務用 Skype Server 環境所主控的會議。   |Y   |
|A/AAAA   |*Av。\<sip-domain\>* 集區 FQDN <br/>*AV1。 <span></span>contoso <span></span>*  |A/V Edge 外部 IP 位址  <br/> 131.107.16.170, 131.107.16.171   |A/V Edge service 可讓外部使用者使用音訊、影片、應用程式共用和檔案傳輸功能。   |Y   |
|CNAME   |Sip。*\<sipdomain\>* <br/> Sip。*<span></span> contoso <span></span>*  |外部存取 Edge 集區 FQDN  <br/>*Access1。 <span></span>contoso <span></span>*  |尋找 Edge Server 集區。 請參閱[商務用 Skype 用戶端尋找服務的演練](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_Sip。 \_Tls。*\<sipdomain\>* <br/>\_Sip。 \_Tls。 <span></span>*contoso <span></span>*  |外部存取 Edge FQDN  <br/>_Access1。 <span></span>contoso <span></span>_  |用於外部使用者存取。 請參閱[商務用 Skype 用戶端尋找服務的演練](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_sipfederationtls。 \_Tcp。*\<sipdomain\>* <br/>\_sipfederationtls。 \_Tcp。 <span></span>*contoso <span></span>*  |外部存取 Edge FQDN  <br/>*Access1。 <span></span>contoso <span></span>*  |用於同盟與公用 IM 連線   |&#x2776;  |
|SRV   |\_xmpp-伺服器。 \_Tcp。*<microsoft.rtc.management.xds.sipdomain \>* <br/>\_xmpp-伺服器。 \_Tcp。*<span></span> contoso <span></span>*  |外部存取 Edge FQDN  <br/>*Access1。 <span></span>contoso <span></span>*  |XMPP Proxy 服務會接受及傳送可延伸的訊息和顯示狀態通訊協定 (XMPP) 郵件傳送至及從設定的 XMPP 同盟協力廠商。   |Y，以部署同盟，否則為選用  <br/> 無法在商務用 Skype Server 2019 中使用。|
|SRV   |\_sipfederationtls。 \_Tcp。*\<sipdomain\>* <br/>\_sipfederationtls。 \_Tcp。*<span></span> contoso <span></span>*  |外部存取 Edge FQDN  <br/>*Access1。 <span></span>contoso <span></span>*  |若要支援推播通知服務和 Apple 推播通知服務，您可以為每個 SIP 網域建立一個 SRV 記錄。 &#x2778;  ||
|A/AAAA   |外部前端集區 web 服務 FQDN  <br/>*網頁分機 <span></span>contoso <span></span>*  |反向 proxy 公用 IP 位址、代理至前端集區的外部 Web 服務 VIP &#x2776; <br/> 131.107.155.1 proxy 至192.168.21.120   |商務用 Skype Web 應用程式所使用的前端集區外部介面   |Y   |
|A/AAAA/CNAME   |lyncdiscover.*\<sipdomain\>* <br/> lyncdiscover.*<span></span> contoso <span></span>*  |反向 proxy 公用 IP 位址、解析為 Director 集區的外部 Web 服務 VIP （如果有的話），或如果您沒有 Director &#x2777; 則為前端集區。 <br/> 131.107.155.1 proxy 至192.168.21.120   | 用戶端 AutoDiscover 的外部記錄，也可由反向 proxy 伺服器解析，由行動性、商務用 Skype Web 應用程式及排程器 Web 應用程式所使用 <br/> 若要支援推播通知服務和 Apple Push Notification 服務，您可以為每個具有 Microsoft Lync Mobile 用戶端的 SIP 網域建立一個 SRV 記錄。 3   |Y   |
|A/AAAA   |滿足。*\<sipdomain\>* <br/> 滿足。*<span></span> contoso <span></span>*  |反向 proxy 公用 IP 位址，解析為前端集區的外部 Web 介面  <br/> 131.107.155.1 proxy 至192.168.21.120   |商務用 Skype Web 服務的 Proxy  <br/> 請參閱 [簡易 URLs](dns.md#BK_Simple)  |Y   |
|A/AAAA   |撥入。*\<sipdomain\>* <br/> 撥入。*<span></span> contoso <span></span>*  |反向 proxy 公用 IP 位址，代理到前端集區的外部 Web 介面  <br/> 131.107.155.1 proxy 至192.168.21.120   |商務用 Skype Web 服務的 Proxy  <br/> 請參閱 [簡易 URLs](dns.md#BK_Simple)  |Y   |
|A/AAAA   |Office Web Apps Server 集區 FQDN  <br/> OWA。 <span></span>contoso <span></span>   | 反向 proxy 公用 IP 位址，將 proxy 加入 Office Web Apps Server 的外部 Web 介面 <br/> 131.107.155.1 proxy 至192.168.1。5   | Office Web Apps Server 集區 VIP 位址 <br/> 192.168.1.5   |定義 Office Web Apps Server 集區 FQDN   |

部署同盟所需的 &#x2776;，否則為選用。

用戶端使用 &#x2777; 來探索前端伺服器或前端集區，並以使用者身分驗證和登入。

&#x2778; 此需求只適用于 Apple 或 Microsoft 的行動裝置上的用戶端。 Android 和 Nokia Symbian 裝置不使用推播通知。

 如需邊際伺服器及周邊網路的詳細資訊，請參閱 Edge server [DNS 規劃](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) 內容。

> [!IMPORTANT]
> 商務用 Skype Server 支援使用 IPv6 定址。 如需詳細資訊，請參閱[IPv6 在商務用 Skype 中的計畫](ipv6.md)。

> [!IMPORTANT]
> 如需 Fqdn 的詳細資訊，請參閱 [DNS 基礎](basics.md)。

**分割大腦 DNS** 
<a name="BK_split"></a>

分割的大腦 DNS 是指具有相同命名空間的兩個 DNS 區域的 DNS 設定。 第一個 DNS 區域會處理內部要求，而第二個 DNS 區域會處理外部要求（如這些表格所述）。 如需相關資訊，請參閱 [裂腦 DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)。

## <a name="hybrid-considerations"></a>混合考慮
<a name="BK_Hybrid"> </a>

如果您計畫讓部分使用者位於線上，且某些使用者位於內部部署，請參閱混合式連線規劃文章[商務用 Skype server 2019](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)。 您必須將商務用 Skype Server 2015 的 dns 設定為 normal，也可以新增額外的 dns 記錄。

您也應該參閱「Office 365 URLs 和 IP 位址範圍 [https://aka.ms/o365ips](/microsoft-365/enterprise/urls-and-ip-address-ranges) 」，以確認您的使用者可以存取所需的線上資源。

## <a name="simple-urls"></a>簡單 URL
<a name="BK_Simple"> </a>

統一資源定位器 (URL) 是一種網頁資源參照，可指定其電腦網路上的位置，以及用來進行檢索的通訊協定。

商務用 Skype Server 支援使用三種「簡易」 URLs 存取服務：

- 「**開會**」是用來做為網站中所有會議的基礎 URL。 符合簡易 URL 的範例是 HTTPs： <span></span> // <span></span> 符合。 <span></span>contoso <span></span> 。 特定會議的 URL 可能是 HTTPs： <span></span> // <span></span> 符合。 <span></span>contoso <span></span> .com/_username_/7322994。

    透過「符合簡易 URL」，加入會議的連結很容易理解，而且易於交流。

- **撥入** 功能可讓您存取電話撥入式會議設定網頁。 此頁面會以其可用語言、指派會議資訊 (，也就是針對不需要排程) 的會議，以及在會議 DTMF 中的控制措施，以及支援管理個人識別碼) 的個人 (標識號，以及所指派的會議資訊。 撥入簡易 URL 會包含在所有會議邀請中，讓想要撥入會議的使用者可以存取必要的電話號碼和 PIN 碼資訊。 撥入式簡易 URL 的範例是 HTTPs:// <span></span> 撥入。 <span></span>contoso <span></span> 。

- 系統 **管理員** 可讓您快速存取商務用 Skype Server 控制台。 從組織防火牆內部的任何電腦，管理員都可以在瀏覽器中輸入管理員簡易 URL，以開啟商務用 Skype Server 控制台。 系統管理員簡易 URL 是您組織內部。 管理員簡易 URL 的範例是 HTTPs:// <span></span> admin。 <span></span>contoso <span></span> 。

[商務用 Skype Server 中的簡單 URLs](simple-urls.md)，會更詳細地討論簡單的 URLs。

## <a name="dns-by-server-role"></a>依伺服器角色的 DNS
<a name="BK_Servers"> </a>

您可以視需要設定這些集區和伺服器的名稱，但讓他們記住並反映其在系統中的功能。

### <a name="dns-records-for-individual-servers-or-pools"></a>個別伺服器或集區的 DNS 記錄

這些一般記錄需求適用于商務用 Skype 所使用的任何伺服器角色。 集區是一組執行相同服務的伺服器，這些伺服器會一起運作，以處理透過負載平衡器導向的用戶端要求。 如需詳細資訊，請參閱[商務用 Skype 的負載平衡需求](load-balancing.md)

**伺服器/集區角色的 DNS 記錄需求 (假設 DNS 負載平衡)**

|部署案例|DNS 需求|
|:-----|:-----|
|一部伺服器：  <br/> Persistent Chat、Director、轉送伺服器、前端伺服器   |一筆內部 A 記錄，用來將伺服器的完整網域名稱 (FQDN) 解析為 IP 位址。  <br/> ServerRole。 <span></span>contoso <span></span> .com 10.10.10。0   |
|池：  <br/> Persistent Chat，Director，Edge Server，轉送伺服器，前端   |內部 A 記錄，可將集區中每個伺服器節點的完整功能變數名稱 (FQDN) 解析成其 IP 位址。  <br/>**範例** <br/> ServerRole01。 <span></span>contoso <span></span> .com 的10.10.10。1  <br/> ServerRole02。 <span></span>contoso <span></span> .com 10.10.10。2  <br/> 多重內部 A 記錄，可將集區的完整功能變數名稱 (FQDN) 解析為集區中伺服器節點的 IP 位址。  <br/>**範例** <br/> ServerPool。 <span></span>contoso <span></span> .com 的10.10.10。1  <br/> ServerPool。 <span></span>contoso <span></span> .com 10.10.10。2   |

### <a name="edge-server-specific-dns-topics"></a>Edge Server 特定的 DNS 主題

 若要規劃 edge server 部署，請參閱[商務用 Skype Server 2015 中的 edge server 部署方案](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)，以及具備下列各節[商務用 Skype Server 2015 的高級 edge server DNS 規劃](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md)

- [DNS 災難修復](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [DNS 負載平衡](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [沒有 split-大腦 DNS 的自動設定](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [裂腦 DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [商務用 Skype 用戶端尋找服務的逐步解說](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)