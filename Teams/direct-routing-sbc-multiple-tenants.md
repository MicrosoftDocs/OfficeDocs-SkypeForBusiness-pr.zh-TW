---
title: 設定會話邊界控制器 - 多個租使用者
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
description: 瞭解如何在 SBC (設定一個會話邊界控制器) 為 Microsoft 合作夥伴及/或 PSTN 電信) 服務多個租使用者。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 343e2d1aedefd34de452df8da6ce9a5ad1a726ba
ms.sourcegitcommit: b12ec4703b164c545d17b02815edd6ee28d40bed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49923845"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a><span data-ttu-id="364b6-103">設定多個租用戶的工作階段邊界控制器</span><span class="sxs-lookup"><span data-stu-id="364b6-103">Configure a Session Border Controller for multiple tenants</span></span>

<span data-ttu-id="364b6-104">直接路由支援在 SBC (上) 一個會話邊界控制器，以服務多個租使用者。</span><span class="sxs-lookup"><span data-stu-id="364b6-104">Direct Routing supports configuring one Session Border Controller (SBC) to serve multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="364b6-105">此案例是專為 Microsoft 合作夥伴和/或 PSTN 電信平臺所設計，本文稍後稱為電信者。</span><span class="sxs-lookup"><span data-stu-id="364b6-105">This scenario is designed for Microsoft partners and/or PSTN carriers, referred to as carriers later in this document.</span></span> <span data-ttu-id="364b6-106">電信業者銷售傳送至 Microsoft Teams 的電話語音服務給客戶。</span><span class="sxs-lookup"><span data-stu-id="364b6-106">A carrier sells telephony services delivered to Microsoft Teams to their customers.</span></span> 

<span data-ttu-id="364b6-107">電信公司：</span><span class="sxs-lookup"><span data-stu-id="364b6-107">A carrier:</span></span>
- <span data-ttu-id="364b6-108">在資料中心部署和管理 SBC (客戶不需要執行 SBC，而且他們會在 Teams 用戶端用戶端服務中從電信業者) 。</span><span class="sxs-lookup"><span data-stu-id="364b6-108">Deploys and manages an SBC in their datacenter (customers do not need to implement an SBC, and they receive telephony services from the carrier in the Teams client).</span></span>
- <span data-ttu-id="364b6-109">將 SBC 與多個租使用者相互連接。</span><span class="sxs-lookup"><span data-stu-id="364b6-109">Interconnects the SBC to multiple tenants.</span></span>
- <span data-ttu-id="364b6-110">為客戶提供 PSTN 服務。</span><span class="sxs-lookup"><span data-stu-id="364b6-110">Provides PSTN services to customers.</span></span>
- <span data-ttu-id="364b6-111">端對端管理通話品質。</span><span class="sxs-lookup"><span data-stu-id="364b6-111">Manages call quality end to end.</span></span>
- <span data-ttu-id="364b6-112">PSTN 服務另行收費。</span><span class="sxs-lookup"><span data-stu-id="364b6-112">Charges separately for PSTN services.</span></span>

<span data-ttu-id="364b6-113">Microsoft 並未管理電信電信公司。</span><span class="sxs-lookup"><span data-stu-id="364b6-113">Microsoft does not manage carriers.</span></span> <span data-ttu-id="364b6-114">Microsoft 提供 PBX (Microsoft Phone System) Teams 用戶端。</span><span class="sxs-lookup"><span data-stu-id="364b6-114">Microsoft offers a PBX (Microsoft Phone System) and a Teams client.</span></span> <span data-ttu-id="364b6-115">Microsoft 也會為可與 Microsoft Phone System 一同使用的手機和認證 SBC 提供認證。</span><span class="sxs-lookup"><span data-stu-id="364b6-115">Microsoft also certifies phones, and certifies SBCs that can be used with the Microsoft Phone System.</span></span> <span data-ttu-id="364b6-116">選擇電信業者之前，請確定您的選擇具有通過認證的 SBC，而且可以端對端管理語音品質。</span><span class="sxs-lookup"><span data-stu-id="364b6-116">Before choosing a carrier, please ensure that your choice has a certified SBC and can manage voice quality end to end.</span></span>

<span data-ttu-id="364b6-117">以下是設定案例的技術執行步驟。</span><span class="sxs-lookup"><span data-stu-id="364b6-117">The following are the technical implementation steps to configure the scenario.</span></span>

