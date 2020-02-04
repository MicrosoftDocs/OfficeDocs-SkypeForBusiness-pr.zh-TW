---
title: Lync Server 2013：通話許可控制的概覽
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
ms.openlocfilehash: f5b38fbb1ae1e209e5b5332e896d806d1ca24975
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="bdfc6-102">Lync Server 2013 中的通話許可控制概覽</span><span class="sxs-lookup"><span data-stu-id="bdfc6-102">Overview of call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdfc6-103">_**主題上次修改日期：** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="bdfc6-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="bdfc6-104">即時通訊對可能會在擁擠網路上發生的延遲與資料包遺失敏感。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-104">Real-time communications are sensitive to the latency and packet loss that can occur on congested networks.</span></span> <span data-ttu-id="bdfc6-105">[通話許可控制] （CAC）會根據可用的網路頻寬決定是否允許建立即時通訊會話，例如語音或視頻通話。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-105">Call admission control (CAC) determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="bdfc6-106">Lync Server 2013 中的 CAC 設計提供了四個主要屬性：</span><span class="sxs-lookup"><span data-stu-id="bdfc6-106">The CAC design in Lync Server 2013 offers four main attributes:</span></span>

  - <span data-ttu-id="bdfc6-107">您可以輕鬆地部署和管理，不需要額外的裝置，例如特殊設定的路由器。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-107">It is simple to deploy and manage without requiring additional equipment, such as specially configured routers.</span></span>

  - <span data-ttu-id="bdfc6-108">它解決了重要的整合通訊使用案例，例如漫遊使用者和多個目前狀態點。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-108">It addresses critical unified communications use cases, such as roaming users and multiple points of presence.</span></span> <span data-ttu-id="bdfc6-109">系統會根據端點所在的位置強制執行 CAC 原則，而不是使用者的駐留位置。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-109">CAC policies are enforced according to where the endpoint is located, not where the user is homed.</span></span>

  - <span data-ttu-id="bdfc6-110">除了語音通話之外，也可以將它套用到其他流量，例如視頻通話和音訊/視訊會議會話。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-110">In addition to voice calls, it can be applied to other traffic, such as video calls and audio/video conferencing sessions.</span></span>

  - <span data-ttu-id="bdfc6-111">提供靈活的方式來啟用各種類型的網路拓撲。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-111">Provides the flexibility to enable representation of various kinds of network topologies.</span></span> <span data-ttu-id="bdfc6-112">如需範例，請參閱[Lync Server 2013 中的 CAC 元件與拓撲](lync-server-2013-components-and-topologies-for-cac.md)。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-112">For examples, see [Components and topologies for CAC in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).</span></span>

<span data-ttu-id="bdfc6-113">如果新的語音或視頻會話超過您在 WAN 連結上設定的頻寬限制，該會話會被封鎖，或（僅限電話撥打電話）重新路由至 PSTN。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-113">If a new voice or video session exceeds the bandwidth limits that you have set on a WAN link, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>

<span data-ttu-id="bdfc6-114">CAC 只會控制語音和影片的即時流量。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-114">CAC controls real-time traffic for voice and video only.</span></span> <span data-ttu-id="bdfc6-115">它不會控制資料流量。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-115">It does not control data traffic.</span></span>

<span data-ttu-id="bdfc6-116">系統管理員會定義 CAC 原則，這些原則是由每個前端池所安裝的頻寬原則服務所強制執行。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-116">Administrators define CAC policies, which are enforced by the Bandwidth Policy Service that is installed with every Front End pool.</span></span> <span data-ttu-id="bdfc6-117">CAC 設定會自動傳播至您網路中的所有 Lync Server 前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-117">CAC settings are automatically propagated to all Lync Server Front End Servers in your network.</span></span>

<span data-ttu-id="bdfc6-118">針對由於 CAC 原則而失敗的呼叫，請依照下列步驟重新路由呼叫的優先順序順序如下：</span><span class="sxs-lookup"><span data-stu-id="bdfc6-118">For calls that fail because of CAC policies, the order of precedence for rerouting the call is as follows:</span></span>

1.  <span data-ttu-id="bdfc6-119">互聯</span><span class="sxs-lookup"><span data-stu-id="bdfc6-119">Internet</span></span>

