---
title: Lync Server 2013：運作相依性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Operational dependencies
ms:assetid: 450b6be2-7fb3-47d7-8b0b-c05faa331e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720559(v=OCS.15)
ms:contentKeyID: 63969597
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e506fbbe204b7248396c25c3728556c61681cbf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526570"
---
# <a name="operational-dependencies-in-lync-server-2013"></a><span data-ttu-id="db771-102">Lync Server 2013 的運作相依性</span><span class="sxs-lookup"><span data-stu-id="db771-102">Operational dependencies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db771-103">_**主題上次修改日期：** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="db771-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="db771-104">本檔中所討論的參考架構可協助確保您具有 Lync Server 2013 部署，但不僅可以縮放至組織的需求，還會以 Microsoft 的最佳作法架構為基礎。</span><span class="sxs-lookup"><span data-stu-id="db771-104">The Reference Architecture discussed in this document will help ensure that you have a Lync Server 2013 deployment that not only scales to the organization’s requirements but is architected as per Microsoft best practices.</span></span> <span data-ttu-id="db771-105">請注意，它可能是 Lync Server 2013 的實施方式，也就是企業中的任何其他服務，都仍然需要監控和主動管理，才能維持高層次的服務可用性及服務品質給企業。</span><span class="sxs-lookup"><span data-stu-id="db771-105">Be that as it may the Lync Server 2013 implementation is a dynamic service and like any other service in the enterprise still requires monitoring and proactive management to maintain high level of service availability and service quality to the business.</span></span>

<span data-ttu-id="db771-106">在組織的日常業務中，Lync Server 2013 變得更深入 ingrained，這一點很重要：服務必須正確且有形的服務層級管理才能加以管理。</span><span class="sxs-lookup"><span data-stu-id="db771-106">As Lync Server 2013 becomes deeply ingrained in the organization’s everyday business it is important that the service be managed by accurate and tangible service level management.</span></span> <span data-ttu-id="db771-107">Lync 系統架構可能會變得複雜而且非常整合，為了維護有效的服務層級管理，並建立 Lync Server 2013 的 Sla，對了解系統對其他平臺和伺服器的相依性而言變得很重要。</span><span class="sxs-lookup"><span data-stu-id="db771-107">The Lync system architecture can become complex and very integrated and in order to maintain effective service level management and establish SLAs for Lync Server 2013 it becomes critical to understand the system’s dependencies on other platforms and servers.</span></span> <span data-ttu-id="db771-108">同樣重要的是，請注意哪些商務服務（例如語音和 UC 整合的應用程式）會因 Lync 而異。</span><span class="sxs-lookup"><span data-stu-id="db771-108">Equally important is to note which business services, such as voice and UC integrated applications, become dependent on Lync.</span></span>

<span data-ttu-id="db771-109">必須建立 Lync Server 2013，請注意所有說出的相依性。</span><span class="sxs-lookup"><span data-stu-id="db771-109">Lync Server 2013 must be established noting all the said dependencies.</span></span> <span data-ttu-id="db771-110">服務地圖可讓您在 Lync 及其相依的服務之間制定 SLA，並提供 SLA 協商的開始位置。</span><span class="sxs-lookup"><span data-stu-id="db771-110">The service map will allow you to formulate a SLA between Lync and its dependent service and provide a starting place for SLA negotiation.</span></span>

<span data-ttu-id="db771-111">下表列出 Lync 基礎結構的一般相依性服務。</span><span class="sxs-lookup"><span data-stu-id="db771-111">The following table lists the typical dependency services for a Lync infrastructure.</span></span> <span data-ttu-id="db771-112">這些技術中的每一項都應有自己的主動監控。</span><span class="sxs-lookup"><span data-stu-id="db771-112">Each of these technologies should have its own proactive monitoring.</span></span>

