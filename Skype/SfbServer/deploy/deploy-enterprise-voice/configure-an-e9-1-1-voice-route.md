---
title: 在商務用 Skype Server 中設定 E9-1-1 的語音路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: 在商務用 Skype Server Enterprise Voice 中設定 E9-1-1 個語音路由。
ms.openlocfilehash: c835aa2ab2b20f7877aa6a0deeb70c7459bcd8cc
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001393"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a>在商務用 Skype Server 中設定 E9-1-1 的語音路由
 
在商務用 Skype Server Enterprise Voice 中設定 E9-1-1 個語音路由。 
  
若要部署 E9-1，您必須先設定緊急通話語音路線。 如需建立語音路由的詳細資料，請參閱[在商務用 Skype 中建立或修改語音路線](create-or-modify-a-voice-route.md)。 例如，如果您的部署包含主要 SIP 幹線和次要 SIP 主幹，您可以定義多個路由。 
  
> [!NOTE]
> 若要在 E9-1 邀請中包含位置資訊，您需要設定連接至 E9-1 服務提供者的 SIP 幹線，以透過閘道路由緊急通話。 若要這樣做，請將**new-cstrunkconfiguration** Cmdlet 的 EnablePIDFLOSupport 標誌設定為 True。 EnablePIDFLOSupport 的預設值為 False。 例如： `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.`您不需要為 fallback 公用交換電話網絡（PSTN）閘道及緊急位置識別號碼（ELIN）閘道啟用接收位置。
  
### <a name="to-configure-an-e9-1-1-voice-route"></a>若要設定 E9-1-1 的語音路線

1. 以 RTCUniversalServerAdmins 群組成員或 CsVoiceAdministrator 系統管理角色的成員的帳戶登入電腦。
    
2.  啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。
    
3. 執行下列 Cmdlet 以建立新的 PSTN 使用記錄。 
    
    此名稱必須與您在位置原則中用於**PSTN**設定的名稱相同。 雖然您的部署會有多個電話使用記錄，但下列範例會將 [緊急使用量] 新增到目前可用 PSTN 用法的清單中。 如需詳細資訊，請參閱[在商務用 Skype 中設定語音原則、PSTN 使用方式記錄及語音路由](voice-and-pstn.md)。
    
   ```powershell
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. 執行下列 Cmdlet，以使用您在上一個步驟中建立的 PSTN 使用狀況記錄來建立新的語音路由。
    
    數位模式必須是在位置原則中的 [**緊急撥號字串**] 設定中所使用的相同數位模式。 商務用 Skype 將 "+" 新增到緊急通話，所以需要 "+" 符號。 "Co1-pstngateway-1" 是針對 E9-1 服務提供者或 ELIN 閘道服務 ID 的 SIP 幹線服務識別碼。 下列範例使用「EmergencyRoute」做為語音路由的名稱。
    
   ```powershell
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. 或者，對於 SIP 中繼連線，我們建議您執行下列 Cmdlet 來為 E9 建立本機路由，以供-1-1 服務提供者的 SIP 幹線所處理的通話。 如果無法連線至 E9-1-1 服務提供者，就會使用這個路由。 
    
    下列範例假設使用者的語音原則中有「本機」用法。
    
   ```powershell
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


