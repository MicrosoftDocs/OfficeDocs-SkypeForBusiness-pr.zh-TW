---
title: 使用直接路由規劃媒體旁路
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: 請閱讀本主題, 以瞭解如何使用手機系統直接路由規劃媒體旁路。
ms.openlocfilehash: 70d0b5ea61d0d7a8001bb1dbfabda2c45274e521
ms.sourcegitcommit: 6cbdcb8606044ad7ab49a4e3c828c2dc3d50fcc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/09/2019
ms.locfileid: "36271443"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>使用直接路由規劃媒體旁路

## <a name="about-media-bypass-with-direct-routing"></a>關於直接路由的媒體旁路

[媒體旁路] 可讓您縮短媒體流量的路徑, 並減少傳輸中的跳躍數, 以獲得更佳的效能。 在媒體旁路的情況下, 媒體會保留在會話邊界控制器 (SBC) 和用戶端之間, 而不是透過 Microsoft Phone 系統傳送。 若要設定媒體旁路, SBC 與用戶端必須位於同一個位置或網路上。

您可以使用**設定 CSOnlinePSTNGateway**命令, 並將 **-MediaBypass**參數設定為 true 或 false, 以控制每個 SBC 的媒體旁路。 如果您啟用 [媒體旁路], 這並不表示所有媒體流量都會留在公司網路內。 本文將說明不同案例中的通話流程。    

下圖說明通話流程中的差異, 以及不使用媒體旁路的情況。

若沒有媒體旁路, 當用戶端撥打或接聽來電時, 在 SBC、Microsoft Phone 系統和團隊用戶端之間的信號與媒體流程, 如下圖所示:

![顯示沒有媒體旁路的信號和媒體流程](media/direct-routing-media-bypass-1.png)


但假設使用者與 SBC 在相同的大樓或 network 中。 例如, 假設在 Frankfurt 中建立的使用者撥打電話給 PSTN 使用者: 

- 如果**沒有媒體旁路**, 媒體會透過阿姆斯特丹或都柏林 (在 Microsoft 資料中心的部署位置), 並回到 Frankfurt 中的 SBC 來流動。 

  之所以選取 [歐洲資料中心], 是因為 SBC 是在歐洲, 而 Microsoft 使用最接近 SBC 的資料中心。 雖然這種方法不會影響通話品質, 因為在大部分地區內的 Microsoft 網路中的流量流程已優化, 但通信量卻有不必要的迴圈。     

- 在**媒體旁路**的情況下, 媒體會直接保留在團隊使用者與 SBC 之間, 如下圖所示:

![顯示使用媒體旁路的信號及媒體流程](media/direct-routing-media-bypass-2.png)

媒體旁路利用在 SBC 上的團隊用戶端和 ICE lite 上稱為互動式連線建立 (ICE) 的通訊協定。 這些通訊協定可讓直接路由使用最直接的媒體路徑來獲得最佳品質。 冰與冰 Lite 是 WebRTC 的標準。 如需這些通訊協定的詳細資訊, 請參閱 RFC 5245。


## <a name="call-flow-and-firewall-planning"></a>通話流程與防火牆規劃

通話流程和防火牆規劃取決於使用者是否能直接存取 SBC 的公用 IP 位址, 以及使用者是否在網路內或外部。

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>如果使用者可以直接存取 SBC 的公用 IP 位址, 就可以進行通話流程

如果使用者可以直接存取 SBC 的公用 IP 位址, 則呼叫流程如下所示:

- 針對媒體旁路, 小組用戶端必須能夠存取 SBC 的公用 IP 位址 (即使是來自內部網路)。 如果不想要直接媒體, 媒體可以透過傳輸中繼流過。

- 當使用者與 SBC 在相同的建築物和/或網路中時, 建議使用這項方案: 從媒體路徑中移除 Microsoft 雲端元件。

- 通知總是透過 Microsoft 雲端傳送流程。

下圖顯示啟用媒體旁路時的通話流程、用戶端為內部, 且用戶端可以取得 SBC 的公用 IP 位址 (直接媒體): 

