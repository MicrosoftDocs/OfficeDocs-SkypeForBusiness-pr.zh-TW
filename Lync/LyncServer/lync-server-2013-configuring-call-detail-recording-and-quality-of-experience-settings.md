---
title: 設定詳細通話記錄及經驗品質設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring call detail recording and Quality of Experience settings
ms:assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204621(v=OCS.15)
ms:contentKeyID: 48183223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67c9759faad4ed96cdf65d8bd22c5778512933de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-call-detail-recording-and-quality-of-experience-settings-in-lync-server-2013"></a><span data-ttu-id="344af-102">在 Lync Server 2013 中設定通話詳細資料錄製和體驗品質設定</span><span class="sxs-lookup"><span data-stu-id="344af-102">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="344af-103">_**主題上次修改日期：** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="344af-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="344af-104">在您將監視存放區與前端池關聯之後，請設定監視存放區，然後安裝和設定 SQL Server Reporting Services 及監視報告，您可以管理呼叫詳細資料錄製（CDR）及體驗品質（QoE）使用 Lync Server 管理命令介面進行監視。</span><span class="sxs-lookup"><span data-stu-id="344af-104">After you have associated a monitoring store with a Front End pool, set up the monitoring store, and then installed and configured SQL Server Reporting Services and Monitoring Reports you can manage Call Detail Recording (CDR) and Quality of Experience (QoE) monitoring by using Lync Server Management Shell.</span></span> <span data-ttu-id="344af-105">Lync Server 管理命令介面 Cmdlet 可讓您針對特定網站或整個 Lync Server 部署啟用及停用 CDR 及/或 QoE 監視;如此一來，您就可以使用簡單的命令完成下列作業：</span><span class="sxs-lookup"><span data-stu-id="344af-105">Lync Server Management Shell cmdlets allow you to enable and disable CDR and/or QoE monitoring for a particular site or for your entire Lync Server deployment; that can be done with a command as simple as this:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $False

