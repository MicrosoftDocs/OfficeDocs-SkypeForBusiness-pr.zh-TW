---
title: Lync Server 2013：tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblSkippedAffiliations
ms:assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558611(v=OCS.15)
ms:contentKeyID: 48183373
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06269ede55a46757f78595d7573f3cd77414d1d5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblskippedaffiliations-in-lync-server-2013"></a><span data-ttu-id="5b8c2-102">Lync Server 2013 中的 tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="5b8c2-102">tblSkippedAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b8c2-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5b8c2-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5b8c2-104">tblSkippedAffiliations 包含無法讀取的隸屬關係（通常是由於 Active Directory 網域服務存取錯誤）。</span><span class="sxs-lookup"><span data-stu-id="5b8c2-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>

### <a name="columns"></a><span data-ttu-id="5b8c2-105">分欄</span><span class="sxs-lookup"><span data-stu-id="5b8c2-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b8c2-106">左欄</span><span class="sxs-lookup"><span data-stu-id="5b8c2-106">Column</span></span></th>
<th><span data-ttu-id="5b8c2-107">類型</span><span class="sxs-lookup"><span data-stu-id="5b8c2-107">Type</span></span></th>
<th><span data-ttu-id="5b8c2-108">描述</span><span class="sxs-lookup"><span data-stu-id="5b8c2-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b8c2-109">prinID</span><span class="sxs-lookup"><span data-stu-id="5b8c2-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="5b8c2-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="5b8c2-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5b8c2-111">Principal ID。</span><span class="sxs-lookup"><span data-stu-id="5b8c2-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b8c2-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="5b8c2-112">affDescription</span></span></p></td>
<td><p><span data-ttu-id="5b8c2-113">Nvarchar （256），not null</span><span class="sxs-lookup"><span data-stu-id="5b8c2-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="5b8c2-114">標識隸屬關係的字串。</span><span class="sxs-lookup"><span data-stu-id="5b8c2-114">A string identifying the affiliation.</span></span></p>
<p><span data-ttu-id="5b8c2-115">格式為： guid： {0} uri： {1} &gt; id：{2}</span><span class="sxs-lookup"><span data-stu-id="5b8c2-115">The format is: guid: {0} uri: {1}&gt; id: {2}</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b8c2-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="5b8c2-116">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="5b8c2-117">int，not null</span><span class="sxs-lookup"><span data-stu-id="5b8c2-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5b8c2-118">更新此列之主體的 ID。</span><span class="sxs-lookup"><span data-stu-id="5b8c2-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="5b8c2-119">因為 Active Directory 同步處理是這些專案的唯一來源，所以它永遠是1（系統使用者）。</span><span class="sxs-lookup"><span data-stu-id="5b8c2-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="5b8c2-120">鍵</span><span class="sxs-lookup"><span data-stu-id="5b8c2-120">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b8c2-121">欄（s）</span><span class="sxs-lookup"><span data-stu-id="5b8c2-121">Column(s)</span></span></th>
<th><span data-ttu-id="5b8c2-122">描述</span><span class="sxs-lookup"><span data-stu-id="5b8c2-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b8c2-123">&lt;prinID, affDescription&gt;</span><span class="sxs-lookup"><span data-stu-id="5b8c2-123">&lt;prinID, affDescription&gt;</span></span></p></td>
<td><p><span data-ttu-id="5b8c2-124">主鍵。</span><span class="sxs-lookup"><span data-stu-id="5b8c2-124">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b8c2-125">prinID</span><span class="sxs-lookup"><span data-stu-id="5b8c2-125">prinID</span></span></p></td>
<td><p><span data-ttu-id="5b8c2-126">在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="5b8c2-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