2.  <span data-ttu-id="bdfc6-120">PSTN</span><span class="sxs-lookup"><span data-stu-id="bdfc6-120">PSTN</span></span>

3.  <span data-ttu-id="bdfc6-121">語音信箱</span><span class="sxs-lookup"><span data-stu-id="bdfc6-121">Voice mail</span></span>

<span data-ttu-id="bdfc6-122">通話詳細資料錄製（CDR）可捕獲重新路由至 PSTN 或語音信箱之通話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-122">Call detail recording (CDR) captures information about calls that are rerouted to the PSTN or to voice mail.</span></span> <span data-ttu-id="bdfc6-123">CDR 不會捕獲重新路由至網際網路之通話的相關資訊，因為網際網路被視為替換路徑，而不是次要選項。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-123">CDR does not capture information about calls that are rerouted to the Internet, because the Internet is treated as an alternate path rather than a secondary option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bdfc6-124">由於頻寬限制，語音信箱的存款不會遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-124">Voice mail deposits will not be denied because of bandwidth constraints.</span></span>



</div>

<span data-ttu-id="bdfc6-125">頻寬原則服務會以逗號分隔值（CSV）格式產生兩種類型的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-125">The Bandwidth Policy Service generates two types of log files in comma separated values (CSV) format.</span></span> <span data-ttu-id="bdfc6-126">當頻寬要求遭到拒絕時，**檢查失敗**記錄檔案會捕獲資訊。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-126">The **check failures** log file captures information when bandwidth requests are denied.</span></span> <span data-ttu-id="bdfc6-127">**連結利用率**記錄檔案會捕獲網路拓撲及 WAN 連結頻寬利用率的快照。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-127">The **link utilization** log file captures a snapshot of the network topology and the WAN link bandwidth utilization.</span></span> <span data-ttu-id="bdfc6-128">這兩個記錄檔都能根據利用率，協助您微調您的 CAC 原則。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-128">Both of these log files can assist you in fine-tuning your CAC policies based on utilization.</span></span>

<div>

## <a name="call-admission-control-considerations"></a><span data-ttu-id="bdfc6-129">通話許可控制考慮</span><span class="sxs-lookup"><span data-stu-id="bdfc6-129">Call Admission Control Considerations</span></span>

<span data-ttu-id="bdfc6-130">系統管理員選取將頻寬原則服務安裝在中央網站中設定的第一個池上。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-130">The administrator selects to install the Bandwidth Policy Service on the first pool configured in the central site.</span></span> <span data-ttu-id="bdfc6-131">由於每個網路區域都有一個中心網站，每個網路區域只有一個頻寬原則服務，可管理該區域的頻寬原則、其關聯的網站，以及這些網站的連結。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-131">Since there is a single central site per network region, there is only one Bandwidth Policy Service per network region, which manages bandwidth policy for that region, its associated sites and the links to those sites.</span></span> <span data-ttu-id="bdfc6-132">頻寬原則服務是作為前端伺服器的一部分執行，因此在該池中內建了高可用性。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-132">The Bandwidth Policy Service runs as part of the Front End Servers, and therefore high availability is built-in within that pool.</span></span> <span data-ttu-id="bdfc6-133">每個前端伺服器上執行的頻寬原則服務會每隔15秒進行一次同步處理。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-133">The Bandwidth Policy Service running on each Front End Server synchronizes every 15 seconds.</span></span> <span data-ttu-id="bdfc6-134">如果前端池失敗，則不會再針對該網站強制執行 CAC 原則，除非是前端池為止，因而頻寬原則服務再次成為正常運作。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-134">If the Front End pool fails, CAC policies are no longer enforced for that site until the Front End pool and consequently the Bandwidth Policy Service becomes operational again.</span></span> <span data-ttu-id="bdfc6-135">這表示所有的呼叫都會在頻寬原則服務不在服務期間完成。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-135">This implies that all calls will go through for the duration the Bandwidth Policy Service is out of service.</span></span> <span data-ttu-id="bdfc6-136">因此，您在此期間可能會有頻寬過度訂閱給您的連結</span><span class="sxs-lookup"><span data-stu-id="bdfc6-136">Therefore there is the possibility of bandwidth oversubscription of your links during this period</span></span>

