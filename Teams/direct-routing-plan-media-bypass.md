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
description: 瞭解如何使用電話系統直接路由規劃媒體旁路，這可讓您縮短媒體流量的路徑並提升績效。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e21007c31dca540e4f659aad627911b4aec2e456
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460863"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>媒體旁路搭配直接路由方案

## <a name="about-media-bypass-with-direct-routing"></a>關於使用直接路由旁路的媒體

媒體旁路可讓您縮短媒體流量的路徑，並減少傳輸中的躍點數目，以提升績效。 媒體旁路時，媒體會保留在會話邊界控制器 (SBC) 與用戶端之間，而不是透過 Microsoft Phone System 傳送。 若要設定媒體旁路，SBC 和用戶端必須位於相同的位置或網路中。

您可以使用 **Set-CSOnlinePSTNGateway** 命令，將 **-MediaBypass** 參數設為 True 或 False，控制每個 SBC 的媒體旁路。 如果您啟用媒體旁路，並不表示所有媒體流量都會留在公司網路中。 本文將說明不同情況下的通話流程。    

下圖說明通話流程與媒體旁路和不含媒體旁路的差異。

若沒有媒體旁路，當用戶端撥打或接聽電話時，SBC、Microsoft Phone System 和 Teams 用戶端之間的訊號和媒體流程，如下圖所示：

> [!div class="mx-imgBorder"]
> ![顯示訊號與媒體流程，而不忽略媒體](media/direct-routing-media-bypass-1.png)


