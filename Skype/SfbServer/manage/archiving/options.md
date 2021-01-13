---
title: 管理商務用 Skype Server 中的封存選項
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 摘要：瞭解如何設定商務用 Skype Server 的封存選項。
ms.openlocfilehash: ee0145ac0896e1bbb8d18c6a51116f2ddd75ee05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817533"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a><span data-ttu-id="73331-103">管理商務用 Skype Server 中的封存選項</span><span class="sxs-lookup"><span data-stu-id="73331-103">Manage archiving options in Skype for Business Server</span></span>

<span data-ttu-id="73331-104">**摘要：** 瞭解如何設定商務用 Skype Server 的封存選項。</span><span class="sxs-lookup"><span data-stu-id="73331-104">**Summary:** Learn how to configure archiving options for Skype for Business Server.</span></span>
  
<span data-ttu-id="73331-105">您最初在部署時設定封存，但是您可以在部署後變更、新增和刪除設定。</span><span class="sxs-lookup"><span data-stu-id="73331-105">You initially configure archiving at deployment, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="73331-106">封存選項會決定是否要：</span><span class="sxs-lookup"><span data-stu-id="73331-106">Archiving options determine whether to:</span></span> 
  
- <span data-ttu-id="73331-107">啟用或停用封存</span><span class="sxs-lookup"><span data-stu-id="73331-107">Enable or disable archiving</span></span>
    
- <span data-ttu-id="73331-108">封存 IM 工作階段</span><span class="sxs-lookup"><span data-stu-id="73331-108">Archive IM sessions</span></span>
    
- <span data-ttu-id="73331-109">封存 web 會議會話</span><span class="sxs-lookup"><span data-stu-id="73331-109">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="73331-110">封存無法使用時封鎖活動</span><span class="sxs-lookup"><span data-stu-id="73331-110">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="73331-111">使用 Exchange 整合</span><span class="sxs-lookup"><span data-stu-id="73331-111">Use Exchange integration</span></span>
    
- <span data-ttu-id="73331-112">設定資料的清除和匯出</span><span class="sxs-lookup"><span data-stu-id="73331-112">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="73331-113">您可以在下列層級指定設定選項：</span><span class="sxs-lookup"><span data-stu-id="73331-113">You can specify configuration options at the following levels:</span></span>
  
- <span data-ttu-id="73331-114">當您部署商務用 Skype Server 時，預設會建立全域層級設定</span><span class="sxs-lookup"><span data-stu-id="73331-114">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="73331-115">選用的網站層級設定，指定如何為特定網站實施封存</span><span class="sxs-lookup"><span data-stu-id="73331-115">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="73331-116">選用集區層級設定，指定如何為特定集區實施封存</span><span class="sxs-lookup"><span data-stu-id="73331-116">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="73331-117">您可以刪除網站設定或集區設定，但無法刪除全域設定。</span><span class="sxs-lookup"><span data-stu-id="73331-117">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="73331-118">如果您刪除全域設定，它會自動重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="73331-118">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="73331-119">如需如何執行封存設定與封存設定階層的詳細資訊，請參閱 [在商務用 Skype Server 中規劃](../../plan-your-deployment/archiving/archiving.md)封存。</span><span class="sxs-lookup"><span data-stu-id="73331-119">For details about how archiving configurations are implemented and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="73331-120">使用控制台設定封存選項</span><span class="sxs-lookup"><span data-stu-id="73331-120">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="73331-121">您可以使用 [控制台] 設定封存選項，如下所示：</span><span class="sxs-lookup"><span data-stu-id="73331-121">You can configure archiving options by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="73331-122">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="73331-122">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="73331-123">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="73331-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="73331-124">在左導覽列中 **，按一下 [** 封存設定]。</span><span class="sxs-lookup"><span data-stu-id="73331-124">In the left navigation bar, click **Archiving Configuration**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="73331-125">使用 Windows PowerShell 設定封存選項</span><span class="sxs-lookup"><span data-stu-id="73331-125">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="73331-126">您也可以使用下表所列的 Windows PowerShell Cmdlet 來設定封存選項。</span><span class="sxs-lookup"><span data-stu-id="73331-126">You can also configure archiving options by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="73331-127">如需語法的詳細資訊（包括所有可用參數），請參閱 [商務用 Skype Server 管理命令](../management-shell.md)介面。</span><span class="sxs-lookup"><span data-stu-id="73331-127">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="73331-128">**指令程式**</span><span class="sxs-lookup"><span data-stu-id="73331-128">**Cmdlet**</span></span>|<span data-ttu-id="73331-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="73331-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="73331-130">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="73331-130">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="73331-131">傳回組織中封存設定設定的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="73331-131">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="73331-132">New-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="73331-132">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="73331-133">會建立一組新的立即訊息 (IM) 設定，可用來啟用或停用自動儲存 IM 會話，並封鎖任何無法封存的立即訊息。</span><span class="sxs-lookup"><span data-stu-id="73331-133">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="73331-134">Remove-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="73331-134">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="73331-135">移除指定的封存設定集合，用來啟用或停用自動儲存立即訊息 (IM) 會話，並選擇性地封鎖無法封存的任何立即訊息。</span><span class="sxs-lookup"><span data-stu-id="73331-135">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="73331-136">Set-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="73331-136">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="73331-137">修改現有的立即訊息 (IM 集合) 封存設定選項。</span><span class="sxs-lookup"><span data-stu-id="73331-137">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |
