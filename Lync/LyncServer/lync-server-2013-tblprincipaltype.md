---
title: Lync Server 2013： tblPrincipalType
description: Lync Server 2013： tblPrincipalType。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba0f607d4499b54b16d7ecf8a4e7de603e874788
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549859"
---
# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="5bc62-103">Lync Server 2013 中的 tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="5bc62-103">tblPrincipalType in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5bc62-104">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5bc62-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5bc62-105">tblPrincipalType 含有主要類型以分類 tblPrincipal 表格中的項目。</span><span class="sxs-lookup"><span data-stu-id="5bc62-105">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="5bc62-106">Columns</span><span class="sxs-lookup"><span data-stu-id="5bc62-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5bc62-107">欄</span><span class="sxs-lookup"><span data-stu-id="5bc62-107">Column</span></span></th>
<th><span data-ttu-id="5bc62-108">類型</span><span class="sxs-lookup"><span data-stu-id="5bc62-108">Type</span></span></th>
<th><span data-ttu-id="5bc62-109">描述</span><span class="sxs-lookup"><span data-stu-id="5bc62-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5bc62-110">ptypeID</span><span class="sxs-lookup"><span data-stu-id="5bc62-110">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="5bc62-111">smallint，非 null</span><span class="sxs-lookup"><span data-stu-id="5bc62-111">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="5bc62-112">主體類型識別碼。</span><span class="sxs-lookup"><span data-stu-id="5bc62-112">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bc62-113">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="5bc62-113">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="5bc62-114">nvarchar (256)，非 null</span><span class="sxs-lookup"><span data-stu-id="5bc62-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="5bc62-115">類型的描述。</span><span class="sxs-lookup"><span data-stu-id="5bc62-115">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bc62-116">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="5bc62-116">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="5bc62-117">bit，非 null</span><span class="sxs-lookup"><span data-stu-id="5bc62-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="5bc62-118">如果類型對應至作為內部用途的主體，則為 True。</span><span class="sxs-lookup"><span data-stu-id="5bc62-118">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bc62-119">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="5bc62-119">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="5bc62-120">bit，非 null</span><span class="sxs-lookup"><span data-stu-id="5bc62-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="5bc62-121">如果類型為使用者類型，則為 True。</span><span class="sxs-lookup"><span data-stu-id="5bc62-121">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="5bc62-122">索引鍵</span><span class="sxs-lookup"><span data-stu-id="5bc62-122">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5bc62-123">欄</span><span class="sxs-lookup"><span data-stu-id="5bc62-123">Column</span></span></th>
<th><span data-ttu-id="5bc62-124">描述</span><span class="sxs-lookup"><span data-stu-id="5bc62-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5bc62-125">ptypeID</span><span class="sxs-lookup"><span data-stu-id="5bc62-125">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="5bc62-126">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="5bc62-126">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="5bc62-127">主體值</span><span class="sxs-lookup"><span data-stu-id="5bc62-127">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5bc62-128">ID</span><span class="sxs-lookup"><span data-stu-id="5bc62-128">ID</span></span></th>
<th><span data-ttu-id="5bc62-129">角色</span><span class="sxs-lookup"><span data-stu-id="5bc62-129">Role</span></span></th>
<th><span data-ttu-id="5bc62-130">描述</span><span class="sxs-lookup"><span data-stu-id="5bc62-130">Description</span></span></th>
<th><span data-ttu-id="5bc62-131">使用者</span><span class="sxs-lookup"><span data-stu-id="5bc62-131">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5bc62-132">1 </span><span class="sxs-lookup"><span data-stu-id="5bc62-132">1</span></span></p></td>
<td><p><span data-ttu-id="5bc62-133">任何</span><span class="sxs-lookup"><span data-stu-id="5bc62-133">Any</span></span></p></td>
<td><p><span data-ttu-id="5bc62-p101">不含已知類型的一般主體。不使用在 tblPrincipal 表格中。</span><span class="sxs-lookup"><span data-stu-id="5bc62-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bc62-136">第</span><span class="sxs-lookup"><span data-stu-id="5bc62-136">2</span></span></p></td>
<td><p><span data-ttu-id="5bc62-137">AnyUser</span><span class="sxs-lookup"><span data-stu-id="5bc62-137">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="5bc62-p102">使用者類型的一般主體。不使用在 tblPrincipal 表格中。</span><span class="sxs-lookup"><span data-stu-id="5bc62-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="5bc62-140">是</span><span class="sxs-lookup"><span data-stu-id="5bc62-140">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bc62-141">個</span><span class="sxs-lookup"><span data-stu-id="5bc62-141">3</span></span></p></td>
<td><p><span data-ttu-id="5bc62-142">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="5bc62-142">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="5bc62-p103">含群組語意的一般主體。不使用在 tblPrincipal 表格中。</span><span class="sxs-lookup"><span data-stu-id="5bc62-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bc62-145">4 </span><span class="sxs-lookup"><span data-stu-id="5bc62-145">4</span></span></p></td>
<td><p><span data-ttu-id="5bc62-146">SystemUser</span><span class="sxs-lookup"><span data-stu-id="5bc62-146">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="5bc62-147">Persistent Chat Server 內部使用的主體。</span><span class="sxs-lookup"><span data-stu-id="5bc62-147">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bc62-148">5 </span><span class="sxs-lookup"><span data-stu-id="5bc62-148">5</span></span></p></td>
<td><p><span data-ttu-id="5bc62-149">使用者</span><span class="sxs-lookup"><span data-stu-id="5bc62-149">User</span></span></p></td>
<td><p><span data-ttu-id="5bc62-150">一般使用者。</span><span class="sxs-lookup"><span data-stu-id="5bc62-150">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="5bc62-151">是</span><span class="sxs-lookup"><span data-stu-id="5bc62-151">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bc62-152">8 </span><span class="sxs-lookup"><span data-stu-id="5bc62-152">8</span></span></p></td>
<td><p><span data-ttu-id="5bc62-153">直流</span><span class="sxs-lookup"><span data-stu-id="5bc62-153">DC</span></span></p></td>
<td><p><span data-ttu-id="5bc62-154">Active Directory 網域服務網域控制站。</span><span class="sxs-lookup"><span data-stu-id="5bc62-154">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bc62-155">9 </span><span class="sxs-lookup"><span data-stu-id="5bc62-155">9</span></span></p></td>
<td><p><span data-ttu-id="5bc62-156">群組</span><span class="sxs-lookup"><span data-stu-id="5bc62-156">Group</span></span></p></td>
<td><p><span data-ttu-id="5bc62-157">Active Directory 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="5bc62-157">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bc62-158">10 </span><span class="sxs-lookup"><span data-stu-id="5bc62-158">10</span></span></p></td>
<td><p><span data-ttu-id="5bc62-159">資料夾</span><span class="sxs-lookup"><span data-stu-id="5bc62-159">Folder</span></span></p></td>
<td><p><span data-ttu-id="5bc62-160">Active Directory 容器或組織單位。</span><span class="sxs-lookup"><span data-stu-id="5bc62-160">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="5bc62-161">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5bc62-161">See Also</span></span>


[<span data-ttu-id="5bc62-162">Lync Server 2013 中的 tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="5bc62-162">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

