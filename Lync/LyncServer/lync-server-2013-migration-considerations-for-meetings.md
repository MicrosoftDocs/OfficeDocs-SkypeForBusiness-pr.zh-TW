---
title: Lync Server 2013：會議的遷移考慮
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
ms.openlocfilehash: 6af94514360509d4f608a21228b2fecf9a522007
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a><span data-ttu-id="7df8a-102">Lync Server 2013 中的會議遷移考慮</span><span class="sxs-lookup"><span data-stu-id="7df8a-102">Migration considerations for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7df8a-103">_**主題上次修改日期：** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="7df8a-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="7df8a-104">本節將討論下列主題：</span><span class="sxs-lookup"><span data-stu-id="7df8a-104">The following topics are discussed in this section:</span></span>

  - <span data-ttu-id="7df8a-105">在 Microsoft Lync Server 2013 中對會議所做的變更</span><span class="sxs-lookup"><span data-stu-id="7df8a-105">Changes to meetings in Microsoft Lync Server 2013</span></span>

  - <span data-ttu-id="7df8a-106">根據其會議需求來遷移使用者</span><span class="sxs-lookup"><span data-stu-id="7df8a-106">Migrating users based on their conferencing needs</span></span>

  - <span data-ttu-id="7df8a-107">遷移現有的會議與會議內容</span><span class="sxs-lookup"><span data-stu-id="7df8a-107">Migrating existing meetings and meeting content</span></span>

  - <span data-ttu-id="7df8a-108">在 Lync Server 2010 遷移期間的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="7df8a-108">User experience during Lync Server 2010 migration</span></span>

  - <span data-ttu-id="7df8a-109">Office 通訊伺服器 2007 R2 遷移期間的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="7df8a-109">User Experience during Office Communications Server 2007 R2 migration</span></span>

  - <span data-ttu-id="7df8a-110">Microsoft Lync 2013 與舊版伺服器版本的會議相容性</span><span class="sxs-lookup"><span data-stu-id="7df8a-110">Microsoft Lync 2013 compatibility with meetings on earlier server versions</span></span>

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a><span data-ttu-id="7df8a-111">Lync Server 2013 中的會議變更</span><span class="sxs-lookup"><span data-stu-id="7df8a-111">Changes to Meetings in Lync Server 2013</span></span>

<span data-ttu-id="7df8a-112">**Lync Server 2013 功能。**   Lync server 2013 提供新的會議功能，在使用者的帳戶移至 lync Server 2013 並以 lync 2013 用戶端登入之後，使用者就能使用。</span><span class="sxs-lookup"><span data-stu-id="7df8a-112">**Lync Server 2013 features.**   Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="7df8a-113">新功能在[Lync server 2013 的新會議功能](lync-server-2013-new-conferencing-features.md)中有說明，以及[lync server 2013 中用戶端的新](lync-server-2013-what-s-new-for-clients.md)功能。</span><span class="sxs-lookup"><span data-stu-id="7df8a-113">New features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="7df8a-114">**會議 URL。**   就像在 lync server 2010 中，lync server 2013 中所有新近排程的會議都有 HTTPS://的 URL 首碼，而現有的會議則與使用者帳戶一起遷移。</span><span class="sxs-lookup"><span data-stu-id="7df8a-114">**Meeting URL.**   As in Lync Server 2010, all newly scheduled meetings in Lync Server 2013 have a URL prefix of https:// and existing meetings migrate along with user accounts.</span></span> <span data-ttu-id="7df8a-115">不過，Lync Server 2013 不支援 Office 通訊伺服器 2007 R2 會議呼叫（conf://URL 首碼）或 web 會議（meet://URL 首碼）。</span><span class="sxs-lookup"><span data-stu-id="7df8a-115">However, Lync Server 2013 does not support the Office Communications Server 2007 R2 conference call (conf:// URL prefix) or web conference (meet:// URL prefix).</span></span> <span data-ttu-id="7df8a-116">如需詳細資訊，請參閱本主題稍後的「從 Office 通訊伺服器 2007 R2 遷移會議」。</span><span class="sxs-lookup"><span data-stu-id="7df8a-116">See “Migrating Meetings from Office Communications Server 2007 R2” later in this topic for more information.</span></span>

