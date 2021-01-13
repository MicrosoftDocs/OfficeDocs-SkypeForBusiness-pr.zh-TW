---
title: 封存組態
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
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: 您可以使用封存設定來控制商務用 Skype Server 部署的封存選項，包含啟用及停用下列選項：
ms.openlocfilehash: 96a01579f43833017978fc6067b5a86f9e9951aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827003"
---
# <a name="archiving-configuration"></a><span data-ttu-id="7c298-103">封存組態</span><span class="sxs-lookup"><span data-stu-id="7c298-103">Archiving Configuration</span></span>
 
<span data-ttu-id="7c298-104">您可以使用封存設定來控制商務用 Skype Server 部署的封存選項，包含啟用及停用下列選項：</span><span class="sxs-lookup"><span data-stu-id="7c298-104">You use Archiving configurations to control archiving options for your Skype for Business Server deployment, including enabling and disabling the following options:</span></span>
  
- <span data-ttu-id="7c298-105">封存失敗時封鎖立即訊息 (IM) 或會議會話</span><span class="sxs-lookup"><span data-stu-id="7c298-105">Blocking of instant messaging (IM) or conferencing sessions if archiving fails</span></span>
    
- <span data-ttu-id="7c298-106">與 Exchange 2013 儲存體整合，供位於 Exchange 2013 的使用者使用</span><span class="sxs-lookup"><span data-stu-id="7c298-106">Integration with Exchange 2013 storage, for users homed on Exchange 2013</span></span>
    
- <span data-ttu-id="7c298-107">清除封存的資料</span><span class="sxs-lookup"><span data-stu-id="7c298-107">Purging of archived data</span></span>
    
<span data-ttu-id="7c298-108">封存設定包括全域設定，以及選擇性地包含一或多個網站與集區封存設定：</span><span class="sxs-lookup"><span data-stu-id="7c298-108">Archiving configurations include the global configuration and, optionally, one or more site and pool Archiving configurations:</span></span>
  
- <span data-ttu-id="7c298-109">**通用** 設定預設會在所有商務用 Skype Server 部署中建立全域設定。</span><span class="sxs-lookup"><span data-stu-id="7c298-109">**Global configuration** The global configuration is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="7c298-110">您可以編輯全域設定，但無法刪除此封存設定。</span><span class="sxs-lookup"><span data-stu-id="7c298-110">You edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="7c298-111">若嘗試將其刪除，所有選項都會重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="7c298-111">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="7c298-112">**網站設定 (選用)** 您可以指定一或多個網站封存設定，每個網站封存設定可用於控制特定網站的封存選項。</span><span class="sxs-lookup"><span data-stu-id="7c298-112">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="7c298-113">網站設定會覆寫全域設定，但僅限於在封存網站設定中指定的網站。</span><span class="sxs-lookup"><span data-stu-id="7c298-113">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="7c298-114">您可以編輯或刪除網站設定。</span><span class="sxs-lookup"><span data-stu-id="7c298-114">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="7c298-115">**集區設定 (選用)** 您可以指定一或多個集區封存設定，以控制特定集區的封存選項。</span><span class="sxs-lookup"><span data-stu-id="7c298-115">**Pool configuration (optional)** You can specify one or more pool Archiving configuration, to control archiving options for a specific pool.</span></span> <span data-ttu-id="7c298-116">集區設定優先於全域設定與網站設定，但僅限於封存集區設定中所指定的集區。</span><span class="sxs-lookup"><span data-stu-id="7c298-116">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="7c298-117">您可以編輯或刪除集區設定。</span><span class="sxs-lookup"><span data-stu-id="7c298-117">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7c298-118">封存設定會套用至位於商務用 Skype Server 上的使用者，而且如果您使用 Exchange 將封存資料儲存在 Microsoft Exchange 中，則在 Exchange 2013 上的使用者，但是會以稍有不同的方式來執行 Exchange 2013 上的使用者。</span><span class="sxs-lookup"><span data-stu-id="7c298-118">Archiving configurations apply to users homed on Skype for Business Server and, if you use Exchange to store archiving data in Microsoft Exchange, to users homed on Exchange 2013 but are implemented slightly differently for users homed on Exchange 2013.</span></span> <span data-ttu-id="7c298-119">其差異會在下一節中說明。</span><span class="sxs-lookup"><span data-stu-id="7c298-119">The differences are described in the next section.</span></span> 
  
