---
title: Lync Server 2013： CDR views 清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR views
ms:assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688009(v=OCS.15)
ms:contentKeyID: 49733598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37f41be7781f3cdce6b458b1eeaeb5cb8431b8d0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513960"
---
# <a name="list-of-cdr-views-in-lync-server-2013"></a><span data-ttu-id="59bb6-102">Lync Server 2013 中 CDR 視圖的清單</span><span class="sxs-lookup"><span data-stu-id="59bb6-102">List of CDR views in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59bb6-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="59bb6-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="59bb6-104">檢視讓您可以輕鬆取得從 CDR 資料庫傳回資料時最常見情況的資訊。</span><span class="sxs-lookup"><span data-stu-id="59bb6-104">Views provide an easy way to access information about the most common scenarios used for returning data from the CDR database.</span></span> <span data-ttu-id="59bb6-105">建議您使用 [視圖] 來建立自訂報表，而不是使用實際的 CDR 資料庫資料表;這是因為資料庫檢視更可能與未來的 Lync Server 版本保持向後相容性。</span><span class="sxs-lookup"><span data-stu-id="59bb6-105">It is recommended that you use views for building custom reports instead of using the actual CDR database tables ; that’s because the database views are more likely to maintain backwards compatibility with future releases of Lync Server.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59bb6-106">檢視名稱</span><span class="sxs-lookup"><span data-stu-id="59bb6-106">View Name</span></span></th>
<th><span data-ttu-id="59bb6-107">描述</span><span class="sxs-lookup"><span data-stu-id="59bb6-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59bb6-108"><a href="lync-server-2013-clientversions-view.md">Lync Server 2013 中的 ClientVersions 視圖</a></span><span class="sxs-lookup"><span data-stu-id="59bb6-108"><a href="lync-server-2013-clientversions-view.md">ClientVersions view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="59bb6-109">傳回通訊工作階段中使用的用戶端軟體/裝置資訊。</span><span class="sxs-lookup"><span data-stu-id="59bb6-109">Returns information about the client software/devices used in a communication session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59bb6-110"><a href="lync-server-2013-conferencemessagecount-view.md">Lync Server 2013 中的 ConferenceMessageCount 視圖</a></span><span class="sxs-lookup"><span data-stu-id="59bb6-110"><a href="lync-server-2013-conferencemessagecount-view.md">ConferenceMessageCount view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="59bb6-111">傳回會議中使用者傳送的訊息數量資訊。</span><span class="sxs-lookup"><span data-stu-id="59bb6-111">Returns information about the number of messages sent by users in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59bb6-112"><a href="lync-server-2013-conferences-view.md">Lync Server 2013 中的會議視圖</a></span><span class="sxs-lookup"><span data-stu-id="59bb6-112"><a href="lync-server-2013-conferences-view.md">Conferences view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="59bb6-113">傳回會議資訊，包含開始時間、結束時間以及唯一會議召集人。</span><span class="sxs-lookup"><span data-stu-id="59bb6-113">Returns conference information, including start time, end time, and conference organizer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59bb6-114"><a href="lync-server-2013-conferencesessiondetails-view.md">Lync Server 2013 中的 ConferenceSessionDetails 視圖</a></span><span class="sxs-lookup"><span data-stu-id="59bb6-114"><a href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="59bb6-115">傳回所有會議工作階段的工作階段詳細資料，包含開始及結束時間、使用者 ID、回應碼及診斷 ID。</span><span class="sxs-lookup"><span data-stu-id="59bb6-115">Returns session details for all conferencing sessions, including start and end time, user IDs, response codes, and diagnostic IDs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59bb6-116"><a href="lync-server-2013-conferenceuris-view.md">Lync Server 2013 中的 ConferenceUris 視圖</a></span><span class="sxs-lookup"><span data-stu-id="59bb6-116"><a href="lync-server-2013-conferenceuris-view.md">ConferenceUris view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="59bb6-117">傳回會議中使用的會議 URI 資訊</span><span class="sxs-lookup"><span data-stu-id="59bb6-117">Returns information about conference URIs used in a conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59bb6-118"><a href="lync-server-2013-errorreport-view.md">Lync Server 2013 中的 ErrorReport 視圖</a></span><span class="sxs-lookup"><span data-stu-id="59bb6-118"><a href="lync-server-2013-errorreport-view.md">ErrorReport view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="59bb6-119">傳回工作階段期間發生之錯誤的資訊。</span><span class="sxs-lookup"><span data-stu-id="59bb6-119">Returns information about errors that occurred during a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59bb6-120"><a href="lync-server-2013-filetransfers-view.md">Lync Server 2013 中的 FileTransfers 視圖</a></span><span class="sxs-lookup"><span data-stu-id="59bb6-120"><a href="lync-server-2013-filetransfers-view.md">FileTransfers view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="59bb6-121">傳回檔案傳輸工作階段的資訊，包含檔案名稱以及是否接受、拒絕或取消傳輸。</span><span class="sxs-lookup"><span data-stu-id="59bb6-121">Returns information about file transfer sessions, including the file name and whether the transfer was accepted, rejected, or cancelled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59bb6-122"><a href="lync-server-2013-focusjoinsandleaves-view.md">Lync Server 2013 中的 FocusJoinsAndLeaves 視圖</a></span><span class="sxs-lookup"><span data-stu-id="59bb6-122"><a href="lync-server-2013-focusjoinsandleaves-view.md">FocusJoinsAndLeaves view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="59bb6-123">傳回會議加入及會議離開活動的資訊</span><span class="sxs-lookup"><span data-stu-id="59bb6-123">Returns information about conference join and leave activities.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59bb6-124"><a href="lync-server-2013-mcujoinsandleaves-view.md">Lync Server 2013 中的 McuJoinsAndLeaves 視圖</a></span><span class="sxs-lookup"><span data-stu-id="59bb6-124"><a href="lync-server-2013-mcujoinsandleaves-view.md">McuJoinsAndLeaves view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="59bb6-125">傳回會議加入及會議離開活動的合併資訊 (每次會議加入均有對應的會議離開作為搭配)。</span><span class="sxs-lookup"><span data-stu-id="59bb6-125">Returns combined information about conference join and leave activities (each conference join is paired with the corresponding conference leave).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59bb6-126"><a href="lync-server-2013-mcus-view.md">Lync Server 2013 中的 Mcus 視圖</a></span><span class="sxs-lookup"><span data-stu-id="59bb6-126"><a href="lync-server-2013-mcus-view.md">Mcus view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="59bb6-127">傳回會議伺服器的資訊。</span><span class="sxs-lookup"><span data-stu-id="59bb6-127">Returns information about Conferencing servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59bb6-128"><a href="lync-server-2013-media-view.md">Lync Server 2013 中的媒體視圖</a></span><span class="sxs-lookup"><span data-stu-id="59bb6-128"><a href="lync-server-2013-media-view.md">Media view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="59bb6-129">傳回對等通訊工作階段中使用的媒體類型資訊。</span><span class="sxs-lookup"><span data-stu-id="59bb6-129">Returns information about the types of media used in peer-to-peer communication sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59bb6-130"><a href="lync-server-2013-progressreport-view.md">Lync Server 2013 中的 ProgressReport 視圖</a></span><span class="sxs-lookup"><span data-stu-id="59bb6-130"><a href="lync-server-2013-progressreport-view.md">ProgressReport view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="59bb6-131">傳回已完成之工作階段的資訊。</span><span class="sxs-lookup"><span data-stu-id="59bb6-131">Returns information about completed sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59bb6-132"><a href="lync-server-2013-registration-view.md">Lync Server 2013 中的註冊視圖</a></span><span class="sxs-lookup"><span data-stu-id="59bb6-132"><a href="lync-server-2013-registration-view.md">Registration view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="59bb6-133">傳回 Lync Server 註冊的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="59bb6-133">Returns information about registrations with Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59bb6-134"><a href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 中的 SessionDetails 視圖</a></span><span class="sxs-lookup"><span data-stu-id="59bb6-134"><a href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="59bb6-135">傳回對等工作階段的資訊，包含 VoIP 對 VoIP 電話、雙方 IM 工作階段，或其他對等通訊工作階段。</span><span class="sxs-lookup"><span data-stu-id="59bb6-135">Returns information about peer-to-peer sessions, including VoIP-VoIP phone calls, two-party IM sessions, or other peer-to-peer communication sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59bb6-136"><a href="lync-server-2013-user-view.md">Lync Server 2013 中的使用者視圖</a></span><span class="sxs-lookup"><span data-stu-id="59bb6-136"><a href="lync-server-2013-user-view.md">User view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="59bb6-137">傳回已加入通訊工作階段之使用者的資訊。</span><span class="sxs-lookup"><span data-stu-id="59bb6-137">Returns information about the users who have participated in communication sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59bb6-138"><a href="lync-server-2013-voipdetails-view.md">Lync Server 2013 中的 VoIPDetails 視圖</a></span><span class="sxs-lookup"><span data-stu-id="59bb6-138"><a href="lync-server-2013-voipdetails-view.md">VoIPDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="59bb6-139">傳回至少包含一位 VoIP 使用者之對等工作階段的資訊。</span><span class="sxs-lookup"><span data-stu-id="59bb6-139">Returns information for peer-to-peer sessions involving at least one VoIP (Voice over IO) user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

