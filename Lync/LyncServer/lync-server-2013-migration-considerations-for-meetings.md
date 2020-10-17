---
title: Lync Server 2013：會議的遷移考慮
description: Lync Server 2013：會議的遷移考慮。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration considerations for meetings
ms:assetid: a9807d58-99a3-4cff-b4c6-74950d106a2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412800(v=OCS.15)
ms:contentKeyID: 61097556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e238405acf7bc2a96fd2efd4cca761c1f1f258fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560939"
---
# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a><span data-ttu-id="5384c-103">Lync Server 2013 中的會議遷移考慮</span><span class="sxs-lookup"><span data-stu-id="5384c-103">Migration considerations for meetings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5384c-104">_**主題上次修改日期：** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="5384c-104">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="5384c-105">本節將討論下列主題：</span><span class="sxs-lookup"><span data-stu-id="5384c-105">The following topics are discussed in this section:</span></span>

  - <span data-ttu-id="5384c-106">Microsoft Lync Server 2013 中的會議變更</span><span class="sxs-lookup"><span data-stu-id="5384c-106">Changes to meetings in Microsoft Lync Server 2013</span></span>

  - <span data-ttu-id="5384c-107">依據使用者的會議需求移轉使用者</span><span class="sxs-lookup"><span data-stu-id="5384c-107">Migrating users based on their conferencing needs</span></span>

  - <span data-ttu-id="5384c-108">移轉現有的會議與會議內容</span><span class="sxs-lookup"><span data-stu-id="5384c-108">Migrating existing meetings and meeting content</span></span>

  - <span data-ttu-id="5384c-109">Lync Server 2010 遷移期間的使用者經驗</span><span class="sxs-lookup"><span data-stu-id="5384c-109">User experience during Lync Server 2010 migration</span></span>

  - <span data-ttu-id="5384c-110">Office 通訊伺服器 2007 R2 遷移期間的使用者經驗</span><span class="sxs-lookup"><span data-stu-id="5384c-110">User Experience during Office Communications Server 2007 R2 migration</span></span>

  - <span data-ttu-id="5384c-111">Microsoft Lync 2013 與舊版伺服器版本上的會議相容性</span><span class="sxs-lookup"><span data-stu-id="5384c-111">Microsoft Lync 2013 compatibility with meetings on earlier server versions</span></span>

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a><span data-ttu-id="5384c-112">Lync Server 2013 中的會議變更</span><span class="sxs-lookup"><span data-stu-id="5384c-112">Changes to Meetings in Lync Server 2013</span></span>

<span data-ttu-id="5384c-113">**Lync Server 2013 功能。**    Lync Server 2013 提供新的會議功能，當使用者的帳戶移至 Lync Server 2013 並以 Lync 2013 用戶端登入時，這些功能就可供使用者使用。</span><span class="sxs-lookup"><span data-stu-id="5384c-113">**Lync Server 2013 features.**   Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="5384c-114">[Lync server 2013 中的新會議功能](lync-server-2013-new-conferencing-features.md)會列出新功能，以及[lync server 2013 中用戶端的新](lync-server-2013-what-s-new-for-clients.md)功能。</span><span class="sxs-lookup"><span data-stu-id="5384c-114">New features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="5384c-115">**會議 URL。**    在 Lync Server 2010 中，Lync Server 2013 中的所有新排程會議都具有 URL 首碼 HTTPs://，且現有會議會隨使用者帳戶一起遷移。</span><span class="sxs-lookup"><span data-stu-id="5384c-115">**Meeting URL.**   As in Lync Server 2010, all newly scheduled meetings in Lync Server 2013 have a URL prefix of https:// and existing meetings migrate along with user accounts.</span></span> <span data-ttu-id="5384c-116">不過，Lync Server 2013 不支援 Office 通訊伺服器 2007 R2 會議呼叫 (conf://URL 首碼) 或 web 會議 (meet://URL 首碼) 。</span><span class="sxs-lookup"><span data-stu-id="5384c-116">However, Lync Server 2013 does not support the Office Communications Server 2007 R2 conference call (conf:// URL prefix) or web conference (meet:// URL prefix).</span></span> <span data-ttu-id="5384c-117">如需詳細資訊，請參閱本主題稍後的「從 Office 通訊伺服器 2007 R2 遷移會議」。</span><span class="sxs-lookup"><span data-stu-id="5384c-117">See “Migrating Meetings from Office Communications Server 2007 R2” later in this topic for more information.</span></span>

