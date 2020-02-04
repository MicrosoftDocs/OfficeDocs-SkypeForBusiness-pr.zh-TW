---
title: Lync Server 2013： UserStatistics 表格
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
ms.openlocfilehash: 7609747848e1943a08eff2fa77b87f0168710f81
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="e26d8-102">Lync Server 2013 中的 UserStatistics 表格</span><span class="sxs-lookup"><span data-stu-id="e26d8-102">UserStatistics table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e26d8-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e26d8-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e26d8-104">UserStatistics 資料表是支援資料表。</span><span class="sxs-lookup"><span data-stu-id="e26d8-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="e26d8-105">資料表中的每一筆記錄都儲存著個別使用者使用系統的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e26d8-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="e26d8-106">此表格是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="e26d8-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e26d8-107">左欄</span><span class="sxs-lookup"><span data-stu-id="e26d8-107">Column</span></span></th>
<th><span data-ttu-id="e26d8-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="e26d8-108">Data Type</span></span></th>
<th><span data-ttu-id="e26d8-109">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="e26d8-109">Key/Index</span></span></th>
<th><span data-ttu-id="e26d8-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="e26d8-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e26d8-111"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="e26d8-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="e26d8-112">int</span><span class="sxs-lookup"><span data-stu-id="e26d8-112">int</span></span></p></td>
<td><p><span data-ttu-id="e26d8-113">首選</span><span class="sxs-lookup"><span data-stu-id="e26d8-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="e26d8-114">標識此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="e26d8-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e26d8-115"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="e26d8-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e26d8-116">datetime</span><span class="sxs-lookup"><span data-stu-id="e26d8-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e26d8-117">使用者最後一次登入的時間。</span><span class="sxs-lookup"><span data-stu-id="e26d8-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e26d8-118"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="e26d8-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e26d8-119">datetime</span><span class="sxs-lookup"><span data-stu-id="e26d8-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e26d8-120">使用者最後一次組織會議的時間。</span><span class="sxs-lookup"><span data-stu-id="e26d8-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e26d8-121"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="e26d8-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e26d8-122">datetime</span><span class="sxs-lookup"><span data-stu-id="e26d8-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e26d8-123">使用者最後一次遇到通話失敗的問題。</span><span class="sxs-lookup"><span data-stu-id="e26d8-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e26d8-124"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="e26d8-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e26d8-125">datetime</span><span class="sxs-lookup"><span data-stu-id="e26d8-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e26d8-126">使用者最後一次遇到「會議召集人」通話失敗的問題。</span><span class="sxs-lookup"><span data-stu-id="e26d8-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

