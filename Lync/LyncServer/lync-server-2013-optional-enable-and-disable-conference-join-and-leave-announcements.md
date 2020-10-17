---
title: " (選用) 啟用和停用會議加入和離開宣告"
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
ms.openlocfilehash: a50431ee1917c580440f8a47cff0ca09f5e47f07
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524430"
---
# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a><span data-ttu-id="8efef-102"> (選用) 在 Lync Server 2013 中啟用和停用會議加入和離開宣告</span><span class="sxs-lookup"><span data-stu-id="8efef-102">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8efef-103">_**主題上次修改日期：** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="8efef-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="8efef-104">當撥入使用者加入或離開會議時，會議宣告應用程式可以透過播放音調或口述其名稱來宣告其進入或退出。</span><span class="sxs-lookup"><span data-stu-id="8efef-104">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="8efef-105">您可以透過執行 Cmdlet 來變更宣告的運作方式。</span><span class="sxs-lookup"><span data-stu-id="8efef-105">You can change how announcements work by running cmdlets.</span></span> <span data-ttu-id="8efef-106">這是選擇性的步驟。</span><span class="sxs-lookup"><span data-stu-id="8efef-106">This step is optional.</span></span>

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="8efef-107">修改會議加入和離開宣告行為</span><span class="sxs-lookup"><span data-stu-id="8efef-107">To modify the conference join and leave announcement behavior</span></span>

1.  <span data-ttu-id="8efef-108">以 RTCUniversalServerAdmins 群組成員或 **Cs-ServerAdministrator**、**CsAdministrator** 角色成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="8efef-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="8efef-109">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="8efef-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8efef-110">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="8efef-110">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingConfiguration
    
    <span data-ttu-id="8efef-111">此 Cmdlet 會在加入會議時，檢索參與者是否需要記錄其名稱的相關資訊，以及當參與者加入或離開電話撥入式會議時，Lync Server 的回應方式。</span><span class="sxs-lookup"><span data-stu-id="8efef-111">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Lync Server responds when participants join or leave a dial-in conference.</span></span>

4.  <span data-ttu-id="8efef-112">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="8efef-112">Run the following at the command prompt:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    <span data-ttu-id="8efef-113">**EnableNameRecording**    決定匿名參與者是否要求在進入會議之前記錄其名稱。</span><span class="sxs-lookup"><span data-stu-id="8efef-113">**EnableNameRecording**   Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="8efef-114">預設值為 "$true，這表示匿名參與者在加入會議時，系統會提示他們輸入名稱。</span><span class="sxs-lookup"><span data-stu-id="8efef-114">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="8efef-115"> (驗證的參與者不會記錄其名稱，因為會改為使用其顯示名稱。 ) </span><span class="sxs-lookup"><span data-stu-id="8efef-115">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
    <span data-ttu-id="8efef-116">**EntryExitAnnouncementsEnabledByDefault**    會指出預設是否開啟或關閉宣告。</span><span class="sxs-lookup"><span data-stu-id="8efef-116">**EntryExitAnnouncementsEnabledByDefault**   Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="8efef-117">預設值為 "$false，這表示當參與者加入或離開會議時，預設不會有宣告。</span><span class="sxs-lookup"><span data-stu-id="8efef-117">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="8efef-118">會議召集人可以在排程會議時覆寫此設定。</span><span class="sxs-lookup"><span data-stu-id="8efef-118">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
    <span data-ttu-id="8efef-119">**EntryExitAnnouncementsType**    會指出每當參與者加入或離開已啟用宣告的會議時所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="8efef-119">**EntryExitAnnouncementsType**   Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="8efef-120">預設值為 "UseNames，這表示有類似下列的宣告：「Ken Myer 已加入會議」（已開啟宣告）。</span><span class="sxs-lookup"><span data-stu-id="8efef-120">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
    <span data-ttu-id="8efef-121">您可以在全域範圍或網站範圍中設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="8efef-121">You can configure these settings at the global scope or at the site scope.</span></span> <span data-ttu-id="8efef-122">在網站範圍設定的設定會優先于在全域範圍設定的設定。</span><span class="sxs-lookup"><span data-stu-id="8efef-122">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
    
    <span data-ttu-id="8efef-123">例如：</span><span class="sxs-lookup"><span data-stu-id="8efef-123">For example:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    <span data-ttu-id="8efef-124">在此範例中，設定是在 Redmond 的網站範圍設定。</span><span class="sxs-lookup"><span data-stu-id="8efef-124">In this example, settings are configured at the site scope for Redmond.</span></span> <span data-ttu-id="8efef-125">宣告已開啟，但是參與者加入會議時，不會提示參與者說出其名稱。</span><span class="sxs-lookup"><span data-stu-id="8efef-125">Announcements are turned on, but participants are not prompted to say their name when they join a conference.</span></span> <span data-ttu-id="8efef-126">當參與者進入或離開會議時，會播放音調。</span><span class="sxs-lookup"><span data-stu-id="8efef-126">A tone is played when participants enter or leave a conference.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

