---
title: 'Lync Server 2013: tblSkippedAffiliations'
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
ms.openlocfilehash: d21dbda8b649588e691d285c62ff865e9f001308
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblskippedaffiliations-in-lync-server-2013"></a><span data-ttu-id="d7f38-102">Lync Server 2013 中的 tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="d7f38-102">tblSkippedAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7f38-103">_**主題上次修改日期：** 2012年-09-12_</span><span class="sxs-lookup"><span data-stu-id="d7f38-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="d7f38-104">tblSkippedAffiliations 包含無法讀取 （通常是由於 Active Directory 網域服務存取錯誤） 的關係。</span><span class="sxs-lookup"><span data-stu-id="d7f38-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>

### <a name="columns"></a><span data-ttu-id="d7f38-105">Columns</span><span class="sxs-lookup"><span data-stu-id="d7f38-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7f38-106">欄</span><span class="sxs-lookup"><span data-stu-id="d7f38-106">Column</span></span></th>
<th><span data-ttu-id="d7f38-107">類型	</span><span class="sxs-lookup"><span data-stu-id="d7f38-107">Type</span></span></th>
<th><span data-ttu-id="d7f38-108">描述</span><span class="sxs-lookup"><span data-stu-id="d7f38-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7f38-109">prinID</span><span class="sxs-lookup"><span data-stu-id="d7f38-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="d7f38-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="d7f38-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d7f38-111">主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="d7f38-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7f38-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="d7f38-112">affDescription</span></span></p></td>
<td><p><span data-ttu-id="d7f38-113">nvarchar (255)，非 null</span><span class="sxs-lookup"><span data-stu-id="d7f38-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="d7f38-114">識別關係的字串。</span><span class="sxs-lookup"><span data-stu-id="d7f38-114">A string identifying the affiliation.</span></span></p>
<p><span data-ttu-id="d7f38-115">格式為： guid: {0} uri: {1} &gt;識別碼：{2}</span><span class="sxs-lookup"><span data-stu-id="d7f38-115">The format is: guid: {0} uri: {1}&gt; id: {2}</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7f38-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="d7f38-116">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="d7f38-117">int，非 null</span><span class="sxs-lookup"><span data-stu-id="d7f38-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d7f38-p101">上次更新此列之主體的識別碼。其一律為 1 (系統使用者) 因為 Active Directory 同步處理是這些項目的唯一來源。</span><span class="sxs-lookup"><span data-stu-id="d7f38-p101">ID of the principal that updated this row. It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="d7f38-120">索引鍵</span><span class="sxs-lookup"><span data-stu-id="d7f38-120">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7f38-121">資料欄</span><span class="sxs-lookup"><span data-stu-id="d7f38-121">Column(s)</span></span></th>
<th><span data-ttu-id="d7f38-122">描述</span><span class="sxs-lookup"><span data-stu-id="d7f38-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7f38-123">&lt;prinID affDescription&gt;</span><span class="sxs-lookup"><span data-stu-id="d7f38-123">&lt;prinID, affDescription&gt;</span></span></p></td>
<td><p><span data-ttu-id="d7f38-124">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="d7f38-124">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7f38-125">prinID</span><span class="sxs-lookup"><span data-stu-id="d7f38-125">prinID</span></span></p></td>
<td><p><span data-ttu-id="d7f38-126">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="d7f38-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

