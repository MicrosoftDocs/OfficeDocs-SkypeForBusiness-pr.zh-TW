---
title: 封存設定建立新的或編輯現有
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
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
description: 您可以使用封存設定來控制部署的封存選項。 封存組態除了包含全域設定之外，也可能包含一或多個網站設定與集區設定：
ms.openlocfilehash: e0f56e125919bcb27cd9523213c92b7906e89ff0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827013"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a><span data-ttu-id="d5c12-104">封存組態：建立新的或編輯現有</span><span class="sxs-lookup"><span data-stu-id="d5c12-104">Archiving Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="d5c12-105">您可以使用封存設定來控制部署的封存選項。</span><span class="sxs-lookup"><span data-stu-id="d5c12-105">You use Archiving configurations to control archiving options for your deployment.</span></span> <span data-ttu-id="d5c12-106">封存組態除了包含全域設定之外，也可能包含一或多個網站設定與集區設定：</span><span class="sxs-lookup"><span data-stu-id="d5c12-106">Archiving configurations include the global configuration, and, optionally, one or more site and pool configurations:</span></span>
  
- <span data-ttu-id="d5c12-107">**通用** 設定預設會建立全域設定。</span><span class="sxs-lookup"><span data-stu-id="d5c12-107">**Global configuration** The global configuration is created by default.</span></span> <span data-ttu-id="d5c12-108">您可以編輯全域設定，但無法刪除此封存組態。</span><span class="sxs-lookup"><span data-stu-id="d5c12-108">You can edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="d5c12-109">若嘗試將其刪除，所有選項都會重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="d5c12-109">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="d5c12-110">**網站設定 (選用)** 您可以指定一或多個網站封存設定，每個網站封存設定可用於控制特定網站的封存選項。</span><span class="sxs-lookup"><span data-stu-id="d5c12-110">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="d5c12-111">網站設定會覆寫全域設定，但僅限於在封存網站設定中指定的網站。</span><span class="sxs-lookup"><span data-stu-id="d5c12-111">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="d5c12-112">您可以編輯或刪除網站設定。</span><span class="sxs-lookup"><span data-stu-id="d5c12-112">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="d5c12-113">**集區設定 (選用)** 您可以指定一或多個集區封存設定，以控制特定集區的封存選項。</span><span class="sxs-lookup"><span data-stu-id="d5c12-113">**Pool configuration (optional)** You can specify one or more pool Archiving configurations, to control archiving options for a specific pool.</span></span> <span data-ttu-id="d5c12-114">集區設定優先於全域設定與網站設定，但僅限於封存集區設定中所指定的集區。</span><span class="sxs-lookup"><span data-stu-id="d5c12-114">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="d5c12-115">您可以編輯或刪除集區設定。</span><span class="sxs-lookup"><span data-stu-id="d5c12-115">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d5c12-116">封存設定會套用至位於商務用 Skype Server 上的使用者，如果您啟用 Microsoft Exchange 整合2013選項，則會將 Microsoft exchange 中的封存資料儲存至 Exchange 2013 上的使用者。</span><span class="sxs-lookup"><span data-stu-id="d5c12-116">Archiving configurations apply to users homed on Skype for Business Server, and, if you enable the Microsoft Exchange integration option to use Exchange 2013 to store archiving data in Microsoft Exchange, to users homed on Exchange 2013.</span></span> <span data-ttu-id="d5c12-117">不過，對於位於 Exchange 2013 上的使用者而言，有些選項的執行效果稍有不同，如下一節所述。</span><span class="sxs-lookup"><span data-stu-id="d5c12-117">However, some options are implemented slightly differently for users homed on Exchange 2013, as described in the next section.</span></span> 
  