<span data-ttu-id="7df8a-117">**用戶端支援。**   與 lync server 2010 不同，lync server 2013 不支援 Office Communicator 用戶端進行會議。</span><span class="sxs-lookup"><span data-stu-id="7df8a-117">**Client support.**   Unlike Lync Server 2010, Lync Server 2013 does not support Office Communicator clients for conferencing.</span></span> <span data-ttu-id="7df8a-118">您無法使用下列用戶端來加入透過 Lync 2013 的線上會議增益集排程的會議：</span><span class="sxs-lookup"><span data-stu-id="7df8a-118">You cannot use the following clients to join meetings scheduled through the Online Meeting Add-in for Lync 2013:</span></span>

  - <span data-ttu-id="7df8a-119">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="7df8a-119">Office Communicator 2007 R2</span></span>

  - <span data-ttu-id="7df8a-120">Microsoft Office 通訊伺服器 2007 R2 助理</span><span class="sxs-lookup"><span data-stu-id="7df8a-120">Microsoft Office Communications Server 2007 R2 Attendant</span></span>

  - <span data-ttu-id="7df8a-121">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="7df8a-121">Office Communicator 2007</span></span>

  - <span data-ttu-id="7df8a-122">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="7df8a-122">Office Live Meeting 2007</span></span>

<span data-ttu-id="7df8a-123">在遷移期間，Office Communicator 2007 R2 使用者應該使用 Lync Web App 2013 加入 Lync Server 2013 會議，直到他們的用戶端升級為止。</span><span class="sxs-lookup"><span data-stu-id="7df8a-123">During migration, Office Communicator 2007 R2 users should use Lync Web App 2013 to join Lync Server 2013 meetings until their clients are upgraded.</span></span> <span data-ttu-id="7df8a-124">請注意，Office Communicator 2007 R2 使用者可以繼續針對 Lync Server 2013 使用現有的用戶端，以取得目前狀態與 IM 功能，但不支援會議功能。</span><span class="sxs-lookup"><span data-stu-id="7df8a-124">Note that Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a><span data-ttu-id="7df8a-125">根據其會議需求來遷移使用者</span><span class="sxs-lookup"><span data-stu-id="7df8a-125">Migrating Users Based on Their Conferencing Needs</span></span>

<span data-ttu-id="7df8a-126">**經常會議召集人。**   考慮在程式的早期階段遷移會議召集人，讓他們可以利用[lync Server 2013 中新](lync-server-2013-new-conferencing-features.md)的 [會議] 功能所述的新 Lync server 2013 和 Lync 2013 功能，以及[lync server 2013 中用戶端的新](lync-server-2013-what-s-new-for-clients.md)功能。</span><span class="sxs-lookup"><span data-stu-id="7df8a-126">**Frequent meeting organizers.**   Consider migrating frequent meeting organizers early in the process so that they can take advantage of the new Lync Server 2013 and Lync 2013 features outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="7df8a-127">**Live Meeting 使用者。**   如果您是從 Office 通訊伺服器 2007 R2 進行遷移，且您的使用者需要使用 Live Meeting 所特有的 web 會議功能，就是您可以使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="7df8a-127">**Live Meeting users.**   If you are migrating from Office Communications Server 2007 R2 and you have users who need web conferencing features specific to Live Meeting—particularly support for large meetings and break-out rooms—you have the following options:</span></span>

  - <span data-ttu-id="7df8a-128">建議召集人使用 Live Meeting 服務（如果您的組織中有提供）。</span><span class="sxs-lookup"><span data-stu-id="7df8a-128">Advise organizers to use the Live Meeting service, if available in your organization.</span></span>

  - <span data-ttu-id="7df8a-129">將召集人留在舊版 Office 通訊伺服器上，讓他們可以繼續排程以伺服器為基礎的 Live Meeting web 會議。</span><span class="sxs-lookup"><span data-stu-id="7df8a-129">Leave the organizers homed on the earlier version of Office Communications Server, so they can continue to schedule server-based Live Meeting web conferences.</span></span>

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a><span data-ttu-id="7df8a-130">遷移現有的會議與會議內容</span><span class="sxs-lookup"><span data-stu-id="7df8a-130">Migrating Existing Meetings and Meeting Content</span></span>

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a><span data-ttu-id="7df8a-131">從 Lync Server 2010 遷移會議</span><span class="sxs-lookup"><span data-stu-id="7df8a-131">Migrating Meetings from Lync Server 2010</span></span>

