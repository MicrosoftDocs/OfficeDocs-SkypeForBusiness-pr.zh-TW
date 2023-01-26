---
title: 媒體旁路搭配直接路由方案
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 瞭解如何使用電話系統直接路由來規劃媒體略過，這可讓您縮短媒體流量路徑並改善效能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ea92103789927d35ae8bdd317987f32863d4d74e
ms.sourcegitcommit: e09591a0df9848b50bfeda29650e91e9d35724af
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/24/2023
ms.locfileid: "69981788"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>媒體旁路搭配直接路由方案

## <a name="about-media-bypass-with-direct-routing"></a>關於媒體略過與直接路由

媒體略過可讓您縮短媒體流量路徑，並減少傳輸中的躍點數量，以獲得更好的效能。 媒體略過時，媒體會保留在會話框線控制器 (SBC) 和用戶端之間，而不是透過 Microsoft Phone System 傳送。 若要設定媒體略過，SBC 和用戶端必須位於相同的位置或網路。

您可以使用 **Set-CSOnlinePSTNGateway** 命令，並將 **-MediaBypass** 參數設為 True 或 False，以控制每個 SBC 的媒體略過。 如果您啟用媒體略過，這並不表示所有媒體流量都會保留在公司網路內。 本文將說明不同案例中的通話流程。

下圖說明通話流程與媒體略過的差異。

當用戶端撥打或接聽電話時，不需略過媒體，SBC、Microsoft 電話系統和 Teams 用戶端之間的訊號和媒體流程，如下圖所示：

> [!div class="mx-imgBorder"]
> ![顯示訊號和媒體流程，但不需媒體略過。](media/direct-routing-media-bypass-1.png)


但讓我們假設使用者與 SBC 在同一棟大樓或網路上。 例如，假設一位使用者在[增益集] 的大樓內，撥打電話給 PSTN 使用者： 

- **若不使用媒體略過**，媒體會透過阿姆斯特丹或都柏林 (部署 Microsoft 資料中心) ，然後再回到 SBC in Defender。 

  由於 SBC 位於歐洲地區，且 Microsoft 使用最接近 SBC 的資料中心，因此已選取歐洲的資料中心。 由於大多數地區內的 Microsoft 網路流量優化，此方法不會影響通話品質，但流量卻有不必要的迴圈。     

- **媒體略過** 時，媒體會直接保留在 Teams 使用者和 SBC 之間，如下圖所示：

  > [!div class="mx-imgBorder"]
  > ![顯示媒體略過的訊號和媒體流程。](media/direct-routing-media-bypass-2.png)

媒體略過會運用稱為互動式連線的通訊協定，在 Teams 用戶端上 (ICE) ，以及 SBC 上的 ICE 精簡版。 這些通訊協定可讓直接路由使用最直接的媒體路徑來獲得最佳品質。 ICE 和 ICE Lite 是 WebRTC 標準。 如需這些通訊協定的詳細資訊，請參閱 RFC 5245。


## <a name="call-flow-and-firewall-planning"></a>通話流程和防火牆規劃

通話流程和防火牆規劃取決於使用者是否可以直接存取 SBC 的公用 IP 位址，以及使用者是否在網路內部或外部。

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>如果使用者可以直接存取 SBC 的公用 IP 位址，則通話流程

如果使用者可以直接存取 SBC 的公用 IP 位址，通話流程如下：

- 若要略過媒體，Teams 用戶端必須能夠存取 SBC 的公用 IP 位址，即使是從內部網路也能存取。 如果不需要直接媒體，媒體可以透過傳輸轉送進行。

- 當使用者與 SBC 在同一棟大樓和/或網路中時，建議使用此解決方案：從媒體路徑移除 Microsoft 雲端元件。

- 訊號一律會透過 Microsoft 雲端傳入。

下圖顯示啟用媒體略過時的通話流程、用戶端為內部，且用戶端可以到達 SBC 的公用 IP 位址 (直接媒體) ： 

