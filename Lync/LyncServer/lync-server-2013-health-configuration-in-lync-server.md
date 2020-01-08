---
title: Lync Server 2013： Lync Server 中的健康配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a719a5e8695dbbd0705aa649d72a32a2bfdc7d38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="health-configuration-in-lync-server-2013"></a><span data-ttu-id="426c7-102">Lync Server 2013 中的健康配置</span><span class="sxs-lookup"><span data-stu-id="426c7-102">Health configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="426c7-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="426c7-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="426c7-104">在各種網站、Microsoft 知識庫文章和 Lync Server 資源套件工具之間，在執行 Lync Server 時遇到問題的管理員，絕對不會有解決這些問題的方式。</span><span class="sxs-lookup"><span data-stu-id="426c7-104">Between various websites, Microsoft Knowledge Base articles, and Lync Server Resource Kit tools, administrators who encounter problems when running Lync Server are never far from a way to solve those problems.</span></span>

<span data-ttu-id="426c7-105">顯然，無法保證 Lync Server 2013 不會遇到問題，因為 Lync Server 可能受到許多專案（例如網路損毀和硬體故障）影響，而產品本身無法控制。</span><span class="sxs-lookup"><span data-stu-id="426c7-105">Obviously there is no way to guarantee that you will never encounter problems with Lync Server 2013 because Lync Server can be affected by many things—like network crashes and hardware failures—that the product itself cannot control.</span></span> <span data-ttu-id="426c7-106">透過執行健康情況監視，系統管理員可以在轉換為實際問題之前，先找出潛在的問題。</span><span class="sxs-lookup"><span data-stu-id="426c7-106">By implementing health monitoring, administrators can identify potential problems before they turn into actual problems.</span></span> <span data-ttu-id="426c7-107">例如，管理員可以使用 Lync Server monitoring 來識別趨勢與 tendencies。</span><span class="sxs-lookup"><span data-stu-id="426c7-107">For example, administrators can use Lync Server monitoring to identify trends and tendencies.</span></span> <span data-ttu-id="426c7-108">例如，音訊/視訊會議數的穩定增加，可能會建議您在系統超載之前必須增加容量。</span><span class="sxs-lookup"><span data-stu-id="426c7-108">For example, a steady increase in the number of audio/video conferences might suggest a need to add capacity before the system becomes overloaded.</span></span>

<span data-ttu-id="426c7-109">在類似的方式中，管理員可以在指定的事件發生時，使用系統中心作業管理員來執行即時警報，以及執行預先測試系統的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="426c7-109">In a similar fashion, administrators can use System Center Operations Manager to do such things as issue real-time alerts when specified events occur, and to run synthetic transactions that proactively test the system.</span></span> <span data-ttu-id="426c7-110">在 Lync Server 中使用綜合交易，以確認使用者能夠成功完成一般工作，例如登入系統、交換立即訊息，或撥打電話給位於公用交換電話網絡（PSTN）的電話。</span><span class="sxs-lookup"><span data-stu-id="426c7-110">Synthetic transactions are used in Lync Server to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="426c7-111">例如，定期執行這些測試時，您可能會在登入 Lync Server 時提醒您可能會遇到的問題，並讓您有機會修正問題，才能讓支援小組遇到來自使用者無法連線的呼叫。</span><span class="sxs-lookup"><span data-stu-id="426c7-111">For example, periodically running these tests can alert you to potential problems with users logging on to Lync Server, and give you a chance to correct the problem before your support team is flooded with calls from users unable to make a connection.</span></span> <span data-ttu-id="426c7-112">透過使用 System Center Operations Manager 執行這些綜合交易，系統管理員可以定期監視 Lync Server 在每天24小時內的部署，而不需要執行任何其他動作，就不需要回應任何可能的警示會發出。</span><span class="sxs-lookup"><span data-stu-id="426c7-112">By using System Center Operations Manager to run these synthetic transactions, administrators can routinely monitor their deployment of Lync Server continuously for 24 hours every day without having to do much of anything beyond responding to any alerts that might be issued.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="426c7-113">針對 Lync Server 2013，System Center Operations Manager 的管理套件也能夠偵測到可能會對 Lync Server 造成負面影響的「外部」問題。</span><span class="sxs-lookup"><span data-stu-id="426c7-113">For Lync Server 2013, the Management Pack for System Center Operations Manager is also able to detect "external" issues that can adversely affect Lync Server.</span></span> <span data-ttu-id="426c7-114">例如，當網際網路資訊服務（IIS）離線、在 Lync 伺服器電腦上的系統資源低於指定的數量，或 Lync Server 電腦遇到硬體故障時，系統管理員就可以收到通知。</span><span class="sxs-lookup"><span data-stu-id="426c7-114">For example, administrators can be notified if Internet Information Services (IIS) goes offline, system resources on a Lync Server computer fall below a specified amount, or a Lync Server computer experiences a hardware failure.</span></span>



