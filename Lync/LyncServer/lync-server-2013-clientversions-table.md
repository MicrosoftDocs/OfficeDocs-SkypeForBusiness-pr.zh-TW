---
title: Lync Server 2013： ClientVersions 表格
description: Lync Server 2013： ClientVersions 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ClientVersions table
ms:assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398356(v=OCS.15)
ms:contentKeyID: 48184176
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81cf7147b7e36148901580983cf66176b574f815
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542809"
---
# <a name="clientversions-table-in-lync-server-2013"></a><span data-ttu-id="918c9-103">Lync Server 2013 中的 ClientVersions 表格</span><span class="sxs-lookup"><span data-stu-id="918c9-103">ClientVersions table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="918c9-104">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="918c9-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="918c9-p101">ClientVersions 表格是一種支援資料表，儲存資料庫中所記錄的工作階段之各種參與用戶端類型和版本清單。表格中的每筆記錄代表一個用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="918c9-p101">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database. Each record in the table represents one client version.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="918c9-107">欄</span><span class="sxs-lookup"><span data-stu-id="918c9-107">Column</span></span></th>
<th><span data-ttu-id="918c9-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="918c9-108">Data Type</span></span></th>
<th><span data-ttu-id="918c9-109">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="918c9-109">Key/Index</span></span></th>
<th><span data-ttu-id="918c9-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="918c9-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="918c9-111"><strong>VersionId</strong></span><span class="sxs-lookup"><span data-stu-id="918c9-111"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="918c9-112"><strong>int</strong></span><span class="sxs-lookup"><span data-stu-id="918c9-112"><strong>int</strong></span></span></p></td>
<td><p><span data-ttu-id="918c9-113">主要</span><span class="sxs-lookup"><span data-stu-id="918c9-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="918c9-114">用於識別此用戶端類型及版本的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="918c9-114">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="918c9-115"><strong>版本</strong></span><span class="sxs-lookup"><span data-stu-id="918c9-115"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="918c9-116"><strong>Nvarchar (256) </strong></span><span class="sxs-lookup"><span data-stu-id="918c9-116"><strong>nvarchar(256)</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="918c9-117">版本名稱。</span><span class="sxs-lookup"><span data-stu-id="918c9-117">Version name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="918c9-118"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="918c9-118"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="918c9-119">int</span><span class="sxs-lookup"><span data-stu-id="918c9-119">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="918c9-120">指出工作階段所使用的用戶端類型。</span><span class="sxs-lookup"><span data-stu-id="918c9-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="918c9-121">如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="918c9-121">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="918c9-122">此欄位是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="918c9-122">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

