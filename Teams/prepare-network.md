---
title: 針對 Teams 準備組織的網路
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: 了解如何針對 Microsoft Teams 準備組織的網路，包括網路需求、網路最佳化和頻寬需求。
localization_priority: Priority
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: ff6959319a55183f33c8998adc4a4a46c640bca4
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768382"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="02ae8-103">針對 Microsoft Teams 準備組織的網路</span><span class="sxs-lookup"><span data-stu-id="02ae8-103">Prepare your organization's network for Microsoft Teams</span></span> 

## <a name="network-requirements"></a><span data-ttu-id="02ae8-104">網路需求</span><span class="sxs-lookup"><span data-stu-id="02ae8-104">Network requirements</span></span>

<span data-ttu-id="02ae8-105">如果您已[針對 Microsoft 365 或 Office 365 最佳化您的網路](/Office365/Enterprise/assessing-network-connectivity)，則可能已準備好使用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="02ae8-105">If you've already [optimized your network for Microsoft 365 or Office 365](/Office365/Enterprise/assessing-network-connectivity), you're probably ready for Microsoft Teams.</span></span> <span data-ttu-id="02ae8-106">在任何情況下，尤其是如果您要快速推出 Teams 做為第一個 Microsoft 365 或 Office 365 工作負載以支援 **遠端工作者** - 請在開始推出 Teams 之前，檢查下列項目：</span><span class="sxs-lookup"><span data-stu-id="02ae8-106">In any case - and especially if you're rolling out Teams quickly as your first Microsoft 365 or Office 365 workload to support **remote workers** - check the following before you begin your Teams rollout:</span></span>