- 路徑的箭號和數值是依照[Microsoft 團隊通話流程](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)文章。

- SIP 信號總是會採用路徑4和 4 ' (視通信量的方向而定)。 媒體保持在本機, 並採用路徑5b。

![顯示已啟用媒體旁路的通話流程, 用戶端是內部的](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>如果使用者無法存取 SBC 的公用 IP 位址, 通話流程

如果使用者無法存取 SBC 的公用 IP 位址, 下列說明通話流程。 

例如, 假設使用者是外部使用者, 而租使用者系統管理員決定不要將 SBC 的公用 IP 位址開啟至網際網路中的每個人, 但僅限 Microsoft 雲端。 流量的內部元件可以透過團隊傳輸繼電器來流動。 這是商業網路以外的使用者的建議配置。 請考慮下列事項:

- 使用團隊傳輸中繼。

- 針對媒體旁路, Microsoft 使用的傳輸繼電器版本必須在團隊傳輸中繼器與 SBC 之間開啟埠 50 000 至 59 999 (將來我們打算移至只需要3478和3479埠的版本)。

- 針對媒體優化用途, Microsoft 建議您只開啟 SBC 的公用 IP 位址至團隊傳輸中繼。 對於公司網路以外的用戶端, Microsoft 建議使用傳輸中繼, 而不是直接到達 SBC 的公用 IP 位址。

下列圖表顯示在啟用媒體旁路時的通話流程、用戶端為外部, 且用戶端無法取得會話邊界控制器的公用 IP 位址 (媒體是由小組傳輸轉接傳送來中繼)。

- 路徑的箭號和數值是依照[Microsoft 團隊通話流程](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)文章。

- 媒體是透過路徑3、3 '、4和4」進行中繼

![顯示使用者無法存取 SBC 公用 IP 的通話流程](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>如果使用者在網路以外且能存取 SBC 的公用 IP, 通話流程

> [!NOTE]
> 這不是建議的設定, 因為它不會利用團隊傳輸繼電器。 相反地, 您應該考慮先前的情況, 即使用者無法存取 SBC 的公用 IP 位址。 

下圖顯示啟用媒體旁路時的通話流程、用戶端為外部, 且用戶端可以取得 SBC (直接媒體) 的公用 IP 位址。

- 路徑的箭號和數值是依照[Microsoft 團隊通話流程](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)文章。

- SIP 信號通常會採用路徑3和 3 ' (視流量方向而定)。 媒體流程使用路徑2。

![顯示使用者無法存取 SBC 公用 IP 的通話流程](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a>媒體處理器與傳輸繼電器的用途

Microsoft 雲端中有兩個元件可位於媒體流量的路徑: 媒體處理器和傳輸中繼。 

- 媒體處理器是一個公開的元件, 可在非旁路情況下處理媒體, 並處理語音應用程式的媒體。

   媒體處理器一直在最終使用者未繞過呼叫的路徑中, 但不會在回避通話的路徑中。 媒體處理器總是位於所有語音應用程式的路徑中, 例如通話寄存、組織自動語音應答及通話佇列。

- 傳輸中繼是用來連線到最接近的傳輸服務, 以傳送即時流量。

   傳輸繼電器可能是或不在繞過通話的路徑中, 也可能不是來源於或發給最終使用者--視使用者的位置和網路的設定方式而定。

下圖顯示兩個通話流程: 一個啟用「媒體旁路」, 而另一個停用媒體旁路的情況。 注意: 圖表只會說明源自--或發至端使用者的流量。  
- 媒體控制器是 Azure 中的 microservice, 可指派媒體處理器並建立會話描述通訊協定 (SDP) 提供的功能。

- SIP Proxy 是一個元件, 可將小組中使用的 HTTP REST 信號轉譯成 SIP。    

![顯示已啟用及停用媒體旁路的通話流程](media/direct-routing-media-bypass-6.png)


下表摘要列出媒體處理器與傳輸中繼之間的差異。

|    | 媒體處理器 | 傳輸繼電器|
| :--------------|:---------------|:------------|
在媒體路徑中, 讓使用者無法避開來電 | 總會 | 任何 | 
在媒體路徑中, 讓使用者略過來電 | 任何 | 如果用戶端無法在公用 IP 位址上到達 SBC | 
在語音應用程式的媒體路徑中 | 總會 | 任何 | 
可以執行轉碼 (B2BUA)\* | 是的 | 否, 只在端點之間中繼音訊 | 
全球和位置的實例數 | 總共8個: 美國東和西部為2。在阿姆斯特丹和都柏林中為 2,2在香港與新加坡中;日本中的 2 (在 Q1CY2019 中新增)  | 條

IP 範圍是 52.112.0.0/14 (從52.112.0.1 到52.115.255.254 的 IP 位址)。 

\*轉碼說明: 

- 媒體處理常式是 B2BUA, 這表示它可以變更編解碼器 (例如, 從 [團隊用戶端] 到 [MP] 和 [在 MP 與 SBC 之間 711] 的絞絲)。

- 傳輸中繼並非 B2BUA, 這表示在用戶端與 SBC 之間不會變更編解碼器, 即使流量透過中繼流程也一樣。

### <a name="use-of-teams-transport-relays-in-escalation-scenarios-if-trunk-is-configured-for-media-bypass"></a>如果已針對媒體旁路設定幹線, 在問題上報案例中使用團隊傳輸繼電器

在下列案例中, 小組傳輸繼電器永遠都在媒體路徑中:

- 從1:1 升級到群組通話的通話
- 通話會傳送給聯盟團隊使用者
- 通話是轉寄或轉接至商務用 Skype 使用者

請確定您的 SBC 能夠存取傳輸繼電器, 如下所述。    


## <a name="sip-signaling-fqdns"></a>SIP 信號: Fqdn

針對 SIP 信號, FQDN 和防火牆需求與非繞過案例相同。 

在下列 Office 365 環境中提供直接路由:
- Office 365
- Office 365 GCC
- Office 365 GCC 高
- Office 365 DoD 進一步瞭解[office 365 和美國政府環境](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)(例如 GCC、gcc 高和 DoD)。

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 和 Office 365 GCC 環境

直接路由的連接點是下列三個 Fqdn:

- **sip.pstnhub.microsoft.com** –全域 FQDN-必須先嘗試。 當 SBC 傳送要求來解析此名稱時, Microsoft Azure DNS 伺服器會傳回指向指派給 SBC 之主要 Azure 資料中心的 IP 位址。 作業是以資料中心的效能指標, 以及與 SBC 有關的地理位置為基礎。 傳回的 IP 位址會對應到主要 FQDN。

- **sip2.pstnhub.microsoft.com** –次要 FQDN-地理位置對應至第二個優先順序區域。

- **sip3.pstnhub.microsoft.com** –三元 FQDN-[地理位置] 對應至第三個優先順序區域。

您必須將這三個 Fqdn 放在一起, 才能:

- 提供最佳的使用體驗 (在所指派的 SBC 資料中心較少且最接近的情況下, 由查詢第一個 FQDN)。

- 在來自 SBC 的連線建立至遇到暫時問題的資料中心時, 提供容錯移轉。 如需詳細資訊, 請參閱下方的容錯移轉機制。


Fqdn **sip.pstnhub.microsoft.com**、 **sip2.pstnhub.microsoft.com**和**sip3.pstnhub.microsoft.com**將解析成下列其中一個 IP 位址:
- 52.114.148.0
- 52.114.132.46
- 52.114.75.24
- 52.114.76.76
- 52.114.7.24
- 52.114.14.70

您必須在防火牆中開啟所有這些 IP 位址的埠, 以允許傳入及傳出流量進出位址來傳送信號。 如果您的防火牆支援 DNS 名稱, FQDN **sip-all.pstnhub.microsoft.com**會解析為所有這些 IP 位址。 

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 環境

直接路由的連接點是下列 FQDN:

**sip.pstnhub.dod.teams.microsoft.us** –全域 FQDN。 因為 Office 365 DoD 環境僅存在於美國資料中心, 所以沒有次要和第三個 Fqdn。

Fqdn – sip.pstnhub.dod.teams.microsoft.us 將會解析成下列其中一個 IP 位址:

- 52.127.64.33
- 52.127.68.34

您必須在防火牆中開啟所有這些 IP 位址的埠, 以允許傳入及傳出流量進出位址來傳送信號。  如果您的防火牆支援 DNS 名稱, FQDN sip.pstnhub.dod.teams.microsoft.us 會解析為所有這些 IP 位址。 

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC 高環境

直接路由的連接點是下列 FQDN:

**sip.pstnhub.gov.teams.microsoft.us** –全域 FQDN。 由於 GCC 的高環境僅存在於美國資料中心, 因此沒有副及三元 Fqdn。

Fqdn – sip.pstnhub.gov.teams.microsoft.us 將會解析成下列其中一個 IP 位址:

- 52.127.88.59
- 52.127.92.64

您必須在防火牆中開啟所有這些 IP 位址的埠, 以允許傳入及傳出流量進出位址來傳送信號。  如果您的防火牆支援 DNS 名稱, FQDN sip.pstnhub.gov.teams.microsoft.us 會解析為所有這些 IP 位址。 

## <a name="sip-signaling-ports"></a>SIP 信號: 埠

對於所有提供直接路由的 Office 365 環境而言, 埠需求都是相同的:
- Office 365
- Office 365 GCC
- Office 365 GCC 高
- Office 365 DoD

您必須使用下列埠:

| 頻寬 | 從 | 自 | 來源埠 | 目的地埠|
| :-------- | :-------- |:-----------|:--------|:---------|
SIP/TLS| SIP Proxy | SBC | 1024-65535 | 在 SBC 上定義 |
| SIP/TLS | SBC | SIP Proxy | 在 SBC 上定義 | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>媒體流量: IP 與埠範圍

如果用戶端無法使用公用 IP 位址到達 SBC, 則在 SBC 與團隊用戶端之間的媒體流量會流動 (如果有直接連線) 或透過團隊傳輸中繼。

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>直接媒體流量的需求 (在團隊用戶端與 SBC 之間) 

用戶端必須能夠存取指定的埠 (請參閱 table) 至 SBC 的公用 IP 位址。 

注意: 如果用戶端在內部網路中, 則媒體會流向 SBC 的公用 IP 位址。 您可以在您的 NAT 裝置上設定 hairpinning, 讓交通永不離開商業網路裝置。

| 頻寬 | 從 | 自 | 來源埠 | 目的地埠|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | 端 | SBC | 50 000 – 50 019  | 在 SBC 上定義 |
| UDP/SRTP | SBC | 端 | 在 SBC 上定義 | 50 000 – 50 019  |


注意: 如果您的網路裝置會轉譯用戶端的來源埠, 請確定已在網路設備與 SBC 之間開啟已轉換的埠。 

### <a name="requirements-for-using-transport-relays"></a>使用傳輸繼電器的需求

傳輸繼電器與媒體處理器在同一個範圍內 (適用于非旁路情況): 

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 和 Office 365 GCC 環境

-52.112.0.0/14 (從52.112.0.1 到52.115.255.254 的 IP 位址)

## <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 環境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC 高環境

- 52.127.88.0/21


[小組傳輸中繼] 的埠範圍 (適用于所有環境) 如下表所示:


| 頻寬 | 從 | 自 | 來源埠 | 目的地埠|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | 傳輸中繼 | SBC | 50 000-59 999    | 在 SBC 上定義 |
| UDP/SRTP | SBC | 傳輸中繼 | 在 SBC 上定義 | 50 000 – 59 999、3478、3479     |


注意: Microsoft 建議在 SBC 上每個併發呼叫至少有兩個埠。 因為 Microsoft 有兩個版本的傳輸繼電器, 所以需要下列各項:

- v4, 只能與埠範圍 50 000 搭配 59 999

- v6 是與埠3478、3479搭配使用

目前, 媒體旁路只支援 v4 版的傳輸中繼。 我們會在未來推出 v6 支援。 

您需要開啟埠3478和3479以進行轉換。 當 Microsoft 使用媒體旁路支援 v6 傳輸中繼時, 您就不需要重新設定您的網路設備或 SBCs。 

### <a name="requirements-for-using-media-processors"></a>使用媒體處理器的需求

媒體處理器總是位於語音應用程式和網路 cleints 的媒體路徑中 (適用于 exampe, 小組 cleint 是 Edge 或 Google Chrome)。 其需求與非旁路設定相同。


媒體流量的 IP 範圍是 

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 和 Office 365 GCC 環境

-52.112.0.0/14 (從52.112.0.1 到52.115.255.254 的 IP 位址)

## <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 環境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC 高環境

- 52.127.88.0/21

媒體處理器的埠範圍 (適用于所有環境) 如下表所示:

| 頻寬 | 從 | 自 | 來源埠 | 目的地埠|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | 媒體處理器 | SBC | 49 152 – 53 247    | 在 SBC 上定義 |
| UDP/SRTP | SBC | 媒體處理器 | 在 SBC 上定義 | 49 152 – 53 247     |

## <a name="considerations-if-you-have-skype-for-business-phones-in-your-network"></a>如果您在網路上有商務用 Skype 電話, 請考慮  

如果您的網路中有任何使用 [直接傳送] 的商務用 Skype 端點 (例如, 小組使用者可以擁有以商務用 Skype 用戶端為基礎的3PIP 電話), 則必須關閉為這些使用者提供服務的主幹上的媒體旁路。

您可以為這些使用者建立單獨的幹線, 並將其指派為線上語音路由策略。

高層次的設定步驟:

- 依類型分割使用者-視使用者是否有3PIP 電話而定。

- 使用不同的 Fqdn 建立兩個不同的 trunks: 一個為媒體略過啟用;另一種是。 

  兩個 trunks 都指向同一個 SBC。 TLS SIP 信號的埠必須不同。 媒體埠必須相同。

- 根據線上語音路由策略中的使用者類型, 指派正確的主幹。

下列範例說明這個邏輯。

| 使用者組 | 使用者數量 | 在 OVRP 中指派中繼 FQDN | 已啟用媒體旁路 |
| :------------ |:----------------- |:--------------|:--------------|
擁有團隊用戶端與3PIP 手機的使用者 | 20 | sbc1.contoso.com:5061 | 虛假 | 
只有團隊結束點的使用者 (包括為小組認證的新電話) | 980 | sbc2.contoso.com:5060 | 滿足

兩個 trunks 都可以指向相同的同一個 SBC, 且具有相同的公用 IP 位址。 SBC 上的 TLS 信號埠必須不同, 如下圖所示。 注意: 您必須確認您的憑證同時支援這兩個 trunks。 在 SAN 中, 您必須有兩個名稱 (**sbc1.contoso.com**和**sbc2.contoso.com**), 或是擁有萬用字元證書。


![顯示兩個 trunks 可以指向同一個公用 IP 的同一個 SBC](media/direct-routing-media-bypass-7.png)

如需如何在同一個 SBC 上設定兩個 trunks 的相關資訊, 請參閱您的 SBC 轉銷商提供的檔:

 - [AudioCodes 部署檔](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 部署檔](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [功能區通訊部署檔](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-系統 (anynode) 部署檔](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a>媒體略過支援的用戶端端點

所有團隊端點都支援媒體旁路。

Webcleints (Microsoft Edge、Google Chrome 或 Mozilla Firefox) 中的 [團隊網頁應用程式], 我們會將呼叫轉換成非旁路, 即使它是繞過通話。 這會自動發生, 不需要系統管理員執行任何動作。 
 
## <a name="see-also"></a>另請參閱

[使用直接路由來設定媒體旁路](direct-routing-configure-media-bypass.md)



