---
title: Lync Server 2013：Lync 2013 中的用戶端互通性
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
ms.openlocfilehash: b28d0de09a46a2be8b968e55c8f551e397da6ae8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-interoperability-in-lync-2013"></a><span data-ttu-id="3ec67-102">Lync 2013 中的用戶端互通性</span><span class="sxs-lookup"><span data-stu-id="3ec67-102">Client interoperability in Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ec67-103">_**主題上次修改日期：** 2016-03-04_</span><span class="sxs-lookup"><span data-stu-id="3ec67-103">_**Topic Last Modified:** 2016-03-04_</span></span>

<span data-ttu-id="3ec67-104">本主題討論 Microsoft Lync Server 2013 用戶端與舊版 Lync Server 和 Office 通訊伺服器之間的共存與用戶端互動的能力。</span><span class="sxs-lookup"><span data-stu-id="3ec67-104">This topic discusses the ability of Microsoft Lync Server 2013 clients to coexist and interact with clients from earlier versions of Lync Server and Office Communications Server.</span></span>

<div>

## <a name="server-and-client-compatibility"></a><span data-ttu-id="3ec67-105">伺服器與用戶端相容性</span><span class="sxs-lookup"><span data-stu-id="3ec67-105">Server and Client Compatibility</span></span>

<span data-ttu-id="3ec67-106">下表顯示用戶端版本和伺服器版本支援的組合。</span><span class="sxs-lookup"><span data-stu-id="3ec67-106">The following table shows the supported combinations of client versions and server versions.</span></span> <span data-ttu-id="3ec67-107">此表格指示用戶端嘗試連線至所指示的伺服器時，是否支援登入。</span><span class="sxs-lookup"><span data-stu-id="3ec67-107">This table indicates whether sign-in is supported when the client attempts to connect to the server indicated.</span></span> <span data-ttu-id="3ec67-108">Lync Server 2013 支援舊版的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="3ec67-108">Lync Server 2013 supports the previous client version.</span></span> <span data-ttu-id="3ec67-109">此外，Lync Server 2010 支援新的 Lync 2013 用戶端，也與舊版版本不同。</span><span class="sxs-lookup"><span data-stu-id="3ec67-109">Also, unlike previous releases, Lync Server 2010 supports the new Lync 2013 clients.</span></span> <span data-ttu-id="3ec67-110">這可讓從 Lync Server 2010 升級的組織在獨立于 Lync Server 升級的情況下，推出新的用戶端。</span><span class="sxs-lookup"><span data-stu-id="3ec67-110">This allows organizations who are upgrading from Lync Server 2010 to roll out new clients independent of Lync Server upgrades.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3ec67-111">用戶端</span><span class="sxs-lookup"><span data-stu-id="3ec67-111">Client</span></span></th>
<th><span data-ttu-id="3ec67-112">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ec67-112">Lync Server 2013</span></span></th>
<th><span data-ttu-id="3ec67-113">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3ec67-113">Lync Server 2010</span></span></th>
<th><span data-ttu-id="3ec67-114">Office 通訊伺服器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3ec67-114">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ec67-115">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="3ec67-115">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="3ec67-116">受</span><span class="sxs-lookup"><span data-stu-id="3ec67-116">Supported</span></span></p></td>
<td><p><span data-ttu-id="3ec67-117">Supported5</span><span class="sxs-lookup"><span data-stu-id="3ec67-117">Supported5</span></span></p></td>
<td><p><span data-ttu-id="3ec67-118">不支援</span><span class="sxs-lookup"><span data-stu-id="3ec67-118">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec67-119">Lync 2013 基本版</span><span class="sxs-lookup"><span data-stu-id="3ec67-119">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="3ec67-120">受</span><span class="sxs-lookup"><span data-stu-id="3ec67-120">Supported</span></span></p></td>
<td><p><span data-ttu-id="3ec67-121">受</span><span class="sxs-lookup"><span data-stu-id="3ec67-121">Supported</span></span></p></td>
<td><p><span data-ttu-id="3ec67-122">不支援</span><span class="sxs-lookup"><span data-stu-id="3ec67-122">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec67-123">Lync Web App 2013</span><span class="sxs-lookup"><span data-stu-id="3ec67-123">Lync Web App 2013</span></span></p></td>
<td><p><span data-ttu-id="3ec67-124">受</span><span class="sxs-lookup"><span data-stu-id="3ec67-124">Supported</span></span></p></td>
<td><p><span data-ttu-id="3ec67-125">不支援</span><span class="sxs-lookup"><span data-stu-id="3ec67-125">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="3ec67-126">不支援</span><span class="sxs-lookup"><span data-stu-id="3ec67-126">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec67-127">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="3ec67-127">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="3ec67-128">受</span><span class="sxs-lookup"><span data-stu-id="3ec67-128">Supported</span></span></p></td>
<td><p><span data-ttu-id="3ec67-129">受</span><span class="sxs-lookup"><span data-stu-id="3ec67-129">Supported</span></span></p></td>
<td><p><span data-ttu-id="3ec67-130">不支援</span><span class="sxs-lookup"><span data-stu-id="3ec67-130">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec67-131">Lync 2010 助理</span><span class="sxs-lookup"><span data-stu-id="3ec67-131">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="3ec67-132">受</span><span class="sxs-lookup"><span data-stu-id="3ec67-132">Supported</span></span></p></td>
<td><p><span data-ttu-id="3ec67-133">受</span><span class="sxs-lookup"><span data-stu-id="3ec67-133">Supported</span></span></p></td>
<td><p><span data-ttu-id="3ec67-134">不支援</span><span class="sxs-lookup"><span data-stu-id="3ec67-134">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec67-135">Lync 2010 群組聊天</span><span class="sxs-lookup"><span data-stu-id="3ec67-135">Lync 2010 Group Chat</span></span></p></td>
<td><p><span data-ttu-id="3ec67-136">Supported1</span><span class="sxs-lookup"><span data-stu-id="3ec67-136">Supported1</span></span></p></td>
<td><p><span data-ttu-id="3ec67-137">Supported2</span><span class="sxs-lookup"><span data-stu-id="3ec67-137">Supported2</span></span></p></td>
<td><p><span data-ttu-id="3ec67-138">不適用</span><span class="sxs-lookup"><span data-stu-id="3ec67-138">Not Applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec67-139">Lync Web App 2010</span><span class="sxs-lookup"><span data-stu-id="3ec67-139">Lync Web App 2010</span></span></p></td>
<td><p><span data-ttu-id="3ec67-140">不支援</span><span class="sxs-lookup"><span data-stu-id="3ec67-140">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="3ec67-141">受</span><span class="sxs-lookup"><span data-stu-id="3ec67-141">Supported</span></span></p></td>
<td><p><span data-ttu-id="3ec67-142">不支援</span><span class="sxs-lookup"><span data-stu-id="3ec67-142">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec67-143">Lync 2010 出席者</span><span class="sxs-lookup"><span data-stu-id="3ec67-143">Lync 2010 Attendee</span></span></p></td>
<td><p><span data-ttu-id="3ec67-144">無法 Supported3</span><span class="sxs-lookup"><span data-stu-id="3ec67-144">Not Supported3</span></span></p></td>
<td><p><span data-ttu-id="3ec67-145">受</span><span class="sxs-lookup"><span data-stu-id="3ec67-145">Supported</span></span></p></td>
<td><p><span data-ttu-id="3ec67-146">不支援</span><span class="sxs-lookup"><span data-stu-id="3ec67-146">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec67-147">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3ec67-147">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="3ec67-148">Interoperable4</span><span class="sxs-lookup"><span data-stu-id="3ec67-148">Interoperable4</span></span></p></td>
<td><p><span data-ttu-id="3ec67-149">受</span><span class="sxs-lookup"><span data-stu-id="3ec67-149">Supported</span></span></p></td>
<td><p><span data-ttu-id="3ec67-150">受</span><span class="sxs-lookup"><span data-stu-id="3ec67-150">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec67-151">Microsoft Office 通訊伺服器 2007 R2 助理</span><span class="sxs-lookup"><span data-stu-id="3ec67-151">Microsoft Office Communications Server 2007 R2 Attendant</span></span></p></td>
<td><p><span data-ttu-id="3ec67-152">不支援</span><span class="sxs-lookup"><span data-stu-id="3ec67-152">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="3ec67-153">受</span><span class="sxs-lookup"><span data-stu-id="3ec67-153">Supported</span></span></p></td>
<td><p><span data-ttu-id="3ec67-154">受</span><span class="sxs-lookup"><span data-stu-id="3ec67-154">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec67-155">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="3ec67-155">Office Communicator 2007</span></span></p></td>
<td><p><span data-ttu-id="3ec67-156">不支援</span><span class="sxs-lookup"><span data-stu-id="3ec67-156">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="3ec67-157">受</span><span class="sxs-lookup"><span data-stu-id="3ec67-157">Supported</span></span></p></td>
<td><p><span data-ttu-id="3ec67-158">受</span><span class="sxs-lookup"><span data-stu-id="3ec67-158">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec67-159">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="3ec67-159">Office Live Meeting 2007</span></span></p></td>
<td><p><span data-ttu-id="3ec67-160">不支援</span><span class="sxs-lookup"><span data-stu-id="3ec67-160">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="3ec67-161">受</span><span class="sxs-lookup"><span data-stu-id="3ec67-161">Supported</span></span></p></td>
<td><p><span data-ttu-id="3ec67-162">受</span><span class="sxs-lookup"><span data-stu-id="3ec67-162">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec67-163">Lync Windows Store 應用程式</span><span class="sxs-lookup"><span data-stu-id="3ec67-163">Lync Windows Store app</span></span></p></td>
<td><p><span data-ttu-id="3ec67-164">受</span><span class="sxs-lookup"><span data-stu-id="3ec67-164">Supported</span></span></p></td>
<td><p><span data-ttu-id="3ec67-165">受</span><span class="sxs-lookup"><span data-stu-id="3ec67-165">Supported</span></span></p></td>
<td><p><span data-ttu-id="3ec67-166">不支援</span><span class="sxs-lookup"><span data-stu-id="3ec67-166">Not Supported</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3ec67-167">1For 詳細資料，請參閱[從 Lync server 2010 遷移、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天至 Lync server 2013、持續聊天伺服器](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="3ec67-167">1For details, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="3ec67-168">2In Microsoft Lync Server 2010，您可以在群組聊天伺服器（即 Lync Server 2010 的協力廠商信任應用程式）中使用群組聊天功能。</span><span class="sxs-lookup"><span data-stu-id="3ec67-168">2In Microsoft Lync Server 2010, group chat functionality was available with Group Chat Server, a third-party trusted application for Lync Server 2010.</span></span> <span data-ttu-id="3ec67-169">Lync 2013 用戶端與 Lync Server 2010 （群組聊天）不相容。</span><span class="sxs-lookup"><span data-stu-id="3ec67-169">Lync 2013 clients are not compatible with Lync Server 2010, Group Chat.</span></span>

