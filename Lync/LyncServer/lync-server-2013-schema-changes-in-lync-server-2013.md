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
ms.openlocfilehash: 1c3733eee90fb1ea0bb3e0a67be88243dee56aa7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510780"
---
# <a name="schema-changes-in-lync-server-2013"></a><span data-ttu-id="d14c2-102">Lync Server 2013 中的架構變更</span><span class="sxs-lookup"><span data-stu-id="d14c2-102">Schema changes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d14c2-103">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="d14c2-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="d14c2-104">在您部署及操作 Lync Server 2013 之前，您必須透過擴充架構來準備 Active Directory 網域服務。</span><span class="sxs-lookup"><span data-stu-id="d14c2-104">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="d14c2-105">架構擴充新增了 Lync Server 2013 所需的類別和屬性。</span><span class="sxs-lookup"><span data-stu-id="d14c2-105">The schema extensions add the classes and attributes that are required by Lync Server 2013.</span></span>

<span data-ttu-id="d14c2-106">Lync Server 2013 需要數個新的類別和屬性，並修改一些現有的類別和屬性。</span><span class="sxs-lookup"><span data-stu-id="d14c2-106">Lync Server 2013 requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="d14c2-107">此外，Lync Server 2013 的大部分設定資訊都會儲存在中央管理存放區，而不是在 AD DS 中，就像先前的版本一樣。</span><span class="sxs-lookup"><span data-stu-id="d14c2-107">In addition, much configuration information for Lync Server 2013 is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="d14c2-108">下列資訊仍儲存在 Lync Server 2013 的 AD DS 中：</span><span class="sxs-lookup"><span data-stu-id="d14c2-108">The following information is still stored in AD DS in Lync Server 2013:</span></span>

  - <span data-ttu-id="d14c2-109">**架構擴充**：</span><span class="sxs-lookup"><span data-stu-id="d14c2-109">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="d14c2-110">使用者物件擴充</span><span class="sxs-lookup"><span data-stu-id="d14c2-110">User object extensions</span></span>
    
      - <span data-ttu-id="d14c2-111">Office 通訊伺服器2007和 Office 通訊伺服器 2007 R2 類別的分機，以維持與支援的舊版的回溯相容性</span><span class="sxs-lookup"><span data-stu-id="d14c2-111">Extensions for Office Communications Server 2007 and Office Communications Server 2007 R2 classes to maintain backward compatibility with supported previous versions</span></span>

