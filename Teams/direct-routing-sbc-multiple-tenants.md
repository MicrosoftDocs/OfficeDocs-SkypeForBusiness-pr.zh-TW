---
title: 設定會話邊界控制器-多重承租人
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 瞭解如何設定一個會話邊界控制器（SBC）來為 Microsoft 合作夥伴和/或 PSTN 運營商提供多個租使用者。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 883df3c78387d509f094f91bc346fc5b31f53690
ms.sourcegitcommit: 0835f4335ebc8ca53b8348e0b1b906828eb4e13e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2020
ms.locfileid: "43918712"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a><span data-ttu-id="cacbb-103">設定多個租用戶的工作階段邊界控制器</span><span class="sxs-lookup"><span data-stu-id="cacbb-103">Configure a Session Border Controller for multiple tenants</span></span>

<span data-ttu-id="cacbb-104">直接路由支援設定一個會話邊界控制器（SBC）來提供多個租使用者。</span><span class="sxs-lookup"><span data-stu-id="cacbb-104">Direct Routing supports configuring one Session Border Controller (SBC) to serve multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="cacbb-105">這個案例是針對 Microsoft 合作夥伴和/或 PSTN 運營商所設計，在本檔的稍後部分稱為運營商。</span><span class="sxs-lookup"><span data-stu-id="cacbb-105">This scenario is designed for Microsoft partners and/or PSTN carriers, referred to as carriers later in this document.</span></span> <span data-ttu-id="cacbb-106">運營商將提供給 Microsoft 團隊的電話語音出售給客戶。</span><span class="sxs-lookup"><span data-stu-id="cacbb-106">A carrier sells telephony services delivered to Microsoft Teams to their customers.</span></span> 

<span data-ttu-id="cacbb-107">運營商：</span><span class="sxs-lookup"><span data-stu-id="cacbb-107">A carrier:</span></span>
- <span data-ttu-id="cacbb-108">在其資料中心中部署和管理 SBC （客戶不需要實施 SBC，而且會從團隊用戶端的載波接收電話語音）。</span><span class="sxs-lookup"><span data-stu-id="cacbb-108">Deploys and manages an SBC in their datacenter (customers do not need to implement an SBC, and they receive telephony services from the carrier in the Teams client).</span></span>
- <span data-ttu-id="cacbb-109">將 SBC 互連至多個租使用者。</span><span class="sxs-lookup"><span data-stu-id="cacbb-109">Interconnects the SBC to multiple tenants.</span></span>
- <span data-ttu-id="cacbb-110">提供 PSTN 服務給客戶。</span><span class="sxs-lookup"><span data-stu-id="cacbb-110">Provides PSTN services to customers.</span></span>
- <span data-ttu-id="cacbb-111">管理 [通話品質結束]。</span><span class="sxs-lookup"><span data-stu-id="cacbb-111">Manages call quality end to end.</span></span>
- <span data-ttu-id="cacbb-112">針對 PSTN 服務分別收取費用。</span><span class="sxs-lookup"><span data-stu-id="cacbb-112">Charges separately for PSTN services.</span></span>

<span data-ttu-id="cacbb-113">Microsoft 不會管理運營商。</span><span class="sxs-lookup"><span data-stu-id="cacbb-113">Microsoft does not manage carriers.</span></span> <span data-ttu-id="cacbb-114">Microsoft 提供 PBX （Microsoft 手機系統）與團隊用戶端。</span><span class="sxs-lookup"><span data-stu-id="cacbb-114">Microsoft offers a PBX (Microsoft Phone System) and a Teams client.</span></span> <span data-ttu-id="cacbb-115">Microsoft 也會認證手機，並證實可搭配 Microsoft Phone 系統使用的 SBCs。</span><span class="sxs-lookup"><span data-stu-id="cacbb-115">Microsoft also certifies phones, and certifies SBCs that can be used with the Microsoft Phone System.</span></span> <span data-ttu-id="cacbb-116">選擇運營商前，請確定您的選擇有認證的 SBC，且可管理語音品質端到端。</span><span class="sxs-lookup"><span data-stu-id="cacbb-116">Before choosing a carrier, please ensure that your choice has a certified SBC and can manage voice quality end to end.</span></span>

<span data-ttu-id="cacbb-117">以下是設定案例的技術實施步驟。</span><span class="sxs-lookup"><span data-stu-id="cacbb-117">The following are the technical implementation steps to configure the scenario.</span></span>

<span data-ttu-id="cacbb-118">**僅限運營商：**</span><span class="sxs-lookup"><span data-stu-id="cacbb-118">**Carrier only:**</span></span>
1. <span data-ttu-id="cacbb-119">根據[認證的 sbc 廠商指示](#deploy-and-configure-the-sbc)，部署 SBC 並針對主機案例進行設定。</span><span class="sxs-lookup"><span data-stu-id="cacbb-119">Deploy the SBC and configure it for the hosting scenario according to the [instructions from the certified SBC vendors](#deploy-and-configure-the-sbc).</span></span>
2. <span data-ttu-id="cacbb-120">在電信公司租使用者中註冊基礎功能變數名稱，並要求萬用字元憑證。</span><span class="sxs-lookup"><span data-stu-id="cacbb-120">Register a base domain name in the carrier tenant and request a wildcard certificate.</span></span>
3. <span data-ttu-id="cacbb-121">針對每個客戶註冊子域，這是基本網域的一部分。</span><span class="sxs-lookup"><span data-stu-id="cacbb-121">Register a subdomain for every customer, which is part of the base domain.</span></span>

<span data-ttu-id="cacbb-122">**有客戶全域系統管理員的電信公司：**</span><span class="sxs-lookup"><span data-stu-id="cacbb-122">**Carrier with a Customer Global Administrator:**</span></span>
1. <span data-ttu-id="cacbb-123">將子功能變數名稱稱新增至客戶租使用者。</span><span class="sxs-lookup"><span data-stu-id="cacbb-123">Add the subdomain name to the customer tenant.</span></span>
2. <span data-ttu-id="cacbb-124">啟用 [子功能變數名稱]。</span><span class="sxs-lookup"><span data-stu-id="cacbb-124">Activate the subdomain name.</span></span>
3. <span data-ttu-id="cacbb-125">將載波的主幹設定為客戶租使用者並提供使用者。</span><span class="sxs-lookup"><span data-stu-id="cacbb-125">Configure the trunk from the carrier to the customer tenant and provision users.</span></span>

<span data-ttu-id="cacbb-126">*請務必瞭解 DNS 的基本概念，以及功能變數名稱在 Office 365 中的管理方式。繼續進行之前，請先參閱[取得 Office 365 網域的](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)說明。*</span><span class="sxs-lookup"><span data-stu-id="cacbb-126">*Please make sure you understand DNS basics and how the domain name is managed in Office 365. Review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) before proceeding further.*</span></span>

