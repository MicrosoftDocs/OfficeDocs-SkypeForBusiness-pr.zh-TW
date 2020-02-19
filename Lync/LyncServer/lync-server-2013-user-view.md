---
title: Lync Server 2013： 使用者檢視
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
ms.openlocfilehash: a63150d567b893b4d1c4445d91544b4c83659bf4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-view-in-lync-server-2013"></a><span data-ttu-id="ab77e-102">Lync Server 2013 中的使用者檢視</span><span class="sxs-lookup"><span data-stu-id="ab77e-102">User view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab77e-103">_**主題上次修改日期：** 2012年-10-01_</span><span class="sxs-lookup"><span data-stu-id="ab77e-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ab77e-104">使用者檢視會儲存在資料庫中有記錄之通話或工作階段中所涉及的使用者相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ab77e-104">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="ab77e-105">Microsoft Lync Server 2013 中已採用此檢視。</span><span class="sxs-lookup"><span data-stu-id="ab77e-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab77e-106">欄</span><span class="sxs-lookup"><span data-stu-id="ab77e-106">Column</span></span></th>
<th><span data-ttu-id="ab77e-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="ab77e-107">Data Type</span></span></th>
<th><span data-ttu-id="ab77e-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="ab77e-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab77e-109">UserId</span><span class="sxs-lookup"><span data-stu-id="ab77e-109">UserId</span></span></p></td>
<td><p><span data-ttu-id="ab77e-110">int</span><span class="sxs-lookup"><span data-stu-id="ab77e-110">int</span></span></p></td>
<td><p><span data-ttu-id="ab77e-111">用於識別此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="ab77e-111">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab77e-112">UserUri</span><span class="sxs-lookup"><span data-stu-id="ab77e-112">UserUri</span></span></p></td>
<td><p><span data-ttu-id="ab77e-113">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="ab77e-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ab77e-114">使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="ab77e-114">Uri of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab77e-115">TenantKey</span><span class="sxs-lookup"><span data-stu-id="ab77e-115">TenantKey</span></span></p></td>
<td><p><span data-ttu-id="ab77e-116">唯一</span><span class="sxs-lookup"><span data-stu-id="ab77e-116">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="ab77e-117">使用者的租用戶。</span><span class="sxs-lookup"><span data-stu-id="ab77e-117">Tenant of user.</span></span> <span data-ttu-id="ab77e-118">請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租用戶表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ab77e-118">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab77e-119">UriType</span><span class="sxs-lookup"><span data-stu-id="ab77e-119">UriType</span></span></p></td>
<td><p><span data-ttu-id="ab77e-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ab77e-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ab77e-121">使用者 URI 的類型。</span><span class="sxs-lookup"><span data-stu-id="ab77e-121">Type of user URI.</span></span> <span data-ttu-id="ab77e-122">請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ab77e-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

