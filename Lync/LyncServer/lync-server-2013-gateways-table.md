---
title: Lync Server 2013：閘道表格
description: Lync Server 2013：閘道表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Gateways table
ms:assetid: a909daad-d137-45e0-b149-1de9f8e1e029
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412795(v=OCS.15)
ms:contentKeyID: 48185034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 869aee0227c64c17f7bdbbfd82acbd43ae029bac
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567039"
---
# <a name="gateways-table-in-lync-server-2013"></a><span data-ttu-id="79160-103">Lync Server 2013 中的閘道表格</span><span class="sxs-lookup"><span data-stu-id="79160-103">Gateways table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79160-104">_**主題上次修改日期：** 2010-11-05_</span><span class="sxs-lookup"><span data-stu-id="79160-104">_**Topic Last Modified:** 2010-11-05_</span></span>

<span data-ttu-id="79160-105">閘道表格是支援的表格。</span><span class="sxs-lookup"><span data-stu-id="79160-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="79160-106">每筆記錄都儲存在公用交換電話網路 (PSTN) 具有資料庫中記錄的電話所涉及的一個閘道的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="79160-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79160-107">欄</span><span class="sxs-lookup"><span data-stu-id="79160-107">Column</span></span></th>
<th><span data-ttu-id="79160-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="79160-108">Data Type</span></span></th>
<th><span data-ttu-id="79160-109">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="79160-109">Key/Index</span></span></th>
<th><span data-ttu-id="79160-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="79160-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79160-111"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="79160-111"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="79160-112">int</span><span class="sxs-lookup"><span data-stu-id="79160-112">int</span></span></p></td>
<td><p><span data-ttu-id="79160-113">主要</span><span class="sxs-lookup"><span data-stu-id="79160-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="79160-114">用於識別此閘道的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="79160-114">Unique number identifying this gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79160-115"><strong>閘道</strong></span><span class="sxs-lookup"><span data-stu-id="79160-115"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="79160-116">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="79160-116">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="79160-117">閘道名稱。</span><span class="sxs-lookup"><span data-stu-id="79160-117">Gateway name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

