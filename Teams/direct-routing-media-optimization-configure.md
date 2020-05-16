---
title: 直接路由本機媒體優化
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 04/07/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: 針對直接路由設定本機媒體優化
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3da3cf243b24d0f614c05e9d09eb68796a68545
ms.sourcegitcommit: 296aeac481f901eb9d52b4f12a8c037afc49fa77
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2020
ms.locfileid: "44256488"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a>針對直接路由設定本機媒體優化

本機媒體優化的設定是以其他雲端語音功能（例如位置式路由和動態緊急通話）通用的網路設定為基礎。 若要深入瞭解網路區域、網路網站、網路子網和信任的 IP 位址，請參閱[雲端語音功能的網路設定](cloud-voice-network-settings.md)。

在您設定本機媒體優化之前，請參閱[直接路由的本機媒體優化](direct-routing-media-optimization.md)。  

若要設定本機媒體優化，必須執行下列步驟。 您可以使用 [團隊系統管理中心] 或 [PowerShell]。 如需詳細資訊，請參閱[管理您的網路拓撲](manage-your-network-topology.md)。

1. 設定使用者和 SBC 網站（如本文所述）。
2. 針對本機媒體優化設定 SBCs （視您的 SBC 供應商規格而有所不同）。

下圖顯示本文範例中所用的網路設定。

![顯示網路設定範例的圖表](media/direct-routing-media-op-9.png "網路設定範例")


## <a name="configure-the-user-and-the-sbc-sites"></a>設定使用者和 SBC 網站

若要設定使用者與 SBC 網站，您將需要：