### <a name="typical-dependency-services"></a><span data-ttu-id="db771-113">一般相關性服務</span><span class="sxs-lookup"><span data-stu-id="db771-113">Typical dependency services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db771-114">Dependency 服務</span><span class="sxs-lookup"><span data-stu-id="db771-114">Dependency Service</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db771-115">作業系統</span><span class="sxs-lookup"><span data-stu-id="db771-115">Operating systems</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db771-116">伺服器硬體</span><span class="sxs-lookup"><span data-stu-id="db771-116">Server Hardware</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db771-117">Active Directory</span><span class="sxs-lookup"><span data-stu-id="db771-117">Active Directory</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db771-118">公開金鑰基礎結構</span><span class="sxs-lookup"><span data-stu-id="db771-118">Public Key Infrastructure</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db771-119">網域命名服務</span><span class="sxs-lookup"><span data-stu-id="db771-119">Domain Naming Service</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db771-120">資料庫服務</span><span class="sxs-lookup"><span data-stu-id="db771-120">Database Services</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db771-121">儲存服務</span><span class="sxs-lookup"><span data-stu-id="db771-121">Storage Services</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db771-122">系統管理–監控與發佈</span><span class="sxs-lookup"><span data-stu-id="db771-122">System Management – Monitoring and distribution</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db771-123">安全服務-防病毒</span><span class="sxs-lookup"><span data-stu-id="db771-123">Security Services - Antivirus</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db771-124">網路基礎結構-網際網路</span><span class="sxs-lookup"><span data-stu-id="db771-124">Network Infrastructure - Internet</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db771-125">網路基礎結構–內部 (LAN/WAN) </span><span class="sxs-lookup"><span data-stu-id="db771-125">Network Infrastructure – Internal (LAN/WAN)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db771-126">電話語音基礎結構– IP-PBX 和閘道</span><span class="sxs-lookup"><span data-stu-id="db771-126">Telephony Infrastructure – IP-PBX and Gateways</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db771-127">雲端服務</span><span class="sxs-lookup"><span data-stu-id="db771-127">Cloud Services</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="db771-128">假設組織的運作變得很成熟，其作用如 MOF 所規定的變更、事件及版本管理等基本服務等級管理功能。</span><span class="sxs-lookup"><span data-stu-id="db771-128">It is assumed that the organization is operationally mature in exercising basic service level management functions such as change, incident and release management as prescribed by the MOF.</span></span> <span data-ttu-id="db771-129">Lync 解決方案應採用這些功能，並遵循相同的操作管理程式。</span><span class="sxs-lookup"><span data-stu-id="db771-129">The Lync solution should be adopted by these functions and become subject to the same operational management processes.</span></span>

<span data-ttu-id="db771-130">根據以上取得的資訊來建立，我們現在更深入瞭解對企業中的 Lync 服務有何影響。</span><span class="sxs-lookup"><span data-stu-id="db771-130">Building on the information obtained above we now have a greater understanding of what can impact the Lync service in the enterprise.</span></span> <span data-ttu-id="db771-131">為了協助確保 Lync Server 2013 服務可用性和品質，下列監控工具必須附帶參考架構部署：</span><span class="sxs-lookup"><span data-stu-id="db771-131">To help ensure Lync Server 2013 service availability and quality, the following monitoring tools must accompany the reference architecture deployment:</span></span>

