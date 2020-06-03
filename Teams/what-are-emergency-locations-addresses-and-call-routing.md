---
title: 規劃及管理緊急通話
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
- Calling Plans
- Direct Routing
- seo-marvel-mar2020
description: 瞭解緊急通話，包括緊急位址、緊急通話路由及動態緊急通話的相關資訊。
ms.openlocfilehash: 889446ca08289ccb15128bee8ca6b6170398c599
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539490"
---
# <a name="manage-emergency-calling"></a><span data-ttu-id="ec2ea-103">管理緊急通話</span><span class="sxs-lookup"><span data-stu-id="ec2ea-103">Manage emergency calling</span></span>

<span data-ttu-id="ec2ea-104">本文將說明管理緊急通話所需注意的概念， &mdash; 包括緊急位址、動態緊急位址及緊急通話路由的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-104">This article describes concepts you'll need to know to manage emergency calling&mdash;it includes information about emergency addresses, dynamic emergency addresses, and emergency call routing.</span></span> <span data-ttu-id="ec2ea-105">本文使用下列術語：</span><span class="sxs-lookup"><span data-stu-id="ec2ea-105">This article uses the following terminology:</span></span>

- <span data-ttu-id="ec2ea-106">**緊急位址**-市政位址是 &mdash; 貴組織中公司位置的物理或街道位址。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-106">**Emergency address** - A civic address&mdash;the physical or street address of a place of business for your organization.</span></span>

  <span data-ttu-id="ec2ea-107">例如，位址 12345 [*北部] 街道、[雷德蒙]、[98052 華盛頓] （WA））* 是用來將緊急呼叫路由至適當的派單頒發機構，並協助您尋找緊急來電者。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-107">For example, the address  *12345 North Main Street, Redmond, WA 98052* is used to route emergency calls to the appropriate dispatch authorities and to assist in locating the emergency caller.</span></span>

- <span data-ttu-id="ec2ea-108">**地點**-通常是底價、樓、翼或辦公室號碼。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-108">**Place** - Typically a floor, building, wing, or office number.</span></span> <span data-ttu-id="ec2ea-109">[地點] 與緊急位址相關聯，可在建築物中提供更精確的位置。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-109">Place is associated with an emergency address to give a more exact location within a building.</span></span> <span data-ttu-id="ec2ea-110">您可以有與緊急位址相關聯的不限制數量的位置。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-110">You can have an unlimited number of places associated with an emergency address.</span></span> <span data-ttu-id="ec2ea-111">例如，如果您的組織有多個建築物，您可能會想要在每個建築物中包含每個建築物和每個樓層的位置資訊。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-111">For example, if your organization has multiple buildings, you might want to include place information for each building and for every floor within each building.</span></span>  

- <span data-ttu-id="ec2ea-112">**緊急位置**-位置是 &mdash; 有選擇性位置的市政位址。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-112">**Emergency location** - A location is a civic address&mdash;with an optional place.</span></span> <span data-ttu-id="ec2ea-113">如果您的公司有一個以上的物理位置，可能需要一個以上的緊急位置。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-113">If your business has more than one physical location, it's likely that you'll need more than one emergency location.</span></span> 

  <span data-ttu-id="ec2ea-114">當您建立緊急位址時，系統會自動為此位址建立唯一的位置識別碼。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-114">When you create an emergency address, a unique location ID is automatically created for this address.</span></span>  <span data-ttu-id="ec2ea-115">如果您在 [緊急位址] 中新增位置 &mdash; ，例如，如果您在建築物位址加上樓面， &mdash; 就會為 [緊急位址] 和 [地點] 的組合建立位置 ID。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-115">If you add a place to an emergency address&mdash;for example, if you add a floor to a building address&mdash;a location ID is created for the combination of the emergency address and place.</span></span>  <span data-ttu-id="ec2ea-116">在這個範例中，會有兩個位置 Id：一個用於市政位址;一個用於已連接的市政位址和相關聯的位置。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-116">In this example, there will be two location IDs: one for the civic address; one for the joined civic address and associated place.</span></span>

  <span data-ttu-id="ec2ea-117">當您將緊急位置指派給使用者或網站時，它就是與使用者或網站相關聯的唯一位置識別碼。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-117">When you assign an emergency location to a user or site, it's this unique location ID that's associated with the user or site.</span></span>

