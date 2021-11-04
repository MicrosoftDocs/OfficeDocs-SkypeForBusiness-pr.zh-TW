---
title: 在商務用 Skype Server 中管理會議加入和離開宣告
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 摘要：瞭解如何在商務用 Skype Server 中管理會議加入和保留宣告。
ms.openlocfilehash: 375cd1da4e60ccd9c6d7e4eb2864d49279e3c62a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765481"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>在商務用 Skype Server 中管理會議加入和離開宣告
 
**摘要：** 瞭解如何在商務用 Skype Server 中管理會議加入和保留宣告。
  
當撥入使用者加入或離開會議時，會議宣告應用程式可以透過播放音調或口述其名稱來宣告其進入或退出狀態。 您可以使用商務用 Skype Server 管理命令介面和 **test-csdialinconferencing 指令程式** 來變更宣告的運作方式，並使用下列參數：
  
- EnableNameRecording-決定匿名參與者是否要求在進入會議之前記錄其名稱。 預設值為 "$true，這表示匿名參與者在加入會議時，系統會提示他們輸入名稱。  (驗證的參與者不會記錄其名稱，因為會改為使用其顯示名稱。 ) 
    
- EntryExitAnnouncementsEnabledByDefault-會指出預設是否開啟或關閉宣告。 預設值為 "$false，這表示當參與者加入或離開會議時，預設不會有宣告。 會議召集人可以在排程會議時覆寫此設定。
    
- EntryExitAnnouncementsType-表示每當參與者加入或離開已啟用宣告的會議時所採取的動作。 預設值為 "UseNames，這表示有類似下列的宣告：「Ken Myer 已加入會議」（已開啟宣告）。
    
您可以在全域範圍或網站範圍中設定這些設定。 在網站範圍設定的設定優先于在全域範圍設定的設定。
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>修改會議加入和離開宣告行為

1. 以 RTCUniversalServerAdmins 群組成員或 Cs-ServerAdministrator、CsAdministrator 角色成員的身分登入電腦。
    
2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
3. 在命令提示字元中執行下列命令：
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

此 Cmdlet 會在加入會議時，會檢索是否需要參與者記錄其名稱的相關資訊，以及當參與者加入或離開電話撥入式會議時，商務用 Skype Server 的回應方式。
    
4. 在命令提示字元中執行下列命令：
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

在下列範例中，設定是在 Redmond 的網站範圍設定。 宣告已開啟，但是參與者加入會議時，不會提示參與者說出其名稱。 當參與者進入或離開會議時，會播放音調：
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

如需詳細資訊，包括語法和完整的參數清單，請參閱 [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)。
