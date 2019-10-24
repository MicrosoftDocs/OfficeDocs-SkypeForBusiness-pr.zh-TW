---
title: 設定動態緊急通話
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
description: 設定動態緊急通話
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b166c93bb213fab6e8025a1837ef67baa65c884
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/15/2019
ms.locfileid: "37639271"
---
# <a name="plan-and-configure-dynamic-emergency-calling-for-calling-plans"></a><span data-ttu-id="59764-103">規劃及設定通話方案的動態緊急通話</span><span class="sxs-lookup"><span data-stu-id="59764-103">Plan and configure dynamic emergency calling for Calling Plans</span></span>
<span data-ttu-id="59764-104">Microsoft 通話方案的動態緊急通話可提供根據團隊用戶端目前位置來設定和路由緊急通話的功能。</span><span class="sxs-lookup"><span data-stu-id="59764-104">Dynamic emergency calling for Microsoft Calling Plans provides the capability to configure and route emergency calls based on the current location of the Teams client.</span></span>  <span data-ttu-id="59764-105">自動路由至適當的公用安全回應點（PSAP）或通知安全服務台人員的功能，會視小組使用者使用的國家/地區而有所不同。</span><span class="sxs-lookup"><span data-stu-id="59764-105">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) or to notify security desk personnel varies depending on the country of usage of the Teams user.</span></span>  

> [!Note] 
> <span data-ttu-id="59764-106">動態緊急通話目前僅適用于美國。</span><span class="sxs-lookup"><span data-stu-id="59764-106">Dynamic emergency calling is currently available only in the United States.</span></span> <span data-ttu-id="59764-107">不過，在整個國家/地區的範圍內支援安全服務台通知。</span><span class="sxs-lookup"><span data-stu-id="59764-107">Security desk notification, however, is supported across country boundaries.</span></span>

<span data-ttu-id="59764-108">在**美國**境內，您可以設定動態緊急呼叫路由，如下所示：</span><span class="sxs-lookup"><span data-stu-id="59764-108">**Within the United States**, you can configure dynamic emergency call routing as follows:</span></span>
  
- <span data-ttu-id="59764-109">如果團隊用戶端位於租使用者定義的動態緊急位置，來自該用戶端的緊急呼叫會自動路由至該地理位置的 PSAP 服務。</span><span class="sxs-lookup"><span data-stu-id="59764-109">If a Teams client is located at a tenant-defined dynamic emergency location, emergency calls from that client are automatically routed to the PSAP serving that geographic location.</span></span>  

- <span data-ttu-id="59764-110">如果團隊用戶端不在租使用者的動態緊急位置，來自該用戶端的緊急呼叫是由國內話務中心加以遮罩，在將來電轉接到該地理位置的 PSAP 之前，決定呼叫者的位置。</span><span class="sxs-lookup"><span data-stu-id="59764-110">If a Teams client is not located at a tenant-defined dynamic emergency location, emergency calls from that client are screened by a national call center to determine the location of the caller before transferring the call to the PSAP serving that geographic location.</span></span>

<span data-ttu-id="59764-111">您可以設定安全服務台通知，如下所示：</span><span class="sxs-lookup"><span data-stu-id="59764-111">You can configure security desk notification as follows:</span></span>

- <span data-ttu-id="59764-112">如果團隊用戶端位於租使用者定義的網路網站上，系統會通知針對該網站設定的安全性群組成員。</span><span class="sxs-lookup"><span data-stu-id="59764-112">If a Teams client is located at a tenant-defined network site, the security group members configured for that site will be notified.</span></span>

- <span data-ttu-id="59764-113">如果團隊用戶端不位於租使用者的網路網站上，系統會通知使用者設定的安全性群組成員。</span><span class="sxs-lookup"><span data-stu-id="59764-113">If a Teams client is not located at a tenant-defined network site, the security group members configured for the user will be notified.</span></span>

