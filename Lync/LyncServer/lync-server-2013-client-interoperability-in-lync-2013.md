---
title: Lync Server 2013： Lync 2013 中的用戶端互通性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 437051279393b9dedc7c4def0c75cd119cded914
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="client-interoperability-in-lync-2013"></a><span data-ttu-id="c9731-102">Lync 2013 中的用戶端互通性</span><span class="sxs-lookup"><span data-stu-id="c9731-102">Client interoperability in Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9731-103">_**主題上次修改日期：** 2016-03-04_</span><span class="sxs-lookup"><span data-stu-id="c9731-103">_**Topic Last Modified:** 2016-03-04_</span></span>

<span data-ttu-id="c9731-104">本主題討論 Microsoft Lync Server 2013 用戶端與舊版 Lync Server 和 Office 通訊伺服器上的用戶端共存及互動的能力。</span><span class="sxs-lookup"><span data-stu-id="c9731-104">This topic discusses the ability of Microsoft Lync Server 2013 clients to coexist and interact with clients from earlier versions of Lync Server and Office Communications Server.</span></span>

<div>

## <a name="server-and-client-compatibility"></a><span data-ttu-id="c9731-105">伺服器與用戶端相容性</span><span class="sxs-lookup"><span data-stu-id="c9731-105">Server and Client Compatibility</span></span>