但我們假設使用者與 SBC 位於相同的建築物或網路中。 例如，假設位於 [星展圖》 大樓的使用者撥打給 PSTN 使用者： 

- **媒體若不** 經由媒體旁路，將會透過 (布建 Microsoft 資料中心的) ，並回到位於卡特的 SBC。 

  由於 SBC 位於歐洲，而 Microsoft 使用離 SBC 最近的資料中心，因此會選取歐洲資料中心。 雖然這個方法不會因為 Microsoft 網路中大部分地區的流量優化而影響通話品質，但流量有不必要的迴圈。     

- **媒體旁** 路時，媒體會直接保留在 Teams 使用者與 SBC 之間，如下圖所示：

  > [!div class="mx-imgBorder"]
  > ![使用媒體旁路顯示訊號與媒體流程](media/direct-routing-media-bypass-2.png)

媒體旁路會運用稱為互動式連接新 (ICE) Teams 用戶端上的通訊協定，以及 SBC 上的 ICE lite。 這些通訊協定可讓直接路由使用最直接的媒體路徑，以獲得最佳品質。 ICE 和 ICE Lite 是 WebRTC 標準。 有關這些通訊協定的詳細資訊，請參閱 RFC 5245。


## <a name="call-flow-and-firewall-planning"></a>通話流程與防火牆規劃

通話流程與防火牆規劃取決於使用者是否可以直接存取 SBC 的公用 IP 位址，以及使用者是否位於網路內外。

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>如果使用者可以直接存取 SBC 的公用 IP 位址，則通話流程

如果使用者可以直接存取 SBC 的公用 IP 位址，通話流程如下：

- 對於媒體旁路，Teams 用戶端必須能存取 SBC 的公用 IP 位址，即使從內部網路也一樣。 如果不需要直接媒體，媒體可以透過傳輸轉場流程。

- 當使用者與 SBC 位於同一棟大樓和/或網路中時，建議的解決方案是移除媒體路徑中的 Microsoft Cloud 元件。

- 訊號一直透過 Microsoft 雲端流動。

下圖顯示啟用媒體旁路時通話流程、用戶端在內部，且用戶端可以直接 (SBC 的公用 IP) ： 

- 路徑的箭號和數值會與 Microsoft Teams 通話 [流量一樣](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)。

- SIP 訊號一直採用 4' 和 4' 路徑 (視交通路線) 。 媒體會保持為本地，並採用路徑 5b。

> [!div class="mx-imgBorder"]
> ![顯示已啟用媒體旁路的通話流程，用戶端在內部](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>如果使用者無法存取 SBC 的公用 IP 位址，則通話流程

以下說明如果使用者無法存取 SBC 的公用 IP 位址，通話流程。 

例如，假設使用者是外部使用者，而租使用者系統管理員決定不對網際網路中的每個人開啟 SBC 的公用 IP 位址，但只開放給 Microsoft Cloud。 流量的內部元件可以透過 Teams 傳輸轉場流程。 請考慮下列事項：

- 使用 Teams 傳輸轉場。

- 針對媒體旁路，Microsoft 使用的傳輸轉場版本需要在 Teams 傳輸轉場和 SBC (之間開啟埠 50 000 到 59 999 (，我們計畫未來移往只需要 3478 和 3479 個埠) 的版本。


下圖顯示啟用媒體旁路時通話流程、用戶端為外部，且用戶端無法到達會話框線控制器的公用 IP 位址 (媒體會由 Teams 傳輸轉場) 。

- 路徑的箭號和數值會與 Microsoft Teams 通話 [流量一樣](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)。

- 媒體會透過路徑 3、3'、4 和 4' 進行轉場

> [!div class="mx-imgBorder"]
> ![如果使用者無法存取 SBC 的公用 IP，則顯示通話流程](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>如果使用者位於網路外部，且可存取 SBC 的公用 IP，則通話流程

> [!NOTE]
> 這不是建議的配置，因為它不會利用 Teams 傳輸轉場。 不過，您應該考慮先前使用者無法存取 SBC 公用 IP 位址的情況。 

下圖顯示啟用媒體旁路、用戶端為外部，且用戶端可以到達 SBC 的公用 IP 位址 (直接媒體) 。

- 路徑的箭號和數值符合 Microsoft Teams 通話 [流程一](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) 文。

- SIP 訊號一定採用路徑 3 和 3' (視交通路線) 。 媒體會使用路徑 2 流動。

> [!div class="mx-imgBorder"]
> ![如果使用者無法存取 SBC 的公用 IP，則顯示通話流程](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a>媒體處理器與傳輸轉場的使用

Microsoft Cloud 有兩個元件可以在媒體流量的路徑中：媒體處理器和傳輸轉場。 

- 媒體處理器是一種公開元件，可處理非旁路情況下的媒體，並處理語音應用程式的媒體。

   媒體處理器一直位於非旁路使用者通話的路徑中，但絕不會在旁路通話的路徑中。 媒體處理器永遠位於所有語音應用程式的路徑中，例如通話停駐、組織自動語音留言和通話佇列。

- 傳輸轉送是用來連接到最近的傳輸服務，以傳送即時流量。

   傳輸轉會可能位於旁路的通話路徑中 ，這些通話來自或目的地是使用者，視使用者的目前位置及網路設置方式而不同。

下圖顯示兩個通話流程：一個已啟用媒體旁路，另一個已停用媒體旁路。 請注意，此圖表只會說明來自或目的地使用者的流量。  
- 媒體控制器是 Azure 中的一種微型服務，可指派媒體處理器，並建立 SDP (會話描述) 通訊協定。

- SIP Proxy 是一個元件，將 Teams 中所使用的 HTTP REST 訊號轉換為 SIP。    

> [!div class="mx-imgBorder"]
> ![顯示啟用和停用媒體旁路的通話流程](media/direct-routing-media-bypass-6.png)


下表摘要列出媒體處理器與傳輸轉場的差異。

|    | 媒體處理器 | 傳輸轉場|
| :--------------|:---------------|:------------|
使用者非旁路通話的媒體路徑 | 總是 | 如果用戶端無法直接到達媒體處理器 | 
使用者旁路通話的媒體路徑 | 從來 沒有 | 如果用戶端無法到達公用 IP 位址上的 SBC | 
語音應用程式的媒體路徑 | 總是 | 從來 沒有 | 
可以執行 B2BUA (轉) \* | 是 | 否，只會在端點之間轉傳音訊 | 
全球實例數目和位置 | 總計 10 個：美國東部和西部 2 個;2 在荷蘭，在愛爾蘭及愛爾蘭;香港和新加坡有 2 個;日本為 2;2 位於澳洲東部及東南亞 | 多個

IP 範圍為：
- 52.112.0.0/14 (IP 位址從 52.112.0.1 到 52.115.255.254) 
- 2014/52.120.0.0/14 (IP 位址從 52.120.0.1 到 52.123.255.254) 

\* 轉碼說明： 

- 媒體處理器是 B2BUA，這表示它可以在 MP 和 S) BC (之間將編解碼器變更為 (，從 Teams 用戶端變更為 MP 和 G.711。

- 傳輸轉場不是 B2BUA，這表示編解碼器不會在用戶端和 SBC 之間變更，即使流量是透過轉場進行。

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a>如果系統已針對媒體旁路設置樹線，則使用 Teams 媒體處理器

在下列情況下，Teams 媒體處理器一直在媒體路徑中插入：

- 通話從 1：1 升級為群組通話
- 通話正要撥打到 Teams 的聯盟使用者
- 呼叫已轉接或轉接給商務用 Skype 使用者

請確定您的 SBC 能夠存取媒體處理器和傳輸轉場範圍，如下所述。    


## <a name="sip-signaling-fqdns"></a>SIP 訊號：FQDN

針對 SIP 訊號，FQDN 和防火牆需求與非旁路案例相同。 

直接路由提供于下列 Microsoft 365 或 Office 365 環境：
- Microsoft 365 或 Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD 深入瞭解 [Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) 和美國政府環境，例如 GCC、GCC High 和 DoD。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365 和 Office 365 GCC 環境

直接路由的連接點為下列三個 FQDN：

- **sip.pstnhub.microsoft.com** 全域 FQDN – 必須先嘗試。 當 SBC 傳送解決此名稱的要求時，Microsoft Azure DNS 伺服器會回到指向指派給 SBC 的主要 Azure 資料中心的 IP 位址。 此工作分派是根據資料中心的績效計量，以及 SBC 的地理位置鄰近。 所回的 IP 位址會對應到主要 FQDN。

- **sip2.pstnhub.microsoft.com** - 次要 FQDN – 地理上會與第二個優先順序區域進行地圖。

- **sip3.pstnhub.microsoft.com** 線 FQDN – 地理上會與第三個優先順序區域進行地圖。

您必須放置這三個 FQDN，才能：

- 查詢第一個 FQDN (，以提供最佳體驗，讓負載較少且最接近指派的 SBC 資料中心) 。

- 從 SBC 建立與遇到暫時問題的資料中心的連接時，提供容錯移轉。 詳細資訊請參閱下方的容錯移轉機制。


FQDNS **sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com** 和sip3.pstnhub.microsoft.com **會解析** 為下列其中一個 IP 位址：
- 52.114.148.0
- 52.114.132.46
- 52.114.16.74
- 52.114.20.29
- 52.114.75.24
- 52.114.76.76
- 52.114.7.24
- 52.114.14.70

您必須在防火牆中開啟所有這些 IP 位址的埠，以允許接收和傳出流量到與來自該位址的訊號。 如果您的防火牆支援 DNS 名稱，FQDN **sip-all.pstnhub.microsoft.com** 解析為所有這些 IP 位址。 

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 環境

直接路由的連接點為下列 FQDN：

**sip.pstnhub.dod.teams.microsoft.us** - 全域 FQDN。 由於 Office 365 DoD 環境只存在於美國資料中心，因此沒有次要和環性 FQDN。

FQDN – sip.pstnhub.dod.teams.microsoft.us會解析為下列其中一個 IP 位址：

- 52.127.64.33
- 52.127.68.34

您必須在防火牆中開啟所有這些 IP 位址的埠，以允許接收和傳出流量到與來自該位址的訊號。  如果您的防火牆支援 DNS 名稱，FQDN sip.pstnhub.dod.teams.microsoft.us解析為所有這些 IP 位址。 

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High 環境

直接路由的連接點為下列 FQDN：

**sip.pstnhub.gov.teams.microsoft.us** - 全域 FQDN。 由於 GCC High 環境只存在於美國資料中心，因此沒有次要和小費 FQDN。

FQDN – sip.pstnhub.gov.teams.microsoft.us會解析為下列其中一個 IP 位址：

- 52.127.88.59
- 52.127.92.64

您必須在防火牆中開啟所有這些 IP 位址的埠，以允許接收和傳出流量到與來自該位址的訊號。  如果您的防火牆支援 DNS 名稱，FQDN sip.pstnhub.gov.teams.microsoft.us解析為所有這些 IP 位址。 

## <a name="sip-signaling-ports"></a>SIP 訊號：埠

針對提供直接路由的所有 Office 365 環境，埠需求相同：
- Microsoft 365 或 Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

您必須使用下列埠：

| 交通 | 從 | 自 | 來源埠 | 目的地埠|
| :-------- | :-------- |:-----------|:--------|:---------|
SIP/TLS| SIP Proxy | Sbc | 1024 - 65535 | 在 SBC 上定義 |
| SIP/TLS | Sbc | SIP Proxy | 在 SBC 上定義 | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>媒體流量：IP 和埠範圍

媒體流量在 SBC 和 Teams 用戶端之間流動 ，如果可直接連接可以使用，或者如果用戶端無法使用公用 IP 位址到達 SBC，則媒體流量會透過 Teams 傳輸轉場。

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>Teams 用戶端與 SBC (之間的直接媒體流量)  

用戶端必須能存取指定的埠 (請參閱) SBC 公用 IP 位址上的資料表。 

注意：如果用戶端位於內部網路中，媒體會流向 SBC 的公用 IP 位址。 您可以在 NAT 裝置上設定美髮釘釘，讓流量不會離開商業網路設備。

| 交通 | 從 | 自 | 來源埠 | 目的地埠|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | 用戶端 | Sbc | 50 000 – 50 019  | 在 SBC 上定義 |
| UDP/SRTP | Sbc | 用戶端 | 在 SBC 上定義 | 50 000 – 50 019  |


> [!NOTE]
> 如果您有可轉換用戶端來源埠的網路裝置，請確定已翻譯的埠在網路設備和 SBC 之間開啟。 

### <a name="requirements-for-using-transport-relays"></a>使用傳輸轉場的需求

傳輸轉場與媒體處理器的範圍相同， (非旁路情況下) ： 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365 和 Office 365 GCC 環境

- 52.112.0.0 /14 (IP 位址從 52.112.0.1 到 52.115.255.254) 

## <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 環境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High 環境

- 52.127.88.0/21


適用于所有環境 (Teams 傳輸轉場) 如下表所示：


| 交通 | 從 | 自 | 來源埠 | 目的地埠|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | 傳輸轉場 | Sbc | 50 000 -59 999    | 在 SBC 上定義 |
| UDP/SRTP | Sbc | 傳輸轉場 | 在 SBC 上定義 | 50 000 – 59 999, 3478, 3479     |


> [!NOTE]
> Microsoft 建議 SBC 上每個同時通話至少兩個埠。 由於 Microsoft 有兩個版本的傳輸轉場，因此需要下列專案：
> 
> - v4，只能使用埠範圍 50 000 到 59 999
> 
> - v6，適用于埠 3478、3479

目前，媒體旁路僅支援 v4 版的傳輸轉場。 我們未來將會推出 v6 的支援。 

您需要開啟埠 3478 和 3479 進行轉場。 當 Microsoft 推出 v6 傳輸轉場與媒體旁路的支援時，就不需要重新配置您的網路設備或 SBC。 

### <a name="requirements-for-using-media-processors"></a>使用媒體處理器的需求

媒體處理器一直位於語音應用程式和網頁用戶端的媒體路徑中 (例如 Edge 或 Google Chrome 中的 Teams 用戶端) 。 需求與非旁路組組相同。


媒體流量的 IP 範圍為 

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 和 Office 365 GCC 環境

- 52.112.0.0 /14 (IP 位址從 52.112.0.1 到 52.115.255.254) 

## <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 環境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High 環境

- 52.127.88.0/21

適用于所有環境 (媒體處理器的) 範圍如下表所示：

| 交通 | 從 | 自 | 來源埠 | 目的地埠|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | 媒體處理器 | Sbc | 3478、3479 和 49 152 – 53 247    | 在 SBC 上定義 |
| UDP/SRTP | Sbc | 媒體處理器 | 在 SBC 上定義 | 3478、3479 和 49 152 – 53 247     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a>設定媒體旁路和非媒體旁路的個別中繼  

如果您要從非媒體旁路移至媒體旁路，並想要在所有使用方式移為媒體旁路之前確認功能，您可以建立個別的中繼和個別的線上語音路由策略，以路由至媒體旁路，並指派給特定使用者。 

高層級組組步驟：

- 識別要測試媒體旁路的使用者。

- 使用不同的 FQDN 建立兩個不同的樹線：一個啟用媒體旁路;另一個不會。 

  兩個樹線都指向相同的 SBC。 TLS SIP 訊號的埠必須不同。 媒體的埠必須相同。

- 建立新的線上語音路由策略，並將媒體旁路路由指派給與此政策 PSTN 使用量相關聯的對應路由。

- 將新的線上語音路由策略指派給已識別以測試媒體旁路的使用者。

下列範例說明此邏輯。

| 一組使用者 | 使用者數目 | 以 OVRP 指派的中繼 FQDN | 已啟用媒體旁路 |
| :------------ |:----------------- |:--------------|:--------------|
具有非媒體旁路系統的使用者 | 980 | sbc1.contoso.com:5060 | 真
有媒體旁路的使用者 | 20 | sbc2.contoso.com:5061 | 假 | 

這兩個樹線可以指向擁有相同公用 IP 位址的同一個 SBC。 SBC 上的 TLS 訊號埠必須不同，如下圖所示。 請注意，您必須確定您的憑證支援兩個樹狀線。 在 SAN 中，您必須有兩個名稱 (sbc1.contoso.com，sbc2.contoso.com) 或萬用字元憑證。 

> [!div class="mx-imgBorder"]
> ![顯示兩個樹線可以指向具有相同公用 IP 的同一個 SBC](media/direct-routing-media-bypass-7.png)

若要瞭解如何在同一個 SBC 上設定兩條樹線，請參閱 SBC 廠商提供的檔：

 - [AudioCodes 部署檔](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 部署檔](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [功能區通訊部署檔](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems (anynode) 部署檔](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a>媒體旁路支援的用戶端端點

所有獨立的 Teams 桌面用戶端、Android 和 iOS 用戶端以及 Teams Phone 裝置都支援媒體旁路。 

對於不支援媒體旁路的所有其他端點，即使通話以旁路通話啟動，我們也會將呼叫轉換為非旁路。 這會自動發生，而且不需要系統管理員執行任何動作。 這包括商務用 Skype 3PIP 電話，以及支援在 Microsoft Edge、Google Chrome、Mozilla Firefox) 上直接路由通話 (WebRTC 用戶端的 Teams Web 用戶端。 
 
## <a name="see-also"></a>另請參閱

[設定媒體旁路搭配直接路由](direct-routing-configure-media-bypass.md)


