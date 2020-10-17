---
title: Lync Server 2013：通話許可控制的概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of call admission control
ms:assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398529(v=OCS.15)
ms:contentKeyID: 48184474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe2d7622a29a1526430a25341d04bf0b6399e15a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530690"
---
# <a name="overview-of-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="67910-102">Lync Server 2013 中的通話許可控制概覽</span><span class="sxs-lookup"><span data-stu-id="67910-102">Overview of call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67910-103">_**主題上次修改日期：** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="67910-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="67910-104">即時通訊最在意壅塞網路上可能發生的延遲和封包遺失。</span><span class="sxs-lookup"><span data-stu-id="67910-104">Real-time communications are sensitive to the latency and packet loss that can occur on congested networks.</span></span> <span data-ttu-id="67910-105">通話許可控制服務 (CAC) 會根據可用的網路頻寬，判斷是否允許建立即時通訊工作階段 (如語音或視訊通話)。</span><span class="sxs-lookup"><span data-stu-id="67910-105">Call admission control (CAC) determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="67910-106">Lync Server 2013 中的 CAC 設計提供四個主要屬性：</span><span class="sxs-lookup"><span data-stu-id="67910-106">The CAC design in Lync Server 2013 offers four main attributes:</span></span>

  - <span data-ttu-id="67910-107">部署及管理簡單，並不需要其他設備 (如特別設定的路由器)。</span><span class="sxs-lookup"><span data-stu-id="67910-107">It is simple to deploy and manage without requiring additional equipment, such as specially configured routers.</span></span>

  - <span data-ttu-id="67910-p102">解決重要整合通訊使用案例 (如漫遊使用者及多點出席)。根據端點所在位置，而非使用者所在位置，來強制執行 CAC 原則。</span><span class="sxs-lookup"><span data-stu-id="67910-p102">It addresses critical unified communications use cases, such as roaming users and multiple points of presence. CAC policies are enforced according to where the endpoint is located, not where the user is homed.</span></span>

  - <span data-ttu-id="67910-110">除了語音電話之外，這也適用於其他流量 (如視訊通話及音訊/視訊會議工作階段)。</span><span class="sxs-lookup"><span data-stu-id="67910-110">In addition to voice calls, it can be applied to other traffic, such as video calls and audio/video conferencing sessions.</span></span>

  - <span data-ttu-id="67910-111">提供啟用呈現各種網路拓撲的彈性。</span><span class="sxs-lookup"><span data-stu-id="67910-111">Provides the flexibility to enable representation of various kinds of network topologies.</span></span> <span data-ttu-id="67910-112">如需有關範例，請參閱 [Lync Server 2013 中的 CAC 的元件與拓撲](lync-server-2013-components-and-topologies-for-cac.md)。</span><span class="sxs-lookup"><span data-stu-id="67910-112">For examples, see [Components and topologies for CAC in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).</span></span>

<span data-ttu-id="67910-113">如果新的語音或視訊工作階段超出針對 WAN 連結所設定的頻寬限制，則會封鎖工作階段，或將它重新路由傳送至 PSTN (僅限電話)。</span><span class="sxs-lookup"><span data-stu-id="67910-113">If a new voice or video session exceeds the bandwidth limits that you have set on a WAN link, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>

<span data-ttu-id="67910-p104">CAC 僅控制語音及視訊的即時流量。並不控制資料流量。</span><span class="sxs-lookup"><span data-stu-id="67910-p104">CAC controls real-time traffic for voice and video only. It does not control data traffic.</span></span>

<span data-ttu-id="67910-116">管理員會定義 CAC 原則，這些原則是由隨每個前端集區一起安裝的頻寬原則服務所強制執行。</span><span class="sxs-lookup"><span data-stu-id="67910-116">Administrators define CAC policies, which are enforced by the Bandwidth Policy Service that is installed with every Front End pool.</span></span> <span data-ttu-id="67910-117">CAC 設定會自動傳播至您網路中的所有 Lync Server 前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="67910-117">CAC settings are automatically propagated to all Lync Server Front End Servers in your network.</span></span>

<span data-ttu-id="67910-118">針對因 CAC 原則而失敗的通話，重新路由傳送通話的優先順序如下：</span><span class="sxs-lookup"><span data-stu-id="67910-118">For calls that fail because of CAC policies, the order of precedence for rerouting the call is as follows:</span></span>

1.  <span data-ttu-id="67910-119">網際網路</span><span class="sxs-lookup"><span data-stu-id="67910-119">Internet</span></span>

