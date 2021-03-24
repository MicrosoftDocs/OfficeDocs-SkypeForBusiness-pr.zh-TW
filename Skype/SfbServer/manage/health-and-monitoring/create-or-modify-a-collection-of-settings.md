---
title: 在商務用 Skype Server 中建立或修改 CDR 配置設定的集合
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
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: 摘要：瞭解商務用 Skype Server 中 (CDR) 的詳細通話記錄。
ms.openlocfilehash: da4383ef31b2d3ee781c445f2c935b79ea89bed8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095367"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="1fcf0-103">在商務用 Skype Server 中建立或修改 CDR 配置設定的集合</span><span class="sxs-lookup"><span data-stu-id="1fcf0-103">Create or modify a collection of CDR configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="1fcf0-104">**摘要：** 深入瞭解商務用 Skype Server 中 (CDR) 的詳細通話記錄。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-104">**Summary:** Learn about Call detail recording (CDR) in Skype for Business Server.</span></span>
  
<span data-ttu-id="1fcf0-105"> (CDR) 的詳細資料記錄可讓您追蹤對等立即訊息會話的使用方式，例如對等立即訊息會話、透過網際網路通訊協定 (VoIP) 電話及會議通話等事項。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-105">Call detail recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls.</span></span> <span data-ttu-id="1fcf0-106">這個使用狀況資料包含有關通話者雙方身分、通話時間以及通話時間長度的資訊。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-106">This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="1fcf0-107">當您安裝商務用 Skype Server 時，系統會為您建立單一、全域的 CDR 配置設定集合。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-107">When you install Skype for Business Server a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="1fcf0-108">系統管理員也可以選擇建立網站範圍的自訂設定。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-108">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="1fcf0-109">只要使用這些網站範圍的設定，其優先順序就高於全域設定。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-109">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="1fcf0-110">例如，如果您為 Redmond 網站建立網站範圍的設定，則這些設定 (，而不是通用設定) 將用來管理 Redmond 中的 CDR。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-110">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage CDR in Redmond.</span></span>
  
