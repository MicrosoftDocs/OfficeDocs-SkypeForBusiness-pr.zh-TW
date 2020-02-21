---
title: 'Lync Server 2013: Tenants 表格'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Tenants table
ms:assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412950(v=OCS.15)
ms:contentKeyID: 48185309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d33f9138267cd26ff58fb32fc06c33c8b793c6d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tenants-table-in-lync-server-2013"></a><span data-ttu-id="92db1-102">Lync Server 2013 中的租用戶表格</span><span class="sxs-lookup"><span data-stu-id="92db1-102">Tenants table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92db1-103">_**主題上次修改日期：** 2012年-09-28_</span><span class="sxs-lookup"><span data-stu-id="92db1-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="92db1-104">Tenants 表格是一種支援資料表儲存的各種不同的租用戶清單。</span><span class="sxs-lookup"><span data-stu-id="92db1-104">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="92db1-105">表格中的每筆記錄代表一位承租人。</span><span class="sxs-lookup"><span data-stu-id="92db1-105">Each record in the table represents one tenant.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="92db1-106">在內部部署中，CDR 會使用內建租用戶識別碼表示各種驗證類型，例如公共 IM 連線、 同盟及匿名。</span><span class="sxs-lookup"><span data-stu-id="92db1-106">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92db1-107">欄</span><span class="sxs-lookup"><span data-stu-id="92db1-107">Column</span></span></th>
<th><span data-ttu-id="92db1-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="92db1-108">Data Type</span></span></th>
<th><span data-ttu-id="92db1-109">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="92db1-109">Key/Index</span></span></th>
<th><span data-ttu-id="92db1-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="92db1-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92db1-111"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="92db1-111"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="92db1-112">int</span><span class="sxs-lookup"><span data-stu-id="92db1-112">int</span></span></p></td>
<td><p><span data-ttu-id="92db1-113">主要</span><span class="sxs-lookup"><span data-stu-id="92db1-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="92db1-114">用於識別此租用戶識別碼的唯一號碼</span><span class="sxs-lookup"><span data-stu-id="92db1-114">Unique number identifying this Tenant ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92db1-115"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="92db1-115"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="92db1-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="92db1-116">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="92db1-117">允許的值：</span><span class="sxs-lookup"><span data-stu-id="92db1-117">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="92db1-118">00000000-0000-0000-0000-000000000000 – 企業</span><span class="sxs-lookup"><span data-stu-id="92db1-118">00000000-0000-0000-0000-000000000000 – Enterprise</span></span></p></li>
<li><p><span data-ttu-id="92db1-119">00000000-0000-0000-0000-000000000001 – 同盟</span><span class="sxs-lookup"><span data-stu-id="92db1-119">00000000-0000-0000-0000-000000000001 – Federated</span></span></p></li>
<li><p><span data-ttu-id="92db1-120">00000000-0000-0000-0000-000000000002 – 匿名</span><span class="sxs-lookup"><span data-stu-id="92db1-120">00000000-0000-0000-0000-000000000002 – Anonymous</span></span></p></li>
<li><p><span data-ttu-id="92db1-121">00000000-0000-0000-0000-000000000003 – 公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="92db1-121">00000000-0000-0000-0000-000000000003 – Public IM connectivity</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

