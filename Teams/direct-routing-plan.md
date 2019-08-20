---
title: 規劃直接路由
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: 請閱讀本主題, 瞭解 Microsoft 手機系統直通路由如何讓您將支援的客戶提供的會話邊界控制器 (SBC) 連線至 Microsoft Phone 系統。
ms.openlocfilehash: 8dc06650a50af5b66931f196c0a1c3d7c5090bc5
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464576"
---
# <a name="plan-direct-routing"></a><span data-ttu-id="1b40a-103">規劃直接路由</span><span class="sxs-lookup"><span data-stu-id="1b40a-103">Plan Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="1b40a-104">請觀看下列會話, 瞭解直接路由的優點、如何規劃, 以及部署方式:[直接在 Microsoft 團隊中傳送路線](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="1b40a-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="1b40a-105">Microsoft Phone 系統直通路由可讓您將支援的客戶提供的會話邊界控制器 (SBC) 連線至 Microsoft Phone 系統。</span><span class="sxs-lookup"><span data-stu-id="1b40a-105">Microsoft Phone System Direct Routing lets you connect a supported, customer-provided Session Border Controller (SBC) to Microsoft Phone System.</span></span>  <span data-ttu-id="1b40a-106">例如, 您可以使用此功能, 將內部部署 PSTN 連線與 Microsoft 團隊用戶端連線, 如下圖所示:</span><span class="sxs-lookup"><span data-stu-id="1b40a-106">With this capability, for example, you can configure on-premises PSTN connectivity with Microsoft Teams client, as shown in the following diagram:</span></span> 

<span data-ttu-id="1b40a-107">![顯示內部部署 PSTN 連線性配置的圖表](media/PlanDirectRouting1-PSTNwithTeams.png "與 Microsoft 團隊用戶端的內部部署 PSTN 連線能力")</span><span class="sxs-lookup"><span data-stu-id="1b40a-107">![Diagram showing configuration of on-premises PSTN connectivity](media/PlanDirectRouting1-PSTNwithTeams.png "Configuration of on-premises PSTN connectivity with Microsoft Teams client")</span></span>

  > [!NOTE]
  > <span data-ttu-id="1b40a-108">商務用 Skype Online 也能讓您與客戶提供的 SBC 搭配使用, 但這需要一個內部部署商務用 Skype Server 部署, 或是一個特殊版本的商務用 Skype (稱為雲端連接器), 在 SBC 與 Microsoft 雲端之間。</span><span class="sxs-lookup"><span data-stu-id="1b40a-108">Skype for Business Online also lets you pair a customer-provided SBC, but this requires an on-premises Skype for Business Server deployment or a special edition of Skype for Business, called Cloud Connector, in between the SBC and the Microsoft Cloud.</span></span> <span data-ttu-id="1b40a-109">這個案例稱為混合式語音。</span><span class="sxs-lookup"><span data-stu-id="1b40a-109">This scenario is known as hybrid voice.</span></span> <span data-ttu-id="1b40a-110">相反地, 直接路由可讓支援的 SBC 與 Microsoft 雲端之間的直接連接。</span><span class="sxs-lookup"><span data-stu-id="1b40a-110">In contrast, Direct Routing allows a direct connection between the supported SBC and the Microsoft Cloud.</span></span> 

<span data-ttu-id="1b40a-111">透過直接路由, 您可以將您的 SBC 連接到幾乎所有的電話幹線, 或與協力廠商公開的電話網絡 (PSTN) 裝置互連。</span><span class="sxs-lookup"><span data-stu-id="1b40a-111">With Direct Routing, you can connect your SBC to almost any telephony trunk or interconnect with third-party Public Switched Telephone Network (PSTN) equipment.</span></span> <span data-ttu-id="1b40a-112">[直接佈線] 可讓您:</span><span class="sxs-lookup"><span data-stu-id="1b40a-112">Direct Routing enables you to:</span></span> 