<span data-ttu-id="59764-114">**在美國以外**，緊急通話會傳送到已對應給使用者的電話號碼的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="59764-114">**Outside of the United States**, emergency calls are routed to the PSAP that is mapped to the phone number assigned to the user.</span></span>  <span data-ttu-id="59764-115">某些國家/地區（例如英國及加拿大），在將呼叫者轉移至適當的 PSAP 之前，會 nationally [呼叫] 的畫面，而其他人則直接路由至 PSAP，而不論使用者目前位於何處。</span><span class="sxs-lookup"><span data-stu-id="59764-115">Some countries, such as the Great Britain and Canada, screen the calls nationally before transferring the caller to the appropriate PSAP, while others route directly to the PSAP regardless of where the user is currently located.</span></span> 

<span data-ttu-id="59764-116">請注意，您可以為所有通話方案使用者設定動態的 security 辦公桌通知。</span><span class="sxs-lookup"><span data-stu-id="59764-116">Note that you can configure dynamic security desk notification for all Calling Plan users.</span></span>


## <a name="supported-clients"></a><span data-ttu-id="59764-117">支援的用戶端</span><span class="sxs-lookup"><span data-stu-id="59764-117">Supported clients</span></span>

<span data-ttu-id="59764-118">目前支援下列用戶端。</span><span class="sxs-lookup"><span data-stu-id="59764-118">The following clients are currently supported.</span></span>  <span data-ttu-id="59764-119">經常回到查看此清單的更新。</span><span class="sxs-lookup"><span data-stu-id="59764-119">Check back often to see updates to this list.</span></span>

- <span data-ttu-id="59764-120">Windows 版團隊桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="59764-120">Teams desktop client for Windows</span></span>
- <span data-ttu-id="59764-121">Mac 版團隊桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="59764-121">Teams desktop client for Mac</span></span>

## <a name="configure-dynamic-emergency-calling"></a><span data-ttu-id="59764-122">設定動態緊急通話</span><span class="sxs-lookup"><span data-stu-id="59764-122">Configure dynamic emergency calling</span></span>

<span data-ttu-id="59764-123">若要設定動態緊急通話，您需要執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="59764-123">To configure dynamic emergency calling, you need to perform the following tasks:</span></span>