2.  <span data-ttu-id="67910-120">Pstn</span><span class="sxs-lookup"><span data-stu-id="67910-120">PSTN</span></span>

3.  <span data-ttu-id="67910-121">語音信箱</span><span class="sxs-lookup"><span data-stu-id="67910-121">Voice mail</span></span>

<span data-ttu-id="67910-p106">詳細通話記錄 (CDR) 可擷取重新路由傳送至 PSTN 或語音信箱之通話的資訊。CDR 不會擷取重新路由傳送至網際網路之通話的資訊，因為網際網路是視為替代路徑，而非次要選項。</span><span class="sxs-lookup"><span data-stu-id="67910-p106">Call detail recording (CDR) captures information about calls that are rerouted to the PSTN or to voice mail. CDR does not capture information about calls that are rerouted to the Internet, because the Internet is treated as an alternate path rather than a secondary option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="67910-124">因為頻寬條件約束，所以不會拒絕語音信箱儲放。</span><span class="sxs-lookup"><span data-stu-id="67910-124">Voice mail deposits will not be denied because of bandwidth constraints.</span></span>



</div>

<span data-ttu-id="67910-p107">頻寬原則服務會產生兩種類型的記錄檔，其格式為逗點分隔值 (CSV)。**check failures** 記錄檔會擷取拒絕頻寬要求時的資訊。**link utilization** 記錄檔會擷取網路拓撲及 WAN 連結頻寬使用的快照集。這兩種記錄檔可以協助您根據使用率來微調 CAC 原則。</span><span class="sxs-lookup"><span data-stu-id="67910-p107">The Bandwidth Policy Service generates two types of log files in comma separated values (CSV) format. The **check failures** log file captures information when bandwidth requests are denied. The **link utilization** log file captures a snapshot of the network topology and the WAN link bandwidth utilization. Both of these log files can assist you in fine-tuning your CAC policies based on utilization.</span></span>

<div>

## <a name="call-admission-control-considerations"></a><span data-ttu-id="67910-129">通話許可控制考量</span><span class="sxs-lookup"><span data-stu-id="67910-129">Call Admission Control Considerations</span></span>

<span data-ttu-id="67910-130">系統管理員可選取在設定於中央網站的第一個集區來安裝頻寬原則服務。</span><span class="sxs-lookup"><span data-stu-id="67910-130">The administrator selects to install the Bandwidth Policy Service on the first pool configured in the central site.</span></span> <span data-ttu-id="67910-131">由於每個網路地區只有單一中央網站，所以每個網路地區僅有一項頻寬原則服務，負責管理該區域的頻寬原則和其相關聯的網站以及與這些網站的連結。</span><span class="sxs-lookup"><span data-stu-id="67910-131">Since there is a single central site per network region, there is only one Bandwidth Policy Service per network region, which manages bandwidth policy for that region, its associated sites and the links to those sites.</span></span> <span data-ttu-id="67910-132">頻寬原則服務會作為前端伺服器的一部分來執行，因此在該集區中內建高可用性。</span><span class="sxs-lookup"><span data-stu-id="67910-132">The Bandwidth Policy Service runs as part of the Front End Servers, and therefore high availability is built-in within that pool.</span></span> <span data-ttu-id="67910-133">在每一部前端伺服器上執行的頻寬原則服務會每隔15秒同步處理。</span><span class="sxs-lookup"><span data-stu-id="67910-133">The Bandwidth Policy Service running on each Front End Server synchronizes every 15 seconds.</span></span> <span data-ttu-id="67910-134">如果前端集區失敗，則不會再對該網站執行 CAC 原則，直到前端集區，因此頻寬原則服務也會再次運作。</span><span class="sxs-lookup"><span data-stu-id="67910-134">If the Front End pool fails, CAC policies are no longer enforced for that site until the Front End pool and consequently the Bandwidth Policy Service becomes operational again.</span></span> <span data-ttu-id="67910-135">這表示在頻寬原則服務停止運作期間，所有通話將會通過。</span><span class="sxs-lookup"><span data-stu-id="67910-135">This implies that all calls will go through for the duration the Bandwidth Policy Service is out of service.</span></span> <span data-ttu-id="67910-136">因此在這段期間，您的連結可能會發生頻寬超額的情況</span><span class="sxs-lookup"><span data-stu-id="67910-136">Therefore there is the possibility of bandwidth oversubscription of your links during this period</span></span>

