---
title: 封存配置建立新的或編輯現有的
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
ROBOTS: NOINDEX, NOFOLLOW
description: 您可以使用封存組態控制部署的封存選項。封存組態除了包含全域組態之外，也可能包含一或多個站台組態與集區組態：
ms.openlocfilehash: 0c387095f40078246a1391af5968925a7b28caf2
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691138"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a><span data-ttu-id="5245d-104">封存組態：建立新的或編輯現有</span><span class="sxs-lookup"><span data-stu-id="5245d-104">Archiving Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="5245d-p102">您可以使用封存組態控制部署的封存選項。封存組態除了包含全域組態之外，也可能包含一或多個站台組態與集區組態：</span><span class="sxs-lookup"><span data-stu-id="5245d-p102">You use Archiving configurations to control archiving options for your deployment. Archiving configurations include the global configuration, and, optionally, one or more site and pool configurations:</span></span>
  
- <span data-ttu-id="5245d-107">**全域配置**預設會建立全域配置。</span><span class="sxs-lookup"><span data-stu-id="5245d-107">**Global configuration** The global configuration is created by default.</span></span> <span data-ttu-id="5245d-108">您可以編輯全域組態，但無法刪除該封存組態。</span><span class="sxs-lookup"><span data-stu-id="5245d-108">You can edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="5245d-109">若您嘗試刪除，所有選項都會重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="5245d-109">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="5245d-110">**網站設定（選用）** 您可以指定一個或多個網站歸檔設定，每個設定都可以設定以控制特定網站的封存選項。</span><span class="sxs-lookup"><span data-stu-id="5245d-110">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="5245d-111">網站組態會覆寫全域組態，但僅限於該封存網站組態中指定的網站。</span><span class="sxs-lookup"><span data-stu-id="5245d-111">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="5245d-112">您可以編輯或刪除網站組態。</span><span class="sxs-lookup"><span data-stu-id="5245d-112">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="5245d-113">**池配置（選用）** 您可以指定一個或多個池存檔設定，以控制特定池的存檔選項。</span><span class="sxs-lookup"><span data-stu-id="5245d-113">**Pool configuration (optional)** You can specify one or more pool Archiving configurations, to control archiving options for a specific pool.</span></span> <span data-ttu-id="5245d-114">集區組態會覆寫全域組態及網站組態，但僅限於在封存集區組態中指定的集區。</span><span class="sxs-lookup"><span data-stu-id="5245d-114">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="5245d-115">您可以編輯或刪除集區組態。</span><span class="sxs-lookup"><span data-stu-id="5245d-115">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5245d-116">封存設定適用于駐留在商務用 Skype Server 的使用者，如果您啟用 Microsoft Exchange 整合選項，就能使用 Exchange 將存檔資料儲存在 Microsoft Exchange 中，以供駐留在 Exchange 的使用者使用。</span><span class="sxs-lookup"><span data-stu-id="5245d-116">Archiving configurations apply to users homed on Skype for Business Server, and, if you enable the Microsoft Exchange integration option to use Exchange to store archiving data in Microsoft Exchange, to users homed on Exchange.</span></span> <span data-ttu-id="5245d-117">不過，某些選項對於駐留在 Exchange 上的使用者來說，會稍有不同，如下一節所述。</span><span class="sxs-lookup"><span data-stu-id="5245d-117">However, some options are implemented slightly differently for users homed on Exchange, as described in the next section.</span></span> 
  
