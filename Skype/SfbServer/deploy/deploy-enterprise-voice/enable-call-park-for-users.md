---
title: 為商務用 Skype 中的使用者啟用通話駐留
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
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: 在商務用 Skype Server 企業語音中為使用者啟用通話駐留。
ms.openlocfilehash: 87ac29c8f9b6c893149db8fb91561ee4b3cf1166
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843506"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>為商務用 Skype 中的使用者啟用通話駐留
 
在商務用 Skype Server 企業語音中為使用者啟用通話駐留。
  
預設會停用所有使用者的通話駐留。 使用者在語音原則中為通話駐留啟用電話時，無法寄存通話或取得寄存的通話。
  
您可以在全域範圍或網站範圍或使用者範圍上啟用通話駐留。 使用者範圍優先于網站範圍，而網站範圍優先于全域範圍。 如果您有多個語音原則，請複習所有原則以啟用通話駐留，而不只是全域原則。
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>使用商務用 Skype Server 控制台為使用者啟用通話駐留

1. 以 **RTCUniversalServerAdmins** 群組成員的身分，或是 **CsVoiceAdministrator**、 **CsServerAdministrator** 或 **CsAdministrator** 系統管理角色的成員身分登入電腦。
    
2. 開啟商務用 Skype Server 控制台]。
    
3. 在左導覽列中，按一下 **[語音路由]**。
    
4. 按一下 [ **語音原則** ] 索引標籤。
    
5. 按兩下現有的語音原則，以開啟 [ **編輯語音原則** ] 對話方塊。
    
6. 在 [ **通話功能**] 底下，選取 [ **啟用通話駐留**]。
    
7. 按一下 **[確定]** 以儲存語音原則
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>若要使用 Cmdlet 為使用者啟用通話駐留

1. 以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 系統管理角色的成員身分登入電腦。
    
2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
3. 運行：
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    例如，若要啟用預設全域語音原則的通話駐留：
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>另請參閱



[在商務用 Skype 中建立或修改語音原則及設定 PSTN 使用方式記錄](voice-policy-and-pstn-usage-records.md)

