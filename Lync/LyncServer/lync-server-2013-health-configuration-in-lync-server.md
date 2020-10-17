---
title: Lync Server 2013： Lync Server 中的健康情況設定
description: Lync Server 2013： Lync Server 中的 Health configuration。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 999a6d5401cb34382a4120f9255c91c846f72422
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552849"
---
# <a name="health-configuration-in-lync-server-2013"></a><span data-ttu-id="fbb23-103">Lync Server 2013 中的健康情況設定</span><span class="sxs-lookup"><span data-stu-id="fbb23-103">Health configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbb23-104">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="fbb23-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="fbb23-105">在不同的網站、Microsoft 知識庫文章和 Lync Server 資源工具組工具之間，在執行 Lync Server 時遇到問題的系統管理員，永遠不會從解決這些問題的方式開始。</span><span class="sxs-lookup"><span data-stu-id="fbb23-105">Between various websites, Microsoft Knowledge Base articles, and Lync Server Resource Kit tools, administrators who encounter problems when running Lync Server are never far from a way to solve those problems.</span></span>

<span data-ttu-id="fbb23-106">顯然，您無法保證 Lync Server 2013 的問題，因為 Lync Server 可能會受到許多專案（例如網路損毀和硬體失敗）的影響，產品本身無法控制。</span><span class="sxs-lookup"><span data-stu-id="fbb23-106">Obviously there is no way to guarantee that you will never encounter problems with Lync Server 2013 because Lync Server can be affected by many things—like network crashes and hardware failures—that the product itself cannot control.</span></span> <span data-ttu-id="fbb23-107">透過實施狀況監視，系統管理員可以在潛在問題變成實際問題之前識別潛在的問題。</span><span class="sxs-lookup"><span data-stu-id="fbb23-107">By implementing health monitoring, administrators can identify potential problems before they turn into actual problems.</span></span> <span data-ttu-id="fbb23-108">例如，系統管理員可以使用 Lync Server 監視來識別趨勢和 tendencies。</span><span class="sxs-lookup"><span data-stu-id="fbb23-108">For example, administrators can use Lync Server monitoring to identify trends and tendencies.</span></span> <span data-ttu-id="fbb23-109">例如，當音訊/視訊會議數目不斷增加時，可能會建議您在系統超載之前必須增加容量。</span><span class="sxs-lookup"><span data-stu-id="fbb23-109">For example, a steady increase in the number of audio/video conferences might suggest a need to add capacity before the system becomes overloaded.</span></span>

<span data-ttu-id="fbb23-110">以類似的方式，系統管理員可以使用 System Center Operations Manager 做為當指定的事件發生時發出即時警示，以及執行主動測試系統的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="fbb23-110">In a similar fashion, administrators can use System Center Operations Manager to do such things as issue real-time alerts when specified events occur, and to run synthetic transactions that proactively test the system.</span></span> <span data-ttu-id="fbb23-111">在 Lync Server 中使用綜合交易，以確認使用者能夠成功完成常見的工作，例如登入系統、交換立即訊息，或撥打位於公用交換電話網路 (PSTN) 的電話。</span><span class="sxs-lookup"><span data-stu-id="fbb23-111">Synthetic transactions are used in Lync Server to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="fbb23-112">例如，定期執行這些測試時，可能會提醒您登入 Lync Server 的使用者可能發生問題，並讓您有機會修正問題，您的支援小組會在您的支援小組充斥使用者的通話無法進行連線的情況下加以修正。</span><span class="sxs-lookup"><span data-stu-id="fbb23-112">For example, periodically running these tests can alert you to potential problems with users logging on to Lync Server, and give you a chance to correct the problem before your support team is flooded with calls from users unable to make a connection.</span></span> <span data-ttu-id="fbb23-113">透過使用 System Center Operations Manager 執行這些綜合交易，管理員可以定期監視其 Lync Server 的部署，使其持續每天24小時，而不需要回應可能發出的任何警示。</span><span class="sxs-lookup"><span data-stu-id="fbb23-113">By using System Center Operations Manager to run these synthetic transactions, administrators can routinely monitor their deployment of Lync Server continuously for 24 hours every day without having to do much of anything beyond responding to any alerts that might be issued.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fbb23-114">對於 Lync Server 2013，System Center Operations Manager 管理元件也可以偵測可能對 Lync Server 產生不良影響的「外部」問題。</span><span class="sxs-lookup"><span data-stu-id="fbb23-114">For Lync Server 2013, the Management Pack for System Center Operations Manager is also able to detect "external" issues that can adversely affect Lync Server.</span></span> <span data-ttu-id="fbb23-115">例如，當 Internet information Services (IIS) 離線、Lync Server 電腦上的系統資源低於指定的數量或 Lync Server 電腦發生硬體故障時，系統管理員便可獲得通知。</span><span class="sxs-lookup"><span data-stu-id="fbb23-115">For example, administrators can be notified if Internet Information Services (IIS) goes offline, system resources on a Lync Server computer fall below a specified amount, or a Lync Server computer experiences a hardware failure.</span></span>