<span data-ttu-id="c9731-106">下表顯示支援的用戶端版本和伺服器版本組合。</span><span class="sxs-lookup"><span data-stu-id="c9731-106">The following table shows the supported combinations of client versions and server versions.</span></span> <span data-ttu-id="c9731-107">此表格指出當用戶端嘗試連線至指出的伺服器時，是否支援登入。</span><span class="sxs-lookup"><span data-stu-id="c9731-107">This table indicates whether sign-in is supported when the client attempts to connect to the server indicated.</span></span> <span data-ttu-id="c9731-108">Lync Server 2013 支援舊版的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="c9731-108">Lync Server 2013 supports the previous client version.</span></span> <span data-ttu-id="c9731-109">此外，與舊版不同的是，Lync Server 2010 支援新的 Lync 2013 用戶端。</span><span class="sxs-lookup"><span data-stu-id="c9731-109">Also, unlike previous releases, Lync Server 2010 supports the new Lync 2013 clients.</span></span> <span data-ttu-id="c9731-110">這可讓從 Lync Server 2010 升級的組織，將新的用戶端與 Lync Server 升級獨立。</span><span class="sxs-lookup"><span data-stu-id="c9731-110">This allows organizations who are upgrading from Lync Server 2010 to roll out new clients independent of Lync Server upgrades.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9731-111">用戶端</span><span class="sxs-lookup"><span data-stu-id="c9731-111">Client</span></span></th>
<th><span data-ttu-id="c9731-112">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9731-112">Lync Server 2013</span></span></th>
<th><span data-ttu-id="c9731-113">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="c9731-113">Lync Server 2010</span></span></th>
<th><span data-ttu-id="c9731-114">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="c9731-114">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9731-115">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="c9731-115">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="c9731-116">支援</span><span class="sxs-lookup"><span data-stu-id="c9731-116">Supported</span></span></p></td>
<td><p><span data-ttu-id="c9731-117">Supported5</span><span class="sxs-lookup"><span data-stu-id="c9731-117">Supported5</span></span></p></td>
<td><p><span data-ttu-id="c9731-118">不支援</span><span class="sxs-lookup"><span data-stu-id="c9731-118">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9731-119">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="c9731-119">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="c9731-120">支援</span><span class="sxs-lookup"><span data-stu-id="c9731-120">Supported</span></span></p></td>
<td><p><span data-ttu-id="c9731-121">支援</span><span class="sxs-lookup"><span data-stu-id="c9731-121">Supported</span></span></p></td>
<td><p><span data-ttu-id="c9731-122">不支援</span><span class="sxs-lookup"><span data-stu-id="c9731-122">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9731-123">Lync Web App 2013</span><span class="sxs-lookup"><span data-stu-id="c9731-123">Lync Web App 2013</span></span></p></td>
<td><p><span data-ttu-id="c9731-124">支援</span><span class="sxs-lookup"><span data-stu-id="c9731-124">Supported</span></span></p></td>
<td><p><span data-ttu-id="c9731-125">不支援</span><span class="sxs-lookup"><span data-stu-id="c9731-125">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c9731-126">不支援</span><span class="sxs-lookup"><span data-stu-id="c9731-126">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9731-127">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="c9731-127">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="c9731-128">支援</span><span class="sxs-lookup"><span data-stu-id="c9731-128">Supported</span></span></p></td>
<td><p><span data-ttu-id="c9731-129">支援</span><span class="sxs-lookup"><span data-stu-id="c9731-129">Supported</span></span></p></td>
<td><p><span data-ttu-id="c9731-130">不支援</span><span class="sxs-lookup"><span data-stu-id="c9731-130">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9731-131">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="c9731-131">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="c9731-132">支援</span><span class="sxs-lookup"><span data-stu-id="c9731-132">Supported</span></span></p></td>
<td><p><span data-ttu-id="c9731-133">支援</span><span class="sxs-lookup"><span data-stu-id="c9731-133">Supported</span></span></p></td>
<td><p><span data-ttu-id="c9731-134">不支援</span><span class="sxs-lookup"><span data-stu-id="c9731-134">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9731-135">Lync 2010 群組聊天</span><span class="sxs-lookup"><span data-stu-id="c9731-135">Lync 2010 Group Chat</span></span></p></td>
<td><p><span data-ttu-id="c9731-136">Supported1</span><span class="sxs-lookup"><span data-stu-id="c9731-136">Supported1</span></span></p></td>
<td><p><span data-ttu-id="c9731-137">Supported2</span><span class="sxs-lookup"><span data-stu-id="c9731-137">Supported2</span></span></p></td>
<td><p><span data-ttu-id="c9731-138">不適用</span><span class="sxs-lookup"><span data-stu-id="c9731-138">Not Applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9731-139">Lync Web App 2010</span><span class="sxs-lookup"><span data-stu-id="c9731-139">Lync Web App 2010</span></span></p></td>
<td><p><span data-ttu-id="c9731-140">不支援</span><span class="sxs-lookup"><span data-stu-id="c9731-140">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c9731-141">支援</span><span class="sxs-lookup"><span data-stu-id="c9731-141">Supported</span></span></p></td>
<td><p><span data-ttu-id="c9731-142">不支援</span><span class="sxs-lookup"><span data-stu-id="c9731-142">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9731-143">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="c9731-143">Lync 2010 Attendee</span></span></p></td>
<td><p><span data-ttu-id="c9731-144">非 Supported3</span><span class="sxs-lookup"><span data-stu-id="c9731-144">Not Supported3</span></span></p></td>
<td><p><span data-ttu-id="c9731-145">支援</span><span class="sxs-lookup"><span data-stu-id="c9731-145">Supported</span></span></p></td>
<td><p><span data-ttu-id="c9731-146">不支援</span><span class="sxs-lookup"><span data-stu-id="c9731-146">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9731-147">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="c9731-147">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="c9731-148">Interoperable4</span><span class="sxs-lookup"><span data-stu-id="c9731-148">Interoperable4</span></span></p></td>
<td><p><span data-ttu-id="c9731-149">支援</span><span class="sxs-lookup"><span data-stu-id="c9731-149">Supported</span></span></p></td>
<td><p><span data-ttu-id="c9731-150">支援</span><span class="sxs-lookup"><span data-stu-id="c9731-150">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9731-151">Microsoft Office Communications Server 2007 R2 Attendant</span><span class="sxs-lookup"><span data-stu-id="c9731-151">Microsoft Office Communications Server 2007 R2 Attendant</span></span></p></td>
<td><p><span data-ttu-id="c9731-152">不支援</span><span class="sxs-lookup"><span data-stu-id="c9731-152">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c9731-153">支援</span><span class="sxs-lookup"><span data-stu-id="c9731-153">Supported</span></span></p></td>
<td><p><span data-ttu-id="c9731-154">支援</span><span class="sxs-lookup"><span data-stu-id="c9731-154">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9731-155">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="c9731-155">Office Communicator 2007</span></span></p></td>
<td><p><span data-ttu-id="c9731-156">不支援</span><span class="sxs-lookup"><span data-stu-id="c9731-156">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c9731-157">支援</span><span class="sxs-lookup"><span data-stu-id="c9731-157">Supported</span></span></p></td>
<td><p><span data-ttu-id="c9731-158">支援</span><span class="sxs-lookup"><span data-stu-id="c9731-158">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9731-159">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="c9731-159">Office Live Meeting 2007</span></span></p></td>
<td><p><span data-ttu-id="c9731-160">不支援</span><span class="sxs-lookup"><span data-stu-id="c9731-160">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c9731-161">支援</span><span class="sxs-lookup"><span data-stu-id="c9731-161">Supported</span></span></p></td>
<td><p><span data-ttu-id="c9731-162">支援</span><span class="sxs-lookup"><span data-stu-id="c9731-162">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9731-163">Lync Windows Store 應用程式</span><span class="sxs-lookup"><span data-stu-id="c9731-163">Lync Windows Store app</span></span></p></td>
<td><p><span data-ttu-id="c9731-164">支援</span><span class="sxs-lookup"><span data-stu-id="c9731-164">Supported</span></span></p></td>
<td><p><span data-ttu-id="c9731-165">支援</span><span class="sxs-lookup"><span data-stu-id="c9731-165">Supported</span></span></p></td>
<td><p><span data-ttu-id="c9731-166">不支援</span><span class="sxs-lookup"><span data-stu-id="c9731-166">Not Supported</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c9731-167">1For 詳細資料，請參閱[從 Lync server 2010，Group chat 或 Office 通訊伺服器 2007 R2 群組聊天至 Lync server 2013，Persistent Chat server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="c9731-167">1For details, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="c9731-168">2In Microsoft Lync Server 2010，群組聊天伺服器會提供群組聊天功能，這是 Lync Server 2010 的協力廠商信任應用程式。</span><span class="sxs-lookup"><span data-stu-id="c9731-168">2In Microsoft Lync Server 2010, group chat functionality was available with Group Chat Server, a third-party trusted application for Lync Server 2010.</span></span> <span data-ttu-id="c9731-169">Lync 2013 用戶端與 Lync Server 2010 （群組聊天）不相容。</span><span class="sxs-lookup"><span data-stu-id="c9731-169">Lync 2013 clients are not compatible with Lync Server 2010, Group Chat.</span></span>

