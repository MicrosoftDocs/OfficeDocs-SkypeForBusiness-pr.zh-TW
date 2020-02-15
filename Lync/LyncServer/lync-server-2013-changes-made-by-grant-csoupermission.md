---
title: 'Lync Server 2013: Grant-csoupermission 所做的變更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfad0cf4b8b863cd19d4d4113241477de1a50aaf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043925"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="7618d-102">Grant-csoupermission Lync Server 2013 中所做的變更</span><span class="sxs-lookup"><span data-stu-id="7618d-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7618d-103">_**主題上次修改日期：** 2012年-06-20 個_</span><span class="sxs-lookup"><span data-stu-id="7618d-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="7618d-104">若要委派 Lync Server 2013 管理，您可以指定組織單位 (Ou) 來新增權限，使樹系準備所建立的 RTC 萬用群組的成員能夠存取 Ou 不需要以 Domain Admins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="7618d-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="7618d-105">**Grant-csoupermission** cmdlet 授與權限給所指定的下列表格中所指定 OU 中的物件。</span><span class="sxs-lookup"><span data-stu-id="7618d-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="7618d-106">授與使用者物件的權限</span><span class="sxs-lookup"><span data-stu-id="7618d-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="7618d-107">當您針對 OU 執行**Grant-csoupermission** cmdlet 的使用者物件時，群組會授與權限，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="7618d-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="7618d-108">使用者物件的授與的權限</span><span class="sxs-lookup"><span data-stu-id="7618d-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7618d-109">Group</span><span class="sxs-lookup"><span data-stu-id="7618d-109">Group</span></span></th>
<th><span data-ttu-id="7618d-110">權限</span><span class="sxs-lookup"><span data-stu-id="7618d-110">Permission</span></span></th>
<th><span data-ttu-id="7618d-111">適用於</span><span class="sxs-lookup"><span data-stu-id="7618d-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7618d-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="7618d-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="7618d-113">「 複寫目錄變更</span><span class="sxs-lookup"><span data-stu-id="7618d-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="7618d-114">只有此物件</span><span class="sxs-lookup"><span data-stu-id="7618d-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7618d-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7618d-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7618d-116">列出內容</span><span class="sxs-lookup"><span data-stu-id="7618d-116">List contents</span></span></p>
<p><span data-ttu-id="7618d-117">讀取所有內容</span><span class="sxs-lookup"><span data-stu-id="7618d-117">Read all properties</span></span></p>
<p><span data-ttu-id="7618d-118">讀取權限</span><span class="sxs-lookup"><span data-stu-id="7618d-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="7618d-119">只有此物件</span><span class="sxs-lookup"><span data-stu-id="7618d-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7618d-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7618d-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7618d-121">列出內容</span><span class="sxs-lookup"><span data-stu-id="7618d-121">List contents</span></span></p>
<p><span data-ttu-id="7618d-122">讀取所有內容</span><span class="sxs-lookup"><span data-stu-id="7618d-122">Read all properties</span></span></p>
<p><span data-ttu-id="7618d-123">讀取權限</span><span class="sxs-lookup"><span data-stu-id="7618d-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="7618d-124">只有此物件</span><span class="sxs-lookup"><span data-stu-id="7618d-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7618d-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7618d-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7618d-126">讀取 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="7618d-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="7618d-127">讀取 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="7618d-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="7618d-128">讀取 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="7618d-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="7618d-129">讀取 Public-information</span><span class="sxs-lookup"><span data-stu-id="7618d-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="7618d-130">讀取 General-information</span><span class="sxs-lookup"><span data-stu-id="7618d-130">Read General-Information</span></span></p>
<p><span data-ttu-id="7618d-131">讀取使用者帳戶限制</span><span class="sxs-lookup"><span data-stu-id="7618d-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="7618d-132">子系 User 物件</span><span class="sxs-lookup"><span data-stu-id="7618d-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7618d-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="7618d-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="7618d-134">寫入 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="7618d-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="7618d-135">寫入 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="7618d-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="7618d-136">寫入 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="7618d-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="7618d-137">寫入 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="7618d-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="7618d-138">寫入 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="7618d-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="7618d-139">子系 User 物件</span><span class="sxs-lookup"><span data-stu-id="7618d-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="7618d-140">授與 Computer 物件的權限</span><span class="sxs-lookup"><span data-stu-id="7618d-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="7618d-141">當您針對 OU 執行**Grant-csoupermission** cmdlet 的電腦物件時，群組會授與權限，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="7618d-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="7618d-142">電腦物件的授與的權限</span><span class="sxs-lookup"><span data-stu-id="7618d-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7618d-143">Group</span><span class="sxs-lookup"><span data-stu-id="7618d-143">Group</span></span></th>
<th><span data-ttu-id="7618d-144">權限</span><span class="sxs-lookup"><span data-stu-id="7618d-144">Permission</span></span></th>
<th><span data-ttu-id="7618d-145">適用於</span><span class="sxs-lookup"><span data-stu-id="7618d-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7618d-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="7618d-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="7618d-147">「 複寫目錄變更</span><span class="sxs-lookup"><span data-stu-id="7618d-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="7618d-148">只有此物件</span><span class="sxs-lookup"><span data-stu-id="7618d-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7618d-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7618d-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7618d-150">列出內容</span><span class="sxs-lookup"><span data-stu-id="7618d-150">List contents</span></span></p>
<p><span data-ttu-id="7618d-151">讀取所有內容</span><span class="sxs-lookup"><span data-stu-id="7618d-151">Read all properties</span></span></p>
<p><span data-ttu-id="7618d-152">讀取權限</span><span class="sxs-lookup"><span data-stu-id="7618d-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="7618d-153">只有此物件</span><span class="sxs-lookup"><span data-stu-id="7618d-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7618d-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7618d-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7618d-155">列出內容</span><span class="sxs-lookup"><span data-stu-id="7618d-155">List contents</span></span></p>
<p><span data-ttu-id="7618d-156">讀取所有內容</span><span class="sxs-lookup"><span data-stu-id="7618d-156">Read all properties</span></span></p>
<p><span data-ttu-id="7618d-157">讀取權限</span><span class="sxs-lookup"><span data-stu-id="7618d-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="7618d-158">只有此物件</span><span class="sxs-lookup"><span data-stu-id="7618d-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7618d-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7618d-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7618d-160">讀取 Public-information</span><span class="sxs-lookup"><span data-stu-id="7618d-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="7618d-161">讀取驗證型 DNS 主機的名稱</span><span class="sxs-lookup"><span data-stu-id="7618d-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="7618d-162">子系 Computer 物件</span><span class="sxs-lookup"><span data-stu-id="7618d-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7618d-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="7618d-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="7618d-164">讀取 Public-information</span><span class="sxs-lookup"><span data-stu-id="7618d-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="7618d-165">讀取驗證型 DNS 主機的名稱</span><span class="sxs-lookup"><span data-stu-id="7618d-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="7618d-166">子系 Computer 物件</span><span class="sxs-lookup"><span data-stu-id="7618d-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="7618d-167">授與 Contact 或 AppContact 物件的權限</span><span class="sxs-lookup"><span data-stu-id="7618d-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="7618d-168">當您針對 OU 執行**Grant-csoupermission** cmdlet 的 Contact 或 AppContact 物件時，會授與群組的權限，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="7618d-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="7618d-169">Contact 或 AppContact 物件的授與的權限</span><span class="sxs-lookup"><span data-stu-id="7618d-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7618d-170">Group</span><span class="sxs-lookup"><span data-stu-id="7618d-170">Group</span></span></th>
<th><span data-ttu-id="7618d-171">權限</span><span class="sxs-lookup"><span data-stu-id="7618d-171">Permission</span></span></th>
<th><span data-ttu-id="7618d-172">適用於</span><span class="sxs-lookup"><span data-stu-id="7618d-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7618d-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="7618d-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="7618d-174">「 複寫目錄變更</span><span class="sxs-lookup"><span data-stu-id="7618d-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="7618d-175">只有此物件</span><span class="sxs-lookup"><span data-stu-id="7618d-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7618d-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7618d-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7618d-177">列出內容</span><span class="sxs-lookup"><span data-stu-id="7618d-177">List contents</span></span></p>
<p><span data-ttu-id="7618d-178">讀取所有內容</span><span class="sxs-lookup"><span data-stu-id="7618d-178">Read all properties</span></span></p>
<p><span data-ttu-id="7618d-179">讀取權限</span><span class="sxs-lookup"><span data-stu-id="7618d-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="7618d-180">只有此物件</span><span class="sxs-lookup"><span data-stu-id="7618d-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7618d-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7618d-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7618d-182">列出內容</span><span class="sxs-lookup"><span data-stu-id="7618d-182">List contents</span></span></p>
<p><span data-ttu-id="7618d-183">讀取所有內容</span><span class="sxs-lookup"><span data-stu-id="7618d-183">Read all properties</span></span></p>
<p><span data-ttu-id="7618d-184">讀取權限</span><span class="sxs-lookup"><span data-stu-id="7618d-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="7618d-185">只有此物件</span><span class="sxs-lookup"><span data-stu-id="7618d-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7618d-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7618d-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7618d-187">讀取 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="7618d-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="7618d-188">讀取 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="7618d-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="7618d-189">讀取 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="7618d-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="7618d-190">讀取 Public-information</span><span class="sxs-lookup"><span data-stu-id="7618d-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="7618d-191">讀取 General-information</span><span class="sxs-lookup"><span data-stu-id="7618d-191">Read General-Information</span></span></p>
<p><span data-ttu-id="7618d-192">讀取 Personal-information</span><span class="sxs-lookup"><span data-stu-id="7618d-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="7618d-193">讀取使用者帳戶限制</span><span class="sxs-lookup"><span data-stu-id="7618d-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="7618d-194">子系 Contact 物件</span><span class="sxs-lookup"><span data-stu-id="7618d-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7618d-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="7618d-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="7618d-196">寫入 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="7618d-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="7618d-197">寫入 otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="7618d-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="7618d-198">寫入 displayName</span><span class="sxs-lookup"><span data-stu-id="7618d-198">Write displayName</span></span></p>
<p><span data-ttu-id="7618d-199">寫入 description</span><span class="sxs-lookup"><span data-stu-id="7618d-199">Write description</span></span></p>
<p><span data-ttu-id="7618d-200">寫入 telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="7618d-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="7618d-201">寫入 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="7618d-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="7618d-202">寫入 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="7618d-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="7618d-203">寫入 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="7618d-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="7618d-204">寫入 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="7618d-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="7618d-205">子系 Contact 物件</span><span class="sxs-lookup"><span data-stu-id="7618d-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="7618d-206">授與 Device 物件的權限</span><span class="sxs-lookup"><span data-stu-id="7618d-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="7618d-207">當您執行**Grant-csoupermission** cmdlet Device 物件的 OU 上時，群組會授與權限，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="7618d-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="7618d-208">裝置物件的授與的權限</span><span class="sxs-lookup"><span data-stu-id="7618d-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7618d-209">Group</span><span class="sxs-lookup"><span data-stu-id="7618d-209">Group</span></span></th>
<th><span data-ttu-id="7618d-210">權限</span><span class="sxs-lookup"><span data-stu-id="7618d-210">Permission</span></span></th>
<th><span data-ttu-id="7618d-211">適用於</span><span class="sxs-lookup"><span data-stu-id="7618d-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7618d-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="7618d-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="7618d-213">「 複寫目錄變更</span><span class="sxs-lookup"><span data-stu-id="7618d-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="7618d-214">只有此物件</span><span class="sxs-lookup"><span data-stu-id="7618d-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7618d-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7618d-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7618d-216">列出內容</span><span class="sxs-lookup"><span data-stu-id="7618d-216">List contents</span></span></p>
<p><span data-ttu-id="7618d-217">讀取所有內容</span><span class="sxs-lookup"><span data-stu-id="7618d-217">Read all properties</span></span></p>
<p><span data-ttu-id="7618d-218">讀取權限</span><span class="sxs-lookup"><span data-stu-id="7618d-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="7618d-219">只有此物件</span><span class="sxs-lookup"><span data-stu-id="7618d-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7618d-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7618d-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7618d-221">列出內容</span><span class="sxs-lookup"><span data-stu-id="7618d-221">List contents</span></span></p>
<p><span data-ttu-id="7618d-222">讀取所有內容</span><span class="sxs-lookup"><span data-stu-id="7618d-222">Read all properties</span></span></p>
<p><span data-ttu-id="7618d-223">讀取權限</span><span class="sxs-lookup"><span data-stu-id="7618d-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="7618d-224">只有此物件</span><span class="sxs-lookup"><span data-stu-id="7618d-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7618d-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7618d-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7618d-226">讀取 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="7618d-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="7618d-227">讀取 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="7618d-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="7618d-228">讀取 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="7618d-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="7618d-229">讀取 Public-information</span><span class="sxs-lookup"><span data-stu-id="7618d-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="7618d-230">讀取 Personal-information</span><span class="sxs-lookup"><span data-stu-id="7618d-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="7618d-231">讀取 General-information</span><span class="sxs-lookup"><span data-stu-id="7618d-231">Read General-Information</span></span></p>
<p><span data-ttu-id="7618d-232">讀取使用者帳戶限制</span><span class="sxs-lookup"><span data-stu-id="7618d-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="7618d-233">子系 Contact 物件</span><span class="sxs-lookup"><span data-stu-id="7618d-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7618d-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="7618d-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="7618d-235">建立子項</span><span class="sxs-lookup"><span data-stu-id="7618d-235">Create child</span></span></p>
<p><span data-ttu-id="7618d-236">刪除子項</span><span class="sxs-lookup"><span data-stu-id="7618d-236">Delete child</span></span></p>
<p><span data-ttu-id="7618d-237">刪除樹狀目錄</span><span class="sxs-lookup"><span data-stu-id="7618d-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="7618d-238">連絡人</span><span class="sxs-lookup"><span data-stu-id="7618d-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7618d-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="7618d-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="7618d-240">寫入 displayName</span><span class="sxs-lookup"><span data-stu-id="7618d-240">Write displayName</span></span></p>
<p><span data-ttu-id="7618d-241">寫入 description</span><span class="sxs-lookup"><span data-stu-id="7618d-241">Write description</span></span></p>
<p><span data-ttu-id="7618d-242">寫入 telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="7618d-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="7618d-243">子系 User 物件</span><span class="sxs-lookup"><span data-stu-id="7618d-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7618d-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="7618d-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="7618d-245">寫入 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="7618d-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="7618d-246">寫入 otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="7618d-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="7618d-247">寫入 displayName</span><span class="sxs-lookup"><span data-stu-id="7618d-247">Write displayName</span></span></p>
<p><span data-ttu-id="7618d-248">寫入 description</span><span class="sxs-lookup"><span data-stu-id="7618d-248">Write description</span></span></p>
<p><span data-ttu-id="7618d-249">寫入 telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="7618d-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="7618d-250">寫入 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="7618d-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="7618d-251">寫入 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="7618d-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="7618d-252">寫入 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="7618d-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="7618d-253">寫入 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="7618d-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="7618d-254">子系 Contact 物件</span><span class="sxs-lookup"><span data-stu-id="7618d-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="7618d-255">授與 InetOrgPerson 物件的權限</span><span class="sxs-lookup"><span data-stu-id="7618d-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="7618d-256">當您執行**Grant-csoupermission** cmdlet InetOrgPerson 物件的 OU 上時，群組會授與權限，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="7618d-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="7618d-257">InetOrgPerson 物件的授與的權限</span><span class="sxs-lookup"><span data-stu-id="7618d-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7618d-258">Group</span><span class="sxs-lookup"><span data-stu-id="7618d-258">Group</span></span></th>
<th><span data-ttu-id="7618d-259">權限</span><span class="sxs-lookup"><span data-stu-id="7618d-259">Permission</span></span></th>
<th><span data-ttu-id="7618d-260">適用於</span><span class="sxs-lookup"><span data-stu-id="7618d-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7618d-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="7618d-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="7618d-262">「 複寫目錄變更</span><span class="sxs-lookup"><span data-stu-id="7618d-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="7618d-263">只有此物件</span><span class="sxs-lookup"><span data-stu-id="7618d-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7618d-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7618d-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7618d-265">列出內容</span><span class="sxs-lookup"><span data-stu-id="7618d-265">List contents</span></span></p>
<p><span data-ttu-id="7618d-266">讀取所有內容</span><span class="sxs-lookup"><span data-stu-id="7618d-266">Read all properties</span></span></p>
<p><span data-ttu-id="7618d-267">讀取權限</span><span class="sxs-lookup"><span data-stu-id="7618d-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="7618d-268">只有此物件</span><span class="sxs-lookup"><span data-stu-id="7618d-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7618d-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7618d-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7618d-270">列出內容</span><span class="sxs-lookup"><span data-stu-id="7618d-270">List contents</span></span></p>
<p><span data-ttu-id="7618d-271">讀取所有內容</span><span class="sxs-lookup"><span data-stu-id="7618d-271">Read all properties</span></span></p>
<p><span data-ttu-id="7618d-272">讀取權限</span><span class="sxs-lookup"><span data-stu-id="7618d-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="7618d-273">只有此物件</span><span class="sxs-lookup"><span data-stu-id="7618d-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7618d-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7618d-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="7618d-275">讀取 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="7618d-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="7618d-276">讀取 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="7618d-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="7618d-277">讀取 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="7618d-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="7618d-278">讀取 Personal-information</span><span class="sxs-lookup"><span data-stu-id="7618d-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="7618d-279">讀取 Public-information</span><span class="sxs-lookup"><span data-stu-id="7618d-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="7618d-280">讀取 General-information</span><span class="sxs-lookup"><span data-stu-id="7618d-280">Read General-Information</span></span></p>
<p><span data-ttu-id="7618d-281">讀取使用者帳戶限制</span><span class="sxs-lookup"><span data-stu-id="7618d-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="7618d-282">子系 inetOrgPerson 物件</span><span class="sxs-lookup"><span data-stu-id="7618d-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7618d-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="7618d-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="7618d-284">寫入 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="7618d-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="7618d-285">寫入 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="7618d-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="7618d-286">寫入 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="7618d-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="7618d-287">寫入 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="7618d-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="7618d-288">子系 inetOrgPerson 物件</span><span class="sxs-lookup"><span data-stu-id="7618d-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

