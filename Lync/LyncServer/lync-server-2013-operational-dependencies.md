---
title: Lync Server 2013：運作相依性
description: Lync Server 2013：運作相依性。
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
ms.openlocfilehash: 4e240981f5dfded7c27f123c8483794ea3ffedff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579189"
---
# <a name="operational-dependencies-in-lync-server-2013"></a><span data-ttu-id="a7594-103">Lync Server 2013 的運作相依性</span><span class="sxs-lookup"><span data-stu-id="a7594-103">Operational dependencies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7594-104">_**主題上次修改日期：** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="a7594-104">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="a7594-105">本檔中所討論的參考架構可協助確保您具有 Lync Server 2013 部署，但不僅可以縮放至組織的需求，還會以 Microsoft 的最佳作法架構為基礎。</span><span class="sxs-lookup"><span data-stu-id="a7594-105">The Reference Architecture discussed in this document will help ensure that you have a Lync Server 2013 deployment that not only scales to the organization’s requirements but is architected as per Microsoft best practices.</span></span> <span data-ttu-id="a7594-106">請注意，它可能是 Lync Server 2013 的實施方式，也就是企業中的任何其他服務，都仍然需要監控和主動管理，才能維持高層次的服務可用性及服務品質給企業。</span><span class="sxs-lookup"><span data-stu-id="a7594-106">Be that as it may the Lync Server 2013 implementation is a dynamic service and like any other service in the enterprise still requires monitoring and proactive management to maintain high level of service availability and service quality to the business.</span></span>

<span data-ttu-id="a7594-107">在組織的日常業務中，Lync Server 2013 變得更深入 ingrained，這一點很重要：服務必須正確且有形的服務層級管理才能加以管理。</span><span class="sxs-lookup"><span data-stu-id="a7594-107">As Lync Server 2013 becomes deeply ingrained in the organization’s everyday business it is important that the service be managed by accurate and tangible service level management.</span></span> <span data-ttu-id="a7594-108">Lync 系統架構可能會變得複雜而且非常整合，為了維護有效的服務層級管理，並建立 Lync Server 2013 的 Sla，對了解系統對其他平臺和伺服器的相依性而言變得很重要。</span><span class="sxs-lookup"><span data-stu-id="a7594-108">The Lync system architecture can become complex and very integrated and in order to maintain effective service level management and establish SLAs for Lync Server 2013 it becomes critical to understand the system’s dependencies on other platforms and servers.</span></span> <span data-ttu-id="a7594-109">同樣重要的是，請注意哪些商務服務（例如語音和 UC 整合的應用程式）會因 Lync 而異。</span><span class="sxs-lookup"><span data-stu-id="a7594-109">Equally important is to note which business services, such as voice and UC integrated applications, become dependent on Lync.</span></span>

<span data-ttu-id="a7594-110">必須建立 Lync Server 2013，請注意所有說出的相依性。</span><span class="sxs-lookup"><span data-stu-id="a7594-110">Lync Server 2013 must be established noting all the said dependencies.</span></span> <span data-ttu-id="a7594-111">服務地圖可讓您在 Lync 及其相依的服務之間制定 SLA，並提供 SLA 協商的開始位置。</span><span class="sxs-lookup"><span data-stu-id="a7594-111">The service map will allow you to formulate a SLA between Lync and its dependent service and provide a starting place for SLA negotiation.</span></span>

<span data-ttu-id="a7594-112">下表列出 Lync 基礎結構的一般相依性服務。</span><span class="sxs-lookup"><span data-stu-id="a7594-112">The following table lists the typical dependency services for a Lync infrastructure.</span></span> <span data-ttu-id="a7594-113">這些技術中的每一項都應有自己的主動監控。</span><span class="sxs-lookup"><span data-stu-id="a7594-113">Each of these technologies should have its own proactive monitoring.</span></span>

