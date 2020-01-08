---
title: Lync Server 2013：操作相依性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Operational dependencies
ms:assetid: 450b6be2-7fb3-47d7-8b0b-c05faa331e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720559(v=OCS.15)
ms:contentKeyID: 63969597
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d54ef9959f48c085ad4f5f28f182b86442ebec8c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974688"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="operational-dependencies-in-lync-server-2013"></a><span data-ttu-id="4a532-102">Lync Server 2013 的操作相依性</span><span class="sxs-lookup"><span data-stu-id="4a532-102">Operational dependencies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a532-103">_**主題上次修改日期：** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="4a532-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="4a532-104">本檔中討論的參考體系結構將協助確保您有一份 Lync Server 2013 部署，不僅可根據組織的需求而調整規模，而且會以 Microsoft 最佳做法來設計。</span><span class="sxs-lookup"><span data-stu-id="4a532-104">The Reference Architecture discussed in this document will help ensure that you have a Lync Server 2013 deployment that not only scales to the organization’s requirements but is architected as per Microsoft best practices.</span></span> <span data-ttu-id="4a532-105">請注意，這可能是 Lync Server 2013 實現是動態服務，而且與企業中的任何其他服務一樣，都仍需要監視和前瞻性管理，才能維持高層次的服務可用性與企業的服務品質。</span><span class="sxs-lookup"><span data-stu-id="4a532-105">Be that as it may the Lync Server 2013 implementation is a dynamic service and like any other service in the enterprise still requires monitoring and proactive management to maintain high level of service availability and service quality to the business.</span></span>

<span data-ttu-id="4a532-106">隨著 Lync Server 2013 逐漸成為組織日常業務中的 ingrained，請務必透過精確且有形的服務層級管理來管理該服務。</span><span class="sxs-lookup"><span data-stu-id="4a532-106">As Lync Server 2013 becomes deeply ingrained in the organization’s everyday business it is important that the service be managed by accurate and tangible service level management.</span></span> <span data-ttu-id="4a532-107">Lync 系統架構可能會變得複雜且非常複雜，以便維持有效的服務層級管理，並建立 Lync Server 2013 的 Sla，這對於瞭解系統對其他平臺和伺服器的相依性而言是至關重要的。</span><span class="sxs-lookup"><span data-stu-id="4a532-107">The Lync system architecture can become complex and very integrated and in order to maintain effective service level management and establish SLAs for Lync Server 2013 it becomes critical to understand the system’s dependencies on other platforms and servers.</span></span> <span data-ttu-id="4a532-108">同等重要的是，請注意哪些商務服務（例如語音和 UC 整合的應用程式）會依賴 Lync。</span><span class="sxs-lookup"><span data-stu-id="4a532-108">Equally important is to note which business services, such as voice and UC integrated applications, become dependent on Lync.</span></span>

<span data-ttu-id="4a532-109">必須建立 Lync Server 2013，請注意所有說出的相依性。</span><span class="sxs-lookup"><span data-stu-id="4a532-109">Lync Server 2013 must be established noting all the said dependencies.</span></span> <span data-ttu-id="4a532-110">[服務地圖] 可讓您在 Lync 與其相依的服務之間制定 SLA，並提供 SLA 協商的起點。</span><span class="sxs-lookup"><span data-stu-id="4a532-110">The service map will allow you to formulate a SLA between Lync and its dependent service and provide a starting place for SLA negotiation.</span></span>

<span data-ttu-id="4a532-111">下表列出 Lync 基礎結構的典型相依性服務。</span><span class="sxs-lookup"><span data-stu-id="4a532-111">The following table lists the typical dependency services for a Lync infrastructure.</span></span> <span data-ttu-id="4a532-112">這些技術中的每一個都應有自己的前瞻性監視。</span><span class="sxs-lookup"><span data-stu-id="4a532-112">Each of these technologies should have its own proactive monitoring.</span></span>

