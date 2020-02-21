---
title: 'Lync Server 2013: tblPrincipalType'
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
ms.openlocfilehash: 0de18da521bd4dadc63d5be592009bd60b643e7b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="66c9f-102">Lync Server 2013 中的參照 tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="66c9f-102">tblPrincipalType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66c9f-103">_**主題上次修改日期：** 2012年-09-12_</span><span class="sxs-lookup"><span data-stu-id="66c9f-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="66c9f-104">tblPrincipalType 含有主要類型以分類 tblPrincipal 表格中的項目。</span><span class="sxs-lookup"><span data-stu-id="66c9f-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="66c9f-105">Columns</span><span class="sxs-lookup"><span data-stu-id="66c9f-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66c9f-106">欄</span><span class="sxs-lookup"><span data-stu-id="66c9f-106">Column</span></span></th>
<th><span data-ttu-id="66c9f-107">類型	</span><span class="sxs-lookup"><span data-stu-id="66c9f-107">Type</span></span></th>
<th><span data-ttu-id="66c9f-108">描述</span><span class="sxs-lookup"><span data-stu-id="66c9f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66c9f-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="66c9f-109">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="66c9f-110">smallint，非 null</span><span class="sxs-lookup"><span data-stu-id="66c9f-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="66c9f-111">主體類型識別碼。</span><span class="sxs-lookup"><span data-stu-id="66c9f-111">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66c9f-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="66c9f-112">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="66c9f-113">nvarchar (256)，非 null</span><span class="sxs-lookup"><span data-stu-id="66c9f-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="66c9f-114">類型的描述。</span><span class="sxs-lookup"><span data-stu-id="66c9f-114">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66c9f-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="66c9f-115">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="66c9f-116">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="66c9f-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="66c9f-117">如果類型對應至作為內部用途的主體，則為 True。</span><span class="sxs-lookup"><span data-stu-id="66c9f-117">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66c9f-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="66c9f-118">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="66c9f-119">bit，非 null</span><span class="sxs-lookup"><span data-stu-id="66c9f-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="66c9f-120">如果類型為使用者類型，則為 True。</span><span class="sxs-lookup"><span data-stu-id="66c9f-120">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="66c9f-121">索引鍵</span><span class="sxs-lookup"><span data-stu-id="66c9f-121">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66c9f-122">欄</span><span class="sxs-lookup"><span data-stu-id="66c9f-122">Column</span></span></th>
<th><span data-ttu-id="66c9f-123">描述</span><span class="sxs-lookup"><span data-stu-id="66c9f-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66c9f-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="66c9f-124">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="66c9f-125">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="66c9f-125">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="66c9f-126">主體值</span><span class="sxs-lookup"><span data-stu-id="66c9f-126">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66c9f-127">ID</span><span class="sxs-lookup"><span data-stu-id="66c9f-127">ID</span></span></th>
<th><span data-ttu-id="66c9f-128">角色</span><span class="sxs-lookup"><span data-stu-id="66c9f-128">Role</span></span></th>
<th><span data-ttu-id="66c9f-129">描述</span><span class="sxs-lookup"><span data-stu-id="66c9f-129">Description</span></span></th>
<th><span data-ttu-id="66c9f-130">使用者</span><span class="sxs-lookup"><span data-stu-id="66c9f-130">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66c9f-131">1</span><span class="sxs-lookup"><span data-stu-id="66c9f-131">1</span></span></p></td>
<td><p><span data-ttu-id="66c9f-132">任何</span><span class="sxs-lookup"><span data-stu-id="66c9f-132">Any</span></span></p></td>
<td><p><span data-ttu-id="66c9f-p101">不含已知類型的一般主體。不使用在 tblPrincipal 表格中。</span><span class="sxs-lookup"><span data-stu-id="66c9f-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66c9f-135">2</span><span class="sxs-lookup"><span data-stu-id="66c9f-135">2</span></span></p></td>
<td><p><span data-ttu-id="66c9f-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="66c9f-136">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="66c9f-p102">使用者類型的一般主體。不使用在 tblPrincipal 表格中。</span><span class="sxs-lookup"><span data-stu-id="66c9f-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="66c9f-139">是</span><span class="sxs-lookup"><span data-stu-id="66c9f-139">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66c9f-140">3</span><span class="sxs-lookup"><span data-stu-id="66c9f-140">3</span></span></p></td>
<td><p><span data-ttu-id="66c9f-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="66c9f-141">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="66c9f-p103">含群組語意的一般主體。不使用在 tblPrincipal 表格中。</span><span class="sxs-lookup"><span data-stu-id="66c9f-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66c9f-144">4</span><span class="sxs-lookup"><span data-stu-id="66c9f-144">4</span></span></p></td>
<td><p><span data-ttu-id="66c9f-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="66c9f-145">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="66c9f-146">Persistent Chat Server 在內部使用的主體。</span><span class="sxs-lookup"><span data-stu-id="66c9f-146">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66c9f-147">5</span><span class="sxs-lookup"><span data-stu-id="66c9f-147">5</span></span></p></td>
<td><p><span data-ttu-id="66c9f-148">使用者</span><span class="sxs-lookup"><span data-stu-id="66c9f-148">User</span></span></p></td>
<td><p><span data-ttu-id="66c9f-149">一般使用者。</span><span class="sxs-lookup"><span data-stu-id="66c9f-149">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="66c9f-150">是</span><span class="sxs-lookup"><span data-stu-id="66c9f-150">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66c9f-151">8 </span><span class="sxs-lookup"><span data-stu-id="66c9f-151">8</span></span></p></td>
<td><p><span data-ttu-id="66c9f-152">DC</span><span class="sxs-lookup"><span data-stu-id="66c9f-152">DC</span></span></p></td>
<td><p><span data-ttu-id="66c9f-153">Active Directory 網域服務的網域控制站。</span><span class="sxs-lookup"><span data-stu-id="66c9f-153">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66c9f-154">9 </span><span class="sxs-lookup"><span data-stu-id="66c9f-154">9</span></span></p></td>
<td><p><span data-ttu-id="66c9f-155">Group</span><span class="sxs-lookup"><span data-stu-id="66c9f-155">Group</span></span></p></td>
<td><p><span data-ttu-id="66c9f-156">Active Directory 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="66c9f-156">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66c9f-157">10 </span><span class="sxs-lookup"><span data-stu-id="66c9f-157">10</span></span></p></td>
<td><p><span data-ttu-id="66c9f-158">資料夾</span><span class="sxs-lookup"><span data-stu-id="66c9f-158">Folder</span></span></p></td>
<td><p><span data-ttu-id="66c9f-159">Active Directory 容器或組織單位。</span><span class="sxs-lookup"><span data-stu-id="66c9f-159">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="66c9f-160">另請參閱</span><span class="sxs-lookup"><span data-stu-id="66c9f-160">See Also</span></span>


[<span data-ttu-id="66c9f-161">Lync Server 2013 中的 tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="66c9f-161">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

