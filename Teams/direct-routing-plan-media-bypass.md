---
title: 媒體旁路搭配直接路由方案
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 瞭解如何使用直接路由規劃媒體電話系統，這可讓您縮短媒體流量的路徑，並改善績效。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cc499d779af2e5eea765e9cf858b170241095e82
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2021
ms.locfileid: "58234778"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>媒體旁路搭配直接路由方案

## <a name="about-media-bypass-with-direct-routing"></a>關於使用直接路由的媒體旁路

媒體旁路可讓您縮短媒體流量的路徑，並減少傳輸中的躍點數量，以提升績效。 在媒體旁路時，媒體會保留在會話邊界控制器 (SBC) 與用戶端之間，而不是透過 Microsoft 電話 系統傳送。 若要設定媒體旁路，SBC 和用戶端必須位於相同的位置或網路。

您可以使用 **Set-CSOnlinePSTNGateway** 命令，將 **-MediaBypass** 參數設為 True 或 false，控制每個 SBC 的媒體旁路。 如果您啟用媒體旁路，這不表示所有媒體流量都會維持在公司網路中。 本文將說明不同情況下的通話流程。

下圖說明通話流程與媒體旁路和無媒體旁路的差異。

若沒有媒體旁路，當用戶端撥打或接收通話時，SBC、Microsoft 電話 System 和 Teams 用戶端之間的訊號和媒體流程，如下圖所示：

> [!div class="mx-imgBorder"]
> ![顯示沒有媒體旁路的訊號和媒體流程](media/direct-routing-media-bypass-1.png)


但假設使用者與 SBC 位於同一棟大樓或網路中。 例如，假設一位位於德國慕尼克大樓的使用者打電話給 PSTN 使用者： 

- **若沒有媒體** 旁路，媒體會透過 (或布建 Microsoft 資料中心的) ，並回到位於德國的 SBC。 

  已選取歐洲資料中心，因為 SBC 位於歐洲，而 Microsoft 會使用最接近 SBC 的資料中心。 雖然這個方法不會因為 Microsoft 網路內部流量優化而影響通話品質，但流量有不必要的回路。     

- **在媒體旁** 路時，媒體會直接保留在Teams使用者與 SBC 之間，如下圖所示：

  > [!div class="mx-imgBorder"]
  > ![使用媒體旁路顯示訊號和媒體流程](media/direct-routing-media-bypass-2.png)

媒體旁路會利用 SBC 上 (的 ICE) 協定Teams ICE lite。 這些通訊協定可讓直接路由使用最直接的媒體路徑，以獲得最佳品質。 ICE 和 ICE Lite 是 WebRTC 標準。 有關這些通訊協定的詳細資訊，請參閱 RFC 5245。


## <a name="call-flow-and-firewall-planning"></a>通話流程與防火牆規劃

通話流程與防火牆規劃取決於使用者是否可直接存取 SBC 的公用 IP 位址，以及使用者是否位於網路內外。

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>如果使用者能直接存取 SBC 的公用 IP 位址，則通話流程

如果使用者能直接存取 SBC 的公用 IP 位址，則通話流程如下所示：

- 對於媒體旁Teams，即使來自內部網路，用戶端也必須能夠存取 SBC 的公用 IP 位址。 如果不需要直接媒體，媒體可以透過傳輸轉場流程。

- 當使用者與 SBC 位於同一棟大樓和/或網路中時，建議使用這個解決方案：從媒體路徑移除 Microsoft Cloud 元件。

- 訊號永遠會透過 Microsoft 雲端傳輸。

下圖顯示啟用媒體旁路時通話流程、用戶端為內部，且用戶端可以直接 (SBC 的公用 IP 位址) ： 

- 路徑的箭號和數值與通話Microsoft Teams[一樣](./microsoft-teams-online-call-flows.md)。

- SIP 訊號一直採用 4' 和 4' 路徑 (視流量方向) 。 媒體保持為本地，並採用路徑 5b。