- <span data-ttu-id="ec2ea-118">**已**登錄的位址-指派給每個通話方案使用者的緊急位址;它有時稱為靜態緊急位址或記錄的位址。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-118">**Registered address** - An emergency address that is assigned to each Calling Plan user; it is sometimes referred to as a static emergency address or address of record.</span></span>  <span data-ttu-id="ec2ea-119">（已註冊的位址不適用於直接路由使用者）。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-119">(Registered addresses do not apply to Direct Routing users.)</span></span>

<span data-ttu-id="ec2ea-120">您可以使用 [團隊系統管理中心]，為通話方案使用者建立緊急位址。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-120">You create emergency addresses for Calling Plan users by using the Teams admin center.</span></span>  

>[!Note]
><span data-ttu-id="ec2ea-121">您管理緊急呼叫的方式有一些差異，取決於您使用的是電話系統通話方案，還是您的 PSTN 連線的電話系統直向路由。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-121">There are some differences in how you manage emergency calling depending on whether you are using Phone System Calling Plans or Phone System Direct Routing for your PSTN connectivity.</span></span> <span data-ttu-id="ec2ea-122">本文將說明這些考慮。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-122">These considerations are described throughout this article.</span></span>

## <a name="emergency-address-validation"></a><span data-ttu-id="ec2ea-123">緊急位址驗證</span><span class="sxs-lookup"><span data-stu-id="ec2ea-123">Emergency address validation</span></span>

<span data-ttu-id="ec2ea-124">若要將緊急位址指派給使用者或網路識別碼，您必須確保緊急位址標示為「已驗證」。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-124">To assign an emergency address to a user or to a network identifier, you must ensure that the emergency address is marked as "validated."</span></span>  <span data-ttu-id="ec2ea-125">位址驗證可確保位址合法，且在指派後無法進行修改。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-125">Address validation ensures that the address is legitimate, and that it cannot be modified after it is assigned.</span></span> 

<span data-ttu-id="ec2ea-126">如果您使用 [團隊系統管理中心] 的 [位址圖] 搜尋功能來定義緊急位址，位址就會自動標示為 [已驗證]。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-126">If you define an emergency address by using the address map search feature in the Teams admin center, the address is automatically marked as validated.</span></span> <span data-ttu-id="ec2ea-127">您無法修改已驗證的緊急位址。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-127">You cannot modify a validated emergency address.</span></span> <span data-ttu-id="ec2ea-128">因此，如果位址的格式或代表變更，您必須使用已更新的格式建立新的位址。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-128">Therefore, if the format or representation of the address changes, you must create a new address with the updated format.</span></span>


## <a name="emergency-address-geo-codes"></a><span data-ttu-id="ec2ea-129">緊急位址 geo 代碼</span><span class="sxs-lookup"><span data-stu-id="ec2ea-129">Emergency address geo codes</span></span>

<span data-ttu-id="ec2ea-130">每個緊急位址都可以有與其相關聯的地理程式碼（緯度和經度）。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-130">Each emergency address can have a geo code (latitude and longitude) associated with it.</span></span> <span data-ttu-id="ec2ea-131">在某些國家/地區使用這些地理程式碼，以協助以動態位置路由緊急通話。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-131">These geo codes are used in some countries to assist in routing emergency calls with dynamic locations.</span></span> 

<span data-ttu-id="ec2ea-132">如果您使用 [團隊系統管理中心] 的 [位址圖] 搜尋功能來定義緊急位址，則地理程式碼會自動與緊急位址建立關聯。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-132">If you define an emergency address by using the address map search feature in the Teams admin center, the geo code is automatically associated with an emergency address.</span></span> <span data-ttu-id="ec2ea-133">如果您使用 PowerShell 定義位址，您也可以將地區代碼與位址建立關聯。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-133">You can also associate geo codes with an address if you define the address by using PowerShell.</span></span> <span data-ttu-id="ec2ea-134">不過，Microsoft 建議您使用 [團隊系統管理中心] 中的 [地圖搜尋] 功能，為通話方案建立緊急位址，這將確保位址已格式化、驗證且具有適當的地區代碼。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-134">However, Microsoft recommends that you create emergency addresses for Calling Plan by using the map search feature in Teams admin center, which will ensure that the addresses are formatted, validated, and have the appropriate geo codes.</span></span>  

