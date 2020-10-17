---
title: Lync Server 2013：建立經驗品質配置設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Quality of Experience configuration settings
ms:assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521006(v=OCS.15)
ms:contentKeyID: 48184357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a94b7183be9927267796d3e2adaed12b3b71eaf6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501630"
---
# <a name="create-quality-of-experience-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="142ed-102">在 Lync Server 2013 中建立經驗品質設定設定</span><span class="sxs-lookup"><span data-stu-id="142ed-102">Create Quality of Experience configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="142ed-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="142ed-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="142ed-p101">「經驗品質 (QoE)」計量在追蹤組織中進行之音訊和視訊通話的品質，包括遺失的網路封包數量、背景雜訊和「抖動」(封包延遲差異) 等項目的數量。這些計量會儲存在與其他資料 (例如詳細通話記錄) 不同的資料庫中，讓您可獨立於其他資料記錄來啟用和停用 QoE。</span><span class="sxs-lookup"><span data-stu-id="142ed-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>

<span data-ttu-id="142ed-106">當您安裝 Microsoft Lync Server 2013 時，會為您建立單一、全域的 QoE 配置設定集合。</span><span class="sxs-lookup"><span data-stu-id="142ed-106">When you install Microsoft Lync Server 2013, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="142ed-107">系統管理員也可以選擇建立網站範圍的自訂設定。</span><span class="sxs-lookup"><span data-stu-id="142ed-107">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="142ed-108">只要使用這些網站範圍的設定，其優先順序就高於全域設定。</span><span class="sxs-lookup"><span data-stu-id="142ed-108">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="142ed-109">例如，如果為 Redmond 網站建立網站範圍的設定，則會使用這些設定 (而非全域設定) 來管理 Redmond 的 QoE。</span><span class="sxs-lookup"><span data-stu-id="142ed-109">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>

<span data-ttu-id="142ed-110">您可以使用 Lync Server 控制台或 [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) Cmdlet 來建立 QoE 的設定設定。</span><span class="sxs-lookup"><span data-stu-id="142ed-110">QoE configuration settings can be created by using either Lync Server Control Panel or the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet.</span></span> <span data-ttu-id="142ed-111">如果您使用 Lync Server 控制台建立新的設定，您可以使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="142ed-111">If you are using Lync Server Control Panel to create new settings the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="142ed-112">UI 設定</span><span class="sxs-lookup"><span data-stu-id="142ed-112">UI Setting</span></span></th>
<th><span data-ttu-id="142ed-113">PowerShell 參數</span><span class="sxs-lookup"><span data-stu-id="142ed-113">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="142ed-114">描述</span><span class="sxs-lookup"><span data-stu-id="142ed-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="142ed-115">名稱</span><span class="sxs-lookup"><span data-stu-id="142ed-115">Name</span></span></p></td>
<td><p><span data-ttu-id="142ed-116">身分識別</span><span class="sxs-lookup"><span data-stu-id="142ed-116">Identity</span></span></p></td>
<td><p><span data-ttu-id="142ed-p104">要建立之設定的唯一識別碼。QoE 組態設定僅可在網站範圍內建立。</span><span class="sxs-lookup"><span data-stu-id="142ed-p104">Unique identifier for the settings to be created. QoE configuration settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="142ed-119">啟用 QoE 資料的監控</span><span class="sxs-lookup"><span data-stu-id="142ed-119">Enable monitoring of QoE data</span></span></p></td>
<td><p><span data-ttu-id="142ed-120">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="142ed-120">EnableQoE</span></span></p></td>
<td><p><span data-ttu-id="142ed-121">指定是否將收集 QoE 記錄並儲存至監控資料庫。</span><span class="sxs-lookup"><span data-stu-id="142ed-121">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="142ed-122">啟用 QoE 資料的清除</span><span class="sxs-lookup"><span data-stu-id="142ed-122">Enable purging of QoE data</span></span></p></td>
<td><p><span data-ttu-id="142ed-123">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="142ed-123">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="142ed-124">指定是否在 <strong>[將 QoE 資料保留最大持續期間 (天)]</strong> 屬性中定義的期間經過之後，將清除記錄。</span><span class="sxs-lookup"><span data-stu-id="142ed-124">Specifies whether records will be purged after the duration defined in the <strong>Keep QoE data for a maximum duration (days)</strong> property has elapsed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="142ed-125">將 QoE 資料保留最大持續期間 (天)</span><span class="sxs-lookup"><span data-stu-id="142ed-125">Keep QoE data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="142ed-126">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="142ed-126">KeepQoEDataForDays</span></span></p></td>
<td><p><span data-ttu-id="142ed-p105">QoE 資料從資料庫清除之前將會儲存的天數。如果停用清除，將會忽略此值。</span><span class="sxs-lookup"><span data-stu-id="142ed-p105">Number of days QoE data will be stored before being purged from the database. This value is ignored if purging is disabled.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="142ed-129">New-CsQoEConfiguration Cmdlet 包含 Lync Server 控制台中無法使用的其他選項。</span><span class="sxs-lookup"><span data-stu-id="142ed-129">The New-CsQoEConfiguration cmdlet includes additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="142ed-130">如需詳細資訊，請參閱 CsQoEConfiguration 的「 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">新增-</A> 說明主題。</span><span class="sxs-lookup"><span data-stu-id="142ed-130">For more information, see the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</A> help topic.</span></span>



