---
title: 'Lync Server 2013: tblPrincipal'
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
ms.openlocfilehash: b9d5122b375b4906320f254179ce101652ad6db2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="16eb5-102">Lync Server 2013 中的 tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="16eb5-102">tblPrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16eb5-103">_**主題上次修改日期：** 2012年-09-12_</span><span class="sxs-lookup"><span data-stu-id="16eb5-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="16eb5-104">tblPrincipal 包含所有主體，包括使用者、資料夾及群組。</span><span class="sxs-lookup"><span data-stu-id="16eb5-104">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="16eb5-105">Columns</span><span class="sxs-lookup"><span data-stu-id="16eb5-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16eb5-106">欄</span><span class="sxs-lookup"><span data-stu-id="16eb5-106">Column</span></span></th>
<th><span data-ttu-id="16eb5-107">類型	</span><span class="sxs-lookup"><span data-stu-id="16eb5-107">Type</span></span></th>
<th><span data-ttu-id="16eb5-108">描述</span><span class="sxs-lookup"><span data-stu-id="16eb5-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16eb5-109">prinID</span><span class="sxs-lookup"><span data-stu-id="16eb5-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="16eb5-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="16eb5-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="16eb5-111">主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="16eb5-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16eb5-112">prinGuid</span><span class="sxs-lookup"><span data-stu-id="16eb5-112">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="16eb5-113">GUID，非 null</span><span class="sxs-lookup"><span data-stu-id="16eb5-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="16eb5-114">主體 GUID。</span><span class="sxs-lookup"><span data-stu-id="16eb5-114">Principal GUID.</span></span> <span data-ttu-id="16eb5-115">這是廣泛用來作為替代的主索引鍵因為其意義透過跨越到 Active Directory 網域服務空間。</span><span class="sxs-lookup"><span data-stu-id="16eb5-115">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="16eb5-116">（如快取的主體 GUID 是等於相對應的 Active Directory 物件的 GUID）。</span><span class="sxs-lookup"><span data-stu-id="16eb5-116">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16eb5-117">prinUri</span><span class="sxs-lookup"><span data-stu-id="16eb5-117">prinUri</span></span></p></td>
<td><p><span data-ttu-id="16eb5-118">nvarchar (256)，非 null</span><span class="sxs-lookup"><span data-stu-id="16eb5-118">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="16eb5-p102">主體 URI。SIP 配置可用於使用者，而 ma-grp 幾乎可用於其他所有項目。</span><span class="sxs-lookup"><span data-stu-id="16eb5-p102">Principal URI. The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16eb5-121">prinName</span><span class="sxs-lookup"><span data-stu-id="16eb5-121">prinName</span></span></p></td>
<td><p><span data-ttu-id="16eb5-122">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="16eb5-122">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="16eb5-p103">一般名稱。僅可用於使用者類型。</span><span class="sxs-lookup"><span data-stu-id="16eb5-p103">Common name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16eb5-125">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="16eb5-125">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="16eb5-126">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="16eb5-126">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="16eb5-p104">顯示名稱。僅可用於使用者類型。</span><span class="sxs-lookup"><span data-stu-id="16eb5-p104">Display name. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16eb5-129">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="16eb5-129">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="16eb5-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="16eb5-130">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="16eb5-p105">公司名稱。僅可用於使用者類型。</span><span class="sxs-lookup"><span data-stu-id="16eb5-p105">Company name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16eb5-133">prinEmail</span><span class="sxs-lookup"><span data-stu-id="16eb5-133">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="16eb5-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="16eb5-134">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="16eb5-p106">電子郵件。僅可用於使用者類型。</span><span class="sxs-lookup"><span data-stu-id="16eb5-p106">Email. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16eb5-137">prinADPath</span><span class="sxs-lookup"><span data-stu-id="16eb5-137">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="16eb5-138">nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="16eb5-138">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="16eb5-p107">Active Directory 物件 (主體為快取版本) 的網域名稱。非 Active Directory 物件的類型可以是 Null (例如系統使用者)。</span><span class="sxs-lookup"><span data-stu-id="16eb5-p107">Domain name of the Active Directory object that the principal is a cached version of. Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16eb5-141">prinADUserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="16eb5-141">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="16eb5-142">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="16eb5-142">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="16eb5-p108">使用者的使用者主體名稱 (UPN)。僅可用於一般使用者類型。</span><span class="sxs-lookup"><span data-stu-id="16eb5-p108">User’s user principal name (UPN). Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16eb5-145">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="16eb5-145">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="16eb5-146">smallint，非 null</span><span class="sxs-lookup"><span data-stu-id="16eb5-146">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="16eb5-147">0：主體為作用中狀態。</span><span class="sxs-lookup"><span data-stu-id="16eb5-147">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="16eb5-148">1：主體已停用，因為使用者的 SIP 功能已停用。</span><span class="sxs-lookup"><span data-stu-id="16eb5-148">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="16eb5-149">2：主體已刪除，因為相關聯的 AD 物件已刪除。</span><span class="sxs-lookup"><span data-stu-id="16eb5-149">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16eb5-150">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="16eb5-150">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="16eb5-151">smallint，非 null</span><span class="sxs-lookup"><span data-stu-id="16eb5-151">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="16eb5-152">主體類型 (參照 tblPrincipalType 表格)。</span><span class="sxs-lookup"><span data-stu-id="16eb5-152">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16eb5-153">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="16eb5-153">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="16eb5-154">臨界值</span><span class="sxs-lookup"><span data-stu-id="16eb5-154">Int</span></span></p></td>
<td><p><span data-ttu-id="16eb5-155">主體的 Lync 集區指派。</span><span class="sxs-lookup"><span data-stu-id="16eb5-155">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16eb5-156">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="16eb5-156">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="16eb5-157">臨界值</span><span class="sxs-lookup"><span data-stu-id="16eb5-157">Int</span></span></p></td>
<td><p><span data-ttu-id="16eb5-158">對於使用者來說，如果出現標記類型原則的常設聊天室伺服器原則值。</span><span class="sxs-lookup"><span data-stu-id="16eb5-158">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16eb5-159">prinAddedBy</span><span class="sxs-lookup"><span data-stu-id="16eb5-159">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="16eb5-160">int</span><span class="sxs-lookup"><span data-stu-id="16eb5-160">int</span></span></p></td>
<td><p><span data-ttu-id="16eb5-161">建立者的主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="16eb5-161">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16eb5-162">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="16eb5-162">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="16eb5-163">bigint，非 null</span><span class="sxs-lookup"><span data-stu-id="16eb5-163">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="16eb5-164">建立時間的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="16eb5-164">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16eb5-165">prinUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="16eb5-165">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="16eb5-166">int</span><span class="sxs-lookup"><span data-stu-id="16eb5-166">int</span></span></p></td>
<td><p><span data-ttu-id="16eb5-167">最近一次進行更新之主體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="16eb5-167">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16eb5-168">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="16eb5-168">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="16eb5-169">bigint，非 null</span><span class="sxs-lookup"><span data-stu-id="16eb5-169">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="16eb5-170">最近一次更新的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="16eb5-170">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16eb5-171">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="16eb5-171">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="16eb5-172">datetime，非 null</span><span class="sxs-lookup"><span data-stu-id="16eb5-172">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="16eb5-173">最近一次主體之 Active Directory Sync 重新整理的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="16eb5-173">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="16eb5-174">索引鍵</span><span class="sxs-lookup"><span data-stu-id="16eb5-174">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16eb5-175">欄</span><span class="sxs-lookup"><span data-stu-id="16eb5-175">Column</span></span></th>
<th><span data-ttu-id="16eb5-176">描述</span><span class="sxs-lookup"><span data-stu-id="16eb5-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16eb5-177">prinID</span><span class="sxs-lookup"><span data-stu-id="16eb5-177">prinID</span></span></p></td>
<td><p><span data-ttu-id="16eb5-178">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="16eb5-178">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16eb5-179">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="16eb5-179">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="16eb5-180">在 tblPrincipalType.ptypeID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="16eb5-180">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

