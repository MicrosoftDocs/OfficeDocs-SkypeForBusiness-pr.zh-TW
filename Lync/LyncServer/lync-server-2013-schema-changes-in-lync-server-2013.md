---
title: Lync Server 2013： Lync Server 2013 中的架構變更
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
ms.openlocfilehash: 54a3fd5f18785a649803cc6f9a0a56d7b98a2ee6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-changes-in-lync-server-2013"></a><span data-ttu-id="5def6-102">Lync Server 2013 中的架構變更</span><span class="sxs-lookup"><span data-stu-id="5def6-102">Schema changes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5def6-103">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="5def6-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="5def6-104">在您部署並操作 Lync Server 2013 之前，您必須透過延伸架構來準備 Active Directory 網域服務。</span><span class="sxs-lookup"><span data-stu-id="5def6-104">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="5def6-105">架構延伸會新增 Lync Server 2013 所需的類別和屬性。</span><span class="sxs-lookup"><span data-stu-id="5def6-105">The schema extensions add the classes and attributes that are required by Lync Server 2013.</span></span>

<span data-ttu-id="5def6-106">Lync Server 2013 需要幾個新的類別和屬性，並修改一些現有的類別和屬性。</span><span class="sxs-lookup"><span data-stu-id="5def6-106">Lync Server 2013 requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="5def6-107">此外，Lync Server 2013 的許多配置資訊會儲存在中央管理儲存區中，而不是在 AD DS 中，就像在舊版中一樣。</span><span class="sxs-lookup"><span data-stu-id="5def6-107">In addition, much configuration information for Lync Server 2013 is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="5def6-108">下列資訊仍會儲存在 Lync Server 2013 的 AD DS 中：</span><span class="sxs-lookup"><span data-stu-id="5def6-108">The following information is still stored in AD DS in Lync Server 2013:</span></span>

  - <span data-ttu-id="5def6-109">**架構擴充**：</span><span class="sxs-lookup"><span data-stu-id="5def6-109">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="5def6-110">使用者物件延伸</span><span class="sxs-lookup"><span data-stu-id="5def6-110">User object extensions</span></span>
    
      - <span data-ttu-id="5def6-111">Office 通訊伺服器2007與 Office 通訊伺服器 2007 R2 類別的擴充功能，可維持與支援的早期版本的向後相容性</span><span class="sxs-lookup"><span data-stu-id="5def6-111">Extensions for Office Communications Server 2007 and Office Communications Server 2007 R2 classes to maintain backward compatibility with supported previous versions</span></span>

