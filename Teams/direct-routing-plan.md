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
description: 瞭解 Microsoft Phone 系統 Direct 路由如何讓您將支援的客戶提供的會話邊界控制器 (SBC) 至 Microsoft Phone System。
ms.openlocfilehash: f6ff76e2bb5725e7e574a7ea6c87ab5e99a6adc1
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359399"
---
# <a name="plan-direct-routing"></a><span data-ttu-id="7c5cd-103">規劃直接路由</span><span class="sxs-lookup"><span data-stu-id="7c5cd-103">Plan Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="7c5cd-104">請觀看下列會話，瞭解直接路由的優點、如何規劃，以及部署方式： [直接在 Microsoft 團隊中傳送路線](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="7c5cd-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="7c5cd-105">Microsoft Phone 系統 Direct 路由可讓您將支援的客戶提供的會話邊界控制器 (SBC) 連線至 Microsoft Phone System。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-105">Microsoft Phone System Direct Routing lets you connect a supported, customer-provided Session Border Controller (SBC) to Microsoft Phone System.</span></span>  <span data-ttu-id="7c5cd-106">例如，有了這項功能，您可以在 Microsoft 團隊用戶端 (PSTN) 連線（如下圖所示）來設定內部部署公用交換器電話網絡。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-106">With this capability, for example, you can configure on-premises Public Switched Telephone Network (PSTN) connectivity with Microsoft Teams client, as shown in the following diagram:</span></span> 

<span data-ttu-id="7c5cd-107">![顯示內部部署 PSTN 連線性配置的圖表](media/PlanDirectRouting1-PSTNwithTeams.png "與 Microsoft 團隊用戶端的內部部署 PSTN 連線能力")</span><span class="sxs-lookup"><span data-stu-id="7c5cd-107">![Diagram showing configuration of on-premises PSTN connectivity](media/PlanDirectRouting1-PSTNwithTeams.png "Configuration of on-premises PSTN connectivity with Microsoft Teams client")</span></span>

  > [!NOTE]
  > <span data-ttu-id="7c5cd-108">商務用 Skype Online 也能讓您與客戶提供的 SBC 搭配使用，但這需要一個內部部署商務用 Skype Server 部署，或是一個特殊版本的商務用 Skype （稱為雲端連接器），在 SBC 與 Microsoft 雲端之間。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-108">Skype for Business Online also lets you pair a customer-provided SBC, but this requires an on-premises Skype for Business Server deployment or a special edition of Skype for Business, called Cloud Connector, in between the SBC and the Microsoft Cloud.</span></span> <span data-ttu-id="7c5cd-109">這個案例稱為混合式語音。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-109">This scenario is known as hybrid voice.</span></span> <span data-ttu-id="7c5cd-110">相反地，直接路由可讓支援的 SBC 與 Microsoft 雲端之間的直接連接。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-110">In contrast, Direct Routing allows a direct connection between the supported SBC and the Microsoft Cloud.</span></span>

> [!Important]
> <span data-ttu-id="7c5cd-111">雲端連接器版本將于2021年7月31日與商務用 Skype Online 一起停用。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-111">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="7c5cd-112">貴組織升級至團隊後，請瞭解如何使用 [直接路由](direct-routing-landing-page.md)將內部部署電話網絡連線至團隊。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-112">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](direct-routing-landing-page.md).</span></span> 

<span data-ttu-id="7c5cd-113">透過直接路由，您可以將您的 SBC 連接到幾乎所有的電話幹線或與協力廠商 PSTN 裝置的互聯。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-113">With Direct Routing, you can connect your SBC to almost any telephony trunk or interconnect with third-party PSTN equipment.</span></span> <span data-ttu-id="7c5cd-114">[直接佈線] 可讓您：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-114">Direct Routing enables you to:</span></span> 

- <span data-ttu-id="7c5cd-115">在 Microsoft Phone 系統中使用幾乎任何 PSTN 幹線。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-115">Use virtually any PSTN trunk with Microsoft Phone System.</span></span> 
- <span data-ttu-id="7c5cd-116">在客戶擁有的電話裝置（例如協力廠商私人分支 exchange (PBX) 、模擬裝置和 Microsoft Phone 系統）之間設定互通性。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-116">Configure interoperability between customer-owned telephony equipment, such as a third-party private branch exchange (PBX), analog devices, and Microsoft Phone System.</span></span>

<span data-ttu-id="7c5cd-117">Microsoft 也提供所有雲端語音解決方案，例如通話方案。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-117">Microsoft also offers all-in-the-cloud voice solutions, such as Calling Plan.</span></span> <span data-ttu-id="7c5cd-118">不過，在下列情況下，混合式語音方案可能最適合您的組織：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-118">However, a hybrid voice solution might be best for your organization if:</span></span> 

- <span data-ttu-id="7c5cd-119">Microsoft 通話方案不適用於您的國家/地區。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-119">Microsoft Calling Plan is not available in your country.</span></span> 
- <span data-ttu-id="7c5cd-120">貴組織需要連線至協力廠商類比裝置、話務中心等。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-120">Your organization requires connection to third-party analog devices, call centers, and so on.</span></span> 
- <span data-ttu-id="7c5cd-121">您的組織已擁有 PSTN 載波的現有合約。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-121">Your organization has an existing contract with a PSTN carrier.</span></span>

<span data-ttu-id="7c5cd-122">直接路由還支援擁有 Microsoft 通話方案額外授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-122">Direct Routing also supports users who have the additional license for the Microsoft Calling Plan.</span></span> <span data-ttu-id="7c5cd-123">如需詳細資訊，請參閱 [電話系統和通話方案](calling-plan-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-123">For more information, see [Phone System and Calling Plans](calling-plan-landing-page.md).</span></span> 

