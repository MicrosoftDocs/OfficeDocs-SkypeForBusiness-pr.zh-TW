---
title: 直接路由本地媒體優化
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
description: 設定直接路由的當地媒體優化
appliesto:
- Microsoft Teams
ms.openlocfilehash: ecbbb4f01267265f9f1041e7d51652d063ced353
ms.sourcegitcommit: 2aea6ec07149a3054ee4434c8a0bffabf1a16d25
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46576985"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a>設定直接路由的當地媒體優化

Local Media 優化的設定是以其他雲端語音功能所常見的網路設定為基礎，例如Location-Based路由和動態緊急電話。 若要深入瞭解網路區域、網路網站、網路子網和信任的 IP 位址，請參閱雲端 [語音功能的網路設定](cloud-voice-network-settings.md)。

設定 Local Media 優化之前，請參閱直接路由 [的當地媒體優化](direct-routing-media-optimization.md)。  

若要設定 Local Media 優化，需要下列步驟。 您可以使用系統管理Teams PowerShell。 詳細資料請參閱 [管理您的網路拓撲](manage-your-network-topology.md)。

1. 設定使用者和 SBC 網站 (如本文所述) 。
2. 根據 SBC 廠商規格 (設定 SBC 本地媒體優化) 。

下圖顯示本文中範例中使用的網路設定。

![顯示網路設定範例的圖表](media/direct-routing-media-op-9.png "範例的網路設定")


## <a name="configure-the-user-and-the-sbc-sites"></a>設定使用者和 SBC 網站

若要設定使用者和 SBC 網站，您必須：

