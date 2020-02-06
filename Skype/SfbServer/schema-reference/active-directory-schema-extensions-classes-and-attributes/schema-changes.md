---
title: 商務用 Skype Server 中的架構變更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: 在您部署並執行商務用 Skype Server 之前，您必須透過延伸架構來準備 Active Directory 網域服務。 架構延伸會新增商務用 Skype Server 所需的類別和屬性。
ms.openlocfilehash: 0c3765fe36b252cc03218a3fa4365c5cc36c7f48
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815481"
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="bee01-104">商務用 Skype Server 中的架構變更</span><span class="sxs-lookup"><span data-stu-id="bee01-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="bee01-105">在您部署並執行商務用 Skype Server 之前，您必須透過延伸架構來準備 Active Directory 網域服務。</span><span class="sxs-lookup"><span data-stu-id="bee01-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="bee01-106">架構延伸會新增商務用 Skype Server 所需的類別和屬性。</span><span class="sxs-lookup"><span data-stu-id="bee01-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="bee01-107">如果您要從 Lync Server 2013 升級到商務用 Skype Server 2015，則不會進行任何架構變更，因此本文不適用。</span><span class="sxs-lookup"><span data-stu-id="bee01-107">If you are upgrading from Lync Server 2013 to Skype for Business Server 2015, no schema changes are made and therefore this article does not apply.</span></span>
  
