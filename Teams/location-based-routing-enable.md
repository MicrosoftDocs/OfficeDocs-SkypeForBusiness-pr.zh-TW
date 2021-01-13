---
title: 啟用直接路由的依位置路由
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解如何啟用直接路由的 Location-Based 路由，包括為使用者、網路網站、閘道設定及呼叫原則啟用路由。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fe9600a1ddc530b1dbbcb6c061021c9d4cd9d537
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822913"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>啟用直接路由的依位置路由

在您按照本文中的步驟進行之前，請確定您已閱讀「 [規劃」 Location-Based 路由以進行直接路由](location-based-routing-plan.md) ，並已完成 [設定 Location-Based 路由的網路設定](location-based-routing-configure-network-settings.md)中的步驟。

本文說明如何啟用 Location-Based 路由以進行直接路由。 在您部署手機系統直通路由及設定網路區域、網站和子網之後，您就可以開始 Location-Based 路由。 若要完成本文中的步驟，您需要熟悉 PowerShell Cmdlet。 若要深入瞭解，請參閱 [團隊 PowerShell 概覽](teams-powershell-overview.md)。

 您必須啟用 Location-Based 路由，才能進行下列作業：
- 使用者
- 網路網站
- 閘道設定
- 通話原則

您可以使用 [Microsoft Team 管理中心](#using-the-microsoft-teams-admin-center) 或 [PowerShel](#using-powershell)l 來啟用 Location-Based 路由。

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

### <a name="enable-location-based-routing-for-users"></a>為使用者啟用 Location-Based 路由

1. 建立語音路由策略，並將 PSTN 用途指派給原則。 當您將 PSTN 用途指派給原則時，請確定執行下列其中一項操作：

    - 使用與在網站使用 PSTN 閘道的語音路由相關的 PSTN 用法。
    - 使用與使用不需要 Location-Based 路由限制之區域中之 PSTN 閘道之語音路由的 PSTN 用法。
2. 將語音路由原則指派給需要強制執行路由限制的使用者。

若要深入瞭解如何建立語音路由策略並指派給使用者，請參閱 [在 Microsoft 團隊中管理語音路由原則](manage-voice-routing-policies.md)。

### <a name="enable-location-based-routing-for-network-sites"></a>啟用網路網站的 Location-Based 路由

針對需要強制執行路由限制的網站啟用 Location-Based 路由。 若要這樣做，請在 Microsoft 團隊系統管理中心的左導覽中，移至 [**位置**  >  **網路拓撲**]，選取網路網站，按一下 [**編輯**]，然後開啟 [以 **位置為基礎的路由**]。  

若要深入瞭解，請參閱 [管理您的網路拓撲](manage-your-network-topology.md)。

### <a name="enable-location-based-routing-for-gateways"></a>啟用閘道 Location-Based 路由

啟用 Location-Based 路由至將呼叫路由至 pstn 閘道，並將呼叫路由到 PSTN 的閘道，並建立閘道所在的網路網站。 

1. 在左側導覽中，移至 [**語音**  >  **直式路由**]，然後按一下 [ **SBCs** ] 索引標籤。
2. 選取 SBC，然後按一下 [ **編輯**]。 
3. 在 [位置] 下的 [ **路由及媒體優化**] 底下，開啟 [ **啟用根據位置的路由**]。
4. 指定閘道網站識別碼，然後設定 [略過模式]。
5. 按一下 **[儲存]**。

### <a name="enable-location-based-routing-for-calling-policies"></a>啟用呼叫原則 Location-Based 路由

若要針對特定使用者強制執行 Location-Based 路由，請設定使用者的通話原則來避免 PSTN 免付費旁路。 若要這樣做，請在通話原則中開啟 [ **防止收費略過** ] 設定。

若要深入瞭解，請參閱 [在團隊中呼叫原則](teams-calling-policy.md)。

## <a name="using-powershell"></a>使用 PowerShell

### <a name="enable-location-based-routing-for-users"></a>為使用者啟用 Location-Based 路由

1. 使用 [CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) Cmdlet 來設定 PSTN 用法。 針對多種用途，請使用逗號來分隔每個用法。

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    例如：
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. 使用 [新的 CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) Cmdlet 來建立語音路由策略，以將使用者與適當的 PSTN 用法進行關聯。

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    當您將 PSTN 用途指派給語音路由策略時，請務必執行下列其中一項操作：
    - 使用與在網站使用 PSTN 閘道的語音路由相關聯的 PSTN 用法
    - 使用與使用不需要 Location-Based 路由限制之區域中之 PSTN 閘道之語音路由的 PSTN 用法。

    在這個範例中，我們會建立兩個新的語音路由策略，並將 PSTN 使用方式指派給它們。 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    下表顯示在這個範例中定義的語音路由策略。 
    
    ||語音路由原則1|語音路由策略2|
    |---------|---------|---------|
    |線上語音原則識別碼   |新德里線上語音路由策略   |Hyderabad 線上語音路由策略    |
    |線上 PSTN 用法  |長途  |遠距離、本機、內部  |

3. 使用 [授與 CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) Cmdlet，將線上語音路由策略與需要強制執行路由限制的使用者建立關聯。
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a>啟用網路網站的 Location-Based 路由

1.  使用 [CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) Cmdlet 來啟用 Location-Based 路由，並將語音路由策略與您的網路網站進行關聯，而您必須強制執行路由限制。
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    在這個範例中，我們會針對新德里網站和 Hyderabad 網站啟用 Location-Based 路由。 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    下表顯示在這個範例中，為 Location-Based 路由而啟用的網站。

    ||Site 1 (新德里)   |Site 2 (Hyderabad)   |
    |---------|---------|---------|
|網站名稱    |Site 1 (新德里)     |Site 2 (Hyderabad)    
    |EnableLocationBasedRouting    |滿足    |滿足    |
    |網     |Subnet 1 (新德里)      |Subnet 2 (Hyderabad)      |

### <a name="enable-location-based-routing-for-gateways"></a>啟用閘道 Location-Based 路由

1. 使用 [CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) Cmdlet 來為每個閘道或網路網站建立閘道配置。 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    如果有多個閘道與系統 (（例如閘道或 PBX) ），請修改每個閘道以啟用 Location-Based 路由限制。 

    在這個範例中，我們會為每個閘道建立一個閘道配置。 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    如需詳細資訊，請參閱 [設定直接路由](direct-routing-configure.md)。
    
2. 使用 [CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) Cmdlet 來針對需要強制執行路由限制的閘道啟用 Location-Based 路由。 

    啟用 Location-Based 路由至將呼叫路由至 pstn 閘道，並將呼叫路由到 PSTN 的閘道，並建立閘道所在的網路網站。

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    在這個範例中，我們會針對與 Hyderabad 網站中的 PSTN 閘道相關聯的每個閘道啟用 Location-Based 路由。 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    不要針對未將呼叫路由至 PSTN 的閘道啟用 Location-Based 路由。 不過，您仍然必須將閘道與系統所在的網路網站建立關聯。 這是因為，對於透過此閘道連線之端點的 PSTN 呼叫，必須強制執行 Location-Based 路由限制。 在這個範例中，對於與新德里與 Hyderabad 網站中的 PBX 系統相關聯的每個閘道，都不會啟用 Location-Based 路由。

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>啟用呼叫原則 Location-Based 路由

若要針對特定的使用者強制執行 Location-Based 路由，請設定使用者的語音原則來避免 PTSN 免付費略過。 

使用 [授與 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) Cmdlet，透過避免 PSTN 免付費旁路來啟用 Location-Based 路由。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
在這個範例中，我們將避免 PSTN 免付費旁路 User1's 通話原則。 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>相關主題

- [小組中雲端語音功能的網路設定](cloud-voice-network-settings.md)
