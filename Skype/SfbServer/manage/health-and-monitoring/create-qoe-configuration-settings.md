---
title: 在商務用 Skype Server 中建立體驗配置設定品質
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
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: 摘要：瞭解商務用 Skype Server 中的體驗品質（QoE）設定。
ms.openlocfilehash: 5366937f1faa01e6533b51677122713ee9e839fa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818033"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="d4238-103">在商務用 Skype Server 中建立體驗配置設定品質</span><span class="sxs-lookup"><span data-stu-id="d4238-103">Create Quality of Experience configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="d4238-104">**摘要：** 瞭解商務用 Skype Server 中的體驗品質（QoE）設定。</span><span class="sxs-lookup"><span data-stu-id="d4238-104">**Summary:** Learn about Quality of Experience (QoE) settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="d4238-105">經驗品質（QoE）度量單位會追蹤您組織中的音訊和視頻通話品質，包括網路資料包遺失、背景雜色及「抖動」（資料包延遲的差異）的數量。</span><span class="sxs-lookup"><span data-stu-id="d4238-105">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span> <span data-ttu-id="d4238-106">這些度量單位會與其他資料（例如通話明細記錄）之外，儲存在資料庫中，讓您可以啟用和停用與其他資料錄製無關的 QoE。</span><span class="sxs-lookup"><span data-stu-id="d4238-106">These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="d4238-107">當您安裝商務用 Skype Server 時，系統會為您建立單一、全域的 QoE 配置設定集合。</span><span class="sxs-lookup"><span data-stu-id="d4238-107">When you install Skype for Business Server, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="d4238-108">系統管理員也可以選擇在網站範圍中建立自訂設定。</span><span class="sxs-lookup"><span data-stu-id="d4238-108">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="d4238-109">只要使用這些網站範圍的設定，就會優先于全域設定。</span><span class="sxs-lookup"><span data-stu-id="d4238-109">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="d4238-110">例如，如果您為雷德蒙的網站建立網站範圍的設定，則這些設定（而不是 [全域設定]）將會用於管理雷德蒙的 QoE。</span><span class="sxs-lookup"><span data-stu-id="d4238-110">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>
  
<span data-ttu-id="d4238-111">您可以使用商務用 Skype Server 的 [控制台] 或[新的-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) Cmdlet 來建立 QoE 設定設定。</span><span class="sxs-lookup"><span data-stu-id="d4238-111">QoE configuration settings can be created by using either Skype for Business Server Control Panel or the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="d4238-112">如果您使用商務用 Skype Server 的 [控制台] 來建立新設定，您可以使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="d4238-112">If you are using Skype for Business Server Control Panel to create new settings the following options will be available to you:</span></span>
  
|<span data-ttu-id="d4238-113">**UI 設定**</span><span class="sxs-lookup"><span data-stu-id="d4238-113">**UI setting**</span></span>|<span data-ttu-id="d4238-114">**PowerShell 參數**</span><span class="sxs-lookup"><span data-stu-id="d4238-114">**PowerShell parameter**</span></span>|<span data-ttu-id="d4238-115">**說明**</span><span class="sxs-lookup"><span data-stu-id="d4238-115">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d4238-116">名稱</span><span class="sxs-lookup"><span data-stu-id="d4238-116">Name</span></span>  <br/> |<span data-ttu-id="d4238-117">Identity</span><span class="sxs-lookup"><span data-stu-id="d4238-117">Identity</span></span>  <br/> |<span data-ttu-id="d4238-118">要建立之設定的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="d4238-118">Unique identifier for the settings to be created.</span></span> <span data-ttu-id="d4238-119">QoE 設定只能在網站範圍建立。</span><span class="sxs-lookup"><span data-stu-id="d4238-119">QoE configuration settings can only be created at the site scope.</span></span>  <br/> |
|<span data-ttu-id="d4238-120">啟用監視 QoE 資料</span><span class="sxs-lookup"><span data-stu-id="d4238-120">Enable monitoring of QoE data</span></span>  <br/> |<span data-ttu-id="d4238-121">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="d4238-121">EnableQoE</span></span>  <br/> |<span data-ttu-id="d4238-122">指定是否要收集 QoE 記錄並將它儲存到監視資料庫。</span><span class="sxs-lookup"><span data-stu-id="d4238-122">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span>  <br/> |
|<span data-ttu-id="d4238-123">啟用清除 QoE 資料</span><span class="sxs-lookup"><span data-stu-id="d4238-123">Enable purging of QoE data</span></span>  <br/> |<span data-ttu-id="d4238-124">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="d4238-124">EnablePurging</span></span>  <br/> |<span data-ttu-id="d4238-125">指定是否要在 [保留 QoE 資料] 中定義的持續時間 **（天數）** 屬性已過久之後，才清除記錄。</span><span class="sxs-lookup"><span data-stu-id="d4238-125">Specifies whether records will be purged after the duration defined in the **Keep QoE data for a maximum duration (days)** property has elapsed.</span></span> <br/> |
|<span data-ttu-id="d4238-126">保留 QoE 資料以取得最長持續時間（天）</span><span class="sxs-lookup"><span data-stu-id="d4238-126">Keep QoE data for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="d4238-127">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="d4238-127">KeepQoEDataForDays</span></span>  <br/> |<span data-ttu-id="d4238-128">從資料庫清除 QoE 資料前要儲存的天數。</span><span class="sxs-lookup"><span data-stu-id="d4238-128">Number of days QoE data will be stored before being purged from the database.</span></span> <span data-ttu-id="d4238-129">如果停用清除功能，就會忽略這個值。</span><span class="sxs-lookup"><span data-stu-id="d4238-129">This value is ignored if purging is disabled.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="d4238-130">CsQoEConfiguration Cmdlet 包含無法在商務用 Skype Server [控制台] 中使用的其他選項。</span><span class="sxs-lookup"><span data-stu-id="d4238-130">The New-CsQoEConfiguration cmdlet includes additional options not available in Skype for Business Server Control Panel.</span></span> <span data-ttu-id="d4238-131">如需詳細資訊，請參閱[新的 CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)說明主題。</span><span class="sxs-lookup"><span data-stu-id="d4238-131">For more information, see the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) help topic.</span></span>
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d4238-132">使用商務用 Skype Server [控制台] 建立 QoE 設定設定</span><span class="sxs-lookup"><span data-stu-id="d4238-132">To create QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d4238-133">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="d4238-133">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="d4238-134">如需詳細資訊，請參閱**委派設定許可權**。</span><span class="sxs-lookup"><span data-stu-id="d4238-134">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="d4238-135">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="d4238-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="d4238-136">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [**體驗資料品質**]。</span><span class="sxs-lookup"><span data-stu-id="d4238-136">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="d4238-137">在 [**體驗品質資料**] 頁面上，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="d4238-137">On the **Quality of Experience Data** page, click **New**.</span></span>
    
