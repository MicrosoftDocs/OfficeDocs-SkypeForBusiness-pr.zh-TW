---
title: 針對 Teams 準備組織的網路
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: 瞭解如何為 Microsoft 團隊準備貴組織的網路，包括網路需求、網路優化和頻寬需求。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 30d67c34e4ef0b7d94b9161bd5f12c51006aaa4e
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "44669404"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="0963c-103">針對 Microsoft Teams 準備組織的網路</span><span class="sxs-lookup"><span data-stu-id="0963c-103">Prepare your organization's network for Microsoft Teams</span></span> 

## <a name="network-requirements"></a><span data-ttu-id="0963c-104">網路需求</span><span class="sxs-lookup"><span data-stu-id="0963c-104">Network requirements</span></span>

<span data-ttu-id="0963c-105">如果您已經針對[microsoft 365 或 Office 365 優化您的網路](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity)，您可能已經準備好開始進行 microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="0963c-105">If you've already [optimized your network for Microsoft 365 or Office 365](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity), you're probably ready for Microsoft Teams.</span></span> <span data-ttu-id="0963c-106">在任何情況下，特別是如果您是在第一份 Microsoft 365 或 Office 365 工作負載快速推出，以支援**遠端工作人員**，請先檢查下列專案，然後再開始進行團隊推出：</span><span class="sxs-lookup"><span data-stu-id="0963c-106">In any case - and especially if you're rolling out Teams quickly as your first Microsoft 365 or Office 365 workload to support **remote workers** - check the following before you begin your Teams rollout:</span></span>

