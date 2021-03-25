---
title: 針對 Teams 準備組織的網路
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: 瞭解如何為 Microsoft Teams 準備貴組織的網路，包括網路需求、網路優化和頻寬需求。
localization_priority: Normal
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
ms.openlocfilehash: 1c84a753146899011fa34be56e0746cc0c600b31
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117751"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="7de6e-103">針對 Microsoft Teams 準備組織的網路</span><span class="sxs-lookup"><span data-stu-id="7de6e-103">Prepare your organization's network for Microsoft Teams</span></span> 

## <a name="network-requirements"></a><span data-ttu-id="7de6e-104">網路需求</span><span class="sxs-lookup"><span data-stu-id="7de6e-104">Network requirements</span></span>

<span data-ttu-id="7de6e-105">如果您已經針對 [Microsoft 365 或 Office 365](/Office365/Enterprise/assessing-network-connectivity)優化您的網路，您可能已準備好使用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="7de6e-105">If you've already [optimized your network for Microsoft 365 or Office 365](/Office365/Enterprise/assessing-network-connectivity), you're probably ready for Microsoft Teams.</span></span> <span data-ttu-id="7de6e-106">在任何情況下 ，尤其是當您將 Teams 快速推出為第一個 Microsoft 365 或 Office 365工作負載以支援遠端員工時，在開始推出 Teams 之前，請檢查下列事項：</span><span class="sxs-lookup"><span data-stu-id="7de6e-106">In any case - and especially if you're rolling out Teams quickly as your first Microsoft 365 or Office 365 workload to support **remote workers** - check the following before you begin your Teams rollout:</span></span>

