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
- m365initiative-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
description: 瞭解如何設定 Microsoft 通話方案電話系統直接路由動態緊急電話功能。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5454eff6e09e923a6db8de1ba8c9e9fe47c3f0f2
ms.sourcegitcommit: 5c68298474d1782e69bde8c0940be7150cb93f6e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096307"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a><span data-ttu-id="09eb2-103">規劃和設定動態緊急電話</span><span class="sxs-lookup"><span data-stu-id="09eb2-103">Plan and configure dynamic emergency calling</span></span> 

<span data-ttu-id="09eb2-104">Microsoft 通話方案與直接路由的動態緊急電話系統提供設定和路由緊急電話的能力，並依據用戶端的目前位置通知Teams人員。</span><span class="sxs-lookup"><span data-stu-id="09eb2-104">Dynamic emergency calling for Microsoft Calling Plans and Phone System Direct Routing provides the capability to configure and route emergency calls and notify security personnel based on the current location of the Teams client.</span></span>  

<span data-ttu-id="09eb2-105">根據租使用者系統管理員定義的網路拓撲，Teams用戶端會向位置資訊服務中心或 LIS (提供網路) 。</span><span class="sxs-lookup"><span data-stu-id="09eb2-105">Based on the network topology that the tenant administrator defines, the Teams client provides network connectivity information in a request to the Location Information Service (LIS).</span></span> <span data-ttu-id="09eb2-106">如果有相符專案，LIS 會將位置返回用戶端。</span><span class="sxs-lookup"><span data-stu-id="09eb2-106">If there's a match, the LIS returns a location to the client.</span></span> <span data-ttu-id="09eb2-107">此位置資料會傳回用戶端。</span><span class="sxs-lookup"><span data-stu-id="09eb2-107">This location data is transmitted back to the client.</span></span>  

<span data-ttu-id="09eb2-108">用戶端Teams緊急通話中包含位置資料。</span><span class="sxs-lookup"><span data-stu-id="09eb2-108">The Teams client includes location data as part of an emergency call.</span></span> <span data-ttu-id="09eb2-109">然後，緊急服務提供者會使用這些資料來判斷適當的公用安全應答點 (PSAP) ，然後將通話路由至該 PSAP，讓 PSAP 調度員取得來電者的位置。</span><span class="sxs-lookup"><span data-stu-id="09eb2-109">This data is then used by the emergency service provider to determine the appropriate Public Safety Answering Point (PSAP) and to route the call to that PSAP, which allows the PSAP dispatcher to obtain the caller's location.</span></span>  

<span data-ttu-id="09eb2-110">針對動態緊急電話，必須發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="09eb2-110">For dynamic emergency calling, the following must occur:</span></span>

1. <span data-ttu-id="09eb2-111">網路系統管理員會設定網路設定和 LIS，以建立網路/緊急位置地圖。</span><span class="sxs-lookup"><span data-stu-id="09eb2-111">The network administrator configures network settings and the LIS to create a network/emergency location map.</span></span>

   <span data-ttu-id="09eb2-112">針對直接路由，路由緊急電話需要其他組組，並可能還需要合作夥伴連接。</span><span class="sxs-lookup"><span data-stu-id="09eb2-112">For Direct Routing, additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="09eb2-113">系統管理員必須為緊急位置識別號碼 (ELIN) 應用程式設定與緊急路由服務 (ERS) 提供者 (美國) 或會話邊界控制器 (SBC) 的連接。</span><span class="sxs-lookup"><span data-stu-id="09eb2-113">The administrator must configure connection to an Emergency Routing Service (ERS) provider (United States) **OR** configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

2. <span data-ttu-id="09eb2-114">在啟動期間和之後定期，或網路連接變更時，Teams用戶端會傳送包含其網路連接資訊的位置要求至網路設定和 LIS。</span><span class="sxs-lookup"><span data-stu-id="09eb2-114">During startup and periodically afterwards, or when a network connection is changed, the Teams client sends a location request that contains its network connectivity information to the network settings and the LIS.</span></span>

   - <span data-ttu-id="09eb2-115">如果有網路設定網站相符 ，緊急電話Teams會從該網站回到用戶端。</span><span class="sxs-lookup"><span data-stu-id="09eb2-115">If there's a network settings site match – emergency calling policies are returned to the Teams client from that site.</span></span> <span data-ttu-id="09eb2-116"> (有關政策的資訊，請參閱設定 [緊急](#configure-emergency-policies)) 。</span><span class="sxs-lookup"><span data-stu-id="09eb2-116">(For more information about policies, see [Configure emergency policies](#configure-emergency-policies)).</span></span>

   - <span data-ttu-id="09eb2-117">如果有 LIS 相符專案，則從已連接用戶端Teams網路元素的緊急位置會Teams用戶端。</span><span class="sxs-lookup"><span data-stu-id="09eb2-117">If there's an LIS match – an emergency location from the network element the Teams client is connected to is returned to the Teams client.</span></span> <span data-ttu-id="09eb2-118">會以下列循序執行比對，並返回第一個相符的結果：</span><span class="sxs-lookup"><span data-stu-id="09eb2-118">The match is performed in the following order with the first matched result being returned:</span></span>
       - <span data-ttu-id="09eb2-119">Wap</span><span class="sxs-lookup"><span data-stu-id="09eb2-119">WAP</span></span>
       - <span data-ttu-id="09eb2-120">乙太網路交換器/埠</span><span class="sxs-lookup"><span data-stu-id="09eb2-120">Ethernet switch/port</span></span>
       - <span data-ttu-id="09eb2-121">乙太網路交換器</span><span class="sxs-lookup"><span data-stu-id="09eb2-121">Ethernet switch</span></span>
       - <span data-ttu-id="09eb2-122">子網路</span><span class="sxs-lookup"><span data-stu-id="09eb2-122">Subnet</span></span>

