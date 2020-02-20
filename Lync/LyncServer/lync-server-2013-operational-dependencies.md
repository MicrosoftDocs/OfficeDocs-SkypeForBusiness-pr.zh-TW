---
title: Lync Server 2013： 操作相依性
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
ms.openlocfilehash: 9901d664f667dce2e669b9f20e040b6b2b7ff1a1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="operational-dependencies-in-lync-server-2013"></a><span data-ttu-id="b70d5-102">在 Lync Server 2013 的操作相依性</span><span class="sxs-lookup"><span data-stu-id="b70d5-102">Operational dependencies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b70d5-103">_**主題上次修改日期：** 2015年-05-15_</span><span class="sxs-lookup"><span data-stu-id="b70d5-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="b70d5-104">本文件所述參考架構有助於確保您具有 Lync Server 2013 部署的組織需求的比例，調整不僅架構，根據 Microsoft 最佳作法。</span><span class="sxs-lookup"><span data-stu-id="b70d5-104">The Reference Architecture discussed in this document will help ensure that you have a Lync Server 2013 deployment that not only scales to the organization’s requirements but is architected as per Microsoft best practices.</span></span> <span data-ttu-id="b70d5-105">要亦，就可能的 Lync Server 2013 實作是動態的服務，如同在企業中的任何其他服務仍需要監視和主動式管理以維護高層級的服務可用性和業務的服務品質。</span><span class="sxs-lookup"><span data-stu-id="b70d5-105">Be that as it may the Lync Server 2013 implementation is a dynamic service and like any other service in the enterprise still requires monitoring and proactive management to maintain high level of service availability and service quality to the business.</span></span>

<span data-ttu-id="b70d5-106">為 Lync Server 2013 會變成深 ingrained 組織日常商務版中很重要服務由正確且有形服務層級管理。</span><span class="sxs-lookup"><span data-stu-id="b70d5-106">As Lync Server 2013 becomes deeply ingrained in the organization’s everyday business it is important that the service be managed by accurate and tangible service level management.</span></span> <span data-ttu-id="b70d5-107">複雜且非常整合，可能會變得 Lync 系統架構，並且以維護有效的服務等級管理和建立 Lync Server 2013 的 Sla 成為重要若要了解其他平台與伺服器上的系統的相依性。</span><span class="sxs-lookup"><span data-stu-id="b70d5-107">The Lync system architecture can become complex and very integrated and in order to maintain effective service level management and establish SLAs for Lync Server 2013 it becomes critical to understand the system’s dependencies on other platforms and servers.</span></span> <span data-ttu-id="b70d5-108">同樣重要的是要注意的商務服務，例如語音和 UC 整合式應用程式，成為取決於 Lync。</span><span class="sxs-lookup"><span data-stu-id="b70d5-108">Equally important is to note which business services, such as voice and UC integrated applications, become dependent on Lync.</span></span>

<span data-ttu-id="b70d5-109">您會看到所有前述的相依性必須建立 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="b70d5-109">Lync Server 2013 must be established noting all the said dependencies.</span></span> <span data-ttu-id="b70d5-110">服務對應可讓您制訂 Lync 和其依存服務之間的 SLA，並提供 SLA 交涉的起始位置。</span><span class="sxs-lookup"><span data-stu-id="b70d5-110">The service map will allow you to formulate a SLA between Lync and its dependent service and provide a starting place for SLA negotiation.</span></span>

<span data-ttu-id="b70d5-111">下表列出 Lync 基礎結構的典型的相依性服務。</span><span class="sxs-lookup"><span data-stu-id="b70d5-111">The following table lists the typical dependency services for a Lync infrastructure.</span></span> <span data-ttu-id="b70d5-112">每項技術應該會有其專屬主動式監控。</span><span class="sxs-lookup"><span data-stu-id="b70d5-112">Each of these technologies should have its own proactive monitoring.</span></span>