<span data-ttu-id="7df8a-132">當您將使用者從 Lync Server 2010 移至 Lync Server 2013 時，下列資訊會與使用者帳戶一起移動：</span><span class="sxs-lookup"><span data-stu-id="7df8a-132">When you move a user from Lync Server 2010 to Lync Server 2013, the following information moves with the user’s account:</span></span>

  - <span data-ttu-id="7df8a-133">已由使用者排程的會議。</span><span class="sxs-lookup"><span data-stu-id="7df8a-133">Meetings already scheduled by the user.</span></span> <span data-ttu-id="7df8a-134">這包含會議目錄和會議資料。</span><span class="sxs-lookup"><span data-stu-id="7df8a-134">This includes conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="7df8a-135">使用者的個人身分識別號碼（PIN）。</span><span class="sxs-lookup"><span data-stu-id="7df8a-135">The user’s personal identification number (PIN).</span></span> <span data-ttu-id="7df8a-136">使用者目前的 PIN 會持續起作用，直到過期為止，或使用者要求新的 PIN。</span><span class="sxs-lookup"><span data-stu-id="7df8a-136">The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="7df8a-137">不過，下列使用者帳戶資訊不會移到新伺服器：</span><span class="sxs-lookup"><span data-stu-id="7df8a-137">However, the following user account information does not move to the new server:</span></span>

  - <span data-ttu-id="7df8a-138">會議內容，例如 PowerPoint 簡報、白板內容，以及投票資料</span><span class="sxs-lookup"><span data-stu-id="7df8a-138">Meeting content, for example PowerPoint presentations, whiteboard content, and poll data</span></span>

<span data-ttu-id="7df8a-139">若要移動已在會議中共用的內容，請使用 Move-csuser Cmdlet 的 MoveMeetingContent 參數。</span><span class="sxs-lookup"><span data-stu-id="7df8a-139">To move the content that has been shared in meetings, use the MoveMeetingContent parameter of the Move-CsUser cmdlet.</span></span> <span data-ttu-id="7df8a-140">如需有關使用此 Cmdlet 的詳細資訊，請參閱 Lync Server 2013 Cmdlet 檔中的[移動流覽 move-csuser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) 。</span><span class="sxs-lookup"><span data-stu-id="7df8a-140">For details about using this cmdlet, see [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) in the Lync Server 2013 cmdlets documentation.</span></span>

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a><span data-ttu-id="7df8a-141">從 Office 通訊伺服器 2007 R2 遷移會議</span><span class="sxs-lookup"><span data-stu-id="7df8a-141">Migrating Meetings from Office Communications Server 2007 R2</span></span>

<span data-ttu-id="7df8a-142">Office 通訊伺服器 2007 R2 會議可以是電話會議（conf://URL 首碼）或網路會議（meet://URL 首碼）。</span><span class="sxs-lookup"><span data-stu-id="7df8a-142">Office Communications Server 2007 R2 meetings are either conference calls (conf:// URL prefix) or web conferences (meet:// URL prefix).</span></span> <span data-ttu-id="7df8a-143">Lync Server 2013 不支援這些較舊的 conf://和 meet://會議，且不會與使用者帳戶一起遷移。</span><span class="sxs-lookup"><span data-stu-id="7df8a-143">Lync Server 2013 does not support these earlier conf:// and meet:// conferences, and they are not migrated along with the user account.</span></span> <span data-ttu-id="7df8a-144">遷移之後，您應該指示使用者更新已排程之任何線上會議的連結。</span><span class="sxs-lookup"><span data-stu-id="7df8a-144">After migration, you should instruct users to update the links for any online meetings they have scheduled.</span></span> <span data-ttu-id="7df8a-145">他們可以在安裝 Lync 2013 用戶端後執行此動作，方法是開啟已排程的會議邀請，這會更新會議 URL，並重新傳送邀請給參與者。</span><span class="sxs-lookup"><span data-stu-id="7df8a-145">They can do this after installing the Lync 2013 client by opening a scheduled meeting invitation—which updates the meeting URL—and resending the invitation to participants.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a><span data-ttu-id="7df8a-146">在 Lync Server 2010 遷移期間的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="7df8a-146">User Experience during Lync Server 2010 Migration</span></span>

