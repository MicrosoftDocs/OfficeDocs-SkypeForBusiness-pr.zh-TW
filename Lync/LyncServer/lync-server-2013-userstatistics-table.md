---
title: Lync Server 2013： UserStatistics 表格
description: Lync Server 2013： UserStatistics 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserStatistics table
ms:assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721893(v=OCS.15)
ms:contentKeyID: 49733827
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75b34fa3c34af4cc9cf2cacc6ae7feb4d217114c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548529"
---
# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="6e435-103">Lync Server 2013 中的 UserStatistics 表格</span><span class="sxs-lookup"><span data-stu-id="6e435-103">UserStatistics table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e435-104">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="6e435-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="6e435-105">UserStatistics 表格是支援的表格。</span><span class="sxs-lookup"><span data-stu-id="6e435-105">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="6e435-106">資料表中的每一筆記錄都儲存了個別使用者對系統使用方式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="6e435-106">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="6e435-107">此表格已引進 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="6e435-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6e435-108">欄</span><span class="sxs-lookup"><span data-stu-id="6e435-108">Column</span></span></th>
<th><span data-ttu-id="6e435-109">資料類型</span><span class="sxs-lookup"><span data-stu-id="6e435-109">Data Type</span></span></th>
<th><span data-ttu-id="6e435-110">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="6e435-110">Key/Index</span></span></th>
<th><span data-ttu-id="6e435-111">詳細資料</span><span class="sxs-lookup"><span data-stu-id="6e435-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e435-112"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="6e435-112"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="6e435-113">int</span><span class="sxs-lookup"><span data-stu-id="6e435-113">int</span></span></p></td>
<td><p><span data-ttu-id="6e435-114">主要</span><span class="sxs-lookup"><span data-stu-id="6e435-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="6e435-115">用於識別此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="6e435-115">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e435-116"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="6e435-116"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6e435-117">datetime</span><span class="sxs-lookup"><span data-stu-id="6e435-117">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6e435-118">使用者上次登入的時間。</span><span class="sxs-lookup"><span data-stu-id="6e435-118">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e435-119"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="6e435-119"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6e435-120">datetime</span><span class="sxs-lookup"><span data-stu-id="6e435-120">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6e435-121">使用者上次組織會議的時間。</span><span class="sxs-lookup"><span data-stu-id="6e435-121">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e435-122"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="6e435-122"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6e435-123">datetime</span><span class="sxs-lookup"><span data-stu-id="6e435-123">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6e435-124">上次使用者發生通話失敗的時間。</span><span class="sxs-lookup"><span data-stu-id="6e435-124">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e435-125"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="6e435-125"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6e435-126">datetime</span><span class="sxs-lookup"><span data-stu-id="6e435-126">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6e435-127">使用者最後一次遇到會議召集人的呼叫失敗。</span><span class="sxs-lookup"><span data-stu-id="6e435-127">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