### <a name="typical-dependency-services"></a><span data-ttu-id="b70d5-113">典型的相依性服務</span><span class="sxs-lookup"><span data-stu-id="b70d5-113">Typical dependency services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b70d5-114">相依性服務</span><span class="sxs-lookup"><span data-stu-id="b70d5-114">Dependency Service</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b70d5-115">作業系統</span><span class="sxs-lookup"><span data-stu-id="b70d5-115">Operating systems</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b70d5-116">伺服器硬體</span><span class="sxs-lookup"><span data-stu-id="b70d5-116">Server Hardware</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b70d5-117">Active Directory</span><span class="sxs-lookup"><span data-stu-id="b70d5-117">Active Directory</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b70d5-118">公開金鑰基礎結構</span><span class="sxs-lookup"><span data-stu-id="b70d5-118">Public Key Infrastructure</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b70d5-119">網域命名服務</span><span class="sxs-lookup"><span data-stu-id="b70d5-119">Domain Naming Service</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b70d5-120">資料庫服務。</span><span class="sxs-lookup"><span data-stu-id="b70d5-120">Database Services</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b70d5-121">儲存體服務</span><span class="sxs-lookup"><span data-stu-id="b70d5-121">Storage Services</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b70d5-122">系統管理-監控和通訊群組</span><span class="sxs-lookup"><span data-stu-id="b70d5-122">System Management – Monitoring and distribution</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b70d5-123">安全性 Services-防毒軟體</span><span class="sxs-lookup"><span data-stu-id="b70d5-123">Security Services - Antivirus</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b70d5-124">網路基礎結構的網際網路</span><span class="sxs-lookup"><span data-stu-id="b70d5-124">Network Infrastructure - Internet</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b70d5-125">網路基礎結構 – 內部 (LAN/WAN)</span><span class="sxs-lookup"><span data-stu-id="b70d5-125">Network Infrastructure – Internal (LAN/WAN)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b70d5-126">電話語音基礎結構 – IP PBX 與閘道</span><span class="sxs-lookup"><span data-stu-id="b70d5-126">Telephony Infrastructure – IP-PBX and Gateways</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b70d5-127">雲端服務</span><span class="sxs-lookup"><span data-stu-id="b70d5-127">Cloud Services</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b70d5-128">假設組織是方面成人中執行基本的服務等級管理功能，例如變更、 事件和版本管理 mof 所述。</span><span class="sxs-lookup"><span data-stu-id="b70d5-128">It is assumed that the organization is operationally mature in exercising basic service level management functions such as change, incident and release management as prescribed by the MOF.</span></span> <span data-ttu-id="b70d5-129">Lync 解決方案應該採用這些函數，並成為受到相同的操作管理程序。</span><span class="sxs-lookup"><span data-stu-id="b70d5-129">The Lync solution should be adopted by these functions and become subject to the same operational management processes.</span></span>

<span data-ttu-id="b70d5-130">現在我們上面取得的資訊為基礎的建置有更深入瞭解什麼可能會影響在企業中的 Lync 服務。</span><span class="sxs-lookup"><span data-stu-id="b70d5-130">Building on the information obtained above we now have a greater understanding of what can impact the Lync service in the enterprise.</span></span> <span data-ttu-id="b70d5-131">為了協助確保 Lync Server 2013 服務的可用性和品質，下列監視工具必須伴隨著參考架構部署：</span><span class="sxs-lookup"><span data-stu-id="b70d5-131">To help ensure Lync Server 2013 service availability and quality, the following monitoring tools must accompany the reference architecture deployment:</span></span>

