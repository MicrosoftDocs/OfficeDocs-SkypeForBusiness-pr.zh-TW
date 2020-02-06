---
title: 在商務用 Skype Server 中建立或修改 CDR 配置設定的集合
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
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: 摘要：瞭解商務用 Skype Server 中的通話詳細資料錄製（CDR）。
ms.openlocfilehash: 88e86aaec7ca922db39b8c74dc1b354ab0389ba7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818043"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="3f227-103">在商務用 Skype Server 中建立或修改 CDR 配置設定的集合</span><span class="sxs-lookup"><span data-stu-id="3f227-103">Create or modify a collection of CDR configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="3f227-104">**摘要：** 瞭解商務用 Skype Server 中的通話詳細資料錄製（CDR）。</span><span class="sxs-lookup"><span data-stu-id="3f227-104">**Summary:** Learn about Call detail recording (CDR) in Skype for Business Server.</span></span>
  
<span data-ttu-id="3f227-105">通話詳細資料錄製（CDR）可讓您追蹤諸如對等立即訊息會話、透過網際網路通訊協定（VoIP）電話撥打電話及會議呼叫等專案的使用方式。</span><span class="sxs-lookup"><span data-stu-id="3f227-105">Call detail recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls.</span></span> <span data-ttu-id="3f227-106">此使用量資料包括呼叫者、呼叫者及交談時間的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="3f227-106">This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="3f227-107">當您安裝商務用 Skype Server 時，系統會為您建立單一、全域的 CDR 配置設定。</span><span class="sxs-lookup"><span data-stu-id="3f227-107">When you install Skype for Business Server a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="3f227-108">系統管理員也可以選擇在網站範圍中建立自訂設定。</span><span class="sxs-lookup"><span data-stu-id="3f227-108">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="3f227-109">只要使用這些網站範圍的設定，就會優先于全域設定。</span><span class="sxs-lookup"><span data-stu-id="3f227-109">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="3f227-110">例如，如果您為雷德蒙的網站建立網站範圍的設定，則這些設定（而不是 [全域設定]）將會用於管理雷德蒙者中的 CDR。</span><span class="sxs-lookup"><span data-stu-id="3f227-110">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage CDR in Redmond.</span></span>
  
<span data-ttu-id="3f227-111">您可以使用商務用 Skype Server 的 [控制台] 或[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) Cmdlet 來建立 CDR 配置設定。</span><span class="sxs-lookup"><span data-stu-id="3f227-111">You can create CDR configuration settings by using either Skype for Business Server Control Panel or the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="3f227-112">您可以使用商務用 Skype Server 的 [控制台] 或[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) Cmdlet 來修改現有的設定。</span><span class="sxs-lookup"><span data-stu-id="3f227-112">You can use Skype for Business Server Control Panel or the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet to modify existing settings.</span></span> <span data-ttu-id="3f227-113">如果您使用商務用 Skype Server 的 [控制台] 來建立或修改設定，您可以使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="3f227-113">If you are using Skype for Business Server Control Panel to create or modify settings, the following options will be available to you:</span></span>
  
