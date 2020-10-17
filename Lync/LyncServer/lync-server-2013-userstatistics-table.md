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
ms.openlocfilehash: 55df55ba8c9953a1efce25269c24b43328472d7f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529990"
---
# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="69f1c-102">Lync Server 2013 中的 UserStatistics 表格</span><span class="sxs-lookup"><span data-stu-id="69f1c-102">UserStatistics table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69f1c-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="69f1c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="69f1c-104">UserStatistics 表格是支援的表格。</span><span class="sxs-lookup"><span data-stu-id="69f1c-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="69f1c-105">資料表中的每一筆記錄都儲存了個別使用者對系統使用方式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="69f1c-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="69f1c-106">此表格已引進 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="69f1c-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69f1c-107">欄</span><span class="sxs-lookup"><span data-stu-id="69f1c-107">Column</span></span></th>
<th><span data-ttu-id="69f1c-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="69f1c-108">Data Type</span></span></th>
<th><span data-ttu-id="69f1c-109">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="69f1c-109">Key/Index</span></span></th>
<th><span data-ttu-id="69f1c-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="69f1c-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69f1c-111"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="69f1c-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="69f1c-112">int</span><span class="sxs-lookup"><span data-stu-id="69f1c-112">int</span></span></p></td>
<td><p><span data-ttu-id="69f1c-113">主要</span><span class="sxs-lookup"><span data-stu-id="69f1c-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="69f1c-114">用於識別此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="69f1c-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69f1c-115"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="69f1c-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="69f1c-116">datetime</span><span class="sxs-lookup"><span data-stu-id="69f1c-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69f1c-117">使用者上次登入的時間。</span><span class="sxs-lookup"><span data-stu-id="69f1c-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69f1c-118"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="69f1c-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="69f1c-119">datetime</span><span class="sxs-lookup"><span data-stu-id="69f1c-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69f1c-120">使用者上次組織會議的時間。</span><span class="sxs-lookup"><span data-stu-id="69f1c-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69f1c-121"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="69f1c-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="69f1c-122">datetime</span><span class="sxs-lookup"><span data-stu-id="69f1c-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69f1c-123">上次使用者發生通話失敗的時間。</span><span class="sxs-lookup"><span data-stu-id="69f1c-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69f1c-124"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="69f1c-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="69f1c-125">datetime</span><span class="sxs-lookup"><span data-stu-id="69f1c-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69f1c-126">使用者最後一次遇到會議召集人的呼叫失敗。</span><span class="sxs-lookup"><span data-stu-id="69f1c-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

