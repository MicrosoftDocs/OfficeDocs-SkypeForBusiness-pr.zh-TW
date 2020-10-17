---
title: Lync Server 2013： MediationServers 表格
description: Lync Server 2013： MediationServers 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediationServers table
ms:assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412743(v=OCS.15)
ms:contentKeyID: 48184929
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a227f76272790d3a23ff06f0c97ba4a263f418a5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568599"
---
# <a name="mediationservers-table-in-lync-server-2013"></a><span data-ttu-id="131cc-103">Lync Server 2013 中的 MediationServers 表格</span><span class="sxs-lookup"><span data-stu-id="131cc-103">MediationServers table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="131cc-104">_**主題上次修改日期：** 2010-11-06_</span><span class="sxs-lookup"><span data-stu-id="131cc-104">_**Topic Last Modified:** 2010-11-06_</span></span>

<span data-ttu-id="131cc-105">MediationServers 表格是支援的表格。</span><span class="sxs-lookup"><span data-stu-id="131cc-105">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="131cc-106">每筆記錄都儲存在具有資料庫中記錄之通話所涉及的一個轉送伺服器的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="131cc-106">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="131cc-107">欄</span><span class="sxs-lookup"><span data-stu-id="131cc-107">Column</span></span></th>
<th><span data-ttu-id="131cc-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="131cc-108">Data Type</span></span></th>
<th><span data-ttu-id="131cc-109">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="131cc-109">Key/Index</span></span></th>
<th><span data-ttu-id="131cc-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="131cc-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="131cc-111"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="131cc-111"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="131cc-112">int</span><span class="sxs-lookup"><span data-stu-id="131cc-112">int</span></span></p></td>
<td><p><span data-ttu-id="131cc-113">主要</span><span class="sxs-lookup"><span data-stu-id="131cc-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="131cc-114">用於識別此轉送伺服器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="131cc-114">Unique number identifying this Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="131cc-115"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="131cc-115"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="131cc-116">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="131cc-116">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="131cc-117">轉送伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="131cc-117">Mediation Server name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

