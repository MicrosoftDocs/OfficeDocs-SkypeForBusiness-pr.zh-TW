---
title: 存檔原則建立新的或編輯現有的
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
ROBOTS: NOINDEX, NOFOLLOW
description: 您可以在部署中，針對駐留在商務用 Skype Server 上的使用者，使用封存原則來控制內部與外部通訊的存檔。 封存原則包含全域原則，以及一或多個網站與使用者原則 (後者並非必要)：
ms.openlocfilehash: 1eb1f0060e80fbb7d325f5fbe1b7a247d6d006b6
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691217"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a><span data-ttu-id="76168-104">封存原則：建立新的或編輯現有</span><span class="sxs-lookup"><span data-stu-id="76168-104">Archiving Policy: Create New or Edit Existing</span></span>
 
<span data-ttu-id="76168-105">您可以在部署中，針對駐留在商務用 Skype Server 上的使用者，使用封存原則來控制內部與外部通訊的存檔。</span><span class="sxs-lookup"><span data-stu-id="76168-105">You use Archiving policies to control archiving of internal and external communications in your deployment for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="76168-106">封存原則包含全域原則，以及一或多個網站與使用者原則 (後者並非必要)：</span><span class="sxs-lookup"><span data-stu-id="76168-106">Archiving policies include the global policy, and, optionally, one or more site and user policies:</span></span>
  