<span data-ttu-id="c9731-170">3Lync Web App 2013 現在提供完整的會議體驗，包括電腦音訊和影片，且被視為 Lync 2010 出席者的取代。</span><span class="sxs-lookup"><span data-stu-id="c9731-170">3Lync Web App 2013 now provides a full in-meeting experience, including computer audio and video, and is considered the replacement for Lync 2010 Attendee.</span></span> <span data-ttu-id="c9731-171">只有當您使用不受支援的瀏覽器 (Internet Explorer 6 或 Internet Explorer 7) 與 Windows XP 時，lync 2010 出席者才會連線至 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="c9731-171">Lync 2010 Attendee will connect to Lync Server 2013 only when you are using an unsupported browser (Internet Explorer 6 or Internet Explorer 7) and Windows XP.</span></span>

<span data-ttu-id="c9731-172">Office Communicator 2007 R2 中的4The 目前狀態和 IM 功能與 Lync Server 2013 相容，但會議功能卻不相容。</span><span class="sxs-lookup"><span data-stu-id="c9731-172">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="c9731-173">從 Office 通訊伺服器 2007 R2 進行遷移時，Office Communicator 2007 R2 適用于目前狀態和 IM 互通性，但是使用者應使用 Lync Web App 2013 加入 Lync Server 的 [2013] 會議。</span><span class="sxs-lookup"><span data-stu-id="c9731-173">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

<span data-ttu-id="c9731-174">5如需限制，請參閱本主題稍後的「Lync Server 2010 會議中2013的 ' 會議功能支援」。</span><span class="sxs-lookup"><span data-stu-id="c9731-174">5 For limitations, see "Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings" later in this topic.</span></span>

</div>

<div>

## <a name="interoperability-among-clients"></a><span data-ttu-id="c9731-175">用戶端間的互通性</span><span class="sxs-lookup"><span data-stu-id="c9731-175">Interoperability among Clients</span></span>

<span data-ttu-id="c9731-176">在 Lync Server 2013 版本中，各種用戶端版本可以在對等與會議案例中順利互動。</span><span class="sxs-lookup"><span data-stu-id="c9731-176">With the Lync Server 2013 release, various client versions can interact seamlessly in both peer-to-peer and conferencing scenarios.</span></span> <span data-ttu-id="c9731-177">本節討論使用者與其他使用不同版本用戶端和伺服器的使用者進行互動時的功能可用性。</span><span class="sxs-lookup"><span data-stu-id="c9731-177">This section discusses feature availability when users interact with other users who are using different versions of clients and servers.</span></span>

<div>

## <a name="peer-to-peer-feature-support"></a><span data-ttu-id="c9731-178">Peer-to-Peer 功能支援</span><span class="sxs-lookup"><span data-stu-id="c9731-178">Peer-to-Peer Feature Support</span></span>

<span data-ttu-id="c9731-179">對等功能可支援位於不同伺服器版本的使用者，以及使用不同用戶端版本的使用者。</span><span class="sxs-lookup"><span data-stu-id="c9731-179">Peer-to-peer features are supported for users who are homed on different versions of the server and who are using different client versions.</span></span> <span data-ttu-id="c9731-180">使用者經驗和可用的功能，與使用者的用戶端功能和使用者登入之伺服器的版本一致。</span><span class="sxs-lookup"><span data-stu-id="c9731-180">The end-user experience and available features are consistent with the capabilities of the user’s client and the version of the server the user is signed in to.</span></span> <span data-ttu-id="c9731-181">換句話說：</span><span class="sxs-lookup"><span data-stu-id="c9731-181">In other words:</span></span>

  - <span data-ttu-id="c9731-182">若使用者已使用舊版用戶端登入 Lync Server 2013，使用者就會使用自己的經驗。</span><span class="sxs-lookup"><span data-stu-id="c9731-182">If a user is signed in to Lync Server 2013 with an older client, the user will have the same experience he or she is used to.</span></span> <span data-ttu-id="c9731-183">在升級使用者的用戶端之前，不會提供 Lync Server 2013 中引入的任何新功能。</span><span class="sxs-lookup"><span data-stu-id="c9731-183">None of the new features introduced in Lync Server 2013 will be available until the user’s client is upgraded.</span></span> <span data-ttu-id="c9731-184">範例包括影片庫視圖、HD 影片、更新 PowerPoint 共用，以及在會議輸入時靜音所有出席者音訊和影片的選項。</span><span class="sxs-lookup"><span data-stu-id="c9731-184">Examples include video gallery view, HD video, updated PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="c9731-185">[Lync server 2013 中的新會議功能](lync-server-2013-new-conferencing-features.md)會列出新功能，以及[lync server 2013 中用戶端的新](lync-server-2013-what-s-new-for-clients.md)功能。</span><span class="sxs-lookup"><span data-stu-id="c9731-185">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

  - <span data-ttu-id="c9731-186">如果使用者登入 Lync Server 2010 與 Lync 2013 用戶端，則在使用者移至 Lync Server 2013 之前，Lync Server 2010 不支援的任何新功能將無法使用。</span><span class="sxs-lookup"><span data-stu-id="c9731-186">If a user is signed in to Lync Server 2010 with a Lync 2013 client, any new features not supported by Lync Server 2010 will be unavailable until the user is moved to Lync Server 2013.</span></span>