|<span data-ttu-id="3f227-114">**UI 設定**</span><span class="sxs-lookup"><span data-stu-id="3f227-114">**UI setting**</span></span>|<span data-ttu-id="3f227-115">**PowerShell 參數**</span><span class="sxs-lookup"><span data-stu-id="3f227-115">**PowerShell parameter**</span></span>|<span data-ttu-id="3f227-116">**說明**</span><span class="sxs-lookup"><span data-stu-id="3f227-116">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3f227-117">名稱</span><span class="sxs-lookup"><span data-stu-id="3f227-117">Name</span></span>  <br/> |<span data-ttu-id="3f227-118">Identity</span><span class="sxs-lookup"><span data-stu-id="3f227-118">Identity</span></span>  <br/> |<span data-ttu-id="3f227-119">所建立的 CDR 配置設定的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="3f227-119">Unique identifier for the CDR configuration settings being created.</span></span> <span data-ttu-id="3f227-120">這些設定只能在網站範圍建立。</span><span class="sxs-lookup"><span data-stu-id="3f227-120">These settings can only be created at the site scope.</span></span>  <br/> |
|<span data-ttu-id="3f227-121">啟用 CDRs 的監控</span><span class="sxs-lookup"><span data-stu-id="3f227-121">Enable monitoring of CDRs</span></span>  <br/> |<span data-ttu-id="3f227-122">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="3f227-122">EnableCDR</span></span>  <br/> |<span data-ttu-id="3f227-123">指出是否已啟用 CDR。</span><span class="sxs-lookup"><span data-stu-id="3f227-123">Indicates whether or not CDR is enabled.</span></span>  <br/> |
|<span data-ttu-id="3f227-124">啟用清除 CDRs</span><span class="sxs-lookup"><span data-stu-id="3f227-124">Enable purging of CDRs</span></span>  <br/> |<span data-ttu-id="3f227-125">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="3f227-125">EnablePurging</span></span>  <br/> |<span data-ttu-id="3f227-126">指出 CDR 記錄是否會定期從 CDR 資料庫中刪除。</span><span class="sxs-lookup"><span data-stu-id="3f227-126">Indicates whether or not CDR records will periodically be deleted from the CDR database.</span></span>  <br/> |
|<span data-ttu-id="3f227-127">保留 CDRs 的最大持續時間（天）</span><span class="sxs-lookup"><span data-stu-id="3f227-127">Keep CDRs for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="3f227-128">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="3f227-128">KeepCallDetailForDays</span></span>  <br/> |<span data-ttu-id="3f227-129">表示 CDR 記錄將保留在 CDR 資料庫中的天數。</span><span class="sxs-lookup"><span data-stu-id="3f227-129">Indicates the number of days that CDR records will be kept in the CDR database.</span></span> <span data-ttu-id="3f227-130">任何超過指定天數的記錄都會自動刪除。</span><span class="sxs-lookup"><span data-stu-id="3f227-130">Any records older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="3f227-131">（請注意，清除功能只會在已啟用清除時才會發生。）</span><span class="sxs-lookup"><span data-stu-id="3f227-131">(Note that purging will take only place if purging has been enabled.)</span></span>  <br/> |
|<span data-ttu-id="3f227-132">針對最大持續時間（天）保留錯誤報表資料</span><span class="sxs-lookup"><span data-stu-id="3f227-132">Keep error report data for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="3f227-133">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="3f227-133">KeepErrorReportForDays</span></span>  <br/> |<span data-ttu-id="3f227-134">表示保留 CDR 錯誤報表的天數。</span><span class="sxs-lookup"><span data-stu-id="3f227-134">Indicates the number of days that CDR error reports are kept.</span></span> <span data-ttu-id="3f227-135">任何超過指定天數的報告都會自動刪除。</span><span class="sxs-lookup"><span data-stu-id="3f227-135">Any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="3f227-136">CDR 錯誤報表是用戶端應用程式上傳的診斷報告。</span><span class="sxs-lookup"><span data-stu-id="3f227-136">CDR error reports are diagnostic reports uploaded by client applications.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="3f227-137">新的-CsCdrConfiguration 和 CsCdrConfiguration Cmdlet 包括在商務用 Skype Server [控制台] 中無法使用的其他選項。</span><span class="sxs-lookup"><span data-stu-id="3f227-137">The New-CsCdrConfiguration and Set-CsCdrConfiguration cmdlets include additional options not available in Skype for Business Server Control Panel.</span></span> <span data-ttu-id="3f227-138">如需詳細資訊，請參閱[新的-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)和[設定 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)的協助主題。</span><span class="sxs-lookup"><span data-stu-id="3f227-138">See the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) and the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) help topics for more information.</span></span>
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="3f227-139">使用商務用 Skype Server [控制台] 建立 CDR 配置設定</span><span class="sxs-lookup"><span data-stu-id="3f227-139">To create CDR configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="3f227-140">在商務用 Skype Server 的 [控制台] 中，按一下 [**監視及**封存]。</span><span class="sxs-lookup"><span data-stu-id="3f227-140">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="3f227-141">在 [**通話詳細資料記錄**] 索引標籤上，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="3f227-141">On the **Call Detail Recording** tab, click **New**.</span></span>
    
3. <span data-ttu-id="3f227-142">在 [**選取網站**] 對話方塊中，選取要建立新配置設定的網站。</span><span class="sxs-lookup"><span data-stu-id="3f227-142">In the **Select a Site** dialog box, select the site where the new configuration settings are to be created.</span></span> <span data-ttu-id="3f227-143">如果對話方塊是空白的，則表示您的所有網站都已指派給 CDR 配置設定的集合。</span><span class="sxs-lookup"><span data-stu-id="3f227-143">If the dialog box is empty, that means all of your sites have already been assigned a collection of CDR configuration settings.</span></span> <span data-ttu-id="3f227-144">每個網站僅限一個此類集合。</span><span class="sxs-lookup"><span data-stu-id="3f227-144">Each site is limited to a single such collection.</span></span> <span data-ttu-id="3f227-145">在這種情況下，您可以刪除並重新建立設定，或直接修改現有的設定。</span><span class="sxs-lookup"><span data-stu-id="3f227-145">In that case you can either delete and then re-create the settings, or simply modify the existing settings.</span></span>
    