<span data-ttu-id="344af-106">當您安裝 Microsoft Lync Server 2013 時，您也會針對 CDR 和 QoE 安裝預先定義的全域配置設定集合。</span><span class="sxs-lookup"><span data-stu-id="344af-106">When you install Microsoft Lync Server 2013, you will also install a predefined collection of global configuration settings for both CDR and QoE.</span></span> <span data-ttu-id="344af-107">[通話詳細資料錄製] 使用的一些常用設定的預設值如下表所示：</span><span class="sxs-lookup"><span data-stu-id="344af-107">Default values for some of the more commonly-used settings used by Call Detail Recording are shown in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="344af-108">Property</span><span class="sxs-lookup"><span data-stu-id="344af-108">Property</span></span></th>
<th><span data-ttu-id="344af-109">描述</span><span class="sxs-lookup"><span data-stu-id="344af-109">Description</span></span></th>
<th><span data-ttu-id="344af-110">預設值</span><span class="sxs-lookup"><span data-stu-id="344af-110">Default Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="344af-111">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="344af-111">EnableCDR</span></span></p></td>
<td><p><span data-ttu-id="344af-112">指出是否已啟用 CDR。</span><span class="sxs-lookup"><span data-stu-id="344af-112">Indicates whether or not CDR is enabled.</span></span> <span data-ttu-id="344af-113">如果為 True，則會收集所有 CDR 記錄，並將其寫入監視資料庫。</span><span class="sxs-lookup"><span data-stu-id="344af-113">If True, all CDR records will be collected and written to the monitoring database.</span></span></p></td>
<td><p><span data-ttu-id="344af-114">滿足</span><span class="sxs-lookup"><span data-stu-id="344af-114">True</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="344af-115">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="344af-115">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="344af-116">指出 CDR 記錄是否會定期從資料庫中刪除。</span><span class="sxs-lookup"><span data-stu-id="344af-116">Indicates whether or not CDR records will periodically be deleted from the database.</span></span> <span data-ttu-id="344af-117">如果為 True，則在屬性 KeepCallDetailForDays （適用于 CDR 記錄）和 KeepErrorReportForDays （針對 CDR 錯誤）指定的時段之後，將會刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="344af-117">If True, records will be deleted after the time period specified by the properties KeepCallDetailForDays (for CDR records) and KeepErrorReportForDays (for CDR errors).</span></span> <span data-ttu-id="344af-118">如果是 False，則會無限期維護 CDR 記錄。</span><span class="sxs-lookup"><span data-stu-id="344af-118">If False, CDR records will be maintained indefinitely.</span></span></p></td>
<td><p><span data-ttu-id="344af-119">滿足</span><span class="sxs-lookup"><span data-stu-id="344af-119">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="344af-120">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="344af-120">KeepCallDetailForDays</span></span></p></td>
<td><p><span data-ttu-id="344af-121">指出 CDR 記錄將保留在資料庫中的天數;任何超過指定天數的記錄都會自動刪除。</span><span class="sxs-lookup"><span data-stu-id="344af-121">Indicates the number of days that CDR records will be kept in the database; any records older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="344af-122">不過，這只會在已啟用清除的情況下發生。</span><span class="sxs-lookup"><span data-stu-id="344af-122">However, this will occur only if purging has been enabled.</span></span></p>
<p><span data-ttu-id="344af-123">KeepCallDetailForDays 可以設定為1到2562天之間（大約7年）的任何整數值。</span><span class="sxs-lookup"><span data-stu-id="344af-123">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days (approximately 7 years).</span></span></p></td>
<td><p><span data-ttu-id="344af-124">60 天</span><span class="sxs-lookup"><span data-stu-id="344af-124">60 days</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="344af-125">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="344af-125">KeepErrorReportForDays</span></span></p></td>
<td><p><span data-ttu-id="344af-126">指出 CDR 錯誤報表的保留天數;任何超過指定天數的報告都會自動刪除。</span><span class="sxs-lookup"><span data-stu-id="344af-126">Indicates the number of days that CDR error reports are kept; any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="344af-127">CDR 錯誤報表是由用戶端應用程式（例如 Microsoft Lync 2013）上傳的診斷報告。</span><span class="sxs-lookup"><span data-stu-id="344af-127">CDR error reports are diagnostic reports uploaded by client applications such as Microsoft Lync 2013.</span></span></p>
<p><span data-ttu-id="344af-128">您可以將此屬性設定為1到2562天之間的任何整數值。</span><span class="sxs-lookup"><span data-stu-id="344af-128">You can set this property to any integer value between 1 and 2562 days.</span></span></p></td>
<td><p><span data-ttu-id="344af-129">60 天</span><span class="sxs-lookup"><span data-stu-id="344af-129">60 days</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="344af-130">同樣地，此表格會顯示所選 QoE 設定的預設值：</span><span class="sxs-lookup"><span data-stu-id="344af-130">Similarly, default values for selected QoE settings are shown in this table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="344af-131">Property</span><span class="sxs-lookup"><span data-stu-id="344af-131">Property</span></span></th>
<th><span data-ttu-id="344af-132">描述</span><span class="sxs-lookup"><span data-stu-id="344af-132">Description</span></span></th>
<th><span data-ttu-id="344af-133">預設值</span><span class="sxs-lookup"><span data-stu-id="344af-133">Default Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="344af-134">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="344af-134">EnableQoE</span></span></p></td>
<td><p><span data-ttu-id="344af-135">指出是否已啟用 QoE 監視。</span><span class="sxs-lookup"><span data-stu-id="344af-135">Indicates whether or not QoE monitoring is enabled.</span></span> <span data-ttu-id="344af-136">如果為 True，則會收集所有 QoE 記錄並寫入監視資料庫。</span><span class="sxs-lookup"><span data-stu-id="344af-136">If True, all QoE records will be collected and written to the monitoring database.</span></span></p></td>
<td><p><span data-ttu-id="344af-137">滿足</span><span class="sxs-lookup"><span data-stu-id="344af-137">True</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="344af-138">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="344af-138">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="344af-139">指出 QoE 記錄是否會定期從資料庫中刪除。</span><span class="sxs-lookup"><span data-stu-id="344af-139">Indicates whether or not QoE records will periodically be deleted from the database.</span></span> <span data-ttu-id="344af-140">如果為 True，則會在 KeepQoEDataForDays 屬性指定的時段之後刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="344af-140">If True, records will be deleted after the time period specified by the KeepQoEDataForDays property.</span></span> <span data-ttu-id="344af-141">如果是 False，QoE 記錄將會無限期維護。</span><span class="sxs-lookup"><span data-stu-id="344af-141">If False, QoE records will be maintained indefinitely.</span></span></p></td>
<td><p><span data-ttu-id="344af-142">滿足</span><span class="sxs-lookup"><span data-stu-id="344af-142">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="344af-143">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="344af-143">KeepQoEDataForDays</span></span></p></td>
<td><p><span data-ttu-id="344af-144">指出 QoE 記錄將保留在資料庫中的天數;任何超過指定天數的記錄都會自動刪除。</span><span class="sxs-lookup"><span data-stu-id="344af-144">Indicates the number of days that QoE records will be kept in the database; any records older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="344af-145">不過，這只會在已啟用清除的情況下發生。</span><span class="sxs-lookup"><span data-stu-id="344af-145">However, this will occur only if purging has been enabled.</span></span></p>
<p><span data-ttu-id="344af-146">KeepCallDetailForDays 可以設定為1到2562天之間的任何整數值。</span><span class="sxs-lookup"><span data-stu-id="344af-146">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days.</span></span></p></td>
<td><p><span data-ttu-id="344af-147">60 天</span><span class="sxs-lookup"><span data-stu-id="344af-147">60 days</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="344af-148">如果您需要修改這些全域設定，您可以使用 CsCdrConfiguration 和 CsQoEConfiguration Cmdlet 來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="344af-148">If you need to modify these global settings you can do so by using the Set-CsCdrConfiguration and the Set-CsQoEConfiguration cmdlets.</span></span> <span data-ttu-id="344af-149">例如，此命令（在 Lync Server 管理命令介面內執行）會停用全域範圍中的 CDR 監視;這是透過將 EnableCDR 屬性設定為 False （$False）來完成：</span><span class="sxs-lookup"><span data-stu-id="344af-149">For example, this command (run from within the Lync Server Management Shell) disables CDR monitoring at the global scope; that's done by setting the EnableCDR property to False ($False):</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $False

