---
title: 管理商務用 Skype Server 中的封存
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
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: 摘要：瞭解如何管理商務用 Skype 伺服器的封存。
ms.openlocfilehash: 3c84fe35e59d14f957391ecb9bdc503e1bff6b87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817733"
---
# <a name="manage-archiving-in-skype-for-business-server"></a><span data-ttu-id="2bf8e-103">管理商務用 Skype Server 中的封存</span><span class="sxs-lookup"><span data-stu-id="2bf8e-103">Manage archiving in Skype for Business Server</span></span>

<span data-ttu-id="2bf8e-104">**摘要：** 瞭解如何管理商務用 Skype Server 的封存。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-104">**Summary:** Learn how to manage archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="2bf8e-105">當您為組織部署封存時，您會在部署期間指定初始設定。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-105">When you deploy archiving for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="2bf8e-106">不過，有時候您可能想要變更如何針對日常管理執行封存支援，或符合貴組織的新需求。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-106">However, there may be times when you want to change how you implement archiving support for day-to-day management or to meet new requirements for your organization.</span></span> <span data-ttu-id="2bf8e-107">例如，您可能需要為特定網站、特定集區或組織內的特定使用者設定不同的封存支援。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-107">For example, you may need to set up archiving support differently for a specific site, a specific pool, or specific users within your organization.</span></span> <span data-ttu-id="2bf8e-108">針對駐留在商務用 Skype Server 的使用者，您可以建立及自訂封存設定選項和使用者原則，以執行此動作。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-108">For users homed on Skype for Business Server, you do this by creating and customizing archiving configuration options and user policies.</span></span> 
  
<span data-ttu-id="2bf8e-109">閱讀本主題之前，請確定您已熟悉 [規劃商務用 Skype server](../../plan-your-deployment/archiving/archiving.md) 中的封存資訊，以及如何 [部署商務用 skype server](../../deploy/deploy-archiving/deploy-archiving.md)的封存。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-109">Before you read this topic, be sure you are familiar with the information in [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Deploy archiving for Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2bf8e-110">如果您為部署啟用 Microsoft Exchange 整合，Exchange 原則會控制是否為位於 Exchange 上的使用者啟用封存，並將其信箱置於 In-Place 保留狀態。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-110">If you enable Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="2bf8e-111">如需詳細資訊，請參閱 Plan for 封存 [In 商務用 Skype server](../../plan-your-deployment/archiving/archiving.md) 和 [設定與 Exchange storage 的整合（適用于商務用 skype 伺服器](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)）。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="archiving-configuration-options"></a><span data-ttu-id="2bf8e-112">封存設定選項</span><span class="sxs-lookup"><span data-stu-id="2bf8e-112">Archiving configuration options</span></span>

<span data-ttu-id="2bf8e-113">封存設定選項指定是否：</span><span class="sxs-lookup"><span data-stu-id="2bf8e-113">Archiving configuration options specify whether to:</span></span>
  
- <span data-ttu-id="2bf8e-114">啟用或停用封存</span><span class="sxs-lookup"><span data-stu-id="2bf8e-114">Enable or disable archiving</span></span>
    
- <span data-ttu-id="2bf8e-115">封存 IM 工作階段</span><span class="sxs-lookup"><span data-stu-id="2bf8e-115">Archive IM sessions</span></span>
    
- <span data-ttu-id="2bf8e-116">封存 web 會議會話</span><span class="sxs-lookup"><span data-stu-id="2bf8e-116">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="2bf8e-117">封存無法使用時封鎖活動</span><span class="sxs-lookup"><span data-stu-id="2bf8e-117">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="2bf8e-118">使用 Exchange 整合</span><span class="sxs-lookup"><span data-stu-id="2bf8e-118">Use Exchange integration</span></span>
    
- <span data-ttu-id="2bf8e-119">設定資料的清除和匯出</span><span class="sxs-lookup"><span data-stu-id="2bf8e-119">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="2bf8e-120">您可以在全域、網站或集區層級設定這些選項。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-120">These options can be set at the global, site, or pool level.</span></span> <span data-ttu-id="2bf8e-121">如需詳細資訊，請參閱 [Manage 封存 options In 商務用 Skype Server](options.md)。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-121">For more information, see [Manage archiving options in Skype for Business Server](options.md).</span></span>
  
## <a name="archiving-policies"></a><span data-ttu-id="2bf8e-122">封存原則</span><span class="sxs-lookup"><span data-stu-id="2bf8e-122">Archiving policies</span></span>

<span data-ttu-id="2bf8e-123">封存原則決定是否要封存下列專案：</span><span class="sxs-lookup"><span data-stu-id="2bf8e-123">Archiving policies determine whether to archive the following:</span></span>
  
- <span data-ttu-id="2bf8e-124">內部通訊</span><span class="sxs-lookup"><span data-stu-id="2bf8e-124">Internal communications</span></span>
    
- <span data-ttu-id="2bf8e-125">外部通訊</span><span class="sxs-lookup"><span data-stu-id="2bf8e-125">External communications</span></span>
    
