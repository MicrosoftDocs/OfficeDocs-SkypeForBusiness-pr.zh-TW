---
title: Lync Server 2013：由授與授權所做的變更 CsOUPermission
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
ms.openlocfilehash: 9056753e57f57b131a05d13eb2862611ba34f966
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="75c2e-102">在 Lync Server 2013 中由 Grant CsOUPermission 所做的變更</span><span class="sxs-lookup"><span data-stu-id="75c2e-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75c2e-103">_**主題上次修改日期：** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="75c2e-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="75c2e-104">若要委派 Lync Server 2013 管理，您可以在指定的組織單位（Ou）中新增許可權，以便由林準備建立的 RTC 通用群組成員可以存取 Ou，而不是網域管理員群組的成員。</span><span class="sxs-lookup"><span data-stu-id="75c2e-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="75c2e-105">**Grant CsOuPermission** Cmdlet 會根據下表中的指定，將許可權授與指定 OU 中的物件。</span><span class="sxs-lookup"><span data-stu-id="75c2e-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="75c2e-106">授與使用者物件的許可權</span><span class="sxs-lookup"><span data-stu-id="75c2e-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="75c2e-107">當您針對 OU 中的使用者物件執行**Grant CsOuPermission** Cmdlet 時，系統會授與群組的許可權，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="75c2e-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="75c2e-108">授與使用者物件的許可權</span><span class="sxs-lookup"><span data-stu-id="75c2e-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75c2e-109">群組</span><span class="sxs-lookup"><span data-stu-id="75c2e-109">Group</span></span></th>
<th><span data-ttu-id="75c2e-110">拒絕</span><span class="sxs-lookup"><span data-stu-id="75c2e-110">Permission</span></span></th>
<th><span data-ttu-id="75c2e-111">適用于</span><span class="sxs-lookup"><span data-stu-id="75c2e-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75c2e-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="75c2e-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="75c2e-113">複製目錄變更</span><span class="sxs-lookup"><span data-stu-id="75c2e-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="75c2e-114">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="75c2e-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75c2e-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="75c2e-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="75c2e-116">清單內容</span><span class="sxs-lookup"><span data-stu-id="75c2e-116">List contents</span></span></p>
<p><span data-ttu-id="75c2e-117">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="75c2e-117">Read all properties</span></span></p>
<p><span data-ttu-id="75c2e-118">讀取權限</span><span class="sxs-lookup"><span data-stu-id="75c2e-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="75c2e-119">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="75c2e-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75c2e-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="75c2e-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="75c2e-121">清單內容</span><span class="sxs-lookup"><span data-stu-id="75c2e-121">List contents</span></span></p>
<p><span data-ttu-id="75c2e-122">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="75c2e-122">Read all properties</span></span></p>
<p><span data-ttu-id="75c2e-123">讀取權限</span><span class="sxs-lookup"><span data-stu-id="75c2e-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="75c2e-124">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="75c2e-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75c2e-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="75c2e-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="75c2e-126">閱讀 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="75c2e-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="75c2e-127">閱讀 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="75c2e-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="75c2e-128">閱讀 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="75c2e-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="75c2e-129">閱讀公用資訊</span><span class="sxs-lookup"><span data-stu-id="75c2e-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="75c2e-130">閱讀一般資訊</span><span class="sxs-lookup"><span data-stu-id="75c2e-130">Read General-Information</span></span></p>
<p><span data-ttu-id="75c2e-131">閱讀使用者-帳戶限制</span><span class="sxs-lookup"><span data-stu-id="75c2e-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="75c2e-132">後代使用者物件</span><span class="sxs-lookup"><span data-stu-id="75c2e-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75c2e-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="75c2e-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="75c2e-134">撰寫 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="75c2e-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="75c2e-135">撰寫 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="75c2e-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="75c2e-136">撰寫 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="75c2e-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="75c2e-137">撰寫 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="75c2e-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="75c2e-138">撰寫 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="75c2e-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="75c2e-139">後代使用者物件</span><span class="sxs-lookup"><span data-stu-id="75c2e-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="75c2e-140">授與電腦物件的許可權</span><span class="sxs-lookup"><span data-stu-id="75c2e-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="75c2e-141">當您針對 OU 中的電腦物件執行**Grant CsOuPermission** Cmdlet 時，系統會授與群組的許可權，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="75c2e-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="75c2e-142">授與電腦物件的許可權</span><span class="sxs-lookup"><span data-stu-id="75c2e-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75c2e-143">群組</span><span class="sxs-lookup"><span data-stu-id="75c2e-143">Group</span></span></th>
<th><span data-ttu-id="75c2e-144">拒絕</span><span class="sxs-lookup"><span data-stu-id="75c2e-144">Permission</span></span></th>
<th><span data-ttu-id="75c2e-145">適用于</span><span class="sxs-lookup"><span data-stu-id="75c2e-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75c2e-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="75c2e-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="75c2e-147">複製目錄變更</span><span class="sxs-lookup"><span data-stu-id="75c2e-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="75c2e-148">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="75c2e-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75c2e-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="75c2e-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="75c2e-150">清單內容</span><span class="sxs-lookup"><span data-stu-id="75c2e-150">List contents</span></span></p>
<p><span data-ttu-id="75c2e-151">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="75c2e-151">Read all properties</span></span></p>
<p><span data-ttu-id="75c2e-152">讀取權限</span><span class="sxs-lookup"><span data-stu-id="75c2e-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="75c2e-153">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="75c2e-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75c2e-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="75c2e-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="75c2e-155">清單內容</span><span class="sxs-lookup"><span data-stu-id="75c2e-155">List contents</span></span></p>
<p><span data-ttu-id="75c2e-156">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="75c2e-156">Read all properties</span></span></p>
<p><span data-ttu-id="75c2e-157">讀取權限</span><span class="sxs-lookup"><span data-stu-id="75c2e-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="75c2e-158">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="75c2e-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75c2e-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="75c2e-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="75c2e-160">閱讀公用資訊</span><span class="sxs-lookup"><span data-stu-id="75c2e-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="75c2e-161">已驗證閱讀-DNS 主機名稱</span><span class="sxs-lookup"><span data-stu-id="75c2e-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="75c2e-162">後代電腦物件</span><span class="sxs-lookup"><span data-stu-id="75c2e-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75c2e-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="75c2e-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="75c2e-164">閱讀公用資訊</span><span class="sxs-lookup"><span data-stu-id="75c2e-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="75c2e-165">已驗證閱讀-DNS 主機名稱</span><span class="sxs-lookup"><span data-stu-id="75c2e-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="75c2e-166">後代電腦物件</span><span class="sxs-lookup"><span data-stu-id="75c2e-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="75c2e-167">授予連絡人或 AppContact 物件的許可權</span><span class="sxs-lookup"><span data-stu-id="75c2e-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="75c2e-168">當您在 OU 上執行連絡人物件或 AppContact 物件的**Grant CsOuPermission** Cmdlet 時，系統會授與群組的許可權，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="75c2e-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="75c2e-169">授與連絡人或 AppContact 物件的許可權</span><span class="sxs-lookup"><span data-stu-id="75c2e-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75c2e-170">群組</span><span class="sxs-lookup"><span data-stu-id="75c2e-170">Group</span></span></th>
<th><span data-ttu-id="75c2e-171">拒絕</span><span class="sxs-lookup"><span data-stu-id="75c2e-171">Permission</span></span></th>
<th><span data-ttu-id="75c2e-172">適用于</span><span class="sxs-lookup"><span data-stu-id="75c2e-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75c2e-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="75c2e-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="75c2e-174">複製目錄變更</span><span class="sxs-lookup"><span data-stu-id="75c2e-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="75c2e-175">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="75c2e-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75c2e-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="75c2e-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="75c2e-177">清單內容</span><span class="sxs-lookup"><span data-stu-id="75c2e-177">List contents</span></span></p>
<p><span data-ttu-id="75c2e-178">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="75c2e-178">Read all properties</span></span></p>
<p><span data-ttu-id="75c2e-179">讀取權限</span><span class="sxs-lookup"><span data-stu-id="75c2e-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="75c2e-180">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="75c2e-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75c2e-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="75c2e-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="75c2e-182">清單內容</span><span class="sxs-lookup"><span data-stu-id="75c2e-182">List contents</span></span></p>
<p><span data-ttu-id="75c2e-183">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="75c2e-183">Read all properties</span></span></p>
<p><span data-ttu-id="75c2e-184">讀取權限</span><span class="sxs-lookup"><span data-stu-id="75c2e-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="75c2e-185">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="75c2e-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75c2e-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="75c2e-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="75c2e-187">閱讀 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="75c2e-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="75c2e-188">閱讀 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="75c2e-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="75c2e-189">閱讀 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="75c2e-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="75c2e-190">閱讀公用資訊</span><span class="sxs-lookup"><span data-stu-id="75c2e-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="75c2e-191">閱讀一般資訊</span><span class="sxs-lookup"><span data-stu-id="75c2e-191">Read General-Information</span></span></p>
<p><span data-ttu-id="75c2e-192">閱讀個人資訊</span><span class="sxs-lookup"><span data-stu-id="75c2e-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="75c2e-193">閱讀使用者-帳戶限制</span><span class="sxs-lookup"><span data-stu-id="75c2e-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="75c2e-194">子代連絡人物件</span><span class="sxs-lookup"><span data-stu-id="75c2e-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75c2e-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="75c2e-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="75c2e-196">撰寫 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="75c2e-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="75c2e-197">撰寫 otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="75c2e-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="75c2e-198">寫入 displayName</span><span class="sxs-lookup"><span data-stu-id="75c2e-198">Write displayName</span></span></p>
<p><span data-ttu-id="75c2e-199">撰寫描述</span><span class="sxs-lookup"><span data-stu-id="75c2e-199">Write description</span></span></p>
<p><span data-ttu-id="75c2e-200">撰寫 Telephonenumber 相同</span><span class="sxs-lookup"><span data-stu-id="75c2e-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="75c2e-201">撰寫 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="75c2e-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="75c2e-202">撰寫 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="75c2e-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="75c2e-203">撰寫 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="75c2e-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="75c2e-204">撰寫 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="75c2e-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="75c2e-205">子代連絡人物件</span><span class="sxs-lookup"><span data-stu-id="75c2e-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="75c2e-206">為裝置物件授與許可權</span><span class="sxs-lookup"><span data-stu-id="75c2e-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="75c2e-207">當您針對 OU 中的裝置物件執行**Grant CsOuPermission** Cmdlet 時，系統會授與群組的許可權，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="75c2e-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="75c2e-208">針對裝置物件所授的許可權</span><span class="sxs-lookup"><span data-stu-id="75c2e-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75c2e-209">群組</span><span class="sxs-lookup"><span data-stu-id="75c2e-209">Group</span></span></th>
<th><span data-ttu-id="75c2e-210">拒絕</span><span class="sxs-lookup"><span data-stu-id="75c2e-210">Permission</span></span></th>
<th><span data-ttu-id="75c2e-211">適用于</span><span class="sxs-lookup"><span data-stu-id="75c2e-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75c2e-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="75c2e-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="75c2e-213">複製目錄變更</span><span class="sxs-lookup"><span data-stu-id="75c2e-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="75c2e-214">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="75c2e-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75c2e-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="75c2e-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="75c2e-216">清單內容</span><span class="sxs-lookup"><span data-stu-id="75c2e-216">List contents</span></span></p>
<p><span data-ttu-id="75c2e-217">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="75c2e-217">Read all properties</span></span></p>
<p><span data-ttu-id="75c2e-218">讀取權限</span><span class="sxs-lookup"><span data-stu-id="75c2e-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="75c2e-219">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="75c2e-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75c2e-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="75c2e-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="75c2e-221">清單內容</span><span class="sxs-lookup"><span data-stu-id="75c2e-221">List contents</span></span></p>
<p><span data-ttu-id="75c2e-222">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="75c2e-222">Read all properties</span></span></p>
<p><span data-ttu-id="75c2e-223">讀取權限</span><span class="sxs-lookup"><span data-stu-id="75c2e-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="75c2e-224">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="75c2e-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75c2e-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="75c2e-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="75c2e-226">閱讀 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="75c2e-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="75c2e-227">閱讀 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="75c2e-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="75c2e-228">閱讀 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="75c2e-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="75c2e-229">閱讀公用資訊</span><span class="sxs-lookup"><span data-stu-id="75c2e-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="75c2e-230">閱讀個人資訊</span><span class="sxs-lookup"><span data-stu-id="75c2e-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="75c2e-231">閱讀一般資訊</span><span class="sxs-lookup"><span data-stu-id="75c2e-231">Read General-Information</span></span></p>
<p><span data-ttu-id="75c2e-232">閱讀使用者-帳戶限制</span><span class="sxs-lookup"><span data-stu-id="75c2e-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="75c2e-233">子代連絡人物件</span><span class="sxs-lookup"><span data-stu-id="75c2e-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75c2e-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="75c2e-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="75c2e-235">建立子系</span><span class="sxs-lookup"><span data-stu-id="75c2e-235">Create child</span></span></p>
<p><span data-ttu-id="75c2e-236">刪除子系</span><span class="sxs-lookup"><span data-stu-id="75c2e-236">Delete child</span></span></p>
<p><span data-ttu-id="75c2e-237">刪除樹</span><span class="sxs-lookup"><span data-stu-id="75c2e-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="75c2e-238">資訊</span><span class="sxs-lookup"><span data-stu-id="75c2e-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75c2e-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="75c2e-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="75c2e-240">寫入 displayName</span><span class="sxs-lookup"><span data-stu-id="75c2e-240">Write displayName</span></span></p>
<p><span data-ttu-id="75c2e-241">撰寫描述</span><span class="sxs-lookup"><span data-stu-id="75c2e-241">Write description</span></span></p>
<p><span data-ttu-id="75c2e-242">撰寫 Telephonenumber 相同</span><span class="sxs-lookup"><span data-stu-id="75c2e-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="75c2e-243">後代使用者物件</span><span class="sxs-lookup"><span data-stu-id="75c2e-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75c2e-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="75c2e-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="75c2e-245">撰寫 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="75c2e-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="75c2e-246">撰寫 otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="75c2e-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="75c2e-247">寫入 displayName</span><span class="sxs-lookup"><span data-stu-id="75c2e-247">Write displayName</span></span></p>
<p><span data-ttu-id="75c2e-248">撰寫描述</span><span class="sxs-lookup"><span data-stu-id="75c2e-248">Write description</span></span></p>
<p><span data-ttu-id="75c2e-249">撰寫 Telephonenumber 相同</span><span class="sxs-lookup"><span data-stu-id="75c2e-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="75c2e-250">撰寫 msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="75c2e-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="75c2e-251">撰寫 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="75c2e-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="75c2e-252">撰寫 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="75c2e-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="75c2e-253">撰寫 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="75c2e-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="75c2e-254">子代連絡人物件</span><span class="sxs-lookup"><span data-stu-id="75c2e-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="75c2e-255">授予 InetOrgPerson 物件的許可權</span><span class="sxs-lookup"><span data-stu-id="75c2e-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="75c2e-256">當您針對 OU 上的 InetOrgPerson 物件執行**Grant CsOuPermission** Cmdlet 時，系統會授與群組的許可權，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="75c2e-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="75c2e-257">授與 InetOrgPerson 物件的許可權</span><span class="sxs-lookup"><span data-stu-id="75c2e-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75c2e-258">群組</span><span class="sxs-lookup"><span data-stu-id="75c2e-258">Group</span></span></th>
<th><span data-ttu-id="75c2e-259">拒絕</span><span class="sxs-lookup"><span data-stu-id="75c2e-259">Permission</span></span></th>
<th><span data-ttu-id="75c2e-260">適用于</span><span class="sxs-lookup"><span data-stu-id="75c2e-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75c2e-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="75c2e-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="75c2e-262">複製目錄變更</span><span class="sxs-lookup"><span data-stu-id="75c2e-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="75c2e-263">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="75c2e-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75c2e-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="75c2e-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="75c2e-265">清單內容</span><span class="sxs-lookup"><span data-stu-id="75c2e-265">List contents</span></span></p>
<p><span data-ttu-id="75c2e-266">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="75c2e-266">Read all properties</span></span></p>
<p><span data-ttu-id="75c2e-267">讀取權限</span><span class="sxs-lookup"><span data-stu-id="75c2e-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="75c2e-268">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="75c2e-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75c2e-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="75c2e-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="75c2e-270">清單內容</span><span class="sxs-lookup"><span data-stu-id="75c2e-270">List contents</span></span></p>
<p><span data-ttu-id="75c2e-271">讀取所有屬性</span><span class="sxs-lookup"><span data-stu-id="75c2e-271">Read all properties</span></span></p>
<p><span data-ttu-id="75c2e-272">讀取權限</span><span class="sxs-lookup"><span data-stu-id="75c2e-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="75c2e-273">僅限這個物件</span><span class="sxs-lookup"><span data-stu-id="75c2e-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75c2e-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="75c2e-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="75c2e-275">閱讀 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="75c2e-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="75c2e-276">閱讀 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="75c2e-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="75c2e-277">閱讀 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="75c2e-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="75c2e-278">閱讀個人資訊</span><span class="sxs-lookup"><span data-stu-id="75c2e-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="75c2e-279">閱讀公用資訊</span><span class="sxs-lookup"><span data-stu-id="75c2e-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="75c2e-280">閱讀一般資訊</span><span class="sxs-lookup"><span data-stu-id="75c2e-280">Read General-Information</span></span></p>
<p><span data-ttu-id="75c2e-281">閱讀使用者-帳戶限制</span><span class="sxs-lookup"><span data-stu-id="75c2e-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="75c2e-282">子代 inetOrgPerson 物件</span><span class="sxs-lookup"><span data-stu-id="75c2e-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75c2e-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="75c2e-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="75c2e-284">撰寫 RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="75c2e-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="75c2e-285">撰寫 RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="75c2e-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="75c2e-286">撰寫 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="75c2e-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="75c2e-287">撰寫 proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="75c2e-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="75c2e-288">子代 inetOrgPerson 物件</span><span class="sxs-lookup"><span data-stu-id="75c2e-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