<!-- end list -->

  - <span data-ttu-id="d14c2-112">儲存在 Lync Server 擴充架構和現有架構類別中的**資料** () ：</span><span class="sxs-lookup"><span data-stu-id="d14c2-112">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="d14c2-113">使用者 SIP 統一資源識別項 (URI) 和其他使用者設定</span><span class="sxs-lookup"><span data-stu-id="d14c2-113">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="d14c2-114">回應群組和會議助理等應用程式的連絡人物件</span><span class="sxs-lookup"><span data-stu-id="d14c2-114">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="d14c2-115">中央管理存放區的指標</span><span class="sxs-lookup"><span data-stu-id="d14c2-115">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="d14c2-116">Kerberos 驗證帳戶 (選用的電腦物件) </span><span class="sxs-lookup"><span data-stu-id="d14c2-116">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="d14c2-117">本主題說明 Lync Server 2013 所需的 Active Directory 架構變更。</span><span class="sxs-lookup"><span data-stu-id="d14c2-117">This topic describes the Active Directory schema changes required by Lync Server 2013.</span></span> <span data-ttu-id="d14c2-118">它不會描述先前版本的 Office 通訊伺服器所引進的架構變更。</span><span class="sxs-lookup"><span data-stu-id="d14c2-118">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="d14c2-119">如需類別及其描述的清單，請參閱 [Lync Server 2013 中的架構類別和描述](lync-server-2013-schema-classes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="d14c2-119">For a list of classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="d14c2-120">如需屬性及其描述的清單，請參閱 [Lync Server 2013 中的架構屬性和描述](lync-server-2013-schema-attributes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="d14c2-120">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="d14c2-121">如需其屬性可能包含的類別清單，請參閱 [在 Lync Server 2013 中依類別的架構屬性](lync-server-2013-schema-attributes-by-class.md)。</span><span class="sxs-lookup"><span data-stu-id="d14c2-121">For a list of classes with the attributes they may contain, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span>

<span data-ttu-id="d14c2-122">MsRTCSIP 首碼可識別 Lync Server 專用的類別和屬性。</span><span class="sxs-lookup"><span data-stu-id="d14c2-122">The msRTCSIP prefix identifies classes and attributes that are specific to Lync Server.</span></span>

<div>

## <a name="new-active-directory-attributes"></a><span data-ttu-id="d14c2-123">新的 Active Directory 屬性</span><span class="sxs-lookup"><span data-stu-id="d14c2-123">New Active Directory Attributes</span></span>

<span data-ttu-id="d14c2-124">下表說明 Lync Server 2013 新增的 Active Directory 屬性。</span><span class="sxs-lookup"><span data-stu-id="d14c2-124">The following table describes the Active Directory attributes that are added by Lync Server 2013.</span></span>

### <a name="attributes-added-by-lync-server-2013"></a><span data-ttu-id="d14c2-125">Lync Server 2013 新增的屬性</span><span class="sxs-lookup"><span data-stu-id="d14c2-125">Attributes Added by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d14c2-126">屬性</span><span class="sxs-lookup"><span data-stu-id="d14c2-126">Attribute</span></span></th>
<th><span data-ttu-id="d14c2-127">描述</span><span class="sxs-lookup"><span data-stu-id="d14c2-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d14c2-128">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="d14c2-128">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="d14c2-129">此多重值屬性包含適用于使用者之保留原則的識別碼。</span><span class="sxs-lookup"><span data-stu-id="d14c2-129">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="d14c2-130">保留原則會在保留期間保留使用者的信箱專案。</span><span class="sxs-lookup"><span data-stu-id="d14c2-130">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="d14c2-131">此屬性與 Exchange 2013 共用。</span><span class="sxs-lookup"><span data-stu-id="d14c2-131">This attribute is shared with Exchange 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d14c2-132">msRTCSIP UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="d14c2-132">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="d14c2-133">這是 SIP 路由群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="d14c2-133">This is the SIP routing group ID.</span></span> <span data-ttu-id="d14c2-134">相同群組中的使用者會註冊到同一個前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="d14c2-134">Users in the same group will register to the same Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d14c2-135">msRTCSIP MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="d14c2-135">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="d14c2-136">此屬性用來儲存前端集區所使用的鏡像 SQL Server 後端。</span><span class="sxs-lookup"><span data-stu-id="d14c2-136">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a><span data-ttu-id="d14c2-137">修改的 Active Directory 類別</span><span class="sxs-lookup"><span data-stu-id="d14c2-137">Modified Active Directory Classes</span></span>

<span data-ttu-id="d14c2-138">下表說明 Lync Server 2013 修改的 Active Directory 類別。</span><span class="sxs-lookup"><span data-stu-id="d14c2-138">The following table describes the Active Directory classes that are modified by Lync Server 2013.</span></span>

### <a name="classes-modified-by-lync-server-2013"></a><span data-ttu-id="d14c2-139">Lync Server 2013 修改的類別</span><span class="sxs-lookup"><span data-stu-id="d14c2-139">Classes Modified by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d14c2-140">類別</span><span class="sxs-lookup"><span data-stu-id="d14c2-140">Class</span></span></th>
<th><span data-ttu-id="d14c2-141">變更</span><span class="sxs-lookup"><span data-stu-id="d14c2-141">Change</span></span></th>
<th><span data-ttu-id="d14c2-142">類別或屬性</span><span class="sxs-lookup"><span data-stu-id="d14c2-142">Class or Attribute</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d14c2-143">使用者</span><span class="sxs-lookup"><span data-stu-id="d14c2-143">User</span></span></p></td>
<td><p><span data-ttu-id="d14c2-144">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="d14c2-144">add: mayContain</span></span></p>
<p><span data-ttu-id="d14c2-145">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="d14c2-145">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="d14c2-146">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="d14c2-146">ProxyAddresses</span></span></p>
<p><span data-ttu-id="d14c2-147">msRTCSIP UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="d14c2-147">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d14c2-148">連絡人</span><span class="sxs-lookup"><span data-stu-id="d14c2-148">Contact</span></span></p></td>
<td><p><span data-ttu-id="d14c2-149">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="d14c2-149">add: mayContain</span></span></p>
<p><span data-ttu-id="d14c2-150">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="d14c2-150">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="d14c2-151">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="d14c2-151">ProxyAddresses</span></span></p>
<p><span data-ttu-id="d14c2-152">msRTCSIP UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="d14c2-152">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d14c2-153">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="d14c2-153">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="d14c2-154">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="d14c2-154">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="d14c2-155">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="d14c2-155">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d14c2-156">msRTCSIP GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="d14c2-156">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="d14c2-157">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="d14c2-157">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="d14c2-158">msRTCSIP MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="d14c2-158">msRTCSIP-MirrorBackEndServer</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