<span data-ttu-id="7c298-120">[ **封存** 設定] 頁面會列出為您的部署設定的每個封存原則。</span><span class="sxs-lookup"><span data-stu-id="7c298-120">The **Archiving Configuration** page lists each Archiving policy that is configured for your deployment.</span></span> <span data-ttu-id="7c298-121">它也會顯示原則名稱、範圍 (全域、網站或集區) ，以及針對每個封存設定啟用的封存選項。</span><span class="sxs-lookup"><span data-stu-id="7c298-121">It also shows the policy name, scope (global, site, or pool), and which archiving options are enabled for each Archiving configuration.</span></span> <span data-ttu-id="7c298-122">在 [封存設定 **] 頁面上** ，您可以使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="7c298-122">From the **Archiving Configuration** page, you have the following options:</span></span>
- <span data-ttu-id="7c298-123">**新** 您可以新增一或多個下列選用的封存設定。</span><span class="sxs-lookup"><span data-stu-id="7c298-123">**New** You can add one or more of each of the following optional Archiving configurations.</span></span>
    
  - <span data-ttu-id="7c298-124">網站設定</span><span class="sxs-lookup"><span data-stu-id="7c298-124">Site configuration</span></span>
    
  - <span data-ttu-id="7c298-125">集區設定</span><span class="sxs-lookup"><span data-stu-id="7c298-125">Pool configuration</span></span>
    
- <span data-ttu-id="7c298-126">**編輯** 您可以變更頁面上所列之任何封存設定的選項。</span><span class="sxs-lookup"><span data-stu-id="7c298-126">**Edit** You can change the options of any of the Archiving configurations listed on the page.</span></span> <span data-ttu-id="7c298-127">使用此選項，您可以執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="7c298-127">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="7c298-128">**顯示詳細資料** 此選項會開啟對話方塊，您可以在其中變更所選封存設定的封存選項。</span><span class="sxs-lookup"><span data-stu-id="7c298-128">**Show details** This option opens a dialog box in which you can change the archiving options for the selected Archiving configuration.</span></span> <span data-ttu-id="7c298-129">您一次只能顯示一個封存設定的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="7c298-129">You can only show details for one Archiving configuration at a time.</span></span>
    
  - <span data-ttu-id="7c298-130">**全選** 此選項會選取清單中的所有封存設定。</span><span class="sxs-lookup"><span data-stu-id="7c298-130">**Select all** This option selects all Archiving configurations in the list.</span></span>
    
  - <span data-ttu-id="7c298-131">**Delete** 此選項會刪除所有選取的封存設定。</span><span class="sxs-lookup"><span data-stu-id="7c298-131">**Delete** This option deletes all selected Archiving configurations.</span></span>
    
- <span data-ttu-id="7c298-132">**動作** 您可以使用此選項，快速啟用或停用頁面上所列之任何設定中的 IM 會話或 web 會議會話的封存，而不是編輯設定。</span><span class="sxs-lookup"><span data-stu-id="7c298-132">**Action** You can use this option to quickly enable or disable archiving of IM sessions or web conferencing sessions in any configuration listed on the page, instead of editing the configuration.</span></span> <span data-ttu-id="7c298-133">[ **動作** ] 下的可用選項取決於目前在封存設定中指定的選項。</span><span class="sxs-lookup"><span data-stu-id="7c298-133">The options available under **Action** depend on what option is currently specified in the Archiving configuration.</span></span> <span data-ttu-id="7c298-134">所有選項均可使用，但目前針對封存設定所作用的選項除外。</span><span class="sxs-lookup"><span data-stu-id="7c298-134">All options are available, except the option currently in effect for the Archiving configuration.</span></span> <span data-ttu-id="7c298-135">選項包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="7c298-135">Options include the following:</span></span>
    
  - <span data-ttu-id="7c298-136">**封存 IM 工作階段**</span><span class="sxs-lookup"><span data-stu-id="7c298-136">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="7c298-137">**封存 IM 和 Web 會議工作階段**</span><span class="sxs-lookup"><span data-stu-id="7c298-137">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="7c298-138">**停用封存**</span><span class="sxs-lookup"><span data-stu-id="7c298-138">**Disable archiving**</span></span>
    
- <span data-ttu-id="7c298-139">**Refresh** 您可以重新整理「封存設定 **」頁面，** 以確認所有封存設定之選項的狀態。</span><span class="sxs-lookup"><span data-stu-id="7c298-139">**Refresh** You can refresh the **Archiving Configuration** page to verify the status of the options of all Archiving configurations.</span></span>
    
<span data-ttu-id="7c298-140">如需有關封存功能及功能（包括 Exchange 整合）的詳細資訊，請參閱 [在商務用 skype 2015 server 中規劃](../../plan-your-deployment/archiving/archiving.md)封存、 [部署商務用 skype server 2015](../../deploy/deploy-archiving/deploy-archiving.md)的封存，以及 [管理商務用 skype server 2015 中](../../manage/archiving/archiving.md)的封存。</span><span class="sxs-lookup"><span data-stu-id="7c298-140">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

