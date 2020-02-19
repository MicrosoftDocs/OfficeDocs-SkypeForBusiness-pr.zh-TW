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
ms.openlocfilehash: 2758b52b44a58095203deb7e70387934f723ee97
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140686"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="a0d3f-102">Lync Server 2013 中的 UserStatistics 資料表</span><span class="sxs-lookup"><span data-stu-id="a0d3f-102">UserStatistics table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0d3f-103">_**主題上次修改日期：** 2012年-09-28_</span><span class="sxs-lookup"><span data-stu-id="a0d3f-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a0d3f-104">UserStatistics 資料表是一種支援資料表。</span><span class="sxs-lookup"><span data-stu-id="a0d3f-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="a0d3f-105">在資料表中的每一筆記錄會儲存系統，個別使用者的使用狀況的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a0d3f-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="a0d3f-106">Microsoft Lync Server 2013 中已採用此表格。</span><span class="sxs-lookup"><span data-stu-id="a0d3f-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0d3f-107">欄</span><span class="sxs-lookup"><span data-stu-id="a0d3f-107">Column</span></span></th>
<th><span data-ttu-id="a0d3f-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="a0d3f-108">Data Type</span></span></th>
<th><span data-ttu-id="a0d3f-109">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="a0d3f-109">Key/Index</span></span></th>
<th><span data-ttu-id="a0d3f-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="a0d3f-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0d3f-111"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="a0d3f-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="a0d3f-112">int</span><span class="sxs-lookup"><span data-stu-id="a0d3f-112">int</span></span></p></td>
<td><p><span data-ttu-id="a0d3f-113">主要</span><span class="sxs-lookup"><span data-stu-id="a0d3f-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="a0d3f-114">用於識別此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="a0d3f-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0d3f-115"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="a0d3f-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a0d3f-116">datetime</span><span class="sxs-lookup"><span data-stu-id="a0d3f-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a0d3f-117">上次使用者登入。</span><span class="sxs-lookup"><span data-stu-id="a0d3f-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0d3f-118"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="a0d3f-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a0d3f-119">datetime</span><span class="sxs-lookup"><span data-stu-id="a0d3f-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a0d3f-120">上次使用者召集的會議。</span><span class="sxs-lookup"><span data-stu-id="a0d3f-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0d3f-121"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="a0d3f-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a0d3f-122">datetime</span><span class="sxs-lookup"><span data-stu-id="a0d3f-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a0d3f-123">上次使用者上次發生通話失敗。</span><span class="sxs-lookup"><span data-stu-id="a0d3f-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0d3f-124"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="a0d3f-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a0d3f-125">datetime</span><span class="sxs-lookup"><span data-stu-id="a0d3f-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a0d3f-126">上次使用者遇到通話失敗會議召集人的身分。</span><span class="sxs-lookup"><span data-stu-id="a0d3f-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

