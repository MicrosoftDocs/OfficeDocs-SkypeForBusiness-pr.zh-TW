---
title: 在商務用 Skype Server 中管理會議加入與離開宣告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: '摘要: 瞭解如何管理會議加入, 以及如何在商務用 Skype Server 中保留宣告。'
ms.openlocfilehash: 3d9a14e36dfe6b8df51e5ee91dd329ce34452cda
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189661"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a><span data-ttu-id="56361-103">在商務用 Skype Server 中管理會議加入與離開宣告</span><span class="sxs-lookup"><span data-stu-id="56361-103">Manage conference join and leave announcements in Skype for Business Server</span></span>
 
<span data-ttu-id="56361-104">**摘要:** 瞭解如何管理會議加入, 以及如何在商務用 Skype Server 中保留公告。</span><span class="sxs-lookup"><span data-stu-id="56361-104">**Summary:** Learn how to manage conference join and leave announcements in Skype for Business Server.</span></span>
  
<span data-ttu-id="56361-105">當撥入使用者加入或離開會議時, 會議宣告應用程式可以透過播放音調或說出其名稱來宣告其進入或結束。</span><span class="sxs-lookup"><span data-stu-id="56361-105">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="56361-106">您可以使用商務用 Skype Server Management 命令介面和**CsDialinConferencing** Cmdlet 以及下列參數來變更宣告的運作方式:</span><span class="sxs-lookup"><span data-stu-id="56361-106">You can change how announcements work by using Skype for Business Server Management Shell and the **Set-CsDialinConferencing** cmdlet with the following parameters:</span></span>
  
- <span data-ttu-id="56361-107">EnableNameRecording-判斷匿名參與者是否需要在進入會議之前先記錄他們的名稱。</span><span class="sxs-lookup"><span data-stu-id="56361-107">EnableNameRecording - Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="56361-108">預設值為「$true」, 表示加入會議時, 系統會提示匿名參與者指出他們的名稱。</span><span class="sxs-lookup"><span data-stu-id="56361-108">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="56361-109">(經過驗證的參與者不會記錄其名稱, 因為改為使用其顯示名稱。)</span><span class="sxs-lookup"><span data-stu-id="56361-109">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
- <span data-ttu-id="56361-110">EntryExitAnnouncementsEnabledByDefault-表示預設是否開啟或關閉宣告。</span><span class="sxs-lookup"><span data-stu-id="56361-110">EntryExitAnnouncementsEnabledByDefault - Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="56361-111">預設值為「$false」, 這表示參與者加入或離開會議時, 預設沒有宣告。</span><span class="sxs-lookup"><span data-stu-id="56361-111">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="56361-112">會議召集人可以在排程會議時覆蓋此設定。</span><span class="sxs-lookup"><span data-stu-id="56361-112">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
- <span data-ttu-id="56361-113">EntryExitAnnouncementsType-表示每當參與者加入或離開已啟用宣告的會議時所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="56361-113">EntryExitAnnouncementsType - Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="56361-114">預設值為 "UseNames", 這表示您已開啟公告時的「Ken Myer 已加入會議」:</span><span class="sxs-lookup"><span data-stu-id="56361-114">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
<span data-ttu-id="56361-115">您可以在全域範圍或網站範圍中設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="56361-115">You can configure these settings at the global scope or at the site scope.</span></span> <span data-ttu-id="56361-116">在網站範圍設定的設定, 會優先于在全域範圍中設定的設定。</span><span class="sxs-lookup"><span data-stu-id="56361-116">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="56361-117">修改會議加入並離開宣告行為</span><span class="sxs-lookup"><span data-stu-id="56361-117">To modify the conference join and leave announcement behavior</span></span>

1. <span data-ttu-id="56361-118">以 RTCUniversalServerAdmins 群組的成員或 Cs-ServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="56361-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="56361-119">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="56361-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="56361-120">在命令提示字元執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="56361-120">Run the following at the command prompt:</span></span>
    
   ```
   Get-CsDialinConferencingConfiguration
   ```

<span data-ttu-id="56361-121">此 Cmdlet 會在加入會議時, 以及參與者加入或離開電話撥入式會議時, 如何回應參與者是否必須記錄其名稱的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="56361-121">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Skype for Business Server responds when participants join or leave a dial-in conference.</span></span>
    
4. <span data-ttu-id="56361-122">在命令提示字元執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="56361-122">Run the following at the command prompt:</span></span>
    
   ```
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

<span data-ttu-id="56361-123">在下列範例中, 設定是在雷德蒙的網站範圍設定。</span><span class="sxs-lookup"><span data-stu-id="56361-123">In the following example, settings are configured at the site scope for Redmond.</span></span> <span data-ttu-id="56361-124">公告已開啟, 但在加入會議時, 系統不會提示參與者說出其名稱。</span><span class="sxs-lookup"><span data-stu-id="56361-124">Announcements are turned on, but participants are not prompted to say their name when they join a conference.</span></span> <span data-ttu-id="56361-125">當參與者進入或離開會議時, 會播放音調:</span><span class="sxs-lookup"><span data-stu-id="56361-125">A tone is played when participants enter or leave a conference:</span></span>
  
```
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

<span data-ttu-id="56361-126">如需詳細資訊 (包括語法及完整的參數清單), 請參閱[設定 CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="56361-126">For more information, including syntax and a complete list of parameters, see [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span></span>
  

