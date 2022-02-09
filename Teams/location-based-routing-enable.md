---
title: 啟用直接路由的依位置路由
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解如何啟用直接Location-Based路由的路由，包括為使用者、網路網站、閘道組配置和通話規則啟用路由。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a53ab4ad866f3d9ad6acb1258247da59b15a27d9
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399487"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>啟用直接路由的依位置路由

在您遵循本文中的步驟之前，請確定您閱讀了直接路由Location-Based [路由](location-based-routing-plan.md) 方案，並已完成設定路由的網路Location-Based [步驟](location-based-routing-configure-network-settings.md)。

本文將說明如何啟用直接路由Location-Based路由。 部署直接路由電話系統設定網路區域、網站和子網之後，就可以啟用 Location-Based路由。 若要完成本文中的步驟，您需要熟悉 PowerShell Cmdlet。 若要深入瞭解，請參閱[powerShell Teams概觀](teams-powershell-overview.md)。

 您必須啟用下列Location-Based路由：
- 使用者
- 網路網站
- 閘道配置
- 通話原則

您可以使用系統管理中心[Microsoft Teams](#using-the-microsoft-teams-admin-center) [PowerShell](#using-powershell)來啟用Location-Based路由。

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

### <a name="enable-location-based-routing-for-users"></a>為Location-Based啟用路由

1. 建立語音路由策略，並將 PSTN 使用量指派給該策略。 當您將 PSTN 使用量指派給策略時，請確定您執行下列其中一項操作：

    - 使用與使用 PSTN 閘道本地到網站的語音路由相關聯的 PSTN 使用方式。
    - 使用與使用 PSTN 閘道的語音路由相關聯的 PSTN 使用方式，Location-Based不需要路由限制的地區。
2. 將語音路由策略指派給需要強制執行路由限制的使用者。

若要深入瞭解如何建立語音路由策略並將其指派給使用者，請參閱在 Microsoft Teams 中[管理語音路由Microsoft Teams](manage-voice-routing-policies.md)。

### <a name="enable-location-based-routing-for-network-sites"></a>啟用Location-Based網站的路由

針對需要Location-Based路由限制的網站啟用路由路由。 若要這麼做，請在系統管理中心的左側導Microsoft Teams，前往 **LocationsNetwork**  >  拓撲，選取網路網站，按一下 [編輯，然後開啟位置型 **路由。**  

若要深入瞭解，請參閱 [管理您的網路拓撲](manage-your-network-topology.md)。

### <a name="enable-location-based-routing-for-gateways"></a>啟用Location-Based閘道的路由

啟用 Location-Based路由至閘道，將呼叫路由至將通話路由至 PSTN 的 PSTN 閘道，並將閘道所在的網路網站建立關聯。 

1. 在左側流覽中，前往 **VoiceDirect**  >  **路由**，然後按一下 **[SBCs> 定位** 點。
2. 選取 SBC，然後按一下 [ **編輯**。 
3. 在 **位置路由和媒體優化下**，開啟啟用 **位置型路由**。
4. 指定閘道網站識別碼，然後設定旁路模式。
5. 按一下 [儲存]。

### <a name="enable-location-based-routing-for-calling-policies"></a>針對Location-Based啟用路由

若要為Location-Based使用者強制執行路由，請設定使用者的通話策略，以防止 PSTN 付費旁路。 若要這麼做，請開啟通話政策中的防止免付費路設定。

若要深入瞭解，請參閱通話[Teams](teams-calling-policy.md)。

## <a name="using-powershell"></a>使用 PowerShell

### <a name="enable-location-based-routing-for-users"></a>為Location-Based啟用路由

1. 使用 [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) Cmdlet 來設定 PSTN 使用方式。 針對多個使用方式，請以逗號分隔每個使用方式。

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    例如：
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. 使用 [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) Cmdlet 建立語音路由策略，讓使用者與適當的 PSTN 使用方式建立關聯。

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    當您將 PSTN 使用量指派給語音路由策略時，請務必執行下列其中一項操作：
    - 使用與使用 PSTN 閘道本地到網站的語音路由相關聯的 PSTN 使用方式
    - 使用與使用 PSTN 閘道的語音路由相關聯的 PSTN 使用方式，Location-Based不需要路由限制的地區。

    在此範例中，我們建立兩個新的語音路由策略，並指派 PSTN 使用方式給他們。 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    下表顯示此範例中定義的語音路由策略。 
    
    |&nbsp;|語音路由策略 1|語音路由策略 2|
    |---------|---------|---------|
    |線上語音策略識別碼   |印度線上語音路由政策   |海德拉巴線上語音路由政策    |
    |線上 PSTN 使用方式  |長距離  |長距離、本地、內部  |

3. 使用 [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) Cmdlet 將線上語音路由策略關聯到需要強制執行路由限制的使用者。
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a>啟用Location-Based網站的路由

1.  使用 [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) Cmdlet 啟用 Location-Based 路由，並將語音路由策略關聯到需要強制執行路由限制的網路網站。
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    在此範例中，我們Location-Based印度網站和海德拉巴網站的路由。 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    下表顯示在此範例中啟用 Location-Based路由的網站。

    |&nbsp;|第 1 (裡)   |網站 2 (海德拉巴)   |
    |---------|---------|---------|
    |網站名稱    |第 1 (裡)     |網站 2 (海德拉巴) |
    |EnableLocationBasedRouting    |真    |真    |
    |子網     |第 1 (裡)      |子網 2 (海德拉巴)      |

### <a name="enable-location-based-routing-for-gateways"></a>啟用Location-Based閘道的路由

1. 使用 [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) Cmdlet 為每個閘道或網路網站建立閘道組式。 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    如果多個閘道與系統連結 (例如閘道或 PBX) ，請修改每個閘道，Location-Based路由限制。 

    在此範例中，我們會為每個閘道建立一個閘道組組。 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    詳細資訊，請參閱設定 [直接路由](direct-routing-configure.md)。
    
2. 使用 [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) Cmdlet 為需要強制執行路由限制Location-Based閘道啟用 Location-Based路由。 

    啟用 Location-Based路由至閘道，將呼叫路由至將通話路由至 PSTN 的 PSTN 閘道，並將閘道所在的網路網站建立關聯。

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    在此範例中，Location-Based在Deri 和 Hyder廣告網站中，針對與 PSTN 閘道相關聯的每個閘道啟用 [路由路由> 功能。 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    請勿針對不會將Location-Based路由到 PSTN 的閘道啟用路由。 不過，您仍然需要將閘道與系統所在的網路網站建立關聯。 這是因為必須Location-Based PSTN 通話到達經由此閘道連接的端點時，強制執行路由限制。 在此範例中，Location-Based和海德拉巴網站中與 PBX 系統相關聯的每個閘道，不會啟用路由。

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>針對Location-Based啟用路由

若要針對Location-Based強制路由，請設定使用者的語音策略，以防止 PTSN 付費旁路。 

使用 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) Cmdlet 來Location-Based PSTN 付費旁路來啟用路由。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
在此範例中，我們防止 PSTN 付費旁路至 User1 的通話政策。 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>相關主題

- [雲端語音功能的網路設定Teams](cloud-voice-network-settings.md)