<span data-ttu-id="bdfc6-137">頻寬原則服務可在前端池中提供高可用性;不過，它不會提供跨前端池的冗余。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-137">The Bandwidth Policy Service provides high availability within a Front End pool; however, it does not provide redundancy across Front End pools.</span></span> <span data-ttu-id="bdfc6-138">頻寬原則服務無法從一個前端池轉移到另一個。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-138">The Bandwidth Policy Service cannot failover from one Front End pool to another.</span></span> <span data-ttu-id="bdfc6-139">一旦已還原對前端池的服務之後，就會繼續執行頻寬原則服務，並再次強制執行頻寬原則檢查。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-139">Once service to the Front End pool is restored, the Bandwidth Policy Service is resumed and can enforce bandwidth policy checks again.</span></span>

<div>

## <a name="network-considerations"></a><span data-ttu-id="bdfc6-140">網路考慮</span><span class="sxs-lookup"><span data-stu-id="bdfc6-140">Network Considerations</span></span>

<span data-ttu-id="bdfc6-141">雖然 Lync Server 2013 中的頻寬原則服務強制執行音訊與視頻的頻寬限制，但在網路路由器（第2層和第3層）不會強制執行此限制。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-141">Although bandwidth restriction for audio and video is enforced by the Bandwidth Policy Service in Lync Server 2013, this restriction is not enforced at the network router (layer 2 and 3).</span></span> <span data-ttu-id="bdfc6-142">Lync Server 2010 CAC 無法防止資料應用程式（例如，在 WAN 連結上佔用整個網路頻寬），包括您的 CAC 原則所保留的音訊和視頻頻寬。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-142">Lync Server 2010 CAC cannot prevent a data application, for example, from consuming the entire network bandwidth on a WAN link, including the bandwidth that is reserved for audio and video by your CAC policy.</span></span> <span data-ttu-id="bdfc6-143">若要保護您網路上的必要頻寬，您可以部署服務品質（QoS）通訊協定（例如差異服務（DiffServ））。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-143">To protect the necessary bandwidth on your network, you can deploy a Quality of Service (QoS) protocol such as Differentiated Services (DiffServ).</span></span> <span data-ttu-id="bdfc6-144">因此，最佳做法是將您定義的 CAC 頻寬原則與您可能部署的任何 QoS 設定進行協調。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-144">Therefore, a best practice is to coordinate the CAC bandwidth policies you define with any QoS settings that you might deploy.</span></span>

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a><span data-ttu-id="bdfc6-145">VPN 上的媒體與信號路徑</span><span class="sxs-lookup"><span data-stu-id="bdfc6-145">Media and Signaling Paths over VPN</span></span>

<span data-ttu-id="bdfc6-146">如果您的企業透過 VPN 支援媒體，請確定媒體資料流程和傳送信號資料流程都透過 VPN，或者兩者都是透過網際網路路由。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-146">If your enterprise supports media through VPN, ensure that either both the media stream and the signaling stream go through the VPN or both are routed through the internet.</span></span> <span data-ttu-id="bdfc6-147">根據預設，媒體和傳送信號資料流程會透過 VPN 隧道進行。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-147">By default, the media and signaling streams go through the VPN tunnel.</span></span>

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a><span data-ttu-id="bdfc6-148">呼叫外部使用者的許可控制</span><span class="sxs-lookup"><span data-stu-id="bdfc6-148">Call Admission Control of Outside Users</span></span>

<span data-ttu-id="bdfc6-149">對於網路流量流經網際網路的遠端使用者，不會強制執行呼叫許可控制。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-149">Call admission control is not enforced for remote users where the network traffic flows through the Internet.</span></span> <span data-ttu-id="bdfc6-150">因為媒體流量是穿越網際網路，而不是由 Lync Server 管理，所以無法套用 CAC。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-150">Because the media traffic is traversing the Internet, which is not managed by Lync Server, CAC cannot be applied.</span></span> <span data-ttu-id="bdfc6-151">不過，您可以在通話中的部分，在整個商業網路中執行 CAC 檢查。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-151">CAC checks will be performed, however, on the portion of the call that flows through the enterprise network.</span></span>

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a><span data-ttu-id="bdfc6-152">呼叫接入控制 PSTN 連接</span><span class="sxs-lookup"><span data-stu-id="bdfc6-152">Call Admission Control of PSTN Connections</span></span>

