---
title: 設定動態緊急電話
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
description: 瞭解如何設定 Microsoft 通話方案和電話系統直接路由動態緊急通話功能。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b76f8605aa1151911c26e0724db161b3a497fcf6
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164552"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a><span data-ttu-id="5bd58-103">規劃和設定動態緊急電話</span><span class="sxs-lookup"><span data-stu-id="5bd58-103">Plan and configure dynamic emergency calling</span></span> 

<span data-ttu-id="5bd58-104">Microsoft 通話方案和電話系統直連路由的動態緊急通話可提供設定及路由緊急通話的功能，並根據團隊用戶端的目前位置來通知安全人員。</span><span class="sxs-lookup"><span data-stu-id="5bd58-104">Dynamic emergency calling for Microsoft Calling Plans and Phone System Direct Routing provides the capability to configure and route emergency calls and notify security personnel based on the current location of the Teams client.</span></span>  

<span data-ttu-id="5bd58-105">根據租使用者管理員定義的網路拓撲，小組用戶端會在位置資訊服務（.LIS）的要求中提供網路連線資訊。</span><span class="sxs-lookup"><span data-stu-id="5bd58-105">Based on the network topology that the tenant administrator defines, the Teams client provides network connectivity information in a request to the Location Information Service (LIS).</span></span>  <span data-ttu-id="5bd58-106">如果有相符的專案，則 .LIS 會傳回用戶端的位置。</span><span class="sxs-lookup"><span data-stu-id="5bd58-106">If there is a match, the LIS returns a location to the client.</span></span> <span data-ttu-id="5bd58-107">這個位置資料會傳回用戶端。</span><span class="sxs-lookup"><span data-stu-id="5bd58-107">This location data is transmitted back to the client.</span></span>  

<span data-ttu-id="5bd58-108">團隊用戶端包含位置資料做為緊急通話的一部分。</span><span class="sxs-lookup"><span data-stu-id="5bd58-108">The Teams client includes location data as part of an emergency call.</span></span> <span data-ttu-id="5bd58-109">這個資料然後由緊急服務提供者用來判斷適當的公用安全回應點（PSAP），並將呼叫路由到該 PSAP，這可讓 PSAP dispatcher 取得來電者的位置。</span><span class="sxs-lookup"><span data-stu-id="5bd58-109">This data is then used by the emergency service provider to determine the appropriate Public Safety Answering Point (PSAP) and to route the call to that PSAP, which allows the PSAP dispatcher to obtain the caller's location.</span></span>  

<span data-ttu-id="5bd58-110">針對動態緊急通話，必須發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="5bd58-110">For dynamic emergency calling, the following must occur:</span></span>

1. <span data-ttu-id="5bd58-111">網路系統管理員會設定網路設定和 .LIS，以建立網路/緊急位置地圖。</span><span class="sxs-lookup"><span data-stu-id="5bd58-111">The network administrator configures network settings and the LIS to create a network/emergency location map.</span></span>

   <span data-ttu-id="5bd58-112">針對直接路由，需要進行額外的設定，以路由緊急呼叫並可能提供合作夥伴連線。</span><span class="sxs-lookup"><span data-stu-id="5bd58-112">For Direct Routing, additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="5bd58-113">系統管理員必須設定與緊急路由服務（ERS）提供者（美國）的連線，**或**針對緊急位置識別號碼（ELIN）應用程式設定會話邊界控制器（SBC）。</span><span class="sxs-lookup"><span data-stu-id="5bd58-113">The administrator must configure connection to an Emergency Routing Service (ERS) provider (United States) **OR** configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

