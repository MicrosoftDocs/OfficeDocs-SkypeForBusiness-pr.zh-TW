---
title: " (選用) 啟用和停用會議加入和離開宣告"
description: " (選用) 啟用和停用會議加入和離開宣告。"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Enable and disable conference join and leave announcements
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398834(v=OCS.15)
ms:contentKeyID: 48185403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70cd6b452a44d7d40f23d5ca96b6e4b7b063d2ec
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565779"
---
# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a><span data-ttu-id="f1696-103"> (選用) 在 Lync Server 2013 中啟用和停用會議加入和離開宣告</span><span class="sxs-lookup"><span data-stu-id="f1696-103">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1696-104">_**主題上次修改日期：** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="f1696-104">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="f1696-105">當撥入使用者加入或離開會議時，會議宣告應用程式可以透過播放音調或口述其名稱來宣告其進入或退出。</span><span class="sxs-lookup"><span data-stu-id="f1696-105">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="f1696-106">您可以透過執行 Cmdlet 來變更宣告的運作方式。</span><span class="sxs-lookup"><span data-stu-id="f1696-106">You can change how announcements work by running cmdlets.</span></span> <span data-ttu-id="f1696-107">這是選擇性的步驟。</span><span class="sxs-lookup"><span data-stu-id="f1696-107">This step is optional.</span></span>

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="f1696-108">修改會議加入和離開宣告行為</span><span class="sxs-lookup"><span data-stu-id="f1696-108">To modify the conference join and leave announcement behavior</span></span>

1.  <span data-ttu-id="f1696-109">以 RTCUniversalServerAdmins 群組成員或 **Cs-ServerAdministrator**、**CsAdministrator** 角色成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="f1696-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="f1696-110">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="f1696-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f1696-111">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f1696-111">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingConfiguration
    
    <span data-ttu-id="f1696-112">此 Cmdlet 會在加入會議時，檢索參與者是否需要記錄其名稱的相關資訊，以及當參與者加入或離開電話撥入式會議時，Lync Server 的回應方式。</span><span class="sxs-lookup"><span data-stu-id="f1696-112">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Lync Server responds when participants join or leave a dial-in conference.</span></span>

4.  <span data-ttu-id="f1696-113">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f1696-113">Run the following at the command prompt:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    <span data-ttu-id="f1696-114">**EnableNameRecording**    決定匿名參與者是否要求在進入會議之前記錄其名稱。</span><span class="sxs-lookup"><span data-stu-id="f1696-114">**EnableNameRecording**   Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="f1696-115">預設值為 "$true，這表示匿名參與者在加入會議時，系統會提示他們輸入名稱。</span><span class="sxs-lookup"><span data-stu-id="f1696-115">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="f1696-116"> (驗證的參與者不會記錄其名稱，因為會改為使用其顯示名稱。 ) </span><span class="sxs-lookup"><span data-stu-id="f1696-116">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
    <span data-ttu-id="f1696-117">**EntryExitAnnouncementsEnabledByDefault**    會指出預設是否開啟或關閉宣告。</span><span class="sxs-lookup"><span data-stu-id="f1696-117">**EntryExitAnnouncementsEnabledByDefault**   Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="f1696-118">預設值為 "$false，這表示當參與者加入或離開會議時，預設不會有宣告。</span><span class="sxs-lookup"><span data-stu-id="f1696-118">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="f1696-119">會議召集人可以在排程會議時覆寫此設定。</span><span class="sxs-lookup"><span data-stu-id="f1696-119">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
    <span data-ttu-id="f1696-120">**EntryExitAnnouncementsType**    會指出每當參與者加入或離開已啟用宣告的會議時所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="f1696-120">**EntryExitAnnouncementsType**   Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="f1696-121">預設值為 "UseNames，這表示有類似下列的宣告：「Ken Myer 已加入會議」（已開啟宣告）。</span><span class="sxs-lookup"><span data-stu-id="f1696-121">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
    <span data-ttu-id="f1696-122">您可以在全域範圍或網站範圍中設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="f1696-122">You can configure these settings at the global scope or at the site scope.</span></span> <span data-ttu-id="f1696-123">在網站範圍設定的設定會優先于在全域範圍設定的設定。</span><span class="sxs-lookup"><span data-stu-id="f1696-123">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
    
    <span data-ttu-id="f1696-124">例如：</span><span class="sxs-lookup"><span data-stu-id="f1696-124">For example:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    <span data-ttu-id="f1696-125">在此範例中，設定是在 Redmond 的網站範圍設定。</span><span class="sxs-lookup"><span data-stu-id="f1696-125">In this example, settings are configured at the site scope for Redmond.</span></span> <span data-ttu-id="f1696-126">宣告已開啟，但是參與者加入會議時，不會提示參與者說出其名稱。</span><span class="sxs-lookup"><span data-stu-id="f1696-126">Announcements are turned on, but participants are not prompted to say their name when they join a conference.</span></span> <span data-ttu-id="f1696-127">當參與者進入或離開會議時，會播放音調。</span><span class="sxs-lookup"><span data-stu-id="f1696-127">A tone is played when participants enter or leave a conference.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

