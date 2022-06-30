---
title: 啟用直接路由的依位置路由
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解如何啟用Location-Based直接路由的路由，包括為使用者啟用、網路網站、閘道設定和通話原則。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aadf5f4e4dff855d80c275be3d2027e767a732ad
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562192"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>啟用直接路由的依位置路由

本文說明如何啟用直接路由Location-Based路由。 依照本文中的步驟進行之前，請務必先閱讀規劃 [Location-Based直接路由的路由](location-based-routing-plan.md) ，並完成設定 [Location-Based路由的網路設定](location-based-routing-configure-network-settings.md)中的步驟。

 部署直接路由並設定網路區域、網站和子網之後，就可以啟用Location-Based路由。 若要完成本文中的步驟，您必須熟悉 PowerShell Cmdlet。 若要深入瞭解，請參閱 [Teams PowerShell 概觀](teams-powershell-overview.md)

 您必須啟用下列Location-Based路由：

- 使用者
- 網路網站
- 閘道設定
- 通話原則

您可以使用 Teams 系統 [管理中心](#using-the-microsoft-teams-admin-center) 或 [PowerShell](#using-powershell) 來啟用Location-Based路由。

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

### <a name="enable-location-based-routing-for-users"></a>為使用者啟用Location-Based路由

1. 建立語音路由原則，並將 PSTN 使用量指派給原則。 當您將 PSTN 使用量指派給原則時，請確定您執行下列其中一項操作：

    - 使用與使用本機至網站之 PSTN 閘道之語音路由相關聯的 PSTN 使用方式。

    - 使用與使用 PSTN 閘道的語音路由相關聯的 PSTN 使用方式，該閘道位於不需要Location-Based路由限制的地區。

2. 將語音路由原則指派給需要強制執行路由限制的使用者。

若要深入瞭解如何建立語音路由原則並將它們指派給使用者，請參閱 [管理 Microsoft Teams 中的語音路由原則](manage-voice-routing-policies.md)。

### <a name="enable-location-based-routing-for-network-sites"></a>啟用網路網站的Location-Based路由

針對需要強制執行路由限制的網站啟用Location-Based路由。 若要這麼做，請在 Microsoft Teams 系統管理中心的左側導覽中，移至 [**位置**  >  **網路拓撲]**，選取網路網站，按一下 **[編輯**]，然後開啟 **[以位置為基礎的路由]**。  

若要深入瞭解，請參閱 [管理您的網路拓撲](manage-your-network-topology.md)。

### <a name="enable-location-based-routing-for-gateways"></a>啟用閘道Location-Based路由

啟用Location-Based路由到路由呼叫 PSTN 閘道以路由呼叫 PSTN 的閘道，並建立閘道所在網路網站的關聯。 

1. 在左側導覽中，移至 **[語音**  >  **直接路由]**，然後按一下 [**SBC] 索引卷** 標。

2. 選取 SBC，然後按一下 **[編輯]**。 

3. 在 **[以位置為基礎的路由和媒體優化**] 底下，開啟 **[啟用以位置為基礎的路由]**。

4. 指定閘道網站識別碼，然後設定略過模式。

5. 按一下 [儲存]。

### <a name="enable-location-based-routing-for-calling-policies"></a>啟用通話原則的Location-Based路由

若要針對特定使用者強制執行Location-Based路由，請設定使用者的通話原則以防止 PSTN 付費旁路。 若要這麼做，請開啟通話原則中的 **防止付費旁路** 設定。

若要深入瞭解，請參閱 [Teams 中的通話原則](teams-calling-policy.md)。

## <a name="using-powershell"></a>使用 PowerShell

### <a name="enable-location-based-routing-for-users"></a>為使用者啟用Location-Based路由

1. 若要設定 PSTN 使用量，請使用 [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) Cmdlet。 針對多個使用量，請以逗號分隔每個使用量。

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```

    例如：

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```

2. 若要建立語音路由原則，將使用者與適當的 PSTN 使用方式建立關聯，請使用 [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) Cmdlet。

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    當您將 PSTN 使用量指派給語音路由原則時，請確定您執行下列其中一項操作：

    - 使用與使用本機至網站之 PSTN 閘道之語音路由相關聯的 PSTN 使用方式。

    - 使用與使用 PSTN 閘道的語音路由相關聯的 PSTN 使用方式，該閘道位於不需要Location-Based路由限制的地區。

    下列範例會建立兩個新的語音路由原則，並將 PSTN 使用量指派給他們。 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ``` 

    下表顯示此範例中定義的語音路由原則。 
    
    |&nbsp;|語音路由原則 1|語音路由原則 2|
    |---------|---------|---------|
    |線上語音原則識別碼   |網站線上語音路由原則   |文拉布線上語音路由原則    |
    |線上 PSTN 使用量  |長距離  |長途電話、本機、內部  |

3. 若要將線上語音路由原則與需要強制執行路由限制的使用者建立關聯，請使用 [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) Cmdlet。

    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```

### <a name="enable-location-based-routing-for-network-sites"></a>啟用網路網站的Location-Based路由

1. 若要啟用Location-Based路由，並將語音路由原則關聯到需要強制執行路由限制的網路網站，請使用 [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) Cmdlet。

    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    此範例會啟用Location-Based對[天山] 網站和[庫里拉巴] 網站的路由。 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    下表顯示此範例中啟用Location-Based路由的網站。

    |&nbsp;|網站 1 (關)   |網站 2 (文拉巴)   |
    |---------|---------|---------|
    |網站名稱    |網站 1 (關)     |網站 2 (文拉巴) |
    |EnableLocationBasedRouting    |真    |真    |
    |子網     |Subnet 1 (關)      |Subnet 2 (體)      |


### <a name="enable-location-based-routing-for-gateways"></a>啟用閘道Location-Based路由

1. 若要為每個閘道或網路網站建立閘道設定，請使用 [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) Cmdlet。 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```

    如果多個閘道與 [閘道] 或 [PBX) 等系統 (相關聯，請修改每個閘道以啟用Location-Based路由限制。 

    下列範例會為每個閘道建立一個閘道設定。 

    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    如需詳細資訊，請參閱 [設定直接路由](direct-routing-configure.md)。
    
2. 若要針對需要強制執行路由限制的閘道啟用Location-Based路由，請使用 [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) Cmdlet。 

    啟用Location-Based路由到路由呼叫 PSTN 閘道以路由呼叫 PSTN 的閘道，並建立閘道所在網路網站的關聯。

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

   下列範例會針對與[地道] 和 [海德拉巴] 網站中的 PSTN 閘道相關聯的每個閘道啟用Location-Based路由。 

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```

    針對未將呼叫路由至 PSTN 的閘道，請勿啟用Location-Based路由。 不過，您仍須將閘道與系統所在的網路網站建立關聯。 這是因為必須針對到達透過此閘道連線的端點的 PSTN 通話，強制執行Location-Based路由限制。 在此範例中，[Location-Based路由] 並不會針對每個與 PbX 系統關聯的閘道啟用，

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>啟用通話原則的Location-Based路由

若要針對特定使用者強制執行Location-Based路由，請設定使用者的語音原則以防止 PTSN 付費旁路。 

若要透過防止 PSTN 免付費旁路啟Location-Based路由，請使用 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) Cmdlet。


```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```

在此範例中，我們防止 PSTN 付費略過 User1 的通話原則。 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>相關主題

- [Teams 中雲端語音功能的網路設定](cloud-voice-network-settings.md)