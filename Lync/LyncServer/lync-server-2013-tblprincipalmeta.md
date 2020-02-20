---
title: 'Lync Server 2013: tblprincipalmeta 表格'
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
ms.openlocfilehash: 5a1b4161a04b3107e3aff7b55ab82840ac6680e6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="4c1bc-102">Lync Server 2013 中的 tblprincipalmeta 表格</span><span class="sxs-lookup"><span data-stu-id="4c1bc-102">tblPrincipalMeta in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c1bc-103">_**主題上次修改日期：** 2012年-09-12_</span><span class="sxs-lookup"><span data-stu-id="4c1bc-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="4c1bc-104">tblprincipalmeta 表格包含必須從 Active Directory 網域服務重新整理的主體。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="4c1bc-105">Columns</span><span class="sxs-lookup"><span data-stu-id="4c1bc-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c1bc-106">欄</span><span class="sxs-lookup"><span data-stu-id="4c1bc-106">Column</span></span></th>
<th><span data-ttu-id="4c1bc-107">類型	</span><span class="sxs-lookup"><span data-stu-id="4c1bc-107">Type</span></span></th>
<th><span data-ttu-id="4c1bc-108">描述</span><span class="sxs-lookup"><span data-stu-id="4c1bc-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c1bc-109">prinID</span><span class="sxs-lookup"><span data-stu-id="4c1bc-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="4c1bc-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="4c1bc-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4c1bc-111">主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1bc-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="4c1bc-112">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="4c1bc-113">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="4c1bc-113">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="4c1bc-114">若主體關係必須重新整理，則為 True。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-114">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1bc-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="4c1bc-115">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="4c1bc-116">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="4c1bc-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="4c1bc-117">若主體屬性必須重新整理，則為 True。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-117">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1bc-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="4c1bc-118">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="4c1bc-119">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="4c1bc-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="4c1bc-120">若主體已刪除，則為 True。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-120">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1bc-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="4c1bc-121">tryCount</span></span></p></td>
<td><p><span data-ttu-id="4c1bc-122">int</span><span class="sxs-lookup"><span data-stu-id="4c1bc-122">int</span></span></p></td>
<td><p><span data-ttu-id="4c1bc-123">至今嘗試從 AD DS 重新整理主體的次數。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1bc-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="4c1bc-124">lastTry</span></span></p></td>
<td><p><span data-ttu-id="4c1bc-125">datetime</span><span class="sxs-lookup"><span data-stu-id="4c1bc-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="4c1bc-p101">最近一次嘗試重新整理主體的時間戳記。若尚未重新整理過，可以是 null。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1bc-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="4c1bc-128">nextTry</span></span></p></td>
<td><p><span data-ttu-id="4c1bc-129">datetime</span><span class="sxs-lookup"><span data-stu-id="4c1bc-129">datetime</span></span></p></td>
<td><p><span data-ttu-id="4c1bc-p102">排定下次重新整理時間戳記。若未排定之後的重新整理，可以是 null。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="4c1bc-132">索引鍵</span><span class="sxs-lookup"><span data-stu-id="4c1bc-132">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c1bc-133">欄</span><span class="sxs-lookup"><span data-stu-id="4c1bc-133">Column</span></span></th>
<th><span data-ttu-id="4c1bc-134">描述</span><span class="sxs-lookup"><span data-stu-id="4c1bc-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c1bc-135">prinID</span><span class="sxs-lookup"><span data-stu-id="4c1bc-135">prinID</span></span></p></td>
<td><p><span data-ttu-id="4c1bc-136">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-136">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1bc-137">prinID</span><span class="sxs-lookup"><span data-stu-id="4c1bc-137">prinID</span></span></p></td>
<td><p><span data-ttu-id="4c1bc-138">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

