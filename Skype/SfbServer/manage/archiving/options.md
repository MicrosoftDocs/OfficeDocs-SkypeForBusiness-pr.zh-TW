---
title: 在商務用 Skype Server 中管理存檔選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 摘要：瞭解如何設定商務用 Skype Server 的存檔選項。
ms.openlocfilehash: af5c8f90cd49f556e1e787e5f550b54da1976c45
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818895"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a><span data-ttu-id="38da0-103">在商務用 Skype Server 中管理存檔選項</span><span class="sxs-lookup"><span data-stu-id="38da0-103">Manage archiving options in Skype for Business Server</span></span>

<span data-ttu-id="38da0-104">**摘要：** 瞭解如何設定商務用 Skype Server 的存檔選項。</span><span class="sxs-lookup"><span data-stu-id="38da0-104">**Summary:** Learn how to configure archiving options for Skype for Business Server.</span></span>
  
<span data-ttu-id="38da0-105">您最初是在部署期間設定封存，但是您可以在部署之後變更、新增及刪除設定。</span><span class="sxs-lookup"><span data-stu-id="38da0-105">You initially configure archiving at deployment, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="38da0-106">[封存選項] 可決定是否要：</span><span class="sxs-lookup"><span data-stu-id="38da0-106">Archiving options determine whether to:</span></span> 
  
- <span data-ttu-id="38da0-107">啟用或停用封存功能</span><span class="sxs-lookup"><span data-stu-id="38da0-107">Enable or disable archiving</span></span>
    
- <span data-ttu-id="38da0-108">封存 IM 工作階段</span><span class="sxs-lookup"><span data-stu-id="38da0-108">Archive IM sessions</span></span>
    
- <span data-ttu-id="38da0-109">封存網路會議會話</span><span class="sxs-lookup"><span data-stu-id="38da0-109">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="38da0-110">存檔無法使用時封鎖活動</span><span class="sxs-lookup"><span data-stu-id="38da0-110">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="38da0-111">使用 Exchange 整合</span><span class="sxs-lookup"><span data-stu-id="38da0-111">Use Exchange integration</span></span>
    
- <span data-ttu-id="38da0-112">設定清除及匯出資料</span><span class="sxs-lookup"><span data-stu-id="38da0-112">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="38da0-113">您可以在下列層面指定配置選項：</span><span class="sxs-lookup"><span data-stu-id="38da0-113">You can specify configuration options at the following levels:</span></span>
  
- <span data-ttu-id="38da0-114">部署商務用 Skype Server 時預設建立的全域層級設定</span><span class="sxs-lookup"><span data-stu-id="38da0-114">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="38da0-115">選擇性網站層級設定，指定如何針對特定網站執行歸檔</span><span class="sxs-lookup"><span data-stu-id="38da0-115">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="38da0-116">指定如何針對特定的資料庫池實施歸檔的選用池層級設定</span><span class="sxs-lookup"><span data-stu-id="38da0-116">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="38da0-117">您可以刪除網站配置或池設定，但無法刪除全域設定。</span><span class="sxs-lookup"><span data-stu-id="38da0-117">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="38da0-118">如果您刪除全域設定，系統會自動將其重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="38da0-118">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="38da0-119">如需如何實施封存配置以及歸檔設定的階層的詳細資料，請參閱[在商務用 Skype 伺服器中規劃](../../plan-your-deployment/archiving/archiving.md)封存。</span><span class="sxs-lookup"><span data-stu-id="38da0-119">For details about how archiving configurations are implemented and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="38da0-120">使用 [控制台] 設定存檔選項</span><span class="sxs-lookup"><span data-stu-id="38da0-120">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="38da0-121">您可以使用 [控制台] 來設定封存選項，如下所示：</span><span class="sxs-lookup"><span data-stu-id="38da0-121">You can configure archiving options by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="38da0-122">從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="38da0-122">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="38da0-123">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="38da0-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="38da0-124">在左側導覽列中，按一下 [封存**配置**]。</span><span class="sxs-lookup"><span data-stu-id="38da0-124">In the left navigation bar, click **Archiving Configuration**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="38da0-125">使用 Windows PowerShell 設定封存選項</span><span class="sxs-lookup"><span data-stu-id="38da0-125">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="38da0-126">您也可以使用下表所列的 Windows PowerShell Cmdlet 來設定封存選項。</span><span class="sxs-lookup"><span data-stu-id="38da0-126">You can also configure archiving options by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="38da0-127">如需語法的詳細資料（包括所有可用的參數），請參閱[商務用 Skype Server 管理命令](../management-shell.md)介面。</span><span class="sxs-lookup"><span data-stu-id="38da0-127">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="38da0-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="38da0-128">**Cmdlet**</span></span>|<span data-ttu-id="38da0-129">**說明**</span><span class="sxs-lookup"><span data-stu-id="38da0-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="38da0-130">CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="38da0-130">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="38da0-131">傳回貴組織中的存檔設定設定的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="38da0-131">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="38da0-132">新-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="38da0-132">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="38da0-133">建立一組新的立即訊息（IM）設定，這可以用來啟用或停用自動儲存 IM 會話，並封鎖任何無法封存的立即訊息。</span><span class="sxs-lookup"><span data-stu-id="38da0-133">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="38da0-134">移除-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="38da0-134">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="38da0-135">移除指定的存檔設定集合，這些設定是用來啟用或停用立即訊息（IM）會話，以及選擇性地封鎖任何無法封存的立即訊息。</span><span class="sxs-lookup"><span data-stu-id="38da0-135">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="38da0-136">Set-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="38da0-136">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="38da0-137">修改現有的立即訊息（IM）封存配置選項組合。</span><span class="sxs-lookup"><span data-stu-id="38da0-137">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |
