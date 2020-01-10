---
title: 在商務用 Skype 中啟用電話寄存給使用者
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
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: 在商務用 Skype Server Enterprise Voice 中，允許通話駐留的使用者使用。
ms.openlocfilehash: c3ad2bcf70c7b175ba372ba2834e56209de9f664
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002553"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>在商務用 Skype 中啟用電話寄存給使用者
 
在商務用 Skype Server Enterprise Voice 中，允許通話駐留的使用者使用。
  
根據預設，會停用所有使用者的 [通話駐留]。 使用者在語音原則中啟用通話駐留前，不能寄存通話或取得停用通話。
  
您可以在全域範圍或在網站範圍或使用者範圍中啟用通話駐留。 [使用者範圍] 的優先順序高於 [網站範圍]，而 [網站範圍] 的優先順序高於 [全域範圍]。 如果您有多個語音原則，請查看所有原則來啟用通話駐留，而不只是全域原則。
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>若要使用商務用 Skype Server 的 [控制台] 來為使用者啟用通話駐留

1. 以**RTCUniversalServerAdmins**群組的成員或**CsVoiceAdministrator**、 **CsServerAdministrator**或**CsAdministrator**系統管理角色的成員的身分登入電腦。
    
2. 開啟商務用 Skype Server 的 [控制台]。
    
3. 在左側導覽列中，按一下 [**語音路由**]。
    
4. 按一下 [**語音原則**] 索引標籤。
    
5. 按兩下現有的語音原則，以開啟 [**編輯語音原則**] 對話方塊。
    
6. 在 [**呼叫功能**] 底下，選取 [**啟用通話駐留**]。
    
7. 按一下 **[確定]** 儲存語音原則
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>若要使用 Cmdlet 來為使用者啟用通話駐留

1. 以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 系統管理角色的成員的身分登入電腦。
    
2. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。
    
3. 用盡
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    例如，若要針對預設的全域語音原則啟用通話駐留，請執行下列動作：
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>另請參閱



[在商務用 Skype 中建立或修改語音原則及設定 PSTN 使用記錄](voice-policy-and-pstn-usage-records.md)

