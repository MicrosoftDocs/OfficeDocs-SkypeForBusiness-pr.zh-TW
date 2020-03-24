---
title: 針對 Microsoft Teams 準備組織的網路
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: 在您推出 Microsoft 團隊前，請先評估並準備您的網路，以確定它已準備好供團隊使用。 資訊包括網路需求、頻寬需求和網路優化指導方針。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: d85bb4ba32bf83d3c774a2b6700a96c7e35dcb2a
ms.sourcegitcommit: 545e466f1fa9163bb00cc96c8db70a70b02af697
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "42935240"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="978b0-104">針對 Microsoft Teams 準備組織的網路</span><span class="sxs-lookup"><span data-stu-id="978b0-104">Prepare your organization's network for Microsoft Teams</span></span> 

## <a name="network-requirements"></a><span data-ttu-id="978b0-105">網路需求</span><span class="sxs-lookup"><span data-stu-id="978b0-105">Network requirements</span></span>

<span data-ttu-id="978b0-106">如果您已經針對[Office 365 優化您的網路](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity)，您可能已經準備好開始進行 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="978b0-106">If you've already [optimized your network for Office 365](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity), you're probably ready for Microsoft Teams.</span></span> <span data-ttu-id="978b0-107">在任何情況下，特別是如果您是在第一個 Office 365 工作負載中快速推出團隊以支援**遠端工作人員**，請先檢查下列專案，然後再開始進行團隊推出：</span><span class="sxs-lookup"><span data-stu-id="978b0-107">In any case - and especially if you're rolling out Teams quickly as your first Office 365 workload to support **remote workers** - check the following before you begin your Teams rollout:</span></span>

