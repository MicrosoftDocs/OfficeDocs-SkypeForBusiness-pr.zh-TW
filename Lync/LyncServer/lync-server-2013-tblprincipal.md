---
title: Lync Server 2013： tblPrincipal
description: Lync Server 2013： tblPrincipal。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48184571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f07b37ac4c8ceed5c044b5c263eeee6370adfdc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547489"
---
# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="df71b-103">Lync Server 2013 中的 tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="df71b-103">tblPrincipal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df71b-104">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="df71b-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="df71b-105">tblPrincipal 包含所有主體，包括使用者、資料夾及群組。</span><span class="sxs-lookup"><span data-stu-id="df71b-105">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="df71b-106">Columns</span><span class="sxs-lookup"><span data-stu-id="df71b-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="df71b-107">欄</span><span class="sxs-lookup"><span data-stu-id="df71b-107">Column</span></span></th>
<th><span data-ttu-id="df71b-108">類型</span><span class="sxs-lookup"><span data-stu-id="df71b-108">Type</span></span></th>
<th><span data-ttu-id="df71b-109">描述</span><span class="sxs-lookup"><span data-stu-id="df71b-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="df71b-110">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="df71b-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="df71b-111">int，非 null</span><span class="sxs-lookup"><span data-stu-id="df71b-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="df71b-112">主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="df71b-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df71b-113">prinGuid</span><span class="sxs-lookup"><span data-stu-id="df71b-113">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="df71b-114">GUID，非 null</span><span class="sxs-lookup"><span data-stu-id="df71b-114">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="df71b-115">主體 GUID。</span><span class="sxs-lookup"><span data-stu-id="df71b-115">Principal GUID.</span></span> <span data-ttu-id="df71b-116">因為它的意義會跨越 Active Directory 網域服務空間，所以這會被廣泛當作替代主鍵使用。</span><span class="sxs-lookup"><span data-stu-id="df71b-116">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="df71b-117"> (快取主體的 GUID 等於對應的 Active Directory 物件 GUID。 ) </span><span class="sxs-lookup"><span data-stu-id="df71b-117">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df71b-118">prinUri</span><span class="sxs-lookup"><span data-stu-id="df71b-118">prinUri</span></span></p></td>
<td><p><span data-ttu-id="df71b-119">nvarchar (256)，非 null</span><span class="sxs-lookup"><span data-stu-id="df71b-119">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="df71b-p102">主體 URI。SIP 配置可用於使用者，而 ma-grp 幾乎可用於其他所有項目。</span><span class="sxs-lookup"><span data-stu-id="df71b-p102">Principal URI. The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df71b-122">prinName</span><span class="sxs-lookup"><span data-stu-id="df71b-122">prinName</span></span></p></td>
<td><p><span data-ttu-id="df71b-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="df71b-123">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="df71b-p103">一般名稱。僅可用於使用者類型。</span><span class="sxs-lookup"><span data-stu-id="df71b-p103">Common name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df71b-126">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="df71b-126">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="df71b-127">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="df71b-127">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="df71b-p104">顯示名稱。僅可用於使用者類型。</span><span class="sxs-lookup"><span data-stu-id="df71b-p104">Display name. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df71b-130">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="df71b-130">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="df71b-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="df71b-131">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="df71b-p105">公司名稱。僅可用於使用者類型。</span><span class="sxs-lookup"><span data-stu-id="df71b-p105">Company name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df71b-134">prinEmail</span><span class="sxs-lookup"><span data-stu-id="df71b-134">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="df71b-135">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="df71b-135">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="df71b-p106">電子郵件。僅可用於使用者類型。</span><span class="sxs-lookup"><span data-stu-id="df71b-p106">Email. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df71b-138">prinADPath</span><span class="sxs-lookup"><span data-stu-id="df71b-138">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="df71b-139">nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="df71b-139">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="df71b-p107">Active Directory 物件 (主體為快取版本) 的網域名稱。非 Active Directory 物件的類型可以是 Null (例如系統使用者)。</span><span class="sxs-lookup"><span data-stu-id="df71b-p107">Domain name of the Active Directory object that the principal is a cached version of. Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df71b-142">prinADUserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="df71b-142">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="df71b-143">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="df71b-143">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="df71b-p108">使用者的使用者主體名稱 (UPN)。僅可用於一般使用者類型。</span><span class="sxs-lookup"><span data-stu-id="df71b-p108">User’s user principal name (UPN). Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df71b-146">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="df71b-146">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="df71b-147">smallint，非 null</span><span class="sxs-lookup"><span data-stu-id="df71b-147">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="df71b-148">0：主體為作用中狀態。</span><span class="sxs-lookup"><span data-stu-id="df71b-148">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="df71b-149">1：主體已停用，因為使用者的 SIP 功能已停用。</span><span class="sxs-lookup"><span data-stu-id="df71b-149">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="df71b-150">2：主體已刪除，因為相關聯的 AD 物件已刪除。</span><span class="sxs-lookup"><span data-stu-id="df71b-150">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df71b-151">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="df71b-151">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="df71b-152">smallint，非 null</span><span class="sxs-lookup"><span data-stu-id="df71b-152">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="df71b-153">主體類型 (參照 tblPrincipalType 表格)。</span><span class="sxs-lookup"><span data-stu-id="df71b-153">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df71b-154">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="df71b-154">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="df71b-155">臨界值</span><span class="sxs-lookup"><span data-stu-id="df71b-155">Int</span></span></p></td>
<td><p><span data-ttu-id="df71b-156">主體的 Lync 集區指派。</span><span class="sxs-lookup"><span data-stu-id="df71b-156">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df71b-157">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="df71b-157">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="df71b-158">臨界值</span><span class="sxs-lookup"><span data-stu-id="df71b-158">Int</span></span></p></td>
<td><p><span data-ttu-id="df71b-159">如果存在標記類型原則，則為 user 的 Persistent Chat Server policy value。</span><span class="sxs-lookup"><span data-stu-id="df71b-159">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df71b-160">prinAddedBy</span><span class="sxs-lookup"><span data-stu-id="df71b-160">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="df71b-161">int</span><span class="sxs-lookup"><span data-stu-id="df71b-161">int</span></span></p></td>
<td><p><span data-ttu-id="df71b-162">建立者的主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="df71b-162">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df71b-163">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="df71b-163">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="df71b-164">bigint，非 null</span><span class="sxs-lookup"><span data-stu-id="df71b-164">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="df71b-165">建立時間的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="df71b-165">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df71b-166">prinUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="df71b-166">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="df71b-167">int</span><span class="sxs-lookup"><span data-stu-id="df71b-167">int</span></span></p></td>
<td><p><span data-ttu-id="df71b-168">最近一次進行更新之主體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="df71b-168">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df71b-169">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="df71b-169">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="df71b-170">bigint，非 null</span><span class="sxs-lookup"><span data-stu-id="df71b-170">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="df71b-171">最近一次更新的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="df71b-171">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df71b-172">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="df71b-172">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="df71b-173">datetime，非 null</span><span class="sxs-lookup"><span data-stu-id="df71b-173">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="df71b-174">最近一次主體之 Active Directory Sync 重新整理的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="df71b-174">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="df71b-175">索引鍵</span><span class="sxs-lookup"><span data-stu-id="df71b-175">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="df71b-176">欄</span><span class="sxs-lookup"><span data-stu-id="df71b-176">Column</span></span></th>
<th><span data-ttu-id="df71b-177">描述</span><span class="sxs-lookup"><span data-stu-id="df71b-177">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="df71b-178">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="df71b-178">prinID</span></span></p></td>
<td><p><span data-ttu-id="df71b-179">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="df71b-179">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df71b-180">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="df71b-180">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="df71b-181">在 tblPrincipalType.ptypeID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="df71b-181">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