### <a name="monitoring-tools"></a><span data-ttu-id="b70d5-132">監視工具</span><span class="sxs-lookup"><span data-stu-id="b70d5-132">Monitoring tools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b70d5-133">元件</span><span class="sxs-lookup"><span data-stu-id="b70d5-133">Component</span></span></th>
<th><span data-ttu-id="b70d5-134">描述</span><span class="sxs-lookup"><span data-stu-id="b70d5-134">Description</span></span></th>
<th><span data-ttu-id="b70d5-135">適用的網站</span><span class="sxs-lookup"><span data-stu-id="b70d5-135">Applicable Site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b70d5-136">Lync Server 2013 監控伺服器</span><span class="sxs-lookup"><span data-stu-id="b70d5-136">Lync Server 2013 Monitoring Server</span></span></p></td>
<td><p><span data-ttu-id="b70d5-137">部署每個中央站台的至少一個 Lync Server 2013 Monitoring Server 角色及設定經驗品質 (QoE) 報告套件。</span><span class="sxs-lookup"><span data-stu-id="b70d5-137">Deploy at least one Lync Server 2013 Monitoring Server role per Central site and configure Quality of Experience (QoE) Reporting Pack.</span></span></p>
<p><span data-ttu-id="b70d5-138">Lync Server 2013 部署文件，以進一步的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="b70d5-138">Refer to the Lync Server 2013 Deployment documentation for further details:</span></span></p>
<p><span data-ttu-id="b70d5-139"><a href="lync-server-2013-deploying-monitoring.md">部署 Lync Server 2013 中監視</a></span><span class="sxs-lookup"><span data-stu-id="b70d5-139"><a href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b70d5-140">中央網站</span><span class="sxs-lookup"><span data-stu-id="b70d5-140">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="b70d5-141">Tether 至其最接近的執行個體監控伺服器角色的每個集區。</span><span class="sxs-lookup"><span data-stu-id="b70d5-141">Tether each pool to its nearest instance of the Monitoring Server role.</span></span></p></td>
<td><p><span data-ttu-id="b70d5-142">中央網站</span><span class="sxs-lookup"><span data-stu-id="b70d5-142">Central sites</span></span></p>
<p><span data-ttu-id="b70d5-143">分支站台</span><span class="sxs-lookup"><span data-stu-id="b70d5-143">Branch sites</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b70d5-144">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="b70d5-144">System Center Operations Manager 2012</span></span></p></td>
<td><p><span data-ttu-id="b70d5-145">System Center Operations Manager 2012 與 Microsoft Lync Server 2013 管理組件 (MP) 」 匯入。</span><span class="sxs-lookup"><span data-stu-id="b70d5-145">System Center Operations Manager 2012 with the Microsoft Lync Server 2013 Management Pack (MP) imported.</span></span></p>
<p><span data-ttu-id="b70d5-146">管理組件會實作傳統的事件記錄檔，以及啟用 Lync Server 2013 中的新可用檢測 latency 效能計數器型檢測。</span><span class="sxs-lookup"><span data-stu-id="b70d5-146">The Management Pack implements traditional Event Log and Performance counter based instrumentation is utilized as well as enabling newly available instrumentation in Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="b70d5-147">中央網站</span><span class="sxs-lookup"><span data-stu-id="b70d5-147">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="b70d5-148">請確定集中探索到的角色和元件需要要監視的探索會自動完成讀取拓撲文件發佈中央管理資料庫中的集中探索指令碼為基礎。</span><span class="sxs-lookup"><span data-stu-id="b70d5-148">Make sure that Central Discovery to discovery of roles and components that need to be monitored are automatically completed based on a central discovery script that reads the topology document published in Central Management Database.</span></span></p></td>
<td><p><span data-ttu-id="b70d5-149">中央網站</span><span class="sxs-lookup"><span data-stu-id="b70d5-149">Central Site</span></span></p>
<p><span data-ttu-id="b70d5-150">分支網站</span><span class="sxs-lookup"><span data-stu-id="b70d5-150">Branch Site</span></span></p>
<p><span data-ttu-id="b70d5-151">Edge 網站</span><span class="sxs-lookup"><span data-stu-id="b70d5-151">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="b70d5-152">將系統中心 Operations Manager 2007 代理程式部署至所有部署的伺服器執行 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="b70d5-152">Deploy System Centre Operations Manager 2007 agents to all deployed servers running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="b70d5-153">中央網站</span><span class="sxs-lookup"><span data-stu-id="b70d5-153">Central Site</span></span></p>
<p><span data-ttu-id="b70d5-154">分支網站</span><span class="sxs-lookup"><span data-stu-id="b70d5-154">Branch Site</span></span></p>
<p><span data-ttu-id="b70d5-155">Edge 網站</span><span class="sxs-lookup"><span data-stu-id="b70d5-155">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="b70d5-156">請確定通知設定優先順序的警示：</span><span class="sxs-lookup"><span data-stu-id="b70d5-156">Make sure Prioritized Alerts are configured for notification:</span></span></p>
<p><span data-ttu-id="b70d5-157">高優先順序提醒</span><span class="sxs-lookup"><span data-stu-id="b70d5-157">High Priority Alerts</span></span></p>
<p><span data-ttu-id="b70d5-158">中度優先順序提醒</span><span class="sxs-lookup"><span data-stu-id="b70d5-158">Medium Priority Alerts</span></span></p>
<p><span data-ttu-id="b70d5-159">其他的警告。</span><span class="sxs-lookup"><span data-stu-id="b70d5-159">Other Alerts.</span></span></p></td>
<td><p><span data-ttu-id="b70d5-160">中央網站</span><span class="sxs-lookup"><span data-stu-id="b70d5-160">Central Site</span></span></p>
<p><span data-ttu-id="b70d5-161">分支網站</span><span class="sxs-lookup"><span data-stu-id="b70d5-161">Branch Site</span></span></p>
<p><span data-ttu-id="b70d5-162">Edge 網站</span><span class="sxs-lookup"><span data-stu-id="b70d5-162">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="b70d5-163">設定連接埠監控您的部署。</span><span class="sxs-lookup"><span data-stu-id="b70d5-163">Configure Port monitoring for your deployment.</span></span></p></td>
<td><p><span data-ttu-id="b70d5-164">中央網站</span><span class="sxs-lookup"><span data-stu-id="b70d5-164">Central Site</span></span></p>
<p><span data-ttu-id="b70d5-165">分支網站</span><span class="sxs-lookup"><span data-stu-id="b70d5-165">Branch Site</span></span></p>
<p><span data-ttu-id="b70d5-166">Edge 網站</span><span class="sxs-lookup"><span data-stu-id="b70d5-166">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="b70d5-167">設定 URL 監視您的部署</span><span class="sxs-lookup"><span data-stu-id="b70d5-167">Configure URL monitoring for your deployment</span></span></p></td>
<td><p><span data-ttu-id="b70d5-168">中央網站</span><span class="sxs-lookup"><span data-stu-id="b70d5-168">Central Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b70d5-169">Lync 和 System Center Operations Manager 整合</span><span class="sxs-lookup"><span data-stu-id="b70d5-169">Lync and System Center Operations Manager integration</span></span></p></td>
<td><p><span data-ttu-id="b70d5-170">部署通話可靠性和媒體品質 MonitoringCall 可靠性與媒體品質監控使用監控伺服器電腦作為其監看員節點來監視通話可靠性和媒體品質的 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="b70d5-170">Deploy Call Reliability and Media Quality MonitoringCall reliability and media quality monitoring use the Monitoring Server computer as their watcher node to monitor call reliability and media quality of Lync Server.</span></span> <span data-ttu-id="b70d5-171">這些功能查詢監控伺服器資料庫進行分析。</span><span class="sxs-lookup"><span data-stu-id="b70d5-171">Both of these features query the Monitoring Server databases to do analysis.</span></span></p></td>
<td><p><span data-ttu-id="b70d5-172">中央網站</span><span class="sxs-lookup"><span data-stu-id="b70d5-172">Central Site</span></span></p>
<p><span data-ttu-id="b70d5-173">分支網站</span><span class="sxs-lookup"><span data-stu-id="b70d5-173">Branch Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="b70d5-174">請確定正確地設定媒體品質警告臨界值。</span><span class="sxs-lookup"><span data-stu-id="b70d5-174">Ensure Media Quality warning thresholds are accurately configured.</span></span> <span data-ttu-id="b70d5-175">下表指出最大網路平均意見分數的轉碼器。</span><span class="sxs-lookup"><span data-stu-id="b70d5-175">The following table indicates the maximum Network Mean Opinion Scores by Codec.</span></span> <span data-ttu-id="b70d5-176">在生產環境中應監視這些分數的某一段，並根據組織的特定通話的 NMOS 分數就必須建立可接受的閾值。</span><span class="sxs-lookup"><span data-stu-id="b70d5-176">In production these scores should be monitored for a set period and acceptable thresholds must be established based on the organization specific NMOS scores.</span></span></p></td>
<td><p><span data-ttu-id="b70d5-177">中央網站</span><span class="sxs-lookup"><span data-stu-id="b70d5-177">Central Site</span></span></p>
<p><span data-ttu-id="b70d5-178">分支網站</span><span class="sxs-lookup"><span data-stu-id="b70d5-178">Branch Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b70d5-179">Lync Server 2013 綜合交易監看員</span><span class="sxs-lookup"><span data-stu-id="b70d5-179">Lync Server 2013 Synthetic Transaction Watcher</span></span></p></td>
<td><p><span data-ttu-id="b70d5-180">部署專用的 Lync Server 設為綜合交易監看員。</span><span class="sxs-lookup"><span data-stu-id="b70d5-180">Deploy a dedicated Lync Server to be a synthetic transaction watcher.</span></span></p>
<p><span data-ttu-id="b70d5-181">綜合交易是預先定義的時間間隔自動觸發管理組件的 Lync Server 2013 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b70d5-181">Synthetic transactions are Lync Server 2013 Windows PowerShell cmdlets that are automatically triggered by the management pack on a predefined interval.</span></span> <span data-ttu-id="b70d5-182">這些是指定負責探索及執行 STs 的每個集區伺服器的管理員綜合交易監看員節點上執行。</span><span class="sxs-lookup"><span data-stu-id="b70d5-182">These are executed on a synthetic transaction watcher node which is an administrator designated server responsible for discovery and execution of STs for each pool.</span></span></p>
<p><span data-ttu-id="b70d5-183">我們不建議您的綜合交易監看員節點以使用現有的 Microsoft Lync Server 2013 伺服器。</span><span class="sxs-lookup"><span data-stu-id="b70d5-183">We do not recommend that you use an existing Microsoft Lync Server 2013 server as a synthetic transaction watcher node.</span></span> <span data-ttu-id="b70d5-184">這是因為執行 STs 的高 CPU/記憶體使用量需求。</span><span class="sxs-lookup"><span data-stu-id="b70d5-184">This is due to the high CPU/memory usage requirements for running STs.</span></span> <span data-ttu-id="b70d5-185">綜合交易監看員節點使用新的伺服器電腦 （或虛擬伺服器）。</span><span class="sxs-lookup"><span data-stu-id="b70d5-185">Use a new server computer (or a virtual server) for the synthetic transaction watcher node.</span></span></p></td>
<td><p><span data-ttu-id="b70d5-186">中央網站</span><span class="sxs-lookup"><span data-stu-id="b70d5-186">Central Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="b70d5-187">部署綜合交易監看員節點。</span><span class="sxs-lookup"><span data-stu-id="b70d5-187">Deploying synthetic transactions watcher node.</span></span></p>
<p><span data-ttu-id="b70d5-188">從 UCTAP 參照 MonitoringCS_withSCOM.docx 文件連線文件。</span><span class="sxs-lookup"><span data-stu-id="b70d5-188">Refer to the MonitoringCS_withSCOM.docx document from UCTAP connect documentation.</span></span></p></td>
<td><p><span data-ttu-id="b70d5-189">中央網站</span><span class="sxs-lookup"><span data-stu-id="b70d5-189">Central Site</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a><span data-ttu-id="b70d5-190">每個轉碼器的最大網路 MOS 分數</span><span class="sxs-lookup"><span data-stu-id="b70d5-190">Maximum Network MOS scores per codec</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b70d5-191">案例</span><span class="sxs-lookup"><span data-stu-id="b70d5-191">Scenario</span></span></th>
<th><span data-ttu-id="b70d5-192">轉碼器</span><span class="sxs-lookup"><span data-stu-id="b70d5-192">Codec</span></span></th>
<th><span data-ttu-id="b70d5-193">最大 NMOS</span><span class="sxs-lookup"><span data-stu-id="b70d5-193">Max NMOS</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b70d5-194">UC-UC 通話</span><span class="sxs-lookup"><span data-stu-id="b70d5-194">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="b70d5-195">RTAudio WB</span><span class="sxs-lookup"><span data-stu-id="b70d5-195">RTAudio WB</span></span></p></td>
<td><p><span data-ttu-id="b70d5-196">4.10</span><span class="sxs-lookup"><span data-stu-id="b70d5-196">4.10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b70d5-197">UC-UC 通話</span><span class="sxs-lookup"><span data-stu-id="b70d5-197">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="b70d5-198">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="b70d5-198">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="b70d5-199">2.95</span><span class="sxs-lookup"><span data-stu-id="b70d5-199">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b70d5-200">電話會議</span><span class="sxs-lookup"><span data-stu-id="b70d5-200">Conference call</span></span></p></td>
<td><p><span data-ttu-id="b70d5-201">Siren</span><span class="sxs-lookup"><span data-stu-id="b70d5-201">Siren</span></span></p></td>
<td><p><span data-ttu-id="b70d5-202">3.72</span><span class="sxs-lookup"><span data-stu-id="b70d5-202">3.72</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b70d5-203">UC-PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="b70d5-203">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="b70d5-204">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="b70d5-204">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="b70d5-205">2.95</span><span class="sxs-lookup"><span data-stu-id="b70d5-205">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b70d5-206">UC-PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="b70d5-206">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="b70d5-207">G-711</span><span class="sxs-lookup"><span data-stu-id="b70d5-207">G-711</span></span></p></td>
<td><p><span data-ttu-id="b70d5-208">3.61</span><span class="sxs-lookup"><span data-stu-id="b70d5-208">3.61</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b70d5-209">重要性上一個主動監視活動，維護工作應該要執行管理中心、 Edge 和分支網站上重複執行每日、 每週及每月 Lync RA 作業指南中所定義。</span><span class="sxs-lookup"><span data-stu-id="b70d5-209">Over and above the previous pro-active monitoring activities, maintenance tasks should be executed for Central, Edge and Branch sites on a recurring daily, weekly and monthly basis as defined in the Lync RA Operations Guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