3. <span data-ttu-id="09eb2-123">當Teams用戶端撥打緊急電話時，緊急位置會傳送至 PSTN 網路。</span><span class="sxs-lookup"><span data-stu-id="09eb2-123">When the Teams client makes an emergency call, the emergency location is conveyed to the PSTN network.</span></span>

   <span data-ttu-id="09eb2-124">對於直接路由，系統管理員必須將 SBC 設定為傳送緊急電話給 ERS 提供者，或設定 SBC ELIN 應用程式。</span><span class="sxs-lookup"><span data-stu-id="09eb2-124">For Direct Routing, the administrator must configure the SBC to send emergency calls to the ERS provider or configure the SBC ELIN application.</span></span>

<span data-ttu-id="09eb2-125">本文包含下列各節。</span><span class="sxs-lookup"><span data-stu-id="09eb2-125">This article contains the following sections.</span></span>

- [<span data-ttu-id="09eb2-126">設定緊急位址</span><span class="sxs-lookup"><span data-stu-id="09eb2-126">Configure emergency addresses</span></span>](#assign-emergency-addresses)
- [<span data-ttu-id="09eb2-127">設定網路設定</span><span class="sxs-lookup"><span data-stu-id="09eb2-127">Configure network settings</span></span>](#configure-network-settings)
- [<span data-ttu-id="09eb2-128">設定位置資訊服務</span><span class="sxs-lookup"><span data-stu-id="09eb2-128">Configure Location Information Service</span></span>](#configure-location-information-service)
- [<span data-ttu-id="09eb2-129">設定緊急政策</span><span class="sxs-lookup"><span data-stu-id="09eb2-129">Configure emergency policies</span></span>](#configure-emergency-policies)
- [<span data-ttu-id="09eb2-130">啟用使用者和網站</span><span class="sxs-lookup"><span data-stu-id="09eb2-130">Enable users and sites</span></span>](#enable-users-and-sites)
- [<span data-ttu-id="09eb2-131">測試緊急通話</span><span class="sxs-lookup"><span data-stu-id="09eb2-131">Test emergency calling</span></span>](#test-emergency-calling)

<span data-ttu-id="09eb2-132">自動路由至適當的安全性應答點 (PSAP) 的能力會視使用者使用Teams國而異。</span><span class="sxs-lookup"><span data-stu-id="09eb2-132">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) varies depending on the country of usage of the Teams user.</span></span>

<span data-ttu-id="09eb2-133">若要進一步瞭解緊急電話，包括緊急位址和緊急電話路由的資訊、國家/地區特有的資訊，以及網路設定和網路拓撲的資訊，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="09eb2-133">For more information about emergency calling, including information about emergency addresses and emergency call routing, information specific to countries, and information about network settings and network topology, see the following:</span></span>

- [<span data-ttu-id="09eb2-134">管理緊急電話</span><span class="sxs-lookup"><span data-stu-id="09eb2-134">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="09eb2-135">管理雲端語音功能的網路設定</span><span class="sxs-lookup"><span data-stu-id="09eb2-135">Manage network settings for cloud voice features</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="09eb2-136">管理雲端語音功能的網路拓撲</span><span class="sxs-lookup"><span data-stu-id="09eb2-136">Manage your network topology for cloud voice features</span></span>](manage-your-network-topology.md)

<span data-ttu-id="09eb2-137">有關哪些功能可在政府雲端使用，請參閱本文結尾的政府支援[](#government-support)。</span><span class="sxs-lookup"><span data-stu-id="09eb2-137">For more information about which features are available in the government clouds, see [Government support](#government-support) at the end of this article.</span></span>


## <a name="supported-clients"></a><span data-ttu-id="09eb2-138">支援的用戶端</span><span class="sxs-lookup"><span data-stu-id="09eb2-138">Supported clients</span></span>

<span data-ttu-id="09eb2-139">目前支援下列用戶端。</span><span class="sxs-lookup"><span data-stu-id="09eb2-139">The following clients are currently supported.</span></span>  <span data-ttu-id="09eb2-140">經常回來查看此清單的更新。</span><span class="sxs-lookup"><span data-stu-id="09eb2-140">Check back often to see updates to this list.</span></span>

- <span data-ttu-id="09eb2-141">Teams Microsoft 電腦版桌面Windows</span><span class="sxs-lookup"><span data-stu-id="09eb2-141">Teams desktop client for Microsoft Windows</span></span>
- <span data-ttu-id="09eb2-142">Teams MacOS 版桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="09eb2-142">Teams desktop client for Apple macOS</span></span>
- <span data-ttu-id="09eb2-143">Teams適用于 Apple iOS 用戶端版本 1.0.92.2019121004 和 App Store 版本 1.0.92 及更新版本的行動用戶端</span><span class="sxs-lookup"><span data-stu-id="09eb2-143">Teams mobile client for Apple iOS client version 1.0.92.2019121004 and App Store version 1.0.92 and greater</span></span>
- <span data-ttu-id="09eb2-144">Teams Android 用戶端和 Google Play 商店版本 1416/1.0.0.2019121201 及更新版本的行動用戶端</span><span class="sxs-lookup"><span data-stu-id="09eb2-144">Teams mobile client for Android client and Google Play store version 1416/1.0.0.2019121201 and greater</span></span>
- <span data-ttu-id="09eb2-145">Teams 1449/1.0.94.2019110802 及更新版本</span><span class="sxs-lookup"><span data-stu-id="09eb2-145">Teams phone version 1449/1.0.94.2019110802 and greater</span></span>
- <span data-ttu-id="09eb2-146">Teams 會議室版本 4.4.25.0 及更新版本</span><span class="sxs-lookup"><span data-stu-id="09eb2-146">Teams Rooms version 4.4.25.0 and greater</span></span>

> [!NOTE]
> <span data-ttu-id="09eb2-147">Web 用戶端不支援動態緊急電話，包括安全Teams通知。</span><span class="sxs-lookup"><span data-stu-id="09eb2-147">Dynamic emergency calling, including security desk notification, isn't supported on the Teams web client.</span></span> <span data-ttu-id="09eb2-148">若要防止使用者使用網路用戶端Teams PSTN 號碼，您可以設定Teams，並關閉 [允許 **Web PSTN** 通話設定。</span><span class="sxs-lookup"><span data-stu-id="09eb2-148">To prevent users from using the Teams web client to call PSTN numbers, you can set a Teams calling policy and turn off the **Allow web PSTN calling** setting.</span></span> <span data-ttu-id="09eb2-149">若要深入瞭解，請參閱在[](teams-calling-policy.md)Teams[和 Set-CsTeamsCallingPolicy 中的通話政策](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="09eb2-149">To learn more, see [Calling policies in Teams](teams-calling-policy.md) and [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> 

> [!NOTE]
> <span data-ttu-id="09eb2-150">所有用戶端都支援子網和 WiFi Teams位置。</span><span class="sxs-lookup"><span data-stu-id="09eb2-150">Subnet and WiFi-based locations are supported on all Teams clients.</span></span> <br>
> <span data-ttu-id="09eb2-151">乙太網路/ (LLDP) 僅支援 Windows 且目前僅支援 Windows 8.1 及更新版本。</span><span class="sxs-lookup"><span data-stu-id="09eb2-151">Ethernet/Switch (LLDP) is only supported on Windows and only on Windows versions 8.1 and later at this time.</span></span>

## <a name="assign-emergency-addresses"></a><span data-ttu-id="09eb2-152">指派緊急位址</span><span class="sxs-lookup"><span data-stu-id="09eb2-152">Assign emergency addresses</span></span>

<span data-ttu-id="09eb2-153">您可以將緊急位址指派給通話方案使用者，以及動態取得位置所需的網路識別碼。</span><span class="sxs-lookup"><span data-stu-id="09eb2-153">You can assign emergency addresses to both Calling Plan users and to the network identifiers that are required for dynamically obtaining a location.</span></span> <span data-ttu-id="09eb2-154"> (子網和 WiFi AP 支援。</span><span class="sxs-lookup"><span data-stu-id="09eb2-154">(Subnet and WiFi AP are supported.</span></span> <span data-ttu-id="09eb2-155">目前支援乙太網路Windows 8.1/埠) 。</span><span class="sxs-lookup"><span data-stu-id="09eb2-155">Ethernet switch/port is supported on Windows 8.1 and later at this time).</span></span>

<span data-ttu-id="09eb2-156">若要支援美國境內緊急電話的自動路由，您必須確保指派給網路識別碼的緊急位置包含相關聯的地理代碼。</span><span class="sxs-lookup"><span data-stu-id="09eb2-156">To support automated routing of emergency calls within the United States, you must ensure that the emergency locations that are assigned to network identifiers include the associated geo codes.</span></span> <span data-ttu-id="09eb2-157"> (沒有地理代碼的緊急位址無法指派給動態位置所需的網路識別碼。) </span><span class="sxs-lookup"><span data-stu-id="09eb2-157">(Emergency addresses without geo codes can't be assigned to the network identifiers that are required for dynamic locations.)</span></span>

<span data-ttu-id="09eb2-158">Azure 地圖用於位置型服務。</span><span class="sxs-lookup"><span data-stu-id="09eb2-158">Azure Maps is used for location-based services.</span></span>  <span data-ttu-id="09eb2-159">當您使用系統管理中心輸入緊急位址Microsoft Teams，Teams檢查 Azure 地圖位址：</span><span class="sxs-lookup"><span data-stu-id="09eb2-159">When you enter an emergency address by using the Microsoft Teams admin center, Teams checks Azure Maps for the address:</span></span>

- <span data-ttu-id="09eb2-160">如果找到相符專案，系統會自動包含地理代碼。</span><span class="sxs-lookup"><span data-stu-id="09eb2-160">If a match is found, the geo codes are automatically included.</span></span>

- <span data-ttu-id="09eb2-161">如果找不到相符專案，您將有機會手動建立緊急位址。</span><span class="sxs-lookup"><span data-stu-id="09eb2-161">If a match isn't found, you will have the opportunity to manually create an emergency address.</span></span> <span data-ttu-id="09eb2-162">您可以使用 PIN 拖放功能執行此工作。</span><span class="sxs-lookup"><span data-stu-id="09eb2-162">You can use the PIN drop feature to do this.</span></span> 

<span data-ttu-id="09eb2-163">這表示，如果為指派給通話方案使用者而建立的現有緊急位置是針對動態位置所建立，必須重新建立相同的位址，以包含地理代碼。</span><span class="sxs-lookup"><span data-stu-id="09eb2-163">This means that if an existing emergency location that is created for assigning to Calling Plan users is intended for a dynamic location, the same address needs to be re-created to include the geo codes.</span></span> <span data-ttu-id="09eb2-164">若要區別這兩個位置，您應該包含不同的描述。</span><span class="sxs-lookup"><span data-stu-id="09eb2-164">To distinguish between the two locations, you should include a different description.</span></span> <span data-ttu-id="09eb2-165">新的緊急位置可以指派給擁有舊位置的使用者。</span><span class="sxs-lookup"><span data-stu-id="09eb2-165">The new emergency location can be assigned to the users who have the old location.</span></span> <span data-ttu-id="09eb2-166">完全移移後，可以刪除舊位置。</span><span class="sxs-lookup"><span data-stu-id="09eb2-166">When fully migrated, the old location can be deleted.</span></span>

<span data-ttu-id="09eb2-167">您可以在系統管理中心Microsoft Teams或使用 PowerShell 來新增和指派緊急位址。</span><span class="sxs-lookup"><span data-stu-id="09eb2-167">You add and assign emergency addresses in the Microsoft Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="09eb2-168">若要詳細資訊，請參閱 [為貴組織](add-change-remove-emergency-location-organization.md) 新增緊急位置，以及指派 [使用者的緊急位置](assign-change-emergency-location-user.md)。</span><span class="sxs-lookup"><span data-stu-id="09eb2-168">For more information, see [Add an emergency location for your organization](add-change-remove-emergency-location-organization.md) and [Assign an emergency location for a user](assign-change-emergency-location-user.md).</span></span>

## <a name="configure-network-settings"></a><span data-ttu-id="09eb2-169">設定網路設定</span><span class="sxs-lookup"><span data-stu-id="09eb2-169">Configure network settings</span></span>

<span data-ttu-id="09eb2-170">網路設定可用來判斷用戶端Teams，以及動態取得緊急通話策略和緊急位置。</span><span class="sxs-lookup"><span data-stu-id="09eb2-170">Network settings are used to determine the location of a Teams client, and to dynamically obtain emergency calling policies and an emergency location.</span></span> <span data-ttu-id="09eb2-171">您可以根據貴組織希望緊急電話運作方式來設定網路設定。</span><span class="sxs-lookup"><span data-stu-id="09eb2-171">You can configure network settings according to how your organization wants emergency calling to function.</span></span>

<span data-ttu-id="09eb2-172">網路設定包括包含子網集合的網站，這些網站僅用於動態策略指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="09eb2-172">Network settings include sites that include a collection of subnets and these are used exclusively for dynamic policy assignment to users.</span></span> <span data-ttu-id="09eb2-173">例如，緊急通話策略和緊急電話路由策略可能會指派給「Redmond 網站」，讓任何從家用或另一個 Microsoft 位置漫遊的使用者，都使用 Redmond 特有的緊急號碼、路由和安全性電話機進行配置。</span><span class="sxs-lookup"><span data-stu-id="09eb2-173">For example, an emergency calling policy and an emergency call routing policy might be assigned to the "Redmond site" so that any user that roams from home or another Microsoft location is configured with emergency numbers, routing, and security desk specific to Redmond.</span></span>  

> [!Note]
> <span data-ttu-id="09eb2-174">子網也可以定義在 LIS 中，而且可以與緊急位置相關聯。</span><span class="sxs-lookup"><span data-stu-id="09eb2-174">Subnets can also be defined in LIS and can be associated with an emergency location.</span></span>  <span data-ttu-id="09eb2-175">LIS 子網必須由符合指派給用戶端之子網 IP 範圍的網路識別碼定義。</span><span class="sxs-lookup"><span data-stu-id="09eb2-175">LIS subnets must be defined by the Network ID matching the subnet IP range assigned to clients.</span></span> <span data-ttu-id="09eb2-176">例如，用戶端 IP/遮罩 10.10.10.150/25 的網路識別碼是 **10.10.10.128**。</span><span class="sxs-lookup"><span data-stu-id="09eb2-176">For example, the network ID for a client IP/mask of 10.10.10.150/25 is **10.10.10.128**.</span></span> <span data-ttu-id="09eb2-177">詳細資訊請參閱瞭解 [TCP/IP 位址和子網劃分基本功能](/troubleshoot/windows-client/networking/tcpip-addressing-and-subnetting)。</span><span class="sxs-lookup"><span data-stu-id="09eb2-177">For more information, see [Understand TCP/IP addressing and subnetting basics](/troubleshoot/windows-client/networking/tcpip-addressing-and-subnetting).</span></span>

> [!Important]
> <span data-ttu-id="09eb2-178">雲端 Proxy 服務部署不支援網路設定設定檢查，這些部署會修改來自Teams IP 位址。</span><span class="sxs-lookup"><span data-stu-id="09eb2-178">Network configuration setting lookups are not supported with cloud proxy service deployments that modify the source IP addresses from Teams clients.</span></span>

<span data-ttu-id="09eb2-179">請記住下列定義。</span><span class="sxs-lookup"><span data-stu-id="09eb2-179">Keep the following definitions in mind.</span></span> <span data-ttu-id="09eb2-180">詳細資訊，請參閱 [雲端語音功能的網路設定](cloud-voice-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="09eb2-180">For more information, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

- <span data-ttu-id="09eb2-181">信任的 IP 位址包含商業網路的網際網路外部 IP 位址集合，並用來判斷使用者的端點是否位於公司網路內。</span><span class="sxs-lookup"><span data-stu-id="09eb2-181">Trusted IP addresses contain a collection of the internet external IP addresses of the enterprise network and are used to determine if the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="09eb2-182">只有在使用者的外部 IP 位址符合信任的 IP 位址中的 IP 位址時，才能嘗試取得動態策略或位置。</span><span class="sxs-lookup"><span data-stu-id="09eb2-182">An attempt to obtain a dynamic policy or location will only be made if the user's external IP address matches an IP address in the trusted IP address.</span></span> <span data-ttu-id="09eb2-183">您可以根據 IPv4 或 IPv6 IP 位址進行比對，並視要送往網路設定之 IP 封包的格式而定。</span><span class="sxs-lookup"><span data-stu-id="09eb2-183">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span>  <span data-ttu-id="09eb2-184"> (如果公用 IP 位址同時有 IPv4 和 IPv6，您必須同時將兩者新增為信任的 IP 位址。) </span><span class="sxs-lookup"><span data-stu-id="09eb2-184">(If a public IP address has both IPv4 and IPv6, you need to add both as trusted IP addresses.)</span></span>

- <span data-ttu-id="09eb2-185">網路區域包含網路網站的集合。</span><span class="sxs-lookup"><span data-stu-id="09eb2-185">A network region contains a collection of network sites.</span></span> 

- <span data-ttu-id="09eb2-186">網路網站代表貴組織具有實體值的位置，例如辦公室、一組建築物或校園。</span><span class="sxs-lookup"><span data-stu-id="09eb2-186">A network site represents a location where your organization has a physical value, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="09eb2-187">這些網站定義為 IP 子網的集合。</span><span class="sxs-lookup"><span data-stu-id="09eb2-187">These sites are defined as a collection of IP subnets.</span></span>

- <span data-ttu-id="09eb2-188">網路子網必須與特定網路網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="09eb2-188">A network subnet must be associated with a specific network site.</span></span> <span data-ttu-id="09eb2-189">用戶端的位置是根據網路子網和相關網路網站所決定。</span><span class="sxs-lookup"><span data-stu-id="09eb2-189">A client's location is determined based on the network subnet and the associated network site.</span></span>  

<span data-ttu-id="09eb2-190">您可以在系統管理中心Microsoft Teams或使用 PowerShell 來設定網路設定。</span><span class="sxs-lookup"><span data-stu-id="09eb2-190">You configure network settings in the Microsoft Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="09eb2-191">若要深入瞭解，請參閱 [管理雲端語音功能的網路拓撲](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="09eb2-191">To learn more, see [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span>

<span data-ttu-id="09eb2-192">請注意，網路設定 (可能需要一些時間) 才能進行一些網路設定變更 (例如新位址、網路識別碼等) 來傳播，並且可供 Teams 用戶端使用。</span><span class="sxs-lookup"><span data-stu-id="09eb2-192">Note that it can take some time (up to a couple of hours) for some changes to network settings (such as a new address, network identifier, and so on) to propagate and be available to Teams clients.</span></span>  

<span data-ttu-id="09eb2-193">**針對通話方案使用者：**</span><span class="sxs-lookup"><span data-stu-id="09eb2-193">**For Calling Plan users:**</span></span>

- <span data-ttu-id="09eb2-194">如果需要動態設定安全電話台通知，您必須同時設定信任的 IP 位址和網路網站。</span><span class="sxs-lookup"><span data-stu-id="09eb2-194">If dynamic configuration of security desk notification is required, you must configure both trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="09eb2-195">如果只需要動態位置，則必須只設定信任的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="09eb2-195">If only dynamic locations are required, you must configure only trusted IP addresses.</span></span>

- <span data-ttu-id="09eb2-196">如果兩者都不需要，則不需要設定網路設定。</span><span class="sxs-lookup"><span data-stu-id="09eb2-196">If neither are required, configuring network settings isn't required.</span></span> 

<span data-ttu-id="09eb2-197">**針對直接路由使用者：**</span><span class="sxs-lookup"><span data-stu-id="09eb2-197">**For Direct Routing users:**</span></span>

- <span data-ttu-id="09eb2-198">如果需要動態啟用緊急電話或安全性電話台通知的動態設定，則必須同時設定信任的 IP 位址和網路網站。</span><span class="sxs-lookup"><span data-stu-id="09eb2-198">If dynamic enablement of emergency calling or dynamic configuration of security desk notification is required, then you must configure both Trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="09eb2-199">如果只需要動態位置，則必須只設定信任的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="09eb2-199">If only dynamic locations are required, you must configure only trusted IP addresses.</span></span>

- <span data-ttu-id="09eb2-200">如果兩者都不需要，則不需要設定網路設定。</span><span class="sxs-lookup"><span data-stu-id="09eb2-200">If neither are required, configuring network settings isn't required.</span></span>


## <a name="configure-location-information-service"></a><span data-ttu-id="09eb2-201">設定位置資訊服務</span><span class="sxs-lookup"><span data-stu-id="09eb2-201">Configure Location Information Service</span></span>

<span data-ttu-id="09eb2-202">用戶端Teams會從與不同網路識別碼相關聯的位置取得緊急位址。</span><span class="sxs-lookup"><span data-stu-id="09eb2-202">A Teams client obtains emergency addresses from the locations associated with different network identifiers.</span></span> <span data-ttu-id="09eb2-203">支援子網和無線存取點 (WAP) 。</span><span class="sxs-lookup"><span data-stu-id="09eb2-203">Both subnets and wireless access points (WAPs) are supported.</span></span> <span data-ttu-id="09eb2-204">目前支援乙太網路Windows 8.1/埠。</span><span class="sxs-lookup"><span data-stu-id="09eb2-204">Ethernet switch/port is supported on Windows 8.1 and later at this time.</span></span>

<span data-ttu-id="09eb2-205">若要讓用戶端取得位置，您必須在 LIS 中填入網路識別碼 (子網、WAP、切換器、埠和) 位置。</span><span class="sxs-lookup"><span data-stu-id="09eb2-205">For a client to obtain a location, you must populate the LIS with network identifiers (subnets, WAPs, switches, ports) and emergency locations.</span></span> <span data-ttu-id="09eb2-206">您可以在系統管理中心Microsoft Teams PowerShell 執行此工作。</span><span class="sxs-lookup"><span data-stu-id="09eb2-206">You can do this in the Microsoft Teams admin center or by using PowerShell.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="09eb2-207">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="09eb2-207">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="09eb2-208">在左側流覽中，前往位置  >  **網路&位置**。</span><span class="sxs-lookup"><span data-stu-id="09eb2-208">In the left navigation, go to **Locations** > **Networks & locations**.</span></span>
2. <span data-ttu-id="09eb2-209">按一下代表要新增之網路識別碼的 Tab。</span><span class="sxs-lookup"><span data-stu-id="09eb2-209">Click the tab that represents the network identifier that you want to add.</span></span> <span data-ttu-id="09eb2-210">例如，按一下 **[子網\*\*\*\*、Wi-Fi 存取點、\*\*\*\*開關** 或 **埠。**</span><span class="sxs-lookup"><span data-stu-id="09eb2-210">For example, click **Subnets**, **Wi-Fi access points**, **Switches**, or **Ports**.</span></span> <span data-ttu-id="09eb2-211">然後按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="09eb2-211">Then click **Add**.</span></span>
3. <span data-ttu-id="09eb2-212">完成欄位，新增緊急位置，然後按一下 [ **套用**。</span><span class="sxs-lookup"><span data-stu-id="09eb2-212">Complete the fields, add an emergency location, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="09eb2-213">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="09eb2-213">Using PowerShell</span></span>

<span data-ttu-id="09eb2-214">使用下列 Cmdlet 在 LIS 中新增埠、切換、子網和 WAP。</span><span class="sxs-lookup"><span data-stu-id="09eb2-214">Use the following cmdlets to add ports, switches, subnets, and WAPs to the LIS.</span></span>

- <span data-ttu-id="09eb2-215">[取得](/powershell/module/skype/get-csonlinelissubnet?view=skype-ps)、 [設定](/powershell/module/skype/set-csonlinelissubnet?view=skype-ps)、 [移除](/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet</span><span class="sxs-lookup"><span data-stu-id="09eb2-215">[Get](/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet</span></span>
- <span data-ttu-id="09eb2-216">[取得](/powershell/module/skype/get-csonlinelisport?view=skype-ps)、 [設定](/powershell/module/skype/set-csonlinelisport?view=skype-ps)、 [移除](/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort</span><span class="sxs-lookup"><span data-stu-id="09eb2-216">[Get](/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort</span></span>
- <span data-ttu-id="09eb2-217">[取得](/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps)、 [設定](/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps)、 [移除](/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="09eb2-217">[Get](/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Set](/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint</span></span>
- <span data-ttu-id="09eb2-218">[取得](/powershell/module/skype/get-csonlinelisswitch?view=skype-ps)、 [設定](/powershell/module/skype/set-csonlinelisswitch?view=skype-ps)、 [移除](/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch</span><span class="sxs-lookup"><span data-stu-id="09eb2-218">[Get](/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch</span></span>

>[!Important]
><span data-ttu-id="09eb2-219">如果子網是作為網路網站的一部分使用，則必須在位置資訊服務中重新定義子網，以呈現動態位置。</span><span class="sxs-lookup"><span data-stu-id="09eb2-219">If subnets are being used as part of network sites, they must be redefined in the Location Information Service to render dynamic locations.</span></span>

## <a name="configure-emergency-policies"></a><span data-ttu-id="09eb2-220">設定緊急政策</span><span class="sxs-lookup"><span data-stu-id="09eb2-220">Configure emergency policies</span></span>

<span data-ttu-id="09eb2-221">使用下列策略來設定緊急電話。</span><span class="sxs-lookup"><span data-stu-id="09eb2-221">Use the following policies to configure emergency calling.</span></span> <span data-ttu-id="09eb2-222">您可以在系統管理中心Microsoft Teams使用 PowerShell 來管理這些策略。</span><span class="sxs-lookup"><span data-stu-id="09eb2-222">You can manage these policies in the Microsoft Teams admin center or by using PowerShell.</span></span>

- <span data-ttu-id="09eb2-223">**緊急電話路由原則** - 僅適用于直接路由。</span><span class="sxs-lookup"><span data-stu-id="09eb2-223">**Emergency call routing policy** – Applies only to Direct Routing.</span></span> <span data-ttu-id="09eb2-224">此策略會設定緊急號碼、每個號碼的遮罩 ，以及每個號碼的 PSTN 路由。</span><span class="sxs-lookup"><span data-stu-id="09eb2-224">This policy configures the emergency numbers, masks per number if desired, and the PSTN route per number.</span></span>  <span data-ttu-id="09eb2-225">您可以將此策略指派給使用者、網路網站或兩者。</span><span class="sxs-lookup"><span data-stu-id="09eb2-225">You can assign this policy to users, to network sites, or to both.</span></span> <span data-ttu-id="09eb2-226"> (通話方案 Teams 用戶端會根據國家/地區 Microsoft 365 或 Office 365 使用位置自動啟用緊急電話。) 若要深入瞭解，請參閱管理直接路由的緊急電話路由[策略。](manage-emergency-call-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="09eb2-226">(Calling Plans Teams clients are automatically enabled for emergency calling with the emergency numbers from the country based upon their Microsoft 365 or Office 365 usage location.)  To  learn more, see [Manage emergency call routing policies for Direct Routing](manage-emergency-call-routing-policies.md).</span></span>

- <span data-ttu-id="09eb2-227">**緊急通話原則** - 適用于通話方案及直接路由。</span><span class="sxs-lookup"><span data-stu-id="09eb2-227">**Emergency calling policy** - Applies to Calling Plans and Direct Routing.</span></span> <span data-ttu-id="09eb2-228">此策略會設定撥打緊急電話時的安全性電話台通知體驗。</span><span class="sxs-lookup"><span data-stu-id="09eb2-228">This policy configures the security desk notification experience when an emergency call is made.</span></span> <span data-ttu-id="09eb2-229">您可以設定要通知哪些人，以及如何通知他們。</span><span class="sxs-lookup"><span data-stu-id="09eb2-229">You can set who to notify and how they are notified.</span></span> <span data-ttu-id="09eb2-230">例如，若要自動通知貴組織的安全電話台，讓他們接聽緊急電話。</span><span class="sxs-lookup"><span data-stu-id="09eb2-230">For example, to automatically notify your organization's security desk and have them listen in on emergency calls.</span></span>  <span data-ttu-id="09eb2-231">此策略可以指派給使用者或網路網站，也可以同時指派給使用者或網路網站。</span><span class="sxs-lookup"><span data-stu-id="09eb2-231">This policy can either be assigned to users or network sites or both.</span></span> <span data-ttu-id="09eb2-232">若要深入瞭解，請參閱在 Teams 中[管理緊急Teams。](manage-emergency-calling-policies.md)</span><span class="sxs-lookup"><span data-stu-id="09eb2-232">To learn more, see [Manage emergency calling policies in Teams](manage-emergency-calling-policies.md).</span></span>

## <a name="enable-users-and-sites"></a><span data-ttu-id="09eb2-233">啟用使用者和網站</span><span class="sxs-lookup"><span data-stu-id="09eb2-233">Enable users and sites</span></span>

<span data-ttu-id="09eb2-234">您可以將緊急通話路由策略和緊急通話策略指派給使用者和網站。</span><span class="sxs-lookup"><span data-stu-id="09eb2-234">You can assign emergency call routing policies and emergency calling policies to users and to sites.</span></span> <span data-ttu-id="09eb2-235">請記住，緊急通話路由原則僅適用于直接路由。</span><span class="sxs-lookup"><span data-stu-id="09eb2-235">Keep in mind that emergency call routing policies apply to Direct Routing only.</span></span> <span data-ttu-id="09eb2-236"> (雖然可以將此策略指派給通話方案使用者，但該政策將沒有任何作用。) </span><span class="sxs-lookup"><span data-stu-id="09eb2-236">(Although it's possible to assign this policy to a Calling Plan user, the policy will have no effect.)</span></span>

<span data-ttu-id="09eb2-237">您可以在系統管理中心Microsoft Teams使用 PowerShell 指派策略。</span><span class="sxs-lookup"><span data-stu-id="09eb2-237">You assign policies in the Microsoft Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="09eb2-238">若要深入了解，請參閱：</span><span class="sxs-lookup"><span data-stu-id="09eb2-238">To learn more, see:</span></span>

- [<span data-ttu-id="09eb2-239">管理直接路由的緊急通話路由策略</span><span class="sxs-lookup"><span data-stu-id="09eb2-239">Manage emergency call routing policies for Direct Routing</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="09eb2-240">在 Teams</span><span class="sxs-lookup"><span data-stu-id="09eb2-240">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)

<span data-ttu-id="09eb2-241">以下是一些 PowerShell 範例。</span><span class="sxs-lookup"><span data-stu-id="09eb2-241">Here's some PowerShell examples.</span></span>

<span data-ttu-id="09eb2-242">若要啟用特定使用者的安全性桌面通知，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="09eb2-242">To enable a specific user for security desk notification, use the following command:</span></span>

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

<span data-ttu-id="09eb2-243">若要將名為「Contoso 緊急電話政策 1」的政策指派給網站 1，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="09eb2-243">To assign a policy called "Contoso Emergency Calling Policy 1" to Site 1, use the following command:</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

<span data-ttu-id="09eb2-244">若要啟用特定直接路由使用者進行緊急通話，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="09eb2-244">To enable a specific Direct Routing user for emergency calling, use the following command:</span></span>

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

<span data-ttu-id="09eb2-245">若要將名為「Contoso New York 緊急電話路由」的政策指派給網站 1，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="09eb2-245">To assign a policy called "Contoso New York Emergency Call Routing" to Site 1, use the following command:</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

<span data-ttu-id="09eb2-246">如果您將緊急通話策略指派給網路網站和使用者，且該使用者位於該網路網站，則指派給網路網站的策略會取代指派給使用者的策略。</span><span class="sxs-lookup"><span data-stu-id="09eb2-246">If you assigned an emergency calling policy to a network site and to a user, and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="test-emergency-calling"></a><span data-ttu-id="09eb2-247">測試緊急通話</span><span class="sxs-lookup"><span data-stu-id="09eb2-247">Test emergency calling</span></span>

<span data-ttu-id="09eb2-248">美國部分緊急路由服務提供者 (ERSP) 提供緊急通話測試 Bot。</span><span class="sxs-lookup"><span data-stu-id="09eb2-248">Some Emergency Routing Service Providers (ERSPs) in the United States offer an emergency calling test bot.</span></span>

- <span data-ttu-id="09eb2-249">**美國的通話方案使用者可以** 使用預先定義的測試緊急號碼 933 來驗證其緊急通話設定。</span><span class="sxs-lookup"><span data-stu-id="09eb2-249">**Calling Plan users in the United States** can use the predefined test emergency number 933 to validate their emergency calling configuration.</span></span> <span data-ttu-id="09eb2-250">此號碼會路由至 Bot，然後回顯來電者的電話號碼 (電話線識別碼) 、緊急位址或位置，以及通話是否會自動路由至 PSAP 或先進行篩選。</span><span class="sxs-lookup"><span data-stu-id="09eb2-250">This number is routed to a bot, which then echoes back the caller phone number (calling line ID), emergency address or location, and whether the call would be automatically routed to the PSAP or screened first.</span></span>

- <span data-ttu-id="09eb2-251">**美國的直接路由客戶應該** 與他們的 ERSP 協調，以進行測試服務。</span><span class="sxs-lookup"><span data-stu-id="09eb2-251">**Direct Routing customers in the United States** should coordinate with their ERSP for a test service.</span></span>

## <a name="government-support"></a><span data-ttu-id="09eb2-252">政府支援</span><span class="sxs-lookup"><span data-stu-id="09eb2-252">Government support</span></span>

<span data-ttu-id="09eb2-253">下表顯示政府雲端動態緊急電話的支援：</span><span class="sxs-lookup"><span data-stu-id="09eb2-253">The following table shows support for dynamic emergency calling in the government clouds:</span></span>

| <span data-ttu-id="09eb2-254">雲</span><span class="sxs-lookup"><span data-stu-id="09eb2-254">Cloud</span></span> | <span data-ttu-id="09eb2-255">可用 性</span><span class="sxs-lookup"><span data-stu-id="09eb2-255">Availability</span></span> |
| :------------|:-------|
| <span data-ttu-id="09eb2-256">全球多重租使用者</span><span class="sxs-lookup"><span data-stu-id="09eb2-256">World Wide Multi Tenant</span></span> | <span data-ttu-id="09eb2-257">可在所有用戶端Teams使用</span><span class="sxs-lookup"><span data-stu-id="09eb2-257">Available on all Teams clients</span></span> |
| <span data-ttu-id="09eb2-258">GCC</span><span class="sxs-lookup"><span data-stu-id="09eb2-258">GCC</span></span> | <span data-ttu-id="09eb2-259">可在所有用戶端Teams使用</span><span class="sxs-lookup"><span data-stu-id="09eb2-259">Available on all Teams clients</span></span> |
| <span data-ttu-id="09eb2-260">GCCH</span><span class="sxs-lookup"><span data-stu-id="09eb2-260">GCCH</span></span> | <span data-ttu-id="09eb2-261">可在桌面Teams使用</span><span class="sxs-lookup"><span data-stu-id="09eb2-261">Available on Teams desktop</span></span> |
| <span data-ttu-id="09eb2-262">國防部</span><span class="sxs-lookup"><span data-stu-id="09eb2-262">DoD</span></span> | <span data-ttu-id="09eb2-263">等待</span><span class="sxs-lookup"><span data-stu-id="09eb2-263">Pending</span></span> |

 ## <a name="related-topics"></a><span data-ttu-id="09eb2-264">相關主題</span><span class="sxs-lookup"><span data-stu-id="09eb2-264">Related topics</span></span>

- [<span data-ttu-id="09eb2-265">管理緊急電話</span><span class="sxs-lookup"><span data-stu-id="09eb2-265">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="09eb2-266">管理緊急電話原則</span><span class="sxs-lookup"><span data-stu-id="09eb2-266">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="09eb2-267">管理緊急通話路由策略 </span><span class="sxs-lookup"><span data-stu-id="09eb2-267">Manage emergency call routing policies </span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="09eb2-268">新增、變更或移除貴組織的緊急位置</span><span class="sxs-lookup"><span data-stu-id="09eb2-268">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="09eb2-269">指派或變更使用者的緊急位置</span><span class="sxs-lookup"><span data-stu-id="09eb2-269">Assign or change an emergency location for your user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="09eb2-270">雲端語音功能的網路設定</span><span class="sxs-lookup"><span data-stu-id="09eb2-270">Network settings for cloud voice features</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="09eb2-271">管理雲端語音功能的網路拓撲</span><span class="sxs-lookup"><span data-stu-id="09eb2-271">Manage your network topology for cloud voice features</span></span>](manage-your-network-topology.md)
