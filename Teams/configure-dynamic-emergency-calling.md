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
ms.openlocfilehash: 4f2d2f440296316cd448013022494021e3557c32
ms.sourcegitcommit: 19662d4bc4070f6031084d93e8794e0e02decd2b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/01/2020
ms.locfileid: "47321736"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a><span data-ttu-id="b8fae-103">規劃和設定動態緊急電話</span><span class="sxs-lookup"><span data-stu-id="b8fae-103">Plan and configure dynamic emergency calling</span></span> 

<span data-ttu-id="b8fae-104">Microsoft 通話方案和電話系統直連路由的動態緊急通話可提供設定及路由緊急通話的功能，並根據團隊用戶端的目前位置來通知安全人員。</span><span class="sxs-lookup"><span data-stu-id="b8fae-104">Dynamic emergency calling for Microsoft Calling Plans and Phone System Direct Routing provides the capability to configure and route emergency calls and notify security personnel based on the current location of the Teams client.</span></span>  

<span data-ttu-id="b8fae-105">根據租使用者管理員定義的網路拓撲，小組用戶端會在 (.LIS) 的位置資訊服務要求中提供網路連線資訊。</span><span class="sxs-lookup"><span data-stu-id="b8fae-105">Based on the network topology that the tenant administrator defines, the Teams client provides network connectivity information in a request to the Location Information Service (LIS).</span></span> <span data-ttu-id="b8fae-106">如果有相符的專案，則 .LIS 會傳回用戶端的位置。</span><span class="sxs-lookup"><span data-stu-id="b8fae-106">If there's a match, the LIS returns a location to the client.</span></span> <span data-ttu-id="b8fae-107">這個位置資料會傳回用戶端。</span><span class="sxs-lookup"><span data-stu-id="b8fae-107">This location data is transmitted back to the client.</span></span>  

<span data-ttu-id="b8fae-108">團隊用戶端包含位置資料做為緊急通話的一部分。</span><span class="sxs-lookup"><span data-stu-id="b8fae-108">The Teams client includes location data as part of an emergency call.</span></span> <span data-ttu-id="b8fae-109">然後，緊急服務提供者會使用這個資料來判斷適當的公用安全回應點 (PSAP) ，並將呼叫路由到該 PSAP，這可讓 PSAP dispatcher 取得來電者的位置。</span><span class="sxs-lookup"><span data-stu-id="b8fae-109">This data is then used by the emergency service provider to determine the appropriate Public Safety Answering Point (PSAP) and to route the call to that PSAP, which allows the PSAP dispatcher to obtain the caller's location.</span></span>  

<span data-ttu-id="b8fae-110">針對動態緊急通話，必須發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="b8fae-110">For dynamic emergency calling, the following must occur:</span></span>

1. <span data-ttu-id="b8fae-111">網路系統管理員會設定網路設定和 .LIS，以建立網路/緊急位置地圖。</span><span class="sxs-lookup"><span data-stu-id="b8fae-111">The network administrator configures network settings and the LIS to create a network/emergency location map.</span></span>

   <span data-ttu-id="b8fae-112">針對直接路由，需要進行額外的設定，以路由緊急呼叫並可能提供合作夥伴連線。</span><span class="sxs-lookup"><span data-stu-id="b8fae-112">For Direct Routing, additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="b8fae-113">系統管理員必須設定與緊急路由服務的連線， (ERS) 提供者 (美國) ， **或** 針對緊急位置識別編號 (ELIN) 應用程式設定會話框線控制器 (SBC) 。</span><span class="sxs-lookup"><span data-stu-id="b8fae-113">The administrator must configure connection to an Emergency Routing Service (ERS) provider (United States) **OR** configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