</div>

<span data-ttu-id="fbb23-116">Lync Server 2013 中的健康情況設定是圍繞 System Center Operations Manager 和 Lync Server 管理元件的使用而建立。</span><span class="sxs-lookup"><span data-stu-id="fbb23-116">Health configuration in Lync Server 2013 is built around System Center Operations Manager and the use of Lync Server Management Packs.</span></span> <span data-ttu-id="fbb23-117">這些管理元件包含許多新的功能和增強功能，包括：</span><span class="sxs-lookup"><span data-stu-id="fbb23-117">These Management Packs include a number of new features and enhancements, including:</span></span>

  - <span data-ttu-id="fbb23-118">**任何位置的案例可用性。**</span><span class="sxs-lookup"><span data-stu-id="fbb23-118">**Scenario availability from any location.**</span></span> <span data-ttu-id="fbb23-119">Lync Server 2010 管理元件引進監控使用者案例可用性與綜合交易的概念。</span><span class="sxs-lookup"><span data-stu-id="fbb23-119">The Lync Server 2010 Management Pack introduced the concept of monitoring end user scenario availability with synthetic transactions.</span></span> <span data-ttu-id="fbb23-120">在 Lync Server 2013 中，這些代理程式會有更多的綜合交易，而且可以從企業內部的不同位置執行，從企業以外的遠端地理位置，依分支機搆裝置和 Lync Server 2010 部署，將覆蓋範圍新增至舊版 Edge 部署。</span><span class="sxs-lookup"><span data-stu-id="fbb23-120">In Lync Server 2013, these agents have more synthetic transactions and can be run from a variety of locations inside the enterprise, from remote geographic locations outside of the enterprise, against branch office appliances and against Lync Server 2010 deployments to add coverage to legacy Edge deployments.</span></span>

  - <span data-ttu-id="fbb23-121">**綜合交易記錄檔。**</span><span class="sxs-lookup"><span data-stu-id="fbb23-121">**Synthetic transaction logs.**</span></span> <span data-ttu-id="fbb23-122">當綜合交易失敗時，系統管理員可以存取 HTML 記錄檔，以協助判斷失敗的情形。</span><span class="sxs-lookup"><span data-stu-id="fbb23-122">When a synthetic transaction fails, administrators have access to HTML logs to help determine what failed.</span></span> <span data-ttu-id="fbb23-123">這包括瞭解哪些動作失敗、每個動作的延遲、執行測試所用的命令列，以及所發生的錯誤。</span><span class="sxs-lookup"><span data-stu-id="fbb23-123">This includes understanding which action failed, the latency of each action, the command-line used to run the test, and the error that was encountered.</span></span>

  - <span data-ttu-id="fbb23-124">**增加通話可靠性覆蓋範圍。**</span><span class="sxs-lookup"><span data-stu-id="fbb23-124">**Increased call reliability coverage.**</span></span> <span data-ttu-id="fbb23-125">Lync Server 2010 管理元件引入了「可靠性警示」，偵測影響使用者音訊撥號的嚴重連線問題。</span><span class="sxs-lookup"><span data-stu-id="fbb23-125">The Lync Server 2010 Management Pack introduced call reliability alerting to detect severe connectivity issues that affect the audio calls of end users.</span></span> <span data-ttu-id="fbb23-126">Lync Server 2013 管理元件新增對等立即訊息 (IM) 和其他基本會議功能的覆蓋率，以在減少噪音時最大化覆蓋範圍。</span><span class="sxs-lookup"><span data-stu-id="fbb23-126">The Lync Server 2013 Management Packs add coverage for peer-to-peer instant messaging (IM) and other basic conferencing features to maximize coverage while reducing noise.</span></span>

  - <span data-ttu-id="fbb23-127">**相關性監控。**</span><span class="sxs-lookup"><span data-stu-id="fbb23-127">**Dependency monitoring.**</span></span> <span data-ttu-id="fbb23-128">Lync Server 案例可能會因為各種外部因素而失敗，例如 IIS 離線、有限的 CPU 和記憶體資源和磁片問題。</span><span class="sxs-lookup"><span data-stu-id="fbb23-128">Lync Server scenarios can fail due to a variety of external factors such as IIS being offline, limited CPU and memory resources, and disk issues.</span></span> <span data-ttu-id="fbb23-129">新的管理元件會檢查數個重要的相依性，以確保系統管理員知道其影響。</span><span class="sxs-lookup"><span data-stu-id="fbb23-129">The new management packs check several critical dependencies to ensure administrators are aware of their impact.</span></span>

  - <span data-ttu-id="fbb23-130">**增強型報告。**</span><span class="sxs-lookup"><span data-stu-id="fbb23-130">**Enhanced reporting.**</span></span> <span data-ttu-id="fbb23-131">一組報告，可協助系統管理員評估案例可用性、規劃容量，以及查看哪些元件遇到最大的問題。</span><span class="sxs-lookup"><span data-stu-id="fbb23-131">A set of reports to help administrators estimate scenario availability, plan for capacity, and see which components are experiencing the most issues.</span></span>

