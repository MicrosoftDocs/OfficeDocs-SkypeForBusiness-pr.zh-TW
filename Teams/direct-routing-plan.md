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
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: 瞭解 Microsoft Phone 系統 Direct 路由如何讓您將支援的客戶提供的會話邊界控制器（SBC）連線至 Microsoft Phone 系統。
ms.openlocfilehash: bd221be2174a538956667e0b113d459f2293882f
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691229"
---
# <a name="plan-direct-routing"></a><span data-ttu-id="09741-103">規劃直接路由</span><span class="sxs-lookup"><span data-stu-id="09741-103">Plan Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="09741-104">請觀看下列會話，瞭解直接路由的優點、如何規劃，以及部署方式：[直接在 Microsoft 團隊中傳送路線](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="09741-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="09741-105">Microsoft Phone 系統直通路由可讓您將支援的客戶提供的會話邊界控制器（SBC）連線至 Microsoft Phone 系統。</span><span class="sxs-lookup"><span data-stu-id="09741-105">Microsoft Phone System Direct Routing lets you connect a supported, customer-provided Session Border Controller (SBC) to Microsoft Phone System.</span></span>  <span data-ttu-id="09741-106">例如，有了這項功能，您就可以設定與 Microsoft 團隊用戶端的內部部署公用電話網絡（PSTN）連線，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="09741-106">With this capability, for example, you can configure on-premises Public Switched Telephone Network (PSTN) connectivity with Microsoft Teams client, as shown in the following diagram:</span></span> 

<span data-ttu-id="09741-107">![顯示內部部署 PSTN 連線性配置的圖表](media/PlanDirectRouting1-PSTNwithTeams.png "與 Microsoft 團隊用戶端的內部部署 PSTN 連線能力")</span><span class="sxs-lookup"><span data-stu-id="09741-107">![Diagram showing configuration of on-premises PSTN connectivity](media/PlanDirectRouting1-PSTNwithTeams.png "Configuration of on-premises PSTN connectivity with Microsoft Teams client")</span></span>

  > [!NOTE]
  > <span data-ttu-id="09741-108">商務用 Skype Online 也能讓您與客戶提供的 SBC 搭配使用，但這需要一個內部部署商務用 Skype Server 部署，或是一個特殊版本的商務用 Skype （稱為雲端連接器），在 SBC 與 Microsoft 雲端之間。</span><span class="sxs-lookup"><span data-stu-id="09741-108">Skype for Business Online also lets you pair a customer-provided SBC, but this requires an on-premises Skype for Business Server deployment or a special edition of Skype for Business, called Cloud Connector, in between the SBC and the Microsoft Cloud.</span></span> <span data-ttu-id="09741-109">這個案例稱為混合式語音。</span><span class="sxs-lookup"><span data-stu-id="09741-109">This scenario is known as hybrid voice.</span></span> <span data-ttu-id="09741-110">相反地，直接路由可讓支援的 SBC 與 Microsoft 雲端之間的直接連接。</span><span class="sxs-lookup"><span data-stu-id="09741-110">In contrast, Direct Routing allows a direct connection between the supported SBC and the Microsoft Cloud.</span></span> 

<span data-ttu-id="09741-111">透過直接路由，您可以將您的 SBC 連接到幾乎所有的電話幹線或與協力廠商 PSTN 裝置的互聯。</span><span class="sxs-lookup"><span data-stu-id="09741-111">With Direct Routing, you can connect your SBC to almost any telephony trunk or interconnect with third-party PSTN equipment.</span></span> <span data-ttu-id="09741-112">[直接佈線] 可讓您：</span><span class="sxs-lookup"><span data-stu-id="09741-112">Direct Routing enables you to:</span></span> 

- <span data-ttu-id="09741-113">在 Microsoft Phone 系統中使用幾乎任何 PSTN 幹線。</span><span class="sxs-lookup"><span data-stu-id="09741-113">Use virtually any PSTN trunk with Microsoft Phone System.</span></span> 
- <span data-ttu-id="09741-114">在客戶擁有的電話語音裝置（例如協力廠商私人分支 exchange （PBX）、類比裝置和 Microsoft Phone 系統之間設定互通性。</span><span class="sxs-lookup"><span data-stu-id="09741-114">Configure interoperability between customer-owned telephony equipment, such as a third-party private branch exchange (PBX), analog devices, and Microsoft Phone System.</span></span>

<span data-ttu-id="09741-115">Microsoft 也提供所有雲端語音解決方案，例如通話方案。</span><span class="sxs-lookup"><span data-stu-id="09741-115">Microsoft also offers all-in-the-cloud voice solutions, such as Calling Plan.</span></span> <span data-ttu-id="09741-116">不過，在下列情況下，混合式語音方案可能最適合您的組織：</span><span class="sxs-lookup"><span data-stu-id="09741-116">However, a hybrid voice solution might be best for your organization if:</span></span> 

- <span data-ttu-id="09741-117">Microsoft 通話方案不適用於您的國家/地區。</span><span class="sxs-lookup"><span data-stu-id="09741-117">Microsoft Calling Plan is not available in your country.</span></span> 
- <span data-ttu-id="09741-118">貴組織需要連線至協力廠商類比裝置、話務中心等。</span><span class="sxs-lookup"><span data-stu-id="09741-118">Your organization requires connection to third-party analog devices, call centers, and so on.</span></span> 
- <span data-ttu-id="09741-119">您的組織已擁有 PSTN 載波的現有合約。</span><span class="sxs-lookup"><span data-stu-id="09741-119">Your organization has an existing contract with a PSTN carrier.</span></span>