1.  <span data-ttu-id="0963c-107">您的所有位置都有網際網路存取權（以便他們可以連線至 Microsoft 365 或 Office 365）嗎？</span><span class="sxs-lookup"><span data-stu-id="0963c-107">Do all your locations have internet access (so they can connect to Microsoft 365 or Office 365)?</span></span> <span data-ttu-id="0963c-108">除了標準的網路流量之外，請確定您已針對團隊中的媒體開啟下列專案（適用于所有位置）：</span><span class="sxs-lookup"><span data-stu-id="0963c-108">At a minimum, in addition to normal web traffic, make sure you've opened the following, for all locations, for media in Teams:</span></span>

    |  |  |
    |---------|---------|
    |<span data-ttu-id="0963c-109">埠</span><span class="sxs-lookup"><span data-stu-id="0963c-109">Ports</span></span>     |<span data-ttu-id="0963c-110">UDP 埠<strong>3478</strong>到<strong>3481</strong></span><span class="sxs-lookup"><span data-stu-id="0963c-110">UDP ports <strong>3478</strong> through <strong>3481</strong></span></span>        |
    |[<span data-ttu-id="0963c-111">IP 位址</span><span class="sxs-lookup"><span data-stu-id="0963c-111">IP addresses</span></span>](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<span data-ttu-id="0963c-112"><strong>13.107.64.0/18</strong>、 <strong>52.112.0.0/14</strong>和<strong>52.120.0.0/14</strong></span><span class="sxs-lookup"><span data-stu-id="0963c-112"><strong>13.107.64.0/18</strong>, <strong>52.112.0.0/14</strong>, and <strong>52.120.0.0/14</strong></span></span>         |

> [!IMPORTANT]
> <span data-ttu-id="0963c-113">如果您需要與商務用 Skype （內部部署或線上）聯盟，您將需要設定一些額外的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="0963c-113">If you need to federate with Skype for Business, either on-premises or online, you will need to configure some additional DNS records.</span></span>
>
>|<span data-ttu-id="0963c-114">CNAME 記錄/主機名稱</span><span class="sxs-lookup"><span data-stu-id="0963c-114">CNAME Records / Host name</span></span>  |<span data-ttu-id="0963c-115">TTL</span><span class="sxs-lookup"><span data-stu-id="0963c-115">TTL</span></span>  |<span data-ttu-id="0963c-116">指向 [位址] 或 [值]</span><span class="sxs-lookup"><span data-stu-id="0963c-116">Points to address or value</span></span>  |
>|---------|---------|---------|
>|<span data-ttu-id="0963c-117">呼吸</span><span class="sxs-lookup"><span data-stu-id="0963c-117">sip</span></span>     |    <span data-ttu-id="0963c-118">3600</span><span class="sxs-lookup"><span data-stu-id="0963c-118">3600</span></span>     |    <span data-ttu-id="0963c-119">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0963c-119">sipdir.online.lync.com</span></span>     |
>|<span data-ttu-id="0963c-120">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="0963c-120">lyncdiscover</span></span>     |   <span data-ttu-id="0963c-121">3600</span><span class="sxs-lookup"><span data-stu-id="0963c-121">3600</span></span>      |    <span data-ttu-id="0963c-122">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0963c-122">webdir.online.lync.com</span></span>     |
>


    
2.  <span data-ttu-id="0963c-123">您是否有驗證的網域供 Microsoft 365 或 Office 365 （例如 contoso.com）？</span><span class="sxs-lookup"><span data-stu-id="0963c-123">Do you have a verified domain for Microsoft 365 or Office 365 (for example, contoso.com)?</span></span>
    
      - <span data-ttu-id="0963c-124">如果您的組織尚未推出 Microsoft 365 或 Office 365，請參閱[microsoft 365 或 office 365 商務版快速](https://docs.microsoft.com/office365/admin/admin-overview/get-started-with-office-365)入門。</span><span class="sxs-lookup"><span data-stu-id="0963c-124">If your organization hasn't rolled out Microsoft 365 or Office 365, see [Getting Started with Microsoft 365 or Office 365 for business](https://docs.microsoft.com/office365/admin/admin-overview/get-started-with-office-365).</span></span>
      - <span data-ttu-id="0963c-125">如果您的組織尚未新增或設定 Microsoft 365 或 Office 365 的驗證網域，請參閱[驗證您的 microsoft 365 或 office 365 網域](https://docs.microsoft.com/office365/admin/setup/domains-faq)。</span><span class="sxs-lookup"><span data-stu-id="0963c-125">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see [Verify your Microsoft 365 or Office 365 domain](https://docs.microsoft.com/office365/admin/setup/domains-faq).</span></span>

3.  <span data-ttu-id="0963c-126">貴組織已部署 Exchange Online 和 SharePoint Online 嗎？</span><span class="sxs-lookup"><span data-stu-id="0963c-126">Has your organization deployed Exchange Online and SharePoint Online?</span></span>
    
      - <span data-ttu-id="0963c-127">如果您的組織沒有 Exchange Online，請參閱[瞭解 exchange 與 Microsoft 團隊互動的方式](exchange-teams-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="0963c-127">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](exchange-teams-interact.md).</span></span>
      - <span data-ttu-id="0963c-128">如果您的組織沒有 SharePoint Online，請參閱[瞭解 Sharepoint online 與商務用 OneDrive 與 Microsoft 團隊互動的方式](sharepoint-onedrive-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="0963c-128">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

<span data-ttu-id="0963c-129">確認符合這些網路需求之後，您就可以準備好要[推出小組](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="0963c-129">Once you've verified that you meet these network requirements, you may be ready to [Roll out Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="0963c-130">如果您是大型的跨國公司，或者如果您知道您有一些網路限制，請繼續閱讀以瞭解如何為團隊評估及優化您的網路。</span><span class="sxs-lookup"><span data-stu-id="0963c-130">If you're a large multinational enterprise, or if you know you've got some network limitations, read on to learn how to assess and optimize your network for Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0963c-131">**針對教育機構**：如果您的組織是教育機構，且您是使用學生資訊系統（SIS），請先[部署學校資料同步](https://docs.microsoft.com/schooldatasync/)處理，然後再將團隊推出。</span><span class="sxs-lookup"><span data-stu-id="0963c-131">**For educational institutions**: If your organization is an educational institution and you use a Student Information System (SIS), [deploy School Data Sync](https://docs.microsoft.com/schooldatasync/) before you roll out Teams.</span></span>
>  
> <span data-ttu-id="0963c-132">執行**內部部署商務用 Skype server**：如果您的組織正在執行內部部署商務用 skype 伺服器（或 Lync Server），您必須[設定 Azure AD Connect](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect) ，以將您的內部部署目錄與 Microsoft 365 或 Office 365 同步處理。</span><span class="sxs-lookup"><span data-stu-id="0963c-132">**Running on-premises Skype for Business Server**: If your organization is running on-premises Skype for Business Server (or Lync Server), you must [configure Azure AD Connect](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect) to synchronize your on-premises directory with Microsoft 365 or Office 365.</span></span>

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a><span data-ttu-id="0963c-133">最佳做法：使用 CQD 和通話分析監控您的網路</span><span class="sxs-lookup"><span data-stu-id="0963c-133">Best practice: Monitor your network using CQD and call analytics</span></span> 

<span data-ttu-id="0963c-134">使用[通話品質儀表板（CQD）](turning-on-and-using-call-quality-dashboard.md) ，深入瞭解團隊中的通話和會議品質。</span><span class="sxs-lookup"><span data-stu-id="0963c-134">Use the [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to gain insight into the quality of calls and meetings in Teams.</span></span> <span data-ttu-id="0963c-135">CQD 可協助您保持密切留意品質、可靠性和使用者體驗，以協助您優化網路。</span><span class="sxs-lookup"><span data-stu-id="0963c-135">CQD can help you optimize your network by keeping a close eye on quality, reliability, and the user experience.</span></span> <span data-ttu-id="0963c-136">CQD 會在整個組織中查看匯總遙測，在這種情況下，整體模式會變得明顯，讓您找出問題並規劃修正。</span><span class="sxs-lookup"><span data-stu-id="0963c-136">CQD looks at aggregate telemetry for an entire organization where overall patterns can become apparent, which lets you identify problems and plan remediation.</span></span> <span data-ttu-id="0963c-137">此外，CQD 提供豐富的度量報告，可讓您深入瞭解整體品質、可靠性及使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="0963c-137">Additionally, CQD provides rich metrics reports that provide insight into overall quality, reliability, and user experience.</span></span> 

<span data-ttu-id="0963c-138">您將使用[呼叫分析](set-up-call-analytics.md)來調查個別使用者的通話與會議問題。</span><span class="sxs-lookup"><span data-stu-id="0963c-138">You'll use [call analytics](set-up-call-analytics.md) to investigate call and meeting problems for an individual user.</span></span>

## <a name="network-optimization"></a><span data-ttu-id="0963c-139">網路優化</span><span class="sxs-lookup"><span data-stu-id="0963c-139">Network optimization</span></span>

<span data-ttu-id="0963c-140">如果您是小型企業版且已推出 Microsoft 365 或 Office 365，則下列工作是選擇性的，而且不是必要的。</span><span class="sxs-lookup"><span data-stu-id="0963c-140">The following tasks are optional and aren't required for rolling out Teams, especially if you're a small business and you've already rolled out Microsoft 365 or Office 365.</span></span> <span data-ttu-id="0963c-141">使用本指導方針來優化您的網路與團隊效能，或者您知道您有一些網路限制。</span><span class="sxs-lookup"><span data-stu-id="0963c-141">Use this guidance to optimize your network and Teams performance or if you know you've got some network limitations.</span></span>

<span data-ttu-id="0963c-142">在下列情況中，您可能會想要執行額外的網路優化動作：</span><span class="sxs-lookup"><span data-stu-id="0963c-142">You might want to do additional network optimization if:</span></span>

  - <span data-ttu-id="0963c-143">團隊執行緩慢（可能是您的頻寬不夠用）</span><span class="sxs-lookup"><span data-stu-id="0963c-143">Teams runs slowly (maybe you have insufficient bandwidth)</span></span>
  - <span data-ttu-id="0963c-144">呼叫繼續放下（可能是防火牆或 proxy 攔截程式所致）</span><span class="sxs-lookup"><span data-stu-id="0963c-144">Calls keep dropping (might be due to firewall or proxy blockers)</span></span>
  - <span data-ttu-id="0963c-145">通話有靜態和剪下，或聲音像機器人（可能是抖動或資料包遺失）</span><span class="sxs-lookup"><span data-stu-id="0963c-145">Calls have static and cut out, or voices sound like robots (could be jitter or packet loss)</span></span>

<span data-ttu-id="0963c-146">如需網路優化的深入討論，包括識別及修正網路障礙的指導方針，請參閱[Microsoft 365 和 Office 365 網路連線原則](https://aka.ms/pnc)。</span><span class="sxs-lookup"><span data-stu-id="0963c-146">For an in-depth discussion of network optimization, including guidance for identifying and fixing network impairments, read [Microsoft 365 and Office 365 Network Connectivity Principles](https://aka.ms/pnc).</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="0963c-147"><strong>網路優化工作</strong></span><span class="sxs-lookup"><span data-stu-id="0963c-147"><strong>Network optimization task</strong></span></span></th>
<th><span data-ttu-id="0963c-148"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="0963c-148"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="0963c-149">網路 planner</span><span class="sxs-lookup"><span data-stu-id="0963c-149">Network planner</span></span></td>
<td><p><span data-ttu-id="0963c-150">如需評估網路的協助，包括貴組織之物理位置的頻寬計算和網路需求，請查看 [<a href="https://admin.teams.microsoft.com">小組管理中心</a>] 中的 [<a href="https://docs.microsoft.com/microsoftteams/network-planner">網路 Planner</a>工具]。</span><span class="sxs-lookup"><span data-stu-id="0963c-150">For help assessing your network, including bandwidth calculations and network requirements across your org's physical locations, check out the <a href="https://docs.microsoft.com/microsoftteams/network-planner">Network Planner</a> tool, in the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="0963c-151">當您提供您的網路詳細資料和團隊使用量時，網路 Planner 會計算您的網路需求，以便在整個組織的物理位置部署團隊和雲端語音。</span><span class="sxs-lookup"><span data-stu-id="0963c-151">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span></p>
<p><span data-ttu-id="0963c-152">如需範例案例，請參閱<a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">使用網路 Planner-範例案例</a>。</span><span class="sxs-lookup"><span data-stu-id="0963c-152">For an example scenario, see <a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">Using Network Planner - example scenario</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0963c-153">團隊顧問</span><span class="sxs-lookup"><span data-stu-id="0963c-153">Advisor for Teams</span></span></td>
<td><span data-ttu-id="0963c-154"><a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">團隊的 Advisor</a>是<a href="https://admin.teams.microsoft.com">團隊系統管理中心</a>的一部分。</span><span class="sxs-lookup"><span data-stu-id="0963c-154"><a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">Advisor for Teams</a> is part of the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="0963c-155">它會評估您的 Microsoft 365 或 Office 365 環境，並識別最常見的設定，您可能需要更新或修改，才能成功地推出小組。</span><span class="sxs-lookup"><span data-stu-id="0963c-155">It assesses your Microsoft 365 or Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0963c-156">外部名稱解析</span><span class="sxs-lookup"><span data-stu-id="0963c-156">External Name Resolution</span></span></td>
<td><span data-ttu-id="0963c-157">請確定執行團隊用戶端的所有電腦都可以解析外部 DNS 查詢，以探索 Microsoft 365 或 Office 365 提供的服務，而且您的防火牆無法防止存取。</span><span class="sxs-lookup"><span data-stu-id="0963c-157">Be sure that all computers running the Teams client can resolve external DNS queries to discover the services provided by Microsoft 365 or Office 365 and that your firewalls are not preventing access.</span></span> <span data-ttu-id="0963c-158">如需設定防火牆埠的相關資訊，請移至<a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 和 Office 365 url 與 IP 範圍</a>。</span><span class="sxs-lookup"><span data-stu-id="0963c-158">For information about configuring firewall ports, go to <a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 and Office 365 URLs and IP ranges</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0963c-159">維護會話暫留</span><span class="sxs-lookup"><span data-stu-id="0963c-159">Maintain session persistence</span></span></td>
<td><span data-ttu-id="0963c-160">請確定您的防火牆沒有變更 UDP 的對應網路位址轉譯（NAT）位址或埠。</span><span class="sxs-lookup"><span data-stu-id="0963c-160">Make sure your firewall doesn't change the mapped Network Address Translation (NAT) addresses or ports for UDP.</span></span></td>
</tr><tr class="odd">
<td><span data-ttu-id="0963c-161">驗證 NAT 池子大小</span><span class="sxs-lookup"><span data-stu-id="0963c-161">Validate NAT pool size</span></span></td>
<td><span data-ttu-id="0963c-162">驗證使用者連線所需的網路位址轉譯（NAT）池大小。</span><span class="sxs-lookup"><span data-stu-id="0963c-162">Validate the network address translation (NAT) pool size required for user connectivity.</span></span> <span data-ttu-id="0963c-163">當多個使用者和裝置使用<a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">網路位址轉譯（NAT）或埠位址轉換（PAT）</a>存取 Microsoft 365 或 Office 365 時，您必須確保隱藏在每個公開路由的 IP 位址後面的裝置不會超過支援的數量。</span><span class="sxs-lookup"><span data-stu-id="0963c-163">When multiple users and devices access Microsoft 365 or Office 365 using <a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">Network Address Translation (NAT) or Port Address Translation (PAT)</a>, you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span> <span data-ttu-id="0963c-164">確保已將足夠的公用 IP 位址指派給 NAT 池，以避免埠耗盡。</span><span class="sxs-lookup"><span data-stu-id="0963c-164">Ensure that adequate public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="0963c-165">埠耗盡會影響內部使用者和裝置無法連線至 Microsoft 365 或 Office 365 服務的情況。</span><span class="sxs-lookup"><span data-stu-id="0963c-165">Port exhaustion will contribute to internal users and devices being unable to connect to the Microsoft 365 or Office 365 service.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0963c-166">路由至 Microsoft 資料中心</span><span class="sxs-lookup"><span data-stu-id="0963c-166">Routing to Microsoft data centers</span></span></td>
<td><span data-ttu-id="0963c-167"><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">實施最有效率的路由至 Microsoft 資料中心</a>。</span><span class="sxs-lookup"><span data-stu-id="0963c-167"><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">Implement the most efficient routing to Microsoft data centers</a>.</span></span> <span data-ttu-id="0963c-168">找出可使用當地或地區出口點數盡可能高效地連線至 Microsoft 網路的位置。</span><span class="sxs-lookup"><span data-stu-id="0963c-168">Identify locations that can use local or regional egress points to connect to the Microsoft network as efficiently as possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0963c-169">入侵偵測與防範指導方針</span><span class="sxs-lookup"><span data-stu-id="0963c-169">Intrusion Detection and Prevention Guidance</span></span></td>
<td><span data-ttu-id="0963c-170">如果您的環境針對外寄連線的安全層級部署了<a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">入侵偵測</a>或防護系統（IDS/IPS），請務必將所有 Microsoft 365 或 Office 365 url 加上白名單。</span><span class="sxs-lookup"><span data-stu-id="0963c-170">If your environment has an <a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Intrusion Detection</a> or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, be sure to whitelist all Microsoft 365 or Office 365 URLs.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0963c-171">設定分割隧道 VPN</span><span class="sxs-lookup"><span data-stu-id="0963c-171">Configure split-tunnel VPN</span></span></td>
<td><p><span data-ttu-id="0963c-172">我們建議您為小組流量提供備用路徑，這種方法會繞過虛擬私人網路（VPN），通常稱為[分割隧道 VPN](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing)。</span><span class="sxs-lookup"><span data-stu-id="0963c-172">We recommend that you provide an alternate path for Teams traffic that bypasses the virtual private network (VPN), commonly known as [split-tunnel VPN](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing).</span></span> <span data-ttu-id="0963c-173">分割隧道意味著 Microsoft 365 或 Office 365 的流量不會透過 VPN，而是直接移至 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0963c-173">Split tunneling means that traffic for Microsoft 365 or Office 365 doesn't go through the VPN but instead goes directly to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="0963c-174">略過您的 VPN 會對團隊品質產生正面影響，並減少從 VPN 裝置與組織網路的載入。</span><span class="sxs-lookup"><span data-stu-id="0963c-174">Bypassing your VPN will have a positive impact on Teams quality, and it reduces load from the VPN devices and the organization's network.</span></span> <span data-ttu-id="0963c-175">若要實現分割隧道 VPN，請與您的 VPN 廠商合作。</span><span class="sxs-lookup"><span data-stu-id="0963c-175">To implement a split-tunnel VPN, work with your VPN vendor.</span></span></p>
<p><span data-ttu-id="0963c-176">我們建議您避開 VPN 的其他原因：</span><span class="sxs-lookup"><span data-stu-id="0963c-176">Other reasons why we recommend bypassing the VPN:</span></span>
<ul>
<li><p><span data-ttu-id="0963c-177">Vpn 通常不會設計或設定為支援即時媒體。</span><span class="sxs-lookup"><span data-stu-id="0963c-177">VPNs are typically not designed or configured to support real-time media.</span></span></p></li> 
<li><p><span data-ttu-id="0963c-178">某些 Vpn 可能也不支援 UDP （這是小組所需要的）。</span><span class="sxs-lookup"><span data-stu-id="0963c-178">Some VPNs might also not support UDP (which is required for Teams).</span></span></p></li> 
<li><p><span data-ttu-id="0963c-179">Vpn 也會在已加密的媒體流量上方引入額外的加密層級。</span><span class="sxs-lookup"><span data-stu-id="0963c-179">VPNs also introduce an extra layer of encryption on top of media traffic that's already encrypted.</span></span></p></li> 
<li><p><span data-ttu-id="0963c-180">由於將流量釘選到 VPN 裝置上，因此可能無法有效地連接至團隊。</span><span class="sxs-lookup"><span data-stu-id="0963c-180">Connectivity to Teams might not be efficient due to hair-pinning traffic through a VPN device.</span></span></p></li></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0963c-181">實施 QoS</span><span class="sxs-lookup"><span data-stu-id="0963c-181">Implement QoS</span></span></td>
<td><span data-ttu-id="0963c-182"><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">使用服務品質（QoS）</a>來設定資料包優先順序。</span><span class="sxs-lookup"><span data-stu-id="0963c-182"><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">Use Quality of Service (QoS)</a> to configure packet prioritization.</span></span> <span data-ttu-id="0963c-183">這將改善團隊中的通話品質，並協助您監控通話品質並進行問題的疑難排解。</span><span class="sxs-lookup"><span data-stu-id="0963c-183">This will improve call quality in Teams and help you monitor and troubleshoot call quality.</span></span> <span data-ttu-id="0963c-184">QoS 應該在受管理的網路的所有區段上執行。</span><span class="sxs-lookup"><span data-stu-id="0963c-184">QoS should be implemented on all segments of a managed network.</span></span> <span data-ttu-id="0963c-185">即使已針對頻寬充分提供網路，QoS 也會在事件發生時，在發生意外的網路事件時，降低風險。</span><span class="sxs-lookup"><span data-stu-id="0963c-185">Even when a network has been adequately provisioned for bandwidth, QoS provides risk mitigation in the event of unanticipated network events.</span></span> <span data-ttu-id="0963c-186">透過 QoS，語音流量的優先順序會使這些意外事件不會對品質造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="0963c-186">With QoS, voice traffic is prioritized so that these unanticipated events don't negatively affect quality.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0963c-187">優化 WiFi</span><span class="sxs-lookup"><span data-stu-id="0963c-187">Optimize WiFi</span></span></td>
<td><p><span data-ttu-id="0963c-188">與 VPN 類似，WiFi 網路不一定設計或設定為支援即時媒體。</span><span class="sxs-lookup"><span data-stu-id="0963c-188">Similar to VPN, WiFi networks aren't necessarily designed or configured to support real-time media.</span></span> <span data-ttu-id="0963c-189">規劃或優化 WiFi 網路以支援小組是高品質部署的重要考慮。</span><span class="sxs-lookup"><span data-stu-id="0963c-189">Planning for, or optimizing, a WiFi network to support Teams is an important consideration for a high-quality deployment.</span></span> <span data-ttu-id="0963c-190">請考慮下列因素：</span><span class="sxs-lookup"><span data-stu-id="0963c-190">Consider these factors:</span></span></p>
<ul>
<li><p><span data-ttu-id="0963c-191">實施 QoS 或 WiFi 多媒體（WMM），以確保媒體流量在您的 WiFi 網路上適當地進行優先順序設定。</span><span class="sxs-lookup"><span data-stu-id="0963c-191">Implement QoS or WiFi Multimedia (WMM) to ensure that media traffic is getting prioritized appropriately over your WiFi networks.</span></span></p></li>
<li><p><span data-ttu-id="0963c-192">規劃及優化 WiFi 區段和存取點的位置。</span><span class="sxs-lookup"><span data-stu-id="0963c-192">Plan and optimize the WiFi bands and access point placement.</span></span> <span data-ttu-id="0963c-193">2.4 GHz 範圍可能會根據存取點位置提供適當的體驗，但存取點通常會受到在該範圍中運作的其他消費者裝置的影響。</span><span class="sxs-lookup"><span data-stu-id="0963c-193">The 2.4 GHz range might provide an adequate experience depending on access point placement, but access points are often affected by other consumer devices that operate in that range.</span></span> <span data-ttu-id="0963c-194">5 GHz 的範圍更適合用於即時媒體，因為它有大量的功能，但需要更多存取點才能取得足夠的覆蓋範圍。</span><span class="sxs-lookup"><span data-stu-id="0963c-194">The 5 GHz range is better suited to real-time media due to its dense range, but it requires more access points to get sufficient coverage.</span></span> <span data-ttu-id="0963c-195">端點也需要支援該範圍，並將其設定為可據此加以設定以利用這些區段。</span><span class="sxs-lookup"><span data-stu-id="0963c-195">Endpoints also need to support that range and be configured to leverage those bands accordingly.</span></span></p></li>
<li><p><span data-ttu-id="0963c-196">如果您使用的是雙頻帶 WiFi 網路，請考慮執行頻帶控制。</span><span class="sxs-lookup"><span data-stu-id="0963c-196">If you're using dual-band WiFi networks, consider implementing band steering.</span></span> <span data-ttu-id="0963c-197">[<em>樂隊</em>控制] 是由 WiFi 廠家提供的技術，可影響雙頻帶用戶端使用 5 GHz 範圍。</span><span class="sxs-lookup"><span data-stu-id="0963c-197"><em>Band steering</em> is a technique implemented by WiFi vendors to influence dual-band clients to use the 5 GHz range.</span></span></p></li>
<li><p><span data-ttu-id="0963c-198">當同一個頻道的存取點太靠近時，可能會導致信號重迭，並無意間爭奪，從而導致使用者無法正常使用。</span><span class="sxs-lookup"><span data-stu-id="0963c-198">When access points of the same channel are too close together, they can cause signal overlap and unintentionally compete, resulting in a bad experience for the user.</span></span> <span data-ttu-id="0963c-199">確定彼此連續的存取點位於沒有交疊的頻道上。</span><span class="sxs-lookup"><span data-stu-id="0963c-199">Ensure that access points that are next to each other are on channels that don't overlap.</span></span></p></li>
</ul>
<p><span data-ttu-id="0963c-200">每個無線廠商都有自己的部署其無線解決方案的建議。</span><span class="sxs-lookup"><span data-stu-id="0963c-200">Each wireless vendor has its own recommendations for deploying its wireless solution.</span></span> <span data-ttu-id="0963c-201">請諮詢您的 WiFi 供應商以取得特定指導方針。</span><span class="sxs-lookup"><span data-stu-id="0963c-201">Consult your WiFi vendor for specific guidance.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a><span data-ttu-id="0963c-202">頻寬需求</span><span class="sxs-lookup"><span data-stu-id="0963c-202">Bandwidth requirements</span></span>

<span data-ttu-id="0963c-203">無論您的網路狀況為何，小組都會設計為提供最佳的音訊、影片和內容共用體驗。</span><span class="sxs-lookup"><span data-stu-id="0963c-203">Teams is designed to give the best audio, video, and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="0963c-204">如此一來，當頻寬不足時，小組會將音訊品質與影片品質進行優先順序。</span><span class="sxs-lookup"><span data-stu-id="0963c-204">That said, when bandwidth is insufficient, Teams prioritizes audio quality over video quality.</span></span>

<span data-ttu-id="0963c-205">在頻寬*不*受限制的情況下，小組會優化媒體質量，包括高達1080p 的影片解析度、30fps 影片和15fps 內容，以及高保真音訊。</span><span class="sxs-lookup"><span data-stu-id="0963c-205">Where bandwidth *isn't* limited, Teams optimizes media quality, including up to 1080p video resolution, up to 30fps for video and 15fps for content, and high-fidelity audio.</span></span> 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a><span data-ttu-id="0963c-206">相關主題</span><span class="sxs-lookup"><span data-stu-id="0963c-206">Related Topics</span></span>

[<span data-ttu-id="0963c-207">Microsoft 365 和 Office 365 網路連接原則</span><span class="sxs-lookup"><span data-stu-id="0963c-207">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](https://aka.ms/pnc)

[<span data-ttu-id="0963c-208">全球端點：商務用 Skype Online 與團隊</span><span class="sxs-lookup"><span data-stu-id="0963c-208">Worldwide endpoints: Skype for Business Online and Teams</span></span>](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[<span data-ttu-id="0963c-209">小組的 Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="0963c-209">Proxy servers for Teams</span></span>](proxy-servers-for-skype-for-business-online.md)

[<span data-ttu-id="0963c-210">團隊中的媒體：為什麼會議很簡單</span><span class="sxs-lookup"><span data-stu-id="0963c-210">Media in Teams: Why meetings are simple</span></span>](https://aka.ms/teams-media)

[<span data-ttu-id="0963c-211">團隊中的媒體：深入瞭解媒體流程</span><span class="sxs-lookup"><span data-stu-id="0963c-211">Media in Teams: Deep dive into media flows</span></span>](https://aka.ms/teams-media-flows)

[<span data-ttu-id="0963c-212">Teams 中的身分識別和驗證</span><span class="sxs-lookup"><span data-stu-id="0963c-212">Identity models and authentication in Teams</span></span>](identify-models-authentication.md)

[<span data-ttu-id="0963c-213">如何推出 Teams</span><span class="sxs-lookup"><span data-stu-id="0963c-213">How to roll out Teams</span></span>](How-to-roll-out-teams.md)

