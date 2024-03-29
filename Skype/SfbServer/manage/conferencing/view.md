---
title: 在商務用 Skype Server 中查看會議原則
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
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 摘要：瞭解如何在商務用 Skype Server 中查看會議原則。
---

# <a name="view-conferencing-policies-in-skype-for-business-server"></a>在商務用 Skype Server 中查看會議原則
 
**總結：** 瞭解如何在商務用 Skype Server 中查看會議原則。
  
您可以使用商務用 Skype Server 控制台] 或使用商務用 Skype Server 管理命令介面來查看會議原則。
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台來查看會議原則

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2.  開啟商務用 Skype Server 控制台]。
    
3. 在左導覽列中，按一下 [ **會議**]，然後按一下 [ **會議原則**]。
    
4. 在 [ **會議原則** ] 頁面上，連按兩下您要查看的會議原則。
    
5. 在 [ **編輯檔案篩選**] 中，選取 [ **顯示詳細資料** ] 核取方塊。
    
    **編輯會議原則- \<policy\>** 開啟顯示選取原則的設定。
    
    如需設定設定的詳細資訊，請參閱[在商務用 Skype Server 中建立會議原則](create-policies.md)。
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面來查看會議原則

若要查看會議原則，請使用 **Get-CsConferencingPolicy** Cmdlet：
  
```PowerShell
Get-CsConferencingPolicy
```

Cmdlet 會傳回下列資訊：
  
<pre>
Identity                                  : Global
AllowIPAudio                              : True
AllowIPVideo                              : True
AllowMultiView                            : True
Description                               :
AllowParticipantControl                   : True
AllowAnnotations                          : True
DisablePowerPointAnnotations              : False
AllowUserToScheduleMeetingsWithAppSharing : True
AllowNonEnterpriseVoiceUsersToDialOut     : False
AllowAnonymousUsersToDialOut              : False
AllowAnonymousParticipantsInMeetings      : True
AllowExternalUsersToSaveContent           : True
AllowExternalUserControl                  : False
AllowExternalUsersToRecordMeeting         : False
AllowPolls                                : True
AllowSharedNotes                          : True
EnableDialInConferencing                  : True
EnableAppDesktopSharing                   : Desktop
AllowConferenceRecording                  : False
EnableP2PRecording                        : False
EnableFileTransfer                        : True
EnableP2PFileTransfer                     : True
EnableP2PVideo                            : True
AllowLargeMeetings                        : False
EnableDataCollaboration                   : True
MaxVideoConferenceResolution              : VGA
MaxMeetingSize                            : 250
AudioBitRateKb                            : 200
VideoBitRateKb                            : 50000
AppSharingBitRateKb                       : 50000
FileTransferBitRateKb                     : 50000
TotalReceiveVideoBitRateKb                : 6000
EnableMultiViewJoin                       : True
</pre>

如需詳細資訊，包括完整的語法描述及參數清單，請參閱 [Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps)。