### <a name="monitoring-tools"></a><span data-ttu-id="db771-132">監視工具</span><span class="sxs-lookup"><span data-stu-id="db771-132">Monitoring tools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db771-133">元件</span><span class="sxs-lookup"><span data-stu-id="db771-133">Component</span></span></th>
<th><span data-ttu-id="db771-134">描述</span><span class="sxs-lookup"><span data-stu-id="db771-134">Description</span></span></th>
<th><span data-ttu-id="db771-135">適用的網站</span><span class="sxs-lookup"><span data-stu-id="db771-135">Applicable Site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db771-136">Lync Server 2013 監控伺服器</span><span class="sxs-lookup"><span data-stu-id="db771-136">Lync Server 2013 Monitoring Server</span></span></p></td>
<td><p><span data-ttu-id="db771-137">每個中央網站至少部署一個 Lync Server 2013 監控伺服器角色，並設定 (QoE) 報告套件的經驗品質。</span><span class="sxs-lookup"><span data-stu-id="db771-137">Deploy at least one Lync Server 2013 Monitoring Server role per Central site and configure Quality of Experience (QoE) Reporting Pack.</span></span></p>
<p><span data-ttu-id="db771-138">如需詳細資訊，請參閱 Lync Server 2013 部署檔：</span><span class="sxs-lookup"><span data-stu-id="db771-138">Refer to the Lync Server 2013 Deployment documentation for further details:</span></span></p>
<p><span data-ttu-id="db771-139"><a href="lync-server-2013-deploying-monitoring.md">在 Lync Server 2013 中部署監控</a></span><span class="sxs-lookup"><span data-stu-id="db771-139"><a href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="db771-140">中央網站</span><span class="sxs-lookup"><span data-stu-id="db771-140">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="db771-141">將每個集區 Tether 至其最接近的監控伺服器角色實例。</span><span class="sxs-lookup"><span data-stu-id="db771-141">Tether each pool to its nearest instance of the Monitoring Server role.</span></span></p></td>
<td><p><span data-ttu-id="db771-142">中央網站</span><span class="sxs-lookup"><span data-stu-id="db771-142">Central sites</span></span></p>
<p><span data-ttu-id="db771-143">分支網站</span><span class="sxs-lookup"><span data-stu-id="db771-143">Branch sites</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db771-144">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="db771-144">System Center Operations Manager 2012</span></span></p></td>
<td><p><span data-ttu-id="db771-145">System Center Operations Manager 2012 使用 Microsoft Lync Server 2013 管理元件 (MP) 匯入。</span><span class="sxs-lookup"><span data-stu-id="db771-145">System Center Operations Manager 2012 with the Microsoft Lync Server 2013 Management Pack (MP) imported.</span></span></p>
<p><span data-ttu-id="db771-146">管理套件會使用傳統事件記錄檔和效能計數器型工具，並在 Lync Server 2013 中啟用新近可用的器械功能。</span><span class="sxs-lookup"><span data-stu-id="db771-146">The Management Pack implements traditional Event Log and Performance counter based instrumentation is utilized as well as enabling newly available instrumentation in Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="db771-147">中央網站</span><span class="sxs-lookup"><span data-stu-id="db771-147">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="db771-148">根據讀取中央管理資料庫中發佈的拓撲檔的中央探索腳本，確定已自動完成探索需要監控之角色和元件的集中探索。</span><span class="sxs-lookup"><span data-stu-id="db771-148">Make sure that Central Discovery to discovery of roles and components that need to be monitored are automatically completed based on a central discovery script that reads the topology document published in Central Management Database.</span></span></p></td>
<td><p><span data-ttu-id="db771-149">中央網站</span><span class="sxs-lookup"><span data-stu-id="db771-149">Central Site</span></span></p>
<p><span data-ttu-id="db771-150">分支網站</span><span class="sxs-lookup"><span data-stu-id="db771-150">Branch Site</span></span></p>
<p><span data-ttu-id="db771-151">Edge 網站</span><span class="sxs-lookup"><span data-stu-id="db771-151">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="db771-152">將 System 中心 Operations Manager 2007 代理程式部署至所有執行 Lync Server 的已部署伺服器。</span><span class="sxs-lookup"><span data-stu-id="db771-152">Deploy System Centre Operations Manager 2007 agents to all deployed servers running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="db771-153">中央網站</span><span class="sxs-lookup"><span data-stu-id="db771-153">Central Site</span></span></p>
<p><span data-ttu-id="db771-154">分支網站</span><span class="sxs-lookup"><span data-stu-id="db771-154">Branch Site</span></span></p>
<p><span data-ttu-id="db771-155">Edge 網站</span><span class="sxs-lookup"><span data-stu-id="db771-155">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="db771-156">請確定已為通知設定優先順序警示：</span><span class="sxs-lookup"><span data-stu-id="db771-156">Make sure Prioritized Alerts are configured for notification:</span></span></p>
<p><span data-ttu-id="db771-157">高優先順序警示</span><span class="sxs-lookup"><span data-stu-id="db771-157">High Priority Alerts</span></span></p>
<p><span data-ttu-id="db771-158">中優先順序警示</span><span class="sxs-lookup"><span data-stu-id="db771-158">Medium Priority Alerts</span></span></p>
<p><span data-ttu-id="db771-159">其他警示。</span><span class="sxs-lookup"><span data-stu-id="db771-159">Other Alerts.</span></span></p></td>
<td><p><span data-ttu-id="db771-160">中央網站</span><span class="sxs-lookup"><span data-stu-id="db771-160">Central Site</span></span></p>
<p><span data-ttu-id="db771-161">分支網站</span><span class="sxs-lookup"><span data-stu-id="db771-161">Branch Site</span></span></p>
<p><span data-ttu-id="db771-162">Edge 網站</span><span class="sxs-lookup"><span data-stu-id="db771-162">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="db771-163">設定部署的埠監視。</span><span class="sxs-lookup"><span data-stu-id="db771-163">Configure Port monitoring for your deployment.</span></span></p></td>
<td><p><span data-ttu-id="db771-164">中央網站</span><span class="sxs-lookup"><span data-stu-id="db771-164">Central Site</span></span></p>
<p><span data-ttu-id="db771-165">分支網站</span><span class="sxs-lookup"><span data-stu-id="db771-165">Branch Site</span></span></p>
<p><span data-ttu-id="db771-166">Edge 網站</span><span class="sxs-lookup"><span data-stu-id="db771-166">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="db771-167">設定部署的 URL 監控</span><span class="sxs-lookup"><span data-stu-id="db771-167">Configure URL monitoring for your deployment</span></span></p></td>
<td><p><span data-ttu-id="db771-168">中央網站</span><span class="sxs-lookup"><span data-stu-id="db771-168">Central Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db771-169">Lync 和 System Center Operations Manager 整合</span><span class="sxs-lookup"><span data-stu-id="db771-169">Lync and System Center Operations Manager integration</span></span></p></td>
<td><p><span data-ttu-id="db771-170">部署通話可靠性和媒體質量 MonitoringCall 可靠性和媒體質量監控使用監控伺服器電腦作為其監看員節點，以監視 Lync Server 的通話可靠性和媒體質量。</span><span class="sxs-lookup"><span data-stu-id="db771-170">Deploy Call Reliability and Media Quality MonitoringCall reliability and media quality monitoring use the Monitoring Server computer as their watcher node to monitor call reliability and media quality of Lync Server.</span></span> <span data-ttu-id="db771-171">這兩項功能都會查詢監控伺服器資料庫，以進行分析。</span><span class="sxs-lookup"><span data-stu-id="db771-171">Both of these features query the Monitoring Server databases to do analysis.</span></span></p></td>
<td><p><span data-ttu-id="db771-172">中央網站</span><span class="sxs-lookup"><span data-stu-id="db771-172">Central Site</span></span></p>
<p><span data-ttu-id="db771-173">分支網站</span><span class="sxs-lookup"><span data-stu-id="db771-173">Branch Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="db771-174">確定已正確設定媒體質量警告閾值。</span><span class="sxs-lookup"><span data-stu-id="db771-174">Ensure Media Quality warning thresholds are accurately configured.</span></span> <span data-ttu-id="db771-175">下表指出編解碼器的最大網路平均觀點。</span><span class="sxs-lookup"><span data-stu-id="db771-175">The following table indicates the maximum Network Mean Opinion Scores by Codec.</span></span> <span data-ttu-id="db771-176">在實際執行中，您必須根據組織的特定 NMOS 分數，監視這些分數。</span><span class="sxs-lookup"><span data-stu-id="db771-176">In production these scores should be monitored for a set period and acceptable thresholds must be established based on the organization specific NMOS scores.</span></span></p></td>
<td><p><span data-ttu-id="db771-177">中央網站</span><span class="sxs-lookup"><span data-stu-id="db771-177">Central Site</span></span></p>
<p><span data-ttu-id="db771-178">分支網站</span><span class="sxs-lookup"><span data-stu-id="db771-178">Branch Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db771-179">Lync Server 2013 綜合交易觀察程式</span><span class="sxs-lookup"><span data-stu-id="db771-179">Lync Server 2013 Synthetic Transaction Watcher</span></span></p></td>
<td><p><span data-ttu-id="db771-180">部署專用的 Lync 伺服器成為綜合交易觀察程式。</span><span class="sxs-lookup"><span data-stu-id="db771-180">Deploy a dedicated Lync Server to be a synthetic transaction watcher.</span></span></p>
<p><span data-ttu-id="db771-181">綜合交易是 Lync Server 2013 Windows PowerShell Cmdlet，由管理套件依預先定義的間隔自動觸發。</span><span class="sxs-lookup"><span data-stu-id="db771-181">Synthetic transactions are Lync Server 2013 Windows PowerShell cmdlets that are automatically triggered by the management pack on a predefined interval.</span></span> <span data-ttu-id="db771-182">這些會在綜合交易觀察程式節點上執行，這是管理員指派的伺服器，負責為每個集區探索及執行 STs。</span><span class="sxs-lookup"><span data-stu-id="db771-182">These are executed on a synthetic transaction watcher node which is an administrator designated server responsible for discovery and execution of STs for each pool.</span></span></p>
<p><span data-ttu-id="db771-183">建議您不要將現有的 Microsoft Lync Server 2013 伺服器當做綜合交易觀察器節點使用。</span><span class="sxs-lookup"><span data-stu-id="db771-183">We do not recommend that you use an existing Microsoft Lync Server 2013 server as a synthetic transaction watcher node.</span></span> <span data-ttu-id="db771-184">這是因為執行 STs 的高 CPU/記憶體使用量需求。</span><span class="sxs-lookup"><span data-stu-id="db771-184">This is due to the high CPU/memory usage requirements for running STs.</span></span> <span data-ttu-id="db771-185">針對綜合交易觀察器節點，使用新的伺服器電腦 (或虛擬伺服器) 。</span><span class="sxs-lookup"><span data-stu-id="db771-185">Use a new server computer (or a virtual server) for the synthetic transaction watcher node.</span></span></p></td>
<td><p><span data-ttu-id="db771-186">中央網站</span><span class="sxs-lookup"><span data-stu-id="db771-186">Central Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="db771-187">部署綜合交易觀察程式節點。</span><span class="sxs-lookup"><span data-stu-id="db771-187">Deploying synthetic transactions watcher node.</span></span></p>
<p><span data-ttu-id="db771-188">從 UCTAP connect 檔參考 MonitoringCS_withSCOM.docx 檔。</span><span class="sxs-lookup"><span data-stu-id="db771-188">Refer to the MonitoringCS_withSCOM.docx document from UCTAP connect documentation.</span></span></p></td>
<td><p><span data-ttu-id="db771-189">中央網站</span><span class="sxs-lookup"><span data-stu-id="db771-189">Central Site</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a><span data-ttu-id="db771-190">每個編解碼器的最大網路 MOS 分數</span><span class="sxs-lookup"><span data-stu-id="db771-190">Maximum Network MOS scores per codec</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db771-191">案例</span><span class="sxs-lookup"><span data-stu-id="db771-191">Scenario</span></span></th>
<th><span data-ttu-id="db771-192">轉碼器</span><span class="sxs-lookup"><span data-stu-id="db771-192">Codec</span></span></th>
<th><span data-ttu-id="db771-193">最大 NMOS</span><span class="sxs-lookup"><span data-stu-id="db771-193">Max NMOS</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db771-194">UC-UC 通話</span><span class="sxs-lookup"><span data-stu-id="db771-194">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="db771-195">RTAudio WB</span><span class="sxs-lookup"><span data-stu-id="db771-195">RTAudio WB</span></span></p></td>
<td><p><span data-ttu-id="db771-196">4.10</span><span class="sxs-lookup"><span data-stu-id="db771-196">4.10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db771-197">UC-UC 通話</span><span class="sxs-lookup"><span data-stu-id="db771-197">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="db771-198">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="db771-198">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="db771-199">2.95</span><span class="sxs-lookup"><span data-stu-id="db771-199">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db771-200">電話會議</span><span class="sxs-lookup"><span data-stu-id="db771-200">Conference call</span></span></p></td>
<td><p><span data-ttu-id="db771-201">警笛</span><span class="sxs-lookup"><span data-stu-id="db771-201">Siren</span></span></p></td>
<td><p><span data-ttu-id="db771-202">3.72</span><span class="sxs-lookup"><span data-stu-id="db771-202">3.72</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db771-203">UC-PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="db771-203">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="db771-204">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="db771-204">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="db771-205">2.95</span><span class="sxs-lookup"><span data-stu-id="db771-205">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db771-206">UC-PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="db771-206">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="db771-207">G-711</span><span class="sxs-lookup"><span data-stu-id="db771-207">G-711</span></span></p></td>
<td><p><span data-ttu-id="db771-208">3.61</span><span class="sxs-lookup"><span data-stu-id="db771-208">3.61</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="db771-209">過去和高於先前的 pro 主動監控活動，應依 Lync RA 操作指南中所定義的每日、每週及每月的週期，針對中央、Edge 和分支網站執行維護工作。</span><span class="sxs-lookup"><span data-stu-id="db771-209">Over and above the previous pro-active monitoring activities, maintenance tasks should be executed for Central, Edge and Branch sites on a recurring daily, weekly and monthly basis as defined in the Lync RA Operations Guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

