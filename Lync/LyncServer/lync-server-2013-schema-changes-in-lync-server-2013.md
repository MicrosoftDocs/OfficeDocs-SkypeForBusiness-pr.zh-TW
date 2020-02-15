---
title: Lync Server 2013 中的 Lync Server 2013： 結構描述變更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema changes in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48185575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 789a6a67b1794eee5f01e8672f9aeb1076646ecf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-changes-in-lync-server-2013"></a><span data-ttu-id="5b5ae-102">Lync Server 2013 中的結構描述變更</span><span class="sxs-lookup"><span data-stu-id="5b5ae-102">Schema changes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b5ae-103">_**主題上次修改日期：** 2012年-10-18_</span><span class="sxs-lookup"><span data-stu-id="5b5ae-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="5b5ae-104">部署及操作 Lync Server 2013 之前，您必須準備 Active Directory 網域服務來擴充架構。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-104">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="5b5ae-105">架構延伸模組新增的類別和 Lync Server 2013 所需的屬性。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-105">The schema extensions add the classes and attributes that are required by Lync Server 2013.</span></span>

<span data-ttu-id="5b5ae-106">Lync Server 2013 需要數個新的類別和屬性，並修改某些現有類別和屬性。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-106">Lync Server 2013 requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="5b5ae-107">此外，針對 Lync Server 2013 多組態資訊而不是 AD DS 中的中央管理存放區中儲存在舊版中。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-107">In addition, much configuration information for Lync Server 2013 is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="5b5ae-108">Lync Server 2013 中的 AD DS 中仍儲存下列資訊：</span><span class="sxs-lookup"><span data-stu-id="5b5ae-108">The following information is still stored in AD DS in Lync Server 2013:</span></span>

  - <span data-ttu-id="5b5ae-109">**架構延伸模組**：</span><span class="sxs-lookup"><span data-stu-id="5b5ae-109">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="5b5ae-110">使用者物件延伸</span><span class="sxs-lookup"><span data-stu-id="5b5ae-110">User object extensions</span></span>
    
      - <span data-ttu-id="5b5ae-111">Office Communications Server 2007 和 Office Communications Server 2007 R2 類別，以維持與支援的舊版的回溯相容性的副檔名</span><span class="sxs-lookup"><span data-stu-id="5b5ae-111">Extensions for Office Communications Server 2007 and Office Communications Server 2007 R2 classes to maintain backward compatibility with supported previous versions</span></span>

