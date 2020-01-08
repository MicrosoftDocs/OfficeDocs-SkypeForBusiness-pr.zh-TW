---
title: Lync Server 2013： CDR 視圖清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of CDR views
ms:assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688009(v=OCS.15)
ms:contentKeyID: 49733598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 112e565c07c685c1ecdf5db1d8a2de8717ba959e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-views-in-lync-server-2013"></a><span data-ttu-id="dfeac-102">Lync Server 2013 中的 CDR 視圖清單</span><span class="sxs-lookup"><span data-stu-id="dfeac-102">List of CDR views in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfeac-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="dfeac-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="dfeac-104">[視圖] 提供一種簡單的方式，可存取從 CDR 資料庫傳回資料最常見的案例資訊。</span><span class="sxs-lookup"><span data-stu-id="dfeac-104">Views provide an easy way to access information about the most common scenarios used for returning data from the CDR database.</span></span> <span data-ttu-id="dfeac-105">建議您使用 [視圖] 來建立自訂報表，而不是使用實際的 CDR 資料庫資料表;這是因為資料庫檢視很可能會與未來的 Lync Server 版本保持向後相容性。</span><span class="sxs-lookup"><span data-stu-id="dfeac-105">It is recommended that you use views for building custom reports instead of using the actual CDR database tables ; that’s because the database views are more likely to maintain backwards compatibility with future releases of Lync Server.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dfeac-106">[視圖名稱]</span><span class="sxs-lookup"><span data-stu-id="dfeac-106">View Name</span></span></th>
<th><span data-ttu-id="dfeac-107">描述</span><span class="sxs-lookup"><span data-stu-id="dfeac-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dfeac-108"><a href="lync-server-2013-clientversions-view.md">Lync Server 2013 中的 [ClientVersions] 視圖</a></span><span class="sxs-lookup"><span data-stu-id="dfeac-108"><a href="lync-server-2013-clientversions-view.md">ClientVersions view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="dfeac-109">傳回通訊會話中使用之用戶端軟體/裝置的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="dfeac-109">Returns information about the client software/devices used in a communication session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfeac-110"><a href="lync-server-2013-conferencemessagecount-view.md">Lync Server 2013 中的 [ConferenceMessageCount] 視圖</a></span><span class="sxs-lookup"><span data-stu-id="dfeac-110"><a href="lync-server-2013-conferencemessagecount-view.md">ConferenceMessageCount view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="dfeac-111">傳回會議中使用者傳送的訊息數的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="dfeac-111">Returns information about the number of messages sent by users in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfeac-112"><a href="lync-server-2013-conferences-view.md">Lync Server 2013 中的會議視圖</a></span><span class="sxs-lookup"><span data-stu-id="dfeac-112"><a href="lync-server-2013-conferences-view.md">Conferences view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="dfeac-113">傳回會議資訊，包括 [開始時間]、[結束時間] 和 [會議召集人]。</span><span class="sxs-lookup"><span data-stu-id="dfeac-113">Returns conference information, including start time, end time, and conference organizer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfeac-114"><a href="lync-server-2013-conferencesessiondetails-view.md">Lync Server 2013 中的 [ConferenceSessionDetails] 視圖</a></span><span class="sxs-lookup"><span data-stu-id="dfeac-114"><a href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="dfeac-115">傳回所有會議會話的會話詳細資料，包括開始和結束時間、使用者識別碼、回應代碼，以及診斷 Id。</span><span class="sxs-lookup"><span data-stu-id="dfeac-115">Returns session details for all conferencing sessions, including start and end time, user IDs, response codes, and diagnostic IDs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfeac-116"><a href="lync-server-2013-conferenceuris-view.md">Lync Server 2013 中的 [ConferenceUris] 視圖</a></span><span class="sxs-lookup"><span data-stu-id="dfeac-116"><a href="lync-server-2013-conferenceuris-view.md">ConferenceUris view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="dfeac-117">傳回會議中使用之會議 Uri 的相關資訊</span><span class="sxs-lookup"><span data-stu-id="dfeac-117">Returns information about conference URIs used in a conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfeac-118"><a href="lync-server-2013-errorreport-view.md">Lync Server 2013 中的 [ErrorReport] 視圖</a></span><span class="sxs-lookup"><span data-stu-id="dfeac-118"><a href="lync-server-2013-errorreport-view.md">ErrorReport view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="dfeac-119">傳回在會話期間發生之錯誤的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="dfeac-119">Returns information about errors that occurred during a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfeac-120"><a href="lync-server-2013-filetransfers-view.md">Lync Server 2013 中的 [FileTransfers] 視圖</a></span><span class="sxs-lookup"><span data-stu-id="dfeac-120"><a href="lync-server-2013-filetransfers-view.md">FileTransfers view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="dfeac-121">傳回檔案傳輸會話的相關資訊，包括檔案名，以及傳輸被接受、拒絕或取消。</span><span class="sxs-lookup"><span data-stu-id="dfeac-121">Returns information about file transfer sessions, including the file name and whether the transfer was accepted, rejected, or cancelled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfeac-122"><a href="lync-server-2013-focusjoinsandleaves-view.md">Lync Server 2013 中的 [FocusJoinsAndLeaves] 視圖</a></span><span class="sxs-lookup"><span data-stu-id="dfeac-122"><a href="lync-server-2013-focusjoinsandleaves-view.md">FocusJoinsAndLeaves view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="dfeac-123">傳回會議加入與離開活動的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="dfeac-123">Returns information about conference join and leave activities.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfeac-124"><a href="lync-server-2013-mcujoinsandleaves-view.md">Lync Server 2013 中的 [McuJoinsAndLeaves] 視圖</a></span><span class="sxs-lookup"><span data-stu-id="dfeac-124"><a href="lync-server-2013-mcujoinsandleaves-view.md">McuJoinsAndLeaves view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="dfeac-125">傳回會議加入與離開活動的綜合資訊（每個會議加入都與對應的會議休假成對出現）。</span><span class="sxs-lookup"><span data-stu-id="dfeac-125">Returns combined information about conference join and leave activities (each conference join is paired with the corresponding conference leave).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfeac-126"><a href="lync-server-2013-mcus-view.md">Lync Server 2013 中的 [Mcus] 視圖</a></span><span class="sxs-lookup"><span data-stu-id="dfeac-126"><a href="lync-server-2013-mcus-view.md">Mcus view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="dfeac-127">傳回會議服務器的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="dfeac-127">Returns information about Conferencing servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfeac-128"><a href="lync-server-2013-media-view.md">Lync Server 2013 中的媒體視圖</a></span><span class="sxs-lookup"><span data-stu-id="dfeac-128"><a href="lync-server-2013-media-view.md">Media view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="dfeac-129">傳回對等通訊會話中所使用之媒體類型的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="dfeac-129">Returns information about the types of media used in peer-to-peer communication sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfeac-130"><a href="lync-server-2013-progressreport-view.md">Lync Server 2013 中的 [ProgressReport] 視圖</a></span><span class="sxs-lookup"><span data-stu-id="dfeac-130"><a href="lync-server-2013-progressreport-view.md">ProgressReport view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="dfeac-131">傳回已完成會話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="dfeac-131">Returns information about completed sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfeac-132"><a href="lync-server-2013-registration-view.md">Lync Server 2013 中的 [註冊] 視圖</a></span><span class="sxs-lookup"><span data-stu-id="dfeac-132"><a href="lync-server-2013-registration-view.md">Registration view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="dfeac-133">傳回有關 Lync Server 註冊的資訊。</span><span class="sxs-lookup"><span data-stu-id="dfeac-133">Returns information about registrations with Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfeac-134"><a href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 中的 [SessionDetails] 視圖</a></span><span class="sxs-lookup"><span data-stu-id="dfeac-134"><a href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="dfeac-135">傳回點對點工作階段的相關資訊，包括 VoIP VoIP 電話、兩方 IM 會話，或其他對等通訊會話。</span><span class="sxs-lookup"><span data-stu-id="dfeac-135">Returns information about peer-to-peer sessions, including VoIP-VoIP phone calls, two-party IM sessions, or other peer-to-peer communication sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfeac-136"><a href="lync-server-2013-user-view.md">Lync Server 2013 中的使用者視圖</a></span><span class="sxs-lookup"><span data-stu-id="dfeac-136"><a href="lync-server-2013-user-view.md">User view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="dfeac-137">傳回參與通訊會話之使用者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="dfeac-137">Returns information about the users who have participated in communication sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfeac-138"><a href="lync-server-2013-voipdetails-view.md">Lync Server 2013 中的 [VoIPDetails] 視圖</a></span><span class="sxs-lookup"><span data-stu-id="dfeac-138"><a href="lync-server-2013-voipdetails-view.md">VoIPDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="dfeac-139">傳回至少包含一個 VoIP （在 IO 上）使用者的點對點工作階段的資訊。</span><span class="sxs-lookup"><span data-stu-id="dfeac-139">Returns information for peer-to-peer sessions involving at least one VoIP (Voice over IO) user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

