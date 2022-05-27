---
title: 設定直接路由的本機媒體優化
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
description: 設定直接路由的本機媒體優化
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58cf5f560a22a58cb76ea28389d0dce1e3b3f4fb
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674875"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a>設定直接路由的本機媒體優化

本機媒體優化的設定是以其他雲端語音功能常見的網路設定為基礎，例如Location-Based路由和動態緊急通話。 若要深入瞭解網路區域、網路網站、網路子網和受信任的 IP 位址，請參閱 [雲端語音功能的網路設定](cloud-voice-network-settings.md)。

設定本機媒體優化之前，請參閱 [直接路由的本機媒體優化](direct-routing-media-optimization.md)。

若要設定本機媒體優化，必須執行下列步驟。 您可以使用 Teams 管理員 Center 或 PowerShell。 如需詳細資料，請 [參閱管理您的網路拓撲](manage-your-network-topology.md)。

1. 如本文) 所述，設定使用者和 SBC 網站 (。
2. 根據您的 SBC 廠商規格 () 設定本機媒體優化的 SBC。

下圖顯示本文範例中所使用的網路設定。

> [!div class="mx-imgBorder"]
> ![顯示範例之網路設定的圖表。](media/direct-routing-media-op-9.png "範例的網路設定")

## <a name="configure-the-user-and-the-sbc-sites"></a>設定使用者和 SBC 網站

若要設定使用者和 SBC 網站，您必須：

1. [管理外部信任的 IP 位址](#manage-external-trusted-ip-addresses)。

2. [設定網路](#define-the-network-topology) 區域、網路網站和網路子網來定義網路拓撲。

3. 將 SBC (的) 指派給具有相關模式和 Proxy SBC 值的網站 () ，以[定義虛擬網路](#define-the-virtual-network-topology)拓撲。

> [!NOTE]
> 本機媒體優化仰賴被偵測為外部或內部的用戶端位置，相對於連線到直接路由 (DR) 會話框線控制器 (SBC) 內部介面的公司網路。
> 在偵測到客戶網路外部的用戶端點時，分割通道 VPN 案例中，即使用戶端可以連線到客戶直接路由 SBC 的內部介面，Microsoft 仍會將外部位置訊號傳送到 SBC。 使用本機媒體優化直接路由的客戶可能會遇到長時間通話設定時間，在某些情況下，從 PSTN 接聽來電時不會出現音訊。
> 若要避免此問題，VPN 系統管理員必須封鎖遠端 VPN 使用者和直接路由 SBC 內部介面之間的存取。

## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a>根據 SBC 廠商規格設定本機媒體優化的 SBC () 

本文將說明 Microsoft 元件的設定。 如需 SBC 設定的相關資訊，請參閱您的 SBC 廠商檔。 如需哪些 SBC 廠商支援本機媒體優化的相關資訊，請參閱 [通過直接路由認證的會話框線控制器](direct-routing-border-controllers.md)。

## <a name="manage-external-trusted-ip-addresses"></a>管理外部信任的 IP 位址

外部信任的 IP 是商業網路的網際網路外部 IP。 這些 IP 是Microsoft Teams用戶端連線至Microsoft 365時所使用的 IP 位址。 您必須為每個使用者使用本機媒體優化的網站新增這些外部 IP。

若要新增每個網站的公用 IP 位址，請使用New-CsTenantTrustedIPAddress Cmdlet。 您可以為租使用者定義無限數目的受信任 IP 位址。 如果Microsoft 365看到的外部 IP 同時為 IPv4 和 IPv6 位址，您必須新增這兩種類型的 IP 位址。 對於 IPv4，請使用遮罩 32。 若是 IPv6，請使用遮罩 128。 您可以在 Cmdlet 上指定不同的 MaskBits，藉此同時新增個別外部 IP 位址和外部 IP 子網。

```powershell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```

新增信任 IP 位址的範例。

```powershell
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```

## <a name="define-the-network-topology"></a>定義網路拓撲

本節說明如何定義網路拓撲的網路區域、網路網站和網路子網。

所有參數都區分大小寫，因此您必須確定使用的大小寫與設定期間使用的大小寫相同。   (例如，GatewaySiteID 值 「越南」 和 「vietnam」 會被視為不同的網站。) 

### <a name="define-network-regions"></a>定義網路區域

若要定義網路區域，請使用New-CsTenantNetworkRegion Cmdlet。 RegionID 參數是一個邏輯名稱，代表區域的地理位置，沒有相依性或限制。 CentralSite `<site ID>` 參數為選用。

```powershell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>
```

下列範例會建立名為 APAC 的網路區域：

```powershell
New-CsTenantNetworkRegion -NetworkRegionID "APAC"
```

### <a name="define-network-sites"></a>定義網路網站

若要定義網路網站，請使用New-CsTenantNetworkSite Cmdlet。 每個網路網站都必須與網路區域建立關聯。

```powershell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

下列範例會在 APAC 地區建立三個新的網路網站，越南、印尼和新加坡：

```powershell
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a>定義網路子網

若要定義網路子網並將它們與網路網站建立關聯，請使用New-CsTenantNetworkSubnet Cmdlet。 每個網路子網只能與一個網站相關聯。

```powershell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

下列範例定義三個網路子網，並將它們與三個網路網站建立關聯：越南、印尼和新加坡：

```powershell
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID "Vietnam"
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID "Indonesia"
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID "Singapore"
```

## <a name="define-the-virtual-network-topology"></a>定義虛擬網路拓撲

首先，租使用者系統管理員會使用 New-CsOnlinePSTNGateway Cmdlet，為每個相關的 SBC 建立新的 SBC 設定。
租使用者系統管理員使用 Set-CsOnlinePSTNGateway Cmdlet 來指定 PSTN 閘道物件的網路網站，藉此定義虛擬網路拓撲：

```powershell
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

注意下列事項：

- 如果客戶擁有單一 SBC，則 -ProxySBC 參數必須是具有集中式主幹案例的強制$null或 SBC FQDN 值 (集中式主幹) 。
- -MediaBypass 參數必須設定為 $true，才能支援本機媒體優化。
- 如果 SBC 未設定 -BypassMode 參數，將不會傳送 X-MS 標頭。
- 所有參數都區分大小寫，因此您必須確定使用的大小寫與設定期間使用的大小寫相同。   (例如，GatewaySiteID 值 「越南」 和 「vietnam」 會被視為不同的網站。) 

下列範例將三個 SBC 新增至 APAC 地區的網路網站越南、印尼和新加坡，且模式一律略過：

```powershell
Set-CSOnlinePSTNGateway -Identity "proxysbc.contoso.com" -GatewaySiteID "Singapore" -MediaBypass $true -BypassMode "Always" -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity "VNsbc.contoso.com" -GatewaySiteID "Vietnam" -MediaBypass $true -BypassMode "Always" -ProxySBC "proxysbc.contoso.com"

Set-CSOnlinePSTNGateway -Identity "IDsbc.contoso.com" -GatewaySiteID "Indonesia" -MediaBypass $true -BypassMode "Always" -ProxySBC "proxysbc.contoso.com"
```

> [!NOTE]
> 若要確保當同時設定本機媒體優化和Location-Based路由 (LBR) 時，LBR 作業不會中斷，您必須將 GatewaySiteLbrEnabled 參數設定為每個下游 SBC 的$true，以針對 LBR 啟用下限 SB。  (Proxy SBC.) 此設定並非必要設定

根據上述資訊，直接路由將包含三個 SIP 標頭至 SIP 邀請和重新邀請，如下表所示。

在 [邀請] 上的直接路由中導入 X-MS 標題，如果已定義 BypassMode，Re-Invites：

|頁首名稱|值|註解|
|---|---|---|
|X-MS-UserLocation|內部/外部|指出使用者是否為內部或外部|
|Request-URI INVITE sip： +84439263000@VNsbc.contoso.com SIP /2.0|SBC FQDN|即使 SBC 未直接連線到直接路由，也會以通話為目標的 FQDN|
|X-MS-MediaPath|範例：proxysbc.contoso.com、VNsbc.contoso.com|應用於使用者與目標 SBC 之間媒體路徑的 SBC 順序。 最後的 SBC 永遠都是最後一個|
|X-MS-UserSite|usersiteID|由租使用者系統管理員定義的字串|

## <a name="call-flows"></a>通話流量

下列顯示兩種模式的通話流量：

- [一律略過](#always-bypass-mode)
- [僅適用于本機使用者](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a>一律略過模式

[永遠略過模式] 是最簡單的設定選項。 如果所有 SB 都可從任何網站連線，租使用者系統管理員可以為所有使用者和 SBC 設定單一網站。

範例顯示下列案例的一律略過模式：

- [撥出電話，且使用者與 SBC 位於同一個位置](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [輸入通話，且使用者與 SBC 位於同一個位置](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [撥出電話，且使用者是外部使用者](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [輸入電話，且使用者是外部使用者](#inbound-calls-and-the-user-is-external-with-always-bypass)

下表顯示範例中使用的 FQDN 和 IP 位址：

|FQDN|SBC 外部 IP 位址|SBC 內部 IP 位址|內部子網|位置|外部 NAT (信任的 IP) |
|---|---|---|---|---|---|
|VNsbc.contoso.com|無|192.168.1.5|192.168.1.0/24|越南|172.16.240.110|
|IDsbc.contoso.com|無|192.168.2.5|192.168.2.0/24|印尼|172.16.240.120|
|proxysbc.contoso.com|172.16.240.133|192.168.3.5|192.168.3.0/24|新加坡|172.16.240.130|

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>撥出電話，且使用者與 SBC 使用 Always Bypass 位於同一個位置

|模式|使用者|位置|撥號方向|
|---|---|---|---|
|AlwaysBypass|內部|與 SBC 相同的網站|出境|

下表顯示使用者設定和動作：

|使用者實體位置|使用者撥打或接聽來電至/接聽號碼|使用者電話號碼|線上語音路由原則|為 SBC 設定模式|
|---|---|---|---|---|
|越南|+84 4 3926 3000|+84 4 5555 5555|優先順序 1：^ \+ 84 (\d {9}) $ -VNsbc.contoso.com <br> 優先順序 2：.* - proxysbc.contoso.com|VNsbc.contoso.com – 永遠略過 <br> proxysbc.contoso.com – 永遠略過|

下圖顯示輸出通話的 SIP 標準為 Always 略過模式，且使用者與 SBC 位於同一個位置。

> [!div class="mx-imgBorder"]
> ![顯示撥出通話的圖表。](media/direct-routing-media-op-10.png "撥出電話")

下表顯示由直接路由傳送的 X-MS 標頭：

|參數|解釋|
|---|---|
|邀請 +8443926300@VNsbc.contoso.com|如線上語音路由原則中所定義，SBC 的目標 FQDN 會在要求 URI 中傳送|
|X-MS-UserLocation：內部|指出使用者位於公司網路內的欄位|
|X-MS-MediaPath：VNsbc.contoso.com|指定用戶端必須周轉至目標 SBC 的 SBC。 在此情況下，因為我們有 Always Bypass，且用戶端是內部傳送為標頭中的唯一名稱的目標名稱。|
|X-MS-UserSite：越南|使用者所在網站內所指示的欄位。|

#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>輸入電話，且使用者與 SBC 使用 Always Bypass 位於同一個位置

|模式|使用者|位置|撥號方向|
|---|---|---|---|---|
|AlwaysBypass|內部|與 SBC 相同的網站|入境|

在輸入通話中，使用者的位置為未知，且 SBC 必須猜測使用者的位置。 如果猜測不正確，則需要重新邀請。 此案例假設使用者是內部使用者、媒體可以直接流程，而且不需要進行其他動作 (重新邀請) 。
連線至直接路由服務的 SBC 會提供Record-Route和連絡人欄位，以回報原始 SBC 位置。 根據這些欄位，媒體路徑是由直接路由計算。

注意：如果使用者可以有多個端點，就無法支援 183。 在此情況下，直接路由一律會使用 180 響鈴。

下圖顯示搭配 AlwaysBypass 模式進行輸入通話的 SIP，且使用者與 SBC 位於同一個位置。

> [!div class="mx-imgBorder"]
> ![顯示 SIP 記憶體的圖表。](media/direct-routing-media-op-11.png)

#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a>撥出電話，且使用者使用 Always Bypass 的外部

|模式|使用者|網站|撥號方向
|---|---|---|---|
|AlwaysBypass|外部|不適用|出境|

下圖顯示以 AlwaysBypass 模式輸出通話的 SIP 預留位置，且使用者是外部使用者：

> [!div class="mx-imgBorder"]
> ![圖表顯示 SIP 的特性。](media/direct-routing-media-op-12.png)

下表顯示直接路由服務所傳送的 X-MS 標頭：

|參數|解釋|
|---|---|
|邀請 +8443926300@VNsbc.contoso.com|如線上語音路由原則中所定義，SBC 的目標 FQDN 會在要求 URI 中傳送。|
|X-MS-UserLocation：外部|表示使用者位於公司網路外部的欄位。|
|X-MS-MediaPath：proxysbc.contoso.com、VNsbc.contoso.com|指定用戶端必須周轉至目標 SBC 的 SBC。 在此情況下，因為我們有 Always Bypass，且用戶端是外部用戶端。|

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a>輸入電話，且使用者使用 Always Bypass 的外部電話

|模式|使用者|網站|撥號方向|
|---|---|---|---|
|AlwaysBypass|外部|不適用|入境|

對於輸入通話，連線到直接路由的 SBC 預設需要傳送重新邀請 (，如果使用者的位置是外部媒體，一律會提供本機媒體候選項目) 。  X-MediaPath 是根據Record-Route和指定的 SBC 使用者來計算。

下圖顯示具有 AlwaysBypass 模式之輸入通話的 SIP 預留位置，且使用者是外部使用者。

> [!div class="mx-imgBorder"]
> ![再次顯示 SIP 的圖表。](media/direct-routing-media-op-13.png)

### <a name="only-for-local-users-mode"></a>僅適用于本機使用者模式

只有在使用者與 SBC 位於相同位置時，才能提供目標 SBC 的本機媒體候選字。 在所有其他情況下，媒體會流經 Proxy SBC 的內部或外部 IP。

以下是描述的案例：

- [撥出電話，且使用者與 SBC 位於同一個位置](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [輸入通話，且使用者與 SBC 位於同一個位置](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [使用者的位置與 SBC 不同，但位於公司網路中](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [輸入通話，且使用者是內部使用者，但位置與 SBC 不同](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

下表顯示使用者設定和動作：

|使用者實體位置|使用者撥打或接聽來電至/接聽號碼|使用者電話號碼|線上語音路由原則|為 SBC 設定模式|
|---|---|---|---|---|
|越南|+84 4 3926 3000|+84 4 5555 5555|優先順序 1：^ \+ 84 (\d {9}) $ -VNsbc.contoso.com <br> 優先順序 2：.* - proxysbc.contoso.com|VNsbc.contoso.com – 只有ForLocalUsers Proxysbc.contoso.com – 永遠略過|

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>撥出電話與使用者所在的位置與 SBC 相同，僅限本機使用者

|模式|使用者|網站|撥號方向|
|---|---|---|---|
|OnlyForLocalUsers|內部|與 SBC 相同|出境|

下圖顯示只有ForLocalUsers 模式的撥出通話，且使用者與 SBC 位於同一個位置。 當 [使用者與 SBC 位於同一個位置時，就會在撥出通話中顯示相同的](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)流程。

> [!div class="mx-imgBorder"]
> ![圖表再次顯示 SIP 自訂。](media/direct-routing-media-op-14.png)

#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>輸入電話與使用者所在的位置與 SBC 相同，僅適用于本機使用者

|模式|使用者|網站|撥號方向|
|---|---|---|---|
|OnlyForLocalUsers|內部|與 SBC 相同|入境|

下圖顯示只有ForLocalUsers 模式的輸入通話，且使用者與 SBC 位於同一個位置。 這與 [使用者位於 SBC 相同位置時，輸入通話中顯示的流程相同](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)。

> [!div class="mx-imgBorder"]
> ![另一個顯示 SIP 特性圖表。](media/direct-routing-media-op-15.png)

#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a>使用者的位置與 SBC 不同，但僅限本機使用者在公司網路中

|模式|使用者|網站|撥號方向|
|---|---|---|---|
|OnlyForLocalUsers|內部|與 SBC 不同|出境|

直接路由會根據在 SBC 上所報告的使用者位置和模式來計算 X-MediaPath。

下圖顯示只有ForLocalUsers 模式的撥出通話，以及與 SBC 不同位置的內部使用者。

> [!div class="mx-imgBorder"]
> ![另一個圖表顯示 SIP 的特性。](media/direct-routing-media-op-16.png)

#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a>輸入通話，且使用者是內部使用者，但與 SBC 不同，僅限本機使用者

|模式|使用者|網站|撥號方向|
|---|---|---|---|
|OnlyForLocalUsers|內部|與 SBC 不同|入境|

下圖顯示只有ForLocalUsers 模式的輸入通話，以及與 SBC 不同位置的內部使用者。

> [!div class="mx-imgBorder"]
> ![還有另一個顯示 SIP 存取的圖表。](media/direct-routing-media-op-17.png)
