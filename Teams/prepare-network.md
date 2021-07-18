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
ms.openlocfilehash: db911db3631caebb0e767401f80c36bdac6c9c1b
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420828"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="f8cc1-103">針對 Microsoft Teams 準備組織的網路</span><span class="sxs-lookup"><span data-stu-id="f8cc1-103">Prepare your organization's network for Microsoft Teams</span></span> 

## <a name="network-requirements"></a><span data-ttu-id="f8cc1-104">網路需求</span><span class="sxs-lookup"><span data-stu-id="f8cc1-104">Network requirements</span></span>

<span data-ttu-id="f8cc1-105">如果您已[針對 Microsoft 365 或 Office 365 最佳化您的網路](/Office365/Enterprise/assessing-network-connectivity)，則可能已準備好使用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-105">If you've already [optimized your network for Microsoft 365 or Office 365](/Office365/Enterprise/assessing-network-connectivity), you're probably ready for Microsoft Teams.</span></span> <span data-ttu-id="f8cc1-106">在任何情況下，尤其是如果您要快速推出 Teams 做為第一個 Microsoft 365 或 Office 365 工作負載以支援 **遠端工作者** - 請在開始推出 Teams 之前，檢查下列項目：</span><span class="sxs-lookup"><span data-stu-id="f8cc1-106">In any case - and especially if you're rolling out Teams quickly as your first Microsoft 365 or Office 365 workload to support **remote workers** - check the following before you begin your Teams rollout:</span></span>

