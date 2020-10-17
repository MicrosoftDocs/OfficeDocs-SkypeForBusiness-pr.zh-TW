---
title: Lync Server 2013：使用者視圖
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
ms.openlocfilehash: f978b6acaa1cdfdf6abf2d768c1fb679af260a63
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530150"
---
# <a name="user-view-in-lync-server-2013"></a><span data-ttu-id="913e4-102">Lync Server 2013 中的使用者視圖</span><span class="sxs-lookup"><span data-stu-id="913e4-102">User view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="913e4-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="913e4-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="913e4-104">使用者檢視會儲存在資料庫中有記錄之通話或工作階段中所涉及的使用者相關資訊。</span><span class="sxs-lookup"><span data-stu-id="913e4-104">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="913e4-105">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="913e4-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="913e4-106">欄</span><span class="sxs-lookup"><span data-stu-id="913e4-106">Column</span></span></th>
<th><span data-ttu-id="913e4-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="913e4-107">Data Type</span></span></th>
<th><span data-ttu-id="913e4-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="913e4-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="913e4-109">UserId</span><span class="sxs-lookup"><span data-stu-id="913e4-109">UserId</span></span></p></td>
<td><p><span data-ttu-id="913e4-110">int</span><span class="sxs-lookup"><span data-stu-id="913e4-110">int</span></span></p></td>
<td><p><span data-ttu-id="913e4-111">用於識別此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="913e4-111">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="913e4-112">UserUri</span><span class="sxs-lookup"><span data-stu-id="913e4-112">UserUri</span></span></p></td>
<td><p><span data-ttu-id="913e4-113">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="913e4-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="913e4-114">使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="913e4-114">Uri of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="913e4-115">TenantKey</span><span class="sxs-lookup"><span data-stu-id="913e4-115">TenantKey</span></span></p></td>
<td><p><span data-ttu-id="913e4-116">唯一</span><span class="sxs-lookup"><span data-stu-id="913e4-116">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="913e4-117">使用者的租用戶。</span><span class="sxs-lookup"><span data-stu-id="913e4-117">Tenant of user.</span></span> <span data-ttu-id="913e4-118">如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="913e4-118">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="913e4-119">UriType</span><span class="sxs-lookup"><span data-stu-id="913e4-119">UriType</span></span></p></td>
<td><p><span data-ttu-id="913e4-120">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="913e4-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="913e4-121">使用者 URI 的類型。</span><span class="sxs-lookup"><span data-stu-id="913e4-121">Type of user URI.</span></span> <span data-ttu-id="913e4-122">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="913e4-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

