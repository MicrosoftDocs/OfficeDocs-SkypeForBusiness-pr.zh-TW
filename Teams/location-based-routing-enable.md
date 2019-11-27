---
title: 啟用直接路由的依位置路由
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解如何針對直接路由啟用以位置為基礎的路由。
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 615848be1f91f80b0afd06c1eaa44a4f9d7b4f63
ms.sourcegitcommit: 021c86bf579e315f15815dcddf232a0c651cbf6b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2019
ms.locfileid: "39615793"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>啟用直接路由的依位置路由

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

在您按照本文中的步驟進行之前，請確定您已閱讀「[規劃位置」路由以進行直接路由](location-based-routing-plan.md)，並已完成[設定位置路由的網路設定](location-based-routing-configure-network-settings.md)中的步驟。

本文說明如何啟用直接路由的以位置為基礎的路由。 在您部署手機系統直接路由並設定網路區域、網站和子網之後，您就可以開始啟用位置路由。 若要完成本文中的步驟，您需要熟悉 PowerShell Cmdlet。 若要深入瞭解，請參閱[團隊 PowerShell 概覽](teams-powershell-overview.md)。

 您必須啟用下列各項的位置路由：
- 使用者
- 網路網站
- 閘道設定
- 通話原則

## <a name="enable-location-based-routing-for-users"></a>針對使用者啟用以位置為基礎的路由

1. 使用[CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) Cmdlet 來設定 PSTN 用法。 針對多種用途，請使用逗號來分隔每個用法。

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    例如：
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. 使用[新的 CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) Cmdlet 來建立語音路由策略，以將使用者與適當的 PSTN 用法進行關聯。

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    當您將 PSTN 用途指派給語音路由策略時，請務必執行下列其中一項操作：
    - 使用與在網站使用 PSTN 閘道的語音路由相關聯的 PSTN 用法
    - 使用不需要以位置為基礎路由限制之區域中的 PSTN 閘道的語音路由所關聯的 PSTN 用法。

    在這個範例中，我們會建立兩個新的語音路由策略，並將 PSTN 使用方式指派給它們。 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    下表顯示在這個範例中定義的語音路由策略。 
    
    ||語音路由原則1|語音路由策略2|
    |---------|---------|---------|
    |線上語音原則識別碼   |新德里線上語音路由策略   |Hyderabad 線上語音路由策略    |
    |線上 PSTN 用法  |長途  |遠距離、本機、內部  |

3. 使用[授與 CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) Cmdlet，將線上語音路由策略與需要強制執行路由限制的使用者建立關聯。
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a>啟用網路網站的位置路由
1.  使用[CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) Cmdlet 來啟用以位置為基礎的路由，並將語音路由策略與您的網路網站進行關聯，而您必須強制執行路由限制。
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    在這個範例中，我們會針對新德里網站和 Hyderabad 網站啟用位置路由。 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    下表顯示在這個範例中，針對位置路由啟用的網站。

    ||Site 1 （新德里）  |Site 2 （Hyderabad）  |
    |---------|---------|---------|
|網站名稱    |Site 1 （新德里）    |Site 2 （Hyderabad）   
    |EnableLocationBasedRouting    |滿足    |滿足    |
    |網     |Subnet 1 （新德里）     |Subnet 2 （Hyderabad）     |

## <a name="enable-location-based-routing-for-gateways"></a>啟用閘道的位置路由
1. 使用[CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) Cmdlet 來為每個閘道或網路網站建立閘道配置。 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    如果有多個閘道與系統相關聯（例如，閘道或 PBX），請修改每個閘道以啟用以位置為基礎的路由限制。 

    在這個範例中，我們會為每個閘道建立一個閘道配置。 
    ```
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    如需詳細資訊，請參閱[設定直接路由](direct-routing-configure.md)。
    
2. 使用[CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) Cmdlet 來針對需要強制執行路由限制的閘道，啟用以位置為基礎的路由。 

    啟用將呼叫路由至 pstn 閘道，並將呼叫路由到 PSTN 的閘道，並將閘道所在的網路網站與網路網站建立關聯，以進行位置路由。

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    在這個範例中，我們為在新德里與 Hyderabad 網站中與 PSTN 閘道相關聯的每個閘道啟用位置路由。 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    不要針對未將呼叫路由至 PSTN 的閘道啟用位置式路由。 不過，您仍然必須將閘道與系統所在的網路網站建立關聯。 這是因為以位置為基礎的路由限制需要針對透過此閘道所連線的端點而進行 PSTN 呼叫強制執行。 在這個範例中，對於與新德里與 Hyderabad 網站中的 PBX 系統相關聯的每個閘道，都不會啟用位置路由。

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    連接至不路由呼叫至 PSTN （例如 PBX）的系統的端點，將會有類似的限制，因為已啟用位置路由的團隊使用者的端點。 這表示無論使用者的位置為何，這些使用者都可以對團隊使用者進行呼叫和接聽。 他們也可以在不將呼叫路由至 PSTN 網路的其他系統（例如，連線到不同 PBX 的端點）撥打電話和接聽電話，而不論系統與哪個網路網站的關聯。 所有的撥入通話、撥出通話、來電轉接及涉及 PSTN 端點的來電轉接，都會受到位置式路由 enforcements。 這些通話只能使用定義為此類系統的本機的 PSTN 閘道。 

    下表顯示兩個不同網路網站中四個閘道的閘道設定：兩個連接至 PSTN 閘道的兩個閘道，以及兩個連線至 PBX 系統 

    ||GatewaySiteLbrEnabled   |NetworkSiteID  |
    |---------|---------|---------|
    |PstnGateway：閘道 1 DEL-GW    |    滿足     |   Site 1 （新德里）      |
    |PstnGateway： Gateway 2 HYD-GW     |   滿足      |      Site 2 （Hyderabad）   |
    |PstnGateway：閘道 3 DEL-PBX    |    虛假     |     Site 1 （新德里）    |
    |PstnGateway：閘道 4 HYD-PBX    |    虛假     |    Site 2 （Hyderabad）     |

## <a name="enable-location-based-routing-for-calling-policies"></a>啟用呼叫原則的位置路由

若要針對特定的使用者強制執行以位置為基礎的路由，請設定使用者的語音原則來避免 PTSN 免付費旁路。 

使用[授與 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) Cmdlet，透過避免 PSTN 免付費旁路來啟用以位置為基礎的路由。

```
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
在這個範例中，我們將避免 PSTN 免付費旁路 User1's 通話原則。 

```
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

## <a name="related-topics"></a>相關主題

- [小組中雲端語音功能的網路設定](cloud-voice-network-settings.md)
