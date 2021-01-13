---
title: 商務用 Skype Server 中的架構變更
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: 在您部署及操作商務用 Skype Server 之前，您必須透過擴充架構來準備 Active Directory 網域服務。 架構擴充新增商務用 Skype Server 所需的類別和屬性。
ms.openlocfilehash: 4ca18b0ccfde6b247f1c29e140004804462d0f56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813573"
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="76030-104">商務用 Skype Server 中的架構變更</span><span class="sxs-lookup"><span data-stu-id="76030-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="76030-105">在您部署及操作商務用 Skype Server 之前，您必須透過擴充架構來準備 Active Directory 網域服務。</span><span class="sxs-lookup"><span data-stu-id="76030-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="76030-106">架構擴充新增商務用 Skype Server 所需的類別和屬性。</span><span class="sxs-lookup"><span data-stu-id="76030-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="76030-107">如果您是從 Lync Server 2013 升級至商務用 Skype Server 2015，則不會進行任何架構變更，因此不會套用這篇文章。</span><span class="sxs-lookup"><span data-stu-id="76030-107">If you are upgrading from Lync Server 2013 to Skype for Business Server 2015, no schema changes are made and therefore this article does not apply.</span></span>
  
<span data-ttu-id="76030-108">商務用 Skype 伺服器需要數個新的類別和屬性，並修改一些現有的類別和屬性。</span><span class="sxs-lookup"><span data-stu-id="76030-108">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="76030-109">此外，商務用 Skype 伺服器的大部分設定資訊都會儲存在中央管理存放區，而不是 AD DS 中，就像先前的版本一樣。</span><span class="sxs-lookup"><span data-stu-id="76030-109">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="76030-110">下列資訊仍儲存在 AD DS 中的商務用 Skype Server 中：</span><span class="sxs-lookup"><span data-stu-id="76030-110">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="76030-111">**架構擴充**：</span><span class="sxs-lookup"><span data-stu-id="76030-111">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="76030-112">使用者物件擴充</span><span class="sxs-lookup"><span data-stu-id="76030-112">User object extensions</span></span>
    
  - <span data-ttu-id="76030-113">用於維護與支援之舊版 Lync Server 的回溯相容性的類別擴充。</span><span class="sxs-lookup"><span data-stu-id="76030-113">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="76030-114">儲存在商務用 Skype Server 擴充架構和現有架構類別中的 **資料** () ：</span><span class="sxs-lookup"><span data-stu-id="76030-114">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="76030-115">使用者 SIP 統一資源識別項 (URI) 和其他使用者設定</span><span class="sxs-lookup"><span data-stu-id="76030-115">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="76030-116">回應群組和會議助理等應用程式的連絡人物件</span><span class="sxs-lookup"><span data-stu-id="76030-116">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="76030-117">中央管理存放區的指標</span><span class="sxs-lookup"><span data-stu-id="76030-117">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="76030-118">Kerberos 驗證帳戶 (選用的電腦物件) </span><span class="sxs-lookup"><span data-stu-id="76030-118">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="76030-119">本主題說明商務用 Skype Server 所需的 Active Directory 架構變更。</span><span class="sxs-lookup"><span data-stu-id="76030-119">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="76030-120">它不會描述先前版本的 Office 通訊伺服器所引進的架構變更。</span><span class="sxs-lookup"><span data-stu-id="76030-120">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="76030-121">如需類別及其描述的清單，請參閱 [在商務用 Skype Server 中的架構類別和描述](schema-classes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="76030-121">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="76030-122">如需屬性及其描述的清單，請參閱 [商務用 Skype Server 中的架構屬性和描述](schema-attributes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="76030-122">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="76030-123">如需其屬性可能包含的類別清單，請參閱 [在商務用 Skype Server 中的類別架構屬性依類別](schema-attributes-by-class.md)。</span><span class="sxs-lookup"><span data-stu-id="76030-123">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="76030-124">MsRTCSIP 首碼可識別商務用 Skype Server 專用的類別和屬性。</span><span class="sxs-lookup"><span data-stu-id="76030-124">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="76030-125">新的 Active Directory 屬性</span><span class="sxs-lookup"><span data-stu-id="76030-125">New Active Directory Attributes</span></span>

<span data-ttu-id="76030-126">下表說明商務用 Skype Server 新增的 Active Directory 屬性。</span><span class="sxs-lookup"><span data-stu-id="76030-126">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="76030-127">**商務用 Skype Server 新增的屬性**</span><span class="sxs-lookup"><span data-stu-id="76030-127">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="76030-128">**屬性**</span><span class="sxs-lookup"><span data-stu-id="76030-128">**Attribute**</span></span>|<span data-ttu-id="76030-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="76030-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="76030-130">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="76030-130">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="76030-131">此多重值屬性包含適用于使用者之保留原則的識別碼。</span><span class="sxs-lookup"><span data-stu-id="76030-131">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="76030-132">保留原則會在保留期間保留使用者的信箱專案。</span><span class="sxs-lookup"><span data-stu-id="76030-132">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="76030-133">此屬性與 Exchange 2013 共用。</span><span class="sxs-lookup"><span data-stu-id="76030-133">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="76030-134">msRTCSIP UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="76030-134">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="76030-135">這是 SIP 路由群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="76030-135">This is the SIP routing group ID.</span></span> <span data-ttu-id="76030-136">相同群組中的使用者會註冊到同一個前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="76030-136">Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="76030-137">msRTCSIP MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="76030-137">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="76030-138">此屬性用來儲存前端集區所使用的鏡像 SQL Server 後端。</span><span class="sxs-lookup"><span data-stu-id="76030-138">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="76030-139">修改的 Active Directory 類別</span><span class="sxs-lookup"><span data-stu-id="76030-139">Modified Active Directory Classes</span></span>

<span data-ttu-id="76030-140">下表說明商務用 Skype Server 所修改的 Active Directory 類別。</span><span class="sxs-lookup"><span data-stu-id="76030-140">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="76030-141">**商務用 Skype Server 修改的類別**</span><span class="sxs-lookup"><span data-stu-id="76030-141">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="76030-142">**類別**</span><span class="sxs-lookup"><span data-stu-id="76030-142">**Class**</span></span>|<span data-ttu-id="76030-143">**變更**</span><span class="sxs-lookup"><span data-stu-id="76030-143">**Change**</span></span>|<span data-ttu-id="76030-144">**類別或屬性**</span><span class="sxs-lookup"><span data-stu-id="76030-144">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="76030-145">使用者</span><span class="sxs-lookup"><span data-stu-id="76030-145">User</span></span>  <br/> |<span data-ttu-id="76030-146">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="76030-146">add: mayContain</span></span>  <br/> <span data-ttu-id="76030-147">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="76030-147">add: mayContain</span></span>  <br/> |<span data-ttu-id="76030-148">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="76030-148">ProxyAddresses</span></span>  <br/> <span data-ttu-id="76030-149">msRTCSIP UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="76030-149">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="76030-150">連絡人</span><span class="sxs-lookup"><span data-stu-id="76030-150">Contact</span></span>  <br/> |<span data-ttu-id="76030-151">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="76030-151">add: mayContain</span></span>  <br/> <span data-ttu-id="76030-152">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="76030-152">add: mayContain</span></span>  <br/> |<span data-ttu-id="76030-153">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="76030-153">ProxyAddresses</span></span>  <br/> <span data-ttu-id="76030-154">msRTCSIP UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="76030-154">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="76030-155">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="76030-155">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="76030-156">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="76030-156">add: mayContain</span></span>  <br/> |<span data-ttu-id="76030-157">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="76030-157">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="76030-158">msRTCSIP GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="76030-158">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="76030-159">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="76030-159">add: mayContain</span></span>  <br/> |<span data-ttu-id="76030-160">msRTCSIP MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="76030-160">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

