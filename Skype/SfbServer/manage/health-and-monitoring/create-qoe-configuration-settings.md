---
title: 在商務用 Skype Server 中建立經驗品質設定設定
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
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: 摘要：瞭解商務用 Skype Server 中 (QoE) 設定的經驗品質。
ms.openlocfilehash: d1d0b299b5cf0bbaf3627b7c90f90e7e1d958d10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816993"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="278e7-103">在商務用 Skype Server 中建立經驗品質設定設定</span><span class="sxs-lookup"><span data-stu-id="278e7-103">Create Quality of Experience configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="278e7-104">**摘要：** 深入瞭解商務用 Skype Server 中 (QoE) 設定的經驗品質。</span><span class="sxs-lookup"><span data-stu-id="278e7-104">**Summary:** Learn about Quality of Experience (QoE) settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="278e7-p101">「經驗品質 (QoE)」計量在追蹤組織中進行之音訊和視訊通話的品質，包括遺失的網路封包數量、背景雜訊和「抖動」(封包延遲差異) 等項目的數量。這些計量會儲存在與其他資料 (例如詳細通話記錄) 不同的資料庫中，讓您可獨立於其他資料記錄來啟用和停用 QoE。</span><span class="sxs-lookup"><span data-stu-id="278e7-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="278e7-107">當您安裝商務用 Skype Server 時，會為您建立單一、全域 QoE 設定的集合。</span><span class="sxs-lookup"><span data-stu-id="278e7-107">When you install Skype for Business Server, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="278e7-108">系統管理員也可以選擇建立網站範圍的自訂設定。</span><span class="sxs-lookup"><span data-stu-id="278e7-108">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="278e7-109">只要使用這些網站範圍的設定，其優先順序就高於全域設定。</span><span class="sxs-lookup"><span data-stu-id="278e7-109">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="278e7-110">例如，如果為 Redmond 網站建立網站範圍的設定，則會使用這些設定 (而非全域設定) 來管理 Redmond 的 QoE。</span><span class="sxs-lookup"><span data-stu-id="278e7-110">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>
  
<span data-ttu-id="278e7-111">您可以使用商務用 Skype Server 控制台或 [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) Cmdlet 來建立 QoE 設定設定。</span><span class="sxs-lookup"><span data-stu-id="278e7-111">QoE configuration settings can be created by using either Skype for Business Server Control Panel or the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="278e7-112">如果您使用商務用 Skype Server 控制台建立新的設定，您可以使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="278e7-112">If you are using Skype for Business Server Control Panel to create new settings the following options will be available to you:</span></span>
  
|<span data-ttu-id="278e7-113">**UI 設定**</span><span class="sxs-lookup"><span data-stu-id="278e7-113">**UI setting**</span></span>|<span data-ttu-id="278e7-114">**PowerShell 參數**</span><span class="sxs-lookup"><span data-stu-id="278e7-114">**PowerShell parameter**</span></span>|<span data-ttu-id="278e7-115">**描述**</span><span class="sxs-lookup"><span data-stu-id="278e7-115">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="278e7-116">名稱</span><span class="sxs-lookup"><span data-stu-id="278e7-116">Name</span></span>  <br/> |<span data-ttu-id="278e7-117">身分識別</span><span class="sxs-lookup"><span data-stu-id="278e7-117">Identity</span></span>  <br/> |<span data-ttu-id="278e7-p104">要建立之設定的唯一識別碼。QoE 組態設定僅可在網站範圍內建立。</span><span class="sxs-lookup"><span data-stu-id="278e7-p104">Unique identifier for the settings to be created. QoE configuration settings can only be created at the site scope.</span></span>  <br/> |
|<span data-ttu-id="278e7-120">啟用 QoE 資料的監控</span><span class="sxs-lookup"><span data-stu-id="278e7-120">Enable monitoring of QoE data</span></span>  <br/> |<span data-ttu-id="278e7-121">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="278e7-121">EnableQoE</span></span>  <br/> |<span data-ttu-id="278e7-122">指定是否將收集 QoE 記錄並儲存至監控資料庫。</span><span class="sxs-lookup"><span data-stu-id="278e7-122">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span>  <br/> |
|<span data-ttu-id="278e7-123">啟用 QoE 資料的清除</span><span class="sxs-lookup"><span data-stu-id="278e7-123">Enable purging of QoE data</span></span>  <br/> |<span data-ttu-id="278e7-124">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="278e7-124">EnablePurging</span></span>  <br/> |<span data-ttu-id="278e7-125">指定是否在 **[將 QoE 資料保留最大持續期間 (天)]** 屬性中定義的期間經過之後，將清除記錄。</span><span class="sxs-lookup"><span data-stu-id="278e7-125">Specifies whether records will be purged after the duration defined in the **Keep QoE data for a maximum duration (days)** property has elapsed.</span></span> <br/> |
|<span data-ttu-id="278e7-126">將 QoE 資料保留最大持續期間 (天)</span><span class="sxs-lookup"><span data-stu-id="278e7-126">Keep QoE data for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="278e7-127">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="278e7-127">KeepQoEDataForDays</span></span>  <br/> |<span data-ttu-id="278e7-p105">QoE 資料從資料庫清除之前將會儲存的天數。如果停用清除，將會忽略此值。</span><span class="sxs-lookup"><span data-stu-id="278e7-p105">Number of days QoE data will be stored before being purged from the database. This value is ignored if purging is disabled.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="278e7-130">New-CsQoEConfiguration Cmdlet 包含商務用 Skype Server [控制台] 中無法使用的其他選項。</span><span class="sxs-lookup"><span data-stu-id="278e7-130">The New-CsQoEConfiguration cmdlet includes additional options not available in Skype for Business Server Control Panel.</span></span> <span data-ttu-id="278e7-131">如需詳細資訊，請參閱 CsQoEConfiguration 的「 [新增-](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) 說明主題。</span><span class="sxs-lookup"><span data-stu-id="278e7-131">For more information, see the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) help topic.</span></span>
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="278e7-132">使用商務用 Skype Server 控制台建立 QoE 配置設定</span><span class="sxs-lookup"><span data-stu-id="278e7-132">To create QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="278e7-133">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="278e7-133">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="278e7-134">如需詳細資訊，請參閱＜**Delegate Setup Permissions**＞。</span><span class="sxs-lookup"><span data-stu-id="278e7-134">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="278e7-135">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="278e7-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="278e7-136">在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[經驗品質資料]**。</span><span class="sxs-lookup"><span data-stu-id="278e7-136">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="278e7-137">在 **[經驗品質資料]** 頁面上，按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="278e7-137">On the **Quality of Experience Data** page, click **New**.</span></span>
    
