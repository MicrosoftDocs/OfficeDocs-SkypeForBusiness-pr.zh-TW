---
title: Lync Server 2013：ConferenceMessageCount 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceMessageCount table
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398590(v=OCS.15)
ms:contentKeyID: 48184570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d2994f02bf087ef55edff6b2153e7504f881b03
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-table-in-lync-server-2013"></a><span data-ttu-id="ca719-102">Lync Server 2013 中的 ConferenceMessageCount 表格</span><span class="sxs-lookup"><span data-stu-id="ca719-102">ConferenceMessageCount table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca719-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ca719-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ca719-104">此資料表中的每筆記錄代表一個 IM 會議中的一位使用者，包括該使用者所傳送的訊息數目。</span><span class="sxs-lookup"><span data-stu-id="ca719-104">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="ca719-105">每個會議都是由這個表格中的多筆記錄所代表;每個使用者一個記錄。</span><span class="sxs-lookup"><span data-stu-id="ca719-105">Each conference is represented by multiple records in this table; one record for each user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca719-106">左欄</span><span class="sxs-lookup"><span data-stu-id="ca719-106">Column</span></span></th>
<th><span data-ttu-id="ca719-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="ca719-107">Data Type</span></span></th>
<th><span data-ttu-id="ca719-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="ca719-108">Key/Index</span></span></th>
<th><span data-ttu-id="ca719-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="ca719-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca719-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ca719-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ca719-111">datetime</span><span class="sxs-lookup"><span data-stu-id="ca719-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="ca719-112">主要、外部</span><span class="sxs-lookup"><span data-stu-id="ca719-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ca719-113">會議實例的時間。</span><span class="sxs-lookup"><span data-stu-id="ca719-113">Time of conference instance.</span></span> <span data-ttu-id="ca719-114">與<strong>SessionIdSeq</strong>搭配使用，可唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="ca719-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="ca719-115">如需詳細資訊，請參閱<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a>的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="ca719-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca719-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ca719-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ca719-117">int</span><span class="sxs-lookup"><span data-stu-id="ca719-117">int</span></span></p></td>
<td><p><span data-ttu-id="ca719-118">主要、外部</span><span class="sxs-lookup"><span data-stu-id="ca719-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ca719-119">識別會議實例的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="ca719-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="ca719-120">與<strong>SessionIdTime</strong>搭配使用，可唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="ca719-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="ca719-121">如需詳細資訊，請參閱<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a>的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="ca719-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca719-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="ca719-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="ca719-123">int</span><span class="sxs-lookup"><span data-stu-id="ca719-123">int</span></span></p></td>
<td><p><span data-ttu-id="ca719-124">外</span><span class="sxs-lookup"><span data-stu-id="ca719-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ca719-125">標識此使用者的唯一編號，從<a href="lync-server-2013-users-table.md">Lync Server 2013 的 [使用者] 資料表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="ca719-125">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca719-126"><strong>MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="ca719-126"><strong>MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="ca719-127">Smallint</span><span class="sxs-lookup"><span data-stu-id="ca719-127">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ca719-128">此使用者在此會議期間傳送的訊息數目。</span><span class="sxs-lookup"><span data-stu-id="ca719-128">The number of messages sent by this user during this conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

