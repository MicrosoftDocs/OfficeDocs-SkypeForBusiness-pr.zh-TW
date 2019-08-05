---
title: 在商務用 Skype Server 中管理存檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: '摘要: 瞭解如何管理商務用 Skype Server 的封存。'
ms.openlocfilehash: e4566760a9d071b87596e581689f6373ca3cda49
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189349"
---
# <a name="manage-archiving-in-skype-for-business-server"></a><span data-ttu-id="16440-103">在商務用 Skype Server 中管理存檔</span><span class="sxs-lookup"><span data-stu-id="16440-103">Manage archiving in Skype for Business Server</span></span>

<span data-ttu-id="16440-104">**摘要:** 瞭解如何管理商務用 Skype Server 的封存。</span><span class="sxs-lookup"><span data-stu-id="16440-104">**Summary:** Learn how to manage archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="16440-105">當您為貴組織部署存檔時, 您會在部署期間指定初始配置。</span><span class="sxs-lookup"><span data-stu-id="16440-105">When you deploy archiving for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="16440-106">不過, 有時候您可能會想要變更針對日常管理實施封存支援的方式, 或符合貴組織的新需求。</span><span class="sxs-lookup"><span data-stu-id="16440-106">However, there may be times when you want to change how you implement archiving support for day-to-day management or to meet new requirements for your organization.</span></span> <span data-ttu-id="16440-107">例如, 您可能需要針對特定網站、特定池或貴組織內的特定使用者設定不同的存檔支援。</span><span class="sxs-lookup"><span data-stu-id="16440-107">For example, you may need to set up archiving support differently for a specific site, a specific pool, or specific users within your organization.</span></span> <span data-ttu-id="16440-108">針對駐留在商務用 Skype Server 的使用者, 您可以建立及自訂封存配置選項和使用者原則來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="16440-108">For users homed on Skype for Business Server, you do this by creating and customizing archiving configuration options and user policies.</span></span> 
  