5. <span data-ttu-id="278e7-138">在 **[選取站台]** 中，按一下要套用原則的網站，並按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="278e7-138">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>
    
6. <span data-ttu-id="278e7-139">在 **[新的經驗品質設定]** 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="278e7-139">In **New Quality of Experience Setting**, do the following:</span></span>
    
   - <span data-ttu-id="278e7-140">選取 **[啟用經驗品質 (QoE) 資料的監控]** 開啟監控功能。</span><span class="sxs-lookup"><span data-stu-id="278e7-140">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
   - <span data-ttu-id="278e7-141">選取 **[啟用經驗品質 (QoE) 資料的清除]** 開啟清除功能。</span><span class="sxs-lookup"><span data-stu-id="278e7-141">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
   - <span data-ttu-id="278e7-142">在 **[將 QoE 資料保留最大持續期間 (天)]** 中，選取應該保留 QoE 記錄的最大天數。</span><span class="sxs-lookup"><span data-stu-id="278e7-142">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>
    
7. <span data-ttu-id="278e7-143">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="278e7-143">Click **Commit**.</span></span>
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="278e7-144">使用 Windows PowerShell Cmdlet 建立 QoE 設定設定</span><span class="sxs-lookup"><span data-stu-id="278e7-144">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="278e7-145">您可以使用 Windows PowerShell 和 New-CsQoEConfiguration Cmdlet 來建立 QoE 設定設定。</span><span class="sxs-lookup"><span data-stu-id="278e7-145">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="278e7-146">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="278e7-146">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="278e7-147">如需使用遠端 Windows PowerShell 連線到商務用 Skype 伺服器的詳細資訊，請參閱博客文章 [：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="278e7-147">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="278e7-148">商務用 Skype Server 中的程式相同。</span><span class="sxs-lookup"><span data-stu-id="278e7-148">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="278e7-149">建立新的 QoE 組態設定集合</span><span class="sxs-lookup"><span data-stu-id="278e7-149">To create a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="278e7-150">下列命令會建立要套用至 Redmond 網站的新 QoE 組態設定集合：</span><span class="sxs-lookup"><span data-stu-id="278e7-150">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="278e7-151">建立新的 QoE 組態設定集合並停用 QoE 監控</span><span class="sxs-lookup"><span data-stu-id="278e7-151">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="278e7-p109">因為上述命令未指定參數 (除了必要的 Identity 參數)，新的組態設定集合會將預設值用於其所有屬性。若要使用不同的屬性值來建立設定，只要包含適當的參數及參數值即可。例如，若要建立預設為允許停用經驗品質記錄之 QoE 組態設定的集合，請使用如下的命令：</span><span class="sxs-lookup"><span data-stu-id="278e7-p109">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="278e7-155">建立新的 QoE 組態設定集合時指定多個屬性值</span><span class="sxs-lookup"><span data-stu-id="278e7-155">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="278e7-p110">您可藉由包含多個參數來指定多個參數值。例如，下列命令會將新設定架構為將 QoE 資料保留 30 天，並在上午 3:00 清除舊資料：</span><span class="sxs-lookup"><span data-stu-id="278e7-p110">You can multiple property values by including multiple parameters. For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

<span data-ttu-id="278e7-158">如需詳細資訊，請參閱 [CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="278e7-158">For more information, see the help topic for the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  