<span data-ttu-id="67910-137">頻寬原則服務可提供前端集區中的高可用性;不過，它不提供跨前端集區的冗余。</span><span class="sxs-lookup"><span data-stu-id="67910-137">The Bandwidth Policy Service provides high availability within a Front End pool; however, it does not provide redundancy across Front End pools.</span></span> <span data-ttu-id="67910-138">頻寬原則服務無法從一個前端集區容錯移轉至另一個前端集區。</span><span class="sxs-lookup"><span data-stu-id="67910-138">The Bandwidth Policy Service cannot failover from one Front End pool to another.</span></span> <span data-ttu-id="67910-139">在還原前端集區的服務後，會繼續執行頻寬原則服務，並可重新執行頻寬原則檢查。</span><span class="sxs-lookup"><span data-stu-id="67910-139">Once service to the Front End pool is restored, the Bandwidth Policy Service is resumed and can enforce bandwidth policy checks again.</span></span>

<div>

## <a name="network-considerations"></a><span data-ttu-id="67910-140">網路考量</span><span class="sxs-lookup"><span data-stu-id="67910-140">Network Considerations</span></span>

<span data-ttu-id="67910-141">雖然 Lync Server 2013 中的頻寬原則服務會強制執行音訊和影片的頻寬限制，但此限制不會在網路路由器上強制執行 (layer 2 和 3) 。</span><span class="sxs-lookup"><span data-stu-id="67910-141">Although bandwidth restriction for audio and video is enforced by the Bandwidth Policy Service in Lync Server 2013, this restriction is not enforced at the network router (layer 2 and 3).</span></span> <span data-ttu-id="67910-142">Lync Server 2010 CAC 無法防止資料應用程式，例如，在 WAN 連結上消耗整個網路頻寬，包括您的 CAC 原則為音訊和影片保留的頻寬。</span><span class="sxs-lookup"><span data-stu-id="67910-142">Lync Server 2010 CAC cannot prevent a data application, for example, from consuming the entire network bandwidth on a WAN link, including the bandwidth that is reserved for audio and video by your CAC policy.</span></span> <span data-ttu-id="67910-143">若要在網路上保護必要的頻寬，您可以將服務品質 (QoS) 通訊協定（如差異服務 (DiffServ) ）。</span><span class="sxs-lookup"><span data-stu-id="67910-143">To protect the necessary bandwidth on your network, you can deploy a Quality of Service (QoS) protocol such as Differentiated Services (DiffServ).</span></span> <span data-ttu-id="67910-144">因此，最佳作法是將您定義的 CAC 頻寬原則與您可能部署的任何 QoS 設定進行協調。</span><span class="sxs-lookup"><span data-stu-id="67910-144">Therefore, a best practice is to coordinate the CAC bandwidth policies you define with any QoS settings that you might deploy.</span></span>

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a><span data-ttu-id="67910-145">透過 VPN 的媒體及訊號路徑</span><span class="sxs-lookup"><span data-stu-id="67910-145">Media and Signaling Paths over VPN</span></span>

<span data-ttu-id="67910-p111">如果您的企業支援透過 VPN 的媒體，請確定媒體串流及訊號串流通過 VPN，或是兩者都是透過網際網路進行路由傳送。媒體及訊號串流預設會通過 VPN 通道。</span><span class="sxs-lookup"><span data-stu-id="67910-p111">If your enterprise supports media through VPN, ensure that either both the media stream and the signaling stream go through the VPN or both are routed through the internet. By default, the media and signaling streams go through the VPN tunnel.</span></span>

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a><span data-ttu-id="67910-148">外部使用者的通話許可控制</span><span class="sxs-lookup"><span data-stu-id="67910-148">Call Admission Control of Outside Users</span></span>

<span data-ttu-id="67910-149">針對網路流量流過網際網路的遠端使用者，不會強制執行通話許可控制服務。</span><span class="sxs-lookup"><span data-stu-id="67910-149">Call admission control is not enforced for remote users where the network traffic flows through the Internet.</span></span> <span data-ttu-id="67910-150">因為媒體流量是透過網際網路進行，而不是由 Lync Server 管理，所以無法套用 CAC。</span><span class="sxs-lookup"><span data-stu-id="67910-150">Because the media traffic is traversing the Internet, which is not managed by Lync Server, CAC cannot be applied.</span></span> <span data-ttu-id="67910-151">不過，會針對流過企業網路的通話部分執行 CAC 檢查。</span><span class="sxs-lookup"><span data-stu-id="67910-151">CAC checks will be performed, however, on the portion of the call that flows through the enterprise network.</span></span>

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a><span data-ttu-id="67910-152">PSTN 連線的通話許可控制</span><span class="sxs-lookup"><span data-stu-id="67910-152">Call Admission Control of PSTN Connections</span></span>