<span data-ttu-id="7df8a-147">本節提供從 Lync 2010 遷移時使用者的會議體驗摘要。</span><span class="sxs-lookup"><span data-stu-id="7df8a-147">This section provides a summary of users’ conferencing experience when migrating from Lync 2010.</span></span> <span data-ttu-id="7df8a-148">如需有關 Lync Server 2013 用戶端如何共存以及與舊版用戶端和伺服器版本互動的詳細資訊，請參閱[Lync 2013 中的用戶端互通性](lync-server-2013-client-interoperability-in-lync-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="7df8a-148">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a><span data-ttu-id="7df8a-149">使用 Lync 2013 用戶端加入 Lync Server 2010 會議</span><span class="sxs-lookup"><span data-stu-id="7df8a-149">Joining Lync Server 2010 Meetings with a Lync 2013 Client</span></span>

<span data-ttu-id="7df8a-150">從 Lync Server 2010 遷移期間，您可能會在使用者使用 Lync 2013 用戶端加入 Lync Server 2010 會議時，共存一段時間。</span><span class="sxs-lookup"><span data-stu-id="7df8a-150">During migration from Lync Server 2010, there may be a period of coexistence when users join Lync Server 2010 meetings with a Lync 2013 client.</span></span> <span data-ttu-id="7df8a-151">這些使用者可以存取 Lync 2013 用戶端的功能，但有下列例外狀況：</span><span class="sxs-lookup"><span data-stu-id="7df8a-151">These users have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="7df8a-152">在**參與者**管理選項（可透過指向會議視窗中的 [人員] 圖示來存取），[**無會議 IM** ] 選項不起作用。</span><span class="sxs-lookup"><span data-stu-id="7df8a-152">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="7df8a-153">[圖庫] 視圖在視訊會議中不起作用。</span><span class="sxs-lookup"><span data-stu-id="7df8a-153">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="7df8a-154">使用者只會看到現用喇叭，而不是所有喇叭。</span><span class="sxs-lookup"><span data-stu-id="7df8a-154">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="7df8a-155">在 [**挑選版面**配置選項] 清單中，[**庫視圖**] 無法使用</span><span class="sxs-lookup"><span data-stu-id="7df8a-155">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="7df8a-156">「參與者清單」預設會顯示在 [視訊會議] 中。</span><span class="sxs-lookup"><span data-stu-id="7df8a-156">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="7df8a-157">在參與者清單中以滑鼠右鍵按一下使用者時，無法使用 [**鎖定影片焦點**] 和 [**釘選到圖庫**] 參與者管理選項。</span><span class="sxs-lookup"><span data-stu-id="7df8a-157">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a><span data-ttu-id="7df8a-158">Office 通訊伺服器 2007 R2 遷移期間的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="7df8a-158">User Experience during Office Communications Server 2007 R2 Migration</span></span>

<span data-ttu-id="7df8a-159">本節提供在安裝 Lync 2013 之前和之後從 Office 通訊伺服器 2007 R2 進行遷移時的使用者會議體驗摘要。</span><span class="sxs-lookup"><span data-stu-id="7df8a-159">This section provides a summary of users’ conferencing experience when migrating from Office Communications Server 2007 R2, both before and after Lync 2013 is installed.</span></span> <span data-ttu-id="7df8a-160">如需有關 Lync Server 2013 用戶端如何共存以及與舊版用戶端和伺服器版本互動的詳細資訊，請參閱[Lync 2013 中的用戶端互通性](lync-server-2013-client-interoperability-in-lync-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="7df8a-160">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a><span data-ttu-id="7df8a-161">在已遷移使用者帳戶之後，安裝 Lync 2013 之前</span><span class="sxs-lookup"><span data-stu-id="7df8a-161">After User Account is Migrated, Before Lync 2013 Is Installed</span></span>

<span data-ttu-id="7df8a-162">在使用者遷移至 Lync Server 2013 伺服器之後，但在安裝新的用戶端之前，Office Communicator 2007 R2 使用者可以繼續針對 Lync Server 2013 使用現有的用戶端，以瞭解目前狀態與 IM 功能，但是會議功能不會受.</span><span class="sxs-lookup"><span data-stu-id="7df8a-162">After a user is migrated to the Lync Server 2013 server, but before new clients are installed, Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a><span data-ttu-id="7df8a-163">在已安裝 Lync 2013 之後，進行使用者帳戶遷移之後</span><span class="sxs-lookup"><span data-stu-id="7df8a-163">After User Account is Migrated, After Lync 2013 Is Installed</span></span>

<span data-ttu-id="7df8a-164">當已遷移的使用者安裝 Lync 2013 時，也會安裝 Lync 2013 的線上會議增益集。</span><span class="sxs-lookup"><span data-stu-id="7df8a-164">When a migrated user installs Lync 2013, the Online Meeting Add-in for Lync 2013 is installed too.</span></span> <span data-ttu-id="7df8a-165">這會產生下列效果：</span><span class="sxs-lookup"><span data-stu-id="7df8a-165">This has the following effects:</span></span>

  - <span data-ttu-id="7df8a-166">所有後續排程的會議都會使用新的會議格式，這會使用 HTTPs://位址，而不是舊版 meet://Live 會議位址。</span><span class="sxs-lookup"><span data-stu-id="7df8a-166">All subsequently scheduled meetings use the new meeting format, which uses an https:// address instead of the legacy meet:// Live Meeting address.</span></span>

  - <span data-ttu-id="7df8a-167">在 Lync 2013 的 IT 管理部署中，系統管理員可以選擇卸載 Microsoft Office Outlook 的會議增益集，這是用來排程 Live Meeting 伺服器與服務的會議。</span><span class="sxs-lookup"><span data-stu-id="7df8a-167">In an IT-managed deployment of Lync 2013, the administrator has the option of uninstalling the Conferencing Add-in for Microsoft Office Outlook, which is used to schedule Live Meeting server and service-based meetings.</span></span> <span data-ttu-id="7df8a-168">不過，您可能需要繼續排程 Live Meeting 服務會議的使用者。</span><span class="sxs-lookup"><span data-stu-id="7df8a-168">However, you may have users who need to continue to schedule Live Meeting service meetings.</span></span> <span data-ttu-id="7df8a-169">在這種情況下，您可以允許兩個增益集共存。</span><span class="sxs-lookup"><span data-stu-id="7df8a-169">In this case, you can allow both add-ins to coexist.</span></span>

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a><span data-ttu-id="7df8a-170">與使用舊版客戶的同盟組織進行會議</span><span class="sxs-lookup"><span data-stu-id="7df8a-170">Meetings with Federated Organizations that Use Previous Clients</span></span>

<span data-ttu-id="7df8a-171">使用 Microsoft Office Communicator 2007 的同盟組織中的使用者，如果召集人已鎖定這些會議，則無法加入貴組織中的 Lync Server 2013 會議。</span><span class="sxs-lookup"><span data-stu-id="7df8a-171">Users in federated organizations who are using Microsoft Office Communicator 2007 cannot join Lync Server 2013 meetings in your organization if those meetings are locked by the organizer.</span></span> <span data-ttu-id="7df8a-172">您必須在 Lync Server 2013 中重新安排這些會議，以便在聯盟參與者使用新的 HTTPs://會議 URL 加入會議時，他們可以使用 Lync Web App。</span><span class="sxs-lookup"><span data-stu-id="7df8a-172">You have to reschedule these meetings in Lync Server 2013 so when federated participants join the meeting by using the new https:// meeting URL, they can use Lync Web App.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