</div>

<span data-ttu-id="426c7-115">Lync Server 2013 中的健康設定是圍繞 System Center Operations Manager 和 Lync Server 管理套件的使用所建立。</span><span class="sxs-lookup"><span data-stu-id="426c7-115">Health configuration in Lync Server 2013 is built around System Center Operations Manager and the use of Lync Server Management Packs.</span></span> <span data-ttu-id="426c7-116">這些管理套件包含許多新功能和增強功能，包括：</span><span class="sxs-lookup"><span data-stu-id="426c7-116">These Management Packs include a number of new features and enhancements, including:</span></span>

  - <span data-ttu-id="426c7-117">**從任何位置進行案例的可用性。**</span><span class="sxs-lookup"><span data-stu-id="426c7-117">**Scenario availability from any location.**</span></span> <span data-ttu-id="426c7-118">Lync Server 2010 管理套件引進了利用綜合交易來監視使用者案例可用性的概念。</span><span class="sxs-lookup"><span data-stu-id="426c7-118">The Lync Server 2010 Management Pack introduced the concept of monitoring end user scenario availability with synthetic transactions.</span></span> <span data-ttu-id="426c7-119">在 Lync Server 2013 中，這些代理程式有更多綜合交易，而且可以從企業內部的不同位置執行，從企業外部的遠端地理位置，針對分支機搆裝置和 Lync Server 2010[部署] 可將覆蓋範圍新增到舊版 Edge 部署。</span><span class="sxs-lookup"><span data-stu-id="426c7-119">In Lync Server 2013, these agents have more synthetic transactions and can be run from a variety of locations inside the enterprise, from remote geographic locations outside of the enterprise, against branch office appliances and against Lync Server 2010 deployments to add coverage to legacy Edge deployments.</span></span>

  - <span data-ttu-id="426c7-120">**綜合交易記錄記錄。**</span><span class="sxs-lookup"><span data-stu-id="426c7-120">**Synthetic transaction logs.**</span></span> <span data-ttu-id="426c7-121">當綜合交易失敗時，系統管理員可以存取 HTML 記錄，以協助判斷失敗的原因。</span><span class="sxs-lookup"><span data-stu-id="426c7-121">When a synthetic transaction fails, administrators have access to HTML logs to help determine what failed.</span></span> <span data-ttu-id="426c7-122">這包括瞭解哪個動作失敗、每個動作的延遲、用於執行測試的命令列，以及所遇到的錯誤。</span><span class="sxs-lookup"><span data-stu-id="426c7-122">This includes understanding which action failed, the latency of each action, the command-line used to run the test, and the error that was encountered.</span></span>

  - <span data-ttu-id="426c7-123">**增加通話可靠性覆蓋範圍。**</span><span class="sxs-lookup"><span data-stu-id="426c7-123">**Increased call reliability coverage.**</span></span> <span data-ttu-id="426c7-124">Lync Server 2010 管理套件引入了呼叫可靠性觸發程式，以偵測對使用者的音訊撥號產生影響的嚴重連接問題。</span><span class="sxs-lookup"><span data-stu-id="426c7-124">The Lync Server 2010 Management Pack introduced call reliability alerting to detect severe connectivity issues that affect the audio calls of end users.</span></span> <span data-ttu-id="426c7-125">Lync Server 2013 管理套件新增對等立即訊息（IM）及其他基本會議功能的覆蓋範圍，同時降低噪音。</span><span class="sxs-lookup"><span data-stu-id="426c7-125">The Lync Server 2013 Management Packs add coverage for peer-to-peer instant messaging (IM) and other basic conferencing features to maximize coverage while reducing noise.</span></span>

  - <span data-ttu-id="426c7-126">**相依性監視。**</span><span class="sxs-lookup"><span data-stu-id="426c7-126">**Dependency monitoring.**</span></span> <span data-ttu-id="426c7-127">Lync Server 案例可能會因為各種外部因素（例如，IIS 離線、有限的 CPU 和記憶體資源，以及磁片問題）而失敗。</span><span class="sxs-lookup"><span data-stu-id="426c7-127">Lync Server scenarios can fail due to a variety of external factors such as IIS being offline, limited CPU and memory resources, and disk issues.</span></span> <span data-ttu-id="426c7-128">新的管理套件會檢查數個重要的相依性，以確保系統管理員知道其影響。</span><span class="sxs-lookup"><span data-stu-id="426c7-128">The new management packs check several critical dependencies to ensure administrators are aware of their impact.</span></span>

  - <span data-ttu-id="426c7-129">**增強的報表。**</span><span class="sxs-lookup"><span data-stu-id="426c7-129">**Enhanced reporting.**</span></span> <span data-ttu-id="426c7-130">一組報告，可協助系統管理員估計案例可用性、規劃容量，以及查看有哪些元件遇到最多問題。</span><span class="sxs-lookup"><span data-stu-id="426c7-130">A set of reports to help administrators estimate scenario availability, plan for capacity, and see which components are experiencing the most issues.</span></span>

