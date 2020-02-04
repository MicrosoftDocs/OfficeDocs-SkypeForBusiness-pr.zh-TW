---
title: Lync Server 2013：建立或修改 CDR 配置設定的集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of CDR configuration settings
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49733812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37ed8be52827f56b14c52f1bddd950ab39883cdf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="76ce3-102">在 Lync Server 2013 中建立或修改 CDR 配置設定的集合</span><span class="sxs-lookup"><span data-stu-id="76ce3-102">Create or modify a collection of CDR configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76ce3-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="76ce3-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="76ce3-104">通話詳細資料錄製（CDR）可讓您追蹤諸如對等立即訊息會話、透過網際網路通訊協定（VoIP）電話撥打電話及會議呼叫等專案的使用方式。</span><span class="sxs-lookup"><span data-stu-id="76ce3-104">Call detail recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls.</span></span> <span data-ttu-id="76ce3-105">此使用量資料包括呼叫者、呼叫者及交談時間的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="76ce3-105">This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="76ce3-106">當您安裝 Microsoft Lync Server 2013 時，系統會為您建立單一的 [CDR 設定] 設定的全域集合。</span><span class="sxs-lookup"><span data-stu-id="76ce3-106">When you install Microsoft Lync Server 2013 a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="76ce3-107">系統管理員也可以選擇在網站範圍中建立自訂設定。</span><span class="sxs-lookup"><span data-stu-id="76ce3-107">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="76ce3-108">只要使用這些網站範圍的設定，就會優先于全域設定。</span><span class="sxs-lookup"><span data-stu-id="76ce3-108">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="76ce3-109">例如，如果您為雷德蒙的網站建立網站範圍的設定，則這些設定（而不是 [全域設定]）將會用於管理雷德蒙者中的 CDR。</span><span class="sxs-lookup"><span data-stu-id="76ce3-109">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage CDR in Redmond.</span></span>