<span data-ttu-id="1fcf0-111">您可以使用商務用 Skype Server 控制台或 [CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) Cmdlet 來建立 CDR 設定設定。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-111">You can create CDR configuration settings by using either Skype for Business Server Control Panel or the [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="1fcf0-112">您可以使用商務用 Skype Server 控制台或 [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) Cmdlet 來修改現有的設定。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-112">You can use Skype for Business Server Control Panel or the [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet to modify existing settings.</span></span> <span data-ttu-id="1fcf0-113">如果您使用商務用 Skype Server 控制台建立或修改設定，您會使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="1fcf0-113">If you are using Skype for Business Server Control Panel to create or modify settings, the following options will be available to you:</span></span>
  
|<span data-ttu-id="1fcf0-114">**UI 設定**</span><span class="sxs-lookup"><span data-stu-id="1fcf0-114">**UI setting**</span></span>|<span data-ttu-id="1fcf0-115">**PowerShell 參數**</span><span class="sxs-lookup"><span data-stu-id="1fcf0-115">**PowerShell parameter**</span></span>|<span data-ttu-id="1fcf0-116">**描述**</span><span class="sxs-lookup"><span data-stu-id="1fcf0-116">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1fcf0-117">名稱</span><span class="sxs-lookup"><span data-stu-id="1fcf0-117">Name</span></span>  <br/> |<span data-ttu-id="1fcf0-118">身分識別</span><span class="sxs-lookup"><span data-stu-id="1fcf0-118">Identity</span></span>  <br/> |<span data-ttu-id="1fcf0-119">要建立之 CDR 設定設定的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-119">Unique identifier for the CDR configuration settings being created.</span></span> <span data-ttu-id="1fcf0-120">這些設定只可在網站範圍建立。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-120">These settings can only be created at the site scope.</span></span>  <br/> |
|<span data-ttu-id="1fcf0-121">啟用 Cdr 的監控</span><span class="sxs-lookup"><span data-stu-id="1fcf0-121">Enable monitoring of CDRs</span></span>  <br/> |<span data-ttu-id="1fcf0-122">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="1fcf0-122">EnableCDR</span></span>  <br/> |<span data-ttu-id="1fcf0-123">表示是否啟用 CDR。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-123">Indicates whether or not CDR is enabled.</span></span>  <br/> |
|<span data-ttu-id="1fcf0-124">啟用清除 Cdr</span><span class="sxs-lookup"><span data-stu-id="1fcf0-124">Enable purging of CDRs</span></span>  <br/> |<span data-ttu-id="1fcf0-125">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="1fcf0-125">EnablePurging</span></span>  <br/> |<span data-ttu-id="1fcf0-126">會指出是否要定期從 CDR 資料庫中刪除 CDR 記錄。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-126">Indicates whether or not CDR records will periodically be deleted from the CDR database.</span></span>  <br/> |
|<span data-ttu-id="1fcf0-127">將 Cdr 保留最大持續期間 (天數) </span><span class="sxs-lookup"><span data-stu-id="1fcf0-127">Keep CDRs for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="1fcf0-128">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="1fcf0-128">KeepCallDetailForDays</span></span>  <br/> |<span data-ttu-id="1fcf0-129">會指出 CDR 記錄會保留在 CDR 資料庫中的天數。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-129">Indicates the number of days that CDR records will be kept in the CDR database.</span></span> <span data-ttu-id="1fcf0-130">任何早于指定天數的記錄會自動刪除。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-130">Any records older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="1fcf0-131"> (請注意，只有在啟用清除功能時，才會進行清除。 ) </span><span class="sxs-lookup"><span data-stu-id="1fcf0-131">(Note that purging will take only place if purging has been enabled.)</span></span>  <br/> |
|<span data-ttu-id="1fcf0-132">將錯誤報表資料保留最大持續 (天數) </span><span class="sxs-lookup"><span data-stu-id="1fcf0-132">Keep error report data for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="1fcf0-133">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="1fcf0-133">KeepErrorReportForDays</span></span>  <br/> |<span data-ttu-id="1fcf0-134">指出 CDR 錯誤報表保留的天數。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-134">Indicates the number of days that CDR error reports are kept.</span></span> <span data-ttu-id="1fcf0-135">任何早于指定天數的報告都會自動刪除。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-135">Any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="1fcf0-136">CDR 錯誤報表是由用戶端應用程式上傳的診斷報告。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-136">CDR error reports are diagnostic reports uploaded by client applications.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="1fcf0-137">New-CsCdrConfiguration 和 Set-CsCdrConfiguration Cmdlet 包含其他無法在商務用 Skype Server 控制台中使用的選項。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-137">The New-CsCdrConfiguration and Set-CsCdrConfiguration cmdlets include additional options not available in Skype for Business Server Control Panel.</span></span> <span data-ttu-id="1fcf0-138">如需詳細資訊，請參閱 [新的 CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) 和 [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-138">See the [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) and the [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) help topics for more information.</span></span>
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1fcf0-139">使用商務用 Skype Server 控制台建立 CDR 設定設定</span><span class="sxs-lookup"><span data-stu-id="1fcf0-139">To create CDR configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1fcf0-140">在商務用 Skype Server 控制台中，按一下 [ **監視與** 封存]。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-140">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="1fcf0-141">在 [ **詳細通話記錄** ] 索引標籤上，按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-141">On the **Call Detail Recording** tab, click **New**.</span></span>
    
3. <span data-ttu-id="1fcf0-142">在 [ **選取網站** ] 對話方塊中，選取要建立新設定的網站。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-142">In the **Select a Site** dialog box, select the site where the new configuration settings are to be created.</span></span> <span data-ttu-id="1fcf0-143">如果對話方塊是空白的，表示您的所有網站都已指派 CDR 設定的集合。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-143">If the dialog box is empty, that means all of your sites have already been assigned a collection of CDR configuration settings.</span></span> <span data-ttu-id="1fcf0-144">每個網站都限制為單一這類集合。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-144">Each site is limited to a single such collection.</span></span> <span data-ttu-id="1fcf0-145">在這種情況下，您可以先刪除然後重新建立設定，或是只修改現有的設定。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-145">In that case you can either delete and then re-create the settings, or simply modify the existing settings.</span></span>
    
4. <span data-ttu-id="1fcf0-146">在 [ **新的詳細通話記錄] (CDR) 設定** ] 對話方塊中，進行想要的選擇，然後按一下 [ **認可**]。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-146">In the **New Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1fcf0-147">使用商務用 Skype Server 控制台修改現有 CDR 設定設定</span><span class="sxs-lookup"><span data-stu-id="1fcf0-147">To modify existing CDR configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1fcf0-148">在商務用 Skype Server 控制台中，按一下 [ **監視與** 封存]。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-148">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="1fcf0-149">按兩下要修改的設定集合，或選取集合，按一下 [ **編輯**]，然後按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-149">Double-click the collection of settings to be modified, or select the collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="1fcf0-150">請注意，您一次只能修改單一集合。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-150">Note that you can only modify a single collection at a time.</span></span> <span data-ttu-id="1fcf0-151">若要對多個集合進行相同的變更，請改用商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-151">To make the same changes to multiple collections, use the Skype for Business Server Management Shell instead.</span></span>
    
3. <span data-ttu-id="1fcf0-152">在 [ **編輯詳細通話記錄 (CDR) 設定** ] 對話方塊中，進行想要的選擇，然後按一下 [ **認可**]。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-152">In the **Edit Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1fcf0-153">使用 Windows PowerShell Cmdlet 建立 CDR 設定設定</span><span class="sxs-lookup"><span data-stu-id="1fcf0-153">Creating CDR configuration settings by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1fcf0-154">您也可以使用 Windows PowerShell 和 **CsCdrConfiguration** Cmdlet 來建立 CDR 設定設定。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-154">You can create CDR configuration settings can also be created by using Windows PowerShell and the **New-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="1fcf0-155">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-155">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1fcf0-156">如需使用遠端 Windows PowerShell 連線到商務用 Skype 伺服器的詳細資訊，請參閱博客文章 [：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-156">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="1fcf0-157">商務用 Skype Server 中的程式相同。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-157">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="1fcf0-158">若要建立新的 CDR 配置設定集合</span><span class="sxs-lookup"><span data-stu-id="1fcf0-158">To create a new collection of CDR configuration settings</span></span>

 <span data-ttu-id="1fcf0-159">此命令會為 Redmond 網站建立新的 CDR 設定設定集合：</span><span class="sxs-lookup"><span data-stu-id="1fcf0-159">This command creates a new collection of CDR configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="1fcf0-160">建立停用詳細通話記錄的 CDR 設定設定集合</span><span class="sxs-lookup"><span data-stu-id="1fcf0-160">To create a collection of CDR configuration settings that disable call detail recording</span></span>

 <span data-ttu-id="1fcf0-161">因為上述命令未指定參數 (除了必要的 Identity 參數)，新的組態設定集合會將預設值用於其所有屬性。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-161">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> <span data-ttu-id="1fcf0-162">若要使用不同的屬性值來建立設定，只要包含適當的參數及參數值即可。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-162">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="1fcf0-163">例如，若要建立通話詳細資料設定的集合，根據預設，允許停用詳細通話記錄，請使用類似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="1fcf0-163">For example, to create a collection of Call Detail configuration settings that, by default, allow disable Call Detail recording use a command like this:</span></span>
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="1fcf0-164">若要在建立新的 CDR 配置設定集合時指定多個屬性值</span><span class="sxs-lookup"><span data-stu-id="1fcf0-164">To specify multiple property values when creating a new collection of CDR configuration settings</span></span>

 <span data-ttu-id="1fcf0-165">您可以包含多個參數來修改多個屬性值。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-165">You can modify multiple property values by including multiple parameters.</span></span> <span data-ttu-id="1fcf0-166">例如，此命令會設定新的設定，將詳細通話記錄保留30天和錯誤報表的90天：</span><span class="sxs-lookup"><span data-stu-id="1fcf0-166">For example, this command configures the new settings to keep Call Detail records for 30 days and error reports for 90 days:</span></span>
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

<span data-ttu-id="1fcf0-167">如需詳細資訊，請參閱 [CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="1fcf0-167">For more information, see the help topic for the [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