### <a name="typical-dependency-services"></a><span data-ttu-id="4a532-113">典型的相依性服務</span><span class="sxs-lookup"><span data-stu-id="4a532-113">Typical dependency services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a532-114">相依性服務</span><span class="sxs-lookup"><span data-stu-id="4a532-114">Dependency Service</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a532-115">作業系統</span><span class="sxs-lookup"><span data-stu-id="4a532-115">Operating systems</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a532-116">伺服器硬體</span><span class="sxs-lookup"><span data-stu-id="4a532-116">Server Hardware</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a532-117">Active Directory</span><span class="sxs-lookup"><span data-stu-id="4a532-117">Active Directory</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a532-118">公用金鑰基礎結構</span><span class="sxs-lookup"><span data-stu-id="4a532-118">Public Key Infrastructure</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a532-119">網域命名服務</span><span class="sxs-lookup"><span data-stu-id="4a532-119">Domain Naming Service</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a532-120">資料庫服務</span><span class="sxs-lookup"><span data-stu-id="4a532-120">Database Services</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a532-121">儲存服務</span><span class="sxs-lookup"><span data-stu-id="4a532-121">Storage Services</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a532-122">系統管理-監控與發佈</span><span class="sxs-lookup"><span data-stu-id="4a532-122">System Management – Monitoring and distribution</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a532-123">安全性服務-防毒軟體</span><span class="sxs-lookup"><span data-stu-id="4a532-123">Security Services - Antivirus</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a532-124">網路基礎結構-網際網路</span><span class="sxs-lookup"><span data-stu-id="4a532-124">Network Infrastructure - Internet</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a532-125">網路基礎結構–內部（LAN/WAN）</span><span class="sxs-lookup"><span data-stu-id="4a532-125">Network Infrastructure – Internal (LAN/WAN)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a532-126">電話語音基礎結構-IP-PBX 和閘道</span><span class="sxs-lookup"><span data-stu-id="4a532-126">Telephony Infrastructure – IP-PBX and Gateways</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a532-127">雲端服務</span><span class="sxs-lookup"><span data-stu-id="4a532-127">Cloud Services</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4a532-128">我們會假設組織在使用中的基本服務等級管理功能（例如，由 MOF 所指定的變更、事件和版本管理），以成熟的方式進行。</span><span class="sxs-lookup"><span data-stu-id="4a532-128">It is assumed that the organization is operationally mature in exercising basic service level management functions such as change, incident and release management as prescribed by the MOF.</span></span> <span data-ttu-id="4a532-129">Lync 解決方案應該由這些函數所採納，並遵循相同的操作管理程式。</span><span class="sxs-lookup"><span data-stu-id="4a532-129">The Lync solution should be adopted by these functions and become subject to the same operational management processes.</span></span>

<span data-ttu-id="4a532-130">根據上述取得的資訊來建立，我們現在已更深入瞭解對企業中的 Lync 服務有何影響。</span><span class="sxs-lookup"><span data-stu-id="4a532-130">Building on the information obtained above we now have a greater understanding of what can impact the Lync service in the enterprise.</span></span> <span data-ttu-id="4a532-131">為了協助確保 Lync Server 2013 服務可用性與品質，下列監視工具必須隨附參考體系結構部署：</span><span class="sxs-lookup"><span data-stu-id="4a532-131">To help ensure Lync Server 2013 service availability and quality, the following monitoring tools must accompany the reference architecture deployment:</span></span>