<span data-ttu-id="fbb23-132">管理元件也包含各種功能，可協助偵測和診斷，對 Lync Server 部署的健康情況提供即時的可見度。</span><span class="sxs-lookup"><span data-stu-id="fbb23-132">The Management Packs also include a variety of features to help detect and diagnose provide real-time visibility into the health your Lync Server deployment.</span></span> <span data-ttu-id="fbb23-133">下表列出這些功能。</span><span class="sxs-lookup"><span data-stu-id="fbb23-133">These features are listed in the following table.</span></span>

### <a name="management-pack-features"></a><span data-ttu-id="fbb23-134">管理元件功能</span><span class="sxs-lookup"><span data-stu-id="fbb23-134">Management Pack Features</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fbb23-135">功能</span><span class="sxs-lookup"><span data-stu-id="fbb23-135">Feature</span></span></th>
<th><span data-ttu-id="fbb23-136">描述</span><span class="sxs-lookup"><span data-stu-id="fbb23-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fbb23-137">綜合交易</span><span class="sxs-lookup"><span data-stu-id="fbb23-137">Synthetic Transactions</span></span></p></td>
<td><p><span data-ttu-id="fbb23-138">可以從不同位置執行的 Windows PowerShell Cmdlet，以確保使用者可以立即使用登入、目前狀態、IM 和會議等使用者案例。</span><span class="sxs-lookup"><span data-stu-id="fbb23-138">Windows PowerShell cmdlets that can be run from various locations to ensure that end user scenarios such as sign-in, presence, IM, and conferencing are readily available to end users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbb23-139">通話可靠性警示</span><span class="sxs-lookup"><span data-stu-id="fbb23-139">Call Reliability Alerts</span></span></p></td>
<td><p><span data-ttu-id="fbb23-140"> (CDR) 中的詳細通話記錄的資料庫查詢。</span><span class="sxs-lookup"><span data-stu-id="fbb23-140">Database queries for Call Detail Records (CDR).</span></span> <span data-ttu-id="fbb23-141">前端伺服器會寫入這些記錄，反映使用者是否可以連線至來電或來電終止的原因。</span><span class="sxs-lookup"><span data-stu-id="fbb23-141">These records are written by Front End Servers to reflect whether end users were able to connect to a call or why a call was terminated.</span></span> <span data-ttu-id="fbb23-142">這些查詢會產生警示，指出當種類廣泛的使用者遇到對等通話或基本會議功能的連線問題時。</span><span class="sxs-lookup"><span data-stu-id="fbb23-142">These queries result in alerts that indicate when a wide range of end users are experiencing connectivity issues for peer-to-peer calls or basic conferencing functionality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbb23-143">媒體質量警示</span><span class="sxs-lookup"><span data-stu-id="fbb23-143">Media Quality Alerts</span></span></p></td>
<td><p><span data-ttu-id="fbb23-144">查看經驗品質 (QoE) 用戶端于每次通話結束時所發佈的報表。</span><span class="sxs-lookup"><span data-stu-id="fbb23-144">Database queries that look at Quality of Experience (QoE) reports published by clients at the end of each call.</span></span> <span data-ttu-id="fbb23-145">這些查詢會產生警示，以找出使用者在通話和會議期間可能會出現媒體質量不良的情況。</span><span class="sxs-lookup"><span data-stu-id="fbb23-145">These queries result in alerts that pinpoint scenarios where users are likely to be experiencing poor media quality during calls and conferences.</span></span> <span data-ttu-id="fbb23-146">資料是以重要計量（如資料包延遲和遺失）為基礎，其所知道的標準是直接參與通話品質。</span><span class="sxs-lookup"><span data-stu-id="fbb23-146">The data is built upon key metrics such as packet latency and loss, metrics that are known to directly contribute to call quality.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbb23-147">元件健康情況</span><span class="sxs-lookup"><span data-stu-id="fbb23-147">Component Health</span></span></p></td>
<td><p><span data-ttu-id="fbb23-148">個別的伺服器元件會使用事件記錄檔和效能計數器來引發警示。</span><span class="sxs-lookup"><span data-stu-id="fbb23-148">Individual server components raise alerts by using event logs and performance counters.</span></span> <span data-ttu-id="fbb23-149">這些警示指出可能會嚴重影響一或多個使用者案例的失敗條件。</span><span class="sxs-lookup"><span data-stu-id="fbb23-149">These alerts indicate failure conditions that can severely impact one or more end user scenarios.</span></span> <span data-ttu-id="fbb23-150">這些警示也可指出各種其他的失敗狀況，包括未執行的服務、高失敗率、高郵件延遲或連線問題。</span><span class="sxs-lookup"><span data-stu-id="fbb23-150">These alerts can also indicate a variety of other failure conditions, including services not running, high failure rates, high message latency, or connectivity issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbb23-151">依存健康情況</span><span class="sxs-lookup"><span data-stu-id="fbb23-151">Dependency Health</span></span></p></td>
<td><p><span data-ttu-id="fbb23-152">失敗可能是由各種外部原因所造成。</span><span class="sxs-lookup"><span data-stu-id="fbb23-152">Failures can occur for a variety of external reasons.</span></span> <span data-ttu-id="fbb23-153">管理元件現在會針對可能表示嚴重問題的一些重要外部相依性，監控及收集資料，包括 IIS 可用性、伺服器和程式的 CPU 和記憶體使用量，以及磁片計量。</span><span class="sxs-lookup"><span data-stu-id="fbb23-153">The management packs now monitor and collect data for some of the critical external dependencies that might indicate severe issues, including IIS availability, CPU and memory usage of servers and processes, and disk metrics.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fbb23-154">系統發出的警示分為三個一般類別：</span><span class="sxs-lookup"><span data-stu-id="fbb23-154">The alerts issued by the system have been classified into three general categories:</span></span>

  - <span data-ttu-id="fbb23-155">**高優先順序警示。**</span><span class="sxs-lookup"><span data-stu-id="fbb23-155">**High-priority Alerts.**</span></span> <span data-ttu-id="fbb23-156">這些警示表示的情況會導致大量使用者的服務停機。</span><span class="sxs-lookup"><span data-stu-id="fbb23-156">These alerts indicate conditions that will cause service outages for large groups of users.</span></span> <span data-ttu-id="fbb23-157">例如，由於 Lync Server 2013 具有內建的高可用性功能，所以單一機器上的元件失敗不是高優先順序的警示。</span><span class="sxs-lookup"><span data-stu-id="fbb23-157">For example, a component failure on a single machine is not a high-priority alert because Lync Server 2013 has built-in high availability features.</span></span> <span data-ttu-id="fbb23-158">相反地，高優先順序的提醒代表「在晚間喚醒系統管理員」足夠嚴重的問題。</span><span class="sxs-lookup"><span data-stu-id="fbb23-158">Instead, high-priority alerts represent problems serious enough “to wake up administrators at night.”</span></span> <span data-ttu-id="fbb23-159">綜合交易和離線服務偵測到中斷 (例如，音訊/視訊會議) 會限定為高優先順序警示。</span><span class="sxs-lookup"><span data-stu-id="fbb23-159">Outages detected by synthetic transactions and offline services (for example, audio/video conferencing) qualify as high-priority alerts.</span></span>

  - <span data-ttu-id="fbb23-160">**中優先順序警示。**</span><span class="sxs-lookup"><span data-stu-id="fbb23-160">**Medium-priority alerts.**.</span></span> <span data-ttu-id="fbb23-161">這些警示會指出會影響使用者子集的條件，或表示通話品質降級。</span><span class="sxs-lookup"><span data-stu-id="fbb23-161">These alerts indicate conditions that affect a subset of users or indicate call quality degradation.</span></span> <span data-ttu-id="fbb23-162">這包括元件失敗、通話中的延遲或通話中降級的音訊品質等問題。</span><span class="sxs-lookup"><span data-stu-id="fbb23-162">That includes problems such as component failures, latency in call establishment, or degraded audio quality in call.</span></span> <span data-ttu-id="fbb23-163">此類別中的警示是有狀態的，並指出目前問題的狀態。</span><span class="sxs-lookup"><span data-stu-id="fbb23-163">Alerts in this category are stateful and indicate the current status of the issue.</span></span> <span data-ttu-id="fbb23-164">例如，假設您的通話所建立的時間超過警示閾值。</span><span class="sxs-lookup"><span data-stu-id="fbb23-164">For example, suppose your call establishment times exceed the alert threshold.</span></span> <span data-ttu-id="fbb23-165">如果通話的時間傳回正常，系統中心 Operations Manager 中會自動解決這些警示。</span><span class="sxs-lookup"><span data-stu-id="fbb23-165">If call establishment times return to normal, these alerts will be auto-resolved in System Center Operations Manager.</span></span> <span data-ttu-id="fbb23-166">這些警示的預期是，系統管理員會在相同的工作日查看他們。</span><span class="sxs-lookup"><span data-stu-id="fbb23-166">The expectation for these alerts is that an administrator will look at them on the same business day.</span></span>

  - <span data-ttu-id="fbb23-167">**其他警示。**</span><span class="sxs-lookup"><span data-stu-id="fbb23-167">**Other alerts.**</span></span> <span data-ttu-id="fbb23-168">這些是元件中可能會影響特定使用者或使用者子集的警示。</span><span class="sxs-lookup"><span data-stu-id="fbb23-168">These are alerts from components that might affect a specific user or subset of users.</span></span> <span data-ttu-id="fbb23-169">例如，通訊錄服務可能無法剖析指定使用者的 Active Directory 專案。</span><span class="sxs-lookup"><span data-stu-id="fbb23-169">For example, perhaps the Address Book service could not parse the Active Directory entry of a given user.</span></span> <span data-ttu-id="fbb23-170">這些警示的預期是，當系統管理員有可用時間時，就會收到這些通知。</span><span class="sxs-lookup"><span data-stu-id="fbb23-170">The expectation for these alerts is that administrators will get to them when they have time available.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fbb23-171">本章節內容</span><span class="sxs-lookup"><span data-stu-id="fbb23-171">In This Section</span></span>

  - [<span data-ttu-id="fbb23-172">設定 Lync Server 2013 以與 System Center Operations Manager 搭配使用</span><span class="sxs-lookup"><span data-stu-id="fbb23-172">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [<span data-ttu-id="fbb23-173">在 Lync Server 2013 中使用綜合交易記錄的豐富記錄</span><span class="sxs-lookup"><span data-stu-id="fbb23-173">Using rich logging for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [<span data-ttu-id="fbb23-174">使用 Microsoft SQL Server 2008 R2 作為 Lync Server 2013 的 System Center Operations Manager 資料庫</span><span class="sxs-lookup"><span data-stu-id="fbb23-174">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