</div>

<div>

## <a name="to-create-qoe-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="142ed-131">使用 Lync Server 控制台建立 QoE 配置設定</span><span class="sxs-lookup"><span data-stu-id="142ed-131">To create QoE configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="142ed-132">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="142ed-132">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="142ed-133">如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="142ed-133">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="142ed-134">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="142ed-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="142ed-135">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="142ed-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="142ed-136">在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[經驗品質資料]**。</span><span class="sxs-lookup"><span data-stu-id="142ed-136">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="142ed-137">在 **[經驗品質資料]** 頁面上，按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="142ed-137">On the **Quality of Experience Data** page, click **New**.</span></span>

5.  <span data-ttu-id="142ed-138">在 **[選取站台]** 中，按一下要套用原則的網站，並按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="142ed-138">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>

6.  <span data-ttu-id="142ed-139">在 **[新的經驗品質設定]** 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="142ed-139">In **New Quality of Experience Setting**, do the following:</span></span>
    
      - <span data-ttu-id="142ed-140">選取 **[啟用經驗品質 (QoE) 資料的監控]** 開啟監控功能。</span><span class="sxs-lookup"><span data-stu-id="142ed-140">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
      - <span data-ttu-id="142ed-141">選取 **[啟用經驗品質 (QoE) 資料的清除]** 開啟清除功能。</span><span class="sxs-lookup"><span data-stu-id="142ed-141">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
      - <span data-ttu-id="142ed-142">在 **[將 QoE 資料保留最大持續期間 (天)]** 中，選取應該保留 QoE 記錄的最大天數。</span><span class="sxs-lookup"><span data-stu-id="142ed-142">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>

7.  <span data-ttu-id="142ed-143">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="142ed-143">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="142ed-144">使用 Windows PowerShell Cmdlet 建立 QoE 設定設定</span><span class="sxs-lookup"><span data-stu-id="142ed-144">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="142ed-145">您可以使用 Windows PowerShell 和 New-CsQoEConfiguration Cmdlet 來建立 QoE 設定設定。</span><span class="sxs-lookup"><span data-stu-id="142ed-145">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="142ed-146">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="142ed-146">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="142ed-147">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="142ed-147">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="142ed-148">建立新的 QoE 組態設定集合</span><span class="sxs-lookup"><span data-stu-id="142ed-148">To create a new collection of QoE configuration settings</span></span>

  - <span data-ttu-id="142ed-149">下列命令會建立要套用至 Redmond 網站的新 QoE 組態設定集合：</span><span class="sxs-lookup"><span data-stu-id="142ed-149">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="142ed-150">建立新的 QoE 組態設定集合並停用 QoE 監控</span><span class="sxs-lookup"><span data-stu-id="142ed-150">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

  - <span data-ttu-id="142ed-p110">因為上述命令未指定參數 (除了必要的 Identity 參數)，新的組態設定集合會將預設值用於其所有屬性。若要使用不同的屬性值來建立設定，只要包含適當的參數及參數值即可。例如，若要建立預設為允許停用經驗品質記錄之 QoE 組態設定的集合，請使用如下的命令：</span><span class="sxs-lookup"><span data-stu-id="142ed-p110">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="142ed-154">建立新的 QoE 組態設定集合時指定多個屬性值</span><span class="sxs-lookup"><span data-stu-id="142ed-154">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

  - <span data-ttu-id="142ed-p111">您可藉由包含多個參數來指定多個參數值。例如，下列命令會將新設定架構為將 QoE 資料保留 30 天，並在上午 3:00 清除舊資料：</span><span class="sxs-lookup"><span data-stu-id="142ed-p111">You can multiple property values by including multiple parameters. For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

</div>

<span data-ttu-id="142ed-157">如需詳細資訊，請參閱 [CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="142ed-157">For more information, see the help topic for the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