- <span data-ttu-id="1b40a-113">在 Microsoft Phone 系統中使用幾乎任何 PSTN 幹線。</span><span class="sxs-lookup"><span data-stu-id="1b40a-113">Use virtually any PSTN trunk with Microsoft Phone System.</span></span> 
- <span data-ttu-id="1b40a-114">在客戶擁有的電話語音裝置 (例如協力廠商私人分支 exchange (PBX)、類比裝置和 Microsoft Phone 系統之間設定互通性。</span><span class="sxs-lookup"><span data-stu-id="1b40a-114">Configure interoperability between customer-owned telephony equipment, such as a third-party private branch exchange (PBX), analog devices, and Microsoft Phone System.</span></span>

<span data-ttu-id="1b40a-115">Microsoft 也提供所有雲端語音解決方案, 例如通話方案。</span><span class="sxs-lookup"><span data-stu-id="1b40a-115">Microsoft also offers all-in-the-cloud voice solutions, such as Calling Plan.</span></span>  <span data-ttu-id="1b40a-116">不過, 在下列情況下, 混合式語音方案可能最適合您的組織:</span><span class="sxs-lookup"><span data-stu-id="1b40a-116">However, a hybrid voice solution might be best for your organization if:</span></span> 

- <span data-ttu-id="1b40a-117">Microsoft 通話方案不適用於您的國家/地區。</span><span class="sxs-lookup"><span data-stu-id="1b40a-117">Microsoft Calling Plan is not available in your country.</span></span> 
- <span data-ttu-id="1b40a-118">貴組織需要連線至協力廠商類比裝置、話務中心等。</span><span class="sxs-lookup"><span data-stu-id="1b40a-118">Your organization requires connection to third-party analog devices, call centers, and so on.</span></span> 
- <span data-ttu-id="1b40a-119">您的組織已擁有 PSTN 載波的現有合約。</span><span class="sxs-lookup"><span data-stu-id="1b40a-119">Your organization has an existing contract with a PSTN carrier.</span></span>

<span data-ttu-id="1b40a-120">直接路由還支援擁有 Microsoft 通話方案額外授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="1b40a-120">Direct Routing also supports users who have the additional license for the Microsoft Calling Plan.</span></span> <span data-ttu-id="1b40a-121">如需詳細資訊, 請參閱[電話系統和通話方案](calling-plan-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="1b40a-121">For more information, see [Phone System and Calling Plans](calling-plan-landing-page.md).</span></span> 

<span data-ttu-id="1b40a-122">透過直接傳送, 當使用者參與排程的會議時, Microsoft 音訊會議服務會提供撥入號碼, 這需要正確的授權。</span><span class="sxs-lookup"><span data-stu-id="1b40a-122">With Direct Routing, when users participate in a scheduled conference, the dial-in number is provided by Microsoft Audio Conferencing service, which requires proper licensing.</span></span>  <span data-ttu-id="1b40a-123">當您撥出時, Microsoft 音訊會議服務會使用線上通話功能 (需要適當的授權) 來放置通話。</span><span class="sxs-lookup"><span data-stu-id="1b40a-123">When dialing out, the Microsoft Audio Conferencing service places the call using online calling capabilities, which requires proper licensing.</span></span> <span data-ttu-id="1b40a-124">(請注意, [撥出] 不會透過 [直接路由] 路由。)如需詳細資訊, 請參閱[與團隊進行線上會議](https://products.office.com/microsoft-teams/online-meeting-solutions)。</span><span class="sxs-lookup"><span data-stu-id="1b40a-124">(Note that dialing out does not route through Direct Routing.) For more information, see [Online Meetings with Teams](https://products.office.com/microsoft-teams/online-meeting-solutions).</span></span> 
 
<span data-ttu-id="1b40a-125">規劃直接路由部署是成功實現的關鍵。</span><span class="sxs-lookup"><span data-stu-id="1b40a-125">Planning your deployment of Direct Routing is key to a successful implementation.</span></span> <span data-ttu-id="1b40a-126">本文將說明基礎結構和授權需求, 並提供 SBC 連線性的相關資訊:</span><span class="sxs-lookup"><span data-stu-id="1b40a-126">This article describes infrastructure and licensing requirements and provides information about SBC connectivity:</span></span> 

- [<span data-ttu-id="1b40a-127">基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="1b40a-127">Infrastructure requirements</span></span>](#infrastructure-requirements)
- [<span data-ttu-id="1b40a-128">授權與其他需求</span><span class="sxs-lookup"><span data-stu-id="1b40a-128">Licensing and other requirements</span></span>](#licensing-and-other-requirements)
- [<span data-ttu-id="1b40a-129">SBC 網功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="1b40a-129">SBC domain names</span></span>](#sbc-domain-names)
- [<span data-ttu-id="1b40a-130">SBC 公開信任的憑證</span><span class="sxs-lookup"><span data-stu-id="1b40a-130">Public trusted certificate for the SBC</span></span>](#public-trusted-certificate-for-the-sbc)
- [<span data-ttu-id="1b40a-131">SIP 信號: Fqdn</span><span class="sxs-lookup"><span data-stu-id="1b40a-131">SIP Signaling: FQDNs</span></span>](#sip-signaling-fqdns)
- [<span data-ttu-id="1b40a-132">SIP 信號: 埠</span><span class="sxs-lookup"><span data-stu-id="1b40a-132">SIP Signaling: Ports</span></span>](#sip-signaling-ports)
- [<span data-ttu-id="1b40a-133">媒體流量: 埠範圍</span><span class="sxs-lookup"><span data-stu-id="1b40a-133">Media traffic: Port ranges</span></span>](#media-traffic-port-ranges)
- [<span data-ttu-id="1b40a-134">支援的會話邊界控制器 (SBCs)</span><span class="sxs-lookup"><span data-stu-id="1b40a-134">Supported Session Border Controllers (SBCs)</span></span>](#supported-session-border-controllers-sbcs)

<span data-ttu-id="1b40a-135">如需有關設定直接路由的詳細資訊, 請參閱[設定直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="1b40a-135">For detailed information about configuring Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="infrastructure-requirements"></a><span data-ttu-id="1b40a-136">基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="1b40a-136">Infrastructure requirements</span></span>
<span data-ttu-id="1b40a-137">下表列出支援的 SBCs、網域及其他網路連線需求之基礎結構需求:</span><span class="sxs-lookup"><span data-stu-id="1b40a-137">The infrastructure requirements for the supported SBCs, domains, and other network connectivity requirements to deploy Direct Routing are listed in the following table:</span></span>  

|<span data-ttu-id="1b40a-138">**基礎結構需求**</span><span class="sxs-lookup"><span data-stu-id="1b40a-138">**Infrastructure requirement**</span></span>|<span data-ttu-id="1b40a-139">**您需要下列各項**</span><span class="sxs-lookup"><span data-stu-id="1b40a-139">**You need the following**</span></span>|
|:--- |:--- |
|<span data-ttu-id="1b40a-140">會話邊界控制器 (SBC)</span><span class="sxs-lookup"><span data-stu-id="1b40a-140">Session Border Controller (SBC)</span></span>|<span data-ttu-id="1b40a-141">受支援的 SBC。</span><span class="sxs-lookup"><span data-stu-id="1b40a-141">A supported SBC.</span></span> <span data-ttu-id="1b40a-142">如需詳細資訊, 請參閱[支援的 SBCs](#supported-session-border-controllers-sbcs)。</span><span class="sxs-lookup"><span data-stu-id="1b40a-142">For more information, see [Supported SBCs](#supported-session-border-controllers-sbcs).</span></span>|
|<span data-ttu-id="1b40a-143">連線至 SBC 的電話語音 trunks</span><span class="sxs-lookup"><span data-stu-id="1b40a-143">Telephony trunks connected to the SBC</span></span>|<span data-ttu-id="1b40a-144">一個或多個連線至 SBC 的電話 trunks。</span><span class="sxs-lookup"><span data-stu-id="1b40a-144">One or more telephony trunks connected to the SBC.</span></span> <span data-ttu-id="1b40a-145">在一端, SBC 透過直接路由連接到 Microsoft 手機系統。</span><span class="sxs-lookup"><span data-stu-id="1b40a-145">On one end, the SBC connects to the Microsoft Phone System via Direct Routing.</span></span> <span data-ttu-id="1b40a-146">SBC 也可以連接到協力廠商電話實體, 例如 Pbx、類比電話卡等。</span><span class="sxs-lookup"><span data-stu-id="1b40a-146">The SBC can also connect to third-party telephony entities, such as PBXs, Analog Telephony Adapters, and so on.</span></span> <span data-ttu-id="1b40a-147">任何連接至 SBC 的 PSTN 連接選項都會正常運作。</span><span class="sxs-lookup"><span data-stu-id="1b40a-147">Any PSTN connectivity option connected to the SBC will work.</span></span> <span data-ttu-id="1b40a-148">(注意: 若要將 PSTN trunks 設定為 SBC, 請參閱 SBC 廠商或主幹提供者)。</span><span class="sxs-lookup"><span data-stu-id="1b40a-148">(Note: For configuration of the PSTN trunks to SBC, please refer to the SBC vendors or trunk providers.)</span></span>|
|<span data-ttu-id="1b40a-149">Office 365 租使用者</span><span class="sxs-lookup"><span data-stu-id="1b40a-149">Office 365 tenant</span></span>|<span data-ttu-id="1b40a-150">您用來家用 Microsoft 團隊使用者的 Office 365 租使用者, 以及與 SBC 的設定和連線。</span><span class="sxs-lookup"><span data-stu-id="1b40a-150">An Office 365 tenant that you use to home your Microsoft Teams users, and the configuration and connection to the SBC.</span></span>|
|<span data-ttu-id="1b40a-151">使用者註冊機構</span><span class="sxs-lookup"><span data-stu-id="1b40a-151">User registrar</span></span>|<span data-ttu-id="1b40a-152">使用者必須駐留在 Office 365 中。</span><span class="sxs-lookup"><span data-stu-id="1b40a-152">User must be homed in Office 365.</span></span><br/><span data-ttu-id="1b40a-153">如果您的公司有內部部署商務用 Skype 或 Lync 環境, 且其混合式連線至 Office 365, 則您無法在團隊中為使用者駐留內部部署啟用語音功能。</span><span class="sxs-lookup"><span data-stu-id="1b40a-153">If your company has an on-premises Skype for Business or Lync environment with hybrid connectivity to Office 365, you cannot enable voice in Teams for a user homed on-premises.</span></span><br/><br/><span data-ttu-id="1b40a-154">若要檢查使用者的註冊機構, 請使用下列商務用 Skype Online PowerShell Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1b40a-154">To check the registrar of a user, use the following Skype for Business Online PowerShell cmdlet:</span></span><br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/><span data-ttu-id="1b40a-155">Cmdlet 的輸出應該會顯示:</span><span class="sxs-lookup"><span data-stu-id="1b40a-155">The output of the cmdlet should show:</span></span><br/><code>HostingProvider : sipfed.online.lync.com</code>|
|<span data-ttu-id="1b40a-156">定義域</span><span class="sxs-lookup"><span data-stu-id="1b40a-156">Domains</span></span>|<span data-ttu-id="1b40a-157">新增至您 Office 365 租使用者的一個或多個網域。</span><span class="sxs-lookup"><span data-stu-id="1b40a-157">One or more domains added to your Office 365 tenants.</span></span><br/><br/><span data-ttu-id="1b40a-158">**注意:** 您無法使用針對您的租使用者自動建立的預設網域 onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="1b40a-158">**Note:** You cannot use the default domain, \*.onmicrosoft.com, that is automatically created for your tenant.</span></span><br/><br/><span data-ttu-id="1b40a-159">若要查看網域, 您可以使用下列商務用 Skype Online PowerShell Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1b40a-159">To view the domains, you can use the following Skype for Business Online PowerShell cmdlet:</span></span><br/><code>Get-CsTenant \| fl Domains</code><br/><br/><span data-ttu-id="1b40a-160">如需網域和 Office 365 租使用者的詳細資訊, 請參閱[網域常見問題](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)。</span><span class="sxs-lookup"><span data-stu-id="1b40a-160">For more information about domains and Office 365 tenants, see [Domains FAQ](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).</span></span>|
|<span data-ttu-id="1b40a-161">SBC 的公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="1b40a-161">Public IP address for the SBC</span></span>|<span data-ttu-id="1b40a-162">可用於連線至 SBC 的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1b40a-162">A public IP address that can be used to connect to the SBC.</span></span> <span data-ttu-id="1b40a-163">根據 SBC 的類型而定, SBC 可以使用 NAT。</span><span class="sxs-lookup"><span data-stu-id="1b40a-163">Based on the type of SBC, the SBC can use NAT.</span></span>|
|<span data-ttu-id="1b40a-164">SBC 的完整功能變數名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="1b40a-164">Fully Qualified Domain Name (FQDN) for the SBC</span></span>|<span data-ttu-id="1b40a-165">SBC 的 FQDN, FQDN 的網域部分是您 Office 365 租使用者中已註冊的網域之一。</span><span class="sxs-lookup"><span data-stu-id="1b40a-165">A FQDN for the SBC, where the domain portion of the FQDN is one of the registered domains in your Office 365 tenant.</span></span> <span data-ttu-id="1b40a-166">如需詳細資訊, 請參閱[SBC 功能變數名稱](#sbc-domain-names)。</span><span class="sxs-lookup"><span data-stu-id="1b40a-166">For more information, see [SBC domain names](#sbc-domain-names).</span></span>|
|<span data-ttu-id="1b40a-167">SBC 的公用 DNS 專案</span><span class="sxs-lookup"><span data-stu-id="1b40a-167">Public DNS entry for the SBC</span></span> |<span data-ttu-id="1b40a-168">將 SBC FQDN 對應至公用 IP 位址的公用 DNS 專案。</span><span class="sxs-lookup"><span data-stu-id="1b40a-168">A public DNS entry mapping the SBC FQDN to the public IP Address.</span></span> |
|<span data-ttu-id="1b40a-169">SBC 公開信任的憑證</span><span class="sxs-lookup"><span data-stu-id="1b40a-169">Public trusted certificate for the SBC</span></span> |<span data-ttu-id="1b40a-170">SBC 的憑證, 用於與直接路由的所有通訊。</span><span class="sxs-lookup"><span data-stu-id="1b40a-170">A certificate for the SBC to be used for all communication with Direct Routing.</span></span> <span data-ttu-id="1b40a-171">如需詳細資訊, 請參閱[SBC 的公用信任憑證](#public-trusted-certificate-for-the-sbc)。</span><span class="sxs-lookup"><span data-stu-id="1b40a-171">For more information, see [Public trusted certificate for the SBC](#public-trusted-certificate-for-the-sbc).</span></span>|
|<span data-ttu-id="1b40a-172">直接路由的連接點</span><span class="sxs-lookup"><span data-stu-id="1b40a-172">Connection points for Direct Routing</span></span> |<span data-ttu-id="1b40a-173">直接路由的連接點是下列三個 Fqdn:</span><span class="sxs-lookup"><span data-stu-id="1b40a-173">The connection points for Direct Routing are the following three FQDNs:</span></span><br/><br/><span data-ttu-id="1b40a-174">`sip.pstnhub.microsoft.com`–必須先嘗試使用全域 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1b40a-174">`sip.pstnhub.microsoft.com` – Global FQDN, must be tried first.</span></span><br/><span data-ttu-id="1b40a-175">`sip2.pstnhub.microsoft.com`–次要 FQDN, 地理位置對應至第二個優先順序區域。</span><span class="sxs-lookup"><span data-stu-id="1b40a-175">`sip2.pstnhub.microsoft.com` – Secondary FQDN, geographically maps to the second priority region.</span></span><br/><span data-ttu-id="1b40a-176">`sip3.pstnhub.microsoft.com`–三元 FQDN, 地理位置對應至第三個優先順序區域。</span><span class="sxs-lookup"><span data-stu-id="1b40a-176">`sip3.pstnhub.microsoft.com` – Tertiary FQDN, geographically maps to the third priority region.</span></span><br/><br/><span data-ttu-id="1b40a-177">如需設定需求的相關資訊, 請參閱[SIP 信號: fqdn](#sip-signaling-fqdns)。</span><span class="sxs-lookup"><span data-stu-id="1b40a-177">For information on configuration requirements, see [SIP Signaling: FQDNs](#sip-signaling-fqdns).</span></span>|
|<span data-ttu-id="1b40a-178">用於直接路由媒體的防火牆 IP 位址和埠</span><span class="sxs-lookup"><span data-stu-id="1b40a-178">Firewall IP addresses and ports for Direct Routing media</span></span> |<span data-ttu-id="1b40a-179">SBC 會與雲端中的下列服務進行通訊:</span><span class="sxs-lookup"><span data-stu-id="1b40a-179">The SBC communicates to the following services in the cloud:</span></span><br/><br/><span data-ttu-id="1b40a-180">負責處理信號的 SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="1b40a-180">SIP Proxy, which handles the signaling</span></span><br/><span data-ttu-id="1b40a-181">處理媒體的媒體處理器-除了媒體旁路</span><span class="sxs-lookup"><span data-stu-id="1b40a-181">Media Processor, which handles media -except when Media Bypass is on</span></span><br/><br/><span data-ttu-id="1b40a-182">這兩個服務在 Microsoft 雲端中都有不同的 IP 位址, 本文稍後會說明此檔。</span><span class="sxs-lookup"><span data-stu-id="1b40a-182">These two services have separate IP addresses in Microsoft Cloud, described later in this document.</span></span><br/><br/><span data-ttu-id="1b40a-183">如需詳細資訊, 請參閱[Office 365 url 和 IP 位址範圍](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)中的[Microsoft 團隊區段](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)。</span><span class="sxs-lookup"><span data-stu-id="1b40a-183">For more information, see the [Microsoft Teams section](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) in [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> |
|<span data-ttu-id="1b40a-184">媒體傳輸設定檔</span><span class="sxs-lookup"><span data-stu-id="1b40a-184">Media Transport Profile</span></span>|<span data-ttu-id="1b40a-185">TCP/RTP/SAVP</span><span class="sxs-lookup"><span data-stu-id="1b40a-185">TCP/RTP/SAVP</span></span> <br/><span data-ttu-id="1b40a-186">UDP/RTP/SAVP</span><span class="sxs-lookup"><span data-stu-id="1b40a-186">UDP/RTP/SAVP</span></span>|
<span data-ttu-id="1b40a-187">Microsoft 團隊媒體的防火牆 IP 位址和埠</span><span class="sxs-lookup"><span data-stu-id="1b40a-187">Firewall IP addresses and ports for Microsoft Teams media</span></span> |<span data-ttu-id="1b40a-188">如需詳細資訊, 請參閱[Office 365 url 與 IP 位址範圍](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="1b40a-188">For more information, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> |
|||

## <a name="licensing-and-other-requirements"></a><span data-ttu-id="1b40a-189">授權與其他需求</span><span class="sxs-lookup"><span data-stu-id="1b40a-189">Licensing and other requirements</span></span> 

<span data-ttu-id="1b40a-190">直接傳送的使用者必須具備下列 Office 365 中指派的授權:</span><span class="sxs-lookup"><span data-stu-id="1b40a-190">Users of Direct Routing must have the following licenses assigned in Office 365:</span></span> 

- <span data-ttu-id="1b40a-191">Microsoft Phone 系統</span><span class="sxs-lookup"><span data-stu-id="1b40a-191">Microsoft Phone System</span></span> 
- <span data-ttu-id="1b40a-192">Microsoft 團隊 + 商務用 Skype 方案 2 (如果包含在授權 Sku 中)</span><span class="sxs-lookup"><span data-stu-id="1b40a-192">Microsoft Teams + Skype for Business Plan 2 if included in Licensing Sku</span></span>
- <span data-ttu-id="1b40a-193">Microsoft 音訊會議</span><span class="sxs-lookup"><span data-stu-id="1b40a-193">Microsoft Audio Conferencing</span></span> 

> [!NOTE]
> <span data-ttu-id="1b40a-194">商務用 Skype 方案不應從隨附它的任何授權 SKU 中移除。</span><span class="sxs-lookup"><span data-stu-id="1b40a-194">Skype for Business Plan should not be removed from any licensing SKU where it is included.</span></span> 


> [!IMPORTANT]
>  <span data-ttu-id="1b40a-195">如果您想要將外部參與者新增至排程的會議, 請撥打電話給他們, 或提供撥入號碼,*必須具備*音訊會議授權。</span><span class="sxs-lookup"><span data-stu-id="1b40a-195">In the case that you would like to add external participants to scheduled meetings, either by dialing out to them or by providing the dial-in number, the audio conferencing license is *required*.</span></span>

> [!NOTE]
> <span data-ttu-id="1b40a-196">*需要*音訊會議授權才能進行下列作業:</span><span class="sxs-lookup"><span data-stu-id="1b40a-196">The audio conferencing license is *required* to:</span></span>
> - <span data-ttu-id="1b40a-197">從1:1 呼叫升級到群組通話。</span><span class="sxs-lookup"><span data-stu-id="1b40a-197">Escalate from 1:1 call to a group call.</span></span>
> - <span data-ttu-id="1b40a-198">將外部參與者新增至排程的會議, 方法是撥出或提供撥入號碼。</span><span class="sxs-lookup"><span data-stu-id="1b40a-198">Add external participants to scheduled meetings, by either dialing out or providing the dial-in number.</span></span> 


<span data-ttu-id="1b40a-199">此外, 您必須確認下列事項:</span><span class="sxs-lookup"><span data-stu-id="1b40a-199">In addition, you must ensure the following:</span></span>
 
- <span data-ttu-id="1b40a-200">CsOnlineVoiceRoutingPolicy 已指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="1b40a-200">CsOnlineVoiceRoutingPolicy is assigned to the user.</span></span> 
- <span data-ttu-id="1b40a-201">在 Microsoft 團隊的租使用者層級啟用 [允許私人通話]。</span><span class="sxs-lookup"><span data-stu-id="1b40a-201">Allow Private Calling is enabled at the tenant level for Microsoft Teams.</span></span> 

<span data-ttu-id="1b40a-202">直接路由還支援 Microsoft 通話方案授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="1b40a-202">Direct Routing also supports users who are licensed for Microsoft Calling Plan.</span></span> <span data-ttu-id="1b40a-203">含有通話方案的 Microsoft Phone 系統可以使用直接路由介面傳送一些通話。</span><span class="sxs-lookup"><span data-stu-id="1b40a-203">Microsoft Phone System with Calling Plan can route some calls using the Direct Routing interface.</span></span> <span data-ttu-id="1b40a-204">不過, 使用者的電話號碼必須是線上購買或移植至 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="1b40a-204">However, the users' phone numbers must be either acquired online or ported to Microsoft.</span></span>  

<span data-ttu-id="1b40a-205">針對相同的使用者混合通話方案和直接路由連線是選擇性的, 但可能很有用, 例如, 當使用者獲指派 Microsoft 通話方案, 但想要透過 SBC 路由進行一些呼叫時。</span><span class="sxs-lookup"><span data-stu-id="1b40a-205">Mixing Calling Plan and Direct Routing connectivity for the same user is optional, but could be useful, for example, when the user is assigned a Microsoft Calling Plan but wants to route some calls via SBC.</span></span> <span data-ttu-id="1b40a-206">其中一個最常見的案例是呼叫協力廠商的 Pbx。</span><span class="sxs-lookup"><span data-stu-id="1b40a-206">One of the most common scenarios are calls to third-party PBXs.</span></span>  <span data-ttu-id="1b40a-207">透過 Microsoft 通話方案傳送協力廠商的 Pbx, 除了呼叫連接至該 Pbx 的電話之外, 所有通話都是透過但連接至協力廠商 Pbx 的電話撥打電話給 SBC, 因此請在商業網路中, 而不是 PSTN。</span><span class="sxs-lookup"><span data-stu-id="1b40a-207">With third-party PBXs, all calls, except calls to the phones connected to that PBXs, are routed via Microsoft Calling Plan; but calls to the phones connected to third-party PBXs go to the SBC, therefore stay within the enterprise network and not to the PSTN.</span></span> 

<span data-ttu-id="1b40a-208">如需有關手機系統授權的詳細資訊, 請參閱[充分利用 office 365](https://products.office.com/compare-all-microsoft-office-products?tab=2)和[Office 365 方案選項](https://technet.microsoft.com/library/office-365-plan-options.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1b40a-208">For more information about Phone System licensing, see [Get the most from Office with Office 365](https://products.office.com/compare-all-microsoft-office-products?tab=2) and [Office 365 Plan Options](https://technet.microsoft.com/library/office-365-plan-options.aspx).</span></span> 

<span data-ttu-id="1b40a-209">如需手機系統授權的詳細資訊, 請參閱[Microsoft 團隊附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="1b40a-209">For more information about Phone System licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span> 

## <a name="sbc-domain-names"></a><span data-ttu-id="1b40a-210">SBC 網功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="1b40a-210">SBC domain names</span></span>

<span data-ttu-id="1b40a-211">SBC 功能變數名稱必須來自租使用者的「網域」中所註冊的名稱之一。</span><span class="sxs-lookup"><span data-stu-id="1b40a-211">The SBC domain name must be from one of the names registered in “Domains” of the tenant.</span></span> <span data-ttu-id="1b40a-212">您無法針對 SBC 的 FQDN 名稱使用 \* onmicrosoft.com 租使用者。</span><span class="sxs-lookup"><span data-stu-id="1b40a-212">You cannot use the \*.onmicrosoft.com tenant for the FQDN name of the SBC.</span></span>

<span data-ttu-id="1b40a-213">下表顯示針對租使用者註冊的 DNS 名稱範例, 無論該名稱是否可做為 SBC 的 FQDN, 以及有效 FQDN 名稱的範例:</span><span class="sxs-lookup"><span data-stu-id="1b40a-213">The following table shows examples of DNS names registered for the tenant, whether the name can be used as a FQDN for the SBC, and examples of valid FQDN names:</span></span>

|<span data-ttu-id="1b40a-214">**DNS 名稱**</span><span class="sxs-lookup"><span data-stu-id="1b40a-214">**DNS name**</span></span>|<span data-ttu-id="1b40a-215">**可用於 SBC FQDN**</span><span class="sxs-lookup"><span data-stu-id="1b40a-215">**Can be used for SBC FQDN**</span></span>|<span data-ttu-id="1b40a-216">**FQDN 名稱範例**</span><span class="sxs-lookup"><span data-stu-id="1b40a-216">**Examples of FQDN names**</span></span>|
|:--- |:--- |:--- |
<span data-ttu-id="1b40a-217">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b40a-217">contoso.com</span></span>|<span data-ttu-id="1b40a-218">是的</span><span class="sxs-lookup"><span data-stu-id="1b40a-218">Yes</span></span>|<span data-ttu-id="1b40a-219">**有效的名稱:**</span><span class="sxs-lookup"><span data-stu-id="1b40a-219">**Valid names:**</span></span><br/><span data-ttu-id="1b40a-220">sbc1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b40a-220">sbc1.contoso.com</span></span><br/><span data-ttu-id="1b40a-221">ssbcs15.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b40a-221">ssbcs15.contoso.com</span></span><br/><span data-ttu-id="1b40a-222">europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b40a-222">europe.contoso.com</span></span>|
|<span data-ttu-id="1b40a-223">contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="1b40a-223">contoso.onmicrosoft.com</span></span>|<span data-ttu-id="1b40a-224">不</span><span class="sxs-lookup"><span data-stu-id="1b40a-224">No</span></span>|<br/><span data-ttu-id="1b40a-225">SBC 名稱不支援使用 \*. onmicrosoft.com 網域</span><span class="sxs-lookup"><span data-stu-id="1b40a-225">Using \*.onmicrosoft.com domains is not supported for SBC names</span></span>

<span data-ttu-id="1b40a-226">假設您要使用新的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="1b40a-226">Assume you want to use a new domain name.</span></span> <span data-ttu-id="1b40a-227">例如, 您的租使用者有 contoso.com 做為在您的租使用者中註冊的功能變數名稱, 而您想要使用 sbc1.sip.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="1b40a-227">For example, your tenant has contoso.com as a domain name registered in your tenant, and you want to use sbc1.sip.contoso.com.</span></span> <span data-ttu-id="1b40a-228">您必須先在租使用者的 [網域] 中註冊功能變數名稱 sip.contoso.com, 才能將其與 name sbc1.sip.contoso.com 進行配對。</span><span class="sxs-lookup"><span data-stu-id="1b40a-228">Before you can pair an SBC with the name sbc1.sip.contoso.com, you must register the domain name sip.contoso.com in "Domains" in your tenant.</span></span> <span data-ttu-id="1b40a-229">如果您在註冊功能變數名稱前嘗試搭配 sbc1.sip.contoso.com 進行配對, 您會收到下列錯誤: 「無法使用「sbc1.sip.contoso.com」網域, 因為它未針對此租使用者進行設定。」</span><span class="sxs-lookup"><span data-stu-id="1b40a-229">If you try pairing an SBC with sbc1.sip.contoso.com before registering the domain name, you will get the following error: "Cannot use the "sbc1.sip.contoso.com" domain as it was not configured for this tenant."</span></span>
<span data-ttu-id="1b40a-230">在您新增功能變數名稱之後, 您也需要使用 UPN user@sip.contoso.com 建立使用者並指派「團隊」授權。</span><span class="sxs-lookup"><span data-stu-id="1b40a-230">After you add the domain name, you also need to create a user with UPN user@sip.contoso.com and assign a "Teams" license.</span></span> <span data-ttu-id="1b40a-231">在將功能變數名稱新增至租使用者的「網域」之後, 可能需要長達24小時才能完全設定功能變數名稱, 並會為使用者指派授權。</span><span class="sxs-lookup"><span data-stu-id="1b40a-231">It might take up to 24 hours to fully provision the domain name after it is added to "Domains" of your tenant, a user with a new name is created, and a license is assigned to the user.</span></span> 

<span data-ttu-id="1b40a-232">公司可能會在一個租使用者中有數個 SIP 位址空間。</span><span class="sxs-lookup"><span data-stu-id="1b40a-232">It is possible that a company might have several SIP address spaces in one tenant.</span></span> <span data-ttu-id="1b40a-233">例如, 公司可能會將 contoso.com 做為 SIP 位址空間, 並 fabrikam.com 為第二個 SIP 位址空間。</span><span class="sxs-lookup"><span data-stu-id="1b40a-233">For example, a company might have contoso.com as a SIP address space and fabrikam.com as the second SIP address space.</span></span> <span data-ttu-id="1b40a-234">有些使用者有位址 user@contoso.com, 而有些使用者則是位址 user@fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="1b40a-234">Some users have address user@contoso.com and some users have address user@fabrikam.com.</span></span> 

<span data-ttu-id="1b40a-235">SBC 只需要一個 FQDN, 而且可以從成對的租使用者中的任何位址空間來服務使用者。</span><span class="sxs-lookup"><span data-stu-id="1b40a-235">The SBC only needs one FQDN and can service users from any address space in the paired tenant.</span></span> <span data-ttu-id="1b40a-236">例如, 擁有 name sbc1.contoso.com 的 SBC 可以接收並傳送具有位址 user@contoso.com 和 user@fabrikam.com 之使用者的 PSTN 流量, 只要這些 SIP 位址空間已在相同的租使用者中註冊。</span><span class="sxs-lookup"><span data-stu-id="1b40a-236">For example,  an SBC with the name sbc1.contoso.com can receive and send the PSTN traffic for users with addresses user@contoso.com and user@fabrikam.com as long as these SIP address spaces are registered in the same tenant.</span></span>  

## <a name="public-trusted-certificate-for-the-sbc"></a><span data-ttu-id="1b40a-237">SBC 公開信任的憑證</span><span class="sxs-lookup"><span data-stu-id="1b40a-237">Public trusted certificate for the SBC</span></span>

<span data-ttu-id="1b40a-238">Microsoft 強烈建議您透過產生認證簽署要求 (CSR) 來要求 SBC 的憑證。</span><span class="sxs-lookup"><span data-stu-id="1b40a-238">Microsoft strongly recommends that you request the certificate for the SBC by generating a certification signing request (CSR).</span></span> <span data-ttu-id="1b40a-239">如需針對 SBC 產生 CSR 的特定指示, 請參閱由您的 SBC 轉銷商提供的互連指示或檔。</span><span class="sxs-lookup"><span data-stu-id="1b40a-239">For specific instructions on generating a CSR for an SBC, refer to the interconnection instructions or documentation provided by your SBC vendors.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="1b40a-240">大多數憑證授權單位 (Ca) 需要私密金鑰大小至少為2048。</span><span class="sxs-lookup"><span data-stu-id="1b40a-240">Most Certificate Authorities (CAs) require the private key size to be at least 2048.</span></span> <span data-ttu-id="1b40a-241">產生 CSR 時, 請記住這一點。</span><span class="sxs-lookup"><span data-stu-id="1b40a-241">Keep this in mind when generating the CSR.</span></span>

<span data-ttu-id="1b40a-242">憑證必須在 [主旨]、[常見名稱] 或 [subject 替代名稱] 欄位中有 SBC FQDN。</span><span class="sxs-lookup"><span data-stu-id="1b40a-242">The certificate needs to have the SBC FQDN in the subject, common name, or subject alternate name fields.</span></span>

<span data-ttu-id="1b40a-243">或者, 直接路由支援 SAN 中的萬用字元, 而萬用字元必須符合[TLS 上標準 RFC HTTP](https://tools.ietf.org/html/rfc2818#section-3.1)的要求。</span><span class="sxs-lookup"><span data-stu-id="1b40a-243">Alternatively, Direct Routing  supports a wildcard in SAN, and the wildcard needs to conform to standard [RFC HTTP Over TLS](https://tools.ietf.org/html/rfc2818#section-3.1).</span></span> <span data-ttu-id="1b40a-244">SAN 中會使用 \* contoso.com, 這會與 SBC FQDN sbc.contoso.com 相符, 但不會與 sbc.test.contoso.com 相符。</span><span class="sxs-lookup"><span data-stu-id="1b40a-244">An example would be using \*.contoso.com in the SAN, which would match the SBC FQDN sbc.contoso.com, but wouldn’t match with sbc.test.contoso.com.</span></span>

<span data-ttu-id="1b40a-245">憑證需要由下列其中一個根憑證授權單位產生:</span><span class="sxs-lookup"><span data-stu-id="1b40a-245">The certificate needs to be generated by one of the following root certificate authorities:</span></span>

- <span data-ttu-id="1b40a-246">AffirmTrust</span><span class="sxs-lookup"><span data-stu-id="1b40a-246">AffirmTrust</span></span>
- <span data-ttu-id="1b40a-247">AddTrust 外部 CA 根目錄</span><span class="sxs-lookup"><span data-stu-id="1b40a-247">AddTrust External CA Root</span></span>
- <span data-ttu-id="1b40a-248">巴爾的摩 CyberTrust 根</span><span class="sxs-lookup"><span data-stu-id="1b40a-248">Baltimore CyberTrust Root</span></span>
- <span data-ttu-id="1b40a-249">Buypass</span><span class="sxs-lookup"><span data-stu-id="1b40a-249">Buypass</span></span>
- <span data-ttu-id="1b40a-250">Cybertrust</span><span class="sxs-lookup"><span data-stu-id="1b40a-250">Cybertrust</span></span>
- <span data-ttu-id="1b40a-251">Class 3 公用主要憑證授權單位</span><span class="sxs-lookup"><span data-stu-id="1b40a-251">Class 3 Public Primary Certification Authority</span></span>
- <span data-ttu-id="1b40a-252">Comodo 安全的根 CA</span><span class="sxs-lookup"><span data-stu-id="1b40a-252">Comodo Secure Root CA</span></span>
- <span data-ttu-id="1b40a-253">德國 Telekom</span><span class="sxs-lookup"><span data-stu-id="1b40a-253">Deutsche Telekom</span></span> 
- <span data-ttu-id="1b40a-254">DigiCert 全域根 CA</span><span class="sxs-lookup"><span data-stu-id="1b40a-254">DigiCert Global Root CA</span></span>
- <span data-ttu-id="1b40a-255">DigiCert 高確定性 EV 根 CA</span><span class="sxs-lookup"><span data-stu-id="1b40a-255">DigiCert High Assurance EV Root CA</span></span>
- <span data-ttu-id="1b40a-256">Entrust</span><span class="sxs-lookup"><span data-stu-id="1b40a-256">Entrust</span></span>
- <span data-ttu-id="1b40a-257">GlobalSign</span><span class="sxs-lookup"><span data-stu-id="1b40a-257">GlobalSign</span></span>
- <span data-ttu-id="1b40a-258">移至 Go daddy</span><span class="sxs-lookup"><span data-stu-id="1b40a-258">Go Daddy</span></span>
- <span data-ttu-id="1b40a-259">GeoTrust</span><span class="sxs-lookup"><span data-stu-id="1b40a-259">GeoTrust</span></span>
- <span data-ttu-id="1b40a-260">Verisign, Inc。</span><span class="sxs-lookup"><span data-stu-id="1b40a-260">Verisign, Inc.</span></span> 
- <span data-ttu-id="1b40a-261">Starfield</span><span class="sxs-lookup"><span data-stu-id="1b40a-261">Starfield</span></span> 
- <span data-ttu-id="1b40a-262">Microsoft 適用的 Symantec 企業行動裝置根</span><span class="sxs-lookup"><span data-stu-id="1b40a-262">Symantec Enterprise Mobile Root for Microsoft</span></span> 
- <span data-ttu-id="1b40a-263">SwissSign</span><span class="sxs-lookup"><span data-stu-id="1b40a-263">SwissSign</span></span>
- <span data-ttu-id="1b40a-264">Thawte 日戳 CA</span><span class="sxs-lookup"><span data-stu-id="1b40a-264">Thawte Timestamping CA</span></span>
- <span data-ttu-id="1b40a-265">Trustwave</span><span class="sxs-lookup"><span data-stu-id="1b40a-265">Trustwave</span></span>
- <span data-ttu-id="1b40a-266">TeliaSonera</span><span class="sxs-lookup"><span data-stu-id="1b40a-266">TeliaSonera</span></span> 
- <span data-ttu-id="1b40a-267">T 系統國際 GmbH (德國 Telekom)</span><span class="sxs-lookup"><span data-stu-id="1b40a-267">T-Systems International GmbH (Deutsche Telekom)</span></span>
- <span data-ttu-id="1b40a-268">QuoVadis</span><span class="sxs-lookup"><span data-stu-id="1b40a-268">QuoVadis</span></span>

<span data-ttu-id="1b40a-269">Microsoft 正在努力根據客戶要求新增其他認證機構。</span><span class="sxs-lookup"><span data-stu-id="1b40a-269">Microsoft is working on adding additional certification authorities based on customer requests.</span></span> 

## <a name="sip-signaling-fqdns"></a><span data-ttu-id="1b40a-270">SIP 信號: Fqdn</span><span class="sxs-lookup"><span data-stu-id="1b40a-270">SIP Signaling: FQDNs</span></span> 

<span data-ttu-id="1b40a-271">在下列 Office 365 環境中提供直接路由:</span><span class="sxs-lookup"><span data-stu-id="1b40a-271">Direct Routing is offered in the following Office 365 environments:</span></span>
- <span data-ttu-id="1b40a-272">Office 365</span><span class="sxs-lookup"><span data-stu-id="1b40a-272">Office 365</span></span>
- <span data-ttu-id="1b40a-273">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="1b40a-273">Office 365 GCC</span></span>
- <span data-ttu-id="1b40a-274">Office 365 GCC 高</span><span class="sxs-lookup"><span data-stu-id="1b40a-274">Office 365 GCC High</span></span>
- <span data-ttu-id="1b40a-275">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="1b40a-275">Office 365 DoD</span></span>

<span data-ttu-id="1b40a-276">深入瞭解[Office 365 和美國政府環境](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)(例如 GCC、gcc 高和 DoD)。</span><span class="sxs-lookup"><span data-stu-id="1b40a-276">Learn more about [Office 365 and US Government environments](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="1b40a-277">Office 365 和 Office 365 GCC 環境</span><span class="sxs-lookup"><span data-stu-id="1b40a-277">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="1b40a-278">直接路由的連接點是下列三個 Fqdn:</span><span class="sxs-lookup"><span data-stu-id="1b40a-278">The connection point for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="1b40a-279">**sip.pstnhub.microsoft.com** –全域 FQDN-必須先嘗試。</span><span class="sxs-lookup"><span data-stu-id="1b40a-279">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="1b40a-280">當 SBC 傳送要求來解析此名稱時, Microsoft Azure DNS 伺服器會傳回指向指派給 SBC 之主要 Azure 資料中心的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1b40a-280">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="1b40a-281">作業是以資料中心的效能指標, 以及與 SBC 有關的地理位置為基礎。</span><span class="sxs-lookup"><span data-stu-id="1b40a-281">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="1b40a-282">傳回的 IP 位址會對應到主要 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1b40a-282">The IP address returned corresponds to the primary FQDN.</span></span>
- <span data-ttu-id="1b40a-283">**sip2.pstnhub.microsoft.com** –次要 FQDN-地理位置對應至第二個優先順序區域。</span><span class="sxs-lookup"><span data-stu-id="1b40a-283">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>
- <span data-ttu-id="1b40a-284">**sip3.pstnhub.microsoft.com** –三元 FQDN-[地理位置] 對應至第三個優先順序區域。</span><span class="sxs-lookup"><span data-stu-id="1b40a-284">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="1b40a-285">若要執行下列三個 Fqdn, 必須進行下列動作:</span><span class="sxs-lookup"><span data-stu-id="1b40a-285">Placing these three FQDNs in order is required to:</span></span>

- <span data-ttu-id="1b40a-286">提供最佳的使用體驗 (在所指派的 SBC 資料中心較少且最接近的情況下, 由查詢第一個 FQDN)。</span><span class="sxs-lookup"><span data-stu-id="1b40a-286">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>
- <span data-ttu-id="1b40a-287">提供從 SBC 連線到發生暫時問題的資料中心時的容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="1b40a-287">Provide failover when connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="1b40a-288">如需詳細資訊, 請參閱下方的[容錯移轉機制](#failover-mechanism-for-sip-signaling)。</span><span class="sxs-lookup"><span data-stu-id="1b40a-288">For more information, see [Failover mechanism](#failover-mechanism-for-sip-signaling) below.</span></span>  

<span data-ttu-id="1b40a-289">Fqdn (sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com 和 sip3.pstnhub.microsoft.com) 會解析成下列其中一個 IP 位址:</span><span class="sxs-lookup"><span data-stu-id="1b40a-289">The FQDNs – sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com and sip3.pstnhub.microsoft.com – will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="1b40a-290">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="1b40a-290">52.114.148.0</span></span>
- <span data-ttu-id="1b40a-291">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="1b40a-291">52.114.132.46</span></span> 
- <span data-ttu-id="1b40a-292">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="1b40a-292">52.114.75.24</span></span> 
- <span data-ttu-id="1b40a-293">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="1b40a-293">52.114.76.76</span></span> 
- <span data-ttu-id="1b40a-294">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="1b40a-294">52.114.7.24</span></span> 
- <span data-ttu-id="1b40a-295">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="1b40a-295">52.114.14.70</span></span>

<span data-ttu-id="1b40a-296">您必須在防火牆中開啟所有這些 IP 位址的埠, 以允許傳入及傳出流量進出位址來傳送信號。</span><span class="sxs-lookup"><span data-stu-id="1b40a-296">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="1b40a-297">如果您的防火牆支援 DNS 名稱, FQDN sip-all.pstnhub.microsoft.com 會解析為所有這些 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1b40a-297">If your firewall supports DNS names, the FQDN sip-all.pstnhub.microsoft.com resolves to all these IP addresses.</span></span> 


### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="1b40a-298">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="1b40a-298">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="1b40a-299">直接路由的連接點是下列 FQDN:</span><span class="sxs-lookup"><span data-stu-id="1b40a-299">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="1b40a-300">**sip.pstnhub.dod.teams.microsoft.us** –全域 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1b40a-300">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="1b40a-301">因為 Office 365 DoD 環境僅存在於美國資料中心, 所以沒有次要和第三個 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="1b40a-301">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="1b40a-302">Fqdn – sip.pstnhub.dod.teams.microsoft.us 將會解析成下列其中一個 IP 位址:</span><span class="sxs-lookup"><span data-stu-id="1b40a-302">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="1b40a-303">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="1b40a-303">52.127.64.33</span></span>
- <span data-ttu-id="1b40a-304">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="1b40a-304">52.127.68.34</span></span>

<span data-ttu-id="1b40a-305">您必須在防火牆中開啟所有這些 IP 位址的埠, 以允許傳入及傳出流量進出位址來傳送信號。</span><span class="sxs-lookup"><span data-stu-id="1b40a-305">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="1b40a-306">如果您的防火牆支援 DNS 名稱, FQDN sip.pstnhub.dod.teams.microsoft.us 會解析為所有這些 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1b40a-306">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="1b40a-307">Office 365 GCC 高環境</span><span class="sxs-lookup"><span data-stu-id="1b40a-307">Office 365 GCC High environment</span></span>

<span data-ttu-id="1b40a-308">直接路由的連接點是下列 FQDN:</span><span class="sxs-lookup"><span data-stu-id="1b40a-308">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="1b40a-309">**sip.pstnhub.gov.teams.microsoft.us** –全域 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1b40a-309">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="1b40a-310">由於 GCC 的高環境僅存在於美國資料中心, 因此沒有副及三元 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="1b40a-310">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="1b40a-311">Fqdn – sip.pstnhub.gov.teams.microsoft.us 將會解析成下列其中一個 IP 位址:</span><span class="sxs-lookup"><span data-stu-id="1b40a-311">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="1b40a-312">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="1b40a-312">52.127.88.59</span></span>
- <span data-ttu-id="1b40a-313">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="1b40a-313">52.127.92.64</span></span>

<span data-ttu-id="1b40a-314">您必須在防火牆中開啟所有這些 IP 位址的埠, 以允許傳入及傳出流量進出位址來傳送信號。</span><span class="sxs-lookup"><span data-stu-id="1b40a-314">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="1b40a-315">如果您的防火牆支援 DNS 名稱, FQDN sip.pstnhub.gov.teams.microsoft.us 會解析為所有這些 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1b40a-315">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="1b40a-316">SIP 信號: 埠</span><span class="sxs-lookup"><span data-stu-id="1b40a-316">SIP Signaling: Ports</span></span>

<span data-ttu-id="1b40a-317">對於所有提供直接路由的 Office 365 環境而言, 埠需求都是相同的:</span><span class="sxs-lookup"><span data-stu-id="1b40a-317">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="1b40a-318">Office 365</span><span class="sxs-lookup"><span data-stu-id="1b40a-318">Office 365</span></span>
- <span data-ttu-id="1b40a-319">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="1b40a-319">Office 365 GCC</span></span>
- <span data-ttu-id="1b40a-320">Office 365 GCC 高</span><span class="sxs-lookup"><span data-stu-id="1b40a-320">Office 365 GCC High</span></span>
- <span data-ttu-id="1b40a-321">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="1b40a-321">Office 365 DoD</span></span>

<span data-ttu-id="1b40a-322">您必須使用下列埠:</span><span class="sxs-lookup"><span data-stu-id="1b40a-322">You must use the following ports:</span></span>

|<span data-ttu-id="1b40a-323">**頻寬**</span><span class="sxs-lookup"><span data-stu-id="1b40a-323">**Traffic**</span></span>|<span data-ttu-id="1b40a-324">**從**</span><span class="sxs-lookup"><span data-stu-id="1b40a-324">**From**</span></span>|<span data-ttu-id="1b40a-325">**自**</span><span class="sxs-lookup"><span data-stu-id="1b40a-325">**To**</span></span>|<span data-ttu-id="1b40a-326">**來源埠**</span><span class="sxs-lookup"><span data-stu-id="1b40a-326">**Source port**</span></span>|<span data-ttu-id="1b40a-327">**目的地埠**</span><span class="sxs-lookup"><span data-stu-id="1b40a-327">**Destination port**</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="1b40a-328">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="1b40a-328">SIP/TLS</span></span>|<span data-ttu-id="1b40a-329">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="1b40a-329">SIP Proxy</span></span>|<span data-ttu-id="1b40a-330">SBC</span><span class="sxs-lookup"><span data-stu-id="1b40a-330">SBC</span></span>|<span data-ttu-id="1b40a-331">1024–65535</span><span class="sxs-lookup"><span data-stu-id="1b40a-331">1024 – 65535</span></span>|<span data-ttu-id="1b40a-332">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="1b40a-332">Defined on the SBC</span></span>|
<span data-ttu-id="1b40a-333">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="1b40a-333">SIP/TLS</span></span>|<span data-ttu-id="1b40a-334">SBC</span><span class="sxs-lookup"><span data-stu-id="1b40a-334">SBC</span></span>|<span data-ttu-id="1b40a-335">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="1b40a-335">SIP Proxy</span></span>|<span data-ttu-id="1b40a-336">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="1b40a-336">Defined on the SBC</span></span>|<span data-ttu-id="1b40a-337">5061</span><span class="sxs-lookup"><span data-stu-id="1b40a-337">5061</span></span>|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a><span data-ttu-id="1b40a-338">SIP 信號的容錯移轉機制</span><span class="sxs-lookup"><span data-stu-id="1b40a-338">Failover mechanism for SIP Signaling</span></span>

<span data-ttu-id="1b40a-339">SBC 會進行 DNS 查詢來解析 sip.pstnhub.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="1b40a-339">The SBC makes a DNS query to resolve sip.pstnhub.microsoft.com.</span></span> <span data-ttu-id="1b40a-340">根據 SBC 位置和資料中心效能指標, 選取主要資料中心。</span><span class="sxs-lookup"><span data-stu-id="1b40a-340">Based on the SBC location and the datacenter performance metrics, the primary datacenter is selected.</span></span> <span data-ttu-id="1b40a-341">如果主要資料中心遇到問題, SBC 將會嘗試可解析為第二個已指定資料中心的 sip2.pstnhub.microsoft.com, 而且在兩個區域中的資料中心無法使用的情況下, SBC 會重試最後一個 FQDN (sip3.pstnhub.microsoft.com), 提供第三個資料中心 IP。</span><span class="sxs-lookup"><span data-stu-id="1b40a-341">If the primary datacenter experiences an issue, the SBC will try the sip2.pstnhub.microsoft.com, which resolves to the second assigned datacenter, and, in the rare case that datacenters in two regions are not available, the SBC retries the last FQDN (sip3.pstnhub.microsoft.com), which provides the tertiary datacenter IP.</span></span>

<span data-ttu-id="1b40a-342">下表摘要列出主要、次要及三元資料中心之間的關聯:</span><span class="sxs-lookup"><span data-stu-id="1b40a-342">The table below summarizes the relationships between primary, secondary, and tertiary datacenters:</span></span>

|<span data-ttu-id="1b40a-343">**如果主要資料中心是**</span><span class="sxs-lookup"><span data-stu-id="1b40a-343">**If the primary datacenter is**</span></span>|<span data-ttu-id="1b40a-344">**中東**</span><span class="sxs-lookup"><span data-stu-id="1b40a-344">**EMEA**</span></span>|<span data-ttu-id="1b40a-345">**NOAM**</span><span class="sxs-lookup"><span data-stu-id="1b40a-345">**NOAM**</span></span>|<span data-ttu-id="1b40a-346">**太**</span><span class="sxs-lookup"><span data-stu-id="1b40a-346">**ASIA**</span></span>|
|:--- |:--- |:--- |:--- |
|<span data-ttu-id="1b40a-347">副資料中心 (sip2.pstnhub.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="1b40a-347">The secondary datacenter (sip2.pstnhub.microsoft.com)</span></span>|<span data-ttu-id="1b40a-348">一下</span><span class="sxs-lookup"><span data-stu-id="1b40a-348">US</span></span>|<span data-ttu-id="1b40a-349">歐洲</span><span class="sxs-lookup"><span data-stu-id="1b40a-349">EU</span></span>|<span data-ttu-id="1b40a-350">一下</span><span class="sxs-lookup"><span data-stu-id="1b40a-350">US</span></span>|
|<span data-ttu-id="1b40a-351">第三個資料中心 (sip3.pstnhub.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="1b40a-351">The tertiary datacenter (sip3.pstnhub.microsoft.com)</span></span>|<span data-ttu-id="1b40a-352">太</span><span class="sxs-lookup"><span data-stu-id="1b40a-352">ASIA</span></span>|<span data-ttu-id="1b40a-353">太</span><span class="sxs-lookup"><span data-stu-id="1b40a-353">ASIA</span></span>|<span data-ttu-id="1b40a-354">歐洲</span><span class="sxs-lookup"><span data-stu-id="1b40a-354">EU</span></span>|
|||||

## <a name="media-traffic-port-ranges"></a><span data-ttu-id="1b40a-355">媒體流量: 埠範圍</span><span class="sxs-lookup"><span data-stu-id="1b40a-355">Media traffic: Port ranges</span></span>
<span data-ttu-id="1b40a-356">請注意, 如果您想要在不使用媒體的情況下部署直接路由, 請套用下列需求。</span><span class="sxs-lookup"><span data-stu-id="1b40a-356">Note that the requirements below apply if you want to deploy Direct Routing without Media Bypass.</span></span> <span data-ttu-id="1b40a-357">如需媒體旁路的防火牆需求, 請參閱[使用直接路由來規劃媒體旁路](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-plan-media-bypass)。</span><span class="sxs-lookup"><span data-stu-id="1b40a-357">For firewall requirements for Media Bypass, please refer to [Plan for media bypass with Direct Routing](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-plan-media-bypass).</span></span>



<span data-ttu-id="1b40a-358">媒體流量會流過 Microsoft 雲端中的個別服務。</span><span class="sxs-lookup"><span data-stu-id="1b40a-358">The media traffic flows to and from a separate service in the Microsoft Cloud.</span></span> <span data-ttu-id="1b40a-359">媒體流量的 IP 範圍:</span><span class="sxs-lookup"><span data-stu-id="1b40a-359">The IP range for Media traffic:</span></span>

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="1b40a-360">Office 365 和 Office 365 GCC 環境</span><span class="sxs-lookup"><span data-stu-id="1b40a-360">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="1b40a-361">52.112.0.0/14 (從52.112.0.1 到52.115.255.254 的 IP 位址)。</span><span class="sxs-lookup"><span data-stu-id="1b40a-361">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254).</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="1b40a-362">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="1b40a-362">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="1b40a-363">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="1b40a-363">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="1b40a-364">Office 365 GCC 高環境</span><span class="sxs-lookup"><span data-stu-id="1b40a-364">Office 365 GCC High environment</span></span>

- <span data-ttu-id="1b40a-365">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="1b40a-365">52.127.88.0/21</span></span>

### <a name="port-range-applicable-to-all-environments"></a><span data-ttu-id="1b40a-366">埠範圍 (適用于所有環境)</span><span class="sxs-lookup"><span data-stu-id="1b40a-366">Port range (applicable to all environments)</span></span>
<span data-ttu-id="1b40a-367">媒體處理器的埠範圍如下表所示:</span><span class="sxs-lookup"><span data-stu-id="1b40a-367">The port range of the Media Processors is shown in the following table:</span></span> 

|<span data-ttu-id="1b40a-368">**頻寬**</span><span class="sxs-lookup"><span data-stu-id="1b40a-368">**Traffic**</span></span>|<span data-ttu-id="1b40a-369">**從**</span><span class="sxs-lookup"><span data-stu-id="1b40a-369">**From**</span></span>|<span data-ttu-id="1b40a-370">**自**</span><span class="sxs-lookup"><span data-stu-id="1b40a-370">**To**</span></span>|<span data-ttu-id="1b40a-371">**來源埠**</span><span class="sxs-lookup"><span data-stu-id="1b40a-371">**Source port**</span></span>|<span data-ttu-id="1b40a-372">**目的地埠**</span><span class="sxs-lookup"><span data-stu-id="1b40a-372">**Destination port**</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="1b40a-373">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="1b40a-373">UDP/SRTP</span></span>|<span data-ttu-id="1b40a-374">媒體處理器</span><span class="sxs-lookup"><span data-stu-id="1b40a-374">Media Processor</span></span>|<span data-ttu-id="1b40a-375">SBC</span><span class="sxs-lookup"><span data-stu-id="1b40a-375">SBC</span></span>|<span data-ttu-id="1b40a-376">49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="1b40a-376">49 152 – 53 247</span></span>|<span data-ttu-id="1b40a-377">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="1b40a-377">Defined on the SBC</span></span>|
|<span data-ttu-id="1b40a-378">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="1b40a-378">UDP/SRTP</span></span>|<span data-ttu-id="1b40a-379">SBC</span><span class="sxs-lookup"><span data-stu-id="1b40a-379">SBC</span></span>|<span data-ttu-id="1b40a-380">媒體處理器</span><span class="sxs-lookup"><span data-stu-id="1b40a-380">Media Processor</span></span>|<span data-ttu-id="1b40a-381">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="1b40a-381">Defined on the SBC</span></span>|<span data-ttu-id="1b40a-382">49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="1b40a-382">49 152 – 53 247</span></span>|
|

  > [!NOTE]
  > <span data-ttu-id="1b40a-383">Microsoft 建議在 SBC 上每個併發呼叫至少有兩個埠。</span><span class="sxs-lookup"><span data-stu-id="1b40a-383">Microsoft  recommends at least two ports per concurrent call on the SBC.</span></span>

## <a name="media-traffic-codecs"></a><span data-ttu-id="1b40a-384">媒體流量: 編解碼器</span><span class="sxs-lookup"><span data-stu-id="1b40a-384">Media traffic: Codecs</span></span>

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a><span data-ttu-id="1b40a-385">在 SBC 與雲端媒體處理器或 Microsoft 團隊用戶端之間的腿。</span><span class="sxs-lookup"><span data-stu-id="1b40a-385">Leg between SBC and Cloud Media Processor or Microsoft Teams client.</span></span>
<span data-ttu-id="1b40a-386">適用于媒體旁路大小寫和非旁路情況</span><span class="sxs-lookup"><span data-stu-id="1b40a-386">Applies to both media bypass case and non-bypass cases</span></span>

<span data-ttu-id="1b40a-387">在會話邊界控制器和雲端媒體處理器 (沒有媒體旁路) 或團隊用戶端與 SBC (如果已啟用媒體旁路) 之間, 在腿的直接路由介面上, 您可以使用下列編解碼器:</span><span class="sxs-lookup"><span data-stu-id="1b40a-387">The Direct Routing interface on the leg between the Session Border Controller and Cloud Media Processor (without media bypass) or between the Teams client and the SBC (if Media Bypass enabled) can use the following codecs:</span></span>
- <span data-ttu-id="1b40a-388">非媒體旁路 (SBC 到雲端媒體處理器): 絞絲、711、722、G 729</span><span class="sxs-lookup"><span data-stu-id="1b40a-388">Non-Media bypass (SBC to Cloud Media Processor): SILK, G.711, G.722, G.729</span></span>
- <span data-ttu-id="1b40a-389">媒體旁路 (SBC 至團隊用戶端): 絞絲、711、722、G 729、OPUS</span><span class="sxs-lookup"><span data-stu-id="1b40a-389">Media Bypass (SBC to Teams client):  SILK, G.711, G.722, G.729, OPUS</span></span>

<span data-ttu-id="1b40a-390">您可以從優惠中排除不想要的編解碼器, 以強制在會話邊界控制器上使用特定的編解碼器。</span><span class="sxs-lookup"><span data-stu-id="1b40a-390">You can force use of the specific codec on the Session Border Controller by excluding undesirable codecs from the offer.</span></span>

### <a name="leg-between-microsoft-teams-client--and-cloud-media-processor"></a><span data-ttu-id="1b40a-391">Microsoft 團隊用戶端與雲端媒體處理器之間的腿</span><span class="sxs-lookup"><span data-stu-id="1b40a-391">Leg between Microsoft Teams Client  and Cloud Media Processor</span></span>
<span data-ttu-id="1b40a-392">僅適用于非媒體旁路大小寫。</span><span class="sxs-lookup"><span data-stu-id="1b40a-392">Applies to non-media bypass case only.</span></span> <span data-ttu-id="1b40a-393">在團隊用戶端和 SBC 之間, 將媒體旁路媒體直接流向</span><span class="sxs-lookup"><span data-stu-id="1b40a-393">With Media Bypass media flows directly between Teams client and SBC</span></span>

<span data-ttu-id="1b40a-394">在雲端媒體處理器與 Microsoft 團隊用戶端之間的腿上, 使用的是絞絲或722。</span><span class="sxs-lookup"><span data-stu-id="1b40a-394">On the leg between the Cloud Media Processor and Microsoft Teams client either SILK or G.722 used.</span></span> <span data-ttu-id="1b40a-395">此腿上以 Microsoft 演算法為基礎的編解碼器選擇, 會考慮多個參數。</span><span class="sxs-lookup"><span data-stu-id="1b40a-395">The codec choice on this leg  based on Microsoft algorithms, which take into consideration multiple parameters.</span></span> 


## <a name="supported-session-border-controllers-sbcs"></a><span data-ttu-id="1b40a-396">支援的會話邊界控制器 (SBCs)</span><span class="sxs-lookup"><span data-stu-id="1b40a-396">Supported Session Border Controllers (SBCs)</span></span>

<span data-ttu-id="1b40a-397">Microsoft 只支援驗證的 SBCs 與直接路由配對。</span><span class="sxs-lookup"><span data-stu-id="1b40a-397">Microsoft only supports certified SBCs to pair with Direct Routing.</span></span> <span data-ttu-id="1b40a-398">因為企業語音對企業而言是很重要的, Microsoft 會以所選的 SBCs 來執行大量測試, 並與 SBC 廠商搭配使用, 以確保兩個系統相容。</span><span class="sxs-lookup"><span data-stu-id="1b40a-398">Because Enterprise Voice is critical for businesses, Microsoft runs intensive tests with the selected SBCs, and works with the SBC vendors to ensure the two systems are compatible.</span></span> 

<span data-ttu-id="1b40a-399">已驗證的裝置會列為 [團隊直接路由] 的 [認證者]。</span><span class="sxs-lookup"><span data-stu-id="1b40a-399">Devices that have been validated are listed as Certified for Teams Direct Routing.</span></span> <span data-ttu-id="1b40a-400">認證的裝置在所有情況下都能保證正常運作。</span><span class="sxs-lookup"><span data-stu-id="1b40a-400">The certified devices are guaranteed to work in all scenarios.</span></span> 

<span data-ttu-id="1b40a-401">如需支援的 SBCs 的詳細資訊, 請參閱[認證以直接路由的會話邊界控制器清單](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="1b40a-401">For more information about supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

 
## <a name="see-also"></a><span data-ttu-id="1b40a-402">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1b40a-402">See also</span></span>

[<span data-ttu-id="1b40a-403">設定直接路由</span><span class="sxs-lookup"><span data-stu-id="1b40a-403">Configure Direct Routing</span></span>](direct-routing-configure.md)