### <a name="monitoring-tools"></a><span data-ttu-id="4a532-132">監視工具</span><span class="sxs-lookup"><span data-stu-id="4a532-132">Monitoring tools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a532-133">元件</span><span class="sxs-lookup"><span data-stu-id="4a532-133">Component</span></span></th>
<th><span data-ttu-id="4a532-134">描述</span><span class="sxs-lookup"><span data-stu-id="4a532-134">Description</span></span></th>
<th><span data-ttu-id="4a532-135">適用的網站</span><span class="sxs-lookup"><span data-stu-id="4a532-135">Applicable Site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a532-136">Lync Server 2013 監視伺服器</span><span class="sxs-lookup"><span data-stu-id="4a532-136">Lync Server 2013 Monitoring Server</span></span></p></td>
<td><p><span data-ttu-id="4a532-137">針對每個中心網站部署至少一個 Lync Server 2013 監視伺服器角色，並設定體驗品質（QoE）報告套件。</span><span class="sxs-lookup"><span data-stu-id="4a532-137">Deploy at least one Lync Server 2013 Monitoring Server role per Central site and configure Quality of Experience (QoE) Reporting Pack.</span></span></p>
<p><span data-ttu-id="4a532-138">如需詳細資訊，請參閱 Lync Server 2013 部署檔：</span><span class="sxs-lookup"><span data-stu-id="4a532-138">Refer to the Lync Server 2013 Deployment documentation for further details:</span></span></p>
<p><span data-ttu-id="4a532-139"><a href="lync-server-2013-deploying-monitoring.md">在 Lync Server 2013 中部署監視</a></span><span class="sxs-lookup"><span data-stu-id="4a532-139"><a href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4a532-140">中央網站</span><span class="sxs-lookup"><span data-stu-id="4a532-140">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="4a532-141">Tether 每個池至其最接近的監視伺服器角色實例。</span><span class="sxs-lookup"><span data-stu-id="4a532-141">Tether each pool to its nearest instance of the Monitoring Server role.</span></span></p></td>
<td><p><span data-ttu-id="4a532-142">中央網站</span><span class="sxs-lookup"><span data-stu-id="4a532-142">Central sites</span></span></p>
<p><span data-ttu-id="4a532-143">分支網站</span><span class="sxs-lookup"><span data-stu-id="4a532-143">Branch sites</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a532-144">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="4a532-144">System Center Operations Manager 2012</span></span></p></td>
<td><p><span data-ttu-id="4a532-145">已匯入 Microsoft Lync Server 2013 管理套件（MP）的 System Center Operations Manager 2012。</span><span class="sxs-lookup"><span data-stu-id="4a532-145">System Center Operations Manager 2012 with the Microsoft Lync Server 2013 Management Pack (MP) imported.</span></span></p>
<p><span data-ttu-id="4a532-146">管理套件可實現傳統的事件記錄和效能計數器式分析，以及在 Lync Server 2013 中啟用新近可用的工具。</span><span class="sxs-lookup"><span data-stu-id="4a532-146">The Management Pack implements traditional Event Log and Performance counter based instrumentation is utilized as well as enabling newly available instrumentation in Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="4a532-147">中央網站</span><span class="sxs-lookup"><span data-stu-id="4a532-147">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="4a532-148">請確定集中式探索要探索的角色和元件會根據中央探索腳本自動完成，此腳本會讀取中央管理資料庫中發佈的拓撲檔。</span><span class="sxs-lookup"><span data-stu-id="4a532-148">Make sure that Central Discovery to discovery of roles and components that need to be monitored are automatically completed based on a central discovery script that reads the topology document published in Central Management Database.</span></span></p></td>
<td><p><span data-ttu-id="4a532-149">中央網站</span><span class="sxs-lookup"><span data-stu-id="4a532-149">Central Site</span></span></p>
<p><span data-ttu-id="4a532-150">分支網站</span><span class="sxs-lookup"><span data-stu-id="4a532-150">Branch Site</span></span></p>
<p><span data-ttu-id="4a532-151">Edge 網站</span><span class="sxs-lookup"><span data-stu-id="4a532-151">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="4a532-152">將 System 中心 Operations Manager 2007 agent 部署到所有執行 Lync Server 的已部署伺服器。</span><span class="sxs-lookup"><span data-stu-id="4a532-152">Deploy System Centre Operations Manager 2007 agents to all deployed servers running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="4a532-153">中央網站</span><span class="sxs-lookup"><span data-stu-id="4a532-153">Central Site</span></span></p>
<p><span data-ttu-id="4a532-154">分支網站</span><span class="sxs-lookup"><span data-stu-id="4a532-154">Branch Site</span></span></p>
<p><span data-ttu-id="4a532-155">Edge 網站</span><span class="sxs-lookup"><span data-stu-id="4a532-155">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="4a532-156">請確定已針對通知設定優先的通知：</span><span class="sxs-lookup"><span data-stu-id="4a532-156">Make sure Prioritized Alerts are configured for notification:</span></span></p>
<p><span data-ttu-id="4a532-157">高優先順序警示</span><span class="sxs-lookup"><span data-stu-id="4a532-157">High Priority Alerts</span></span></p>
<p><span data-ttu-id="4a532-158">中等優先順序警示</span><span class="sxs-lookup"><span data-stu-id="4a532-158">Medium Priority Alerts</span></span></p>
<p><span data-ttu-id="4a532-159">其他通知。</span><span class="sxs-lookup"><span data-stu-id="4a532-159">Other Alerts.</span></span></p></td>
<td><p><span data-ttu-id="4a532-160">中央網站</span><span class="sxs-lookup"><span data-stu-id="4a532-160">Central Site</span></span></p>
<p><span data-ttu-id="4a532-161">分支網站</span><span class="sxs-lookup"><span data-stu-id="4a532-161">Branch Site</span></span></p>
<p><span data-ttu-id="4a532-162">Edge 網站</span><span class="sxs-lookup"><span data-stu-id="4a532-162">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="4a532-163">針對您的部署設定埠監視。</span><span class="sxs-lookup"><span data-stu-id="4a532-163">Configure Port monitoring for your deployment.</span></span></p></td>
<td><p><span data-ttu-id="4a532-164">中央網站</span><span class="sxs-lookup"><span data-stu-id="4a532-164">Central Site</span></span></p>
<p><span data-ttu-id="4a532-165">分支網站</span><span class="sxs-lookup"><span data-stu-id="4a532-165">Branch Site</span></span></p>
<p><span data-ttu-id="4a532-166">Edge 網站</span><span class="sxs-lookup"><span data-stu-id="4a532-166">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="4a532-167">針對您的部署設定 URL 監視</span><span class="sxs-lookup"><span data-stu-id="4a532-167">Configure URL monitoring for your deployment</span></span></p></td>
<td><p><span data-ttu-id="4a532-168">中央網站</span><span class="sxs-lookup"><span data-stu-id="4a532-168">Central Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a532-169">Lync 與系統中心作業管理員整合</span><span class="sxs-lookup"><span data-stu-id="4a532-169">Lync and System Center Operations Manager integration</span></span></p></td>
<td><p><span data-ttu-id="4a532-170">部署通話可靠性和媒體質量 MonitoringCall 可靠性和媒體質量監控使用監視伺服器電腦作為其觀察程式節點，以監控 Lync Server 的通話可靠性和媒體質量。</span><span class="sxs-lookup"><span data-stu-id="4a532-170">Deploy Call Reliability and Media Quality MonitoringCall reliability and media quality monitoring use the Monitoring Server computer as their watcher node to monitor call reliability and media quality of Lync Server.</span></span> <span data-ttu-id="4a532-171">這兩個功能都能查詢監視伺服器資料庫來進行分析。</span><span class="sxs-lookup"><span data-stu-id="4a532-171">Both of these features query the Monitoring Server databases to do analysis.</span></span></p></td>
<td><p><span data-ttu-id="4a532-172">中央網站</span><span class="sxs-lookup"><span data-stu-id="4a532-172">Central Site</span></span></p>
<p><span data-ttu-id="4a532-173">分支網站</span><span class="sxs-lookup"><span data-stu-id="4a532-173">Branch Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="4a532-174">確定正確設定媒體質量警告閾值。</span><span class="sxs-lookup"><span data-stu-id="4a532-174">Ensure Media Quality warning thresholds are accurately configured.</span></span> <span data-ttu-id="4a532-175">下表說明編解碼器的網路平均觀點。</span><span class="sxs-lookup"><span data-stu-id="4a532-175">The following table indicates the maximum Network Mean Opinion Scores by Codec.</span></span> <span data-ttu-id="4a532-176">在生產中，這些分數必須針對設定的期限加以監視，而且必須根據組織的特定 NMOS 分數來建立可接受的閾值。</span><span class="sxs-lookup"><span data-stu-id="4a532-176">In production these scores should be monitored for a set period and acceptable thresholds must be established based on the organization specific NMOS scores.</span></span></p></td>
<td><p><span data-ttu-id="4a532-177">中央網站</span><span class="sxs-lookup"><span data-stu-id="4a532-177">Central Site</span></span></p>
<p><span data-ttu-id="4a532-178">分支網站</span><span class="sxs-lookup"><span data-stu-id="4a532-178">Branch Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a532-179">Lync Server 2013 綜合交易觀察程式</span><span class="sxs-lookup"><span data-stu-id="4a532-179">Lync Server 2013 Synthetic Transaction Watcher</span></span></p></td>
<td><p><span data-ttu-id="4a532-180">將專用的 Lync 伺服器部署為綜合交易觀察程式。</span><span class="sxs-lookup"><span data-stu-id="4a532-180">Deploy a dedicated Lync Server to be a synthetic transaction watcher.</span></span></p>
<p><span data-ttu-id="4a532-181">綜合交易是 Lync Server 2013 的 Windows PowerShell Cmdlet，管理套件會在預先定義的時間間隔自動觸發。</span><span class="sxs-lookup"><span data-stu-id="4a532-181">Synthetic transactions are Lync Server 2013 Windows PowerShell cmdlets that are automatically triggered by the management pack on a predefined interval.</span></span> <span data-ttu-id="4a532-182">這些都是在綜合交易觀察程式節點上執行，這是管理員指派的伺服器，負責針對每個池進行 STs 探索及執行。</span><span class="sxs-lookup"><span data-stu-id="4a532-182">These are executed on a synthetic transaction watcher node which is an administrator designated server responsible for discovery and execution of STs for each pool.</span></span></p>
<p><span data-ttu-id="4a532-183">我們不建議您將現有的 Microsoft Lync Server 2013 伺服器做為綜合交易觀察程式節點。</span><span class="sxs-lookup"><span data-stu-id="4a532-183">We do not recommend that you use an existing Microsoft Lync Server 2013 server as a synthetic transaction watcher node.</span></span> <span data-ttu-id="4a532-184">這是由於執行 STs 的高 CPU/記憶體使用量需求所造成。</span><span class="sxs-lookup"><span data-stu-id="4a532-184">This is due to the high CPU/memory usage requirements for running STs.</span></span> <span data-ttu-id="4a532-185">針對 [綜合交易觀察程式] 節點，使用新的伺服器電腦（或虛擬伺服器）。</span><span class="sxs-lookup"><span data-stu-id="4a532-185">Use a new server computer (or a virtual server) for the synthetic transaction watcher node.</span></span></p></td>
<td><p><span data-ttu-id="4a532-186">中央網站</span><span class="sxs-lookup"><span data-stu-id="4a532-186">Central Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="4a532-187">部署 [綜合交易觀察程式] 節點。</span><span class="sxs-lookup"><span data-stu-id="4a532-187">Deploying synthetic transactions watcher node.</span></span></p>
<p><span data-ttu-id="4a532-188">請參閱 UCTAP connect 檔中的 MonitoringCS_withSCOM .docx 檔。</span><span class="sxs-lookup"><span data-stu-id="4a532-188">Refer to the MonitoringCS_withSCOM.docx document from UCTAP connect documentation.</span></span></p></td>
<td><p><span data-ttu-id="4a532-189">中央網站</span><span class="sxs-lookup"><span data-stu-id="4a532-189">Central Site</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a><span data-ttu-id="4a532-190">每個編解碼器的最大網路 MOS 分數</span><span class="sxs-lookup"><span data-stu-id="4a532-190">Maximum Network MOS scores per codec</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a532-191">例子</span><span class="sxs-lookup"><span data-stu-id="4a532-191">Scenario</span></span></th>
<th><span data-ttu-id="4a532-192">編碼</span><span class="sxs-lookup"><span data-stu-id="4a532-192">Codec</span></span></th>
<th><span data-ttu-id="4a532-193">最大 NMOS</span><span class="sxs-lookup"><span data-stu-id="4a532-193">Max NMOS</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a532-194">UC-UC 通話</span><span class="sxs-lookup"><span data-stu-id="4a532-194">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="4a532-195">RTAudio WB</span><span class="sxs-lookup"><span data-stu-id="4a532-195">RTAudio WB</span></span></p></td>
<td><p><span data-ttu-id="4a532-196">4.10</span><span class="sxs-lookup"><span data-stu-id="4a532-196">4.10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a532-197">UC-UC 通話</span><span class="sxs-lookup"><span data-stu-id="4a532-197">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="4a532-198">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="4a532-198">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="4a532-199">2.95</span><span class="sxs-lookup"><span data-stu-id="4a532-199">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a532-200">電話會議</span><span class="sxs-lookup"><span data-stu-id="4a532-200">Conference call</span></span></p></td>
<td><p><span data-ttu-id="4a532-201">Siren</span><span class="sxs-lookup"><span data-stu-id="4a532-201">Siren</span></span></p></td>
<td><p><span data-ttu-id="4a532-202">3.72</span><span class="sxs-lookup"><span data-stu-id="4a532-202">3.72</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a532-203">UC-PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="4a532-203">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="4a532-204">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="4a532-204">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="4a532-205">2.95</span><span class="sxs-lookup"><span data-stu-id="4a532-205">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a532-206">UC-PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="4a532-206">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="4a532-207">G-711</span><span class="sxs-lookup"><span data-stu-id="4a532-207">G-711</span></span></p></td>
<td><p><span data-ttu-id="4a532-208">3.61</span><span class="sxs-lookup"><span data-stu-id="4a532-208">3.61</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4a532-209">在先前的主動預防性監視活動中，根據在 Lync RA 操作指南中定義的每日、每週和每月，定期執行維護工作。</span><span class="sxs-lookup"><span data-stu-id="4a532-209">Over and above the previous pro-active monitoring activities, maintenance tasks should be executed for Central, Edge and Branch sites on a recurring daily, weekly and monthly basis as defined in the Lync RA Operations Guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