<span data-ttu-id="76ce3-110">您可以使用 Lync Server [控制台] 或[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) Cmdlet 來建立 CDR 配置設定。</span><span class="sxs-lookup"><span data-stu-id="76ce3-110">You can create CDR configuration settings by using either Lync Server Control Panel or the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span> <span data-ttu-id="76ce3-111">您可以使用 Lync Server [控制台] 或[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) Cmdlet 來修改現有的設定。</span><span class="sxs-lookup"><span data-stu-id="76ce3-111">You can use Lync Server Control Panel or the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet to modify existing settings.</span></span> <span data-ttu-id="76ce3-112">如果您使用 Lync Server [控制台] 來建立或修改設定，您可以使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="76ce3-112">If you are using Lync Server Control Panel to create or modify settings, the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76ce3-113">UI 設定</span><span class="sxs-lookup"><span data-stu-id="76ce3-113">UI Setting</span></span></th>
<th><span data-ttu-id="76ce3-114">PowerShell 參數</span><span class="sxs-lookup"><span data-stu-id="76ce3-114">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="76ce3-115">說明</span><span class="sxs-lookup"><span data-stu-id="76ce3-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76ce3-116">名稱</span><span class="sxs-lookup"><span data-stu-id="76ce3-116">Name</span></span></p></td>
<td><p><span data-ttu-id="76ce3-117">Identity</span><span class="sxs-lookup"><span data-stu-id="76ce3-117">Identity</span></span></p></td>
<td><p><span data-ttu-id="76ce3-118">所建立的 CDR 配置設定的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="76ce3-118">Unique identifier for the CDR configuration settings being created.</span></span> <span data-ttu-id="76ce3-119">這些設定只能在網站範圍建立。</span><span class="sxs-lookup"><span data-stu-id="76ce3-119">These settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76ce3-120">啟用 CDRs 的監控</span><span class="sxs-lookup"><span data-stu-id="76ce3-120">Enable monitoring of CDRs</span></span></p></td>
<td><p><span data-ttu-id="76ce3-121">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="76ce3-121">EnableCDR</span></span></p></td>
<td><p><span data-ttu-id="76ce3-122">指出是否已啟用 CDR。</span><span class="sxs-lookup"><span data-stu-id="76ce3-122">Indicates whether or not CDR is enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76ce3-123">啟用清除 CDRs</span><span class="sxs-lookup"><span data-stu-id="76ce3-123">Enable purging of CDRs</span></span></p></td>
<td><p><span data-ttu-id="76ce3-124">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="76ce3-124">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="76ce3-125">指出 CDR 記錄是否會定期從 CDR 資料庫中刪除。</span><span class="sxs-lookup"><span data-stu-id="76ce3-125">Indicates whether or not CDR records will periodically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76ce3-126">保留 CDRs 的最大持續時間（天）</span><span class="sxs-lookup"><span data-stu-id="76ce3-126">Keep CDRs for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="76ce3-127">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="76ce3-127">KeepCallDetailForDays</span></span></p></td>
<td><p><span data-ttu-id="76ce3-128">表示 CDR 記錄將保留在 CDR 資料庫中的天數。</span><span class="sxs-lookup"><span data-stu-id="76ce3-128">Indicates the number of days that CDR records will be kept in the CDR database.</span></span> <span data-ttu-id="76ce3-129">任何超過指定天數的記錄都會自動刪除。</span><span class="sxs-lookup"><span data-stu-id="76ce3-129">Any records older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="76ce3-130">（請注意，清除功能只會在已啟用清除時才會發生。）</span><span class="sxs-lookup"><span data-stu-id="76ce3-130">(Note that purging will take only place if purging has been enabled.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76ce3-131">針對最大持續時間（天）保留錯誤報表資料</span><span class="sxs-lookup"><span data-stu-id="76ce3-131">Keep error report data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="76ce3-132">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="76ce3-132">KeepErrorReportForDays</span></span></p></td>
<td><p><span data-ttu-id="76ce3-133">表示保留 CDR 錯誤報表的天數。</span><span class="sxs-lookup"><span data-stu-id="76ce3-133">Indicates the number of days that CDR error reports are kept.</span></span> <span data-ttu-id="76ce3-134">任何超過指定天數的報告都會自動刪除。</span><span class="sxs-lookup"><span data-stu-id="76ce3-134">Any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="76ce3-135">CDR 錯誤報表是用戶端應用程式上傳的診斷報告。</span><span class="sxs-lookup"><span data-stu-id="76ce3-135">CDR error reports are diagnostic reports uploaded by client applications.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="76ce3-136">CsCdrConfiguration 和 CsCdrConfiguration Cmdlet 包括在 Lync Server [控制台] 中無法使用的其他選項。</span><span class="sxs-lookup"><span data-stu-id="76ce3-136">The New-CsCdrConfiguration and Set-CsCdrConfiguration cmdlets include additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="76ce3-137">如需詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">新的-CsCdrConfiguration</A>和<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">設定 CsCdrConfiguration</A>的協助主題。</span><span class="sxs-lookup"><span data-stu-id="76ce3-137">See the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> and the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</A> help topics for more information.</span></span>



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="76ce3-138">使用 Lync Server [控制台] 建立 CDR 配置設定</span><span class="sxs-lookup"><span data-stu-id="76ce3-138">To create CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="76ce3-139">在 Lync Server [控制台] 中，按一下 [**監視及**封存]。</span><span class="sxs-lookup"><span data-stu-id="76ce3-139">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="76ce3-140">在 [**通話詳細資料記錄**] 索引標籤上，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="76ce3-140">On the **Call Detail Recording** tab, click **New**.</span></span>

3.  <span data-ttu-id="76ce3-141">在 [**選取網站**] 對話方塊中，選取要建立新配置設定的網站。</span><span class="sxs-lookup"><span data-stu-id="76ce3-141">In the **Select a Site** dialog box, select the site where the new configuration settings are to be created.</span></span> <span data-ttu-id="76ce3-142">如果對話方塊是空白的，則表示您的所有網站都已指派給 CDR 配置設定的集合。</span><span class="sxs-lookup"><span data-stu-id="76ce3-142">If the dialog box is empty, that means all of your sites have already been assigned a collection of CDR configuration settings.</span></span> <span data-ttu-id="76ce3-143">每個網站僅限一個此類集合。</span><span class="sxs-lookup"><span data-stu-id="76ce3-143">Each site is limited to a single such collection.</span></span> <span data-ttu-id="76ce3-144">在這種情況下，您可以刪除並重新建立設定，或直接修改現有的設定。</span><span class="sxs-lookup"><span data-stu-id="76ce3-144">In that case you can either delete and then re-create the settings, or simply modify the existing settings.</span></span>

4.  <span data-ttu-id="76ce3-145">在 [**新增通話詳細資料錄製（CDR）設定**] 對話方塊中，選取所要的選項，然後按一下 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="76ce3-145">In the **New Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="76ce3-146">使用 Lync Server [控制台] 修改現有的 CDR 配置設定</span><span class="sxs-lookup"><span data-stu-id="76ce3-146">To modify existing CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="76ce3-147">在 Lync Server [控制台] 中，按一下 [**監視及**封存]。</span><span class="sxs-lookup"><span data-stu-id="76ce3-147">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="76ce3-148">按兩下要修改的設定集合，或選取該收藏，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="76ce3-148">Double-click the collection of settings to be modified, or select the collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="76ce3-149">請注意，您一次只能修改單一集合。</span><span class="sxs-lookup"><span data-stu-id="76ce3-149">Note that you can only modify a single collection at a time.</span></span> <span data-ttu-id="76ce3-150">若要對多個收藏進行相同的變更，請改用 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="76ce3-150">To make the same changes to multiple collections, use the Lync Server Management Shell instead.</span></span>

3.  <span data-ttu-id="76ce3-151">在 [**編輯通話詳細資料錄製（CDR）] 設定**對話方塊中，選取所要的選項，然後按一下 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="76ce3-151">In the **Edit Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="76ce3-152">使用 Windows PowerShell Cmdlet 建立 CDR 配置設定</span><span class="sxs-lookup"><span data-stu-id="76ce3-152">Creating CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="76ce3-153">您也可以使用 Windows PowerShell 和**CsCdrConfiguration** Cmdlet 來建立 CDR 配置設定。</span><span class="sxs-lookup"><span data-stu-id="76ce3-153">You can create CDR configuration settings can also be created by using Windows PowerShell and the **New-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="76ce3-154">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="76ce3-154">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="76ce3-155">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="76ce3-155">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="76ce3-156">若要建立新的 CDR 配置設定集合</span><span class="sxs-lookup"><span data-stu-id="76ce3-156">To create a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="76ce3-157">這個命令會建立套用至雷德蒙網站的 CDR 設定設定的新集合：</span><span class="sxs-lookup"><span data-stu-id="76ce3-157">This command creates a new collection of CDR configuration settings applied to the Redmond site:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="76ce3-158">若要建立停用通話詳細資料錄製的 CDR 配置設定集合</span><span class="sxs-lookup"><span data-stu-id="76ce3-158">To create a collection of CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="76ce3-159">因為在上述命令中沒有指定任何參數（強制身分識別參數以外），所以新的配置設定集合會將預設值用於其所有屬性。</span><span class="sxs-lookup"><span data-stu-id="76ce3-159">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> <span data-ttu-id="76ce3-160">若要建立使用不同屬性值的設定，只要包含適當的參數和參數值即可。</span><span class="sxs-lookup"><span data-stu-id="76ce3-160">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="76ce3-161">例如，若要建立通話詳細資料設定的集合，根據預設，允許停用通話詳細資料錄製使用如下所示的命令：</span><span class="sxs-lookup"><span data-stu-id="76ce3-161">For example, to create a collection of Call Detail configuration settings that, by default, allow disable Call Detail recording use a command like this:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="76ce3-162">建立新的 CDR 配置設定集合時，指定多個屬性值</span><span class="sxs-lookup"><span data-stu-id="76ce3-162">To specify multiple property values when creating a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="76ce3-163">您可以透過包含多個參數來修改多個屬性值。</span><span class="sxs-lookup"><span data-stu-id="76ce3-163">You can modify multiple property values by including multiple parameters.</span></span> <span data-ttu-id="76ce3-164">例如，這個命令會將新設定設定為將呼叫詳細資料記錄保持在30天，並將錯誤報表保留90天：</span><span class="sxs-lookup"><span data-stu-id="76ce3-164">For example, this command configures the new settings to keep Call Detail records for 30 days and error reports for 90 days:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

<span data-ttu-id="76ce3-165">如需詳細資訊，請參閱[新版-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="76ce3-165">For more information, see the help topic for the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

