---
title: （選用）啟用和停用會議加入和離開宣告
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
ms.openlocfilehash: 6b18dadbb4b7dc5a35f8688c46f2836b46cb55a5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a><span data-ttu-id="ed8ea-102">（選用）啟用和停用會議加入和離開宣告在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed8ea-102">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed8ea-103">_**主題上次修改日期：** 2012年-09-30_</span><span class="sxs-lookup"><span data-stu-id="ed8ea-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="ed8ea-104">當撥入使用者加入或離開會議時，會議宣告應用程式可以宣布其進入或結束播放音零或說他們的名稱。</span><span class="sxs-lookup"><span data-stu-id="ed8ea-104">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="ed8ea-105">您可以變更執行 cmdlet 的宣告運作方式。</span><span class="sxs-lookup"><span data-stu-id="ed8ea-105">You can change how announcements work by running cmdlets.</span></span> <span data-ttu-id="ed8ea-106">此步驟是選用的。</span><span class="sxs-lookup"><span data-stu-id="ed8ea-106">This step is optional.</span></span>

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="ed8ea-107">若要修改會議加入和離開宣告行為</span><span class="sxs-lookup"><span data-stu-id="ed8ea-107">To modify the conference join and leave announcement behavior</span></span>

1.  <span data-ttu-id="ed8ea-108">以 RTCUniversalServerAdmins 群組成員或 **Cs-ServerAdministrator**、**CsAdministrator** 角色成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="ed8ea-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="ed8ea-109">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="ed8ea-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ed8ea-110">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ed8ea-110">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingConfiguration
    
    <span data-ttu-id="ed8ea-111">此 cmdlet 會擷取參與者是否需要記錄其姓名加入會議時，與 Lync Server 時參與者加入或離開電話撥入式會議的回應資訊。</span><span class="sxs-lookup"><span data-stu-id="ed8ea-111">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Lync Server responds when participants join or leave a dial-in conference.</span></span>

4.  <span data-ttu-id="ed8ea-112">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ed8ea-112">Run the following at the command prompt:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    <span data-ttu-id="ed8ea-113">**EnableNameRecording**   決定匿名參與者上當系統要記錄其姓名進入會議之前。</span><span class="sxs-lookup"><span data-stu-id="ed8ea-113">**EnableNameRecording**   Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="ed8ea-114">預設值為 「 $true 」 這表示，提示匿名參與者加入會議時的狀態其名稱。</span><span class="sxs-lookup"><span data-stu-id="ed8ea-114">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="ed8ea-115">（已驗證的參與者未記錄其姓名因為可以改為使用其顯示名稱。）</span><span class="sxs-lookup"><span data-stu-id="ed8ea-115">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
    <span data-ttu-id="ed8ea-116">**EntryExitAnnouncementsEnabledByDefault**   宣告是否會開啟或關閉，預設會指示。</span><span class="sxs-lookup"><span data-stu-id="ed8ea-116">**EntryExitAnnouncementsEnabledByDefault**   Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="ed8ea-117">預設值為 「 $false 」 表示預設有任何宣告時參與者加入或離開會議。</span><span class="sxs-lookup"><span data-stu-id="ed8ea-117">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="ed8ea-118">排程會議時，會議召集人可以覆寫此設定。</span><span class="sxs-lookup"><span data-stu-id="ed8ea-118">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
    <span data-ttu-id="ed8ea-119">**EntryExitAnnouncementsType**   表示每當參與者加入或離開宣告已啟用的會議時所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="ed8ea-119">**EntryExitAnnouncementsType**   Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="ed8ea-120">預設值是 「 UseNames，「 這就表示有宣告如下: 「 Ken Myer 已加入會議 」 宣告已開啟。</span><span class="sxs-lookup"><span data-stu-id="ed8ea-120">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
    <span data-ttu-id="ed8ea-121">在全域範圍，或在網站範圍，您可以設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="ed8ea-121">You can configure these settings at the global scope or at the site scope.</span></span> <span data-ttu-id="ed8ea-122">在網站範圍設定的設定優先於在全域範圍設定的設定。</span><span class="sxs-lookup"><span data-stu-id="ed8ea-122">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
    
    <span data-ttu-id="ed8ea-123">例如：</span><span class="sxs-lookup"><span data-stu-id="ed8ea-123">For example:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    <span data-ttu-id="ed8ea-124">在這個範例中，設定是在 Redmond 的網站範圍設定。</span><span class="sxs-lookup"><span data-stu-id="ed8ea-124">In this example, settings are configured at the site scope for Redmond.</span></span> <span data-ttu-id="ed8ea-125">宣告開啟狀態，但參與者系統不會提示他們加入會議時，說出其名稱。</span><span class="sxs-lookup"><span data-stu-id="ed8ea-125">Announcements are turned on, but participants are not prompted to say their name when they join a conference.</span></span> <span data-ttu-id="ed8ea-126">當參與者進入或離開會議時，就會播放音。</span><span class="sxs-lookup"><span data-stu-id="ed8ea-126">A tone is played when participants enter or leave a conference.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