1.  <span data-ttu-id="02ae8-107">您的所有位置是否都有網際網路存取權 (以便它們可以連線到 Microsoft 365 或 Office 365)？</span><span class="sxs-lookup"><span data-stu-id="02ae8-107">Do all your locations have internet access (so they can connect to Microsoft 365 or Office 365)?</span></span> <span data-ttu-id="02ae8-108">除了一般網路流量之外，請確定您至少已針對 Teams 中的媒體，對所有位置開放下列項目：</span><span class="sxs-lookup"><span data-stu-id="02ae8-108">At a minimum, in addition to normal web traffic, make sure you've opened the following, for all locations, for media in Teams:</span></span>

    |  |  |
    |---------|---------|
    |<span data-ttu-id="02ae8-109">連接埠</span><span class="sxs-lookup"><span data-stu-id="02ae8-109">Ports</span></span>     |<span data-ttu-id="02ae8-110">UDP 連接埠 <strong>3478</strong> 到 <strong>3481</strong></span><span class="sxs-lookup"><span data-stu-id="02ae8-110">UDP ports <strong>3478</strong> through <strong>3481</strong></span></span>        |
    |[<span data-ttu-id="02ae8-111">IP 位址</span><span class="sxs-lookup"><span data-stu-id="02ae8-111">IP addresses</span></span>](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<span data-ttu-id="02ae8-112"><strong>13.107.64.0/18</strong>、<strong>52.112.0.0/14</strong> 和 <strong>52.120.0.0/14</strong></span><span class="sxs-lookup"><span data-stu-id="02ae8-112"><strong>13.107.64.0/18</strong>, <strong>52.112.0.0/14</strong>, and <strong>52.120.0.0/14</strong></span></span>         |

    > [!IMPORTANT]
    > <span data-ttu-id="02ae8-113">如果需要與商務用 Skype (內部部署或線上) 進行同盟，您必須設定一些額外的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="02ae8-113">If you need to federate with Skype for Business, either on-premises or online, you will need to configure some additional DNS records.</span></span>
    >
    >|<span data-ttu-id="02ae8-114">CNAME 記錄/主機名稱</span><span class="sxs-lookup"><span data-stu-id="02ae8-114">CNAME Records / Host name</span></span>  |<span data-ttu-id="02ae8-115">TTL</span><span class="sxs-lookup"><span data-stu-id="02ae8-115">TTL</span></span>  |<span data-ttu-id="02ae8-116">指向位址或值</span><span class="sxs-lookup"><span data-stu-id="02ae8-116">Points to address or value</span></span>  |
    >|---------|---------|---------|
    >|<span data-ttu-id="02ae8-117">sip</span><span class="sxs-lookup"><span data-stu-id="02ae8-117">sip</span></span>     |    <span data-ttu-id="02ae8-118">3600</span><span class="sxs-lookup"><span data-stu-id="02ae8-118">3600</span></span>     |    <span data-ttu-id="02ae8-119">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="02ae8-119">sipdir.online.lync.com</span></span>     |
    >|<span data-ttu-id="02ae8-120">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="02ae8-120">lyncdiscover</span></span>     |   <span data-ttu-id="02ae8-121">3600</span><span class="sxs-lookup"><span data-stu-id="02ae8-121">3600</span></span>      |    <span data-ttu-id="02ae8-122">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="02ae8-122">webdir.online.lync.com</span></span>     |
    
2.  <span data-ttu-id="02ae8-123">您是否有 Microsoft 365 或 Office 365 的經驗證網域 (例如，contoso.com)？</span><span class="sxs-lookup"><span data-stu-id="02ae8-123">Do you have a verified domain for Microsoft 365 or Office 365 (for example, contoso.com)?</span></span>
    
    - <span data-ttu-id="02ae8-124">如果您的組織尚未推出 Microsoft 365 或 Office 365，請參閱[開始使用](/microsoft-365/admin/admin-overview/get-started-with-office-365)。</span><span class="sxs-lookup"><span data-stu-id="02ae8-124">If your organization hasn't rolled out Microsoft 365 or Office 365, see [Get started](/microsoft-365/admin/admin-overview/get-started-with-office-365).</span></span>
    - <span data-ttu-id="02ae8-125">如果您的組織尚未為 Microsoft 365 或 Office 365 新增或設定經驗證的網域，請參閱[網域常見問題集](/microsoft-365/admin/setup/domains-faq)。</span><span class="sxs-lookup"><span data-stu-id="02ae8-125">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see the [Domains FAQ](/microsoft-365/admin/setup/domains-faq).</span></span>

3.  <span data-ttu-id="02ae8-126">您的組織是否已部署 Exchange Online 和 SharePoint Online？</span><span class="sxs-lookup"><span data-stu-id="02ae8-126">Has your organization deployed Exchange Online and SharePoint Online?</span></span>
    
    - <span data-ttu-id="02ae8-127">如果您的組織沒有 Exchange Online，請參閱[了解 Exchange 和 Microsoft Teams 如何互動](exchange-teams-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="02ae8-127">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](exchange-teams-interact.md).</span></span>
    - <span data-ttu-id="02ae8-128">如果您的組織沒有 SharePoint Online，請參閱[了解 SharePoint Online 和商務用 OneDrive 如何與 Microsoft Teams 互動](sharepoint-onedrive-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="02ae8-128">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

<span data-ttu-id="02ae8-129">一旦確認您符合這些網路需求，就可以開始[推出 Teams](./deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="02ae8-129">Once you've verified that you meet these network requirements, you may be ready to [Roll out Teams](./deploy-overview.md).</span></span> <span data-ttu-id="02ae8-130">如果您是大型的多國企業，或如果您知道有一些網路限制，請繼續閱讀以了解如何評估及最佳化 Teams 的網路。</span><span class="sxs-lookup"><span data-stu-id="02ae8-130">If you're a large multinational enterprise, or if you know you've got some network limitations, read on to learn how to assess and optimize your network for Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="02ae8-131">**適用於教育機構**：如果您的組織是教育機構，且您使用學生資訊系統 (SIS)，請在推出 Teams 之前[部署學校資料同步處理](/schooldatasync/)。</span><span class="sxs-lookup"><span data-stu-id="02ae8-131">**For educational institutions**: If your organization is an educational institution and you use a Student Information System (SIS), [deploy School Data Sync](/schooldatasync/) before you roll out Teams.</span></span>
>  
> <span data-ttu-id="02ae8-132">**執行內部部署商務用 Skype Server**：如果您的組織執行的是內部部署商務用 Skype Server (或 Lync Server)，您必須[設定 Azure AD Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect)，以與 Microsoft 365 或 Office 365 同步處理您的內部部署目錄。</span><span class="sxs-lookup"><span data-stu-id="02ae8-132">**Running on-premises Skype for Business Server**: If your organization is running on-premises Skype for Business Server (or Lync Server), you must [configure Azure AD Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect) to synchronize your on-premises directory with Microsoft 365 or Office 365.</span></span>

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a><span data-ttu-id="02ae8-133">最佳做法：使用 CQD 和通話分析監視您的網路</span><span class="sxs-lookup"><span data-stu-id="02ae8-133">Best practice: Monitor your network using CQD and call analytics</span></span> 

<span data-ttu-id="02ae8-134">使用[通話品質儀表板 (CQD)](turning-on-and-using-call-quality-dashboard.md) 以深入了解 Teams 中的通話和會議品質。</span><span class="sxs-lookup"><span data-stu-id="02ae8-134">Use the [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to gain insight into the quality of calls and meetings in Teams.</span></span> <span data-ttu-id="02ae8-135">CQD 會透過持續注意品質、可靠性和使用者體驗，協助您最佳化您的網路。</span><span class="sxs-lookup"><span data-stu-id="02ae8-135">CQD can help you optimize your network by keeping a close eye on quality, reliability, and the user experience.</span></span> <span data-ttu-id="02ae8-136">CQD 會查看整個組織整體模式可能變得明顯處的彙總遙測，這可讓您識別問題並規劃補救。</span><span class="sxs-lookup"><span data-stu-id="02ae8-136">CQD looks at aggregate telemetry for an entire organization where overall patterns can become apparent, which lets you identify problems and plan remediation.</span></span> <span data-ttu-id="02ae8-137">此外，CQD 會提供豐富的計量報告，其提供整體品質、可靠性和使用者體驗的深入見解。</span><span class="sxs-lookup"><span data-stu-id="02ae8-137">Additionally, CQD provides rich metrics reports that provide insight into overall quality, reliability, and user experience.</span></span> 

<span data-ttu-id="02ae8-138">您將使用[通話分析](set-up-call-analytics.md)來調查個別使用者的通話和會議問題。</span><span class="sxs-lookup"><span data-stu-id="02ae8-138">You'll use [call analytics](set-up-call-analytics.md) to investigate call and meeting problems for an individual user.</span></span>

## <a name="network-optimization"></a><span data-ttu-id="02ae8-139">網路​​最佳化</span><span class="sxs-lookup"><span data-stu-id="02ae8-139">Network optimization</span></span>

<span data-ttu-id="02ae8-140">下列工作是選用的，且並非推出 Teams 時的必要項目，特別是如果您是小型企業，而且已經推出 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="02ae8-140">The following tasks are optional and aren't required for rolling out Teams, especially if you're a small business and you've already rolled out Microsoft 365 or Office 365.</span></span> <span data-ttu-id="02ae8-141">使用此指引來最佳化您的網路和 Teams 的效能，或如果您知道您有一些網路限制，也請參考此指引。</span><span class="sxs-lookup"><span data-stu-id="02ae8-141">Use this guidance to optimize your network and Teams performance or if you know you've got some network limitations.</span></span>

<span data-ttu-id="02ae8-142">您可能會想要執行其他網路最佳化，前提是：</span><span class="sxs-lookup"><span data-stu-id="02ae8-142">You might want to do additional network optimization if:</span></span>

  - <span data-ttu-id="02ae8-143">Teams 執行速度緩慢 (可能是您的頻寬不足)</span><span class="sxs-lookup"><span data-stu-id="02ae8-143">Teams runs slowly (maybe you have insufficient bandwidth)</span></span>
  - <span data-ttu-id="02ae8-144">通話持續斷線 (可能是防火牆或 Proxy 封鎖程式所導致)</span><span class="sxs-lookup"><span data-stu-id="02ae8-144">Calls keep dropping (might be due to firewall or proxy blockers)</span></span>
  - <span data-ttu-id="02ae8-145">通話有停滯和中斷，或聲音聽起來像機器人 (可能是抖動或封包遺失)</span><span class="sxs-lookup"><span data-stu-id="02ae8-145">Calls have static and cut out, or voices sound like robots (could be jitter or packet loss)</span></span>

<span data-ttu-id="02ae8-146">如需網路最佳化的深入討論，包括識別和修正網路減損的指引，請參閱 [Microsoft 365 和 Office 365 網路連線原則](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)。</span><span class="sxs-lookup"><span data-stu-id="02ae8-146">For an in-depth discussion of network optimization, including guidance for identifying and fixing network impairments, read [Microsoft 365 and Office 365 Network Connectivity Principles](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles).</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="02ae8-147"><strong>網路​​最佳化工作</strong></span><span class="sxs-lookup"><span data-stu-id="02ae8-147"><strong>Network optimization task</strong></span></span></th>
<th><span data-ttu-id="02ae8-148"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="02ae8-148"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="02ae8-149">網路規劃中心</span><span class="sxs-lookup"><span data-stu-id="02ae8-149">Network planner</span></span></td>
<td><p><span data-ttu-id="02ae8-150">如需評估您的網路 (包括組織實體位置的頻寬計算和網路需求) 的協助，請查看 <a href="https://admin.teams.microsoft.com">Teams 系統管理中心</a>中的<a href="/microsoftteams/network-planner">網路規劃中心</a>工具。</span><span class="sxs-lookup"><span data-stu-id="02ae8-150">For help assessing your network, including bandwidth calculations and network requirements across your org's physical locations, check out the <a href="/microsoftteams/network-planner">Network Planner</a> tool, in the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="02ae8-151">提供網路詳細資料和 Teams 使用狀況時，網路規劃中心會計算在組織的實體位置間部署 Teams 與雲端語音的網路需求。</span><span class="sxs-lookup"><span data-stu-id="02ae8-151">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span></p>
<p><span data-ttu-id="02ae8-152">如需範例案例，請參閱<a href="/microsoftteams/tutorial-network-planner-example">網路規劃中心 - 範例案例</a>。</span><span class="sxs-lookup"><span data-stu-id="02ae8-152">For an example scenario, see <a href="/microsoftteams/tutorial-network-planner-example">Using Network Planner - example scenario</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="02ae8-153">適用於 Teams 的建議程式</span><span class="sxs-lookup"><span data-stu-id="02ae8-153">Advisor for Teams</span></span></td>
<td><span data-ttu-id="02ae8-154"><a href="/microsoftteams/use-advisor-teams-roll-out">適用於 Teams 的建議程式</a>是 <a href="https://admin.teams.microsoft.com">Teams 系統管理中心</a>的一部分。</span><span class="sxs-lookup"><span data-stu-id="02ae8-154"><a href="/microsoftteams/use-advisor-teams-roll-out">Advisor for Teams</a> is part of the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="02ae8-155">在您成功推出 Teams 前，它會評估您的 Microsoft 365 或 Office 365 環境，找出可能需要更新或修改的最常用設定。</span><span class="sxs-lookup"><span data-stu-id="02ae8-155">It assesses your Microsoft 365 or Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="02ae8-156">外部名稱解析</span><span class="sxs-lookup"><span data-stu-id="02ae8-156">External Name Resolution</span></span></td>
<td><span data-ttu-id="02ae8-157">請確定執行 Teams 用戶端的所有電腦都可以解析外部 DNS 查詢，以探索 Microsoft 365 或 Office 365 提供的服務，而且您的防火牆不會阻止存取。</span><span class="sxs-lookup"><span data-stu-id="02ae8-157">Be sure that all computers running the Teams client can resolve external DNS queries to discover the services provided by Microsoft 365 or Office 365 and that your firewalls are not preventing access.</span></span> <span data-ttu-id="02ae8-158">如需設定防火牆連接埠的詳細資訊，請前往 <a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 和 Office 365 與 IP 範圍</a>。</span><span class="sxs-lookup"><span data-stu-id="02ae8-158">For information about configuring firewall ports, go to <a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 and Office 365 URLs and IP ranges</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="02ae8-159">維護工作階段持續性</span><span class="sxs-lookup"><span data-stu-id="02ae8-159">Maintain session persistence</span></span></td>
<td><span data-ttu-id="02ae8-160">請確定您的防火牆不會變更對應的網路位址轉譯 (NAT) 位址或 UDP 的連接埠。</span><span class="sxs-lookup"><span data-stu-id="02ae8-160">Make sure your firewall doesn't change the mapped Network Address Translation (NAT) addresses or ports for UDP.</span></span></td>
</tr><tr class="odd">
<td><span data-ttu-id="02ae8-161">驗證 NAT 集區大小</span><span class="sxs-lookup"><span data-stu-id="02ae8-161">Validate NAT pool size</span></span></td>
<td><span data-ttu-id="02ae8-162">驗證使用者連線所需的網路位址轉譯 (NAT) 集區大小。</span><span class="sxs-lookup"><span data-stu-id="02ae8-162">Validate the network address translation (NAT) pool size required for user connectivity.</span></span> <span data-ttu-id="02ae8-163">多個使用者和裝置使用<a href="/office365/enterprise/nat-support-with-office-365">網路位址轉譯 (NAT) 或連接埠位址轉譯 (PAT)</a> 存取 Microsoft 365 或 Office 365 時，您必須確保隱藏於每個可路由 IP 位址後方的裝置不超過支援的數量。</span><span class="sxs-lookup"><span data-stu-id="02ae8-163">When multiple users and devices access Microsoft 365 or Office 365 using <a href="/office365/enterprise/nat-support-with-office-365">Network Address Translation (NAT) or Port Address Translation (PAT)</a>, you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span> <span data-ttu-id="02ae8-164">確保將充足的公用 IP 位址指派到 NAT 集區，以防止連接埠耗盡。</span><span class="sxs-lookup"><span data-stu-id="02ae8-164">Ensure that adequate public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="02ae8-165">連接埠耗盡會導致內部使用者和裝置無法連線到 Microsoft 365 或 Office 365 服務。</span><span class="sxs-lookup"><span data-stu-id="02ae8-165">Port exhaustion will contribute to internal users and devices being unable to connect to the Microsoft 365 or Office 365 service.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="02ae8-166">路由至 Microsoft 資料中心</span><span class="sxs-lookup"><span data-stu-id="02ae8-166">Routing to Microsoft data centers</span></span></td>
<td><span data-ttu-id="02ae8-167"><a href="/office365/enterprise/client-connectivity">對 Microsoft 資料中心實作最有效率的路由</a>。</span><span class="sxs-lookup"><span data-stu-id="02ae8-167"><a href="/office365/enterprise/client-connectivity">Implement the most efficient routing to Microsoft data centers</a>.</span></span> <span data-ttu-id="02ae8-168">盡可能有效率地識別可使用本機或區域出口點來連線至 Microsoft 網路的位置。</span><span class="sxs-lookup"><span data-stu-id="02ae8-168">Identify locations that can use local or regional egress points to connect to the Microsoft network as efficiently as possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="02ae8-169">入侵偵測與預防指引</span><span class="sxs-lookup"><span data-stu-id="02ae8-169">Intrusion Detection and Prevention Guidance</span></span></td>
<td><span data-ttu-id="02ae8-170">如果您的環境已部署<a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">入侵偵測</a>或預防系統 (IDS/IPS)，以針對輸出連線獲得額外一層的安全性，請務必允許所有 Microsoft 365 或 Office 365 URL。</span><span class="sxs-lookup"><span data-stu-id="02ae8-170">If your environment has an <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Intrusion Detection</a> or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, be sure to allow all Microsoft 365 or Office 365 URLs.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="02ae8-171">設定分割通道 VPN</span><span class="sxs-lookup"><span data-stu-id="02ae8-171">Configure split-tunnel VPN</span></span></td>
<td><p><span data-ttu-id="02ae8-172">建議您為會略過虛擬私人網路 (VPN) 的 Teams 流量提供替代路徑，通常稱為<a href="/windows/security/identity-protection/vpn/vpn-routing">分割通道 VPN</a>。</span><span class="sxs-lookup"><span data-stu-id="02ae8-172">We recommend that you provide an alternate path for Teams traffic that bypasses the virtual private network (VPN), commonly known as <a href="/windows/security/identity-protection/vpn/vpn-routing">split-tunnel VPN</a>.</span></span> <span data-ttu-id="02ae8-173">分割通道表示 Microsoft 365 或 Office 365 的流量不會通過 VPN，而是直接進入 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="02ae8-173">Split tunneling means that traffic for Microsoft 365 or Office 365 doesn't go through the VPN but instead goes directly to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="02ae8-174">略過 VPN 會對 Teams 品質產生正面影響，並減少來自 VPN 裝置和組織網路的負載。</span><span class="sxs-lookup"><span data-stu-id="02ae8-174">Bypassing your VPN will have a positive impact on Teams quality, and it reduces load from the VPN devices and the organization's network.</span></span> <span data-ttu-id="02ae8-175">若要實作分割通道 VPN，請與 VPN 廠商合作。</span><span class="sxs-lookup"><span data-stu-id="02ae8-175">To implement a split-tunnel VPN, work with your VPN vendor.</span></span></p>
<p><span data-ttu-id="02ae8-176">我們建議略過 VPN 的其他原因：</span><span class="sxs-lookup"><span data-stu-id="02ae8-176">Other reasons why we recommend bypassing the VPN:</span></span>
<ul>
<li><p><span data-ttu-id="02ae8-177">VPN 通常不會設計或設定為支援即時媒體。</span><span class="sxs-lookup"><span data-stu-id="02ae8-177">VPNs are typically not designed or configured to support real-time media.</span></span></p></li> 
<li><p><span data-ttu-id="02ae8-178">某些 VPN 可能也不支援 UDP (這是 Teams 所需)。</span><span class="sxs-lookup"><span data-stu-id="02ae8-178">Some VPNs might also not support UDP (which is required for Teams).</span></span></p></li> 
<li><p><span data-ttu-id="02ae8-179">VPN 也會在已加密的媒體流量上引入額外的加密層。</span><span class="sxs-lookup"><span data-stu-id="02ae8-179">VPNs also introduce an extra layer of encryption on top of media traffic that's already encrypted.</span></span></p></li> 
<li><p><span data-ttu-id="02ae8-180">由於透過 VPN 裝置切換流量，與 Teams 的連線可能會沒有效率。</span><span class="sxs-lookup"><span data-stu-id="02ae8-180">Connectivity to Teams might not be efficient due to hair-pinning traffic through a VPN device.</span></span></p></li></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="02ae8-181">實作 QoS</span><span class="sxs-lookup"><span data-stu-id="02ae8-181">Implement QoS</span></span></td>
<td><span data-ttu-id="02ae8-182"><a href="/microsoftteams/qos-in-teams">使用服務品質 (QoS)</a> 來設定封包優先順序。</span><span class="sxs-lookup"><span data-stu-id="02ae8-182"><a href="/microsoftteams/qos-in-teams">Use Quality of Service (QoS)</a> to configure packet prioritization.</span></span> <span data-ttu-id="02ae8-183">這將改善 Teams 中的通話品質，並協助您監控和疑難排解通話品質。</span><span class="sxs-lookup"><span data-stu-id="02ae8-183">This will improve call quality in Teams and help you monitor and troubleshoot call quality.</span></span> <span data-ttu-id="02ae8-184">QoS 應該在受管理網路的所有區段上實作。</span><span class="sxs-lookup"><span data-stu-id="02ae8-184">QoS should be implemented on all segments of a managed network.</span></span> <span data-ttu-id="02ae8-185">即使在網路已佈建足夠頻寬時，在發生未預期的網路事件時，QoS 也可提供風險緩解。</span><span class="sxs-lookup"><span data-stu-id="02ae8-185">Even when a network has been adequately provisioned for bandwidth, QoS provides risk mitigation in the event of unanticipated network events.</span></span> <span data-ttu-id="02ae8-186">使用 QoS 時，會優先處理語音流量，使得這些非預期的事件不會對品質造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="02ae8-186">With QoS, voice traffic is prioritized so that these unanticipated events don't negatively affect quality.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="02ae8-187">最佳化 WiFi</span><span class="sxs-lookup"><span data-stu-id="02ae8-187">Optimize WiFi</span></span></td>
<td><p><span data-ttu-id="02ae8-188">類似於 VPN，WiFi 網路不一定需要設計或設定為支援即時媒體。</span><span class="sxs-lookup"><span data-stu-id="02ae8-188">Similar to VPN, WiFi networks aren't necessarily designed or configured to support real-time media.</span></span> <span data-ttu-id="02ae8-189">規劃或最佳化 WiFi 網路以支援 Teams，是實現高品質部署的重要考慮事項。</span><span class="sxs-lookup"><span data-stu-id="02ae8-189">Planning for, or optimizing, a WiFi network to support Teams is an important consideration for a high-quality deployment.</span></span> <span data-ttu-id="02ae8-190">考慮下列因素：</span><span class="sxs-lookup"><span data-stu-id="02ae8-190">Consider these factors:</span></span></p>
<ul>
<li><p><span data-ttu-id="02ae8-191">實作 QoS 或 WiFi 多媒體 (WMM) 以確保透過 WiFi 網路的媒體流量有適當的優先順序。</span><span class="sxs-lookup"><span data-stu-id="02ae8-191">Implement QoS or WiFi Multimedia (WMM) to ensure that media traffic is getting prioritized appropriately over your WiFi networks.</span></span></p></li>
<li><p><span data-ttu-id="02ae8-192">規劃和最佳化 WiFi 頻帶與存取點放置方式。</span><span class="sxs-lookup"><span data-stu-id="02ae8-192">Plan and optimize the WiFi bands and access point placement.</span></span> <span data-ttu-id="02ae8-193">根據存取點放置方式，2.4 GHz 範圍可能會提供足夠的體驗，但存取點往往會受到該範圍中運作的其他消費者裝置影響。</span><span class="sxs-lookup"><span data-stu-id="02ae8-193">The 2.4 GHz range might provide an adequate experience depending on access point placement, but access points are often affected by other consumer devices that operate in that range.</span></span> <span data-ttu-id="02ae8-194">5 GHz 範圍因其密度範圍較適合即時媒體，但需要更多存取點以取得足夠的覆蓋範圍。</span><span class="sxs-lookup"><span data-stu-id="02ae8-194">The 5 GHz range is better suited to real-time media due to its dense range, but it requires more access points to get sufficient coverage.</span></span> <span data-ttu-id="02ae8-195">端點也需要支援該範圍並經過設定，才能據以運用這些頻帶。</span><span class="sxs-lookup"><span data-stu-id="02ae8-195">Endpoints also need to support that range and be configured to leverage those bands accordingly.</span></span></p></li>
<li><p><span data-ttu-id="02ae8-196">如果您使用的是雙頻 WiFi 網路，請考慮實作頻帶操縱。</span><span class="sxs-lookup"><span data-stu-id="02ae8-196">If you're using dual-band WiFi networks, consider implementing band steering.</span></span> <span data-ttu-id="02ae8-197"><em>頻帶操縱</em>是 WiFi 廠商所實作的技術，可影響雙頻用戶端以使用 5 GHz 範圍。</span><span class="sxs-lookup"><span data-stu-id="02ae8-197"><em>Band steering</em> is a technique implemented by WiFi vendors to influence dual-band clients to use the 5 GHz range.</span></span></p></li>
<li><p><span data-ttu-id="02ae8-198">當相同頻道的存取點太接近時，可能會導致信號重疊且無意間的競爭，導致使用者體驗不佳。</span><span class="sxs-lookup"><span data-stu-id="02ae8-198">When access points of the same channel are too close together, they can cause signal overlap and unintentionally compete, resulting in a bad experience for the user.</span></span> <span data-ttu-id="02ae8-199">確保頻道上相鄰的存取點沒有重疊。</span><span class="sxs-lookup"><span data-stu-id="02ae8-199">Ensure that access points that are next to each other are on channels that don't overlap.</span></span></p></li>
</ul>
<p><span data-ttu-id="02ae8-200">每個無線廠商都有其部署無線解決方案的建議。</span><span class="sxs-lookup"><span data-stu-id="02ae8-200">Each wireless vendor has its own recommendations for deploying its wireless solution.</span></span> <span data-ttu-id="02ae8-201">請洽詢您的 WiFi 廠商以了解特定指引。</span><span class="sxs-lookup"><span data-stu-id="02ae8-201">Consult your WiFi vendor for specific guidance.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a><span data-ttu-id="02ae8-202">頻寬需求</span><span class="sxs-lookup"><span data-stu-id="02ae8-202">Bandwidth requirements</span></span>

<span data-ttu-id="02ae8-203">無論您的網路狀況如何，Teams 的設計都可提供最佳的音訊、視訊和內容共用體驗。</span><span class="sxs-lookup"><span data-stu-id="02ae8-203">Teams is designed to give the best audio, video, and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="02ae8-204">也就是說，當頻寬不足時，Teams 會優先處理音訊品質，之後才是視訊品質。</span><span class="sxs-lookup"><span data-stu-id="02ae8-204">That said, when bandwidth is insufficient, Teams prioritizes audio quality over video quality.</span></span>

<span data-ttu-id="02ae8-205">在頻寬 *未* 受限的情況下，Teams 會最佳化媒體品質，包括最高 1080p 的視訊解析度、最高 30fps 的視訊和 15fps 的內容，以及高逼真度音訊。</span><span class="sxs-lookup"><span data-stu-id="02ae8-205">Where bandwidth *isn't* limited, Teams optimizes media quality, including up to 1080p video resolution, up to 30fps for video and 15fps for content, and high-fidelity audio.</span></span> 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a><span data-ttu-id="02ae8-206">相關主題</span><span class="sxs-lookup"><span data-stu-id="02ae8-206">Related Topics</span></span>

[<span data-ttu-id="02ae8-207">Microsoft 365 和 Office 365 網路連線原則</span><span class="sxs-lookup"><span data-stu-id="02ae8-207">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[<span data-ttu-id="02ae8-208">全球端點：商務用 Skype Online 和 Teams</span><span class="sxs-lookup"><span data-stu-id="02ae8-208">Worldwide endpoints: Skype for Business Online and Teams</span></span>](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[<span data-ttu-id="02ae8-209">Teams 的 Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="02ae8-209">Proxy servers for Teams</span></span>](proxy-servers-for-skype-for-business-online.md)

[<span data-ttu-id="02ae8-210">Teams 中的媒體：為什麼會議很簡單</span><span class="sxs-lookup"><span data-stu-id="02ae8-210">Media in Teams: Why meetings are simple</span></span>](https://aka.ms/teams-media)

[<span data-ttu-id="02ae8-211">Teams 中的媒體：深入探討媒體流程</span><span class="sxs-lookup"><span data-stu-id="02ae8-211">Media in Teams: Deep dive into media flows</span></span>](https://aka.ms/teams-media-flows)

[<span data-ttu-id="02ae8-212">Teams 中的身分識別和驗證</span><span class="sxs-lookup"><span data-stu-id="02ae8-212">Identity models and authentication in Teams</span></span>](identify-models-authentication.md)

[<span data-ttu-id="02ae8-213">如何推出 Teams</span><span class="sxs-lookup"><span data-stu-id="02ae8-213">How to roll out Teams</span></span>](./deploy-overview.md)

[<span data-ttu-id="02ae8-214">Teams 疑難排解</span><span class="sxs-lookup"><span data-stu-id="02ae8-214">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
