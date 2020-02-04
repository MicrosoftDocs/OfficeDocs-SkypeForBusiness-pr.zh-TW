---
title: (選用) 啟用和停用會議加入和離開宣告
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
ms.openlocfilehash: 8b8e75a0d2ed81a515540f2a8a1811998a85d44c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a><span data-ttu-id="d087f-102">(選用) 在 Lync Server 2013 中啟用和停用會議加入和離開宣告</span><span class="sxs-lookup"><span data-stu-id="d087f-102">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d087f-103">_**主題上次修改日期：** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="d087f-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="d087f-104">當撥入使用者加入或離開會議時，會議宣告應用程式可以透過播放音調或說出其名稱來宣告其進入或結束。</span><span class="sxs-lookup"><span data-stu-id="d087f-104">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="d087f-105">您可以透過執行 Cmdlet 來變更宣告的運作方式。</span><span class="sxs-lookup"><span data-stu-id="d087f-105">You can change how announcements work by running cmdlets.</span></span> <span data-ttu-id="d087f-106">此為選用步驟。</span><span class="sxs-lookup"><span data-stu-id="d087f-106">This step is optional.</span></span>

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="d087f-107">修改會議加入並離開宣告行為</span><span class="sxs-lookup"><span data-stu-id="d087f-107">To modify the conference join and leave announcement behavior</span></span>

1.  <span data-ttu-id="d087f-108">以 RTCUniversalServerAdmins 群組的成員或**Cs-ServerAdministrator**或**CsAdministrator**角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="d087f-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="d087f-109">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="d087f-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d087f-110">在命令提示字元執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d087f-110">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingConfiguration
    
    <span data-ttu-id="d087f-111">這個 Cmdlet 會在加入會議時，以及 Lync Server 如何在參與者加入或離開電話撥入式會議時的回應，來檢索相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d087f-111">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Lync Server responds when participants join or leave a dial-in conference.</span></span>

4.  <span data-ttu-id="d087f-112">在命令提示字元執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d087f-112">Run the following at the command prompt:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    <span data-ttu-id="d087f-113">**EnableNameRecording**   會判斷匿名參與者是否需要在進入會議之前先記錄其名稱。</span><span class="sxs-lookup"><span data-stu-id="d087f-113">**EnableNameRecording**   Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="d087f-114">預設值為「$true」，表示加入會議時，系統會提示匿名參與者指出他們的名稱。</span><span class="sxs-lookup"><span data-stu-id="d087f-114">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="d087f-115">（經過驗證的參與者不會記錄其名稱，因為改為使用其顯示名稱。）</span><span class="sxs-lookup"><span data-stu-id="d087f-115">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
    <span data-ttu-id="d087f-116">**[EntryExitAnnouncementsEnabledByDefault**   ] 表示預設是否開啟或關閉公告。</span><span class="sxs-lookup"><span data-stu-id="d087f-116">**EntryExitAnnouncementsEnabledByDefault**   Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="d087f-117">預設值為「$false」，這表示參與者加入或離開會議時，預設沒有宣告。</span><span class="sxs-lookup"><span data-stu-id="d087f-117">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="d087f-118">會議召集人可以在排程會議時覆蓋此設定。</span><span class="sxs-lookup"><span data-stu-id="d087f-118">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
    <span data-ttu-id="d087f-119">**EntryExitAnnouncementsType**   表示每當參與者加入或離開已啟用宣告的會議時所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="d087f-119">**EntryExitAnnouncementsType**   Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="d087f-120">預設值為 "UseNames"，這表示您已開啟公告時的「Ken Myer 已加入會議」：</span><span class="sxs-lookup"><span data-stu-id="d087f-120">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
    <span data-ttu-id="d087f-121">您可以在全域範圍或網站範圍中設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="d087f-121">You can configure these settings at the global scope or at the site scope.</span></span> <span data-ttu-id="d087f-122">在網站範圍設定的設定，會優先于在全域範圍中設定的設定。</span><span class="sxs-lookup"><span data-stu-id="d087f-122">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
    
    <span data-ttu-id="d087f-123">例如：</span><span class="sxs-lookup"><span data-stu-id="d087f-123">For example:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    <span data-ttu-id="d087f-124">在這個範例中，設定是在雷德蒙的網站範圍設定。</span><span class="sxs-lookup"><span data-stu-id="d087f-124">In this example, settings are configured at the site scope for Redmond.</span></span> <span data-ttu-id="d087f-125">公告已開啟，但在加入會議時，系統不會提示參與者說出其名稱。</span><span class="sxs-lookup"><span data-stu-id="d087f-125">Announcements are turned on, but participants are not prompted to say their name when they join a conference.</span></span> <span data-ttu-id="d087f-126">當參與者進入或離開會議時，會播放音調。</span><span class="sxs-lookup"><span data-stu-id="d087f-126">A tone is played when participants enter or leave a conference.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

