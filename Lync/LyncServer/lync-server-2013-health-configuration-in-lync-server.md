---
title: 在 Lync Server 中的 Lync Server 2013： 健康情況設定
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
ms.openlocfilehash: ee193ba28b10e8f209513d5bd6c8b58ae8c4fff9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135450"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="health-configuration-in-lync-server-2013"></a><span data-ttu-id="1b893-102">Lync Server 2013 中的健康情況設定</span><span class="sxs-lookup"><span data-stu-id="1b893-102">Health configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b893-103">_**主題上次修改日期：** 2012年-10-22_</span><span class="sxs-lookup"><span data-stu-id="1b893-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="1b893-104">各種網站、 Microsoft 知識庫文章和 Lync Server Resource Kit 工具，之間執行 Lync Server 時遇到問題的系統管理員都可以解決這些問題的方式。</span><span class="sxs-lookup"><span data-stu-id="1b893-104">Between various websites, Microsoft Knowledge Base articles, and Lync Server Resource Kit tools, administrators who encounter problems when running Lync Server are never far from a way to solve those problems.</span></span>

<span data-ttu-id="1b893-105">明顯沒有方法來確保您會永遠不會遇到問題的 Lync Server 2013 由於 Lync 伺服器可能受到許多事項 — 像是網路損毀及硬體故障 — 產品本身無法控制的。</span><span class="sxs-lookup"><span data-stu-id="1b893-105">Obviously there is no way to guarantee that you will never encounter problems with Lync Server 2013 because Lync Server can be affected by many things—like network crashes and hardware failures—that the product itself cannot control.</span></span> <span data-ttu-id="1b893-106">藉由實作狀況監視，系統管理員可以識別潛在的問題之前他們開啟成實際的問題。</span><span class="sxs-lookup"><span data-stu-id="1b893-106">By implementing health monitoring, administrators can identify potential problems before they turn into actual problems.</span></span> <span data-ttu-id="1b893-107">例如，系統管理員可以使用監視來找出趨勢和喜好傾向有關的 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="1b893-107">For example, administrators can use Lync Server monitoring to identify trends and tendencies.</span></span> <span data-ttu-id="1b893-108">例如，音訊/視訊會議數目穩定增加可能建議需要增加產能，系統會變成超載之前。</span><span class="sxs-lookup"><span data-stu-id="1b893-108">For example, a steady increase in the number of audio/video conferences might suggest a need to add capacity before the system becomes overloaded.</span></span>

<span data-ttu-id="1b893-109">在類似的方式，系統管理員可以使用 System Center Operations Manager，以指定的事件發生時，請勿為此問題： 即時提醒等項目並執行主動測試系統的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="1b893-109">In a similar fashion, administrators can use System Center Operations Manager to do such things as issue real-time alerts when specified events occur, and to run synthetic transactions that proactively test the system.</span></span> <span data-ttu-id="1b893-110">綜合交易，可用在 Lync 伺服器中，驗證使用者能夠成功地完成一般作業，例如登入系統、 交換立即訊息，或透過電話呼叫位於公用交換的電話網路 (PSTN)。</span><span class="sxs-lookup"><span data-stu-id="1b893-110">Synthetic transactions are used in Lync Server to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="1b893-111">例如，定期執行這些測試可以潛在的問題與使用者登入 Lync Server 時提醒您，讓您有機會更正問題，才能支援小組大量湧入使用者無法進行連線的來電。</span><span class="sxs-lookup"><span data-stu-id="1b893-111">For example, periodically running these tests can alert you to potential problems with users logging on to Lync Server, and give you a chance to correct the problem before your support team is flooded with calls from users unable to make a connection.</span></span> <span data-ttu-id="1b893-112">使用 System Center Operations Manager 執行下列綜合交易，系統管理員可以定期監視持續的每一天 24 小時的 Lync Server 部署而不用執行大部分的任何項目超過回應任何可能的警示發出。</span><span class="sxs-lookup"><span data-stu-id="1b893-112">By using System Center Operations Manager to run these synthetic transactions, administrators can routinely monitor their deployment of Lync Server continuously for 24 hours every day without having to do much of anything beyond responding to any alerts that might be issued.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1b893-113">Lync Server 2013 中，也是能夠偵測 「 外部 」 的問題，可能會影響 Lync Server 的 System Center Operations Manager 管理組件。</span><span class="sxs-lookup"><span data-stu-id="1b893-113">For Lync Server 2013, the Management Pack for System Center Operations Manager is also able to detect "external" issues that can adversely affect Lync Server.</span></span> <span data-ttu-id="1b893-114">例如，如果網際網路資訊服務 (IIS) 離線，Lync Server 電腦上的系統資源低於指定的數量，或 Lync Server 電腦發生硬體失敗，系統管理員就可以收到通知。</span><span class="sxs-lookup"><span data-stu-id="1b893-114">For example, administrators can be notified if Internet Information Services (IIS) goes offline, system resources on a Lync Server computer fall below a specified amount, or a Lync Server computer experiences a hardware failure.</span></span>



