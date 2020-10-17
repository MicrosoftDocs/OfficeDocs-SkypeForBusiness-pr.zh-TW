---
title: Lync Server 2013： Grant-CsOUPermission 所做的變更
description: Lync Server 2013： Grant-CsOUPermission 所做的變更。
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
ms.openlocfilehash: 10d3db0e9dde380628690bc016e2b4bd2ec85b54
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543609"
---
# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="09b1b-103">Lync Server 2013 中 Grant-CsOUPermission 所做的變更</span><span class="sxs-lookup"><span data-stu-id="09b1b-103">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09b1b-104">_**主題上次修改日期：** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="09b1b-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="09b1b-105">若要委派 Lync Server 2013 管理，您可以將許可權新增至指定的組織單位 (Ou) ，以便樹系準備所建立的 RTC 通用群組成員可以存取 Ou，而不是 Domain Admins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="09b1b-105">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="09b1b-106">**Grant-CsOuPermission** Cmdlet 會依照下表所指定的方式，將許可權授與指定之 OU 中的物件。</span><span class="sxs-lookup"><span data-stu-id="09b1b-106">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="09b1b-107">授與使用者物件的許可權</span><span class="sxs-lookup"><span data-stu-id="09b1b-107">Granting Permission for User Objects</span></span>

<span data-ttu-id="09b1b-108">當您為 OU 上的使用者物件執行 **Grant-CsOuPermission** Cmdlet 時，會將許可權授與下表所示的許可權。</span><span class="sxs-lookup"><span data-stu-id="09b1b-108">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="09b1b-109">使用者物件的授與許可權</span><span class="sxs-lookup"><span data-stu-id="09b1b-109">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09b1b-110">群組</span><span class="sxs-lookup"><span data-stu-id="09b1b-110">Group</span></span></th>
<th><span data-ttu-id="09b1b-111">權限</span><span class="sxs-lookup"><span data-stu-id="09b1b-111">Permission</span></span></th>
<th><span data-ttu-id="09b1b-112">適用於</span><span class="sxs-lookup"><span data-stu-id="09b1b-112">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09b1b-113">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="09b1b-113">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="09b1b-114">複製目錄變更</span><span class="sxs-lookup"><span data-stu-id="09b1b-114">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="09b1b-115">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="09b1b-115">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09b1b-116">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="09b1b-116">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="09b1b-117">清單內容</span><span class="sxs-lookup"><span data-stu-id="09b1b-117">List contents</span></span></p>
<p><span data-ttu-id="09b1b-118">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="09b1b-118">Read all properties</span></span></p>
<p><span data-ttu-id="09b1b-119">讀取權限</span><span class="sxs-lookup"><span data-stu-id="09b1b-119">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="09b1b-120">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="09b1b-120">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09b1b-121">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="09b1b-121">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="09b1b-122">清單內容</span><span class="sxs-lookup"><span data-stu-id="09b1b-122">List contents</span></span></p>
<p><span data-ttu-id="09b1b-123">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="09b1b-123">Read all properties</span></span></p>
<p><span data-ttu-id="09b1b-124">讀取權限</span><span class="sxs-lookup"><span data-stu-id="09b1b-124">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="09b1b-125">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="09b1b-125">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09b1b-126">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="09b1b-126">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="09b1b-127">讀取 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="09b1b-127">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="09b1b-128">讀取 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="09b1b-128">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="09b1b-129">讀取 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="09b1b-129">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="09b1b-130">讀取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="09b1b-130">Read Public-Information</span></span></p>
<p><span data-ttu-id="09b1b-131">讀取 General-Information</span><span class="sxs-lookup"><span data-stu-id="09b1b-131">Read General-Information</span></span></p>
<p><span data-ttu-id="09b1b-132">讀取 User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="09b1b-132">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="09b1b-133">子代使用者物件</span><span class="sxs-lookup"><span data-stu-id="09b1b-133">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09b1b-134">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="09b1b-134">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="09b1b-135">寫入 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="09b1b-135">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="09b1b-136">寫入 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="09b1b-136">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="09b1b-137">寫入 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="09b1b-137">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="09b1b-138">寫入 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="09b1b-138">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="09b1b-139">寫入 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="09b1b-139">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="09b1b-140">子代使用者物件</span><span class="sxs-lookup"><span data-stu-id="09b1b-140">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="09b1b-141">授與電腦物件的許可權</span><span class="sxs-lookup"><span data-stu-id="09b1b-141">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="09b1b-142">當您為 OU 上的電腦物件執行 **Grant-CsOuPermission** Cmdlet 時，系統會將群組授與下表所示的許可權。</span><span class="sxs-lookup"><span data-stu-id="09b1b-142">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="09b1b-143">電腦物件的授與許可權</span><span class="sxs-lookup"><span data-stu-id="09b1b-143">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09b1b-144">群組</span><span class="sxs-lookup"><span data-stu-id="09b1b-144">Group</span></span></th>
<th><span data-ttu-id="09b1b-145">權限</span><span class="sxs-lookup"><span data-stu-id="09b1b-145">Permission</span></span></th>
<th><span data-ttu-id="09b1b-146">適用於</span><span class="sxs-lookup"><span data-stu-id="09b1b-146">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09b1b-147">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="09b1b-147">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="09b1b-148">複製目錄變更</span><span class="sxs-lookup"><span data-stu-id="09b1b-148">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="09b1b-149">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="09b1b-149">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09b1b-150">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="09b1b-150">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="09b1b-151">清單內容</span><span class="sxs-lookup"><span data-stu-id="09b1b-151">List contents</span></span></p>
<p><span data-ttu-id="09b1b-152">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="09b1b-152">Read all properties</span></span></p>
<p><span data-ttu-id="09b1b-153">讀取權限</span><span class="sxs-lookup"><span data-stu-id="09b1b-153">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="09b1b-154">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="09b1b-154">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09b1b-155">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="09b1b-155">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="09b1b-156">清單內容</span><span class="sxs-lookup"><span data-stu-id="09b1b-156">List contents</span></span></p>
<p><span data-ttu-id="09b1b-157">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="09b1b-157">Read all properties</span></span></p>
<p><span data-ttu-id="09b1b-158">讀取權限</span><span class="sxs-lookup"><span data-stu-id="09b1b-158">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="09b1b-159">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="09b1b-159">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09b1b-160">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="09b1b-160">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="09b1b-161">讀取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="09b1b-161">Read Public-Information</span></span></p>
<p><span data-ttu-id="09b1b-162">讀取 Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="09b1b-162">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="09b1b-163">子代電腦物件</span><span class="sxs-lookup"><span data-stu-id="09b1b-163">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09b1b-164">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="09b1b-164">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="09b1b-165">讀取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="09b1b-165">Read Public-Information</span></span></p>
<p><span data-ttu-id="09b1b-166">讀取 Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="09b1b-166">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="09b1b-167">子代電腦物件</span><span class="sxs-lookup"><span data-stu-id="09b1b-167">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="09b1b-168">授與連絡人或 AppContact 物件的許可權</span><span class="sxs-lookup"><span data-stu-id="09b1b-168">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="09b1b-169">當您對 OU 上的連絡人物件或 AppContact 物件執行 **Grant-CsOuPermission** Cmdlet 時，會授與下表所示的許可權。</span><span class="sxs-lookup"><span data-stu-id="09b1b-169">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="09b1b-170">授與連絡人或 AppContact 物件的許可權</span><span class="sxs-lookup"><span data-stu-id="09b1b-170">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09b1b-171">群組</span><span class="sxs-lookup"><span data-stu-id="09b1b-171">Group</span></span></th>
<th><span data-ttu-id="09b1b-172">權限</span><span class="sxs-lookup"><span data-stu-id="09b1b-172">Permission</span></span></th>
<th><span data-ttu-id="09b1b-173">適用於</span><span class="sxs-lookup"><span data-stu-id="09b1b-173">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09b1b-174">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="09b1b-174">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="09b1b-175">複製目錄變更</span><span class="sxs-lookup"><span data-stu-id="09b1b-175">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="09b1b-176">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="09b1b-176">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09b1b-177">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="09b1b-177">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="09b1b-178">清單內容</span><span class="sxs-lookup"><span data-stu-id="09b1b-178">List contents</span></span></p>
<p><span data-ttu-id="09b1b-179">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="09b1b-179">Read all properties</span></span></p>
<p><span data-ttu-id="09b1b-180">讀取權限</span><span class="sxs-lookup"><span data-stu-id="09b1b-180">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="09b1b-181">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="09b1b-181">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09b1b-182">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="09b1b-182">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="09b1b-183">清單內容</span><span class="sxs-lookup"><span data-stu-id="09b1b-183">List contents</span></span></p>
<p><span data-ttu-id="09b1b-184">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="09b1b-184">Read all properties</span></span></p>
<p><span data-ttu-id="09b1b-185">讀取權限</span><span class="sxs-lookup"><span data-stu-id="09b1b-185">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="09b1b-186">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="09b1b-186">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09b1b-187">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="09b1b-187">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="09b1b-188">讀取 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="09b1b-188">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="09b1b-189">讀取 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="09b1b-189">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="09b1b-190">讀取 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="09b1b-190">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="09b1b-191">讀取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="09b1b-191">Read Public-Information</span></span></p>
<p><span data-ttu-id="09b1b-192">讀取 General-Information</span><span class="sxs-lookup"><span data-stu-id="09b1b-192">Read General-Information</span></span></p>
<p><span data-ttu-id="09b1b-193">讀取 Personal-Information</span><span class="sxs-lookup"><span data-stu-id="09b1b-193">Read Personal-Information</span></span></p>
<p><span data-ttu-id="09b1b-194">讀取 User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="09b1b-194">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="09b1b-195">子代連絡人物件</span><span class="sxs-lookup"><span data-stu-id="09b1b-195">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09b1b-196">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="09b1b-196">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="09b1b-197">寫入 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="09b1b-197">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="09b1b-198">寫入 otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="09b1b-198">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="09b1b-199">寫入 displayName</span><span class="sxs-lookup"><span data-stu-id="09b1b-199">Write displayName</span></span></p>
<p><span data-ttu-id="09b1b-200">寫入描述</span><span class="sxs-lookup"><span data-stu-id="09b1b-200">Write description</span></span></p>
<p><span data-ttu-id="09b1b-201">寫入 telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="09b1b-201">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="09b1b-202">寫入 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="09b1b-202">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="09b1b-203">寫入 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="09b1b-203">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="09b1b-204">寫入 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="09b1b-204">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="09b1b-205">寫入 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="09b1b-205">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="09b1b-206">子代連絡人物件</span><span class="sxs-lookup"><span data-stu-id="09b1b-206">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="09b1b-207">授與裝置物件的許可權</span><span class="sxs-lookup"><span data-stu-id="09b1b-207">Granting Permission for Device Objects</span></span>