- 路徑的箭號和數值是根據 [Microsoft Teams 通話流量](./microsoft-teams-online-call-flows.md)。

- SIP 訊號一律會根據流量) 的方向，採用 4 和 4' (路徑。 媒體會保持本機，並採用路徑 5b。

> [!div class="mx-imgBorder"]
> ![顯示已啟用 Media Bypass 的通話流程、用戶端為內部。](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>如果使用者無法存取 SBC 的公用 IP 位址，則撥號流程

下列說明如果使用者無法存取 SBC 的公用 IP 位址時的通話流程。 

例如，假設使用者是外部使用者，且租使用者系統管理員決定不要向網際網路上的每個人開啟 SBC 的公用 IP 位址，但只開啟 Microsoft Cloud。 流量的內部元件可以透過 Teams 傳輸轉送流程。 請考慮下列事項：

- 使用 Teams 傳輸轉送。

- 若要略過媒體，Microsoft 會使用需要在 Teams 傳輸轉送和 SBC (之間開啟埠 50 000 到 59 999 的傳輸轉送版本，我們計畫日後移至需要 3478-3481 埠) 的版本。


下圖顯示啟用媒體略過時的通話流程、用戶端為外部，且用戶端無法到達會話框線控制器的公用 IP 位址， (媒體是由 Teams 傳輸轉送) 轉送。

- 路徑的箭號和數值是根據 [Microsoft Teams 通話流量](./microsoft-teams-online-call-flows.md)。

- 媒體會透過路徑 3、3'、4 和 4' 轉送

> [!div class="mx-imgBorder"]
> ![如果使用者無法存取 SBC 的公用 IP，則會顯示通話流程。](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>如果使用者在網路外部且可以存取 SBC 的公用 IP，則通話流程

> [!NOTE]
> 這不是建議的設定，因為它不使用 Teams 傳輸轉送。 相反地，您應該考慮先前使用者無法存取 SBC 公用 IP 位址的案例。 

下圖顯示啟用媒體略過時的通話流程、用戶端為外部，且用戶端可以到達 SBC 的公用 IP 位址 (直接媒體) 。

- 路徑的箭號和數值是根據 [Microsoft Teams 通話流程](./microsoft-teams-online-call-flows.md) 文章。

- SIP 訊號一律會根據流量) 的方向，採用 3 和 3' (路徑。 使用路徑 2 的媒體流量。

> [!div class="mx-imgBorder"]
> ![如果使用者無法存取 SBC 的公用 IP，則會顯示通話流程。](media/direct-routing-media-bypass-5.png)



## <a name="use-of-media-processors-and-transport-relays"></a>使用媒體處理器和傳輸轉送

Microsoft Cloud 中有兩個可以位於媒體流量路徑的元件：媒體處理器和傳輸轉送。 

- 媒體處理器是一種公開元件，可處理非旁路案例中的媒體，並處理語音應用程式的媒體。

   媒體處理器一律位於使用者非略過的通話路徑中，但不會位於略過的通話路徑中。 媒體處理器一律位於所有語音應用程式的路徑中，例如「通話駐留」、「組織自動語音應答」和「通話佇列」。

- 傳輸轉送是用來連線到最近的傳輸服務，以傳送即時流量。

   視使用者所在的位置和網路設定方式而定，傳輸轉送可能或不在略過的通話路徑中，而這些呼叫是來自使用者或目的地是使用者。

下圖顯示兩個通話流程：一個已啟用媒體略過，第二個已停用媒體略過。

> [!NOTE]
> 圖表只會說明來自使用者或目的地使用者的流量。  

- Media Controller 是 Azure 中的一個微伺服器，可指派媒體處理器，並在 SDP) 優惠 (建立會話描述通訊協定。

- SIP Proxy 是將 Teams 中使用的 HTTP REST 訊號轉換為 SIP 的元件。    

> [!div class="mx-imgBorder"]
> ![顯示已啟用和停用 Media Bypass 的通話流量。](media/direct-routing-media-bypass-6.png)


下表摘要說明媒體處理器與傳輸轉送之間的差異。

|  &nbsp; | 媒體處理器 | 傳輸轉送|
| :--------------|:---------------|:------------|
|使用者非略過通話的媒體路徑 | 總是 | 如果用戶端無法直接連線到 Media Processor |
|使用者略過通話的媒體路徑 | 從來 沒有 | 如果用戶端無法連線到公用 IP 位址上的 SBC |
|在語音應用程式的媒體路徑中 | 總是 | 從來 沒有 |
|可以執行轉譯 (B2BUA) \* | 是 | 否，只在端點之間轉送音訊 |

IP 範圍如下：
- 52.112.0.0/14 (IP 位址從 52.112.0.1 到 52.115.255.254) 
- 52.122.0.0/15 (IP 位址從 52.122.0.1 到 52.123.255.254) 

\* 轉譯說明： 

- 媒體處理器是 B2BUA，這表示它可以將編解碼器變更 (例如，在 MP 與 SBC) 之間，從 Teams 用戶端變更為 MP 和 G.711。

- 傳輸轉送不是 B2BUA，這表示用戶端和 SBC 之間永遠不會變更編解碼器，即使流量是透過轉送。

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a>如果主幹設定為媒體略過，請使用 Teams Media 處理器

在下列案例中，Teams 媒體處理器一律會插入媒體路徑：

- 通話從 1：1 升級為群組通話
- 通話即將撥打給同盟 Teams 使用者
- 呼叫會轉接或轉接給商務用 Skype使用者

請確定您的 SBC 可以存取媒體處理器和傳輸轉送範圍，如下所述。    


## <a name="sip-signaling-fqdns"></a>SIP 訊號：FQDN

對於 SIP 訊號，FQDN 和防火牆需求與非略過的案例相同。 

在下列 Microsoft 365 或 Office 365 環境中提供直接路由：
- Microsoft 365 或 Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD 深入瞭解[Office 365 及美國政府環境](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)，例如 GCC、GCC High 和 DoD。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365 和 Office 365 GCC 環境

直接路由的連接點為下列三個 FQDN：

- **sip.pstnhub.microsoft.com** – 全球 FQDN – 必須先試用。 當 SBC 傳送解決此名稱的要求時，Microsoft Azure DNS 伺服器會傳回指向指派給 SBC 的主要 Azure 資料中心之 IP 位址。 作業是根據資料中心的效能指派，以及與 SBC 的地理鄰近度。 傳回的 IP 位址會對應到主要的 FQDN。

- **sip2.pstnhub.microsoft.com** – 次要 FQDN – 地理位置對應到第二優先順序地區。

- **sip3.pstnhub.microsoft.com** – 新式 FQDN – 地理位置對應到第三優先順序地區。

您必須將這三個 FQDN 放在以下位置：

- 透過查詢第一個 FQDN) ，提供 (載入較少且最接近指派的 SBC 資料中心的最佳體驗。

- 從 SBC 連線建立至發生暫時性問題的資料中心時，提供容錯移轉。 如需詳細資訊，請參閱下方的容錯移轉機制。


FQDN **sip.pstnhub.microsoft.com**、 **sip2.pstnhub.microsoft.com** 和 **sip3.pstnhub.microsoft.com** 將解析為來自下列子網的 IP 位址：
- 52.112.0.0/14
- 52.122.0.0/15

您必須在防火牆中開啟所有這些 IP 範圍的埠，以允許內送和外寄流量從位址進入和移出訊號。

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 環境

直接路由的連接點為下列 FQDN：

**sip.pstnhub.dod.teams.microsoft.us** – 全球 FQDN。 由於Office 365 DoD 環境僅存在於美國資料中心，因此沒有次要和次要 FQDN。

FQDN sip.pstnhub.dod.teams.microsoft.us 將從下列子網解析為 IP 位址：

- 52.127.64.0/21

您必須在防火牆中開啟所有這些 IP 範圍的埠，以允許內送和外寄流量從位址進入和移出訊號。  如果您的防火牆支援 DNS 名稱，FQDN sip.pstnhub.dod.teams.microsoft.us 解析到所有這些 IP 子網。 

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High 環境

直接路由的連接點為下列 FQDN：

**sip.pstnhub.gov.teams.microsoft.us** – 全球 FQDN。 由於 GCC High 環境僅存在於美國資料中心，因此沒有次要和次要 FQDN。

FQDN sip.pstnhub.gov.teams.microsoft.us 將從下列子網解析為 IP 位址：

- 52.127.88.0/21

您必須在防火牆中開啟所有這些 IP 範圍的埠，以允許內送和外寄流量從位址進入和移出訊號。  如果您的防火牆支援 DNS 名稱，FQDN sip.pstnhub.gov.teams.microsoft.us 解析到所有這些 IP 子網。 

## <a name="sip-signaling-ports"></a>SIP 訊號：埠

對於提供直接路由的所有Office 365環境，埠需求都相同：
- Microsoft 365 或 Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

您必須使用下列埠：

| 交通 | 從 | 自 | 來源埠 | 目的地埠|
| :-------- | :-------- |:-----------|:--------|:---------|
| SIP/TLS| SIP Proxy | Sbc | 1024 - 65535 | 定義于 SBC |
| SIP/TLS | Sbc | SIP Proxy | 定義于 SBC | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>媒體流量：IP 和埠範圍

如果可使用直接連線能力，或如果用戶端無法使用公用 IP 位址連線至 SBC，則媒體流量會在 SBC 和 Teams 用戶端之間延伸。

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>在 Teams 用戶端和 SBC) 之間 (媒體直接流量的需求 

用戶端必須能夠存取指定的埠 (請參閱 SBC 公用 IP 位址上的資料表) 。 

> [!NOTE]
> 如果用戶端位於內部網路，媒體會流向 SBC 的公用 IP 位址。 您可以在 NAT 裝置上設定美髮釘選，讓流量永遠不會離開商業網路設備。

| 交通 | 從 | 自 | 來源埠 | 目的地埠|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | 用戶端 | Sbc | 50000-50019| 定義于 SBC |
| UDP/SRTP | Sbc | 用戶端 | 定義于 SBC | 50000-50019  |


> [!NOTE]
> 如果您的網路裝置可以翻譯用戶端的來源埠，請確定已在網路設備和 SBC 之間開啟翻譯埠。 

### <a name="requirements-for-using-transport-relays"></a>使用傳輸轉送的需求

對於非旁路案例，傳輸轉送的範圍與媒體處理器 () ： 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365 和 Office 365 GCC 環境

- 52.112.0.0 /14 (IP 位址從 52.112.0.1 到 52.115.255.254) 

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 環境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High 環境

- 52.127.88.0/21


Teams 傳輸轉送 (適用于所有環境) 的埠範圍如下表所示：


| 交通 | 從 | 自 | 來源埠 | 目的地埠|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | 傳輸轉送 | Sbc | 50 000 -59 999    | 定義于 SBC |
| UDP/SRTP | Sbc | 傳輸轉送 | 定義于 SBC | 50 000 – 59 999, 3478-3481     |


> [!NOTE]
> Microsoft 建議至少在 SBC 上同時通話兩個埠。 由於 Microsoft 有兩個版本的傳輸轉送，因此必須執行下列動作：
> 
> - v4，僅適用于埠範圍 50 000 到 59 999
> 
> - v6，可與埠 3478-3481 搭配使用

目前，媒體略過僅支援 v4 版本的傳輸轉送。 我們未來將會推出 v6 的支援。 

您必須開啟埠 3478-3481 才能進行轉換。 當 Microsoft 使用 Media Bypass 引進 v6 傳輸轉送的支援時，您不需要重新設定網路設備或 SBC。 

### <a name="requirements-for-using-media-processors"></a>使用媒體處理器的需求

媒體處理器永遠位於語音應用程式和 Web 用戶端的媒體路徑 (例如，Microsoft Edge 或 Google Chrome 中的 Teams 用戶端) 。 這些需求與非略過設定相同。


媒體流量的 IP 範圍為 

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365與Office 365 GCC 環境

- 52.112.0.0 /14 (IP 位址從 52.112.0.1 到 52.115.255.254) 

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 環境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High 環境

- 52.127.88.0/21

適用于所有環境) 的媒體處理器 (埠範圍如下表所示：

| 交通 | 從 | 自 | 來源埠 | 目的地埠|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | 媒體處理器 | Sbc | 3478-3481 和 49 152 – 53 247    | 定義于 SBC |
| UDP/SRTP | Sbc | 媒體處理器 | 定義于 SBC | 3478-3481 和 49 152 – 53 247     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a>設定媒體略過和非媒體旁路的個別樹幹  

如果您要從非媒體略過移轉到媒體，並想要在將所有使用方式移轉到媒體略過之前確認功能，您可以建立個別的主幹和個別的線上語音路由原則，以路由至媒體略過主幹並指派給特定使用者。 

高階設定步驟：

- 識別要測試媒體略過的使用者。

- 使用不同的 FQDN 建立兩個不同的樹幹：一個啟用媒體略過;另一個則不會。 

  兩個樹幹都指向相同的 SBC。 TLS SIP 訊號的埠必須不同。 媒體埠必須相同。

- 建立新的線上語音路由原則，並將媒體略過主幹指派給與此原則的 PSTN 使用量相關聯的對應路由。

- 將新的線上語音路由原則指派給您已識別為略過測試媒體的使用者。

以下範例說明此邏輯。

| 一組使用者 | 使用者數目 | 在 OVRP 中指派的主幹 FQDN | 已啟用媒體略過 |
| :------------ |:----------------- |:--------------|:--------------|
| 具有非媒體旁路主幹的使用者 | 980 | sbc1.contoso.com:5061 | 假 |
| 擁有媒體略過主幹的使用者 | 20 | sbc2.contoso.com:5060 | 真 | 

兩個主幹可以指向具有相同公用 IP 位址的相同 SBC。 SBC 上的 TLS 訊號埠必須不同，如下圖所示。 請注意，您必須確認憑證支援兩個主幹。 在 SAN 中，您需要有兩個名稱 (**sbc1.contoso.com** 和 **sbc2.contoso.com**) 或有萬用字元憑證。

> [!div class="mx-imgBorder"]
> ![顯示兩個主幹可以指向具有相同公用 IP 的相同 SBC。](media/direct-routing-media-bypass-7.png)

如需如何在同一個 SBC 上設定兩根樹幹的相關資訊，請參閱您的 SBC 廠商所提供的檔：

 - [AudioCodes 部署檔](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 部署檔](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [功能區通訊部署檔](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems (任何節點) 部署檔](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a>媒體略過支援的用戶端點

所有獨立 Teams 桌面用戶端、Android 和 iOS 用戶端以及 Teams Phone 裝置都支援媒體略過功能。 

對於不支援媒體略過的所有其他端點，即使通話是以略過通話方式啟動，我們也會將通話轉換為非略過。 這會自動發生，而且不需要系統管理員採取任何動作。 這包括商務用 Skype 3PIP 手機，以及支援在 Microsoft Edge、Google Chrome、Mozilla Firefox) 上執行之 WebRTC 用戶端的直接路由通話 (Teams Web 用戶端。 
 
## <a name="see-also"></a>另請參閱

[設定媒體旁路搭配直接路由](direct-routing-configure-media-bypass.md)