<span data-ttu-id="5245d-118">若要設定現有或新的封存組態，請指定下列選項：</span><span class="sxs-lookup"><span data-stu-id="5245d-118">To configure the settings for a new or existing Archiving configuration, specify the following options:</span></span>
- <span data-ttu-id="5245d-119">**名稱**每個存檔設定都需要名稱。</span><span class="sxs-lookup"><span data-stu-id="5245d-119">**Name** Each Archiving configuration requires a name.</span></span> <span data-ttu-id="5245d-120">名稱是由您要新增或編輯的配置類型決定：</span><span class="sxs-lookup"><span data-stu-id="5245d-120">The name is determined by the type of configuration you are adding or editing:</span></span>
    
  - <span data-ttu-id="5245d-121">**全域配置**預設名稱為全域。</span><span class="sxs-lookup"><span data-stu-id="5245d-121">**Global configuration** The default name is Global.</span></span> <span data-ttu-id="5245d-122">例如，Contoso 北美組織。</span><span class="sxs-lookup"><span data-stu-id="5245d-122">For example, Contoso North American Organization.</span></span>
    
  - <span data-ttu-id="5245d-123">**網站**設定清單包含您部署中可用的網站。</span><span class="sxs-lookup"><span data-stu-id="5245d-123">**Site configuration** The list contains the available sites in your deployment.</span></span> <span data-ttu-id="5245d-124">按一下某個網站加以選取。</span><span class="sxs-lookup"><span data-stu-id="5245d-124">Click a single site to select it.</span></span> <span data-ttu-id="5245d-125">例如，Redmond 資料中心。</span><span class="sxs-lookup"><span data-stu-id="5245d-125">For example, Redmond Data Center.</span></span>
    
  - <span data-ttu-id="5245d-126">**池配置**指定適當的名稱，這可以是您部署中特定前端池或標準版伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="5245d-126">**Pool configuration** Specify an appropriate name, which can be the name of a specific Front End pool or Standard Edition Server in your deployment.</span></span> <span data-ttu-id="5245d-127">例如：行銷部門。</span><span class="sxs-lookup"><span data-stu-id="5245d-127">For example, Marketing Division.</span></span>
    
- <span data-ttu-id="5245d-128">**描述**這是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="5245d-128">**Description** This is optional.</span></span> <span data-ttu-id="5245d-129">使用它來提供其他詳細資料，例如設定的範圍或用途。</span><span class="sxs-lookup"><span data-stu-id="5245d-129">Use it to provide additional details, such as the scope or use of the configuration.</span></span> <span data-ttu-id="5245d-130">例如，與其他網站的法律部門共同合作。</span><span class="sxs-lookup"><span data-stu-id="5245d-130">For example, Coordinate with Legal Departments of Other Sites.</span></span>
    
- <span data-ttu-id="5245d-131">**存檔設定**選項包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="5245d-131">**Archiving setting** Options include the following:</span></span>
    
  - <span data-ttu-id="5245d-132">**封存 IM 工作階段**</span><span class="sxs-lookup"><span data-stu-id="5245d-132">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="5245d-133">**封存 IM 與 Web 會議工作階段**</span><span class="sxs-lookup"><span data-stu-id="5245d-133">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="5245d-134">**停用封存**</span><span class="sxs-lookup"><span data-stu-id="5245d-134">**Disable archiving**</span></span>
    
- <span data-ttu-id="5245d-135">**如果存檔失敗，封鎖立即訊息（IM）或網路會議會話**失敗包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="5245d-135">**Block instant messaging (IM) or web conferencing sessions if archiving fails** Failures include the following:</span></span>
    
  - <span data-ttu-id="5245d-136">**IM**失敗可能是儲存空間服務的完整資料庫或問題。</span><span class="sxs-lookup"><span data-stu-id="5245d-136">**IM** A failure could be a full database or problem with the storage service.</span></span> <span data-ttu-id="5245d-137">在此情況下，具有封存能力的使用者皆無法使用 IM。</span><span class="sxs-lookup"><span data-stu-id="5245d-137">In this case, IM is blocked for users who are enabled for Archiving.</span></span>
    
  - <span data-ttu-id="5245d-138">**會議**失敗可能是無法使用的檔案共用或儲存服務的問題。</span><span class="sxs-lookup"><span data-stu-id="5245d-138">**Conferencing** A failure could be an unavailable file share or a problem with the storage service.</span></span> <span data-ttu-id="5245d-139">在此情況下，所有於失敗時間在集區中進行的會議，都會切換為限制模式，而且無法啟動新的會議。</span><span class="sxs-lookup"><span data-stu-id="5245d-139">In this case, all active conferences hosted in the pool at the time of failure are switched to restricted mode and new conferences cannot be activated.</span></span>
    
    <span data-ttu-id="5245d-140">IM 和會議會在更正失敗之後自動復原。</span><span class="sxs-lookup"><span data-stu-id="5245d-140">Both IM and conferencing automatically recover after the failures are corrected.</span></span>
    
