---
title: 設定詳細通話記錄及經驗品質設定
description: 設定詳細通話記錄及經驗品質設定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring call detail recording and Quality of Experience settings
ms:assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204621(v=OCS.15)
ms:contentKeyID: 48183223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be0238701f561e6694786faec7fc914dcc9cda40
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567169"
---
# <a name="configuring-call-detail-recording-and-quality-of-experience-settings-in-lync-server-2013"></a><span data-ttu-id="4364b-103">在 Lync Server 2013 中設定詳細通話記錄及經驗品質設定</span><span class="sxs-lookup"><span data-stu-id="4364b-103">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4364b-104">_**主題上次修改日期：** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="4364b-104">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="4364b-105">在您將監視存放區與前端集區相關聯之後，請先設定監視儲存體，然後安裝及設定 SQL Server Reporting Services 與監視報告，以使用 Lync Server 管理命令介面來管理詳細通話記錄 (CDR) 和經驗品質 (QoE) 監視。</span><span class="sxs-lookup"><span data-stu-id="4364b-105">After you have associated a monitoring store with a Front End pool, set up the monitoring store, and then installed and configured SQL Server Reporting Services and Monitoring Reports you can manage Call Detail Recording (CDR) and Quality of Experience (QoE) monitoring by using Lync Server Management Shell.</span></span> <span data-ttu-id="4364b-106">Lync Server 管理命令介面 Cmdlet 可讓您啟用及停用特定網站或整個 Lync Server 部署的 CDR 和/或 QoE 監視;您可以使用下列方式做為簡單的命令：</span><span class="sxs-lookup"><span data-stu-id="4364b-106">Lync Server Management Shell cmdlets allow you to enable and disable CDR and/or QoE monitoring for a particular site or for your entire Lync Server deployment; that can be done with a command as simple as this:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $False

