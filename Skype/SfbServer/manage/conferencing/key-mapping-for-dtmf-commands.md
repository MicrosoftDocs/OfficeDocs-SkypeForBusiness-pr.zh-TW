---
title: 在商務用 Skype Server 中管理 DTMF 命令的金鑰組應
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: 摘要：瞭解如何在商務用 Skype Server 中管理雙音調多頻率（DTMF）命令的按鍵對應。
ms.openlocfilehash: fdb9846da81c4029fa67df606fa021397a46b3ad
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818534"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a>在商務用 Skype Server 中管理 DTMF 命令的金鑰組應
 
**摘要：** 瞭解如何在商務用 Skype Server 中管理雙音調多頻率（DTMF）命令的按鍵對應。
  
電話撥入式會議使用者可以按電話鍵臺上的按鍵，以執行雙音調多頻率（DTMF）命令。 DTMF 命令可讓撥入會議的使用者控制會議設定（例如靜音及 unmuting 本身，或是使用電話鍵，在通話中鎖定及解除鎖定會議）。 
  
若要管理 DTMF 命令所使用的金鑰，請使用商務用 Skype Server 管理命令介面（含**CsDialinConferencingDtmfConfiguration**、 **CsDialinConferencingDtmfConfiguration**和**CsDialinConferencingDtmfConfiguration** Cmdlet）。
  
當您為網站建立新的 DTMF 設定時，網站設定會優先于全域設定。 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a>管理 DTMF 命令的金鑰組應

1. 以 RTCUniversalServerAdmins 群組的成員或 Cs-ServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。
    
2. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。
    
3. 若要查看電話撥入式會議所用的 DTMF 設定，請在命令提示字元執行下列命令：
    
   ```PowerShell
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. 若要修改用於電話撥入式會議的 DTMF 設定，請執行下列 Cmdlet，並指定要為每個您要變更的選項按下的索引鍵：
    
   ```PowerShell
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. 可選若要針對特定網站建立其他 DTMF 命令組，請搭配使用**CsDialinConferencingDtmfConfiguration** Cmdlet 搭配網站身分識別。
    
下列範例會交換按下的按鍵來啟用或停用宣告，以及按下來將所有參與者靜音和取消靜音的按鍵。 由於沒有指定身分識別，這些變更會套用到全域 DTMF 設定：
  
```PowerShell
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

如需詳細資訊，請參閱[CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps)、 [Set CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)和[CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)。
  

