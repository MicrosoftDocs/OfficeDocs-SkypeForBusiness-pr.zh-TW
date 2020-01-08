---
title: Lync Server 2013：使用者視圖
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User view
ms:assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688100(v=OCS.15)
ms:contentKeyID: 49733699
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21c22bdfbf758545418a821edaba5d8aaf447b87
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977224"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-view-in-lync-server-2013"></a><span data-ttu-id="c5c7b-102">Lync Server 2013 中的使用者視圖</span><span class="sxs-lookup"><span data-stu-id="c5c7b-102">User view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5c7b-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c5c7b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c5c7b-104">[使用者] 視圖儲存已參與通話的使用者相關資訊，或在資料庫中有記錄的會話。</span><span class="sxs-lookup"><span data-stu-id="c5c7b-104">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="c5c7b-105">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="c5c7b-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5c7b-106">左欄</span><span class="sxs-lookup"><span data-stu-id="c5c7b-106">Column</span></span></th>
<th><span data-ttu-id="c5c7b-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="c5c7b-107">Data Type</span></span></th>
<th><span data-ttu-id="c5c7b-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="c5c7b-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5c7b-109">UserId</span><span class="sxs-lookup"><span data-stu-id="c5c7b-109">UserId</span></span></p></td>
<td><p><span data-ttu-id="c5c7b-110">int</span><span class="sxs-lookup"><span data-stu-id="c5c7b-110">int</span></span></p></td>
<td><p><span data-ttu-id="c5c7b-111">標識此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="c5c7b-111">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5c7b-112">UserUri</span><span class="sxs-lookup"><span data-stu-id="c5c7b-112">UserUri</span></span></p></td>
<td><p><span data-ttu-id="c5c7b-113">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="c5c7b-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c5c7b-114">使用者的 Uri。</span><span class="sxs-lookup"><span data-stu-id="c5c7b-114">Uri of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5c7b-115">TenantKey</span><span class="sxs-lookup"><span data-stu-id="c5c7b-115">TenantKey</span></span></p></td>
<td><p><span data-ttu-id="c5c7b-116">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="c5c7b-116">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="c5c7b-117">使用者租使用者。</span><span class="sxs-lookup"><span data-stu-id="c5c7b-117">Tenant of user.</span></span> <span data-ttu-id="c5c7b-118">如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</span><span class="sxs-lookup"><span data-stu-id="c5c7b-118">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5c7b-119">UriType</span><span class="sxs-lookup"><span data-stu-id="c5c7b-119">UriType</span></span></p></td>
<td><p><span data-ttu-id="c5c7b-120">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="c5c7b-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5c7b-121">使用者 URI 的類型。</span><span class="sxs-lookup"><span data-stu-id="c5c7b-121">Type of user URI.</span></span> <span data-ttu-id="c5c7b-122">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="c5c7b-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