<span data-ttu-id="2bf8e-126">您可以在全域、網站或使用者層級設定這些原則。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-126">These policies can be set at the global, site, or user level.</span></span> <span data-ttu-id="2bf8e-127">如需詳細資訊，請參閱 [在商務用 Skype Server 中管理封存原則](policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-127">For more information, see [Manage archiving policies in Skype for Business Server](policies.md).</span></span>
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a><span data-ttu-id="2bf8e-128">使用控制台或使用 Windows PowerShell 管理封存</span><span class="sxs-lookup"><span data-stu-id="2bf8e-128">Manage archiving by using the Control Panel or by using Windows PowerShell</span></span>

<span data-ttu-id="2bf8e-129">您可以使用 [控制台] 或使用 Windows PowerShell 管理封存。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-129">You can manage archiving by using the Control Panel or by using Windows PowerShell.</span></span> <span data-ttu-id="2bf8e-130">下表摘要說明可協助您管理封存的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-130">The following table summarizes the cmdlets available to help you manage archiving.</span></span> <span data-ttu-id="2bf8e-131">如需語法的詳細資訊（包括所有可用參數），請參閱 [商務用 Skype Server 管理命令](../management-shell.md)介面。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-131">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span> 


|<span data-ttu-id="2bf8e-132">**指令程式**</span><span class="sxs-lookup"><span data-stu-id="2bf8e-132">**Cmdlet**</span></span>|<span data-ttu-id="2bf8e-133">**描述**</span><span class="sxs-lookup"><span data-stu-id="2bf8e-133">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2bf8e-134">Export-CsArchivingData</span><span class="sxs-lookup"><span data-stu-id="2bf8e-134">Export-CsArchivingData</span></span>  <br/> |<span data-ttu-id="2bf8e-135">匯出已儲存在商務用 Skype Server 封存資料庫中的記錄。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-135">Exports records that have been stored in the Skype for Business Server Archiving database.</span></span>  <br/> |
|<span data-ttu-id="2bf8e-136">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="2bf8e-136">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="2bf8e-137">傳回組織中封存設定設定的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-137">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="2bf8e-138">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="2bf8e-138">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="2bf8e-139">傳回組織內部和外部通訊的封存原則資訊。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-139">Returns information about your organization's archiving policies for internal and external communications.</span></span>  <br/> |
|<span data-ttu-id="2bf8e-140">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="2bf8e-140">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="2bf8e-141">指派立即訊息 (IM) 會話封存原則指派給使用者或使用者組。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-141">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="2bf8e-142">這些原則可讓您封存內部使用者之間及/或封存內部使用者與外部協力廠商之間所發生的所有 IM 工作階段。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-142">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="2bf8e-143">Invoke-CsArchivingDatabasePurge</span><span class="sxs-lookup"><span data-stu-id="2bf8e-143">Invoke-CsArchivingDatabasePurge</span></span>  <br/> |<span data-ttu-id="2bf8e-144">手動清除封存資料庫中的記錄。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-144">Manually purges records from the Archiving database.</span></span>  <br/> |
|<span data-ttu-id="2bf8e-145">New-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="2bf8e-145">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="2bf8e-146">會建立一組新的立即訊息 (IM) 設定，可用來啟用或停用自動儲存 IM 會話，並封鎖任何無法封存的立即訊息。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-146">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="2bf8e-147">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="2bf8e-147">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="2bf8e-148">建立新的立即訊息 (IM) 會話封存原則。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-148">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="2bf8e-149">這些原則可讓您封存內部使用者之間及/或封存內部使用者與外部協力廠商之間所發生的所有 IM 工作階段。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-149">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="2bf8e-150">Remove-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="2bf8e-150">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="2bf8e-151">移除指定的封存設定集合，用來啟用或停用自動儲存立即訊息 (IM) 會話，並選擇性地封鎖無法封存的任何立即訊息。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-151">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="2bf8e-152">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="2bf8e-152">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="2bf8e-153">移除指定的立即訊息 (IM) 封存原則，可判斷商務用 Skype 伺服器是否會自動儲存內部使用者和/或內部使用者與同盟協力廠商之間所有 IM 會話之間所發生的所有 IM 會話。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-153">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="2bf8e-154">Set-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="2bf8e-154">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="2bf8e-155">修改現有的立即訊息 (IM 集合) 封存設定選項。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-155">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |
|<span data-ttu-id="2bf8e-156">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="2bf8e-156">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="2bf8e-157">修改現有的立即訊息 (IM) 封存原則。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-157">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="2bf8e-158">封存原則讓您能夠封存內部使用者之間所發生的所有 IM 會話和會議。您也可以封存在內部使用者與同盟協力廠商之間進行的會話。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-158">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="2bf8e-159">Set-CsArchivingServer</span><span class="sxs-lookup"><span data-stu-id="2bf8e-159">Set-CsArchivingServer</span></span>  <br/> |<span data-ttu-id="2bf8e-160">可讓您指定一或多個封存伺服器的新資料庫位置。</span><span class="sxs-lookup"><span data-stu-id="2bf8e-160">Enables you to specify a new database location for one or more Archiving Servers.</span></span>  <br/> |
   

