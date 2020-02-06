---
title: 在商務用 Skype Server 中管理會議加入與離開宣告
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
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 摘要：瞭解如何管理會議加入，以及如何在商務用 Skype Server 中保留宣告。
ms.openlocfilehash: 5f975637ca1d85e11c6889a07ff90055ef79ffc5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818544"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>在商務用 Skype Server 中管理會議加入與離開宣告
 
**摘要：** 瞭解如何管理會議加入，以及如何在商務用 Skype Server 中保留公告。
  
當撥入使用者加入或離開會議時，會議宣告應用程式可以透過播放音調或說出其名稱來宣告其進入或結束。 您可以使用商務用 Skype Server Management 命令介面和**CsDialinConferencing** Cmdlet 以及下列參數來變更宣告的運作方式：
  
- EnableNameRecording-判斷匿名參與者是否需要在進入會議之前先記錄他們的名稱。 預設值為「$true」，表示加入會議時，系統會提示匿名參與者指出他們的名稱。 （經過驗證的參與者不會記錄其名稱，因為改為使用其顯示名稱。）
    
- EntryExitAnnouncementsEnabledByDefault-表示預設是否開啟或關閉宣告。 預設值為「$false」，這表示參與者加入或離開會議時，預設沒有宣告。 會議召集人可以在排程會議時覆蓋此設定。
    
- EntryExitAnnouncementsType-表示每當參與者加入或離開已啟用宣告的會議時所採取的動作。 預設值為 "UseNames"，這表示您已開啟公告時的「Ken Myer 已加入會議」：
    
您可以在全域範圍或網站範圍中設定這些設定。 在網站範圍設定的設定，會優先于在全域範圍中設定的設定。
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>修改會議加入並離開宣告行為

1. 以 RTCUniversalServerAdmins 群組的成員或 Cs-ServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。
    
2. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。
    
3. 在命令提示字元執行下列動作：
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

此 Cmdlet 會在加入會議時，以及參與者加入或離開電話撥入式會議時，如何回應參與者是否必須記錄其名稱的相關資訊。
    
4. 在命令提示字元執行下列動作：
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

在下列範例中，設定是在雷德蒙的網站範圍設定。 公告已開啟，但在加入會議時，系統不會提示參與者說出其名稱。 當參與者進入或離開會議時，會播放音調：
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

如需詳細資訊（包括語法及完整的參數清單），請參閱[設定 CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)。
  

