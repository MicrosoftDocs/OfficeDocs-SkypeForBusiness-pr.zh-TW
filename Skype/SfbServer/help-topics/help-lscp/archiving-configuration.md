---
title: 封存組態
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: '您可以使用封存配置來控制商務用 Skype Server 部署的封存選項, 包括啟用和停用下列選項:'
ms.openlocfilehash: 8f3ed4289d68359cb8eb0d4cb0bfc3a303c53dd3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193162"
---
# <a name="archiving-configuration"></a><span data-ttu-id="8ca5a-103">封存組態</span><span class="sxs-lookup"><span data-stu-id="8ca5a-103">Archiving Configuration</span></span>
 
<span data-ttu-id="8ca5a-104">您可以使用封存配置來控制商務用 Skype Server 部署的封存選項, 包括啟用和停用下列選項:</span><span class="sxs-lookup"><span data-stu-id="8ca5a-104">You use Archiving configurations to control archiving options for your Skype for Business Server deployment, including enabling and disabling the following options:</span></span>
  
- <span data-ttu-id="8ca5a-105">若封存失敗，封鎖立即訊息 (IM) 或會議工作階段</span><span class="sxs-lookup"><span data-stu-id="8ca5a-105">Blocking of instant messaging (IM) or conferencing sessions if archiving fails</span></span>
    
- <span data-ttu-id="8ca5a-106">與 Exchange 中的使用者整合 Exchange 2013 儲存空間 (針對駐留在 Exchange 2013 的使用者)</span><span class="sxs-lookup"><span data-stu-id="8ca5a-106">Integration with Exchange 2013 storage, for users homed on Exchange 2013</span></span>
    
- <span data-ttu-id="8ca5a-107">清除封存資料</span><span class="sxs-lookup"><span data-stu-id="8ca5a-107">Purging of archived data</span></span>
    
<span data-ttu-id="8ca5a-108">封存組態包含全域組態以及選用的一或多個網站與集區封存組態：</span><span class="sxs-lookup"><span data-stu-id="8ca5a-108">Archiving configurations include the global configuration and, optionally, one or more site and pool Archiving configurations:</span></span>
  
- <span data-ttu-id="8ca5a-109">**全域配置**預設會在所有商務用 Skype Server 部署中建立全域配置。</span><span class="sxs-lookup"><span data-stu-id="8ca5a-109">**Global configuration** The global configuration is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="8ca5a-110">您可以編輯全域組態，但無法刪除此封存組態。</span><span class="sxs-lookup"><span data-stu-id="8ca5a-110">You edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="8ca5a-111">如果嘗試刪除此原則，則所有選項會重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="8ca5a-111">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="8ca5a-112">**網站設定 (選用)** 您可以指定一個或多個網站歸檔設定, 每個設定都可以設定以控制特定網站的封存選項。</span><span class="sxs-lookup"><span data-stu-id="8ca5a-112">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="8ca5a-113">網站組態會覆寫全域組態，但僅限於該封存網站組態中指定的網站。</span><span class="sxs-lookup"><span data-stu-id="8ca5a-113">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="8ca5a-114">您可以編輯或刪除網站組態。</span><span class="sxs-lookup"><span data-stu-id="8ca5a-114">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="8ca5a-115">**池配置 (選用)** 您可以指定一個或多個池存檔設定, 以控制特定池的存檔選項。</span><span class="sxs-lookup"><span data-stu-id="8ca5a-115">**Pool configuration (optional)** You can specify one or more pool Archiving configuration, to control archiving options for a specific pool.</span></span> <span data-ttu-id="8ca5a-116">集區組態會覆寫全域組態及網站組態，但僅限於在封存集區組態中指定的集區。</span><span class="sxs-lookup"><span data-stu-id="8ca5a-116">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="8ca5a-117">您可以編輯或刪除集區組態。</span><span class="sxs-lookup"><span data-stu-id="8ca5a-117">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8ca5a-118">封存設定適用于駐留在商務用 Skype Server 的使用者, 而且如果您使用 Exchange 將存檔資料儲存在 Microsoft Exchange 中, 則是駐留在 Exchange 2013 的使用者, 但在 Exchange 2013 上的使用者的執行方式稍有不同。</span><span class="sxs-lookup"><span data-stu-id="8ca5a-118">Archiving configurations apply to users homed on Skype for Business Server and, if you use Exchange to store archiving data in Microsoft Exchange, to users homed on Exchange 2013 but are implemented slightly differently for users homed on Exchange 2013.</span></span> <span data-ttu-id="8ca5a-119">下一節將說明此不同之處。</span><span class="sxs-lookup"><span data-stu-id="8ca5a-119">The differences are described in the next section.</span></span> 
  