1.  <span data-ttu-id="7de6e-107">您的所有位置是否都有網際網路 (，以便他們連接到 Microsoft 365 或 Office 365) ？</span><span class="sxs-lookup"><span data-stu-id="7de6e-107">Do all your locations have internet access (so they can connect to Microsoft 365 or Office 365)?</span></span> <span data-ttu-id="7de6e-108">除了一般 Web 流量之外，請至少針對 Teams 中的媒體，針對所有位置開啟下列專案：</span><span class="sxs-lookup"><span data-stu-id="7de6e-108">At a minimum, in addition to normal web traffic, make sure you've opened the following, for all locations, for media in Teams:</span></span>

    |  |  |
    |---------|---------|
    |<span data-ttu-id="7de6e-109">港口</span><span class="sxs-lookup"><span data-stu-id="7de6e-109">Ports</span></span>     |<span data-ttu-id="7de6e-110">UDP 埠 <strong>3478</strong> 到 <strong>3481</strong></span><span class="sxs-lookup"><span data-stu-id="7de6e-110">UDP ports <strong>3478</strong> through <strong>3481</strong></span></span>        |
    |[<span data-ttu-id="7de6e-111">IP 位址</span><span class="sxs-lookup"><span data-stu-id="7de6e-111">IP addresses</span></span>](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<span data-ttu-id="7de6e-112"><strong>13.107.64.0/18、52.112.0.0/14</strong>和<strong>52.120.0.0/14</strong> <strong></strong></span><span class="sxs-lookup"><span data-stu-id="7de6e-112"><strong>13.107.64.0/18</strong>, <strong>52.112.0.0/14</strong>, and <strong>52.120.0.0/14</strong></span></span>         |

    > [!IMPORTANT]
    > <span data-ttu-id="7de6e-113">如果您需要與商務用 Skype 進行內部部署或線上聯合，則需要設定一些額外的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="7de6e-113">If you need to federate with Skype for Business, either on-premises or online, you will need to configure some additional DNS records.</span></span>
    >
    >|<span data-ttu-id="7de6e-114">CNAME 記錄 / 主機名稱</span><span class="sxs-lookup"><span data-stu-id="7de6e-114">CNAME Records / Host name</span></span>  |<span data-ttu-id="7de6e-115">Ttl</span><span class="sxs-lookup"><span data-stu-id="7de6e-115">TTL</span></span>  |<span data-ttu-id="7de6e-116">指向位址或值</span><span class="sxs-lookup"><span data-stu-id="7de6e-116">Points to address or value</span></span>  |
    >|---------|---------|---------|
    >|<span data-ttu-id="7de6e-117">Sip</span><span class="sxs-lookup"><span data-stu-id="7de6e-117">sip</span></span>     |    <span data-ttu-id="7de6e-118">3600</span><span class="sxs-lookup"><span data-stu-id="7de6e-118">3600</span></span>     |    <span data-ttu-id="7de6e-119">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7de6e-119">sipdir.online.lync.com</span></span>     |
    >|<span data-ttu-id="7de6e-120">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="7de6e-120">lyncdiscover</span></span>     |   <span data-ttu-id="7de6e-121">3600</span><span class="sxs-lookup"><span data-stu-id="7de6e-121">3600</span></span>      |    <span data-ttu-id="7de6e-122">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7de6e-122">webdir.online.lync.com</span></span>     |
    
2.  <span data-ttu-id="7de6e-123">您是否有 Microsoft 365 或 Office 365 (驗證網域，例如 contoso.com) ？</span><span class="sxs-lookup"><span data-stu-id="7de6e-123">Do you have a verified domain for Microsoft 365 or Office 365 (for example, contoso.com)?</span></span>
    
    - <span data-ttu-id="7de6e-124">如果貴組織尚未推出 Microsoft 365 或 Office 365，請參閱 [開始使用](/microsoft-365/admin/admin-overview/get-started-with-office-365)。</span><span class="sxs-lookup"><span data-stu-id="7de6e-124">If your organization hasn't rolled out Microsoft 365 or Office 365, see [Get started](/microsoft-365/admin/admin-overview/get-started-with-office-365).</span></span>
    - <span data-ttu-id="7de6e-125">如果貴組織尚未新增或已針對 Microsoft 365 或 Office 365 新增或已驗證網域，請參閱 [網域常見問題](/microsoft-365/admin/setup/domains-faq)。</span><span class="sxs-lookup"><span data-stu-id="7de6e-125">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see the [Domains FAQ](/microsoft-365/admin/setup/domains-faq).</span></span>

3.  <span data-ttu-id="7de6e-126">您的組織是否部署 Exchange Online 和 SharePoint Online？</span><span class="sxs-lookup"><span data-stu-id="7de6e-126">Has your organization deployed Exchange Online and SharePoint Online?</span></span>
    
    - <span data-ttu-id="7de6e-127">如果貴組織沒有 Exchange Online，請參閱瞭解 Exchange 與 [Microsoft Teams 的互動方式](exchange-teams-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="7de6e-127">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](exchange-teams-interact.md).</span></span>
    - <span data-ttu-id="7de6e-128">如果貴組織沒有 SharePoint Online，請參閱瞭解 [SharePoint Online](sharepoint-onedrive-interact.md)和商務用 OneDrive 如何與 Microsoft Teams 互動。</span><span class="sxs-lookup"><span data-stu-id="7de6e-128">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

<span data-ttu-id="7de6e-129">確認您符合這些網路需求之後，就可以開始 [推出 Teams 了](./deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="7de6e-129">Once you've verified that you meet these network requirements, you may be ready to [Roll out Teams](./deploy-overview.md).</span></span> <span data-ttu-id="7de6e-130">如果您是大型跨國企業，或如果您知道自己有一些網路限制，請繼續閱讀以瞭解如何評估及優化 Teams 的網路。</span><span class="sxs-lookup"><span data-stu-id="7de6e-130">If you're a large multinational enterprise, or if you know you've got some network limitations, read on to learn how to assess and optimize your network for Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7de6e-131">**適用于教育機構**：如果貴組織是教育機構，而且您使用學生資訊系統 (SIS) ，請部署學校資料同步處理，[](/schooldatasync/)然後再推出 Teams。</span><span class="sxs-lookup"><span data-stu-id="7de6e-131">**For educational institutions**: If your organization is an educational institution and you use a Student Information System (SIS), [deploy School Data Sync](/schooldatasync/) before you roll out Teams.</span></span>
>  
> <span data-ttu-id="7de6e-132">**執行內部部署商務用 Skype Server：** 如果貴組織執行的是內部部署商務用 Skype Server (或 Lync Server) ，您必須設定 [Azure AD Connect，](/skypeforbusiness/hybrid/configure-azure-ad-connect) 以同步處理您的內部部署目錄與 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="7de6e-132">**Running on-premises Skype for Business Server**: If your organization is running on-premises Skype for Business Server (or Lync Server), you must [configure Azure AD Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect) to synchronize your on-premises directory with Microsoft 365 or Office 365.</span></span>

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a><span data-ttu-id="7de6e-133">最佳做法：使用 CQD 和通話分析監控您的網路</span><span class="sxs-lookup"><span data-stu-id="7de6e-133">Best practice: Monitor your network using CQD and call analytics</span></span> 

<span data-ttu-id="7de6e-134">使用 [CQD (儀表板 ](turning-on-and-using-call-quality-dashboard.md)) 以深入瞭解 Teams 中的通話和會議品質。</span><span class="sxs-lookup"><span data-stu-id="7de6e-134">Use the [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to gain insight into the quality of calls and meetings in Teams.</span></span> <span data-ttu-id="7de6e-135">CQD 可密切注意品質、可靠性及使用者體驗，協助優化您的網路。</span><span class="sxs-lookup"><span data-stu-id="7de6e-135">CQD can help you optimize your network by keeping a close eye on quality, reliability, and the user experience.</span></span> <span data-ttu-id="7de6e-136">CQD 會查看整個組織的匯總遙測，其中整體模式可能會變得明顯，這可讓您找出問題並規劃補救。</span><span class="sxs-lookup"><span data-stu-id="7de6e-136">CQD looks at aggregate telemetry for an entire organization where overall patterns can become apparent, which lets you identify problems and plan remediation.</span></span> <span data-ttu-id="7de6e-137">此外，CQD 還提供豐富的度量報表，可提供整體品質、可靠性及使用者體驗的深入見解。</span><span class="sxs-lookup"><span data-stu-id="7de6e-137">Additionally, CQD provides rich metrics reports that provide insight into overall quality, reliability, and user experience.</span></span> 

<span data-ttu-id="7de6e-138">您將使用通話 [分析](set-up-call-analytics.md) 來調查個別使用者的通話和會議問題。</span><span class="sxs-lookup"><span data-stu-id="7de6e-138">You'll use [call analytics](set-up-call-analytics.md) to investigate call and meeting problems for an individual user.</span></span>

## <a name="network-optimization"></a><span data-ttu-id="7de6e-139">網路優化</span><span class="sxs-lookup"><span data-stu-id="7de6e-139">Network optimization</span></span>

<span data-ttu-id="7de6e-140">下列工作是選擇性的，且不需要用於推出 Teams，尤其是如果您是小型企業，而且已經推出 Microsoft 365 或 Office 365 時。</span><span class="sxs-lookup"><span data-stu-id="7de6e-140">The following tasks are optional and aren't required for rolling out Teams, especially if you're a small business and you've already rolled out Microsoft 365 or Office 365.</span></span> <span data-ttu-id="7de6e-141">請使用本指南來優化您的網路和 Teams 績效，或者如果您知道自己有一些網路限制。</span><span class="sxs-lookup"><span data-stu-id="7de6e-141">Use this guidance to optimize your network and Teams performance or if you know you've got some network limitations.</span></span>

<span data-ttu-id="7de6e-142">如果：</span><span class="sxs-lookup"><span data-stu-id="7de6e-142">You might want to do additional network optimization if:</span></span>

  - <span data-ttu-id="7de6e-143">團隊執行速度緩慢 (可能您沒有足夠的頻寬) </span><span class="sxs-lookup"><span data-stu-id="7de6e-143">Teams runs slowly (maybe you have insufficient bandwidth)</span></span>
  - <span data-ttu-id="7de6e-144">通話持續 (可能是防火牆或 Proxy 封鎖) </span><span class="sxs-lookup"><span data-stu-id="7de6e-144">Calls keep dropping (might be due to firewall or proxy blockers)</span></span>
  - <span data-ttu-id="7de6e-145">通話具有靜態和中斷，或語音聽起來像機器人 (可能會抖動或封包遺失) </span><span class="sxs-lookup"><span data-stu-id="7de6e-145">Calls have static and cut out, or voices sound like robots (could be jitter or packet loss)</span></span>

<span data-ttu-id="7de6e-146">請參閱 Microsoft [365 和 Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)網路連接原則，以深入瞭解網路優化，包括識別及修正網路障礙的指南。</span><span class="sxs-lookup"><span data-stu-id="7de6e-146">For an in-depth discussion of network optimization, including guidance for identifying and fixing network impairments, read [Microsoft 365 and Office 365 Network Connectivity Principles](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles).</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="7de6e-147"><strong>網路優化工作</strong></span><span class="sxs-lookup"><span data-stu-id="7de6e-147"><strong>Network optimization task</strong></span></span></th>
<th><span data-ttu-id="7de6e-148"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="7de6e-148"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="7de6e-149">網路規劃中心</span><span class="sxs-lookup"><span data-stu-id="7de6e-149">Network planner</span></span></td>
<td><p><span data-ttu-id="7de6e-150">如要協助評估您的網路，包括整個組織實體位置的頻寬計算和網路需求，請查看 Teams 系統管理中心的網路規劃<a href="/microsoftteams/network-planner"></a><a href="https://admin.teams.microsoft.com">工具</a>。</span><span class="sxs-lookup"><span data-stu-id="7de6e-150">For help assessing your network, including bandwidth calculations and network requirements across your org's physical locations, check out the <a href="/microsoftteams/network-planner">Network Planner</a> tool, in the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="7de6e-151">當您提供您的網路詳細資料及 Teams 使用方式時，網路規劃工具會計算您在整個組織實體位置部署 Teams 和雲端語音的網路需求。</span><span class="sxs-lookup"><span data-stu-id="7de6e-151">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span></p>
<p><span data-ttu-id="7de6e-152">針對範例案例，請參閱 <a href="/microsoftteams/tutorial-network-planner-example">使用網路規劃工具 - 範例案例</a>。</span><span class="sxs-lookup"><span data-stu-id="7de6e-152">For an example scenario, see <a href="/microsoftteams/tutorial-network-planner-example">Using Network Planner - example scenario</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7de6e-153">Teams 顧問</span><span class="sxs-lookup"><span data-stu-id="7de6e-153">Advisor for Teams</span></span></td>
<td><span data-ttu-id="7de6e-154"><a href="/microsoftteams/use-advisor-teams-roll-out">Teams 的顧問</a> 是 <a href="https://admin.teams.microsoft.com">Teams 系統管理中心的一部分</a>。</span><span class="sxs-lookup"><span data-stu-id="7de6e-154"><a href="/microsoftteams/use-advisor-teams-roll-out">Advisor for Teams</a> is part of the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="7de6e-155">在您成功推出 Teams 前，它會評估您的 Microsoft 365 或 Office 365 環境，找出可能需要更新或修改的最常用設定。</span><span class="sxs-lookup"><span data-stu-id="7de6e-155">It assesses your Microsoft 365 or Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7de6e-156">外部名稱解析</span><span class="sxs-lookup"><span data-stu-id="7de6e-156">External Name Resolution</span></span></td>
<td><span data-ttu-id="7de6e-157">請確定執行 Teams 用戶端的所有電腦都可以解決外部 DNS 查詢，以探索 Microsoft 365 或 Office 365 所提供的服務，而且您的防火牆並未阻止存取。</span><span class="sxs-lookup"><span data-stu-id="7de6e-157">Be sure that all computers running the Teams client can resolve external DNS queries to discover the services provided by Microsoft 365 or Office 365 and that your firewalls are not preventing access.</span></span> <span data-ttu-id="7de6e-158">若要瞭解防火牆埠的組組資訊，請前往 <a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 和 Office 365 URL 和 IP 範圍</a>。</span><span class="sxs-lookup"><span data-stu-id="7de6e-158">For information about configuring firewall ports, go to <a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 and Office 365 URLs and IP ranges</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7de6e-159">維持會話持續性</span><span class="sxs-lookup"><span data-stu-id="7de6e-159">Maintain session persistence</span></span></td>
<td><span data-ttu-id="7de6e-160">請確定防火牆不會變更對應網路位址翻譯 (UDP) 位址或埠。</span><span class="sxs-lookup"><span data-stu-id="7de6e-160">Make sure your firewall doesn't change the mapped Network Address Translation (NAT) addresses or ports for UDP.</span></span></td>
</tr><tr class="odd">
<td><span data-ttu-id="7de6e-161">驗證 NAT 資料庫大小</span><span class="sxs-lookup"><span data-stu-id="7de6e-161">Validate NAT pool size</span></span></td>
<td><span data-ttu-id="7de6e-162">驗證網路位址翻譯 (NAT) 使用者連接所需的資料庫大小。</span><span class="sxs-lookup"><span data-stu-id="7de6e-162">Validate the network address translation (NAT) pool size required for user connectivity.</span></span> <span data-ttu-id="7de6e-163">當多個使用者和裝置使用網路位址翻譯 (NAT) 或埠位址翻譯 <a href="/office365/enterprise/nat-support-with-office-365"> (PAT) </a>存取 Microsoft 365 或 Office 365 時，您必須確保隱藏在每個公開可路由 IP 位址後面的裝置不會超過支援的數量。</span><span class="sxs-lookup"><span data-stu-id="7de6e-163">When multiple users and devices access Microsoft 365 or Office 365 using <a href="/office365/enterprise/nat-support-with-office-365">Network Address Translation (NAT) or Port Address Translation (PAT)</a>, you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span> <span data-ttu-id="7de6e-164">確保將適當的公用 IP 位址指派給 NAT 資料庫，以防止埠用盡。</span><span class="sxs-lookup"><span data-stu-id="7de6e-164">Ensure that adequate public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="7de6e-165">埠用盡會導致內部使用者和裝置無法連接到 Microsoft 365 或 Office 365 服務。</span><span class="sxs-lookup"><span data-stu-id="7de6e-165">Port exhaustion will contribute to internal users and devices being unable to connect to the Microsoft 365 or Office 365 service.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7de6e-166">路由至 Microsoft 資料中心</span><span class="sxs-lookup"><span data-stu-id="7de6e-166">Routing to Microsoft data centers</span></span></td>
<td><span data-ttu-id="7de6e-167"><a href="/office365/enterprise/client-connectivity">以最有效率的方式路由至 Microsoft 資料中心</a>。</span><span class="sxs-lookup"><span data-stu-id="7de6e-167"><a href="/office365/enterprise/client-connectivity">Implement the most efficient routing to Microsoft data centers</a>.</span></span> <span data-ttu-id="7de6e-168">找出可使用當地或地區出口點盡可能有效率地連接到 Microsoft 網路的位置。</span><span class="sxs-lookup"><span data-stu-id="7de6e-168">Identify locations that can use local or regional egress points to connect to the Microsoft network as efficiently as possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7de6e-169">入侵偵測與防護指南</span><span class="sxs-lookup"><span data-stu-id="7de6e-169">Intrusion Detection and Prevention Guidance</span></span></td>
<td><span data-ttu-id="7de6e-170">如果您的環境已部署入侵<a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools"></a>偵測或防護系統 (IDS/IPS) ，為出站連接部署額外一層安全性，請務必允許所有 Microsoft 365 或 Office 365 URL。</span><span class="sxs-lookup"><span data-stu-id="7de6e-170">If your environment has an <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Intrusion Detection</a> or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, be sure to allow all Microsoft 365 or Office 365 URLs.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7de6e-171">設定分割線 VPN</span><span class="sxs-lookup"><span data-stu-id="7de6e-171">Configure split-tunnel VPN</span></span></td>
<td><p><span data-ttu-id="7de6e-172">我們建議您為 Teams 流量提供替代路徑，以避開虛擬私人網路絡或 VPN (VPN) 通常稱為<a href="/windows/security/identity-protection/vpn/vpn-routing">分割式 VPN。</a></span><span class="sxs-lookup"><span data-stu-id="7de6e-172">We recommend that you provide an alternate path for Teams traffic that bypasses the virtual private network (VPN), commonly known as <a href="/windows/security/identity-protection/vpn/vpn-routing">split-tunnel VPN</a>.</span></span> <span data-ttu-id="7de6e-173">分割管道表示 Microsoft 365 或 Office 365 的流量不會經過 VPN，而是直接進入 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="7de6e-173">Split tunneling means that traffic for Microsoft 365 or Office 365 doesn't go through the VPN but instead goes directly to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="7de6e-174">忽略您的 VPN 將會對 Teams 品質產生正面影響，而且會減少 VPN 裝置和組織網路的負載。</span><span class="sxs-lookup"><span data-stu-id="7de6e-174">Bypassing your VPN will have a positive impact on Teams quality, and it reduces load from the VPN devices and the organization's network.</span></span> <span data-ttu-id="7de6e-175">若要執行分割式 VPN，請與 VPN 廠商合作。</span><span class="sxs-lookup"><span data-stu-id="7de6e-175">To implement a split-tunnel VPN, work with your VPN vendor.</span></span></p>
<p><span data-ttu-id="7de6e-176">建議忽略 VPN 的其他原因：</span><span class="sxs-lookup"><span data-stu-id="7de6e-176">Other reasons why we recommend bypassing the VPN:</span></span>
<ul>
<li><p><span data-ttu-id="7de6e-177">VPN 通常未設計或配置為支援即時媒體。</span><span class="sxs-lookup"><span data-stu-id="7de6e-177">VPNs are typically not designed or configured to support real-time media.</span></span></p></li> 
<li><p><span data-ttu-id="7de6e-178">某些 VPN 可能也不支援 Teams (所需的 UDP) 。</span><span class="sxs-lookup"><span data-stu-id="7de6e-178">Some VPNs might also not support UDP (which is required for Teams).</span></span></p></li> 
<li><p><span data-ttu-id="7de6e-179">VPN 也會在已加密的媒體流量上引入額外的加密層。</span><span class="sxs-lookup"><span data-stu-id="7de6e-179">VPNs also introduce an extra layer of encryption on top of media traffic that's already encrypted.</span></span></p></li> 
<li><p><span data-ttu-id="7de6e-180">透過 VPN 裝置將流量釘在一起，因此與 Teams 的連接可能沒有效率。</span><span class="sxs-lookup"><span data-stu-id="7de6e-180">Connectivity to Teams might not be efficient due to hair-pinning traffic through a VPN device.</span></span></p></li></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7de6e-181">實現 QoS</span><span class="sxs-lookup"><span data-stu-id="7de6e-181">Implement QoS</span></span></td>
<td><span data-ttu-id="7de6e-182"><a href="/microsoftteams/qos-in-teams">使用 QoS (服務品質) </a> 設定封包優先順序。</span><span class="sxs-lookup"><span data-stu-id="7de6e-182"><a href="/microsoftteams/qos-in-teams">Use Quality of Service (QoS)</a> to configure packet prioritization.</span></span> <span data-ttu-id="7de6e-183">這將改善 Teams 中的通話品質，並説明您監控和疑難排解通話品質。</span><span class="sxs-lookup"><span data-stu-id="7de6e-183">This will improve call quality in Teams and help you monitor and troubleshoot call quality.</span></span> <span data-ttu-id="7de6e-184">QoS 應在受管理網路的所有區段上執行。</span><span class="sxs-lookup"><span data-stu-id="7de6e-184">QoS should be implemented on all segments of a managed network.</span></span> <span data-ttu-id="7de6e-185">即使網路已充分配置頻寬，QoS 在發生非意外的網路事件時，也能夠降低風險。</span><span class="sxs-lookup"><span data-stu-id="7de6e-185">Even when a network has been adequately provisioned for bandwidth, QoS provides risk mitigation in the event of unanticipated network events.</span></span> <span data-ttu-id="7de6e-186">使用 QoS 時，語音流量會優先處理，這樣這些非意外的事件不會對品質造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="7de6e-186">With QoS, voice traffic is prioritized so that these unanticipated events don't negatively affect quality.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7de6e-187">優化 WiFi</span><span class="sxs-lookup"><span data-stu-id="7de6e-187">Optimize WiFi</span></span></td>
<td><p><span data-ttu-id="7de6e-188">與 VPN 類似，WiFi 網路不一定要經過設計或配置，以支援即時媒體。</span><span class="sxs-lookup"><span data-stu-id="7de6e-188">Similar to VPN, WiFi networks aren't necessarily designed or configured to support real-time media.</span></span> <span data-ttu-id="7de6e-189">規劃或優化支援 Teams 的 WiFi 網路是高品質部署的重要考慮。</span><span class="sxs-lookup"><span data-stu-id="7de6e-189">Planning for, or optimizing, a WiFi network to support Teams is an important consideration for a high-quality deployment.</span></span> <span data-ttu-id="7de6e-190">請考慮以下因素：</span><span class="sxs-lookup"><span data-stu-id="7de6e-190">Consider these factors:</span></span></p>
<ul>
<li><p><span data-ttu-id="7de6e-191">在 WMM 中 (QoS 或 WiFi 多媒體) ，以確保媒體流量在 WiFi 網路上獲得適當的優先順序。</span><span class="sxs-lookup"><span data-stu-id="7de6e-191">Implement QoS or WiFi Multimedia (WMM) to ensure that media traffic is getting prioritized appropriately over your WiFi networks.</span></span></p></li>
<li><p><span data-ttu-id="7de6e-192">規劃並優化 WiFi 頻帶和存取點位置。</span><span class="sxs-lookup"><span data-stu-id="7de6e-192">Plan and optimize the WiFi bands and access point placement.</span></span> <span data-ttu-id="7de6e-193">2.4 GHz 範圍可能會根據訪問點位置提供適當的體驗，但訪問點通常會受到該範圍內運作的其他消費者裝置影響。</span><span class="sxs-lookup"><span data-stu-id="7de6e-193">The 2.4 GHz range might provide an adequate experience depending on access point placement, but access points are often affected by other consumer devices that operate in that range.</span></span> <span data-ttu-id="7de6e-194">5 GHz 範圍較適合即時媒體，因為範圍較廣，但需要更多存取點才能獲得足夠的覆蓋。</span><span class="sxs-lookup"><span data-stu-id="7de6e-194">The 5 GHz range is better suited to real-time media due to its dense range, but it requires more access points to get sufficient coverage.</span></span> <span data-ttu-id="7de6e-195">端點也需要支援該範圍，並據此進行配置以運用這些頻帶。</span><span class="sxs-lookup"><span data-stu-id="7de6e-195">Endpoints also need to support that range and be configured to leverage those bands accordingly.</span></span></p></li>
<li><p><span data-ttu-id="7de6e-196">如果您使用的是雙頻 WiFi 網路，請考慮使用帶式轉向。</span><span class="sxs-lookup"><span data-stu-id="7de6e-196">If you're using dual-band WiFi networks, consider implementing band steering.</span></span> <span data-ttu-id="7de6e-197"><em>頻帶轉向</em> 是 WiFi 廠商所執行的一項技術，可影響雙頻用戶端使用 5 GHz 範圍。</span><span class="sxs-lookup"><span data-stu-id="7de6e-197"><em>Band steering</em> is a technique implemented by WiFi vendors to influence dual-band clients to use the 5 GHz range.</span></span></p></li>
<li><p><span data-ttu-id="7de6e-198">當同一個通道的存取點太接近時，可能會導致訊號重迭，以及不小心相互競爭，給使用者造成不良的體驗。</span><span class="sxs-lookup"><span data-stu-id="7de6e-198">When access points of the same channel are too close together, they can cause signal overlap and unintentionally compete, resulting in a bad experience for the user.</span></span> <span data-ttu-id="7de6e-199">請確保彼此旁邊的訪問點位於不重迭的頻道上。</span><span class="sxs-lookup"><span data-stu-id="7de6e-199">Ensure that access points that are next to each other are on channels that don't overlap.</span></span></p></li>
</ul>
<p><span data-ttu-id="7de6e-200">每個無線廠商都有自己的無線解決方案部署建議。</span><span class="sxs-lookup"><span data-stu-id="7de6e-200">Each wireless vendor has its own recommendations for deploying its wireless solution.</span></span> <span data-ttu-id="7de6e-201">請查閱您的 WiFi 廠商以尋求特定指引。</span><span class="sxs-lookup"><span data-stu-id="7de6e-201">Consult your WiFi vendor for specific guidance.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a><span data-ttu-id="7de6e-202">頻寬需求</span><span class="sxs-lookup"><span data-stu-id="7de6e-202">Bandwidth requirements</span></span>

<span data-ttu-id="7de6e-203">無論您的網路條件如何，Teams 都能提供最佳的音訊、視像和內容共用體驗。</span><span class="sxs-lookup"><span data-stu-id="7de6e-203">Teams is designed to give the best audio, video, and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="7de6e-204">也就是說，當頻寬不足時，Teams 會優先處理音訊品質與視音訊品質。</span><span class="sxs-lookup"><span data-stu-id="7de6e-204">That said, when bandwidth is insufficient, Teams prioritizes audio quality over video quality.</span></span>

<span data-ttu-id="7de6e-205">在頻寬沒有限制的地方，Teams 會優化媒體質量，包括高達 1080p 影片解析度、最多 30fps 視音訊和 15fps 內容，以及高逼真度音訊。</span><span class="sxs-lookup"><span data-stu-id="7de6e-205">Where bandwidth *isn't* limited, Teams optimizes media quality, including up to 1080p video resolution, up to 30fps for video and 15fps for content, and high-fidelity audio.</span></span> 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a><span data-ttu-id="7de6e-206">相關主題</span><span class="sxs-lookup"><span data-stu-id="7de6e-206">Related Topics</span></span>

[<span data-ttu-id="7de6e-207">Microsoft 365 和 Office 365 網路連接原則</span><span class="sxs-lookup"><span data-stu-id="7de6e-207">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[<span data-ttu-id="7de6e-208">全球端點：商務用 Skype Online 和 Teams</span><span class="sxs-lookup"><span data-stu-id="7de6e-208">Worldwide endpoints: Skype for Business Online and Teams</span></span>](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[<span data-ttu-id="7de6e-209">Teams 的 Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="7de6e-209">Proxy servers for Teams</span></span>](proxy-servers-for-skype-for-business-online.md)

[<span data-ttu-id="7de6e-210">Teams 中的媒體：為什麼會議簡單</span><span class="sxs-lookup"><span data-stu-id="7de6e-210">Media in Teams: Why meetings are simple</span></span>](https://aka.ms/teams-media)

[<span data-ttu-id="7de6e-211">Teams 中的媒體：深入探討媒體流程</span><span class="sxs-lookup"><span data-stu-id="7de6e-211">Media in Teams: Deep dive into media flows</span></span>](https://aka.ms/teams-media-flows)

[<span data-ttu-id="7de6e-212">Teams 中的身分識別和驗證</span><span class="sxs-lookup"><span data-stu-id="7de6e-212">Identity models and authentication in Teams</span></span>](identify-models-authentication.md)

[<span data-ttu-id="7de6e-213">如何推出 Teams</span><span class="sxs-lookup"><span data-stu-id="7de6e-213">How to roll out Teams</span></span>](./deploy-overview.md)

[<span data-ttu-id="7de6e-214">Teams 疑難排解</span><span class="sxs-lookup"><span data-stu-id="7de6e-214">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)