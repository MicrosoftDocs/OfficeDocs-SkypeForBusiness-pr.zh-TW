---
title: Lync Server 2013： ConferenceMessageCount 表格
description: Lync Server 2013： ConferenceMessageCount 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceMessageCount table
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398590(v=OCS.15)
ms:contentKeyID: 48184570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 271b654c09ab1aef194eb613e660de208aea1534
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561619"
---
# <a name="conferencemessagecount-table-in-lync-server-2013"></a><span data-ttu-id="e354b-103">Lync Server 2013 中的 ConferenceMessageCount 表格</span><span class="sxs-lookup"><span data-stu-id="e354b-103">ConferenceMessageCount table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e354b-104">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e354b-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e354b-105">此資料表中的每一筆記錄都代表一個 IM 會議中的一個使用者，並包含該使用者所傳送的訊息數目。</span><span class="sxs-lookup"><span data-stu-id="e354b-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="e354b-106">每個會議都會以此表格中的多筆記錄表示。每一位使用者一筆記錄。</span><span class="sxs-lookup"><span data-stu-id="e354b-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e354b-107">欄</span><span class="sxs-lookup"><span data-stu-id="e354b-107">Column</span></span></th>
<th><span data-ttu-id="e354b-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="e354b-108">Data Type</span></span></th>
<th><span data-ttu-id="e354b-109">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="e354b-109">Key/Index</span></span></th>
<th><span data-ttu-id="e354b-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="e354b-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e354b-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e354b-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e354b-112">datetime</span><span class="sxs-lookup"><span data-stu-id="e354b-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="e354b-113">主要，外部</span><span class="sxs-lookup"><span data-stu-id="e354b-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e354b-114">會議執行個體的時間。</span><span class="sxs-lookup"><span data-stu-id="e354b-114">Time of conference instance.</span></span> <span data-ttu-id="e354b-115">與 <strong>SessionIdSeq</strong> 搭配使用，以唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="e354b-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="e354b-116">如需詳細資訊，請參閱 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="e354b-116">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e354b-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e354b-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e354b-118">int</span><span class="sxs-lookup"><span data-stu-id="e354b-118">int</span></span></p></td>
<td><p><span data-ttu-id="e354b-119">主要、外部</span><span class="sxs-lookup"><span data-stu-id="e354b-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e354b-120">用於辨識執行個體的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="e354b-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="e354b-121">與 <strong>SessionIdTime</strong> 搭配使用，以唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="e354b-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="e354b-122">如需詳細資訊，請參閱 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="e354b-122">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e354b-123"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="e354b-123"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="e354b-124">int</span><span class="sxs-lookup"><span data-stu-id="e354b-124">int</span></span></p></td>
<td><p><span data-ttu-id="e354b-125">Foreign</span><span class="sxs-lookup"><span data-stu-id="e354b-125">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e354b-126">用於識別此使用者的唯一號碼， <a href="lync-server-2013-users-table.md">在 Lync Server 2013 的 [使用者] 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="e354b-126">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e354b-127"><strong>MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="e354b-127"><strong>MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="e354b-128">Smallint</span><span class="sxs-lookup"><span data-stu-id="e354b-128">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e354b-129">此會議期間此使用者所傳送的訊息數。</span><span class="sxs-lookup"><span data-stu-id="e354b-129">The number of messages sent by this user during this conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