<span data-ttu-id="8ca5a-p105">「封存組態」\*\*\*\* 頁面列出針對您部署所設定的每個封存原則。該頁面也會顯示原則名稱、範圍 (全域、網站或集區)，以及已針對每個封存組態啟用的封存選項。您可從「封存組態」\*\*\*\* 頁面執行下列選項：</span><span class="sxs-lookup"><span data-stu-id="8ca5a-p105">The **Archiving Configuration** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or pool), and which archiving options are enabled for each Archiving configuration. From the **Archiving Configuration** page, you have the following options:</span></span>
- <span data-ttu-id="8ca5a-123">**新增**您可以新增下列其中一或多個選用的存檔設定。</span><span class="sxs-lookup"><span data-stu-id="8ca5a-123">**New** You can add one or more of each of the following optional Archiving configurations.</span></span>
    
  - <span data-ttu-id="8ca5a-124">網站組態</span><span class="sxs-lookup"><span data-stu-id="8ca5a-124">Site configuration</span></span>
    
  - <span data-ttu-id="8ca5a-125">集區組態</span><span class="sxs-lookup"><span data-stu-id="8ca5a-125">Pool configuration</span></span>
    
- <span data-ttu-id="8ca5a-126">[**編輯**]您可以變更頁面上所列的任何存檔設定選項。</span><span class="sxs-lookup"><span data-stu-id="8ca5a-126">**Edit** You can change the options of any of the Archiving configurations listed on the page.</span></span> <span data-ttu-id="8ca5a-127">使用此選項, 您可以執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="8ca5a-127">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="8ca5a-128">**顯示詳細資料**這個選項會開啟一個對話方塊, 您可以在其中變更所選封存設定的 [封存] (存檔) 選項。</span><span class="sxs-lookup"><span data-stu-id="8ca5a-128">**Show details** This option opens a dialog box in which you can change the archiving options for the selected Archiving configuration.</span></span> <span data-ttu-id="8ca5a-129">您一次只能顯示一個存檔設定的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8ca5a-129">You can only show details for one Archiving configuration at a time.</span></span>
    
  - <span data-ttu-id="8ca5a-130">**選取全部**此選項會選取清單中的所有存檔設定。</span><span class="sxs-lookup"><span data-stu-id="8ca5a-130">**Select all** This option selects all Archiving configurations in the list.</span></span>
    
  - <span data-ttu-id="8ca5a-131">**刪除**此選項會刪除所有選取的存檔設定。</span><span class="sxs-lookup"><span data-stu-id="8ca5a-131">**Delete** This option deletes all selected Archiving configurations.</span></span>
    
- <span data-ttu-id="8ca5a-132">**動作**您可以使用這個選項, 在頁面上所列的任何設定中快速啟用或停用 IM 會話或網路會議會話的存檔, 而不是編輯設定。</span><span class="sxs-lookup"><span data-stu-id="8ca5a-132">**Action** You can use this option to quickly enable or disable archiving of IM sessions or web conferencing sessions in any configuration listed on the page, instead of editing the configuration.</span></span> <span data-ttu-id="8ca5a-133">[**動作**] 底下的可用選項, 取決於存檔設定中目前指定的選項。</span><span class="sxs-lookup"><span data-stu-id="8ca5a-133">The options available under **Action** depend on what option is currently specified in the Archiving configuration.</span></span> <span data-ttu-id="8ca5a-134">您可以使用所有選項, 除了目前對封存設定有效的選項。</span><span class="sxs-lookup"><span data-stu-id="8ca5a-134">All options are available, except the option currently in effect for the Archiving configuration.</span></span> <span data-ttu-id="8ca5a-135">選項包括下列各項:</span><span class="sxs-lookup"><span data-stu-id="8ca5a-135">Options include the following:</span></span>
    
  - <span data-ttu-id="8ca5a-136">**封存 IM 工作階段**</span><span class="sxs-lookup"><span data-stu-id="8ca5a-136">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="8ca5a-137">**封存 IM 與 Web 會議工作階段**</span><span class="sxs-lookup"><span data-stu-id="8ca5a-137">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="8ca5a-138">**停用封存**</span><span class="sxs-lookup"><span data-stu-id="8ca5a-138">**Disable archiving**</span></span>
    
- <span data-ttu-id="8ca5a-139">**更新**您可以重新整理\*\*\*\* [封存設定] 頁面, 以驗證所有存檔設定的選項狀態。</span><span class="sxs-lookup"><span data-stu-id="8ca5a-139">**Refresh** You can refresh the **Archiving Configuration** page to verify the status of the options of all Archiving configurations.</span></span>
    
<span data-ttu-id="8ca5a-140">如需有關存檔功能和功能 (包括 Exchange 整合) 的詳細資料, 請參閱[在商務用 Skype server 2015 中進行](../../plan-your-deployment/archiving/archiving.md)封存、[部署商務用 skype server 2015 的](../../deploy/deploy-archiving/deploy-archiving.md)封存, 以及[在 Skype 中管理存檔商務伺服器 2015](../../manage/archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="8ca5a-140">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