<span data-ttu-id="426c7-131">管理套件也包含各種功能，可協助偵測及診斷程式在您的 Lync Server 部署中即時看到健康情況。</span><span class="sxs-lookup"><span data-stu-id="426c7-131">The Management Packs also include a variety of features to help detect and diagnose provide real-time visibility into the health your Lync Server deployment.</span></span> <span data-ttu-id="426c7-132">下表列出了這些功能。</span><span class="sxs-lookup"><span data-stu-id="426c7-132">These features are listed in the following table.</span></span>

### <a name="management-pack-features"></a><span data-ttu-id="426c7-133">管理套件功能</span><span class="sxs-lookup"><span data-stu-id="426c7-133">Management Pack Features</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="426c7-134">功能</span><span class="sxs-lookup"><span data-stu-id="426c7-134">Feature</span></span></th>
<th><span data-ttu-id="426c7-135">描述</span><span class="sxs-lookup"><span data-stu-id="426c7-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="426c7-136">綜合交易</span><span class="sxs-lookup"><span data-stu-id="426c7-136">Synthetic Transactions</span></span></p></td>
<td><p><span data-ttu-id="426c7-137">可從不同位置執行的 Windows PowerShell Cmdlet，以確保使用者可隨時使用登入、目前狀態、IM 及會議等使用者案例。</span><span class="sxs-lookup"><span data-stu-id="426c7-137">Windows PowerShell cmdlets that can be run from various locations to ensure that end user scenarios such as sign-in, presence, IM, and conferencing are readily available to end users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426c7-138">通話可靠性警報</span><span class="sxs-lookup"><span data-stu-id="426c7-138">Call Reliability Alerts</span></span></p></td>
<td><p><span data-ttu-id="426c7-139">[通話詳細資料記錄（CDR）] 的資料庫查詢。</span><span class="sxs-lookup"><span data-stu-id="426c7-139">Database queries for Call Detail Records (CDR).</span></span> <span data-ttu-id="426c7-140">這些記錄是由前端伺服器所撰寫，以反映最終使用者是否可以連線到通話，或為什麼來電終止。</span><span class="sxs-lookup"><span data-stu-id="426c7-140">These records are written by Front End Servers to reflect whether end users were able to connect to a call or why a call was terminated.</span></span> <span data-ttu-id="426c7-141">這些查詢會產生警示，指出大量使用者何時遇到對等通話或基本會議功能的連線問題。</span><span class="sxs-lookup"><span data-stu-id="426c7-141">These queries result in alerts that indicate when a wide range of end users are experiencing connectivity issues for peer-to-peer calls or basic conferencing functionality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426c7-142">媒體質量警示</span><span class="sxs-lookup"><span data-stu-id="426c7-142">Media Quality Alerts</span></span></p></td>
<td><p><span data-ttu-id="426c7-143">在每次通話結束時，查看用戶端發佈之經驗品質（QoE）報告的資料庫查詢。</span><span class="sxs-lookup"><span data-stu-id="426c7-143">Database queries that look at Quality of Experience (QoE) reports published by clients at the end of each call.</span></span> <span data-ttu-id="426c7-144">這些查詢會產生警示，指出使用者在通話和會議期間可能遇到媒體質量不佳的情況。</span><span class="sxs-lookup"><span data-stu-id="426c7-144">These queries result in alerts that pinpoint scenarios where users are likely to be experiencing poor media quality during calls and conferences.</span></span> <span data-ttu-id="426c7-145">此資料是根據重要的度量單位（例如資料包延遲與遺失）來建立，這些標準已知會直接參與通話品質。</span><span class="sxs-lookup"><span data-stu-id="426c7-145">The data is built upon key metrics such as packet latency and loss, metrics that are known to directly contribute to call quality.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426c7-146">元件健康情況</span><span class="sxs-lookup"><span data-stu-id="426c7-146">Component Health</span></span></p></td>
<td><p><span data-ttu-id="426c7-147">個別伺服器元件會使用事件記錄和效能計數器來產生警示。</span><span class="sxs-lookup"><span data-stu-id="426c7-147">Individual server components raise alerts by using event logs and performance counters.</span></span> <span data-ttu-id="426c7-148">這些警示代表可能會嚴重影響一或多個最終使用者案例的失敗情況。</span><span class="sxs-lookup"><span data-stu-id="426c7-148">These alerts indicate failure conditions that can severely impact one or more end user scenarios.</span></span> <span data-ttu-id="426c7-149">這些警示也可能會指出各種其他失敗的狀況，包括未執行的服務、高失敗率、高資訊延遲或連線問題。</span><span class="sxs-lookup"><span data-stu-id="426c7-149">These alerts can also indicate a variety of other failure conditions, including services not running, high failure rates, high message latency, or connectivity issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426c7-150">相依性狀況</span><span class="sxs-lookup"><span data-stu-id="426c7-150">Dependency Health</span></span></p></td>
<td><p><span data-ttu-id="426c7-151">失敗可能是由各種外部原因所導致。</span><span class="sxs-lookup"><span data-stu-id="426c7-151">Failures can occur for a variety of external reasons.</span></span> <span data-ttu-id="426c7-152">管理套件現在會針對一些可能表示嚴重問題的重要外部相依性監視及收集資料，包括 IIS 可用性、伺服器與程式的 CPU 和記憶體使用量，以及磁片規格。</span><span class="sxs-lookup"><span data-stu-id="426c7-152">The management packs now monitor and collect data for some of the critical external dependencies that might indicate severe issues, including IIS availability, CPU and memory usage of servers and processes, and disk metrics.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="426c7-153">系統所頒發的警示已分為三個一般類別：</span><span class="sxs-lookup"><span data-stu-id="426c7-153">The alerts issued by the system have been classified into three general categories:</span></span>

  - <span data-ttu-id="426c7-154">**高優先順序的警示。**</span><span class="sxs-lookup"><span data-stu-id="426c7-154">**High-priority Alerts.**</span></span> <span data-ttu-id="426c7-155">這些警示代表會導致大型使用者群組服務中斷的情況。</span><span class="sxs-lookup"><span data-stu-id="426c7-155">These alerts indicate conditions that will cause service outages for large groups of users.</span></span> <span data-ttu-id="426c7-156">例如，單一電腦上的元件失敗不是高優先順序的警示，因為 Lync Server 2013 具有內建的高可用性功能。</span><span class="sxs-lookup"><span data-stu-id="426c7-156">For example, a component failure on a single machine is not a high-priority alert because Lync Server 2013 has built-in high availability features.</span></span> <span data-ttu-id="426c7-157">相反地，高優先順序的警示代表嚴重不足，以喚醒在夜間喚醒系統管理員的問題。</span><span class="sxs-lookup"><span data-stu-id="426c7-157">Instead, high-priority alerts represent problems serious enough “to wake up administrators at night.”</span></span> <span data-ttu-id="426c7-158">綜合交易與離線服務（例如音訊/視訊會議）檢測到的中斷是資格為高優先順序的通知。</span><span class="sxs-lookup"><span data-stu-id="426c7-158">Outages detected by synthetic transactions and offline services (for example, audio/video conferencing) qualify as high-priority alerts.</span></span>

  - <span data-ttu-id="426c7-159">**中等優先順序的通知。**</span><span class="sxs-lookup"><span data-stu-id="426c7-159">**Medium-priority alerts.**.</span></span> <span data-ttu-id="426c7-160">這些警示代表會影響使用者子集的條件，或指示通話品質下降。</span><span class="sxs-lookup"><span data-stu-id="426c7-160">These alerts indicate conditions that affect a subset of users or indicate call quality degradation.</span></span> <span data-ttu-id="426c7-161">包括元件失敗、通話中的延遲，或通話中的音訊品質下降等問題。</span><span class="sxs-lookup"><span data-stu-id="426c7-161">That includes problems such as component failures, latency in call establishment, or degraded audio quality in call.</span></span> <span data-ttu-id="426c7-162">此類別中的警示是全狀態的，並指出問題的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="426c7-162">Alerts in this category are stateful and indicate the current status of the issue.</span></span> <span data-ttu-id="426c7-163">例如，假設您的通話建立時間超過警示閾值。</span><span class="sxs-lookup"><span data-stu-id="426c7-163">For example, suppose your call establishment times exceed the alert threshold.</span></span> <span data-ttu-id="426c7-164">如果通話建立時間傳回正常，系統中心作業管理員將會自動解析這些警示。</span><span class="sxs-lookup"><span data-stu-id="426c7-164">If call establishment times return to normal, these alerts will be auto-resolved in System Center Operations Manager.</span></span> <span data-ttu-id="426c7-165">這些警報的預期是，系統管理員會在同一工作日中查看他們。</span><span class="sxs-lookup"><span data-stu-id="426c7-165">The expectation for these alerts is that an administrator will look at them on the same business day.</span></span>

  - <span data-ttu-id="426c7-166">**其他通知。**</span><span class="sxs-lookup"><span data-stu-id="426c7-166">**Other alerts.**</span></span> <span data-ttu-id="426c7-167">這些是可能會影響特定使用者或使用者子集之元件的警示。</span><span class="sxs-lookup"><span data-stu-id="426c7-167">These are alerts from components that might affect a specific user or subset of users.</span></span> <span data-ttu-id="426c7-168">例如，通訊錄服務可能無法分析指定使用者的 Active Directory 專案。</span><span class="sxs-lookup"><span data-stu-id="426c7-168">For example, perhaps the Address Book service could not parse the Active Directory entry of a given user.</span></span> <span data-ttu-id="426c7-169">這些警示的預期是，當使用者有可用時間時，就會收到這些通知。</span><span class="sxs-lookup"><span data-stu-id="426c7-169">The expectation for these alerts is that administrators will get to them when they have time available.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="426c7-170">本節內容</span><span class="sxs-lookup"><span data-stu-id="426c7-170">In This Section</span></span>

  - [<span data-ttu-id="426c7-171">設定 Lync Server 2013 以搭配 System Center Operations Manager 使用</span><span class="sxs-lookup"><span data-stu-id="426c7-171">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - <span data-ttu-id="426c7-172">[在 Lync Server 2013 中使用 [綜合交易] 的豐富記錄](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)</span><span class="sxs-lookup"><span data-stu-id="426c7-172">[Using rich logging for synthetic transactions in Lync Server 2013](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)</span></span>

  - [<span data-ttu-id="426c7-173">使用 Microsoft SQL Server 2008 R2 作為 Lync Server 2013 的 System Center Operations Manager 資料庫</span><span class="sxs-lookup"><span data-stu-id="426c7-173">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