### <a name="typical-dependency-services"></a><span data-ttu-id="a7594-114">一般相關性服務</span><span class="sxs-lookup"><span data-stu-id="a7594-114">Typical dependency services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a7594-115">Dependency 服務</span><span class="sxs-lookup"><span data-stu-id="a7594-115">Dependency Service</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7594-116">作業系統</span><span class="sxs-lookup"><span data-stu-id="a7594-116">Operating systems</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7594-117">伺服器硬體</span><span class="sxs-lookup"><span data-stu-id="a7594-117">Server Hardware</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7594-118">Active Directory</span><span class="sxs-lookup"><span data-stu-id="a7594-118">Active Directory</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7594-119">公開金鑰基礎結構</span><span class="sxs-lookup"><span data-stu-id="a7594-119">Public Key Infrastructure</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7594-120">網域命名服務</span><span class="sxs-lookup"><span data-stu-id="a7594-120">Domain Naming Service</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7594-121">資料庫服務</span><span class="sxs-lookup"><span data-stu-id="a7594-121">Database Services</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7594-122">儲存服務</span><span class="sxs-lookup"><span data-stu-id="a7594-122">Storage Services</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7594-123">系統管理–監控與發佈</span><span class="sxs-lookup"><span data-stu-id="a7594-123">System Management – Monitoring and distribution</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7594-124">安全服務-防病毒</span><span class="sxs-lookup"><span data-stu-id="a7594-124">Security Services - Antivirus</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7594-125">網路基礎結構-網際網路</span><span class="sxs-lookup"><span data-stu-id="a7594-125">Network Infrastructure - Internet</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7594-126">網路基礎結構–內部 (LAN/WAN) </span><span class="sxs-lookup"><span data-stu-id="a7594-126">Network Infrastructure – Internal (LAN/WAN)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7594-127">電話語音基礎結構– IP-PBX 和閘道</span><span class="sxs-lookup"><span data-stu-id="a7594-127">Telephony Infrastructure – IP-PBX and Gateways</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7594-128">雲端服務</span><span class="sxs-lookup"><span data-stu-id="a7594-128">Cloud Services</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a7594-129">假設組織的運作變得很成熟，其作用如 MOF 所規定的變更、事件及版本管理等基本服務等級管理功能。</span><span class="sxs-lookup"><span data-stu-id="a7594-129">It is assumed that the organization is operationally mature in exercising basic service level management functions such as change, incident and release management as prescribed by the MOF.</span></span> <span data-ttu-id="a7594-130">Lync 解決方案應採用這些功能，並遵循相同的操作管理程式。</span><span class="sxs-lookup"><span data-stu-id="a7594-130">The Lync solution should be adopted by these functions and become subject to the same operational management processes.</span></span>

<span data-ttu-id="a7594-131">根據以上取得的資訊來建立，我們現在更深入瞭解對企業中的 Lync 服務有何影響。</span><span class="sxs-lookup"><span data-stu-id="a7594-131">Building on the information obtained above we now have a greater understanding of what can impact the Lync service in the enterprise.</span></span> <span data-ttu-id="a7594-132">為了協助確保 Lync Server 2013 服務可用性和品質，下列監控工具必須附帶參考架構部署：</span><span class="sxs-lookup"><span data-stu-id="a7594-132">To help ensure Lync Server 2013 service availability and quality, the following monitoring tools must accompany the reference architecture deployment:</span></span>