<span data-ttu-id="364b6-118">**只提供電信商：**</span><span class="sxs-lookup"><span data-stu-id="364b6-118">**Carrier only:**</span></span>
1. <span data-ttu-id="364b6-119">根據認證 SBC 廠商的指示部署 SBC，並針對託管案例 [進行設定](#deploy-and-configure-the-sbc)。</span><span class="sxs-lookup"><span data-stu-id="364b6-119">Deploy the SBC and configure it for the hosting scenario according to the [instructions from the certified SBC vendors](#deploy-and-configure-the-sbc).</span></span>
2. <span data-ttu-id="364b6-120">在電信業者租使用者中註冊基本功能變數名稱，並要求萬用字元憑證。</span><span class="sxs-lookup"><span data-stu-id="364b6-120">Register a base domain name in the carrier tenant and request a wildcard certificate.</span></span>
3. <span data-ttu-id="364b6-121">針對每個客戶註冊子域，這是基本網域的一部分。</span><span class="sxs-lookup"><span data-stu-id="364b6-121">Register a subdomain for every customer, which is part of the base domain.</span></span>

<span data-ttu-id="364b6-122">**具有客戶全域系統管理員的電信公司：**</span><span class="sxs-lookup"><span data-stu-id="364b6-122">**Carrier with a Customer Global Administrator:**</span></span>
1. <span data-ttu-id="364b6-123">將子功能變數名稱稱新增到客戶租使用者。</span><span class="sxs-lookup"><span data-stu-id="364b6-123">Add the subdomain name to the customer tenant.</span></span>
2. <span data-ttu-id="364b6-124">啟動子功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="364b6-124">Activate the subdomain name.</span></span>
3. <span data-ttu-id="364b6-125">設定從電信公司到客戶租使用者的主幹，並配置使用者。</span><span class="sxs-lookup"><span data-stu-id="364b6-125">Configure the trunk from the carrier to the customer tenant and provision users.</span></span>

<span data-ttu-id="364b6-126">*請務必瞭解 DNS 基本功能，以及 Microsoft 365 或 Office 365 中的功能變數名稱管理方式。在 [繼續進行之前，先查看取得 Microsoft 365 或 Office 365 網](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 域的協助。*</span><span class="sxs-lookup"><span data-stu-id="364b6-126">*Please make sure you understand DNS basics and how the domain name is managed in Microsoft 365 or Office 365. Review [Get help with Microsoft 365 or Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) before proceeding further.*</span></span>

## <a name="deploy-and-configure-the-sbc"></a><span data-ttu-id="364b6-127">部署及設定 SBC</span><span class="sxs-lookup"><span data-stu-id="364b6-127">Deploy and configure the SBC</span></span>

<span data-ttu-id="364b6-128">如需如何部署及設定 SBC 託管案例 SBC 的詳細步驟，請參閱 SBC 廠商的檔。</span><span class="sxs-lookup"><span data-stu-id="364b6-128">For the detailed steps on how to deploy and configure SBCs for an SBC hosting scenario, please refer to the SBC vendor's documentation.</span></span>

- <span data-ttu-id="364b6-129">**AudioCodes：** [Direct Routing Configuration notes，](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)the SBC 主機託管案例的組式描述于「將 AudioCodes SBC 連結至 Microsoft Teams 直接路由主機管理模型組組記」。</span><span class="sxs-lookup"><span data-stu-id="364b6-129">**AudioCodes:** [Direct Routing Configuration notes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), the configuration of the SBC hosting scenario described in "Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note."</span></span> 
- <span data-ttu-id="364b6-130">**Oracle：Direct** [Routing Configuration notes，](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)the configuration of SBC hosting scenario is described in the "Microsoft" section.</span><span class="sxs-lookup"><span data-stu-id="364b6-130">**Oracle:** [Direct Routing Configuration notes](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html), the configuration of the SBC hosting scenario is described in the "Microsoft" section.</span></span> 
- <span data-ttu-id="364b6-131">**功能區通訊：** 請參閱功能區 [通訊 SBC 核心版 Microsoft Teams](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe)設定指南，以瞭解如何設定功能區核心系列 SB0 及此頁面功能區最佳作法 - 設定 Microsoft Teams 直接路由 [SBC Edge](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)的電信業者</span><span class="sxs-lookup"><span data-stu-id="364b6-131">**Ribbon Communications:**  Please refer to the [Ribbon Communications SBC Core Microsoft Teams Configuration Guide](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) for documentation on how to configure Ribbon Core Series SBCs and to this page [Ribbon Best Practice - Configuring Carriers for Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)</span></span>
- <span data-ttu-id="364b6-132">**TE-Systems (anynode) ：**  請在 [TE-Systems Community](https://community.te-systems.de/) 頁面上註冊，以瞭解如何為多個租使用者設定 anynode SBC 的檔和範例。</span><span class="sxs-lookup"><span data-stu-id="364b6-132">**TE-Systems (anynode):**  Please register on the [TE-Systems Community page](https://community.te-systems.de/) for documentation and examples on how to configure anynode SBC for multiple tenants.</span></span>
- <span data-ttu-id="364b6-133">**元數：**  請在 [Metasw一社群頁面](https://manuals.metaswitch.com/MAN39555) 註冊，以瞭解如何為多個租使用者啟用 Perimeta SBC 的檔。</span><span class="sxs-lookup"><span data-stu-id="364b6-133">**Metaswitch:**  Please register on the [Metaswitch Community page](https://manuals.metaswitch.com/MAN39555) for documentation on how to enable Perimeta SBC for multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="364b6-134">請注意如何設定「連絡人」標頭。</span><span class="sxs-lookup"><span data-stu-id="364b6-134">Please pay attention to how to configure the "Contact" header.</span></span> <span data-ttu-id="364b6-135">連絡人標題可用來在傳入的邀請訊息上尋找客戶租使用者。</span><span class="sxs-lookup"><span data-stu-id="364b6-135">The Contact header is used to find the customer tenant on the incoming invite message.</span></span> 

## <a name="register-a-base-domain-and-subdomains"></a><span data-ttu-id="364b6-136">註冊基本網域和子域</span><span class="sxs-lookup"><span data-stu-id="364b6-136">Register a base domain and subdomains</span></span>

<span data-ttu-id="364b6-137">針對託管案例，您必須建立：</span><span class="sxs-lookup"><span data-stu-id="364b6-137">For the hosting scenario, you need to create:</span></span>
- <span data-ttu-id="364b6-138">電信業者所擁有的一個基礎功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="364b6-138">One base domain name owned by the carrier.</span></span>
- <span data-ttu-id="364b6-139">這是每個客戶租使用者中基礎功能變數名稱的一部分之子域。</span><span class="sxs-lookup"><span data-stu-id="364b6-139">A subdomain that is part of the base domain name in every customer tenant.</span></span>

<span data-ttu-id="364b6-140">在下列範例中：</span><span class="sxs-lookup"><span data-stu-id="364b6-140">In the following example:</span></span>
- <span data-ttu-id="364b6-141">Adatum 是一家電信業者，提供網際網路和電話語音給數位客戶。</span><span class="sxs-lookup"><span data-stu-id="364b6-141">Adatum is a carrier that serves several customers by providing Internet and telephony services.</span></span>
- <span data-ttu-id="364b6-142">Woodgrove Bank、Contoso 和 Adventure Works 是三個擁有 Microsoft 365 或 Office 365 網域但從 Adatum 接收電話語音的客戶。</span><span class="sxs-lookup"><span data-stu-id="364b6-142">Woodgrove Bank, Contoso, and Adventure Works are three customers that have Microsoft 365 or Office 365 domains but receive the telephony services from Adatum.</span></span>

<span data-ttu-id="364b6-143">子域必須與要為客戶配置的主幹 FQDN 名稱與傳送邀請給 Microsoft 365 或 Office 365 時，連絡人標頭中的 FQDN 相符。</span><span class="sxs-lookup"><span data-stu-id="364b6-143">Subdomains **MUST** match the FQDN name of the trunk that will be configured for the customer and the FQDN in the Contact header when sending the Invite to Microsoft 365 or Office 365.</span></span> 

<span data-ttu-id="364b6-144">當通話抵達 Microsoft 365 或 Office 365 直接路由介面時，該介面會使用連絡人標頭，尋找使用者應查看的租使用者。</span><span class="sxs-lookup"><span data-stu-id="364b6-144">When a call arrives at the Microsoft 365 or Office 365 Direct Routing interface, the interface uses the Contact header to find the tenant where the user should be looked up.</span></span> <span data-ttu-id="364b6-145">直接路由不會在邀請上使用電話號碼查找，因為有些客戶的非 DID 號碼可能會與數個租使用者重迭。</span><span class="sxs-lookup"><span data-stu-id="364b6-145">Direct Routing does not use phone number lookup on the Invite, as some customers might have non-DID numbers that can overlap in several tenants.</span></span> <span data-ttu-id="364b6-146">因此，若要找出以電話號碼來尋找使用者的確切租使用者，在連絡人標頭中必須輸入 FQDN 名稱。</span><span class="sxs-lookup"><span data-stu-id="364b6-146">Therefore, the FQDN name in the Contact header is required to identify the exact tenant to look up the user by the phone number.</span></span>

<span data-ttu-id="364b6-147">*如需在 Microsoft  [365 或 Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 組織中建立功能變數名稱的資訊，請參閱取得 Office 365 網域的協助。*</span><span class="sxs-lookup"><span data-stu-id="364b6-147">*Please review  [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about creating domain names in Microsoft 365 or Office 365 organizations.*</span></span>

<span data-ttu-id="364b6-148">下圖摘要說明基礎網域、子域和連絡人標頭的需求。</span><span class="sxs-lookup"><span data-stu-id="364b6-148">The following diagram summarizes the requirements to base domain, subdomains, and Contact header.</span></span>

![顯示網域和連絡人頁眉需求的圖表](media/direct-routing-1-sbc-requirements.png)

<span data-ttu-id="364b6-150">SBC 需要憑證來驗證連結。</span><span class="sxs-lookup"><span data-stu-id="364b6-150">The SBC requires a certificate to authenticate the connections.</span></span> <span data-ttu-id="364b6-151">針對 SBC 主機服務案例，電信業者需要向 CN 和/或 SAN .base_domain (要求憑證，例如 *\* \* .customers.adatum.biz) 。*</span><span class="sxs-lookup"><span data-stu-id="364b6-151">For the SBC hosting scenario, the carrier needs to request a certificate with CN and/or SAN *\*.base_domain (for example, \*.customers.adatum.biz)*.</span></span> <span data-ttu-id="364b6-152">此憑證可用來驗證從單一 SBC 服務的多個租使用者之連結。</span><span class="sxs-lookup"><span data-stu-id="364b6-152">This certificate can be used to authenticate connections to multiple tenants served from a single SBC.</span></span>


<span data-ttu-id="364b6-153">下表是一個組配置的範例。</span><span class="sxs-lookup"><span data-stu-id="364b6-153">The following table is an example of one configuration.</span></span>


|<span data-ttu-id="364b6-154">新的功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="364b6-154">New domain name</span></span> |<span data-ttu-id="364b6-155">類型</span><span class="sxs-lookup"><span data-stu-id="364b6-155">Type</span></span>|<span data-ttu-id="364b6-156">註冊</span><span class="sxs-lookup"><span data-stu-id="364b6-156">Registered</span></span>  |<span data-ttu-id="364b6-157">SBC 憑證 CN/SAN</span><span class="sxs-lookup"><span data-stu-id="364b6-157">Certificate CN/SAN for SBC</span></span>  |<span data-ttu-id="364b6-158">範例中的租使用者預設網域</span><span class="sxs-lookup"><span data-stu-id="364b6-158">Tenant default domain in the example</span></span>  |<span data-ttu-id="364b6-159">傳送來電給使用者時，SBC 必須在連絡人標頭中顯示之 FQDN 名稱</span><span class="sxs-lookup"><span data-stu-id="364b6-159">FQDN name that SBC must present in the Contact header when sending calls to users</span></span>|
|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="364b6-160">customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="364b6-160">customers.adatum.biz</span></span>|    <span data-ttu-id="364b6-161">基地</span><span class="sxs-lookup"><span data-stu-id="364b6-161">Base</span></span>     |     <span data-ttu-id="364b6-162">在電信公司租使用者中</span><span class="sxs-lookup"><span data-stu-id="364b6-162">In carrier tenant</span></span>  |    <span data-ttu-id="364b6-163">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="364b6-163">\*.customers.adatum.biz</span></span>  |   <span data-ttu-id="364b6-164">adatum.biz</span><span class="sxs-lookup"><span data-stu-id="364b6-164">adatum.biz</span></span>      |<span data-ttu-id="364b6-165">NA，這是服務租使用者，沒有使用者</span><span class="sxs-lookup"><span data-stu-id="364b6-165">NA, this is a service tenant, no users</span></span> |
|<span data-ttu-id="364b6-166">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="364b6-166">sbc1.customers.adatum.biz</span></span>|    <span data-ttu-id="364b6-167">子域</span><span class="sxs-lookup"><span data-stu-id="364b6-167">Subdomain</span></span>  |    <span data-ttu-id="364b6-168">在客戶租使用者中</span><span class="sxs-lookup"><span data-stu-id="364b6-168">In a customer tenant</span></span>  |    <span data-ttu-id="364b6-169">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="364b6-169">\*.customers.adatum.biz</span></span>  | <span data-ttu-id="364b6-170">woodgrovebank.us</span><span class="sxs-lookup"><span data-stu-id="364b6-170">woodgrovebank.us</span></span>  |  <span data-ttu-id="364b6-171">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="364b6-171">sbc1.customers.adatum.biz</span></span>|
|<span data-ttu-id="364b6-172">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="364b6-172">sbc2.customers.adatum.biz</span></span>  |   <span data-ttu-id="364b6-173">子域</span><span class="sxs-lookup"><span data-stu-id="364b6-173">Subdomain</span></span> | <span data-ttu-id="364b6-174">在客戶租使用者中</span><span class="sxs-lookup"><span data-stu-id="364b6-174">In a customer tenant</span></span>   |   <span data-ttu-id="364b6-175">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="364b6-175">\*.customers.adatum.biz</span></span>   |<span data-ttu-id="364b6-176">contoso.com</span><span class="sxs-lookup"><span data-stu-id="364b6-176">contoso.com</span></span>   |<span data-ttu-id="364b6-177">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="364b6-177">sbc2.customers.adatum.biz</span></span> |
|<span data-ttu-id="364b6-178">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="364b6-178">sbc3.customers.adatum.biz</span></span> |   <span data-ttu-id="364b6-179">子域</span><span class="sxs-lookup"><span data-stu-id="364b6-179">Subdomain</span></span> | <span data-ttu-id="364b6-180">在客戶租使用者中</span><span class="sxs-lookup"><span data-stu-id="364b6-180">In a customer tenant</span></span> |   <span data-ttu-id="364b6-181">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="364b6-181">\*.customers.adatum.biz</span></span>  |  <span data-ttu-id="364b6-182">adventureworks.com</span><span class="sxs-lookup"><span data-stu-id="364b6-182">adventureworks.com</span></span> | <span data-ttu-id="364b6-183">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="364b6-183">sbc3.customers.adatum.biz</span></span> |
||         |         |         |         |         |

<span data-ttu-id="364b6-184">若要設定基底和子域，請遵循下列所述步驟。</span><span class="sxs-lookup"><span data-stu-id="364b6-184">To configure the base and subdomains, please follow the steps described below.</span></span> <span data-ttu-id="364b6-185">在範例中，我們會針對 Woodgrove Bank 租使用者 (customers.adatum.biz) 一個客戶帳戶設定基本功能變數名稱 (sbc1.customers.adatum.biz域) 。</span><span class="sxs-lookup"><span data-stu-id="364b6-185">In the example, we will configure a base domain name (customers.adatum.biz) and a subdomain for one customer (sbc1.customers.adatum.biz in Woodgrove Bank tenant).</span></span>

> [!NOTE]
> <span data-ttu-id="364b6-186">在sbcX.customers.adatum.biz租使用者中啟用語音功能。</span><span class="sxs-lookup"><span data-stu-id="364b6-186">Use sbcX.customers.adatum.biz to enable voice in the carrier tenant.</span></span> <span data-ttu-id="364b6-187">sbcX 可以是任何唯一且有效的 Alphanumeric 主機名稱。</span><span class="sxs-lookup"><span data-stu-id="364b6-187">sbcX can be any unique and valid alphanumeric hostname.</span></span>

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a><span data-ttu-id="364b6-188">在電信公司租使用者中註冊基本功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="364b6-188">Register a base domain name in the carrier tenant</span></span>

<span data-ttu-id="364b6-189">**這些動作是在電信公司租使用者中執行。**</span><span class="sxs-lookup"><span data-stu-id="364b6-189">**These actions are performed in the carrier tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a><span data-ttu-id="364b6-190">確定您擁有電信公司租使用者的適當許可權</span><span class="sxs-lookup"><span data-stu-id="364b6-190">Ensure that you have appropriate rights in the carrier tenant</span></span>

<span data-ttu-id="364b6-191">如果您是以全域系統管理員的名號，在 Microsoft 365 系統管理中心內，才能新增網域。</span><span class="sxs-lookup"><span data-stu-id="364b6-191">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="364b6-192">若要驗證您擁有的角色，請前往 Microsoft 365 系統管理中心 (、前往使用者作用中使用者，然後確認您擁有 https://portal.office.com)   >  全域系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="364b6-192">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="364b6-193">有關系統管理員角色以及如何在 Microsoft 365 或 Office 365 中指派角色詳細資訊，請參閱關於 [系統管理員角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。</span><span class="sxs-lookup"><span data-stu-id="364b6-193">For more information about admin roles and how to assign a role in Microsoft 365 or Office 365, see [About admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a><span data-ttu-id="364b6-194">新增基本網域至租使用者並進行驗證</span><span class="sxs-lookup"><span data-stu-id="364b6-194">Add a base domain to the tenant and verify it</span></span>

1. <span data-ttu-id="364b6-195">在 Microsoft 365 系統管理中心，請前往設定  >  **網域**  >  **新增網域**。</span><span class="sxs-lookup"><span data-stu-id="364b6-195">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="364b6-196">在 **輸入您擁有之網域的** 方塊中，輸入基本網域的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="364b6-196">In the **Enter a domain you own** box, type the FQDN of the base domain.</span></span> <span data-ttu-id="364b6-197">在下列範例中，基本網域為 *customers.adatum.biz。*</span><span class="sxs-lookup"><span data-stu-id="364b6-197">In the following example, the base domain is *customers.adatum.biz*.</span></span>

    ![顯示新增網域頁面的螢幕擷取畫面](media/direct-routing-2-sbc-add-domain.png)

3. <span data-ttu-id="364b6-199">按一下 [ **下一步**。</span><span class="sxs-lookup"><span data-stu-id="364b6-199">Click **Next**.</span></span>
4. <span data-ttu-id="364b6-200">在範例中，租使用者已經有adatum.biz驗證功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="364b6-200">In the example, the tenant already has adatum.biz as a verified domain name.</span></span> <span data-ttu-id="364b6-201">精靈不會要求進行其他驗證，因為 customers.adatum.biz是已登錄名稱的子域。</span><span class="sxs-lookup"><span data-stu-id="364b6-201">The wizard will not ask for additional verification because customers.adatum.biz is a subdomain for the already registered name.</span></span> <span data-ttu-id="364b6-202">不過，如果您新增之前尚未驗證的 FQDN，則需要執行驗證程式。</span><span class="sxs-lookup"><span data-stu-id="364b6-202">However, if you add an FQDN that has not been verified before, you will need to go through the process of verification.</span></span> <span data-ttu-id="364b6-203">以下說明驗證 [程式](#add-a-subdomain-to-the-customer-tenant-and-verify-it)。</span><span class="sxs-lookup"><span data-stu-id="364b6-203">The process of verification is [described below](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span></span>

    ![顯示已驗證功能變數名稱確認的螢幕擷取畫面](media/direct-routing-3-sbc-verify-domain.png)

5. <span data-ttu-id="364b6-205">按 **[下** 一步，在 [ **更新 DNS** 設定> 頁面上，選取我要新增 **DNS** 記錄，然後按一下 [下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="364b6-205">Click **Next**, and on the **Update DNS Settings** page, select **I'll add the DNS records myself** and click **Next**.</span></span>
6. <span data-ttu-id="364b6-206">在下一頁中，清除所有值 (除非您要使用 Exchange、SharePoint 或 Teams/商務用 Skype) 功能變數名稱，請按一下 [下一步，然後按一下 [完成。</span><span class="sxs-lookup"><span data-stu-id="364b6-206">On the next page, clear all values (unless you want to use the domain name for Exchange, SharePoint, or Teams/Skype for Business), click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="364b6-207">請確定您的新網域是設定完成狀態。</span><span class="sxs-lookup"><span data-stu-id="364b6-207">Make sure your new domain is in the Setup complete status.</span></span>

    ![顯示設定完成狀態之網域的螢幕擷取畫面](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a><span data-ttu-id="364b6-209">啟用功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="364b6-209">Activate the domain name</span></span>

<span data-ttu-id="364b6-210">註冊功能變數名稱之後，您必須新增至少一個 E1、E3 或 E5 授權使用者，並指派 SIP 位址的 SIP 位址的 FQDN 部分，與所建立之基本網域配對，以啟用該功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="364b6-210">After you have registered a domain name, you need to activate it by adding at least one E1, E3, or E5 licensed user and assigning a SIP address with the FQDN portion of the SIP address matching the created base domain.</span></span> <span data-ttu-id="364b6-211">在網域啟用之後，授權 (最多可能需要 24 小時的時間) 。</span><span class="sxs-lookup"><span data-stu-id="364b6-211">License can be revoked after the domain activation (it can take up to 24 hours).</span></span>

> [!NOTE]
> <span data-ttu-id="364b6-212">電信業者租使用者必須保留指派給租使用者至少一個 E1/E3/E5/M365 商務版授權，以避免移除商務用 Skype 組配置。</span><span class="sxs-lookup"><span data-stu-id="364b6-212">The Carrier tenant must keep at least one E1/E3/E5/M365 Business license assigned to the tenant to avoid removal of the Skype for Business configuration.</span></span> 

<span data-ttu-id="364b6-213">*如需在 [Microsoft 365 或 Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 組織中新增使用者之詳細資訊，請參閱取得 Microsoft 365 或 Office 365 網域的協助。*</span><span class="sxs-lookup"><span data-stu-id="364b6-213">*Please review [Get help with Microsoft 365 or Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Microsoft 365 or Office 365 organizations.*</span></span>

<span data-ttu-id="364b6-214">例如：test@customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="364b6-214">For example: test@customers.adatum.biz</span></span>

![基礎網域啟用頁面的螢幕擷取畫面](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a><span data-ttu-id="364b6-216">在客戶租使用者中註冊子功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="364b6-216">Register a subdomain name in a customer tenant</span></span>

<span data-ttu-id="364b6-217">您必須為每個客戶建立唯一的子功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="364b6-217">You will need to create a unique subdomain name for every customer.</span></span> <span data-ttu-id="364b6-218">在此範例中，我們會建立一個子域sbc1.customers.adatum.biz租使用者中的子域，其預設功能變數名稱是 woodgrovebank.us。</span><span class="sxs-lookup"><span data-stu-id="364b6-218">In this example, we will create a subdomain sbc1.customers.adatum.biz in a tenant with the default domain name woodgrovebank.us.</span></span>

<span data-ttu-id="364b6-219">**下方所有動作都位在客戶租使用者中。**</span><span class="sxs-lookup"><span data-stu-id="364b6-219">**All actions below are in the customer tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a><span data-ttu-id="364b6-220">確定您擁有客戶租使用者的適當許可權</span><span class="sxs-lookup"><span data-stu-id="364b6-220">Ensure that you have appropriate rights in the customer tenant</span></span>

<span data-ttu-id="364b6-221">如果您是以全域系統管理員的名名，在 Microsoft 365 系統管理中心內，才能新增網域。</span><span class="sxs-lookup"><span data-stu-id="364b6-221">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="364b6-222">若要驗證您擁有的角色，請前往 Microsoft 365 系統管理中心 (、前往使用者作用中使用者，然後確認您擁有 https://portal.office.com)   >  全域系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="364b6-222">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="364b6-223">有關系統管理員角色以及如何在 Microsoft 365 或 Office 365 中指派角色詳細資訊，請參閱關於 [系統管理員角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。</span><span class="sxs-lookup"><span data-stu-id="364b6-223">For more information about admin roles and how to assign a role in Microsoft 365 or Office 365, see [About admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a><span data-ttu-id="364b6-224">新增子域至客戶租使用者並驗證</span><span class="sxs-lookup"><span data-stu-id="364b6-224">Add a subdomain to the customer tenant and verify it</span></span>
1. <span data-ttu-id="364b6-225">在 Microsoft 365 系統管理中心，請前往設定  >  **網域**  >  **新增網域**。</span><span class="sxs-lookup"><span data-stu-id="364b6-225">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="364b6-226">在 **輸入您擁有網域的** 方塊中，輸入此租使用者子域的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="364b6-226">In the **Enter a domain you own** box, type the FQDN of the subdomain for this tenant.</span></span> <span data-ttu-id="364b6-227">在下面的範例中，子域是sbc1.customers.adatum.biz。</span><span class="sxs-lookup"><span data-stu-id="364b6-227">In the example below, the subdomain is sbc1.customers.adatum.biz.</span></span>

    ![新增網域頁面的螢幕擷取畫面](media/direct-routing-5-sbc-add-customer-domain.png)

3. <span data-ttu-id="364b6-229">按一下 [ **下一步**。</span><span class="sxs-lookup"><span data-stu-id="364b6-229">Click **Next**.</span></span>
4. <span data-ttu-id="364b6-230">FQDN 從未在租使用者中註冊過。</span><span class="sxs-lookup"><span data-stu-id="364b6-230">The FQDN has never been registered in the tenant.</span></span> <span data-ttu-id="364b6-231">在下一個步驟中，您將必須驗證網域。</span><span class="sxs-lookup"><span data-stu-id="364b6-231">In the next step, you will need to verify the domain.</span></span> <span data-ttu-id="364b6-232">請 **改為選取新增 TXT 記錄**。</span><span class="sxs-lookup"><span data-stu-id="364b6-232">Select **Add a TXT record instead**.</span></span> 

    ![驗證網域頁面的螢幕擷取畫面](media/direct-routing-6-sbc-verify-customer-domain.png)

5. <span data-ttu-id="364b6-234">按 **[下** 一步，然後記下為了驗證功能變數名稱而產生的 TXT 值。</span><span class="sxs-lookup"><span data-stu-id="364b6-234">Click **Next**, and note the TXT value generated to verify the domain name.</span></span>

    ![在驗證網域頁面上的文字記錄螢幕擷取畫面](media/direct-routing-7-sbc-verify-domain-txt.png)

6. <span data-ttu-id="364b6-236">使用電信公司 DNS 主機服務提供者中上一個步驟中的值來建立 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="364b6-236">Create the TXT record with the value from the previous step in carrier's DNS hosting provider.</span></span>

    ![顯示建立 TXT 記錄的螢幕擷取畫面](media/direct-routing-8-sbc-txt-record.png)

    <span data-ttu-id="364b6-238">詳情請參閱在任何 DNS 主機服務提供者建立 [DNS 記錄](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)。</span><span class="sxs-lookup"><span data-stu-id="364b6-238">For more information, refer to [Create DNS records at any DNS hosting provider](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span></span>

7. <span data-ttu-id="364b6-239">返回客戶的 Microsoft 365 系統管理中心，然後按一下 [ **驗證**。</span><span class="sxs-lookup"><span data-stu-id="364b6-239">Go back to the customer's Microsoft 365 admin center and click **Verify**.</span></span> 
8. <span data-ttu-id="364b6-240">在下一頁中，選取 **[我將** 自己新增 DNS 記錄，然後按一下 [下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="364b6-240">On the next page, select **I'll add the DNS records myself** and click **Next**.</span></span>

    ![更新 DNS 設定頁面上選項的螢幕擷取畫面](media/direct-routing-9-sbc-update-dns.png)

9. <span data-ttu-id="364b6-242">在 [ **選擇您的線上服務** ; 頁面上，清除所有選項，然後按一下 [下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="364b6-242">On the **Choose your online services** page, clear all options and click **Next**.</span></span>

    ![選擇您的線上服務頁面的螢幕擷取畫面](media/direct-routing-10-sbc-choose-services.png)

10. <span data-ttu-id="364b6-244">按一下 **[更新** DNS 設定 **頁面的完成** 時間。</span><span class="sxs-lookup"><span data-stu-id="364b6-244">Click **Finish** on the **Update DNS settings** page.</span></span>

    ![更新 DNS 設定頁面的螢幕擷取畫面](media/direct-routing-11-sbc-update-dns-finish.png)

11. <span data-ttu-id="364b6-246">請確保已設定 **完成狀態**。</span><span class="sxs-lookup"><span data-stu-id="364b6-246">Ensure that the status is **Setup complete**.</span></span> 
    
    ![顯示安裝完成狀態的頁面螢幕擷取畫面](media/direct-routing-12-sbc-setup-complete.png)
    
> [!NOTE]
> <span data-ttu-id="364b6-248">個別用戶端的基本 URL 和子域必須位於相同的租使用者上，才能新增直接 _路由主幹_ 。</span><span class="sxs-lookup"><span data-stu-id="364b6-248">The base URL and the subdomain for the individual client have to be on the same tenant to enable you to add a _direct route_ trunk.</span></span>

### <a name="activate-the-subdomain-name"></a><span data-ttu-id="364b6-249">啟動子功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="364b6-249">Activate the subdomain name</span></span>

<span data-ttu-id="364b6-250">註冊功能變數名稱之後，您必須新增至少一個使用者，並指派 SIP 位址的 SIP 位址 FQDN 部分，且該位址符合客戶租使用者中已建立之子域，以啟用該功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="364b6-250">After you register a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created subdomain in the customer tenant.</span></span> <span data-ttu-id="364b6-251">在子域啟用之後，使用者可能會撤銷授權 (最多可能需要 24 小時的時間) 。</span><span class="sxs-lookup"><span data-stu-id="364b6-251">License can be revoked from user after the subdomain activation (it can take up to 24 hours).</span></span>

<span data-ttu-id="364b6-252">*如需在 [Microsoft 365 或 Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 組織中新增使用者之詳細資訊，請參閱取得 Microsoft 365 或 Office 365 網域的協助。*</span><span class="sxs-lookup"><span data-stu-id="364b6-252">*Please review [Get help with Microsoft 365 or Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Microsoft 365 or Office 365 organizations.*</span></span>

<span data-ttu-id="364b6-253">例如：test@sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="364b6-253">For example: test@sbc1.customers.adatum.biz</span></span>

![子域頁面的啟用螢幕擷取畫面](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a><span data-ttu-id="364b6-255">建立主幹及提供使用者</span><span class="sxs-lookup"><span data-stu-id="364b6-255">Create a trunk and provision users</span></span>

<span data-ttu-id="364b6-256">在直接路由的初次發行中，Microsoft 要求每個使用 New-CSOnlinePSTNGateway 的客戶租使用者 () 新增一條主幹。</span><span class="sxs-lookup"><span data-stu-id="364b6-256">With the initial release of Direct Routing, Microsoft required a trunk to be added to each served tenant (customer tenant) using New-CSOnlinePSTNGateway.</span></span>

<span data-ttu-id="364b6-257">不過，有兩個原因未達最佳結果：</span><span class="sxs-lookup"><span data-stu-id="364b6-257">However, this has not proved optimal for two reasons:</span></span>
 
- <span data-ttu-id="364b6-258">**負荷管理**。</span><span class="sxs-lookup"><span data-stu-id="364b6-258">**Overhead management**.</span></span> <span data-ttu-id="364b6-259">例如，將 SBC 卸去或耗盡，會變更某些參數，例如啟用或停用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="364b6-259">Offloading or draining an SBC, for example, changes some parameters, like enabling or disabling media bypass.</span></span> <span data-ttu-id="364b6-260">變更埠需要以執行 Set-CSOnlinePSTNGateway (，來變更多個租使用者中的參數) ，但實際上是同一個 SBC。</span><span class="sxs-lookup"><span data-stu-id="364b6-260">Changing the port requires changing parameters in multiple tenants (by running Set-CSOnlinePSTNGateway), but it is in fact the same SBC.</span></span> 

-  <span data-ttu-id="364b6-261">**負荷處理**。</span><span class="sxs-lookup"><span data-stu-id="364b6-261">**Overhead processing**.</span></span> <span data-ttu-id="364b6-262">收集及監控主幹健康情況資料 - 從多個邏輯主幹收集的 SIP 選項，實際上，同一個 SBC 和相同的實體主幹，會降低路由資料的處理速度。</span><span class="sxs-lookup"><span data-stu-id="364b6-262">Gathering and monitoring trunk health data - SIP options collected from multiple logical trunks that are, in reality, the same SBC and the same physical trunk, slows down processing of the routing data.</span></span>
 
<span data-ttu-id="364b6-263">根據這項意見回饋，Microsoft 帶來新的邏輯來為客戶租使用者提供主幹。</span><span class="sxs-lookup"><span data-stu-id="364b6-263">Based on this feedback, Microsoft is bringing in a new logic to provision the trunks for the customer tenants.</span></span>

<span data-ttu-id="364b6-264">已推出兩個新實體：</span><span class="sxs-lookup"><span data-stu-id="364b6-264">Two new entities were introduced:</span></span>
-    <span data-ttu-id="364b6-265">使用 New-CSOnlinePSTNGateway 命令在電信公司租使用者中註冊的電信公司主幹，例如 New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true。</span><span class="sxs-lookup"><span data-stu-id="364b6-265">A carrier trunk registered in the carrier tenant using the command New-CSOnlinePSTNGateway, for example New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true.</span></span>

-    <span data-ttu-id="364b6-266">不需要註冊的衍生主幹。</span><span class="sxs-lookup"><span data-stu-id="364b6-266">A derived trunk, that does not require registration.</span></span> <span data-ttu-id="364b6-267">它只是從電信公司主幹中新增的所需的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="364b6-267">It is simply a desired host name added in from of the carrier trunk.</span></span> <span data-ttu-id="364b6-268">它會從電信商主幹衍生其所有組設定參數。</span><span class="sxs-lookup"><span data-stu-id="364b6-268">It derives all of its configuration parameters from the carrier trunk.</span></span> <span data-ttu-id="364b6-269">衍生的主幹不需要在 PowerShell 中建立，而電信業者主幹的關聯是以 FQDN 名稱為基礎 (請參閱下方) 。</span><span class="sxs-lookup"><span data-stu-id="364b6-269">The derived trunk doesn't need to be created in PowerShell, and the association with the carrier trunk is based on the FQDN name (see details below).</span></span>

<span data-ttu-id="364b6-270">**提供邏輯和範例**</span><span class="sxs-lookup"><span data-stu-id="364b6-270">**Provisioning logic and example**</span></span>

-    <span data-ttu-id="364b6-271">電信公司只需要使用 (命令，在電信) 線中設定及管理單一Set-CSOnlinePSTNGateway線。</span><span class="sxs-lookup"><span data-stu-id="364b6-271">Carriers only need to set up and manage a single trunk  (carrier trunk in the carrier domain), using the Set-CSOnlinePSTNGateway command.</span></span> <span data-ttu-id="364b6-272">在上例中，它adatum.biz;</span><span class="sxs-lookup"><span data-stu-id="364b6-272">In the example above it is adatum.biz;</span></span>
-    <span data-ttu-id="364b6-273">在客戶租使用者中，電信公司只需要將衍生的主幹 FQDN 新增到使用者的語音路由策略。</span><span class="sxs-lookup"><span data-stu-id="364b6-273">In the customer tenant, the carrier need only to add the derived trunk FQDN to the voice routing policies of the users.</span></span> <span data-ttu-id="364b6-274">不需要為主幹New-CSOnlinePSTNGateway線。</span><span class="sxs-lookup"><span data-stu-id="364b6-274">There is no need to run New-CSOnlinePSTNGateway for a trunk.</span></span>
-    <span data-ttu-id="364b6-275">如名稱所示，衍生的主幹會繼承或衍生電信公司主幹的所有設定參數。</span><span class="sxs-lookup"><span data-stu-id="364b6-275">The derived trunk, as the name suggests, inherits or derives all the configuration parameters from the carrier trunk.</span></span> <span data-ttu-id="364b6-276">例子：</span><span class="sxs-lookup"><span data-stu-id="364b6-276">Examples:</span></span>
-    <span data-ttu-id="364b6-277">Customers.adatum.biz – 需要在電信公司租使用者中建立之電信公司主幹。</span><span class="sxs-lookup"><span data-stu-id="364b6-277">Customers.adatum.biz – the carrier trunk which needs to be created in the carrier tenant.</span></span>
-    <span data-ttu-id="364b6-278">Sbc1.customers.adatum.biz – 客戶租使用者中的衍生主幹，不需要在 PowerShell 中建立。</span><span class="sxs-lookup"><span data-stu-id="364b6-278">Sbc1.customers.adatum.biz – the derived trunk in a customer tenant that does not need to be created in PowerShell.</span></span>  <span data-ttu-id="364b6-279">只要在線上語音路由政策中，即可在客戶租使用者中新增衍生主幹名稱，而不必建立。</span><span class="sxs-lookup"><span data-stu-id="364b6-279">You can simply add the name of the derived trunk in the customer tenant in the online voice routing policy without creating it.</span></span>
-   <span data-ttu-id="364b6-280">電信公司必須設定 DNS 記錄，以解析衍生的主幹 FQDN 到電信公司 SBC IP 位址。</span><span class="sxs-lookup"><span data-stu-id="364b6-280">Carrier will need to setup DNS record resolving derived trunk FQDN to carrier SBC ip address.</span></span>

-    <span data-ttu-id="364b6-281">在電信電信 (租使用者) 進行的任何變更，都會自動適用于衍生主幹。</span><span class="sxs-lookup"><span data-stu-id="364b6-281">Any changes made on a carrier trunk (on carrier tenant) is automatically applied to derived trunks.</span></span> <span data-ttu-id="364b6-282">例如，電信公司可以變更電信公司主幹上的 SIP 埠，這項變更適用于所有衍生的主幹。</span><span class="sxs-lookup"><span data-stu-id="364b6-282">For example, carriers can change an SIP port on the carrier trunk, and this change applies to all derived trunks.</span></span> <span data-ttu-id="364b6-283">設定主幹的新邏輯簡化了管理，因為不需要前往每個租使用者，也不需要變更每一條主幹上的參數。</span><span class="sxs-lookup"><span data-stu-id="364b6-283">New logic to configure the trunks simplifies the management as you don't need to go to every tenant and change the parameter on every trunk.</span></span>
-    <span data-ttu-id="364b6-284">選項只會送到電信公司主幹 FQDN。</span><span class="sxs-lookup"><span data-stu-id="364b6-284">The options are sent only to the carrier trunk FQDN.</span></span> <span data-ttu-id="364b6-285">電信公司主幹的健康情況狀態會適用于所有衍生主幹，並用於路由決策。</span><span class="sxs-lookup"><span data-stu-id="364b6-285">The health status of the carrier trunk is applied to all derived trunks and is used for routing decisions.</span></span> <span data-ttu-id="364b6-286">進一瞭解更多直接 [路由選項](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot)。</span><span class="sxs-lookup"><span data-stu-id="364b6-286">Find out more about [Direct Routing options](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot).</span></span>
-    <span data-ttu-id="364b6-287">電信公司可以消耗電信公司主幹的消耗，而所有衍生的主幹也會耗盡。</span><span class="sxs-lookup"><span data-stu-id="364b6-287">The carrier can drain the carrier trunk, and all derived trunks will be drained as well.</span></span> 
 

<span data-ttu-id="364b6-288">**從先前的模型移往電信運輸主幹**</span><span class="sxs-lookup"><span data-stu-id="364b6-288">**Migration from the previous model to the carrier trunk**</span></span>
 
<span data-ttu-id="364b6-289">針對從電信公司託管模型的目前執行移向新模型，電信公司需要重新建立客戶租使用者主幹。</span><span class="sxs-lookup"><span data-stu-id="364b6-289">For migration from the current implementation of the carrier hosted model to the new model, the carriers will need to reconfigure the trunks for customer tenants.</span></span> <span data-ttu-id="364b6-290">使用線路離開電信Remove-CSOnlinePSTNGateway (租使用者中的主幹，移除客戶租使用者中的) -</span><span class="sxs-lookup"><span data-stu-id="364b6-290">Remove the trunks from the customer tenants using Remove-CSOnlinePSTNGateway (leaving the trunk in the carrier tenant)-</span></span>

<span data-ttu-id="364b6-291">我們強烈建議您儘快移移至新的解決方案，我們將加強使用電信號和衍生主幹模型的監控與部署功能。</span><span class="sxs-lookup"><span data-stu-id="364b6-291">We highly encourage migrating to the new solution as soon as possible as we will be enhancing monitoring and provisioning using the carrier and derived trunk model.</span></span>
 

<span data-ttu-id="364b6-292">請參閱 [SBC](#deploy-and-configure-the-sbc) 廠商有關在連絡人標頭中傳送子域之 FQDN 名稱的指示。</span><span class="sxs-lookup"><span data-stu-id="364b6-292">Please refer to the [SBC vendor instructions](#deploy-and-configure-the-sbc) on configuring sending the FQDN name of subdomains in the Contact header.</span></span>

## <a name="considerations-for-setting-up-muti-tenant-failover"></a><span data-ttu-id="364b6-293">設定靜音租使用者容錯移轉的考慮事項</span><span class="sxs-lookup"><span data-stu-id="364b6-293">Considerations for setting up muti-tenant failover</span></span> 

<span data-ttu-id="364b6-294">若要為多租使用者環境設定容錯移轉，您必須執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="364b6-294">To set up failover for a multi-tenant environment, you'll need to do the following:</span></span>

- <span data-ttu-id="364b6-295">針對每個租使用者，為兩個不同的 SBC 新增 FQDN。</span><span class="sxs-lookup"><span data-stu-id="364b6-295">For each tenant, add the FQDNs for two different SBCs.</span></span>  <span data-ttu-id="364b6-296">例如：</span><span class="sxs-lookup"><span data-stu-id="364b6-296">For example:</span></span>

   <span data-ttu-id="364b6-297">customer1.sbc1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="364b6-297">customer1.sbc1.contoso.com</span></span> <br>
   <span data-ttu-id="364b6-298">customer1.sbc2.contoso.com</span><span class="sxs-lookup"><span data-stu-id="364b6-298">customer1.sbc2.contoso.com</span></span> <br>

- <span data-ttu-id="364b6-299">在使用者的線上語音路由策略中，指定兩個 SBC。</span><span class="sxs-lookup"><span data-stu-id="364b6-299">In the Online Voice Routing policies of the users, specify both SBCs.</span></span>  <span data-ttu-id="364b6-300">如果某個 SBC 失敗，路由策略會路由呼叫到第二個 SBC。</span><span class="sxs-lookup"><span data-stu-id="364b6-300">If one SBC fails, the routing policy will route calls to the second SBC.</span></span>


## <a name="see-also"></a><span data-ttu-id="364b6-301">另請參閱</span><span class="sxs-lookup"><span data-stu-id="364b6-301">See also</span></span>

[<span data-ttu-id="364b6-302">規劃直接路由</span><span class="sxs-lookup"><span data-stu-id="364b6-302">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="364b6-303">設定直接路由</span><span class="sxs-lookup"><span data-stu-id="364b6-303">Configure Direct Routing</span></span>](direct-routing-configure.md)