<!-- end list -->

  - <span data-ttu-id="5def6-112">**資料**（儲存在 Lync Server 擴展架構和現有的架構類別中）：</span><span class="sxs-lookup"><span data-stu-id="5def6-112">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="5def6-113">使用者 SIP 統一資源識別項（URI）及其他使用者設定</span><span class="sxs-lookup"><span data-stu-id="5def6-113">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="5def6-114">回應群組和會議助理等應用程式的連絡人物件</span><span class="sxs-lookup"><span data-stu-id="5def6-114">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="5def6-115">指向中央管理存放區的指標</span><span class="sxs-lookup"><span data-stu-id="5def6-115">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="5def6-116">Kerberos 驗證帳戶（選擇性電腦物件）</span><span class="sxs-lookup"><span data-stu-id="5def6-116">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="5def6-117">本主題說明 Lync Server 2013 所需的 Active Directory 架構變更。</span><span class="sxs-lookup"><span data-stu-id="5def6-117">This topic describes the Active Directory schema changes required by Lync Server 2013.</span></span> <span data-ttu-id="5def6-118">它不會說明舊版 Office 通訊伺服器所引入的架構變更。</span><span class="sxs-lookup"><span data-stu-id="5def6-118">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="5def6-119">如需類別及其描述的清單，請參閱[Lync Server 2013 中的架構類別與說明](lync-server-2013-schema-classes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="5def6-119">For a list of classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="5def6-120">如需屬性及其描述的清單，請參閱[Lync Server 2013 中的架構屬性及描述](lync-server-2013-schema-attributes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="5def6-120">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="5def6-121">如需具有它們可能包含之屬性的類別清單，請參閱[Lync Server 2013 中的類別的架構屬性](lync-server-2013-schema-attributes-by-class.md)。</span><span class="sxs-lookup"><span data-stu-id="5def6-121">For a list of classes with the attributes they may contain, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span>

<span data-ttu-id="5def6-122">MsRTCSIP 首碼會識別 Lync Server 專用的類別和屬性。</span><span class="sxs-lookup"><span data-stu-id="5def6-122">The msRTCSIP prefix identifies classes and attributes that are specific to Lync Server.</span></span>

<div>

## <a name="new-active-directory-attributes"></a><span data-ttu-id="5def6-123">新的 Active Directory 屬性</span><span class="sxs-lookup"><span data-stu-id="5def6-123">New Active Directory Attributes</span></span>

<span data-ttu-id="5def6-124">下表說明 Lync Server 2013 新增的 Active Directory 屬性。</span><span class="sxs-lookup"><span data-stu-id="5def6-124">The following table describes the Active Directory attributes that are added by Lync Server 2013.</span></span>

### <a name="attributes-added-by-lync-server-2013"></a><span data-ttu-id="5def6-125">Lync Server 2013 新增的屬性</span><span class="sxs-lookup"><span data-stu-id="5def6-125">Attributes Added by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5def6-126">Attribute</span><span class="sxs-lookup"><span data-stu-id="5def6-126">Attribute</span></span></th>
<th><span data-ttu-id="5def6-127">說明</span><span class="sxs-lookup"><span data-stu-id="5def6-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5def6-128">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="5def6-128">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="5def6-129">這個多重值屬性包含適用于使用者的保留原則的識別碼。</span><span class="sxs-lookup"><span data-stu-id="5def6-129">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="5def6-130">保留原則在保留期間保留使用者的信箱專案。</span><span class="sxs-lookup"><span data-stu-id="5def6-130">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="5def6-131">這個屬性是與 Exchange 2013 共用的。</span><span class="sxs-lookup"><span data-stu-id="5def6-131">This attribute is shared with Exchange 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5def6-132">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="5def6-132">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="5def6-133">這是 SIP 路由群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="5def6-133">This is the SIP routing group ID.</span></span> <span data-ttu-id="5def6-134">相同群組中的使用者會註冊到相同的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="5def6-134">Users in the same group will register to the same Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5def6-135">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="5def6-135">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="5def6-136">這個屬性是用來儲存前端池所使用的鏡像 SQL Server 後端。</span><span class="sxs-lookup"><span data-stu-id="5def6-136">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a><span data-ttu-id="5def6-137">已修改的 Active Directory 類別</span><span class="sxs-lookup"><span data-stu-id="5def6-137">Modified Active Directory Classes</span></span>

<span data-ttu-id="5def6-138">下表說明 Lync Server 2013 修改的 Active Directory 類別。</span><span class="sxs-lookup"><span data-stu-id="5def6-138">The following table describes the Active Directory classes that are modified by Lync Server 2013.</span></span>

### <a name="classes-modified-by-lync-server-2013"></a><span data-ttu-id="5def6-139">Lync Server 2013 修改的類別</span><span class="sxs-lookup"><span data-stu-id="5def6-139">Classes Modified by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5def6-140">靜態類</span><span class="sxs-lookup"><span data-stu-id="5def6-140">Class</span></span></th>
<th><span data-ttu-id="5def6-141">切換</span><span class="sxs-lookup"><span data-stu-id="5def6-141">Change</span></span></th>
<th><span data-ttu-id="5def6-142">類別或屬性</span><span class="sxs-lookup"><span data-stu-id="5def6-142">Class or Attribute</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5def6-143">使用者</span><span class="sxs-lookup"><span data-stu-id="5def6-143">User</span></span></p></td>
<td><p><span data-ttu-id="5def6-144">新增： mayContain</span><span class="sxs-lookup"><span data-stu-id="5def6-144">add: mayContain</span></span></p>
<p><span data-ttu-id="5def6-145">新增： mayContain</span><span class="sxs-lookup"><span data-stu-id="5def6-145">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="5def6-146">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="5def6-146">ProxyAddresses</span></span></p>
<p><span data-ttu-id="5def6-147">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="5def6-147">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5def6-148">資訊</span><span class="sxs-lookup"><span data-stu-id="5def6-148">Contact</span></span></p></td>
<td><p><span data-ttu-id="5def6-149">新增： mayContain</span><span class="sxs-lookup"><span data-stu-id="5def6-149">add: mayContain</span></span></p>
<p><span data-ttu-id="5def6-150">新增： mayContain</span><span class="sxs-lookup"><span data-stu-id="5def6-150">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="5def6-151">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="5def6-151">ProxyAddresses</span></span></p>
<p><span data-ttu-id="5def6-152">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="5def6-152">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5def6-153">郵件-收件者</span><span class="sxs-lookup"><span data-stu-id="5def6-153">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="5def6-154">新增： mayContain</span><span class="sxs-lookup"><span data-stu-id="5def6-154">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="5def6-155">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="5def6-155">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5def6-156">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="5def6-156">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="5def6-157">新增： mayContain</span><span class="sxs-lookup"><span data-stu-id="5def6-157">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="5def6-158">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="5def6-158">msRTCSIP-MirrorBackEndServer</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