2. <span data-ttu-id="b8fae-114">在啟動期間及之後定期進行，或當網路連線變更時，小組用戶端會將包含其網路連線資訊的位置要求傳送到網路設定和 IIS 類型。</span><span class="sxs-lookup"><span data-stu-id="b8fae-114">During startup and periodically afterwards, or when a network connection is changed, the Teams client sends a location request that contains its network connectivity information to the network settings and the LIS.</span></span>

   - <span data-ttu-id="b8fae-115">如果網路設定網站相符，緊急通話原則會傳回該網站的小組用戶端。</span><span class="sxs-lookup"><span data-stu-id="b8fae-115">If there's a network settings site match – emergency calling policies are returned to the Teams client from that site.</span></span> <span data-ttu-id="b8fae-116"> (如需原則的詳細資訊，請參閱 [設定緊急原則](#configure-emergency-policies)) 。</span><span class="sxs-lookup"><span data-stu-id="b8fae-116">(For more information about policies, see [Configure emergency policies](#configure-emergency-policies)).</span></span>

   - <span data-ttu-id="b8fae-117">如果有一個根目錄相符的專案，則會將團隊用戶端連接至的網元中的緊急位置傳回給團隊用戶端。</span><span class="sxs-lookup"><span data-stu-id="b8fae-117">If there's an LIS match – an emergency location from the network element the Teams client is connected to is returned to the Teams client.</span></span> <span data-ttu-id="b8fae-118">會以下列循序執行相符，且會傳回第一個相符的結果：</span><span class="sxs-lookup"><span data-stu-id="b8fae-118">The match is performed in the following order with the first matched result being returned:</span></span>
       - <span data-ttu-id="b8fae-119">WPA</span><span class="sxs-lookup"><span data-stu-id="b8fae-119">WAP</span></span>
       - <span data-ttu-id="b8fae-120">乙太網路交換器/埠</span><span class="sxs-lookup"><span data-stu-id="b8fae-120">Ethernet Switch/Port</span></span>
       - <span data-ttu-id="b8fae-121">乙太網交換器</span><span class="sxs-lookup"><span data-stu-id="b8fae-121">Ethernet Switch</span></span>
       - <span data-ttu-id="b8fae-122">子網路</span><span class="sxs-lookup"><span data-stu-id="b8fae-122">Subnet</span></span>

3. <span data-ttu-id="b8fae-123">當團隊用戶端進行緊急通話時，緊急位置會傳達給 PSTN 網路。</span><span class="sxs-lookup"><span data-stu-id="b8fae-123">When the Teams client makes an emergency call, the emergency location is conveyed to the PSTN network.</span></span>

   <span data-ttu-id="b8fae-124">如果是直接路由，系統管理員必須設定 SBC 來傳送緊急呼叫給 ERS 提供者，或設定 SBC ELIN 應用程式。</span><span class="sxs-lookup"><span data-stu-id="b8fae-124">For Direct Routing, the administrator must configure the SBC to send emergency calls to the ERS provider or configure the SBC ELIN application.</span></span>

<span data-ttu-id="b8fae-125">本文包含下列各節。</span><span class="sxs-lookup"><span data-stu-id="b8fae-125">This article contains the following sections.</span></span>