<span data-ttu-id="09741-120">直接路由還支援擁有 Microsoft 通話方案額外授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="09741-120">Direct Routing also supports users who have the additional license for the Microsoft Calling Plan.</span></span> <span data-ttu-id="09741-121">如需詳細資訊，請參閱[電話系統和通話方案](calling-plan-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="09741-121">For more information, see [Phone System and Calling Plans](calling-plan-landing-page.md).</span></span> 

<span data-ttu-id="09741-122">透過直接傳送，當使用者參與排程的會議時，Microsoft 音訊會議服務會提供撥入號碼，這需要正確的授權。</span><span class="sxs-lookup"><span data-stu-id="09741-122">With Direct Routing, when users participate in a scheduled conference, the dial-in number is provided by Microsoft Audio Conferencing service, which requires proper licensing.</span></span>  <span data-ttu-id="09741-123">當您撥出時，Microsoft 音訊會議服務會使用線上通話功能（需要適當的授權）來放置通話。</span><span class="sxs-lookup"><span data-stu-id="09741-123">When dialing out, the Microsoft Audio Conferencing service places the call using online calling capabilities, which requires proper licensing.</span></span> <span data-ttu-id="09741-124">（請注意，[撥出] 不會透過 [直接路由] 路由。）如需詳細資訊，請參閱[與團隊進行線上會議](https://products.office.com/microsoft-teams/online-meeting-solutions)。</span><span class="sxs-lookup"><span data-stu-id="09741-124">(Note that dialing out does not route through Direct Routing.) For more information, see [Online Meetings with Teams](https://products.office.com/microsoft-teams/online-meeting-solutions).</span></span> 
 
<span data-ttu-id="09741-125">規劃直接路由部署是成功實現的關鍵。</span><span class="sxs-lookup"><span data-stu-id="09741-125">Planning your deployment of Direct Routing is key to a successful implementation.</span></span> <span data-ttu-id="09741-126">本文將說明基礎結構和授權需求，並提供 SBC 連線性的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="09741-126">This article describes infrastructure and licensing requirements and provides information about SBC connectivity:</span></span> 

- [<span data-ttu-id="09741-127">基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="09741-127">Infrastructure requirements</span></span>](#infrastructure-requirements)
- [<span data-ttu-id="09741-128">授權與其他需求</span><span class="sxs-lookup"><span data-stu-id="09741-128">Licensing and other requirements</span></span>](#licensing-and-other-requirements)
- [<span data-ttu-id="09741-129">SBC 網功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="09741-129">SBC domain names</span></span>](#sbc-domain-names)
- [<span data-ttu-id="09741-130">SBC 公開信任的憑證</span><span class="sxs-lookup"><span data-stu-id="09741-130">Public trusted certificate for the SBC</span></span>](#public-trusted-certificate-for-the-sbc)
- [<span data-ttu-id="09741-131">SIP 信號： Fqdn</span><span class="sxs-lookup"><span data-stu-id="09741-131">SIP Signaling: FQDNs</span></span>](#sip-signaling-fqdns)
- [<span data-ttu-id="09741-132">SIP 信號：埠</span><span class="sxs-lookup"><span data-stu-id="09741-132">SIP Signaling: Ports</span></span>](#sip-signaling-ports)
- [<span data-ttu-id="09741-133">媒體流量：埠範圍</span><span class="sxs-lookup"><span data-stu-id="09741-133">Media traffic: Port ranges</span></span>](#media-traffic-port-ranges)
- [<span data-ttu-id="09741-134">支援的會話邊界控制器（SBCs）</span><span class="sxs-lookup"><span data-stu-id="09741-134">Supported Session Border Controllers (SBCs)</span></span>](#supported-session-border-controllers-sbcs)

<span data-ttu-id="09741-135">如需有關設定直接路由的詳細資訊，請參閱[設定直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="09741-135">For detailed information about configuring Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="infrastructure-requirements"></a><span data-ttu-id="09741-136">基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="09741-136">Infrastructure requirements</span></span>
<span data-ttu-id="09741-137">下表列出支援的 SBCs、網域及其他網路連線需求之基礎結構需求：</span><span class="sxs-lookup"><span data-stu-id="09741-137">The infrastructure requirements for the supported SBCs, domains, and other network connectivity requirements to deploy Direct Routing are listed in the following table:</span></span>  

|<span data-ttu-id="09741-138">**基礎結構需求**</span><span class="sxs-lookup"><span data-stu-id="09741-138">**Infrastructure requirement**</span></span>|<span data-ttu-id="09741-139">**您需要下列各項**</span><span class="sxs-lookup"><span data-stu-id="09741-139">**You need the following**</span></span>|
|:--- |:--- |
|<span data-ttu-id="09741-140">會話邊界控制器（SBC）</span><span class="sxs-lookup"><span data-stu-id="09741-140">Session Border Controller (SBC)</span></span>|<span data-ttu-id="09741-141">受支援的 SBC。</span><span class="sxs-lookup"><span data-stu-id="09741-141">A supported SBC.</span></span> <span data-ttu-id="09741-142">如需詳細資訊，請參閱[支援的 SBCs](#supported-session-border-controllers-sbcs)。</span><span class="sxs-lookup"><span data-stu-id="09741-142">For more information, see [Supported SBCs](#supported-session-border-controllers-sbcs).</span></span>|
|<span data-ttu-id="09741-143">連線至 SBC 的電話語音 trunks</span><span class="sxs-lookup"><span data-stu-id="09741-143">Telephony trunks connected to the SBC</span></span>|<span data-ttu-id="09741-144">一個或多個連線至 SBC 的電話 trunks。</span><span class="sxs-lookup"><span data-stu-id="09741-144">One or more telephony trunks connected to the SBC.</span></span> <span data-ttu-id="09741-145">在一端，SBC 透過直接路由連接到 Microsoft 手機系統。</span><span class="sxs-lookup"><span data-stu-id="09741-145">On one end, the SBC connects to the Microsoft Phone System via Direct Routing.</span></span> <span data-ttu-id="09741-146">SBC 也可以連接到協力廠商電話實體，例如 Pbx、類比電話卡等。</span><span class="sxs-lookup"><span data-stu-id="09741-146">The SBC can also connect to third-party telephony entities, such as PBXs, Analog Telephony Adapters, and so on.</span></span> <span data-ttu-id="09741-147">任何連接至 SBC 的 PSTN 連接選項都會正常運作。</span><span class="sxs-lookup"><span data-stu-id="09741-147">Any PSTN connectivity option connected to the SBC will work.</span></span> <span data-ttu-id="09741-148">（如需將 PSTN trunks 設定至 SBC，請參閱 SBC 廠商或主幹提供者）。</span><span class="sxs-lookup"><span data-stu-id="09741-148">(For configuration of the PSTN trunks to the SBC, please refer to the SBC vendors or trunk providers.)</span></span>|
|<span data-ttu-id="09741-149">Microsoft 365 或 Office 365 組織</span><span class="sxs-lookup"><span data-stu-id="09741-149">Microsoft 365 or Office 365 organization</span></span>|<span data-ttu-id="09741-150">您用來將 Microsoft 團隊使用者用來家用的 Microsoft 365 或 Office 365 組織，以及 SBC 的設定與連接。</span><span class="sxs-lookup"><span data-stu-id="09741-150">An Microsoft 365 or Office 365 organization that you use to home your Microsoft Teams users, and the configuration and connection to the SBC.</span></span>|
|<span data-ttu-id="09741-151">使用者註冊機構</span><span class="sxs-lookup"><span data-stu-id="09741-151">User registrar</span></span>|<span data-ttu-id="09741-152">使用者必須駐留在 Microsoft 365 或 Office 365 中。</span><span class="sxs-lookup"><span data-stu-id="09741-152">User must be homed in Microsoft 365 or Office 365.</span></span><br/><span data-ttu-id="09741-153">如果您的公司有內部部署商務用 Skype 或 Lync 環境，且其混合式連線至 Microsoft 365 或 Office 365，您就無法在小組中為使用者駐留內部部署的使用者啟用語音功能。</span><span class="sxs-lookup"><span data-stu-id="09741-153">If your company has an on-premises Skype for Business or Lync environment with hybrid connectivity to Microsoft 365 or Office 365, you cannot enable voice in Teams for a user homed on-premises.</span></span><br/><br/><span data-ttu-id="09741-154">若要檢查使用者的註冊機構，請使用下列商務用 Skype Online PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="09741-154">To check the registrar of a user, use the following Skype for Business Online PowerShell cmdlet:</span></span><br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/><span data-ttu-id="09741-155">Cmdlet 的輸出應該會顯示：</span><span class="sxs-lookup"><span data-stu-id="09741-155">The output of the cmdlet should show:</span></span><br/><code>HostingProvider : sipfed.online.lync.com</code>|
|<span data-ttu-id="09741-156">定義域</span><span class="sxs-lookup"><span data-stu-id="09741-156">Domains</span></span>|<span data-ttu-id="09741-157">新增至您的 Microsoft 365 或 Office 365 組織的一個或多個網域。</span><span class="sxs-lookup"><span data-stu-id="09741-157">One or more domains added to your Microsoft 365 or Office 365 organizations.</span></span><br/><br/><span data-ttu-id="09741-158">請注意，您無法使用 \* 針對您的租使用者自動建立的預設網域 onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="09741-158">Note that you cannot use the default domain, \*.onmicrosoft.com, that is automatically created for your tenant.</span></span><br/><br/><span data-ttu-id="09741-159">若要查看網域，您可以使用下列商務用 Skype Online PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="09741-159">To view the domains, you can use the following Skype for Business Online PowerShell cmdlet:</span></span><br/><code>Get-CsTenant \| fl Domains</code><br/><br/><span data-ttu-id="09741-160">如需網域與 Microsoft 365 或 Office 365 組織的詳細資訊，請參閱[網域常見問題](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)。</span><span class="sxs-lookup"><span data-stu-id="09741-160">For more information about domains and Microsoft 365 or Office 365 organizations, see [Domains FAQ](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).</span></span>|
|<span data-ttu-id="09741-161">SBC 的公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="09741-161">Public IP address for the SBC</span></span>|<span data-ttu-id="09741-162">可用於連線至 SBC 的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="09741-162">A public IP address that can be used to connect to the SBC.</span></span> <span data-ttu-id="09741-163">根據 SBC 的類型而定，SBC 可以使用 NAT。</span><span class="sxs-lookup"><span data-stu-id="09741-163">Based on the type of SBC, the SBC can use NAT.</span></span>|
|<span data-ttu-id="09741-164">SBC 的完整功能變數名稱（FQDN）</span><span class="sxs-lookup"><span data-stu-id="09741-164">Fully Qualified Domain Name (FQDN) for the SBC</span></span>|<span data-ttu-id="09741-165">SBC 的 FQDN，其中 FQDN 的網域部分是您的 Microsoft 365 或 Office 365 組織中的註冊網域之一。</span><span class="sxs-lookup"><span data-stu-id="09741-165">A FQDN for the SBC, where the domain portion of the FQDN is one of the registered domains in your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="09741-166">如需詳細資訊，請參閱[SBC 功能變數名稱](#sbc-domain-names)。</span><span class="sxs-lookup"><span data-stu-id="09741-166">For more information, see [SBC domain names](#sbc-domain-names).</span></span>|
|<span data-ttu-id="09741-167">SBC 的公用 DNS 專案</span><span class="sxs-lookup"><span data-stu-id="09741-167">Public DNS entry for the SBC</span></span> |<span data-ttu-id="09741-168">將 SBC FQDN 對應至公用 IP 位址的公用 DNS 專案。</span><span class="sxs-lookup"><span data-stu-id="09741-168">A public DNS entry mapping the SBC FQDN to the public IP Address.</span></span> |
|<span data-ttu-id="09741-169">SBC 公開信任的憑證</span><span class="sxs-lookup"><span data-stu-id="09741-169">Public trusted certificate for the SBC</span></span> |<span data-ttu-id="09741-170">SBC 的憑證，用於與直接路由的所有通訊。</span><span class="sxs-lookup"><span data-stu-id="09741-170">A certificate for the SBC to be used for all communication with Direct Routing.</span></span> <span data-ttu-id="09741-171">如需詳細資訊，請參閱[SBC 的公用信任憑證](#public-trusted-certificate-for-the-sbc)。</span><span class="sxs-lookup"><span data-stu-id="09741-171">For more information, see [Public trusted certificate for the SBC](#public-trusted-certificate-for-the-sbc).</span></span>|
|<span data-ttu-id="09741-172">直接路由的連接點</span><span class="sxs-lookup"><span data-stu-id="09741-172">Connection points for Direct Routing</span></span> |<span data-ttu-id="09741-173">直接路由的連接點是下列三個 Fqdn：</span><span class="sxs-lookup"><span data-stu-id="09741-173">The connection points for Direct Routing are the following three FQDNs:</span></span><br/><br/><span data-ttu-id="09741-174">`sip.pstnhub.microsoft.com`–必須先嘗試使用全域 FQDN。</span><span class="sxs-lookup"><span data-stu-id="09741-174">`sip.pstnhub.microsoft.com` – Global FQDN, must be tried first.</span></span><br/><span data-ttu-id="09741-175">`sip2.pstnhub.microsoft.com`–次要 FQDN，地理位置對應至第二個優先順序區域。</span><span class="sxs-lookup"><span data-stu-id="09741-175">`sip2.pstnhub.microsoft.com` – Secondary FQDN, geographically maps to the second priority region.</span></span><br/><span data-ttu-id="09741-176">`sip3.pstnhub.microsoft.com`–三元 FQDN，地理位置對應至第三個優先順序區域。</span><span class="sxs-lookup"><span data-stu-id="09741-176">`sip3.pstnhub.microsoft.com` – Tertiary FQDN, geographically maps to the third priority region.</span></span><br/><br/><span data-ttu-id="09741-177">如需設定需求的相關資訊，請參閱[SIP 信號： fqdn](#sip-signaling-fqdns)。</span><span class="sxs-lookup"><span data-stu-id="09741-177">For information on configuration requirements, see [SIP Signaling: FQDNs](#sip-signaling-fqdns).</span></span>|
|<span data-ttu-id="09741-178">用於直接路由媒體的防火牆 IP 位址和埠</span><span class="sxs-lookup"><span data-stu-id="09741-178">Firewall IP addresses and ports for Direct Routing media</span></span> |<span data-ttu-id="09741-179">SBC 會與雲端中的下列服務進行通訊：</span><span class="sxs-lookup"><span data-stu-id="09741-179">The SBC communicates to the following services in the cloud:</span></span><br/><br/><span data-ttu-id="09741-180">負責處理信號的 SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="09741-180">SIP Proxy, which handles the signaling</span></span><br/><span data-ttu-id="09741-181">處理媒體的媒體處理器-除了媒體旁路</span><span class="sxs-lookup"><span data-stu-id="09741-181">Media Processor, which handles media -except when Media Bypass is on</span></span><br/><br/><span data-ttu-id="09741-182">這兩個服務在 Microsoft 雲端中都有不同的 IP 位址，本文稍後會說明此檔。</span><span class="sxs-lookup"><span data-stu-id="09741-182">These two services have separate IP addresses in Microsoft Cloud, described later in this document.</span></span><br/><br/><span data-ttu-id="09741-183">如需詳細資訊，請參閱[url 和 IP 位址範圍](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)中的[Microsoft 團隊區段](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)。</span><span class="sxs-lookup"><span data-stu-id="09741-183">For more information, see the [Microsoft Teams section](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) in [URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> |
|<span data-ttu-id="09741-184">媒體傳輸設定檔</span><span class="sxs-lookup"><span data-stu-id="09741-184">Media Transport Profile</span></span>|<span data-ttu-id="09741-185">TCP/RTP/SAVP</span><span class="sxs-lookup"><span data-stu-id="09741-185">TCP/RTP/SAVP</span></span> <br/><span data-ttu-id="09741-186">UDP/RTP/SAVP</span><span class="sxs-lookup"><span data-stu-id="09741-186">UDP/RTP/SAVP</span></span>|
<span data-ttu-id="09741-187">Microsoft 團隊媒體的防火牆 IP 位址和埠</span><span class="sxs-lookup"><span data-stu-id="09741-187">Firewall IP addresses and ports for Microsoft Teams media</span></span> |<span data-ttu-id="09741-188">如需詳細資訊，請參閱[url 與 IP 位址範圍](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="09741-188">For more information, see [URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> |
|||

## <a name="licensing-and-other-requirements"></a><span data-ttu-id="09741-189">授權與其他需求</span><span class="sxs-lookup"><span data-stu-id="09741-189">Licensing and other requirements</span></span> 

<span data-ttu-id="09741-190">直接傳送的使用者必須具有下列在 Microsoft 365 或 Office 365 中指派的授權：</span><span class="sxs-lookup"><span data-stu-id="09741-190">Users of Direct Routing must have the following licenses assigned in Microsoft 365 or Office 365:</span></span> 

- <span data-ttu-id="09741-191">Microsoft Phone System。</span><span class="sxs-lookup"><span data-stu-id="09741-191">Microsoft Phone System.</span></span> 
- <span data-ttu-id="09741-192">Microsoft 團隊 + 商務用 Skype 方案2（如果包含在授權中）。</span><span class="sxs-lookup"><span data-stu-id="09741-192">Microsoft Teams + Skype for Business Plan 2, if included in licensing.</span></span>
- <span data-ttu-id="09741-193">Microsoft 音訊會議（如需有關授權的特定範例，請閱讀下列注意事項及以下段落）。</span><span class="sxs-lookup"><span data-stu-id="09741-193">Microsoft Audio Conferencing (please read the notes and the paragraph below for specific examples about when the license is required).</span></span>

> [!NOTE]
> <span data-ttu-id="09741-194">商務用 Skype 方案不應從隨附的任何授權合約中移除。</span><span class="sxs-lookup"><span data-stu-id="09741-194">Skype for Business Plan should not be removed from any licensing agreement where it is included.</span></span> 


> [!IMPORTANT]
>  <span data-ttu-id="09741-195">如果您想要將外部參與者新增至排程的會議，請撥打電話給他們，或提供撥入號碼，必須具備音訊會議授權。</span><span class="sxs-lookup"><span data-stu-id="09741-195">In the case that you would like to add external participants to scheduled meetings, either by dialing out to them or by providing the dial-in number, the audio conferencing license is required.</span></span>


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a><span data-ttu-id="09741-196">即席通話升級和音訊會議授權</span><span class="sxs-lookup"><span data-stu-id="09741-196">Ad hoc call escalation and Audio Conferencing license</span></span>

<span data-ttu-id="09741-197">團隊使用者可以啟動一對一團隊至 PSTN 或小組通話小組，並將 PSTN 參與者加入該小組。</span><span class="sxs-lookup"><span data-stu-id="09741-197">A Teams user can start a one-on-one Teams to PSTN or Teams to Teams call and add a PSTN participant to it.</span></span> <span data-ttu-id="09741-198">這個案例稱為「ad hoc」會議。</span><span class="sxs-lookup"><span data-stu-id="09741-198">This scenario is called an ad hoc conference.</span></span> <span data-ttu-id="09741-199">呼叫所採取的路徑，取決於升級通話的使用者是否已指派 Microsoft 音訊會議授權：</span><span class="sxs-lookup"><span data-stu-id="09741-199">The path that the call takes depends whether the user who escalates the call has a Microsoft Audio Conferencing license assigned or not:</span></span>

- <span data-ttu-id="09741-200">如果升級通話的小組使用者已指派 Microsoft 音訊會議授權，則會透過 Microsoft 音訊會議服務進行升級。</span><span class="sxs-lookup"><span data-stu-id="09741-200">If the Teams user who escalates the call has a Microsoft Audio Conferencing license assigned, the escalation happens through the Microsoft Audio Conferencing service.</span></span> <span data-ttu-id="09741-201">受邀加入現有通話的遠端 PSTN 參與者會收到來電通知，並查看指派給啟動呈報之小組使用者的 Microsoft 橋接器號碼。</span><span class="sxs-lookup"><span data-stu-id="09741-201">The remote PSTN participant who is invited to the existing call receives a notification about the incoming call and sees the number of the Microsoft bridge assigned to the Teams user who initiated the escalation.</span></span>
- <span data-ttu-id="09741-202">如果升級通話的小組使用者沒有指派 Microsoft 音訊會議授權，就會透過連線至直接路由介面的會話邊界控制器進行升級。</span><span class="sxs-lookup"><span data-stu-id="09741-202">If the Teams user who escalates the call does not have the Microsoft Audio Conferencing license assigned, the escalation happens through a Session Border Controller connected to the Direct Routing interface.</span></span> <span data-ttu-id="09741-203">受邀接聽通話的遠端 PSTN 參與者會收到來電的通知，並查看已開始升級的小組使用者人數。</span><span class="sxs-lookup"><span data-stu-id="09741-203">The remote PSTN participant who is invited to the call receives a notification about the incoming call and sees the number of the Teams user who initiated the escalation.</span></span> <span data-ttu-id="09741-204">上報所用的特定 SBC 是由使用者的路由原則所定義。</span><span class="sxs-lookup"><span data-stu-id="09741-204">The specific SBC used for the escalation is defined by Routing Policy of the user.</span></span> 


<span data-ttu-id="09741-205">此外，您必須確認下列事項：</span><span class="sxs-lookup"><span data-stu-id="09741-205">In addition, you must ensure the following:</span></span>
 
- <span data-ttu-id="09741-206">CsOnlineVoiceRoutingPolicy 已指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="09741-206">CsOnlineVoiceRoutingPolicy is assigned to the user.</span></span> 
- <span data-ttu-id="09741-207">在 Microsoft 團隊的租使用者層級啟用 [允許私人通話]。</span><span class="sxs-lookup"><span data-stu-id="09741-207">Allow Private Calling is enabled at the tenant level for Microsoft Teams.</span></span> 

<span data-ttu-id="09741-208">直接路由還支援 Microsoft 通話方案授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="09741-208">Direct Routing also supports users who are licensed for Microsoft Calling Plan.</span></span> <span data-ttu-id="09741-209">含有通話方案的 Microsoft Phone 系統可以使用直接路由介面傳送一些通話。</span><span class="sxs-lookup"><span data-stu-id="09741-209">Microsoft Phone System with Calling Plan can route some calls using the Direct Routing interface.</span></span> <span data-ttu-id="09741-210">不過，使用者的電話號碼必須是線上購買或移植至 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="09741-210">However, the users' phone numbers must be either acquired online or ported to Microsoft.</span></span>  

<span data-ttu-id="09741-211">針對相同的使用者混合通話方案和直接路由連線是選擇性的，但可能很有用（例如，當使用者指派 Microsoft 通話方案，但想要使用 SBC 路由進行一些呼叫）。</span><span class="sxs-lookup"><span data-stu-id="09741-211">Mixing Calling Plan and Direct Routing connectivity for the same user is optional, but could be useful (for example, when the user is assigned a Microsoft Calling Plan but wants to route some calls using the SBC).</span></span> <span data-ttu-id="09741-212">其中一個最常見的案例是呼叫協力廠商的 Pbx。</span><span class="sxs-lookup"><span data-stu-id="09741-212">One of the most common scenarios is calls to third-party PBXs.</span></span>  <span data-ttu-id="09741-213">透過協力廠商 Pbx，所有通話（除了連接至該 Pbx 的電話除外）都是使用 Microsoft 通話方案進行路由，但連接至協力廠商 Pbx 的電話撥打電話給 SBC，因此，不會在商業網路中，也不是 PSTN。</span><span class="sxs-lookup"><span data-stu-id="09741-213">With third-party PBXs, all calls, except calls to the phones connected to that PBXs, are routed using Microsoft Calling Plan, but calls to the phones connected to third-party PBXs go to the SBC, and therefore stay within the enterprise network and not the PSTN.</span></span> 

<span data-ttu-id="09741-214">如需手機系統授權的詳細資訊，請參閱[充分利用 Office](https://products.office.com/compare-all-microsoft-office-products?tab=2)和[方案選項](https://technet.microsoft.com/library/office-365-plan-options.aspx)。</span><span class="sxs-lookup"><span data-stu-id="09741-214">For more information about Phone System licensing, see [Get the most from Office](https://products.office.com/compare-all-microsoft-office-products?tab=2) and [Plan Options](https://technet.microsoft.com/library/office-365-plan-options.aspx).</span></span> 

<span data-ttu-id="09741-215">如需手機系統授權的詳細資訊，請參閱[Microsoft 團隊附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="09741-215">For more information about Phone System licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span> 

## <a name="supported-end-points"></a><span data-ttu-id="09741-216">支援的端點</span><span class="sxs-lookup"><span data-stu-id="09741-216">Supported end points</span></span> 

<span data-ttu-id="09741-217">您可以用做為終點：</span><span class="sxs-lookup"><span data-stu-id="09741-217">You can use as an end point:</span></span>

- <span data-ttu-id="09741-218">任何團隊用戶端。</span><span class="sxs-lookup"><span data-stu-id="09741-218">Any Teams client.</span></span> 
- <span data-ttu-id="09741-219">常見的區域電話。</span><span class="sxs-lookup"><span data-stu-id="09741-219">Common Area Phones.</span></span> <span data-ttu-id="09741-220">請參閱[設定 Microsoft 團隊的通用區域電話授權](https://docs.microsoft.com/microsoftteams/set-up-common-area-phones)。</span><span class="sxs-lookup"><span data-stu-id="09741-220">See [Set up the Common Area Phone license for Microsoft Teams](https://docs.microsoft.com/microsoftteams/set-up-common-area-phones).</span></span> <span data-ttu-id="09741-221">注意在使用直接傳送來設定一般的區域手機時，不需要通話方案授權。</span><span class="sxs-lookup"><span data-stu-id="09741-221">Note you do not need a Calling Plan license when setting up a Common Area Phone with Direct Routing.</span></span>
- <span data-ttu-id="09741-222">商務用 Skype 3PIP 電話。</span><span class="sxs-lookup"><span data-stu-id="09741-222">Skype for Business 3PIP phones.</span></span> <span data-ttu-id="09741-223">請參閱[Microsoft 團隊的商務用 Skype 電話（3PIP）支援](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)</span><span class="sxs-lookup"><span data-stu-id="09741-223">See [Skype for Business phones (3PIP) support with Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)</span></span>


## <a name="sbc-domain-names"></a><span data-ttu-id="09741-224">SBC 網功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="09741-224">SBC domain names</span></span>

<span data-ttu-id="09741-225">SBC 網功能變數名稱稱必須來自于租使用者網域中註冊的其中一個名稱。</span><span class="sxs-lookup"><span data-stu-id="09741-225">The SBC domain name must be from one of the names registered in Domains of the tenant.</span></span> <span data-ttu-id="09741-226">您無法 \* 針對 SBC 的 FQDN 名稱使用 onmicrosoft.com 租使用者。</span><span class="sxs-lookup"><span data-stu-id="09741-226">You cannot use the \*.onmicrosoft.com tenant for the FQDN name of the SBC.</span></span>

<span data-ttu-id="09741-227">下表顯示針對租使用者註冊的 DNS 名稱範例，無論該名稱是否可做為 SBC 的 FQDN，以及有效 FQDN 名稱的範例：</span><span class="sxs-lookup"><span data-stu-id="09741-227">The following table shows examples of DNS names registered for the tenant, whether the name can be used as an FQDN for the SBC, and examples of valid FQDN names:</span></span>

|<span data-ttu-id="09741-228">**DNS 名稱**</span><span class="sxs-lookup"><span data-stu-id="09741-228">**DNS name**</span></span>|<span data-ttu-id="09741-229">**可用於 SBC FQDN**</span><span class="sxs-lookup"><span data-stu-id="09741-229">**Can be used for SBC FQDN**</span></span>|<span data-ttu-id="09741-230">**FQDN 名稱範例**</span><span class="sxs-lookup"><span data-stu-id="09741-230">**Examples of FQDN names**</span></span>|
|:--- |:--- |:--- |
<span data-ttu-id="09741-231">contoso.com</span><span class="sxs-lookup"><span data-stu-id="09741-231">contoso.com</span></span>|<span data-ttu-id="09741-232">是</span><span class="sxs-lookup"><span data-stu-id="09741-232">Yes</span></span>|<span data-ttu-id="09741-233">**有效的名稱：**</span><span class="sxs-lookup"><span data-stu-id="09741-233">**Valid names:**</span></span><br/><span data-ttu-id="09741-234">sbc1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="09741-234">sbc1.contoso.com</span></span><br/><span data-ttu-id="09741-235">ssbcs15.contoso.com</span><span class="sxs-lookup"><span data-stu-id="09741-235">ssbcs15.contoso.com</span></span><br/><span data-ttu-id="09741-236">europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="09741-236">europe.contoso.com</span></span>|
|<span data-ttu-id="09741-237">contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="09741-237">contoso.onmicrosoft.com</span></span>|<span data-ttu-id="09741-238">否</span><span class="sxs-lookup"><span data-stu-id="09741-238">No</span></span>|<span data-ttu-id="09741-239">SBC 名稱不支援使用 \*. onmicrosoft.com 網域</span><span class="sxs-lookup"><span data-stu-id="09741-239">Using \*.onmicrosoft.com domains is not supported for SBC names</span></span>

<span data-ttu-id="09741-240">假設您要使用新的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="09741-240">Assume you want to use a new domain name.</span></span> <span data-ttu-id="09741-241">例如，您的租使用者有 contoso.com 做為在您的租使用者中註冊的功能變數名稱，而您想要使用 sbc1.sip.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="09741-241">For example, your tenant has contoso.com as a domain name registered in your tenant, and you want to use sbc1.sip.contoso.com.</span></span> <span data-ttu-id="09741-242">您必須先在租使用者中的網域中註冊功能變數名稱 sip.contoso.com，才能將其與 name sbc1.sip.contoso.com 進行配對。</span><span class="sxs-lookup"><span data-stu-id="09741-242">Before you can pair an SBC with the name sbc1.sip.contoso.com, you must register the domain name sip.contoso.com in Domains in your tenant.</span></span> <span data-ttu-id="09741-243">如果您在註冊功能變數名稱前嘗試搭配 sbc1.sip.contoso.com 進行配對，您會收到下列錯誤：「無法使用「sbc1.sip.contoso.com」網域，因為它未針對此租使用者進行設定。」</span><span class="sxs-lookup"><span data-stu-id="09741-243">If you try pairing an SBC with sbc1.sip.contoso.com before registering the domain name, you will get the following error: "Cannot use the "sbc1.sip.contoso.com" domain as it was not configured for this tenant."</span></span>
<span data-ttu-id="09741-244">在您新增功能變數名稱之後，您也需要使用 UPN user@sip.contoso.com 建立使用者並指派小組授權。</span><span class="sxs-lookup"><span data-stu-id="09741-244">After you add the domain name, you also need to create a user with UPN user@sip.contoso.com and assign a Teams license.</span></span> <span data-ttu-id="09741-245">在將功能變數名稱新增至租使用者的網域之後，最多可能需要24小時才能完全提供該功能變數名稱，並會建立一個具有新名稱的使用者，並指派授權給使用者。</span><span class="sxs-lookup"><span data-stu-id="09741-245">It might take up to 24 hours to fully provision the domain name after it is added to Domains of your tenant, a user with a new name is created, and a license is assigned to the user.</span></span> 

<span data-ttu-id="09741-246">公司可能會在一個租使用者中有數個 SIP 位址空間。</span><span class="sxs-lookup"><span data-stu-id="09741-246">It is possible that a company might have several SIP address spaces in one tenant.</span></span> <span data-ttu-id="09741-247">例如，公司可能會將 contoso.com 做為 SIP 位址空間，並 fabrikam.com 為第二個 SIP 位址空間。</span><span class="sxs-lookup"><span data-stu-id="09741-247">For example, a company might have contoso.com as a SIP address space and fabrikam.com as the second SIP address space.</span></span> <span data-ttu-id="09741-248">有些使用者有位址 user@contoso.com，而有些使用者則是位址 user@fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="09741-248">Some users have address user@contoso.com and some users have address user@fabrikam.com.</span></span> 

<span data-ttu-id="09741-249">SBC 只需要一個 FQDN，而且可以從成對的租使用者中的任何位址空間來服務使用者。</span><span class="sxs-lookup"><span data-stu-id="09741-249">The SBC only needs one FQDN and can service users from any address space in the paired tenant.</span></span> <span data-ttu-id="09741-250">例如，擁有 name sbc1.contoso.com 的 SBC 可以接收並傳送具有位址 user@contoso.com 和 user@fabrikam.com 之使用者的 PSTN 流量，只要這些 SIP 位址空間已在相同的租使用者中註冊。</span><span class="sxs-lookup"><span data-stu-id="09741-250">For example,  an SBC with the name sbc1.contoso.com can receive and send the PSTN traffic for users with addresses user@contoso.com and user@fabrikam.com as long as these SIP address spaces are registered in the same tenant.</span></span>  

## <a name="public-trusted-certificate-for-the-sbc"></a><span data-ttu-id="09741-251">SBC 公開信任的憑證</span><span class="sxs-lookup"><span data-stu-id="09741-251">Public trusted certificate for the SBC</span></span>

<span data-ttu-id="09741-252">Microsoft 建議您透過產生認證簽署要求（CSR）來要求 SBC 的憑證。</span><span class="sxs-lookup"><span data-stu-id="09741-252">Microsoft recommends that you request the certificate for the SBC by generating a certification signing request (CSR).</span></span> <span data-ttu-id="09741-253">如需針對 SBC 產生 CSR 的特定指示，請參閱由您的 SBC 轉銷商提供的互連指示或檔。</span><span class="sxs-lookup"><span data-stu-id="09741-253">For specific instructions on generating a CSR for an SBC, refer to the interconnection instructions or documentation provided by your SBC vendors.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="09741-254">大多數憑證授權單位（Ca）需要私密金鑰大小至少為2048。</span><span class="sxs-lookup"><span data-stu-id="09741-254">Most Certificate Authorities (CAs) require the private key size to be at least 2048.</span></span> <span data-ttu-id="09741-255">產生 CSR 時，請記住這一點。</span><span class="sxs-lookup"><span data-stu-id="09741-255">Keep this in mind when generating the CSR.</span></span>

<span data-ttu-id="09741-256">憑證在 subject 欄位中必須將 SBC FQDN 做為公用名（CN）。</span><span class="sxs-lookup"><span data-stu-id="09741-256">The certificate needs to have the SBC FQDN as the common name (CN) in the subject field.</span></span>

<span data-ttu-id="09741-257">或者，直接路由支援 SAN 中的萬用字元，而萬用字元必須符合[TLS 上標準 RFC HTTP](https://tools.ietf.org/html/rfc2818#section-3.1)的要求。</span><span class="sxs-lookup"><span data-stu-id="09741-257">Alternatively, Direct Routing  supports a wildcard in SAN, and the wildcard needs to conform to standard [RFC HTTP Over TLS](https://tools.ietf.org/html/rfc2818#section-3.1).</span></span> <span data-ttu-id="09741-258">\*在 SAN 中將會使用 contoso.com，這會與 SBC FQDN sbc.contoso.com 相符，但不會與 sbc.test.contoso.com 相符。</span><span class="sxs-lookup"><span data-stu-id="09741-258">An example would be using \*.contoso.com in the SAN, which would match the SBC FQDN sbc.contoso.com, but wouldn't match with sbc.test.contoso.com.</span></span>

<span data-ttu-id="09741-259">憑證需要由下列其中一個根憑證授權單位產生：</span><span class="sxs-lookup"><span data-stu-id="09741-259">The certificate needs to be generated by one of the following root certificate authorities:</span></span>

- <span data-ttu-id="09741-260">AffirmTrust</span><span class="sxs-lookup"><span data-stu-id="09741-260">AffirmTrust</span></span>
- <span data-ttu-id="09741-261">AddTrust 外部 CA 根目錄</span><span class="sxs-lookup"><span data-stu-id="09741-261">AddTrust External CA Root</span></span>
- <span data-ttu-id="09741-262">巴爾的摩 CyberTrust 根</span><span class="sxs-lookup"><span data-stu-id="09741-262">Baltimore CyberTrust Root</span></span>
- <span data-ttu-id="09741-263">Buypass</span><span class="sxs-lookup"><span data-stu-id="09741-263">Buypass</span></span>
- <span data-ttu-id="09741-264">Cybertrust</span><span class="sxs-lookup"><span data-stu-id="09741-264">Cybertrust</span></span>
- <span data-ttu-id="09741-265">Class 3 公用主要憑證授權單位</span><span class="sxs-lookup"><span data-stu-id="09741-265">Class 3 Public Primary Certification Authority</span></span>
- <span data-ttu-id="09741-266">Comodo 安全的根 CA</span><span class="sxs-lookup"><span data-stu-id="09741-266">Comodo Secure Root CA</span></span>
- <span data-ttu-id="09741-267">德國 Telekom</span><span class="sxs-lookup"><span data-stu-id="09741-267">Deutsche Telekom</span></span> 
- <span data-ttu-id="09741-268">DigiCert 全域根 CA</span><span class="sxs-lookup"><span data-stu-id="09741-268">DigiCert Global Root CA</span></span>
- <span data-ttu-id="09741-269">DigiCert 高確定性 EV 根 CA</span><span class="sxs-lookup"><span data-stu-id="09741-269">DigiCert High Assurance EV Root CA</span></span>
- <span data-ttu-id="09741-270">Entrust</span><span class="sxs-lookup"><span data-stu-id="09741-270">Entrust</span></span>
- <span data-ttu-id="09741-271">GlobalSign</span><span class="sxs-lookup"><span data-stu-id="09741-271">GlobalSign</span></span>
- <span data-ttu-id="09741-272">移至 Go daddy</span><span class="sxs-lookup"><span data-stu-id="09741-272">Go Daddy</span></span>
- <span data-ttu-id="09741-273">GeoTrust</span><span class="sxs-lookup"><span data-stu-id="09741-273">GeoTrust</span></span>
- <span data-ttu-id="09741-274">Verisign，Inc。</span><span class="sxs-lookup"><span data-stu-id="09741-274">Verisign, Inc.</span></span> 
- <span data-ttu-id="09741-275">SSL.com</span><span class="sxs-lookup"><span data-stu-id="09741-275">SSL.com</span></span>
- <span data-ttu-id="09741-276">Starfield</span><span class="sxs-lookup"><span data-stu-id="09741-276">Starfield</span></span>
- <span data-ttu-id="09741-277">Microsoft 適用的 Symantec 企業行動裝置根</span><span class="sxs-lookup"><span data-stu-id="09741-277">Symantec Enterprise Mobile Root for Microsoft</span></span> 
- <span data-ttu-id="09741-278">SwissSign</span><span class="sxs-lookup"><span data-stu-id="09741-278">SwissSign</span></span>
- <span data-ttu-id="09741-279">Thawte 日戳 CA</span><span class="sxs-lookup"><span data-stu-id="09741-279">Thawte Timestamping CA</span></span>
- <span data-ttu-id="09741-280">Trustwave</span><span class="sxs-lookup"><span data-stu-id="09741-280">Trustwave</span></span>
- <span data-ttu-id="09741-281">TeliaSonera</span><span class="sxs-lookup"><span data-stu-id="09741-281">TeliaSonera</span></span> 
- <span data-ttu-id="09741-282">T 系統國際 GmbH （德國 Telekom）</span><span class="sxs-lookup"><span data-stu-id="09741-282">T-Systems International GmbH (Deutsche Telekom)</span></span>
- <span data-ttu-id="09741-283">QuoVadis</span><span class="sxs-lookup"><span data-stu-id="09741-283">QuoVadis</span></span>

<span data-ttu-id="09741-284">Microsoft 正在努力根據客戶要求新增其他認證機構。</span><span class="sxs-lookup"><span data-stu-id="09741-284">Microsoft is working on adding additional certification authorities based on customer requests.</span></span> 

## <a name="sip-signaling-fqdns"></a><span data-ttu-id="09741-285">SIP 信號： Fqdn</span><span class="sxs-lookup"><span data-stu-id="09741-285">SIP Signaling: FQDNs</span></span> 

<span data-ttu-id="09741-286">在下列環境中提供直接路由：</span><span class="sxs-lookup"><span data-stu-id="09741-286">Direct Routing is offered in the following environments:</span></span>
- <span data-ttu-id="09741-287">Microsoft 365 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="09741-287">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="09741-288">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="09741-288">Office 365 GCC</span></span>
- <span data-ttu-id="09741-289">Office 365 GCC 高</span><span class="sxs-lookup"><span data-stu-id="09741-289">Office 365 GCC High</span></span>
- <span data-ttu-id="09741-290">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="09741-290">Office 365 DoD</span></span>

<span data-ttu-id="09741-291">深入瞭解[Office 365 和美國政府環境](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)（例如 GCC、gcc 高和 DoD）。</span><span class="sxs-lookup"><span data-stu-id="09741-291">Learn more about [Office 365 and US Government environments](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="09741-292">Microsoft 365、Office 365 及 Office 365 GCC 環境</span><span class="sxs-lookup"><span data-stu-id="09741-292">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="09741-293">直接路由的連接點是下列三個 Fqdn：</span><span class="sxs-lookup"><span data-stu-id="09741-293">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="09741-294">**sip.pstnhub.microsoft.com** –全域 FQDN-必須先嘗試。</span><span class="sxs-lookup"><span data-stu-id="09741-294">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="09741-295">當 SBC 傳送要求來解析此名稱時，Microsoft Azure DNS 伺服器會傳回指向指派給 SBC 之主要 Azure 資料中心的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="09741-295">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="09741-296">作業是以資料中心的效能指標，以及與 SBC 有關的地理位置為基礎。</span><span class="sxs-lookup"><span data-stu-id="09741-296">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="09741-297">傳回的 IP 位址會對應到主要 FQDN。</span><span class="sxs-lookup"><span data-stu-id="09741-297">The IP address returned corresponds to the primary FQDN.</span></span>
- <span data-ttu-id="09741-298">**sip2.pstnhub.microsoft.com** –次要 FQDN-地理位置對應至第二個優先順序區域。</span><span class="sxs-lookup"><span data-stu-id="09741-298">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>
- <span data-ttu-id="09741-299">**sip3.pstnhub.microsoft.com** –三元 FQDN-[地理位置] 對應至第三個優先順序區域。</span><span class="sxs-lookup"><span data-stu-id="09741-299">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="09741-300">若要執行下列三個 Fqdn，必須進行下列動作：</span><span class="sxs-lookup"><span data-stu-id="09741-300">Placing these three FQDNs in order is required to:</span></span>

- <span data-ttu-id="09741-301">提供最佳的使用體驗（在所指派的 SBC 資料中心較少且最接近的情況下，由查詢第一個 FQDN）。</span><span class="sxs-lookup"><span data-stu-id="09741-301">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>
- <span data-ttu-id="09741-302">提供從 SBC 連線到發生暫時問題的資料中心時的容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="09741-302">Provide failover when connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="09741-303">如需詳細資訊，請參閱下方的[容錯移轉機制](#failover-mechanism-for-sip-signaling)。</span><span class="sxs-lookup"><span data-stu-id="09741-303">For more information, see [Failover mechanism](#failover-mechanism-for-sip-signaling) below.</span></span>  

<span data-ttu-id="09741-304">Fqdn （sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com 和 sip3.pstnhub.microsoft.com）會解析成下列其中一個 IP 位址：</span><span class="sxs-lookup"><span data-stu-id="09741-304">The FQDNs – sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com and sip3.pstnhub.microsoft.com – will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="09741-305">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="09741-305">52.114.148.0</span></span>
- <span data-ttu-id="09741-306">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="09741-306">52.114.132.46</span></span> 
- <span data-ttu-id="09741-307">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="09741-307">52.114.75.24</span></span> 
- <span data-ttu-id="09741-308">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="09741-308">52.114.76.76</span></span> 
- <span data-ttu-id="09741-309">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="09741-309">52.114.7.24</span></span> 
- <span data-ttu-id="09741-310">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="09741-310">52.114.14.70</span></span>

<span data-ttu-id="09741-311">您必須在防火牆中開啟所有這些 IP 位址的埠，以允許傳入及傳出流量進出位址來傳送信號。</span><span class="sxs-lookup"><span data-stu-id="09741-311">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="09741-312">如果您的防火牆支援 DNS 名稱，FQDN sip-all.pstnhub.microsoft.com 會解析為所有這些 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="09741-312">If your firewall supports DNS names, the FQDN sip-all.pstnhub.microsoft.com resolves to all these IP addresses.</span></span> 


### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="09741-313">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="09741-313">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="09741-314">直接路由的連接點是下列 FQDN：</span><span class="sxs-lookup"><span data-stu-id="09741-314">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="09741-315">**sip.pstnhub.dod.teams.microsoft.us** –全域 FQDN。</span><span class="sxs-lookup"><span data-stu-id="09741-315">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="09741-316">因為 Office 365 DoD 環境僅存在於美國資料中心，所以沒有次要和第三個 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="09741-316">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="09741-317">FQDN sip.pstnhub.dod.teams.microsoft.us 將解析成下列其中一個 IP 位址：</span><span class="sxs-lookup"><span data-stu-id="09741-317">The FQDN sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="09741-318">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="09741-318">52.127.64.33</span></span>
- <span data-ttu-id="09741-319">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="09741-319">52.127.68.34</span></span>

<span data-ttu-id="09741-320">您必須在防火牆中開啟所有這些 IP 位址的埠，以允許傳入及傳出流量進出位址來傳送信號。</span><span class="sxs-lookup"><span data-stu-id="09741-320">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="09741-321">Office 365 GCC 高環境</span><span class="sxs-lookup"><span data-stu-id="09741-321">Office 365 GCC High environment</span></span>

<span data-ttu-id="09741-322">直接路由的連接點是下列 FQDN：</span><span class="sxs-lookup"><span data-stu-id="09741-322">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="09741-323">**sip.pstnhub.gov.teams.microsoft.us** –全域 FQDN。</span><span class="sxs-lookup"><span data-stu-id="09741-323">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="09741-324">由於 GCC 的高環境僅存在於美國資料中心，因此沒有副及三元 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="09741-324">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="09741-325">FQDN sip.pstnhub.gov.teams.microsoft.us 將解析成下列其中一個 IP 位址：</span><span class="sxs-lookup"><span data-stu-id="09741-325">The FQDN sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="09741-326">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="09741-326">52.127.88.59</span></span>
- <span data-ttu-id="09741-327">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="09741-327">52.127.92.64</span></span>

<span data-ttu-id="09741-328">您必須在防火牆中開啟所有這些 IP 位址的埠，以允許傳入及傳出流量進出位址來傳送信號。</span><span class="sxs-lookup"><span data-stu-id="09741-328">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>

## <a name="sip-signaling-ports"></a><span data-ttu-id="09741-329">SIP 信號：埠</span><span class="sxs-lookup"><span data-stu-id="09741-329">SIP Signaling: Ports</span></span>

<span data-ttu-id="09741-330">您必須在提供直接路由的 Microsoft 365 或 Office 365 環境中使用下列埠：</span><span class="sxs-lookup"><span data-stu-id="09741-330">You must use the following ports for Microsoft 365 or Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="09741-331">Microsoft 365 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="09741-331">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="09741-332">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="09741-332">Office 365 GCC</span></span>
- <span data-ttu-id="09741-333">Office 365 GCC 高</span><span class="sxs-lookup"><span data-stu-id="09741-333">Office 365 GCC High</span></span>
- <span data-ttu-id="09741-334">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="09741-334">Office 365 DoD</span></span>

|<span data-ttu-id="09741-335">**頻寬**</span><span class="sxs-lookup"><span data-stu-id="09741-335">**Traffic**</span></span>|<span data-ttu-id="09741-336">**從**</span><span class="sxs-lookup"><span data-stu-id="09741-336">**From**</span></span>|<span data-ttu-id="09741-337">**自**</span><span class="sxs-lookup"><span data-stu-id="09741-337">**To**</span></span>|<span data-ttu-id="09741-338">**來源埠**</span><span class="sxs-lookup"><span data-stu-id="09741-338">**Source port**</span></span>|<span data-ttu-id="09741-339">**目的地埠**</span><span class="sxs-lookup"><span data-stu-id="09741-339">**Destination port**</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="09741-340">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="09741-340">SIP/TLS</span></span>|<span data-ttu-id="09741-341">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="09741-341">SIP Proxy</span></span>|<span data-ttu-id="09741-342">SBC</span><span class="sxs-lookup"><span data-stu-id="09741-342">SBC</span></span>|<span data-ttu-id="09741-343">1024–65535</span><span class="sxs-lookup"><span data-stu-id="09741-343">1024 – 65535</span></span>|<span data-ttu-id="09741-344">在 SBC 上定義（必須使用 Office 365 GCC 高/DoD 專用埠5061）</span><span class="sxs-lookup"><span data-stu-id="09741-344">Defined on the SBC (For Office 365 GCC High/DoD only port 5061 must be used)</span></span>|
<span data-ttu-id="09741-345">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="09741-345">SIP/TLS</span></span>|<span data-ttu-id="09741-346">SBC</span><span class="sxs-lookup"><span data-stu-id="09741-346">SBC</span></span>|<span data-ttu-id="09741-347">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="09741-347">SIP Proxy</span></span>|<span data-ttu-id="09741-348">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="09741-348">Defined on the SBC</span></span>|<span data-ttu-id="09741-349">5061</span><span class="sxs-lookup"><span data-stu-id="09741-349">5061</span></span>|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a><span data-ttu-id="09741-350">SIP 信號的容錯移轉機制</span><span class="sxs-lookup"><span data-stu-id="09741-350">Failover mechanism for SIP Signaling</span></span>

<span data-ttu-id="09741-351">SBC 會進行 DNS 查詢來解析 sip.pstnhub.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="09741-351">The SBC makes a DNS query to resolve sip.pstnhub.microsoft.com.</span></span> <span data-ttu-id="09741-352">根據 SBC 位置和資料中心效能指標，選取主要資料中心。</span><span class="sxs-lookup"><span data-stu-id="09741-352">Based on the SBC location and the datacenter performance metrics, the primary datacenter is selected.</span></span> <span data-ttu-id="09741-353">如果主要資料中心遇到問題，SBC 將會嘗試可解析為第二個已指定資料中心的 sip2.pstnhub.microsoft.com，而且在兩個區域中的資料中心無法使用的極少數情況下，SBC 會重試最後一個 FQDN （sip3.pstnhub.microsoft.com），提供第三個資料中心 IP。</span><span class="sxs-lookup"><span data-stu-id="09741-353">If the primary datacenter experiences an issue, the SBC will try the sip2.pstnhub.microsoft.com, which resolves to the second assigned datacenter, and, in the rare case that datacenters in two regions are not available, the SBC retries the last FQDN (sip3.pstnhub.microsoft.com), which provides the tertiary datacenter IP.</span></span>

<span data-ttu-id="09741-354">下表摘要列出主要、次要及三元資料中心之間的關聯：</span><span class="sxs-lookup"><span data-stu-id="09741-354">The table below summarizes the relationships between primary, secondary, and tertiary datacenters:</span></span>

|<span data-ttu-id="09741-355">**如果主要資料中心是**</span><span class="sxs-lookup"><span data-stu-id="09741-355">**If the primary datacenter is**</span></span>|<span data-ttu-id="09741-356">**中東**</span><span class="sxs-lookup"><span data-stu-id="09741-356">**EMEA**</span></span>|<span data-ttu-id="09741-357">**NOAM**</span><span class="sxs-lookup"><span data-stu-id="09741-357">**NOAM**</span></span>|<span data-ttu-id="09741-358">**太**</span><span class="sxs-lookup"><span data-stu-id="09741-358">**ASIA**</span></span>|
|:--- |:--- |:--- |:--- |
|<span data-ttu-id="09741-359">副資料中心（sip2.pstnhub.microsoft.com）</span><span class="sxs-lookup"><span data-stu-id="09741-359">The secondary datacenter (sip2.pstnhub.microsoft.com)</span></span>|<span data-ttu-id="09741-360">一下</span><span class="sxs-lookup"><span data-stu-id="09741-360">US</span></span>|<span data-ttu-id="09741-361">歐洲</span><span class="sxs-lookup"><span data-stu-id="09741-361">EU</span></span>|<span data-ttu-id="09741-362">一下</span><span class="sxs-lookup"><span data-stu-id="09741-362">US</span></span>|
|<span data-ttu-id="09741-363">第三個資料中心（sip3.pstnhub.microsoft.com）</span><span class="sxs-lookup"><span data-stu-id="09741-363">The tertiary datacenter (sip3.pstnhub.microsoft.com)</span></span>|<span data-ttu-id="09741-364">太</span><span class="sxs-lookup"><span data-stu-id="09741-364">ASIA</span></span>|<span data-ttu-id="09741-365">太</span><span class="sxs-lookup"><span data-stu-id="09741-365">ASIA</span></span>|<span data-ttu-id="09741-366">歐洲</span><span class="sxs-lookup"><span data-stu-id="09741-366">EU</span></span>|
|||||

## <a name="media-traffic-port-ranges"></a><span data-ttu-id="09741-367">媒體流量：埠範圍</span><span class="sxs-lookup"><span data-stu-id="09741-367">Media traffic: Port ranges</span></span>
<span data-ttu-id="09741-368">請注意，如果您想要在不使用媒體的情況下部署直接路由，請套用下列需求。</span><span class="sxs-lookup"><span data-stu-id="09741-368">Note that the requirements below apply if you want to deploy Direct Routing without Media Bypass.</span></span> <span data-ttu-id="09741-369">如需媒體旁路的防火牆需求，請參閱[使用直接路由來規劃媒體旁路](https://docs.microsoft.com/microsoftteams/direct-routing-plan-media-bypass)。</span><span class="sxs-lookup"><span data-stu-id="09741-369">For firewall requirements for Media Bypass, please refer to [Plan for media bypass with Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-plan-media-bypass).</span></span>



<span data-ttu-id="09741-370">媒體流量會流過 Microsoft 雲端中的個別服務。</span><span class="sxs-lookup"><span data-stu-id="09741-370">The media traffic flows to and from a separate service in the Microsoft Cloud.</span></span> <span data-ttu-id="09741-371">媒體流量的 IP 位址範圍如下所示。</span><span class="sxs-lookup"><span data-stu-id="09741-371">The IP address ranges for Media traffic are as follows.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="09741-372">Microsoft 365、Office 365 及 Office 365 GCC 環境</span><span class="sxs-lookup"><span data-stu-id="09741-372">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="09741-373">52.112.0.0/14 （從52.112.0.1 到52.115.255.254 的 IP 位址）。</span><span class="sxs-lookup"><span data-stu-id="09741-373">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254).</span></span>
- <span data-ttu-id="09741-374">52.120.0.0/14 （從52.120.0.1 到52.123.255.254 的 IP 位址）。</span><span class="sxs-lookup"><span data-stu-id="09741-374">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254).</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="09741-375">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="09741-375">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="09741-376">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="09741-376">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="09741-377">Office 365 GCC 高環境</span><span class="sxs-lookup"><span data-stu-id="09741-377">Office 365 GCC High environment</span></span>

- <span data-ttu-id="09741-378">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="09741-378">52.127.88.0/21</span></span>

### <a name="port-range-applicable-to-all-environments"></a><span data-ttu-id="09741-379">埠範圍（適用于所有環境）</span><span class="sxs-lookup"><span data-stu-id="09741-379">Port range (applicable to all environments)</span></span>
<span data-ttu-id="09741-380">媒體處理器的埠範圍如下表所示：</span><span class="sxs-lookup"><span data-stu-id="09741-380">The port range of the Media Processors is shown in the following table:</span></span> 

|<span data-ttu-id="09741-381">**頻寬**</span><span class="sxs-lookup"><span data-stu-id="09741-381">**Traffic**</span></span>|<span data-ttu-id="09741-382">**從**</span><span class="sxs-lookup"><span data-stu-id="09741-382">**From**</span></span>|<span data-ttu-id="09741-383">**自**</span><span class="sxs-lookup"><span data-stu-id="09741-383">**To**</span></span>|<span data-ttu-id="09741-384">**來源埠**</span><span class="sxs-lookup"><span data-stu-id="09741-384">**Source port**</span></span>|<span data-ttu-id="09741-385">**目的地埠**</span><span class="sxs-lookup"><span data-stu-id="09741-385">**Destination port**</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="09741-386">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="09741-386">UDP/SRTP</span></span>|<span data-ttu-id="09741-387">媒體處理器</span><span class="sxs-lookup"><span data-stu-id="09741-387">Media Processor</span></span>|<span data-ttu-id="09741-388">SBC</span><span class="sxs-lookup"><span data-stu-id="09741-388">SBC</span></span>|<span data-ttu-id="09741-389">3478-3481 與49152–53247</span><span class="sxs-lookup"><span data-stu-id="09741-389">3478-3481 and 49152 – 53247</span></span>|<span data-ttu-id="09741-390">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="09741-390">Defined on the SBC</span></span>|
|<span data-ttu-id="09741-391">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="09741-391">UDP/SRTP</span></span>|<span data-ttu-id="09741-392">SBC</span><span class="sxs-lookup"><span data-stu-id="09741-392">SBC</span></span>|<span data-ttu-id="09741-393">媒體處理器</span><span class="sxs-lookup"><span data-stu-id="09741-393">Media Processor</span></span>|<span data-ttu-id="09741-394">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="09741-394">Defined on the SBC</span></span>|<span data-ttu-id="09741-395">3478-3481 與49152–53247</span><span class="sxs-lookup"><span data-stu-id="09741-395">3478-3481 and 49152 – 53247</span></span>|

  > [!NOTE]
  > <span data-ttu-id="09741-396">Microsoft 建議在 SBC 上每個併發呼叫至少有兩個埠。</span><span class="sxs-lookup"><span data-stu-id="09741-396">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span>


## <a name="media-traffic-media-processors-geography"></a><span data-ttu-id="09741-397">媒體流量：媒體處理器地理位置</span><span class="sxs-lookup"><span data-stu-id="09741-397">Media traffic: Media processors geography</span></span>

<span data-ttu-id="09741-398">媒體流量透過稱為媒體處理器的元件來流動。</span><span class="sxs-lookup"><span data-stu-id="09741-398">The media traffic flows via components called media processors.</span></span> <span data-ttu-id="09741-399">媒體處理器與 SIP proxy 放在同一個資料中心。</span><span class="sxs-lookup"><span data-stu-id="09741-399">Media processors are placed in the same datacenters as SIP proxies.</span></span> <span data-ttu-id="09741-400">此外，還有其他媒體處理器可優化媒體流程。</span><span class="sxs-lookup"><span data-stu-id="09741-400">Also, there are additional media processors to optimize media flow.</span></span> <span data-ttu-id="09741-401">例如，我們目前沒有在澳大利亞（透過新加坡或香港）傳送 sip proxy 元件，但我們在澳大利亞有本機的媒體處理器。</span><span class="sxs-lookup"><span data-stu-id="09741-401">For example, we do not have a SIP proxy component now in Australia (SIP flows via Singapore or Hong Kong) but we do have the media processor locally in Australia.</span></span> <span data-ttu-id="09741-402">在本機提供媒體處理器的需求是由我們透過傳送流量（例如從澳大利亞到新加坡或香港）來取得的延隔時間來決定。</span><span class="sxs-lookup"><span data-stu-id="09741-402">The need for the media processors locally is dictated by the latency which we experience by sending traffic long-distance, for example from Australia to Singapore or Hong Kong.</span></span> <span data-ttu-id="09741-403">雖然從澳大利亞到香港或新加坡的流量範例中的延遲，仍可保持良好的 SIP 流量通話品質，而不需要進行即時媒體流量。</span><span class="sxs-lookup"><span data-stu-id="09741-403">While latency in the example of traffic flowing from Australia to Hong Kong or Singapore is acceptable to preserve good call quality for SIP traffic, for real-time media traffic it is not.</span></span>

<span data-ttu-id="09741-404">媒體處理器的位置：</span><span class="sxs-lookup"><span data-stu-id="09741-404">Location of the media processors:</span></span>

<span data-ttu-id="09741-405">已部署 SIP proxy 和媒體處理器元件的位置：</span><span class="sxs-lookup"><span data-stu-id="09741-405">Locations where both SIP proxy and media processor components deployed:</span></span>
- <span data-ttu-id="09741-406">我們（美國西部和東資料中心有兩個）</span><span class="sxs-lookup"><span data-stu-id="09741-406">US (two in US West and US East datacenters)</span></span>
- <span data-ttu-id="09741-407">歐洲（阿姆斯特丹與都柏林資料中心）</span><span class="sxs-lookup"><span data-stu-id="09741-407">Europe (Amsterdam and Dublin datacenters)</span></span>
- <span data-ttu-id="09741-408">亞洲（新加坡與香港資料中心）</span><span class="sxs-lookup"><span data-stu-id="09741-408">Asia (Singapore and Hong Kong datacenters)</span></span>

<span data-ttu-id="09741-409">只部署媒體處理器的位置（由上述最接近資料中心的 SIP 流程）：</span><span class="sxs-lookup"><span data-stu-id="09741-409">Locations where only media processors are deployed (SIP flows via the closest datacenter listed above):</span></span>
- <span data-ttu-id="09741-410">日本（JP 東部和西部資料中心）</span><span class="sxs-lookup"><span data-stu-id="09741-410">Japan (JP East and West datacenters)</span></span>
- <span data-ttu-id="09741-411">澳大利亞（AU 東和東南部資料中心）</span><span class="sxs-lookup"><span data-stu-id="09741-411">Australia (AU East and Southeast datacenters)</span></span>




## <a name="media-traffic-codecs"></a><span data-ttu-id="09741-412">媒體流量：編解碼器</span><span class="sxs-lookup"><span data-stu-id="09741-412">Media traffic: Codecs</span></span>

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a><span data-ttu-id="09741-413">在 SBC 與雲端媒體處理器或 Microsoft 團隊用戶端之間的腿。</span><span class="sxs-lookup"><span data-stu-id="09741-413">Leg between SBC and Cloud Media Processor or Microsoft Teams client.</span></span>
<span data-ttu-id="09741-414">適用于媒體旁路大小寫和非旁路情況。</span><span class="sxs-lookup"><span data-stu-id="09741-414">Applies to both media bypass case and non-bypass cases.</span></span>

<span data-ttu-id="09741-415">在會話邊界控制器和雲端媒體處理器（沒有媒體旁路）或團隊用戶端與 SBC （如果已啟用媒體旁路）之間，在腿的直接路由介面上，您可以使用下列編解碼器：</span><span class="sxs-lookup"><span data-stu-id="09741-415">The Direct Routing interface on the leg between the Session Border Controller and Cloud Media Processor (without media bypass) or between the Teams client and the SBC (if Media Bypass enabled) can use the following codecs:</span></span>

- <span data-ttu-id="09741-416">非媒體旁路（SBC 到雲端媒體處理器）：絞絲、711、722、G 729</span><span class="sxs-lookup"><span data-stu-id="09741-416">Non-Media bypass (SBC to Cloud Media Processor): SILK, G.711, G.722, G.729</span></span>
- <span data-ttu-id="09741-417">媒體旁路（SBC 至團隊用戶端）：絞絲、711、729、722、G</span><span class="sxs-lookup"><span data-stu-id="09741-417">Media Bypass (SBC to Teams client):  SILK, G.711, G.722, G.729</span></span>

<span data-ttu-id="09741-418">您可以從優惠中排除不想要的編解碼器，以強制在會話邊界控制器上使用特定的編解碼器。</span><span class="sxs-lookup"><span data-stu-id="09741-418">You can force use of the specific codec on the Session Border Controller by excluding undesirable codecs from the offer.</span></span>

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a><span data-ttu-id="09741-419">Microsoft 團隊用戶端與雲端媒體處理器之間的腿</span><span class="sxs-lookup"><span data-stu-id="09741-419">Leg between Microsoft Teams Client and Cloud Media Processor</span></span>
<span data-ttu-id="09741-420">僅適用于非媒體旁路大小寫。</span><span class="sxs-lookup"><span data-stu-id="09741-420">Applies to non-media bypass case only.</span></span> <span data-ttu-id="09741-421">在媒體旁路的情況下，媒體會直接在團隊用戶端和 SBC 之間流動。</span><span class="sxs-lookup"><span data-stu-id="09741-421">With Media Bypass, the media flows directly between the Teams client and the SBC.</span></span>

<span data-ttu-id="09741-422">在雲端媒體處理器與 Microsoft 團隊用戶端之間的腿上，使用的是絞絲或722。</span><span class="sxs-lookup"><span data-stu-id="09741-422">On the leg between the Cloud Media Processor and Microsoft Teams client either SILK or G.722 is used.</span></span> <span data-ttu-id="09741-423">這個腿的編解碼器選擇是以 Microsoft 演算法為基礎，考慮了多個參數。</span><span class="sxs-lookup"><span data-stu-id="09741-423">The codec choice on this leg is based on Microsoft algorithms, which take into consideration multiple parameters.</span></span> 


## <a name="supported-session-border-controllers-sbcs"></a><span data-ttu-id="09741-424">支援的會話邊界控制器（SBCs）</span><span class="sxs-lookup"><span data-stu-id="09741-424">Supported Session Border Controllers (SBCs)</span></span>

<span data-ttu-id="09741-425">Microsoft 只支援驗證的 SBCs 與直接路由配對。</span><span class="sxs-lookup"><span data-stu-id="09741-425">Microsoft only supports certified SBCs to pair with Direct Routing.</span></span> <span data-ttu-id="09741-426">因為企業語音對企業而言是很重要的，Microsoft 會以所選的 SBCs 來執行大量測試，並與 SBC 廠商搭配使用，以確保兩個系統相容。</span><span class="sxs-lookup"><span data-stu-id="09741-426">Because Enterprise Voice is critical for businesses, Microsoft runs intensive tests with the selected SBCs, and works with the SBC vendors to ensure the two systems are compatible.</span></span> 

<span data-ttu-id="09741-427">已驗證的裝置會列為 [團隊直接路由] 的 [認證者]。</span><span class="sxs-lookup"><span data-stu-id="09741-427">Devices that have been validated are listed as Certified for Teams Direct Routing.</span></span> <span data-ttu-id="09741-428">認證的裝置在所有情況下都能保證正常運作。</span><span class="sxs-lookup"><span data-stu-id="09741-428">The certified devices are guaranteed to work in all scenarios.</span></span> 

<span data-ttu-id="09741-429">如需支援的 SBCs 的詳細資訊，請參閱[認證以直接路由的會話邊界控制器清單](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="09741-429">For more information about supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

 
## <a name="see-also"></a><span data-ttu-id="09741-430">另請參閱</span><span class="sxs-lookup"><span data-stu-id="09741-430">See also</span></span>

[<span data-ttu-id="09741-431">設定直接路由</span><span class="sxs-lookup"><span data-stu-id="09741-431">Configure Direct Routing</span></span>](direct-routing-configure.md)
