---
title: Lync Server 2013： Grant-CsOUPermission 所做的變更
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
ms.openlocfilehash: 0ff916c0b4e284f9c6ce4d5dbaf9c2e196ed4bc6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529430"
---
# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="635ef-102">Lync Server 2013 中 Grant-CsOUPermission 所做的變更</span><span class="sxs-lookup"><span data-stu-id="635ef-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="635ef-103">_**主題上次修改日期：** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="635ef-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="635ef-104">若要委派 Lync Server 2013 管理，您可以將許可權新增至指定的組織單位 (Ou) ，以便樹系準備所建立的 RTC 通用群組成員可以存取 Ou，而不是 Domain Admins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="635ef-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="635ef-105">**Grant-CsOuPermission** Cmdlet 會依照下表所指定的方式，將許可權授與指定之 OU 中的物件。</span><span class="sxs-lookup"><span data-stu-id="635ef-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="635ef-106">授與使用者物件的許可權</span><span class="sxs-lookup"><span data-stu-id="635ef-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="635ef-107">當您為 OU 上的使用者物件執行 **Grant-CsOuPermission** Cmdlet 時，會將許可權授與下表所示的許可權。</span><span class="sxs-lookup"><span data-stu-id="635ef-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="635ef-108">使用者物件的授與許可權</span><span class="sxs-lookup"><span data-stu-id="635ef-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="635ef-109">群組</span><span class="sxs-lookup"><span data-stu-id="635ef-109">Group</span></span></th>
<th><span data-ttu-id="635ef-110">權限</span><span class="sxs-lookup"><span data-stu-id="635ef-110">Permission</span></span></th>
<th><span data-ttu-id="635ef-111">適用於</span><span class="sxs-lookup"><span data-stu-id="635ef-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="635ef-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="635ef-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="635ef-113">複製目錄變更</span><span class="sxs-lookup"><span data-stu-id="635ef-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="635ef-114">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="635ef-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="635ef-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="635ef-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="635ef-116">清單內容</span><span class="sxs-lookup"><span data-stu-id="635ef-116">List contents</span></span></p>
<p><span data-ttu-id="635ef-117">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="635ef-117">Read all properties</span></span></p>
<p><span data-ttu-id="635ef-118">讀取權限</span><span class="sxs-lookup"><span data-stu-id="635ef-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="635ef-119">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="635ef-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="635ef-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="635ef-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="635ef-121">清單內容</span><span class="sxs-lookup"><span data-stu-id="635ef-121">List contents</span></span></p>
<p><span data-ttu-id="635ef-122">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="635ef-122">Read all properties</span></span></p>
<p><span data-ttu-id="635ef-123">讀取權限</span><span class="sxs-lookup"><span data-stu-id="635ef-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="635ef-124">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="635ef-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="635ef-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="635ef-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="635ef-126">讀取 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="635ef-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="635ef-127">讀取 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="635ef-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="635ef-128">讀取 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="635ef-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="635ef-129">讀取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="635ef-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="635ef-130">讀取 General-Information</span><span class="sxs-lookup"><span data-stu-id="635ef-130">Read General-Information</span></span></p>
<p><span data-ttu-id="635ef-131">讀取 User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="635ef-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="635ef-132">子代使用者物件</span><span class="sxs-lookup"><span data-stu-id="635ef-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="635ef-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="635ef-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="635ef-134">寫入 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="635ef-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="635ef-135">寫入 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="635ef-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="635ef-136">寫入 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="635ef-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="635ef-137">寫入 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="635ef-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="635ef-138">寫入 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="635ef-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="635ef-139">子代使用者物件</span><span class="sxs-lookup"><span data-stu-id="635ef-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="635ef-140">授與電腦物件的許可權</span><span class="sxs-lookup"><span data-stu-id="635ef-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="635ef-141">當您為 OU 上的電腦物件執行 **Grant-CsOuPermission** Cmdlet 時，系統會將群組授與下表所示的許可權。</span><span class="sxs-lookup"><span data-stu-id="635ef-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="635ef-142">電腦物件的授與許可權</span><span class="sxs-lookup"><span data-stu-id="635ef-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="635ef-143">群組</span><span class="sxs-lookup"><span data-stu-id="635ef-143">Group</span></span></th>
<th><span data-ttu-id="635ef-144">權限</span><span class="sxs-lookup"><span data-stu-id="635ef-144">Permission</span></span></th>
<th><span data-ttu-id="635ef-145">適用於</span><span class="sxs-lookup"><span data-stu-id="635ef-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="635ef-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="635ef-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="635ef-147">複製目錄變更</span><span class="sxs-lookup"><span data-stu-id="635ef-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="635ef-148">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="635ef-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="635ef-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="635ef-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="635ef-150">清單內容</span><span class="sxs-lookup"><span data-stu-id="635ef-150">List contents</span></span></p>
<p><span data-ttu-id="635ef-151">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="635ef-151">Read all properties</span></span></p>
<p><span data-ttu-id="635ef-152">讀取權限</span><span class="sxs-lookup"><span data-stu-id="635ef-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="635ef-153">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="635ef-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="635ef-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="635ef-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="635ef-155">清單內容</span><span class="sxs-lookup"><span data-stu-id="635ef-155">List contents</span></span></p>
<p><span data-ttu-id="635ef-156">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="635ef-156">Read all properties</span></span></p>
<p><span data-ttu-id="635ef-157">讀取權限</span><span class="sxs-lookup"><span data-stu-id="635ef-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="635ef-158">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="635ef-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="635ef-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="635ef-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="635ef-160">讀取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="635ef-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="635ef-161">讀取 Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="635ef-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="635ef-162">子代電腦物件</span><span class="sxs-lookup"><span data-stu-id="635ef-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="635ef-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="635ef-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="635ef-164">讀取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="635ef-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="635ef-165">讀取 Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="635ef-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="635ef-166">子代電腦物件</span><span class="sxs-lookup"><span data-stu-id="635ef-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="635ef-167">授與連絡人或 AppContact 物件的許可權</span><span class="sxs-lookup"><span data-stu-id="635ef-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="635ef-168">當您對 OU 上的連絡人物件或 AppContact 物件執行 **Grant-CsOuPermission** Cmdlet 時，會授與下表所示的許可權。</span><span class="sxs-lookup"><span data-stu-id="635ef-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="635ef-169">授與連絡人或 AppContact 物件的許可權</span><span class="sxs-lookup"><span data-stu-id="635ef-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="635ef-170">群組</span><span class="sxs-lookup"><span data-stu-id="635ef-170">Group</span></span></th>
<th><span data-ttu-id="635ef-171">權限</span><span class="sxs-lookup"><span data-stu-id="635ef-171">Permission</span></span></th>
<th><span data-ttu-id="635ef-172">適用於</span><span class="sxs-lookup"><span data-stu-id="635ef-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="635ef-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="635ef-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="635ef-174">複製目錄變更</span><span class="sxs-lookup"><span data-stu-id="635ef-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="635ef-175">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="635ef-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="635ef-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="635ef-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="635ef-177">清單內容</span><span class="sxs-lookup"><span data-stu-id="635ef-177">List contents</span></span></p>
<p><span data-ttu-id="635ef-178">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="635ef-178">Read all properties</span></span></p>
<p><span data-ttu-id="635ef-179">讀取權限</span><span class="sxs-lookup"><span data-stu-id="635ef-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="635ef-180">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="635ef-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="635ef-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="635ef-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="635ef-182">清單內容</span><span class="sxs-lookup"><span data-stu-id="635ef-182">List contents</span></span></p>
<p><span data-ttu-id="635ef-183">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="635ef-183">Read all properties</span></span></p>
<p><span data-ttu-id="635ef-184">讀取權限</span><span class="sxs-lookup"><span data-stu-id="635ef-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="635ef-185">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="635ef-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="635ef-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="635ef-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="635ef-187">讀取 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="635ef-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="635ef-188">讀取 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="635ef-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="635ef-189">讀取 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="635ef-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="635ef-190">讀取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="635ef-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="635ef-191">讀取 General-Information</span><span class="sxs-lookup"><span data-stu-id="635ef-191">Read General-Information</span></span></p>
<p><span data-ttu-id="635ef-192">讀取 Personal-Information</span><span class="sxs-lookup"><span data-stu-id="635ef-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="635ef-193">讀取 User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="635ef-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="635ef-194">子代連絡人物件</span><span class="sxs-lookup"><span data-stu-id="635ef-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="635ef-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="635ef-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="635ef-196">寫入 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="635ef-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="635ef-197">寫入 otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="635ef-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="635ef-198">寫入 displayName</span><span class="sxs-lookup"><span data-stu-id="635ef-198">Write displayName</span></span></p>
<p><span data-ttu-id="635ef-199">寫入描述</span><span class="sxs-lookup"><span data-stu-id="635ef-199">Write description</span></span></p>
<p><span data-ttu-id="635ef-200">寫入 telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="635ef-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="635ef-201">寫入 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="635ef-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="635ef-202">寫入 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="635ef-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="635ef-203">寫入 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="635ef-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="635ef-204">寫入 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="635ef-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="635ef-205">子代連絡人物件</span><span class="sxs-lookup"><span data-stu-id="635ef-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="635ef-206">授與裝置物件的許可權</span><span class="sxs-lookup"><span data-stu-id="635ef-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="635ef-207">當您為 OU 上的裝置物件執行 **Grant-CsOuPermission** Cmdlet 時，會將許可權授與下表所示的許可權。</span><span class="sxs-lookup"><span data-stu-id="635ef-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="635ef-208">對 Device 物件授與的許可權</span><span class="sxs-lookup"><span data-stu-id="635ef-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="635ef-209">群組</span><span class="sxs-lookup"><span data-stu-id="635ef-209">Group</span></span></th>
<th><span data-ttu-id="635ef-210">權限</span><span class="sxs-lookup"><span data-stu-id="635ef-210">Permission</span></span></th>
<th><span data-ttu-id="635ef-211">適用於</span><span class="sxs-lookup"><span data-stu-id="635ef-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="635ef-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="635ef-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="635ef-213">複製目錄變更</span><span class="sxs-lookup"><span data-stu-id="635ef-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="635ef-214">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="635ef-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="635ef-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="635ef-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="635ef-216">清單內容</span><span class="sxs-lookup"><span data-stu-id="635ef-216">List contents</span></span></p>
<p><span data-ttu-id="635ef-217">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="635ef-217">Read all properties</span></span></p>
<p><span data-ttu-id="635ef-218">讀取權限</span><span class="sxs-lookup"><span data-stu-id="635ef-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="635ef-219">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="635ef-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="635ef-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="635ef-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="635ef-221">清單內容</span><span class="sxs-lookup"><span data-stu-id="635ef-221">List contents</span></span></p>
<p><span data-ttu-id="635ef-222">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="635ef-222">Read all properties</span></span></p>
<p><span data-ttu-id="635ef-223">讀取權限</span><span class="sxs-lookup"><span data-stu-id="635ef-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="635ef-224">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="635ef-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="635ef-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="635ef-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="635ef-226">讀取 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="635ef-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="635ef-227">讀取 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="635ef-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="635ef-228">讀取 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="635ef-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="635ef-229">讀取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="635ef-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="635ef-230">讀取 Personal-Information</span><span class="sxs-lookup"><span data-stu-id="635ef-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="635ef-231">讀取 General-Information</span><span class="sxs-lookup"><span data-stu-id="635ef-231">Read General-Information</span></span></p>
<p><span data-ttu-id="635ef-232">讀取 User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="635ef-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="635ef-233">子代連絡人物件</span><span class="sxs-lookup"><span data-stu-id="635ef-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="635ef-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="635ef-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="635ef-235">建立子項</span><span class="sxs-lookup"><span data-stu-id="635ef-235">Create child</span></span></p>
<p><span data-ttu-id="635ef-236">刪除子項</span><span class="sxs-lookup"><span data-stu-id="635ef-236">Delete child</span></span></p>
<p><span data-ttu-id="635ef-237">刪除樹</span><span class="sxs-lookup"><span data-stu-id="635ef-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="635ef-238">連絡人</span><span class="sxs-lookup"><span data-stu-id="635ef-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="635ef-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="635ef-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="635ef-240">寫入 displayName</span><span class="sxs-lookup"><span data-stu-id="635ef-240">Write displayName</span></span></p>
<p><span data-ttu-id="635ef-241">寫入描述</span><span class="sxs-lookup"><span data-stu-id="635ef-241">Write description</span></span></p>
<p><span data-ttu-id="635ef-242">寫入 telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="635ef-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="635ef-243">子代使用者物件</span><span class="sxs-lookup"><span data-stu-id="635ef-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="635ef-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="635ef-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="635ef-245">寫入 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="635ef-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="635ef-246">寫入 otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="635ef-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="635ef-247">寫入 displayName</span><span class="sxs-lookup"><span data-stu-id="635ef-247">Write displayName</span></span></p>
<p><span data-ttu-id="635ef-248">寫入描述</span><span class="sxs-lookup"><span data-stu-id="635ef-248">Write description</span></span></p>
<p><span data-ttu-id="635ef-249">寫入 telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="635ef-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="635ef-250">寫入 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="635ef-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="635ef-251">寫入 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="635ef-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="635ef-252">寫入 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="635ef-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="635ef-253">寫入 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="635ef-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="635ef-254">子代連絡人物件</span><span class="sxs-lookup"><span data-stu-id="635ef-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="635ef-255">授與 InetOrgPerson 物件的許可權</span><span class="sxs-lookup"><span data-stu-id="635ef-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="635ef-256">當您為 OU 上的 InetOrgPerson 物件執行 **Grant-CsOuPermission** Cmdlet 時，會將許可權授與下表所示的許可權。</span><span class="sxs-lookup"><span data-stu-id="635ef-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="635ef-257">InetOrgPerson 物件的授與許可權</span><span class="sxs-lookup"><span data-stu-id="635ef-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="635ef-258">群組</span><span class="sxs-lookup"><span data-stu-id="635ef-258">Group</span></span></th>
<th><span data-ttu-id="635ef-259">權限</span><span class="sxs-lookup"><span data-stu-id="635ef-259">Permission</span></span></th>
<th><span data-ttu-id="635ef-260">適用於</span><span class="sxs-lookup"><span data-stu-id="635ef-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="635ef-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="635ef-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="635ef-262">複製目錄變更</span><span class="sxs-lookup"><span data-stu-id="635ef-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="635ef-263">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="635ef-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="635ef-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="635ef-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="635ef-265">清單內容</span><span class="sxs-lookup"><span data-stu-id="635ef-265">List contents</span></span></p>
<p><span data-ttu-id="635ef-266">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="635ef-266">Read all properties</span></span></p>
<p><span data-ttu-id="635ef-267">讀取權限</span><span class="sxs-lookup"><span data-stu-id="635ef-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="635ef-268">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="635ef-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="635ef-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="635ef-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="635ef-270">清單內容</span><span class="sxs-lookup"><span data-stu-id="635ef-270">List contents</span></span></p>
<p><span data-ttu-id="635ef-271">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="635ef-271">Read all properties</span></span></p>
<p><span data-ttu-id="635ef-272">讀取權限</span><span class="sxs-lookup"><span data-stu-id="635ef-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="635ef-273">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="635ef-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="635ef-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="635ef-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="635ef-275">讀取 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="635ef-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="635ef-276">讀取 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="635ef-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="635ef-277">讀取 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="635ef-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="635ef-278">讀取 Personal-Information</span><span class="sxs-lookup"><span data-stu-id="635ef-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="635ef-279">讀取 Public-Information</span><span class="sxs-lookup"><span data-stu-id="635ef-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="635ef-280">讀取 General-Information</span><span class="sxs-lookup"><span data-stu-id="635ef-280">Read General-Information</span></span></p>
<p><span data-ttu-id="635ef-281">讀取 User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="635ef-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="635ef-282">子代 inetOrgPerson 物件</span><span class="sxs-lookup"><span data-stu-id="635ef-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="635ef-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="635ef-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="635ef-284">寫入 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="635ef-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="635ef-285">寫入 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="635ef-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="635ef-286">寫入 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="635ef-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="635ef-287">寫入 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="635ef-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="635ef-288">子代 inetOrgPerson 物件</span><span class="sxs-lookup"><span data-stu-id="635ef-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

