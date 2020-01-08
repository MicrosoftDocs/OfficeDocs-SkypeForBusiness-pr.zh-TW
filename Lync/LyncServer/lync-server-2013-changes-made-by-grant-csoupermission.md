---
title: Lync Server 2013：由授與授權所做的變更 CsOUPermission
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ce6b16dff48afeeec848024d763655695905008
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="2a096-102">在 Lync Server 2013 中由 Grant CsOUPermission 所做的變更</span><span class="sxs-lookup"><span data-stu-id="2a096-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a096-103">_**主題上次修改日期：** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="2a096-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="2a096-104">若要委派 Lync Server 2013 管理，您可以在指定的組織單位（Ou）中新增許可權，以便由林準備建立的 RTC 通用群組成員可以存取 Ou，而不是網域管理員群組的成員。</span><span class="sxs-lookup"><span data-stu-id="2a096-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="2a096-105">**Grant CsOuPermission** Cmdlet 會根據下表中的指定，將許可權授與指定 OU 中的物件。</span><span class="sxs-lookup"><span data-stu-id="2a096-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="2a096-106">授與使用者物件的許可權</span><span class="sxs-lookup"><span data-stu-id="2a096-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="2a096-107">當您針對 OU 中的使用者物件執行**Grant CsOuPermission** Cmdlet 時，系統會授與群組的許可權，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="2a096-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="2a096-108">授與使用者物件的許可權</span><span class="sxs-lookup"><span data-stu-id="2a096-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a096-109">群組</span><span class="sxs-lookup"><span data-stu-id="2a096-109">Group</span></span></th>
<th><span data-ttu-id="2a096-110">拒絕</span><span class="sxs-lookup"><span data-stu-id="2a096-110">Permission</span></span></th>
<th><span data-ttu-id="2a096-111">適用于</span><span class="sxs-lookup"><span data-stu-id="2a096-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a096-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="2a096-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="2a096-113">複製目錄變更</span><span class="sxs-lookup"><span data-stu-id="2a096-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="2a096-114">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="2a096-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a096-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="2a096-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="2a096-116">清單內容</span><span class="sxs-lookup"><span data-stu-id="2a096-116">List contents</span></span></p>
<p><span data-ttu-id="2a096-117">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="2a096-117">Read all properties</span></span></p>
<p><span data-ttu-id="2a096-118">讀取權限</span><span class="sxs-lookup"><span data-stu-id="2a096-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="2a096-119">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="2a096-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a096-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="2a096-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="2a096-121">清單內容</span><span class="sxs-lookup"><span data-stu-id="2a096-121">List contents</span></span></p>
<p><span data-ttu-id="2a096-122">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="2a096-122">Read all properties</span></span></p>
<p><span data-ttu-id="2a096-123">讀取權限</span><span class="sxs-lookup"><span data-stu-id="2a096-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="2a096-124">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="2a096-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a096-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="2a096-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="2a096-126">閱讀 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="2a096-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="2a096-127">閱讀 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="2a096-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="2a096-128">閱讀 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="2a096-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="2a096-129">閱讀公用資訊</span><span class="sxs-lookup"><span data-stu-id="2a096-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="2a096-130">閱讀一般資訊</span><span class="sxs-lookup"><span data-stu-id="2a096-130">Read General-Information</span></span></p>
<p><span data-ttu-id="2a096-131">閱讀使用者-帳戶限制</span><span class="sxs-lookup"><span data-stu-id="2a096-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="2a096-132">後代使用者物件</span><span class="sxs-lookup"><span data-stu-id="2a096-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a096-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="2a096-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="2a096-134">撰寫 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="2a096-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="2a096-135">撰寫 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="2a096-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="2a096-136">撰寫 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="2a096-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="2a096-137">撰寫 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="2a096-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="2a096-138">撰寫 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="2a096-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="2a096-139">後代使用者物件</span><span class="sxs-lookup"><span data-stu-id="2a096-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="2a096-140">授與電腦物件的許可權</span><span class="sxs-lookup"><span data-stu-id="2a096-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="2a096-141">當您針對 OU 中的電腦物件執行**Grant CsOuPermission** Cmdlet 時，系統會授與群組的許可權，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="2a096-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="2a096-142">授與電腦物件的許可權</span><span class="sxs-lookup"><span data-stu-id="2a096-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a096-143">群組</span><span class="sxs-lookup"><span data-stu-id="2a096-143">Group</span></span></th>
<th><span data-ttu-id="2a096-144">拒絕</span><span class="sxs-lookup"><span data-stu-id="2a096-144">Permission</span></span></th>
<th><span data-ttu-id="2a096-145">適用于</span><span class="sxs-lookup"><span data-stu-id="2a096-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a096-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="2a096-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="2a096-147">複製目錄變更</span><span class="sxs-lookup"><span data-stu-id="2a096-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="2a096-148">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="2a096-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a096-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="2a096-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="2a096-150">清單內容</span><span class="sxs-lookup"><span data-stu-id="2a096-150">List contents</span></span></p>
<p><span data-ttu-id="2a096-151">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="2a096-151">Read all properties</span></span></p>
<p><span data-ttu-id="2a096-152">讀取權限</span><span class="sxs-lookup"><span data-stu-id="2a096-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="2a096-153">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="2a096-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a096-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="2a096-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="2a096-155">清單內容</span><span class="sxs-lookup"><span data-stu-id="2a096-155">List contents</span></span></p>
<p><span data-ttu-id="2a096-156">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="2a096-156">Read all properties</span></span></p>
<p><span data-ttu-id="2a096-157">讀取權限</span><span class="sxs-lookup"><span data-stu-id="2a096-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="2a096-158">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="2a096-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a096-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="2a096-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="2a096-160">閱讀公用資訊</span><span class="sxs-lookup"><span data-stu-id="2a096-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="2a096-161">已驗證閱讀-DNS 主機名稱</span><span class="sxs-lookup"><span data-stu-id="2a096-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="2a096-162">後代電腦物件</span><span class="sxs-lookup"><span data-stu-id="2a096-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a096-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="2a096-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="2a096-164">閱讀公用資訊</span><span class="sxs-lookup"><span data-stu-id="2a096-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="2a096-165">已驗證閱讀-DNS 主機名稱</span><span class="sxs-lookup"><span data-stu-id="2a096-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="2a096-166">後代電腦物件</span><span class="sxs-lookup"><span data-stu-id="2a096-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="2a096-167">授予連絡人或 AppContact 物件的許可權</span><span class="sxs-lookup"><span data-stu-id="2a096-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="2a096-168">當您在 OU 上執行連絡人物件或 AppContact 物件的**Grant CsOuPermission** Cmdlet 時，系統會授與群組的許可權，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="2a096-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="2a096-169">授與連絡人或 AppContact 物件的許可權</span><span class="sxs-lookup"><span data-stu-id="2a096-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a096-170">群組</span><span class="sxs-lookup"><span data-stu-id="2a096-170">Group</span></span></th>
<th><span data-ttu-id="2a096-171">拒絕</span><span class="sxs-lookup"><span data-stu-id="2a096-171">Permission</span></span></th>
<th><span data-ttu-id="2a096-172">適用于</span><span class="sxs-lookup"><span data-stu-id="2a096-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a096-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="2a096-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="2a096-174">複製目錄變更</span><span class="sxs-lookup"><span data-stu-id="2a096-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="2a096-175">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="2a096-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a096-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="2a096-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="2a096-177">清單內容</span><span class="sxs-lookup"><span data-stu-id="2a096-177">List contents</span></span></p>
<p><span data-ttu-id="2a096-178">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="2a096-178">Read all properties</span></span></p>
<p><span data-ttu-id="2a096-179">讀取權限</span><span class="sxs-lookup"><span data-stu-id="2a096-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="2a096-180">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="2a096-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a096-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="2a096-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="2a096-182">清單內容</span><span class="sxs-lookup"><span data-stu-id="2a096-182">List contents</span></span></p>
<p><span data-ttu-id="2a096-183">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="2a096-183">Read all properties</span></span></p>
<p><span data-ttu-id="2a096-184">讀取權限</span><span class="sxs-lookup"><span data-stu-id="2a096-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="2a096-185">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="2a096-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a096-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="2a096-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="2a096-187">閱讀 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="2a096-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="2a096-188">閱讀 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="2a096-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="2a096-189">閱讀 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="2a096-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="2a096-190">閱讀公用資訊</span><span class="sxs-lookup"><span data-stu-id="2a096-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="2a096-191">閱讀一般資訊</span><span class="sxs-lookup"><span data-stu-id="2a096-191">Read General-Information</span></span></p>
<p><span data-ttu-id="2a096-192">閱讀個人資訊</span><span class="sxs-lookup"><span data-stu-id="2a096-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="2a096-193">閱讀使用者-帳戶限制</span><span class="sxs-lookup"><span data-stu-id="2a096-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="2a096-194">子代連絡人物件</span><span class="sxs-lookup"><span data-stu-id="2a096-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a096-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="2a096-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="2a096-196">撰寫 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="2a096-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="2a096-197">撰寫 otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="2a096-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="2a096-198">寫入 displayName</span><span class="sxs-lookup"><span data-stu-id="2a096-198">Write displayName</span></span></p>
<p><span data-ttu-id="2a096-199">撰寫描述</span><span class="sxs-lookup"><span data-stu-id="2a096-199">Write description</span></span></p>
<p><span data-ttu-id="2a096-200">撰寫 Telephonenumber 相同</span><span class="sxs-lookup"><span data-stu-id="2a096-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="2a096-201">撰寫 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="2a096-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="2a096-202">撰寫 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="2a096-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="2a096-203">撰寫 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="2a096-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="2a096-204">撰寫 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="2a096-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="2a096-205">子代連絡人物件</span><span class="sxs-lookup"><span data-stu-id="2a096-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="2a096-206">為裝置物件授與許可權</span><span class="sxs-lookup"><span data-stu-id="2a096-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="2a096-207">當您針對 OU 中的裝置物件執行**Grant CsOuPermission** Cmdlet 時，系統會授與群組的許可權，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="2a096-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="2a096-208">針對裝置物件所授的許可權</span><span class="sxs-lookup"><span data-stu-id="2a096-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a096-209">群組</span><span class="sxs-lookup"><span data-stu-id="2a096-209">Group</span></span></th>
<th><span data-ttu-id="2a096-210">拒絕</span><span class="sxs-lookup"><span data-stu-id="2a096-210">Permission</span></span></th>
<th><span data-ttu-id="2a096-211">適用于</span><span class="sxs-lookup"><span data-stu-id="2a096-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a096-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="2a096-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="2a096-213">複製目錄變更</span><span class="sxs-lookup"><span data-stu-id="2a096-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="2a096-214">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="2a096-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a096-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="2a096-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="2a096-216">清單內容</span><span class="sxs-lookup"><span data-stu-id="2a096-216">List contents</span></span></p>
<p><span data-ttu-id="2a096-217">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="2a096-217">Read all properties</span></span></p>
<p><span data-ttu-id="2a096-218">讀取權限</span><span class="sxs-lookup"><span data-stu-id="2a096-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="2a096-219">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="2a096-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a096-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="2a096-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="2a096-221">清單內容</span><span class="sxs-lookup"><span data-stu-id="2a096-221">List contents</span></span></p>
<p><span data-ttu-id="2a096-222">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="2a096-222">Read all properties</span></span></p>
<p><span data-ttu-id="2a096-223">讀取權限</span><span class="sxs-lookup"><span data-stu-id="2a096-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="2a096-224">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="2a096-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a096-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="2a096-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="2a096-226">閱讀 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="2a096-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="2a096-227">閱讀 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="2a096-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="2a096-228">閱讀 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="2a096-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="2a096-229">閱讀公用資訊</span><span class="sxs-lookup"><span data-stu-id="2a096-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="2a096-230">閱讀個人資訊</span><span class="sxs-lookup"><span data-stu-id="2a096-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="2a096-231">閱讀一般資訊</span><span class="sxs-lookup"><span data-stu-id="2a096-231">Read General-Information</span></span></p>
<p><span data-ttu-id="2a096-232">閱讀使用者-帳戶限制</span><span class="sxs-lookup"><span data-stu-id="2a096-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="2a096-233">子代連絡人物件</span><span class="sxs-lookup"><span data-stu-id="2a096-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a096-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="2a096-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="2a096-235">建立子系</span><span class="sxs-lookup"><span data-stu-id="2a096-235">Create child</span></span></p>
<p><span data-ttu-id="2a096-236">刪除子系</span><span class="sxs-lookup"><span data-stu-id="2a096-236">Delete child</span></span></p>
<p><span data-ttu-id="2a096-237">刪除樹</span><span class="sxs-lookup"><span data-stu-id="2a096-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="2a096-238">資訊</span><span class="sxs-lookup"><span data-stu-id="2a096-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a096-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="2a096-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="2a096-240">寫入 displayName</span><span class="sxs-lookup"><span data-stu-id="2a096-240">Write displayName</span></span></p>
<p><span data-ttu-id="2a096-241">撰寫描述</span><span class="sxs-lookup"><span data-stu-id="2a096-241">Write description</span></span></p>
<p><span data-ttu-id="2a096-242">撰寫 Telephonenumber 相同</span><span class="sxs-lookup"><span data-stu-id="2a096-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="2a096-243">後代使用者物件</span><span class="sxs-lookup"><span data-stu-id="2a096-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a096-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="2a096-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="2a096-245">撰寫 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="2a096-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="2a096-246">撰寫 otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="2a096-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="2a096-247">寫入 displayName</span><span class="sxs-lookup"><span data-stu-id="2a096-247">Write displayName</span></span></p>
<p><span data-ttu-id="2a096-248">撰寫描述</span><span class="sxs-lookup"><span data-stu-id="2a096-248">Write description</span></span></p>
<p><span data-ttu-id="2a096-249">撰寫 Telephonenumber 相同</span><span class="sxs-lookup"><span data-stu-id="2a096-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="2a096-250">撰寫 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="2a096-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="2a096-251">撰寫 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="2a096-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="2a096-252">撰寫 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="2a096-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="2a096-253">撰寫 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="2a096-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="2a096-254">子代連絡人物件</span><span class="sxs-lookup"><span data-stu-id="2a096-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="2a096-255">授予 InetOrgPerson 物件的許可權</span><span class="sxs-lookup"><span data-stu-id="2a096-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="2a096-256">當您針對 OU 上的 InetOrgPerson 物件執行**Grant CsOuPermission** Cmdlet 時，系統會授與群組的許可權，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="2a096-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="2a096-257">授與 InetOrgPerson 物件的許可權</span><span class="sxs-lookup"><span data-stu-id="2a096-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a096-258">群組</span><span class="sxs-lookup"><span data-stu-id="2a096-258">Group</span></span></th>
<th><span data-ttu-id="2a096-259">拒絕</span><span class="sxs-lookup"><span data-stu-id="2a096-259">Permission</span></span></th>
<th><span data-ttu-id="2a096-260">適用于</span><span class="sxs-lookup"><span data-stu-id="2a096-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a096-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="2a096-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="2a096-262">複製目錄變更</span><span class="sxs-lookup"><span data-stu-id="2a096-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="2a096-263">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="2a096-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a096-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="2a096-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="2a096-265">清單內容</span><span class="sxs-lookup"><span data-stu-id="2a096-265">List contents</span></span></p>
<p><span data-ttu-id="2a096-266">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="2a096-266">Read all properties</span></span></p>
<p><span data-ttu-id="2a096-267">讀取權限</span><span class="sxs-lookup"><span data-stu-id="2a096-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="2a096-268">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="2a096-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a096-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="2a096-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="2a096-270">清單內容</span><span class="sxs-lookup"><span data-stu-id="2a096-270">List contents</span></span></p>
<p><span data-ttu-id="2a096-271">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="2a096-271">Read all properties</span></span></p>
<p><span data-ttu-id="2a096-272">讀取權限</span><span class="sxs-lookup"><span data-stu-id="2a096-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="2a096-273">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="2a096-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a096-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="2a096-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="2a096-275">閱讀 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="2a096-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="2a096-276">閱讀 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="2a096-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="2a096-277">閱讀 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="2a096-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="2a096-278">閱讀個人資訊</span><span class="sxs-lookup"><span data-stu-id="2a096-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="2a096-279">閱讀公用資訊</span><span class="sxs-lookup"><span data-stu-id="2a096-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="2a096-280">閱讀一般資訊</span><span class="sxs-lookup"><span data-stu-id="2a096-280">Read General-Information</span></span></p>
<p><span data-ttu-id="2a096-281">閱讀使用者-帳戶限制</span><span class="sxs-lookup"><span data-stu-id="2a096-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="2a096-282">子代 inetOrgPerson 物件</span><span class="sxs-lookup"><span data-stu-id="2a096-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a096-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="2a096-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="2a096-284">撰寫 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="2a096-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="2a096-285">撰寫 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="2a096-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="2a096-286">撰寫 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="2a096-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="2a096-287">撰寫 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="2a096-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="2a096-288">子代 inetOrgPerson 物件</span><span class="sxs-lookup"><span data-stu-id="2a096-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

