---
title: Lync Server 2013：使用者視圖
description: Lync Server 2013：使用者視圖。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User view
ms:assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688100(v=OCS.15)
ms:contentKeyID: 49733699
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa606887e8050a51f1e5a87656bb74a7cd58bbc3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558909"
---
# <a name="user-view-in-lync-server-2013"></a><span data-ttu-id="92829-103">Lync Server 2013 中的使用者視圖</span><span class="sxs-lookup"><span data-stu-id="92829-103">User view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92829-104">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="92829-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="92829-105">使用者檢視會儲存在資料庫中有記錄之通話或工作階段中所涉及的使用者相關資訊。</span><span class="sxs-lookup"><span data-stu-id="92829-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="92829-106">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="92829-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92829-107">欄</span><span class="sxs-lookup"><span data-stu-id="92829-107">Column</span></span></th>
<th><span data-ttu-id="92829-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="92829-108">Data Type</span></span></th>
<th><span data-ttu-id="92829-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="92829-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92829-110">UserId</span><span class="sxs-lookup"><span data-stu-id="92829-110">UserId</span></span></p></td>
<td><p><span data-ttu-id="92829-111">int</span><span class="sxs-lookup"><span data-stu-id="92829-111">int</span></span></p></td>
<td><p><span data-ttu-id="92829-112">用於識別此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="92829-112">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92829-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="92829-113">UserUri</span></span></p></td>
<td><p><span data-ttu-id="92829-114">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="92829-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="92829-115">使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="92829-115">Uri of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92829-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="92829-116">TenantKey</span></span></p></td>
<td><p><span data-ttu-id="92829-117">唯一</span><span class="sxs-lookup"><span data-stu-id="92829-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="92829-118">使用者的租用戶。</span><span class="sxs-lookup"><span data-stu-id="92829-118">Tenant of user.</span></span> <span data-ttu-id="92829-119">如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="92829-119">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92829-120">UriType</span><span class="sxs-lookup"><span data-stu-id="92829-120">UriType</span></span></p></td>
<td><p><span data-ttu-id="92829-121">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="92829-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="92829-122">使用者 URI 的類型。</span><span class="sxs-lookup"><span data-stu-id="92829-122">Type of user URI.</span></span> <span data-ttu-id="92829-123">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="92829-123">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

