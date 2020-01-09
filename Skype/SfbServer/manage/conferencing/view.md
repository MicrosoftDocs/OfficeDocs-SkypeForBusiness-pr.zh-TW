---
title: 在商務用 Skype Server 中查看會議原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 摘要：瞭解如何在商務用 Skype Server 中查看會議原則。
ms.openlocfilehash: 7ea7b5cb9ba54fcf26e5f37b79320466c19d1050
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992188"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a>在商務用 Skype Server 中查看會議原則
 
**摘要：** 瞭解如何在商務用 Skype Server 中查看會議原則。
  
您可以使用商務用 Skype Server 的 [控制台] 或使用商務用 Skype Server Management Shell 來查看會議原則。
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 的 [控制台] 來查看會議原則

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2.  開啟商務用 Skype Server 的 [控制台]。
    
3. 在左側導覽列中，按一下 [**會議**]，然後按一下 [**會議原則**]。
    
4. 在 [**會議原則**] 頁面上，按兩下您要查看的會議原則。
    
5. 在 [**編輯檔案篩選器**] 中，選取 [**顯示詳細資料**] 核取方塊。
    
    [**編輯會議原則\<]\> -** 已開啟顯示所選原則設定的原則。
    
    如需設定設定的詳細資訊，請參閱[在商務用 Skype 伺服器中建立會議原則](create-policies.md)。
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management Shell 來查看會議原則

若要查看會議原則，請使用**CsConferencingPolicy** Cmdlet：
  
```PowerShell
Get-CsConferencingPolicy
```

這個 Cmdlet 會傳回如下所示的資訊：
  
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

如需詳細資訊（包括完整的語法描述及參數清單），請參閱[CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps)。
  

