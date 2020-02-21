---
title: 'Lync Server 2013: UserStatistics 資料表'
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
ms.openlocfilehash: 876d861e62014738816c02e2a6c2628f5dd46fc0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212873"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="45ea2-102">Lync Server 2013 中的 UserStatistics 資料表</span><span class="sxs-lookup"><span data-stu-id="45ea2-102">UserStatistics table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45ea2-103">_**主題上次修改日期：** 2012年-09-28_</span><span class="sxs-lookup"><span data-stu-id="45ea2-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="45ea2-104">UserStatistics 資料表是一種支援資料表。</span><span class="sxs-lookup"><span data-stu-id="45ea2-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="45ea2-105">在資料表中的每一筆記錄會儲存系統，個別使用者的使用狀況的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="45ea2-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="45ea2-106">Microsoft Lync Server 2013 中已採用此表格。</span><span class="sxs-lookup"><span data-stu-id="45ea2-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45ea2-107">欄</span><span class="sxs-lookup"><span data-stu-id="45ea2-107">Column</span></span></th>
<th><span data-ttu-id="45ea2-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="45ea2-108">Data Type</span></span></th>
<th><span data-ttu-id="45ea2-109">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="45ea2-109">Key/Index</span></span></th>
<th><span data-ttu-id="45ea2-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="45ea2-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45ea2-111"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="45ea2-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="45ea2-112">int</span><span class="sxs-lookup"><span data-stu-id="45ea2-112">int</span></span></p></td>
<td><p><span data-ttu-id="45ea2-113">主要</span><span class="sxs-lookup"><span data-stu-id="45ea2-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="45ea2-114">用於識別此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="45ea2-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ea2-115"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="45ea2-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="45ea2-116">datetime</span><span class="sxs-lookup"><span data-stu-id="45ea2-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="45ea2-117">上次使用者登入。</span><span class="sxs-lookup"><span data-stu-id="45ea2-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ea2-118"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="45ea2-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="45ea2-119">datetime</span><span class="sxs-lookup"><span data-stu-id="45ea2-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="45ea2-120">上次使用者召集的會議。</span><span class="sxs-lookup"><span data-stu-id="45ea2-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ea2-121"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="45ea2-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="45ea2-122">datetime</span><span class="sxs-lookup"><span data-stu-id="45ea2-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="45ea2-123">上次使用者上次發生通話失敗。</span><span class="sxs-lookup"><span data-stu-id="45ea2-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ea2-124"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="45ea2-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="45ea2-125">datetime</span><span class="sxs-lookup"><span data-stu-id="45ea2-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="45ea2-126">上次使用者遇到通話失敗會議召集人的身分。</span><span class="sxs-lookup"><span data-stu-id="45ea2-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