1. [管理外部信任的 IP 位址](#manage-external-trusted-ip-addresses)。  

2. 您可以設定網路區域、網路網站和網路子網，以[定義網路拓撲](#define-the-network-topology)。

3. 將 SBC （s）指派給具有相關模式和 proxy SBC 值的網站，以[定義虛擬網路拓撲](#define-the-virtual-network-topology)。


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a>根據 SBC 廠商的規格，設定用於本機媒體優化的 SBC （s）

本文將說明 Microsoft 元件的配置。 如需 SBC 設定的相關資訊，請參閱您的 SBC 供應商檔。

下列 SBC 廠商支援本機媒體優化：

| 那裡 | 產品 |    軟體版本 |
|:------------|:-------|:-------| :-------|
| [Audiocodes](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    Mediant 500 SBC |   7.20 （256） | 
|            |  Mediant 800 SBC |   7.20 （256） | 
|            |  Mediant 2600 SBC |  7.20 （256） | 
|            |  Mediant 4000 SBC |  7.20 （256） | 
|            |  Mediant 1000B SBC | 7.20 （256） | 
|            |  Mediant 9000 SBC |  7.20 （256） | 
|            |  Mediant 虛擬版 SBC |   7.20 （256） | 
|            |  Mediant 雲端版 SBC | 7.20 （256） |
| [功能區 SBC 核心](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  SBC 5110         | 8.2  |
|            |  SBC 5210         | 8.2  |
|            |  SBC 5400         | 8.2  |
|            |  SBC 7000         | 8.2  |
|            |  SBC SWe          | 8.2  |
| [TE-系統](https://www.anynode.de/local_media_optimization/) |  anynode          | 4.0.1 + |
| [聯手](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | AP 1100 | 8.4.0.0.0 |
|        | AP 3900 | 8.4.0.0.0 |
|        | AP 4600 | 8.4.0.0.0 | 
|        | AP 6300 | 8.4.0.0.0 |
|        | AP 6350 | 8.4.0.0.0 | 
|        | VME     | 8.4.0.0.0 |


## <a name="manage-external-trusted-ip-addresses"></a>管理外部信任的 IP 位址

外部信任的 Ip 是商業網路的網際網路外部 Ip。 這些 IP 是 Microsoft 團隊用戶端連線至 Microsoft 365 時所使用的 IP 位址。 您必須針對每一個您有使用者使用本機媒體優化的網站，新增這些外部 Ip。

若要為每個網站新增公用 IP 位址，請使用 CsTenantTrustedIPAddress Cmdlet。 您可以為租使用者定義數量不受信任的 IP 位址。 如果 Microsoft 365 所看到的外部 IPs 都是 IPv4 與 IPv6 位址，則您必須新增這兩種類型的 IP 位址。 若是 IPv4，請使用 mask 32。 若是 IPv6，請使用 mask 128。 您可以在 Cmdlet 上指定不同的 MaskBits，以新增個別的外部 IP 位址和外部 IP 子網。

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


新增信任的 IP 位址範例。

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a>定義網路拓撲

本節說明如何為您的網路拓撲定義網路區域、網路網站和網路子網。

所有參數都是區分大小寫的，因此您必須確保您使用的是在安裝期間使用的相同大小寫。  （例如，GatewaySiteID 值 "越南" 和 "越南" 將會被視為不同的網站）。

### <a name="define-network-regions"></a>定義網路區域

若要定義網路區域，請使用 CsTenantNetworkRegion Cmdlet。 RegionID 參數是代表區域地理位置的邏輯名稱，沒有相依性或限制。 CentralSite <site ID> 參數是選擇性的。

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

下列範例會建立名為 APAC 的網路區域：

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a>定義網路網站

若要定義網路網站，請使用 CsTenantNetworkSite Cmdlet。 每個網路網站都必須與一個網路區域建立關聯。

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

下列範例會在 APAC 區域中建立三個新的網路網站、越南、印尼及新加坡：

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a>定義網路子網

若要定義網路子網並將它們與網路網站關聯，請使用 CsTenantNetworkSubnet Cmdlet。 每個網路子網只能與一個網站建立關聯。 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

下列範例定義三個網路子網，並將它們與三個網路網站進行關聯：越南、印尼及新加坡：

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a>定義虛擬網路拓撲 

首先，租使用者管理員使用 CsOnlinePSTNGateway Cmdlet，為每個相關的 SBC 建立新的 SBC 設定。
租使用者管理員使用 CsOnlinePSTNGateway Cmdlet 來指定 PSTN 閘道物件的網路網站，以定義虛擬網路拓朴：

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

請注意下列事項： 
   - 如果客戶只有一個 SBC，則-ProxySBC 參數必須是強制性 $null 或 SBC FQDN 值（集中 trunks 案例的中央 SBC）。
   - -MediaBypass 參數必須設定為 $true，才能支援本機媒體優化。
   - 如果 SBC 沒有 BypassMode 參數集，則不會傳送 X MS 標頭。 
   - 所有參數都區分大小寫，因此您需要確保您使用的是在安裝期間使用的相同大小寫。  （例如，GatewaySiteID 值 "越南" 和 "越南" 將會被視為不同的網站）。

下列範例會將三個 SBCs 新增到 [APAC] 區域中的 [越南]、[印尼] 和 [新加坡]，且模式總是略過：

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

注意：若要確保在同時設定本機媒體優化和位置式路由（LBR）時不間斷的操作，必須針對每個下游 SBC 將 GatewaySiteLbrEnabled 參數設定為 $true，才能啟用下游 SBCs LBR。 （Proxy SBC 不強制此設定）。

根據上述資訊，直接路由會包含三個專有的 SIP 標頭至 SIP 邀請和重新邀請，如下表所示。

如果定義了 BypassMode，則會直接在邀請和重新邀請上路由的 X MS 標頭：

| 標題名稱 | 相對值 | 註解 | 
|:------------|:-------|:-------|
| X 毫秒-UserLocation | 內部/外部 | 指出使用者是否為內部或外部使用者 |
| 要求-URI 邀請 sip： + 84439263000@VNsbc.contoso.com SIP/2。0 | SBC FQDN | 即使 SBC 未直接連線至直接佈線，也會以呼叫為目標的 FQDN |
| X 毫秒-MediaPath | 範例： proxysbc.contoso.com、VNsbc.contoso.com | 應該用於使用者與目標 SBC 之間媒體路徑的 SBCs 順序。 最後一個 SBC 永遠是最後一個 |
| X 毫秒-UserSite | usersiteID | 由租使用者管理員定義的字串 |

## <a name="call-flows"></a>通話流程 

下列顯示兩種模式的通話流程：

- [永遠略過](#always-bypass-mode)
- [僅適用于本機使用者](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a>[Always 旁路] 模式

[Always 旁路模式] 是最簡單的設定選項。 如果所有的 SBCs 都可從任何網站取得，租使用者管理員可以為所有使用者和 SBCs 設定單一網站。

在下列情況下，這些範例會顯示 [總是繞過] 模式：

- [呼出通話，且使用者與 SBC 位於相同的位置](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [輸入通話，且使用者與 SBC 位於相同的位置](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [[撥出通話] 和 [外部使用者]](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [入站通話與使用者是外部的](#inbound-calls-and-the-user-is-external-with-always-bypass)

下表顯示範例中使用的 FQDN 和 IP 位址：

| 稱 | SBC 外部 IP 位址 | SBC 內部 IP 位址 | 內部子網 | 位置 | 外部 NAT （信任的 IP） |
|:------------|:-------|:-------|:-------|:-------|:-------|
| VNsbc.contoso.com | 無 | 192.168.1.5 | 192.168.1.0/24 | 越南 | 172.16.240.110 |
| IDsbc.contoso.com | 無 | 192.168.2.5 | 192.168.2.0/24 | 印尼 | 172.16.240.120 |
| proxysbc.contoso.com | 172.16.240.133 | 192.168.3.5 | 192.168.3.0/24 | 新加坡 | 172.16.240.130 |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>[呼出通話]，而且使用者與使用永遠略過的 SBC 位於相同的位置

| 下 |    使用者 |  位置 |  通話方向 |
|:------------|:-------|:-------| :-------|
| AlwaysBypass |    內部 |  與 SBC 相同的網站 |  發 |

下表顯示使用者的設定和動作：

| 使用者物理位置| 使用者撥打或接聽電話號碼 | 使用者電話號碼  | 線上語音路由策略 | 針對 SBC 設定的模式 |
|:------------|:-------|:-------|:-------|:-------|
| 越南 | + 84 4 3926 3000 | + 84 4 5555 5555   | 優先順序1： ^ \+ 84 （\d {9} ） $-VNsbc.contoso.com <br> 優先順序2：. *-proxysbc.contoso.com   | VNsbc.contoso.com –總是略過 <br> proxysbc.contoso.com –總是略過


下圖顯示使用 [永遠繞過] 模式進行出站通話的 SIP 階梯，以及使用者與 SBC 位於相同位置的情況。

![顯示出站通話的圖表](media/direct-routing-media-op-10.png "呼出通話")

下表顯示直接路由傳送的 X MS 標頭：

| 參數 | 簡要 |
|:------------|:-------|
| 邀請 + 8443926300@VNsbc.contoso.com | 在線上語音路由策略中定義之 SBC 的目標 FQDN 是在要求 URI 中傳送 | 
| X-MS-UserLocation：內部 | 指出使用者位於公司網路內部的欄位 |
| X-MS-MediaPath： VNsbc.contoso.com |   指定用戶端必須向目標 SBC 遍歷哪個 SBC。 在這種情況下，我們一直都略過，而用戶端則是以標題中的唯一名稱傳送的目標名稱。 | 
|X-MS-UserSite：越南 |   在使用者所在的網站中指示的欄位。 |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>入站通話，且使用者與具有 Always 略過之 SBC 的位置相同

| 下 |    使用者 |  位置 |  通話方向 |
|:------------|:-------|:-------|:-------|:-------|
| AlwaysBypass |    內部 | 與 SBC 相同的網站 | 進貨 |


在撥入通話中，使用者的位置未知，而且 SBC 必須猜使用者在哪裡。 如果 guess 不正確，就需要重新邀請。 這個案例假設使用者是內部使用者，媒體可以直接流向，而且不需要進一步的動作（重新邀請）。
透過提供 Record 路由和連絡人欄位，連線至直接路由服務的 SBC 會報告原始的 SBC 位置。 根據這些欄位，媒體路徑是透過直接路由來計算。

注意：假設使用者可以有多個端點，就不可能支援183。 在這種情況下，直接路由將永遠使用180鈴聲。 

下圖顯示入站通話中 AlwaysBypass 模式的 SIP 階梯，且使用者與 SBC 位於相同的位置。

![顯示 SIP 階梯的圖表](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a>[呼出通話] 與 [永遠略過] 的使用者是外部的

| 下 |    使用者 |  網站 |  通話方向
|:------------|:-------|:-------|:-------|
AlwaysBypass |  外來 |  不適用 | 發 |


下圖顯示使用 AlwaysBypass 模式的出站呼叫的 SIP 階梯，且使用者是外部的：

![顯示 SIP 階梯的圖表](media/direct-routing-media-op-12.png)

下表顯示由直向路由服務傳送的 X MS 標頭：

| 參數 |   簡要 |
|:------------|:-------|
|邀請 + 8443926300@VNsbc.contoso.com | 在線上語音路由策略中定義之 SBC 的目標 FQDN 會在要求 URI 中傳送。|
| X-MS-UserLocation：外部 | 指出使用者位於公司網路以外的欄位。 |
| X-MS-MediaPath： proxysbc.contoso.com，VNsbc.contoso.com    | 指定用戶端必須向目標 SBC 遍歷哪個 SBC。 在這種情況下，我們一直都略過，而用戶端則是外部的。 |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a>輸入通話，且使用者是使用永遠略過的外部

| 下 | 使用者 | 網站 |  通話方向 |
|:------------|:-------|:-------|:-------|
AlwaysBypass |  外來 |  不適用 |   進貨 |

如果是撥入通話，則連接至直接路由的 SBC 必須傳送重新邀請（預設會提供本機媒體候選人）（如果使用者是外部的位置）。  X-MediaPath 是根據記錄路由與指定的 SBC 使用者來計算。

下圖顯示使用 AlwaysBypass 模式的入站呼叫的 SIP 階梯，且使用者是外部的。

![顯示 SIP 階梯的圖表](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a>僅適用于 [本機使用者] 模式

只有在使用者與 SBC 位於相同的位置時，才會提供目標 SBC 的本機媒體候選項目。 在其他所有情況下，媒體會透過 proxy SBC 的內部或外部 IP 來傳送。

描述下列案例：

- [呼出通話，且使用者與 SBC 位於相同的位置](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [輸入通話，且使用者與 SBC 位於相同的位置](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [使用者與 SBC 不在同一個位置，但在商業網路中](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [輸入通話與使用者是內部的，但不在與 SBC 相同的位置](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

下表顯示最終使用者設定和動作：

| 使用者物理位置 |  使用者撥打或接聽電話號碼 |  使用者電話號碼 | 線上語音路由策略 |   針對 SBC 設定的模式 |
|:------------|:-------|:-------|:-------|:-------|
| 越南 | + 84 4 3926 3000 |  + 84 4 5555 5555 | 優先順序1： ^ \+ 84 （\d {9} ） $-VNsbc.contoso.com <br> 優先順序2：. *-proxysbc.contoso.com | VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com-Always 旁路 |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>呼出通話，且使用者與 SBC 在相同的位置，且僅適用于本機使用者

| 下 | 使用者 | 網站 | 通話方向 |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   內部 |與 SBC 相同   | 發 |

下圖顯示使用 OnlyForLocalUsers 模式的撥出電話，且使用者與 SBC 位於相同的位置。 [當使用者位於與 SBC 相同的位置時，在呼出通話](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)中會顯示相同的流程。

![顯示 SIP 階梯的圖表](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>輸入通話，且使用者與 SBC 在相同的位置，且僅適用于本機使用者

| 下 | 使用者 | 網站 | 通話方向 |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   內部 | 與 SBC 相同 | 進貨 |

下圖顯示使用 OnlyForLocalUsers 模式的入站通話，且使用者與 SBC 位於同一個位置。 [當使用者與 SBC 位於同一個位置時](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)，這就是與入站通話中所示的相同流程。

![顯示 SIP 階梯的圖表](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a>使用者與 SBC 不在同一個位置，但位於公司網路中，僅適用于本機使用者

| 下 | 使用者 | 網站 |通話方向 |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers  | 內部 |   SBC 不同 | 發 |

[直接路由] 會根據在 SBC 上設定的使用者和模式的已報告位置來計算 X MediaPath。


下圖顯示使用 OnlyForLocalUsers 模式的撥出電話，以及與 SBC 不在相同位置的內部使用者。

![顯示 SIP 階梯的圖表](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a>撥入通話且使用者是內部使用者，但不與僅供本機使用者使用的 SBC 位置相同

| 下 |    使用者 |  網站 |  通話方向 |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers | 內部 |    SBC 不同 |    進貨 |

下圖顯示使用 OnlyForLocalUsers 模式的入站通話，以及與 SBC 不在相同位置的內部使用者。

![顯示 SIP 階梯的圖表](media/direct-routing-media-op-17.png)