<span data-ttu-id="3ec67-170">3Lync Web App 2013 現在提供完整的會議體驗，包括電腦音訊和影片，並被視為 Lync 2010 出席者的取代。</span><span class="sxs-lookup"><span data-stu-id="3ec67-170">3Lync Web App 2013 now provides a full in-meeting experience, including computer audio and video, and is considered the replacement for Lync 2010 Attendee.</span></span> <span data-ttu-id="3ec67-171">只有當您使用不受支援的瀏覽器（Internet Explorer 6 或 Internet Explorer 7）與 Windows XP 時，lync 2010 出席者才會連線至 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="3ec67-171">Lync 2010 Attendee will connect to Lync Server 2013 only when you are using an unsupported browser (Internet Explorer 6 or Internet Explorer 7) and Windows XP.</span></span>

<span data-ttu-id="3ec67-172">Office Communicator 2007 R2 中的4The 目前狀態與 IM 功能與 Lync Server 2013 相容，但會議功能不相容。</span><span class="sxs-lookup"><span data-stu-id="3ec67-172">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="3ec67-173">從 Office 通訊伺服器 2007 R2 遷移期間，Office Communicator 2007 R2 適用于目前狀態與 IM 互通性，但使用者應該使用 Lync Web App 2013 來加入 Lync Server 2013 會議。</span><span class="sxs-lookup"><span data-stu-id="3ec67-173">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

