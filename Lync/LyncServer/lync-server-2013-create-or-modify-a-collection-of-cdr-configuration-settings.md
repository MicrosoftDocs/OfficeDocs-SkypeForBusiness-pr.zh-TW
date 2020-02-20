---
title: Lync Server 2013： 建立或修改 CDR 組態設定集合
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
ms.openlocfilehash: 6ddb442a2b919650706329b4acaf21311b096b4a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="d17e3-102">建立或修改的 Lync Server 2013 中的 CDR 組態設定集合</span><span class="sxs-lookup"><span data-stu-id="d17e3-102">Create or modify a collection of CDR configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d17e3-103">_**上次修改主題：** 2013年-02-23_</span><span class="sxs-lookup"><span data-stu-id="d17e3-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d17e3-104">詳細通話記錄 (CDR) 可讓您追蹤使用情況的對等立即訊息工作階段，Voice over Internet Protocol (VoIP) 通話，等和會議會呼叫。</span><span class="sxs-lookup"><span data-stu-id="d17e3-104">Call detail recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls.</span></span> <span data-ttu-id="d17e3-105">這個使用狀況資料包含有關通話者雙方身分、通話時間以及通話時間長度的資訊。</span><span class="sxs-lookup"><span data-stu-id="d17e3-105">This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="d17e3-106">當您安裝 Microsoft Lync Server 2013 單一時，為您建立的 CDR 組態設定全域集合。</span><span class="sxs-lookup"><span data-stu-id="d17e3-106">When you install Microsoft Lync Server 2013 a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="d17e3-107">系統管理員也可以選擇建立網站範圍的自訂設定。</span><span class="sxs-lookup"><span data-stu-id="d17e3-107">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="d17e3-108">只要使用這些網站範圍的設定，其優先順序就高於全域設定。</span><span class="sxs-lookup"><span data-stu-id="d17e3-108">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="d17e3-109">例如，如果您建立 Redmond 網站的網站範圍設定然後那些設定 （而不是通用設定]） 將會用來管理在 Redmond 的 CDR。</span><span class="sxs-lookup"><span data-stu-id="d17e3-109">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage CDR in Redmond.</span></span>