- <span data-ttu-id="5245d-141">**Microsoft Exchange 整合**如果您有駐留在 Exchange 的使用者，請選取此選項。</span><span class="sxs-lookup"><span data-stu-id="5245d-141">**Microsoft Exchange integration** Select this option if you have users who are homed on Exchange.</span></span> <span data-ttu-id="5245d-142">使用此選項時，如果使用者的信箱已放在就地保留中，Exchange 就會用來儲存這些使用者的資料。</span><span class="sxs-lookup"><span data-stu-id="5245d-142">With this option, Exchange is used to store data for those users, if their mailboxes have been placed on In-Place Hold.</span></span> <span data-ttu-id="5245d-143">如果您的所有使用者都是以 Exchange 為宿主，則不需要設定個別的 SQL Server 資料庫來儲存存檔資料。</span><span class="sxs-lookup"><span data-stu-id="5245d-143">If all your users are homed on Exchange, you do not need to set up separate SQL Server databases for storage of archiving data.</span></span>
    
- <span data-ttu-id="5245d-144">**允許清除封存資料**選取此選項可啟用清除及指定清除選項，包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="5245d-144">**Enable purging of archiving data** Select this option to enable purging and specify purging options, which include the following:</span></span>
    
  - <span data-ttu-id="5245d-145">在指定的特定天數之後清除。</span><span class="sxs-lookup"><span data-stu-id="5245d-145">Purging after a specific number of days that you specify.</span></span>
    
  - <span data-ttu-id="5245d-146">在匯出封存資料之後進行清除（包含已上傳至 Exchange 的資料，如果您啟用 Microsoft Exchange 整合）。</span><span class="sxs-lookup"><span data-stu-id="5245d-146">Purging after the archiving data has been exported (which includes data that has been uploaded to Exchange, if you enable Microsoft Exchange integration).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5245d-147">如果您啟用 Microsoft Exchange 整合，請清除駐留在 Exchange 的使用者，並將其信箱放在就地保留中的使用者受到 Exchange 控制。</span><span class="sxs-lookup"><span data-stu-id="5245d-147">If you enable Microsoft Exchange integration, purging for users homed on Exchange and with their mailboxes placed on In-Place Hold is controlled by Exchange.</span></span> <span data-ttu-id="5245d-148">唯一的例外狀況是儲存在 Lync Server 檔案共用的會議檔案。</span><span class="sxs-lookup"><span data-stu-id="5245d-148">The only exception is for conferencing files, which are stored on the Lync Server file share.</span></span> <span data-ttu-id="5245d-149">這類檔案會在匯出 (上傳至 Exchange) 之後 (選取匯出封存資料之後才清除資料的選項時)，或是達到指定天數上限之後 (指定保留天數上限時) 才從檔案共用中清除。</span><span class="sxs-lookup"><span data-stu-id="5245d-149">These files are purged from the file share only after the files have been exported (uploaded to Exchange), if you select the option to purge data after the archiving data has been exported, or after the specified maximum number of days, if you specify a maximum number of days for retention.</span></span> 
  
<span data-ttu-id="5245d-150">如需有關存檔功能和功能（包括 Exchange 整合）的詳細資料，請參閱[在商務用 Skype server 中進行](../../../plan-your-deployment/archiving/archiving.md)封存、[部署商務用 skype server](../../../deploy/deploy-archiving/deploy-archiving.md)的封存，以及[管理商務用 skype 伺服器](../../../manage/archiving/archiving.md)的封存。</span><span class="sxs-lookup"><span data-stu-id="5245d-150">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