### <a name="monitoring-tools"></a><span data-ttu-id="a7594-133">監視工具</span><span class="sxs-lookup"><span data-stu-id="a7594-133">Monitoring tools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a7594-134">元件</span><span class="sxs-lookup"><span data-stu-id="a7594-134">Component</span></span></th>
<th><span data-ttu-id="a7594-135">描述</span><span class="sxs-lookup"><span data-stu-id="a7594-135">Description</span></span></th>
<th><span data-ttu-id="a7594-136">適用的網站</span><span class="sxs-lookup"><span data-stu-id="a7594-136">Applicable Site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7594-137">Lync Server 2013 監控伺服器</span><span class="sxs-lookup"><span data-stu-id="a7594-137">Lync Server 2013 Monitoring Server</span></span></p></td>
<td><p><span data-ttu-id="a7594-138">每個中央網站至少部署一個 Lync Server 2013 監控伺服器角色，並設定 (QoE) 報告套件的經驗品質。</span><span class="sxs-lookup"><span data-stu-id="a7594-138">Deploy at least one Lync Server 2013 Monitoring Server role per Central site and configure Quality of Experience (QoE) Reporting Pack.</span></span></p>
<p><span data-ttu-id="a7594-139">如需詳細資訊，請參閱 Lync Server 2013 部署檔：</span><span class="sxs-lookup"><span data-stu-id="a7594-139">Refer to the Lync Server 2013 Deployment documentation for further details:</span></span></p>
<p><span data-ttu-id="a7594-140"><a href="lync-server-2013-deploying-monitoring.md">在 Lync Server 2013 中部署監控</a></span><span class="sxs-lookup"><span data-stu-id="a7594-140"><a href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a7594-141">中央網站</span><span class="sxs-lookup"><span data-stu-id="a7594-141">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a7594-142">將每個集區 Tether 至其最接近的監控伺服器角色實例。</span><span class="sxs-lookup"><span data-stu-id="a7594-142">Tether each pool to its nearest instance of the Monitoring Server role.</span></span></p></td>
<td><p><span data-ttu-id="a7594-143">中央網站</span><span class="sxs-lookup"><span data-stu-id="a7594-143">Central sites</span></span></p>
<p><span data-ttu-id="a7594-144">分支網站</span><span class="sxs-lookup"><span data-stu-id="a7594-144">Branch sites</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7594-145">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="a7594-145">System Center Operations Manager 2012</span></span></p></td>
<td><p><span data-ttu-id="a7594-146">System Center Operations Manager 2012 使用 Microsoft Lync Server 2013 管理元件 (MP) 匯入。</span><span class="sxs-lookup"><span data-stu-id="a7594-146">System Center Operations Manager 2012 with the Microsoft Lync Server 2013 Management Pack (MP) imported.</span></span></p>
<p><span data-ttu-id="a7594-147">管理套件會使用傳統事件記錄檔和效能計數器型工具，並在 Lync Server 2013 中啟用新近可用的器械功能。</span><span class="sxs-lookup"><span data-stu-id="a7594-147">The Management Pack implements traditional Event Log and Performance counter based instrumentation is utilized as well as enabling newly available instrumentation in Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="a7594-148">中央網站</span><span class="sxs-lookup"><span data-stu-id="a7594-148">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a7594-149">根據讀取中央管理資料庫中發佈的拓撲檔的中央探索腳本，確定已自動完成探索需要監控之角色和元件的集中探索。</span><span class="sxs-lookup"><span data-stu-id="a7594-149">Make sure that Central Discovery to discovery of roles and components that need to be monitored are automatically completed based on a central discovery script that reads the topology document published in Central Management Database.</span></span></p></td>
<td><p><span data-ttu-id="a7594-150">中央網站</span><span class="sxs-lookup"><span data-stu-id="a7594-150">Central Site</span></span></p>
<p><span data-ttu-id="a7594-151">分支網站</span><span class="sxs-lookup"><span data-stu-id="a7594-151">Branch Site</span></span></p>
<p><span data-ttu-id="a7594-152">Edge 網站</span><span class="sxs-lookup"><span data-stu-id="a7594-152">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="a7594-153">將 System 中心 Operations Manager 2007 代理程式部署至所有執行 Lync Server 的已部署伺服器。</span><span class="sxs-lookup"><span data-stu-id="a7594-153">Deploy System Centre Operations Manager 2007 agents to all deployed servers running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="a7594-154">中央網站</span><span class="sxs-lookup"><span data-stu-id="a7594-154">Central Site</span></span></p>
<p><span data-ttu-id="a7594-155">分支網站</span><span class="sxs-lookup"><span data-stu-id="a7594-155">Branch Site</span></span></p>
<p><span data-ttu-id="a7594-156">Edge 網站</span><span class="sxs-lookup"><span data-stu-id="a7594-156">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a7594-157">請確定已為通知設定優先順序警示：</span><span class="sxs-lookup"><span data-stu-id="a7594-157">Make sure Prioritized Alerts are configured for notification:</span></span></p>
<p><span data-ttu-id="a7594-158">高優先順序警示</span><span class="sxs-lookup"><span data-stu-id="a7594-158">High Priority Alerts</span></span></p>
<p><span data-ttu-id="a7594-159">中優先順序警示</span><span class="sxs-lookup"><span data-stu-id="a7594-159">Medium Priority Alerts</span></span></p>
<p><span data-ttu-id="a7594-160">其他警示。</span><span class="sxs-lookup"><span data-stu-id="a7594-160">Other Alerts.</span></span></p></td>
<td><p><span data-ttu-id="a7594-161">中央網站</span><span class="sxs-lookup"><span data-stu-id="a7594-161">Central Site</span></span></p>
<p><span data-ttu-id="a7594-162">分支網站</span><span class="sxs-lookup"><span data-stu-id="a7594-162">Branch Site</span></span></p>
<p><span data-ttu-id="a7594-163">Edge 網站</span><span class="sxs-lookup"><span data-stu-id="a7594-163">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="a7594-164">設定部署的埠監視。</span><span class="sxs-lookup"><span data-stu-id="a7594-164">Configure Port monitoring for your deployment.</span></span></p></td>
<td><p><span data-ttu-id="a7594-165">中央網站</span><span class="sxs-lookup"><span data-stu-id="a7594-165">Central Site</span></span></p>
<p><span data-ttu-id="a7594-166">分支網站</span><span class="sxs-lookup"><span data-stu-id="a7594-166">Branch Site</span></span></p>
<p><span data-ttu-id="a7594-167">Edge 網站</span><span class="sxs-lookup"><span data-stu-id="a7594-167">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a7594-168">設定部署的 URL 監控</span><span class="sxs-lookup"><span data-stu-id="a7594-168">Configure URL monitoring for your deployment</span></span></p></td>
<td><p><span data-ttu-id="a7594-169">中央網站</span><span class="sxs-lookup"><span data-stu-id="a7594-169">Central Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7594-170">Lync 和 System Center Operations Manager 整合</span><span class="sxs-lookup"><span data-stu-id="a7594-170">Lync and System Center Operations Manager integration</span></span></p></td>
<td><p><span data-ttu-id="a7594-171">部署通話可靠性和媒體質量 MonitoringCall 可靠性和媒體質量監控使用監控伺服器電腦作為其監看員節點，以監視 Lync Server 的通話可靠性和媒體質量。</span><span class="sxs-lookup"><span data-stu-id="a7594-171">Deploy Call Reliability and Media Quality MonitoringCall reliability and media quality monitoring use the Monitoring Server computer as their watcher node to monitor call reliability and media quality of Lync Server.</span></span> <span data-ttu-id="a7594-172">這兩項功能都會查詢監控伺服器資料庫，以進行分析。</span><span class="sxs-lookup"><span data-stu-id="a7594-172">Both of these features query the Monitoring Server databases to do analysis.</span></span></p></td>
<td><p><span data-ttu-id="a7594-173">中央網站</span><span class="sxs-lookup"><span data-stu-id="a7594-173">Central Site</span></span></p>
<p><span data-ttu-id="a7594-174">分支網站</span><span class="sxs-lookup"><span data-stu-id="a7594-174">Branch Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a7594-175">確定已正確設定媒體質量警告閾值。</span><span class="sxs-lookup"><span data-stu-id="a7594-175">Ensure Media Quality warning thresholds are accurately configured.</span></span> <span data-ttu-id="a7594-176">下表指出編解碼器的最大網路平均觀點。</span><span class="sxs-lookup"><span data-stu-id="a7594-176">The following table indicates the maximum Network Mean Opinion Scores by Codec.</span></span> <span data-ttu-id="a7594-177">在實際執行中，您必須根據組織的特定 NMOS 分數，監視這些分數。</span><span class="sxs-lookup"><span data-stu-id="a7594-177">In production these scores should be monitored for a set period and acceptable thresholds must be established based on the organization specific NMOS scores.</span></span></p></td>
<td><p><span data-ttu-id="a7594-178">中央網站</span><span class="sxs-lookup"><span data-stu-id="a7594-178">Central Site</span></span></p>
<p><span data-ttu-id="a7594-179">分支網站</span><span class="sxs-lookup"><span data-stu-id="a7594-179">Branch Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7594-180">Lync Server 2013 綜合交易觀察程式</span><span class="sxs-lookup"><span data-stu-id="a7594-180">Lync Server 2013 Synthetic Transaction Watcher</span></span></p></td>
<td><p><span data-ttu-id="a7594-181">部署專用的 Lync 伺服器成為綜合交易觀察程式。</span><span class="sxs-lookup"><span data-stu-id="a7594-181">Deploy a dedicated Lync Server to be a synthetic transaction watcher.</span></span></p>
<p><span data-ttu-id="a7594-182">綜合交易是 Lync Server 2013 Windows PowerShell Cmdlet，由管理套件依預先定義的間隔自動觸發。</span><span class="sxs-lookup"><span data-stu-id="a7594-182">Synthetic transactions are Lync Server 2013 Windows PowerShell cmdlets that are automatically triggered by the management pack on a predefined interval.</span></span> <span data-ttu-id="a7594-183">這些會在綜合交易觀察程式節點上執行，這是管理員指派的伺服器，負責為每個集區探索及執行 STs。</span><span class="sxs-lookup"><span data-stu-id="a7594-183">These are executed on a synthetic transaction watcher node which is an administrator designated server responsible for discovery and execution of STs for each pool.</span></span></p>
<p><span data-ttu-id="a7594-184">建議您不要將現有的 Microsoft Lync Server 2013 伺服器當做綜合交易觀察器節點使用。</span><span class="sxs-lookup"><span data-stu-id="a7594-184">We do not recommend that you use an existing Microsoft Lync Server 2013 server as a synthetic transaction watcher node.</span></span> <span data-ttu-id="a7594-185">這是因為執行 STs 的高 CPU/記憶體使用量需求。</span><span class="sxs-lookup"><span data-stu-id="a7594-185">This is due to the high CPU/memory usage requirements for running STs.</span></span> <span data-ttu-id="a7594-186">針對綜合交易觀察器節點，使用新的伺服器電腦 (或虛擬伺服器) 。</span><span class="sxs-lookup"><span data-stu-id="a7594-186">Use a new server computer (or a virtual server) for the synthetic transaction watcher node.</span></span></p></td>
<td><p><span data-ttu-id="a7594-187">中央網站</span><span class="sxs-lookup"><span data-stu-id="a7594-187">Central Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a7594-188">部署綜合交易觀察程式節點。</span><span class="sxs-lookup"><span data-stu-id="a7594-188">Deploying synthetic transactions watcher node.</span></span></p>
<p><span data-ttu-id="a7594-189">從 UCTAP connect 檔參考 MonitoringCS_withSCOM.docx 檔。</span><span class="sxs-lookup"><span data-stu-id="a7594-189">Refer to the MonitoringCS_withSCOM.docx document from UCTAP connect documentation.</span></span></p></td>
<td><p><span data-ttu-id="a7594-190">中央網站</span><span class="sxs-lookup"><span data-stu-id="a7594-190">Central Site</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a><span data-ttu-id="a7594-191">每個編解碼器的最大網路 MOS 分數</span><span class="sxs-lookup"><span data-stu-id="a7594-191">Maximum Network MOS scores per codec</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a7594-192">案例</span><span class="sxs-lookup"><span data-stu-id="a7594-192">Scenario</span></span></th>
<th><span data-ttu-id="a7594-193">轉碼器</span><span class="sxs-lookup"><span data-stu-id="a7594-193">Codec</span></span></th>
<th><span data-ttu-id="a7594-194">最大 NMOS</span><span class="sxs-lookup"><span data-stu-id="a7594-194">Max NMOS</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7594-195">UC-UC 通話</span><span class="sxs-lookup"><span data-stu-id="a7594-195">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="a7594-196">RTAudio WB</span><span class="sxs-lookup"><span data-stu-id="a7594-196">RTAudio WB</span></span></p></td>
<td><p><span data-ttu-id="a7594-197">4.10</span><span class="sxs-lookup"><span data-stu-id="a7594-197">4.10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7594-198">UC-UC 通話</span><span class="sxs-lookup"><span data-stu-id="a7594-198">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="a7594-199">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="a7594-199">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="a7594-200">2.95</span><span class="sxs-lookup"><span data-stu-id="a7594-200">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7594-201">電話會議</span><span class="sxs-lookup"><span data-stu-id="a7594-201">Conference call</span></span></p></td>
<td><p><span data-ttu-id="a7594-202">警笛</span><span class="sxs-lookup"><span data-stu-id="a7594-202">Siren</span></span></p></td>
<td><p><span data-ttu-id="a7594-203">3.72</span><span class="sxs-lookup"><span data-stu-id="a7594-203">3.72</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7594-204">UC-PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="a7594-204">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="a7594-205">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="a7594-205">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="a7594-206">2.95</span><span class="sxs-lookup"><span data-stu-id="a7594-206">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7594-207">UC-PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="a7594-207">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="a7594-208">G-711</span><span class="sxs-lookup"><span data-stu-id="a7594-208">G-711</span></span></p></td>
<td><p><span data-ttu-id="a7594-209">3.61</span><span class="sxs-lookup"><span data-stu-id="a7594-209">3.61</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a7594-210">過去和高於先前的 pro 主動監控活動，應依 Lync RA 操作指南中所定義的每日、每週及每月的週期，針對中央、Edge 和分支網站執行維護工作。</span><span class="sxs-lookup"><span data-stu-id="a7594-210">Over and above the previous pro-active monitoring activities, maintenance tasks should be executed for Central, Edge and Branch sites on a recurring daily, weekly and monthly basis as defined in the Lync RA Operations Guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