<span data-ttu-id="c9731-187">下表比較用戶端登入 Lync Server 2013 或 Lync Server 2010 的點對點工作階段中的功能可用性。</span><span class="sxs-lookup"><span data-stu-id="c9731-187">The following table compares feature availability in peer-to-peer sessions where the client is signed in to either Lync Server 2013 or Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c9731-188">Lync Web App 和 Lync 2010 出席者是僅供會議的用戶端，不會包含在此表格中。</span><span class="sxs-lookup"><span data-stu-id="c9731-188">Lync Web App and Lync 2010 Attendee are meeting-only clients and aren’t included in this table.</span></span>



</div>


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9731-189">用戶端</span><span class="sxs-lookup"><span data-stu-id="c9731-189">Client</span></span></th>
<th><span data-ttu-id="c9731-190">立即訊息</span><span class="sxs-lookup"><span data-stu-id="c9731-190">Instant Messaging</span></span></th>
<th><span data-ttu-id="c9731-191">目前狀態</span><span class="sxs-lookup"><span data-stu-id="c9731-191">Presence</span></span></th>
<th><span data-ttu-id="c9731-192">語音</span><span class="sxs-lookup"><span data-stu-id="c9731-192">Voice</span></span></th>
<th><span data-ttu-id="c9731-193">影片</span><span class="sxs-lookup"><span data-stu-id="c9731-193">Video</span></span></th>
<th><span data-ttu-id="c9731-194">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="c9731-194">Application Sharing</span></span></th>
<th><span data-ttu-id="c9731-195">檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="c9731-195">File Transfer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9731-196">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="c9731-196">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="c9731-197">是</span><span class="sxs-lookup"><span data-stu-id="c9731-197">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-198">是</span><span class="sxs-lookup"><span data-stu-id="c9731-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-199">是</span><span class="sxs-lookup"><span data-stu-id="c9731-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-200">是</span><span class="sxs-lookup"><span data-stu-id="c9731-200">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-201">是</span><span class="sxs-lookup"><span data-stu-id="c9731-201">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-202">是</span><span class="sxs-lookup"><span data-stu-id="c9731-202">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9731-203">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="c9731-203">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="c9731-204">是</span><span class="sxs-lookup"><span data-stu-id="c9731-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-205">是</span><span class="sxs-lookup"><span data-stu-id="c9731-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-206">是</span><span class="sxs-lookup"><span data-stu-id="c9731-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-207">是</span><span class="sxs-lookup"><span data-stu-id="c9731-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-208">是</span><span class="sxs-lookup"><span data-stu-id="c9731-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-209">是</span><span class="sxs-lookup"><span data-stu-id="c9731-209">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9731-210">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="c9731-210">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="c9731-211">是</span><span class="sxs-lookup"><span data-stu-id="c9731-211">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-212">是</span><span class="sxs-lookup"><span data-stu-id="c9731-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-213">是</span><span class="sxs-lookup"><span data-stu-id="c9731-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-214">是</span><span class="sxs-lookup"><span data-stu-id="c9731-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-215">是</span><span class="sxs-lookup"><span data-stu-id="c9731-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-216">是</span><span class="sxs-lookup"><span data-stu-id="c9731-216">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9731-217">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="c9731-217">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="c9731-218">是</span><span class="sxs-lookup"><span data-stu-id="c9731-218">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-219">是</span><span class="sxs-lookup"><span data-stu-id="c9731-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-220">是</span><span class="sxs-lookup"><span data-stu-id="c9731-220">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9731-221">Lync 2010 Mobile</span><span class="sxs-lookup"><span data-stu-id="c9731-221">Lync 2010 Mobile</span></span></p></td>
<td><p><span data-ttu-id="c9731-222">是</span><span class="sxs-lookup"><span data-stu-id="c9731-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-223">是</span><span class="sxs-lookup"><span data-stu-id="c9731-223">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9731-224">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="c9731-224">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="c9731-225">是</span><span class="sxs-lookup"><span data-stu-id="c9731-225">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-226">是</span><span class="sxs-lookup"><span data-stu-id="c9731-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-227">是</span><span class="sxs-lookup"><span data-stu-id="c9731-227">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9731-228">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="c9731-228">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="c9731-229">是</span><span class="sxs-lookup"><span data-stu-id="c9731-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-230">是</span><span class="sxs-lookup"><span data-stu-id="c9731-230">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-231">是</span><span class="sxs-lookup"><span data-stu-id="c9731-231">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-232">是</span><span class="sxs-lookup"><span data-stu-id="c9731-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-233">是1</span><span class="sxs-lookup"><span data-stu-id="c9731-233">Yes1</span></span></p></td>
<td><p><span data-ttu-id="c9731-234">是</span><span class="sxs-lookup"><span data-stu-id="c9731-234">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9731-235">公用 IM (AOL，Yahoo！ ) </span><span class="sxs-lookup"><span data-stu-id="c9731-235">Public IM (AOL, Yahoo!)</span></span></p></td>
<td><p><span data-ttu-id="c9731-236">是</span><span class="sxs-lookup"><span data-stu-id="c9731-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-237">是</span><span class="sxs-lookup"><span data-stu-id="c9731-237">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9731-238">公用 IM (MSN、Windows Live Messenger) </span><span class="sxs-lookup"><span data-stu-id="c9731-238">Public IM (MSN, Windows Live Messenger)</span></span></p></td>
<td><p><span data-ttu-id="c9731-239">是</span><span class="sxs-lookup"><span data-stu-id="c9731-239">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-240">是</span><span class="sxs-lookup"><span data-stu-id="c9731-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-241">是</span><span class="sxs-lookup"><span data-stu-id="c9731-241">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-242">是</span><span class="sxs-lookup"><span data-stu-id="c9731-242">Yes</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="c9731-243">從2012年9月1日起，Microsoft Lync Public IM 連線使用者訂閱授權 (PIC USL) 已不再提供購買新的或更新的協定。</span><span class="sxs-lookup"><span data-stu-id="c9731-243">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="c9731-244">具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="c9731-244">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="c9731-245">信使直到服務關閉日期。</span><span class="sxs-lookup"><span data-stu-id="c9731-245">Messenger until the service shutdown date.</span></span> <span data-ttu-id="c9731-246">AOL 和 Yahoo！的循環結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="c9731-246">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="c9731-247">已宣告。</span><span class="sxs-lookup"><span data-stu-id="c9731-247">has been announced.</span></span> <span data-ttu-id="c9731-248">如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</span><span class="sxs-lookup"><span data-stu-id="c9731-248">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>..</span></span></P>
> <LI>
> <P><span data-ttu-id="c9731-249">PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的每一使用者、每月訂閱授權。</span><span class="sxs-lookup"><span data-stu-id="c9731-249">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="c9731-250">信使。</span><span class="sxs-lookup"><span data-stu-id="c9731-250">Messenger.</span></span> <span data-ttu-id="c9731-251">Microsoft 提供此服務的能力已因 Yahoo！的支援而產生，不會更新的基準合約。</span><span class="sxs-lookup"><span data-stu-id="c9731-251">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="c9731-252">Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。</span><span class="sxs-lookup"><span data-stu-id="c9731-252">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="c9731-253">與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="c9731-253">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="c9731-254">隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以透過 IM 和語音來抵達數百個人的人員。</span><span class="sxs-lookup"><span data-stu-id="c9731-254">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="c9731-255">1在 Office Communicator 2007 R2 中，僅有桌面共用 (與程式共用) 皆可供使用。</span><span class="sxs-lookup"><span data-stu-id="c9731-255">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c9731-256">當商務用 Skype 2015 用戶端使用者介面強制執行時，Office Communicator 2007 R2 和商務用 Skype 2015 之間的桌面共用無法從較新的用戶端啟動。</span><span class="sxs-lookup"><span data-stu-id="c9731-256">Desktop sharing between Office Communicator 2007 R2 and Skype for Business 2015 cannot be initiated from the newer client when the Skype for Business 2015 client user interface is enforced.</span></span>



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a><span data-ttu-id="c9731-257">Lync Server 2010 會議中 Lync 2013 用戶端的會議功能支援</span><span class="sxs-lookup"><span data-stu-id="c9731-257">Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings</span></span>