<span data-ttu-id="7c5cd-124">透過直接傳送，當使用者參與排程的會議時，Microsoft 音訊會議服務會提供撥入號碼，這需要正確的授權。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-124">With Direct Routing, when users participate in a scheduled conference, the dial-in number is provided by Microsoft Audio Conferencing service, which requires proper licensing.</span></span>  <span data-ttu-id="7c5cd-125">當您撥出時，Microsoft 音訊會議服務會使用線上通話功能（需要適當的授權）來放置通話。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-125">When dialing out, the Microsoft Audio Conferencing service places the call using online calling capabilities, which requires proper licensing.</span></span> <span data-ttu-id="7c5cd-126"> (注意如果使用者沒有 Microsoft 音訊會議授權，通話會透過直接路由進行路由 ) 。如需詳細資訊，請參閱 [與團隊進行線上會議](https://products.office.com/microsoft-teams/online-meeting-solutions)。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-126">(Note if a user does not have a Microsoft Audio Conferencing license, the call routes through Direct Routing.) For more information, see [Online Meetings with Teams](https://products.office.com/microsoft-teams/online-meeting-solutions).</span></span> 
 
<span data-ttu-id="7c5cd-127">規劃直接路由部署是成功實現的關鍵。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-127">Planning your deployment of Direct Routing is key to a successful implementation.</span></span> <span data-ttu-id="7c5cd-128">本文將說明基礎結構和授權需求，並提供 SBC 連線性的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-128">This article describes infrastructure and licensing requirements and provides information about SBC connectivity:</span></span> 

- [<span data-ttu-id="7c5cd-129">基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="7c5cd-129">Infrastructure requirements</span></span>](#infrastructure-requirements)
- [<span data-ttu-id="7c5cd-130">授權與其他需求</span><span class="sxs-lookup"><span data-stu-id="7c5cd-130">Licensing and other requirements</span></span>](#licensing-and-other-requirements)
- [<span data-ttu-id="7c5cd-131">SBC 網功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="7c5cd-131">SBC domain names</span></span>](#sbc-domain-names)
- [<span data-ttu-id="7c5cd-132">SBC 公開信任的憑證</span><span class="sxs-lookup"><span data-stu-id="7c5cd-132">Public trusted certificate for the SBC</span></span>](#public-trusted-certificate-for-the-sbc)
- [<span data-ttu-id="7c5cd-133">SIP 信號： Fqdn</span><span class="sxs-lookup"><span data-stu-id="7c5cd-133">SIP Signaling: FQDNs</span></span>](#sip-signaling-fqdns)
- [<span data-ttu-id="7c5cd-134">SIP 信號：埠</span><span class="sxs-lookup"><span data-stu-id="7c5cd-134">SIP Signaling: Ports</span></span>](#sip-signaling-ports)
- [<span data-ttu-id="7c5cd-135">媒體流量：埠範圍</span><span class="sxs-lookup"><span data-stu-id="7c5cd-135">Media traffic: Port ranges</span></span>](#media-traffic-port-ranges)
- [<span data-ttu-id="7c5cd-136">支援的會話邊界控制器 (SBCs) </span><span class="sxs-lookup"><span data-stu-id="7c5cd-136">Supported Session Border Controllers (SBCs)</span></span>](#supported-session-border-controllers-sbcs)

<span data-ttu-id="7c5cd-137">如需有關設定直接路由的詳細資訊，請參閱 [設定直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-137">For detailed information about configuring Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="infrastructure-requirements"></a><span data-ttu-id="7c5cd-138">基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="7c5cd-138">Infrastructure requirements</span></span>
<span data-ttu-id="7c5cd-139">下表列出支援的 SBCs、網域及其他網路連線需求之基礎結構需求：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-139">The infrastructure requirements for the supported SBCs, domains, and other network connectivity requirements to deploy Direct Routing are listed in the following table:</span></span>  

|<span data-ttu-id="7c5cd-140">基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="7c5cd-140">Infrastructure requirement</span></span>|<span data-ttu-id="7c5cd-141">您需要下列各項</span><span class="sxs-lookup"><span data-stu-id="7c5cd-141">You need the following</span></span>|
|:--- |:--- |
|<span data-ttu-id="7c5cd-142"> (SBC 的會話邊界控制器) </span><span class="sxs-lookup"><span data-stu-id="7c5cd-142">Session Border Controller (SBC)</span></span>|<span data-ttu-id="7c5cd-143">受支援的 SBC。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-143">A supported SBC.</span></span> <span data-ttu-id="7c5cd-144">如需詳細資訊，請參閱 [支援的 SBCs](#supported-session-border-controllers-sbcs)。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-144">For more information, see [Supported SBCs](#supported-session-border-controllers-sbcs).</span></span>|
|<span data-ttu-id="7c5cd-145">連線至 SBC 的電話語音 trunks</span><span class="sxs-lookup"><span data-stu-id="7c5cd-145">Telephony trunks connected to the SBC</span></span>|<span data-ttu-id="7c5cd-146">一個或多個連線至 SBC 的電話 trunks。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-146">One or more telephony trunks connected to the SBC.</span></span> <span data-ttu-id="7c5cd-147">在一端，SBC 透過直接路由連接到 Microsoft 手機系統。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-147">On one end, the SBC connects to the Microsoft Phone System via Direct Routing.</span></span> <span data-ttu-id="7c5cd-148">SBC 也可以連接到協力廠商電話實體，例如 Pbx、類比電話卡等。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-148">The SBC can also connect to third-party telephony entities, such as PBXs, Analog Telephony Adapters, and so on.</span></span> <span data-ttu-id="7c5cd-149">任何連接至 SBC 的 PSTN 連接選項都會正常運作。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-149">Any PSTN connectivity option connected to the SBC will work.</span></span> <span data-ttu-id="7c5cd-150"> (將 PSTN trunks 設定至 SBC，請參閱 SBC 廠商或幹線供應商。 ) </span><span class="sxs-lookup"><span data-stu-id="7c5cd-150">(For configuration of the PSTN trunks to the SBC, please refer to the SBC vendors or trunk providers.)</span></span>|
|<span data-ttu-id="7c5cd-151">Microsoft 365 或 Office 365 組織</span><span class="sxs-lookup"><span data-stu-id="7c5cd-151">Microsoft 365 or Office 365 organization</span></span>|<span data-ttu-id="7c5cd-152">您用來將 Microsoft 團隊使用者用來家用的 Microsoft 365 或 Office 365 組織，以及 SBC 的設定與連接。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-152">An Microsoft 365 or Office 365 organization that you use to home your Microsoft Teams users, and the configuration and connection to the SBC.</span></span>|
|<span data-ttu-id="7c5cd-153">使用者註冊機構</span><span class="sxs-lookup"><span data-stu-id="7c5cd-153">User registrar</span></span>|<span data-ttu-id="7c5cd-154">使用者必須駐留在 Microsoft 365 或 Office 365 中。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-154">User must be homed in Microsoft 365 or Office 365.</span></span><br/><span data-ttu-id="7c5cd-155">如果您的公司有內部部署商務用 Skype 或 Lync 環境，且其混合式連線至 Microsoft 365 或 Office 365，您就無法在小組中為使用者駐留內部部署的使用者啟用語音功能。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-155">If your company has an on-premises Skype for Business or Lync environment with hybrid connectivity to Microsoft 365 or Office 365, you cannot enable voice in Teams for a user homed on-premises.</span></span><br/><br/><span data-ttu-id="7c5cd-156">若要檢查使用者的註冊機構，請使用下列商務用 Skype Online PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-156">To check the registrar of a user, use the following Skype for Business Online PowerShell cmdlet:</span></span><br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/><span data-ttu-id="7c5cd-157">Cmdlet 的輸出應該會顯示：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-157">The output of the cmdlet should show:</span></span><br/><code>HostingProvider : sipfed.online.lync.com</code>|
|<span data-ttu-id="7c5cd-158">定義域</span><span class="sxs-lookup"><span data-stu-id="7c5cd-158">Domains</span></span>|<span data-ttu-id="7c5cd-159">新增至您的 Microsoft 365 或 Office 365 組織的一個或多個網域。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-159">One or more domains added to your Microsoft 365 or Office 365 organizations.</span></span><br/><br/><span data-ttu-id="7c5cd-160">請注意，您無法使用 \* 針對您的租使用者自動建立的預設網域 onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-160">Note that you cannot use the default domain, \*.onmicrosoft.com, that is automatically created for your tenant.</span></span><br/><br/><span data-ttu-id="7c5cd-161">若要查看網域，您可以使用下列商務用 Skype Online PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-161">To view the domains, you can use the following Skype for Business Online PowerShell cmdlet:</span></span><br/><code>Get-CsTenant \| fl Domains</code><br/><br/><span data-ttu-id="7c5cd-162">如需網域與 Microsoft 365 或 Office 365 組織的詳細資訊，請參閱 [網域常見問題](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-162">For more information about domains and Microsoft 365 or Office 365 organizations, see [Domains FAQ](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).</span></span>|
|<span data-ttu-id="7c5cd-163">SBC 的公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7c5cd-163">Public IP address for the SBC</span></span>|<span data-ttu-id="7c5cd-164">可用於連線至 SBC 的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-164">A public IP address that can be used to connect to the SBC.</span></span> <span data-ttu-id="7c5cd-165">根據 SBC 的類型而定，SBC 可以使用 NAT。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-165">Based on the type of SBC, the SBC can use NAT.</span></span>|
|<span data-ttu-id="7c5cd-166">在 SBC 中 (FQDN) 的完整功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="7c5cd-166">Fully Qualified Domain Name (FQDN) for the SBC</span></span>|<span data-ttu-id="7c5cd-167">SBC 的 FQDN，其中 FQDN 的網域部分是您的 Microsoft 365 或 Office 365 組織中的註冊網域之一。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-167">A FQDN for the SBC, where the domain portion of the FQDN is one of the registered domains in your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="7c5cd-168">如需詳細資訊，請參閱 [SBC 功能變數名稱](#sbc-domain-names)。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-168">For more information, see [SBC domain names](#sbc-domain-names).</span></span>|
|<span data-ttu-id="7c5cd-169">SBC 的公用 DNS 專案</span><span class="sxs-lookup"><span data-stu-id="7c5cd-169">Public DNS entry for the SBC</span></span> |<span data-ttu-id="7c5cd-170">將 SBC FQDN 對應至公用 IP 位址的公用 DNS 專案。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-170">A public DNS entry mapping the SBC FQDN to the public IP Address.</span></span> |
|<span data-ttu-id="7c5cd-171">SBC 公開信任的憑證</span><span class="sxs-lookup"><span data-stu-id="7c5cd-171">Public trusted certificate for the SBC</span></span> |<span data-ttu-id="7c5cd-172">SBC 的憑證，用於與直接路由的所有通訊。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-172">A certificate for the SBC to be used for all communication with Direct Routing.</span></span> <span data-ttu-id="7c5cd-173">如需詳細資訊，請參閱 [SBC 的公用信任憑證](#public-trusted-certificate-for-the-sbc)。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-173">For more information, see [Public trusted certificate for the SBC](#public-trusted-certificate-for-the-sbc).</span></span>|
|<span data-ttu-id="7c5cd-174">直接路由的連接點</span><span class="sxs-lookup"><span data-stu-id="7c5cd-174">Connection points for Direct Routing</span></span> |<span data-ttu-id="7c5cd-175">直接路由的連接點是下列三個 Fqdn：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-175">The connection points for Direct Routing are the following three FQDNs:</span></span><br/><br/><span data-ttu-id="7c5cd-176">`sip.pstnhub.microsoft.com` –必須先嘗試使用全域 FQDN。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-176">`sip.pstnhub.microsoft.com` – Global FQDN, must be tried first.</span></span><br/><span data-ttu-id="7c5cd-177">`sip2.pstnhub.microsoft.com` –次要 FQDN，地理位置對應至第二個優先順序區域。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-177">`sip2.pstnhub.microsoft.com` – Secondary FQDN, geographically maps to the second priority region.</span></span><br/><span data-ttu-id="7c5cd-178">`sip3.pstnhub.microsoft.com` –三元 FQDN，地理位置對應至第三個優先順序區域。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-178">`sip3.pstnhub.microsoft.com` – Tertiary FQDN, geographically maps to the third priority region.</span></span><br/><br/><span data-ttu-id="7c5cd-179">如需設定需求的相關資訊，請參閱 [SIP 信號： fqdn](#sip-signaling-fqdns)。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-179">For information on configuration requirements, see [SIP Signaling: FQDNs](#sip-signaling-fqdns).</span></span>|
|<span data-ttu-id="7c5cd-180">用於直接路由媒體的防火牆 IP 位址和埠</span><span class="sxs-lookup"><span data-stu-id="7c5cd-180">Firewall IP addresses and ports for Direct Routing media</span></span> |<span data-ttu-id="7c5cd-181">SBC 會與雲端中的下列服務進行通訊：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-181">The SBC communicates to the following services in the cloud:</span></span><br/><br/><span data-ttu-id="7c5cd-182">負責處理信號的 SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="7c5cd-182">SIP Proxy, which handles the signaling</span></span><br/><span data-ttu-id="7c5cd-183">處理媒體的媒體處理器-除了媒體旁路</span><span class="sxs-lookup"><span data-stu-id="7c5cd-183">Media Processor, which handles media -except when Media Bypass is on</span></span><br/><br/><span data-ttu-id="7c5cd-184">這兩個服務在 Microsoft 雲端中都有不同的 IP 位址，本文稍後會說明此檔。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-184">These two services have separate IP addresses in Microsoft Cloud, described later in this document.</span></span><br/><br/><span data-ttu-id="7c5cd-185">如需詳細資訊，請參閱[url 和 IP 位址範圍](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)中的[Microsoft 團隊區段](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-185">For more information, see the [Microsoft Teams section](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) in [URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> |
|<span data-ttu-id="7c5cd-186">媒體傳輸設定檔</span><span class="sxs-lookup"><span data-stu-id="7c5cd-186">Media Transport Profile</span></span>|<span data-ttu-id="7c5cd-187">TCP/RTP/SAVP</span><span class="sxs-lookup"><span data-stu-id="7c5cd-187">TCP/RTP/SAVP</span></span> <br/><span data-ttu-id="7c5cd-188">UDP/RTP/SAVP</span><span class="sxs-lookup"><span data-stu-id="7c5cd-188">UDP/RTP/SAVP</span></span>|
<span data-ttu-id="7c5cd-189">Microsoft 團隊媒體的防火牆 IP 位址和埠</span><span class="sxs-lookup"><span data-stu-id="7c5cd-189">Firewall IP addresses and ports for Microsoft Teams media</span></span> |<span data-ttu-id="7c5cd-190">如需詳細資訊，請參閱 [url 與 IP 位址範圍](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-190">For more information, see [URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> |
|||

## <a name="licensing-and-other-requirements"></a><span data-ttu-id="7c5cd-191">授權與其他需求</span><span class="sxs-lookup"><span data-stu-id="7c5cd-191">Licensing and other requirements</span></span> 

<span data-ttu-id="7c5cd-192">直接傳送的使用者必須具有下列在 Microsoft 365 或 Office 365 中指派的授權：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-192">Users of Direct Routing must have the following licenses assigned in Microsoft 365 or Office 365:</span></span> 

- <span data-ttu-id="7c5cd-193">Microsoft Phone System。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-193">Microsoft Phone System.</span></span> 
- <span data-ttu-id="7c5cd-194">Microsoft 團隊 + 商務用 Skype 方案2（如果包含在授權中）。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-194">Microsoft Teams + Skype for Business Plan 2, if included in licensing.</span></span>
- <span data-ttu-id="7c5cd-195">Microsoft 音訊會議 (請閱讀筆記及下方的段落，以取得有關何時需要授權的特定範例) 。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-195">Microsoft Audio Conferencing (please read the notes and the paragraph below for specific examples about when the license is required).</span></span>

> [!NOTE]
> <span data-ttu-id="7c5cd-196">商務用 Skype 方案不應從隨附的任何授權合約中移除。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-196">Skype for Business Plan should not be removed from any licensing agreement where it is included.</span></span> 


> [!IMPORTANT]
>  <span data-ttu-id="7c5cd-197">如果您想要將外部參與者新增至排程的會議，請撥打電話給他們，或提供撥入號碼，必須具備音訊會議授權。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-197">In the case that you would like to add external participants to scheduled meetings, either by dialing out to them or by providing the dial-in number, the audio conferencing license is required.</span></span>


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a><span data-ttu-id="7c5cd-198">即席通話升級和音訊會議授權</span><span class="sxs-lookup"><span data-stu-id="7c5cd-198">Ad hoc call escalation and Audio Conferencing license</span></span>

<span data-ttu-id="7c5cd-199">團隊使用者可以啟動一對一團隊至 PSTN 或小組通話小組，並將 PSTN 參與者加入該小組。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-199">A Teams user can start a one-on-one Teams to PSTN or Teams to Teams call and add a PSTN participant to it.</span></span> <span data-ttu-id="7c5cd-200">這個案例稱為「ad hoc」會議。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-200">This scenario is called an ad hoc conference.</span></span> <span data-ttu-id="7c5cd-201">呼叫所採取的路徑，取決於升級通話的使用者是否已指派 Microsoft 音訊會議授權：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-201">The path that the call takes depends whether the user who escalates the call has a Microsoft Audio Conferencing license assigned or not:</span></span>

- <span data-ttu-id="7c5cd-202">如果升級通話的小組使用者已指派 Microsoft 音訊會議授權，則會透過 Microsoft 音訊會議服務進行升級。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-202">If the Teams user who escalates the call has a Microsoft Audio Conferencing license assigned, the escalation happens through the Microsoft Audio Conferencing service.</span></span> <span data-ttu-id="7c5cd-203">受邀加入現有通話的遠端 PSTN 參與者會收到來電通知，並查看指派給啟動呈報之小組使用者的 Microsoft 橋接器號碼。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-203">The remote PSTN participant who is invited to the existing call receives a notification about the incoming call and sees the number of the Microsoft bridge assigned to the Teams user who initiated the escalation.</span></span>
- <span data-ttu-id="7c5cd-204">如果升級通話的小組使用者沒有指派 Microsoft 音訊會議授權，就會透過連線至直接路由介面的會話邊界控制器進行升級。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-204">If the Teams user who escalates the call does not have the Microsoft Audio Conferencing license assigned, the escalation happens through a Session Border Controller connected to the Direct Routing interface.</span></span> <span data-ttu-id="7c5cd-205">受邀接聽通話的遠端 PSTN 參與者會收到來電的通知，並查看已開始升級的小組使用者人數。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-205">The remote PSTN participant who is invited to the call receives a notification about the incoming call and sees the number of the Teams user who initiated the escalation.</span></span> <span data-ttu-id="7c5cd-206">上報所用的特定 SBC 是由使用者的路由原則所定義。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-206">The specific SBC used for the escalation is defined by Routing Policy of the user.</span></span> 


<span data-ttu-id="7c5cd-207">此外，您必須確認下列事項：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-207">In addition, you must ensure the following:</span></span>
 
- <span data-ttu-id="7c5cd-208">CsOnlineVoiceRoutingPolicy 已指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-208">CsOnlineVoiceRoutingPolicy is assigned to the user.</span></span> 
- <span data-ttu-id="7c5cd-209">在 Microsoft 團隊的租使用者層級啟用 [允許私人通話]。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-209">Allow Private Calling is enabled at the tenant level for Microsoft Teams.</span></span> 

<span data-ttu-id="7c5cd-210">直接路由還支援 Microsoft 通話方案授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-210">Direct Routing also supports users who are licensed for Microsoft Calling Plan.</span></span> <span data-ttu-id="7c5cd-211">含有通話方案的 Microsoft Phone 系統可以使用直接路由介面傳送一些通話。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-211">Microsoft Phone System with Calling Plan can route some calls using the Direct Routing interface.</span></span> <span data-ttu-id="7c5cd-212">不過，使用者的電話號碼必須是線上購買或移植至 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-212">However, the users' phone numbers must be either acquired online or ported to Microsoft.</span></span>  

<span data-ttu-id="7c5cd-213">針對相同的使用者混合通話方案和直接路由連線是選擇性的，但可能很有用 (例如，在指派 Microsoft 通話方案，但想要使用 SBC) 路由某些來電時。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-213">Mixing Calling Plan and Direct Routing connectivity for the same user is optional, but could be useful (for example, when the user is assigned a Microsoft Calling Plan but wants to route some calls using the SBC).</span></span> <span data-ttu-id="7c5cd-214">其中一個最常見的案例是呼叫協力廠商的 Pbx。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-214">One of the most common scenarios is calls to third-party PBXs.</span></span>  <span data-ttu-id="7c5cd-215">透過協力廠商 Pbx，所有通話（除了連接至該 Pbx 的電話除外）都是使用 Microsoft 通話方案進行路由，但連接至協力廠商 Pbx 的電話撥打電話給 SBC，因此，不會在商業網路中，也不是 PSTN。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-215">With third-party PBXs, all calls, except calls to the phones connected to that PBXs, are routed using Microsoft Calling Plan, but calls to the phones connected to third-party PBXs go to the SBC, and therefore stay within the enterprise network and not the PSTN.</span></span> 

<span data-ttu-id="7c5cd-216">如需手機系統授權的詳細資訊，請參閱 [充分利用 Office](https://products.office.com/compare-all-microsoft-office-products?tab=2) 和 [方案選項](https://technet.microsoft.com/library/office-365-plan-options.aspx)。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-216">For more information about Phone System licensing, see [Get the most from Office](https://products.office.com/compare-all-microsoft-office-products?tab=2) and [Plan Options](https://technet.microsoft.com/library/office-365-plan-options.aspx).</span></span> 

<span data-ttu-id="7c5cd-217">如需手機系統授權的詳細資訊，請參閱 [Microsoft 團隊附加元件授權](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-217">For more information about Phone System licensing, see [Microsoft Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span> 

## <a name="supported-end-points"></a><span data-ttu-id="7c5cd-218">支援的端點</span><span class="sxs-lookup"><span data-stu-id="7c5cd-218">Supported end points</span></span> 

<span data-ttu-id="7c5cd-219">您可以用做為終點：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-219">You can use as an end point:</span></span>

- <span data-ttu-id="7c5cd-220">任何團隊用戶端。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-220">Any Teams client.</span></span> 
- <span data-ttu-id="7c5cd-221">常見的區域電話。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-221">Common Area Phones.</span></span> <span data-ttu-id="7c5cd-222">請參閱 [設定 Microsoft 團隊的通用區域電話授權](https://docs.microsoft.com/microsoftteams/set-up-common-area-phones)。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-222">See [Set up the Common Area Phone license for Microsoft Teams](https://docs.microsoft.com/microsoftteams/set-up-common-area-phones).</span></span> <span data-ttu-id="7c5cd-223">注意在使用直接傳送來設定一般的區域手機時，不需要通話方案授權。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-223">Note you do not need a Calling Plan license when setting up a Common Area Phone with Direct Routing.</span></span>
- <span data-ttu-id="7c5cd-224">商務用 Skype 3PIP 電話。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-224">Skype for Business 3PIP phones.</span></span> <span data-ttu-id="7c5cd-225">[Microsoft 團隊請參閱商務用 Skype 手機 (3PIP) 支援](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)</span><span class="sxs-lookup"><span data-stu-id="7c5cd-225">See [Skype for Business phones (3PIP) support with Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)</span></span>


## <a name="sbc-domain-names"></a><span data-ttu-id="7c5cd-226">SBC 網功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="7c5cd-226">SBC domain names</span></span>

<span data-ttu-id="7c5cd-227">SBC 網功能變數名稱稱必須來自于租使用者網域中註冊的其中一個名稱。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-227">The SBC domain name must be from one of the names registered in Domains of the tenant.</span></span> <span data-ttu-id="7c5cd-228">您無法 \* 針對 SBC 的 FQDN 名稱使用 onmicrosoft.com 租使用者。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-228">You cannot use the \*.onmicrosoft.com tenant for the FQDN name of the SBC.</span></span>

<span data-ttu-id="7c5cd-229">下表顯示針對租使用者註冊的 DNS 名稱範例，無論該名稱是否可做為 SBC 的 FQDN，以及有效 FQDN 名稱的範例：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-229">The following table shows examples of DNS names registered for the tenant, whether the name can be used as an FQDN for the SBC, and examples of valid FQDN names:</span></span>

|<span data-ttu-id="7c5cd-230">DNS 名稱</span><span class="sxs-lookup"><span data-stu-id="7c5cd-230">DNS name</span></span>|<span data-ttu-id="7c5cd-231">可用於 SBC FQDN</span><span class="sxs-lookup"><span data-stu-id="7c5cd-231">Can be used for SBC FQDN</span></span>|<span data-ttu-id="7c5cd-232">FQDN 名稱範例</span><span class="sxs-lookup"><span data-stu-id="7c5cd-232">Examples of FQDN names</span></span>|
|:--- |:--- |:--- |
<span data-ttu-id="7c5cd-233">contoso.com</span><span class="sxs-lookup"><span data-stu-id="7c5cd-233">contoso.com</span></span>|<span data-ttu-id="7c5cd-234">是</span><span class="sxs-lookup"><span data-stu-id="7c5cd-234">Yes</span></span>|<span data-ttu-id="7c5cd-235">**有效的名稱：**</span><span class="sxs-lookup"><span data-stu-id="7c5cd-235">**Valid names:**</span></span><br/><span data-ttu-id="7c5cd-236">sbc1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7c5cd-236">sbc1.contoso.com</span></span><br/><span data-ttu-id="7c5cd-237">ssbcs15.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7c5cd-237">ssbcs15.contoso.com</span></span><br/><span data-ttu-id="7c5cd-238">europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7c5cd-238">europe.contoso.com</span></span>|
|<span data-ttu-id="7c5cd-239">contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="7c5cd-239">contoso.onmicrosoft.com</span></span>|<span data-ttu-id="7c5cd-240">否</span><span class="sxs-lookup"><span data-stu-id="7c5cd-240">No</span></span>|<span data-ttu-id="7c5cd-241">SBC 名稱不支援使用 \*. onmicrosoft.com 網域</span><span class="sxs-lookup"><span data-stu-id="7c5cd-241">Using \*.onmicrosoft.com domains is not supported for SBC names</span></span>

<span data-ttu-id="7c5cd-242">假設您要使用新的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-242">Assume you want to use a new domain name.</span></span> <span data-ttu-id="7c5cd-243">例如，您的租使用者有 contoso.com 做為在您的租使用者中註冊的功能變數名稱，而您想要使用 sbc1.sip.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-243">For example, your tenant has contoso.com as a domain name registered in your tenant, and you want to use sbc1.sip.contoso.com.</span></span> <span data-ttu-id="7c5cd-244">您必須先在租使用者中的網域中註冊功能變數名稱 sip.contoso.com，才能將其與 name sbc1.sip.contoso.com 進行配對。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-244">Before you can pair an SBC with the name sbc1.sip.contoso.com, you must register the domain name sip.contoso.com in Domains in your tenant.</span></span> <span data-ttu-id="7c5cd-245">如果您在註冊功能變數名稱前嘗試搭配 sbc1.sip.contoso.com 進行配對，您會收到下列錯誤：「無法使用「sbc1.sip.contoso.com」網域，因為它未針對此租使用者進行設定。」</span><span class="sxs-lookup"><span data-stu-id="7c5cd-245">If you try pairing an SBC with sbc1.sip.contoso.com before registering the domain name, you will get the following error: "Cannot use the "sbc1.sip.contoso.com" domain as it was not configured for this tenant."</span></span>
<span data-ttu-id="7c5cd-246">在您新增功能變數名稱之後，您也需要使用 UPN user@sip.contoso.com 建立使用者並指派小組授權。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-246">After you add the domain name, you also need to create a user with UPN user@sip.contoso.com and assign a Teams license.</span></span> <span data-ttu-id="7c5cd-247">在將功能變數名稱新增至租使用者的網域之後，最多可能需要24小時才能完全提供該功能變數名稱，並會建立一個具有新名稱的使用者，並指派授權給使用者。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-247">It might take up to 24 hours to fully provision the domain name after it is added to Domains of your tenant, a user with a new name is created, and a license is assigned to the user.</span></span> 

<span data-ttu-id="7c5cd-248">公司可能會在一個租使用者中有數個 SIP 位址空間。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-248">It is possible that a company might have several SIP address spaces in one tenant.</span></span> <span data-ttu-id="7c5cd-249">例如，公司可能會將 contoso.com 做為 SIP 位址空間，並 fabrikam.com 為第二個 SIP 位址空間。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-249">For example, a company might have contoso.com as a SIP address space and fabrikam.com as the second SIP address space.</span></span> <span data-ttu-id="7c5cd-250">有些使用者有位址 user@contoso.com，而有些使用者則是位址 user@fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-250">Some users have address user@contoso.com and some users have address user@fabrikam.com.</span></span> 

<span data-ttu-id="7c5cd-251">SBC 只需要一個 FQDN，而且可以從成對的租使用者中的任何位址空間來服務使用者。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-251">The SBC only needs one FQDN and can service users from any address space in the paired tenant.</span></span> <span data-ttu-id="7c5cd-252">例如，擁有 name sbc1.contoso.com 的 SBC 可以接收並傳送具有位址 user@contoso.com 和 user@fabrikam.com 之使用者的 PSTN 流量，只要這些 SIP 位址空間已在相同的租使用者中註冊。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-252">For example,  an SBC with the name sbc1.contoso.com can receive and send the PSTN traffic for users with addresses user@contoso.com and user@fabrikam.com as long as these SIP address spaces are registered in the same tenant.</span></span>  

## <a name="public-trusted-certificate-for-the-sbc"></a><span data-ttu-id="7c5cd-253">SBC 公開信任的憑證</span><span class="sxs-lookup"><span data-stu-id="7c5cd-253">Public trusted certificate for the SBC</span></span>

<span data-ttu-id="7c5cd-254">Microsoft 建議您在 (CSR) 中產生認證簽署要求，以要求 SBC 的憑證。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-254">Microsoft recommends that you request the certificate for the SBC by generating a certification signing request (CSR).</span></span> <span data-ttu-id="7c5cd-255">如需針對 SBC 產生 CSR 的特定指示，請參閱由您的 SBC 轉銷商提供的互連指示或檔。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-255">For specific instructions on generating a CSR for an SBC, refer to the interconnection instructions or documentation provided by your SBC vendors.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="7c5cd-256">大多數憑證授權單位 (CAs) 需要私密金鑰大小至少為2048。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-256">Most Certificate Authorities (CAs) require the private key size to be at least 2048.</span></span> <span data-ttu-id="7c5cd-257">產生 CSR 時，請記住這一點。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-257">Keep this in mind when generating the CSR.</span></span>

<span data-ttu-id="7c5cd-258">在 subject 欄位中，憑證必須將 SBC FQDN 作為常見名稱 (CN) 。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-258">The certificate needs to have the SBC FQDN as the common name (CN) in the subject field.</span></span>

<span data-ttu-id="7c5cd-259">或者，直接路由支援 SAN 中的萬用字元，而萬用字元必須符合 [TLS 上標準 RFC HTTP](https://tools.ietf.org/html/rfc2818#section-3.1)的要求。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-259">Alternatively, Direct Routing  supports a wildcard in SAN, and the wildcard needs to conform to standard [RFC HTTP Over TLS](https://tools.ietf.org/html/rfc2818#section-3.1).</span></span> <span data-ttu-id="7c5cd-260">\*在 SAN 中將會使用 contoso.com，這會與 SBC FQDN sbc.contoso.com 相符，但不會與 sbc.test.contoso.com 相符。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-260">An example would be using \*.contoso.com in the SAN, which would match the SBC FQDN sbc.contoso.com, but wouldn't match with sbc.test.contoso.com.</span></span>

<span data-ttu-id="7c5cd-261">憑證需要由下列其中一個根憑證授權單位產生：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-261">The certificate needs to be generated by one of the following root certificate authorities:</span></span>

- <span data-ttu-id="7c5cd-262">AffirmTrust</span><span class="sxs-lookup"><span data-stu-id="7c5cd-262">AffirmTrust</span></span>
- <span data-ttu-id="7c5cd-263">AddTrust 外部 CA 根目錄</span><span class="sxs-lookup"><span data-stu-id="7c5cd-263">AddTrust External CA Root</span></span>
- <span data-ttu-id="7c5cd-264">巴爾的摩 CyberTrust Root \*</span><span class="sxs-lookup"><span data-stu-id="7c5cd-264">Baltimore CyberTrust Root\*</span></span>
- <span data-ttu-id="7c5cd-265">Buypass</span><span class="sxs-lookup"><span data-stu-id="7c5cd-265">Buypass</span></span>
- <span data-ttu-id="7c5cd-266">Cybertrust</span><span class="sxs-lookup"><span data-stu-id="7c5cd-266">Cybertrust</span></span>
- <span data-ttu-id="7c5cd-267">Class 3 公用主要憑證授權單位</span><span class="sxs-lookup"><span data-stu-id="7c5cd-267">Class 3 Public Primary Certification Authority</span></span>
- <span data-ttu-id="7c5cd-268">Comodo 安全的根 CA</span><span class="sxs-lookup"><span data-stu-id="7c5cd-268">Comodo Secure Root CA</span></span>
- <span data-ttu-id="7c5cd-269">德國 Telekom</span><span class="sxs-lookup"><span data-stu-id="7c5cd-269">Deutsche Telekom</span></span> 
- <span data-ttu-id="7c5cd-270">DigiCert 全域根 CA</span><span class="sxs-lookup"><span data-stu-id="7c5cd-270">DigiCert Global Root CA</span></span>
- <span data-ttu-id="7c5cd-271">DigiCert 高確定性 EV 根 CA</span><span class="sxs-lookup"><span data-stu-id="7c5cd-271">DigiCert High Assurance EV Root CA</span></span>
- <span data-ttu-id="7c5cd-272">Entrust</span><span class="sxs-lookup"><span data-stu-id="7c5cd-272">Entrust</span></span>
- <span data-ttu-id="7c5cd-273">GlobalSign</span><span class="sxs-lookup"><span data-stu-id="7c5cd-273">GlobalSign</span></span>
- <span data-ttu-id="7c5cd-274">移至 Go daddy</span><span class="sxs-lookup"><span data-stu-id="7c5cd-274">Go Daddy</span></span>
- <span data-ttu-id="7c5cd-275">GeoTrust</span><span class="sxs-lookup"><span data-stu-id="7c5cd-275">GeoTrust</span></span>
- <span data-ttu-id="7c5cd-276">Verisign，Inc。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-276">Verisign, Inc.</span></span> 
- <span data-ttu-id="7c5cd-277">SSL.com</span><span class="sxs-lookup"><span data-stu-id="7c5cd-277">SSL.com</span></span>
- <span data-ttu-id="7c5cd-278">Starfield</span><span class="sxs-lookup"><span data-stu-id="7c5cd-278">Starfield</span></span>
- <span data-ttu-id="7c5cd-279">Microsoft 適用的 Symantec 企業行動裝置根</span><span class="sxs-lookup"><span data-stu-id="7c5cd-279">Symantec Enterprise Mobile Root for Microsoft</span></span> 
- <span data-ttu-id="7c5cd-280">SwissSign</span><span class="sxs-lookup"><span data-stu-id="7c5cd-280">SwissSign</span></span>
- <span data-ttu-id="7c5cd-281">Thawte 日戳 CA</span><span class="sxs-lookup"><span data-stu-id="7c5cd-281">Thawte Timestamping CA</span></span>
- <span data-ttu-id="7c5cd-282">Trustwave</span><span class="sxs-lookup"><span data-stu-id="7c5cd-282">Trustwave</span></span>
- <span data-ttu-id="7c5cd-283">TeliaSonera</span><span class="sxs-lookup"><span data-stu-id="7c5cd-283">TeliaSonera</span></span> 
- <span data-ttu-id="7c5cd-284">T 系統國際 GmbH (德國 Telekom) </span><span class="sxs-lookup"><span data-stu-id="7c5cd-284">T-Systems International GmbH (Deutsche Telekom)</span></span>
- <span data-ttu-id="7c5cd-285">QuoVadis</span><span class="sxs-lookup"><span data-stu-id="7c5cd-285">QuoVadis</span></span>



> [!NOTE]
> <span data-ttu-id="7c5cd-286">\* 如果在 SBC 上針對團隊連結啟用了相互 TLS (MTLS) 支援，則您必須在 SBC 信任的團隊 TLS 內容根存放區中安裝巴爾的摩 CyberTrust 根憑證。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-286">\*If Mutual TLS (MTLS) support is enabled for the Teams connection on the SBC, then you must install the Baltimore CyberTrust Root Certificate in the SBC Trusted Root Store of the Teams TLS context.</span></span> <span data-ttu-id="7c5cd-287"> (這是因為 Microsoft 服務憑證使用巴爾的摩根憑證。 ) 若要下載巴爾的摩根憑證，請參閱 [Office 365 加密鏈](https://docs.microsoft.com/microsoft-365/compliance/encryption-office-365-certificate-chains)。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-287">(This is because the Microsoft service certificates use the Baltimore root certificate.) To download the Baltimore root certificate, see [Office 365 Encryption chains](https://docs.microsoft.com/microsoft-365/compliance/encryption-office-365-certificate-chains).</span></span>

<span data-ttu-id="7c5cd-288">Microsoft 正在努力根據客戶要求新增其他認證機構。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-288">Microsoft is working on adding additional certification authorities based on customer requests.</span></span> 

## <a name="sip-signaling-fqdns"></a><span data-ttu-id="7c5cd-289">SIP 信號： Fqdn</span><span class="sxs-lookup"><span data-stu-id="7c5cd-289">SIP Signaling: FQDNs</span></span> 

<span data-ttu-id="7c5cd-290">在下列環境中提供直接路由：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-290">Direct Routing is offered in the following environments:</span></span>
- <span data-ttu-id="7c5cd-291">Microsoft 365 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="7c5cd-291">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="7c5cd-292">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="7c5cd-292">Office 365 GCC</span></span>
- <span data-ttu-id="7c5cd-293">Office 365 GCC 高</span><span class="sxs-lookup"><span data-stu-id="7c5cd-293">Office 365 GCC High</span></span>
- <span data-ttu-id="7c5cd-294">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="7c5cd-294">Office 365 DoD</span></span>

<span data-ttu-id="7c5cd-295">深入瞭解 [Office 365 和美國政府環境](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) （例如 GCC、gcc 高和 DoD）。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-295">Learn more about [Office 365 and US Government environments](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="7c5cd-296">Microsoft 365、Office 365 及 Office 365 GCC 環境</span><span class="sxs-lookup"><span data-stu-id="7c5cd-296">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="7c5cd-297">直接路由的連接點是下列三個 Fqdn：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-297">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="7c5cd-298">**sip.pstnhub.microsoft.com** –全域 FQDN-必須先嘗試。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-298">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="7c5cd-299">當 SBC 傳送要求來解析此名稱時，Microsoft Azure DNS 伺服器會傳回指向指派給 SBC 之主要 Azure 資料中心的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-299">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="7c5cd-300">作業是以資料中心的效能指標，以及與 SBC 有關的地理位置為基礎。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-300">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="7c5cd-301">傳回的 IP 位址會對應到主要 FQDN。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-301">The IP address returned corresponds to the primary FQDN.</span></span>
- <span data-ttu-id="7c5cd-302">**sip2.pstnhub.microsoft.com** –次要 FQDN-地理位置對應至第二個優先順序區域。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-302">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>
- <span data-ttu-id="7c5cd-303">**sip3.pstnhub.microsoft.com** –三元 FQDN-[地理位置] 對應至第三個優先順序區域。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-303">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="7c5cd-304">若要執行下列三個 Fqdn，必須進行下列動作：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-304">Placing these three FQDNs in order is required to:</span></span>

- <span data-ttu-id="7c5cd-305">透過查詢第一個 FQDN) ，提供 (較小且最接近所指派 SBC 資料中心的最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-305">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>
- <span data-ttu-id="7c5cd-306">提供從 SBC 連線到發生暫時問題的資料中心時的容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-306">Provide failover when connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="7c5cd-307">如需詳細資訊，請參閱下方的 [容錯移轉機制](#failover-mechanism-for-sip-signaling) 。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-307">For more information, see [Failover mechanism](#failover-mechanism-for-sip-signaling) below.</span></span>  

<span data-ttu-id="7c5cd-308">Fqdn （sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com 和 sip3.pstnhub.microsoft.com）會解析成下列其中一個 IP 位址：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-308">The FQDNs – sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com and sip3.pstnhub.microsoft.com – will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="7c5cd-309">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="7c5cd-309">52.114.148.0</span></span>
- <span data-ttu-id="7c5cd-310">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="7c5cd-310">52.114.132.46</span></span> 
- <span data-ttu-id="7c5cd-311">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="7c5cd-311">52.114.75.24</span></span> 
- <span data-ttu-id="7c5cd-312">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="7c5cd-312">52.114.76.76</span></span> 
- <span data-ttu-id="7c5cd-313">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="7c5cd-313">52.114.7.24</span></span> 
- <span data-ttu-id="7c5cd-314">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="7c5cd-314">52.114.14.70</span></span>
- <span data-ttu-id="7c5cd-315">52.114.16.74</span><span class="sxs-lookup"><span data-stu-id="7c5cd-315">52.114.16.74</span></span>
- <span data-ttu-id="7c5cd-316">52.114.20.29</span><span class="sxs-lookup"><span data-stu-id="7c5cd-316">52.114.20.29</span></span>

<span data-ttu-id="7c5cd-317">您必須在防火牆中開啟所有這些 IP 位址的埠，以允許傳入及傳出流量進出位址來傳送信號。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-317">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="7c5cd-318">如果您的防火牆支援 DNS 名稱，FQDN sip-all.pstnhub.microsoft.com 會解析為所有這些 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-318">If your firewall supports DNS names, the FQDN sip-all.pstnhub.microsoft.com resolves to all these IP addresses.</span></span> 


### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="7c5cd-319">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="7c5cd-319">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="7c5cd-320">直接路由的連接點是下列 FQDN：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-320">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="7c5cd-321">**sip.pstnhub.dod.teams.microsoft.us** –全域 FQDN。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-321">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="7c5cd-322">因為 Office 365 DoD 環境僅存在於美國資料中心，所以沒有次要和第三個 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-322">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="7c5cd-323">FQDN sip.pstnhub.dod.teams.microsoft.us 將解析成下列其中一個 IP 位址：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-323">The FQDN sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="7c5cd-324">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="7c5cd-324">52.127.64.33</span></span>
- <span data-ttu-id="7c5cd-325">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="7c5cd-325">52.127.68.34</span></span>

<span data-ttu-id="7c5cd-326">您必須在防火牆中開啟所有這些 IP 位址的埠，以允許傳入及傳出流量進出位址來傳送信號。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-326">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="7c5cd-327">Office 365 GCC 高環境</span><span class="sxs-lookup"><span data-stu-id="7c5cd-327">Office 365 GCC High environment</span></span>

<span data-ttu-id="7c5cd-328">直接路由的連接點是下列 FQDN：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-328">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="7c5cd-329">**sip.pstnhub.gov.teams.microsoft.us** –全域 FQDN。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-329">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="7c5cd-330">由於 GCC 的高環境僅存在於美國資料中心，因此沒有副及三元 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-330">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="7c5cd-331">FQDN sip.pstnhub.gov.teams.microsoft.us 將解析成下列其中一個 IP 位址：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-331">The FQDN sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="7c5cd-332">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="7c5cd-332">52.127.88.59</span></span>
- <span data-ttu-id="7c5cd-333">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="7c5cd-333">52.127.92.64</span></span>

<span data-ttu-id="7c5cd-334">您必須在防火牆中開啟所有這些 IP 位址的埠，以允許傳入及傳出流量進出位址來傳送信號。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-334">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>

## <a name="sip-signaling-ports"></a><span data-ttu-id="7c5cd-335">SIP 信號：埠</span><span class="sxs-lookup"><span data-stu-id="7c5cd-335">SIP Signaling: Ports</span></span>

<span data-ttu-id="7c5cd-336">您必須在提供直接路由的 Microsoft 365 或 Office 365 環境中使用下列埠：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-336">You must use the following ports for Microsoft 365 or Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="7c5cd-337">Microsoft 365 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="7c5cd-337">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="7c5cd-338">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="7c5cd-338">Office 365 GCC</span></span>
- <span data-ttu-id="7c5cd-339">Office 365 GCC 高</span><span class="sxs-lookup"><span data-stu-id="7c5cd-339">Office 365 GCC High</span></span>
- <span data-ttu-id="7c5cd-340">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="7c5cd-340">Office 365 DoD</span></span>

|<span data-ttu-id="7c5cd-341">頻寬</span><span class="sxs-lookup"><span data-stu-id="7c5cd-341">Traffic</span></span>|<span data-ttu-id="7c5cd-342">從</span><span class="sxs-lookup"><span data-stu-id="7c5cd-342">From</span></span>|<span data-ttu-id="7c5cd-343">自</span><span class="sxs-lookup"><span data-stu-id="7c5cd-343">To</span></span>|<span data-ttu-id="7c5cd-344">來源埠</span><span class="sxs-lookup"><span data-stu-id="7c5cd-344">Source port</span></span>|<span data-ttu-id="7c5cd-345">目的地埠</span><span class="sxs-lookup"><span data-stu-id="7c5cd-345">Destination port</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="7c5cd-346">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="7c5cd-346">SIP/TLS</span></span>|<span data-ttu-id="7c5cd-347">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="7c5cd-347">SIP Proxy</span></span>|<span data-ttu-id="7c5cd-348">SBC</span><span class="sxs-lookup"><span data-stu-id="7c5cd-348">SBC</span></span>|<span data-ttu-id="7c5cd-349">1024–65535</span><span class="sxs-lookup"><span data-stu-id="7c5cd-349">1024 – 65535</span></span>|<span data-ttu-id="7c5cd-350">在 SBC (上定義 Office 365 GCC 高/DoD 專用埠5061必須使用) </span><span class="sxs-lookup"><span data-stu-id="7c5cd-350">Defined on the SBC (For Office 365 GCC High/DoD only port 5061 must be used)</span></span>|
<span data-ttu-id="7c5cd-351">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="7c5cd-351">SIP/TLS</span></span>|<span data-ttu-id="7c5cd-352">SBC</span><span class="sxs-lookup"><span data-stu-id="7c5cd-352">SBC</span></span>|<span data-ttu-id="7c5cd-353">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="7c5cd-353">SIP Proxy</span></span>|<span data-ttu-id="7c5cd-354">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="7c5cd-354">Defined on the SBC</span></span>|<span data-ttu-id="7c5cd-355">5061</span><span class="sxs-lookup"><span data-stu-id="7c5cd-355">5061</span></span>|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a><span data-ttu-id="7c5cd-356">SIP 信號的容錯移轉機制</span><span class="sxs-lookup"><span data-stu-id="7c5cd-356">Failover mechanism for SIP Signaling</span></span>

<span data-ttu-id="7c5cd-357">SBC 會進行 DNS 查詢來解析 sip.pstnhub.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-357">The SBC makes a DNS query to resolve sip.pstnhub.microsoft.com.</span></span> <span data-ttu-id="7c5cd-358">根據 SBC 位置和資料中心效能指標，選取主要資料中心。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-358">Based on the SBC location and the datacenter performance metrics, the primary datacenter is selected.</span></span> <span data-ttu-id="7c5cd-359">如果主要資料中心遇到問題，SBC 將會嘗試可解析為第二個已指定資料中心的 sip2.pstnhub.microsoft.com，而且在兩個區域中的資料中心無法使用的情況下，SBC 會重試最後一個 FQDN (sip3.pstnhub.microsoft.com) ，提供第三個資料中心 IP。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-359">If the primary datacenter experiences an issue, the SBC will try the sip2.pstnhub.microsoft.com, which resolves to the second assigned datacenter, and, in the rare case that datacenters in two regions are not available, the SBC retries the last FQDN (sip3.pstnhub.microsoft.com), which provides the tertiary datacenter IP.</span></span>

<span data-ttu-id="7c5cd-360">下表摘要列出主要、次要及三元資料中心之間的關聯：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-360">The table below summarizes the relationships between primary, secondary, and tertiary datacenters:</span></span>

|<span data-ttu-id="7c5cd-361">如果主要資料中心是</span><span class="sxs-lookup"><span data-stu-id="7c5cd-361">If the primary datacenter is</span></span>|<span data-ttu-id="7c5cd-362">中東</span><span class="sxs-lookup"><span data-stu-id="7c5cd-362">EMEA</span></span>|<span data-ttu-id="7c5cd-363">NOAM</span><span class="sxs-lookup"><span data-stu-id="7c5cd-363">NOAM</span></span>|<span data-ttu-id="7c5cd-364">太</span><span class="sxs-lookup"><span data-stu-id="7c5cd-364">ASIA</span></span>|
|:--- |:--- |:--- |:--- |
|<span data-ttu-id="7c5cd-365">次要資料中心 (sip2.pstnhub.microsoft.com) </span><span class="sxs-lookup"><span data-stu-id="7c5cd-365">The secondary datacenter (sip2.pstnhub.microsoft.com)</span></span>|<span data-ttu-id="7c5cd-366">一下</span><span class="sxs-lookup"><span data-stu-id="7c5cd-366">US</span></span>|<span data-ttu-id="7c5cd-367">歐洲</span><span class="sxs-lookup"><span data-stu-id="7c5cd-367">EU</span></span>|<span data-ttu-id="7c5cd-368">一下</span><span class="sxs-lookup"><span data-stu-id="7c5cd-368">US</span></span>|
|<span data-ttu-id="7c5cd-369">第三個資料中心 (sip3.pstnhub.microsoft.com) </span><span class="sxs-lookup"><span data-stu-id="7c5cd-369">The tertiary datacenter (sip3.pstnhub.microsoft.com)</span></span>|<span data-ttu-id="7c5cd-370">太</span><span class="sxs-lookup"><span data-stu-id="7c5cd-370">ASIA</span></span>|<span data-ttu-id="7c5cd-371">太</span><span class="sxs-lookup"><span data-stu-id="7c5cd-371">ASIA</span></span>|<span data-ttu-id="7c5cd-372">歐洲</span><span class="sxs-lookup"><span data-stu-id="7c5cd-372">EU</span></span>|
|||||

## <a name="media-traffic-port-ranges"></a><span data-ttu-id="7c5cd-373">媒體流量：埠範圍</span><span class="sxs-lookup"><span data-stu-id="7c5cd-373">Media traffic: Port ranges</span></span>
<span data-ttu-id="7c5cd-374">請注意，如果您想要在不使用媒體的情況下部署直接路由，請套用下列需求。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-374">Note that the requirements below apply if you want to deploy Direct Routing without Media Bypass.</span></span> <span data-ttu-id="7c5cd-375">如需媒體旁路的防火牆需求，請參閱 [使用直接路由來規劃媒體旁路](https://docs.microsoft.com/microsoftteams/direct-routing-plan-media-bypass)。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-375">For firewall requirements for Media Bypass, please refer to [Plan for media bypass with Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-plan-media-bypass).</span></span>



<span data-ttu-id="7c5cd-376">媒體流量會流過 Microsoft 雲端中的個別服務。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-376">The media traffic flows to and from a separate service in the Microsoft Cloud.</span></span> <span data-ttu-id="7c5cd-377">媒體流量的 IP 位址範圍如下所示。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-377">The IP address ranges for Media traffic are as follows.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="7c5cd-378">Microsoft 365、Office 365 及 Office 365 GCC 環境</span><span class="sxs-lookup"><span data-stu-id="7c5cd-378">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="7c5cd-379">52.112.0.0/14 將 IP 位址從 52.112.0.1 (至 52.115.255.254) 。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-379">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254).</span></span>
- <span data-ttu-id="7c5cd-380">52.120.0.0/14 將 IP 位址從 52.120.0.1 (至 52.123.255.254) 。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-380">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254).</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="7c5cd-381">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="7c5cd-381">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="7c5cd-382">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="7c5cd-382">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="7c5cd-383">Office 365 GCC 高環境</span><span class="sxs-lookup"><span data-stu-id="7c5cd-383">Office 365 GCC High environment</span></span>

- <span data-ttu-id="7c5cd-384">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="7c5cd-384">52.127.88.0/21</span></span>

### <a name="port-range-applicable-to-all-environments"></a><span data-ttu-id="7c5cd-385">適用于所有環境的埠範圍 () </span><span class="sxs-lookup"><span data-stu-id="7c5cd-385">Port range (applicable to all environments)</span></span>
<span data-ttu-id="7c5cd-386">媒體處理器的埠範圍如下表所示：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-386">The port range of the Media Processors is shown in the following table:</span></span> 

|<span data-ttu-id="7c5cd-387">頻寬</span><span class="sxs-lookup"><span data-stu-id="7c5cd-387">Traffic</span></span>|<span data-ttu-id="7c5cd-388">從</span><span class="sxs-lookup"><span data-stu-id="7c5cd-388">From</span></span>|<span data-ttu-id="7c5cd-389">自</span><span class="sxs-lookup"><span data-stu-id="7c5cd-389">To</span></span>|<span data-ttu-id="7c5cd-390">來源埠</span><span class="sxs-lookup"><span data-stu-id="7c5cd-390">Source port</span></span>|<span data-ttu-id="7c5cd-391">目的地埠</span><span class="sxs-lookup"><span data-stu-id="7c5cd-391">Destination port</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="7c5cd-392">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="7c5cd-392">UDP/SRTP</span></span>|<span data-ttu-id="7c5cd-393">媒體處理器</span><span class="sxs-lookup"><span data-stu-id="7c5cd-393">Media Processor</span></span>|<span data-ttu-id="7c5cd-394">SBC</span><span class="sxs-lookup"><span data-stu-id="7c5cd-394">SBC</span></span>|<span data-ttu-id="7c5cd-395">3478-3481 與49152–53247</span><span class="sxs-lookup"><span data-stu-id="7c5cd-395">3478-3481 and 49152 – 53247</span></span>|<span data-ttu-id="7c5cd-396">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="7c5cd-396">Defined on the SBC</span></span>|
|<span data-ttu-id="7c5cd-397">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="7c5cd-397">UDP/SRTP</span></span>|<span data-ttu-id="7c5cd-398">SBC</span><span class="sxs-lookup"><span data-stu-id="7c5cd-398">SBC</span></span>|<span data-ttu-id="7c5cd-399">媒體處理器</span><span class="sxs-lookup"><span data-stu-id="7c5cd-399">Media Processor</span></span>|<span data-ttu-id="7c5cd-400">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="7c5cd-400">Defined on the SBC</span></span>|<span data-ttu-id="7c5cd-401">3478-3481 與49152–53247</span><span class="sxs-lookup"><span data-stu-id="7c5cd-401">3478-3481 and 49152 – 53247</span></span>|

  > [!NOTE]
  > <span data-ttu-id="7c5cd-402">Microsoft 建議在 SBC 上每個併發呼叫至少有兩個埠。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-402">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span>


## <a name="media-traffic-media-processors-geography"></a><span data-ttu-id="7c5cd-403">媒體流量：媒體處理器地理位置</span><span class="sxs-lookup"><span data-stu-id="7c5cd-403">Media traffic: Media processors geography</span></span>

<span data-ttu-id="7c5cd-404">媒體流量透過稱為媒體處理器的元件來流動。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-404">The media traffic flows via components called media processors.</span></span> <span data-ttu-id="7c5cd-405">媒體處理器與 SIP proxy 放在同一個資料中心。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-405">Media processors are placed in the same datacenters as SIP proxies.</span></span> <span data-ttu-id="7c5cd-406">此外，還有其他媒體處理器可優化媒體流程。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-406">Also, there are additional media processors to optimize media flow.</span></span> <span data-ttu-id="7c5cd-407">例如，我們目前在澳大利亞沒有 SIP proxy 元件， (從新加坡或香港) 的 SIP 流程，但我們已在澳大利亞本機提供媒體處理器。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-407">For example, we do not have a SIP proxy component now in Australia (SIP flows via Singapore or Hong Kong) but we do have the media processor locally in Australia.</span></span> <span data-ttu-id="7c5cd-408">在本機提供媒體處理器的需求是由我們透過傳送流量（例如從澳大利亞到新加坡或香港）來取得的延隔時間來決定。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-408">The need for the media processors locally is dictated by the latency which we experience by sending traffic long-distance, for example from Australia to Singapore or Hong Kong.</span></span> <span data-ttu-id="7c5cd-409">雖然從澳大利亞到香港或新加坡的流量範例中的延遲，仍可保持良好的 SIP 流量通話品質，而不需要進行即時媒體流量。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-409">While latency in the example of traffic flowing from Australia to Hong Kong or Singapore is acceptable to preserve good call quality for SIP traffic, for real-time media traffic it is not.</span></span>

<span data-ttu-id="7c5cd-410">媒體處理器的位置：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-410">Location of the media processors:</span></span>

<span data-ttu-id="7c5cd-411">已部署 SIP proxy 和媒體處理器元件的位置：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-411">Locations where both SIP proxy and media processor components deployed:</span></span>
- <span data-ttu-id="7c5cd-412">我們 (美國西部和美國東資料中心的兩個) </span><span class="sxs-lookup"><span data-stu-id="7c5cd-412">US (two in US West and US East datacenters)</span></span>
- <span data-ttu-id="7c5cd-413">歐洲 (阿姆斯特丹與都柏林資料中心) </span><span class="sxs-lookup"><span data-stu-id="7c5cd-413">Europe (Amsterdam and Dublin datacenters)</span></span>
- <span data-ttu-id="7c5cd-414">亞太地區 (新加坡與香港資料中心) </span><span class="sxs-lookup"><span data-stu-id="7c5cd-414">Asia (Singapore and Hong Kong datacenters)</span></span>

<span data-ttu-id="7c5cd-415">透過上方所列的最接近資料中心 (SIP 流程部署媒體處理器的位置) ：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-415">Locations where only media processors are deployed (SIP flows via the closest datacenter listed above):</span></span>
- <span data-ttu-id="7c5cd-416">日本 (JP 東和西部資料中心) </span><span class="sxs-lookup"><span data-stu-id="7c5cd-416">Japan (JP East and West datacenters)</span></span>
- <span data-ttu-id="7c5cd-417">澳大利亞 (AU 東和東南部資料中心) </span><span class="sxs-lookup"><span data-stu-id="7c5cd-417">Australia (AU East and Southeast datacenters)</span></span>




## <a name="media-traffic-codecs"></a><span data-ttu-id="7c5cd-418">媒體流量：編解碼器</span><span class="sxs-lookup"><span data-stu-id="7c5cd-418">Media traffic: Codecs</span></span>

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a><span data-ttu-id="7c5cd-419">在 SBC 與雲端媒體處理器或 Microsoft 團隊用戶端之間的腿。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-419">Leg between SBC and Cloud Media Processor or Microsoft Teams client.</span></span>
<span data-ttu-id="7c5cd-420">適用于媒體旁路大小寫和非旁路情況。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-420">Applies to both media bypass case and non-bypass cases.</span></span>

<span data-ttu-id="7c5cd-421">[會話邊界控制器] 與 [雲端媒體處理器] 之間的直向路由介面 (沒有媒體旁路) 或團隊用戶端與 SBC (（如果已啟用媒體旁路) ）可以使用下列的編解碼器：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-421">The Direct Routing interface on the leg between the Session Border Controller and Cloud Media Processor (without media bypass) or between the Teams client and the SBC (if Media Bypass enabled) can use the following codecs:</span></span>

- <span data-ttu-id="7c5cd-422">非媒體旁路 (SBC 到雲端媒體處理器) ：絲、711、729、722、G</span><span class="sxs-lookup"><span data-stu-id="7c5cd-422">Non-Media bypass (SBC to Cloud Media Processor): SILK, G.711, G.722, G.729</span></span>
- <span data-ttu-id="7c5cd-423">媒體旁路 (SBC 至團隊用戶端) ：711、722、729</span><span class="sxs-lookup"><span data-stu-id="7c5cd-423">Media Bypass (SBC to Teams client):  SILK, G.711, G.722, G.729</span></span>

<span data-ttu-id="7c5cd-424">您可以從優惠中排除不想要的編解碼器，以強制在會話邊界控制器上使用特定的編解碼器。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-424">You can force use of the specific codec on the Session Border Controller by excluding undesirable codecs from the offer.</span></span>

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a><span data-ttu-id="7c5cd-425">Microsoft 團隊用戶端與雲端媒體處理器之間的腿</span><span class="sxs-lookup"><span data-stu-id="7c5cd-425">Leg between Microsoft Teams Client and Cloud Media Processor</span></span>
<span data-ttu-id="7c5cd-426">僅適用于非媒體旁路大小寫。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-426">Applies to non-media bypass case only.</span></span> <span data-ttu-id="7c5cd-427">在媒體旁路的情況下，媒體會直接在團隊用戶端和 SBC 之間流動。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-427">With Media Bypass, the media flows directly between the Teams client and the SBC.</span></span>

<span data-ttu-id="7c5cd-428">在雲端媒體處理器與 Microsoft 團隊用戶端之間的腿上，使用的是絞絲或722。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-428">On the leg between the Cloud Media Processor and Microsoft Teams client either SILK or G.722 is used.</span></span> <span data-ttu-id="7c5cd-429">這個腿的編解碼器選擇是以 Microsoft 演算法為基礎，考慮了多個參數。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-429">The codec choice on this leg is based on Microsoft algorithms, which take into consideration multiple parameters.</span></span> 


## <a name="supported-session-border-controllers-sbcs"></a><span data-ttu-id="7c5cd-430">支援的會話邊界控制器 (SBCs) </span><span class="sxs-lookup"><span data-stu-id="7c5cd-430">Supported Session Border Controllers (SBCs)</span></span>

<span data-ttu-id="7c5cd-431">Microsoft 只支援驗證的 SBCs 與直接路由配對。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-431">Microsoft only supports certified SBCs to pair with Direct Routing.</span></span> <span data-ttu-id="7c5cd-432">因為企業語音對企業而言是很重要的，Microsoft 會以所選的 SBCs 來執行大量測試，並與 SBC 廠商搭配使用，以確保兩個系統相容。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-432">Because Enterprise Voice is critical for businesses, Microsoft runs intensive tests with the selected SBCs, and works with the SBC vendors to ensure the two systems are compatible.</span></span> 

<span data-ttu-id="7c5cd-433">已驗證的裝置會列為 [團隊直接路由] 的 [認證者]。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-433">Devices that have been validated are listed as Certified for Teams Direct Routing.</span></span> <span data-ttu-id="7c5cd-434">認證的裝置在所有情況下都能保證正常運作。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-434">The certified devices are guaranteed to work in all scenarios.</span></span> 

<span data-ttu-id="7c5cd-435">如需支援的 SBCs 的詳細資訊，請參閱 [認證以直接路由的會話邊界控制器清單](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-435">For more information about supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

 
## <a name="see-also"></a><span data-ttu-id="7c5cd-436">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7c5cd-436">See also</span></span>

[<span data-ttu-id="7c5cd-437">設定直接路由</span><span class="sxs-lookup"><span data-stu-id="7c5cd-437">Configure Direct Routing</span></span>](direct-routing-configure.md)