<span data-ttu-id="344af-150">請注意，停用監視並不會解除與 [前端] 池的關聯，也不會卸載或以其他方式影響後端監視資料庫。</span><span class="sxs-lookup"><span data-stu-id="344af-150">Note that disabling monitoring does not dissociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="344af-151">當您使用 Lync Server 管理命令介面來停用 CDR 或 QoE 監視時，您實際所做的全部動作就是暫時停止 Lync Server 收集及封存監視資料。</span><span class="sxs-lookup"><span data-stu-id="344af-151">When you use Lync Server Management Shell to disable either CDR or QoE monitoring all you really do is temporarily stop Lync Server from collecting and archiving monitoring data.</span></span> <span data-ttu-id="344af-152">如果您想要繼續，在這種情況下，您只需將 EnableCDR 屬性設回 True （$True），就可以開始收集及歸檔 CDR 資料：</span><span class="sxs-lookup"><span data-stu-id="344af-152">If you want to resume, in this case, the collection and archiving of CDR data, all you need to do is set the EnableCDR property back to True ($True):</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

<span data-ttu-id="344af-153">同樣地，這個命令會停用全域範圍的 QoE 記錄清除：</span><span class="sxs-lookup"><span data-stu-id="344af-153">Similarly, this command disables the purging of QoE records at the global scope:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnablePurging $False

<span data-ttu-id="344af-154">除了全域設定，還可以將 CDR 及 QoE 設定設定指派給網站範圍。</span><span class="sxs-lookup"><span data-stu-id="344af-154">In addition to the global settings, CDR and QoE configurations settings can be assigned to the site scope.</span></span> <span data-ttu-id="344af-155">這在監視時提供額外的管理靈活性;例如，管理員可以為雷德蒙的網站啟用 CDR 監視，但停用用於都柏林網站的 CDR 監視。</span><span class="sxs-lookup"><span data-stu-id="344af-155">This provides additional management flexibility when it comes to monitoring; for example, an administrator can enable CDR monitoring for the Redmond site but disable CDR monitoring for the Dublin site.</span></span> <span data-ttu-id="344af-156">若要在網站範圍中建立新的 CDR 配置設定，請使用類似以下的命令：</span><span class="sxs-lookup"><span data-stu-id="344af-156">To create new CDR configuration settings at the site scope, use a command similar to this:</span></span>

    New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

<span data-ttu-id="344af-157">請記住，在網站範圍設定的設定會優先于在全域範圍中設定的設定。</span><span class="sxs-lookup"><span data-stu-id="344af-157">Keep in mind that settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="344af-158">例如，假設在全域範圍中啟用 CDR 監視，但在網站範圍停用（針對雷德蒙的網站）。</span><span class="sxs-lookup"><span data-stu-id="344af-158">For example, suppose CDR monitoring is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="344af-159">如此一來，就不會針對雷德蒙者網站上的使用者封存通話詳細資料記錄資訊。</span><span class="sxs-lookup"><span data-stu-id="344af-159">That means that call detail recording information will not be archived for users in the Redmond site.</span></span> <span data-ttu-id="344af-160">不過，其他網站中的使用者（也就是由全域設定所管理的使用者，而不是雷德蒙網站設定）會將通話詳細記錄資訊存檔。</span><span class="sxs-lookup"><span data-stu-id="344af-160">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording information archived.</span></span>

<span data-ttu-id="344af-161">您可以使用如下的命令，在網站範圍建立新的 QoE 配置設定：</span><span class="sxs-lookup"><span data-stu-id="344af-161">New QoE configuration settings can be created at the site scope by using a command like this one:</span></span>

    New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15

<span data-ttu-id="344af-162">如需詳細資訊，請在 Lync Server 管理命令介面中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="344af-162">For more information, type the following commands from within the Lync Server Management Shell:</span></span>

    Get-Help New-CsCdrConfiguration | more
    Get-Help Set-CsCdrConfiguration | more
    Get-Help New-CsQoEConfiguration | more
    Get-Help Set-CsQoEConfiguration | more

</div>

<span> </span>

</div>

</div>

</div>

