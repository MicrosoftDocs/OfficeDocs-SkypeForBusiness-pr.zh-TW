---
title: Lync Server 2013：tblPrincipalType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 725d097e1e2e75b6430974a4f133cb5fa4130346
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="2f40a-102">Lync Server 2013 中的 tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="2f40a-102">tblPrincipalType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f40a-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="2f40a-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="2f40a-104">tblPrincipalType 包含主要類型來分類 tblPrincipal 資料表中的內容。</span><span class="sxs-lookup"><span data-stu-id="2f40a-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="2f40a-105">分欄</span><span class="sxs-lookup"><span data-stu-id="2f40a-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f40a-106">左欄</span><span class="sxs-lookup"><span data-stu-id="2f40a-106">Column</span></span></th>
<th><span data-ttu-id="2f40a-107">類型</span><span class="sxs-lookup"><span data-stu-id="2f40a-107">Type</span></span></th>
<th><span data-ttu-id="2f40a-108">描述</span><span class="sxs-lookup"><span data-stu-id="2f40a-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f40a-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="2f40a-109">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="2f40a-110">Smallint，not null</span><span class="sxs-lookup"><span data-stu-id="2f40a-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="2f40a-111">主體類型 ID。</span><span class="sxs-lookup"><span data-stu-id="2f40a-111">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f40a-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="2f40a-112">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="2f40a-113">Nvarchar （256），not null</span><span class="sxs-lookup"><span data-stu-id="2f40a-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="2f40a-114">類型的描述。</span><span class="sxs-lookup"><span data-stu-id="2f40a-114">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f40a-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="2f40a-115">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="2f40a-116">bit、not null</span><span class="sxs-lookup"><span data-stu-id="2f40a-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="2f40a-117">如果該類型對應到用於內部用途的主體，則為 True。</span><span class="sxs-lookup"><span data-stu-id="2f40a-117">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f40a-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="2f40a-118">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="2f40a-119">bit、not null</span><span class="sxs-lookup"><span data-stu-id="2f40a-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="2f40a-120">如果該類型是使用者類型，則為 True。</span><span class="sxs-lookup"><span data-stu-id="2f40a-120">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="2f40a-121">機碼</span><span class="sxs-lookup"><span data-stu-id="2f40a-121">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f40a-122">左欄</span><span class="sxs-lookup"><span data-stu-id="2f40a-122">Column</span></span></th>
<th><span data-ttu-id="2f40a-123">描述</span><span class="sxs-lookup"><span data-stu-id="2f40a-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f40a-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="2f40a-124">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="2f40a-125">主鍵。</span><span class="sxs-lookup"><span data-stu-id="2f40a-125">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="2f40a-126">主要值</span><span class="sxs-lookup"><span data-stu-id="2f40a-126">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f40a-127">標識號</span><span class="sxs-lookup"><span data-stu-id="2f40a-127">ID</span></span></th>
<th><span data-ttu-id="2f40a-128">角色</span><span class="sxs-lookup"><span data-stu-id="2f40a-128">Role</span></span></th>
<th><span data-ttu-id="2f40a-129">描述</span><span class="sxs-lookup"><span data-stu-id="2f40a-129">Description</span></span></th>
<th><span data-ttu-id="2f40a-130">使用者</span><span class="sxs-lookup"><span data-stu-id="2f40a-130">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f40a-131">1</span><span class="sxs-lookup"><span data-stu-id="2f40a-131">1</span></span></p></td>
<td><p><span data-ttu-id="2f40a-132">每</span><span class="sxs-lookup"><span data-stu-id="2f40a-132">Any</span></span></p></td>
<td><p><span data-ttu-id="2f40a-133">沒有已知類型的一般原則。</span><span class="sxs-lookup"><span data-stu-id="2f40a-133">Generic principal with no known type.</span></span> <span data-ttu-id="2f40a-134">在 tblPrincipal 表格中未使用。</span><span class="sxs-lookup"><span data-stu-id="2f40a-134">Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f40a-135">pplx-2</span><span class="sxs-lookup"><span data-stu-id="2f40a-135">2</span></span></p></td>
<td><p><span data-ttu-id="2f40a-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="2f40a-136">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="2f40a-137">使用者類型的一般主體。</span><span class="sxs-lookup"><span data-stu-id="2f40a-137">Generic principal of user type.</span></span> <span data-ttu-id="2f40a-138">在 tblPrincipal 表格中未使用。</span><span class="sxs-lookup"><span data-stu-id="2f40a-138">Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="2f40a-139">是</span><span class="sxs-lookup"><span data-stu-id="2f40a-139">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f40a-140">3</span><span class="sxs-lookup"><span data-stu-id="2f40a-140">3</span></span></p></td>
<td><p><span data-ttu-id="2f40a-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="2f40a-141">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="2f40a-142">含有群組語義的一般主體。</span><span class="sxs-lookup"><span data-stu-id="2f40a-142">Generic principal with group semantic.</span></span> <span data-ttu-id="2f40a-143">在 tblPrincipal 表格中未使用。</span><span class="sxs-lookup"><span data-stu-id="2f40a-143">Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f40a-144">4</span><span class="sxs-lookup"><span data-stu-id="2f40a-144">4</span></span></p></td>
<td><p><span data-ttu-id="2f40a-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="2f40a-145">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="2f40a-146">永久聊天伺服器在內部使用的主要原則。</span><span class="sxs-lookup"><span data-stu-id="2f40a-146">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f40a-147">500</span><span class="sxs-lookup"><span data-stu-id="2f40a-147">5</span></span></p></td>
<td><p><span data-ttu-id="2f40a-148">使用者</span><span class="sxs-lookup"><span data-stu-id="2f40a-148">User</span></span></p></td>
<td><p><span data-ttu-id="2f40a-149">一般使用者。</span><span class="sxs-lookup"><span data-stu-id="2f40a-149">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="2f40a-150">是</span><span class="sxs-lookup"><span data-stu-id="2f40a-150">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f40a-151">型</span><span class="sxs-lookup"><span data-stu-id="2f40a-151">8</span></span></p></td>
<td><p><span data-ttu-id="2f40a-152">DC</span><span class="sxs-lookup"><span data-stu-id="2f40a-152">DC</span></span></p></td>
<td><p><span data-ttu-id="2f40a-153">Active Directory 網域服務網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="2f40a-153">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f40a-154">9</span><span class="sxs-lookup"><span data-stu-id="2f40a-154">9</span></span></p></td>
<td><p><span data-ttu-id="2f40a-155">群組</span><span class="sxs-lookup"><span data-stu-id="2f40a-155">Group</span></span></p></td>
<td><p><span data-ttu-id="2f40a-156">Active Directory 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="2f40a-156">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f40a-157">第</span><span class="sxs-lookup"><span data-stu-id="2f40a-157">10</span></span></p></td>
<td><p><span data-ttu-id="2f40a-158">資料夾</span><span class="sxs-lookup"><span data-stu-id="2f40a-158">Folder</span></span></p></td>
<td><p><span data-ttu-id="2f40a-159">Active Directory 容器或組織單位。</span><span class="sxs-lookup"><span data-stu-id="2f40a-159">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="2f40a-160">請參閱</span><span class="sxs-lookup"><span data-stu-id="2f40a-160">See Also</span></span>


[<span data-ttu-id="2f40a-161">Lync Server 2013 中的 tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="2f40a-161">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

