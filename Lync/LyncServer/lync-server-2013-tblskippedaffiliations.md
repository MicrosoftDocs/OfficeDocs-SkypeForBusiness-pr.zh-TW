---
title: Lync Server 2013： tblSkippedAffiliations
description: Lync Server 2013： tblSkippedAffiliations。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblSkippedAffiliations
ms:assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558611(v=OCS.15)
ms:contentKeyID: 48183373
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31746cee7302d34a1d19b3059ca1da6beab9345d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563799"
---
# <a name="tblskippedaffiliations-in-lync-server-2013"></a><span data-ttu-id="695f1-103">Lync Server 2013 中的 tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="695f1-103">tblSkippedAffiliations in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="695f1-104">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="695f1-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="695f1-105">tblSkippedAffiliations 包含無法讀取的隸屬 (，通常是因為 Active Directory 網域服務存取錯誤) 。</span><span class="sxs-lookup"><span data-stu-id="695f1-105">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>

### <a name="columns"></a><span data-ttu-id="695f1-106">Columns</span><span class="sxs-lookup"><span data-stu-id="695f1-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="695f1-107">欄</span><span class="sxs-lookup"><span data-stu-id="695f1-107">Column</span></span></th>
<th><span data-ttu-id="695f1-108">類型</span><span class="sxs-lookup"><span data-stu-id="695f1-108">Type</span></span></th>
<th><span data-ttu-id="695f1-109">描述</span><span class="sxs-lookup"><span data-stu-id="695f1-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="695f1-110">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="695f1-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="695f1-111">int，非 null</span><span class="sxs-lookup"><span data-stu-id="695f1-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="695f1-112">主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="695f1-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="695f1-113">affDescription</span><span class="sxs-lookup"><span data-stu-id="695f1-113">affDescription</span></span></p></td>
<td><p><span data-ttu-id="695f1-114">nvarchar (255)，非 null</span><span class="sxs-lookup"><span data-stu-id="695f1-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="695f1-115">識別關係的字串。</span><span class="sxs-lookup"><span data-stu-id="695f1-115">A string identifying the affiliation.</span></span></p>
<p><span data-ttu-id="695f1-116">格式為： guid： {0} uri： {1} &gt; 識別碼：{2}</span><span class="sxs-lookup"><span data-stu-id="695f1-116">The format is: guid: {0} uri: {1}&gt; id: {2}</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="695f1-117">updatedBy</span><span class="sxs-lookup"><span data-stu-id="695f1-117">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="695f1-118">int，非 null</span><span class="sxs-lookup"><span data-stu-id="695f1-118">int, not null</span></span></p></td>
<td><p><span data-ttu-id="695f1-p101">上次更新此列之主體的識別碼。其一律為 1 (系統使用者) 因為 Active Directory 同步處理是這些項目的唯一來源。</span><span class="sxs-lookup"><span data-stu-id="695f1-p101">ID of the principal that updated this row. It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="695f1-121">索引鍵</span><span class="sxs-lookup"><span data-stu-id="695f1-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="695f1-122">欄 (s) </span><span class="sxs-lookup"><span data-stu-id="695f1-122">Column(s)</span></span></th>
<th><span data-ttu-id="695f1-123">描述</span><span class="sxs-lookup"><span data-stu-id="695f1-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="695f1-124">&lt;Tblprincipal.prinid、affDescription&gt;</span><span class="sxs-lookup"><span data-stu-id="695f1-124">&lt;prinID, affDescription&gt;</span></span></p></td>
<td><p><span data-ttu-id="695f1-125">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="695f1-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="695f1-126">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="695f1-126">prinID</span></span></p></td>
<td><p><span data-ttu-id="695f1-127">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="695f1-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