- [<span data-ttu-id="59764-124">設定緊急位址</span><span class="sxs-lookup"><span data-stu-id="59764-124">Configure emergency addresses</span></span>](#configure-emergency-addresses)
- [<span data-ttu-id="59764-125">設定網路設定</span><span class="sxs-lookup"><span data-stu-id="59764-125">Configure network settings</span></span>](#configure-network-settings)
- [<span data-ttu-id="59764-126">設定位置資訊服務</span><span class="sxs-lookup"><span data-stu-id="59764-126">Configure Location Information Service</span></span>](#configure-location-information-service)
- [<span data-ttu-id="59764-127">設定緊急原則</span><span class="sxs-lookup"><span data-stu-id="59764-127">Configure emergency policies</span></span>](#configure-emergency-policies)
- [<span data-ttu-id="59764-128">啟用使用者和網站</span><span class="sxs-lookup"><span data-stu-id="59764-128">Enable users and sites</span></span>](#enable-users-and-sites)
- [<span data-ttu-id="59764-129">測試緊急通話</span><span class="sxs-lookup"><span data-stu-id="59764-129">Test emergency calling</span></span>](#test-emergency-calling)


### <a name="configure-emergency-addresses"></a><span data-ttu-id="59764-130">設定緊急位址</span><span class="sxs-lookup"><span data-stu-id="59764-130">Configure emergency addresses</span></span>

<span data-ttu-id="59764-131">若要支援在美國自動路由，您必須完整設定指派給網路識別碼之緊急位置一部分的市政位址，並包含相關聯的地功能變數代碼。</span><span class="sxs-lookup"><span data-stu-id="59764-131">To support automated routing within the United States, you must fully configure the civic address that is part of the emergency locations that are assigned to network identifiers--and include the associated geo codes.</span></span> <span data-ttu-id="59764-132">（沒有地理程式碼的緊急位址不能指派給動態位置所需的網路識別碼）。</span><span class="sxs-lookup"><span data-stu-id="59764-132">(Emergency addresses without geo-codes cannot be assigned to the network identifiers that are required for dynamic locations.)</span></span>

- <span data-ttu-id="59764-133">如果您透過 Microsoft 團隊系統管理中心輸入緊急位址，則如果找到相符專案，就會自動包含 geo 代碼。</span><span class="sxs-lookup"><span data-stu-id="59764-133">If you enter an emergency address via the Microsoft Teams admin center, the geo codes are automatically included if a match is found.</span></span>

- <span data-ttu-id="59764-134">如果沒有自動找到相符的專案，您就有機會手動建立緊急位址。</span><span class="sxs-lookup"><span data-stu-id="59764-134">If a match is not automatically found, you will have the opportunity to manually create an emergency address.</span></span>  

<span data-ttu-id="59764-135">這表示如果將現有的緊急位址設定為緊急通話，則必須重新建立相同的位址，才能包含 geo 碼。</span><span class="sxs-lookup"><span data-stu-id="59764-135">This means that if an existing emergency address is configured for emergency calling, the same address needs to be re-created to include the geo codes.</span></span>  <span data-ttu-id="59764-136">若要區分兩個位址，您應該包含不同的描述。</span><span class="sxs-lookup"><span data-stu-id="59764-136">To distinguish between the two addresses, you should include a different description.</span></span> <span data-ttu-id="59764-137">新的緊急位址可以指派給擁有舊位址的使用者。</span><span class="sxs-lookup"><span data-stu-id="59764-137">The new emergency address can be assigned to the users who have the old address.</span></span> <span data-ttu-id="59764-138">完全遷移後，就可以刪除舊的位址。</span><span class="sxs-lookup"><span data-stu-id="59764-138">When fully migrated, the old address can be deleted.</span></span> 

<span data-ttu-id="59764-139">如需有關設定緊急位址的詳細資訊，請參閱[什麼是緊急位置、地點及呼叫路由？](what-are-emergency-locations-addresses-and-call-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="59764-139">For more information about configuring emergency addresses, see [What are emergency locations, places, and call routing?](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>

### <a name="configure-network-settings"></a><span data-ttu-id="59764-140">設定網路設定</span><span class="sxs-lookup"><span data-stu-id="59764-140">Configure network settings</span></span>

<span data-ttu-id="59764-141">您必須設定網路設定，以動態取得路由緊急通話的緊急位置，也可以選擇提供安全服務台通知的動態設定。</span><span class="sxs-lookup"><span data-stu-id="59764-141">You need to configure network settings to dynamically obtain an emergency location used for routing emergency calls and, optionally, to provide dynamic configuration of security desk notifications.</span></span> <span data-ttu-id="59764-142">所需的緊急通話體驗將指示需要設定的網路設定。</span><span class="sxs-lookup"><span data-stu-id="59764-142">The emergency calling experience desired will dictate which network settings need to be configured.</span></span> 

<span data-ttu-id="59764-143">請牢記下列定義：</span><span class="sxs-lookup"><span data-stu-id="59764-143">Keep the following definitions in mind:</span></span>

- <span data-ttu-id="59764-144">受信任的 IP 包含商業網路的網際網路外部 Ip 集合，並用來判斷使用者的端點是否在商業網路內。</span><span class="sxs-lookup"><span data-stu-id="59764-144">Trusted IP’s contain a collection of the Internet external IPs of the enterprise network and are used to determine if the user’s endpoint is inside the corporate network.</span></span> <span data-ttu-id="59764-145">只有在使用者的外部 IP 與信任的 IP 集合中的 IP 相符時，才會啟用動態位置。</span><span class="sxs-lookup"><span data-stu-id="59764-145">Dynamic locations will only be enabled if the user’s external IP matches an IP in the Trusted IP collection.</span></span>  <span data-ttu-id="59764-146">您可以針對 IPv4 或 IPv6 IP 位址進行相符，並視傳送至網路設定的 IP 資料包格式而定。</span><span class="sxs-lookup"><span data-stu-id="59764-146">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span>

- <span data-ttu-id="59764-147">網路區域包含一個網路網站集合。</span><span class="sxs-lookup"><span data-stu-id="59764-147">A network region contains a collection of network sites.</span></span> 

- <span data-ttu-id="59764-148">網路網站代表貴組織有實體價值（例如，辦公室、一組建築物或校園）的位置。</span><span class="sxs-lookup"><span data-stu-id="59764-148">A network site represents a location where your organization has a physical value, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="59764-149">這些網站是由 IP 子網的集合所定義。</span><span class="sxs-lookup"><span data-stu-id="59764-149">These sites are defined as a collection of IP subnets.</span></span>

- <span data-ttu-id="59764-150">網路子網必須與特定的網路網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="59764-150">A network subnet must be associated with a specific network site.</span></span> <span data-ttu-id="59764-151">用戶端的位置是根據網路子網和相關的網路網站來決定。</span><span class="sxs-lookup"><span data-stu-id="59764-151">A client's location is determined based on the network subnet and the associated network site.</span></span>  


<span data-ttu-id="59764-152">通話方案使用者：</span><span class="sxs-lookup"><span data-stu-id="59764-152">For Calling Plan users:</span></span>

- <span data-ttu-id="59764-153">如果需要對 security 辦公桌通知進行動態設定，則您必須設定信任的 IP 位址和網路網站。</span><span class="sxs-lookup"><span data-stu-id="59764-153">If dynamic configuration of security desk notification is required, then you must configure both Trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="59764-154">如果只需要動態位置，則您必須只設定信任的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="59764-154">If only dynamic locations are required, then you must configure only Trusted IP addresses.</span></span> 

- <span data-ttu-id="59764-155">如果兩者都不是必要的，則不需要設定網路設定。</span><span class="sxs-lookup"><span data-stu-id="59764-155">If neither are required, then configuration of network settings is not required.</span></span> 

<span data-ttu-id="59764-156">如需詳細資訊，請參閱[設定以位置為基礎的路由的網路設定](location-based-routing-configure-network-settings.md)，說明如何設定網路設定。</span><span class="sxs-lookup"><span data-stu-id="59764-156">For more information, see [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md), which describes how to configure network settings.</span></span> <span data-ttu-id="59764-157">（本文中的資訊同時適用于通話方案和直接路由）。</span><span class="sxs-lookup"><span data-stu-id="59764-157">(The information in this article applies to both Calling Plans and Direct Routing.)</span></span>


### <a name="configure-location-information-service"></a><span data-ttu-id="59764-158">設定位置資訊服務</span><span class="sxs-lookup"><span data-stu-id="59764-158">Configure Location Information Service</span></span>

<span data-ttu-id="59764-159">團隊用戶端會從與不同網路識別碼相關聯的緊急位置取得緊急位址。</span><span class="sxs-lookup"><span data-stu-id="59764-159">A Teams client obtains emergency addresses from the emergency locations associated with different network identifiers.</span></span>  <span data-ttu-id="59764-160">同時支援子網和無線存取點。</span><span class="sxs-lookup"><span data-stu-id="59764-160">Subnets and Wireless Access Points are both supported.</span></span> <span data-ttu-id="59764-161">（乙太網上交換器/埠的支援已擱置。）</span><span class="sxs-lookup"><span data-stu-id="59764-161">(Support for Ethernet switch/port is pending.)</span></span>

<span data-ttu-id="59764-162">若要將位置資訊服務（.LIS）與網路識別碼及緊急位置進行設定，請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="59764-162">To configure the Location Information Service (LIS) with network identifiers and emergency locations, use the following cmdlets:</span></span>

- <span data-ttu-id="59764-163">取得、設定、移除-CsOnlineLisPort</span><span class="sxs-lookup"><span data-stu-id="59764-163">Get, Set, Remove -CsOnlineLisPort</span></span>
- <span data-ttu-id="59764-164">取得、設定、移除-CsOnlineLisSwitch</span><span class="sxs-lookup"><span data-stu-id="59764-164">Get, Set, Remove -CsOnlineLisSwitch</span></span>
- <span data-ttu-id="59764-165">取得、設定、移除-CsOnlineLisSubnet</span><span class="sxs-lookup"><span data-stu-id="59764-165">Get, Set, Remove -CsOnlineLisSubnet</span></span>
- <span data-ttu-id="59764-166">取得、設定、移除-CsOnlineLisWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="59764-166">Get, Set, Remove -CsOnlineLisWirelessAccessPoint</span></span> 

> [!Important] 
> <span data-ttu-id="59764-167">如果子網是作為網路網站的一部分使用，則必須在位置資訊服務中重新定義，才能呈現動態位置。</span><span class="sxs-lookup"><span data-stu-id="59764-167">If subnets are being used as part of network sites, they must be redefined in the Location Information Service to render dynamic locations.</span></span>


### <a name="configure-emergency-policies"></a><span data-ttu-id="59764-168">設定緊急原則</span><span class="sxs-lookup"><span data-stu-id="59764-168">Configure emergency policies</span></span>

<span data-ttu-id="59764-169">緊急原則決定貴組織中的使用者進行緊急通話時，會發生什麼情況。</span><span class="sxs-lookup"><span data-stu-id="59764-169">Emergency policies determine what happens when a user in your organization makes an emergency call.</span></span>  <span data-ttu-id="59764-170">您可以設定要通知的人員，以及使用者呼叫緊急服務時通知的方式。</span><span class="sxs-lookup"><span data-stu-id="59764-170">You can set who to notify and how they are notified when a user calls emergency services.</span></span> <span data-ttu-id="59764-171">例如，您可以將原則設定設定為自動通知貴組織的安全服務台，並讓他們在緊急通話中聆聽。</span><span class="sxs-lookup"><span data-stu-id="59764-171">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in on emergency calls.</span></span>

<span data-ttu-id="59764-172">您可以使用新的 CsTeamsEmergencyCalling 原則 Cmdlet 來管理緊急原則。</span><span class="sxs-lookup"><span data-stu-id="59764-172">You manage emergency policies by using the New-, Set- and Grant-CsTeamsEmergencyCalling Policy cmdlets.</span></span>  <span data-ttu-id="59764-173">如需詳細資訊，請參閱[管理團隊中的緊急通話原則](manage-emergency-calling-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="59764-173">For more information, see [Manage emergency calling policies in Teams](manage-emergency-calling-policies.md).</span></span>


### <a name="enable-users-and-sites"></a><span data-ttu-id="59764-174">啟用使用者和網站</span><span class="sxs-lookup"><span data-stu-id="59764-174">Enable users and sites</span></span>

<span data-ttu-id="59764-175">當通話方案使用者自動啟用緊急通話時，您必須先設定緊急呼叫原則，以讓使用者取得安全服務台通知，如下列範例所示：</span><span class="sxs-lookup"><span data-stu-id="59764-175">While Calling Plan users are automatically enabled for emergency calling, you must enable users for security desk notification by configuring the emergency calling policy as shown in the following example:</span></span>


```
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

<span data-ttu-id="59764-176">您也可以將緊急呼叫原則指派給網路網站，如下列範例所示，該範例會將名為「Contoso 急診通話原則1」的原則指派給 Site 1：</span><span class="sxs-lookup"><span data-stu-id="59764-176">You can also assign the emergency calling policy to a network site as shown in the following example, which assigns a policy called "Contoso Emergency Calling Policy 1" to Site 1:</span></span>

```
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

<span data-ttu-id="59764-177">如果您已將緊急通話原則指派給網路網站和使用者，而且如果該使用者是在該網路網站上，則指派給網路網站的原則會覆寫指派給使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="59764-177">If you assigned an emergency calling policy to a network site and to a user, and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>


### <a name="test-emergency-calling"></a><span data-ttu-id="59764-178">測試緊急通話</span><span class="sxs-lookup"><span data-stu-id="59764-178">Test emergency calling</span></span>

<span data-ttu-id="59764-179">若要在美國測試緊急通話，請使用預先定義的測試緊急號碼933。</span><span class="sxs-lookup"><span data-stu-id="59764-179">To test emergency calling in the United States, use the predefined test emergency number 933.</span></span>  <span data-ttu-id="59764-180">這個號碼會路由到 bot，然後回顯來電者電話號碼（呼叫線路識別碼）、緊急位址或位置，以及是否要先將通話自動路由到 PSAP 或篩選。</span><span class="sxs-lookup"><span data-stu-id="59764-180">This number is routed to a bot, which then echoes back the caller phone number (calling line ID), emergency address or location, and whether the call is automatically routed to the PSAP or screened first.</span></span>  