1.  <span data-ttu-id="f8cc1-107">您的所有位置是否都有網際網路存取權 (以便它們可以連線到 Microsoft 365 或 Office 365)？</span><span class="sxs-lookup"><span data-stu-id="f8cc1-107">Do all your locations have internet access (so they can connect to Microsoft 365 or Office 365)?</span></span> <span data-ttu-id="f8cc1-108">除了正常網路流量之外，請確定您已開啟 [Office 365 URL 和 IP 位址範圍中列入 Teams 的 TCP 埠和 IP 位址](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-108">In addition to normal web traffic, make sure you've opened the TCP ports and IP addresses listed for Teams in [Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f8cc1-109">如果需要與商務用 Skype (內部部署或線上) 進行同盟，您必須設定額外的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-109">If you need to federate with Skype for Business, either on-premises or online, you will need to configure an additional DNS record.</span></span>
    >
    >|<span data-ttu-id="f8cc1-110">DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="f8cc1-110">DNS record</span></span>  |<span data-ttu-id="f8cc1-111">服務</span><span class="sxs-lookup"><span data-stu-id="f8cc1-111">Service</span></span>  |<span data-ttu-id="f8cc1-112">Protocol (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="f8cc1-112">Protocol</span></span>  |<span data-ttu-id="f8cc1-113">Priority (優先順序)</span><span class="sxs-lookup"><span data-stu-id="f8cc1-113">Priority</span></span>  |<span data-ttu-id="f8cc1-114">Weight (權數)</span><span class="sxs-lookup"><span data-stu-id="f8cc1-114">Weight</span></span>  |<span data-ttu-id="f8cc1-115">Port (連接埠)</span><span class="sxs-lookup"><span data-stu-id="f8cc1-115">Port</span></span>  |<span data-ttu-id="f8cc1-116">Target (目標)</span><span class="sxs-lookup"><span data-stu-id="f8cc1-116">Target</span></span>  |
    >|---------|---------|---------|---------|---------|---------|---------|
    >|<span data-ttu-id="f8cc1-117">SRV</span><span class="sxs-lookup"><span data-stu-id="f8cc1-117">SRV</span></span>     |<span data-ttu-id="f8cc1-118">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="f8cc1-118">sipfederationtls</span></span>     |<span data-ttu-id="f8cc1-119">TCP</span><span class="sxs-lookup"><span data-stu-id="f8cc1-119">TCP</span></span>     |<span data-ttu-id="f8cc1-120">100</span><span class="sxs-lookup"><span data-stu-id="f8cc1-120">100</span></span>     |<span data-ttu-id="f8cc1-121">1</span><span class="sxs-lookup"><span data-stu-id="f8cc1-121">1</span></span>     |<span data-ttu-id="f8cc1-122">5061</span><span class="sxs-lookup"><span data-stu-id="f8cc1-122">5061</span></span>     |<span data-ttu-id="f8cc1-123">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f8cc1-123">sipfed.online.lync.com</span></span>     |
    
2.  <span data-ttu-id="f8cc1-124">您是否有 Microsoft 365 或 Office 365 的經驗證網域 (例如，contoso.com)？</span><span class="sxs-lookup"><span data-stu-id="f8cc1-124">Do you have a verified domain for Microsoft 365 or Office 365 (for example, contoso.com)?</span></span>
    
    - <span data-ttu-id="f8cc1-125">如果您的組織尚未推出 Microsoft 365 或 Office 365，請參閱[開始使用](/microsoft-365/admin/admin-overview/get-started-with-office-365)。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-125">If your organization hasn't rolled out Microsoft 365 or Office 365, see [Get started](/microsoft-365/admin/admin-overview/get-started-with-office-365).</span></span>
    - <span data-ttu-id="f8cc1-126">如果您的組織尚未為 Microsoft 365 或 Office 365 新增或設定經驗證的網域，請參閱[網域常見問題集](/microsoft-365/admin/setup/domains-faq)。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-126">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see the [Domains FAQ](/microsoft-365/admin/setup/domains-faq).</span></span>

3.  <span data-ttu-id="f8cc1-127">您的組織是否已部署 Exchange Online 和 SharePoint Online？</span><span class="sxs-lookup"><span data-stu-id="f8cc1-127">Has your organization deployed Exchange Online and SharePoint Online?</span></span>
    
    - <span data-ttu-id="f8cc1-128">如果您的組織沒有 Exchange Online，請參閱[了解 Exchange 和 Microsoft Teams 如何互動](exchange-teams-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-128">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](exchange-teams-interact.md).</span></span>
    - <span data-ttu-id="f8cc1-129">如果您的組織沒有 SharePoint Online，請參閱[了解 SharePoint Online 和商務用 OneDrive 如何與 Microsoft Teams 互動](sharepoint-onedrive-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-129">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

<span data-ttu-id="f8cc1-130">一旦確認您符合這些網路需求，就可以開始[推出 Teams](./deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-130">Once you've verified that you meet these network requirements, you may be ready to [Roll out Teams](./deploy-overview.md).</span></span> <span data-ttu-id="f8cc1-131">如果您是大型的多國企業，或如果您知道有一些網路限制，請繼續閱讀以了解如何評估及最佳化 Teams 的網路。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-131">If you're a large multinational enterprise, or if you know you've got some network limitations, read on to learn how to assess and optimize your network for Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f8cc1-132">**適用於教育機構**：如果您的組織是教育機構，且您使用學生資訊系統 (SIS)，請在推出 Teams 之前 [部署學校資料同步處理](/schooldatasync/)。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-132">**For educational institutions**: If your organization is an educational institution and you use a Student Information System (SIS), [deploy School Data Sync](/schooldatasync/) before you roll out Teams.</span></span>
>  
> <span data-ttu-id="f8cc1-133">**執行內部部署商務用 Skype Server**：如果您的組織執行的是內部部署商務用 Skype Server (或 Lync Server)，您必須 [設定 Azure AD Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect)，以與 Microsoft 365 或 Office 365 同步處理您的內部部署目錄。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-133">**Running on-premises Skype for Business Server**: If your organization is running on-premises Skype for Business Server (or Lync Server), you must [configure Azure AD Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect) to synchronize your on-premises directory with Microsoft 365 or Office 365.</span></span>

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a><span data-ttu-id="f8cc1-134">最佳做法：使用 CQD 和通話分析監視您的網路</span><span class="sxs-lookup"><span data-stu-id="f8cc1-134">Best practice: Monitor your network using CQD and call analytics</span></span> 

<span data-ttu-id="f8cc1-135">使用[通話品質儀表板 (CQD)](turning-on-and-using-call-quality-dashboard.md) 以深入了解 Teams 中的通話和會議品質。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-135">Use the [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to gain insight into the quality of calls and meetings in Teams.</span></span> <span data-ttu-id="f8cc1-136">CQD 會透過持續注意品質、可靠性和使用者體驗，協助您最佳化您的網路。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-136">CQD can help you optimize your network by keeping a close eye on quality, reliability, and the user experience.</span></span> <span data-ttu-id="f8cc1-137">CQD 會查看整個組織整體模式可能變得明顯處的彙總遙測，這可讓您識別問題並規劃補救。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-137">CQD looks at aggregate telemetry for an entire organization where overall patterns can become apparent, which lets you identify problems and plan remediation.</span></span> <span data-ttu-id="f8cc1-138">此外，CQD 會提供豐富的計量報告，其提供整體品質、可靠性和使用者體驗的深入見解。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-138">Additionally, CQD provides rich metrics reports that provide insight into overall quality, reliability, and user experience.</span></span> 

<span data-ttu-id="f8cc1-139">您將使用[通話分析](set-up-call-analytics.md)來調查個別使用者的通話和會議問題。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-139">You'll use [call analytics](set-up-call-analytics.md) to investigate call and meeting problems for an individual user.</span></span>

## <a name="network-optimization"></a><span data-ttu-id="f8cc1-140">網路​​最佳化</span><span class="sxs-lookup"><span data-stu-id="f8cc1-140">Network optimization</span></span>

<span data-ttu-id="f8cc1-141">下列工作是選用的，且並非推出 Teams 時的必要項目，特別是如果您是小型企業，而且已經推出 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-141">The following tasks are optional and aren't required for rolling out Teams, especially if you're a small business and you've already rolled out Microsoft 365 or Office 365.</span></span> <span data-ttu-id="f8cc1-142">使用此指引來最佳化您的網路和 Teams 的效能，或如果您知道您有一些網路限制，也請參考此指引。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-142">Use this guidance to optimize your network and Teams performance or if you know you've got some network limitations.</span></span>

<span data-ttu-id="f8cc1-143">您可能會想要執行其他網路最佳化，前提是：</span><span class="sxs-lookup"><span data-stu-id="f8cc1-143">You might want to do additional network optimization if:</span></span>

  - <span data-ttu-id="f8cc1-144">Teams 執行速度緩慢 (可能是您的頻寬不足)</span><span class="sxs-lookup"><span data-stu-id="f8cc1-144">Teams runs slowly (maybe you have insufficient bandwidth)</span></span>
  - <span data-ttu-id="f8cc1-145">通話持續斷線 (可能是防火牆或 Proxy 封鎖程式所導致)</span><span class="sxs-lookup"><span data-stu-id="f8cc1-145">Calls keep dropping (might be due to firewall or proxy blockers)</span></span>
  - <span data-ttu-id="f8cc1-146">通話有停滯和中斷，或聲音聽起來像機器人 (可能是抖動或封包遺失)</span><span class="sxs-lookup"><span data-stu-id="f8cc1-146">Calls have static and cut out, or voices sound like robots (could be jitter or packet loss)</span></span>

<span data-ttu-id="f8cc1-147">如需網路最佳化的深入討論，包括識別和修正網路減損的指引，請參閱 [Microsoft 365 和 Office 365 網路連線原則](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-147">For an in-depth discussion of network optimization, including guidance for identifying and fixing network impairments, read [Microsoft 365 and Office 365 Network Connectivity Principles](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles).</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="f8cc1-148">網路​​最佳化工作</span><span class="sxs-lookup"><span data-stu-id="f8cc1-148">Network optimization task</span></span></th>
<th><span data-ttu-id="f8cc1-149">詳細資料</span><span class="sxs-lookup"><span data-stu-id="f8cc1-149">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f8cc1-150">網路規劃中心</span><span class="sxs-lookup"><span data-stu-id="f8cc1-150">Network planner</span></span></td>
<td><p><span data-ttu-id="f8cc1-151">如需評估您的網路 (包括組織實體位置的頻寬計算和網路需求) 的協助，請查看 <a href="https://admin.teams.microsoft.com">Teams 系統管理中心</a>中的<a href="/microsoftteams/network-planner">網路規劃中心</a>工具。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-151">For help assessing your network, including bandwidth calculations and network requirements across your org's physical locations, check out the <a href="/microsoftteams/network-planner">Network Planner</a> tool, in the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="f8cc1-152">提供網路詳細資料和 Teams 使用狀況時，網路規劃中心會計算在組織的實體位置間部署 Teams 與雲端語音的網路需求。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-152">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span></p>
<p><span data-ttu-id="f8cc1-153">如需範例案例，請參閱<a href="/microsoftteams/tutorial-network-planner-example">網路規劃中心 - 範例案例</a>。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-153">For an example scenario, see <a href="/microsoftteams/tutorial-network-planner-example">Using Network Planner - example scenario</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f8cc1-154">適用於 Teams 的建議程式</span><span class="sxs-lookup"><span data-stu-id="f8cc1-154">Advisor for Teams</span></span></td>
<td><span data-ttu-id="f8cc1-155"><a href="/microsoftteams/use-advisor-teams-roll-out">適用於 Teams 的建議程式</a>是 <a href="https://admin.teams.microsoft.com">Teams 系統管理中心</a>的一部分。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-155"><a href="/microsoftteams/use-advisor-teams-roll-out">Advisor for Teams</a> is part of the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="f8cc1-156">在您成功推出 Teams 前，它會評估您的 Microsoft 365 或 Office 365 環境，找出可能需要更新或修改的最常用設定。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-156">It assesses your Microsoft 365 or Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f8cc1-157">外部名稱解析</span><span class="sxs-lookup"><span data-stu-id="f8cc1-157">External Name Resolution</span></span></td>
<td><span data-ttu-id="f8cc1-158">請確定執行 Teams 用戶端的所有電腦都可以解析外部 DNS 查詢，以探索 Microsoft 365 或 Office 365 提供的服務，而且您的防火牆不會阻止存取。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-158">Be sure that all computers running the Teams client can resolve external DNS queries to discover the services provided by Microsoft 365 or Office 365 and that your firewalls are not preventing access.</span></span> <span data-ttu-id="f8cc1-159">如需設定防火牆連接埠的詳細資訊，請前往 <a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 和 Office 365 與 IP 範圍</a>。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-159">For information about configuring firewall ports, go to <a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 and Office 365 URLs and IP ranges</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f8cc1-160">維護工作階段持續性</span><span class="sxs-lookup"><span data-stu-id="f8cc1-160">Maintain session persistence</span></span></td>
<td><span data-ttu-id="f8cc1-161">請確定您的防火牆不會變更對應的網路位址轉譯 (NAT) 位址或 UDP 的連接埠。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-161">Make sure your firewall doesn't change the mapped Network Address Translation (NAT) addresses or ports for UDP.</span></span></td>
</tr><tr class="odd">
<td><span data-ttu-id="f8cc1-162">驗證 NAT 集區大小</span><span class="sxs-lookup"><span data-stu-id="f8cc1-162">Validate NAT pool size</span></span></td>
<td><span data-ttu-id="f8cc1-163">驗證使用者連線所需的網路位址轉譯 (NAT) 集區大小。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-163">Validate the network address translation (NAT) pool size required for user connectivity.</span></span> <span data-ttu-id="f8cc1-164">多個使用者和裝置使用<a href="/office365/enterprise/nat-support-with-office-365">網路位址轉譯 (NAT) 或連接埠位址轉譯 (PAT)</a> 存取 Microsoft 365 或 Office 365 時，您必須確保隱藏於每個可路由 IP 位址後方的裝置不超過支援的數量。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-164">When multiple users and devices access Microsoft 365 or Office 365 using <a href="/office365/enterprise/nat-support-with-office-365">Network Address Translation (NAT) or Port Address Translation (PAT)</a>, you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span> <span data-ttu-id="f8cc1-165">確保將充足的公用 IP 位址指派到 NAT 集區，以防止連接埠耗盡。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-165">Ensure that adequate public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="f8cc1-166">連接埠耗盡會導致內部使用者和裝置無法連線到 Microsoft 365 或 Office 365 服務。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-166">Port exhaustion will contribute to internal users and devices being unable to connect to the Microsoft 365 or Office 365 service.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f8cc1-167">路由至 Microsoft 資料中心</span><span class="sxs-lookup"><span data-stu-id="f8cc1-167">Routing to Microsoft data centers</span></span></td>
<td><span data-ttu-id="f8cc1-168"><a href="/office365/enterprise/client-connectivity">對 Microsoft 資料中心實作最有效率的路由</a>。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-168"><a href="/office365/enterprise/client-connectivity">Implement the most efficient routing to Microsoft data centers</a>.</span></span> <span data-ttu-id="f8cc1-169">盡可能有效率地識別可使用本機或區域出口點來連線至 Microsoft 網路的位置。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-169">Identify locations that can use local or regional egress points to connect to the Microsoft network as efficiently as possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f8cc1-170">入侵偵測與預防指引</span><span class="sxs-lookup"><span data-stu-id="f8cc1-170">Intrusion Detection and Prevention Guidance</span></span></td>
<td><span data-ttu-id="f8cc1-171">如果您的環境已部署<a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">入侵偵測</a>或預防系統 (IDS/IPS)，以針對輸出連線獲得額外一層的安全性，請務必允許所有 Microsoft 365 或 Office 365 URL。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-171">If your environment has an <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Intrusion Detection</a> or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, be sure to allow all Microsoft 365 or Office 365 URLs.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f8cc1-172">設定分割通道 VPN</span><span class="sxs-lookup"><span data-stu-id="f8cc1-172">Configure split-tunnel VPN</span></span></td>
<td><p><span data-ttu-id="f8cc1-173">建議您為會略過虛擬私人網路 (VPN) 的 Teams 流量提供替代路徑，通常稱為<a href="/windows/security/identity-protection/vpn/vpn-routing">分割通道 VPN</a>。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-173">We recommend that you provide an alternate path for Teams traffic that bypasses the virtual private network (VPN), commonly known as <a href="/windows/security/identity-protection/vpn/vpn-routing">split-tunnel VPN</a>.</span></span> <span data-ttu-id="f8cc1-174">分割通道表示 Microsoft 365 或 Office 365 的流量不會通過 VPN，而是直接進入 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-174">Split tunneling means that traffic for Microsoft 365 or Office 365 doesn't go through the VPN but instead goes directly to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="f8cc1-175">略過 VPN 會對 Teams 品質產生正面影響，並減少來自 VPN 裝置和組織網路的負載。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-175">Bypassing your VPN will have a positive impact on Teams quality, and it reduces load from the VPN devices and the organization's network.</span></span> <span data-ttu-id="f8cc1-176">若要實作分割通道 VPN，請與 VPN 廠商合作。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-176">To implement a split-tunnel VPN, work with your VPN vendor.</span></span></p>
<p><span data-ttu-id="f8cc1-177">我們建議略過 VPN 的其他原因：</span><span class="sxs-lookup"><span data-stu-id="f8cc1-177">Other reasons why we recommend bypassing the VPN:</span></span>
<ul>
<li><p><span data-ttu-id="f8cc1-178">VPN 通常不會設計或設定為支援即時媒體。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-178">VPNs are typically not designed or configured to support real-time media.</span></span></p></li> 
<li><p><span data-ttu-id="f8cc1-179">某些 VPN 可能也不支援 UDP (這是 Teams 所需)。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-179">Some VPNs might also not support UDP (which is required for Teams).</span></span></p></li> 
<li><p><span data-ttu-id="f8cc1-180">VPN 也會在已加密的媒體流量上引入額外的加密層。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-180">VPNs also introduce an extra layer of encryption on top of media traffic that's already encrypted.</span></span></p></li> 
<li><p><span data-ttu-id="f8cc1-181">由於透過 VPN 裝置切換流量，與 Teams 的連線可能會沒有效率。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-181">Connectivity to Teams might not be efficient due to hair-pinning traffic through a VPN device.</span></span></p></li></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f8cc1-182">實作 QoS</span><span class="sxs-lookup"><span data-stu-id="f8cc1-182">Implement QoS</span></span></td>
<td><span data-ttu-id="f8cc1-183"><a href="/microsoftteams/qos-in-teams">使用服務品質 (QoS)</a> 來設定封包優先順序。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-183"><a href="/microsoftteams/qos-in-teams">Use Quality of Service (QoS)</a> to configure packet prioritization.</span></span> <span data-ttu-id="f8cc1-184">這將改善 Teams 中的通話品質，並協助您監控和疑難排解通話品質。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-184">This will improve call quality in Teams and help you monitor and troubleshoot call quality.</span></span> <span data-ttu-id="f8cc1-185">QoS 應該在受管理網路的所有區段上實作。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-185">QoS should be implemented on all segments of a managed network.</span></span> <span data-ttu-id="f8cc1-186">即使在網路已佈建足夠頻寬時，在發生未預期的網路事件時，QoS 也可提供風險緩解。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-186">Even when a network has been adequately provisioned for bandwidth, QoS provides risk mitigation in the event of unanticipated network events.</span></span> <span data-ttu-id="f8cc1-187">使用 QoS 時，會優先處理語音流量，使得這些非預期的事件不會對品質造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-187">With QoS, voice traffic is prioritized so that these unanticipated events don't negatively affect quality.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f8cc1-188">最佳化 WiFi</span><span class="sxs-lookup"><span data-stu-id="f8cc1-188">Optimize WiFi</span></span></td>
<td><p><span data-ttu-id="f8cc1-189">類似於 VPN，WiFi 網路不一定需要設計或設定為支援即時媒體。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-189">Similar to VPN, WiFi networks aren't necessarily designed or configured to support real-time media.</span></span> <span data-ttu-id="f8cc1-190">規劃或最佳化 WiFi 網路以支援 Teams，是實現高品質部署的重要考慮事項。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-190">Planning for, or optimizing, a WiFi network to support Teams is an important consideration for a high-quality deployment.</span></span> <span data-ttu-id="f8cc1-191">考慮下列因素：</span><span class="sxs-lookup"><span data-stu-id="f8cc1-191">Consider these factors:</span></span></p>
<ul>
<li><p><span data-ttu-id="f8cc1-192">實作 QoS 或 WiFi 多媒體 (WMM) 以確保透過 WiFi 網路的媒體流量有適當的優先順序。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-192">Implement QoS or WiFi Multimedia (WMM) to ensure that media traffic is getting prioritized appropriately over your WiFi networks.</span></span></p></li>
<li><p><span data-ttu-id="f8cc1-193">規劃和最佳化 WiFi 頻帶與存取點放置方式。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-193">Plan and optimize the WiFi bands and access point placement.</span></span> <span data-ttu-id="f8cc1-194">根據存取點放置方式，2.4 GHz 範圍可能會提供足夠的體驗，但存取點往往會受到該範圍中運作的其他消費者裝置影響。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-194">The 2.4 GHz range might provide an adequate experience depending on access point placement, but access points are often affected by other consumer devices that operate in that range.</span></span> <span data-ttu-id="f8cc1-195">5 GHz 範圍因其密度範圍較適合即時媒體，但需要更多存取點以取得足夠的覆蓋範圍。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-195">The 5 GHz range is better suited to real-time media due to its dense range, but it requires more access points to get sufficient coverage.</span></span> <span data-ttu-id="f8cc1-196">端點也需要支援該範圍並經過設定，才能據以運用這些頻帶。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-196">Endpoints also need to support that range and be configured to leverage those bands accordingly.</span></span></p></li>
<li><p><span data-ttu-id="f8cc1-197">如果您使用的是雙頻 WiFi 網路，請考慮實作頻帶操縱。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-197">If you're using dual-band WiFi networks, consider implementing band steering.</span></span> <span data-ttu-id="f8cc1-198"><em>頻帶操縱</em>是 WiFi 廠商所實作的技術，可影響雙頻用戶端以使用 5 GHz 範圍。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-198"><em>Band steering</em> is a technique implemented by WiFi vendors to influence dual-band clients to use the 5 GHz range.</span></span></p></li>
<li><p><span data-ttu-id="f8cc1-199">當相同頻道的存取點太接近時，可能會導致信號重疊且無意間的競爭，導致使用者體驗不佳。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-199">When access points of the same channel are too close together, they can cause signal overlap and unintentionally compete, resulting in a bad experience for the user.</span></span> <span data-ttu-id="f8cc1-200">確保頻道上相鄰的存取點沒有重疊。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-200">Ensure that access points that are next to each other are on channels that don't overlap.</span></span></p></li>
</ul>
<p><span data-ttu-id="f8cc1-201">每個無線廠商都有其部署無線解決方案的建議。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-201">Each wireless vendor has its own recommendations for deploying its wireless solution.</span></span> <span data-ttu-id="f8cc1-202">請洽詢您的 WiFi 廠商以了解特定指引。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-202">Consult your WiFi vendor for specific guidance.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a><span data-ttu-id="f8cc1-203">頻寬需求</span><span class="sxs-lookup"><span data-stu-id="f8cc1-203">Bandwidth requirements</span></span>

<span data-ttu-id="f8cc1-204">無論您的網路狀況如何，Teams 的設計都可提供最佳的音訊、視訊和內容共用體驗。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-204">Teams is designed to give the best audio, video, and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="f8cc1-205">也就是說，當頻寬不足時，Teams 會優先處理音訊品質，之後才是視訊品質。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-205">That said, when bandwidth is insufficient, Teams prioritizes audio quality over video quality.</span></span>

<span data-ttu-id="f8cc1-206">在頻寬未受限的情況下，Teams 會最佳化媒體品質，包括高逼真度音訊、最高至 1080p 的視訊解析度，以及最高 30fps (每秒畫面數) 的視訊和內容。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-206">Where bandwidth isn't limited, Teams optimizes media quality, including high-fidelity audio, up to 1080p video resolution, and up to 30fps (frames per second) for video and content.</span></span>

<span data-ttu-id="f8cc1-207">下表說明 Teams 使用頻寬的方式。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-207">This table describes how Teams uses bandwidth.</span></span> <span data-ttu-id="f8cc1-208">Teams 在頻寬利用方面一向非常節約，可提供低於 1.5 Mbps 的 HD 視訊品質。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-208">Teams is always conservative on bandwidth utilization and can deliver HD video quality in under 1.5Mbps.</span></span> <span data-ttu-id="f8cc1-209">每個音訊/視訊通話或會議中的實際頻寬消耗，會根據幾個因素而有所不同，例如視訊版面配置、視訊解析度和每秒視訊畫面格數。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-209">The actual bandwidth consumption in each audio/video call or meeting will vary based on several factors, such as video layout, video resolution, and video frames per second.</span></span> <span data-ttu-id="f8cc1-210">當有更多頻寬可用時，品質和使用狀況便會提高，以提供最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-210">When more bandwidth is available, quality and usage will increase to deliver the best experience.</span></span>

:::row:::
   :::column span="":::
      <span data-ttu-id="f8cc1-211">**形式**</span><span class="sxs-lookup"><span data-stu-id="f8cc1-211">**Modality**</span></span>
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="f8cc1-212">**頻寬需求 （位元速率 KB/s 上/下）**</span><span class="sxs-lookup"><span data-stu-id="f8cc1-212">**Bandwidth requirements (bitrate KB/s up/down)**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="f8cc1-213">**最小值**</span><span class="sxs-lookup"><span data-stu-id="f8cc1-213">**Minimum**</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="f8cc1-214">**建議**</span><span class="sxs-lookup"><span data-stu-id="f8cc1-214">**Recommended**</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="f8cc1-215">**最佳效能**</span><span class="sxs-lookup"><span data-stu-id="f8cc1-215">**Best performance**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="f8cc1-216">**音訊**</span><span class="sxs-lookup"><span data-stu-id="f8cc1-216">**Audio**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="f8cc1-217">一對一</span><span class="sxs-lookup"><span data-stu-id="f8cc1-217">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8cc1-218">10/10</span><span class="sxs-lookup"><span data-stu-id="f8cc1-218">10/10</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8cc1-219">58/58</span><span class="sxs-lookup"><span data-stu-id="f8cc1-219">58/58</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8cc1-220">76/76</span><span class="sxs-lookup"><span data-stu-id="f8cc1-220">76/76</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="f8cc1-221">會議</span><span class="sxs-lookup"><span data-stu-id="f8cc1-221">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8cc1-222">10/10</span><span class="sxs-lookup"><span data-stu-id="f8cc1-222">10/10</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8cc1-223">58/58</span><span class="sxs-lookup"><span data-stu-id="f8cc1-223">58/58</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8cc1-224">76/76</span><span class="sxs-lookup"><span data-stu-id="f8cc1-224">76/76</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="f8cc1-225">**視訊**</span><span class="sxs-lookup"><span data-stu-id="f8cc1-225">**Video**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="f8cc1-226">一對一</span><span class="sxs-lookup"><span data-stu-id="f8cc1-226">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8cc1-227">150/150</span><span class="sxs-lookup"><span data-stu-id="f8cc1-227">150/150</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8cc1-228">1,500/1,500</span><span class="sxs-lookup"><span data-stu-id="f8cc1-228">1,500/1,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8cc1-229">4,000/4,000</span><span class="sxs-lookup"><span data-stu-id="f8cc1-229">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="f8cc1-230">會議</span><span class="sxs-lookup"><span data-stu-id="f8cc1-230">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8cc1-231">150/200</span><span class="sxs-lookup"><span data-stu-id="f8cc1-231">150/200</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8cc1-232">2,500/4,000</span><span class="sxs-lookup"><span data-stu-id="f8cc1-232">2,500/4,000</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8cc1-233">4,000/4,000</span><span class="sxs-lookup"><span data-stu-id="f8cc1-233">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="f8cc1-234">**共用螢幕**</span><span class="sxs-lookup"><span data-stu-id="f8cc1-234">**Screen sharing**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="f8cc1-235">一對一</span><span class="sxs-lookup"><span data-stu-id="f8cc1-235">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8cc1-236">200/200</span><span class="sxs-lookup"><span data-stu-id="f8cc1-236">200/200</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8cc1-237">1,500/1,500</span><span class="sxs-lookup"><span data-stu-id="f8cc1-237">1,500/1,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8cc1-238">4,000/4,000</span><span class="sxs-lookup"><span data-stu-id="f8cc1-238">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="f8cc1-239">會議</span><span class="sxs-lookup"><span data-stu-id="f8cc1-239">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8cc1-240">250/250</span><span class="sxs-lookup"><span data-stu-id="f8cc1-240">250/250</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8cc1-241">2,500/2,500</span><span class="sxs-lookup"><span data-stu-id="f8cc1-241">2,500/2,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8cc1-242">4,000/4,000</span><span class="sxs-lookup"><span data-stu-id="f8cc1-242">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="f8cc1-243">**齊聚模式**</span><span class="sxs-lookup"><span data-stu-id="f8cc1-243">**Together Mode**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="f8cc1-244">一對一</span><span class="sxs-lookup"><span data-stu-id="f8cc1-244">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8cc1-245">不適用</span><span class="sxs-lookup"><span data-stu-id="f8cc1-245">N/A</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8cc1-246">不適用</span><span class="sxs-lookup"><span data-stu-id="f8cc1-246">N/A</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8cc1-247">不適用</span><span class="sxs-lookup"><span data-stu-id="f8cc1-247">N/A</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="f8cc1-248">會議</span><span class="sxs-lookup"><span data-stu-id="f8cc1-248">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8cc1-249">1,000/1,500</span><span class="sxs-lookup"><span data-stu-id="f8cc1-249">1,000/1,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8cc1-250">1,500/2,500</span><span class="sxs-lookup"><span data-stu-id="f8cc1-250">1,500/2,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="f8cc1-251">2,500/4,000</span><span class="sxs-lookup"><span data-stu-id="f8cc1-251">2,500/4,000</span></span>
   :::column-end:::
:::row-end:::

<span data-ttu-id="f8cc1-252">**最低**、 **建議的**，以及 **最佳** 頻寬需求是根據每個端點的使用情況。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-252">**Minimum**, **Recommended**, and **Best performance** bandwidth requirements are based on per-endpoint usage.</span></span> <span data-ttu-id="f8cc1-253">一般來說，每個使用者為一個端點，例如電腦或行動裝置。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-253">Typically, there's one endpoint per user, such as a computer or mobile device.</span></span> <span data-ttu-id="f8cc1-254">不過，如果使用者 *同時* 在電腦 *與* 行動裝置上參與 Teams 會議，則兩個端點皆會與該使用者相關聯。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-254">However, if a user joins a Teams meeting on *both* a computer *and* a mobile device, two endpoints are associated with that user.</span></span>

- <span data-ttu-id="f8cc1-255">視訊通話的 **最低** 頻寬需求為最高 240p 解析度、共用螢幕內容畫面播放速率可調整 1.875 到 7.5fps，而齊聚模式/大型圖庫視訊最高 540p 解析度。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-255">**Minimum** Bandwidth requirements for video calls are up to 240p resolution, screen sharing content frame rates adaptive 1.875 to 7.5fps, and Together Mode/Large Gallery video up to 540p resolution.</span></span>  

- <span data-ttu-id="f8cc1-256">視訊通話的 **建議** 頻寬需求為最高 1080p 解析度<sup>\*</sup>、共用螢幕內容畫面播放速率可調整為 7.5 到 30fps，而齊聚模式/大型圖庫視訊最高 1080p 解析度<sup>\*</sup>。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-256">**Recommended** Bandwidth requirements for video calls are up to 1080p resolution<sup>\*</sup>, screen sharing content frame rates adaptive 7.5 to 30fps, and Together Mode/Large Gallery video up to 1080p resolution<sup>\*</sup>.</span></span>  

- <span data-ttu-id="f8cc1-257">**「最佳效能** 指引」可達成較大型的會議出席者人數、高遺失環境以及較高動作內容逼真度的視訊，螢幕共用內容畫面播放速率可調整從 15 到 30fps。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-257">**Best Performance** Guidance allows higher fidelity video for larger attendee meetings, high loss environments, and higher motion content with screen sharing content frame rates adaptive 15 to 30fps.</span></span>

<span data-ttu-id="f8cc1-258"><sup>\*</sup>預期最高品質 1080p ，但根據您的網路狀況，音訊解析度和品質會加以優化。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-258"><sup>\*</sup>Expect up to 1080p quality but depending on your network conditions, video resolution and quality will be optimized accordingly.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="f8cc1-259">相關主題</span><span class="sxs-lookup"><span data-stu-id="f8cc1-259">Related Topics</span></span>

[<span data-ttu-id="f8cc1-260">Microsoft 365 和 Office 365 網路連線原則</span><span class="sxs-lookup"><span data-stu-id="f8cc1-260">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[<span data-ttu-id="f8cc1-261">全球端點：商務用 Skype Online 和 Teams</span><span class="sxs-lookup"><span data-stu-id="f8cc1-261">Worldwide endpoints: Skype for Business Online and Teams</span></span>](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[<span data-ttu-id="f8cc1-262">Teams 的 Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="f8cc1-262">Proxy servers for Teams</span></span>](proxy-servers-for-skype-for-business-online.md)

[<span data-ttu-id="f8cc1-263">Teams 中的媒體：為什麼會議很簡單</span><span class="sxs-lookup"><span data-stu-id="f8cc1-263">Media in Teams: Why meetings are simple</span></span>](https://aka.ms/teams-media)

[<span data-ttu-id="f8cc1-264">Teams 中的媒體：深入探討媒體流程</span><span class="sxs-lookup"><span data-stu-id="f8cc1-264">Media in Teams: Deep dive into media flows</span></span>](https://aka.ms/teams-media-flows)

[<span data-ttu-id="f8cc1-265">Teams 中的身分識別和驗證</span><span class="sxs-lookup"><span data-stu-id="f8cc1-265">Identity models and authentication in Teams</span></span>](identify-models-authentication.md)

[<span data-ttu-id="f8cc1-266">如何推出 Teams</span><span class="sxs-lookup"><span data-stu-id="f8cc1-266">How to roll out Teams</span></span>](./deploy-overview.md)

[<span data-ttu-id="f8cc1-267">Teams 疑難排解</span><span class="sxs-lookup"><span data-stu-id="f8cc1-267">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