- [<span data-ttu-id="b8fae-126">設定緊急位址</span><span class="sxs-lookup"><span data-stu-id="b8fae-126">Configure emergency addresses</span></span>](#assign-emergency-addresses)
- [<span data-ttu-id="b8fae-127">設定網路設定</span><span class="sxs-lookup"><span data-stu-id="b8fae-127">Configure network settings</span></span>](#configure-network-settings)
- [<span data-ttu-id="b8fae-128">設定位置資訊服務</span><span class="sxs-lookup"><span data-stu-id="b8fae-128">Configure Location Information Service</span></span>](#configure-location-information-service)
- [<span data-ttu-id="b8fae-129">設定緊急原則</span><span class="sxs-lookup"><span data-stu-id="b8fae-129">Configure emergency policies</span></span>](#configure-emergency-policies)
- [<span data-ttu-id="b8fae-130">啟用使用者和網站</span><span class="sxs-lookup"><span data-stu-id="b8fae-130">Enable users and sites</span></span>](#enable-users-and-sites)
- [<span data-ttu-id="b8fae-131">測試緊急通話</span><span class="sxs-lookup"><span data-stu-id="b8fae-131">Test emergency calling</span></span>](#test-emergency-calling)

<span data-ttu-id="b8fae-132">若要將自動路由至適當的公用安全應答點， (PSAP) 會根據小組使用者使用的國家/地區而有所不同。</span><span class="sxs-lookup"><span data-stu-id="b8fae-132">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) varies depending on the country of usage of the Teams user.</span></span>

<span data-ttu-id="b8fae-133">如需緊急通話的詳細資訊，包括緊急位址及緊急通話路由的相關資訊、國家/地區的相關資訊，以及網路設定和網路拓朴的相關資訊，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="b8fae-133">For more information about emergency calling, including information about emergency addresses and emergency call routing, information specific to countries, and information about network settings and network topology, see the following:</span></span>

- [<span data-ttu-id="b8fae-134">管理緊急通話</span><span class="sxs-lookup"><span data-stu-id="b8fae-134">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="b8fae-135">管理雲端語音功能的網路設定</span><span class="sxs-lookup"><span data-stu-id="b8fae-135">Manage network settings for cloud voice features</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="b8fae-136">管理雲端語音功能的網路拓撲</span><span class="sxs-lookup"><span data-stu-id="b8fae-136">Manage your network topology for cloud voice features</span></span>](manage-your-network-topology.md)

## <a name="supported-clients"></a><span data-ttu-id="b8fae-137">支援的用戶端</span><span class="sxs-lookup"><span data-stu-id="b8fae-137">Supported clients</span></span>

<span data-ttu-id="b8fae-138">目前支援下列用戶端。</span><span class="sxs-lookup"><span data-stu-id="b8fae-138">The following clients are currently supported.</span></span>  <span data-ttu-id="b8fae-139">經常回到查看此清單的更新。</span><span class="sxs-lookup"><span data-stu-id="b8fae-139">Check back often to see updates to this list.</span></span>

- <span data-ttu-id="b8fae-140">Microsoft Windows 版團隊桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="b8fae-140">Teams desktop client for Microsoft Windows</span></span>
- <span data-ttu-id="b8fae-141">Apple macOS 的小組桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="b8fae-141">Teams desktop client for Apple macOS</span></span>
- <span data-ttu-id="b8fae-142">Apple iOS 用戶端版本1.0.92.2019121004 和 App Store 1.0.92 及更高版本的團隊行動用戶端</span><span class="sxs-lookup"><span data-stu-id="b8fae-142">Teams mobile client for Apple iOS client version 1.0.92.2019121004 and App Store version 1.0.92 and greater</span></span>
- <span data-ttu-id="b8fae-143">適用于 Android 用戶端和 Google Play 商店版本 1416/1.0.0.2019121201 及更高版本的團隊行動用戶端</span><span class="sxs-lookup"><span data-stu-id="b8fae-143">Teams mobile client for Android client and Google Play store version 1416/1.0.0.2019121201 and greater</span></span>
- <span data-ttu-id="b8fae-144">團隊手機版本 1449/1.0.94.2019110802 及更高版本</span><span class="sxs-lookup"><span data-stu-id="b8fae-144">Teams phone version 1449/1.0.94.2019110802 and greater</span></span>
- <span data-ttu-id="b8fae-145">團隊聊天室版本4.4.25.0 及更高版本</span><span class="sxs-lookup"><span data-stu-id="b8fae-145">Teams Rooms version 4.4.25.0 and greater</span></span>

> [!NOTE]
> <span data-ttu-id="b8fae-146">小組網頁用戶端不支援動態緊急通話，包括 security 辦公桌通知。</span><span class="sxs-lookup"><span data-stu-id="b8fae-146">Dynamic emergency calling including security desk notification isn't supported on the Teams web client.</span></span> <span data-ttu-id="b8fae-147">若要防止使用者使用團隊網頁用戶端呼叫 PSTN 號碼，您可以設定小組通話原則，然後關閉 [ **允許 WEB PSTN 呼叫** ] 設定。</span><span class="sxs-lookup"><span data-stu-id="b8fae-147">To prevent users from using the Teams web client to call PSTN numbers, you can set a Teams calling policy and turn off the **Allow web PSTN calling** setting.</span></span> <span data-ttu-id="b8fae-148">若要深入瞭解，請參閱在團隊和[設定 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)[中呼叫原則](teams-calling-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="b8fae-148">To learn more, see [Calling policies in Teams](teams-calling-policy.md) and [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span>

## <a name="assign-emergency-addresses"></a><span data-ttu-id="b8fae-149">指派緊急位址</span><span class="sxs-lookup"><span data-stu-id="b8fae-149">Assign emergency addresses</span></span>

<span data-ttu-id="b8fae-150">您可以將緊急位址指派給呼叫方案使用者，以及動態取得位置所需的網路識別碼。</span><span class="sxs-lookup"><span data-stu-id="b8fae-150">You can assign emergency addresses to both Calling Plan users and to the network identifiers that are required for dynamically obtaining a location.</span></span> <span data-ttu-id="b8fae-151">支援 (子網和 WiFi 存取點。</span><span class="sxs-lookup"><span data-stu-id="b8fae-151">(Subnet and WiFi AP are supported.</span></span> <span data-ttu-id="b8fae-152">在 Windows 8.1 和更新版本上支援乙太網交換器/埠) 。</span><span class="sxs-lookup"><span data-stu-id="b8fae-152">Ethernet switch/port is supported on Windows 8.1 and later at this time).</span></span>

<span data-ttu-id="b8fae-153">若要支援在美國的緊急通話自動路由，您必須確認指派給網路識別碼的緊急位置包含關聯的地功能變數代碼。</span><span class="sxs-lookup"><span data-stu-id="b8fae-153">To support automated routing of emergency calls within the United States, you must ensure that the emergency locations that are assigned to network identifiers include the associated geo codes.</span></span> <span data-ttu-id="b8fae-154"> (沒有地理程式碼的緊急位址無法指派給動態位置所需的網路識別碼。 ) </span><span class="sxs-lookup"><span data-stu-id="b8fae-154">(Emergency addresses without geo codes can't be assigned to the network identifiers that are required for dynamic locations.)</span></span>

<span data-ttu-id="b8fae-155">Azure 對應是用來進行位置服務的。</span><span class="sxs-lookup"><span data-stu-id="b8fae-155">Azure Maps is used for location-based services.</span></span>  <span data-ttu-id="b8fae-156">當您使用 Microsoft 團隊系統管理中心輸入緊急位址時，小組會檢查 Azure 對應位址：</span><span class="sxs-lookup"><span data-stu-id="b8fae-156">When you enter an emergency address by using the Microsoft Teams admin center, Teams checks Azure Maps for the address:</span></span>

- <span data-ttu-id="b8fae-157">如果找到相符的位置，系統會自動包含地區代碼。</span><span class="sxs-lookup"><span data-stu-id="b8fae-157">If a match is found, the geo codes are automatically included.</span></span>

- <span data-ttu-id="b8fae-158">如果找不到相符的專案，您就有機會手動建立緊急位址。</span><span class="sxs-lookup"><span data-stu-id="b8fae-158">If a match isn't found, you will have the opportunity to manually create an emergency address.</span></span> <span data-ttu-id="b8fae-159">您可以使用釘選功能來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="b8fae-159">You can use the PIN drop feature to do this.</span></span> 

<span data-ttu-id="b8fae-160">這表示，如果為指派給呼叫計畫使用者的現有緊急位置是針對動態位置所設計，則必須重新建立相同的位址，才能包含 geo 碼。</span><span class="sxs-lookup"><span data-stu-id="b8fae-160">This means that if an existing emergency location that is created for assigning to Calling Plan users is intended for a dynamic location, the same address needs to be re-created to include the geo codes.</span></span> <span data-ttu-id="b8fae-161">若要區分兩個位置，您應該包含不同的描述。</span><span class="sxs-lookup"><span data-stu-id="b8fae-161">To distinguish between the two locations, you should include a different description.</span></span> <span data-ttu-id="b8fae-162">新的緊急位置可以指派給擁有舊位置的使用者。</span><span class="sxs-lookup"><span data-stu-id="b8fae-162">The new emergency location can be assigned to the users who have the old location.</span></span> <span data-ttu-id="b8fae-163">完全遷移後，就可以刪除舊位置。</span><span class="sxs-lookup"><span data-stu-id="b8fae-163">When fully migrated, the old location can be deleted.</span></span>

<span data-ttu-id="b8fae-164">您可以在 Microsoft [團隊管理中心] 或 [使用 PowerShell] 中新增及指派緊急位址。</span><span class="sxs-lookup"><span data-stu-id="b8fae-164">You add and assign emergency addresses in the Microsoft Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="b8fae-165">如需詳細資訊，請參閱為 [您的組織新增緊急位置](add-change-remove-emergency-location-organization.md) ，以及為 [使用者指派緊急位置](assign-change-emergency-location-user.md)。</span><span class="sxs-lookup"><span data-stu-id="b8fae-165">For more information, see [Add an emergency location for your organization](add-change-remove-emergency-location-organization.md) and [Assign an emergency location for a user](assign-change-emergency-location-user.md).</span></span>

## <a name="configure-network-settings"></a><span data-ttu-id="b8fae-166">設定網路設定</span><span class="sxs-lookup"><span data-stu-id="b8fae-166">Configure network settings</span></span>

<span data-ttu-id="b8fae-167">[網路設定] 可用來判斷團隊用戶端的位置，以及動態取得緊急通話原則與緊急位置。</span><span class="sxs-lookup"><span data-stu-id="b8fae-167">Network settings are used to determine the location of a Teams client, and to dynamically obtain emergency calling policies and an emergency location.</span></span> <span data-ttu-id="b8fae-168">您可以根據貴組織希望緊急通話運作的方式來設定網路設定。</span><span class="sxs-lookup"><span data-stu-id="b8fae-168">You can configure network settings according to how your organization wants emergency calling to function.</span></span>

<span data-ttu-id="b8fae-169">[網路設定] 包含包含子網集合的網站，而這些網站則專門用於動態原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="b8fae-169">Network settings include sites that include a collection of subnets and these are used exclusively for dynamic policy assignment to users.</span></span> <span data-ttu-id="b8fae-170">例如，緊急通話原則與緊急呼叫路由策略可能會指派給「雷蒙德網站」，讓從家裡或其他 Microsoft 位置進行漫遊的任何使用者都是以緊急電話號碼、路由及安全服務台進行設定。</span><span class="sxs-lookup"><span data-stu-id="b8fae-170">For example, an emergency calling policy and an emergency call routing policy might be assigned to the "Redmond site" so that any user that roams from home or another Microsoft location is configured with emergency numbers, routing, and security desk specific to Redmond.</span></span>  

>[!Note]
><span data-ttu-id="b8fae-171">子網也可以在 .LIS 中定義，而且可以與緊急位置相關聯。</span><span class="sxs-lookup"><span data-stu-id="b8fae-171">Subnets can also be defined in LIS and can be associated with an emergency location.</span></span>  

<span data-ttu-id="b8fae-172">請牢記下列定義。</span><span class="sxs-lookup"><span data-stu-id="b8fae-172">Keep the following definitions in mind.</span></span> <span data-ttu-id="b8fae-173">如需詳細資訊，請參閱 [雲端語音功能的網路設定](cloud-voice-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="b8fae-173">For more information, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

- <span data-ttu-id="b8fae-174">[信任的 IP 位址] 包含商業網路的網際網路外部 IP 位址集合，並用來判斷使用者的端點是否在商業網路內。</span><span class="sxs-lookup"><span data-stu-id="b8fae-174">Trusted IP addresses contain a collection of the internet external IP addresses of the enterprise network and are used to determine if the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="b8fae-175">只要使用者的外部 IP 位址與信任的 IP 位址中的 IP 位址相符，就會嘗試取得動態原則或位置。</span><span class="sxs-lookup"><span data-stu-id="b8fae-175">An attempt to obtain a dynamic policy or location will only be made if the user's external IP address matches an IP address in the trusted IP address.</span></span> <span data-ttu-id="b8fae-176">您可以針對 IPv4 或 IPv6 IP 位址進行相符，並視傳送至網路設定的 IP 資料包格式而定。</span><span class="sxs-lookup"><span data-stu-id="b8fae-176">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span>  <span data-ttu-id="b8fae-177"> (如果公用 IP 位址同時具有 IPv4 與 IPv6，您必須將兩者都新增為信任的 IP 位址。 ) </span><span class="sxs-lookup"><span data-stu-id="b8fae-177">(If a public IP address has both IPv4 and IPv6, you need to add both as trusted IP addresses.)</span></span>

- <span data-ttu-id="b8fae-178">網路區域包含一個網路網站集合。</span><span class="sxs-lookup"><span data-stu-id="b8fae-178">A network region contains a collection of network sites.</span></span> 

- <span data-ttu-id="b8fae-179">網路網站代表貴組織有實體價值（例如，辦公室、一組建築物或校園）的位置。</span><span class="sxs-lookup"><span data-stu-id="b8fae-179">A network site represents a location where your organization has a physical value, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="b8fae-180">這些網站是由 IP 子網的集合所定義。</span><span class="sxs-lookup"><span data-stu-id="b8fae-180">These sites are defined as a collection of IP subnets.</span></span>

- <span data-ttu-id="b8fae-181">網路子網必須與特定的網路網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="b8fae-181">A network subnet must be associated with a specific network site.</span></span> <span data-ttu-id="b8fae-182">用戶端的位置是根據網路子網和相關的網路網站來決定。</span><span class="sxs-lookup"><span data-stu-id="b8fae-182">A client's location is determined based on the network subnet and the associated network site.</span></span>  

<span data-ttu-id="b8fae-183">您可以在 Microsoft [團隊管理中心] 或 [使用 PowerShell] 中設定網路設定。</span><span class="sxs-lookup"><span data-stu-id="b8fae-183">You configure network settings in the Microsoft Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="b8fae-184">若要深入瞭解，請參閱 [管理雲端語音功能的網路拓撲](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="b8fae-184">To learn more, see [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span>

<span data-ttu-id="b8fae-185">請注意，這可能需要一些時間 (幾個小時的時間，) 針對網路設定所做的一些變更 (例如新的位址、網路識別碼) 等），以傳播並供團隊用戶端使用。</span><span class="sxs-lookup"><span data-stu-id="b8fae-185">Note that it can take some time (up to a couple of hours) for some changes to network settings (such as a new address, network identifier, and so on) to propagate and be available to Teams clients.</span></span>  

<span data-ttu-id="b8fae-186">**通話方案使用者：**</span><span class="sxs-lookup"><span data-stu-id="b8fae-186">**For Calling Plan users:**</span></span>

- <span data-ttu-id="b8fae-187">如果需要對 security 辦公桌通知進行動態設定，您必須設定信任的 IP 位址和網路網站。</span><span class="sxs-lookup"><span data-stu-id="b8fae-187">If dynamic configuration of security desk notification is required, you must configure both trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="b8fae-188">如果只需要動態位置，您必須只設定信任的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="b8fae-188">If only dynamic locations are required, you must configure only trusted IP addresses.</span></span>

- <span data-ttu-id="b8fae-189">如果兩者都不需要，則不需要設定網路設定。</span><span class="sxs-lookup"><span data-stu-id="b8fae-189">If neither are required, configuring network settings isn't required.</span></span> 

<span data-ttu-id="b8fae-190">**針對直接路由使用者：**</span><span class="sxs-lookup"><span data-stu-id="b8fae-190">**For Direct Routing users:**</span></span>

- <span data-ttu-id="b8fae-191">如果您需要動態啟用緊急通話或安全服務台通知的動態設定，則您必須設定信任的 IP 位址和網路網站。</span><span class="sxs-lookup"><span data-stu-id="b8fae-191">If dynamic enablement of emergency calling or dynamic configuration of security desk notification is required, then you must configure both Trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="b8fae-192">如果只需要動態位置，您必須只設定信任的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="b8fae-192">If only dynamic locations are required, you must configure only trusted IP addresses.</span></span>

- <span data-ttu-id="b8fae-193">如果兩者都不需要，則不需要設定網路設定。</span><span class="sxs-lookup"><span data-stu-id="b8fae-193">If neither are required, configuring network settings isn't required.</span></span>


## <a name="configure-location-information-service"></a><span data-ttu-id="b8fae-194">設定位置資訊服務</span><span class="sxs-lookup"><span data-stu-id="b8fae-194">Configure Location Information Service</span></span>

<span data-ttu-id="b8fae-195">團隊用戶端從與不同網路識別碼相關聯的位置取得緊急位址。</span><span class="sxs-lookup"><span data-stu-id="b8fae-195">A Teams client obtains emergency addresses from the locations associated with different network identifiers.</span></span> <span data-ttu-id="b8fae-196">子網和無線存取點都支援 (WAPs) 。</span><span class="sxs-lookup"><span data-stu-id="b8fae-196">Both subnets and wireless access points (WAPs) are supported.</span></span> <span data-ttu-id="b8fae-197">已擱置 (乙太網路交換器/埠的支援。 ) </span><span class="sxs-lookup"><span data-stu-id="b8fae-197">(Support for Ethernet switch/port is pending.)</span></span>

<span data-ttu-id="b8fae-198">若要讓用戶端取得位置，您必須使用網路識別碼來填入 IIS， (子網、WAPs、交換器、埠) 與緊急位置。</span><span class="sxs-lookup"><span data-stu-id="b8fae-198">For a client to obtain a location, you must populate the LIS with network identifiers (subnets, WAPs, switches, ports) and emergency locations.</span></span> <span data-ttu-id="b8fae-199">您可以在 Microsoft 團隊系統管理中心或使用 PowerShell 執行此動作。</span><span class="sxs-lookup"><span data-stu-id="b8fae-199">You can do this in the Microsoft Teams admin center or by using PowerShell.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b8fae-200">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="b8fae-200">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="b8fae-201">在左側導覽中，移至 [**地點**  >  **網路] & 位置**。</span><span class="sxs-lookup"><span data-stu-id="b8fae-201">In the left navigation, go to **Locations** > **Networks & locations**.</span></span>
2. <span data-ttu-id="b8fae-202">按一下代表您要新增之網路識別碼的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="b8fae-202">Click the tab that represents the network identifier that you want to add.</span></span> <span data-ttu-id="b8fae-203">例如，按一下 [ **子網**]、[ **wi-fi 存取點**]、[ **交換器**] 或 [ **埠**]。</span><span class="sxs-lookup"><span data-stu-id="b8fae-203">For example, click **Subnets**, **Wi-Fi access points**, **Switches**, or **Ports**.</span></span> <span data-ttu-id="b8fae-204">然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="b8fae-204">Then click **Add**.</span></span>
3. <span data-ttu-id="b8fae-205">完成欄位、新增緊急位置， **然後按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="b8fae-205">Complete the fields, add an emergency location, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b8fae-206">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8fae-206">Using PowerShell</span></span>

<span data-ttu-id="b8fae-207">使用下列 Cmdlet，將埠、開關、子網及 WAPs 新增至 IIS。</span><span class="sxs-lookup"><span data-stu-id="b8fae-207">Use the following cmdlets to add ports, switches, subnets, and WAPs to the LIS.</span></span>

- <span data-ttu-id="b8fae-208">[取得](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps)、 [設定](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps)、 [移除](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet</span><span class="sxs-lookup"><span data-stu-id="b8fae-208">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet</span></span>
- <span data-ttu-id="b8fae-209">[取得](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps)、 [設定](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps)、 [移除](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort</span><span class="sxs-lookup"><span data-stu-id="b8fae-209">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort</span></span>
- <span data-ttu-id="b8fae-210">[取得](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps)、 [設定](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps)、 [移除](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="b8fae-210">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint</span></span>
- <span data-ttu-id="b8fae-211">[取得](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps)、 [設定](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps)、 [移除](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch</span><span class="sxs-lookup"><span data-stu-id="b8fae-211">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch</span></span>

>[!Important]
><span data-ttu-id="b8fae-212">如果子網是作為網路網站的一部分使用，則必須在位置資訊服務中重新定義，才能呈現動態位置。</span><span class="sxs-lookup"><span data-stu-id="b8fae-212">If subnets are being used as part of network sites, they must be redefined in the Location Information Service to render dynamic locations.</span></span>

## <a name="configure-emergency-policies"></a><span data-ttu-id="b8fae-213">設定緊急原則</span><span class="sxs-lookup"><span data-stu-id="b8fae-213">Configure emergency policies</span></span>

<span data-ttu-id="b8fae-214">使用下列原則設定緊急通話。</span><span class="sxs-lookup"><span data-stu-id="b8fae-214">Use the following policies to configure emergency calling.</span></span> <span data-ttu-id="b8fae-215">您可以在 Microsoft 團隊系統管理中心或使用 PowerShell 管理這些原則。</span><span class="sxs-lookup"><span data-stu-id="b8fae-215">You can manage these policies in the Microsoft Teams admin center or by using PowerShell.</span></span>

- <span data-ttu-id="b8fae-216">**緊急通話路由原則** –只適用于直接路由。</span><span class="sxs-lookup"><span data-stu-id="b8fae-216">**Emergency call routing policy** – Applies only to Direct Routing.</span></span> <span data-ttu-id="b8fae-217">此原則會根據需要設定緊急電話號碼、每個數位的遮罩，以及每個號碼的 PSTN 路由。</span><span class="sxs-lookup"><span data-stu-id="b8fae-217">This policy configures the emergency numbers, masks per number if desired, and the PSTN route per number.</span></span>  <span data-ttu-id="b8fae-218">您可以將此原則指派給使用者、網路網站，或同時指派給這兩者。</span><span class="sxs-lookup"><span data-stu-id="b8fae-218">You can assign this policy to users, to network sites, or to both.</span></span> <span data-ttu-id="b8fae-219"> (通話方案團隊用戶端會根據其 Microsoft 365 或 Office 365 使用位置，自動啟用緊急通話的緊急電話號碼。 ) 若要深入瞭解，請參閱 [管理直接路由的緊急通話路由原則](manage-emergency-call-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b8fae-219">(Calling Plans Teams clients are automatically enabled for emergency calling with the emergency numbers from the country based upon their Microsoft 365 or Office 365 usage location.)  To  learn more, see [Manage emergency call routing policies for Direct Routing](manage-emergency-call-routing-policies.md).</span></span>

- <span data-ttu-id="b8fae-220">**緊急通話原則** -適用于通話方案和直接路由。</span><span class="sxs-lookup"><span data-stu-id="b8fae-220">**Emergency calling policy** - Applies to Calling Plans and Direct Routing.</span></span> <span data-ttu-id="b8fae-221">此原則會在發出緊急通話時設定 security 辦公桌的通知體驗。</span><span class="sxs-lookup"><span data-stu-id="b8fae-221">This policy configures the security desk notification experience when an emergency call is made.</span></span> <span data-ttu-id="b8fae-222">您可以設定要通知的人員，以及通知的方式。</span><span class="sxs-lookup"><span data-stu-id="b8fae-222">You can set who to notify and how they are notified.</span></span> <span data-ttu-id="b8fae-223">例如，自動通知貴組織的安全服務台，並讓他們聆聽緊急通話。</span><span class="sxs-lookup"><span data-stu-id="b8fae-223">For example, to automatically notify your organization's security desk and have them listen in on emergency calls.</span></span>  <span data-ttu-id="b8fae-224">您可以將此原則指派給使用者或網路網站，或同時指派給這兩者。</span><span class="sxs-lookup"><span data-stu-id="b8fae-224">This policy can either be assigned to users or network sites or both.</span></span> <span data-ttu-id="b8fae-225">若要深入瞭解，請參閱 [管理團隊中的緊急通話原則](manage-emergency-calling-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b8fae-225">To learn more, see [Manage emergency calling policies in Teams](manage-emergency-calling-policies.md).</span></span>

## <a name="enable-users-and-sites"></a><span data-ttu-id="b8fae-226">啟用使用者和網站</span><span class="sxs-lookup"><span data-stu-id="b8fae-226">Enable users and sites</span></span>

<span data-ttu-id="b8fae-227">您可以將緊急通話路線原則與緊急通話原則指派給使用者和網站。</span><span class="sxs-lookup"><span data-stu-id="b8fae-227">You can assign emergency call routing policies and emergency calling policies to users and to sites.</span></span> <span data-ttu-id="b8fae-228">請記住，緊急呼叫路由策略只適用于直接路由。</span><span class="sxs-lookup"><span data-stu-id="b8fae-228">Keep in mind that emergency call routing policies apply to Direct Routing only.</span></span> <span data-ttu-id="b8fae-229"> (雖然您可以將此原則指派給通話方案使用者，但原則將沒有任何效果。 ) </span><span class="sxs-lookup"><span data-stu-id="b8fae-229">(Although it's possible to assign this policy to a Calling Plan user, the policy will have no effect.)</span></span>

<span data-ttu-id="b8fae-230">您可以在 Microsoft [團隊管理中心] 或 [使用 PowerShell] 中指派原則。</span><span class="sxs-lookup"><span data-stu-id="b8fae-230">You assign policies in the Microsoft Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="b8fae-231">若要深入瞭解，請參閱：</span><span class="sxs-lookup"><span data-stu-id="b8fae-231">To learn more, see:</span></span>

- [<span data-ttu-id="b8fae-232">管理直接路由的緊急通話路由策略</span><span class="sxs-lookup"><span data-stu-id="b8fae-232">Manage emergency call routing policies for Direct Routing</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="b8fae-233">管理團隊中的緊急通話原則</span><span class="sxs-lookup"><span data-stu-id="b8fae-233">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)

<span data-ttu-id="b8fae-234">以下是一些 PowerShell 範例。</span><span class="sxs-lookup"><span data-stu-id="b8fae-234">Here's some PowerShell examples.</span></span>

<span data-ttu-id="b8fae-235">若要針對安全服務台通知啟用特定的使用者，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="b8fae-235">To enable a specific user for security desk notification, use the following command:</span></span>

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

<span data-ttu-id="b8fae-236">若要將名為「Contoso 緊急通話原則1」的原則指派給 Site 1，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="b8fae-236">To assign a policy called "Contoso Emergency Calling Policy 1" to Site 1, use the following command:</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

<span data-ttu-id="b8fae-237">若要啟用緊急通話的特定直接路由使用者，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="b8fae-237">To enable a specific Direct Routing user for emergency calling, use the following command:</span></span>

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

<span data-ttu-id="b8fae-238">若要將名為「Contoso 紐約急救通話路由」的原則指派給 Site 1，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="b8fae-238">To assign a policy called "Contoso New York Emergency Call Routing" to Site 1, use the following command:</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

<span data-ttu-id="b8fae-239">如果您已將緊急通話原則指派給網路網站和使用者，而且如果該使用者是在該網路網站上，則指派給網路網站的原則會覆寫指派給使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="b8fae-239">If you assigned an emergency calling policy to a network site and to a user, and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="test-emergency-calling"></a><span data-ttu-id="b8fae-240">測試緊急通話</span><span class="sxs-lookup"><span data-stu-id="b8fae-240">Test emergency calling</span></span>

<span data-ttu-id="b8fae-241">某些緊急路由服務提供者在美國 (ERSPs) 提供緊急呼叫測試 bot。</span><span class="sxs-lookup"><span data-stu-id="b8fae-241">Some Emergency Routing Service Providers (ERSPs) in the United States offer an emergency calling test bot.</span></span>

- <span data-ttu-id="b8fae-242">**在美國撥打電話方案使用者** 可以使用預先定義的測試緊急號碼933來驗證緊急通話設定。</span><span class="sxs-lookup"><span data-stu-id="b8fae-242">**Calling Plan users in the United States** can use the predefined test emergency number 933 to validate their emergency calling configuration.</span></span> <span data-ttu-id="b8fae-243">這個號碼會傳送到 bot，然後回顯來電者的電話號碼 (呼叫線路識別碼) 、緊急位址或位置，以及是否要先將呼叫自動路由到 PSAP 或篩選。</span><span class="sxs-lookup"><span data-stu-id="b8fae-243">This number is routed to a bot, which then echoes back the caller phone number (calling line ID), emergency address or location, and whether the call would be automatically routed to the PSAP or screened first.</span></span>

- <span data-ttu-id="b8fae-244">**在美國直接傳送路由的客戶** 應該與其 ERSP，以進行測試服務。</span><span class="sxs-lookup"><span data-stu-id="b8fae-244">**Direct Routing customers in the United States** should coordinate with their ERSP for a test service.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="b8fae-245">相關主題</span><span class="sxs-lookup"><span data-stu-id="b8fae-245">Related topics</span></span>

- [<span data-ttu-id="b8fae-246">管理緊急通話</span><span class="sxs-lookup"><span data-stu-id="b8fae-246">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="b8fae-247">管理緊急電話原則</span><span class="sxs-lookup"><span data-stu-id="b8fae-247">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="b8fae-248">管理緊急呼叫路由策略 </span><span class="sxs-lookup"><span data-stu-id="b8fae-248">Manage emergency call routing policies </span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="b8fae-249">新增、變更或移除貴組織的緊急位置</span><span class="sxs-lookup"><span data-stu-id="b8fae-249">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="b8fae-250">指派或變更使用者的緊急位置</span><span class="sxs-lookup"><span data-stu-id="b8fae-250">Assign or change an emergency location for your user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="b8fae-251">雲端語音功能的網路設定</span><span class="sxs-lookup"><span data-stu-id="b8fae-251">Network settings for cloud voice features</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="b8fae-252">管理雲端語音功能的網路拓撲</span><span class="sxs-lookup"><span data-stu-id="b8fae-252">Manage your network topology for cloud voice features</span></span>](manage-your-network-topology.md)