<span data-ttu-id="c9731-258">當使用者使用 Lync 2013 用戶端加入 Lync Server 2010 會議時，他們可以存取 Lync 2013 用戶端功能，但有下列例外：</span><span class="sxs-lookup"><span data-stu-id="c9731-258">When users join Lync Server 2010 meetings with a Lync 2013 client, they have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="c9731-259">在 [**參與者**管理] 選項中，透過指向會議視窗中的 [人員] 圖示可供存取，[**無會議 IM** ] 選項不會正常運作。</span><span class="sxs-lookup"><span data-stu-id="c9731-259">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="c9731-260">圖庫 View 在影片會議中無法運作。</span><span class="sxs-lookup"><span data-stu-id="c9731-260">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="c9731-261">使用者只會看到使用中的音箱，而不是所有的揚聲器。</span><span class="sxs-lookup"><span data-stu-id="c9731-261">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="c9731-262">在 [**選擇版面**配置選項] 清單中，無法使用**圖庫 View**功能</span><span class="sxs-lookup"><span data-stu-id="c9731-262">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="c9731-263">在 [影片會議] 中，預設會顯示參與者清單。</span><span class="sxs-lookup"><span data-stu-id="c9731-263">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="c9731-264">以滑鼠右鍵按一下參與者清單中的使用者時，會無法使用 [影片] [影片] 和 [**固定至圖庫**]**的 [工作**表參與者管理] 選項。</span><span class="sxs-lookup"><span data-stu-id="c9731-264">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a><span data-ttu-id="c9731-265">Lync Server 2013 會議中的會議功能支援</span><span class="sxs-lookup"><span data-stu-id="c9731-265">Conferencing Feature Support in Lync Server 2013 Meetings</span></span>