> [!div class="mx-imgBorder"]
> ![顯示已啟用媒體旁通的通話流程，用戶端為內部](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>如果使用者無法存取 SBC 的公用 IP 位址，通話流程

以下說明如果使用者無法存取 SBC 的公用 IP 位址，則通話流程。 

例如，假設使用者是外部使用者，而且租使用者系統管理員決定不將 SBC 的公用 IP 位址開放給網際網路中的每個人，而只會開啟到 Microsoft Cloud。 流量的內部元件可以透過傳輸轉Teams流程。 請考慮下列事項：

- Teams使用傳輸轉場。

- 針對媒體旁路，Microsoft 會使用傳輸轉場版本，要求在 Teams 傳輸轉場和 SBC (之間開啟埠 50 000 到 59 999，我們計畫在未來移至需要 3478-3481 埠) 的版本。


下圖顯示啟用媒體旁路時通話流程、用戶端為外部，且用戶端無法到達會話框線控制器的公用 IP 位址 (媒體會由 Teams 傳輸轉) 。

- 路徑的箭號和數值與通話Microsoft Teams[一樣](./microsoft-teams-online-call-flows.md)。

- 媒體會透過路徑 3、3'、4 和 4' 進行轉場

> [!div class="mx-imgBorder"]
> ![如果使用者無法存取 SBC 的公用 IP，則顯示通話流程](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>如果使用者位於網路外部且可存取 SBC 的公用 IP，則通話流程

> [!NOTE]
> 這不是建議的配置，因為它不會利用傳輸轉Teams的優點。 相反地，您應該考慮使用者無法存取 SBC 公用 IP 位址的上一個案例。 

下圖顯示啟用媒體旁路時通話流程、用戶端為外部，且用戶端可以到達 SBC (媒體的公用 IP 位址) 。

- 路徑的箭號和數值與通話流程Microsoft Teams[一樣](./microsoft-teams-online-call-flows.md)。

- SIP 訊號一直採用路徑 3 和 3' (視流量方向) 。 使用路徑 2 的媒體流程。

> [!div class="mx-imgBorder"]
> ![如果使用者無法存取 SBC 的公用 IP，則顯示通話流程](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a>媒體處理器與傳輸轉場的使用

Microsoft Cloud 中的兩個元件可能位在媒體流量路徑中：媒體處理器和傳輸轉場。 

- 媒體處理器是一種公開元件，可處理非旁路情況下的媒體，並處理語音應用程式的媒體。

   媒體處理器一直位於使用者非旁路通話的路徑中，但絕不會在未接來電的路徑中。 媒體處理器會一直位於所有語音應用程式的路徑中，例如通話停駐、組織自動語音留言和通話佇列。

- 傳輸轉送是用來連接到最近的傳輸服務，以傳送即時流量。

   傳輸轉訊可能位於未接來電的路徑中 ，這些通話可能來自或目的地給使用者，視使用者在哪裡以及網路的配置方式而不同。

下圖顯示兩個通話流程 ：一個已啟用媒體旁路，另一個已停用媒體旁路。

> [!NOTE]
> 圖表只會說明來自使用者或目的地使用者的流量。  

- 媒體控制器是 Azure 中的一項微服務，可指派媒體處理器，並建立 SDP (會話) 通訊協定。

- SIP Proxy 是一個元件，可轉換用於 SIP 的 HTTP REST Teams SIP。    

> [!div class="mx-imgBorder"]
> ![顯示已啟用和停用媒體旁路的通話流程](media/direct-routing-media-bypass-6.png)


下表摘要列出媒體處理器與傳輸轉場之間的差異。

|    | 媒體處理器 | 傳輸轉場|
| :--------------|:---------------|:------------|
在媒體路徑中，為使用者撥打非旁路的通話 | 總是 | 如果用戶端無法直接到達媒體處理器 | 
在媒體路徑中為使用者進行旁路通話 | 從來 沒有 | 如果用戶端無法到達公用 IP 位址上的 SBC | 
在語音應用程式的媒體路徑中 | 總是 | 從來 沒有 | 
可以轉譯 B2BUA (B2BUA) \* | 是 | 否，只會在端點之間轉傳音訊 | 
全球實例數目和位置 | 總計 10 個：美國東部和西部 2 個;2 在荷蘭的阿姆斯特丹和伯德林;香港和新加坡有 2 個;日本為 2;澳洲東部和東南亞的 2 個 | 多個

IP 範圍為：
- 52.112.0.0/14 (IP 位址從 52.112.0.1 到 52.115.255.254) 
- 52.120.0.0/14 (IP 位址從 52.120.0.1 到 52.123.255.254) 

\* 轉碼說明： 

- 媒體處理器是 B2BUA，這表示它可以在 MP 和 S) BC (之間將編解碼器從 Teams 用戶端變更為 MP 和 G.711。

- 傳輸轉場不是 B2BUA，這表示編解碼器永遠不會在用戶端與 SBC 之間變更，即使流量是透過轉場流程。

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a>如果主幹Teams媒體旁路，則使用媒體處理器

Teams媒體處理器一直在下列情況下插入媒體路徑中：

- 通話從 1：1 升級為群組通話
- 正在將通話呼叫至Teams使用者
- 呼叫已轉接或轉接至商務用 Skype使用者

請確定您的 SBC 能夠存取媒體處理器和傳輸轉場範圍，如下所示。    


## <a name="sip-signaling-fqdns"></a>SIP 訊號：FQDNs

針對 SIP 訊號，FQDN 和防火牆需求與非旁路案例相同。 

直接路由提供于下列Microsoft 365或Office 365環境中：
- Microsoft 365或Office 365
- Office 365 GCC
- Office 365 GCC高
- Office 365DoD 深入瞭解[Office 365美國政府](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)環境，例如 GCC、GCC高和 DoD。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365及Office 365 GCC環境

直接路由的連接點如下三個 FQDNs：

- **sip.pstnhub.microsoft.com** 全域 FQDN - 必須先嘗試。 當 SBC 傳送解決此名稱的要求時，Microsoft Azure DNS 伺服器會返回指向指派給 SBC 的主要 Azure 資料中心的 IP 位址。 此工作分派是根據資料中心的績效度量，以及 SBC 的地理位置鄰近度。 所退回的 IP 位址會對應到主要 FQDN。

- **sip2.pstnhub.microsoft.com** – 次要 FQDN – 地理上會繪製至第二個優先順序區域。

- **sip3.pstnhub.microsoft.com** - 三級 FQDN – 地理上會與第三個優先順序區域進行地圖。

您必須放置這三個 FQDNs，才能：

- 查詢第一個 FQDN (，提供較不載入且最接近 SBC 資料中心的最佳) 。

- 當從 SBC 建立到發生暫時問題的資料中心的連接時，提供容錯移轉。 詳細資訊，請參閱下方的容錯移轉機制。


FQDNs  **sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com** 和sip3.pstnhub.microsoft.com 會從下列子網解析為 IP 位址：
- 52.112.0.0/14
- 52.120.0.0/14

您必須在防火牆中開啟所有這些 IP 範圍的埠，以允許接收和傳出流量到與來自接收訊號的位址。 如果您的防火牆支援 DNS 名稱，FQDN **sip-all.pstnhub.microsoft.com** 解析為所有這些 IP 子網。 

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 環境

直接路由的連接點為下列 FQDN：

**sip.pstnhub.dod.teams.microsoft.us** – 全域 FQDN。 由於Office 365 DoD 環境僅存在於美國資料中心，因此沒有次要和三級 FQDNs。

FQDN sip.pstnhub.dod.teams.microsoft.us 會從下列子網解析為 IP 位址：

- 52.127.64.0/21

您必須在防火牆中開啟所有這些 IP 範圍的埠，以允許接收和傳出流量到與來自接收訊號的位址。  如果您的防火牆支援 DNS 名稱，FQDN sip.pstnhub.dod.teams.microsoft.us 解析為所有這些 IP 子網。 

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC高環境

直接路由的連接點為下列 FQDN：

**sip.pstnhub.gov.teams.microsoft.us** – 全域 FQDN。 由於GCC高環境僅存在於美國資料中心，因此沒有次要和三級 FQDNs。

FQDN sip.pstnhub.gov.teams.microsoft.us 會從下列子網解析為 IP 位址：

- 52.127.88.0/21

您必須在防火牆中開啟所有這些 IP 範圍的埠，以允許接收和傳出流量到與來自接收訊號的位址。  如果您的防火牆支援 DNS 名稱，FQDN sip.pstnhub.gov.teams.microsoft.us 解析為所有這些 IP 子網。 

## <a name="sip-signaling-ports"></a>SIP 訊號：埠

針對提供直接路由的所有Office 365埠需求相同：
- Microsoft 365或Office 365
- Office 365 GCC
- Office 365 GCC高
- Office 365國防部

您必須使用下列埠：

| 交通 | 從 | 自 | 來源埠 | 目的地埠|
| :-------- | :-------- |:-----------|:--------|:---------|
SIP/TLS| SIP Proxy | Sbc | 1024 - 65535 | 在 SBC 上定義 |
| SIP/TLS | Sbc | SIP Proxy | 在 SBC 上定義 | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>媒體流量：IP 和埠範圍

媒體流量會從 SBC Teams用戶端之間流動，如果有直接連接可用，或透過 Teams 傳輸轉場，如果用戶端無法使用公用 IP 位址到達 SBC。

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>用戶端與 SBC (之間Teams媒體流量的需求)  

用戶端必須能存取指定的埠 (請參閱) SBC 公用 IP 位址上的資料表。 

> [!NOTE]
> 如果用戶端位於內部網路中，媒體會流向 SBC 的公用 IP 位址。 您可以在 NAT 裝置上設定發釘，讓流量永遠不會離開商業網路設備。

| 交通 | 從 | 自 | 來源埠 | 目的地埠|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | 用戶端 | Sbc | 3478-3481 和 49152 – 53247| 在 SBC 上定義 |
| UDP/SRTP | Sbc | 用戶端 | 在 SBC 上定義 | 3478-3481 和 49152 – 53247  |


> [!NOTE]
> 如果您有可翻譯用戶端來源埠的網路設備，請確定已翻譯的埠在網路設備與 SBC 之間開啟。 

### <a name="requirements-for-using-transport-relays"></a>使用傳輸轉場的需求

傳輸轉場與媒體處理器在非 (情況下的傳輸) ： 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365及Office 365 GCC環境

- 52.112.0.0 /14 (IP 位址從 52.112.0.1 到 52.115.255.254) 

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 環境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC高環境

- 52.127.88.0/21


適用于所有Teams傳輸轉 (的埠) 如下表所示：


| 交通 | 從 | 自 | 來源埠 | 目的地埠|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | 傳輸轉場 | Sbc | 50 000 -59 999    | 在 SBC 上定義 |
| UDP/SRTP | Sbc | 傳輸轉場 | 在 SBC 上定義 | 50 000 – 59 999, 3478-3481     |


> [!NOTE]
> Microsoft 建議在 SBC 上，每個同時通話至少兩個埠。 由於 Microsoft 有兩個版本的傳輸轉傳遞，因此必須執行下列操作：
> 
> - v4，只能使用埠範圍 50 000 到 59 999
> 
> - v6，適用于埠 3478-3481

目前，媒體旁路僅支援 v4 版的傳輸轉場。 我們會在未來推出 v6 的支援。 

您需要開啟埠 3478-3481 進行轉場。 當 Microsoft 推出 V6 傳輸轉場與媒體旁路的支援時，您將不需要重新配置您的網路設備或 SBC。 

### <a name="requirements-for-using-media-processors"></a>使用媒體處理器的需求

媒體處理器一直位於語音應用程式和 Web 用戶端的媒體路徑 (例如 Edge 或 Google Chrome Teams用戶端) 。 需求與非旁路組組相同。


媒體流量的 IP 範圍為 

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 Office 365 GCC環境

- 52.112.0.0 /14 (IP 位址從 52.112.0.1 到 52.115.255.254) 

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 環境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC高環境

- 52.127.88.0/21

適用于所有環境 (的媒體處理器) 範圍如下表所示：

| 交通 | 從 | 自 | 來源埠 | 目的地埠|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | 媒體處理器 | Sbc | 3478-3481 和 49 152 – 53 247    | 在 SBC 上定義 |
| UDP/SRTP | Sbc | 媒體處理器 | 在 SBC 上定義 | 3478-3481 和 49 152 – 53 247     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a>設定媒體旁路和非媒體旁路的個別主幹  

如果您要從非媒體旁路移至媒體旁路，並想要先確認功能，然後再將所有使用方式移遷移到媒體旁路，您可以建立個別主幹和個別的線上語音路由策略，以路由至媒體旁路主幹並指派給特定使用者。 

高層次組組步驟：

- 識別要測試媒體旁路的使用者。

- 使用不同的 FQDNs 建立兩個不同的主幹：一個已啟用媒體旁路;另一個則啟用媒體旁路;另一個不會。 

  這兩個主幹都指向相同的 SBC。 TLS SIP 訊號的埠必須不同。 媒體埠必須相同。

- 建立新的線上語音路由策略，並將媒體旁路主幹指派給與此政策 PSTN 使用量相關聯的對應路由。

- 將新的線上語音路由策略指派給已識別以測試媒體旁路的使用者。

下列範例說明此邏輯。

| 一組使用者 | 使用者數目 | 在 OVRP 中指派的主幹 FQDN | 已啟用媒體旁路 |
| :------------ |:----------------- |:--------------|:--------------|
具有非媒體旁路主幹的使用者 | 980 | sbc1.contoso.com:5061 | 假 |
具有媒體旁路主幹的使用者 | 20 | sbc2.contoso.com:5060 | 真 | 

這兩個主幹可以指向具有相同公用 IP 位址的同一個 SBC。 SBC 上的 TLS 訊號埠必須不同，如下圖所示。 請注意，您必須確定憑證支援這兩個主幹。 在 SAN 中，您必須有兩個名稱 (sbc1.contoso.com，sbc2.contoso.com) 萬用字元憑證。 

> [!div class="mx-imgBorder"]
> ![顯示兩個主幹可以指向相同公用 IP 的同一個 SBC](media/direct-routing-media-bypass-7.png)

若要瞭解如何在同一個 SBC 上設定兩個主幹，請參閱 SBC 廠商提供的檔：

 - [AudioCodes 部署檔](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 部署檔](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [功能區通訊部署檔](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems (任何) 部署檔](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a>媒體旁路支援的用戶端端點

所有獨立電腦用戶端、Android 和 iOS 用戶端Teams裝置都支援媒體Teams 電話旁路。 

對於不支援媒體旁路的所有其他端點，我們會將通話轉換為非旁路，即使它以旁路通話開始。 這會自動發生，而且不需要系統管理員執行任何動作。 這包括 商務用 Skype 3PIP 電話和 Teams Web 用戶端，支援在 Microsoft Edge、Google Chrome、Mozilla Firefox) 上直接路由通話 (WebRTC 用戶端。 
 
## <a name="see-also"></a>另請參閱

[設定媒體旁路搭配直接路由](direct-routing-configure-media-bypass.md)