<span data-ttu-id="5384c-118">**用戶端支援。**    與 Lync Server 2010 不同的是，Lync Server 2013 不支援 Office Communicator 用戶端進行會議。</span><span class="sxs-lookup"><span data-stu-id="5384c-118">**Client support.**   Unlike Lync Server 2010, Lync Server 2013 does not support Office Communicator clients for conferencing.</span></span> <span data-ttu-id="5384c-119">您無法使用下列用戶端加入透過 Lync 2013 之線上會議增益集排程的會議：</span><span class="sxs-lookup"><span data-stu-id="5384c-119">You cannot use the following clients to join meetings scheduled through the Online Meeting Add-in for Lync 2013:</span></span>

  - <span data-ttu-id="5384c-120">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="5384c-120">Office Communicator 2007 R2</span></span>

  - <span data-ttu-id="5384c-121">Microsoft Office Communications Server 2007 R2 Attendant</span><span class="sxs-lookup"><span data-stu-id="5384c-121">Microsoft Office Communications Server 2007 R2 Attendant</span></span>

  - <span data-ttu-id="5384c-122">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="5384c-122">Office Communicator 2007</span></span>

  - <span data-ttu-id="5384c-123">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="5384c-123">Office Live Meeting 2007</span></span>

<span data-ttu-id="5384c-124">在遷移期間，Office Communicator 2007 R2 使用者應使用 Lync Web App 2013 加入 Lync Server 2013 會議，直到他們的用戶端升級為止。</span><span class="sxs-lookup"><span data-stu-id="5384c-124">During migration, Office Communicator 2007 R2 users should use Lync Web App 2013 to join Lync Server 2013 meetings until their clients are upgraded.</span></span> <span data-ttu-id="5384c-125">請注意，Office Communicator 2007 R2 使用者可以繼續使用其現有的用戶端對 Lync Server 2013 進行顯示狀態和 IM 功能，但不支援會議功能。</span><span class="sxs-lookup"><span data-stu-id="5384c-125">Note that Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a><span data-ttu-id="5384c-126">依據使用者的會議需求移轉使用者</span><span class="sxs-lookup"><span data-stu-id="5384c-126">Migrating Users Based on Their Conferencing Needs</span></span>

<span data-ttu-id="5384c-127">**頻繁會議召集人。**    請考慮在程式中及早遷移常見的會議召集人，以利用[lync server 2013 中新的會議功能](lync-server-2013-new-conferencing-features.md)所述的新 Lync server 2013 和 Lync 2013 功能，以及[lync server 2013 中用戶端的新](lync-server-2013-what-s-new-for-clients.md)功能。</span><span class="sxs-lookup"><span data-stu-id="5384c-127">**Frequent meeting organizers.**   Consider migrating frequent meeting organizers early in the process so that they can take advantage of the new Lync Server 2013 and Lync 2013 features outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="5384c-128">**Live Meeting 使用者。**    如果您是從 Office 通訊伺服器 2007 R2 進行遷移，且您的使用者需要使用 Live Meeting 特有的 web 會議功能（特別是對大型會議和分割的會議室的支援），您可以使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="5384c-128">**Live Meeting users.**   If you are migrating from Office Communications Server 2007 R2 and you have users who need web conferencing features specific to Live Meeting—particularly support for large meetings and break-out rooms—you have the following options:</span></span>

  - <span data-ttu-id="5384c-129">貴公司如有提供 Live Meeting 服務，建議召集人使用這項服務。</span><span class="sxs-lookup"><span data-stu-id="5384c-129">Advise organizers to use the Live Meeting service, if available in your organization.</span></span>

  - <span data-ttu-id="5384c-130">請將召集人保留在舊版的 Office 通訊伺服器上，如此一來，他們就可以繼續排程伺服器型 Live Meeting web 會議。</span><span class="sxs-lookup"><span data-stu-id="5384c-130">Leave the organizers homed on the earlier version of Office Communications Server, so they can continue to schedule server-based Live Meeting web conferences.</span></span>

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a><span data-ttu-id="5384c-131">移轉現有的會議與會議內容</span><span class="sxs-lookup"><span data-stu-id="5384c-131">Migrating Existing Meetings and Meeting Content</span></span>

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a><span data-ttu-id="5384c-132">從 Lync Server 2010 遷移會議</span><span class="sxs-lookup"><span data-stu-id="5384c-132">Migrating Meetings from Lync Server 2010</span></span>