<span data-ttu-id="4364b-107">當您安裝 Microsoft Lync Server 2013 時，也會為 CDR 和 QoE 同時安裝全域設定設定的預先定義集合。</span><span class="sxs-lookup"><span data-stu-id="4364b-107">When you install Microsoft Lync Server 2013, you will also install a predefined collection of global configuration settings for both CDR and QoE.</span></span> <span data-ttu-id="4364b-108">下表顯示詳細通話記錄較常用的一些設定的預設值：</span><span class="sxs-lookup"><span data-stu-id="4364b-108">Default values for some of the more commonly-used settings used by Call Detail Recording are shown in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4364b-109">屬性	</span><span class="sxs-lookup"><span data-stu-id="4364b-109">Property</span></span></th>
<th><span data-ttu-id="4364b-110">描述</span><span class="sxs-lookup"><span data-stu-id="4364b-110">Description</span></span></th>
<th><span data-ttu-id="4364b-111">預設值</span><span class="sxs-lookup"><span data-stu-id="4364b-111">Default Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4364b-112">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="4364b-112">EnableCDR</span></span></p></td>
<td><p><span data-ttu-id="4364b-p103">表示是否啟用 CDR。若為 True，則會收集所有 CDR 記錄並寫入監控資料庫。</span><span class="sxs-lookup"><span data-stu-id="4364b-p103">Indicates whether or not CDR is enabled. If True, all CDR records will be collected and written to the monitoring database.</span></span></p></td>
<td><p><span data-ttu-id="4364b-115">是</span><span class="sxs-lookup"><span data-stu-id="4364b-115">True</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4364b-116">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="4364b-116">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="4364b-p104">表示是否要從資料庫定期刪除 CDR 記錄。若為 True，則會在過了 KeepCallDetailForDays (適用於 CDR 記錄) 和 KeepErrorReportForDays (適用於 CDR 錯誤) 屬性指定的期間之後刪除記錄。若為 False，則會無限期保留 CDR 記錄。</span><span class="sxs-lookup"><span data-stu-id="4364b-p104">Indicates whether or not CDR records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the properties KeepCallDetailForDays (for CDR records) and KeepErrorReportForDays (for CDR errors). If False, CDR records will be maintained indefinitely.</span></span></p></td>
<td><p><span data-ttu-id="4364b-120">是</span><span class="sxs-lookup"><span data-stu-id="4364b-120">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4364b-121">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="4364b-121">KeepCallDetailForDays</span></span></p></td>
<td><p><span data-ttu-id="4364b-p105">表示在資料庫保留 CDR 記錄的天數；任何超過指定天數的記錄都將自動刪除。但是，只有在啟用清除功能時，才會發生此情況。</span><span class="sxs-lookup"><span data-stu-id="4364b-p105">Indicates the number of days that CDR records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span></p>
<p><span data-ttu-id="4364b-124">您可以將 KeepCallDetailForDays 設為 1 到 2562 天 (大約 7 年) 之間的任何整數值。</span><span class="sxs-lookup"><span data-stu-id="4364b-124">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days (approximately 7 years).</span></span></p></td>
<td><p><span data-ttu-id="4364b-125">60 天</span><span class="sxs-lookup"><span data-stu-id="4364b-125">60 days</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4364b-126">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="4364b-126">KeepErrorReportForDays</span></span></p></td>
<td><p><span data-ttu-id="4364b-127">表示保留 CDR 錯誤報告的天數；任何超過指定天數的報告都將自動刪除。</span><span class="sxs-lookup"><span data-stu-id="4364b-127">Indicates the number of days that CDR error reports are kept; any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="4364b-128">CDR 錯誤報表是由用戶端應用程式（例如 Microsoft Lync 2013）上傳的診斷報告。</span><span class="sxs-lookup"><span data-stu-id="4364b-128">CDR error reports are diagnostic reports uploaded by client applications such as Microsoft Lync 2013.</span></span></p>
<p><span data-ttu-id="4364b-129">您可以將此屬性設為 1 到 2562 天之間的任何整數值。</span><span class="sxs-lookup"><span data-stu-id="4364b-129">You can set this property to any integer value between 1 and 2562 days.</span></span></p></td>
<td><p><span data-ttu-id="4364b-130">60 天</span><span class="sxs-lookup"><span data-stu-id="4364b-130">60 days</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4364b-131">同樣地，下表顯示所選 QoE 設定的預設值：</span><span class="sxs-lookup"><span data-stu-id="4364b-131">Similarly, default values for selected QoE settings are shown in this table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4364b-132">屬性	</span><span class="sxs-lookup"><span data-stu-id="4364b-132">Property</span></span></th>
<th><span data-ttu-id="4364b-133">描述</span><span class="sxs-lookup"><span data-stu-id="4364b-133">Description</span></span></th>
<th><span data-ttu-id="4364b-134">預設值</span><span class="sxs-lookup"><span data-stu-id="4364b-134">Default Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4364b-135">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="4364b-135">EnableQoE</span></span></p></td>
<td><p><span data-ttu-id="4364b-p107">表示是否啟用 QoE 監控。若為 True，則會收集所有 QoE 記錄並寫入監控資料庫。</span><span class="sxs-lookup"><span data-stu-id="4364b-p107">Indicates whether or not QoE monitoring is enabled. If True, all QoE records will be collected and written to the monitoring database.</span></span></p></td>
<td><p><span data-ttu-id="4364b-138">是</span><span class="sxs-lookup"><span data-stu-id="4364b-138">True</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4364b-139">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="4364b-139">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="4364b-p108">表示是否要從資料庫定期刪除 QoE 記錄。若為 True，則會在過了 KeepQoEDataForDays 屬性指定的期間之後刪除記錄。若為 False，則會無限期保留 QoE 記錄。</span><span class="sxs-lookup"><span data-stu-id="4364b-p108">Indicates whether or not QoE records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the KeepQoEDataForDays property. If False, QoE records will be maintained indefinitely.</span></span></p></td>
<td><p><span data-ttu-id="4364b-143">是</span><span class="sxs-lookup"><span data-stu-id="4364b-143">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4364b-144">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="4364b-144">KeepQoEDataForDays</span></span></p></td>
<td><p><span data-ttu-id="4364b-p109">表示在資料庫保留 QoE 記錄的天數；任何超過指定天數的記錄都將自動刪除。但是，只有在啟用清除功能時，才會發生此情況。</span><span class="sxs-lookup"><span data-stu-id="4364b-p109">Indicates the number of days that QoE records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span></p>
<p><span data-ttu-id="4364b-147">您可以將 KeepCallDetailForDays 設為 1 到 2562 天之間的任何整數值。</span><span class="sxs-lookup"><span data-stu-id="4364b-147">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days.</span></span></p></td>
<td><p><span data-ttu-id="4364b-148">60 天</span><span class="sxs-lookup"><span data-stu-id="4364b-148">60 days</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4364b-p110">如果您需要修改這些全域設定，可以使用 Set-CsCdrConfiguration 和 Set-CsQoEConfiguration Cmdlet 執行這項操作。例如，從 Lync Server 管理命令介面執行此命令可在全域範圍停用 CDR 監控；作法是將 EnableCDR 屬性設為 False ($False)：</span><span class="sxs-lookup"><span data-stu-id="4364b-p110">If you need to modify these global settings you can do so by using the Set-CsCdrConfiguration and the Set-CsQoEConfiguration cmdlets. For example, this command (run from within the Lync Server Management Shell) disables CDR monitoring at the global scope; that's done by setting the EnableCDR property to False ($False):</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $False