<span data-ttu-id="3ec67-174">5如需限制，請參閱本主題稍後的「Lync Server 2010 會議中的 Lync 2013 用戶端的會議功能支援」。</span><span class="sxs-lookup"><span data-stu-id="3ec67-174">5 For limitations, see "Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings" later in this topic.</span></span>

</div>

<div>

## <a name="interoperability-among-clients"></a><span data-ttu-id="3ec67-175">用戶端之間的互通性</span><span class="sxs-lookup"><span data-stu-id="3ec67-175">Interoperability among Clients</span></span>

<span data-ttu-id="3ec67-176">在 Lync Server 2013 版本中，各種用戶端版本都可以在對等與會議案例中順利互動。</span><span class="sxs-lookup"><span data-stu-id="3ec67-176">With the Lync Server 2013 release, various client versions can interact seamlessly in both peer-to-peer and conferencing scenarios.</span></span> <span data-ttu-id="3ec67-177">本節討論使用者與其他使用不同版本用戶端和伺服器的使用者互動時的功能可用性。</span><span class="sxs-lookup"><span data-stu-id="3ec67-177">This section discusses feature availability when users interact with other users who are using different versions of clients and servers.</span></span>

<div>

## <a name="peer-to-peer-feature-support"></a><span data-ttu-id="3ec67-178">對等功能支援</span><span class="sxs-lookup"><span data-stu-id="3ec67-178">Peer-to-Peer Feature Support</span></span>