<span data-ttu-id="5384c-133">當您將使用者從 Lync Server 2010 移至 Lync Server 2013 時，下列資訊會隨之使用者帳戶移動：</span><span class="sxs-lookup"><span data-stu-id="5384c-133">When you move a user from Lync Server 2010 to Lync Server 2013, the following information moves with the user’s account:</span></span>

  - <span data-ttu-id="5384c-134">使用者已排定的會議。</span><span class="sxs-lookup"><span data-stu-id="5384c-134">Meetings already scheduled by the user.</span></span> <span data-ttu-id="5384c-135">這包括會議目錄及會議資料。</span><span class="sxs-lookup"><span data-stu-id="5384c-135">This includes conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="5384c-136">使用者的個人身分識別號碼 (PIN) 。</span><span class="sxs-lookup"><span data-stu-id="5384c-136">The user’s personal identification number (PIN).</span></span> <span data-ttu-id="5384c-137">直到過期或使用者要求新 PIN 前，使用者目前的 PIN 都持續有效。</span><span class="sxs-lookup"><span data-stu-id="5384c-137">The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="5384c-138">不過，下列使用者帳戶資訊不會移至新的伺服器：</span><span class="sxs-lookup"><span data-stu-id="5384c-138">However, the following user account information does not move to the new server:</span></span>

  - <span data-ttu-id="5384c-139">會議內容，例如 PowerPoint 簡報、白板內容和輪詢資料</span><span class="sxs-lookup"><span data-stu-id="5384c-139">Meeting content, for example PowerPoint presentations, whiteboard content, and poll data</span></span>

<span data-ttu-id="5384c-140">若要移動會議中已共用的內容，請使用 Move-CsUser Cmdlet 的 MoveMeetingContent 參數。</span><span class="sxs-lookup"><span data-stu-id="5384c-140">To move the content that has been shared in meetings, use the MoveMeetingContent parameter of the Move-CsUser cmdlet.</span></span> <span data-ttu-id="5384c-141">如需使用此 Cmdlet 的詳細資訊，請參閱 Lync Server 2013 Cmdlet 檔中的 [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) 。</span><span class="sxs-lookup"><span data-stu-id="5384c-141">For details about using this cmdlet, see [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) in the Lync Server 2013 cmdlets documentation.</span></span>

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a><span data-ttu-id="5384c-142">從 Office 通訊伺服器 2007 R2 遷移會議</span><span class="sxs-lookup"><span data-stu-id="5384c-142">Migrating Meetings from Office Communications Server 2007 R2</span></span>