>[!Important]
><span data-ttu-id="ec2ea-135">若要將緊急位置指派給網路識別碼以進行動態緊急通話，緊急位址必須包含適當的地理程式碼。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-135">To assign an emergency location to a network identifier for dynamic emergency calling, the emergency address must contain an appropriate geo code.</span></span>


## <a name="considerations-for-calling-plans"></a><span data-ttu-id="ec2ea-136">通話方案的考慮</span><span class="sxs-lookup"><span data-stu-id="ec2ea-136">Considerations for Calling Plans</span></span>

<span data-ttu-id="ec2ea-137">若要瞭解您所在地區是否有可用的通話方案，請參閱[通話方案的國家/地區可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-137">To find out whether Calling Plans is available in your area, see [Country and region availability for Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>


### <a name="emergency-call-enablement"></a><span data-ttu-id="ec2ea-138">緊急通話啟用</span><span class="sxs-lookup"><span data-stu-id="ec2ea-138">Emergency call enablement</span></span>

<span data-ttu-id="ec2ea-139">每個通話方案使用者都會自動啟用緊急通話，而且必須擁有與其指派的電話號碼相關聯的註冊緊急位址。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-139">Each Calling Plan user is automatically enabled for emergency calling and is required to have a registered emergency address associated with their assigned telephone number.</span></span> 

<span data-ttu-id="ec2ea-140">當位置必須與電話號碼相關聯時，視國家/地區而定：</span><span class="sxs-lookup"><span data-stu-id="ec2ea-140">When the location must be associated to the telephone number depends on the country/region:</span></span>

- <span data-ttu-id="ec2ea-141">例如，在美國和加拿大，在指派數位給使用者時，需要緊急位置。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-141">In the United States and Canada, for example, an emergency location is required when a number is assigned to a user.</span></span>

- <span data-ttu-id="ec2ea-142">&mdash; &mdash; 如果您是從 Office 365 取得電話號碼，或從其他服務提供者或運營商轉接時，您可以在歐洲、中東及非洲（EMEA）等其他國家或地區使用。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-142">For other countries&mdash;such as in Europe, the Middle East, and Africa (EMEA)&mdash;an emergency location is required when you get the phone number from Office 365 or when it's transferred from another service provider or carrier.</span></span>

### <a name="dynamic-emergency-calling"></a><span data-ttu-id="ec2ea-143">動態緊急通話</span><span class="sxs-lookup"><span data-stu-id="ec2ea-143">Dynamic emergency calling</span></span>

<span data-ttu-id="ec2ea-144">Microsoft 通話方案的動態緊急通話可提供根據團隊用戶端目前位置來設定和路由緊急通話的功能。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-144">Dynamic emergency calling for Microsoft Calling Plans provides the capability to configure and route emergency calls based on the current location of the Teams client.</span></span> <span data-ttu-id="ec2ea-145">自動路由至適當的公用安全回應點（PSAP）或通知安全服務台人員的功能，會視小組使用者使用的國家/地區而有所不同。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-145">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) or to notify security desk personnel varies depending on the country of usage of the Teams user.</span></span>  

