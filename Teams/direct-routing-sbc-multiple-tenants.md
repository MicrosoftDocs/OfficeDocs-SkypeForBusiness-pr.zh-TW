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
description: 瞭解如何在 SBC 中設定一個會話 (，) Microsoft 合作夥伴和/或 PSTN 電信公司的多個租使用者。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 742b02709585e9a25b170bc99aab3d1939d63f10
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096529"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a><span data-ttu-id="3c1cd-103">設定多個租用戶的工作階段邊界控制器</span><span class="sxs-lookup"><span data-stu-id="3c1cd-103">Configure a Session Border Controller for multiple tenants</span></span>

<span data-ttu-id="3c1cd-104">直接路由支援將一個會話邊界控制器 (SBC) 服務多個租使用者。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-104">Direct Routing supports configuring one Session Border Controller (SBC) to serve multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="3c1cd-105">此案例專為 Microsoft 合作夥伴和/或 PSTN 電信公司所設計，本文稍後稱為電信公司。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-105">This scenario is designed for Microsoft partners and/or PSTN carriers, referred to as carriers later in this document.</span></span> <span data-ttu-id="3c1cd-106">電信業者將傳送至 Microsoft Teams 的電話語音銷售給客戶。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-106">A carrier sells telephony services delivered to Microsoft Teams to their customers.</span></span> 

<span data-ttu-id="3c1cd-107">電信公司：</span><span class="sxs-lookup"><span data-stu-id="3c1cd-107">A carrier:</span></span>
- <span data-ttu-id="3c1cd-108">在資料中心部署及管理 SBC (客戶不需要執行 SBC，而且他們從 Teams 用戶端用戶端的電信業者) 。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-108">Deploys and manages an SBC in their datacenter (customers do not need to implement an SBC, and they receive telephony services from the carrier in the Teams client).</span></span>
- <span data-ttu-id="3c1cd-109">將 SBC 與多個租使用者相互連接。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-109">Interconnects the SBC to multiple tenants.</span></span>
- <span data-ttu-id="3c1cd-110">為客戶提供 PSTN 服務。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-110">Provides PSTN services to customers.</span></span>
- <span data-ttu-id="3c1cd-111">管理電話品質端對端。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-111">Manages call quality end to end.</span></span>
- <span data-ttu-id="3c1cd-112">PSTN 服務另行收費。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-112">Charges separately for PSTN services.</span></span>

<span data-ttu-id="3c1cd-113">Microsoft 不會管理電信公司。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-113">Microsoft does not manage carriers.</span></span> <span data-ttu-id="3c1cd-114">Microsoft 提供 PBX (Microsoft Phone System) Teams 用戶端。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-114">Microsoft offers a PBX (Microsoft Phone System) and a Teams client.</span></span> <span data-ttu-id="3c1cd-115">Microsoft 也會認證可與 Microsoft Phone 系統一起使用的電話，並認證 SBCs。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-115">Microsoft also certifies phones, and certifies SBCs that can be used with the Microsoft Phone System.</span></span> <span data-ttu-id="3c1cd-116">選擇電信業者之前，請確定您的選擇具有經過認證的 SBC，並可以端對端管理語音品質。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-116">Before choosing a carrier, please ensure that your choice has a certified SBC and can manage voice quality end to end.</span></span>

<span data-ttu-id="3c1cd-117">以下是設定案例的技術實現步驟。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-117">The following are the technical implementation steps to configure the scenario.</span></span>

