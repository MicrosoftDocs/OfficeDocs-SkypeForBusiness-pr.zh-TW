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
ms.openlocfilehash: c8e88d7a9fa66f309bbd64ab064ec95adafc40b8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-view-in-lync-server-2013"></a><span data-ttu-id="6ec79-102">Lync Server 2013 中的使用者視圖</span><span class="sxs-lookup"><span data-stu-id="6ec79-102">User view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ec79-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="6ec79-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="6ec79-104">[使用者] 視圖儲存已參與通話的使用者相關資訊，或在資料庫中有記錄的會話。</span><span class="sxs-lookup"><span data-stu-id="6ec79-104">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="6ec79-105">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="6ec79-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ec79-106">左欄</span><span class="sxs-lookup"><span data-stu-id="6ec79-106">Column</span></span></th>
<th><span data-ttu-id="6ec79-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="6ec79-107">Data Type</span></span></th>
<th><span data-ttu-id="6ec79-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="6ec79-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ec79-109">UserId</span><span class="sxs-lookup"><span data-stu-id="6ec79-109">UserId</span></span></p></td>
<td><p><span data-ttu-id="6ec79-110">int</span><span class="sxs-lookup"><span data-stu-id="6ec79-110">int</span></span></p></td>
<td><p><span data-ttu-id="6ec79-111">標識此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="6ec79-111">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ec79-112">UserUri</span><span class="sxs-lookup"><span data-stu-id="6ec79-112">UserUri</span></span></p></td>
<td><p><span data-ttu-id="6ec79-113">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="6ec79-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="6ec79-114">使用者的 Uri。</span><span class="sxs-lookup"><span data-stu-id="6ec79-114">Uri of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ec79-115">TenantKey</span><span class="sxs-lookup"><span data-stu-id="6ec79-115">TenantKey</span></span></p></td>
<td><p><span data-ttu-id="6ec79-116">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="6ec79-116">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="6ec79-117">使用者租使用者。</span><span class="sxs-lookup"><span data-stu-id="6ec79-117">Tenant of user.</span></span> <span data-ttu-id="6ec79-118">如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</span><span class="sxs-lookup"><span data-stu-id="6ec79-118">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ec79-119">UriType</span><span class="sxs-lookup"><span data-stu-id="6ec79-119">UriType</span></span></p></td>
<td><p><span data-ttu-id="6ec79-120">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="6ec79-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6ec79-121">使用者 URI 的類型。</span><span class="sxs-lookup"><span data-stu-id="6ec79-121">Type of user URI.</span></span> <span data-ttu-id="6ec79-122">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="6ec79-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