</div>

<span data-ttu-id="1b893-115">健康情況設定 Lync Server 2013 中的內建繞 System Center Operations Manager 和 Lync Server 管理組件的使用。</span><span class="sxs-lookup"><span data-stu-id="1b893-115">Health configuration in Lync Server 2013 is built around System Center Operations Manager and the use of Lync Server Management Packs.</span></span> <span data-ttu-id="1b893-116">這些管理組件包含許多新功能和增強功能，包括：</span><span class="sxs-lookup"><span data-stu-id="1b893-116">These Management Packs include a number of new features and enhancements, including:</span></span>

  - <span data-ttu-id="1b893-117">**從任何位置的案例可用性。**</span><span class="sxs-lookup"><span data-stu-id="1b893-117">**Scenario availability from any location.**</span></span> <span data-ttu-id="1b893-118">Lync Server 2010 管理組件導監視使用者案例可用性與綜合交易。</span><span class="sxs-lookup"><span data-stu-id="1b893-118">The Lync Server 2010 Management Pack introduced the concept of monitoring end user scenario availability with synthetic transactions.</span></span> <span data-ttu-id="1b893-119">在 Lync Server 2013 中，這些代理程式有更多的綜合交易，且可以執行各式各樣的企業內的位置，從遠端的地理位置，外部 branch office appliance，但針對 Lync Server 2010 企業版若要將涵蓋範圍新增至舊版 Edge 部署的部署。</span><span class="sxs-lookup"><span data-stu-id="1b893-119">In Lync Server 2013, these agents have more synthetic transactions and can be run from a variety of locations inside the enterprise, from remote geographic locations outside of the enterprise, against branch office appliances and against Lync Server 2010 deployments to add coverage to legacy Edge deployments.</span></span>

  - <span data-ttu-id="1b893-120">**綜合交易記錄檔。**</span><span class="sxs-lookup"><span data-stu-id="1b893-120">**Synthetic transaction logs.**</span></span> <span data-ttu-id="1b893-121">當綜合交易失敗時，系統管理員具有 HTML 記錄檔，以協助判斷失敗項目的存取權。</span><span class="sxs-lookup"><span data-stu-id="1b893-121">When a synthetic transaction fails, administrators have access to HTML logs to help determine what failed.</span></span> <span data-ttu-id="1b893-122">這包括了解哪些動作失敗，每個動作的延遲，命令列用來執行測試，並遇到錯誤。</span><span class="sxs-lookup"><span data-stu-id="1b893-122">This includes understanding which action failed, the latency of each action, the command-line used to run the test, and the error that was encountered.</span></span>

  - <span data-ttu-id="1b893-123">**增加的通話可靠性涵蓋範圍。**</span><span class="sxs-lookup"><span data-stu-id="1b893-123">**Increased call reliability coverage.**</span></span> <span data-ttu-id="1b893-124">Lync Server 2010 管理組件引進了通話可靠性警示來偵測會影響使用者的音訊通話的嚴重的連線問題。</span><span class="sxs-lookup"><span data-stu-id="1b893-124">The Lync Server 2010 Management Pack introduced call reliability alerting to detect severe connectivity issues that affect the audio calls of end users.</span></span> <span data-ttu-id="1b893-125">Lync Server 2013 管理組件新增對等立即訊息 (IM) 和其他基本會議功能，以最大化涵蓋範圍，同時減少雜訊的涵蓋範圍。</span><span class="sxs-lookup"><span data-stu-id="1b893-125">The Lync Server 2013 Management Packs add coverage for peer-to-peer instant messaging (IM) and other basic conferencing features to maximize coverage while reducing noise.</span></span>

  - <span data-ttu-id="1b893-126">**監視相依性。**</span><span class="sxs-lookup"><span data-stu-id="1b893-126">**Dependency monitoring.**</span></span> <span data-ttu-id="1b893-127">例如，IIS 正在離線，有限的 CPU 和記憶體資源、 磁碟問題，可能會因各種外部因素而失敗 Lync 伺服器的案例。</span><span class="sxs-lookup"><span data-stu-id="1b893-127">Lync Server scenarios can fail due to a variety of external factors such as IIS being offline, limited CPU and memory resources, and disk issues.</span></span> <span data-ttu-id="1b893-128">新的管理組件會檢查以確保系統管理員會知道其影響幾個重要的相依性。</span><span class="sxs-lookup"><span data-stu-id="1b893-128">The new management packs check several critical dependencies to ensure administrators are aware of their impact.</span></span>

  - <span data-ttu-id="1b893-129">**增強型報告。**</span><span class="sxs-lookup"><span data-stu-id="1b893-129">**Enhanced reporting.**</span></span> <span data-ttu-id="1b893-130">一組可協助系統管理員估計案例可用性報告的容量規劃，並查看哪些元件急需大部分的問題。</span><span class="sxs-lookup"><span data-stu-id="1b893-130">A set of reports to help administrators estimate scenario availability, plan for capacity, and see which components are experiencing the most issues.</span></span>