<span data-ttu-id="bee01-108">商務用 Skype 伺服器需要幾個新的類別和屬性，並修改一些現有的類別和屬性。</span><span class="sxs-lookup"><span data-stu-id="bee01-108">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="bee01-109">此外，商務用 Skype 伺服器的許多配置資訊會儲存在中央管理儲存區，而不是在 AD DS 中，就像在舊版中一樣。</span><span class="sxs-lookup"><span data-stu-id="bee01-109">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="bee01-110">下列資訊仍會儲存在商務用 Skype Server 的 AD DS 中：</span><span class="sxs-lookup"><span data-stu-id="bee01-110">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="bee01-111">**架構擴充**：</span><span class="sxs-lookup"><span data-stu-id="bee01-111">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="bee01-112">使用者物件延伸</span><span class="sxs-lookup"><span data-stu-id="bee01-112">User object extensions</span></span>
    
  - <span data-ttu-id="bee01-113">類別延伸與支援的舊版 Lync Server 保持向後相容性。</span><span class="sxs-lookup"><span data-stu-id="bee01-113">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="bee01-114">**資料**（儲存在商務用 Skype Server 延伸架構和現有的架構類別中）：</span><span class="sxs-lookup"><span data-stu-id="bee01-114">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="bee01-115">使用者 SIP 統一資源識別項（URI）及其他使用者設定</span><span class="sxs-lookup"><span data-stu-id="bee01-115">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="bee01-116">回應群組和會議助理等應用程式的連絡人物件</span><span class="sxs-lookup"><span data-stu-id="bee01-116">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="bee01-117">指向中央管理存放區的指標</span><span class="sxs-lookup"><span data-stu-id="bee01-117">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="bee01-118">Kerberos 驗證帳戶（選擇性電腦物件）</span><span class="sxs-lookup"><span data-stu-id="bee01-118">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="bee01-119">本主題描述商務用 Skype Server 所需的 Active Directory 架構變更。</span><span class="sxs-lookup"><span data-stu-id="bee01-119">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="bee01-120">它不會說明舊版 Office 通訊伺服器所引入的架構變更。</span><span class="sxs-lookup"><span data-stu-id="bee01-120">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="bee01-121">如需類別及其描述的清單，請參閱[商務用 Skype Server 中的架構類別和描述](schema-classes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="bee01-121">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="bee01-122">如需屬性及其描述的清單，請參閱[商務用 Skype Server 中的架構屬性及描述](schema-attributes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="bee01-122">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="bee01-123">如需具有它們可能包含之屬性的類別清單，請參閱[商務用 Skype Server 中的班級架構屬性（依類別](schema-attributes-by-class.md)）。</span><span class="sxs-lookup"><span data-stu-id="bee01-123">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="bee01-124">MsRTCSIP 首碼會識別商務用 Skype Server 專用的類別和屬性。</span><span class="sxs-lookup"><span data-stu-id="bee01-124">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="bee01-125">新的 Active Directory 屬性</span><span class="sxs-lookup"><span data-stu-id="bee01-125">New Active Directory Attributes</span></span>

<span data-ttu-id="bee01-126">下表說明商務用 Skype Server 新增的 Active Directory 屬性。</span><span class="sxs-lookup"><span data-stu-id="bee01-126">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="bee01-127">**商務用 Skype Server 新增的屬性**</span><span class="sxs-lookup"><span data-stu-id="bee01-127">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="bee01-128">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="bee01-128">**Attribute**</span></span>|<span data-ttu-id="bee01-129">**說明**</span><span class="sxs-lookup"><span data-stu-id="bee01-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bee01-130">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="bee01-130">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="bee01-131">這個多重值屬性包含適用于使用者的保留原則的識別碼。</span><span class="sxs-lookup"><span data-stu-id="bee01-131">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="bee01-132">保留原則在保留期間保留使用者的信箱專案。</span><span class="sxs-lookup"><span data-stu-id="bee01-132">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="bee01-133">這個屬性是與 Exchange 2013 共用的。</span><span class="sxs-lookup"><span data-stu-id="bee01-133">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="bee01-134">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="bee01-134">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="bee01-135">這是 SIP 路由群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="bee01-135">This is the SIP routing group ID.</span></span> <span data-ttu-id="bee01-136">相同群組中的使用者會註冊到相同的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="bee01-136">Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="bee01-137">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="bee01-137">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="bee01-138">這個屬性是用來儲存前端池所使用的鏡像 SQL Server 後端。</span><span class="sxs-lookup"><span data-stu-id="bee01-138">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="bee01-139">已修改的 Active Directory 類別</span><span class="sxs-lookup"><span data-stu-id="bee01-139">Modified Active Directory Classes</span></span>

<span data-ttu-id="bee01-140">下表說明商務用 Skype Server 所修改的 Active Directory 類別。</span><span class="sxs-lookup"><span data-stu-id="bee01-140">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="bee01-141">**商務用 Skype Server 修改的類別**</span><span class="sxs-lookup"><span data-stu-id="bee01-141">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="bee01-142">**靜態類**</span><span class="sxs-lookup"><span data-stu-id="bee01-142">**Class**</span></span>|<span data-ttu-id="bee01-143">**切換**</span><span class="sxs-lookup"><span data-stu-id="bee01-143">**Change**</span></span>|<span data-ttu-id="bee01-144">**類別或屬性**</span><span class="sxs-lookup"><span data-stu-id="bee01-144">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bee01-145">使用者</span><span class="sxs-lookup"><span data-stu-id="bee01-145">User</span></span>  <br/> |<span data-ttu-id="bee01-146">新增： mayContain</span><span class="sxs-lookup"><span data-stu-id="bee01-146">add: mayContain</span></span>  <br/> <span data-ttu-id="bee01-147">新增： mayContain</span><span class="sxs-lookup"><span data-stu-id="bee01-147">add: mayContain</span></span>  <br/> |<span data-ttu-id="bee01-148">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="bee01-148">ProxyAddresses</span></span>  <br/> <span data-ttu-id="bee01-149">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="bee01-149">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="bee01-150">資訊</span><span class="sxs-lookup"><span data-stu-id="bee01-150">Contact</span></span>  <br/> |<span data-ttu-id="bee01-151">新增： mayContain</span><span class="sxs-lookup"><span data-stu-id="bee01-151">add: mayContain</span></span>  <br/> <span data-ttu-id="bee01-152">新增： mayContain</span><span class="sxs-lookup"><span data-stu-id="bee01-152">add: mayContain</span></span>  <br/> |<span data-ttu-id="bee01-153">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="bee01-153">ProxyAddresses</span></span>  <br/> <span data-ttu-id="bee01-154">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="bee01-154">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="bee01-155">郵件-收件者</span><span class="sxs-lookup"><span data-stu-id="bee01-155">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="bee01-156">新增： mayContain</span><span class="sxs-lookup"><span data-stu-id="bee01-156">add: mayContain</span></span>  <br/> |<span data-ttu-id="bee01-157">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="bee01-157">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="bee01-158">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="bee01-158">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="bee01-159">新增： mayContain</span><span class="sxs-lookup"><span data-stu-id="bee01-159">add: mayContain</span></span>  <br/> |<span data-ttu-id="bee01-160">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="bee01-160">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

