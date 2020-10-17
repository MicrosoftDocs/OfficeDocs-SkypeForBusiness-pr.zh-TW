---
title: Lync Server 2013：承租人表格
description: Lync Server 2013：承租人資料表。
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
ms.openlocfilehash: 96025dfd9fb42a6083f7f3daca98e243f01a8516
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568529"
---
# <a name="tenants-table-in-lync-server-2013"></a><span data-ttu-id="a865f-103">Lync Server 2013 中的承租人表格</span><span class="sxs-lookup"><span data-stu-id="a865f-103">Tenants table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a865f-104">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a865f-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a865f-105">承租人資料表是一種支援資料表，可儲存各種承租人的清單。</span><span class="sxs-lookup"><span data-stu-id="a865f-105">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="a865f-106">表格中的每筆記錄代表一位承租人。</span><span class="sxs-lookup"><span data-stu-id="a865f-106">Each record in the table represents one tenant.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a865f-107">在內部部署中，CDR 使用內建承租人租使用者識別碼來表示不同的驗證類型，例如公用 IM 連線、同盟和匿名。</span><span class="sxs-lookup"><span data-stu-id="a865f-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span>



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
<th><span data-ttu-id="a865f-108">欄</span><span class="sxs-lookup"><span data-stu-id="a865f-108">Column</span></span></th>
<th><span data-ttu-id="a865f-109">資料類型</span><span class="sxs-lookup"><span data-stu-id="a865f-109">Data Type</span></span></th>
<th><span data-ttu-id="a865f-110">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="a865f-110">Key/Index</span></span></th>
<th><span data-ttu-id="a865f-111">詳細資料</span><span class="sxs-lookup"><span data-stu-id="a865f-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a865f-112"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="a865f-112"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="a865f-113">int</span><span class="sxs-lookup"><span data-stu-id="a865f-113">int</span></span></p></td>
<td><p><span data-ttu-id="a865f-114">主要</span><span class="sxs-lookup"><span data-stu-id="a865f-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="a865f-115">用於識別此租使用者識別碼的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="a865f-115">Unique number identifying this Tenant ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a865f-116"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="a865f-116"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="a865f-117">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="a865f-117">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a865f-118">允許的值：</span><span class="sxs-lookup"><span data-stu-id="a865f-118">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="a865f-119">00000000-0000-0000-0000-000000000000 –企業版</span><span class="sxs-lookup"><span data-stu-id="a865f-119">00000000-0000-0000-0000-000000000000 – Enterprise</span></span></p></li>
<li><p><span data-ttu-id="a865f-120">00000000-0000-0000-0000-000000000001 –同盟</span><span class="sxs-lookup"><span data-stu-id="a865f-120">00000000-0000-0000-0000-000000000001 – Federated</span></span></p></li>
<li><p><span data-ttu-id="a865f-121">00000000-0000-0000-0000-000000000002 –匿名</span><span class="sxs-lookup"><span data-stu-id="a865f-121">00000000-0000-0000-0000-000000000002 – Anonymous</span></span></p></li>
<li><p><span data-ttu-id="a865f-122">00000000-0000-0000-0000-000000000003 –公用 IM 連線能力</span><span class="sxs-lookup"><span data-stu-id="a865f-122">00000000-0000-0000-0000-000000000003 – Public IM connectivity</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