<span data-ttu-id="3ec67-179">針對駐留在不同版本伺服器的使用者，以及使用不同用戶端版本的使用者，都支援對等功能。</span><span class="sxs-lookup"><span data-stu-id="3ec67-179">Peer-to-peer features are supported for users who are homed on different versions of the server and who are using different client versions.</span></span> <span data-ttu-id="3ec67-180">最終使用者體驗和可用功能與使用者用戶端的功能和使用者登入的伺服器版本相符。</span><span class="sxs-lookup"><span data-stu-id="3ec67-180">The end-user experience and available features are consistent with the capabilities of the user’s client and the version of the server the user is signed in to.</span></span> <span data-ttu-id="3ec67-181">換句話說：</span><span class="sxs-lookup"><span data-stu-id="3ec67-181">In other words:</span></span>

  - <span data-ttu-id="3ec67-182">如果使用者是使用舊版用戶端登入 Lync Server 2013，使用者就會使用自己的體驗。</span><span class="sxs-lookup"><span data-stu-id="3ec67-182">If a user is signed in to Lync Server 2013 with an older client, the user will have the same experience he or she is used to.</span></span> <span data-ttu-id="3ec67-183">只有在使用者的用戶端升級之後，才能使用 Lync Server 2013 中引入的任何新功能。</span><span class="sxs-lookup"><span data-stu-id="3ec67-183">None of the new features introduced in Lync Server 2013 will be available until the user’s client is upgraded.</span></span> <span data-ttu-id="3ec67-184">範例包括影片庫視圖、HD 影片、更新的 PowerPoint 共用，以及在會議進入時將所有出席者的音訊和影片設為靜音的選項。</span><span class="sxs-lookup"><span data-stu-id="3ec67-184">Examples include video gallery view, HD video, updated PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="3ec67-185">新功能在[Lync server 2013 的新會議功能](lync-server-2013-new-conferencing-features.md)中有說明，以及[lync server 2013 中用戶端的新](lync-server-2013-what-s-new-for-clients.md)功能。</span><span class="sxs-lookup"><span data-stu-id="3ec67-185">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

  - <span data-ttu-id="3ec67-186">如果使用者是使用 Lync 2013 用戶端登入 Lync Server 2010，則 Lync Server 2010 不支援的任何新功能都將無法使用，除非使用者移至 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="3ec67-186">If a user is signed in to Lync Server 2010 with a Lync 2013 client, any new features not supported by Lync Server 2010 will be unavailable until the user is moved to Lync Server 2013.</span></span>

<span data-ttu-id="3ec67-187">下表將用戶端登入 Lync Server 2013 或 Lync Server 2010 的點對點工作階段中的功能可用性進行比較。</span><span class="sxs-lookup"><span data-stu-id="3ec67-187">The following table compares feature availability in peer-to-peer sessions where the client is signed in to either Lync Server 2013 or Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3ec67-188">Lync Web App 和 Lync 2010 出席者是僅適用于會議的客戶，不會包含在此表格中。</span><span class="sxs-lookup"><span data-stu-id="3ec67-188">Lync Web App and Lync 2010 Attendee are meeting-only clients and aren’t included in this table.</span></span>



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
<th><span data-ttu-id="3ec67-189">用戶端</span><span class="sxs-lookup"><span data-stu-id="3ec67-189">Client</span></span></th>
<th><span data-ttu-id="3ec67-190">立即訊息</span><span class="sxs-lookup"><span data-stu-id="3ec67-190">Instant Messaging</span></span></th>
<th><span data-ttu-id="3ec67-191">目前狀態</span><span class="sxs-lookup"><span data-stu-id="3ec67-191">Presence</span></span></th>
<th><span data-ttu-id="3ec67-192">語音</span><span class="sxs-lookup"><span data-stu-id="3ec67-192">Voice</span></span></th>
<th><span data-ttu-id="3ec67-193">顯示器</span><span class="sxs-lookup"><span data-stu-id="3ec67-193">Video</span></span></th>
<th><span data-ttu-id="3ec67-194">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="3ec67-194">Application Sharing</span></span></th>
<th><span data-ttu-id="3ec67-195">檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="3ec67-195">File Transfer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ec67-196">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="3ec67-196">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="3ec67-197">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-197">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-198">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-199">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-200">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-200">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-201">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-201">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-202">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-202">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec67-203">Lync 2013 基本版</span><span class="sxs-lookup"><span data-stu-id="3ec67-203">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="3ec67-204">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-205">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-206">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-207">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-208">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-209">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-209">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec67-210">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="3ec67-210">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="3ec67-211">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-211">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-212">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-213">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-214">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-215">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-216">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-216">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec67-217">Lync 2010 助理</span><span class="sxs-lookup"><span data-stu-id="3ec67-217">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="3ec67-218">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-218">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-219">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-220">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-220">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec67-221">Lync 2010 行動裝置</span><span class="sxs-lookup"><span data-stu-id="3ec67-221">Lync 2010 Mobile</span></span></p></td>
<td><p><span data-ttu-id="3ec67-222">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-223">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-223">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec67-224">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="3ec67-224">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="3ec67-225">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-225">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-226">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-227">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-227">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec67-228">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3ec67-228">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="3ec67-229">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-230">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-230">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-231">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-231">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-232">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-233">是1</span><span class="sxs-lookup"><span data-stu-id="3ec67-233">Yes1</span></span></p></td>
<td><p><span data-ttu-id="3ec67-234">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-234">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec67-235">公用 IM （AOL、Yahoo！）</span><span class="sxs-lookup"><span data-stu-id="3ec67-235">Public IM (AOL, Yahoo!)</span></span></p></td>
<td><p><span data-ttu-id="3ec67-236">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-237">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-237">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec67-238">公用 IM （MSN、Windows Live Messenger）</span><span class="sxs-lookup"><span data-stu-id="3ec67-238">Public IM (MSN, Windows Live Messenger)</span></span></p></td>
<td><p><span data-ttu-id="3ec67-239">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-239">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-240">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-241">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-241">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-242">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-242">Yes</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="3ec67-243">從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（PIC USL）已不再提供購買新或續約協定的功能。</span><span class="sxs-lookup"><span data-stu-id="3ec67-243">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="3ec67-244">擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="3ec67-244">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="3ec67-245">信使，直到服務關閉日期為止。</span><span class="sxs-lookup"><span data-stu-id="3ec67-245">Messenger until the service shutdown date.</span></span> <span data-ttu-id="3ec67-246">AOL 和 Yahoo！的存留期結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="3ec67-246">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="3ec67-247">已公佈。</span><span class="sxs-lookup"><span data-stu-id="3ec67-247">has been announced.</span></span> <span data-ttu-id="3ec67-248">如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</span><span class="sxs-lookup"><span data-stu-id="3ec67-248">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>..</span></span></P>
> <LI>
> <P><span data-ttu-id="3ec67-249">PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟所需的每個使用者、每月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="3ec67-249">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="3ec67-250">名單.</span><span class="sxs-lookup"><span data-stu-id="3ec67-250">Messenger.</span></span> <span data-ttu-id="3ec67-251">Microsoft 提供此服務的能力已因 Yahoo！的支援而定，不會更新的底層合約。</span><span class="sxs-lookup"><span data-stu-id="3ec67-251">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="3ec67-252">Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。</span><span class="sxs-lookup"><span data-stu-id="3ec67-252">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="3ec67-253">與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="3ec67-253">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="3ec67-254">Skype 同盟將會新增到此清單，讓 Lync 使用者能夠透過 IM 和語音來取得成百上千的人員。</span><span class="sxs-lookup"><span data-stu-id="3ec67-254">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="3ec67-255">1在 Office Communicator 2007 R2 中，只能使用 [桌面共用] （而非 [程式共用]）。</span><span class="sxs-lookup"><span data-stu-id="3ec67-255">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3ec67-256">在強制執行商務用 Skype 2015 用戶端使用者介面時，無法從較新的用戶端啟動 Office Communicator 2007 R2 與商務用 Skype 2015 之間的桌面共用。</span><span class="sxs-lookup"><span data-stu-id="3ec67-256">Desktop sharing between Office Communicator 2007 R2 and Skype for Business 2015 cannot be initiated from the newer client when the Skype for Business 2015 client user interface is enforced.</span></span>



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a><span data-ttu-id="3ec67-257">Lync Server 2010 會議中 Lync 2013 用戶端的會議功能支援</span><span class="sxs-lookup"><span data-stu-id="3ec67-257">Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings</span></span>