<span data-ttu-id="5384c-143">Office 通訊伺服器 2007 R2 會議是電話會議 (conf://URL 首碼) 或網路會議 (meet://URL 首碼) 。</span><span class="sxs-lookup"><span data-stu-id="5384c-143">Office Communications Server 2007 R2 meetings are either conference calls (conf:// URL prefix) or web conferences (meet:// URL prefix).</span></span> <span data-ttu-id="5384c-144">Lync Server 2013 不支援這些早期的 conf://和 meet://會議，也不會與使用者帳戶一起遷移。</span><span class="sxs-lookup"><span data-stu-id="5384c-144">Lync Server 2013 does not support these earlier conf:// and meet:// conferences, and they are not migrated along with the user account.</span></span> <span data-ttu-id="5384c-145">遷移之後，您應該指示使用者更新其已排程的任何線上會議的連結。</span><span class="sxs-lookup"><span data-stu-id="5384c-145">After migration, you should instruct users to update the links for any online meetings they have scheduled.</span></span> <span data-ttu-id="5384c-146">使用者可以在安裝 Lync 2013 用戶端後，開啟已排程的會議邀請（更新會議 URL），然後將邀請重新傳送給參與者，以執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="5384c-146">They can do this after installing the Lync 2013 client by opening a scheduled meeting invitation—which updates the meeting URL—and resending the invitation to participants.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a><span data-ttu-id="5384c-147">Lync Server 2010 遷移期間的使用者經驗</span><span class="sxs-lookup"><span data-stu-id="5384c-147">User Experience during Lync Server 2010 Migration</span></span>

<span data-ttu-id="5384c-148">本節提供從 Lync 2010 遷移時，使用者的會議體驗摘要。</span><span class="sxs-lookup"><span data-stu-id="5384c-148">This section provides a summary of users’ conferencing experience when migrating from Lync 2010.</span></span> <span data-ttu-id="5384c-149">如需 Lync Server 2013 用戶端如何共存及與舊版用戶端及伺服器版本互動的詳細資訊，請參閱 [Lync 2013 中的用戶端互通性](lync-server-2013-client-interoperability-in-lync-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="5384c-149">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a><span data-ttu-id="5384c-150">加入 lync Server 2010 與 Lync 2013 用戶端的會議</span><span class="sxs-lookup"><span data-stu-id="5384c-150">Joining Lync Server 2010 Meetings with a Lync 2013 Client</span></span>

<span data-ttu-id="5384c-151">從 Lync Server 2010 遷移期間，當使用者使用 Lync 2013 用戶端加入 Lync Server 2010 會議時，可能會有一段共存。</span><span class="sxs-lookup"><span data-stu-id="5384c-151">During migration from Lync Server 2010, there may be a period of coexistence when users join Lync Server 2010 meetings with a Lync 2013 client.</span></span> <span data-ttu-id="5384c-152">這些使用者可以存取 Lync 2013 用戶端功能，但有下列例外：</span><span class="sxs-lookup"><span data-stu-id="5384c-152">These users have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="5384c-153">在 [ **參與者** 管理] 選項中，透過指向會議視窗中的 [人員] 圖示可供存取，[ **無會議 IM** ] 選項不會正常運作。</span><span class="sxs-lookup"><span data-stu-id="5384c-153">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="5384c-154">圖庫 View 在影片會議中無法運作。</span><span class="sxs-lookup"><span data-stu-id="5384c-154">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="5384c-155">使用者只會看到使用中的音箱，而不是所有的揚聲器。</span><span class="sxs-lookup"><span data-stu-id="5384c-155">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="5384c-156">在 [ **選擇版面** 配置選項] 清單中，無法使用 **圖庫 View** 功能</span><span class="sxs-lookup"><span data-stu-id="5384c-156">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="5384c-157">在 [影片會議] 中，預設會顯示參與者清單。</span><span class="sxs-lookup"><span data-stu-id="5384c-157">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="5384c-158">以滑鼠右鍵按一下參與者清單中的使用者時，會無法使用 [影片] [影片] 和 [**固定至圖庫**]**的 [工作**表參與者管理] 選項。</span><span class="sxs-lookup"><span data-stu-id="5384c-158">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a><span data-ttu-id="5384c-159">Office 通訊伺服器 2007 R2 遷移期間的使用者經驗</span><span class="sxs-lookup"><span data-stu-id="5384c-159">User Experience during Office Communications Server 2007 R2 Migration</span></span>

<span data-ttu-id="5384c-160">本節提供在安裝 Lync 2013 之前和之後，從 Office 通訊伺服器 2007 R2 進行遷移時，使用者的會議體驗摘要。</span><span class="sxs-lookup"><span data-stu-id="5384c-160">This section provides a summary of users’ conferencing experience when migrating from Office Communications Server 2007 R2, both before and after Lync 2013 is installed.</span></span> <span data-ttu-id="5384c-161">如需 Lync Server 2013 用戶端如何共存及與舊版用戶端及伺服器版本互動的詳細資訊，請參閱 [Lync 2013 中的用戶端互通性](lync-server-2013-client-interoperability-in-lync-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="5384c-161">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a><span data-ttu-id="5384c-162">在遷移使用者帳戶之後，安裝 Lync 2013 之前</span><span class="sxs-lookup"><span data-stu-id="5384c-162">After User Account is Migrated, Before Lync 2013 Is Installed</span></span>

<span data-ttu-id="5384c-163">將使用者遷移至 Lync Server 2013 伺服器之後，但在安裝新用戶端之前，Office Communicator 2007 R2 使用者可以繼續使用其現有的2013用戶端，以進行顯示狀態和 IM 功能，但不支援會議功能。</span><span class="sxs-lookup"><span data-stu-id="5384c-163">After a user is migrated to the Lync Server 2013 server, but before new clients are installed, Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a><span data-ttu-id="5384c-164">在使用者帳戶遷移後，安裝 Lync 2013 之後</span><span class="sxs-lookup"><span data-stu-id="5384c-164">After User Account is Migrated, After Lync 2013 Is Installed</span></span>

<span data-ttu-id="5384c-165">當已遷移的使用者安裝 Lync 2013 時，也會安裝 Lync 2013 的線上會議增益集。</span><span class="sxs-lookup"><span data-stu-id="5384c-165">When a migrated user installs Lync 2013, the Online Meeting Add-in for Lync 2013 is installed too.</span></span> <span data-ttu-id="5384c-166">此作法具有下列影響：</span><span class="sxs-lookup"><span data-stu-id="5384c-166">This has the following effects:</span></span>

  - <span data-ttu-id="5384c-167">所有在此之後排程的會議皆會使用 https:// 位址的新會議格式，而不再使用舊版的 meet:// Live Meeting 位址。</span><span class="sxs-lookup"><span data-stu-id="5384c-167">All subsequently scheduled meetings use the new meeting format, which uses an https:// address instead of the legacy meet:// Live Meeting address.</span></span>

  - <span data-ttu-id="5384c-168">在 Lync 2013 的 IT 管理部署中，管理員可以選擇卸載 Microsoft Office Outlook 的會議增益集，以用於排程 Live Meeting 伺服器和服務型會議。</span><span class="sxs-lookup"><span data-stu-id="5384c-168">In an IT-managed deployment of Lync 2013, the administrator has the option of uninstalling the Conferencing Add-in for Microsoft Office Outlook, which is used to schedule Live Meeting server and service-based meetings.</span></span> <span data-ttu-id="5384c-169">不過您可能還有使用者需要排程 Live Meeting 服務會議。</span><span class="sxs-lookup"><span data-stu-id="5384c-169">However, you may have users who need to continue to schedule Live Meeting service meetings.</span></span> <span data-ttu-id="5384c-170">此時，您可以考慮讓兩者同時並存。</span><span class="sxs-lookup"><span data-stu-id="5384c-170">In this case, you can allow both add-ins to coexist.</span></span>

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a><span data-ttu-id="5384c-171">使用舊版用戶端之同盟組織的會議</span><span class="sxs-lookup"><span data-stu-id="5384c-171">Meetings with Federated Organizations that Use Previous Clients</span></span>

<span data-ttu-id="5384c-172">同盟組織中使用 Microsoft Office Communicator 2007 的使用者，如果召集人鎖定了該會議，則無法在組織中加入 Lync Server 2013 會議。</span><span class="sxs-lookup"><span data-stu-id="5384c-172">Users in federated organizations who are using Microsoft Office Communicator 2007 cannot join Lync Server 2013 meetings in your organization if those meetings are locked by the organizer.</span></span> <span data-ttu-id="5384c-173">您必須在 Lync Server 2013 中重排這些會議，以便在同盟參與者使用新的 HTTPs://會議 URL 加入會議時，他們可以使用 Lync Web App。</span><span class="sxs-lookup"><span data-stu-id="5384c-173">You have to reschedule these meetings in Lync Server 2013 so when federated participants join the meeting by using the new https:// meeting URL, they can use Lync Web App.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