<span data-ttu-id="09b1b-208">當您為 OU 上的裝置物件執行 **Grant-CsOuPermission** Cmdlet 時，會將許可權授與下表所示的許可權。</span><span class="sxs-lookup"><span data-stu-id="09b1b-208">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="09b1b-209">對 Device 物件授與的許可權</span><span class="sxs-lookup"><span data-stu-id="09b1b-209">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09b1b-210">群組</span><span class="sxs-lookup"><span data-stu-id="09b1b-210">Group</span></span></th>
<th><span data-ttu-id="09b1b-211">權限</span><span class="sxs-lookup"><span data-stu-id="09b1b-211">Permission</span></span></th>
<th><span data-ttu-id="09b1b-212">適用於</span><span class="sxs-lookup"><span data-stu-id="09b1b-212">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09b1b-213">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="09b1b-213">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="09b1b-214">複製目錄變更</span><span class="sxs-lookup"><span data-stu-id="09b1b-214">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="09b1b-215">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="09b1b-215">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09b1b-216">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="09b1b-216">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="09b1b-217">清單內容</span><span class="sxs-lookup"><span data-stu-id="09b1b-217">List contents</span></span></p>
<p><span data-ttu-id="09b1b-218">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="09b1b-218">Read all properties</span></span></p>
<p><span data-ttu-id="09b1b-219">讀取權限</span><span class="sxs-lookup"><span data-stu-id="09b1b-219">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="09b1b-220">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="09b1b-220">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09b1b-221">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="09b1b-221">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="09b1b-222">清單內容</span><span class="sxs-lookup"><span data-stu-id="09b1b-222">List contents</span></span></p>
<p><span data-ttu-id="09b1b-223">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="09b1b-223">Read all properties</span></span></p>
<p><span data-ttu-id="09b1b-224">讀取權限</span><span class="sxs-lookup"><span data-stu-id="09b1b-224">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="09b1b-225">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="09b1b-225">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09b1b-226">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="09b1b-226">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="09b1b-227">讀取 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="09b1b-227">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="09b1b-228">讀取 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="09b1b-228">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="09b1b-229">讀取 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="09b1b-229">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="09b1b-230">讀取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="09b1b-230">Read Public-Information</span></span></p>
<p><span data-ttu-id="09b1b-231">讀取 Personal-Information</span><span class="sxs-lookup"><span data-stu-id="09b1b-231">Read Personal-Information</span></span></p>
<p><span data-ttu-id="09b1b-232">讀取 General-Information</span><span class="sxs-lookup"><span data-stu-id="09b1b-232">Read General-Information</span></span></p>
<p><span data-ttu-id="09b1b-233">讀取 User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="09b1b-233">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="09b1b-234">子代連絡人物件</span><span class="sxs-lookup"><span data-stu-id="09b1b-234">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09b1b-235">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="09b1b-235">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="09b1b-236">建立子項</span><span class="sxs-lookup"><span data-stu-id="09b1b-236">Create child</span></span></p>
<p><span data-ttu-id="09b1b-237">刪除子項</span><span class="sxs-lookup"><span data-stu-id="09b1b-237">Delete child</span></span></p>
<p><span data-ttu-id="09b1b-238">刪除樹</span><span class="sxs-lookup"><span data-stu-id="09b1b-238">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="09b1b-239">連絡人</span><span class="sxs-lookup"><span data-stu-id="09b1b-239">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09b1b-240">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="09b1b-240">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="09b1b-241">寫入 displayName</span><span class="sxs-lookup"><span data-stu-id="09b1b-241">Write displayName</span></span></p>
<p><span data-ttu-id="09b1b-242">寫入描述</span><span class="sxs-lookup"><span data-stu-id="09b1b-242">Write description</span></span></p>
<p><span data-ttu-id="09b1b-243">寫入 telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="09b1b-243">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="09b1b-244">子代使用者物件</span><span class="sxs-lookup"><span data-stu-id="09b1b-244">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09b1b-245">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="09b1b-245">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="09b1b-246">寫入 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="09b1b-246">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="09b1b-247">寫入 otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="09b1b-247">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="09b1b-248">寫入 displayName</span><span class="sxs-lookup"><span data-stu-id="09b1b-248">Write displayName</span></span></p>
<p><span data-ttu-id="09b1b-249">寫入描述</span><span class="sxs-lookup"><span data-stu-id="09b1b-249">Write description</span></span></p>
<p><span data-ttu-id="09b1b-250">寫入 telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="09b1b-250">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="09b1b-251">寫入 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="09b1b-251">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="09b1b-252">寫入 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="09b1b-252">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="09b1b-253">寫入 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="09b1b-253">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="09b1b-254">寫入 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="09b1b-254">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="09b1b-255">子代連絡人物件</span><span class="sxs-lookup"><span data-stu-id="09b1b-255">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="09b1b-256">授與 InetOrgPerson 物件的許可權</span><span class="sxs-lookup"><span data-stu-id="09b1b-256">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="09b1b-257">當您為 OU 上的 InetOrgPerson 物件執行 **Grant-CsOuPermission** Cmdlet 時，會將許可權授與下表所示的許可權。</span><span class="sxs-lookup"><span data-stu-id="09b1b-257">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="09b1b-258">InetOrgPerson 物件的授與許可權</span><span class="sxs-lookup"><span data-stu-id="09b1b-258">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09b1b-259">群組</span><span class="sxs-lookup"><span data-stu-id="09b1b-259">Group</span></span></th>
<th><span data-ttu-id="09b1b-260">權限</span><span class="sxs-lookup"><span data-stu-id="09b1b-260">Permission</span></span></th>
<th><span data-ttu-id="09b1b-261">適用於</span><span class="sxs-lookup"><span data-stu-id="09b1b-261">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09b1b-262">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="09b1b-262">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="09b1b-263">複製目錄變更</span><span class="sxs-lookup"><span data-stu-id="09b1b-263">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="09b1b-264">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="09b1b-264">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09b1b-265">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="09b1b-265">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="09b1b-266">清單內容</span><span class="sxs-lookup"><span data-stu-id="09b1b-266">List contents</span></span></p>
<p><span data-ttu-id="09b1b-267">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="09b1b-267">Read all properties</span></span></p>
<p><span data-ttu-id="09b1b-268">讀取權限</span><span class="sxs-lookup"><span data-stu-id="09b1b-268">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="09b1b-269">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="09b1b-269">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09b1b-270">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="09b1b-270">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="09b1b-271">清單內容</span><span class="sxs-lookup"><span data-stu-id="09b1b-271">List contents</span></span></p>
<p><span data-ttu-id="09b1b-272">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="09b1b-272">Read all properties</span></span></p>
<p><span data-ttu-id="09b1b-273">讀取權限</span><span class="sxs-lookup"><span data-stu-id="09b1b-273">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="09b1b-274">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="09b1b-274">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09b1b-275">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="09b1b-275">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="09b1b-276">讀取 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="09b1b-276">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="09b1b-277">讀取 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="09b1b-277">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="09b1b-278">讀取 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="09b1b-278">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="09b1b-279">讀取 Personal-Information</span><span class="sxs-lookup"><span data-stu-id="09b1b-279">Read Personal-Information</span></span></p>
<p><span data-ttu-id="09b1b-280">讀取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="09b1b-280">Read Public-Information</span></span></p>
<p><span data-ttu-id="09b1b-281">讀取 General-Information</span><span class="sxs-lookup"><span data-stu-id="09b1b-281">Read General-Information</span></span></p>
<p><span data-ttu-id="09b1b-282">讀取 User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="09b1b-282">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="09b1b-283">子代 inetOrgPerson 物件</span><span class="sxs-lookup"><span data-stu-id="09b1b-283">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09b1b-284">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="09b1b-284">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="09b1b-285">寫入 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="09b1b-285">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="09b1b-286">寫入 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="09b1b-286">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="09b1b-287">寫入 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="09b1b-287">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="09b1b-288">寫入 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="09b1b-288">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="09b1b-289">子代 inetOrgPerson 物件</span><span class="sxs-lookup"><span data-stu-id="09b1b-289">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

