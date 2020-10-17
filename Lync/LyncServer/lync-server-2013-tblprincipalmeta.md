---
title: Lync Server 2013： tblPrincipalMeta
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615009(v=OCS.15)
ms:contentKeyID: 48184648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d70b26dc074213c30248da0e13f137c8b1e2f58a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523640"
---
# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="ce998-102">Lync Server 2013 中的 tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="ce998-102">tblPrincipalMeta in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce998-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="ce998-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="ce998-104">tblPrincipalMeta 包含必須從 Active Directory 網域服務重新整理的主體。</span><span class="sxs-lookup"><span data-stu-id="ce998-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="ce998-105">Columns</span><span class="sxs-lookup"><span data-stu-id="ce998-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce998-106">欄</span><span class="sxs-lookup"><span data-stu-id="ce998-106">Column</span></span></th>
<th><span data-ttu-id="ce998-107">類型</span><span class="sxs-lookup"><span data-stu-id="ce998-107">Type</span></span></th>
<th><span data-ttu-id="ce998-108">描述</span><span class="sxs-lookup"><span data-stu-id="ce998-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce998-109">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="ce998-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="ce998-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="ce998-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ce998-111">主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="ce998-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce998-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="ce998-112">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="ce998-113">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="ce998-113">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="ce998-114">若主體關係必須重新整理，則為 True。</span><span class="sxs-lookup"><span data-stu-id="ce998-114">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce998-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="ce998-115">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="ce998-116">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="ce998-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="ce998-117">若主體屬性必須重新整理，則為 True。</span><span class="sxs-lookup"><span data-stu-id="ce998-117">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce998-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="ce998-118">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="ce998-119">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="ce998-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="ce998-120">若主體已刪除，則為 True。</span><span class="sxs-lookup"><span data-stu-id="ce998-120">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce998-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="ce998-121">tryCount</span></span></p></td>
<td><p><span data-ttu-id="ce998-122">int</span><span class="sxs-lookup"><span data-stu-id="ce998-122">int</span></span></p></td>
<td><p><span data-ttu-id="ce998-123">至今嘗試從 AD DS 重新整理主體的次數。</span><span class="sxs-lookup"><span data-stu-id="ce998-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce998-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="ce998-124">lastTry</span></span></p></td>
<td><p><span data-ttu-id="ce998-125">datetime</span><span class="sxs-lookup"><span data-stu-id="ce998-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="ce998-p101">最近一次嘗試重新整理主體的時間戳記。若尚未重新整理過，可以是 null。</span><span class="sxs-lookup"><span data-stu-id="ce998-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce998-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="ce998-128">nextTry</span></span></p></td>
<td><p><span data-ttu-id="ce998-129">datetime</span><span class="sxs-lookup"><span data-stu-id="ce998-129">datetime</span></span></p></td>
<td><p><span data-ttu-id="ce998-p102">排定下次重新整理時間戳記。若未排定之後的重新整理，可以是 null。</span><span class="sxs-lookup"><span data-stu-id="ce998-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="ce998-132">索引鍵</span><span class="sxs-lookup"><span data-stu-id="ce998-132">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce998-133">欄</span><span class="sxs-lookup"><span data-stu-id="ce998-133">Column</span></span></th>
<th><span data-ttu-id="ce998-134">描述</span><span class="sxs-lookup"><span data-stu-id="ce998-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce998-135">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="ce998-135">prinID</span></span></p></td>
<td><p><span data-ttu-id="ce998-136">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="ce998-136">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce998-137">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="ce998-137">prinID</span></span></p></td>
<td><p><span data-ttu-id="ce998-138">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="ce998-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