## <a name="deploy-and-configure-the-sbc"></a><span data-ttu-id="cacbb-127">部署並設定 SBC</span><span class="sxs-lookup"><span data-stu-id="cacbb-127">Deploy and configure the SBC</span></span>

<span data-ttu-id="cacbb-128">如需如何針對 SBC 主機案例部署和設定 SBCs 的詳細步驟，請參閱 SBC 供應商的檔。</span><span class="sxs-lookup"><span data-stu-id="cacbb-128">For the detailed steps on how to deploy and configure SBCs for an SBC hosting scenario, please refer to the SBC vendor's documentation.</span></span>

- <span data-ttu-id="cacbb-129">**AudioCodes：** [直接路由設定筆記](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)，在「將 AudioCodes SBC 連線至 Microsoft 團隊直接路由託管模型配置記事」中所述的 SBC 主機案例設定。</span><span class="sxs-lookup"><span data-stu-id="cacbb-129">**AudioCodes:** [Direct Routing Configuration notes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), the configuration of the SBC hosting scenario described in "Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note."</span></span> 
- <span data-ttu-id="cacbb-130">**Oracle：** [直接路由設定筆記](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)，在「Microsoft」一節中將說明 SBC 主機案例的設定。</span><span class="sxs-lookup"><span data-stu-id="cacbb-130">**Oracle:** [Direct Routing Configuration notes](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html), the configuration of the SBC hosting scenario is described in the "Microsoft" section.</span></span> 
- <span data-ttu-id="cacbb-131">**功能區通訊：** 請參閱[功能區通訊 SBC 核心 Microsoft 團隊配置指南](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe)，瞭解如何設定功能區核心數列的 SBCs 與此頁面[功能區最佳做法-為 Microsoft 團隊直接路由 SBC 邊緣配置電信公司](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)</span><span class="sxs-lookup"><span data-stu-id="cacbb-131">**Ribbon Communications:**  Please refer to the [Ribbon Communications SBC Core Microsoft Teams Configuration Guide](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) for documentation on how to configure Ribbon Core Series SBCs and to this page [Ribbon Best Practice - Configuring Carriers for Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)</span></span>
- <span data-ttu-id="cacbb-132">**TE-系統（anynode）：** 請在[TE 系統社區頁面](https://community.te-systems.de/)上登錄，以取得有關如何針對多個租使用者設定 anynode SBC 的檔和範例。</span><span class="sxs-lookup"><span data-stu-id="cacbb-132">**TE-Systems (anynode):**  Please register on the [TE-Systems Community page](https://community.te-systems.de/) for documentation and examples on how to configure anynode SBC for multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="cacbb-133">請務必注意如何設定「連絡人」標題。</span><span class="sxs-lookup"><span data-stu-id="cacbb-133">Please pay attention to how to configure the "Contact" header.</span></span> <span data-ttu-id="cacbb-134">連絡人標題是用來在傳入邀請訊息上尋找客戶租使用者。</span><span class="sxs-lookup"><span data-stu-id="cacbb-134">The Contact header is used to find the customer tenant on the incoming invite message.</span></span> 

## <a name="register-a-base-domain-and-subdomains"></a><span data-ttu-id="cacbb-135">註冊基底網域和子域</span><span class="sxs-lookup"><span data-stu-id="cacbb-135">Register a base domain and subdomains</span></span>

<span data-ttu-id="cacbb-136">針對託管案例，您需要建立：</span><span class="sxs-lookup"><span data-stu-id="cacbb-136">For the hosting scenario, you need to create:</span></span>
- <span data-ttu-id="cacbb-137">載波所擁有的一個基底網功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="cacbb-137">One base domain name owned by the carrier.</span></span>
- <span data-ttu-id="cacbb-138">在每個客戶租使用者中，屬於基礎網功能變數名稱稱的子域。</span><span class="sxs-lookup"><span data-stu-id="cacbb-138">A subdomain that is part of the base domain name in every customer tenant.</span></span>

<span data-ttu-id="cacbb-139">在下列範例中：</span><span class="sxs-lookup"><span data-stu-id="cacbb-139">In the following example:</span></span>
- <span data-ttu-id="cacbb-140">Adatum 是一種提供網際網路和電話語音的運營商，可為多個客戶提供服務。</span><span class="sxs-lookup"><span data-stu-id="cacbb-140">Adatum is a carrier that serves several customers by providing Internet and telephony services.</span></span>
- <span data-ttu-id="cacbb-141">Woodgrove 銀行、Contoso 和艾德公司都是三個擁有 Office 365 網域的客戶，但卻從 Adatum 接收電話語音。</span><span class="sxs-lookup"><span data-stu-id="cacbb-141">Woodgrove Bank, Contoso, and Adventure Works are three customers that have Office 365 domains but receive the telephony services from Adatum.</span></span>

<span data-ttu-id="cacbb-142">在將邀請傳送給 Office 365 時，子域**必須**符合將針對客戶設定的主幹的 FQDN 名稱和連絡人標題中的 fqdn。</span><span class="sxs-lookup"><span data-stu-id="cacbb-142">Subdomains **MUST** match the FQDN name of the trunk that will be configured for the customer and the FQDN in the Contact header when sending the Invite to Office 365.</span></span> 

<span data-ttu-id="cacbb-143">當來電到達 Office 365 Direct 路由介面時，介面會使用連絡人標題尋找使用者應該在其中進行查閱的租使用者。</span><span class="sxs-lookup"><span data-stu-id="cacbb-143">When a call arrives at the Office 365 Direct Routing interface, the interface uses the Contact header to find the tenant where the user should be looked up.</span></span> <span data-ttu-id="cacbb-144">[直接傳送] 不會在邀請中使用電話號碼查閱，因為有些客戶可能有不需要在數個租使用者中重迭的號碼。</span><span class="sxs-lookup"><span data-stu-id="cacbb-144">Direct Routing does not use phone number lookup on the Invite, as some customers might have non-DID numbers that can overlap in several tenants.</span></span> <span data-ttu-id="cacbb-145">因此，連絡人標頭中的 FQDN 名稱是必要的，以識別確切的租使用者，以便透過電話號碼查閱使用者。</span><span class="sxs-lookup"><span data-stu-id="cacbb-145">Therefore, the FQDN name in the Contact header is required to identify the exact tenant to look up the user by the phone number.</span></span>

<span data-ttu-id="cacbb-146">*如需在 Office 365 組織中建立功能變數名稱的詳細資訊，請參閱[取得 office 365 網域](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)的說明。*</span><span class="sxs-lookup"><span data-stu-id="cacbb-146">*Please review  [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about creating domain names in Office 365 organizations.*</span></span>

<span data-ttu-id="cacbb-147">下圖摘要說明基本網域、子域和連絡人標頭的需求。</span><span class="sxs-lookup"><span data-stu-id="cacbb-147">The following diagram summarizes the requirements to base domain, subdomains, and Contact header.</span></span>

![顯示網域和連絡人標題需求的圖表](media/direct-routing-1-sbc-requirements.png)

<span data-ttu-id="cacbb-149">SBC 需要認證，才能驗證連線。</span><span class="sxs-lookup"><span data-stu-id="cacbb-149">The SBC requires a certificate to authenticate the connections.</span></span> <span data-ttu-id="cacbb-150">針對 SBC 主機案例，電信公司需要使用\* \*base_domain （例如\*customers.adatum.biz）\* 要求證書。</span><span class="sxs-lookup"><span data-stu-id="cacbb-150">For the SBC hosting scenario, the carrier needs to request a certificate with SAN *\*.base_domain (for example, \*.customers.adatum.biz)*.</span></span> <span data-ttu-id="cacbb-151">這個憑證可以用來驗證從單一 SBC 提供的多個租使用者的連線。</span><span class="sxs-lookup"><span data-stu-id="cacbb-151">This certificate can be used to authenticate connections to multiple tenants served from a single SBC.</span></span>


<span data-ttu-id="cacbb-152">下表是一個配置的範例。</span><span class="sxs-lookup"><span data-stu-id="cacbb-152">The following table is an example of one configuration.</span></span>


|<span data-ttu-id="cacbb-153">新的功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="cacbb-153">New domain name</span></span> |<span data-ttu-id="cacbb-154">類型</span><span class="sxs-lookup"><span data-stu-id="cacbb-154">Type</span></span>|<span data-ttu-id="cacbb-155">已</span><span class="sxs-lookup"><span data-stu-id="cacbb-155">Registered</span></span>  |<span data-ttu-id="cacbb-156">SBC 的憑證 SAN</span><span class="sxs-lookup"><span data-stu-id="cacbb-156">Certificate SAN for SBC</span></span>  |<span data-ttu-id="cacbb-157">範例中的租使用者預設網域</span><span class="sxs-lookup"><span data-stu-id="cacbb-157">Tenant default domain in the example</span></span>  |<span data-ttu-id="cacbb-158">在傳送來電給使用者時，SBC 必須在連絡人標題中出現的 FQDN 名稱</span><span class="sxs-lookup"><span data-stu-id="cacbb-158">FQDN name that SBC must present in the Contact header when sending calls to users</span></span>|
|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="cacbb-159">customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="cacbb-159">customers.adatum.biz</span></span>|    <span data-ttu-id="cacbb-160">基本</span><span class="sxs-lookup"><span data-stu-id="cacbb-160">Base</span></span>     |     <span data-ttu-id="cacbb-161">在承運人租使用者</span><span class="sxs-lookup"><span data-stu-id="cacbb-161">In carrier tenant</span></span>  |    <span data-ttu-id="cacbb-162">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="cacbb-162">\*.customers.adatum.biz</span></span>  |   <span data-ttu-id="cacbb-163">adatum.biz</span><span class="sxs-lookup"><span data-stu-id="cacbb-163">adatum.biz</span></span>      |<span data-ttu-id="cacbb-164">NA，這是服務租使用者，不含使用者</span><span class="sxs-lookup"><span data-stu-id="cacbb-164">NA, this is a service tenant, no users</span></span> |
|<span data-ttu-id="cacbb-165">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="cacbb-165">sbc1.customers.adatum.biz</span></span>|    <span data-ttu-id="cacbb-166">功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="cacbb-166">Subdomain</span></span>  |    <span data-ttu-id="cacbb-167">在客戶租使用者</span><span class="sxs-lookup"><span data-stu-id="cacbb-167">In a customer tenant</span></span>  |    <span data-ttu-id="cacbb-168">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="cacbb-168">\*.customers.adatum.biz</span></span>  | <span data-ttu-id="cacbb-169">woodgrovebank.us</span><span class="sxs-lookup"><span data-stu-id="cacbb-169">woodgrovebank.us</span></span>  |  <span data-ttu-id="cacbb-170">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="cacbb-170">sbc1.customers.adatum.biz</span></span>|
|<span data-ttu-id="cacbb-171">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="cacbb-171">sbc2.customers.adatum.biz</span></span>  |   <span data-ttu-id="cacbb-172">功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="cacbb-172">Subdomain</span></span> | <span data-ttu-id="cacbb-173">在客戶租使用者</span><span class="sxs-lookup"><span data-stu-id="cacbb-173">In a customer tenant</span></span>   |   <span data-ttu-id="cacbb-174">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="cacbb-174">\*.customers.adatum.biz</span></span>   |<span data-ttu-id="cacbb-175">contoso.com</span><span class="sxs-lookup"><span data-stu-id="cacbb-175">contoso.com</span></span>   |<span data-ttu-id="cacbb-176">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="cacbb-176">sbc2.customers.adatum.biz</span></span> |
|<span data-ttu-id="cacbb-177">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="cacbb-177">sbc3.customers.adatum.biz</span></span> |   <span data-ttu-id="cacbb-178">功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="cacbb-178">Subdomain</span></span> | <span data-ttu-id="cacbb-179">在客戶租使用者</span><span class="sxs-lookup"><span data-stu-id="cacbb-179">In a customer tenant</span></span> |   <span data-ttu-id="cacbb-180">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="cacbb-180">\*.customers.adatum.biz</span></span>  |  <span data-ttu-id="cacbb-181">adventureworks.com</span><span class="sxs-lookup"><span data-stu-id="cacbb-181">adventureworks.com</span></span> | <span data-ttu-id="cacbb-182">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="cacbb-182">sbc3.customers.adatum.biz</span></span> |
||         |         |         |         |         |

<span data-ttu-id="cacbb-183">若要設定基與子域，請依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="cacbb-183">To configure the base and subdomains, please follow the steps described below.</span></span> <span data-ttu-id="cacbb-184">在這個範例中，我們將為一個客戶（Woodgrove 銀行租使用者的 sbc1.customers.adatum.biz）設定基礎網功能變數名稱稱（customers.adatum.biz）和子域。</span><span class="sxs-lookup"><span data-stu-id="cacbb-184">In the example, we will configure a base domain name (customers.adatum.biz) and a subdomain for one customer (sbc1.customers.adatum.biz in Woodgrove Bank tenant).</span></span>

> [!NOTE]
> <span data-ttu-id="cacbb-185">使用 sbcX.customers.adatum.biz 在承運人租使用者中啟用語音。</span><span class="sxs-lookup"><span data-stu-id="cacbb-185">Use sbcX.customers.adatum.biz to enable voice in the carrier tenant.</span></span>

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a><span data-ttu-id="cacbb-186">在電信公司租使用者中註冊基底網功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="cacbb-186">Register a base domain name in the carrier tenant</span></span>

<span data-ttu-id="cacbb-187">**這些動作會在承運人租使用者中執行。**</span><span class="sxs-lookup"><span data-stu-id="cacbb-187">**These actions are performed in the carrier tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a><span data-ttu-id="cacbb-188">確定您在承運人租使用者中擁有適當的許可權</span><span class="sxs-lookup"><span data-stu-id="cacbb-188">Ensure that you have appropriate rights in the carrier tenant</span></span>

<span data-ttu-id="cacbb-189">如果您是以全域系統管理員身分登入 Microsoft 365 系統管理中心，您就只能新增網域。</span><span class="sxs-lookup"><span data-stu-id="cacbb-189">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="cacbb-190">若要驗證您擁有的角色，請登入 Microsoft 365https://portal.office.com)系統管理中心（請移至 [**使用者** > 作用中的**使用者**]，然後確認您擁有全域系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="cacbb-190">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="cacbb-191">如需管理員角色以及如何在 Office 365 中指派角色的詳細資訊，請參閱[關於 office 365 系統管理員角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。</span><span class="sxs-lookup"><span data-stu-id="cacbb-191">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a><span data-ttu-id="cacbb-192">新增基底網域至租使用者並驗證</span><span class="sxs-lookup"><span data-stu-id="cacbb-192">Add a base domain to the tenant and verify it</span></span>

1. <span data-ttu-id="cacbb-193">在 Microsoft 365 系統管理中心中，移至**設定** > **網域** > [**新增網域**]。</span><span class="sxs-lookup"><span data-stu-id="cacbb-193">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="cacbb-194">在 [**輸入您擁有的網域**] 方塊中，輸入基底網域的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="cacbb-194">In the **Enter a domain you own** box, type the FQDN of the base domain.</span></span> <span data-ttu-id="cacbb-195">在下列範例中，基底網域是*customers.adatum.biz*。</span><span class="sxs-lookup"><span data-stu-id="cacbb-195">In the following example, the base domain is *customers.adatum.biz*.</span></span>

    ![顯示 [新增網域] 頁面的螢幕擷取畫面](media/direct-routing-2-sbc-add-domain.png)

3. <span data-ttu-id="cacbb-197">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cacbb-197">Click **Next**.</span></span>
4. <span data-ttu-id="cacbb-198">在這個範例中，租使用者已將 adatum.biz 做為已驗證的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="cacbb-198">In the example, the tenant already has adatum.biz as a verified domain name.</span></span> <span data-ttu-id="cacbb-199">因為 customers.adatum.biz 是已註冊名稱的子域，所以此嚮導不會要求您額外驗證。</span><span class="sxs-lookup"><span data-stu-id="cacbb-199">The wizard will not ask for additional verification because customers.adatum.biz is a subdomain for the already registered name.</span></span> <span data-ttu-id="cacbb-200">不過，如果您在之前新增一個尚未驗證的 FQDN，您將需要完成驗證程式。</span><span class="sxs-lookup"><span data-stu-id="cacbb-200">However, if you add an FQDN that has not been verified before, you will need to go through the process of verification.</span></span> <span data-ttu-id="cacbb-201">驗證的程式[如下所述](#add-a-subdomain-to-the-customer-tenant-and-verify-it)。</span><span class="sxs-lookup"><span data-stu-id="cacbb-201">The process of verification is [described below](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span></span>

    ![螢幕擷取畫面顯示已驗證的功能變數名稱確認](media/direct-routing-3-sbc-verify-domain.png)

5. <span data-ttu-id="cacbb-203">按一下 **[下一步]**，然後在 [**更新 DNS 設定**] 頁面上，選取 [**我將自行新增 DNS 記錄**]，然後按 **[下一步**</span><span class="sxs-lookup"><span data-stu-id="cacbb-203">Click **Next**, and on the **Update DNS Settings** page, select **I'll add the DNS records myself** and click **Next**.</span></span>
6. <span data-ttu-id="cacbb-204">在下一頁上，清除所有值（除非您想要將功能變數名稱用於 Exchange、SharePoint 或團隊/商務用 Skype），請按 **[下一步**]，然後按一下 **[完成**]。</span><span class="sxs-lookup"><span data-stu-id="cacbb-204">On the next page, clear all values (unless you want to use the domain name for Exchange, SharePoint, or Teams/Skype for Business), click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="cacbb-205">請確定您的新網域處於 [設定完成] 狀態。</span><span class="sxs-lookup"><span data-stu-id="cacbb-205">Make sure your new domain is in the Setup complete status.</span></span>

    ![顯示已完成 [設定] 狀態之網域的螢幕擷取畫面](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a><span data-ttu-id="cacbb-207">啟動功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="cacbb-207">Activate the domain name</span></span>

<span data-ttu-id="cacbb-208">在您註冊功能變數名稱之後，您必須加入至少一個 E1、E3 或 E5 授權的使用者，並將 SIP 位址指定為與建立的基礎網域相符的 SIP 位址的 FQDN 部分來啟動。</span><span class="sxs-lookup"><span data-stu-id="cacbb-208">After you have registered a domain name, you need to activate it by adding at least one E1, E3, or E5 licensed user and assigning a SIP address with the FQDN portion of the SIP address matching the created base domain.</span></span> 

<span data-ttu-id="cacbb-209">*如需在 Office 365 組織中新增使用者的詳細資訊，請參閱[取得 office 365 網域的協助](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)。*</span><span class="sxs-lookup"><span data-stu-id="cacbb-209">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 organizations.*</span></span>

<span data-ttu-id="cacbb-210">例如： test@customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="cacbb-210">For example: test@customers.adatum.biz</span></span>

![[基本網域啟用] 頁面的螢幕擷取畫面](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a><span data-ttu-id="cacbb-212">在客戶租使用者中註冊子功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="cacbb-212">Register a subdomain name in a customer tenant</span></span>

<span data-ttu-id="cacbb-213">您將需要為每個客戶建立唯一的子功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="cacbb-213">You will need to create a unique subdomain name for every customer.</span></span> <span data-ttu-id="cacbb-214">在這個範例中，我們將會在租使用者中使用預設功能變數名稱 woodgrovebank.us 建立子域 sbc1.customers.adatum.biz。</span><span class="sxs-lookup"><span data-stu-id="cacbb-214">In this example, we will create a subdomain sbc1.customers.adatum.biz in a tenant with the default domain name woodgrovebank.us.</span></span>

<span data-ttu-id="cacbb-215">**下列所有行動都屬於客戶租使用者。**</span><span class="sxs-lookup"><span data-stu-id="cacbb-215">**All actions below are in the customer tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a><span data-ttu-id="cacbb-216">確定您在客戶租使用者中擁有適當的許可權</span><span class="sxs-lookup"><span data-stu-id="cacbb-216">Ensure that you have appropriate rights in the customer tenant</span></span>

<span data-ttu-id="cacbb-217">如果您是以全域系統管理員身分登入 Microsoft 365 系統管理中心，您就只能新增網域。</span><span class="sxs-lookup"><span data-stu-id="cacbb-217">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="cacbb-218">若要驗證您擁有的角色，請登入 Microsoft 365https://portal.office.com)系統管理中心（請移至 [**使用者** > 作用中的**使用者**]，然後確認您擁有全域系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="cacbb-218">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="cacbb-219">如需管理員角色以及如何在 Office 365 中指派角色的詳細資訊，請參閱[關於 office 365 系統管理員角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。</span><span class="sxs-lookup"><span data-stu-id="cacbb-219">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a><span data-ttu-id="cacbb-220">將子域新增至客戶租使用者並進行驗證</span><span class="sxs-lookup"><span data-stu-id="cacbb-220">Add a subdomain to the customer tenant and verify it</span></span>
1. <span data-ttu-id="cacbb-221">在 Microsoft 365 系統管理中心中，移至**設定** > **網域** > [**新增網域**]。</span><span class="sxs-lookup"><span data-stu-id="cacbb-221">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="cacbb-222">在 [**輸入您擁有的網域**] 方塊中，輸入此租使用者的子域 FQDN。</span><span class="sxs-lookup"><span data-stu-id="cacbb-222">In the **Enter a domain you own** box, type the FQDN of the subdomain for this tenant.</span></span> <span data-ttu-id="cacbb-223">在下列範例中，子域是 sbc1.customers.adatum.biz。</span><span class="sxs-lookup"><span data-stu-id="cacbb-223">In the example below, the subdomain is sbc1.customers.adatum.biz.</span></span>

    ![[新增網域] 頁面的螢幕擷取畫面](media/direct-routing-5-sbc-add-customer-domain.png)

3. <span data-ttu-id="cacbb-225">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cacbb-225">Click **Next**.</span></span>
4. <span data-ttu-id="cacbb-226">FQDN 從未在租使用者中註冊。</span><span class="sxs-lookup"><span data-stu-id="cacbb-226">The FQDN has never been registered in the tenant.</span></span> <span data-ttu-id="cacbb-227">在下一個步驟中，您將需要驗證網域。</span><span class="sxs-lookup"><span data-stu-id="cacbb-227">In the next step, you will need to verify the domain.</span></span> <span data-ttu-id="cacbb-228">選取 [**新增 TXT 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="cacbb-228">Select **Add a TXT record instead**.</span></span> 

    ![[驗證網域] 頁面的螢幕擷取畫面](media/direct-routing-6-sbc-verify-customer-domain.png)

5. <span data-ttu-id="cacbb-230">按一下 **[下一步]**，並記下產生的 TXT 值以驗證功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="cacbb-230">Click **Next**, and note the TXT value generated to verify the domain name.</span></span>

    ![[驗證網域] 頁面上文字記錄的螢幕擷取畫面](media/direct-routing-7-sbc-verify-domain-txt.png)

6. <span data-ttu-id="cacbb-232">在電信公司的 DNS 主機服務提供者中，使用上一個步驟中的值來建立 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="cacbb-232">Create the TXT record with the value from the previous step in carrier's DNS hosting provider.</span></span>

    ![顯示建立 TXT 記錄的螢幕擷取畫面](media/direct-routing-8-sbc-txt-record.png)

    <span data-ttu-id="cacbb-234">如需詳細資訊，請參閱[在任何 dns 主機服務提供者處建立適用于 Office 365 的 dns 記錄](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)。</span><span class="sxs-lookup"><span data-stu-id="cacbb-234">For more information, refer to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span></span>

7. <span data-ttu-id="cacbb-235">回到客戶的 Microsoft 365 系統管理中心，然後按一下 [**驗證**]。</span><span class="sxs-lookup"><span data-stu-id="cacbb-235">Go back to the customer's Microsoft 365 admin center and click **Verify**.</span></span> 
8. <span data-ttu-id="cacbb-236">在下一頁上，選取 [**我將自行新增 DNS 記錄**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cacbb-236">On the next page, select **I'll add the DNS records myself** and click **Next**.</span></span>

    ![[更新 DNS 設定] 頁面上選項的螢幕擷取畫面](media/direct-routing-9-sbc-update-dns.png)

9. <span data-ttu-id="cacbb-238">在 [**選擇您的線上服務**] 頁面上，清除所有選項，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cacbb-238">On the **Choose your online services** page, clear all options and click **Next**.</span></span>

    ![[選擇您的線上服務] 頁面的螢幕擷取畫面](media/direct-routing-10-sbc-choose-services.png)

10. <span data-ttu-id="cacbb-240">按一下 [**更新 DNS 設定**] 頁面上的 **[完成]** 。</span><span class="sxs-lookup"><span data-stu-id="cacbb-240">Click **Finish** on the **Update DNS settings** page.</span></span>

    ![[更新 DNS 設定] 頁面的螢幕擷取畫面](media/direct-routing-11-sbc-update-dns-finish.png)

11. <span data-ttu-id="cacbb-242">確定狀態為 [**設定完成**]。</span><span class="sxs-lookup"><span data-stu-id="cacbb-242">Ensure that the status is **Setup complete**.</span></span> 
    
    ![顯示 [設定完成] 狀態之頁面的螢幕擷取畫面](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a><span data-ttu-id="cacbb-244">啟動子功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="cacbb-244">Activate the subdomain name</span></span>

<span data-ttu-id="cacbb-245">在您註冊功能變數名稱之後，您必須至少新增一個使用者，然後使用與客戶租使用者中建立的子域相符之 SIP 位址的 FQDN 部分來啟動該功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="cacbb-245">After you register a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created subdomain in the customer tenant.</span></span>

<span data-ttu-id="cacbb-246">*如需在 Office 365 組織中新增使用者的詳細資訊，請參閱[取得 office 365 網域的協助](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)。*</span><span class="sxs-lookup"><span data-stu-id="cacbb-246">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 organizations.*</span></span>

<span data-ttu-id="cacbb-247">例如： test@sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="cacbb-247">For example: test@sbc1.customers.adatum.biz</span></span>

![啟用 [子域] 頁面的螢幕擷取畫面](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a><span data-ttu-id="cacbb-249">建立主幹與置備使用者</span><span class="sxs-lookup"><span data-stu-id="cacbb-249">Create a trunk and provision users</span></span>

<span data-ttu-id="cacbb-250">在初次發行直接路由的情況下，Microsoft 需要使用新的 CSOnlinePSTNGateway 將主幹新增至每個服務租使用者（客戶租使用者）。</span><span class="sxs-lookup"><span data-stu-id="cacbb-250">With the initial release of Direct Routing, Microsoft required a trunk to be added to each served tenant (customer tenant) using New-CSOnlinePSTNGateway.</span></span>

<span data-ttu-id="cacbb-251">不過，這種情況尚未獲得最佳的原因：</span><span class="sxs-lookup"><span data-stu-id="cacbb-251">However, this has not proved optimal for two reasons:</span></span>
 
- <span data-ttu-id="cacbb-252">**額外負荷管理**。</span><span class="sxs-lookup"><span data-stu-id="cacbb-252">**Overhead management**.</span></span> <span data-ttu-id="cacbb-253">例如，如果您要啟用或停用媒體旁路，請更換或排出 SBC。</span><span class="sxs-lookup"><span data-stu-id="cacbb-253">Offloading or draining an SBC, for example, changes some parameters, like enabling or disabling media bypass.</span></span> <span data-ttu-id="cacbb-254">變更埠需要變更多個承租人中的參數（透過執行設定 CSOnlinePSTNGateway），但實際上是同一個 SBC。</span><span class="sxs-lookup"><span data-stu-id="cacbb-254">Changing the port requires changing parameters in multiple tenants (by running Set-CSOnlinePSTNGateway), but it is in fact the same SBC.</span></span> 

-  <span data-ttu-id="cacbb-255">**開銷處理**。</span><span class="sxs-lookup"><span data-stu-id="cacbb-255">**Overhead processing**.</span></span> <span data-ttu-id="cacbb-256">收集及監視幹線狀態資料-從多個邏輯 trunks 收集的 SIP 選項，實際上是同一個 SBC 與相同的物理幹線，會減緩路由資料的處理。</span><span class="sxs-lookup"><span data-stu-id="cacbb-256">Gathering and monitoring trunk health data - SIP options collected from multiple logical trunks that are, in reality, the same SBC and the same physical trunk, slows down processing of the routing data.</span></span>
 
<span data-ttu-id="cacbb-257">根據這項意見反應，Microsoft 正在為客戶租使用者提供新的邏輯來提供 trunks。</span><span class="sxs-lookup"><span data-stu-id="cacbb-257">Based on this feedback, Microsoft is bringing in a new logic to provision the trunks for the customer tenants.</span></span>

<span data-ttu-id="cacbb-258">引入了兩個新的實體：</span><span class="sxs-lookup"><span data-stu-id="cacbb-258">Two new entities were introduced:</span></span>
-    <span data-ttu-id="cacbb-259">使用命令 New-CSOnlinePSTNGateway 在載波租使用者中註冊的載波幹線，例如新的-CSOnlinePSTNGateway-FQDN customers.adatum.biz-SIPSignalingport 5068-ForwardPAI $true。</span><span class="sxs-lookup"><span data-stu-id="cacbb-259">A carrier trunk registered in the carrier tenant using the command New-CSOnlinePSTNGateway, for example New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true.</span></span>

-    <span data-ttu-id="cacbb-260">衍生的主幹，不需要註冊。</span><span class="sxs-lookup"><span data-stu-id="cacbb-260">A derived trunk, that does not require registration.</span></span> <span data-ttu-id="cacbb-261">它只是從載波幹線中新增的想要的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="cacbb-261">It is simply a desired host name added in from of the carrier trunk.</span></span> <span data-ttu-id="cacbb-262">它會從載波幹線衍生其所有設定參數。</span><span class="sxs-lookup"><span data-stu-id="cacbb-262">It derives all of its configuration parameters from the carrier trunk.</span></span> <span data-ttu-id="cacbb-263">衍生主幹不需要在 PowerShell 中建立，而且與載波幹線的關聯性是以 FQDN 名稱為基礎（請參閱下方的詳細資料）。</span><span class="sxs-lookup"><span data-stu-id="cacbb-263">The derived trunk doesn't need to be created in PowerShell, and the association with the carrier trunk is based on the FQDN name (see details below).</span></span>

<span data-ttu-id="cacbb-264">**置備邏輯與範例**</span><span class="sxs-lookup"><span data-stu-id="cacbb-264">**Provisioning logic and example**</span></span>

-    <span data-ttu-id="cacbb-265">運營商只需要使用 CSOnlinePSTNGateway 命令來設定和管理單一干線（電信公司網域中的載波幹線）。</span><span class="sxs-lookup"><span data-stu-id="cacbb-265">Carriers only need to set up and manage a single trunk  (carrier trunk in the carrier domain), using the Set-CSOnlinePSTNGateway command.</span></span> <span data-ttu-id="cacbb-266">在上述範例中，它是 adatum.biz;</span><span class="sxs-lookup"><span data-stu-id="cacbb-266">In the example above it is adatum.biz;</span></span>
-    <span data-ttu-id="cacbb-267">在客戶租使用者中，電信公司只需要將衍生的主幹 FQDN 新增至使用者的語音路由原則。</span><span class="sxs-lookup"><span data-stu-id="cacbb-267">In the customer tenant, the carrier need only to add the derived trunk FQDN to the voice routing policies of the users.</span></span> <span data-ttu-id="cacbb-268">不需要針對主幹執行新的 CSOnlinePSTNGateway。</span><span class="sxs-lookup"><span data-stu-id="cacbb-268">There is no need to run New-CSOnlinePSTNGateway for a trunk.</span></span>
-    <span data-ttu-id="cacbb-269">衍生的主幹（如名稱所暗示）會繼承或衍生載波幹線的所有設定參數。</span><span class="sxs-lookup"><span data-stu-id="cacbb-269">The derived trunk, as the name suggests, inherits or derives all the configuration parameters from the carrier trunk.</span></span> <span data-ttu-id="cacbb-270">示例</span><span class="sxs-lookup"><span data-stu-id="cacbb-270">Examples:</span></span>
-    <span data-ttu-id="cacbb-271">Customers.adatum.biz –需要在承運人租使用者中建立的載波主幹。</span><span class="sxs-lookup"><span data-stu-id="cacbb-271">Customers.adatum.biz – the carrier trunk which needs to be created in the carrier tenant.</span></span>
-    <span data-ttu-id="cacbb-272">Sbc1.customers.adatum.biz –客戶租使用者中的衍生主幹，不需要在 PowerShell 中建立。</span><span class="sxs-lookup"><span data-stu-id="cacbb-272">Sbc1.customers.adatum.biz – the derived trunk in a customer tenant that does not need to be created in PowerShell.</span></span>  <span data-ttu-id="cacbb-273">您可以直接在線上語音路由策略中，在客戶租使用者中新增衍生主幹的名稱，而不需建立它。</span><span class="sxs-lookup"><span data-stu-id="cacbb-273">You can simply add the name of the derived trunk in the customer tenant in the online voice routing policy without creating it.</span></span>
-   <span data-ttu-id="cacbb-274">電信公司將需要設定 DNS 記錄，將衍生的主幹 FQDN 解析成載波 SBC ip 位址。</span><span class="sxs-lookup"><span data-stu-id="cacbb-274">Carrier will need to setup DNS record resolving derived trunk FQDN to carrier SBC ip address.</span></span>

-    <span data-ttu-id="cacbb-275">在載波主幹上所做的任何變更（在承運人租使用者），都會自動套用到衍生的 trunks。</span><span class="sxs-lookup"><span data-stu-id="cacbb-275">Any changes made on a carrier trunk (on carrier tenant) is automatically applied to derived trunks.</span></span> <span data-ttu-id="cacbb-276">例如，電信公司可以在載波主幹上變更 SIP 埠，此變更會套用至所有衍生的 trunks。</span><span class="sxs-lookup"><span data-stu-id="cacbb-276">For example, carriers can change an SIP port on the carrier trunk, and this change applies to all derived trunks.</span></span> <span data-ttu-id="cacbb-277">設定 trunks 的新邏輯可簡化管理，因為您不需要移至每個租使用者，並在每個幹線變更參數。</span><span class="sxs-lookup"><span data-stu-id="cacbb-277">New logic to configure the trunks simplifies the management as you don't need to go to every tenant and change the parameter on every trunk.</span></span>
-    <span data-ttu-id="cacbb-278">選項只會傳送給載波中繼 FQDN。</span><span class="sxs-lookup"><span data-stu-id="cacbb-278">The options are sent only to the carrier trunk FQDN.</span></span> <span data-ttu-id="cacbb-279">載波幹線的健康狀態會套用至所有衍生的 trunks，並用於路由決定。</span><span class="sxs-lookup"><span data-stu-id="cacbb-279">The health status of the carrier trunk is applied to all derived trunks and is used for routing decisions.</span></span> <span data-ttu-id="cacbb-280">瞭解更多關於[直接路由選項](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot)的資訊。</span><span class="sxs-lookup"><span data-stu-id="cacbb-280">Find out more about [Direct Routing options](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot).</span></span>
-    <span data-ttu-id="cacbb-281">電信公司可以排出載波幹線，而且所有衍生的 trunks 也會排出。</span><span class="sxs-lookup"><span data-stu-id="cacbb-281">The carrier can drain the carrier trunk, and all derived trunks will be drained as well.</span></span> 
 

<span data-ttu-id="cacbb-282">**從先前的模型遷移至載波幹線**</span><span class="sxs-lookup"><span data-stu-id="cacbb-282">**Migration from the previous model to the carrier trunk**</span></span>
 
<span data-ttu-id="cacbb-283">若要從載波託管模型的目前實現遷移到新的模型，運營商將需要針對客戶租使用者重新設定 trunks。</span><span class="sxs-lookup"><span data-stu-id="cacbb-283">For migration from the current implementation of the carrier hosted model to the new model, the carriers will need to reconfigure the trunks for customer tenants.</span></span> <span data-ttu-id="cacbb-284">使用移除-CSOnlinePSTNGateway （在承運人租使用者中離開主幹）從客戶租使用者中移除 trunks</span><span class="sxs-lookup"><span data-stu-id="cacbb-284">Remove the trunks from the customer tenants using Remove-CSOnlinePSTNGateway (leaving the trunk in the carrier tenant)-</span></span>

<span data-ttu-id="cacbb-285">我們強烈建議您儘快遷移到新的解決方案，因為我們將使用載波和衍生的幹線模型來加強監視和提供。</span><span class="sxs-lookup"><span data-stu-id="cacbb-285">We highly encourage migrating to the new solution as soon as possible as we will be enhancing monitoring and provisioning using the carrier and derived trunk model.</span></span>
 

<span data-ttu-id="cacbb-286">請參閱[SBC 轉銷商提供的相關指示](#deploy-and-configure-the-sbc)，瞭解如何在連絡人標題中傳送子域的 FQDN 名稱。</span><span class="sxs-lookup"><span data-stu-id="cacbb-286">Please refer to the [SBC vendor instructions](#deploy-and-configure-the-sbc) on configuring sending the FQDN name of subdomains in the Contact header.</span></span>

## <a name="considerations-for-setting-up-muti-tenant-failover"></a><span data-ttu-id="cacbb-287">設定 muti-租使用者容錯移轉的考慮</span><span class="sxs-lookup"><span data-stu-id="cacbb-287">Considerations for setting up muti-tenant failover</span></span> 

<span data-ttu-id="cacbb-288">若要針對多租使用者環境設定容錯移轉，您必須執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="cacbb-288">To set up failover for a multi-tenant environment, you'll need to do the following:</span></span>

- <span data-ttu-id="cacbb-289">針對每個租使用者，新增兩個不同 SBCs 的 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="cacbb-289">For each tenant, add the FQDNs for two different SBCs.</span></span>  <span data-ttu-id="cacbb-290">例如：</span><span class="sxs-lookup"><span data-stu-id="cacbb-290">For example:</span></span>

   <span data-ttu-id="cacbb-291">customer1.sbc1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cacbb-291">customer1.sbc1.contoso.com</span></span> <br>
   <span data-ttu-id="cacbb-292">customer2.sbc2.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cacbb-292">customer2.sbc2.contoso.com</span></span> <br>

- <span data-ttu-id="cacbb-293">在使用者的線上語音路由策略中，指定半形。</span><span class="sxs-lookup"><span data-stu-id="cacbb-293">In the Online Voice Routing policies of the users, specify both SBCs.</span></span>  <span data-ttu-id="cacbb-294">如果一個 SBC 失敗，路由策略會將呼叫路由到第二個 SBC。</span><span class="sxs-lookup"><span data-stu-id="cacbb-294">If one SBC fails, the routing policy will route calls to the second SBC.</span></span>


## <a name="see-also"></a><span data-ttu-id="cacbb-295">另請參閱</span><span class="sxs-lookup"><span data-stu-id="cacbb-295">See also</span></span>

[<span data-ttu-id="cacbb-296">規劃直接路由</span><span class="sxs-lookup"><span data-stu-id="cacbb-296">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="cacbb-297">設定直接路由</span><span class="sxs-lookup"><span data-stu-id="cacbb-297">Configure Direct Routing</span></span>](direct-routing-configure.md)