<span data-ttu-id="d5c12-118">若要設定現有或新的封存組態，請指定下列選項：</span><span class="sxs-lookup"><span data-stu-id="d5c12-118">To configure the settings for a new or existing Archiving configuration, specify the following options:</span></span>
- <span data-ttu-id="d5c12-119">**名稱** 每個封存設定都需要名稱。</span><span class="sxs-lookup"><span data-stu-id="d5c12-119">**Name** Each Archiving configuration requires a name.</span></span> <span data-ttu-id="d5c12-120">其名稱取決於您要新增或編輯的設定類型：</span><span class="sxs-lookup"><span data-stu-id="d5c12-120">The name is determined by the type of configuration you are adding or editing:</span></span>
    
  - <span data-ttu-id="d5c12-121">**通用** 設定預設名稱為 Global。</span><span class="sxs-lookup"><span data-stu-id="d5c12-121">**Global configuration** The default name is Global.</span></span> <span data-ttu-id="d5c12-122">例如：Contoso 北美組織。</span><span class="sxs-lookup"><span data-stu-id="d5c12-122">For example, Contoso North American Organization.</span></span>
    
  - <span data-ttu-id="d5c12-123">**網站** 設定此清單包含您部署中可用的網站。</span><span class="sxs-lookup"><span data-stu-id="d5c12-123">**Site configuration** The list contains the available sites in your deployment.</span></span> <span data-ttu-id="d5c12-124">按一下某一個網站即可加以選取。</span><span class="sxs-lookup"><span data-stu-id="d5c12-124">Click a single site to select it.</span></span> <span data-ttu-id="d5c12-125">例如：Redmond 資料中心。</span><span class="sxs-lookup"><span data-stu-id="d5c12-125">For example, Redmond Data Center.</span></span>
    
  - <span data-ttu-id="d5c12-126">**集** 區設定指定適當的名稱，它可以是部署中特定前端集區或 Standard Edition Server 的名稱。</span><span class="sxs-lookup"><span data-stu-id="d5c12-126">**Pool configuration** Specify an appropriate name, which can be the name of a specific Front End pool or Standard Edition Server in your deployment.</span></span> <span data-ttu-id="d5c12-127">例如：行銷部門。</span><span class="sxs-lookup"><span data-stu-id="d5c12-127">For example, Marketing Division.</span></span>
    
- <span data-ttu-id="d5c12-128">**描述** 這是選用的。</span><span class="sxs-lookup"><span data-stu-id="d5c12-128">**Description** This is optional.</span></span> <span data-ttu-id="d5c12-129">使用它來提供其他詳細資料，例如設定的範圍或用法。</span><span class="sxs-lookup"><span data-stu-id="d5c12-129">Use it to provide additional details, such as the scope or use of the configuration.</span></span> <span data-ttu-id="d5c12-130">例如，與其他網站的法律部門進行協調。</span><span class="sxs-lookup"><span data-stu-id="d5c12-130">For example, Coordinate with Legal Departments of Other Sites.</span></span>
    
- <span data-ttu-id="d5c12-131">封存 **設定** 選項包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="d5c12-131">**Archiving setting** Options include the following:</span></span>
    
  - <span data-ttu-id="d5c12-132">**封存 IM 工作階段**</span><span class="sxs-lookup"><span data-stu-id="d5c12-132">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="d5c12-133">**封存 IM 和 Web 會議工作階段**</span><span class="sxs-lookup"><span data-stu-id="d5c12-133">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="d5c12-134">**停用封存**</span><span class="sxs-lookup"><span data-stu-id="d5c12-134">**Disable archiving**</span></span>
    
- <span data-ttu-id="d5c12-135">封存 **失敗時封鎖立即訊息 (IM) 或 web 會議會話** 失敗包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="d5c12-135">**Block instant messaging (IM) or web conferencing sessions if archiving fails** Failures include the following:</span></span>
    
  - <span data-ttu-id="d5c12-136">**IM** 失敗可能是完整的資料庫或儲存服務的問題。</span><span class="sxs-lookup"><span data-stu-id="d5c12-136">**IM** A failure could be a full database or problem with the storage service.</span></span> <span data-ttu-id="d5c12-137">在此情況下，所有具有封存能力的使用者皆會無法使用 IM。</span><span class="sxs-lookup"><span data-stu-id="d5c12-137">In this case, IM is blocked for users who are enabled for Archiving.</span></span>
    
  - <span data-ttu-id="d5c12-138">**會議** 失敗可能是無法使用的檔案共用或儲存服務的問題。</span><span class="sxs-lookup"><span data-stu-id="d5c12-138">**Conferencing** A failure could be an unavailable file share or a problem with the storage service.</span></span> <span data-ttu-id="d5c12-139">在此情況下，所有失敗時於集區中進行的會議，都會切換為限制模式，而且無法發起新的會議。</span><span class="sxs-lookup"><span data-stu-id="d5c12-139">In this case, all active conferences hosted in the pool at the time of failure are switched to restricted mode and new conferences cannot be activated.</span></span>
    
    <span data-ttu-id="d5c12-140">IM 和會議會在失敗更正後自動復原。</span><span class="sxs-lookup"><span data-stu-id="d5c12-140">Both IM and conferencing automatically recover after the failures are corrected.</span></span>
    