5. <span data-ttu-id="d4238-138">在 [**選取網站**] 中，按一下要套用原則的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d4238-138">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>
    
6. <span data-ttu-id="d4238-139">在 [**新的體驗品質] 設定**中，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d4238-139">In **New Quality of Experience Setting**, do the following:</span></span>
    
   - <span data-ttu-id="d4238-140">選取 [**啟用 QoE 資料監視**] 來開啟監視。</span><span class="sxs-lookup"><span data-stu-id="d4238-140">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
   - <span data-ttu-id="d4238-141">選取 [**啟用清除 QoE 資料**] 以開啟 [清除]。</span><span class="sxs-lookup"><span data-stu-id="d4238-141">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
   - <span data-ttu-id="d4238-142">在 **[保留 QoE 的最大持續時間（天）**] 中，選取 QoE 記錄應保留的最大天數。</span><span class="sxs-lookup"><span data-stu-id="d4238-142">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>
    
7. <span data-ttu-id="d4238-143">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d4238-143">Click **Commit**.</span></span>
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d4238-144">使用 Windows PowerShell Cmdlet 建立 QoE 配置設定</span><span class="sxs-lookup"><span data-stu-id="d4238-144">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d4238-145">您可以使用 Windows PowerShell 和 CsQoEConfiguration Cmdlet 來建立 QoE 配置設定。</span><span class="sxs-lookup"><span data-stu-id="d4238-145">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="d4238-146">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d4238-146">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d4238-147">如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料，請參閱博客文章[：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="d4238-147">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="d4238-148">在商務用 Skype 伺服器中，程式是一樣的。</span><span class="sxs-lookup"><span data-stu-id="d4238-148">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="d4238-149">若要建立新的 QoE 配置設定集合</span><span class="sxs-lookup"><span data-stu-id="d4238-149">To create a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="d4238-150">這個命令會建立套用至雷德蒙網站之 QoE 設定設定的新集合：</span><span class="sxs-lookup"><span data-stu-id="d4238-150">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="d4238-151">若要在停用 QoE 監視的情況下，建立新的 QoE 配置設定集合</span><span class="sxs-lookup"><span data-stu-id="d4238-151">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="d4238-152">因為在上述命令中沒有指定任何參數（強制身分識別參數以外），所以新的配置設定集合會將預設值用於其所有屬性。</span><span class="sxs-lookup"><span data-stu-id="d4238-152">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> <span data-ttu-id="d4238-153">若要建立使用不同屬性值的設定，只要包含適當的參數和參數值即可。</span><span class="sxs-lookup"><span data-stu-id="d4238-153">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="d4238-154">例如，若要建立經驗品質設定的集合，請根據預設，允許停用 QoE 錄製使用如下所示的命令：</span><span class="sxs-lookup"><span data-stu-id="d4238-154">For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="d4238-155">建立新的 QoE 配置設定集合時，指定多個屬性值</span><span class="sxs-lookup"><span data-stu-id="d4238-155">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="d4238-156">您可以加入多個參數，以使用多個屬性值。</span><span class="sxs-lookup"><span data-stu-id="d4238-156">You can multiple property values by including multiple parameters.</span></span> <span data-ttu-id="d4238-157">例如，這個命令會將新設定設為保留30天的 QoE 資料，並在 3:00 AM 清除舊資料：</span><span class="sxs-lookup"><span data-stu-id="d4238-157">For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

<span data-ttu-id="d4238-158">如需詳細資訊，請參閱[新版-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="d4238-158">For more information, see the help topic for the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  