- <span data-ttu-id="76168-107">**全域原則**預設會在所有商務用 Skype Server 部署中建立全域原則。</span><span class="sxs-lookup"><span data-stu-id="76168-107">**Global policy** The global policy is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="76168-108">您可以編輯全域原則，但無法刪除此原則。</span><span class="sxs-lookup"><span data-stu-id="76168-108">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="76168-109">如果嘗試刪除此原則，所有選項都會重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="76168-109">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="76168-110">**網站原則（選用）** 您可以指定一或多個網站封存策略，每個原則都可以設定為啟用和停用特定網站的內部或外部通訊的歸檔。</span><span class="sxs-lookup"><span data-stu-id="76168-110">**Site policies (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific site.</span></span> <span data-ttu-id="76168-111">網站原則會覆寫全域原則，但僅限於封存原則中指定的網站。</span><span class="sxs-lookup"><span data-stu-id="76168-111">A site policy overrides the global policy, but only for the sites specified in Archiving policies.</span></span> <span data-ttu-id="76168-112">您可以編輯或刪除網站原則。</span><span class="sxs-lookup"><span data-stu-id="76168-112">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="76168-113">**使用者原則（選用）** 您可以指定一或多個使用者存檔原則，每個策略都可以設定為啟用和停用針對特定使用者進行內部或外部通訊的封存。</span><span class="sxs-lookup"><span data-stu-id="76168-113">**User policies (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving for internal or external communications for a specific user.</span></span> <span data-ttu-id="76168-114">使用者原則會覆寫全域原則及網站原則，但僅限於獲得您指派使用者原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="76168-114">A user policy overrides the global policy and site policies, but only for the user(s) to whom you assign a user policy.</span></span> <span data-ttu-id="76168-115">您可以編輯或刪除使用者原則。</span><span class="sxs-lookup"><span data-stu-id="76168-115">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="76168-116">如果您使用 Exchange 整合來儲存 Microsoft Exchange 中的存檔資料，則 Exchange 原則會控制駐留在 Exchange 的使用者的封存。</span><span class="sxs-lookup"><span data-stu-id="76168-116">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange policies control archiving for users homed on Exchange.</span></span> <span data-ttu-id="76168-117">若要為這些使用者啟用存檔，使用者的信箱必須放在就地保留中。</span><span class="sxs-lookup"><span data-stu-id="76168-117">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="76168-118">若要設定新的或現有的封存原則設定，可指定下列選項：</span><span class="sxs-lookup"><span data-stu-id="76168-118">To configure the settings for a new or existing Archiving policy, you specify the following options:</span></span>
- <span data-ttu-id="76168-119">**名稱**每個存檔原則都需要一個名稱。</span><span class="sxs-lookup"><span data-stu-id="76168-119">**Name** Each Archiving policy requires a name.</span></span> <span data-ttu-id="76168-120">名稱是由您要新增或編輯的原則類型決定：</span><span class="sxs-lookup"><span data-stu-id="76168-120">The name is determined by the type of policy that you are adding or editing:</span></span>
    
  - <span data-ttu-id="76168-121">**全域原則**預設名稱為全域。</span><span class="sxs-lookup"><span data-stu-id="76168-121">**Global policy** The default name is Global.</span></span> <span data-ttu-id="76168-122">您可以將名稱改為更具描述性的名稱。</span><span class="sxs-lookup"><span data-stu-id="76168-122">You can change it to a more descriptive name.</span></span> <span data-ttu-id="76168-123">例如，Contoso 北美組織。</span><span class="sxs-lookup"><span data-stu-id="76168-123">For example, Contoso North American Organization.</span></span>
    
  - <span data-ttu-id="76168-124">**網站原則**此對話方塊中所列的網站包含您部署中所有可用的網站。</span><span class="sxs-lookup"><span data-stu-id="76168-124">**Site policy** The sites listed in this dialog box include all available sites in your deployment.</span></span> <span data-ttu-id="76168-125">按一下某個網站加以選取。</span><span class="sxs-lookup"><span data-stu-id="76168-125">Click a single site to select it.</span></span> <span data-ttu-id="76168-126">例如，Redmond 資料中心。</span><span class="sxs-lookup"><span data-stu-id="76168-126">For example, Redmond Data Center.</span></span>
    
  - <span data-ttu-id="76168-127">**使用者原則**指定適當的名稱，例如特定使用者的名稱，或貴組織中的使用者群組或團隊名稱。</span><span class="sxs-lookup"><span data-stu-id="76168-127">**User policy** Specify an appropriate name, such as the name of a specific user or the name of a user group or team in your organization.</span></span> <span data-ttu-id="76168-128">例如，法務部門。</span><span class="sxs-lookup"><span data-stu-id="76168-128">For example, Legal Department.</span></span>
    
- <span data-ttu-id="76168-129">**描述**這是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="76168-129">**Description** This is optional.</span></span> <span data-ttu-id="76168-130">使用它來提供其他詳細資料，例如原則的範圍或用途。</span><span class="sxs-lookup"><span data-stu-id="76168-130">Use it to provide additional details, such as the scope or use of the policy.</span></span> <span data-ttu-id="76168-131">例如，與其他網站的法律部門共同合作。</span><span class="sxs-lookup"><span data-stu-id="76168-131">For example, Coordinate with Legal Departments of Other Sites.</span></span>
    
- <span data-ttu-id="76168-132">封存**內部通訊**選取此核取方塊以啟用內部網路上的通訊封存。</span><span class="sxs-lookup"><span data-stu-id="76168-132">**Archive internal communications** Select this check box to enable archiving of communications on your internal network.</span></span> <span data-ttu-id="76168-133">根據預設，在任何原則中都不會啟用這項功能。</span><span class="sxs-lookup"><span data-stu-id="76168-133">By default, this is not enabled in any policy.</span></span>
    
- <span data-ttu-id="76168-134">封存**外部通訊**選取此核取方塊以啟用包含外部使用者（例如遠端使用者（包括匿名和 PIC 設定使用者）及聯盟夥伴的通訊的封存。</span><span class="sxs-lookup"><span data-stu-id="76168-134">**Archive external communications** Select this check box to enable archiving of communications that include external users, such as remote users, (including anonymous and PIC-setting users), and federated partners.</span></span> <span data-ttu-id="76168-135">根據預設，在任何原則中都不會啟用這項功能。</span><span class="sxs-lookup"><span data-stu-id="76168-135">By default, this is not enabled in any policy.</span></span>
    
<span data-ttu-id="76168-136">如需有關存檔功能和功能（包括 Exchange 整合）的詳細資料，請參閱[在商務用 Skype server 中進行](../../../plan-your-deployment/archiving/archiving.md)封存、[部署商務用 skype server](../../../deploy/deploy-archiving/deploy-archiving.md)的封存，以及[管理商務用 skype 伺服器](../../../manage/archiving/archiving.md)的封存。</span><span class="sxs-lookup"><span data-stu-id="76168-136">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

