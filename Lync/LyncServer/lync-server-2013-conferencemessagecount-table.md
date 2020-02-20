---
title: 'Lync Server 2013: ConferenceMessageCount 表格'
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
ms.openlocfilehash: e862209d384cd3927b6f8136b1a0d04b378e00c2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145131"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-table-in-lync-server-2013"></a><span data-ttu-id="296b0-102">Lync Server 2013 中的 ConferenceMessageCount 表格</span><span class="sxs-lookup"><span data-stu-id="296b0-102">ConferenceMessageCount table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="296b0-103">_**主題上次修改日期：** 2012年-09-28_</span><span class="sxs-lookup"><span data-stu-id="296b0-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="296b0-104">此表格中的每一筆記錄代表一個 IM 會議中的一位使用者，並包含該使用者所傳送的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="296b0-104">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="296b0-105">此表格中; 中的多筆記錄代表每個會議每位使用者的一筆記錄。</span><span class="sxs-lookup"><span data-stu-id="296b0-105">Each conference is represented by multiple records in this table; one record for each user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="296b0-106">欄</span><span class="sxs-lookup"><span data-stu-id="296b0-106">Column</span></span></th>
<th><span data-ttu-id="296b0-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="296b0-107">Data Type</span></span></th>
<th><span data-ttu-id="296b0-108">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="296b0-108">Key/Index</span></span></th>
<th><span data-ttu-id="296b0-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="296b0-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="296b0-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="296b0-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="296b0-111">datetime</span><span class="sxs-lookup"><span data-stu-id="296b0-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="296b0-112">主要、外部</span><span class="sxs-lookup"><span data-stu-id="296b0-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="296b0-113">會議執行個體的時間。</span><span class="sxs-lookup"><span data-stu-id="296b0-113">Time of conference instance.</span></span> <span data-ttu-id="296b0-114"><strong>SessionIdSeq</strong>搭配使用來唯一地識別會議執行個體。</span><span class="sxs-lookup"><span data-stu-id="296b0-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="296b0-115">請參閱<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中的會議表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="296b0-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="296b0-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="296b0-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="296b0-117">int</span><span class="sxs-lookup"><span data-stu-id="296b0-117">int</span></span></p></td>
<td><p><span data-ttu-id="296b0-118">主要、外部</span><span class="sxs-lookup"><span data-stu-id="296b0-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="296b0-119">用於辨識執行個體的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="296b0-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="296b0-120">搭配<strong>SessionIdTime</strong>用來唯一地識別會議執行個體。</span><span class="sxs-lookup"><span data-stu-id="296b0-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="296b0-121">請參閱<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中的會議表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="296b0-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="296b0-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="296b0-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="296b0-123">int</span><span class="sxs-lookup"><span data-stu-id="296b0-123">int</span></span></p></td>
<td><p><span data-ttu-id="296b0-124">Foreign</span><span class="sxs-lookup"><span data-stu-id="296b0-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="296b0-125">用於識別此使用者，參考來源：<a href="lync-server-2013-users-table.md">使用者在 Lync Server 2013 中資料表</a>的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="296b0-125">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="296b0-126"><strong>MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="296b0-126"><strong>MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="296b0-127">smallint</span><span class="sxs-lookup"><span data-stu-id="296b0-127">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="296b0-128">此使用者在會議期間傳送的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="296b0-128">The number of messages sent by this user during this conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