<span data-ttu-id="c9731-266">Lync Server 2013 提供新的會議功能，當使用者的帳戶移至 Lync Server 2013 並以 Lync 2013 用戶端登入時，這些功能就可供使用者使用。</span><span class="sxs-lookup"><span data-stu-id="c9731-266">Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="c9731-267">範例包括影片庫視圖、HD 影片、PowerPoint 共用，以及在會議輸入時靜音所有出席者音訊和影片的選項。</span><span class="sxs-lookup"><span data-stu-id="c9731-267">Examples include video gallery view, HD video, PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="c9731-268">[Lync server 2013 中的新會議功能](lync-server-2013-new-conferencing-features.md)會列出新功能，以及[lync server 2013 中用戶端的新](lync-server-2013-what-s-new-for-clients.md)功能。</span><span class="sxs-lookup"><span data-stu-id="c9731-268">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="c9731-269">在 Lync Server 2013 會議中，特定的會議功能可供位於不同伺服器版本的使用者和使用不同用戶端和用戶端版本的使用者使用。</span><span class="sxs-lookup"><span data-stu-id="c9731-269">In Lync Server 2013 meetings, certain conferencing features are supported for users who are homed on different versions of the server and who are using different clients and client versions.</span></span> <span data-ttu-id="c9731-270">當用戶端加入 Lync Server 2013 會議時，使用者可以存取此表格中所示的功能和功能。</span><span class="sxs-lookup"><span data-stu-id="c9731-270">When clients join a Lync Server 2013 meeting, users have access to the features and capabilities shown in this table.</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9731-271">用戶端</span><span class="sxs-lookup"><span data-stu-id="c9731-271">Client</span></span></th>
<th><span data-ttu-id="c9731-272">對等 IM</span><span class="sxs-lookup"><span data-stu-id="c9731-272">Peer-to-peer IM</span></span></th>
<th><span data-ttu-id="c9731-273">語音</span><span class="sxs-lookup"><span data-stu-id="c9731-273">Voice</span></span></th>
<th><span data-ttu-id="c9731-274">影片</span><span class="sxs-lookup"><span data-stu-id="c9731-274">Video</span></span></th>
<th><span data-ttu-id="c9731-275">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="c9731-275">Application Sharing</span></span></th>
<th><span data-ttu-id="c9731-276">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="c9731-276">PowerPoint</span></span></th>
<th><span data-ttu-id="c9731-277">檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="c9731-277">File Transfer</span></span></th>
<th><span data-ttu-id="c9731-278">Whiteboard</span><span class="sxs-lookup"><span data-stu-id="c9731-278">Whiteboard</span></span></th>
<th><span data-ttu-id="c9731-279">輪詢</span><span class="sxs-lookup"><span data-stu-id="c9731-279">Polling</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9731-280">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="c9731-280">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="c9731-281">是</span><span class="sxs-lookup"><span data-stu-id="c9731-281">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-282">是</span><span class="sxs-lookup"><span data-stu-id="c9731-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-283">是</span><span class="sxs-lookup"><span data-stu-id="c9731-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-284">是</span><span class="sxs-lookup"><span data-stu-id="c9731-284">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-285">是</span><span class="sxs-lookup"><span data-stu-id="c9731-285">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-286">是</span><span class="sxs-lookup"><span data-stu-id="c9731-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-287">是</span><span class="sxs-lookup"><span data-stu-id="c9731-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-288">是</span><span class="sxs-lookup"><span data-stu-id="c9731-288">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9731-289">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="c9731-289">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="c9731-290">是</span><span class="sxs-lookup"><span data-stu-id="c9731-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-291">是</span><span class="sxs-lookup"><span data-stu-id="c9731-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-292">是</span><span class="sxs-lookup"><span data-stu-id="c9731-292">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-293">是</span><span class="sxs-lookup"><span data-stu-id="c9731-293">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-294">是</span><span class="sxs-lookup"><span data-stu-id="c9731-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-295">是</span><span class="sxs-lookup"><span data-stu-id="c9731-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-296">是</span><span class="sxs-lookup"><span data-stu-id="c9731-296">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-297">是</span><span class="sxs-lookup"><span data-stu-id="c9731-297">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9731-298">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="c9731-298">Lync Web App</span></span></p></td>
<td><p><span data-ttu-id="c9731-299">是</span><span class="sxs-lookup"><span data-stu-id="c9731-299">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-300">是</span><span class="sxs-lookup"><span data-stu-id="c9731-300">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-301">是</span><span class="sxs-lookup"><span data-stu-id="c9731-301">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-302">是</span><span class="sxs-lookup"><span data-stu-id="c9731-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-303">是2</span><span class="sxs-lookup"><span data-stu-id="c9731-303">Yes2</span></span></p></td>
<td><p><span data-ttu-id="c9731-304">是</span><span class="sxs-lookup"><span data-stu-id="c9731-304">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-305">是</span><span class="sxs-lookup"><span data-stu-id="c9731-305">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-306">是</span><span class="sxs-lookup"><span data-stu-id="c9731-306">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9731-307">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="c9731-307">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="c9731-308">是</span><span class="sxs-lookup"><span data-stu-id="c9731-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-309">是</span><span class="sxs-lookup"><span data-stu-id="c9731-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-310">是</span><span class="sxs-lookup"><span data-stu-id="c9731-310">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-311">是</span><span class="sxs-lookup"><span data-stu-id="c9731-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-312">是3</span><span class="sxs-lookup"><span data-stu-id="c9731-312">Yes3</span></span></p></td>
<td><p><span data-ttu-id="c9731-313">是</span><span class="sxs-lookup"><span data-stu-id="c9731-313">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-314">是</span><span class="sxs-lookup"><span data-stu-id="c9731-314">Yes</span></span></p></td>
<td><p><span data-ttu-id="c9731-315">是</span><span class="sxs-lookup"><span data-stu-id="c9731-315">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9731-316">Office Communicator 2007 R2 4</span><span class="sxs-lookup"><span data-stu-id="c9731-316">Office Communicator 2007 R2 4</span></span></p></td>
<td><p><span data-ttu-id="c9731-317">是</span><span class="sxs-lookup"><span data-stu-id="c9731-317">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c9731-318">1在 Office Communicator 2007 R2 中，僅有桌面共用 (與程式共用) 皆可供使用。</span><span class="sxs-lookup"><span data-stu-id="c9731-318">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<span data-ttu-id="c9731-319">2 Lync Server 2013 使用更新的機制來上傳 PowerPoint 檔案。</span><span class="sxs-lookup"><span data-stu-id="c9731-319">2 Lync Server 2013 uses an updated mechanism for uploading PowerPoint files.</span></span> <span data-ttu-id="c9731-320">加入最初排定在 Lync Server 2010 上之會議的 Lync Web App 使用者可以查看和流覽 PowerPoint 簡報，但無法上傳 PowerPoint 檔案。</span><span class="sxs-lookup"><span data-stu-id="c9731-320">Lync Web App users who join a meeting that was originally scheduled on Lync Server 2010 can view and navigate PowerPoint presentations, but cannot upload PowerPoint files.</span></span>