<span data-ttu-id="3c1cd-118">**僅適用于電信公司：**</span><span class="sxs-lookup"><span data-stu-id="3c1cd-118">**Carrier only:**</span></span>
1. <span data-ttu-id="3c1cd-119">部署 SBC，然後根據認證 SBC 廠商的指示，針對託管案例[設定 SBC。](#deploy-and-configure-the-sbc)</span><span class="sxs-lookup"><span data-stu-id="3c1cd-119">Deploy the SBC and configure it for the hosting scenario according to the [instructions from the certified SBC vendors](#deploy-and-configure-the-sbc).</span></span>
2. <span data-ttu-id="3c1cd-120">在電信業者租使用者中註冊基本功能變數名稱，並索取萬用字元憑證。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-120">Register a base domain name in the carrier tenant and request a wildcard certificate.</span></span>
3. <span data-ttu-id="3c1cd-121">針對每個客戶註冊子域，這是基本網域的一部分。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-121">Register a subdomain for every customer, which is part of the base domain.</span></span>

<span data-ttu-id="3c1cd-122">**具有客戶全域系統管理員的電信公司：**</span><span class="sxs-lookup"><span data-stu-id="3c1cd-122">**Carrier with a Customer Global Administrator:**</span></span>
1. <span data-ttu-id="3c1cd-123">將子功能變數名稱稱新增到客戶租使用者。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-123">Add the subdomain name to the customer tenant.</span></span>
2. <span data-ttu-id="3c1cd-124">啟用子功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-124">Activate the subdomain name.</span></span>
3. <span data-ttu-id="3c1cd-125">設定從電信電信企業到客戶租使用者的主幹，並設定使用者。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-125">Configure the trunk from the carrier to the customer tenant and provision users.</span></span>

<span data-ttu-id="3c1cd-126">*請確定您瞭解 DNS 基本功能，以及 Microsoft 365 或 Office 365 中的功能變數名稱管理方式。請 [進一步查看取得 Microsoft 365 或 Office 365 網](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 域的協助。*</span><span class="sxs-lookup"><span data-stu-id="3c1cd-126">*Please make sure you understand DNS basics and how the domain name is managed in Microsoft 365 or Office 365. Review [Get help with Microsoft 365 or Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) before proceeding further.*</span></span>

## <a name="deploy-and-configure-the-sbc"></a><span data-ttu-id="3c1cd-127">部署及設定 SBC</span><span class="sxs-lookup"><span data-stu-id="3c1cd-127">Deploy and configure the SBC</span></span>

<span data-ttu-id="3c1cd-128">如需如何針對 SBC 主機案例部署及設定 SBC 的詳細步驟，請參閱 SBC 廠商的檔。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-128">For the detailed steps on how to deploy and configure SBCs for an SBC hosting scenario, please refer to the SBC vendor's documentation.</span></span>

- <span data-ttu-id="3c1cd-129">**音訊代碼：**[直接路由組](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)記，SBC 主機案例的組式，描述為「將 AudioCodes SBC 連接到 Microsoft Teams 直接路由主機管理模型組組附注」。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-129">**AudioCodes:** [Direct Routing Configuration notes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), the configuration of the SBC hosting scenario described in "Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note."</span></span> 
- <span data-ttu-id="3c1cd-130">**Oracle：**[直接路由群組原則附注](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)，SBC 主機案例的組塊會于「Microsoft」一節中說明。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-130">**Oracle:** [Direct Routing Configuration notes](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html), the configuration of the SBC hosting scenario is described in the "Microsoft" section.</span></span> 
- <span data-ttu-id="3c1cd-131">**功能區通訊：** 請參閱功能區通訊 [SBC 核心 Microsoft Teams](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe)組組指南，以瞭解如何設定功能區核心系列 SBC 的檔，並參閱此頁面功能區最佳做法 - 設定 Microsoft Teams 直接路由 [SBC Edge](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)的電信業者</span><span class="sxs-lookup"><span data-stu-id="3c1cd-131">**Ribbon Communications:**  Please refer to the [Ribbon Communications SBC Core Microsoft Teams Configuration Guide](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) for documentation on how to configure Ribbon Core Series SBCs and to this page [Ribbon Best Practice - Configuring Carriers for Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)</span></span>
- <span data-ttu-id="3c1cd-132">**TE-Systems (anynode) ：**  請在 [TE-Systems Community](https://community.te-systems.de/) 頁面上註冊，以瞭解如何為多個租使用者設定 anynode SBC 的檔和範例。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-132">**TE-Systems (anynode):**  Please register on the [TE-Systems Community page](https://community.te-systems.de/) for documentation and examples on how to configure anynode SBC for multiple tenants.</span></span>
- <span data-ttu-id="3c1cd-133">**Metaswitch：**  請在 [Metaswitch 社群](https://manuals.metaswitch.com/MAN39555) 頁面上註冊，以瞭解如何為多個租使用者啟用 Perimeta SBC 的檔。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-133">**Metaswitch:**  Please register on the [Metaswitch Community page](https://manuals.metaswitch.com/MAN39555) for documentation on how to enable Perimeta SBC for multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="3c1cd-134">請注意如何設定「連絡人」標題。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-134">Please pay attention to how to configure the "Contact" header.</span></span> <span data-ttu-id="3c1cd-135">連絡人標題是用來在傳入的邀請訊息上尋找客戶租使用者。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-135">The Contact header is used to find the customer tenant on the incoming invite message.</span></span> 

## <a name="register-a-base-domain-and-subdomains"></a><span data-ttu-id="3c1cd-136">註冊基本網域和子域</span><span class="sxs-lookup"><span data-stu-id="3c1cd-136">Register a base domain and subdomains</span></span>

<span data-ttu-id="3c1cd-137">針對託管案例，您需要建立：</span><span class="sxs-lookup"><span data-stu-id="3c1cd-137">For the hosting scenario, you need to create:</span></span>
- <span data-ttu-id="3c1cd-138">電信業者擁有的一個基礎功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-138">One base domain name owned by the carrier.</span></span>
- <span data-ttu-id="3c1cd-139">這是每個客戶租使用者中基本功能變數名稱的一部分子域。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-139">A subdomain that is part of the base domain name in every customer tenant.</span></span>

<span data-ttu-id="3c1cd-140">在下列範例中：</span><span class="sxs-lookup"><span data-stu-id="3c1cd-140">In the following example:</span></span>
- <span data-ttu-id="3c1cd-141">Adatum 是一家電信業者，提供網際網路和電話語音，為數個客戶提供服務。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-141">Adatum is a carrier that serves several customers by providing Internet and telephony services.</span></span>
- <span data-ttu-id="3c1cd-142">Woodgrove Bank、Contoso 和 Adventure Works 是三個擁有 Microsoft 365 或 Office 365 網域，但從 Adatum 接收電話語音的客戶。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-142">Woodgrove Bank, Contoso, and Adventure Works are three customers that have Microsoft 365 or Office 365 domains but receive the telephony services from Adatum.</span></span>

<span data-ttu-id="3c1cd-143">當傳送邀請給Microsoft 365 或 Office 365 時，子域必須符合為客戶所配置的主幹 FQDN 名稱，以及連絡人標題中的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-143">Subdomains **MUST** match the FQDN name of the trunk that will be configured for the customer and the FQDN in the Contact header when sending the Invite to Microsoft 365 or Office 365.</span></span> 

<span data-ttu-id="3c1cd-144">當通話抵達 Microsoft 365 或 Office 365 直接路由介面時，介面會使用連絡人標頭來尋找應該查看使用者的租使用者。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-144">When a call arrives at the Microsoft 365 or Office 365 Direct Routing interface, the interface uses the Contact header to find the tenant where the user should be looked up.</span></span> <span data-ttu-id="3c1cd-145">直接路由不會在邀請上使用電話號碼尋找功能，因為有些客戶可能擁有非 DID 號碼，可能會與多個租使用者重迭。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-145">Direct Routing does not use phone number lookup on the Invite, as some customers might have non-DID numbers that can overlap in several tenants.</span></span> <span data-ttu-id="3c1cd-146">因此，必須輸入連絡人標題中的 FQDN 名稱，才能識別確切的租使用者，才能根據電話號碼來查看使用者。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-146">Therefore, the FQDN name in the Contact header is required to identify the exact tenant to look up the user by the phone number.</span></span>

<span data-ttu-id="3c1cd-147">*如需在  [Microsoft 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 或 Office 365 組織中建立功能變數名稱之詳細資訊，請參閱取得 Office 365 網域的協助。*</span><span class="sxs-lookup"><span data-stu-id="3c1cd-147">*Please review  [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about creating domain names in Microsoft 365 or Office 365 organizations.*</span></span>

<span data-ttu-id="3c1cd-148">下圖摘要說明基本網域、子域和連絡人標題的需求。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-148">The following diagram summarizes the requirements to base domain, subdomains, and Contact header.</span></span>

![顯示網域和連絡人標題需求的圖表](media/direct-routing-1-sbc-requirements.png)

<span data-ttu-id="3c1cd-150">SBC 需要憑證來驗證連接。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-150">The SBC requires a certificate to authenticate the connections.</span></span> <span data-ttu-id="3c1cd-151">針對 SBC 主機案例，電信業者需要要求具有 CN 和/或 SAN .base_domain (的憑證，例如 *\* \* .customers.adatum.biz) 。*</span><span class="sxs-lookup"><span data-stu-id="3c1cd-151">For the SBC hosting scenario, the carrier needs to request a certificate with CN and/or SAN *\*.base_domain (for example, \*.customers.adatum.biz)*.</span></span> <span data-ttu-id="3c1cd-152">此憑證可用來驗證從單一 SBC 送達多個租使用者的連接。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-152">This certificate can be used to authenticate connections to multiple tenants served from a single SBC.</span></span>


<span data-ttu-id="3c1cd-153">下表是一組配置的範例。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-153">The following table is an example of one configuration.</span></span>


|<span data-ttu-id="3c1cd-154">新功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="3c1cd-154">New domain name</span></span> |<span data-ttu-id="3c1cd-155">類型</span><span class="sxs-lookup"><span data-stu-id="3c1cd-155">Type</span></span>|<span data-ttu-id="3c1cd-156">註冊</span><span class="sxs-lookup"><span data-stu-id="3c1cd-156">Registered</span></span>  |<span data-ttu-id="3c1cd-157">SBC 的憑證 CN/SAN</span><span class="sxs-lookup"><span data-stu-id="3c1cd-157">Certificate CN/SAN for SBC</span></span>  |<span data-ttu-id="3c1cd-158">範例中的租使用者預設網域</span><span class="sxs-lookup"><span data-stu-id="3c1cd-158">Tenant default domain in the example</span></span>  |<span data-ttu-id="3c1cd-159">將通話傳送給使用者時，SBC 必須在連絡人標題中顯示 FQDN 名稱</span><span class="sxs-lookup"><span data-stu-id="3c1cd-159">FQDN name that SBC must present in the Contact header when sending calls to users</span></span>|
|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="3c1cd-160">customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="3c1cd-160">customers.adatum.biz</span></span>|    <span data-ttu-id="3c1cd-161">基地</span><span class="sxs-lookup"><span data-stu-id="3c1cd-161">Base</span></span>     |     <span data-ttu-id="3c1cd-162">在電信租使用者中</span><span class="sxs-lookup"><span data-stu-id="3c1cd-162">In carrier tenant</span></span>  |    <span data-ttu-id="3c1cd-163">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="3c1cd-163">\*.customers.adatum.biz</span></span>  |   <span data-ttu-id="3c1cd-164">adatum.biz</span><span class="sxs-lookup"><span data-stu-id="3c1cd-164">adatum.biz</span></span>      |<span data-ttu-id="3c1cd-165">NA，這是服務租使用者，沒有使用者</span><span class="sxs-lookup"><span data-stu-id="3c1cd-165">NA, this is a service tenant, no users</span></span> |
|<span data-ttu-id="3c1cd-166">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="3c1cd-166">sbc1.customers.adatum.biz</span></span>|    <span data-ttu-id="3c1cd-167">子域</span><span class="sxs-lookup"><span data-stu-id="3c1cd-167">Subdomain</span></span>  |    <span data-ttu-id="3c1cd-168">在客戶租使用者中</span><span class="sxs-lookup"><span data-stu-id="3c1cd-168">In a customer tenant</span></span>  |    <span data-ttu-id="3c1cd-169">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="3c1cd-169">\*.customers.adatum.biz</span></span>  | <span data-ttu-id="3c1cd-170">woodgrovebank.us</span><span class="sxs-lookup"><span data-stu-id="3c1cd-170">woodgrovebank.us</span></span>  |  <span data-ttu-id="3c1cd-171">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="3c1cd-171">sbc1.customers.adatum.biz</span></span>|
|<span data-ttu-id="3c1cd-172">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="3c1cd-172">sbc2.customers.adatum.biz</span></span>  |   <span data-ttu-id="3c1cd-173">子域</span><span class="sxs-lookup"><span data-stu-id="3c1cd-173">Subdomain</span></span> | <span data-ttu-id="3c1cd-174">在客戶租使用者中</span><span class="sxs-lookup"><span data-stu-id="3c1cd-174">In a customer tenant</span></span>   |   <span data-ttu-id="3c1cd-175">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="3c1cd-175">\*.customers.adatum.biz</span></span>   |<span data-ttu-id="3c1cd-176">contoso.com</span><span class="sxs-lookup"><span data-stu-id="3c1cd-176">contoso.com</span></span>   |<span data-ttu-id="3c1cd-177">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="3c1cd-177">sbc2.customers.adatum.biz</span></span> |
|<span data-ttu-id="3c1cd-178">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="3c1cd-178">sbc3.customers.adatum.biz</span></span> |   <span data-ttu-id="3c1cd-179">子域</span><span class="sxs-lookup"><span data-stu-id="3c1cd-179">Subdomain</span></span> | <span data-ttu-id="3c1cd-180">在客戶租使用者中</span><span class="sxs-lookup"><span data-stu-id="3c1cd-180">In a customer tenant</span></span> |   <span data-ttu-id="3c1cd-181">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="3c1cd-181">\*.customers.adatum.biz</span></span>  |  <span data-ttu-id="3c1cd-182">adventureworks.com</span><span class="sxs-lookup"><span data-stu-id="3c1cd-182">adventureworks.com</span></span> | <span data-ttu-id="3c1cd-183">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="3c1cd-183">sbc3.customers.adatum.biz</span></span> |
||         |         |         |         |         |

<span data-ttu-id="3c1cd-184">若要設定基本和子域，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-184">To configure the base and subdomains, please follow the steps described below.</span></span> <span data-ttu-id="3c1cd-185">在範例中，我們將在 Woodgrove Bank 租使用者 (customers.adatum.biz) 中設定基本功能變數名稱和 (sbc1.customers.adatum.biz 子域) 。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-185">In the example, we will configure a base domain name (customers.adatum.biz) and a subdomain for one customer (sbc1.customers.adatum.biz in Woodgrove Bank tenant).</span></span>

> [!NOTE]
> <span data-ttu-id="3c1cd-186">使用 sbcX.customers.adatum.biz 在電信租使用者中啟用語音。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-186">Use sbcX.customers.adatum.biz to enable voice in the carrier tenant.</span></span> <span data-ttu-id="3c1cd-187">sbcX 可以是任何唯一且有效的 Alphanumeric hostname。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-187">sbcX can be any unique and valid alphanumeric hostname.</span></span>

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a><span data-ttu-id="3c1cd-188">在電信公司租使用者中註冊基本功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="3c1cd-188">Register a base domain name in the carrier tenant</span></span>

<span data-ttu-id="3c1cd-189">**這些動作是在電信租使用者中執行。**</span><span class="sxs-lookup"><span data-stu-id="3c1cd-189">**These actions are performed in the carrier tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a><span data-ttu-id="3c1cd-190">確定您擁有電信租使用者的適當許可權</span><span class="sxs-lookup"><span data-stu-id="3c1cd-190">Ensure that you have appropriate rights in the carrier tenant</span></span>

<span data-ttu-id="3c1cd-191">您只有在以全域系統管理員的登錄至 Microsoft 365 系統管理中心時，才能新增網域。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-191">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="3c1cd-192">若要驗證您擁有的角色，請登錄 Microsoft 365 系統管理中心 (，前往使用者作用中使用者，然後確認您具有全域 https://portal.office.com)   >  系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-192">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="3c1cd-193">有關系統管理員角色以及如何在 Microsoft 365 或 Office 365 中指派角色之詳細資訊，請參閱 [關於系統管理員角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-193">For more information about admin roles and how to assign a role in Microsoft 365 or Office 365, see [About admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a><span data-ttu-id="3c1cd-194">新增基本網域至租使用者並驗證</span><span class="sxs-lookup"><span data-stu-id="3c1cd-194">Add a base domain to the tenant and verify it</span></span>

1. <span data-ttu-id="3c1cd-195">在 Microsoft 365 系統管理中心，**前往設定**  >  **網域**  >  **新增網域**。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-195">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="3c1cd-196">在輸入 **您擁有之網域的** 方塊中，輸入基本網域的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-196">In the **Enter a domain you own** box, type the FQDN of the base domain.</span></span> <span data-ttu-id="3c1cd-197">在下列範例中，基本網域 *customers.adatum.biz。*</span><span class="sxs-lookup"><span data-stu-id="3c1cd-197">In the following example, the base domain is *customers.adatum.biz*.</span></span>

    ![顯示新增網域頁面的螢幕擷取畫面](media/direct-routing-2-sbc-add-domain.png)

3. <span data-ttu-id="3c1cd-199">按一下 **[下一步**。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-199">Click **Next**.</span></span>
4. <span data-ttu-id="3c1cd-200">在範例中，租使用者已經 adatum.biz 驗證功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-200">In the example, the tenant already has adatum.biz as a verified domain name.</span></span> <span data-ttu-id="3c1cd-201">精靈不會要求其他驗證，因為 customers.adatum.biz 已註冊名稱的子域。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-201">The wizard will not ask for additional verification because customers.adatum.biz is a subdomain for the already registered name.</span></span> <span data-ttu-id="3c1cd-202">不過，如果您新增之前尚未驗證的 FQDN，您必須完成驗證程式。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-202">However, if you add an FQDN that has not been verified before, you will need to go through the process of verification.</span></span> <span data-ttu-id="3c1cd-203">驗證程式如下 [所述](#add-a-subdomain-to-the-customer-tenant-and-verify-it)。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-203">The process of verification is [described below](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span></span>

    ![顯示驗證功能變數名稱確認的螢幕擷取畫面](media/direct-routing-3-sbc-verify-domain.png)

5. <span data-ttu-id="3c1cd-205">按一下 **[下** 一步，在 [更新 **DNS 設定** > 頁面上，選取 [我要自己新增 DNS **記錄** ，然後按一下 [下 **一步**> 。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-205">Click **Next**, and on the **Update DNS Settings** page, select **I'll add the DNS records myself** and click **Next**.</span></span>
6. <span data-ttu-id="3c1cd-206">在下一頁上，清除所有值 (，除非您要使用 Exchange、SharePoint 或 Teams/商務用 Skype) 的功能變數名稱，請按一下 [下一步，然後按一下 [**完成**> 。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-206">On the next page, clear all values (unless you want to use the domain name for Exchange, SharePoint, or Teams/Skype for Business), click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="3c1cd-207">請確定您的新網域已達設定完成狀態。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-207">Make sure your new domain is in the Setup complete status.</span></span>

    ![顯示完成設定狀態的網域的螢幕擷取畫面](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a><span data-ttu-id="3c1cd-209">啟用功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="3c1cd-209">Activate the domain name</span></span>

<span data-ttu-id="3c1cd-210">註冊功能變數名稱之後，您必須新增至少一個擁有 Phone System 授權的使用者，並指派 SIP 位址與已建立基本網域相符合之 SIP 位址的 FQDN 部分，以啟用該功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-210">After you have registered a domain name, you need to activate it by adding at least one user with Phone System license and assigning a SIP address with the FQDN portion of the SIP address matching the created base domain.</span></span> <span data-ttu-id="3c1cd-211">授權可在網域啟用後撤銷 (最多可能需要 24 小時) 。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-211">License can be revoked after the domain activation (it can take up to 24 hours).</span></span>

> [!NOTE]
> <span data-ttu-id="3c1cd-212">電信業者租使用者必須保留至少一個指派給租使用者的電話系統授權，以避免移除商務用 Skype 組配置。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-212">The Carrier tenant must keep at least one Phone System license assigned to the tenant to avoid removal of the Skype for Business configuration.</span></span> 

<span data-ttu-id="3c1cd-213">*如需在 [Microsoft 365 或 Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 組織中新增使用者的資訊，請參閱取得 Microsoft 365 或 Office 365 網域的協助。*</span><span class="sxs-lookup"><span data-stu-id="3c1cd-213">*Please review [Get help with Microsoft 365 or Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Microsoft 365 or Office 365 organizations.*</span></span>

<span data-ttu-id="3c1cd-214">例如：test@customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="3c1cd-214">For example: test@customers.adatum.biz</span></span>

![基本網域啟用頁面的螢幕擷取畫面](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a><span data-ttu-id="3c1cd-216">在客戶租使用者中註冊子功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="3c1cd-216">Register a subdomain name in a customer tenant</span></span>

<span data-ttu-id="3c1cd-217">您必須為每個客戶建立唯一的子功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-217">You will need to create a unique subdomain name for every customer.</span></span> <span data-ttu-id="3c1cd-218">在此範例中，我們將使用預設功能變數名稱 sbc1.customers.adatum.biz 租使用者建立子域 woodgrovebank.us。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-218">In this example, we will create a subdomain sbc1.customers.adatum.biz in a tenant with the default domain name woodgrovebank.us.</span></span>

<span data-ttu-id="3c1cd-219">**下列所有動作都位在客戶租使用者中。**</span><span class="sxs-lookup"><span data-stu-id="3c1cd-219">**All actions below are in the customer tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a><span data-ttu-id="3c1cd-220">確定您擁有客戶租使用者的適當許可權</span><span class="sxs-lookup"><span data-stu-id="3c1cd-220">Ensure that you have appropriate rights in the customer tenant</span></span>

<span data-ttu-id="3c1cd-221">您只有在以全域系統管理員的登錄至 Microsoft 365 系統管理中心時，才能新增網域。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-221">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="3c1cd-222">若要驗證您擁有的角色，請登錄 Microsoft 365 系統管理中心 (，前往使用者作用中使用者，然後確認您具有全域 https://portal.office.com)   >  系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-222">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="3c1cd-223">有關系統管理員角色以及如何在 Microsoft 365 或 Office 365 中指派角色之詳細資訊，請參閱 [關於系統管理員角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-223">For more information about admin roles and how to assign a role in Microsoft 365 or Office 365, see [About admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a><span data-ttu-id="3c1cd-224">新增子域至客戶租使用者並驗證</span><span class="sxs-lookup"><span data-stu-id="3c1cd-224">Add a subdomain to the customer tenant and verify it</span></span>
1. <span data-ttu-id="3c1cd-225">在 Microsoft 365 系統管理中心，**前往設定**  >  **網域**  >  **新增網域**。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-225">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="3c1cd-226">在輸入 **您擁有之網域** 的方塊中，輸入此租使用者子域的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-226">In the **Enter a domain you own** box, type the FQDN of the subdomain for this tenant.</span></span> <span data-ttu-id="3c1cd-227">在下列範例中，子域 sbc1.customers.adatum.biz。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-227">In the example below, the subdomain is sbc1.customers.adatum.biz.</span></span>

    ![新增網域頁面的螢幕擷取畫面](media/direct-routing-5-sbc-add-customer-domain.png)

3. <span data-ttu-id="3c1cd-229">按一下 **[下一步**。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-229">Click **Next**.</span></span>
4. <span data-ttu-id="3c1cd-230">FQDN 從未在租使用者中註冊。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-230">The FQDN has never been registered in the tenant.</span></span> <span data-ttu-id="3c1cd-231">在下一個步驟中，您必須驗證網域。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-231">In the next step, you will need to verify the domain.</span></span> <span data-ttu-id="3c1cd-232">請 **改為選取新增 TXT 記錄**。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-232">Select **Add a TXT record instead**.</span></span> 

    ![驗證網域頁面的螢幕擷取畫面](media/direct-routing-6-sbc-verify-customer-domain.png)

5. <span data-ttu-id="3c1cd-234">按一下 **[下** 一步，並記下產生的 TXT 值以驗證功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-234">Click **Next**, and note the TXT value generated to verify the domain name.</span></span>

    ![驗證網域頁面上的文字記錄的螢幕擷取畫面](media/direct-routing-7-sbc-verify-domain-txt.png)

6. <span data-ttu-id="3c1cd-236">使用電信公司 DNS 主機服務提供者中上一個步驟的值建立 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-236">Create the TXT record with the value from the previous step in carrier's DNS hosting provider.</span></span>

    ![顯示建立 TXT 記錄的螢幕擷取畫面](media/direct-routing-8-sbc-txt-record.png)

    <span data-ttu-id="3c1cd-238">若要詳細資訊，請參閱在任何 [DNS](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)主機服務提供者建立 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-238">For more information, refer to [Create DNS records at any DNS hosting provider](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span></span>

7. <span data-ttu-id="3c1cd-239">返回客戶的 Microsoft 365 系統管理中心，然後按一下 [ **驗證**> 。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-239">Go back to the customer's Microsoft 365 admin center and click **Verify**.</span></span> 
8. <span data-ttu-id="3c1cd-240">在下一頁中，選取 **[我要自己新增 DNS 記錄** ，然後按一下 [下 **一步**> 。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-240">On the next page, select **I'll add the DNS records myself** and click **Next**.</span></span>

    ![更新 DNS 設定頁面上選項的螢幕擷取畫面](media/direct-routing-9-sbc-update-dns.png)

9. <span data-ttu-id="3c1cd-242">在 [ **選擇您的線上服務** > 頁面上，清除所有選項，然後按一下 [ **下一步**。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-242">On the **Choose your online services** page, clear all options and click **Next**.</span></span>

    ![選擇線上服務頁面的螢幕擷取畫面](media/direct-routing-10-sbc-choose-services.png)

10. <span data-ttu-id="3c1cd-244">按一下 **[更新** **DNS 設定> 頁面上的 [完成** 。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-244">Click **Finish** on the **Update DNS settings** page.</span></span>

    ![更新 DNS 設定頁面的螢幕擷取畫面](media/direct-routing-11-sbc-update-dns-finish.png)

11. <span data-ttu-id="3c1cd-246">請確保狀態為完成 **設定**。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-246">Ensure that the status is **Setup complete**.</span></span> 
    
    ![顯示設定完成狀態的頁面螢幕擷取畫面](media/direct-routing-12-sbc-setup-complete.png)
    
> [!NOTE]
> <span data-ttu-id="3c1cd-248">個別用戶端的基本 URL 和子域必須位於同一個租使用者上，才能新增 _直接路由_ 主幹。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-248">The base URL and the subdomain for the individual client have to be on the same tenant to enable you to add a _direct route_ trunk.</span></span>

### <a name="activate-the-subdomain-name"></a><span data-ttu-id="3c1cd-249">啟用子功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="3c1cd-249">Activate the subdomain name</span></span>

<span data-ttu-id="3c1cd-250">註冊功能變數名稱之後，您必須新增至少一個使用者，並指派 SIP 位址與客戶租使用者中已建立子域符合之 SIP 位址的 FQDN 部分來啟用功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-250">After you register a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created subdomain in the customer tenant.</span></span> <span data-ttu-id="3c1cd-251">子域啟用之後，使用者 (最多可能需要 24 小時) 。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-251">License can be revoked from user after the subdomain activation (it can take up to 24 hours).</span></span>

<span data-ttu-id="3c1cd-252">*如需在 [Microsoft 365 或 Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 組織中新增使用者的資訊，請參閱取得 Microsoft 365 或 Office 365 網域的協助。*</span><span class="sxs-lookup"><span data-stu-id="3c1cd-252">*Please review [Get help with Microsoft 365 or Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Microsoft 365 or Office 365 organizations.*</span></span>

<span data-ttu-id="3c1cd-253">例如：test@sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="3c1cd-253">For example: test@sbc1.customers.adatum.biz</span></span>

![子域頁面啟用的螢幕擷取畫面](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a><span data-ttu-id="3c1cd-255">建立主幹並配置使用者</span><span class="sxs-lookup"><span data-stu-id="3c1cd-255">Create a trunk and provision users</span></span>

<span data-ttu-id="3c1cd-256">隨著直接路由的初次發行，Microsoft 需要使用 New-CSOnlinePSTNGateway 將主幹新 (每個服務租使用者) 租使用者。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-256">With the initial release of Direct Routing, Microsoft required a trunk to be added to each served tenant (customer tenant) using New-CSOnlinePSTNGateway.</span></span>

<span data-ttu-id="3c1cd-257">不過，有兩個原因並未證明這是最佳結果：</span><span class="sxs-lookup"><span data-stu-id="3c1cd-257">However, this has not proved optimal for two reasons:</span></span>
 
- <span data-ttu-id="3c1cd-258">**間接費用管理**。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-258">**Overhead management**.</span></span> <span data-ttu-id="3c1cd-259">例如，卸載或排空 SBC 會變更一些參數，例如啟用或停用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-259">Offloading or draining an SBC, for example, changes some parameters, like enabling or disabling media bypass.</span></span> <span data-ttu-id="3c1cd-260">變更埠需要執行 Set-CSOnlinePSTNGateway (變更多個租使用者的參數，) 實際上也是相同的 SBC。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-260">Changing the port requires changing parameters in multiple tenants (by running Set-CSOnlinePSTNGateway), but it is in fact the same SBC.</span></span> 

-  <span data-ttu-id="3c1cd-261">**負荷處理**。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-261">**Overhead processing**.</span></span> <span data-ttu-id="3c1cd-262">收集及監控主幹健康情況資料 - 從多個邏輯主幹收集的 SIP 選項，實際上，相同的 SBC 和相同的實體主幹，會降低路由資料的處理速度。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-262">Gathering and monitoring trunk health data - SIP options collected from multiple logical trunks that are, in reality, the same SBC and the same physical trunk, slows down processing of the routing data.</span></span>
 
<span data-ttu-id="3c1cd-263">根據這個意見，Microsoft 會提供新的邏輯來為客戶租使用者配置主幹。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-263">Based on this feedback, Microsoft is bringing in a new logic to provision the trunks for the customer tenants.</span></span>

<span data-ttu-id="3c1cd-264">引進了兩個新實體：</span><span class="sxs-lookup"><span data-stu-id="3c1cd-264">Two new entities were introduced:</span></span>
-    <span data-ttu-id="3c1cd-265">使用命令 New-CSOnlinePSTNGateway 在電信租使用者中註冊的電信母線，例如 New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-265">A carrier trunk registered in the carrier tenant using the command New-CSOnlinePSTNGateway, for example New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true.</span></span>

-    <span data-ttu-id="3c1cd-266">不需要註冊的衍生主幹。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-266">A derived trunk, that does not require registration.</span></span> <span data-ttu-id="3c1cd-267">它只是從電信母線新增到所需的主機名稱稱。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-267">It is simply a desired host name added in from of the carrier trunk.</span></span> <span data-ttu-id="3c1cd-268">它會從電信母線衍生出其所有設定參數。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-268">It derives all of its configuration parameters from the carrier trunk.</span></span> <span data-ttu-id="3c1cd-269">衍生主幹不需要在 PowerShell 中建立，而與電信業者主幹的關聯是以 FQDN 名稱為基礎 (請參閱下方) 。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-269">The derived trunk doesn't need to be created in PowerShell, and the association with the carrier trunk is based on the FQDN name (see details below).</span></span>

<span data-ttu-id="3c1cd-270">**置備邏輯和範例**</span><span class="sxs-lookup"><span data-stu-id="3c1cd-270">**Provisioning logic and example**</span></span>

-    <span data-ttu-id="3c1cd-271">電信公司只需要使用 (命令，在電信) 中設定及管理Set-CSOnlinePSTNGateway主幹。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-271">Carriers only need to set up and manage a single trunk  (carrier trunk in the carrier domain), using the Set-CSOnlinePSTNGateway command.</span></span> <span data-ttu-id="3c1cd-272">在上方範例中，這是 adatum.biz;</span><span class="sxs-lookup"><span data-stu-id="3c1cd-272">In the example above it is adatum.biz;</span></span>
-    <span data-ttu-id="3c1cd-273">在客戶租使用者中，電信公司只需要將衍生主幹 FQDN 新加到使用者的語音路由策略。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-273">In the customer tenant, the carrier need only to add the derived trunk FQDN to the voice routing policies of the users.</span></span> <span data-ttu-id="3c1cd-274">不需要執行主幹New-CSOnlinePSTNGateway程式。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-274">There is no need to run New-CSOnlinePSTNGateway for a trunk.</span></span>
-    <span data-ttu-id="3c1cd-275">如名稱所建議，衍生主幹會繼承或衍生電信母線的所有組組參數。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-275">The derived trunk, as the name suggests, inherits or derives all the configuration parameters from the carrier trunk.</span></span> <span data-ttu-id="3c1cd-276">例子：</span><span class="sxs-lookup"><span data-stu-id="3c1cd-276">Examples:</span></span>
-    <span data-ttu-id="3c1cd-277">Customers.adatum.biz – 需要在電信租使用者中建立電信母線。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-277">Customers.adatum.biz – the carrier trunk which needs to be created in the carrier tenant.</span></span>
-    <span data-ttu-id="3c1cd-278">Sbc1.customers.adatum.biz – 客戶租使用者中的衍生主幹，不需要在 PowerShell 中建立。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-278">Sbc1.customers.adatum.biz – the derived trunk in a customer tenant that does not need to be created in PowerShell.</span></span>  <span data-ttu-id="3c1cd-279">您可以直接在線上語音路由策略的客戶租使用者中新增衍生主幹的名稱，而不必建立。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-279">You can simply add the name of the derived trunk in the customer tenant in the online voice routing policy without creating it.</span></span>
-   <span data-ttu-id="3c1cd-280">電信公司必須設定 DNS 記錄，將衍生主幹 FQDN 解析為電信公司 SBC IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-280">Carrier will need to setup DNS record resolving derived trunk FQDN to carrier SBC ip address.</span></span>

-    <span data-ttu-id="3c1cd-281">在電信 (租使用者) 上進行的任何變更，都會自動適用于衍生的主幹。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-281">Any changes made on a carrier trunk (on carrier tenant) is automatically applied to derived trunks.</span></span> <span data-ttu-id="3c1cd-282">例如，電信公司可以變更電信母線上的 SIP 埠，這項變更會適用于所有衍生的主幹。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-282">For example, carriers can change an SIP port on the carrier trunk, and this change applies to all derived trunks.</span></span> <span data-ttu-id="3c1cd-283">設定主幹的新邏輯簡化了管理，因為您不需要前往每個租使用者並變更每個主幹上的參數。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-283">New logic to configure the trunks simplifies the management as you don't need to go to every tenant and change the parameter on every trunk.</span></span>
-    <span data-ttu-id="3c1cd-284">選項只會送到電信母線 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-284">The options are sent only to the carrier trunk FQDN.</span></span> <span data-ttu-id="3c1cd-285">電信母線的健康狀態會適用于所有衍生主幹，並用於路由決策。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-285">The health status of the carrier trunk is applied to all derived trunks and is used for routing decisions.</span></span> <span data-ttu-id="3c1cd-286">進一瞭解直接 [路由選項](./direct-routing-monitor-and-troubleshoot.md)。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-286">Find out more about [Direct Routing options](./direct-routing-monitor-and-troubleshoot.md).</span></span>
-    <span data-ttu-id="3c1cd-287">電信母線可以排空電信母線，而所有衍生的主幹也會排空。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-287">The carrier can drain the carrier trunk, and all derived trunks will be drained as well.</span></span> 
 

<span data-ttu-id="3c1cd-288">**從上一個模型移往電信母線**</span><span class="sxs-lookup"><span data-stu-id="3c1cd-288">**Migration from the previous model to the carrier trunk**</span></span>
 
<span data-ttu-id="3c1cd-289">若要從目前由電信主機模型所實施的移向新模型，電信公司必須為客戶租使用者重新配置主幹。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-289">For migration from the current implementation of the carrier hosted model to the new model, the carriers will need to reconfigure the trunks for customer tenants.</span></span> <span data-ttu-id="3c1cd-290">從客戶租使用者移除主幹，Remove-CSOnlinePSTNGateway (將主幹留在電信租使用者) -</span><span class="sxs-lookup"><span data-stu-id="3c1cd-290">Remove the trunks from the customer tenants using Remove-CSOnlinePSTNGateway (leaving the trunk in the carrier tenant)-</span></span>

<span data-ttu-id="3c1cd-291">我們強烈建議您儘快移移至新解決方案，因為我們會使用電信母線和衍生主幹模型加強監控與部署。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-291">We highly encourage migrating to the new solution as soon as possible as we will be enhancing monitoring and provisioning using the carrier and derived trunk model.</span></span>
 

<span data-ttu-id="3c1cd-292">請參閱 [SBC 廠商](#deploy-and-configure-the-sbc) 有關在連絡人標題中傳送子域 FQDN 名稱的指示。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-292">Please refer to the [SBC vendor instructions](#deploy-and-configure-the-sbc) on configuring sending the FQDN name of subdomains in the Contact header.</span></span>

## <a name="considerations-for-setting-up-muti-tenant-failover"></a><span data-ttu-id="3c1cd-293">設定 muti-tenant 容錯移轉的考慮</span><span class="sxs-lookup"><span data-stu-id="3c1cd-293">Considerations for setting up muti-tenant failover</span></span> 

<span data-ttu-id="3c1cd-294">若要設定多租使用者環境的容錯移轉，您必須執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="3c1cd-294">To set up failover for a multi-tenant environment, you'll need to do the following:</span></span>

- <span data-ttu-id="3c1cd-295">針對每個租使用者，為兩個不同的 SBC 新增 FQDNs。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-295">For each tenant, add the FQDNs for two different SBCs.</span></span>  <span data-ttu-id="3c1cd-296">例如：</span><span class="sxs-lookup"><span data-stu-id="3c1cd-296">For example:</span></span>

   <span data-ttu-id="3c1cd-297">customer1.sbc1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3c1cd-297">customer1.sbc1.contoso.com</span></span> <br>
   <span data-ttu-id="3c1cd-298">customer1.sbc2.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3c1cd-298">customer1.sbc2.contoso.com</span></span> <br>

- <span data-ttu-id="3c1cd-299">在使用者的線上語音路由規則中，指定兩個 SBC。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-299">In the Online Voice Routing policies of the users, specify both SBCs.</span></span>  <span data-ttu-id="3c1cd-300">如果其中一個 SBC 失敗，路由策略會路由呼叫至第二個 SBC。</span><span class="sxs-lookup"><span data-stu-id="3c1cd-300">If one SBC fails, the routing policy will route calls to the second SBC.</span></span>


## <a name="see-also"></a><span data-ttu-id="3c1cd-301">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3c1cd-301">See also</span></span>

[<span data-ttu-id="3c1cd-302">規劃直接路由</span><span class="sxs-lookup"><span data-stu-id="3c1cd-302">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="3c1cd-303">設定直接路由</span><span class="sxs-lookup"><span data-stu-id="3c1cd-303">Configure Direct Routing</span></span>](direct-routing-configure.md)