<span data-ttu-id="bdfc6-153">無論是連接到 IP/PBX、PSTN 閘道或 SIP 幹線，都能在中繼伺服器上強制使用呼叫許可控制。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-153">Call admission control is enforceable on the Mediation Server regardless of whether it is connected to an IP/PBX, a PSTN gateway, or a SIP trunk.</span></span> <span data-ttu-id="bdfc6-154">因為中繼伺服器是一個後端到後端的使用者代理程式（B2BUA），所以它會終止媒體。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-154">Because the Mediation Server is a back-to-back user agent (B2BUA), it terminates media.</span></span> <span data-ttu-id="bdfc6-155">它有兩個連接端：連線至 Lync Server 的一端，以及連線至 PSTN 閘道、IP/Pbx 或 SIP trunks 的閘道端。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-155">It has two connection sides: a side that is connected to Lync Server and a gateway side, which is connected to PSTN gateways, IP/PBXs, or SIP trunks.</span></span> <span data-ttu-id="bdfc6-156">如需 PSTN 連線的詳細資料，請參閱[在 Lync Server 2013 規劃 PSTN](lync-server-2013-planning-for-pstn-connectivity.md)連線。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-156">For details about PSTN connections, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).</span></span>

<span data-ttu-id="bdfc6-157">除非啟用 [媒體旁路]，否則在中繼伺服器的兩端都可以強制執行 CAC。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-157">CAC can be enforced on both sides of the Mediation Server unless media bypass is enabled.</span></span> <span data-ttu-id="bdfc6-158">如果已啟用媒體旁路，媒體流量就不會穿過中繼伺服器，而是直接在 Lync 用戶端和閘道之間流動。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-158">If media bypass is enabled, the media traffic doesn’t traverse the Mediation Server but instead flows directly between the Lync client and the gateway.</span></span> <span data-ttu-id="bdfc6-159">在此情況下，不需要 CAC。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-159">In this case, CAC is not needed.</span></span> <span data-ttu-id="bdfc6-160">如需詳細資訊，請參閱[在 Lync Server 2013 中規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-160">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).</span></span>

<span data-ttu-id="bdfc6-161">下圖說明如何啟用不使用媒體旁路的 PSTN 連線的 CAC。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-161">The following figure illustrates how CAC is enforced on PSTN connections with and without media bypass enabled.</span></span>

<span data-ttu-id="bdfc6-162">**在連接至 PSTN 時呼叫許可控制強制**</span><span class="sxs-lookup"><span data-stu-id="bdfc6-162">**Call admission control enforcement on connections to the PSTN**</span></span>

<span data-ttu-id="bdfc6-163">![強制語音 CAC 媒體旁路連線](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "強制語音 CAC 媒體旁路連線")</span><span class="sxs-lookup"><span data-stu-id="bdfc6-163">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a><span data-ttu-id="bdfc6-164">與舊版 Office 通訊伺服器的通話許可控制的相容性</span><span class="sxs-lookup"><span data-stu-id="bdfc6-164">Compatibility of Call Admission Control with Earlier Versions of Office Communications Server</span></span>

<span data-ttu-id="bdfc6-165">只能在已啟用 Lync Server 2010 及更新版本的端點上啟用呼叫許可控制。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-165">Call admission control can be enabled only on endpoints that are enabled for Lync Server 2010 and later.</span></span>

<span data-ttu-id="bdfc6-166">在執行 Office Communicator 2007 R2 或更舊版本的端點上無法啟用呼叫許可控制。</span><span class="sxs-lookup"><span data-stu-id="bdfc6-166">Call admission control cannot be enabled on endpoints running Office Communicator 2007 R2 or earlier.</span></span>

<span data-ttu-id="bdfc6-167">**在不同的 Lync Server 版本上應用 CAC**</span><span class="sxs-lookup"><span data-stu-id="bdfc6-167">**Application of CAC on different Lync Server versions**</span></span>

<span data-ttu-id="bdfc6-168">![語音 CAC 版本比較圖表](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "語音 CAC 版本比較圖表")</span><span class="sxs-lookup"><span data-stu-id="bdfc6-168">![Voice CAC Version Comparison diagram](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Voice CAC Version Comparison diagram")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