<span data-ttu-id="c9731-321">3如果會議已排定在 Lync Server 2013 上，且 PowerPoint 的投影片是由 Lync 2013 用戶端上傳，則 Lync 2010 使用者可以查看投影片的許可權。</span><span class="sxs-lookup"><span data-stu-id="c9731-321">3 If the meeting was scheduled on Lync Server 2013 and PowerPoint slides were uploaded by a Lync 2013 client, Lync 2010 users have view-only access to the slides.</span></span> <span data-ttu-id="c9731-322">相反地，如果 Lync 2010 使用者上傳 PowerPoint 投影片，Lync Server 2013 使用者將可以查看和投影片，如果已設定 Office Web Apps Server，就會存取新的功能，例如更高的解析度顯示、動畫、投影片切換效果及內嵌的影片。</span><span class="sxs-lookup"><span data-stu-id="c9731-322">Conversely, if the PowerPoint slides were uploaded by a Lync 2010 user, Lync Server 2013 users will be able to view and slides and, if Office Web Apps Server is configured, access new capabilities such as higher resolution display, animations, slide transitions, and embedded video.</span></span> <span data-ttu-id="c9731-323">如需詳細資訊，請參閱設定[Office Web Apps Server 和 Lync server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="c9731-323">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="c9731-324">Office Communicator 2007 R2 中的4The 目前狀態和 IM 功能與 Lync Server 2013 相容，但會議功能卻不相容。</span><span class="sxs-lookup"><span data-stu-id="c9731-324">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="c9731-325">從 Office 通訊伺服器 2007 R2 進行遷移時，Office Communicator 2007 R2 適用于目前狀態和 IM 互通性，但是使用者應使用 Lync Web App 2013 加入 Lync Server 的 [2013] 會議。</span><span class="sxs-lookup"><span data-stu-id="c9731-325">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a><span data-ttu-id="c9731-326">排程增益集支援</span><span class="sxs-lookup"><span data-stu-id="c9731-326">Scheduling Add-in Support</span></span>

<span data-ttu-id="c9731-327">不同排程增益集的伺服器支援與伺服器及用戶端版本相容性一致。</span><span class="sxs-lookup"><span data-stu-id="c9731-327">Server support for the various scheduling add-ins is consistent with server and client version compatibility.</span></span> <span data-ttu-id="c9731-328">一般來說，Lync Server 2013 上支援下列排程增益集。</span><span class="sxs-lookup"><span data-stu-id="c9731-328">In general, the following scheduling add-ins are supported on Lync Server 2013.</span></span> <span data-ttu-id="c9731-329">不過，舊版的增益集不會提供新的 Lync 2013 增益集功能，例如，將所有出席者的音訊和影片輸入到會議輸入時的選項。</span><span class="sxs-lookup"><span data-stu-id="c9731-329">However, previous versions of add-ins do not provide new Lync 2013 add-in features, such as the option to mute all attendee audio and video upon meeting entry.</span></span>

  - <span data-ttu-id="c9731-330">**Lync 2013**     的線上會議增益集提供與 Lync 2010 的線上會議增益集相同的功能，加入出席者的靜音控制項，讓會議召集人可以排定預設會靜音和影片的會議。</span><span class="sxs-lookup"><span data-stu-id="c9731-330">**Online Meeting Add-in for Lync 2013**   Provides the same features as the Online Meeting Add-in for Lync 2010, with the addition of attendee mute controls, which allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span> <span data-ttu-id="c9731-331">管理員也可以新增自訂標誌、支援 URL、法律免責聲明 URL 或自訂頁腳文字，以自訂群組織的會議邀請。</span><span class="sxs-lookup"><span data-stu-id="c9731-331">Administrators can also customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span>

  - <span data-ttu-id="c9731-332">**Lync 2010**     的線上會議增益集提供 Lync 會議的排程，並移除安排 Office Live Meeting 會議的功能。</span><span class="sxs-lookup"><span data-stu-id="c9731-332">**Online Meeting Add-in for Lync 2010**   Provides scheduling for Lync meetings and removes the capability to schedule Office Live Meeting conferences.</span></span>

  - <span data-ttu-id="c9731-333">**Office Communicator 2007 R2 會議增益集**    提供 Office Live Meeting 會議和 Office Communicator 2007 R2 會議的排程。</span><span class="sxs-lookup"><span data-stu-id="c9731-333">**Office Communicator 2007 R2 Conferencing Add-in**   Provides scheduling for both Office Live Meeting conferences and Office Communicator 2007 R2 conferences.</span></span> 

<div>


> [!NOTE]  
> <span data-ttu-id="c9731-334">無法在 Lync Server 2013 上排定 Live Meeting 會議。</span><span class="sxs-lookup"><span data-stu-id="c9731-334">Live Meeting conferences cannot be scheduled on Lync Server 2013.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9731-335">排程用戶端</span><span class="sxs-lookup"><span data-stu-id="c9731-335">Scheduling Client</span></span></th>
<th><span data-ttu-id="c9731-336">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9731-336">Lync Server 2013</span></span></th>
<th><span data-ttu-id="c9731-337">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="c9731-337">Lync Server 2010</span></span></th>
<th><span data-ttu-id="c9731-338">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="c9731-338">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9731-339">Lync 2013 (的線上會議增益集可以搭配 Office 2013、Outlook 2010 和 Outlook 2007) 使用</span><span class="sxs-lookup"><span data-stu-id="c9731-339">Online Meeting Add-in for Lync 2013 (can be used with Office 2013, Outlook 2010, and Outlook 2007)</span></span></p></td>
<td><p><span data-ttu-id="c9731-340">支援</span><span class="sxs-lookup"><span data-stu-id="c9731-340">Supported</span></span></p></td>
<td><p><span data-ttu-id="c9731-341">支援 (無法使用的新增益集功能) </span><span class="sxs-lookup"><span data-stu-id="c9731-341">Supported (new add-in features not available)</span></span></p></td>
<td><p><span data-ttu-id="c9731-342">不支援</span><span class="sxs-lookup"><span data-stu-id="c9731-342">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9731-343">Lync 2013 Web 排程器</span><span class="sxs-lookup"><span data-stu-id="c9731-343">Lync 2013 Web Scheduler</span></span></p></td>
<td><p><span data-ttu-id="c9731-344">支援</span><span class="sxs-lookup"><span data-stu-id="c9731-344">Supported</span></span></p></td>
<td><p><span data-ttu-id="c9731-345">不支援</span><span class="sxs-lookup"><span data-stu-id="c9731-345">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c9731-346">不支援</span><span class="sxs-lookup"><span data-stu-id="c9731-346">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9731-347">Lync 2010 線上會議增益集</span><span class="sxs-lookup"><span data-stu-id="c9731-347">Online Meeting Add-in for Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="c9731-348">支援</span><span class="sxs-lookup"><span data-stu-id="c9731-348">Supported</span></span></p></td>
<td><p><span data-ttu-id="c9731-349">支援</span><span class="sxs-lookup"><span data-stu-id="c9731-349">Supported</span></span></p></td>
<td><p><span data-ttu-id="c9731-350">不支援</span><span class="sxs-lookup"><span data-stu-id="c9731-350">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9731-351">Office Communicator 2007 R2 會議增益集</span><span class="sxs-lookup"><span data-stu-id="c9731-351">Office Communicator 2007 R2 Conferencing Add-in</span></span></p></td>
<td><p><span data-ttu-id="c9731-352">不支援</span><span class="sxs-lookup"><span data-stu-id="c9731-352">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="c9731-353">支援</span><span class="sxs-lookup"><span data-stu-id="c9731-353">Supported</span></span></p></td>
<td><p><span data-ttu-id="c9731-354">支援</span><span class="sxs-lookup"><span data-stu-id="c9731-354">Supported</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a><span data-ttu-id="c9731-355">加入會議的支援</span><span class="sxs-lookup"><span data-stu-id="c9731-355">Support for Joining Meetings</span></span>

<span data-ttu-id="c9731-356">所有 Lync Server 2013 支援的用戶端都可以加入 Lync 2013 會議。</span><span class="sxs-lookup"><span data-stu-id="c9731-356">All of the clients that Lync Server 2013 supports are allowed to join Lync 2013 meetings.</span></span> <span data-ttu-id="c9731-357">因為 Lync Web App 是伺服器的網頁元件，所以在使用 Lync Web App 來加入 Lync Server 2013 會議時，永遠會使用較新版本的 Lync Web App。</span><span class="sxs-lookup"><span data-stu-id="c9731-357">Because Lync Web App is a web component of the server, in cases where Lync Web App is used to join a Lync Server 2013 meeting, the newer version of Lync Web App is always used.</span></span>

<span data-ttu-id="c9731-358">Lync 2013 用戶端可以加入以向外擴充功能之 Lync 2010 和 Office 通訊伺服器 2007 R2 主控的會議。</span><span class="sxs-lookup"><span data-stu-id="c9731-358">Lync 2013 clients can join meetings hosted on Lync 2010 and Office Communications Server 2007 R2 with scaled-down functionality.</span></span> <span data-ttu-id="c9731-359">「會議中功能」是由主控會議所在的伺服器版本所限制。</span><span class="sxs-lookup"><span data-stu-id="c9731-359">In-meeting features are limited by the version of the server on which the meeting is hosted.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c9731-360">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c9731-360">See Also</span></span>


[<span data-ttu-id="c9731-361">Lync Server 2013 的 lync Windows 應用程式需求</span><span class="sxs-lookup"><span data-stu-id="c9731-361">Lync Windows Store app requirements for Lync Server 2013</span></span>](lync-server-2013-lync-windows-store-app-requirements.md)  
[<span data-ttu-id="c9731-362">Lync Server 2013 中的新會議功能</span><span class="sxs-lookup"><span data-stu-id="c9731-362">New conferencing features in Lync Server 2013</span></span>](lync-server-2013-new-conferencing-features.md)  
[<span data-ttu-id="c9731-363">Lync Server 2013 中用戶端的新功能</span><span class="sxs-lookup"><span data-stu-id="c9731-363">What's new for clients in Lync Server 2013</span></span>](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

