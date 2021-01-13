---
title: 在商務用 Skype Server 中管理會議加入和離開宣告
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 摘要：瞭解如何在商務用 Skype Server 中管理會議加入和離開宣告。
ms.openlocfilehash: 9ca73d3d32ce03a8119d805b5e7260c0a871eb27
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828103"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a><span data-ttu-id="8dca9-103">在商務用 Skype Server 中管理會議加入和離開宣告</span><span class="sxs-lookup"><span data-stu-id="8dca9-103">Manage conference join and leave announcements in Skype for Business Server</span></span>
 
<span data-ttu-id="8dca9-104">**摘要：** 瞭解如何在商務用 Skype Server 中管理會議加入和離開宣告。</span><span class="sxs-lookup"><span data-stu-id="8dca9-104">**Summary:** Learn how to manage conference join and leave announcements in Skype for Business Server.</span></span>
  
<span data-ttu-id="8dca9-105">當撥入使用者加入或離開會議時，會議宣告應用程式可以透過播放音調或口述其名稱來宣告其進入或退出。</span><span class="sxs-lookup"><span data-stu-id="8dca9-105">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="8dca9-106">您可以使用商務用 Skype Server 管理命令介面和 **test-csdialinconferencing 指令程式** 來變更宣告的運作方式，並使用下列參數：</span><span class="sxs-lookup"><span data-stu-id="8dca9-106">You can change how announcements work by using Skype for Business Server Management Shell and the **Set-CsDialinConferencing** cmdlet with the following parameters:</span></span>
  
- <span data-ttu-id="8dca9-107">EnableNameRecording-決定匿名參與者是否要求在進入會議之前記錄其名稱。</span><span class="sxs-lookup"><span data-stu-id="8dca9-107">EnableNameRecording - Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="8dca9-108">預設值為 "$true，這表示匿名參與者在加入會議時，系統會提示他們輸入名稱。</span><span class="sxs-lookup"><span data-stu-id="8dca9-108">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="8dca9-109"> (驗證的參與者不會記錄其名稱，因為會改為使用其顯示名稱。 ) </span><span class="sxs-lookup"><span data-stu-id="8dca9-109">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
- <span data-ttu-id="8dca9-110">EntryExitAnnouncementsEnabledByDefault-會指出預設是否開啟或關閉宣告。</span><span class="sxs-lookup"><span data-stu-id="8dca9-110">EntryExitAnnouncementsEnabledByDefault - Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="8dca9-111">預設值為 "$false，這表示當參與者加入或離開會議時，預設不會有宣告。</span><span class="sxs-lookup"><span data-stu-id="8dca9-111">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="8dca9-112">會議召集人可以在排程會議時覆寫此設定。</span><span class="sxs-lookup"><span data-stu-id="8dca9-112">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
- <span data-ttu-id="8dca9-113">EntryExitAnnouncementsType-表示每當參與者加入或離開已啟用宣告的會議時所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="8dca9-113">EntryExitAnnouncementsType - Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="8dca9-114">預設值為 "UseNames，這表示有類似下列的宣告：「Ken Myer 已加入會議」（已開啟宣告）。</span><span class="sxs-lookup"><span data-stu-id="8dca9-114">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
<span data-ttu-id="8dca9-115">您可以在全域範圍或網站範圍中設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="8dca9-115">You can configure these settings at the global scope or at the site scope.</span></span> <span data-ttu-id="8dca9-116">在網站範圍設定的設定會優先于在全域範圍設定的設定。</span><span class="sxs-lookup"><span data-stu-id="8dca9-116">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="8dca9-117">修改會議加入和離開宣告行為</span><span class="sxs-lookup"><span data-stu-id="8dca9-117">To modify the conference join and leave announcement behavior</span></span>

1. <span data-ttu-id="8dca9-118">以 RTCUniversalServerAdmins 群組成員或 Cs-ServerAdministrator、CsAdministrator 角色成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="8dca9-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="8dca9-119">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="8dca9-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="8dca9-120">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="8dca9-120">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

<span data-ttu-id="8dca9-121">這個 Cmdlet 會取得參與者加入會議時，是否需要參與者記錄其名稱的相關資訊，以及商務用 Skype 伺服器在參與者加入或離開電話撥入式會議時，如何回應。</span><span class="sxs-lookup"><span data-stu-id="8dca9-121">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Skype for Business Server responds when participants join or leave a dial-in conference.</span></span>
    
4. <span data-ttu-id="8dca9-122">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="8dca9-122">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

<span data-ttu-id="8dca9-123">在下列範例中，設定是在 Redmond 的網站範圍設定。</span><span class="sxs-lookup"><span data-stu-id="8dca9-123">In the following example, settings are configured at the site scope for Redmond.</span></span> <span data-ttu-id="8dca9-124">宣告已開啟，但是參與者加入會議時，不會提示參與者說出其名稱。</span><span class="sxs-lookup"><span data-stu-id="8dca9-124">Announcements are turned on, but participants are not prompted to say their name when they join a conference.</span></span> <span data-ttu-id="8dca9-125">當參與者進入或離開會議時，會播放音調：</span><span class="sxs-lookup"><span data-stu-id="8dca9-125">A tone is played when participants enter or leave a conference:</span></span>
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

<span data-ttu-id="8dca9-126">如需詳細資訊，包括語法和完整的參數清單，請參閱 [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="8dca9-126">For more information, including syntax and a complete list of parameters, see [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span></span>
  