<span data-ttu-id="4364b-151">請注意，停用監控並不會解除監控儲存區與前端集區的關聯，也不會解除安裝或影響後端監控資料庫。</span><span class="sxs-lookup"><span data-stu-id="4364b-151">Note that disabling monitoring does not dissociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="4364b-152">當您使用 Lync Server 管理命令介面停用 CDR 或 QoE 監視時，您實際執行的工作會暫時停止 Lync Server 收集和封存監控資料。</span><span class="sxs-lookup"><span data-stu-id="4364b-152">When you use Lync Server Management Shell to disable either CDR or QoE monitoring all you really do is temporarily stop Lync Server from collecting and archiving monitoring data.</span></span> <span data-ttu-id="4364b-153">在此情況下，如果您想繼續收集及封存 CDR 資料，只需要將 EnableCDR 屬性設回 True ($True) 即可：</span><span class="sxs-lookup"><span data-stu-id="4364b-153">If you want to resume, in this case, the collection and archiving of CDR data, all you need to do is set the EnableCDR property back to True ($True):</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

<span data-ttu-id="4364b-154">同樣地，此命令會在全域範圍停止清除 QoE 記錄：</span><span class="sxs-lookup"><span data-stu-id="4364b-154">Similarly, this command disables the purging of QoE records at the global scope:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnablePurging $False

<span data-ttu-id="4364b-p112">除了全域設定之外，也可以對網站範圍指派 CDR 和 QoE 組態設定。這會提供監控作業額外的管理彈性；例如，系統管理員可以啟用 Redmond 網站的 CDR 監控，但停用 Dublin 網站的 CDR 監控。若要在網站範圍建立新的 CDR 組態設定，請使用類似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="4364b-p112">In addition to the global settings, CDR and QoE configurations settings can be assigned to the site scope. This provides additional management flexibility when it comes to monitoring; for example, an administrator can enable CDR monitoring for the Redmond site but disable CDR monitoring for the Dublin site. To create new CDR configuration settings at the site scope, use a command similar to this:</span></span>

    New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

<span data-ttu-id="4364b-p113">請注意，在網站範圍進行的設定優先順序高於在全域範圍進行的設定。例如，假設在全域範圍啟用 CDR 監控，但在網站範圍 (Redmond 網站) 停用 CDR 監控。這表示不會封存 Redmond 網站使用者的詳細通話記錄資訊，但是會封存其他網站使用者 (亦即全域設定 (而非 Redmond 網站設定) 所管理的使用者) 的詳細通話記錄資訊。</span><span class="sxs-lookup"><span data-stu-id="4364b-p113">Keep in mind that settings configured at the site scope take precedence over settings configured at the global scope. For example, suppose CDR monitoring is enabled at the global scope, but disabled at the site scope (for the Redmond site). That means that call detail recording information will not be archived for users in the Redmond site. However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording information archived.</span></span>

<span data-ttu-id="4364b-162">您可以使用類似如下的命令，在網站範圍建立新的 QoE 組態設定：</span><span class="sxs-lookup"><span data-stu-id="4364b-162">New QoE configuration settings can be created at the site scope by using a command like this one:</span></span>

    New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15

<span data-ttu-id="4364b-163">如需詳細資訊，請在 Lync Server 管理命令介面中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="4364b-163">For more information, type the following commands from within the Lync Server Management Shell:</span></span>

    Get-Help New-CsCdrConfiguration | more
    Get-Help Set-CsCdrConfiguration | more
    Get-Help New-CsQoEConfiguration | more
    Get-Help Set-CsQoEConfiguration | more

</div>

<span> </span>

</div>

</div>

</div>