1.  <span data-ttu-id="978b0-108">您所有的位置都有網際網路存取權（讓他們可以連線到 Office 365）嗎？</span><span class="sxs-lookup"><span data-stu-id="978b0-108">Do all your locations have internet access (so they can connect to Office 365)?</span></span> <span data-ttu-id="978b0-109">除了標準的網路流量之外，請確定您已針對團隊中的媒體開啟下列專案（適用于所有位置）：</span><span class="sxs-lookup"><span data-stu-id="978b0-109">At a minimum, in addition to normal web traffic, make sure you've opened the following, for all locations, for media in Teams:</span></span>

    |  |  |
    |---------|---------|
    |<span data-ttu-id="978b0-110">埠</span><span class="sxs-lookup"><span data-stu-id="978b0-110">Ports</span></span>     |<span data-ttu-id="978b0-111">UDP 埠<strong>3478</strong>到<strong>3481</strong></span><span class="sxs-lookup"><span data-stu-id="978b0-111">UDP ports <strong>3478</strong> through <strong>3481</strong></span></span>        |
    |[<span data-ttu-id="978b0-112">IP 位址</span><span class="sxs-lookup"><span data-stu-id="978b0-112">IP addresses</span></span>](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<span data-ttu-id="978b0-113"><strong>13.107.64.0/18</strong>和<strong>52.112.0.0/14</strong></span><span class="sxs-lookup"><span data-stu-id="978b0-113"><strong>13.107.64.0/18</strong> and <strong>52.112.0.0/14</strong></span></span>        |
    
2.  <span data-ttu-id="978b0-114">您有 Office 365 的驗證網域（例如，contoso.com）嗎？</span><span class="sxs-lookup"><span data-stu-id="978b0-114">Do you have a verified domain for Office 365 (for example, contoso.com)?</span></span>
    
      - <span data-ttu-id="978b0-115">如果您的組織尚未推出 Office 365，請參閱[商務用 Office 365 快速入門](https://docs.microsoft.com/office365/admin/admin-overview/get-started-with-office-365)。</span><span class="sxs-lookup"><span data-stu-id="978b0-115">If your organization hasn't rolled out Office 365, see [Getting Started with Office 365 for business](https://docs.microsoft.com/office365/admin/admin-overview/get-started-with-office-365).</span></span>
      - <span data-ttu-id="978b0-116">如果您的組織尚未新增或設定 Office 365 的驗證網域，請參閱[驗證您的 office 365 網域](https://docs.microsoft.com/office365/admin/setup/domains-faq)。</span><span class="sxs-lookup"><span data-stu-id="978b0-116">If your organization hasn't added or configured a verified domain for Office 365, see [Verify your Office 365 domain](https://docs.microsoft.com/office365/admin/setup/domains-faq).</span></span>

3.  <span data-ttu-id="978b0-117">貴組織已部署 Exchange Online 和 SharePoint Online 嗎？</span><span class="sxs-lookup"><span data-stu-id="978b0-117">Has your organization deployed Exchange Online and SharePoint Online?</span></span>
    
      - <span data-ttu-id="978b0-118">如果您的組織沒有 Exchange Online，請參閱[瞭解 exchange 與 Microsoft 團隊互動的方式](exchange-teams-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="978b0-118">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](exchange-teams-interact.md).</span></span>
      - <span data-ttu-id="978b0-119">如果您的組織沒有 SharePoint Online，請參閱[瞭解 Sharepoint online 與商務用 OneDrive 與 Microsoft 團隊互動的方式](sharepoint-onedrive-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="978b0-119">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

<span data-ttu-id="978b0-120">確認符合這些網路需求之後，您就可以準備好要[推出小組](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="978b0-120">Once you've verified that you meet these network requirements, you may be ready to [Roll out Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="978b0-121">如果您是大型的跨國公司，或者如果您知道您有一些網路限制，請繼續閱讀以瞭解如何為團隊評估及優化您的網路。</span><span class="sxs-lookup"><span data-stu-id="978b0-121">If you're a large multinational enterprise, or if you know you've got some network limitations, read on to learn how to assess and optimize your network for Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="978b0-122">**針對教育機構**：如果您的組織是教育機構，且您是使用學生資訊系統（SIS），請先[部署學校資料同步](https://docs.microsoft.com/schooldatasync/)處理，然後再將團隊推出。</span><span class="sxs-lookup"><span data-stu-id="978b0-122">**For educational institutions**: If your organization is an educational institution and you use a Student Information System (SIS), [deploy School Data Sync](https://docs.microsoft.com/schooldatasync/) before you roll out Teams.</span></span>
>  
> <span data-ttu-id="978b0-123">執行**內部部署商務用 Skype server**：如果您的組織正在執行內部部署商務用 skype 伺服器（或 Lync Server），您必須[設定 Azure AD Connect](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect) ，才能將您的內部部署目錄與 Office 365 同步處理。</span><span class="sxs-lookup"><span data-stu-id="978b0-123">**Running on-premises Skype for Business Server**: If your organization is running on-premises Skype for Business Server (or Lync Server), you must [configure Azure AD Connect](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect) to synchronize your on-premises directory with Office 365.</span></span>

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a><span data-ttu-id="978b0-124">最佳做法：使用 CQD 和通話分析監控您的網路</span><span class="sxs-lookup"><span data-stu-id="978b0-124">Best practice: Monitor your network using CQD and call analytics</span></span> 

<span data-ttu-id="978b0-125">使用[通話品質儀表板（CQD）](turning-on-and-using-call-quality-dashboard.md) ，深入瞭解團隊中的通話和會議品質。</span><span class="sxs-lookup"><span data-stu-id="978b0-125">Use the [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to gain insight into the quality of calls and meetings in Teams.</span></span> <span data-ttu-id="978b0-126">CQD 可協助您保持密切留意品質、可靠性和使用者體驗，以協助您優化網路。</span><span class="sxs-lookup"><span data-stu-id="978b0-126">CQD can help you optimize your network by keeping a close eye on quality, reliability, and the user experience.</span></span> <span data-ttu-id="978b0-127">CQD 會在整個組織中查看匯總遙測，在這種情況下，整體模式會變得明顯，讓您找出問題並規劃修正。</span><span class="sxs-lookup"><span data-stu-id="978b0-127">CQD looks at aggregate telemetry for an entire organization where overall patterns can become apparent, which lets you identify problems and plan remediation.</span></span> <span data-ttu-id="978b0-128">此外，CQD 提供豐富的度量報告，可讓您深入瞭解整體品質、可靠性及使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="978b0-128">Additionally, CQD provides rich metrics reports that provide insight into overall quality, reliability, and user experience.</span></span> 

<span data-ttu-id="978b0-129">您將使用[呼叫分析](set-up-call-analytics.md)來調查個別使用者的通話與會議問題。</span><span class="sxs-lookup"><span data-stu-id="978b0-129">You'll use [call analytics](set-up-call-analytics.md) to investigate call and meeting problems for an individual user.</span></span>

## <a name="network-optimization"></a><span data-ttu-id="978b0-130">網路優化</span><span class="sxs-lookup"><span data-stu-id="978b0-130">Network optimization</span></span>

<span data-ttu-id="978b0-131">如果您是小型企業版且已推出 Office 365，則下列工作是選擇性的，而且不是必要的。</span><span class="sxs-lookup"><span data-stu-id="978b0-131">The following tasks are optional and aren't required for rolling out Teams, especially if you're a small business and you've already rolled out Office 365.</span></span> <span data-ttu-id="978b0-132">使用本指導方針來優化您的網路與團隊效能，或者您知道您有一些網路限制。</span><span class="sxs-lookup"><span data-stu-id="978b0-132">Use this guidance to optimize your network and Teams performance or if you know you've got some network limitations.</span></span>

<span data-ttu-id="978b0-133">在下列情況中，您可能會想要執行額外的網路優化動作：</span><span class="sxs-lookup"><span data-stu-id="978b0-133">You might want to do additional network optimization if:</span></span>

  - <span data-ttu-id="978b0-134">團隊執行緩慢（可能是您的頻寬不夠用）</span><span class="sxs-lookup"><span data-stu-id="978b0-134">Teams runs slowly (maybe you have insufficient bandwidth)</span></span>
  - <span data-ttu-id="978b0-135">呼叫繼續放下（可能是防火牆或 proxy 攔截程式所致）</span><span class="sxs-lookup"><span data-stu-id="978b0-135">Calls keep dropping (might be due to firewall or proxy blockers)</span></span>
  - <span data-ttu-id="978b0-136">呼叫是靜態 y、剪取，或像是機器人的語音音效（可能是抖動或資料包遺失）</span><span class="sxs-lookup"><span data-stu-id="978b0-136">Calls are static-y and cut out, or voices sound like robots (could be jitter or packet loss)</span></span>

<span data-ttu-id="978b0-137">如需網路優化的深入討論，包括識別及修正網路障礙的指導方針，請參閱[Office 365 網路連接原則](https://aka.ms/pnc)。</span><span class="sxs-lookup"><span data-stu-id="978b0-137">For an in-depth discussion of network optimization, including guidance for identifying and fixing network impairments, read [Office 365 Network Connectivity Principles](https://aka.ms/pnc).</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="978b0-138"><strong>網路優化工作</strong></span><span class="sxs-lookup"><span data-stu-id="978b0-138"><strong>Network optimization task</strong></span></span></th>
<th><span data-ttu-id="978b0-139"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="978b0-139"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="978b0-140">網路 planner</span><span class="sxs-lookup"><span data-stu-id="978b0-140">Network planner</span></span></td>
<td><p><span data-ttu-id="978b0-141">如需評估網路的協助，包括貴組織之物理位置的頻寬計算和網路需求，請查看 [<a href="https://admin.teams.microsoft.com">小組管理中心</a>] 中的 [<a href="https://docs.microsoft.com/microsoftteams/network-planner">網路 Planner</a>工具]。</span><span class="sxs-lookup"><span data-stu-id="978b0-141">For help assessing your network, including bandwidth calculations and network requirements across your org's physical locations, check out the <a href="https://docs.microsoft.com/microsoftteams/network-planner">Network Planner</a> tool, in the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="978b0-142">當您提供您的網路詳細資料和團隊使用量時，網路 Planner 會計算您的網路需求，以便在整個組織的物理位置部署團隊和雲端語音。</span><span class="sxs-lookup"><span data-stu-id="978b0-142">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span></p>
<p><span data-ttu-id="978b0-143">如需範例案例，請參閱<a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">使用網路 Planner-範例案例</a>。</span><span class="sxs-lookup"><span data-stu-id="978b0-143">For an example scenario, see <a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">Using Network Planner - example scenario</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="978b0-144">團隊顧問</span><span class="sxs-lookup"><span data-stu-id="978b0-144">Advisor for Teams</span></span></td>
<td><span data-ttu-id="978b0-145"><a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">團隊的 Advisor</a>是<a href="https://admin.teams.microsoft.com">團隊系統管理中心</a>的一部分。</span><span class="sxs-lookup"><span data-stu-id="978b0-145"><a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">Advisor for Teams</a> is part of the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="978b0-146">在您成功推出 Teams 前，它會評估您的 Office 365 環境，找出可能需要更新或修改的最常用設定。</span><span class="sxs-lookup"><span data-stu-id="978b0-146">It assesses your Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="978b0-147">外部名稱解析</span><span class="sxs-lookup"><span data-stu-id="978b0-147">External Name Resolution</span></span></td>
<td><span data-ttu-id="978b0-148">請確定執行團隊用戶端的所有電腦都可以解析外部 DNS 查詢，以探索 Office 365 提供的服務，而且您的防火牆不會防止存取。</span><span class="sxs-lookup"><span data-stu-id="978b0-148">Be sure that all computers running the Teams client can resolve external DNS queries to discover the services provided by Office 365 and that your firewalls are not preventing access.</span></span> <span data-ttu-id="978b0-149">如需設定防火牆埠的相關資訊，請移至<a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">Office 365 url 與 IP 範圍</a>。</span><span class="sxs-lookup"><span data-stu-id="978b0-149">For information about configuring firewall ports, go to <a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">Office 365 URLs and IP ranges</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="978b0-150">驗證（NAT）池子大小</span><span class="sxs-lookup"><span data-stu-id="978b0-150">Validate (NAT) pool size</span></span></td>
<td><span data-ttu-id="978b0-151">驗證使用者連線所需的網路位址轉譯（NAT）池大小。</span><span class="sxs-lookup"><span data-stu-id="978b0-151">Validate the network address translation (NAT) pool size required for user connectivity.</span></span> <span data-ttu-id="978b0-152">當多個使用者和裝置使用<a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">網路位址轉譯（NAT）或埠位址轉換（PAT）</a>存取 Office 365 時，您必須確保隱藏在每個公開路由的 IP 位址後面的裝置不會超過支援的號碼。</span><span class="sxs-lookup"><span data-stu-id="978b0-152">When multiple users and devices access Office 365 using <a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">Network Address Translation (NAT) or Port Address Translation (PAT)</a>, you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span> <span data-ttu-id="978b0-153">確保已將足夠的公用 IP 位址指派給 NAT 池，以避免埠耗盡。</span><span class="sxs-lookup"><span data-stu-id="978b0-153">Ensure that adequate public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="978b0-154">埠耗盡會影響內部使用者和裝置無法連線至 Office 365 服務的情況。</span><span class="sxs-lookup"><span data-stu-id="978b0-154">Port exhaustion will contribute to internal users and devices being unable to connect to the Office 365 service.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="978b0-155">路由至 Microsoft 資料中心</span><span class="sxs-lookup"><span data-stu-id="978b0-155">Routing to Microsoft data centers</span></span></td>
<td><span data-ttu-id="978b0-156"><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">實施最有效率的路由至 Microsoft 資料中心</a>。</span><span class="sxs-lookup"><span data-stu-id="978b0-156"><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">Implement the most efficient routing to Microsoft data centers</a>.</span></span> <span data-ttu-id="978b0-157">找出可使用當地或地區出口點數盡可能高效地連線至 Microsoft 網路的位置。</span><span class="sxs-lookup"><span data-stu-id="978b0-157">Identify locations that can use local or regional egress points to connect to the Microsoft network as efficiently as possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="978b0-158">入侵偵測與防範指導方針</span><span class="sxs-lookup"><span data-stu-id="978b0-158">Intrusion Detection and Prevention Guidance</span></span></td>
<td><span data-ttu-id="978b0-159">如果您的環境針對外寄連線的安全層級部署了<a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">入侵偵測</a>或防護系統（IDS/IPS），請務必將所有 Office 365 url 加上白名單。</span><span class="sxs-lookup"><span data-stu-id="978b0-159">If your environment has an <a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Intrusion Detection</a> or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, be sure to whitelist all Office 365 URLs.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="978b0-160">設定分割隧道 VPN</span><span class="sxs-lookup"><span data-stu-id="978b0-160">Configure split-tunnel VPN</span></span></td>
<td><p><span data-ttu-id="978b0-161">我們建議您為小組流量提供備用路徑，這種方法會繞過虛擬私人網路（VPN），通常稱為[分割隧道 VPN](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing)。</span><span class="sxs-lookup"><span data-stu-id="978b0-161">We recommend that you provide an alternate path for Teams traffic that bypasses the virtual private network (VPN), commonly known as [split-tunnel VPN](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing).</span></span> <span data-ttu-id="978b0-162">分割隧道表示 Office 365 的流量不會透過 VPN，而是直接移至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="978b0-162">Split tunneling means that traffic for Office 365 doesn't go through the VPN but instead goes directly to Office 365.</span></span> <span data-ttu-id="978b0-163">略過您的 VPN 會對團隊品質產生正面影響，並減少從 VPN 裝置與組織網路的載入。</span><span class="sxs-lookup"><span data-stu-id="978b0-163">Bypassing your VPN will have a positive impact on Teams quality, and it reduces load from the VPN devices and the organization's network.</span></span> <span data-ttu-id="978b0-164">若要實現分割隧道 VPN，請與您的 VPN 廠商合作。</span><span class="sxs-lookup"><span data-stu-id="978b0-164">To implement a split-tunnel VPN, work with your VPN vendor.</span></span></p>
<p><span data-ttu-id="978b0-165">我們建議您避開 VPN 的其他原因：</span><span class="sxs-lookup"><span data-stu-id="978b0-165">Other reasons why we recommend bypassing the VPN:</span></span>
<ul>
<li><p><span data-ttu-id="978b0-166">Vpn 通常不會設計或設定為支援即時媒體。</span><span class="sxs-lookup"><span data-stu-id="978b0-166">VPNs are typically not designed or configured to support real-time media.</span></span></p></li> 
<li><p><span data-ttu-id="978b0-167">某些 Vpn 可能也不支援 UDP （這是小組所需要的）。</span><span class="sxs-lookup"><span data-stu-id="978b0-167">Some VPNs might also not support UDP (which is required for Teams).</span></span></p></li> 
<li><p><span data-ttu-id="978b0-168">Vpn 也會在已加密的媒體流量上方引入額外的加密層級。</span><span class="sxs-lookup"><span data-stu-id="978b0-168">VPNs also introduce an extra layer of encryption on top of media traffic that's already encrypted.</span></span></p></li> 
<li><p><span data-ttu-id="978b0-169">由於將流量釘選到 VPN 裝置上，因此可能無法有效地連接至團隊。</span><span class="sxs-lookup"><span data-stu-id="978b0-169">Connectivity to Teams might not be efficient due to hair-pinning traffic through a VPN device.</span></span></p></li></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="978b0-170">實施 QoS</span><span class="sxs-lookup"><span data-stu-id="978b0-170">Implement QoS</span></span></td>
<td><span data-ttu-id="978b0-171"><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">使用服務品質（QoS）</a>來設定資料包優先順序。</span><span class="sxs-lookup"><span data-stu-id="978b0-171"><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">Use Quality of Service (QoS)</a> to configure packet prioritization.</span></span> <span data-ttu-id="978b0-172">這將改善團隊中的通話品質，並協助您監控通話品質並進行問題的疑難排解。</span><span class="sxs-lookup"><span data-stu-id="978b0-172">This will improve call quality in Teams and help you monitor and troubleshoot call quality.</span></span> <span data-ttu-id="978b0-173">QoS 應該在受管理的網路的所有區段上執行。</span><span class="sxs-lookup"><span data-stu-id="978b0-173">QoS should be implemented on all segments of a managed network.</span></span> <span data-ttu-id="978b0-174">即使已針對頻寬充分提供網路，QoS 也會在事件發生時，在發生意外的網路事件時，降低風險。</span><span class="sxs-lookup"><span data-stu-id="978b0-174">Even when a network has been adequately provisioned for bandwidth, QoS provides risk mitigation in the event of unanticipated network events.</span></span> <span data-ttu-id="978b0-175">透過 QoS，語音流量的優先順序會使這些意外事件不會對品質造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="978b0-175">With QoS, voice traffic is prioritized so that these unanticipated events don't negatively affect quality.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="978b0-176">優化 WiFi</span><span class="sxs-lookup"><span data-stu-id="978b0-176">Optimize WiFi</span></span></td>
<td><p><span data-ttu-id="978b0-177">與 VPN 類似，WiFi 網路不一定設計或設定為支援即時媒體。</span><span class="sxs-lookup"><span data-stu-id="978b0-177">Similar to VPN, WiFi networks aren't necessarily designed or configured to support real-time media.</span></span> <span data-ttu-id="978b0-178">規劃或優化 WiFi 網路以支援小組是高品質部署的重要考慮。</span><span class="sxs-lookup"><span data-stu-id="978b0-178">Planning for, or optimizing, a WiFi network to support Teams is an important consideration for a high-quality deployment.</span></span> <span data-ttu-id="978b0-179">請考慮下列因素：</span><span class="sxs-lookup"><span data-stu-id="978b0-179">Consider these factors:</span></span></p>
<ul>
<li><p><span data-ttu-id="978b0-180">實施 QoS 或 WiFi 多媒體（WMM），以確保媒體流量在您的 WiFi 網路上適當地進行優先順序設定。</span><span class="sxs-lookup"><span data-stu-id="978b0-180">Implement QoS or WiFi Multimedia (WMM) to ensure that media traffic is getting prioritized appropriately over your WiFi networks.</span></span></p></li>
<li><p><span data-ttu-id="978b0-181">規劃及優化 WiFi 區段和存取點的位置。</span><span class="sxs-lookup"><span data-stu-id="978b0-181">Plan and optimize the WiFi bands and access point placement.</span></span> <span data-ttu-id="978b0-182">2.4 GHz 範圍可能會根據存取點位置提供適當的體驗，但存取點通常會受到在該範圍中運作的其他消費者裝置的影響。</span><span class="sxs-lookup"><span data-stu-id="978b0-182">The 2.4 GHz range might provide an adequate experience depending on access point placement, but access points are often affected by other consumer devices that operate in that range.</span></span> <span data-ttu-id="978b0-183">5 GHz 的範圍更適合用於即時媒體，因為它有大量的功能，但需要更多存取點才能取得足夠的覆蓋範圍。</span><span class="sxs-lookup"><span data-stu-id="978b0-183">The 5 GHz range is better suited to real-time media due to its dense range, but it requires more access points to get sufficient coverage.</span></span> <span data-ttu-id="978b0-184">端點也需要支援該範圍，並將其設定為可據此加以設定以利用這些區段。</span><span class="sxs-lookup"><span data-stu-id="978b0-184">Endpoints also need to support that range and be configured to leverage those bands accordingly.</span></span></p></li>
<li><p><span data-ttu-id="978b0-185">如果您使用的是雙頻帶 WiFi 網路，請考慮執行頻帶控制。</span><span class="sxs-lookup"><span data-stu-id="978b0-185">If you're using dual-band WiFi networks, consider implementing band steering.</span></span> <span data-ttu-id="978b0-186">[<em>樂隊</em>控制] 是由 WiFi 廠家提供的技術，可影響雙頻帶用戶端使用 5 GHz 範圍。</span><span class="sxs-lookup"><span data-stu-id="978b0-186"><em>Band steering</em> is a technique implemented by WiFi vendors to influence dual-band clients to use the 5 GHz range.</span></span></p></li>
<li><p><span data-ttu-id="978b0-187">當同一個頻道的存取點太靠近時，可能會導致信號重迭，並無意間爭奪，從而導致使用者無法正常使用。</span><span class="sxs-lookup"><span data-stu-id="978b0-187">When access points of the same channel are too close together, they can cause signal overlap and unintentionally compete, resulting in a bad experience for the user.</span></span> <span data-ttu-id="978b0-188">確定彼此連續的存取點位於沒有交疊的頻道上。</span><span class="sxs-lookup"><span data-stu-id="978b0-188">Ensure that access points that are next to each other are on channels that don't overlap.</span></span></p></li>
</ul>
<p><span data-ttu-id="978b0-189">每個無線廠商都有自己的部署其無線解決方案的建議。</span><span class="sxs-lookup"><span data-stu-id="978b0-189">Each wireless vendor has its own recommendations for deploying its wireless solution.</span></span> <span data-ttu-id="978b0-190">請諮詢您的 WiFi 供應商以取得特定指導方針。</span><span class="sxs-lookup"><span data-stu-id="978b0-190">Consult your WiFi vendor for specific guidance.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a><span data-ttu-id="978b0-191">頻寬需求</span><span class="sxs-lookup"><span data-stu-id="978b0-191">Bandwidth requirements</span></span>

<span data-ttu-id="978b0-192">無論您的網路狀況為何，小組都會設計為提供最佳的音訊、影片和內容共用體驗。</span><span class="sxs-lookup"><span data-stu-id="978b0-192">Teams is designed to give the best audio, video, and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="978b0-193">如此一來，當頻寬不足時，小組會將音訊品質與影片品質進行優先順序。</span><span class="sxs-lookup"><span data-stu-id="978b0-193">That said, when bandwidth is insufficient, Teams prioritizes audio quality over video quality.</span></span>

<span data-ttu-id="978b0-194">在頻寬*不*受限制的情況下，小組會優化媒體質量，包括高達1080p 的影片解析度、30fps 影片和15fps 內容，以及高保真音訊。</span><span class="sxs-lookup"><span data-stu-id="978b0-194">Where bandwidth *isn't* limited, Teams optimizes media quality, including up to 1080p video resolution, up to 30fps for video and 15fps for content, and high-fidelity audio.</span></span> 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a><span data-ttu-id="978b0-195">相關主題</span><span class="sxs-lookup"><span data-stu-id="978b0-195">Related Topics</span></span>

[<span data-ttu-id="978b0-196">Office 365 網路連接原則</span><span class="sxs-lookup"><span data-stu-id="978b0-196">Office 365 Network Connectivity Principles</span></span>](https://aka.ms/pnc)

[<span data-ttu-id="978b0-197">全球端點：商務用 Skype Online 與團隊</span><span class="sxs-lookup"><span data-stu-id="978b0-197">Worldwide endpoints: Skype for Business Online and Teams</span></span>](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[<span data-ttu-id="978b0-198">小組的 Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="978b0-198">Proxy servers for Teams</span></span>](proxy-servers-for-skype-for-business-online.md)

[<span data-ttu-id="978b0-199">團隊中的媒體：為什麼會議很簡單</span><span class="sxs-lookup"><span data-stu-id="978b0-199">Media in Teams: Why meetings are simple</span></span>](https://aka.ms/teams-media)

[<span data-ttu-id="978b0-200">團隊中的媒體：深入瞭解媒體流程</span><span class="sxs-lookup"><span data-stu-id="978b0-200">Media in Teams: Deep dive into media flows</span></span>](https://aka.ms/teams-media-flows)

[<span data-ttu-id="978b0-201">Teams 中的身分識別和驗證</span><span class="sxs-lookup"><span data-stu-id="978b0-201">Identity models and authentication in Teams</span></span>](identify-models-authentication.md)

[<span data-ttu-id="978b0-202">如何推出 Teams</span><span class="sxs-lookup"><span data-stu-id="978b0-202">How to roll out Teams</span></span>](How-to-roll-out-teams.md)