<span data-ttu-id="67910-153">「通話許可控制」會在轉送伺服器上強制實施，不論它是連接至 IP/PBX、PSTN 閘道或 SIP 主幹。</span><span class="sxs-lookup"><span data-stu-id="67910-153">Call admission control is enforceable on the Mediation Server regardless of whether it is connected to an IP/PBX, a PSTN gateway, or a SIP trunk.</span></span> <span data-ttu-id="67910-154">由於轉送伺服器是 back to back user agent (B2BUA) ，因此會終止媒體。</span><span class="sxs-lookup"><span data-stu-id="67910-154">Because the Mediation Server is a back-to-back user agent (B2BUA), it terminates media.</span></span> <span data-ttu-id="67910-155">有兩個連線方：一種連接至 Lync Server 的一面，以及連接到 PSTN 閘道、IP/PBXs 或 SIP 主幹的閘道端。</span><span class="sxs-lookup"><span data-stu-id="67910-155">It has two connection sides: a side that is connected to Lync Server and a gateway side, which is connected to PSTN gateways, IP/PBXs, or SIP trunks.</span></span> <span data-ttu-id="67910-156">如需 PSTN 連線的詳細資訊，請參閱 [在 Lync Server 2013 中規劃 PSTN](lync-server-2013-planning-for-pstn-connectivity.md)連線。</span><span class="sxs-lookup"><span data-stu-id="67910-156">For details about PSTN connections, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).</span></span>

<span data-ttu-id="67910-157">除非啟用媒體旁路，否則可在轉送伺服器的兩側強制 CAC。</span><span class="sxs-lookup"><span data-stu-id="67910-157">CAC can be enforced on both sides of the Mediation Server unless media bypass is enabled.</span></span> <span data-ttu-id="67910-158">如果啟用媒體旁路，媒體流量不會遍歷轉送伺服器，而是直接在 Lync 用戶端和閘道之間流動。</span><span class="sxs-lookup"><span data-stu-id="67910-158">If media bypass is enabled, the media traffic doesn’t traverse the Mediation Server but instead flows directly between the Lync client and the gateway.</span></span> <span data-ttu-id="67910-159">在此情況下，不需要 CAC。</span><span class="sxs-lookup"><span data-stu-id="67910-159">In this case, CAC is not needed.</span></span> <span data-ttu-id="67910-160">如需詳細資訊，請參閱 [在 Lync Server 2013 中規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="67910-160">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).</span></span>

<span data-ttu-id="67910-161">下圖說明如何在啟用或未啟用媒體旁路的情況下於 PSTN 連線上強制執行 CAC。</span><span class="sxs-lookup"><span data-stu-id="67910-161">The following figure illustrates how CAC is enforced on PSTN connections with and without media bypass enabled.</span></span>

<span data-ttu-id="67910-162">**PSTN 連線的通話許可控制強制執行**</span><span class="sxs-lookup"><span data-stu-id="67910-162">**Call admission control enforcement on connections to the PSTN**</span></span>

<span data-ttu-id="67910-163">![語音 CAC 媒體旁路連接強制](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "語音 CAC 媒體旁路連接強制")</span><span class="sxs-lookup"><span data-stu-id="67910-163">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a><span data-ttu-id="67910-164">通話許可控制與舊版 Office Communications Server 的相容性</span><span class="sxs-lookup"><span data-stu-id="67910-164">Compatibility of Call Admission Control with Earlier Versions of Office Communications Server</span></span>

<span data-ttu-id="67910-165">只能在啟用 Lync Server 2010 和更新版本的端點上啟用通話許可控制。</span><span class="sxs-lookup"><span data-stu-id="67910-165">Call admission control can be enabled only on endpoints that are enabled for Lync Server 2010 and later.</span></span>

<span data-ttu-id="67910-166">無法在執行 Office Communicator 2007 R2 或更早版本的端點上啟用通話許可控制。</span><span class="sxs-lookup"><span data-stu-id="67910-166">Call admission control cannot be enabled on endpoints running Office Communicator 2007 R2 or earlier.</span></span>

<span data-ttu-id="67910-167">**不同 Lync Server 版本上的 CAC 應用**</span><span class="sxs-lookup"><span data-stu-id="67910-167">**Application of CAC on different Lync Server versions**</span></span>

<span data-ttu-id="67910-168">![語音 CAC 版本比較圖表](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "語音 CAC 版本比較圖表")</span><span class="sxs-lookup"><span data-stu-id="67910-168">![Voice CAC Version Comparison diagram](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Voice CAC Version Comparison diagram")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