<span data-ttu-id="3ec67-258">當使用者使用 Lync 2013 用戶端加入 Lync Server 2010 會議時，他們可以使用下列例外狀況來存取 Lync 2013 用戶端功能：</span><span class="sxs-lookup"><span data-stu-id="3ec67-258">When users join Lync Server 2010 meetings with a Lync 2013 client, they have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="3ec67-259">在**參與者**管理選項（可透過指向會議視窗中的 [人員] 圖示來存取），[**無會議 IM** ] 選項不起作用。</span><span class="sxs-lookup"><span data-stu-id="3ec67-259">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="3ec67-260">[圖庫] 視圖在視訊會議中不起作用。</span><span class="sxs-lookup"><span data-stu-id="3ec67-260">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="3ec67-261">使用者只會看到現用喇叭，而不是所有喇叭。</span><span class="sxs-lookup"><span data-stu-id="3ec67-261">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="3ec67-262">在 [**挑選版面**配置選項] 清單中，[**庫視圖**] 無法使用</span><span class="sxs-lookup"><span data-stu-id="3ec67-262">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="3ec67-263">「參與者清單」預設會顯示在 [視訊會議] 中。</span><span class="sxs-lookup"><span data-stu-id="3ec67-263">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="3ec67-264">在參與者清單中以滑鼠右鍵按一下使用者時，無法使用 [**鎖定影片焦點**] 和 [**釘選到圖庫**] 參與者管理選項。</span><span class="sxs-lookup"><span data-stu-id="3ec67-264">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a><span data-ttu-id="3ec67-265">Lync Server 2013 會議中的會議功能支援</span><span class="sxs-lookup"><span data-stu-id="3ec67-265">Conferencing Feature Support in Lync Server 2013 Meetings</span></span>