<span data-ttu-id="d17e3-110">您可以使用 [Lync Server Control Panel] 或 [ [New-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet 建立 CDR 組態設定。</span><span class="sxs-lookup"><span data-stu-id="d17e3-110">You can create CDR configuration settings by using either Lync Server Control Panel or the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span> <span data-ttu-id="d17e3-111">您可以使用 Lync Server Control Panel 或[Set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet 來修改現有的設定。</span><span class="sxs-lookup"><span data-stu-id="d17e3-111">You can use Lync Server Control Panel or the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet to modify existing settings.</span></span> <span data-ttu-id="d17e3-112">如果您用來建立或修改設定 Lync Server Control Panel，會是您可以使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="d17e3-112">If you are using Lync Server Control Panel to create or modify settings, the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d17e3-113">UI 設定</span><span class="sxs-lookup"><span data-stu-id="d17e3-113">UI Setting</span></span></th>
<th><span data-ttu-id="d17e3-114">PowerShell 參數</span><span class="sxs-lookup"><span data-stu-id="d17e3-114">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="d17e3-115">描述</span><span class="sxs-lookup"><span data-stu-id="d17e3-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d17e3-116">名稱</span><span class="sxs-lookup"><span data-stu-id="d17e3-116">Name</span></span></p></td>
<td><p><span data-ttu-id="d17e3-117">身分識別</span><span class="sxs-lookup"><span data-stu-id="d17e3-117">Identity</span></span></p></td>
<td><p><span data-ttu-id="d17e3-118">要建立之 CDR 組態設定的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="d17e3-118">Unique identifier for the CDR configuration settings being created.</span></span> <span data-ttu-id="d17e3-119">只能在網站範圍建立這些設定。</span><span class="sxs-lookup"><span data-stu-id="d17e3-119">These settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d17e3-120">啟用監視 Cdr</span><span class="sxs-lookup"><span data-stu-id="d17e3-120">Enable monitoring of CDRs</span></span></p></td>
<td><p><span data-ttu-id="d17e3-121">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="d17e3-121">EnableCDR</span></span></p></td>
<td><p><span data-ttu-id="d17e3-122">表示是否啟用 CDR。</span><span class="sxs-lookup"><span data-stu-id="d17e3-122">Indicates whether or not CDR is enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d17e3-123">啟用 Cdr 的清除</span><span class="sxs-lookup"><span data-stu-id="d17e3-123">Enable purging of CDRs</span></span></p></td>
<td><p><span data-ttu-id="d17e3-124">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="d17e3-124">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="d17e3-125">會指出會定期從 CDR 資料庫刪除 CDR 記錄。</span><span class="sxs-lookup"><span data-stu-id="d17e3-125">Indicates whether or not CDR records will periodically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d17e3-126">將 Cdr 保留最大持續期限 （天）</span><span class="sxs-lookup"><span data-stu-id="d17e3-126">Keep CDRs for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="d17e3-127">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="d17e3-127">KeepCallDetailForDays</span></span></p></td>
<td><p><span data-ttu-id="d17e3-128">會指出的 CDR 記錄仍會保留 CDR 資料庫中的天數。</span><span class="sxs-lookup"><span data-stu-id="d17e3-128">Indicates the number of days that CDR records will be kept in the CDR database.</span></span> <span data-ttu-id="d17e3-129">將會自動刪除任何記錄早於指定天數。</span><span class="sxs-lookup"><span data-stu-id="d17e3-129">Any records older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="d17e3-130">（請注意，清除不會發生只有是否清除已啟用）。</span><span class="sxs-lookup"><span data-stu-id="d17e3-130">(Note that purging will take only place if purging has been enabled.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d17e3-131">將錯誤報告資料保留最大持續期限 （天）</span><span class="sxs-lookup"><span data-stu-id="d17e3-131">Keep error report data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="d17e3-132">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="d17e3-132">KeepErrorReportForDays</span></span></p></td>
<td><p><span data-ttu-id="d17e3-133">會指出的 CDR 錯誤報告所保留的天數。</span><span class="sxs-lookup"><span data-stu-id="d17e3-133">Indicates the number of days that CDR error reports are kept.</span></span> <span data-ttu-id="d17e3-134">將會自動刪除早於指定天數任何報告。</span><span class="sxs-lookup"><span data-stu-id="d17e3-134">Any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="d17e3-135">CDR 錯誤報告是由用戶端應用程式上傳診斷報告。</span><span class="sxs-lookup"><span data-stu-id="d17e3-135">CDR error reports are diagnostic reports uploaded by client applications.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="d17e3-136">New-cscdrconfiguration 和 Set-cscdrconfiguration cmdlet 包含 Lync Server 控制台不提供的額外選項。</span><span class="sxs-lookup"><span data-stu-id="d17e3-136">The New-CsCdrConfiguration and Set-CsCdrConfiguration cmdlets include additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="d17e3-137">請參閱<A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-cscdrconfiguration</A>和<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-cscdrconfiguration</A>說明主題中的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="d17e3-137">See the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> and the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</A> help topics for more information.</span></span>



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="d17e3-138">若要使用 Lync Server 控制台建立 CDR 組態設定</span><span class="sxs-lookup"><span data-stu-id="d17e3-138">To create CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d17e3-139">Lync Server 控制台] 中按一下 [**監控和封存**]。</span><span class="sxs-lookup"><span data-stu-id="d17e3-139">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="d17e3-140">在 [**詳細通話記錄**] 索引標籤中，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="d17e3-140">On the **Call Detail Recording** tab, click **New**.</span></span>

3.  <span data-ttu-id="d17e3-141">在 [**選取網站**] 對話方塊中，選取要建立新的組態設定的所在的網站。</span><span class="sxs-lookup"><span data-stu-id="d17e3-141">In the **Select a Site** dialog box, select the site where the new configuration settings are to be created.</span></span> <span data-ttu-id="d17e3-142">如果 [對話方塊] 方塊是空的這表示所有網站已指定的 CDR 組態設定集合。</span><span class="sxs-lookup"><span data-stu-id="d17e3-142">If the dialog box is empty, that means all of your sites have already been assigned a collection of CDR configuration settings.</span></span> <span data-ttu-id="d17e3-143">每個網站受限於單一這類集合。</span><span class="sxs-lookup"><span data-stu-id="d17e3-143">Each site is limited to a single such collection.</span></span> <span data-ttu-id="d17e3-144">在此情況下您可以刪除，並是然後重新建立與設定，或只是修改現有的設定。</span><span class="sxs-lookup"><span data-stu-id="d17e3-144">In that case you can either delete and then re-create the settings, or simply modify the existing settings.</span></span>

4.  <span data-ttu-id="d17e3-145">在 [**新詳細通話記錄 (CDR) 設定**] 對話方塊中，進行想要的選擇，然後按一下 [**認可]**。</span><span class="sxs-lookup"><span data-stu-id="d17e3-145">In the **New Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="d17e3-146">若要使用 Lync Server 控制台修改現有的 CDR 組態設定</span><span class="sxs-lookup"><span data-stu-id="d17e3-146">To modify existing CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d17e3-147">Lync Server 控制台] 中按一下 [**監控和封存**]。</span><span class="sxs-lookup"><span data-stu-id="d17e3-147">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="d17e3-148">連按兩下 [設定以進行修改，或選取集合，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**的集合。</span><span class="sxs-lookup"><span data-stu-id="d17e3-148">Double-click the collection of settings to be modified, or select the collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="d17e3-149">請注意，您只能修改一次的單一集合。</span><span class="sxs-lookup"><span data-stu-id="d17e3-149">Note that you can only modify a single collection at a time.</span></span> <span data-ttu-id="d17e3-150">若要讓多個集合相同的變更，請改為使用 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="d17e3-150">To make the same changes to multiple collections, use the Lync Server Management Shell instead.</span></span>

3.  <span data-ttu-id="d17e3-151">在 [**編輯詳細通話記錄 (CDR) 設定**] 對話方塊中，進行想要的選擇，然後按一下 [**認可]**。</span><span class="sxs-lookup"><span data-stu-id="d17e3-151">In the **Edit Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d17e3-152">使用 Windows PowerShell Cmdlet 建立 CDR 組態設定</span><span class="sxs-lookup"><span data-stu-id="d17e3-152">Creating CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d17e3-153">您可以建立 CDR 組態設定也可以建立使用 Windows PowerShell 和**New-cscdrconfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d17e3-153">You can create CDR configuration settings can also be created by using Windows PowerShell and the **New-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="d17e3-154">從 Lync Server 2013 管理命令介面或 Windows PowerShell 的遠端工作階段，您可以執行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d17e3-154">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d17e3-155">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 部落格文章 「 快速開始:: 管理 Microsoft Lync Server 2010 使用遠端 PowerShell 」 在[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="d17e3-155">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="d17e3-156">若要建立新的 CDR 組態設定集合</span><span class="sxs-lookup"><span data-stu-id="d17e3-156">To create a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="d17e3-157">此命令會建立新的 CDR 組態設定套用至 Redmond 網站集合：</span><span class="sxs-lookup"><span data-stu-id="d17e3-157">This command creates a new collection of CDR configuration settings applied to the Redmond site:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="d17e3-158">若要建立一群 CDR 組態設定，停用詳細通話記錄</span><span class="sxs-lookup"><span data-stu-id="d17e3-158">To create a collection of CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="d17e3-159">因為上述命令未指定參數 (除了必要的 Identity 參數)，新的組態設定集合會將預設值用於其所有屬性。</span><span class="sxs-lookup"><span data-stu-id="d17e3-159">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> <span data-ttu-id="d17e3-160">若要使用不同的屬性值來建立設定，只要包含適當的參數及參數值即可。</span><span class="sxs-lookup"><span data-stu-id="d17e3-160">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="d17e3-161">例如，若要建立之呼叫的詳細組態的集合，根據預設，允許設定停用詳細通話記錄使用這類命令：</span><span class="sxs-lookup"><span data-stu-id="d17e3-161">For example, to create a collection of Call Detail configuration settings that, by default, allow disable Call Detail recording use a command like this:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="d17e3-162">若要建立新的 CDR 組態設定集合時指定多個屬性值</span><span class="sxs-lookup"><span data-stu-id="d17e3-162">To specify multiple property values when creating a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="d17e3-163">您可以修改多個屬性值包括多個參數。</span><span class="sxs-lookup"><span data-stu-id="d17e3-163">You can modify multiple property values by including multiple parameters.</span></span> <span data-ttu-id="d17e3-164">例如，此命令會設定要保留 30 天和錯誤報告的詳細通話記錄 90 天的新設定：</span><span class="sxs-lookup"><span data-stu-id="d17e3-164">For example, this command configures the new settings to keep Call Detail records for 30 days and error reports for 90 days:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

<span data-ttu-id="d17e3-165">如需詳細資訊，請參閱[New-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="d17e3-165">For more information, see the help topic for the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