1. [管理外部信任的 IP 位址](#manage-external-trusted-ip-addresses)。  

2. [建立網路區域、](#define-the-network-topology) 網路網站和網路子網，以定義網路拓撲。

3. [使用相關的模式](#define-the-virtual-network-topology) 和 proxy SBC 值 (SBC) 網站 (定義) 拓撲。


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a>根據 SBC () 設定 SBC 的當地語系化媒體優化選項

本文將說明 Microsoft 元件的組組。 有關 SBC 組建的資訊，請參閱您的 SBC 廠商檔。

下列 SBC 廠商支援本地媒體優化：

| 供應商 | 產品 |    軟體版本 |
|:------------|:-------|:-------|
| [音訊代碼](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    Mediant 500 SBC |   7.20A.256 | 
|            |  Mediant 800 SBC |   7.20A.256 | 
|            |  Mediant 2600 SBC |  7.20A.256 | 
|            |  Mediant 4000 SBC |  7.20A.256 | 
|            |  Mediant 1000B SBC | 7.20A.256 | 
|            |  Mediant 9000 SBC |  7.20A.256 | 
|            |  Mediant Virtual Edition SBC |   7.20A.256 | 
|            |  Mediant Cloud Edition SBC | 7.20A.256 |
| [功能區 SBC Core](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  SBC 5110         | 8.2  |
|            |  SBC 5210         | 8.2  |
|            |  SBC 5400         | 8.2  |
|            |  SBC 7000         | 8.2  |
|            |  SBC SWe          | 8.2  |
| [功能區 SBC Edge](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  SBC SWe Lite | 8.1.5 |
|               | SBC 1000 | 8.1.5  |
|               | SBC 2000 | 8.1.5  |
| [TE-SYSTEMS](https://www.anynode.de/local_media_optimization/) |  anynode          | 4.0.1+ |
| [甲骨文](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | AP 1100 | 8.4.0.0.0 |
|        | AP 3900 | 8.4.0.0.0 |
|        | AP 4600 | 8.4.0.0.0 | 
|        | AP 6300 | 8.4.0.0.0 |
|        | AP 6350 | 8.4.0.0.0 | 
|        | Vme     | 8.4.0.0.0 |


## <a name="manage-external-trusted-ip-addresses"></a>管理外部信任的 IP 位址

外部信任的 IP 是商業網路的網際網路外部 IP。 這些 IP 是用戶端在Microsoft Teams時所使用的 IP 位址Microsoft 365。 您必須針對每個使用 Local Media 優化的使用者，新增這些外部 IP。

若要新增每個網站的公用 IP 位址，請使用 New-CsTenantTrustedIPAddress Cmdlet。 您可以為租使用者定義無限個信任的 IP 位址。 如果使用者看到的外部 IP Microsoft 365 IPv4 和 IPv6 位址，您必須新增這兩種類型的 IP 位址。 針對 IPv4，請使用遮罩 32。 針對 IPv6，請使用遮罩 128。 您可以在 Cmdlet 上指定不同的 MaskBit，以新增個別的外部 IP 位址和外部 IP 子網。

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


新增信任 IP 位址的範例。

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a>定義網路拓撲

本節說明如何定義網路拓撲的網路區域、網路網站和網路子網。

所有參數都是區分大小寫的，因此您必須確保您使用的大小寫與設定期間所使用的大小寫相同。   (例如，GatewaySiteID 值「越南」和「越南」會視為不同的網站。) 

### <a name="define-network-regions"></a>定義網路區域

若要定義網路區域，請使用 New-CsTenantNetworkRegion Cmdlet。 RegionID 參數是一個邏輯名稱，代表地區的地理位置，而且沒有相依性或限制。 CentralSite <site ID> 參數為選擇性。

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

下列範例會建立名為 APAC 的網路區域：

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a>定義網路網站

若要定義網路網站，請使用 New-CsTenantNetworkSite Cmdlet。 每個網路網站都必須與網路區域相關聯。

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

下列範例在亞太地區建立三個新網路網站，越南、印尼和新加坡：

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a>定義網路子網

若要定義網路子網並將其與網路網站建立關聯，請使用 New-CsTenantNetworkSubnet Cmdlet。 每個網路子網只能與一個網站建立關聯。 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

下列範例定義三個網路子網，並將它們與三個網路網站建立關聯：越南、印尼和新加坡：

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a>定義虛擬網路拓撲 

首先，租使用者系統管理員會使用 Cmdlet 建立每個相關 SBC 的新 SBC New-CsOnlinePSTNGateway組。
租使用者系統管理員使用 Cmdlet 指定 PSTN 閘道物件的網路網站，以定義Set-CsOnlinePSTNGateway拓撲：

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

注意下列事項： 
   - 如果客戶有單一 SBC，則 -ProxySBC 參數必須是強制 $null 或 SBC FQDN 值 (集中式主幹案例分析) 。
   - -MediaBypass 參數必須設為 $true才能支援 Local Media 優化。
   - 如果 SBC 未設定 -BypassMode 參數，將不會送出 X-MS 標頭。 
   - 所有參數都是區分大小寫的，因此您必須確保您使用的大小寫與設定期間所使用的大小寫相同。   (例如，GatewaySiteID 值「越南」和「越南」會視為不同的網站。) 

下列範例會將三個 SBC 新越南 APAC 地區的網路網站中，且模式永遠會忽略：

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

注意：若要確保同時設定本地媒體優化和 Location-Based 路由 (LBR) 時不間斷的作業，必須將 GatewaySiteLbrEnabled 參數設定為 $true，讓 LBR 啟用下游 SBC。  (Proxy SBC.) 

根據上述資訊，直接路由會包含三個專屬 SIP 標題至 SIP 邀請和重新邀請，如下表所示。

如果已定義 BypassMode，在邀請和 Re-Invites直接路由中引入的 X-MS 標頭：

| 標題名稱 | 值 | 註解 | 
|:------------|:-------|:-------|
| X-MS-UserLocation | 內部/外部 | 指出使用者是內部使用者還是外部使用者 |
| Request-URI INVITE sip： +84439263000@VNsbc.contoso.com SIP /2.0 | SBC FQDN | 目標為通話的 FQDN，即使 SBC 未直接連接到直接路由 |
| X-MS-MediaPath | 範例：proxysbc.contoso.com、VNsbc.contoso.com | 應該用於使用者和目標 SBC 之間媒體路徑的 SBC 順序。 最後一個 SBC 永遠為最後一個 |
| X-MS-UserSite | usersiteID | 租使用者系統管理員定義的字串 |

## <a name="call-flows"></a>通話流程 

下列顯示兩種模式的通話流程：

- [一直忽略](#always-bypass-mode)
- [僅適用于當地使用者](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a>永遠忽略模式

永遠忽略模式是最簡單的設定選項。 如果所有 SBC 都可以從任何網站取得，租使用者系統管理員可以設定所有使用者和 SBC 的單一網站。

下列範例顯示下列案例的一直忽略模式：

- [外發通話與使用者位於 SBC 相同的位置](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [來電和使用者位於 SBC 相同的位置](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [外接通話和使用者是外部使用者](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [來電和使用者是外部使用者](#inbound-calls-and-the-user-is-external-with-always-bypass)

下表顯示範例中使用的 FQDN 和 IP 位址：

| Fqdn | SBC 外部 IP 位址 | SBC 內部 IP 位址 | 內部子網 | 位置 | 外部 NAT (信任的 IP)  |
|:------------|:-------|:-------|:-------|:-------|:-------|
| VNsbc.contoso.com | 無 | 192.168.1.5 | 192.168.1.0/24 | 越南 | 172.16.240.110 |
| IDsbc.contoso.com | 無 | 192.168.2.5 | 192.168.2.0/24 | 印尼 | 172.16.240.120 |
| proxysbc.contoso.com | 172.16.240.133 | 192.168.3.5 | 192.168.3.0/24 | 新加坡 | 172.16.240.130 |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>外發通話和使用者位於與 SBC 相同的位置，且有一直旁路

| 模式 |    使用者 |  位置 |  通話方向 |
|:------------|:-------|:-------| :-------|
| AlwaysBypass |    內部 |  與 SBC 相同的網站 |  出境 |

下表顯示使用者組組和動作：

| 使用者實際位置| 使用者撥打或接收來電到/從號碼 | 使用者電話號碼  | 線上語音路由策略 | 為 SBC 所配置的模式 |
|:------------|:-------|:-------|:-------|:-------|
| 越南 | +84 4 3926 3000 | +84 4 5555 5555   | 優先順序 1：^ \+ 84 (\d) {9} $ -VNsbc.contoso.com <br> 優先順序 2：.* - proxysbc.contoso.com   | VNsbc.contoso.com – 永遠忽略 <br> proxysbc.contoso.com – 永遠忽略


下圖顯示使用 Always 旁路模式的外發通話的 SIP 梯級，以及使用者與 SBC 相同的位置。

![顯示外線通話的圖表](media/direct-routing-media-op-10.png "外接通話")

下表顯示直接路由傳送的 X-MS 標頭：

| 參數 | 解釋 |
|:------------|:-------|
| 邀請 +8443926300@VNsbc.contoso.com | 在線上語音路由策略中定義的 SBC 目標 FQDN 會以要求 URI 傳送 | 
| X-MS-UserLocation：內部 | 該欄位表示使用者位於公司網路內 |
| X-MS-MediaPath：VNsbc.contoso.com |   指定用戶端必須橫穿到目標 SBC 的 SBC。 在此例中，由於我們一直有旁路，而且用戶端是內部的目標名稱，因此會以標題中的唯一名稱來送出。 | 
|X-MS-UserSite：越南 |   使用者所在的網站內所指示的欄位。 |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>來電和使用者位於 SBC 的同一個位置，且有一直旁路

| 模式 |    使用者 |  位置 |  通話方向 |
|:------------|:-------|:-------|:-------|:-------|
| AlwaysBypass |    內部 | 與 SBC 相同的網站 | 入境 |


在輸入通話中，使用者的位置不明，SBC 必須猜測使用者的位置。 如果猜測不正確，將會需要重新邀請。 此案例假設使用者是內部使用者，媒體可以直接流動，因此重新邀請 (不需要執行) 。
連結至直接路由服務的 SBC 會提供 Record-Route和連絡人欄位，以報告原始 SBC 位置。 根據這些欄位，媒體路徑是由直接路由計算。

注意：由於使用者可以有多個端點，因此無法支援 183。 在這種情況下，直接路由一定會使用 180 響鈴。 

下圖顯示使用 AlwaysBypass 模式進行輸入通話的 SIP 梯級，且使用者的位置與 SBC 相同。

![顯示 SIP 梯形圖](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a>外接通話，且使用者是外部使用者，且使用 Always Bypass

| 模式 |    使用者 |  網站 |  通話方向
|:------------|:-------|:-------|:-------|
AlwaysBypass |  外部 |  不適用 | 出境 |


下圖顯示使用 AlwaysBypass 模式的外發通話的 SIP 梯級，且使用者為外部使用者：

![顯示 SIP 梯形圖](media/direct-routing-media-op-12.png)

下表顯示直接路由服務傳送的 X-MS 標頭：

| 參數 |   解釋 |
|:------------|:-------|
|邀請 +8443926300@VNsbc.contoso.com | 在線上語音路由策略中定義的 SBC 目標 FQDN 會傳送至要求 URI。|
| X-MS-UserLocation：外部 | 該欄位表示使用者位於公司網路外部。 |
| X-MS-MediaPath：proxysbc.contoso.com，VNsbc.contoso.com    | 指定用戶端必須橫穿到目標 SBC 的 SBC。 在此案例中，我們一直有旁路，而且用戶端是外部的。 |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a>輸入通話，且使用者是外部使用者，且使用一直旁路

| 模式 | 使用者 | 網站 |  通話方向 |
|:------------|:-------|:-------|:-------|
AlwaysBypass |  外部 |  不適用 |   入境 |

如果是輸入通話，連接到直接路由的 SBC 預設需要傳送重新邀請 (如果使用者的位置是外部) 則一向會提供本地媒體候選者。  X-MediaPath 是根據指定Record-Route SBC 使用者所計算。

下圖顯示使用 AlwaysBypass 模式的輸入通話的 SIP 梯級，且使用者是外部使用者。

![顯示 SIP 梯形圖](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a>僅適用于本地使用者模式

只有在使用者與 SBC 位於同一個位置時，才能提供目標 SBC 的當地媒體候選者。 在所有其他情況下，媒體會透過 Proxy SBC 的內部或外部 IP 進行。

描述下列案例：

- [外發通話與使用者位於 SBC 相同的位置](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [來電和使用者位於 SBC 相同的位置](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [使用者與 SBC 不在同一個位置，但位於公司網路中](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [來電和使用者是內部通話，但與 SBC 不在同一個位置](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

下表顯示使用者組組和動作：

| 使用者實際位置 |  使用者撥打或接收來電到/從號碼 |  使用者電話號碼 | 線上語音路由策略 |   為 SBC 所配置的模式 |
|:------------|:-------|:-------|:-------|:-------|
| 越南 | +84 4 3926 3000 |  +84 4 5555 5555 | 優先順序 1：^ \+ 84 (\d) {9} $ -VNsbc.contoso.com <br> 優先順序 2：.* - proxysbc.contoso.com | VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – 永遠忽略 |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>外發通話和使用者位於 SBC 的同一個位置，且只供當地使用者使用

| 模式 | 使用者 | 網站 | 通話方向 |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   內部 |與 SBC 相同   | 出境 |

下圖顯示 OnlyForLocalUsers 模式的外發通話，而使用者的位置與 SBC 相同。 當使用者位於與 SBC 相同的位置時，此流程會顯示在外接 [通話中](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)。

![顯示 SIP 梯形圖](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>來電和使用者位於 SBC 的同一個位置，且僅適用于當地使用者

| 模式 | 使用者 | 網站 | 通話方向 |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   內部 | 與 SBC 相同 | 入境 |

下圖顯示使用 OnlyForLocalUsers 模式的輸入通話，而使用者的位置與 SBC 相同。 當使用者位於與 SBC 相同的位置時，此流程與 [輸入通話中顯示的流程相同](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)。

![顯示 SIP 梯形圖](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a>使用者與 SBC 不在同一個位置，但位於公司網路中，只有當地使用者才能使用

| 模式 | 使用者 | 網站 |通話方向 |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers  | 內部 |   與 SBC 不同 | 出境 |

直接路由會根據使用者的報告位置，以及 SBC 上所配置的模式來計算 X-MediaPath。


下圖顯示使用 OnlyForLocalUsers 模式的外發通話，以及與 SBC 不在同一個位置的內部使用者。

![顯示 SIP 梯形圖](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a>輸入通話與使用者為內部，但位置與 SBC 不在同一個位置，只供當地使用者使用

| 模式 |    使用者 |  網站 |  通話方向 |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers | 內部 |    與 SBC 不同 |    入境 |

下圖顯示使用 OnlyForLocalUsers 模式的輸入通話，以及與 SBC 不在同一個位置的內部使用者。

![顯示 SIP 梯形圖](media/direct-routing-media-op-17.png)









