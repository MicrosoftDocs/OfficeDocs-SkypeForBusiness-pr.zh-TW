---
title: 封存原則建立新的或編輯現有
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
description: 您可以使用封存原則，針對駐留在商務用 Skype Server 上的使用者，控制部署中內部和外部通訊的封存。 封存原則包含全域原則，並選擇性地包含一或多個網站與使用者原則：
ms.openlocfilehash: 9c852c592776f9e529c11dd46272715af52e8111
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826963"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a><span data-ttu-id="deb3c-104">封存原則：建立新的或編輯現有原則</span><span class="sxs-lookup"><span data-stu-id="deb3c-104">Archiving Policy: Create New or Edit Existing</span></span>
 
<span data-ttu-id="deb3c-105">您可以使用封存原則，針對駐留在商務用 Skype Server 上的使用者，控制部署中內部和外部通訊的封存。</span><span class="sxs-lookup"><span data-stu-id="deb3c-105">You use Archiving policies to control archiving of internal and external communications in your deployment for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="deb3c-106">封存原則包含全域原則，並選擇性地包含一或多個網站與使用者原則：</span><span class="sxs-lookup"><span data-stu-id="deb3c-106">Archiving policies include the global policy, and, optionally, one or more site and user policies:</span></span>
  
- <span data-ttu-id="deb3c-107">**全域原則** 預設會在所有商務用 Skype Server 部署中建立全域原則。</span><span class="sxs-lookup"><span data-stu-id="deb3c-107">**Global policy** The global policy is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="deb3c-108">您可以編輯全域原則，但無法刪除此原則。</span><span class="sxs-lookup"><span data-stu-id="deb3c-108">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="deb3c-109">若嘗試將其刪除，所有選項都會重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="deb3c-109">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="deb3c-110">**網站原則 (選用)** 您可以指定一或多個網站封存原則，每個網站封存原則都可以設定為啟用和停用特定網站的內部或外部通訊的封存。</span><span class="sxs-lookup"><span data-stu-id="deb3c-110">**Site policies (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific site.</span></span> <span data-ttu-id="deb3c-111">網站原則會覆寫全域原則，但僅限於封存原則中指定的網站。</span><span class="sxs-lookup"><span data-stu-id="deb3c-111">A site policy overrides the global policy, but only for the sites specified in Archiving policies.</span></span> <span data-ttu-id="deb3c-112">您可以編輯或刪除網站原則。</span><span class="sxs-lookup"><span data-stu-id="deb3c-112">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="deb3c-113">**使用者原則 (選用)** 您可以指定一或多個使用者封存原則，每個使用者封存原則都可以設定為針對特定使用者，啟用和停用內部或外部通訊的封存。</span><span class="sxs-lookup"><span data-stu-id="deb3c-113">**User policies (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving for internal or external communications for a specific user.</span></span> <span data-ttu-id="deb3c-114">使用者原則會覆寫全域原則及網站原則，但僅限於您指派使用者原則的使用者 (s) 。</span><span class="sxs-lookup"><span data-stu-id="deb3c-114">A user policy overrides the global policy and site policies, but only for the user(s) to whom you assign a user policy.</span></span> <span data-ttu-id="deb3c-115">您可以編輯或刪除使用者原則。</span><span class="sxs-lookup"><span data-stu-id="deb3c-115">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="deb3c-116">如果您使用 Exchange 整合將封存資料儲存在 Microsoft Exchange 中，Exchange 2013 原則會控制位於 Exchange 2013 之使用者的封存。</span><span class="sxs-lookup"><span data-stu-id="deb3c-116">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange 2013 policies control archiving for users homed on Exchange 2013.</span></span> <span data-ttu-id="deb3c-117">若要為這些使用者啟用封存，使用者的信箱必須置於 In-Place 保留狀態。</span><span class="sxs-lookup"><span data-stu-id="deb3c-117">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="deb3c-118">若要設定新的或現有的封存原則設定，請指定下列選項：</span><span class="sxs-lookup"><span data-stu-id="deb3c-118">To configure the settings for a new or existing Archiving policy, you specify the following options:</span></span>
- <span data-ttu-id="deb3c-119">**名稱** 每個封存原則都需要一個名稱。</span><span class="sxs-lookup"><span data-stu-id="deb3c-119">**Name** Each Archiving policy requires a name.</span></span> <span data-ttu-id="deb3c-120">其名稱取決於您要新增或編輯的原則類型：</span><span class="sxs-lookup"><span data-stu-id="deb3c-120">The name is determined by the type of policy that you are adding or editing:</span></span>
    
  - <span data-ttu-id="deb3c-121">**全域原則** 預設名稱為 Global。</span><span class="sxs-lookup"><span data-stu-id="deb3c-121">**Global policy** The default name is Global.</span></span> <span data-ttu-id="deb3c-122">您可以將它變更為更具描述性的名稱。</span><span class="sxs-lookup"><span data-stu-id="deb3c-122">You can change it to a more descriptive name.</span></span> <span data-ttu-id="deb3c-123">例如：Contoso 北美組織。</span><span class="sxs-lookup"><span data-stu-id="deb3c-123">For example, Contoso North American Organization.</span></span>
    
  - <span data-ttu-id="deb3c-124">**網站原則** 此對話方塊中所列的網站包含部署中所有可用的網站。</span><span class="sxs-lookup"><span data-stu-id="deb3c-124">**Site policy** The sites listed in this dialog box include all available sites in your deployment.</span></span> <span data-ttu-id="deb3c-125">按一下某一個網站即可加以選取。</span><span class="sxs-lookup"><span data-stu-id="deb3c-125">Click a single site to select it.</span></span> <span data-ttu-id="deb3c-126">例如：Redmond 資料中心。</span><span class="sxs-lookup"><span data-stu-id="deb3c-126">For example, Redmond Data Center.</span></span>
    
  - <span data-ttu-id="deb3c-127">**使用者原則** 指定適當的名稱，例如特定使用者的名稱，或組織中使用者群組或小組的名稱。</span><span class="sxs-lookup"><span data-stu-id="deb3c-127">**User policy** Specify an appropriate name, such as the name of a specific user or the name of a user group or team in your organization.</span></span> <span data-ttu-id="deb3c-128">例如法律部門。</span><span class="sxs-lookup"><span data-stu-id="deb3c-128">For example, Legal Department.</span></span>
    
- <span data-ttu-id="deb3c-129">**描述** 這是選用的。</span><span class="sxs-lookup"><span data-stu-id="deb3c-129">**Description** This is optional.</span></span> <span data-ttu-id="deb3c-130">使用它來提供其他詳細資料，例如原則的範圍或用法。</span><span class="sxs-lookup"><span data-stu-id="deb3c-130">Use it to provide additional details, such as the scope or use of the policy.</span></span> <span data-ttu-id="deb3c-131">例如，與其他網站的法律部門進行協調。</span><span class="sxs-lookup"><span data-stu-id="deb3c-131">For example, Coordinate with Legal Departments of Other Sites.</span></span>
    
- <span data-ttu-id="deb3c-132">封存 **內部通訊** 選取此核取方塊以啟用內部網路上的通訊的封存。</span><span class="sxs-lookup"><span data-stu-id="deb3c-132">**Archive internal communications** Select this check box to enable archiving of communications on your internal network.</span></span> <span data-ttu-id="deb3c-133">根據預設，不會在任何原則中啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="deb3c-133">By default, this is not enabled in any policy.</span></span>
    
- <span data-ttu-id="deb3c-134">封存 **外部通訊** 選取此核取方塊可啟用包含外部使用者（例如遠端使用者）的通訊封存， (包括匿名和 PIC 使用者) 及同盟協力廠商。</span><span class="sxs-lookup"><span data-stu-id="deb3c-134">**Archive external communications** Select this check box to enable archiving of communications that include external users, such as remote users, (including anonymous and PIC-setting users), and federated partners.</span></span> <span data-ttu-id="deb3c-135">根據預設，不會在任何原則中啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="deb3c-135">By default, this is not enabled in any policy.</span></span>
    
<span data-ttu-id="deb3c-136">如需有關封存功能及功能（包括 Exchange 整合）的詳細資訊，請參閱 [在商務用 skype 2015 server 中規劃](../../plan-your-deployment/archiving/archiving.md)封存、 [部署商務用 skype server 2015](../../deploy/deploy-archiving/deploy-archiving.md)的封存，以及 [管理商務用 skype server 2015 中](../../manage/archiving/archiving.md)的封存。</span><span class="sxs-lookup"><span data-stu-id="deb3c-136">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

