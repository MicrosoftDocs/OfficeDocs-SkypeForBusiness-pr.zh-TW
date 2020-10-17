---
title: Lync Server 2013： ConferenceMessageCount 表格
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
ms.openlocfilehash: ae806fc50fb0d4c4936fb6fbf6f879f4d4fc2ce4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529330"
---
# <a name="conferencemessagecount-table-in-lync-server-2013"></a><span data-ttu-id="8ddd4-102">Lync Server 2013 中的 ConferenceMessageCount 表格</span><span class="sxs-lookup"><span data-stu-id="8ddd4-102">ConferenceMessageCount table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ddd4-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="8ddd4-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="8ddd4-104">此資料表中的每一筆記錄都代表一個 IM 會議中的一個使用者，並包含該使用者所傳送的訊息數目。</span><span class="sxs-lookup"><span data-stu-id="8ddd4-104">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="8ddd4-105">每個會議都會以此表格中的多筆記錄表示。每一位使用者一筆記錄。</span><span class="sxs-lookup"><span data-stu-id="8ddd4-105">Each conference is represented by multiple records in this table; one record for each user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ddd4-106">欄</span><span class="sxs-lookup"><span data-stu-id="8ddd4-106">Column</span></span></th>
<th><span data-ttu-id="8ddd4-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="8ddd4-107">Data Type</span></span></th>
<th><span data-ttu-id="8ddd4-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="8ddd4-108">Key/Index</span></span></th>
<th><span data-ttu-id="8ddd4-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="8ddd4-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ddd4-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="8ddd4-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8ddd4-111">datetime</span><span class="sxs-lookup"><span data-stu-id="8ddd4-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="8ddd4-112">主要，外部</span><span class="sxs-lookup"><span data-stu-id="8ddd4-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8ddd4-113">會議執行個體的時間。</span><span class="sxs-lookup"><span data-stu-id="8ddd4-113">Time of conference instance.</span></span> <span data-ttu-id="8ddd4-114">與 <strong>SessionIdSeq</strong> 搭配使用，以唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="8ddd4-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="8ddd4-115">如需詳細資訊，請參閱 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="8ddd4-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ddd4-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="8ddd4-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="8ddd4-117">int</span><span class="sxs-lookup"><span data-stu-id="8ddd4-117">int</span></span></p></td>
<td><p><span data-ttu-id="8ddd4-118">主要、外部</span><span class="sxs-lookup"><span data-stu-id="8ddd4-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8ddd4-119">用於辨識執行個體的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="8ddd4-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="8ddd4-120">與 <strong>SessionIdTime</strong> 搭配使用，以唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="8ddd4-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="8ddd4-121">如需詳細資訊，請參閱 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="8ddd4-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ddd4-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="8ddd4-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="8ddd4-123">int</span><span class="sxs-lookup"><span data-stu-id="8ddd4-123">int</span></span></p></td>
<td><p><span data-ttu-id="8ddd4-124">Foreign</span><span class="sxs-lookup"><span data-stu-id="8ddd4-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8ddd4-125">用於識別此使用者的唯一號碼， <a href="lync-server-2013-users-table.md">在 Lync Server 2013 的 [使用者] 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="8ddd4-125">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ddd4-126"><strong>MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="8ddd4-126"><strong>MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="8ddd4-127">Smallint</span><span class="sxs-lookup"><span data-stu-id="8ddd4-127">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ddd4-128">此會議期間此使用者所傳送的訊息數。</span><span class="sxs-lookup"><span data-stu-id="8ddd4-128">The number of messages sent by this user during this conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