<!-- end list -->

  - <span data-ttu-id="5b5ae-112">**資料**（儲存在 Lync Server 延伸架構和現有的架構類別中）：</span><span class="sxs-lookup"><span data-stu-id="5b5ae-112">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="5b5ae-113">使用者的 SIP 統一資源識別元 (URI) 及其他使用者設定</span><span class="sxs-lookup"><span data-stu-id="5b5ae-113">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="5b5ae-114">回應群組與會議服務員等應用程式的連絡人物件</span><span class="sxs-lookup"><span data-stu-id="5b5ae-114">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="5b5ae-115">中央管理存放區的指標</span><span class="sxs-lookup"><span data-stu-id="5b5ae-115">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="5b5ae-116">Kerberos 驗證帳戶 （選擇性的電腦物件）</span><span class="sxs-lookup"><span data-stu-id="5b5ae-116">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="5b5ae-117">本主題說明所需的 Lync Server 2013 的 Active Directory 架構變更。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-117">This topic describes the Active Directory schema changes required by Lync Server 2013.</span></span> <span data-ttu-id="5b5ae-118">它不會說明舊版 Office Communications Server 所引進的架構變更。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-118">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="5b5ae-119">類別和及其描述的清單，請參閱[架構類別和 Lync Server 2013 中的描述](lync-server-2013-schema-classes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-119">For a list of classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="5b5ae-120">屬性和及其描述的清單，請參閱[結構描述的屬性和 Lync Server 2013 中的描述](lync-server-2013-schema-attributes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-120">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="5b5ae-121">如需類別與屬性的清單它們可能包含，請參閱[結構描述由 Lync Server 2013 中的類別的屬性](lync-server-2013-schema-attributes-by-class.md)。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-121">For a list of classes with the attributes they may contain, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span>

<span data-ttu-id="5b5ae-122">MsRTCSIP 前置詞會識別類別和 Lync 伺服器特有的屬性。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-122">The msRTCSIP prefix identifies classes and attributes that are specific to Lync Server.</span></span>

<div>

## <a name="new-active-directory-attributes"></a><span data-ttu-id="5b5ae-123">新的 Active Directory 屬性</span><span class="sxs-lookup"><span data-stu-id="5b5ae-123">New Active Directory Attributes</span></span>

<span data-ttu-id="5b5ae-124">下表說明新增的 Lync Server 2013 的 Active Directory 屬性。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-124">The following table describes the Active Directory attributes that are added by Lync Server 2013.</span></span>

### <a name="attributes-added-by-lync-server-2013"></a><span data-ttu-id="5b5ae-125">新增 Lync Server 2013 的屬性</span><span class="sxs-lookup"><span data-stu-id="5b5ae-125">Attributes Added by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b5ae-126">屬性</span><span class="sxs-lookup"><span data-stu-id="5b5ae-126">Attribute</span></span></th>
<th><span data-ttu-id="5b5ae-127">描述</span><span class="sxs-lookup"><span data-stu-id="5b5ae-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b5ae-128">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="5b5ae-128">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="5b5ae-129">此多重值屬性包含識別碼保留套用到使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-129">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="5b5ae-130">保留原則的保留期間保留使用者的信箱項目。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-130">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="5b5ae-131">Exchange 2013 可共用此屬性。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-131">This attribute is shared with Exchange 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b5ae-132">包含 UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="5b5ae-132">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="5b5ae-133">這是 SIP 路由群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-133">This is the SIP routing group ID.</span></span> <span data-ttu-id="5b5ae-134">相同群組中的使用者將登錄至同一個前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-134">Users in the same group will register to the same Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b5ae-135">包含 MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="5b5ae-135">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="5b5ae-136">此屬性用來儲存前端集區所使用的鏡像的 SQL Server 後端。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-136">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a><span data-ttu-id="5b5ae-137">已修改的 Active Directory 類別</span><span class="sxs-lookup"><span data-stu-id="5b5ae-137">Modified Active Directory Classes</span></span>

<span data-ttu-id="5b5ae-138">下表說明修改的 Lync Server 2013 的 Active Directory 類別。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-138">The following table describes the Active Directory classes that are modified by Lync Server 2013.</span></span>

### <a name="classes-modified-by-lync-server-2013"></a><span data-ttu-id="5b5ae-139">Lync Server 2013 所修改的類別</span><span class="sxs-lookup"><span data-stu-id="5b5ae-139">Classes Modified by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b5ae-140">類別</span><span class="sxs-lookup"><span data-stu-id="5b5ae-140">Class</span></span></th>
<th><span data-ttu-id="5b5ae-141">變更</span><span class="sxs-lookup"><span data-stu-id="5b5ae-141">Change</span></span></th>
<th><span data-ttu-id="5b5ae-142">類別或屬性</span><span class="sxs-lookup"><span data-stu-id="5b5ae-142">Class or Attribute</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b5ae-143">使用者</span><span class="sxs-lookup"><span data-stu-id="5b5ae-143">User</span></span></p></td>
<td><p><span data-ttu-id="5b5ae-144">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="5b5ae-144">add: mayContain</span></span></p>
<p><span data-ttu-id="5b5ae-145">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="5b5ae-145">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="5b5ae-146">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="5b5ae-146">ProxyAddresses</span></span></p>
<p><span data-ttu-id="5b5ae-147">包含 UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="5b5ae-147">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b5ae-148">連絡人</span><span class="sxs-lookup"><span data-stu-id="5b5ae-148">Contact</span></span></p></td>
<td><p><span data-ttu-id="5b5ae-149">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="5b5ae-149">add: mayContain</span></span></p>
<p><span data-ttu-id="5b5ae-150">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="5b5ae-150">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="5b5ae-151">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="5b5ae-151">ProxyAddresses</span></span></p>
<p><span data-ttu-id="5b5ae-152">包含 UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="5b5ae-152">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b5ae-153">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="5b5ae-153">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="5b5ae-154">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="5b5ae-154">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="5b5ae-155">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="5b5ae-155">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b5ae-156">包含 GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="5b5ae-156">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="5b5ae-157">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="5b5ae-157">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="5b5ae-158">包含 MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="5b5ae-158">msRTCSIP-MirrorBackEndServer</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