2. <span data-ttu-id="5bd58-114">在啟動期間及之後定期進行，或當網路連線變更時，小組用戶端會將包含其網路連線資訊的位置要求傳送到網路設定和 IIS 類型。</span><span class="sxs-lookup"><span data-stu-id="5bd58-114">During startup and periodically afterwards, or when a network connection is changed, the Teams client sends a location request that contains its network connectivity information to the network settings and the LIS.</span></span>

   - <span data-ttu-id="5bd58-115">如果有網路設定網站相符的專案，緊急通話原則會傳回該網站的小組用戶端。</span><span class="sxs-lookup"><span data-stu-id="5bd58-115">If there is a network settings site match – emergency calling policies are returned to the Teams client from that site.</span></span> <span data-ttu-id="5bd58-116">（如需有關原則的詳細資訊，請參閱[設定緊急原則](#configure-emergency-policies)）。</span><span class="sxs-lookup"><span data-stu-id="5bd58-116">(For more information about policies, see [Configure emergency policies](#configure-emergency-policies)).</span></span>

   - <span data-ttu-id="5bd58-117">如果有一個 IIS 相符的專案，則會將團隊用戶端連接的網路元素的緊急位置傳回給團隊用戶端。</span><span class="sxs-lookup"><span data-stu-id="5bd58-117">If there is an LIS match – an emergency location from the network element the Teams client is connected to is returned to the Teams client.</span></span>

3. <span data-ttu-id="5bd58-118">當團隊用戶端進行緊急通話時，緊急位置會傳達給 PSTN 網路。</span><span class="sxs-lookup"><span data-stu-id="5bd58-118">When the Teams client makes an emergency call, the emergency location is conveyed to the PSTN network.</span></span>

   <span data-ttu-id="5bd58-119">如果是直接路由，系統管理員必須設定 SBC 來傳送緊急呼叫給 ERS 提供者，或設定 SBC ELIN 應用程式。</span><span class="sxs-lookup"><span data-stu-id="5bd58-119">For Direct Routing, the administrator must configure the SBC to send emergency calls to the ERS provider or configure the SBC ELIN application.</span></span>

<span data-ttu-id="5bd58-120">本文包含下列各節。</span><span class="sxs-lookup"><span data-stu-id="5bd58-120">This article contains the following sections.</span></span>

- [<span data-ttu-id="5bd58-121">設定緊急位址</span><span class="sxs-lookup"><span data-stu-id="5bd58-121">Configure emergency addresses</span></span>](#assign-emergency-addresses)
- [<span data-ttu-id="5bd58-122">設定網路設定</span><span class="sxs-lookup"><span data-stu-id="5bd58-122">Configure network settings</span></span>](#configure-network-settings)
- [<span data-ttu-id="5bd58-123">設定位置資訊服務</span><span class="sxs-lookup"><span data-stu-id="5bd58-123">Configure Location Information Service</span></span>](#configure-location-information-service)
- [<span data-ttu-id="5bd58-124">設定緊急原則</span><span class="sxs-lookup"><span data-stu-id="5bd58-124">Configure emergency policies</span></span>](#configure-emergency-policies)
- [<span data-ttu-id="5bd58-125">啟用使用者和網站</span><span class="sxs-lookup"><span data-stu-id="5bd58-125">Enable users and sites</span></span>](#enable-users-and-sites)
- [<span data-ttu-id="5bd58-126">測試緊急通話</span><span class="sxs-lookup"><span data-stu-id="5bd58-126">Test emergency calling</span></span>](#test-emergency-calling)


<span data-ttu-id="5bd58-127">自動路由至適當的公用安全應答點（PSAP）的功能會視小組使用者使用的國家/地區而有所不同。</span><span class="sxs-lookup"><span data-stu-id="5bd58-127">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) varies depending on the country of usage of the Teams user.</span></span> 

<span data-ttu-id="5bd58-128">如需緊急通話的詳細資訊，包括緊急位址及緊急通話路由的相關資訊、國家/地區的相關資訊，以及網路設定和網路拓撲的相關資訊，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="5bd58-128">For more information about emergency calling--including information about emergency addresses and emergency call routing, information specific to countries, and information about network settings and network topology--see the following:</span></span>

- [<span data-ttu-id="5bd58-129">管理緊急通話</span><span class="sxs-lookup"><span data-stu-id="5bd58-129">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="5bd58-130">管理雲端語音功能的網路設定</span><span class="sxs-lookup"><span data-stu-id="5bd58-130">Manage network settings for cloud voice features</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="5bd58-131">管理雲端語音功能的網路拓撲</span><span class="sxs-lookup"><span data-stu-id="5bd58-131">Manage your network topology for cloud voice features</span></span>](manage-your-network-topology.md)


## <a name="supported-clients"></a><span data-ttu-id="5bd58-132">支援的用戶端</span><span class="sxs-lookup"><span data-stu-id="5bd58-132">Supported clients</span></span>

<span data-ttu-id="5bd58-133">目前支援下列用戶端。</span><span class="sxs-lookup"><span data-stu-id="5bd58-133">The following clients are currently supported.</span></span>  <span data-ttu-id="5bd58-134">經常回到查看此清單的更新。</span><span class="sxs-lookup"><span data-stu-id="5bd58-134">Check back often to see updates to this list.</span></span>

- <span data-ttu-id="5bd58-135">Microsoft Windows 版團隊桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="5bd58-135">Teams desktop client for Microsoft Windows</span></span>
- <span data-ttu-id="5bd58-136">Apple macOS 的小組桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="5bd58-136">Teams desktop client for Apple macOS</span></span>
- <span data-ttu-id="5bd58-137">Apple iOS 用戶端版本1.0.92.2019121004 和 App Store 1.0.92 及更高版本的團隊行動用戶端</span><span class="sxs-lookup"><span data-stu-id="5bd58-137">Teams mobile client for Apple iOS client version 1.0.92.2019121004 and App Store version 1.0.92 and greater</span></span>
- <span data-ttu-id="5bd58-138">適用于 Android 用戶端和 Google Play 商店版本 1416/1.0.0.2019121201 及更高版本的團隊行動用戶端</span><span class="sxs-lookup"><span data-stu-id="5bd58-138">Teams mobile client for Android client and Google Play store version 1416/1.0.0.2019121201 and greater</span></span>
- <span data-ttu-id="5bd58-139">團隊手機版本 1449/1.0.94.2019110802 及更高版本</span><span class="sxs-lookup"><span data-stu-id="5bd58-139">Teams phone version 1449/1.0.94.2019110802 and greater</span></span>

## <a name="assign-emergency-addresses"></a><span data-ttu-id="5bd58-140">指派緊急位址</span><span class="sxs-lookup"><span data-stu-id="5bd58-140">Assign emergency addresses</span></span>

<span data-ttu-id="5bd58-141">您可以將緊急位址指派給呼叫方案使用者，以及動態取得位置所需的網路識別碼。</span><span class="sxs-lookup"><span data-stu-id="5bd58-141">You can assign emergency addresses to both Calling Plan users and to the network identifiers that are required for dynamically obtaining a location.</span></span> <span data-ttu-id="5bd58-142">（支援 Subnet 和 WiFi AP; 乙太網上交換器/埠的支援擱置）。</span><span class="sxs-lookup"><span data-stu-id="5bd58-142">(Subnet and WiFi AP are supported; support for Ethernet switch/port is pending).</span></span>

<span data-ttu-id="5bd58-143">若要支援在美國的緊急通話自動路由，您必須確認指派給網路識別碼的緊急位置包含關聯的地功能變數代碼。</span><span class="sxs-lookup"><span data-stu-id="5bd58-143">To support automated routing of emergency calls within the United States, you must ensure that the emergency locations that are assigned to network identifiers include the associated geo codes.</span></span> <span data-ttu-id="5bd58-144">（沒有地理程式碼的緊急位址無法指派給動態位置所需的網路識別碼）。</span><span class="sxs-lookup"><span data-stu-id="5bd58-144">(Emergency addresses without geo codes cannot be assigned to the network identifiers that are required for dynamic locations.)</span></span>

<span data-ttu-id="5bd58-145">Azure 對應是用來進行位置服務的。</span><span class="sxs-lookup"><span data-stu-id="5bd58-145">Azure Maps is used for location-based services.</span></span>  <span data-ttu-id="5bd58-146">當您使用 Microsoft 團隊系統管理中心輸入緊急位址時，小組會檢查 Azure 對應位址：</span><span class="sxs-lookup"><span data-stu-id="5bd58-146">When you enter an emergency address by using the Microsoft Teams admin center, Teams checks Azure Maps for the address:</span></span>

- <span data-ttu-id="5bd58-147">如果找到相符的位置，系統會自動包含地區代碼。</span><span class="sxs-lookup"><span data-stu-id="5bd58-147">If a match is found, the geo codes are automatically included.</span></span>

- <span data-ttu-id="5bd58-148">如果找不到相符的專案，您就有機會手動建立緊急位址。</span><span class="sxs-lookup"><span data-stu-id="5bd58-148">If a match is not found, you will have the opportunity to manually create an emergency address.</span></span> <span data-ttu-id="5bd58-149">您可以使用釘選功能來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="5bd58-149">You can use the PIN drop feature to do this.</span></span>   

<span data-ttu-id="5bd58-150">這表示，如果為指派給呼叫計畫使用者的現有緊急位置是針對動態位置所設計，則必須重新建立相同的位址，才能包含 geo 碼。</span><span class="sxs-lookup"><span data-stu-id="5bd58-150">This means that if an existing emergency location that is created for assigning to Calling Plan users is intended for a dynamic location, the same address needs to be re-created to include the geo codes.</span></span> <span data-ttu-id="5bd58-151">若要區分兩個位置，您應該包含不同的描述。</span><span class="sxs-lookup"><span data-stu-id="5bd58-151">To distinguish between the two locations, you should include a different description.</span></span> <span data-ttu-id="5bd58-152">新的緊急位置可以指派給擁有舊位置的使用者。</span><span class="sxs-lookup"><span data-stu-id="5bd58-152">The new emergency location can be assigned to the users who have the old location.</span></span> <span data-ttu-id="5bd58-153">完全遷移後，就可以刪除舊位置。</span><span class="sxs-lookup"><span data-stu-id="5bd58-153">When fully migrated, the old location can be deleted.</span></span>

<span data-ttu-id="5bd58-154">如需有關設定緊急位址的詳細資訊，請參閱為[您的組織新增緊急位置](add-change-remove-emergency-location-organization.md)並[指派緊急位置給您的使用者](assign-change-emergency-location-user.md)。</span><span class="sxs-lookup"><span data-stu-id="5bd58-154">For more information about configuring emergency addresses, see [Add an emergency location for your organization](add-change-remove-emergency-location-organization.md) and [Assign an emergency location for your user](assign-change-emergency-location-user.md).</span></span>

## <a name="configure-network-settings"></a><span data-ttu-id="5bd58-155">設定網路設定</span><span class="sxs-lookup"><span data-stu-id="5bd58-155">Configure network settings</span></span>

<span data-ttu-id="5bd58-156">[網路設定] 可用來判斷團隊用戶端的位置，以及動態取得緊急通話原則與緊急位置。</span><span class="sxs-lookup"><span data-stu-id="5bd58-156">Network settings are used to determine the location of a Teams client, and to dynamically obtain emergency calling policies and an emergency location.</span></span> <span data-ttu-id="5bd58-157">您可以根據貴組織希望緊急通話運作的方式來設定網路設定。</span><span class="sxs-lookup"><span data-stu-id="5bd58-157">You can configure network settings according to how your organization wants emergency calling to function.</span></span>

<span data-ttu-id="5bd58-158">[網路設定] 包含包含子網集合的網站：這些都是專門針對動態原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="5bd58-158">Network settings include sites that include a collection of subnets--these are used exclusively for dynamic policy assignment to users.</span></span>  <span data-ttu-id="5bd58-159">例如，您可以將 TeamsEmergencyCalling 原則和 TeamsEmergencyCallRouting 原則指派給「雷德蒙網站」，讓從家裡或其他 Microsoft 位置進行漫遊的任何使用者都是以緊急號碼、路由和安全服務台（特定于雷蒙德）來設定。</span><span class="sxs-lookup"><span data-stu-id="5bd58-159">For example, a TeamsEmergencyCalling Policy and TeamsEmergencyCallRouting Policy might be assigned to the "Redmond site" so that any user that roams from home or another Microsoft location is configured with emergency numbers, routing, and security desk specific to Redmond.</span></span>  

>[!Note]
><span data-ttu-id="5bd58-160">子網也可以在 .LIS 中定義，而且可以與緊急位置相關聯。</span><span class="sxs-lookup"><span data-stu-id="5bd58-160">Subnets can also be defined in LIS and can be associated with an emergency location.</span></span>  

<span data-ttu-id="5bd58-161">請牢記下列定義：</span><span class="sxs-lookup"><span data-stu-id="5bd58-161">Keep the following definitions in mind:</span></span>

- <span data-ttu-id="5bd58-162">受信任的 IP 包含商業網路的網際網路外部 Ip 集合，並用來判斷使用者的端點是否在商業網路內。</span><span class="sxs-lookup"><span data-stu-id="5bd58-162">Trusted IP's contain a collection of the Internet external IPs of the enterprise network and are used to determine if the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="5bd58-163">只要使用者的外部 IP 與信任的 IP 位址中的 IP 相符，就會嘗試取得動態原則或位置。</span><span class="sxs-lookup"><span data-stu-id="5bd58-163">An attempt to obtain a dynamic policy or location will only be made if the user's external IP matches an IP in the Trusted IP address.</span></span> <span data-ttu-id="5bd58-164">您可以針對 IPv4 或 IPv6 IP 位址進行相符，並視傳送至網路設定的 IP 資料包格式而定。</span><span class="sxs-lookup"><span data-stu-id="5bd58-164">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span>  <span data-ttu-id="5bd58-165">（如果公用 IP 位址同時具有 IPv4 與 IPv6，您必須將兩者都新增為信任的 IP 位址。）</span><span class="sxs-lookup"><span data-stu-id="5bd58-165">(If a public IP address has both IPv4 and IPv6, you need to add both as trusted IP addresses.)</span></span>

- <span data-ttu-id="5bd58-166">網路區域包含一個網路網站集合。</span><span class="sxs-lookup"><span data-stu-id="5bd58-166">A network region contains a collection of network sites.</span></span> 

- <span data-ttu-id="5bd58-167">網路網站代表貴組織有實體價值（例如，辦公室、一組建築物或校園）的位置。</span><span class="sxs-lookup"><span data-stu-id="5bd58-167">A network site represents a location where your organization has a physical value, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="5bd58-168">這些網站是由 IP 子網的集合所定義。</span><span class="sxs-lookup"><span data-stu-id="5bd58-168">These sites are defined as a collection of IP subnets.</span></span>

- <span data-ttu-id="5bd58-169">網路子網必須與特定的網路網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="5bd58-169">A network subnet must be associated with a specific network site.</span></span> <span data-ttu-id="5bd58-170">用戶端的位置是根據網路子網和相關的網路網站來決定。</span><span class="sxs-lookup"><span data-stu-id="5bd58-170">A client's location is determined based on the network subnet and the associated network site.</span></span>  

<span data-ttu-id="5bd58-171">如需詳細資訊，請參閱[雲端語音功能的網路設定](cloud-voice-network-settings.md)和[管理雲端語音功能的網路拓撲](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="5bd58-171">For more information, see [Network settings for cloud voice features](cloud-voice-network-settings.md) and [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span>

<span data-ttu-id="5bd58-172">請注意，網路設定（例如新位址、網路識別碼等）的某些變更可能需要幾個時間（例如新的位址、網路識別碼等），才能傳播並供團隊用戶端使用。</span><span class="sxs-lookup"><span data-stu-id="5bd58-172">Note that it can take some time (up to a couple of hours) for some changes to network settings (such as a new address, network identifier, and so on) to propagate and be available to Teams clients.</span></span>  

<span data-ttu-id="5bd58-173">**通話方案使用者：**</span><span class="sxs-lookup"><span data-stu-id="5bd58-173">**For Calling Plan users:**</span></span>

- <span data-ttu-id="5bd58-174">如果需要對 security 辦公桌通知進行動態設定，則您必須設定信任的 IP 位址和網路網站。</span><span class="sxs-lookup"><span data-stu-id="5bd58-174">If dynamic configuration of security desk notification is required, then you must configure both Trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="5bd58-175">如果只需要動態位置，則您必須只設定信任的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="5bd58-175">If only dynamic locations are required, then you must configure only Trusted IP addresses.</span></span> 

- <span data-ttu-id="5bd58-176">如果兩者都不是必要的，則不需要設定網路設定。</span><span class="sxs-lookup"><span data-stu-id="5bd58-176">If neither are required, then configuration of network settings is not required.</span></span> 

<span data-ttu-id="5bd58-177">**針對直接路由使用者：**</span><span class="sxs-lookup"><span data-stu-id="5bd58-177">**For Direct Routing users:**</span></span>

- <span data-ttu-id="5bd58-178">如果您需要動態啟用緊急通話或安全服務台通知的動態設定，則您必須設定信任的 IP 位址和網路網站。</span><span class="sxs-lookup"><span data-stu-id="5bd58-178">If dynamic enablement of emergency calling or dynamic configuration of security desk notification is required, then you must configure both Trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="5bd58-179">如果只需要動態位置，則您必須只設定信任的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="5bd58-179">If only dynamic locations are required, then you must configure only Trusted IP addresses.</span></span>

- <span data-ttu-id="5bd58-180">如果兩者都不是必要的，則不需要設定網路設定。</span><span class="sxs-lookup"><span data-stu-id="5bd58-180">If neither are required, then configuration of network settings is not required.</span></span>


## <a name="configure-location-information-service"></a><span data-ttu-id="5bd58-181">設定位置資訊服務</span><span class="sxs-lookup"><span data-stu-id="5bd58-181">Configure Location Information Service</span></span>

<span data-ttu-id="5bd58-182">團隊用戶端從與不同網路識別碼相關聯的位置取得緊急位址。</span><span class="sxs-lookup"><span data-stu-id="5bd58-182">A Teams client obtains emergency addresses from the locations associated with different network identifiers.</span></span> <span data-ttu-id="5bd58-183">同時支援子網和無線存取點（WAPs）。</span><span class="sxs-lookup"><span data-stu-id="5bd58-183">Both subnets and Wireless Access Points (WAPs) are supported.</span></span> <span data-ttu-id="5bd58-184">如果找到多個位置，WAP 會優先于子網。</span><span class="sxs-lookup"><span data-stu-id="5bd58-184">If multiple locations are found, WAP takes precedence over subnet.</span></span> <span data-ttu-id="5bd58-185">（乙太網上交換器/埠的支援已擱置。）</span><span class="sxs-lookup"><span data-stu-id="5bd58-185">(Support for Ethernet switch/port is pending.)</span></span>

<span data-ttu-id="5bd58-186">若要讓用戶端取得位置，您必須使用下列 Cmdlet 來填入位置資訊服務（.LIS）與網路識別碼及緊急位置：</span><span class="sxs-lookup"><span data-stu-id="5bd58-186">For a client to obtain a location, you must populate the Location Information Service (LIS) with network identifiers and emergency locations by using the following cmdlets:</span></span>  


- <span data-ttu-id="5bd58-187">[取得](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps)、[設定](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps)、[移除](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps)-CsOnlineLisPort</span><span class="sxs-lookup"><span data-stu-id="5bd58-187">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort</span></span>
- <span data-ttu-id="5bd58-188">[取得](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps)、[設定](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps)、[移除](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps)-CsOnlineLisSwitch</span><span class="sxs-lookup"><span data-stu-id="5bd58-188">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch</span></span>
- <span data-ttu-id="5bd58-189">[取得](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps)、[設定](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps)、[移除](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps)-CsOnlineLisSubnet</span><span class="sxs-lookup"><span data-stu-id="5bd58-189">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet</span></span>
- <span data-ttu-id="5bd58-190">[取得](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps)、[設定](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps)、[移除](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps
)-CsOnlineLisWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="5bd58-190">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps
) -CsOnlineLisWirelessAccessPoint</span></span> 


>[!Important] 
><span data-ttu-id="5bd58-191">如果子網是作為網路網站的一部分使用，則必須在位置資訊服務中重新定義，才能呈現動態位置。</span><span class="sxs-lookup"><span data-stu-id="5bd58-191">If subnets are being used as part of network sites, they must be redefined in the Location Information Service to render dynamic locations.</span></span>


## <a name="configure-emergency-policies"></a><span data-ttu-id="5bd58-192">設定緊急原則</span><span class="sxs-lookup"><span data-stu-id="5bd58-192">Configure emergency policies</span></span>

<span data-ttu-id="5bd58-193">您可以使用下列原則來設定緊急通話：</span><span class="sxs-lookup"><span data-stu-id="5bd58-193">You use the following policies to configure emergency calling:</span></span>

- <span data-ttu-id="5bd58-194">**TeamsEmergencyCallRoutingPolicy** –只適用于直接路由。</span><span class="sxs-lookup"><span data-stu-id="5bd58-194">**TeamsEmergencyCallRoutingPolicy** – Applies only to Direct Routing.</span></span> <span data-ttu-id="5bd58-195">此原則會根據需要設定緊急電話號碼、每個數位的遮罩，以及每個號碼的 PSTN 路由。</span><span class="sxs-lookup"><span data-stu-id="5bd58-195">This policy configures the emergency numbers, masks per number if desired, and the PSTN route per number.</span></span>  <span data-ttu-id="5bd58-196">您可以將此原則指派給使用者、網路網站，或同時指派給這兩者。</span><span class="sxs-lookup"><span data-stu-id="5bd58-196">You can assign this policy to users, to network sites, or to both.</span></span> <span data-ttu-id="5bd58-197">（通話計畫團隊用戶端會根據其 Office 365 使用位置，自動啟用緊急通話的緊急電話號碼。） 您可以使用 New、Set 和 Grant CsTeamsEmergencyCallRouting Cmdlet 來管理此原則。</span><span class="sxs-lookup"><span data-stu-id="5bd58-197">(Calling Plans Teams clients are automatically enabled for emergency calling with the emergency numbers from the country based upon their Office 365 usage location.)  You manage this policy by using the New-, Set-, and Grant-CsTeamsEmergencyCallRouting cmdlets.</span></span> 

- <span data-ttu-id="5bd58-198">**TeamsEmergencyCallingPolicy** -適用于通話方案和直接路由。</span><span class="sxs-lookup"><span data-stu-id="5bd58-198">**TeamsEmergencyCallingPolicy** - Applies to Calling Plan and Direct Routing.</span></span> <span data-ttu-id="5bd58-199">此原則會在發出緊急通話時設定 security 辦公桌的通知體驗。</span><span class="sxs-lookup"><span data-stu-id="5bd58-199">This policy configures the security desk notification experience when an emergency call is made.</span></span> <span data-ttu-id="5bd58-200">您可以設定要通知的人員，以及通知的方式。</span><span class="sxs-lookup"><span data-stu-id="5bd58-200">You can set who to notify and how they are notified.</span></span> <span data-ttu-id="5bd58-201">例如，自動通知貴組織的安全服務台，並讓他們聆聽緊急通話。</span><span class="sxs-lookup"><span data-stu-id="5bd58-201">For example, to automatically notify your organization's security desk and have them listen in on emergency calls.</span></span>  <span data-ttu-id="5bd58-202">您可以將此原則指派給使用者或網路網站，或同時指派給這兩者。</span><span class="sxs-lookup"><span data-stu-id="5bd58-202">This policy can either be assigned to users or network sites or both.</span></span> <span data-ttu-id="5bd58-203">您可以使用 New、Set 和 Grant CsTeamsEmergencyCallingPolicy Cmdlet 來管理此原則。</span><span class="sxs-lookup"><span data-stu-id="5bd58-203">You manage this policy by using the New-, Set- and Grant-CsTeamsEmergencyCallingPolicy  cmdlets.</span></span> 

<span data-ttu-id="5bd58-204">如需詳細資訊，請參閱[管理團隊中的緊急通話原則](manage-emergency-calling-policies.md)和[管理直接路由的緊急通話路由原則](manage-emergency-call-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5bd58-204">For more information, see [Manage emergency calling policies in Teams](manage-emergency-calling-policies.md) and [Manage emergency call routing policies for Direct Routing](manage-emergency-call-routing-policies.md).</span></span>


## <a name="enable-users-and-sites"></a><span data-ttu-id="5bd58-205">啟用使用者和網站</span><span class="sxs-lookup"><span data-stu-id="5bd58-205">Enable users and sites</span></span>

<span data-ttu-id="5bd58-206">您可以將**TeamsEmergencyCalling**和**TeamsEmergencyCallROuting**原則指派給使用者和網站。</span><span class="sxs-lookup"><span data-stu-id="5bd58-206">You can assign **TeamsEmergencyCalling** and **TeamsEmergencyCallROuting** policies to users and to sites.</span></span>  

<span data-ttu-id="5bd58-207">TeamsEmergencyCallRouting 原則只適用于直接路由。</span><span class="sxs-lookup"><span data-stu-id="5bd58-207">The TeamsEmergencyCallRouting policy applies to Direct Routing only.</span></span> <span data-ttu-id="5bd58-208">（雖然您可以將此原則指派給通話方案使用者，但原則將沒有任何效果。）</span><span class="sxs-lookup"><span data-stu-id="5bd58-208">(Although it's possible to assign this policy to a Calling Plan user, the policy will have no effect.)</span></span>

<span data-ttu-id="5bd58-209">例如，若要針對安全服務台通知啟用特定的使用者，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="5bd58-209">For example, to enable a specific user for security desk notification, use the following command:</span></span>

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

<span data-ttu-id="5bd58-210">若要將名為「Contoso 緊急通話原則1」的原則指派給 Site 1，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="5bd58-210">To assign a policy called "Contoso Emergency Calling Policy 1" to Site 1, use the following command:</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

<span data-ttu-id="5bd58-211">若要啟用緊急通話的特定直接路由使用者，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="5bd58-211">To enable a specific Direct Routing user for emergency calling, use the following command:</span></span>

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

<span data-ttu-id="5bd58-212">若要將名為「Contoso 紐約急救通話路由」的原則指派給 Site 1，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="5bd58-212">To assign a policy called "Contoso New York Emergency Call Routing" to Site 1, use the following command:</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

<span data-ttu-id="5bd58-213">如果您已將緊急通話原則指派給網路網站和使用者，而且如果該使用者是在該網路網站上，則指派給網路網站的原則會覆寫指派給使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="5bd58-213">If you assigned an emergency calling policy to a network site and to a user, and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>


## <a name="test-emergency-calling"></a><span data-ttu-id="5bd58-214">測試緊急通話</span><span class="sxs-lookup"><span data-stu-id="5bd58-214">Test emergency calling</span></span>

<span data-ttu-id="5bd58-215">美國的一些緊急路由服務提供者（ERSPs）提供緊急呼叫測試 bot。</span><span class="sxs-lookup"><span data-stu-id="5bd58-215">Some Emergency Routing Service Providers (ERSPs) in the United States offer an emergency calling test bot.</span></span>

- <span data-ttu-id="5bd58-216">**在美國撥打電話方案使用者**可以使用預先定義的測試緊急號碼933來驗證緊急通話設定。</span><span class="sxs-lookup"><span data-stu-id="5bd58-216">**Calling Plan users in the United States** can use the predefined test emergency number 933 to validate their emergency calling configuration.</span></span> <span data-ttu-id="5bd58-217">這個號碼會路由到 bot，然後回顯來電者電話號碼（呼叫線路識別碼）、緊急位址或位置，以及是否要先將呼叫自動路由到 PSAP 或篩選。</span><span class="sxs-lookup"><span data-stu-id="5bd58-217">This number is routed to a bot, which then echoes back the caller phone number (calling line ID), emergency address or location, and whether the call would be automatically routed to the PSAP or screened first.</span></span>

- <span data-ttu-id="5bd58-218">**在美國直接傳送路由的客戶**應該與其 ERSP，以進行測試服務。</span><span class="sxs-lookup"><span data-stu-id="5bd58-218">**Direct Routing customers in the United States** should coordinate with their ERSP for a test service.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="5bd58-219">相關主題</span><span class="sxs-lookup"><span data-stu-id="5bd58-219">Related topics</span></span>

- [<span data-ttu-id="5bd58-220">管理緊急通話</span><span class="sxs-lookup"><span data-stu-id="5bd58-220">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="5bd58-221">管理緊急電話原則</span><span class="sxs-lookup"><span data-stu-id="5bd58-221">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="5bd58-222">管理緊急呼叫路由策略</span><span class="sxs-lookup"><span data-stu-id="5bd58-222">Manage emergency call routing policies </span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="5bd58-223">新增、變更或移除貴組織的緊急位置</span><span class="sxs-lookup"><span data-stu-id="5bd58-223">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="5bd58-224">指派或變更使用者的緊急位置</span><span class="sxs-lookup"><span data-stu-id="5bd58-224">Assign or change an emergency location for your user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="5bd58-225">雲端語音功能的網路設定</span><span class="sxs-lookup"><span data-stu-id="5bd58-225">Network settings for cloud voice features</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="5bd58-226">管理雲端語音功能的網路拓撲</span><span class="sxs-lookup"><span data-stu-id="5bd58-226">Manage your network topology for cloud voice features</span></span>](manage-your-network-topology.md)
