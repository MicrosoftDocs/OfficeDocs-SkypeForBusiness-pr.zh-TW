---
title: 在商務用 Skype Server 中管理 DTMF 命令的按鍵對應
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: 摘要：瞭解如何在商務用 Skype Server 中管理雙音多頻率 (DTMF) 命令的按鍵對應。
---

# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a>在商務用 Skype Server 中管理 DTMF 命令的按鍵對應
 
**總結：** 瞭解如何在商務用 Skype Server 中管理雙色調多頻率 (DTMF) 命令的按鍵對應。
  
電話撥入式會議使用者可按下電話按鍵上的按鍵，以執行雙音多頻率 (DTMF) 命令。 DTMF 命令可讓撥入會議的使用者控制會議設定 (例如，靜音和 unmuting 本身，或使用電話上的小鍵盤鎖定和解除鎖定會議) 。 
  
若要管理 DTMF 命令使用的金鑰，請使用商務用 Skype Server 管理命令介面搭配 **set-csdialinconferencingdtmfconfiguration**、 **Set-CsDialinConferencingDtmfConfiguration** 和 **set-csdialinconferencingdtmfconfiguration** Cmdlet。
  
當您為網站建立新的 DTMF 設定時，網站設定會優先于通用設定。 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a>管理 DTMF 命令的按鍵對應

1. 以 RTCUniversalServerAdmins 群組成員或 Cs-ServerAdministrator、CsAdministrator 角色成員的身分登入電腦。
    
2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
3. 若要查看用於電話撥入式會議的 DTMF 設定，請在命令提示字元中執行下列命令：
    
   ```PowerShell
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. 若要修改電話撥入式會議所用的 DTMF 設定，請執行下列 Cmdlet，並指定要變更之每個選項的按鍵。
    
   ```PowerShell
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5.  (選用) 若要為特定網站建立其他 DTMF 命令集，請使用具有網站身分識別的 **set-csdialinconferencingdtmfconfiguration** Cmdlet。
    
下列範例會將已按下的按鍵，以啟用或停用用來啟用或停用的宣告，以及已按下以靜音和取消靜音所有參與者的按鍵。 由於沒有指定身分識別，因此這些變更會套用到全域 DTMF 設定：
  
```PowerShell
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

如需詳細資訊，請參閱 [Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps)、 [Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)和 [set-csdialinconferencingdtmfconfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)。