<span data-ttu-id="ec2ea-146">針對呼叫方案使用者，只支援在美國進行路由緊急通話的動態位置，如下所示。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-146">For Calling Plan users, dynamic location for routing emergency calls is only supported in the United States as follows.</span></span> <span data-ttu-id="ec2ea-147">（如需有關動態緊急通話與直接路由的詳細資訊，請參閱[直接路由的注意事項](#considerations-for-direct-routing)。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-147">(For information about dynamic emergency calling and Direct Routing, see [Considerations for Direct Routing](#considerations-for-direct-routing).</span></span>

- <span data-ttu-id="ec2ea-148">如果美國通話方案使用者的團隊用戶端動態取得美國境內的緊急位址，該位址會用於緊急路由，而不是已註冊的位址，而且通話會自動路由到位址的服務區域中的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-148">If a Teams client for a United States Calling Plan user dynamically acquires an emergency address within the United States, that address is used for emergency routing instead of the registered address, and the call will be automatically routed to the PSAP in the serving area of the address.</span></span>

- <span data-ttu-id="ec2ea-149">如果美國通話方案使用者的團隊用戶端無法在美國動態取得緊急位址，則會使用註冊的緊急位址來協助螢幕並傳送通話。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-149">If a Teams client for a United States Calling Plan user doesn't dynamically acquire an emergency address within the United States, then the registered emergency address is used to help screen and route the call.</span></span> <span data-ttu-id="ec2ea-150">不過，在將呼叫者連線至適當的 PSAP 之前，會進行通話，以判斷是否需要更新的位址。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-150">However, the call will be screened to determine if an updated address is required before connecting the caller to the appropriate PSAP.</span></span>

<span data-ttu-id="ec2ea-151">在美國，您必須設定是指派給網路識別碼之緊急位置一部分的市政位址， &mdash; 並包含相關聯的地功能變數代碼。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-151">In the United States, you must configure the civic address that is part of the emergency locations that are assigned to network identifiers&mdash;and include the associated geo codes.</span></span> <span data-ttu-id="ec2ea-152">如需詳細資訊，請參閱[規劃及設定動態緊急通話](configure-dynamic-emergency-calling.md)。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-152">For more information, see [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>


### <a name="emergency-call-routing"></a><span data-ttu-id="ec2ea-153">緊急通話路由</span><span class="sxs-lookup"><span data-stu-id="ec2ea-153">Emergency call routing</span></span>

<span data-ttu-id="ec2ea-154">當小組通話方案使用者撥打電話號碼時，通話如何路由至 PSAP，取決於下列情況：</span><span class="sxs-lookup"><span data-stu-id="ec2ea-154">When a Teams Calling Plan user dials an emergency number, how the call is routed to the PSAP depends on the following:</span></span>

- <span data-ttu-id="ec2ea-155">緊急位址是否由團隊用戶端動態決定。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-155">Whether the emergency address is dynamically determined by the Teams client.</span></span>

- <span data-ttu-id="ec2ea-156">緊急位址是否是與使用者的電話號碼相關聯的登入位址。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-156">Whether the emergency address is the registered address associated with the user's phone number.</span></span>

- <span data-ttu-id="ec2ea-157">該國家/地區的緊急通話網路。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-157">The emergency calling network of that country.</span></span>

  <span data-ttu-id="ec2ea-158">**在美國：**</span><span class="sxs-lookup"><span data-stu-id="ec2ea-158">**In the United States:**</span></span>

  - <span data-ttu-id="ec2ea-159">如果團隊用戶端位於租使用者定義的動態緊急位置，來自該用戶端的緊急呼叫會自動路由至該地理位置的 PSAP 服務。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-159">If a Teams client is located at a tenant-defined dynamic emergency location, emergency calls from that client are automatically routed to the PSAP serving that geographic location.</span></span> 

  - <span data-ttu-id="ec2ea-160">如果團隊用戶端不在租使用者的動態緊急位置，來自該用戶端的緊急呼叫是由國內話務中心加以遮罩，在將來電轉接到該地理位置的 PSAP 之前，決定呼叫者的位置。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-160">If a Teams client is not located at a tenant-defined dynamic emergency location, emergency calls from that client are screened by a national call center to determine the location of the caller before transferring the call to the PSAP serving that geographic location.</span></span>

  - <span data-ttu-id="ec2ea-161">如果緊急來電者無法將其緊急位置更新至 [篩選中心]，該呼叫將會傳送給呼叫者登入位址的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-161">If an emergency caller is unable to update their emergency location to the screening center, the call will be transferred to the PSAP serving the caller's registered address.</span></span>

  <span data-ttu-id="ec2ea-162">**在加拿大、愛爾蘭及英國**，緊急通話是在將呼叫連接至適當的派遣中心之前，先進行確認，以判斷使用者目前的位置。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-162">**In Canada, Ireland, and the United Kingdom**, emergency calls are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center.</span></span> 

  <span data-ttu-id="ec2ea-163">**在華北、德國和西班牙**，緊急通話會直接路由到 PSAP 中與電話號碼相關聯之緊急位址的服務，而不管來電者的位置為何。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-163">**In France, Germany, and Spain**, emergency calls are routed directly to the PSAP serving the emergency address associated with the number regardless of the location of the caller.</span></span>

  <span data-ttu-id="ec2ea-164">**在荷蘭**，無論來電者為何位置，緊急通話都會直接路由到該號碼當地區號的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-164">**In the Netherlands**, emergency calls are routed directly to the PSAP for the local area code of the number regardless of the location of the caller.</span></span>

  <span data-ttu-id="ec2ea-165">**在澳大利亞**，緊急位址是由電信公司合作夥伴設定和路由。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-165">**In Australia**, emergency addresses are configured and routed by the carrier partner.</span></span>

  <span data-ttu-id="ec2ea-166">**在日本**，不支援緊急通話。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-166">**In Japan**, emergency calling is not supported.</span></span>


<span data-ttu-id="ec2ea-167">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="ec2ea-167">For more information, see:</span></span>

- [<span data-ttu-id="ec2ea-168">通話方案</span><span class="sxs-lookup"><span data-stu-id="ec2ea-168">Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="ec2ea-169">通話方案所用的不同類型的電話號碼</span><span class="sxs-lookup"><span data-stu-id="ec2ea-169">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

- [<span data-ttu-id="ec2ea-170">緊急通話條款及條件</span><span class="sxs-lookup"><span data-stu-id="ec2ea-170">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-direct-routing"></a><span data-ttu-id="ec2ea-171">直接路由的考慮</span><span class="sxs-lookup"><span data-stu-id="ec2ea-171">Considerations for Direct Routing</span></span>

<span data-ttu-id="ec2ea-172">如果您的地區無法使用通話方案，或者您想要保留現有的承運人，請考慮[直接傳送](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-172">If Calling Plans are not available in your area or you want to keep your existing carrier, consider [Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="ec2ea-173">如需詳細資訊，請參閱[設定直接路由](direct-routing-configure.md)及[管理緊急呼叫路由策略](manage-emergency-call-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-173">For more information, see [Configure Direct Routing](direct-routing-configure.md) and [Manage emergency call routing policies](manage-emergency-call-routing-policies.md).</span></span>

### <a name="emergency-call-enablement-and-configuration"></a><span data-ttu-id="ec2ea-174">緊急通話啟用與設定</span><span class="sxs-lookup"><span data-stu-id="ec2ea-174">Emergency call enablement and configuration</span></span>

<span data-ttu-id="ec2ea-175">您必須使用小組緊急呼叫路由策略（TeamsEmergencyCallRoutingPolicy）來定義直接路由使用者的緊急通話原則，以定義緊急號碼及其相關聯的路由目的地。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-175">You must define emergency calling policies for Direct Routing users by using a Teams emergency call routing policy (TeamsEmergencyCallRoutingPolicy) to define emergency numbers and their associated routing destination.</span></span> <span data-ttu-id="ec2ea-176">（請注意，直接路由使用者不支援註冊的緊急位置。）</span><span class="sxs-lookup"><span data-stu-id="ec2ea-176">(Note that registered emergency locations are not supported for Direct Routing users.)</span></span>

<span data-ttu-id="ec2ea-177">您可以將緊急呼叫路由策略指派給小組直接傳送使用者帳戶、網路網站或兩者。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-177">You can assign an emergency call routing policy  to a Teams Direct Routing user account, a network site, or both.</span></span> <span data-ttu-id="ec2ea-178">當團隊用戶端啟動或變更網路連線時，小組會在用戶端所在的網路網站上執行查閱，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ec2ea-178">When a Teams client starts or changes a network connection, Teams performs a lookup of the network site where the client is located as follows:</span></span>

- <span data-ttu-id="ec2ea-179">如果緊急呼叫路由策略與網站相關聯，則會使用網站原則設定緊急通話。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-179">If an emergency call routing policy is associated with the site, then the site policy is used to configure emergency calling.</span></span>

- <span data-ttu-id="ec2ea-180">如果沒有與網站相關聯的緊急呼叫路由策略，或用戶端連線至未定義的網站，則會使用與使用者帳戶相關聯的緊急呼叫路由策略來設定緊急通話。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-180">If there is no emergency call routing policy associated with the site, or if the client is connected at an undefined site, then the emergency call routing policy associated with the user account is used to configure emergency calling.</span></span> 

- <span data-ttu-id="ec2ea-181">如果團隊用戶端無法取得緊急通話路由策略，就不會啟用緊急呼叫的使用者。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-181">If the Teams client is unable to obtain an emergency call routing policy, then the user is not enabled for emergency calling.</span></span>

### <a name="dynamic-emergency-calling"></a><span data-ttu-id="ec2ea-182">動態緊急通話</span><span class="sxs-lookup"><span data-stu-id="ec2ea-182">Dynamic emergency calling</span></span>

<span data-ttu-id="ec2ea-183">直接路由使用者的團隊用戶端可以取得動態緊急位址，這可以根據來電者的位置來動態路由通話。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-183">Teams clients for Direct Routing users can acquire a dynamic emergency address, which can be used to dynamically route calls based upon the location of the caller.</span></span> <span data-ttu-id="ec2ea-184">如需詳細資訊，請參閱[設定動態緊急通話](configure-dynamic-emergency-calling.md)。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-184">For more information, see [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

### <a name="emergency-call-routing"></a><span data-ttu-id="ec2ea-185">緊急通話路由</span><span class="sxs-lookup"><span data-stu-id="ec2ea-185">Emergency call routing</span></span>

<span data-ttu-id="ec2ea-186">緊急呼叫路由策略會參照線上 PSTN 使用，必須具備適當的直接路由設定，才能將緊急呼叫正確路由至適當的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-186">The emergency call routing policy references an online PSTN usage, which must have the appropriate Direct Routing configuration to properly route the emergency calls to the appropriate PSTN gateway(s).</span></span> <span data-ttu-id="ec2ea-187">特別是，您必須確保緊急撥號字串有 OnlineVoiceRoute。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-187">In particular, you must ensure that there is an OnlineVoiceRoute for the emergency dial string.</span></span> <span data-ttu-id="ec2ea-188">如需詳細資訊，請參閱[設定直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-188">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span> 

<span data-ttu-id="ec2ea-189">（注意：團隊用戶端會在緊急電話號碼前面加上「+」登入，就像商務用 Skype 用戶端所做的一樣，也就是 + 911。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-189">(Note: Teams clients prepend the "+" sign in front of emergency numbers in a similar manner that Skype for Business client does; that is, +911.</span></span> <span data-ttu-id="ec2ea-190">在未來幾個月內將會修改這項行為，如此一來，進行緊急通話的小組就不會再傳送數位前面的 "+";也就是說，911。）</span><span class="sxs-lookup"><span data-stu-id="ec2ea-190">This behavior will be modified in the coming months so that Teams emergency calls will no longer be sending a "+" preceding the number; that is, 911.)</span></span>

<span data-ttu-id="ec2ea-191">針對直接路由使用者動態路由緊急呼叫的能力，視特定國家/地區內的緊急呼叫網路而定。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-191">The ability to dynamically route emergency calls for Direct Routing users varies depending on the emergency calling network within a given country.</span></span> <span data-ttu-id="ec2ea-192">提供兩種解決方案：</span><span class="sxs-lookup"><span data-stu-id="ec2ea-192">There are two solutions available:</span></span>

- <span data-ttu-id="ec2ea-193">緊急路由服務提供者（僅限美國）</span><span class="sxs-lookup"><span data-stu-id="ec2ea-193">Emergency Routing Service Providers (US only)</span></span> 
- <span data-ttu-id="ec2ea-194">緊急位置身分識別號碼（ELIN）閘道應用程式</span><span class="sxs-lookup"><span data-stu-id="ec2ea-194">Emergency Location Identification Number (ELIN) gateway applications</span></span>

#### <a name="emergency-routing-service-providers"></a><span data-ttu-id="ec2ea-195">緊急路由服務提供者</span><span class="sxs-lookup"><span data-stu-id="ec2ea-195">Emergency Routing Service Providers</span></span>

<span data-ttu-id="ec2ea-196">在美國，有許多認證的緊急路由服務提供者（ERSPs）可以根據來電者的位置自動路由緊急通話。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-196">In the United States, there are numerous certified Emergency Routing Service Providers (ERSPs) that can automatically route emergency calls based upon the location of the caller.</span></span>

- <span data-ttu-id="ec2ea-197">如果緊急路由服務提供者已整合至直接路由部署，則使用動態取得位置的緊急呼叫會自動路由到該位置的公用安全應答點（PSAP）。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-197">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span>

-  <span data-ttu-id="ec2ea-198">在沒有動態取得位置的緊急通話是先進行篩選，以便在根據更新的位置將呼叫連線至適當的派遣中心之前，決定使用者的目前位置。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-198">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span>

<span data-ttu-id="ec2ea-199">如需詳細資訊，請參閱針對[直接路由認證的會話邊界控制器](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-199">For more information, see [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>


#### <a name="emergency-location-identification-number-elin-applications"></a><span data-ttu-id="ec2ea-200">緊急位置識別號碼（ELIN）應用程式</span><span class="sxs-lookup"><span data-stu-id="ec2ea-200">Emergency Location Identification Number (ELIN) applications</span></span>

<span data-ttu-id="ec2ea-201">會話邊界控制器（SBCs）可以包含緊急位置身分識別號碼（ELIN）應用程式。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-201">Session Border Controllers (SBCs) can include Emergency Location Identification Number (ELIN) applications.</span></span> <span data-ttu-id="ec2ea-202">如果 SBC ELIN 應用程式已整合至直接路由部署，您必須在 ELIN 應用程式中設定緊急位址和相關的電話號碼，然後將 ELIN 記錄上傳到各自 PSTN 中的緊急呼叫資料庫。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-202">If an SBC ELIN application is integrated into a Direct Routing deployment, you must configure the emergency addresses and associated telephone numbers in the ELIN application, and then upload the ELIN records to the emergency calling database in the respective PSTN.</span></span>  <span data-ttu-id="ec2ea-203">使用 ELIN 識別碼的小組緊急位置，必須符合 ELIN 應用程式中的專案。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-203">Teams emergency locations with an ELIN identifier must match those within the ELIN application.</span></span>

<span data-ttu-id="ec2ea-204">當有動態取得位置的緊急通話路由至適當的 SBC 時，ELIN 應用程式：</span><span class="sxs-lookup"><span data-stu-id="ec2ea-204">When an emergency call with a dynamically acquired location is routed to the appropriate SBC, the ELIN application:</span></span>

- <span data-ttu-id="ec2ea-205">分析來電者的緊急位置。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-205">Parses the emergency location of the caller.</span></span>
- <span data-ttu-id="ec2ea-206">將位置與 ELIN 記錄相符。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-206">Matches the location to an ELIN record.</span></span>
- <span data-ttu-id="ec2ea-207">以 ELIN 電話號碼取代緊急來電者的號碼。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-207">Substitutes the emergency caller's number with the ELIN phone number.</span></span>
- <span data-ttu-id="ec2ea-208">將呼叫路由至該位置的 PSAP，然後重新分派者從上傳的 ELIN 記錄中取得位置。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-208">Routes the call to the PSAP serving that location, and then the dispatchers obtain the location from the uploaded ELIN record.</span></span>

<span data-ttu-id="ec2ea-209">當來電回緊急電話號碼時，ELIN 應用程式將會對原始緊急來電者執行反向呼叫數位替換。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-209">Upon a call back to the emergency number, the ELIN application will do the reverse called number substitution to that of the original emergency caller.</span></span> 

<span data-ttu-id="ec2ea-210">如需詳細資訊，請參閱針對[直接路由認證的會話邊界控制器](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-210">For more information, see [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>


## <a name="security-desk-notification"></a><span data-ttu-id="ec2ea-211">Security 辦公桌通知</span><span class="sxs-lookup"><span data-stu-id="ec2ea-211">Security desk notification</span></span>

<span data-ttu-id="ec2ea-212">Microsoft 通話方案和電話系統直接路由都提供了 Security 辦公桌通知。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-212">Security desk notification is available with both Microsoft Calling Plans and Phone System Direct Routing.</span></span>

<span data-ttu-id="ec2ea-213">您使用團隊緊急通話原則（TeamsEmergencyCallingPolicy）來設定要在緊急通話期間收到通知的人員，以及通知的方式： [僅限聊天]、[conferenced] 和 [已靜音]，或 [conferenced] 中的 [取消靜音] 功能。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-213">You use a Teams emergency calling policy (TeamsEmergencyCallingPolicy) to configure who should be notified during an emergency call and how they are notified: chat only, conferenced in and muted, or conferenced in and muted but with the ability to unmute.</span></span>  <span data-ttu-id="ec2ea-214">您也可以指定使用者或群組的外部 PSTN 號碼來撥打並加入緊急通話。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-214">You can also specify an external PSTN number of a user or group to call and join the emergency call.</span></span> 

<span data-ttu-id="ec2ea-215">緊急通話原則可以授與團隊使用者帳戶、指派給網路網站，或同時獲兩者。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-215">An emergency calling policy can be granted to a Teams user account, assigned to a network site, or both.</span></span>  <span data-ttu-id="ec2ea-216">當團隊用戶端啟動或變更網路連線時，小組會針對用戶端所在的網路網站執行查閱：</span><span class="sxs-lookup"><span data-stu-id="ec2ea-216">When a Teams client starts or changes a network connection, Teams performs a lookup of the network site where the client is located:</span></span>

- <span data-ttu-id="ec2ea-217">如果緊急通話原則與網路網站相關聯，則會使用網站原則來設定 security 服務台通知。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-217">If an emergency calling policy is associated with a network site, then the site policy is used to configure security desk notification.</span></span>

- <span data-ttu-id="ec2ea-218">如果沒有緊急通話原則與網站相關聯，或用戶端連線至未定義的網站，則會使用與使用者帳戶相關聯的緊急呼叫原則來設定 security 辦公桌通知。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-218">If there is no emergency calling policy associated with the site, or if the client is connected at an undefined site, then the emergency calling policy associated with the user account is used to configure security desk notification.</span></span>  

- <span data-ttu-id="ec2ea-219">如果團隊用戶端無法取得緊急通話原則，就不會為使用者啟用 security 辦公桌通知。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-219">If the Teams client is unable to obtain an emergency calling policy, then the user is not enabled for security desk notification.</span></span>

<span data-ttu-id="ec2ea-220">在緊急通話期間，安全服務台是 conferenced 到通話中，安全服務台使用者的體驗是根據小組的緊急通話原則來控制。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-220">During an emergency call, a security desk is conferenced into the call and the experience of the security desk user is controlled based upon the Teams emergency calling policy.</span></span> <span data-ttu-id="ec2ea-221">群組聊天是從每個安全服務台成員開始，緊急呼叫者的位置會透過重要的訊息通知來共用。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-221">A group chat is started with each security desk member, and the location of the emergency caller is shared via an important message notification.</span></span>  <span data-ttu-id="ec2ea-222">如果會議選項是設定為原則的一部分，則每個安全服務台使用者也會在會議中另行稱為。</span><span class="sxs-lookup"><span data-stu-id="ec2ea-222">If a conference option is configured as part of the policy, each security desk user is additionally called as part of the conference.</span></span>

    
## <a name="related-topics"></a><span data-ttu-id="ec2ea-223">相關主題</span><span class="sxs-lookup"><span data-stu-id="ec2ea-223">Related topics</span></span>

- [<span data-ttu-id="ec2ea-224">管理緊急電話原則</span><span class="sxs-lookup"><span data-stu-id="ec2ea-224">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="ec2ea-225">管理緊急呼叫路由策略</span><span class="sxs-lookup"><span data-stu-id="ec2ea-225">Manage emergency call routing policies </span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="ec2ea-226">新增、變更或移除貴組織的緊急位置</span><span class="sxs-lookup"><span data-stu-id="ec2ea-226">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="ec2ea-227">指派或變更使用者的緊急位置</span><span class="sxs-lookup"><span data-stu-id="ec2ea-227">Assign or change an emergency location for your user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="ec2ea-228">規劃和設定動態緊急電話</span><span class="sxs-lookup"><span data-stu-id="ec2ea-228">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)