- <span data-ttu-id="d5c12-141">**Microsoft Exchange 整合** 如果您擁有位於 Exchange 2013 的使用者，請選取此選項。</span><span class="sxs-lookup"><span data-stu-id="d5c12-141">**Microsoft Exchange integration** Select this option if you have users who are homed on Exchange 2013.</span></span> <span data-ttu-id="d5c12-142">使用此選項時，如果使用者的信箱處於 In-Place 保留狀態，Exchange 2013 會用來儲存這些使用者的資料。</span><span class="sxs-lookup"><span data-stu-id="d5c12-142">With this option, Exchange 2013 is used to store data for those users, if their mailboxes have been placed on In-Place Hold.</span></span> <span data-ttu-id="d5c12-143">如果您的所有使用者都位於 Exchange 2013，您不需要設定個別的 SQL Server 資料庫來儲存封存資料。</span><span class="sxs-lookup"><span data-stu-id="d5c12-143">If all your users are homed on Exchange 2013, you do not need to set up separate SQL Server databases for storage of archiving data.</span></span>
    
- <span data-ttu-id="d5c12-144">**啟用封存資料的清除** 選取此選項可啟用清除並指定清除選項，包括下列專案：</span><span class="sxs-lookup"><span data-stu-id="d5c12-144">**Enable purging of archiving data** Select this option to enable purging and specify purging options, which include the following:</span></span>
    
  - <span data-ttu-id="d5c12-145">在指定的特定天數之後清除。</span><span class="sxs-lookup"><span data-stu-id="d5c12-145">Purging after a specific number of days that you specify.</span></span>
    
  - <span data-ttu-id="d5c12-146">在匯出封存資料之後清除 (包括已上傳至 Exchange 的資料（如果您啟用 Microsoft Exchange 整合) ）。</span><span class="sxs-lookup"><span data-stu-id="d5c12-146">Purging after the archiving data has been exported (which includes data that has been uploaded to Exchange, if you enable Microsoft Exchange integration).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d5c12-147">如果您啟用 Microsoft Exchange 整合，請清除駐留在 Exchange 2013 上的使用者，並將其信箱置於 In-Place [保留]，由 Exchange 所控制。</span><span class="sxs-lookup"><span data-stu-id="d5c12-147">If you enable Microsoft Exchange integration, purging for users homed on Exchange 2013 and with their mailboxes placed on In-Place Hold is controlled by Exchange.</span></span> <span data-ttu-id="d5c12-148">唯一的例外狀況是儲存在 Lync Server 檔共用上的會議檔案。</span><span class="sxs-lookup"><span data-stu-id="d5c12-148">The only exception is for conferencing files, which are stored on the Lync Server file share.</span></span> <span data-ttu-id="d5c12-149">這類檔案會在匯出 (上傳至 Exchange) 之後 (選取匯出封存資料之後才清除資料的選項時)，或是達到指定天數上限之後 (指定保留天數上限時) 才從檔案共用中清除。</span><span class="sxs-lookup"><span data-stu-id="d5c12-149">These files are purged from the file share only after the files have been exported (uploaded to Exchange), if you select the option to purge data after the archiving data has been exported, or after the specified maximum number of days, if you specify a maximum number of days for retention.</span></span> 
  
<span data-ttu-id="d5c12-150">如需有關封存功能及功能（包括 Exchange 整合）的詳細資訊，請參閱 [在商務用 skype 2015 server 中規劃](../../plan-your-deployment/archiving/archiving.md)封存、 [部署商務用 skype server 2015](../../deploy/deploy-archiving/deploy-archiving.md)的封存，以及 [管理商務用 skype server 2015 中](../../manage/archiving/archiving.md)的封存。</span><span class="sxs-lookup"><span data-stu-id="d5c12-150">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

