---
title: Lync Server 2013：tblPrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48184571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c24f963b34ef6184675e724496d7d45ca1d40d27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="54803-102">Lync Server 2013 中的 tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="54803-102">tblPrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54803-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="54803-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="54803-104">tblPrincipal 包含所有的承擔者，包括使用者、資料夾和群組。</span><span class="sxs-lookup"><span data-stu-id="54803-104">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="54803-105">分欄</span><span class="sxs-lookup"><span data-stu-id="54803-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54803-106">左欄</span><span class="sxs-lookup"><span data-stu-id="54803-106">Column</span></span></th>
<th><span data-ttu-id="54803-107">類型</span><span class="sxs-lookup"><span data-stu-id="54803-107">Type</span></span></th>
<th><span data-ttu-id="54803-108">描述</span><span class="sxs-lookup"><span data-stu-id="54803-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54803-109">prinID</span><span class="sxs-lookup"><span data-stu-id="54803-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="54803-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="54803-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="54803-111">Principal ID。</span><span class="sxs-lookup"><span data-stu-id="54803-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54803-112">prinGuid</span><span class="sxs-lookup"><span data-stu-id="54803-112">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="54803-113">GUID，不是 null</span><span class="sxs-lookup"><span data-stu-id="54803-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="54803-114">主要 GUID。</span><span class="sxs-lookup"><span data-stu-id="54803-114">Principal GUID.</span></span> <span data-ttu-id="54803-115">這會被廣泛用做為備用主鍵，因為它的意義是要與 Active Directory 網域服務空間相交。</span><span class="sxs-lookup"><span data-stu-id="54803-115">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="54803-116">（快取的主體的 GUID 等於對應的 Active Directory 物件 GUID。）</span><span class="sxs-lookup"><span data-stu-id="54803-116">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54803-117">prinUri</span><span class="sxs-lookup"><span data-stu-id="54803-117">prinUri</span></span></p></td>
<td><p><span data-ttu-id="54803-118">Nvarchar （256），not null</span><span class="sxs-lookup"><span data-stu-id="54803-118">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="54803-119">主體 URI。</span><span class="sxs-lookup"><span data-stu-id="54803-119">Principal URI.</span></span> <span data-ttu-id="54803-120">SIP 配置適用于使用者，而 ma grp 則用於幾乎所有其他專案。</span><span class="sxs-lookup"><span data-stu-id="54803-120">The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54803-121">prinName</span><span class="sxs-lookup"><span data-stu-id="54803-121">prinName</span></span></p></td>
<td><p><span data-ttu-id="54803-122">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="54803-122">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="54803-123">通用名稱。</span><span class="sxs-lookup"><span data-stu-id="54803-123">Common name.</span></span> <span data-ttu-id="54803-124">僅供使用者類型使用。</span><span class="sxs-lookup"><span data-stu-id="54803-124">Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54803-125">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="54803-125">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="54803-126">NVarchar （256）</span><span class="sxs-lookup"><span data-stu-id="54803-126">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="54803-127">顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="54803-127">Display name.</span></span> <span data-ttu-id="54803-128">僅供使用者類型使用。</span><span class="sxs-lookup"><span data-stu-id="54803-128">Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54803-129">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="54803-129">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="54803-130">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="54803-130">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="54803-131">[公司名稱]。</span><span class="sxs-lookup"><span data-stu-id="54803-131">Company name.</span></span> <span data-ttu-id="54803-132">僅供使用者類型使用。</span><span class="sxs-lookup"><span data-stu-id="54803-132">Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54803-133">prinEmail</span><span class="sxs-lookup"><span data-stu-id="54803-133">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="54803-134">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="54803-134">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="54803-135">電子郵件。</span><span class="sxs-lookup"><span data-stu-id="54803-135">Email.</span></span> <span data-ttu-id="54803-136">僅供使用者類型使用。</span><span class="sxs-lookup"><span data-stu-id="54803-136">Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54803-137">prinADPath</span><span class="sxs-lookup"><span data-stu-id="54803-137">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="54803-138">Nvarchar （384）</span><span class="sxs-lookup"><span data-stu-id="54803-138">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="54803-139">Principal 是其快取版本之 Active Directory 物件的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="54803-139">Domain name of the Active Directory object that the principal is a cached version of.</span></span> <span data-ttu-id="54803-140">對於非 Active Directory 物件（例如系統使用者）的類型，可以是 Null。</span><span class="sxs-lookup"><span data-stu-id="54803-140">Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54803-141">prinADUserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="54803-141">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="54803-142">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="54803-142">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="54803-143">使用者的使用者主體名稱（UPN）。</span><span class="sxs-lookup"><span data-stu-id="54803-143">User’s user principal name (UPN).</span></span> <span data-ttu-id="54803-144">只能由一般的使用者類型使用。</span><span class="sxs-lookup"><span data-stu-id="54803-144">Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54803-145">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="54803-145">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="54803-146">Smallint，not null</span><span class="sxs-lookup"><span data-stu-id="54803-146">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="54803-147">0：主體處於作用中狀態。</span><span class="sxs-lookup"><span data-stu-id="54803-147">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="54803-148">1：主體已停用，因為使用者的 SIP 功能已停用。</span><span class="sxs-lookup"><span data-stu-id="54803-148">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="54803-149">2：由於相關聯的 AD 物件已遭刪除，主體會被刪除。</span><span class="sxs-lookup"><span data-stu-id="54803-149">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54803-150">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="54803-150">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="54803-151">Smallint，not null</span><span class="sxs-lookup"><span data-stu-id="54803-151">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="54803-152">主體類型（從 tblPrincipalType 資料表）。</span><span class="sxs-lookup"><span data-stu-id="54803-152">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54803-153">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="54803-153">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="54803-154">Int</span><span class="sxs-lookup"><span data-stu-id="54803-154">Int</span></span></p></td>
<td><p><span data-ttu-id="54803-155">主體的 Lync pool 分派。</span><span class="sxs-lookup"><span data-stu-id="54803-155">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54803-156">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="54803-156">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="54803-157">Int</span><span class="sxs-lookup"><span data-stu-id="54803-157">Int</span></span></p></td>
<td><p><span data-ttu-id="54803-158">使用者的持續聊天伺服器原則值（如果有標籤類型原則的話）。</span><span class="sxs-lookup"><span data-stu-id="54803-158">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54803-159">prinAddedBy</span><span class="sxs-lookup"><span data-stu-id="54803-159">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="54803-160">int</span><span class="sxs-lookup"><span data-stu-id="54803-160">int</span></span></p></td>
<td><p><span data-ttu-id="54803-161">建立者的主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="54803-161">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54803-162">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="54803-162">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="54803-163">Bigint，not null</span><span class="sxs-lookup"><span data-stu-id="54803-163">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="54803-164">建立時間的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="54803-164">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54803-165">prinUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="54803-165">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="54803-166">int</span><span class="sxs-lookup"><span data-stu-id="54803-166">int</span></span></p></td>
<td><p><span data-ttu-id="54803-167">上次更新此原則的主要使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="54803-167">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54803-168">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="54803-168">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="54803-169">Bigint，not null</span><span class="sxs-lookup"><span data-stu-id="54803-169">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="54803-170">上次更新的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="54803-170">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54803-171">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="54803-171">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="54803-172">datetime、not null</span><span class="sxs-lookup"><span data-stu-id="54803-172">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="54803-173">主體上次 Active Directory 同步處理的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="54803-173">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="54803-174">鍵</span><span class="sxs-lookup"><span data-stu-id="54803-174">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54803-175">左欄</span><span class="sxs-lookup"><span data-stu-id="54803-175">Column</span></span></th>
<th><span data-ttu-id="54803-176">描述</span><span class="sxs-lookup"><span data-stu-id="54803-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54803-177">prinID</span><span class="sxs-lookup"><span data-stu-id="54803-177">prinID</span></span></p></td>
<td><p><span data-ttu-id="54803-178">主鍵。</span><span class="sxs-lookup"><span data-stu-id="54803-178">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54803-179">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="54803-179">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="54803-180">在 tblPrincipalType ptypeID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="54803-180">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