<span data-ttu-id="3ec67-266">Lync Server 2013 提供新的會議功能，在使用者的帳戶移至 Lync Server 2013 並以 Lync 2013 用戶端登入之後，使用者就能使用。</span><span class="sxs-lookup"><span data-stu-id="3ec67-266">Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="3ec67-267">範例包括影片庫視圖、HD 影片、PowerPoint 共用，以及在會議進入時將所有出席者的音訊和影片設為靜音的選項。</span><span class="sxs-lookup"><span data-stu-id="3ec67-267">Examples include video gallery view, HD video, PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="3ec67-268">新功能在[Lync server 2013 的新會議功能](lync-server-2013-new-conferencing-features.md)中有說明，以及[lync server 2013 中用戶端的新](lync-server-2013-what-s-new-for-clients.md)功能。</span><span class="sxs-lookup"><span data-stu-id="3ec67-268">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="3ec67-269">在 Lync Server 2013 會議中，對於駐留在不同版本伺服器的使用者，以及使用不同用戶端和用戶端版本的使用者，都支援某些會議功能。</span><span class="sxs-lookup"><span data-stu-id="3ec67-269">In Lync Server 2013 meetings, certain conferencing features are supported for users who are homed on different versions of the server and who are using different clients and client versions.</span></span> <span data-ttu-id="3ec67-270">當用戶端加入 Lync Server 2013 會議時，使用者可以使用下表所示的功能和功能。</span><span class="sxs-lookup"><span data-stu-id="3ec67-270">When clients join a Lync Server 2013 meeting, users have access to the features and capabilities shown in this table.</span></span>


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
<th><span data-ttu-id="3ec67-271">用戶端</span><span class="sxs-lookup"><span data-stu-id="3ec67-271">Client</span></span></th>
<th><span data-ttu-id="3ec67-272">對等 IM</span><span class="sxs-lookup"><span data-stu-id="3ec67-272">Peer-to-peer IM</span></span></th>
<th><span data-ttu-id="3ec67-273">語音</span><span class="sxs-lookup"><span data-stu-id="3ec67-273">Voice</span></span></th>
<th><span data-ttu-id="3ec67-274">顯示器</span><span class="sxs-lookup"><span data-stu-id="3ec67-274">Video</span></span></th>
<th><span data-ttu-id="3ec67-275">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="3ec67-275">Application Sharing</span></span></th>
<th><span data-ttu-id="3ec67-276">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="3ec67-276">PowerPoint</span></span></th>
<th><span data-ttu-id="3ec67-277">檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="3ec67-277">File Transfer</span></span></th>
<th><span data-ttu-id="3ec67-278">Whiteboard</span><span class="sxs-lookup"><span data-stu-id="3ec67-278">Whiteboard</span></span></th>
<th><span data-ttu-id="3ec67-279">投票</span><span class="sxs-lookup"><span data-stu-id="3ec67-279">Polling</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ec67-280">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="3ec67-280">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="3ec67-281">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-281">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-282">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-283">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-284">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-284">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-285">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-285">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-286">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-287">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-288">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-288">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec67-289">Lync 2013 基本版</span><span class="sxs-lookup"><span data-stu-id="3ec67-289">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="3ec67-290">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-291">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-292">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-292">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-293">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-293">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-294">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-295">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-296">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-296">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-297">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-297">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec67-298">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="3ec67-298">Lync Web App</span></span></p></td>
<td><p><span data-ttu-id="3ec67-299">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-299">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-300">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-300">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-301">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-301">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-302">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-303">是2</span><span class="sxs-lookup"><span data-stu-id="3ec67-303">Yes2</span></span></p></td>
<td><p><span data-ttu-id="3ec67-304">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-304">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-305">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-305">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-306">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-306">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec67-307">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="3ec67-307">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="3ec67-308">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-309">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-310">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-310">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-311">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-312">Yes3</span><span class="sxs-lookup"><span data-stu-id="3ec67-312">Yes3</span></span></p></td>
<td><p><span data-ttu-id="3ec67-313">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-313">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-314">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-314">Yes</span></span></p></td>
<td><p><span data-ttu-id="3ec67-315">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-315">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec67-316">Office Communicator 2007 R2 4</span><span class="sxs-lookup"><span data-stu-id="3ec67-316">Office Communicator 2007 R2 4</span></span></p></td>
<td><p><span data-ttu-id="3ec67-317">是</span><span class="sxs-lookup"><span data-stu-id="3ec67-317">Yes</span></span></p></td>
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


<span data-ttu-id="3ec67-318">1在 Office Communicator 2007 R2 中，只能使用 [桌面共用] （而非 [程式共用]）。</span><span class="sxs-lookup"><span data-stu-id="3ec67-318">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<span data-ttu-id="3ec67-319">2 Lync Server 2013 使用更新的機制來上傳 PowerPoint 檔案。</span><span class="sxs-lookup"><span data-stu-id="3ec67-319">2 Lync Server 2013 uses an updated mechanism for uploading PowerPoint files.</span></span> <span data-ttu-id="3ec67-320">加入原先在 Lync Server 2010 上排程之會議的 Lync Web App 使用者可以查看並流覽 PowerPoint 簡報，但無法上傳 PowerPoint 檔案。</span><span class="sxs-lookup"><span data-stu-id="3ec67-320">Lync Web App users who join a meeting that was originally scheduled on Lync Server 2010 can view and navigate PowerPoint presentations, but cannot upload PowerPoint files.</span></span>

