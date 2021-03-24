---
title: 在 Microsoft Teams 中執行服務品質
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: 瞭解如何在 Microsoft Teams 中準備貴組織的服務品質 (QoS) 網路。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.qos
- ms.teamsadmincenter.meetingsettings.network.qosmarkers
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87f3577d34df6d2b0665a45b60b441d29cd0265b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092611"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a><span data-ttu-id="8676d-103">在 Microsoft Teams 中 (QoS) 服務品質</span><span class="sxs-lookup"><span data-stu-id="8676d-103">Implement Quality of Service (QoS) in Microsoft Teams</span></span>

<span data-ttu-id="8676d-104">Microsoft Teams 中的服務品質 (QoS) 可讓對網路延遲敏感的即時網路流量 (例如語音或視音訊流) 在較不敏感的流量前面「一併切出」 (例如下載新應用程式，其中額外的第二秒下載不是一項大型交易) 。</span><span class="sxs-lookup"><span data-stu-id="8676d-104">Quality of Service (QoS) in Microsoft Teams allows real-time network traffic that's sensitive to network delays (for example, voice or video streams) to "cut in line" in front of traffic that's less sensitive (like downloading a new app, where an extra second to download isn't a large deal).</span></span> <span data-ttu-id="8676d-105">QoS 使用 Windows 群組原則物件和埠型存取控制清單來識別並標記即時資料流中的所有封包。</span><span class="sxs-lookup"><span data-stu-id="8676d-105">QoS uses Windows Group Policy Objects and Port-based Access Control Lists to identify and mark all packets in real-time streams.</span></span> <span data-ttu-id="8676d-106">這可協助您的網路提供語音、視視和螢幕分享的私人網路絡頻寬部分。</span><span class="sxs-lookup"><span data-stu-id="8676d-106">This helps your network to give voice, video, and screen share streams a dedicated portion of network bandwidth.</span></span>

<span data-ttu-id="8676d-107">如果您支援一大群使用者，他們遇到本文所述的任何問題，則您可能需要執行 QoS。</span><span class="sxs-lookup"><span data-stu-id="8676d-107">If you support a large group of users who are experiencing any of the problems described in this article, then you probably need to implement QoS.</span></span> <span data-ttu-id="8676d-108">使用者很少的小型企業可能不需要 QoS，但即使在那裡也很有説明。</span><span class="sxs-lookup"><span data-stu-id="8676d-108">A small business with few users might not need QoS, but even there it should be helpful.</span></span>

<span data-ttu-id="8676d-109">如果沒有某種形式的 QoS，您可能會在語音和視訊中看到下列品質問題：</span><span class="sxs-lookup"><span data-stu-id="8676d-109">Without some form of QoS, you might see the following quality issues in voice and video:</span></span>

- <span data-ttu-id="8676d-110">抖動 – 以不同費率抵達的媒體封包，可能會導致通話中缺少文字或音節</span><span class="sxs-lookup"><span data-stu-id="8676d-110">Jitter – media packets arriving at different rates, which can result in missing words or syllables in calls</span></span>
- <span data-ttu-id="8676d-111">封包遺失 – 封包遺失，這也會降低語音品質，且難以理解語音</span><span class="sxs-lookup"><span data-stu-id="8676d-111">Packet loss – packets dropped, which can also result in lower voice quality and hard to understand speech</span></span>
- <span data-ttu-id="8676d-112">RTT (RTT) 延遲的往返時間 – 媒體封包需要很長的時間到達目的地，這會造成交談中的雙方之間明顯延遲，並造成彼此互相交談</span><span class="sxs-lookup"><span data-stu-id="8676d-112">Delayed round-trip time (RTT) – media packets taking a long time to reach their destinations, which result in noticeable delays between two parties in a conversation and causes people to talk over each other</span></span>

<span data-ttu-id="8676d-113">若要解決這些問題，最不復雜的方法就是增加內部與網際網路之間的資料連線大小。</span><span class="sxs-lookup"><span data-stu-id="8676d-113">The least complex way to address these issues is to increase the size of the data connections, both internally and out to the internet.</span></span> <span data-ttu-id="8676d-114">由於這通常成本高，QoS 提供一種更有效地管理您擁有的資源的方式，而不是新增頻寬。</span><span class="sxs-lookup"><span data-stu-id="8676d-114">Since that is often cost-prohibitive, QoS provides a way to more effectively manage the resources you have instead of adding bandwidth.</span></span> <span data-ttu-id="8676d-115">若要解決品質問題，建議您先使用 QoS，然後只在必要時新增頻寬。</span><span class="sxs-lookup"><span data-stu-id="8676d-115">To address quality issues, we recommend that you first use QoS, then add bandwidth only where necessary.</span></span>

<span data-ttu-id="8676d-116">若要讓 QoS 生效，您必須在整個組織中採用一致的 QoS 設定。</span><span class="sxs-lookup"><span data-stu-id="8676d-116">For QoS to be effective, you must apply consistent QoS settings throughout your organization.</span></span> <span data-ttu-id="8676d-117">任何無法支援 QoS 優先順序的路徑部分，都會降低通話、視像和螢幕分享的品質。</span><span class="sxs-lookup"><span data-stu-id="8676d-117">Any part of the path that fails to support your QoS priorities can degrade the quality of calls, video, and screen sharing.</span></span> <span data-ttu-id="8676d-118">這包括將設定適用于所有使用者電腦或裝置、網路交換器、路由器至網際網路，以及 Teams 服務。</span><span class="sxs-lookup"><span data-stu-id="8676d-118">This includes applying settings to all user PCs or devices, network switches, routers to the internet, and the Teams service.</span></span>

<span data-ttu-id="8676d-119">_圖 1.組織網路與 Microsoft 365 或 Office 365 服務之間的關係_</span><span class="sxs-lookup"><span data-stu-id="8676d-119">_Figure 1. The relationship between an organization's networks and Microsoft 365 or Office 365 services_</span></span>

<span data-ttu-id="8676d-120">![網路與服務之間關係的圖例](media/Qos-in-Teams-Image1.png "組織網路與 Microsoft 365 或 Office 365 服務之間的關係：內部部署網路和裝置會與互連網路連接，而互連網路會與 Microsoft 365 或 Office 365 雲端語音和音訊會議服務連接。")</span><span class="sxs-lookup"><span data-stu-id="8676d-120">![Illustration of the relationship between networks and services](media/Qos-in-Teams-Image1.png "The relationship between an organization's networks and Microsoft 365 or Office 365 services: on-premises network and devices connect with an interconnect network, which in turn connects with Microsoft 365 or Office 365 Cloud Voice and Audio Conferencing services.")</span></span>

## <a name="qos-implementation-checklist"></a><span data-ttu-id="8676d-121">QoS 執行檢查清單</span><span class="sxs-lookup"><span data-stu-id="8676d-121">QoS implementation checklist</span></span>

<span data-ttu-id="8676d-122">在較高層級上，執行下列操作以執行 QoS：</span><span class="sxs-lookup"><span data-stu-id="8676d-122">At a high level, do the following to implement QoS:</span></span>

1. <span data-ttu-id="8676d-123">[請確定您的網路已準備就緒](#make-sure-your-network-is-ready)。</span><span class="sxs-lookup"><span data-stu-id="8676d-123">[Make sure your network is ready](#make-sure-your-network-is-ready).</span></span>

1. <span data-ttu-id="8676d-124">[選取 QoS 實現方法](#select-a-qos-implementation-method)。</span><span class="sxs-lookup"><span data-stu-id="8676d-124">[Select a QoS implementation method](#select-a-qos-implementation-method).</span></span>

1. <span data-ttu-id="8676d-125">[針對每個媒體類型選擇初始埠範圍](#choose-initial-port-ranges-for-each-media-type)。</span><span class="sxs-lookup"><span data-stu-id="8676d-125">[Choose initial port ranges for each media type](#choose-initial-port-ranges-for-each-media-type).</span></span>

1. <span data-ttu-id="8676d-126">實現 QoS 設定：</span><span class="sxs-lookup"><span data-stu-id="8676d-126">Implement QoS settings:</span></span>
   1. <span data-ttu-id="8676d-127">在用戶端使用群組原則物件 (GPO) 設定 [用戶端裝置埠範圍和標記](QoS-in-Teams-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="8676d-127">On clients using a Group Policy Object (GPO) to [set client device port ranges and markings](QoS-in-Teams-clients.md).</span></span>
   2. <span data-ttu-id="8676d-128">在路由器 (查看製造商檔) 或其他網路裝置。</span><span class="sxs-lookup"><span data-stu-id="8676d-128">On routers (see the manufacturer documentation) or other network devices.</span></span> <span data-ttu-id="8676d-129">這可能包括以埠為基礎的存取控制清單 (ACL) 或直接定義 QoS 佇列和 DSCP 標記，或所有這些標記。</span><span class="sxs-lookup"><span data-stu-id="8676d-129">This might include port-based Access Control Lists (ACLs) or simply defining the QoS queues and DSCP markings, or all of these.</span></span>

      > [!IMPORTANT]
      > <span data-ttu-id="8676d-130">我們建議您使用用戶端來源埠，以及 「任何」的來源與目的地 IP 位址來執行這些 QoS 策略。</span><span class="sxs-lookup"><span data-stu-id="8676d-130">We recommend implementing these QoS policies using the client source ports and a source and destination IP address of “any.”</span></span> <span data-ttu-id="8676d-131">這會在內部網路上同時捕獲傳入和傳出媒體流量。</span><span class="sxs-lookup"><span data-stu-id="8676d-131">This will catch both incoming and outgoing media traffic on the internal network.</span></span>  

   3. <span data-ttu-id="8676d-132">[設定您想要如何處理 Teams 會議的媒體流量](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)。</span><span class="sxs-lookup"><span data-stu-id="8676d-132">[Set how you want to handle media traffic for Teams meetings](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).</span></span>

5. <span data-ttu-id="8676d-133">[分析 Teams 網路上](#validate-your-qos-implementation) 流量，以驗證您的 QoS 實現。</span><span class="sxs-lookup"><span data-stu-id="8676d-133">[Validate your QoS implementation](#validate-your-qos-implementation) by analyzing Teams traffic on the network.</span></span>

<span data-ttu-id="8676d-134">當您準備執行 QoS 時，請記住下列指導方針：</span><span class="sxs-lookup"><span data-stu-id="8676d-134">As you prepare to implement QoS, keep the following guidelines in mind:</span></span>

- <span data-ttu-id="8676d-135">Microsoft 365 的最短路徑是最佳路徑。</span><span class="sxs-lookup"><span data-stu-id="8676d-135">The shortest path to Microsoft 365 is best.</span></span>
- <span data-ttu-id="8676d-136">關閉埠只會導致品質降低。</span><span class="sxs-lookup"><span data-stu-id="8676d-136">Closing ports will only lead to quality degradation.</span></span>
- <span data-ttu-id="8676d-137">不建議在兩者之間遇到任何障礙，例如代理。</span><span class="sxs-lookup"><span data-stu-id="8676d-137">Any obstacles in between, such as proxies, aren't recommended.</span></span>
- <span data-ttu-id="8676d-138">限制躍點數目：</span><span class="sxs-lookup"><span data-stu-id="8676d-138">Limit the number of hops:</span></span>
  - <span data-ttu-id="8676d-139">用戶端到網路邊緣 – 3 到 5 個躍點</span><span class="sxs-lookup"><span data-stu-id="8676d-139">Client to network edge – 3 to 5 hops</span></span>
  - <span data-ttu-id="8676d-140">ISP 到 Microsoft 網路邊緣 – 3 躍點</span><span class="sxs-lookup"><span data-stu-id="8676d-140">ISP to Microsoft network edge – 3 hops</span></span>
  - <span data-ttu-id="8676d-141">Microsoft 網路邊緣到最終目的地 – 不相關</span><span class="sxs-lookup"><span data-stu-id="8676d-141">Microsoft network edge to final destination – irrelevant</span></span>

<span data-ttu-id="8676d-142">若要瞭解防火牆埠的組組資訊，請前往 [Office 365 URL 和 IP 範圍](office-365-urls-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="8676d-142">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

## <a name="make-sure-your-network-is-ready"></a><span data-ttu-id="8676d-143">確定您的網路已準備就緒</span><span class="sxs-lookup"><span data-stu-id="8676d-143">Make sure your network is ready</span></span>

<span data-ttu-id="8676d-144">如果您考慮進行 QoS 的實現，您應該已經決定您的頻寬需求和其他 [網路需求](prepare-network.md)。</span><span class="sxs-lookup"><span data-stu-id="8676d-144">If you're considering a QoS implementation, you should already have determined your bandwidth requirements and other [network requirements](prepare-network.md).</span></span>
  
<span data-ttu-id="8676d-145">整個網路的流量塞塞會嚴重影響媒體質量。</span><span class="sxs-lookup"><span data-stu-id="8676d-145">Traffic congestion across a network will greatly impact media quality.</span></span> <span data-ttu-id="8676d-146">頻寬的缺乏會導致性能降低和使用者體驗不佳。</span><span class="sxs-lookup"><span data-stu-id="8676d-146">A lack of bandwidth leads to performance degradation and a poor user experience.</span></span> <span data-ttu-id="8676d-147">隨著 Teams 採用和使用方式的擴大，請使用[](use-call-analytics-to-troubleshoot-poor-call-quality.md)報告、每個使用者通話分析及通話品質儀表板[ (CQD) ](turning-on-and-using-call-quality-dashboard.md)來找出問題，然後使用 QoS 和選擇性頻寬新增功能進行調整。</span><span class="sxs-lookup"><span data-stu-id="8676d-147">As Teams adoption and usage grows, use reporting, [per-user call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md), and [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to identify problems and then make adjustments using QoS and selective bandwidth additions.</span></span>

### <a name="vpn-considerations"></a><span data-ttu-id="8676d-148">VPN 考慮</span><span class="sxs-lookup"><span data-stu-id="8676d-148">VPN considerations</span></span>

<span data-ttu-id="8676d-149">QoS 只有在對來電者之間的所有連結上執行時，才能如預期運作。</span><span class="sxs-lookup"><span data-stu-id="8676d-149">QoS only works as expected when implemented on all links between callers.</span></span> <span data-ttu-id="8676d-150">如果您在內部網路上使用 QoS，而且使用者從遠端位置登錄，則只能在內部受管理的網路中排列優先順序。</span><span class="sxs-lookup"><span data-stu-id="8676d-150">If you use QoS on an internal network and a user signs in from a remote location, you can only prioritize within your internal, managed network.</span></span> <span data-ttu-id="8676d-151">雖然遠端位置可以實獲虛擬私人網路絡 (VPN) ，以接收受管理的連接，但 VPN 本身會增加封包負荷，並造成即時流量的延遲。</span><span class="sxs-lookup"><span data-stu-id="8676d-151">Although remote locations can receive a managed connection by implementing a virtual private network (VPN),  a VPN inherently adds packet overhead and creates delays in real-time traffic.</span></span> <span data-ttu-id="8676d-152">建議您避免在 VPN 上即時通訊流量。</span><span class="sxs-lookup"><span data-stu-id="8676d-152">We  recommend that you avoid running real-time communications traffic over a VPN.</span></span>

<span data-ttu-id="8676d-153">在擁有跨洲受管理連結的通用群組織中，我們強烈建議 QoS，因為這些連結的頻寬與 LAN 比較有限。</span><span class="sxs-lookup"><span data-stu-id="8676d-153">In a global organization with managed links that span continents, we strongly recommend QoS because bandwidth for those links is limited in comparison to the LAN.</span></span>

## <a name="introduction-to-qos-queues"></a><span data-ttu-id="8676d-154">QoS 佇列簡介</span><span class="sxs-lookup"><span data-stu-id="8676d-154">Introduction to QoS queues</span></span>

<span data-ttu-id="8676d-155">若要提供 QoS，網路設備必須擁有流量分類的方法，而且必須能夠區別語音或視像與其他網路流量。</span><span class="sxs-lookup"><span data-stu-id="8676d-155">To provide QoS, network devices must have a way to classify traffic and must be able to distinguish voice or video from other network traffic.</span></span>

<span data-ttu-id="8676d-156">當網路流量進入路由器時，流量會置於佇列中。</span><span class="sxs-lookup"><span data-stu-id="8676d-156">When network traffic enters a router, the traffic is placed into a queue.</span></span> <span data-ttu-id="8676d-157">如果未配置 QoS 策略，則只有一個佇列，且所有資料會視為優先、優先處理，優先順序相同。</span><span class="sxs-lookup"><span data-stu-id="8676d-157">If a QoS policy isn't configured, there is only one queue, and all data is treated as first-in, first-out with the same priority.</span></span> <span data-ttu-id="8676d-158">這表示語音 (對於延遲非常) 可能會卡在流量後面，因為延遲幾毫秒不會是問題。</span><span class="sxs-lookup"><span data-stu-id="8676d-158">That means voice traffic (which is very sensitive to delays) might get stuck behind traffic where a delay of a few extra milliseconds wouldn't be a problem.</span></span>

<span data-ttu-id="8676d-159">當您實現 QoS 時，您可以使用多種擠塞管理功能之一來定義多個佇列，例如 Cisco 的優先順序佇列和以類別為基礎的加權公平佇列[ (CBWFQ) ](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641)以及避免擠塞的功能，例如加權隨機早期偵測[ (WRED) 。](https://en.wikipedia.org/wiki/Weighted_random_early_detection)</span><span class="sxs-lookup"><span data-stu-id="8676d-159">When you implement QoS, you define multiple queues using one of several congestion management features, such as Cisco’s priority queuing and [Class-Based Weighted Fair Queueing (CBWFQ)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) and congestion avoidance features, such as [weighted random early detection (WRED)](https://en.wikipedia.org/wiki/Weighted_random_early_detection).</span></span>

<span data-ttu-id="8676d-160">_圖 2.QoS 佇列範例_</span><span class="sxs-lookup"><span data-stu-id="8676d-160">_Figure 2. Examples of QoS queues_</span></span>

<span data-ttu-id="8676d-161">![QoS 佇列和頻寬劃分的圖例](media/Qos-in-Teams-Image2.png "可用頻寬總計會分成多個已指派不同優先順序的佇列 ，包括音訊、視視和其他流量。")</span><span class="sxs-lookup"><span data-stu-id="8676d-161">![Illustration of QoS queues and bandwidth division](media/Qos-in-Teams-Image2.png "Total available bandwidth is divided among multiple queues—audio, video, and other traffic—that have been assigned different priorities.")</span></span>

<span data-ttu-id="8676d-162">一個簡單的類比是，QoS 會建立資料網路中虛擬的「拼車道」，讓某些類型的資料永遠不會或很少遇到延遲。</span><span class="sxs-lookup"><span data-stu-id="8676d-162">A simple analogy is that QoS creates virtual "carpool lanes" in your data network so some types of data never or rarely encounter a delay.</span></span> <span data-ttu-id="8676d-163">建立這些通路後，您可以調整其相對大小，並更有效地管理您擁有的連接頻寬，同時仍為貴組織的使用者供應商務級體驗。</span><span class="sxs-lookup"><span data-stu-id="8676d-163">Once you create those lanes, you can adjust their relative size and much more effectively manage the connection bandwidth you have, while still delivering business-grade experiences for your organization's users.</span></span>

## <a name="select-a-qos-implementation-method"></a><span data-ttu-id="8676d-164">選取 QoS 實現方法</span><span class="sxs-lookup"><span data-stu-id="8676d-164">Select a QoS implementation method</span></span>

<span data-ttu-id="8676d-165">您可以使用 Access Control Lists (在您的網路路由器上) ACL，透過埠標記來實現 QoS。</span><span class="sxs-lookup"><span data-stu-id="8676d-165">You could implement QoS via port-based tagging, using Access Control Lists (ACLs) on your network's routers.</span></span> <span data-ttu-id="8676d-166">埠型標記是最可靠的方法，因為它適用于混合式 Windows、Mac 和 Linux 環境，而且最容易實現。</span><span class="sxs-lookup"><span data-stu-id="8676d-166">Port-based tagging is the most reliable method because it works in mixed Windows, Mac, and Linux environments and is the easiest to implement.</span></span> <span data-ttu-id="8676d-167">行動用戶端不會提供使用 DSCP 值來標記流量的機制，因此需要使用此方法。</span><span class="sxs-lookup"><span data-stu-id="8676d-167">Mobile clients don't provide a mechanism to mark traffic by using DSCP values, so they'll require this method.</span></span>  

<span data-ttu-id="8676d-168">使用埠標記，您的網路路由器會檢查傳入的封包，如果封包是使用特定埠或埠範圍抵達，它會將其識別為特定媒體類型，並置於該類型的佇列中，在 IP 封包標頭中新增預先確定 [DSCP](https://tools.ietf.org/html/rfc2474) 標記，讓其他裝置能夠識別其流量類型，並在其佇列中給予優先順序。</span><span class="sxs-lookup"><span data-stu-id="8676d-168">Using port-based tagging, your network's router examines an incoming packet, and if the packet arrived using a certain port or range of ports, it identifies it as a certain media type and puts it in the queue for that type, adding a predetermined [DSCP](https://tools.ietf.org/html/rfc2474) mark to the IP Packet header so other devices can recognize its traffic type and give it priority in their queue.</span></span>

<span data-ttu-id="8676d-169">雖然埠標記可跨平臺運作，但只會標記 WAN 邊緣的流量 (無法一路標記到用戶端電腦) 造成管理負荷。</span><span class="sxs-lookup"><span data-stu-id="8676d-169">Although port-based tagging works across platforms, it only marks traffic at the WAN edge (not all the way to the client machine) and creates management overhead.</span></span> <span data-ttu-id="8676d-170">請參閱路由器製造商提供的檔，以參閱如何執行這個方法的指示。</span><span class="sxs-lookup"><span data-stu-id="8676d-170">Refer to the documentation provided by the router manufacturer for instructions on implementing this method.</span></span>

### <a name="insert-dscp-markers"></a><span data-ttu-id="8676d-171">插入 DSCP 標記</span><span class="sxs-lookup"><span data-stu-id="8676d-171">Insert DSCP markers</span></span>

<span data-ttu-id="8676d-172">您也可以使用群組原則物件 (GPO) 來引導用戶端裝置在 IP 封包標頭中插入 DSCP 標記，以將其識別為特定流量類型 (例如語音) 來實現 QoS。</span><span class="sxs-lookup"><span data-stu-id="8676d-172">You could also implement QoS by using a Group Policy Object (GPO) to direct client devices to insert a DSCP marker in IP packet headers identifying it as particular type of traffic (for example, voice).</span></span> <span data-ttu-id="8676d-173">路由器和其他網路裝置可以進行配置，以識別這一點，並將流量放在另一個優先順序較高的佇列中。</span><span class="sxs-lookup"><span data-stu-id="8676d-173">Routers and other network devices can be configured to recognize this and put the traffic in a separate, higher-priority queue.</span></span>

<span data-ttu-id="8676d-174">雖然此案例完全有效，但僅適用于已加入網域的 Windows 用戶端。</span><span class="sxs-lookup"><span data-stu-id="8676d-174">Although this scenario is entirely valid, it will only work for domain-joined Windows clients.</span></span> <span data-ttu-id="8676d-175">任何未加入網域的 Windows 用戶端的裝置將不會啟用 DSCP 標記。</span><span class="sxs-lookup"><span data-stu-id="8676d-175">Any device that isn't a domain-joined Windows client won't be enabled for DSCP tagging.</span></span> <span data-ttu-id="8676d-176">其他用戶端 ，例如執行 macOS 的用戶端，都有硬式編碼標記，而且一定會標記流量。</span><span class="sxs-lookup"><span data-stu-id="8676d-176">Other clients, such as those running macOS, have hard-coded tags and will always tag traffic.</span></span>

<span data-ttu-id="8676d-177">在加號側，透過 GPO 控制 DSCP 標記可確保所有加入網域的電腦都收到相同的設定，而且只有系統管理員可以管理這些設定。</span><span class="sxs-lookup"><span data-stu-id="8676d-177">On the plus side, controlling the DSCP marking via GPO ensures that all domain-joined computers receive the same settings and that only an administrator can manage them.</span></span> <span data-ttu-id="8676d-178">可以使用 GPO 的用戶端會標記在原始裝置上，然後所配置的網路設備可以使用 DSCP 程式碼來識別即時資料流，並給予適當的優先順序。</span><span class="sxs-lookup"><span data-stu-id="8676d-178">Clients that can use GPO will be tagged on the originating device, and then configured network devices can recognize the real-time stream by the DSCP code and give it an appropriate priority.</span></span>

### <a name="best-practice"></a><span data-ttu-id="8676d-179">最佳做法</span><span class="sxs-lookup"><span data-stu-id="8676d-179">Best practice</span></span>

<span data-ttu-id="8676d-180">如果可能的話，我們建議在端點和路由器上的埠型 ACL 組合 DSCP 標記。</span><span class="sxs-lookup"><span data-stu-id="8676d-180">We recommend a combination of DSCP markings at the endpoint and port-based ACLs on routers, if possible.</span></span> <span data-ttu-id="8676d-181">使用 GPO 來吸引大部分的用戶端，以及使用埠型 DSCP 標記，可確保行動、Mac 和其他用戶端仍獲得 QoS (至少部分) 。</span><span class="sxs-lookup"><span data-stu-id="8676d-181">Using a GPO to catch the majority of clients, and also using port-based DSCP tagging will ensure that mobile, Mac, and other clients will still get QoS treatment (at least partially).</span></span>

<span data-ttu-id="8676d-182">DSCP 標記可以比對為貼上戳記，向郵政業者指出遞送的緊急性，以及如何以最佳方式排序，以快速遞送。</span><span class="sxs-lookup"><span data-stu-id="8676d-182">DSCP markings can be likened to postage stamps that indicate to postal workers how urgent the delivery is and how best to sort it for speedy delivery.</span></span> <span data-ttu-id="8676d-183">將網路設定為優先處理即時媒體流之後，遺失的封包和延遲的封包應該會大幅減少。</span><span class="sxs-lookup"><span data-stu-id="8676d-183">Once you've configured your network to give priority to real-time media streams, lost packets and late packets should diminish greatly.</span></span>

<span data-ttu-id="8676d-184">一旦網路中所有的裝置都使用相同的分類、標記和優先順序，可以變更指派給每個流量類型之佇列的埠範圍大小，以減少或消除延遲、丟包和抖動。</span><span class="sxs-lookup"><span data-stu-id="8676d-184">Once all devices in the network are using the same classifications, markings, and priorities, it's possible to reduce or eliminate delays, dropped packets, and jitter by changing the size of the port ranges assigned to the queues used for each traffic type.</span></span> <span data-ttu-id="8676d-185">從 Teams 的觀點看，最重要的組組步驟是封包的分類和標記。</span><span class="sxs-lookup"><span data-stu-id="8676d-185">From the Teams perspective, the most important configuration step is the classification and marking of packets.</span></span> <span data-ttu-id="8676d-186">不過，若要讓端對端 QoS 成功，您也需要小心將應用程式的組式與基礎網路組組對齊。</span><span class="sxs-lookup"><span data-stu-id="8676d-186">However, for end-to-end QoS to be successful, you also need to carefully align the application's configuration with the underlying network configuration.</span></span> <span data-ttu-id="8676d-187">完全實作 QoS 之後，持續管理就是根據貴組織的需求和實際使用量調整指派給每個流量類型的埠範圍的問題。</span><span class="sxs-lookup"><span data-stu-id="8676d-187">Once QoS is fully implemented, ongoing management is a question of adjusting the port ranges assigned to each traffic type based on your organization's needs and actual usage.</span></span>

## <a name="choose-initial-port-ranges-for-each-media-type"></a><span data-ttu-id="8676d-188">針對每種媒體類型選擇初始埠範圍</span><span class="sxs-lookup"><span data-stu-id="8676d-188">Choose initial port ranges for each media type</span></span>

<span data-ttu-id="8676d-189">DSCP 值會告知對應設定的網路要給予封包或資料流程的優先順序，無論 DSCP 標記是由用戶端指派，還是網路本身根據 ACL 設定指派。</span><span class="sxs-lookup"><span data-stu-id="8676d-189">The DSCP value tells a correspondingly configured network what priority to give a packet or stream, whether the DSCP mark is assigned by clients or the network itself based on ACL settings.</span></span> <span data-ttu-id="8676d-190">每個媒體工作負載會獲得自己唯一的 DSCP 值 (其他服務可能會允許工作負載共用 DSCP 標記、Teams 不會) 以及每個媒體類型所使用的已定義和個別埠範圍。</span><span class="sxs-lookup"><span data-stu-id="8676d-190">Each media workload gets its own unique DSCP value (other services might allow workloads to share a DSCP marking, Teams doesn't) and a defined and separate port range used for each media type.</span></span> <span data-ttu-id="8676d-191">其他環境可能有現有的 QoS 策略，這可協助您判斷網路工作負載的優先順序。</span><span class="sxs-lookup"><span data-stu-id="8676d-191">Other environments might have an existing QoS strategy in place, which will help you determine the priority of network workloads.</span></span>

<span data-ttu-id="8676d-192">不同即時串流工作負載的埠範圍相對大小會設定該工作負載可用總頻寬的比例。</span><span class="sxs-lookup"><span data-stu-id="8676d-192">The relative size of the port ranges for different real-time streaming workloads sets the proportion of the total available bandwidth dedicated to that workload.</span></span> <span data-ttu-id="8676d-193">若要回到我們之前的郵政類比：一封有「Air Mail」戳記的信件，可能會于一小時內取到最近的機場，而標示為「大宗郵件」標記的小包裹可以等候一天，然後再在陸地上的一系列貨車上旅行。</span><span class="sxs-lookup"><span data-stu-id="8676d-193">To return to our earlier postal analogy: a letter with an "Air Mail" stamp might get taken within an hour to the nearest airport, while a small package marked "Bulk Mail" mark can wait for a day before traveling over land on a series of trucks.</span></span>

<span data-ttu-id="8676d-194">_建議的初始埠範圍_</span><span class="sxs-lookup"><span data-stu-id="8676d-194">_Recommended initial port ranges_</span></span>

|<span data-ttu-id="8676d-195">媒體流量類型</span><span class="sxs-lookup"><span data-stu-id="8676d-195">Media traffic type</span></span>| <span data-ttu-id="8676d-196">用戶端來源連接埠範圍 </span><span class="sxs-lookup"><span data-stu-id="8676d-196">Client source port range</span></span> |<span data-ttu-id="8676d-197">通訊協定</span><span class="sxs-lookup"><span data-stu-id="8676d-197">Protocol</span></span>|<span data-ttu-id="8676d-198">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="8676d-198">DSCP value</span></span>|<span data-ttu-id="8676d-199">DSCP 類別</span><span class="sxs-lookup"><span data-stu-id="8676d-199">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="8676d-200">音訊</span><span class="sxs-lookup"><span data-stu-id="8676d-200">Audio</span></span>| <span data-ttu-id="8676d-201">50,000-50,019</span><span class="sxs-lookup"><span data-stu-id="8676d-201">50,000–50,019</span></span>|<span data-ttu-id="8676d-202">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="8676d-202">TCP/UDP</span></span>|<span data-ttu-id="8676d-203">46</span><span class="sxs-lookup"><span data-stu-id="8676d-203">46</span></span>|<span data-ttu-id="8676d-204">快速式轉送 (EF)</span><span class="sxs-lookup"><span data-stu-id="8676d-204">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="8676d-205">影片</span><span class="sxs-lookup"><span data-stu-id="8676d-205">Video</span></span>| <span data-ttu-id="8676d-206">50,020-50,039</span><span class="sxs-lookup"><span data-stu-id="8676d-206">50,020–50,039</span></span>|<span data-ttu-id="8676d-207">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="8676d-207">TCP/UDP</span></span>|<span data-ttu-id="8676d-208">34</span><span class="sxs-lookup"><span data-stu-id="8676d-208">34</span></span>|<span data-ttu-id="8676d-209">保證式轉送 (AF41)</span><span class="sxs-lookup"><span data-stu-id="8676d-209">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="8676d-210">應用程式/螢幕共用</span><span class="sxs-lookup"><span data-stu-id="8676d-210">Application/Screen Sharing</span></span>| <span data-ttu-id="8676d-211">50,040-50,059</span><span class="sxs-lookup"><span data-stu-id="8676d-211">50,040–50,059</span></span>|<span data-ttu-id="8676d-212">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="8676d-212">TCP/UDP</span></span>|<span data-ttu-id="8676d-213">18</span><span class="sxs-lookup"><span data-stu-id="8676d-213">18</span></span>|<span data-ttu-id="8676d-214">保證式轉送 (AF21)</span><span class="sxs-lookup"><span data-stu-id="8676d-214">Assured Forwarding (AF21)</span></span>|
||||||

<span data-ttu-id="8676d-215">使用下列設定時，請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="8676d-215">Be aware of the following when you use these settings:</span></span>

- <span data-ttu-id="8676d-216">如果您打算在未來執行 ExpressRoute，但尚未實現 QoS，建議您遵循指引，讓 DSCP 值從寄件者到收件者之間相同。</span><span class="sxs-lookup"><span data-stu-id="8676d-216">If you plan to implement ExpressRoute in the future and haven't yet implemented QoS, we recommend that you follow the guidance so that DSCP values are the same from sender to receiver.</span></span>

- <span data-ttu-id="8676d-217">所有用戶端 ，包括行動用戶端和 Teams 裝置，都會使用這些埠範圍，並會受到您採用之使用這些來源埠範圍的任何 DSCP 政策影響。</span><span class="sxs-lookup"><span data-stu-id="8676d-217">All clients, including mobile clients and Teams devices, will use these port ranges and will be affected by any DSCP policy you implement that uses these source port ranges.</span></span> <span data-ttu-id="8676d-218">唯一繼續使用動態埠的用戶端是瀏覽器型用戶端， (允許參與者使用瀏覽器加入) 。</span><span class="sxs-lookup"><span data-stu-id="8676d-218">The only clients that will continue to use dynamic ports are the browser-based clients (clients that let participants join meetings by using their browsers).</span></span>

- <span data-ttu-id="8676d-219">雖然 Mac 用戶端使用相同的埠範圍，但它也會在 EF (和視) AF41 (使用硬) 。</span><span class="sxs-lookup"><span data-stu-id="8676d-219">Although the Mac client uses the same port ranges, it also uses hard-coded values for audio (EF) and video (AF41).</span></span> <span data-ttu-id="8676d-220">這些值無法進行配置。</span><span class="sxs-lookup"><span data-stu-id="8676d-220">These values aren't configurable.</span></span>

- <span data-ttu-id="8676d-221">如果您稍後需要調整埠範圍以改善使用者體驗，埠範圍不能重迭，而且應該彼此相鄰。</span><span class="sxs-lookup"><span data-stu-id="8676d-221">If you later need to adjust the port ranges to improve user experience, the port ranges can't overlap and should be adjacent to each other.</span></span>

## <a name="migrate-qos-to-teams"></a><span data-ttu-id="8676d-222">將 QoS 遷移到 Teams</span><span class="sxs-lookup"><span data-stu-id="8676d-222">Migrate QoS to Teams</span></span>

<span data-ttu-id="8676d-223">如果您先前已部署商務用 Skype Online，包括 QoS 標記和埠範圍，而且目前正在部署中。</span><span class="sxs-lookup"><span data-stu-id="8676d-223">If you've previously deployed Skype for Business Online, including QoS tagging and port ranges, and are now deploying.</span></span> <span data-ttu-id="8676d-224">Teams、Teams 會尊重現有的組配置，並使用與商務用 Skype 用戶端相同的埠範圍和標記。</span><span class="sxs-lookup"><span data-stu-id="8676d-224">Teams, Teams will respect the existing configuration and will use the same port ranges and tagging as the Skype for Business client.</span></span> <span data-ttu-id="8676d-225">在大多數情況下，不需要其他組組。</span><span class="sxs-lookup"><span data-stu-id="8676d-225">In most cases, no additional configuration will be needed.</span></span>

> [!NOTE]
> <span data-ttu-id="8676d-226">如果您透過群組原則使用應用程式名稱 QoS 標記，您必須將 Teams.exe新增為應用程式名稱。</span><span class="sxs-lookup"><span data-stu-id="8676d-226">If you're using Application Name QoS tagging via Group Policy, you must add Teams.exe as the application name.</span></span>

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a><span data-ttu-id="8676d-227">使用 PowerShell 在 Windows 上的 Teams 中實現 QoS</span><span class="sxs-lookup"><span data-stu-id="8676d-227">Implement QoS in Teams on Windows using PowerShell</span></span>

<span data-ttu-id="8676d-228">**設定音訊的 QoS**</span><span class="sxs-lookup"><span data-stu-id="8676d-228">**Set QoS for audio**</span></span>

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000 -IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

<span data-ttu-id="8676d-229">**設定影片的 QoS**</span><span class="sxs-lookup"><span data-stu-id="8676d-229">**Set QoS for video**</span></span>

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020 -IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

<span data-ttu-id="8676d-230">**設定 QoS 以共用**</span><span class="sxs-lookup"><span data-stu-id="8676d-230">**Set QoS for sharing**</span></span>

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040 -IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a><span data-ttu-id="8676d-231">在 Teams 系統管理中心管理來源埠</span><span class="sxs-lookup"><span data-stu-id="8676d-231">Managing source ports in the Teams admin center</span></span>

<span data-ttu-id="8676d-232">在 Teams 中，應主動管理不同工作負載所使用的 QoS 來源埠，並在必要時進行調整。</span><span class="sxs-lookup"><span data-stu-id="8676d-232">In Teams, QoS source ports used by the different workloads should be actively managed, and adjusted as necessary.</span></span> <span data-ttu-id="8676d-233">參照每個媒體類型 [選擇](#choose-initial-port-ranges-for-each-media-type)初始埠範圍中的資料表，埠範圍可調整，但 DSCP 標記無法進行配置。</span><span class="sxs-lookup"><span data-stu-id="8676d-233">Referring to the table in [Choose initial port ranges for each media type](#choose-initial-port-ranges-for-each-media-type), the port ranges are adjustable, but the DSCP markings aren't configurable.</span></span> <span data-ttu-id="8676d-234">一旦實現這些設定，您可能會發現指定媒體類型需要更多或更少的埠。</span><span class="sxs-lookup"><span data-stu-id="8676d-234">Once you have implemented these settings, you might find that more or fewer ports are needed for a given media type.</span></span> <span data-ttu-id="8676d-235">[每使用者](use-call-analytics-to-troubleshoot-poor-call-quality.md) 通話分析及通話品質儀表板 [ (CQD) ](turning-on-and-using-call-quality-dashboard.md) 應該用於決定在 Teams 已實施之後調整埠範圍，並視需求變更定期調整。</span><span class="sxs-lookup"><span data-stu-id="8676d-235">[Per-user call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md) and [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) should be used in making a decision to adjust port ranges after Teams has been implemented, and periodically as needs change.</span></span>

> [!NOTE]
> <span data-ttu-id="8676d-236">如果您已經根據來源埠範圍和商務用 Skype Online 的 DSCP 標記設定 QoS，相同的設定會套用至 Teams，而且不需要對映射進行其他用戶端或網路變更，不過您可能必須設定 [Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) 中使用的範圍，以符合商務用 Skype Online 的設定。</span><span class="sxs-lookup"><span data-stu-id="8676d-236">If you've already configured QoS based on source port ranges and DSCP markings for Skype for Business Online, the same configuration will apply to Teams and no further client or network changes to the mapping will be required, though you may have to [set the ranges used in Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) to match what was configured for Skype for Business Online.</span></span>

<span data-ttu-id="8676d-237">如果您先前在內部部署商務用 Skype Server，您可能需要重新檢查 QoS 策略。</span><span class="sxs-lookup"><span data-stu-id="8676d-237">If you’ve previously deployed Skype for Business Server on-premises, you might need to re-examine your QoS policies.</span></span> <span data-ttu-id="8676d-238">調整策略以符合您驗證的埠範圍設定，為 Teams 提供高品質的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="8676d-238">Adjust the policies to match port range settings you've verified provide a quality user experience for Teams.</span></span>

## <a name="validate-your-qos-implementation"></a><span data-ttu-id="8676d-239">驗證您的 QoS 實現</span><span class="sxs-lookup"><span data-stu-id="8676d-239">Validate your QoS implementation</span></span>

<span data-ttu-id="8676d-240">若要讓 QoS 生效，GPO 所設定 DSCP 值必須存在於通話的兩端。</span><span class="sxs-lookup"><span data-stu-id="8676d-240">For QoS to be effective, the DSCP value set by the GPO needs to be present at both ends of a call.</span></span> <span data-ttu-id="8676d-241">透過分析 Teams 用戶端產生的流量，您可以確認當 Teams 工作負載流量在網路中移動時，DSCP 值沒有變更或已去除。</span><span class="sxs-lookup"><span data-stu-id="8676d-241">By analyzing the traffic generated by the Teams client, you can verify that the DSCP value isn’t changed or stripped out when the Teams workload traffic moves through the network.</span></span>

<span data-ttu-id="8676d-242">最好是在網路出口點捕獲流量。</span><span class="sxs-lookup"><span data-stu-id="8676d-242">Preferably, you capture traffic at the network egress point.</span></span> <span data-ttu-id="8676d-243">您可以在交換器或路由器上使用埠鏡像來協助進行這項操作。</span><span class="sxs-lookup"><span data-stu-id="8676d-243">You can use port mirroring on a switch or router to help with this.</span></span>

## <a name="implement-qos-for-other-devices"></a><span data-ttu-id="8676d-244">針對其他裝置執行 QoS</span><span class="sxs-lookup"><span data-stu-id="8676d-244">Implement QoS for other devices</span></span>

<span data-ttu-id="8676d-245">請閱讀這些主題，以瞭解如何針對 Intune、Surface、iOS、Android 和 Mac 執行 QoS</span><span class="sxs-lookup"><span data-stu-id="8676d-245">Read these topics for information about implementing QoS for Intune, Surface, iOS, Android, and Mac</span></span>

- [<span data-ttu-id="8676d-246">Surface Hub 2S 的 QoS</span><span class="sxs-lookup"><span data-stu-id="8676d-246">QoS for Surface Hub 2S</span></span>](/surface-hub/surface-hub-2s-manage-intune)

- [<span data-ttu-id="8676d-247">Surface Hub 的 QoS</span><span class="sxs-lookup"><span data-stu-id="8676d-247">QoS for Surface Hub</span></span>](/surface-hub/surface-hub-qos)

- [<span data-ttu-id="8676d-248">iOS、Android 和 Mac 版 QoS</span><span class="sxs-lookup"><span data-stu-id="8676d-248">QoS for iOS, Android, and Mac</span></span>](./meeting-settings-in-teams.md?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a><span data-ttu-id="8676d-249">相關主題</span><span class="sxs-lookup"><span data-stu-id="8676d-249">Related topics</span></span>

- [<span data-ttu-id="8676d-250">影片：網路規劃</span><span class="sxs-lookup"><span data-stu-id="8676d-250">Video: Network Planning</span></span>](https://aka.ms/teams-networking)

- [<span data-ttu-id="8676d-251">針對 Microsoft Teams 準備組織的網路</span><span class="sxs-lookup"><span data-stu-id="8676d-251">Prepare your organization's network for Microsoft Teams</span></span>](prepare-network.md)

- [<span data-ttu-id="8676d-252">在 Teams 用戶端中實現 QoS</span><span class="sxs-lookup"><span data-stu-id="8676d-252">Implement QoS in the Teams client</span></span>](QoS-in-Teams-clients.md)