<span data-ttu-id="16440-109">在您閱讀本主題之前, 請務必熟悉[在商務用 Skype server 中進行](../../plan-your-deployment/archiving/archiving.md)封存所需的資訊, 並[針對商務用 skype server 部署歸檔](../../deploy/deploy-archiving/deploy-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="16440-109">Before you read this topic, be sure you are familiar with the information in [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Deploy archiving for Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="16440-110">如果您針對您的部署啟用 Microsoft Exchange 整合, Exchange 原則會控制是否針對駐留在 Exchange 的使用者啟用封存, 並將其信箱放在就地保留中。</span><span class="sxs-lookup"><span data-stu-id="16440-110">If you enable Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="16440-111">如需詳細資訊, 請參閱[在商務用 Skype server 中進行](../../plan-your-deployment/archiving/archiving.md)封存的規劃, 以及[設定與商務用 Skype server 的 Exchange 儲存體整合](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="16440-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="archiving-configuration-options"></a><span data-ttu-id="16440-112">封存配置選項</span><span class="sxs-lookup"><span data-stu-id="16440-112">Archiving configuration options</span></span>

<span data-ttu-id="16440-113">封存配置選項指定是否:</span><span class="sxs-lookup"><span data-stu-id="16440-113">Archiving configuration options specify whether to:</span></span>
  
- <span data-ttu-id="16440-114">啟用或停用封存功能</span><span class="sxs-lookup"><span data-stu-id="16440-114">Enable or disable archiving</span></span>
    
- <span data-ttu-id="16440-115">封存 IM 工作階段</span><span class="sxs-lookup"><span data-stu-id="16440-115">Archive IM sessions</span></span>
    
- <span data-ttu-id="16440-116">封存網路會議會話</span><span class="sxs-lookup"><span data-stu-id="16440-116">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="16440-117">存檔無法使用時封鎖活動</span><span class="sxs-lookup"><span data-stu-id="16440-117">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="16440-118">使用 Exchange 整合</span><span class="sxs-lookup"><span data-stu-id="16440-118">Use Exchange integration</span></span>
    
- <span data-ttu-id="16440-119">設定清除及匯出資料</span><span class="sxs-lookup"><span data-stu-id="16440-119">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="16440-120">這些選項可以在 [全域]、[網站] 或 [池] 層級設定。</span><span class="sxs-lookup"><span data-stu-id="16440-120">These options can be set at the global, site, or pool level.</span></span> <span data-ttu-id="16440-121">如需詳細資訊, 請參閱[在商務用 Skype Server 中管理封存選項](options.md)。</span><span class="sxs-lookup"><span data-stu-id="16440-121">For more information, see [Manage archiving options in Skype for Business Server](options.md).</span></span>
  
## <a name="archiving-policies"></a><span data-ttu-id="16440-122">歸檔原則</span><span class="sxs-lookup"><span data-stu-id="16440-122">Archiving policies</span></span>

<span data-ttu-id="16440-123">存檔原則決定是否要封存下列專案:</span><span class="sxs-lookup"><span data-stu-id="16440-123">Archiving policies determine whether to archive the following:</span></span>
  
- <span data-ttu-id="16440-124">內部通訊</span><span class="sxs-lookup"><span data-stu-id="16440-124">Internal communications</span></span>
    
- <span data-ttu-id="16440-125">外部通訊</span><span class="sxs-lookup"><span data-stu-id="16440-125">External communications</span></span>
    
<span data-ttu-id="16440-126">這些原則可以在全域、網站或使用者層級設定。</span><span class="sxs-lookup"><span data-stu-id="16440-126">These policies can be set at the global, site, or user level.</span></span> <span data-ttu-id="16440-127">如需詳細資訊, 請參閱[在商務用 Skype Server 中管理存檔原則](policies.md)。</span><span class="sxs-lookup"><span data-stu-id="16440-127">For more information, see [Manage archiving policies in Skype for Business Server](policies.md).</span></span>
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a><span data-ttu-id="16440-128">使用 [控制台] 或使用 Windows PowerShell 來管理存檔</span><span class="sxs-lookup"><span data-stu-id="16440-128">Manage archiving by using the Control Panel or by using Windows PowerShell</span></span>

<span data-ttu-id="16440-129">您可以使用 [控制台] 或使用 Windows PowerShell 來管理存檔。</span><span class="sxs-lookup"><span data-stu-id="16440-129">You can manage archiving by using the Control Panel or by using Windows PowerShell.</span></span> <span data-ttu-id="16440-130">下表摘要列出可協助您管理存檔的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="16440-130">The following table summarizes the cmdlets available to help you manage archiving.</span></span> <span data-ttu-id="16440-131">如需語法的詳細資料 (包括所有可用的參數), 請參閱[商務用 Skype Server 管理命令](../management-shell.md)介面。</span><span class="sxs-lookup"><span data-stu-id="16440-131">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span> 


|<span data-ttu-id="16440-132">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="16440-132">**Cmdlet**</span></span>|<span data-ttu-id="16440-133">**說明**</span><span class="sxs-lookup"><span data-stu-id="16440-133">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="16440-134">Export-CsArchivingData</span><span class="sxs-lookup"><span data-stu-id="16440-134">Export-CsArchivingData</span></span>  <br/> |<span data-ttu-id="16440-135">匯出已儲存在商務用 Skype Server 封存資料庫中的記錄。</span><span class="sxs-lookup"><span data-stu-id="16440-135">Exports records that have been stored in the Skype for Business Server Archiving database.</span></span>  <br/> |
|<span data-ttu-id="16440-136">CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="16440-136">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="16440-137">傳回貴組織中的存檔設定設定的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="16440-137">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="16440-138">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="16440-138">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="16440-139">傳回貴組織的內部和外部通訊原則的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="16440-139">Returns information about your organization's archiving policies for internal and external communications.</span></span>  <br/> |
|<span data-ttu-id="16440-140">授與 CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="16440-140">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="16440-141">將立即訊息 (IM) 會話存檔原則指派給使用者或使用者組。</span><span class="sxs-lookup"><span data-stu-id="16440-141">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="16440-142">這些原則可讓您封存在內部使用者之間進行的所有 IM 會話, 以及/或封存在內部使用者與外部合作夥伴之間發生的所有 IM 會話。</span><span class="sxs-lookup"><span data-stu-id="16440-142">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="16440-143">Invoke-CsArchivingDatabasePurge</span><span class="sxs-lookup"><span data-stu-id="16440-143">Invoke-CsArchivingDatabasePurge</span></span>  <br/> |<span data-ttu-id="16440-144">手動清除封存資料庫中的記錄。</span><span class="sxs-lookup"><span data-stu-id="16440-144">Manually purges records from the Archiving database.</span></span>  <br/> |
|<span data-ttu-id="16440-145">新-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="16440-145">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="16440-146">建立一組新的立即訊息 (IM) 設定, 這可以用來啟用或停用自動儲存 IM 會話, 並封鎖任何無法封存的立即訊息。</span><span class="sxs-lookup"><span data-stu-id="16440-146">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="16440-147">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="16440-147">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="16440-148">建立新的立即訊息 (IM) 會話存檔原則。</span><span class="sxs-lookup"><span data-stu-id="16440-148">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="16440-149">這些原則可讓您封存在內部使用者之間進行的所有 IM 會話, 以及/或封存在內部使用者與外部合作夥伴之間發生的所有 IM 會話。</span><span class="sxs-lookup"><span data-stu-id="16440-149">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="16440-150">移除-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="16440-150">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="16440-151">移除指定的存檔設定集合, 這些設定是用來啟用或停用立即訊息 (IM) 會話, 以及選擇性地封鎖任何無法封存的立即訊息。</span><span class="sxs-lookup"><span data-stu-id="16440-151">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="16440-152">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="16440-152">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="16440-153">移除指定的立即訊息 (IM) 封存原則, 決定商務用 Skype 伺服器是否會自動儲存所有內部使用者之間發生的 IM 會話, 以及/或內部使用者與同盟合作夥伴之間的所有 IM 會話。</span><span class="sxs-lookup"><span data-stu-id="16440-153">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="16440-154">Set-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="16440-154">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="16440-155">修改現有的立即訊息 (IM) 封存配置選項組合。</span><span class="sxs-lookup"><span data-stu-id="16440-155">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |
|<span data-ttu-id="16440-156">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="16440-156">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="16440-157">修改現有的立即訊息 (IM) 封存原則。</span><span class="sxs-lookup"><span data-stu-id="16440-157">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="16440-158">存檔原則可讓您將在內部使用者之間發生的所有 IM 會議與會議封存在一起。您也可以封存在內部使用者和聯盟夥伴之間發生的會話。</span><span class="sxs-lookup"><span data-stu-id="16440-158">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="16440-159">Set-CsArchivingServer</span><span class="sxs-lookup"><span data-stu-id="16440-159">Set-CsArchivingServer</span></span>  <br/> |<span data-ttu-id="16440-160">可讓您為一或多個存檔伺服器指定新的資料庫位置。</span><span class="sxs-lookup"><span data-stu-id="16440-160">Enables you to specify a new database location for one or more Archiving Servers.</span></span>  <br/> |
   