<span data-ttu-id="3ec67-321">3如果會議是在 Lync Server 2013 上排程，且由 Lync 2013 用戶端上傳 PowerPoint 投影片，Lync 2010 使用者只能透過查看方式存取投影片。</span><span class="sxs-lookup"><span data-stu-id="3ec67-321">3 If the meeting was scheduled on Lync Server 2013 and PowerPoint slides were uploaded by a Lync 2013 client, Lync 2010 users have view-only access to the slides.</span></span> <span data-ttu-id="3ec67-322">相反地，如果您是由 Lync 2010 使用者上傳 PowerPoint 投影片，Lync Server 2013 使用者將能夠查看和投影片，而且如果已設定 Office Web Apps 伺服器，也能存取新功能，例如解析度顯示、動畫、投影片切換效果，以及內嵌的影片。</span><span class="sxs-lookup"><span data-stu-id="3ec67-322">Conversely, if the PowerPoint slides were uploaded by a Lync 2010 user, Lync Server 2013 users will be able to view and slides and, if Office Web Apps Server is configured, access new capabilities such as higher resolution display, animations, slide transitions, and embedded video.</span></span> <span data-ttu-id="3ec67-323">如需詳細資訊，請參閱設定[與 Office Web Apps server 和 Lync server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="3ec67-323">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="3ec67-324">Office Communicator 2007 R2 中的4The 目前狀態與 IM 功能與 Lync Server 2013 相容，但會議功能不相容。</span><span class="sxs-lookup"><span data-stu-id="3ec67-324">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="3ec67-325">從 Office 通訊伺服器 2007 R2 遷移期間，Office Communicator 2007 R2 適用于目前狀態與 IM 互通性，但使用者應該使用 Lync Web App 2013 來加入 Lync Server 2013 會議。</span><span class="sxs-lookup"><span data-stu-id="3ec67-325">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a><span data-ttu-id="3ec67-326">排程增益集支援</span><span class="sxs-lookup"><span data-stu-id="3ec67-326">Scheduling Add-in Support</span></span>

<span data-ttu-id="3ec67-327">針對各種排程增益集的伺服器支援，與伺服器和用戶端版本相容性一致。</span><span class="sxs-lookup"><span data-stu-id="3ec67-327">Server support for the various scheduling add-ins is consistent with server and client version compatibility.</span></span> <span data-ttu-id="3ec67-328">一般來說，Lync Server 2013 支援下列排程增益集。</span><span class="sxs-lookup"><span data-stu-id="3ec67-328">In general, the following scheduling add-ins are supported on Lync Server 2013.</span></span> <span data-ttu-id="3ec67-329">不過，先前的增益集版本不會提供新的 Lync 2013 增益集功能，例如，將所有出席者的音訊和會議專案設為靜音時的選項。</span><span class="sxs-lookup"><span data-stu-id="3ec67-329">However, previous versions of add-ins do not provide new Lync 2013 add-in features, such as the option to mute all attendee audio and video upon meeting entry.</span></span>

  - <span data-ttu-id="3ec67-330">**Lync 2013**   的線上會議增益集提供與 lync 2010 的線上會議增益集相同的功能，以及新增出席者靜音控制項，讓會議召集人預設會將出席者音訊和影片設為靜音的會議。</span><span class="sxs-lookup"><span data-stu-id="3ec67-330">**Online Meeting Add-in for Lync 2013**   Provides the same features as the Online Meeting Add-in for Lync 2010, with the addition of attendee mute controls, which allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span> <span data-ttu-id="3ec67-331">系統管理員也可以新增自訂標誌、支援 URL、合法免責聲明 URL 或自訂的頁尾文字，來自訂群組織的會議邀請。</span><span class="sxs-lookup"><span data-stu-id="3ec67-331">Administrators can also customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span>

  - <span data-ttu-id="3ec67-332">**Lync 2010**   的線上會議增益集可為 lync 會議提供排程，並移除安排 Office Live Meeting 會議的功能。</span><span class="sxs-lookup"><span data-stu-id="3ec67-332">**Online Meeting Add-in for Lync 2010**   Provides scheduling for Lync meetings and removes the capability to schedule Office Live Meeting conferences.</span></span>

  - <span data-ttu-id="3ec67-333">**Office Communicator 2007 R2 會議增益集**   可為 office Live Meeting 會議與 office Communicator 2007 R2 會議提供排程。</span><span class="sxs-lookup"><span data-stu-id="3ec67-333">**Office Communicator 2007 R2 Conferencing Add-in**   Provides scheduling for both Office Live Meeting conferences and Office Communicator 2007 R2 conferences.</span></span> 

<div>


> [!NOTE]  
> <span data-ttu-id="3ec67-334">在 Lync Server 2013 上無法排程 Live Meeting 會議。</span><span class="sxs-lookup"><span data-stu-id="3ec67-334">Live Meeting conferences cannot be scheduled on Lync Server 2013.</span></span>



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
<th><span data-ttu-id="3ec67-335">排程用戶端</span><span class="sxs-lookup"><span data-stu-id="3ec67-335">Scheduling Client</span></span></th>
<th><span data-ttu-id="3ec67-336">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ec67-336">Lync Server 2013</span></span></th>
<th><span data-ttu-id="3ec67-337">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3ec67-337">Lync Server 2010</span></span></th>
<th><span data-ttu-id="3ec67-338">Office 通訊伺服器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3ec67-338">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ec67-339">Lync 2013 的線上會議增益集（可與 Office 2013、Outlook 2010 和 Outlook 2007 搭配使用）</span><span class="sxs-lookup"><span data-stu-id="3ec67-339">Online Meeting Add-in for Lync 2013 (can be used with Office 2013, Outlook 2010, and Outlook 2007)</span></span></p></td>
<td><p><span data-ttu-id="3ec67-340">受</span><span class="sxs-lookup"><span data-stu-id="3ec67-340">Supported</span></span></p></td>
<td><p><span data-ttu-id="3ec67-341">支援（沒有可用的新增益集功能）</span><span class="sxs-lookup"><span data-stu-id="3ec67-341">Supported (new add-in features not available)</span></span></p></td>
<td><p><span data-ttu-id="3ec67-342">不支援</span><span class="sxs-lookup"><span data-stu-id="3ec67-342">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec67-343">Lync 2013 Web 排程程式</span><span class="sxs-lookup"><span data-stu-id="3ec67-343">Lync 2013 Web Scheduler</span></span></p></td>
<td><p><span data-ttu-id="3ec67-344">受</span><span class="sxs-lookup"><span data-stu-id="3ec67-344">Supported</span></span></p></td>
<td><p><span data-ttu-id="3ec67-345">不支援</span><span class="sxs-lookup"><span data-stu-id="3ec67-345">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="3ec67-346">不支援</span><span class="sxs-lookup"><span data-stu-id="3ec67-346">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ec67-347">Lync 2010 的線上會議增益集</span><span class="sxs-lookup"><span data-stu-id="3ec67-347">Online Meeting Add-in for Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="3ec67-348">受</span><span class="sxs-lookup"><span data-stu-id="3ec67-348">Supported</span></span></p></td>
<td><p><span data-ttu-id="3ec67-349">受</span><span class="sxs-lookup"><span data-stu-id="3ec67-349">Supported</span></span></p></td>
<td><p><span data-ttu-id="3ec67-350">不支援</span><span class="sxs-lookup"><span data-stu-id="3ec67-350">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ec67-351">Office Communicator 2007 R2 會議增益集</span><span class="sxs-lookup"><span data-stu-id="3ec67-351">Office Communicator 2007 R2 Conferencing Add-in</span></span></p></td>
<td><p><span data-ttu-id="3ec67-352">不支援</span><span class="sxs-lookup"><span data-stu-id="3ec67-352">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="3ec67-353">受</span><span class="sxs-lookup"><span data-stu-id="3ec67-353">Supported</span></span></p></td>
<td><p><span data-ttu-id="3ec67-354">受</span><span class="sxs-lookup"><span data-stu-id="3ec67-354">Supported</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a><span data-ttu-id="3ec67-355">加入會議的支援</span><span class="sxs-lookup"><span data-stu-id="3ec67-355">Support for Joining Meetings</span></span>

<span data-ttu-id="3ec67-356">Lync Server 2013 支援的所有用戶端都可以加入 Lync 2013 會議。</span><span class="sxs-lookup"><span data-stu-id="3ec67-356">All of the clients that Lync Server 2013 supports are allowed to join Lync 2013 meetings.</span></span> <span data-ttu-id="3ec67-357">因為 Lync Web App 是伺服器的網頁元件，所以在使用 Lync Web App 來加入 Lync Server 2013 會議的情況下，會一直使用較新版本的 Lync Web App。</span><span class="sxs-lookup"><span data-stu-id="3ec67-357">Because Lync Web App is a web component of the server, in cases where Lync Web App is used to join a Lync Server 2013 meeting, the newer version of Lync Web App is always used.</span></span>

<span data-ttu-id="3ec67-358">Lync 2013 用戶端可以加入在 Lync 2010 和 Office 通訊伺服器 2007 R2 中託管的會議，並提供上下伸縮功能。</span><span class="sxs-lookup"><span data-stu-id="3ec67-358">Lync 2013 clients can join meetings hosted on Lync 2010 and Office Communications Server 2007 R2 with scaled-down functionality.</span></span> <span data-ttu-id="3ec67-359">[會議中的功能] 是由託管會議的伺服器版本所限制。</span><span class="sxs-lookup"><span data-stu-id="3ec67-359">In-meeting features are limited by the version of the server on which the meeting is hosted.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3ec67-360">請參閱</span><span class="sxs-lookup"><span data-stu-id="3ec67-360">See Also</span></span>


[<span data-ttu-id="3ec67-361">Lync Server 2013 的 lync Windows Store 應用程式需求</span><span class="sxs-lookup"><span data-stu-id="3ec67-361">Lync Windows Store app requirements for Lync Server 2013</span></span>](lync-server-2013-lync-windows-store-app-requirements.md)  
[<span data-ttu-id="3ec67-362">Lync Server 2013 中的新會議功能</span><span class="sxs-lookup"><span data-stu-id="3ec67-362">New conferencing features in Lync Server 2013</span></span>](lync-server-2013-new-conferencing-features.md)  
[<span data-ttu-id="3ec67-363">Lync Server 2013 中的用戶端最新訊息</span><span class="sxs-lookup"><span data-stu-id="3ec67-363">What's new for clients in Lync Server 2013</span></span>](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