<span data-ttu-id="1b893-131">管理組件也包含各種不同的功能，協助您偵測及診斷提供即時的可見性健全狀況 Lync Server 部署。</span><span class="sxs-lookup"><span data-stu-id="1b893-131">The Management Packs also include a variety of features to help detect and diagnose provide real-time visibility into the health your Lync Server deployment.</span></span> <span data-ttu-id="1b893-132">下表列出這些功能。</span><span class="sxs-lookup"><span data-stu-id="1b893-132">These features are listed in the following table.</span></span>

### <a name="management-pack-features"></a><span data-ttu-id="1b893-133">管理組件功能</span><span class="sxs-lookup"><span data-stu-id="1b893-133">Management Pack Features</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b893-134">功能</span><span class="sxs-lookup"><span data-stu-id="1b893-134">Feature</span></span></th>
<th><span data-ttu-id="1b893-135">描述</span><span class="sxs-lookup"><span data-stu-id="1b893-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b893-136">綜合交易</span><span class="sxs-lookup"><span data-stu-id="1b893-136">Synthetic Transactions</span></span></p></td>
<td><p><span data-ttu-id="1b893-137">可以從不同的位置，以確定使用者案例，例如登入、 目前狀態、 IM 及會議會立即供使用者執行的 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1b893-137">Windows PowerShell cmdlets that can be run from various locations to ensure that end user scenarios such as sign-in, presence, IM, and conferencing are readily available to end users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b893-138">通話可靠性通知</span><span class="sxs-lookup"><span data-stu-id="1b893-138">Call Reliability Alerts</span></span></p></td>
<td><p><span data-ttu-id="1b893-139">資料庫查詢的詳細通話記錄 (CDR)。</span><span class="sxs-lookup"><span data-stu-id="1b893-139">Database queries for Call Detail Records (CDR).</span></span> <span data-ttu-id="1b893-140">這些記錄是由前端伺服器以反映使用者是否已能夠連線至通話或呼叫已結束為什麼所撰寫。</span><span class="sxs-lookup"><span data-stu-id="1b893-140">These records are written by Front End Servers to reflect whether end users were able to connect to a call or why a call was terminated.</span></span> <span data-ttu-id="1b893-141">這些查詢結果會指出當各種使用者的提醒中遇到對等通話或基本會議功能的連線的問題。</span><span class="sxs-lookup"><span data-stu-id="1b893-141">These queries result in alerts that indicate when a wide range of end users are experiencing connectivity issues for peer-to-peer calls or basic conferencing functionality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b893-142">媒體品質通知</span><span class="sxs-lookup"><span data-stu-id="1b893-142">Media Quality Alerts</span></span></p></td>
<td><p><span data-ttu-id="1b893-143">資料庫查詢該一下結尾的每個通話的用戶端所發佈的經驗品質 (QoE) 報告。</span><span class="sxs-lookup"><span data-stu-id="1b893-143">Database queries that look at Quality of Experience (QoE) reports published by clients at the end of each call.</span></span> <span data-ttu-id="1b893-144">這些查詢結果中找出使用者所在位置，可能會遇到不佳的媒體品質期間的通話及會議案例的提醒。</span><span class="sxs-lookup"><span data-stu-id="1b893-144">These queries result in alerts that pinpoint scenarios where users are likely to be experiencing poor media quality during calls and conferences.</span></span> <span data-ttu-id="1b893-145">資料是建置於重要量值，例如封包延遲和遺失、 已知直接參與通話品質計量。</span><span class="sxs-lookup"><span data-stu-id="1b893-145">The data is built upon key metrics such as packet latency and loss, metrics that are known to directly contribute to call quality.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b893-146">元件運作情況</span><span class="sxs-lookup"><span data-stu-id="1b893-146">Component Health</span></span></p></td>
<td><p><span data-ttu-id="1b893-147">個別的伺服器元件使用事件記錄檔及效能計數器引發警示。</span><span class="sxs-lookup"><span data-stu-id="1b893-147">Individual server components raise alerts by using event logs and performance counters.</span></span> <span data-ttu-id="1b893-148">這些警示，指出可能會造成嚴重影響一或多個使用者案例的失敗情況。</span><span class="sxs-lookup"><span data-stu-id="1b893-148">These alerts indicate failure conditions that can severely impact one or more end user scenarios.</span></span> <span data-ttu-id="1b893-149">這些警示也可以指出各種不同的其他失敗情況，包括未執行的服務、 高錯誤率、 高郵件延遲或連線問題。</span><span class="sxs-lookup"><span data-stu-id="1b893-149">These alerts can also indicate a variety of other failure conditions, including services not running, high failure rates, high message latency, or connectivity issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b893-150">相依性運作情況</span><span class="sxs-lookup"><span data-stu-id="1b893-150">Dependency Health</span></span></p></td>
<td><p><span data-ttu-id="1b893-151">各種不同的外部原因可能是失敗。</span><span class="sxs-lookup"><span data-stu-id="1b893-151">Failures can occur for a variety of external reasons.</span></span> <span data-ttu-id="1b893-152">管理組件現在會監視，並收集資料的一些可能表示嚴重問題，包括 IIS 伺服器和處理程序及磁碟計量的可用性、 CPU 及記憶體使用量的要徑外部相依性。</span><span class="sxs-lookup"><span data-stu-id="1b893-152">The management packs now monitor and collect data for some of the critical external dependencies that might indicate severe issues, including IIS availability, CPU and memory usage of servers and processes, and disk metrics.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1b893-153">系統發出的通知分為三大類別：</span><span class="sxs-lookup"><span data-stu-id="1b893-153">The alerts issued by the system have been classified into three general categories:</span></span>

  - <span data-ttu-id="1b893-154">**高優先順序的警示。**</span><span class="sxs-lookup"><span data-stu-id="1b893-154">**High-priority Alerts.**</span></span> <span data-ttu-id="1b893-155">這些警示指出將會造成服務中斷情形的大型使用者群組的條件。</span><span class="sxs-lookup"><span data-stu-id="1b893-155">These alerts indicate conditions that will cause service outages for large groups of users.</span></span> <span data-ttu-id="1b893-156">例如，在單一機器上的元件失敗不高優先順序警示因為 Lync Server 2013 已內建的高可用性功能。</span><span class="sxs-lookup"><span data-stu-id="1b893-156">For example, a component failure on a single machine is not a high-priority alert because Lync Server 2013 has built-in high availability features.</span></span> <span data-ttu-id="1b893-157">相反地，高優先順序警示表示問題嚴重 」 至喚醒系統管理員在夜間。 」</span><span class="sxs-lookup"><span data-stu-id="1b893-157">Instead, high-priority alerts represent problems serious enough “to wake up administrators at night.”</span></span> <span data-ttu-id="1b893-158">綜合交易和離線服務 （例如，音訊/視訊會議） 所偵測到的中斷限定為高優先順序的警示。</span><span class="sxs-lookup"><span data-stu-id="1b893-158">Outages detected by synthetic transactions and offline services (for example, audio/video conferencing) qualify as high-priority alerts.</span></span>

  - <span data-ttu-id="1b893-159">**中度優先順序警示。**。</span><span class="sxs-lookup"><span data-stu-id="1b893-159">**Medium-priority alerts.**.</span></span> <span data-ttu-id="1b893-160">這些警示，指出會影響使用者的子集，或指出通話品質降低的條件。</span><span class="sxs-lookup"><span data-stu-id="1b893-160">These alerts indicate conditions that affect a subset of users or indicate call quality degradation.</span></span> <span data-ttu-id="1b893-161">在呼叫建立或在通話的降級音訊品質包含例如元件失敗，延遲的問題。</span><span class="sxs-lookup"><span data-stu-id="1b893-161">That includes problems such as component failures, latency in call establishment, or degraded audio quality in call.</span></span> <span data-ttu-id="1b893-162">此類別中的警示是可設定狀態，並指出之問題的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="1b893-162">Alerts in this category are stateful and indicate the current status of the issue.</span></span> <span data-ttu-id="1b893-163">例如，假設您呼叫的建立時間超過警示臨界值。</span><span class="sxs-lookup"><span data-stu-id="1b893-163">For example, suppose your call establishment times exceed the alert threshold.</span></span> <span data-ttu-id="1b893-164">如果呼叫建立時間傳回為 normal，這些通知就會在 System Center Operations Manager 中自動解決。</span><span class="sxs-lookup"><span data-stu-id="1b893-164">If call establishment times return to normal, these alerts will be auto-resolved in System Center Operations Manager.</span></span> <span data-ttu-id="1b893-165">這些警示的期望時，系統管理員會查看他們在相同的工作天。</span><span class="sxs-lookup"><span data-stu-id="1b893-165">The expectation for these alerts is that an administrator will look at them on the same business day.</span></span>

  - <span data-ttu-id="1b893-166">**其他的警告。**</span><span class="sxs-lookup"><span data-stu-id="1b893-166">**Other alerts.**</span></span> <span data-ttu-id="1b893-167">這些是警示可能會影響到特定使用者子集的元件。</span><span class="sxs-lookup"><span data-stu-id="1b893-167">These are alerts from components that might affect a specific user or subset of users.</span></span> <span data-ttu-id="1b893-168">例如，甚至通訊錄服務無法剖析特定使用者的 Active Directory 項目。</span><span class="sxs-lookup"><span data-stu-id="1b893-168">For example, perhaps the Address Book service could not parse the Active Directory entry of a given user.</span></span> <span data-ttu-id="1b893-169">這些警示的期望是系統管理員將取得給他們，當他們有可用的時間。</span><span class="sxs-lookup"><span data-stu-id="1b893-169">The expectation for these alerts is that administrators will get to them when they have time available.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1b893-170">本章節內容</span><span class="sxs-lookup"><span data-stu-id="1b893-170">In This Section</span></span>

  - [<span data-ttu-id="1b893-171">設定 Lync Server 2013 來使用 System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="1b893-171">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [<span data-ttu-id="1b893-172">使用 Lync Server 2013 中的綜合交易的豐富記錄</span><span class="sxs-lookup"><span data-stu-id="1b893-172">Using rich logging for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [<span data-ttu-id="1b893-173">使用 Microsoft SQL Server 2008 R2 當成 System Center Operations Manager 資料庫 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b893-173">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

