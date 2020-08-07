---
title: 在 Microsoft 團隊中實現服務品質
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: 瞭解如何準備貴組織的網路，以瞭解 Microsoft 團隊中的服務品質 (QoS) 。
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
ms.openlocfilehash: 6a83a18810268d3eb8317eb541f7eb06ff812c9c
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582090"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a><span data-ttu-id="aa0a4-103">在 Microsoft 團隊中實現服務品質 (QoS) </span><span class="sxs-lookup"><span data-stu-id="aa0a4-103">Implement Quality of Service (QoS) in Microsoft Teams</span></span>

<span data-ttu-id="aa0a4-104">Microsoft 團隊中的服務品質 (QoS) 可讓您在不太敏感的通信量（例如下載新的應用程式，也就是下載新的 app 而不是大型 (交易的情況下），允許即時網路流量對網路延遲保密 (例如，語音或影片資料流程) 為「分行」。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-104">Quality of Service (QoS) in Microsoft Teams is a way to allow real-time network traffic that is sensitive to network delays (for example, voice or video streams) to "cut in line" in front of traffic that is less sensitive (like downloading a new app, where an extra second to download isn't a big deal).</span></span> <span data-ttu-id="aa0a4-105">QoS 會在即時資料流中識別並標示所有的資料包， (使用 Windows 群組原則物件，以及稱為埠式存取控制清單的路由功能，如以下所) 示，我們可以協助您的網路提供語音、影片和螢幕共用來串流網絡頻寬的專用部分。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-105">QoS identifies and marks all packets in real-time streams (using Windows Group Policy Objects and a routing feature called Port-based Access Control Lists, more about those is below) which then helps your network to give voice, video, and screen share streams a dedicated portion of network bandwidth.</span></span>

<span data-ttu-id="aa0a4-106">如果您要支援大量的使用者，而且他們遇到下列任何問題，您可能需要實施 QoS。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-106">If you're supporting a large group of users and they're experiencing any of the problems described below, you probably need to implement QoS.</span></span> <span data-ttu-id="aa0a4-107">只有少數使用者的小型企業可能不需要 QoS，但甚至應該有説明。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-107">A small business with few users may not need QoS, but even there it should be helpful.</span></span>

<span data-ttu-id="aa0a4-108">若沒有某種形式的 QoS，您可能會在語音和影片中看到下列品質問題：</span><span class="sxs-lookup"><span data-stu-id="aa0a4-108">Without some form of QoS, you might see the following quality issues in voice and video:</span></span>

- <span data-ttu-id="aa0a4-109">抖動：以不同速度傳入的媒體資料包，可能會導致通話中遺失文字或音節</span><span class="sxs-lookup"><span data-stu-id="aa0a4-109">Jitter – media packets arriving at different rates, which can result in missing words or syllables in calls</span></span>
- <span data-ttu-id="aa0a4-110">資料包遺失-丟棄的資料包，也可能導致語音品質降低且難以理解語音</span><span class="sxs-lookup"><span data-stu-id="aa0a4-110">Packet loss – packets dropped, which can also result in lower voice quality and hard to understand speech</span></span>
- <span data-ttu-id="aa0a4-111">延遲的往返時間 (RTT) -媒體資料包在到達其目的地時需要花很長的時間，這會導致交談中的兩個參與方產生明顯的延遲，讓其他人互相交談</span><span class="sxs-lookup"><span data-stu-id="aa0a4-111">Delayed round trip time (RTT) – media packets taking a long time to reach their destinations, which results in noticeable delays between two parties in a conversation, causing people to talk over each other</span></span>

<span data-ttu-id="aa0a4-112">解決這些問題最簡單的方法，就是在內部與網際網路之間增加資料連線的大小。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-112">The least complex way to address these issues is to increase the size of the data connections, both internally and out to the internet.</span></span> <span data-ttu-id="aa0a4-113">由於這通常是成本低的，因此 QoS 提供一種更有效率的方式來管理您所擁有的資源，而不是增加頻寬。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-113">Since that is often cost-prohibitive, QoS provides a way to more effectively manage the resources you have instead of adding bandwidth.</span></span> <span data-ttu-id="aa0a4-114">若要解決品質問題，建議您先使用 QoS，然後在必要時新增頻寬。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-114">To address quality issues, we recommend that you first use QoS, then add bandwidth only where necessary.</span></span>

<span data-ttu-id="aa0a4-115">為了讓 QoS 生效，您將在整個組織中套用一致的 QoS 設定，因為路徑中無法支援 QoS 優先順序的任何部分都可能會降低通話、影片和螢幕共用的品質。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-115">For QoS to be effective, you'll apply consistent QoS settings throughout your organization, because any part of the path that fails to support your QoS priorities can degrade the quality of calls, video, and screen sharing.</span></span> <span data-ttu-id="aa0a4-116">這包括將設定套用至所有使用者電腦或裝置、網路交換器、網際網路的路由器，以及團隊服務。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-116">This includes applying settings to all user PCs or devices, network switches, routers to the internet, and the Teams service.</span></span>

<span data-ttu-id="aa0a4-117">_圖1。組織的網路與 Microsoft 365 或 Office 365 服務之間的關聯性_</span><span class="sxs-lookup"><span data-stu-id="aa0a4-117">_Figure 1. The relationship between an organization's networks and Microsoft 365 or Office 365 services_</span></span>

<span data-ttu-id="aa0a4-118">![網路與服務之間的關聯性圖例](media/Qos-in-Teams-Image1.png "組織的網路與 Microsoft 365 或 Office 365 服務之間的關係：內部部署的網路和裝置會連線至互聯網絡，而這項功能又與 Microsoft 365 或 Office 365 雲端語音和音訊會議服務連線。")</span><span class="sxs-lookup"><span data-stu-id="aa0a4-118">![Illustration of the relationship between networks and services](media/Qos-in-Teams-Image1.png "The relationship between an organization's networks and Microsoft 365 or Office 365 services: on-premises network and devices connect with an interconnect network, which in turn connects with Microsoft 365 or Office 365 Cloud Voice and Audio Conferencing services.")</span></span>

## <a name="qos-implementation-checklist"></a><span data-ttu-id="aa0a4-119">QoS 實施檢查清單</span><span class="sxs-lookup"><span data-stu-id="aa0a4-119">QoS implementation checklist</span></span>

<span data-ttu-id="aa0a4-120">在高層中，請執行下列動作來實施 QoS：</span><span class="sxs-lookup"><span data-stu-id="aa0a4-120">At a high level, do the following to implement QoS:</span></span>

1. [<span data-ttu-id="aa0a4-121">請確定您的網路已就緒</span><span class="sxs-lookup"><span data-stu-id="aa0a4-121">Make sure your network is ready</span></span>](#make-sure-your-network-is-ready)

1. [<span data-ttu-id="aa0a4-122">選取 QoS 實現方法</span><span class="sxs-lookup"><span data-stu-id="aa0a4-122">Select a QoS implementation method</span></span>](#select-a-qos-implementation-method)

1. [<span data-ttu-id="aa0a4-123">選擇每種媒體類型的初始埠範圍</span><span class="sxs-lookup"><span data-stu-id="aa0a4-123">Choose initial port ranges for each media type</span></span>](#choose-initial-port-ranges-for-each-media-type)

1. <span data-ttu-id="aa0a4-124">實施 QoS 設定：</span><span class="sxs-lookup"><span data-stu-id="aa0a4-124">Implement QoS settings:</span></span>
   1. <span data-ttu-id="aa0a4-125">在使用 GPO 來[設定用戶端裝置埠範圍及標記](QoS-in-Teams-clients.md)的用戶端上</span><span class="sxs-lookup"><span data-stu-id="aa0a4-125">On clients using a GPO to [set client device port ranges and markings](QoS-in-Teams-clients.md)</span></span>
   2. <span data-ttu-id="aa0a4-126">在路由器上 (請參閱製造商說明文件) 或其他網路裝置。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-126">On routers (see the manufacturer documentation) or other network devices.</span></span> <span data-ttu-id="aa0a4-127">這可能包含以埠為基礎的 Acl，或只定義 QoS 佇列和 DSCP 標記，或是它們的全部。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-127">This may include port-based ACLs or simply defining the QoS queues and DSCP markings, or all of these.</span></span>

      > [!IMPORTANT]
      > <span data-ttu-id="aa0a4-128">我們建議您使用用戶端來源埠以及來源和目的地 IP 位址 "any" 來實現這些 QoS 原則。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-128">We recommend implementing these QoS policies using the client source ports and a source and destination IP address of “any.”</span></span> <span data-ttu-id="aa0a4-129">這會在內部網路上捕捉傳入和傳出媒體流量。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-129">This will catch both incoming and outgoing media traffic on the internal network.</span></span>  

   3. [<span data-ttu-id="aa0a4-130">設定您想要處理團隊會議媒體流量的方式</span><span class="sxs-lookup"><span data-stu-id="aa0a4-130">Set how you want to handle media traffic for Teams meetings</span></span>](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

5. <span data-ttu-id="aa0a4-131">分析網路上的小組流量，以[驗證您的 QoS 實現](#validate-your-qos-implementation)。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-131">[Validate your QoS implementation](#validate-your-qos-implementation) by analyzing Teams traffic on the network.</span></span>

<span data-ttu-id="aa0a4-132">當您準備好要實施 QoS 時，請牢記下列準則：</span><span class="sxs-lookup"><span data-stu-id="aa0a4-132">As you prepare to implement QoS, keep the following guidelines in mind:</span></span>

- <span data-ttu-id="aa0a4-133">最短的 Microsoft 365 路徑是最佳做法</span><span class="sxs-lookup"><span data-stu-id="aa0a4-133">The shortest path to Microsoft 365 is best</span></span>
- <span data-ttu-id="aa0a4-134">關閉埠只會導致品質下降</span><span class="sxs-lookup"><span data-stu-id="aa0a4-134">Closing ports will only lead to quality degradation</span></span>
- <span data-ttu-id="aa0a4-135">不建議在任何情況下（例如 proxy）中的任何障礙</span><span class="sxs-lookup"><span data-stu-id="aa0a4-135">Any obstacles in between, such as proxies, aren't recommended</span></span>
- <span data-ttu-id="aa0a4-136">限制跳躍數：</span><span class="sxs-lookup"><span data-stu-id="aa0a4-136">Limit the number of hops:</span></span>
  - <span data-ttu-id="aa0a4-137">用戶端到網路邊緣–3到5個躍點</span><span class="sxs-lookup"><span data-stu-id="aa0a4-137">Client to network edge – 3 to 5 hops</span></span>
  - <span data-ttu-id="aa0a4-138">ISP 至 Microsoft 網路邊緣–3個躍點</span><span class="sxs-lookup"><span data-stu-id="aa0a4-138">ISP to Microsoft network edge – 3 hops</span></span>
  - <span data-ttu-id="aa0a4-139">Microsoft 網路 edge 至最終目的地（不相關）</span><span class="sxs-lookup"><span data-stu-id="aa0a4-139">Microsoft network edge to final destination – irrelevant</span></span>

<span data-ttu-id="aa0a4-140">如需設定防火牆埠的相關資訊，請移至[Office 365 url 與 IP 範圍](office-365-urls-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-140">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>


## <a name="make-sure-your-network-is-ready"></a><span data-ttu-id="aa0a4-141">請確定您的網路已就緒</span><span class="sxs-lookup"><span data-stu-id="aa0a4-141">Make sure your network is ready</span></span>

<span data-ttu-id="aa0a4-142">如果您正在考慮執行 QoS，您應該已經決定您的頻寬需求與其他[網路需求](prepare-network.md)。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-142">If you're considering a QoS implementation, you should already have determined your bandwidth requirements and other [network requirements](prepare-network.md).</span></span> 
  
<span data-ttu-id="aa0a4-143">網路上的流量堵塞會大大影響媒體質量。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-143">Traffic congestion across a network will greatly impact media quality.</span></span> <span data-ttu-id="aa0a4-144">缺乏頻寬會導致效能下降，以及不佳的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-144">A lack of bandwidth leads to performance degradation and a poor user experience.</span></span> <span data-ttu-id="aa0a4-145">隨著團隊採用和使用量的增加，您可以使用 [報告]、[[每使用者通話分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)] 和 [[通話品質儀表板] (CQD) ](turning-on-and-using-call-quality-dashboard.md)來找出問題，然後使用 QoS 及選擇性頻寬增加進行調整。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-145">As Teams adoption and usage grows, use reporting, [per-user call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md), and [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to identify problems and then make adjustments using QoS and selective bandwidth additions.</span></span>

### <a name="vpn-considerations"></a><span data-ttu-id="aa0a4-146">VPN 考慮</span><span class="sxs-lookup"><span data-stu-id="aa0a4-146">VPN considerations</span></span>

<span data-ttu-id="aa0a4-147">QoS 只會在針對呼叫者之間的所有連結所執行時正常運作。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-147">QoS only works as expected when implemented on all links between callers.</span></span> <span data-ttu-id="aa0a4-148">如果您在內部網路上使用 QoS，且使用者從遠端位置登入，則您只能在內部、受管理的網路內進行優先順序設定。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-148">If you use QoS on an internal network and a user signs in from a remote location, you can only prioritize within your internal, managed network.</span></span> <span data-ttu-id="aa0a4-149">雖然遠端位置可以透過將虛擬私人網路絡 (VPN) 來接收受管理的連線，但 VPN 本身會增加資料包的負荷，並在即時流量中產生延遲。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-149">Although remote locations can receive a managed connection by implementing a virtual private network (VPN),  a VPN inherently adds packet overhead and creates delays in real-time traffic.</span></span> <span data-ttu-id="aa0a4-150">我們建議您避免透過 VPN 執行即時通訊流量。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-150">We  recommend that you avoid running real-time communications traffic over a VPN.</span></span>

<span data-ttu-id="aa0a4-151">在有跨洲之受管理連結的通用群組織中，我們強烈建議使用 QoS，因為這些連結的頻寬會與局域網的比較受到限制。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-151">In a global organization with managed links that span continents, we strongly recommend QoS because bandwidth for those links is limited in comparison to the LAN.</span></span>

## <a name="introduction-to-qos-queues"></a><span data-ttu-id="aa0a4-152">QoS 佇列簡介</span><span class="sxs-lookup"><span data-stu-id="aa0a4-152">Introduction to QoS queues</span></span>

<span data-ttu-id="aa0a4-153">若要提供 QoS，網路裝置必須能夠將流量分類，而且必須能夠區別語音或影片與其他網路流量。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-153">To provide QoS, network devices must have a way to classify traffic and must be able to distinguish voice or video from other network traffic.</span></span>

<span data-ttu-id="aa0a4-154">當網路流量進入路由器時，通信量會放入佇列中。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-154">When network traffic enters a router, the traffic is placed into a queue.</span></span> <span data-ttu-id="aa0a4-155">如果未設定 QoS 原則，則只有一個佇列，且所有資料都會以相同的優先順序先進行處理，即先完成。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-155">If a QoS policy isn't configured, there is only one queue, and all data is treated as first-in, first-out with the same priority.</span></span> <span data-ttu-id="aa0a4-156">這表示語音流量 (對延遲而言非常敏感，) 可能會停滯通信量，而延遲幾個額外的毫秒不會發生問題。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-156">That means voice traffic (which is very sensitive to delays) might get stuck behind traffic where a delay of a few extra milliseconds wouldn't be a problem.</span></span>

<span data-ttu-id="aa0a4-157">當您實現 QoS 時，您會使用數個擁塞管理功能中的其中一個來定義多個佇列， (例如 Cisco 的優先順序佇列與[類別式加權公平佇列 (CBWFQ) ](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641)) 和擁塞規避功能 ([WRED (](https://en.wikipedia.org/wiki/Weighted_random_early_detection)) 。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-157">When you implement QoS, you define multiple queues using one of several congestion management features (such as Cisco’s priority queuing and [Class-Based Weighted Fair Queueing (CBWFQ)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641)) and congestion avoidance features (such as [weighted random early detection (WRED)](https://en.wikipedia.org/wiki/Weighted_random_early_detection)).</span></span>

<span data-ttu-id="aa0a4-158">_圖2。QoS 佇列的範例_</span><span class="sxs-lookup"><span data-stu-id="aa0a4-158">_Figure 2. Examples of QoS queues_</span></span>

<span data-ttu-id="aa0a4-159">![QoS 佇列和頻寬劃分的圖例](media/Qos-in-Teams-Image2.png "可用的總頻寬在多個佇列中劃分，即音訊、影片和其他流量，這些都已獲指派不同的優先順序。")</span><span class="sxs-lookup"><span data-stu-id="aa0a4-159">![Illustration of QoS queues and bandwidth division](media/Qos-in-Teams-Image2.png "Total available bandwidth is divided among multiple queues—audio, video, and other traffic—that have been assigned different priorities.")</span></span>

<span data-ttu-id="aa0a4-160">簡單的類比是，QoS 會在您的資料網路中建立虛擬「carpool 車道」，讓某些類型的資料永不出現或很少遇到延遲。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-160">A simple analogy is that QoS creates virtual "carpool lanes" in your data network so some types of data never or rarely encounter a delay.</span></span> <span data-ttu-id="aa0a4-161">建立這些車道之後，您就可以調整其相對大小，以及更有效率地管理您擁有的連線頻寬，同時還能為貴組織的使用者供應商業級的體驗。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-161">Once you create those lanes, you can adjust their relative size and much more effectively manage the connection bandwidth you have, while still delivering business-grade experiences for your organization's users.</span></span>

## <a name="select-a-qos-implementation-method"></a><span data-ttu-id="aa0a4-162">選取 QoS 實現方法</span><span class="sxs-lookup"><span data-stu-id="aa0a4-162">Select a QoS implementation method</span></span>

<span data-ttu-id="aa0a4-163">您可以透過以埠為基礎的標記來實現 QoS，使用網路路由器上 (Acl) 的 [存取控制清單]。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-163">You could implement QoS via port-based tagging, using Access Control Lists (ACLs) on your network's routers.</span></span> <span data-ttu-id="aa0a4-164">以埠為基礎的標記是最可靠的方法，因為它能在混合式 Windows、Mac 和 Linux 環境中運作，且最容易實現。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-164">Port-based tagging is the most reliable method because it works in mixed Windows, Mac, and Linux environments and is the easiest to implement.</span></span> <span data-ttu-id="aa0a4-165">行動用戶端不會提供使用 DSCP 值來標示流量的機制，所以需要這個方法。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-165">Mobile clients don't provide a mechanism to mark traffic by using DSCP values, so they will require this method.</span></span>  

<span data-ttu-id="aa0a4-166">使用以埠為基礎的標記，您的網路路由器會檢查傳入的資料包，如果資料包是使用特定的埠或埠範圍來接收，則會將它識別為特定的媒體類型，並將它放在該類型的[DSCP](https://tools.ietf.org/html/rfc2474)佇列中，以便讓其他裝置辨識其流量類型，並在其佇列中賦予其優先順序。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-166">Using port-based tagging, your network's router examines an incoming packet, and if the packet arrived using a certain port or range of ports, it identifies it as a certain media type and puts it in the queue for that type, adding a predetermined [DSCP](https://tools.ietf.org/html/rfc2474) mark to the IP Packet header so other devices can recognize its traffic type and give it priority in their queue.</span></span>

<span data-ttu-id="aa0a4-167">雖然這可跨平臺使用，但它只會在 WAN edge 中標示流量， (並不完全在用戶端電腦) ，而且會產生管理的額外負荷。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-167">Although this works across platforms, it only marks traffic at the WAN edge (not all the way to the client machine) and creates management overhead.</span></span> <span data-ttu-id="aa0a4-168">您應該參閱路由器製造商提供的檔，以取得實現此方法的指示。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-168">You should refer to the documentation provided by the router manufacturer for instructions on implementing this method.</span></span>

### <a name="insert-dscp-markers"></a><span data-ttu-id="aa0a4-169">插入 DSCP 標記</span><span class="sxs-lookup"><span data-stu-id="aa0a4-169">Insert DSCP markers</span></span>

<span data-ttu-id="aa0a4-170">您也可以使用群組原則物件來實現 QoS， (GPO) 將用戶端裝置插入 IP 包頭中，以將 DSCP 標記插入到特定類型的通訊 (例如，語音) 。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-170">You could also implement QoS by using a Group Policy Object (GPO) to direct client devices to insert a DSCP marker in IP packet headers identifying it as particular type of traffic (for example, voice).</span></span> <span data-ttu-id="aa0a4-171">路由器和其他網路裝置可以設定為可辨識此情況，並將通信量放在個別、較高優先順序的佇列中。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-171">Routers and other network devices can be configured to recognize this and put the traffic in a separate, higher-priority queue.</span></span>

<span data-ttu-id="aa0a4-172">雖然這種情況完全有效，但只有加入網域的 Windows 用戶端才能運作。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-172">Although this scenario is entirely valid, it will only work for domain-joined Windows clients.</span></span> <span data-ttu-id="aa0a4-173">任何不是加入網域之 Windows 用戶端的裝置，都不會啟用 DSCP 標記。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-173">Any device that isn't a domain-joined Windows client won't be enabled for DSCP tagging.</span></span> <span data-ttu-id="aa0a4-174">用戶端（例如 Mac OS）有硬式編碼標籤，而且總是會標記流量。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-174">Clients such as Mac OS have hard-coded tags and will always tag traffic.</span></span>

<span data-ttu-id="aa0a4-175">在加號兩側，透過 GPO 控制 DSCP 標記，以確保所有加入網域的電腦都會收到相同的設定，而且只有系統管理員可以管理它們。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-175">On the plus side, controlling the DSCP marking via GPO ensures that all domain-joined computers receive the same settings and that only an administrator can manage them.</span></span> <span data-ttu-id="aa0a4-176">可使用 GPO 的用戶端會在原始裝置上進行標記，然後設定的網路裝置可以透過 DSCP 代碼辨識即時資料流，並提供適當的優先順序。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-176">Clients that can use GPO will be tagged on the originating device, and then configured network devices can recognize the real-time stream by the DSCP code and give it an appropriate priority.</span></span>

### <a name="best-practice"></a><span data-ttu-id="aa0a4-177">最佳做法</span><span class="sxs-lookup"><span data-stu-id="aa0a4-177">Best practice</span></span>

<span data-ttu-id="aa0a4-178">我們建議在路由器的端點和埠上使用 DSCP 標記組合（如果可能的話）。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-178">We recommend a combination of DSCP markings at the endpoint and port-based ACLs on routers, if possible.</span></span> <span data-ttu-id="aa0a4-179">使用群組原則物件來捕捉大部分的客戶，以及使用埠式 DSCP 標記，也可確保行動裝置、Mac 和其他用戶端仍會取得 QoS 治療 (至少部分) 。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-179">Using a Group Policy object to catch the majority of clients, and also using port-based DSCP tagging will ensure that mobile, Mac, and other clients will still get QoS treatment (at least partially).</span></span>

<span data-ttu-id="aa0a4-180">DSCP 標記可以是 likened 到郵票，指出郵政工人是傳送的緊急程度，以及如何將其排序以進行快速傳送。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-180">DSCP markings can be likened to postage stamps that indicate to postal workers how urgent the delivery is and how best to sort it for speedy delivery.</span></span> <span data-ttu-id="aa0a4-181">將您的網路設定為提供即時媒體資料流程的優先順序之後，遺失的資料包和後期資料包就應該會大大減少。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-181">Once you've configured your network to give priority to real-time media streams, lost packets and late packets should diminish greatly.</span></span>

<span data-ttu-id="aa0a4-182">一旦網路中的所有裝置都使用相同的分類、標記及優先順序，就可以變更指派給每個流量類型所使用之佇列的埠範圍的大小，以減少或避免延遲、刪除資料包和抖動。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-182">Once all devices in the network are using the same classifications, markings, and priorities, it's possible to reduce or eliminate delays, dropped packets, and jitter by changing the size of the port ranges assigned to the queues used for each traffic type.</span></span> <span data-ttu-id="aa0a4-183">從 [小組] 的角度來看，最重要的配置步驟是 [分類] 和 [資料包]，但針對端對端 QoS 是成功的，您也必須小心地將應用程式的設定與基礎網路設定進行對齊。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-183">From the Teams perspective, the most important configuration step is the classification and marking of packets, but for end-to-end QoS to be successful you also need to carefully align the application's configuration with the underlying network configuration.</span></span> <span data-ttu-id="aa0a4-184">當 QoS 完全實現之後，持續進行的管理就是根據貴組織的需求與實際用法調整指派給每個流量類型的埠範圍的問題。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-184">Once QoS is fully implemented, ongoing management is a question of adjusting the port ranges assigned to each traffic type based on your organization's needs and actual usage.</span></span>

## <a name="choose-initial-port-ranges-for-each-media-type"></a><span data-ttu-id="aa0a4-185">選擇每種媒體類型的初始埠範圍</span><span class="sxs-lookup"><span data-stu-id="aa0a4-185">Choose initial port ranges for each media type</span></span>

<span data-ttu-id="aa0a4-186">[DSCP] 值會告知根據 ACL 設定，要提供資料包或資料流程的優先順序設定，哪個優先順序是由用戶端或網路本身指派的。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-186">The DSCP value tells a correspondingly configured network what priority to give a packet or stream, whether the DSCP mark is assigned by clients or the network itself based on ACL settings.</span></span> <span data-ttu-id="aa0a4-187">每個媒體工作負載都會取得自己獨特的 DSCP 值 (其他服務可能允許工作負荷共用 DSCP 標記、團隊不) ，以及每個媒體類型所使用的已定義和不同的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-187">Each media workload gets its own unique DSCP value (other services might allow workloads to share a DSCP marking, Teams does not) and a defined and separate port range used for each media type.</span></span> <span data-ttu-id="aa0a4-188">其他環境可能已有一個現成的 QoS 戰略，這將協助您判斷網路工作負載的優先順序。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-188">Other environments might have an existing QoS strategy in place, which will help you determine the priority of network workloads.</span></span>

<span data-ttu-id="aa0a4-189">不同即時資料流工作負載的埠範圍相對大小，會設定專用於該工作負載的總可用頻寬比例。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-189">The relative size of the port ranges for different real-time streaming workloads sets the proportion of the total available bandwidth dedicated to that workload.</span></span> <span data-ttu-id="aa0a4-190">若要回到我們先前的主要類比：使用「Air Mail」戳記的字母，可能會在一個小時內取得最接近的機場，而標示為「大量信箱」的小型封裝則可以在一天前，在一系列卡車上在飛機上出差前等候一天。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-190">To return to our earlier postal analogy: a letter with an "Air Mail" stamp might get taken within an hour to the nearest airport, while a small package marked "Bulk Mail" mark can wait for a day before traveling over land on a series of trucks.</span></span>

<span data-ttu-id="aa0a4-191">_建議的初始埠範圍_</span><span class="sxs-lookup"><span data-stu-id="aa0a4-191">_Recommended initial port ranges_</span></span>

|<span data-ttu-id="aa0a4-192">媒體流量類型</span><span class="sxs-lookup"><span data-stu-id="aa0a4-192">Media traffic type</span></span>| <span data-ttu-id="aa0a4-193">用戶端來源連接埠範圍 </span><span class="sxs-lookup"><span data-stu-id="aa0a4-193">Client source port range</span></span> |<span data-ttu-id="aa0a4-194">通訊協定</span><span class="sxs-lookup"><span data-stu-id="aa0a4-194">Protocol</span></span>|<span data-ttu-id="aa0a4-195">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="aa0a4-195">DSCP value</span></span>|<span data-ttu-id="aa0a4-196">DSCP 類別</span><span class="sxs-lookup"><span data-stu-id="aa0a4-196">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="aa0a4-197">音訊</span><span class="sxs-lookup"><span data-stu-id="aa0a4-197">Audio</span></span>| <span data-ttu-id="aa0a4-198">50,000-50,019</span><span class="sxs-lookup"><span data-stu-id="aa0a4-198">50,000–50,019</span></span>|<span data-ttu-id="aa0a4-199">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="aa0a4-199">TCP/UDP</span></span>|<span data-ttu-id="aa0a4-200">46</span><span class="sxs-lookup"><span data-stu-id="aa0a4-200">46</span></span>|<span data-ttu-id="aa0a4-201">快速式轉送 (EF)</span><span class="sxs-lookup"><span data-stu-id="aa0a4-201">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="aa0a4-202">影片</span><span class="sxs-lookup"><span data-stu-id="aa0a4-202">Video</span></span>| <span data-ttu-id="aa0a4-203">50,020-50,039</span><span class="sxs-lookup"><span data-stu-id="aa0a4-203">50,020–50,039</span></span>|<span data-ttu-id="aa0a4-204">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="aa0a4-204">TCP/UDP</span></span>|<span data-ttu-id="aa0a4-205">34</span><span class="sxs-lookup"><span data-stu-id="aa0a4-205">34</span></span>|<span data-ttu-id="aa0a4-206">保證式轉送 (AF41)</span><span class="sxs-lookup"><span data-stu-id="aa0a4-206">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="aa0a4-207">應用程式/螢幕共用</span><span class="sxs-lookup"><span data-stu-id="aa0a4-207">Application/Screen Sharing</span></span>| <span data-ttu-id="aa0a4-208">50,040-50,059</span><span class="sxs-lookup"><span data-stu-id="aa0a4-208">50,040–50,059</span></span>|<span data-ttu-id="aa0a4-209">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="aa0a4-209">TCP/UDP</span></span>|<span data-ttu-id="aa0a4-210">滿</span><span class="sxs-lookup"><span data-stu-id="aa0a4-210">18</span></span>|<span data-ttu-id="aa0a4-211">保證式轉送 (AF21)</span><span class="sxs-lookup"><span data-stu-id="aa0a4-211">Assured Forwarding (AF21)</span></span>|
||||||

<span data-ttu-id="aa0a4-212">使用這些設定時，請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="aa0a4-212">Be aware of the following when you use these settings:</span></span>

- <span data-ttu-id="aa0a4-213">如果您打算在未來實施 ExpressRoute，但尚未實現 QoS，我們建議您遵循指導方針，讓 [DSCP 值] 與 [寄件者] 的 DSCP 值相同。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-213">If you plan to implement ExpressRoute in the future and haven't yet implemented QoS, we recommend that you follow the guidance so that DSCP values are the same from sender to receiver.</span></span>
- <span data-ttu-id="aa0a4-214">所有用戶端（包括行動用戶端和團隊裝置）都將使用這些埠範圍，並會受到您使用這些來源埠範圍所執行的任何 DSCP 原則所影響。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-214">All clients, including mobile clients and Teams devices, will use these port ranges and will be affected by any DSCP policy you implement that uses these source port ranges.</span></span> <span data-ttu-id="aa0a4-215">只有以瀏覽器為基礎的用戶端才能繼續使用動態埠， (也就是那些讓參與者使用其瀏覽器加入會議的用戶端) 。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-215">The only clients that will continue to use dynamic ports are the browser-based clients (that is, those clients that let participants join meetings by using their browsers).</span></span>
- <span data-ttu-id="aa0a4-216">雖然 Mac 用戶端使用相同的埠範圍，但它也會針對 (EF) 與 video (AF41) 使用硬式編碼值。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-216">Although the Mac client uses the same port ranges, it also uses hard-coded values for audio (EF) and video (AF41).</span></span> <span data-ttu-id="aa0a4-217">這些值無法設定。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-217">These values are not configurable.</span></span>
- <span data-ttu-id="aa0a4-218">如果您稍後需要調整埠範圍來改善使用者體驗，則埠範圍可能不會重疊，且應該彼此相鄰。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-218">If you later need to adjust the port ranges to improve user experience, the port ranges can not overlap and should be adjacent to each other.</span></span>

## <a name="migrate-qos-to-teams"></a><span data-ttu-id="aa0a4-219">將 QoS 遷移至團隊</span><span class="sxs-lookup"><span data-stu-id="aa0a4-219">Migrate QoS to Teams</span></span>

<span data-ttu-id="aa0a4-220">如果您先前已部署商務用 Skype Online，包括 QoS 標記和埠範圍，且現在正在部署團隊，則團隊會尊重現有的設定，並使用相同的埠範圍，並將其標記為商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-220">If you've previously deployed Skype for Business Online, including QoS tagging and port ranges, and are now deploying Teams, Teams will respect the existing configuration and will use the same port ranges and tagging as the Skype for Business client.</span></span> <span data-ttu-id="aa0a4-221">在大多數情況下，不需要進行額外的配置。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-221">In most cases, no additional configuration will be needed.</span></span>

> [!NOTE]
> <span data-ttu-id="aa0a4-222">如果您是透過群組原則使用應用程式名稱 QoS 標記，您必須將 Teams.exe 新增為應用程式名稱。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-222">If you're using Application Name QoS tagging via Group Policy, you must add Teams.exe as the application name.</span></span>


## <a name="managing-source-ports-in-the-teams-admin-center"></a><span data-ttu-id="aa0a4-223">管理團隊系統管理中心的來源埠</span><span class="sxs-lookup"><span data-stu-id="aa0a4-223">Managing source ports in the Teams admin center</span></span>

<span data-ttu-id="aa0a4-224">在團隊中，不同工作負載所使用的 QoS 來源埠應該積極管理，並視需要調整。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-224">In Teams, QoS source ports used by the different workloads should be actively managed, and adjusted as necessary.</span></span> <span data-ttu-id="aa0a4-225">參照表格在[每個媒體類型的 [初始埠範圍](#choose-initial-port-ranges-for-each-media-type)] 中，埠範圍都是可調整的，但 DSCP 標記無法進行設定。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-225">Referring to the table in [Choose initial port ranges for each media type](#choose-initial-port-ranges-for-each-media-type), the port ranges are adjustable, but the DSCP markings are not configurable.</span></span> <span data-ttu-id="aa0a4-226">一旦您實現這些設定之後，您可能會發現特定媒體類型需要多或較少的埠。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-226">Once you have implemented these settings, you may find that more or fewer ports are needed for a given media type.</span></span> <span data-ttu-id="aa0a4-227">[[每使用者通話分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)] 和 [[通話品質儀表板] (CQD) ](turning-on-and-using-call-quality-dashboard.md)應該用來決定在團隊實施之後調整埠範圍，以及定期視需要變更。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-227">[Per-user call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md) and [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) should be used in making a decision to adjust port ranges after Teams has been implemented, and periodically as needs change.</span></span>

> [!NOTE]
> <span data-ttu-id="aa0a4-228">如果您已經針對商務用 Skype Online 的來源埠範圍和 DSCP 標記設定了 QoS，則相同的設定會套用至小組，而且不需要進一步的用戶端或網路變更，不過您可能必須[將小組中所用的範圍](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)與針對商務用 Skype Online 所設定的範圍相符。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-228">If you've already configured QoS based on source port ranges and DSCP markings for Skype for Business Online, the same configuration will apply to Teams and no further client or network changes to the mapping will be required, though you may have to [set the ranges used in Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) to match what was configured for Skype for Business Online.</span></span>

<span data-ttu-id="aa0a4-229">如果您先前已在內部部署部署商務用 Skype Server，您可能需要重新檢查您的 QoS 原則，並加以調整，以符合您已驗證的埠範圍設定，為小組提供高品質的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-229">If you’ve previously deployed Skype for Business Server on-premises, you may need to re-examine your QoS policies and adjust them to match port range settings you've verified provide a quality user experience for Teams.</span></span>

## <a name="validate-your-qos-implementation"></a><span data-ttu-id="aa0a4-230">驗證您的 QoS 實施</span><span class="sxs-lookup"><span data-stu-id="aa0a4-230">Validate your QoS implementation</span></span>

<span data-ttu-id="aa0a4-231">為了讓 QoS 生效，群群組原則物件所設定的 DSCP 值必須存在於呼叫的兩端。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-231">For QoS to be effective, the DSCP value set by the Group Policy object needs to be present at both ends of a call.</span></span> <span data-ttu-id="aa0a4-232">您可以透過分析團隊用戶端產生的流量，在小組工作負載流量透過網路移動時，確認 DSCP 值沒有變更或剝離。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-232">By analyzing the traffic generated by the Teams client, you can verify that the DSCP value isn’t changed or stripped out when the Teams workload traffic moves through the network.</span></span>

<span data-ttu-id="aa0a4-233">最好的是，您可以在網路出口點捕獲流量。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-233">Preferably, you capture traffic at the network egress point.</span></span> <span data-ttu-id="aa0a4-234">您可以在交換器或路由器上使用埠鏡像來協助解決這個情況。</span><span class="sxs-lookup"><span data-stu-id="aa0a4-234">You can use port mirroring on a switch or router to help with this.</span></span>


## <a name="related-topics"></a><span data-ttu-id="aa0a4-235">相關主題</span><span class="sxs-lookup"><span data-stu-id="aa0a4-235">Related topics</span></span>

[<span data-ttu-id="aa0a4-236">影片：網路規劃</span><span class="sxs-lookup"><span data-stu-id="aa0a4-236">Video: Network Planning</span></span>](https://aka.ms/teams-networking)

[<span data-ttu-id="aa0a4-237">針對 Microsoft Teams 準備組織的網路</span><span class="sxs-lookup"><span data-stu-id="aa0a4-237">Prepare your organization's network for Microsoft Teams</span></span>](prepare-network.md)

[<span data-ttu-id="aa0a4-238">在團隊用戶端中實施 QoS</span><span class="sxs-lookup"><span data-stu-id="aa0a4-238">Implement QoS in the Teams client</span></span>](QoS-in-Teams-clients.md)
