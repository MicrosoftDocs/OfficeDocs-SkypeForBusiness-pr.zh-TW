---
title: 設定商務用 Skype Server 中的 E9-1-1 語音路由
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: 設定商務用 Skype Server 企業語音中的 E9-1-1 語音路由。
ms.openlocfilehash: 86904c32db6ae43b9fa1b6f184048d3b9f419089
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833949"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a>設定商務用 Skype Server 中的 E9-1-1 語音路由
 
設定商務用 Skype Server 企業語音中的 E9-1-1 語音路由。 
  
若要部署 E9-1-1，您需要先設定緊急電話語音路由。 如需建立語音路由的詳細資訊，請參閱[在商務用 Skype 中建立或修改語音路由](create-or-modify-a-voice-route.md)。 例如，如果您的部署包括主要及次要 SIP 主幹，則可以定義多個路由。 
  
> [!NOTE]
> 若要在 E9-1-1 INVITE 中包括位置資訊，則必須先設定連線至 E9-1-1 服務提供者的 SIP 主幹以透過閘道路由傳送緊急電話。 若要進行這項作業，請將 **Set-CsTrunkConfiguration** Cmdlet 上的 EnablePIDFLOSupport 旗標設定為 True。 EnablePIDFLOSupport 的預設值是 False。 例如： `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` 不需要為 fallback 公用交換電話網路 (PSTN) 閘道和緊急位置識別號碼 (ELIN) 閘道啟用接收位置。
  
### <a name="to-configure-an-e9-1-1-voice-route"></a>設定 E9-1-1 語音路由

1. 使用屬於 RTCUniversalServerAdmins 群組成員或 CsVoiceAdministrator 系統管理角色成員的帳戶登入電腦。
    
2.  啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
3. 執行下列 Cmdlet 來建立新的 PSTN 使用方式記錄。 
    
    這必須是用於 [位置原則] 中 **PSTN** 設定的相同名稱。 雖然部署會有多筆電話使用方式記錄，下列範例會將「緊急使用方式」新增至目前可用的 PSTN 使用方式清單。 如需詳細資訊，請參閱[在商務用 Skype 中設定語音原則、PSTN 使用方式記錄和語音路由](voice-and-pstn.md)。
    
   ```powershell
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. 執行下列 Cmdlet，使用上個步驟中所建立的 PSTN 使用方式記錄來建立新的語音路由。
    
    數字模式必須是位置原則的 **緊急撥號字串** 設定中所使用的相同數字模式。 需要 "+" 符號，因為商務用 Skype 會將 "+" 新增至緊急通話。 "Co1-pstngateway-1" 是 E9-1-1 服務提供者或 ELIN 閘道服務 ID 的 SIP 主幹服務 ID。 下列範例會使用“EmergencyRoute”作為語音路由的名稱。
    
   ```powershell
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. （選用）若為 SIP 主幹連線，我們建議您執行下列 Cmdlet，為未由 E9-1-1 服務提供者的 SIP 主幹處理的呼叫建立本機路由。 如果與 E9-1-1 服務提供者的連線無法使用，則會使用此路由。 
    
    下列範例假設使用者的語音原則有「本機」使用方式。
    
   ```powershell
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