4. <span data-ttu-id="3f227-146">在 [**新增通話詳細資料錄製（CDR）設定**] 對話方塊中，選取所要的選項，然後按一下 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="3f227-146">In the **New Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="3f227-147">使用商務用 Skype Server [控制台] 修改現有的 CDR 配置設定</span><span class="sxs-lookup"><span data-stu-id="3f227-147">To modify existing CDR configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="3f227-148">在商務用 Skype Server 的 [控制台] 中，按一下 [**監視及**封存]。</span><span class="sxs-lookup"><span data-stu-id="3f227-148">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="3f227-149">按兩下要修改的設定集合，或選取該收藏，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="3f227-149">Double-click the collection of settings to be modified, or select the collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="3f227-150">請注意，您一次只能修改單一集合。</span><span class="sxs-lookup"><span data-stu-id="3f227-150">Note that you can only modify a single collection at a time.</span></span> <span data-ttu-id="3f227-151">若要對多個收藏進行相同的變更，請改用商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="3f227-151">To make the same changes to multiple collections, use the Skype for Business Server Management Shell instead.</span></span>
    
3. <span data-ttu-id="3f227-152">在 [**編輯通話詳細資料錄製（CDR）] 設定**對話方塊中，選取所要的選項，然後按一下 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="3f227-152">In the **Edit Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3f227-153">使用 Windows PowerShell Cmdlet 建立 CDR 配置設定</span><span class="sxs-lookup"><span data-stu-id="3f227-153">Creating CDR configuration settings by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3f227-154">您也可以使用 Windows PowerShell 和**CsCdrConfiguration** Cmdlet 來建立 CDR 配置設定。</span><span class="sxs-lookup"><span data-stu-id="3f227-154">You can create CDR configuration settings can also be created by using Windows PowerShell and the **New-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="3f227-155">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3f227-155">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3f227-156">如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料，請參閱博客文章[：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="3f227-156">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="3f227-157">在商務用 Skype 伺服器中，程式是一樣的。</span><span class="sxs-lookup"><span data-stu-id="3f227-157">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="3f227-158">若要建立新的 CDR 配置設定集合</span><span class="sxs-lookup"><span data-stu-id="3f227-158">To create a new collection of CDR configuration settings</span></span>

 <span data-ttu-id="3f227-159">這個命令會建立套用至雷德蒙網站的 CDR 設定設定的新集合：</span><span class="sxs-lookup"><span data-stu-id="3f227-159">This command creates a new collection of CDR configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="3f227-160">若要建立停用通話詳細資料錄製的 CDR 配置設定集合</span><span class="sxs-lookup"><span data-stu-id="3f227-160">To create a collection of CDR configuration settings that disable call detail recording</span></span>

 <span data-ttu-id="3f227-161">因為在上述命令中沒有指定任何參數（強制身分識別參數以外），所以新的配置設定集合會將預設值用於其所有屬性。</span><span class="sxs-lookup"><span data-stu-id="3f227-161">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> <span data-ttu-id="3f227-162">若要建立使用不同屬性值的設定，只要包含適當的參數和參數值即可。</span><span class="sxs-lookup"><span data-stu-id="3f227-162">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="3f227-163">例如，若要建立通話詳細資料設定的集合，根據預設，允許停用通話詳細資料錄製使用如下所示的命令：</span><span class="sxs-lookup"><span data-stu-id="3f227-163">For example, to create a collection of Call Detail configuration settings that, by default, allow disable Call Detail recording use a command like this:</span></span>
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="3f227-164">建立新的 CDR 配置設定集合時，指定多個屬性值</span><span class="sxs-lookup"><span data-stu-id="3f227-164">To specify multiple property values when creating a new collection of CDR configuration settings</span></span>

 <span data-ttu-id="3f227-165">您可以透過包含多個參數來修改多個屬性值。</span><span class="sxs-lookup"><span data-stu-id="3f227-165">You can modify multiple property values by including multiple parameters.</span></span> <span data-ttu-id="3f227-166">例如，這個命令會將新設定設定為將呼叫詳細資料記錄保持在30天，並將錯誤報表保留90天：</span><span class="sxs-lookup"><span data-stu-id="3f227-166">For example, this command configures the new settings to keep Call Detail records for 30 days and error reports for 90 days:</span></span>
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

<span data-ttu-id="3f227-167">如需詳細資訊，請參閱[新版-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="3f227-167">For more information, see the help topic for the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  

