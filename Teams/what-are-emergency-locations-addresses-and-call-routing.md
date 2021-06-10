---
title: 規劃及管理緊急電話
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
- m365initiative-voice
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
description: 瞭解緊急通話，包括關於緊急位址、緊急電話路由和動態緊急電話的資訊。
ms.openlocfilehash: 4f2ef86d05537a147a459fd6bc121f0680b534bd
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031599"
---
# <a name="manage-emergency-calling"></a><span data-ttu-id="e818f-103">管理緊急電話</span><span class="sxs-lookup"><span data-stu-id="e818f-103">Manage emergency calling</span></span>

<span data-ttu-id="e818f-104">本文將說明管理緊急電話時必須瞭解的概念，其中包含緊急位址、動態緊急位址和 &mdash; 緊急電話路由的資訊。</span><span class="sxs-lookup"><span data-stu-id="e818f-104">This article describes concepts you'll need to know to manage emergency calling&mdash;it includes information about emergency addresses, dynamic emergency addresses, and emergency call routing.</span></span> <span data-ttu-id="e818f-105">本文使用下列術語：</span><span class="sxs-lookup"><span data-stu-id="e818f-105">This article uses the following terminology:</span></span>

- <span data-ttu-id="e818f-106">**緊急位址** - 組織營業地點的市民位址 &mdash; 或街地位址。</span><span class="sxs-lookup"><span data-stu-id="e818f-106">**Emergency address** - A civic address&mdash;the physical or street address of a place of business for your organization.</span></span>

  <span data-ttu-id="e818f-107">例如，位址  *12345 North Main Street， Redmond， WA 98052* 是用來路由緊急電話給適當的調度機構，並協助尋找緊急來電者。</span><span class="sxs-lookup"><span data-stu-id="e818f-107">For example, the address  *12345 North Main Street, Redmond, WA 98052* is used to route emergency calls to the appropriate dispatch authorities and to assist in locating the emergency caller.</span></span>

- <span data-ttu-id="e818f-108">**位置** - 通常是樓面、建築物、樓面或辦公室號碼。</span><span class="sxs-lookup"><span data-stu-id="e818f-108">**Place** - Typically a floor, building, wing, or office number.</span></span> <span data-ttu-id="e818f-109">Place 與緊急位址相關聯，以在建築物內提供更精確的位置。</span><span class="sxs-lookup"><span data-stu-id="e818f-109">Place is associated with an emergency address to give a more exact location within a building.</span></span> <span data-ttu-id="e818f-110">您可以擁有無限個與緊急位址相關聯的位置。</span><span class="sxs-lookup"><span data-stu-id="e818f-110">You can have an unlimited number of places associated with an emergency address.</span></span> <span data-ttu-id="e818f-111">例如，如果貴組織有多個建築物，您可能會想要包含每個建築物和每棟大樓內每一層的位置資訊。</span><span class="sxs-lookup"><span data-stu-id="e818f-111">For example, if your organization has multiple buildings, you might want to include place information for each building and for every floor within each building.</span></span>  

- <span data-ttu-id="e818f-112">**緊急位置** - 位置是具有選擇性位置 &mdash; 的市民位址。</span><span class="sxs-lookup"><span data-stu-id="e818f-112">**Emergency location** - A location is a civic address&mdash;with an optional place.</span></span> <span data-ttu-id="e818f-113">如果您的公司有一多個實體位置，您可能需要多個緊急位置。</span><span class="sxs-lookup"><span data-stu-id="e818f-113">If your business has more than one physical location, it's likely that you'll need more than one emergency location.</span></span> 

  <span data-ttu-id="e818f-114">當您建立緊急位址時，會自動為此位址建立唯一的位置識別碼。</span><span class="sxs-lookup"><span data-stu-id="e818f-114">When you create an emergency address, a unique location ID is automatically created for this address.</span></span>  <span data-ttu-id="e818f-115">例如，如果您新增一個位置至緊急位址，如果您新增樓面至建築物位址，會針對緊急位址和地點的組合建立 &mdash; &mdash; 位置識別碼。</span><span class="sxs-lookup"><span data-stu-id="e818f-115">If you add a place to an emergency address&mdash;for example, if you add a floor to a building address&mdash;a location ID is created for the combination of the emergency address and place.</span></span>  <span data-ttu-id="e818f-116">在此範例中，將會有兩個位置的 ID：一個為市民位址;一個為已加入的市民位址和相關位置。</span><span class="sxs-lookup"><span data-stu-id="e818f-116">In this example, there will be two location IDs: one for the civic address; one for the joined civic address and associated place.</span></span>

  <span data-ttu-id="e818f-117">當您將緊急位置指派給使用者或網站時，這是與使用者或網站相關聯的這個唯一位置識別碼。</span><span class="sxs-lookup"><span data-stu-id="e818f-117">When you assign an emergency location to a user or site, it's this unique location ID that's associated with the user or site.</span></span>

- <span data-ttu-id="e818f-118">**已登入位址** - 指派給每個通話方案使用者的緊急位址;有時稱為靜態緊急位址或記錄位址。</span><span class="sxs-lookup"><span data-stu-id="e818f-118">**Registered address** - An emergency address that is assigned to each Calling Plan user; it is sometimes referred to as a static emergency address or address of record.</span></span>  <span data-ttu-id="e818f-119"> (登入位址不適用於直接路由使用者。) </span><span class="sxs-lookup"><span data-stu-id="e818f-119">(Registered addresses do not apply to Direct Routing users.)</span></span>

<span data-ttu-id="e818f-120">您可以使用系統管理中心，為通話方案使用者Teams位址。</span><span class="sxs-lookup"><span data-stu-id="e818f-120">You create emergency addresses for Calling Plan users by using the Teams admin center.</span></span>  

>[!Note]
><span data-ttu-id="e818f-121">您管理緊急電話的一些方式有一些差異，電話系統 PSTN 電話系統直接路由。</span><span class="sxs-lookup"><span data-stu-id="e818f-121">There are some differences in how you manage emergency calling depending on whether you are using Phone System Calling Plans or Phone System Direct Routing for your PSTN connectivity.</span></span> <span data-ttu-id="e818f-122">本文將說明這些考慮事項。</span><span class="sxs-lookup"><span data-stu-id="e818f-122">These considerations are described throughout this article.</span></span>

## <a name="emergency-address-validation"></a><span data-ttu-id="e818f-123">緊急位址驗證</span><span class="sxs-lookup"><span data-stu-id="e818f-123">Emergency address validation</span></span>

<span data-ttu-id="e818f-124">若要將緊急位址指派給使用者或網路識別碼，您必須確保緊急位址標示為「已驗證」。</span><span class="sxs-lookup"><span data-stu-id="e818f-124">To assign an emergency address to a user or to a network identifier, you must ensure that the emergency address is marked as "validated."</span></span>  <span data-ttu-id="e818f-125">位址驗證可確保位址合法，且在指派位址後無法修改。</span><span class="sxs-lookup"><span data-stu-id="e818f-125">Address validation ensures that the address is legitimate, and that it cannot be modified after it is assigned.</span></span> 

<span data-ttu-id="e818f-126">如果您在系統管理中心使用位址地圖搜尋功能來定義緊急Teams，位址會自動標示為已驗證。</span><span class="sxs-lookup"><span data-stu-id="e818f-126">If you define an emergency address by using the address map search feature in the Teams admin center, the address is automatically marked as validated.</span></span> <span data-ttu-id="e818f-127">您無法修改已驗證的緊急位址。</span><span class="sxs-lookup"><span data-stu-id="e818f-127">You cannot modify a validated emergency address.</span></span> <span data-ttu-id="e818f-128">因此，如果位址的格式或表示方式變更，您必須使用更新的格式建立新位址。</span><span class="sxs-lookup"><span data-stu-id="e818f-128">Therefore, if the format or representation of the address changes, you must create a new address with the updated format.</span></span>


## <a name="emergency-address-geo-codes"></a><span data-ttu-id="e818f-129">緊急位址地理代碼</span><span class="sxs-lookup"><span data-stu-id="e818f-129">Emergency address geo codes</span></span>

<span data-ttu-id="e818f-130">每個緊急位址都可以有一個地理代碼 (經緯度) 與它相關聯。</span><span class="sxs-lookup"><span data-stu-id="e818f-130">Each emergency address can have a geo code (latitude and longitude) associated with it.</span></span> <span data-ttu-id="e818f-131">在一些國家/地區，這些地理代碼可用來協助以動態位置路由緊急電話。</span><span class="sxs-lookup"><span data-stu-id="e818f-131">These geo codes are used in some countries to assist in routing emergency calls with dynamic locations.</span></span> 

<span data-ttu-id="e818f-132">如果您在系統管理中心使用位址地圖搜尋功能來定義緊急位址Teams，則地理代碼會自動與緊急位址相關聯。</span><span class="sxs-lookup"><span data-stu-id="e818f-132">If you define an emergency address by using the address map search feature in the Teams admin center, the geo code is automatically associated with an emergency address.</span></span> <span data-ttu-id="e818f-133">如果您使用 PowerShell 定義位址，您也可以將地理位置代碼與位址建立關聯。</span><span class="sxs-lookup"><span data-stu-id="e818f-133">You can also associate geo codes with an address if you define the address by using PowerShell.</span></span> <span data-ttu-id="e818f-134">不過，Microsoft 建議您使用 Teams 系統管理中心的地圖搜尋功能，為通話方案建立緊急位址，以確保位址已格式化、驗證，並擁有適當的地理位置代碼。</span><span class="sxs-lookup"><span data-stu-id="e818f-134">However, Microsoft recommends that you create emergency addresses for Calling Plan by using the map search feature in Teams admin center, which will ensure that the addresses are formatted, validated, and have the appropriate geo codes.</span></span>  

>[!Important]
><span data-ttu-id="e818f-135">若要將緊急位置指派給動態緊急電話的網路識別碼，緊急位址必須包含適當的地理位置代碼。</span><span class="sxs-lookup"><span data-stu-id="e818f-135">To assign an emergency location to a network identifier for dynamic emergency calling, the emergency address must contain an appropriate geo code.</span></span>


## <a name="considerations-for-calling-plans"></a><span data-ttu-id="e818f-136">通話方案考慮</span><span class="sxs-lookup"><span data-stu-id="e818f-136">Considerations for Calling Plans</span></span>

<span data-ttu-id="e818f-137">若要瞭解您的地區是否提供通話方案，請參閱通話方案的國家 [/地區可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="e818f-137">To find out whether Calling Plans is available in your area, see [Country and region availability for Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>


### <a name="emergency-call-enablement"></a><span data-ttu-id="e818f-138">緊急通話啟用</span><span class="sxs-lookup"><span data-stu-id="e818f-138">Emergency call enablement</span></span>

<span data-ttu-id="e818f-139">每個通話方案使用者會自動啟用緊急電話，而且必須擁有與其指派的電話號碼相關聯的已註冊緊急位址。</span><span class="sxs-lookup"><span data-stu-id="e818f-139">Each Calling Plan user is automatically enabled for emergency calling and is required to have a registered emergency address associated with their assigned telephone number.</span></span> 

<span data-ttu-id="e818f-140">當位置必須與電話號碼相關聯時，取決於國家/地區：</span><span class="sxs-lookup"><span data-stu-id="e818f-140">When the location must be associated to the telephone number depends on the country/region:</span></span>

- <span data-ttu-id="e818f-141">例如，在美國和加拿大，當指派號碼給使用者時，需要緊急位置。</span><span class="sxs-lookup"><span data-stu-id="e818f-141">In the United States and Canada, for example, an emergency location is required when a number is assigned to a user.</span></span>

- <span data-ttu-id="e818f-142">對於其他國家/地區 ，例如歐洲、中東和非洲 (EMEA) ，當您從 Microsoft 365 或 Office 365 取得電話號碼，或從另一個服務提供者或電信公司移轉電話號碼時，需要緊急位置。</span><span class="sxs-lookup"><span data-stu-id="e818f-142">For other countries--such as in Europe, the Middle East, and Africa (EMEA)--an emergency location is required when you get the phone number from Microsoft 365 or Office 365, or when it's transferred from another service provider or carrier.</span></span>

### <a name="dynamic-emergency-calling"></a><span data-ttu-id="e818f-143">動態緊急電話</span><span class="sxs-lookup"><span data-stu-id="e818f-143">Dynamic emergency calling</span></span>

<span data-ttu-id="e818f-144">Microsoft 通話方案的動態緊急電話提供根據用戶端目前位置設定及路由緊急Teams功能。</span><span class="sxs-lookup"><span data-stu-id="e818f-144">Dynamic emergency calling for Microsoft Calling Plans provides the capability to configure and route emergency calls based on the current location of the Teams client.</span></span> <span data-ttu-id="e818f-145">自動路由至適當的公用安全解答點 (PSAP) 或通知安全服務台人員的能力會視使用者使用Teams國/地區而異。</span><span class="sxs-lookup"><span data-stu-id="e818f-145">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) or to notify security desk personnel varies depending on the country of usage of the Teams user.</span></span>  

<span data-ttu-id="e818f-146">針對通話方案使用者，只有美國支援路由緊急電話的動態位置，如下所示。</span><span class="sxs-lookup"><span data-stu-id="e818f-146">For Calling Plan users, dynamic location for routing emergency calls is only supported in the United States as follows.</span></span> <span data-ttu-id="e818f-147"> (有關動態緊急電話和直接路由的資訊，請參閱 [直接路由的考慮](#considerations-for-direct-routing)。</span><span class="sxs-lookup"><span data-stu-id="e818f-147">(For information about dynamic emergency calling and Direct Routing, see [Considerations for Direct Routing](#considerations-for-direct-routing).</span></span>

- <span data-ttu-id="e818f-148">如果美國Teams方案使用者的 Teams 用戶端動態取得美國國內的緊急位址，該位址會用於緊急路由，而非登入位址，且該通話會自動路由至位址服務區域中的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="e818f-148">If a Teams client for a United States Calling Plan user dynamically acquires an emergency address within the United States, that address is used for emergency routing instead of the registered address, and the call will be automatically routed to the PSAP in the serving area of the address.</span></span>

- <span data-ttu-id="e818f-149">如果Teams美國通話方案使用者的用戶端無法在美國境內動態取得緊急位址，則已註冊的緊急位址會用來協助螢幕和路由通話。</span><span class="sxs-lookup"><span data-stu-id="e818f-149">If a Teams client for a United States Calling Plan user doesn't dynamically acquire an emergency address within the United States, then the registered emergency address is used to help screen and route the call.</span></span> <span data-ttu-id="e818f-150">不過，在將來電者連接到適當的 PSAP 之前，會先篩選電話，判斷是否必須更新位址。</span><span class="sxs-lookup"><span data-stu-id="e818f-150">However, the call will be screened to determine if an updated address is required before connecting the caller to the appropriate PSAP.</span></span>

<span data-ttu-id="e818f-151">在美國，您必須設定屬於指派給網路識別碼之緊急位置的市民位址，並包含 &mdash; 相關聯的地理代碼。</span><span class="sxs-lookup"><span data-stu-id="e818f-151">In the United States, you must configure the civic address that is part of the emergency locations that are assigned to network identifiers&mdash;and include the associated geo codes.</span></span> <span data-ttu-id="e818f-152">詳細資訊，請參閱 [規劃及設定動態緊急電話](configure-dynamic-emergency-calling.md)。</span><span class="sxs-lookup"><span data-stu-id="e818f-152">For more information, see [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>


### <a name="emergency-call-routing"></a><span data-ttu-id="e818f-153">緊急電話路由</span><span class="sxs-lookup"><span data-stu-id="e818f-153">Emergency call routing</span></span>

<span data-ttu-id="e818f-154">當Teams方案使用者撥打緊急號碼時，呼叫路由至 PSAP 的方式取決於下列各項：</span><span class="sxs-lookup"><span data-stu-id="e818f-154">When a Teams Calling Plan user dials an emergency number, how the call is routed to the PSAP depends on the following:</span></span>

- <span data-ttu-id="e818f-155">緊急位址是否由用戶端動態Teams決定。</span><span class="sxs-lookup"><span data-stu-id="e818f-155">Whether the emergency address is dynamically determined by the Teams client.</span></span>

- <span data-ttu-id="e818f-156">緊急位址是否與使用者電話號碼相關聯的登入位址。</span><span class="sxs-lookup"><span data-stu-id="e818f-156">Whether the emergency address is the registered address associated with the user's phone number.</span></span>

- <span data-ttu-id="e818f-157">該國家/地區緊急電話網絡。</span><span class="sxs-lookup"><span data-stu-id="e818f-157">The emergency calling network of that country.</span></span>

  <span data-ttu-id="e818f-158">**在美國：**</span><span class="sxs-lookup"><span data-stu-id="e818f-158">**In the United States:**</span></span>

  - <span data-ttu-id="e818f-159">如果Teams用戶端位於租使用者定義的動態緊急位置，該用戶端的緊急電話會自動路由至該地理位置的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="e818f-159">If a Teams client is located at a tenant-defined dynamic emergency location, emergency calls from that client are automatically routed to the PSAP serving that geographic location.</span></span> 

  - <span data-ttu-id="e818f-160">如果 Teams 用戶端未位於租使用者定義的動態緊急位置，則來自該用戶端的緊急電話會由國家電話中心進行篩選，以決定來電者的位置，然後再將來電轉接至該地理位置的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="e818f-160">If a Teams client is not located at a tenant-defined dynamic emergency location, emergency calls from that client are screened by a national call center to determine the location of the caller before transferring the call to the PSAP serving that geographic location.</span></span>

  - <span data-ttu-id="e818f-161">如果緊急來電者無法將其緊急位置更新至篩選中心，來電會轉接至 PSAP，為來電者的登入位址服務。</span><span class="sxs-lookup"><span data-stu-id="e818f-161">If an emergency caller is unable to update their emergency location to the screening center, the call will be transferred to the PSAP serving the caller's registered address.</span></span>

  <span data-ttu-id="e818f-162">**在加拿大、愛爾蘭** 及英國，緊急電話會先進行篩選，以判斷使用者的目前位置，然後再將電話連接到適當的調度中心。</span><span class="sxs-lookup"><span data-stu-id="e818f-162">**In Canada, Ireland, and the United Kingdom**, emergency calls are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center.</span></span> 

  <span data-ttu-id="e818f-163">**在法國、德國和西班牙**，緊急電話會直接路由至 PSAP，服務與號碼相關聯的緊急位址，無論來電者的位置如何。</span><span class="sxs-lookup"><span data-stu-id="e818f-163">**In France, Germany, and Spain**, emergency calls are routed directly to the PSAP serving the emergency address associated with the number regardless of the location of the caller.</span></span>

  <span data-ttu-id="e818f-164">**在荷蘭，** 無論來電者的位置如何，緊急電話都會直接路由至當地區碼的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="e818f-164">**In the Netherlands**, emergency calls are routed directly to the PSAP for the local area code of the number regardless of the location of the caller.</span></span>

  <span data-ttu-id="e818f-165">**在澳大利亞，** 緊急位址是由電信合作夥伴進行配置和路由。</span><span class="sxs-lookup"><span data-stu-id="e818f-165">**In Australia**, emergency addresses are configured and routed by the carrier partner.</span></span>

  <span data-ttu-id="e818f-166">**在日本，** 不支援緊急電話。</span><span class="sxs-lookup"><span data-stu-id="e818f-166">**In Japan**, emergency calling is not supported.</span></span>


<span data-ttu-id="e818f-167">詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="e818f-167">For more information, see:</span></span>

- [<span data-ttu-id="e818f-168">通話方案</span><span class="sxs-lookup"><span data-stu-id="e818f-168">Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="e818f-169">用於通話方案的各種電話號碼</span><span class="sxs-lookup"><span data-stu-id="e818f-169">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

- [<span data-ttu-id="e818f-170">緊急通話條款及條件</span><span class="sxs-lookup"><span data-stu-id="e818f-170">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-direct-routing"></a><span data-ttu-id="e818f-171">直接路由的考慮</span><span class="sxs-lookup"><span data-stu-id="e818f-171">Considerations for Direct Routing</span></span>

<span data-ttu-id="e818f-172">如果地區沒有通話方案，或您想要保留現有的電信公司，請考慮直接 [路由](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="e818f-172">If Calling Plans are not available in your area or you want to keep your existing carrier, consider [Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="e818f-173">詳細資訊，請參閱設定[直接路由及](direct-routing-configure.md)[管理緊急電話路由策略](manage-emergency-call-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e818f-173">For more information, see [Configure Direct Routing](direct-routing-configure.md) and [Manage emergency call routing policies](manage-emergency-call-routing-policies.md).</span></span>

### <a name="emergency-call-enablement-and-configuration"></a><span data-ttu-id="e818f-174">緊急通話啟用與組</span><span class="sxs-lookup"><span data-stu-id="e818f-174">Emergency call enablement and configuration</span></span>

<span data-ttu-id="e818f-175">您必須使用 Teams 緊急呼叫路由策略 (TeamsEmergencyCallRoutingPolicy) 來定義緊急號碼及其相關聯的路由目的地，以定義直接路由使用者的緊急通話政策。</span><span class="sxs-lookup"><span data-stu-id="e818f-175">You must define emergency calling policies for Direct Routing users by using a Teams emergency call routing policy (TeamsEmergencyCallRoutingPolicy) to define emergency numbers and their associated routing destination.</span></span> <span data-ttu-id="e818f-176"> (請注意，直接路由使用者不支援已註冊的緊急位置。) </span><span class="sxs-lookup"><span data-stu-id="e818f-176">(Note that registered emergency locations are not supported for Direct Routing users.)</span></span>

<span data-ttu-id="e818f-177">您可以將緊急呼叫路由策略指派給 Teams路由使用者帳戶、網路網站或兩者。</span><span class="sxs-lookup"><span data-stu-id="e818f-177">You can assign an emergency call routing policy  to a Teams Direct Routing user account, a network site, or both.</span></span> <span data-ttu-id="e818f-178">當用戶端Teams或變更網路連接時，Teams會執行用戶端所在的網路網站的檢查，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e818f-178">When a Teams client starts or changes a network connection, Teams performs a lookup of the network site where the client is located as follows:</span></span>

- <span data-ttu-id="e818f-179">如果緊急通話路由策略與網站相關聯，則網站策略會用來設定緊急通話。</span><span class="sxs-lookup"><span data-stu-id="e818f-179">If an emergency call routing policy is associated with the site, then the site policy is used to configure emergency calling.</span></span>

- <span data-ttu-id="e818f-180">如果沒有與網站相關聯的緊急呼叫路由策略，或用戶端是在未定義的網站上連接，則與使用者帳戶相關聯的緊急通話路由策略會用來設定緊急通話。</span><span class="sxs-lookup"><span data-stu-id="e818f-180">If there is no emergency call routing policy associated with the site, or if the client is connected at an undefined site, then the emergency call routing policy associated with the user account is used to configure emergency calling.</span></span> 

- <span data-ttu-id="e818f-181">如果Teams用戶端無法取得緊急呼叫路由策略，則使用者不會啟用緊急通話。</span><span class="sxs-lookup"><span data-stu-id="e818f-181">If the Teams client is unable to obtain an emergency call routing policy, then the user is not enabled for emergency calling.</span></span>

### <a name="dynamic-emergency-calling"></a><span data-ttu-id="e818f-182">動態緊急電話</span><span class="sxs-lookup"><span data-stu-id="e818f-182">Dynamic emergency calling</span></span>

<span data-ttu-id="e818f-183">Teams路由使用者的用戶端可以取得動態緊急位址，這個位址可用來根據來電者的位置來動態路由通話。</span><span class="sxs-lookup"><span data-stu-id="e818f-183">Teams clients for Direct Routing users can acquire a dynamic emergency address, which can be used to dynamically route calls based upon the location of the caller.</span></span> <span data-ttu-id="e818f-184">詳細資訊，請參閱 [設定動態緊急電話](configure-dynamic-emergency-calling.md)。</span><span class="sxs-lookup"><span data-stu-id="e818f-184">For more information, see [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

### <a name="emergency-call-routing"></a><span data-ttu-id="e818f-185">緊急電話路由</span><span class="sxs-lookup"><span data-stu-id="e818f-185">Emergency call routing</span></span>

<span data-ttu-id="e818f-186">緊急電話路由策略會參照線上 PSTN 使用方式，其必須擁有適當的直接路由配置，以正確地將緊急電話路由至適當的 PSTN (閘道) 。</span><span class="sxs-lookup"><span data-stu-id="e818f-186">The emergency call routing policy references an online PSTN usage, which must have the appropriate Direct Routing configuration to properly route the emergency calls to the appropriate PSTN gateway(s).</span></span> <span data-ttu-id="e818f-187">特別是，您必須確保緊急撥號字串有 OnlineVoiceRoute。</span><span class="sxs-lookup"><span data-stu-id="e818f-187">In particular, you must ensure that there is an OnlineVoiceRoute for the emergency dial string.</span></span> <span data-ttu-id="e818f-188">詳細資訊，請參閱設定 [直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="e818f-188">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span> 

<span data-ttu-id="e818f-189"> (：Teams用戶端在緊急號碼前面以類似方式將「+」商務用 Skype前面;即 +911。</span><span class="sxs-lookup"><span data-stu-id="e818f-189">(Note: Teams clients prepend the "+" sign in front of emergency numbers in a similar manner that Skype for Business client does; that is, +911.</span></span> <span data-ttu-id="e818f-190">此行為會于未來幾個月內修改，Teams緊急電話不會再在號碼前面傳送「+」;也就是說，911.) </span><span class="sxs-lookup"><span data-stu-id="e818f-190">This behavior will be modified in the coming months so that Teams emergency calls will no longer be sending a "+" preceding the number; that is, 911.)</span></span>

<span data-ttu-id="e818f-191">直接路由使用者動態路由緊急電話的能力會因特定國家/地區內的緊急通話網路而異。</span><span class="sxs-lookup"><span data-stu-id="e818f-191">The ability to dynamically route emergency calls for Direct Routing users varies depending on the emergency calling network within a given country.</span></span> <span data-ttu-id="e818f-192">有兩種可用的解決方案：</span><span class="sxs-lookup"><span data-stu-id="e818f-192">There are two solutions available:</span></span>

- <span data-ttu-id="e818f-193">緊急路由服務提供者僅 (美國) </span><span class="sxs-lookup"><span data-stu-id="e818f-193">Emergency Routing Service Providers (US only)</span></span> 
- <span data-ttu-id="e818f-194">ELIN 閘道應用程式的緊急 (識別) 號碼</span><span class="sxs-lookup"><span data-stu-id="e818f-194">Emergency Location Identification Number (ELIN) gateway applications</span></span>

#### <a name="emergency-routing-service-providers"></a><span data-ttu-id="e818f-195">緊急路由服務提供者</span><span class="sxs-lookup"><span data-stu-id="e818f-195">Emergency Routing Service Providers</span></span>

<span data-ttu-id="e818f-196">在美國，有許多經過認證的緊急路由服務提供者 (ERSP) 根據來電者的位置自動路由緊急電話。</span><span class="sxs-lookup"><span data-stu-id="e818f-196">In the United States, there are numerous certified Emergency Routing Service Providers (ERSPs) that can automatically route emergency calls based upon the location of the caller.</span></span>

- <span data-ttu-id="e818f-197">如果緊急路由服務提供者已整合至直接路由部署，具有動態取得位置的緊急電話會自動路由至服務該位置的公用安全應答點 (PSAP) 點。</span><span class="sxs-lookup"><span data-stu-id="e818f-197">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span>

-  <span data-ttu-id="e818f-198">沒有動態取得位置的緊急電話會先經過篩選，以決定使用者的目前位置，然後再根據更新的位置將通話連接到適當的調度中心。</span><span class="sxs-lookup"><span data-stu-id="e818f-198">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span>

<span data-ttu-id="e818f-199">詳細資訊，請參閱通過 [直接路由認證的會話邊界控制器](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="e818f-199">For more information, see [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>


#### <a name="emergency-location-identification-number-elin-applications"></a><span data-ttu-id="e818f-200">ELIN 應用程式 (緊急) 號碼</span><span class="sxs-lookup"><span data-stu-id="e818f-200">Emergency Location Identification Number (ELIN) applications</span></span>

<span data-ttu-id="e818f-201">會話邊界控制器 (SBC) ELIN 應用程式包含緊急 (識別) 號碼。</span><span class="sxs-lookup"><span data-stu-id="e818f-201">Session Border Controllers (SBCs) can include Emergency Location Identification Number (ELIN) applications.</span></span> <span data-ttu-id="e818f-202">如果 SBC ELIN 應用程式已整合至直接路由部署，您必須在 ELIN 應用程式中設定緊急位址和相關電話號碼，然後將 ELIN 記錄上傳到各自 PSTN 中的緊急通話資料庫。</span><span class="sxs-lookup"><span data-stu-id="e818f-202">If an SBC ELIN application is integrated into a Direct Routing deployment, you must configure the emergency addresses and associated telephone numbers in the ELIN application, and then upload the ELIN records to the emergency calling database in the respective PSTN.</span></span>  <span data-ttu-id="e818f-203">Teams ELIN 識別碼的緊急位置必須與 ELIN 應用程式中的位置相符。</span><span class="sxs-lookup"><span data-stu-id="e818f-203">Teams emergency locations with an ELIN identifier must match those within the ELIN application.</span></span>

<span data-ttu-id="e818f-204">當具有動態取得位置的緊急電話路由至適當的 SBC 時，ELIN 應用程式：</span><span class="sxs-lookup"><span data-stu-id="e818f-204">When an emergency call with a dynamically acquired location is routed to the appropriate SBC, the ELIN application:</span></span>

- <span data-ttu-id="e818f-205">剖析來電者的緊急位置。</span><span class="sxs-lookup"><span data-stu-id="e818f-205">Parses the emergency location of the caller.</span></span>
- <span data-ttu-id="e818f-206">將位置與 ELIN 記錄比對。</span><span class="sxs-lookup"><span data-stu-id="e818f-206">Matches the location to an ELIN record.</span></span>
- <span data-ttu-id="e818f-207">以 ELIN 電話號碼取代緊急來電者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="e818f-207">Substitutes the emergency caller's number with the ELIN phone number.</span></span>
- <span data-ttu-id="e818f-208">將通話路由至服務該位置的 PSAP，然後調度員從上傳的 ELIN 記錄取得位置。</span><span class="sxs-lookup"><span data-stu-id="e818f-208">Routes the call to the PSAP serving that location, and then the dispatchers obtain the location from the uploaded ELIN record.</span></span>

<span data-ttu-id="e818f-209">當呼叫回緊急號碼時，ELIN 應用程式會執行與原始緊急來電者相反的呼叫號碼取代。</span><span class="sxs-lookup"><span data-stu-id="e818f-209">Upon a call back to the emergency number, the ELIN application will do the reverse called number substitution to that of the original emergency caller.</span></span> 

<span data-ttu-id="e818f-210">詳細資訊，請參閱通過 [直接路由認證的會話邊界控制器](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="e818f-210">For more information, see [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>


## <a name="security-desk-notification"></a><span data-ttu-id="e818f-211">安全電話台通知</span><span class="sxs-lookup"><span data-stu-id="e818f-211">Security desk notification</span></span>

<span data-ttu-id="e818f-212">Microsoft 通話方案與直接路由功能電話系統安全電話台通知。</span><span class="sxs-lookup"><span data-stu-id="e818f-212">Security desk notification is available with both Microsoft Calling Plans and Phone System Direct Routing.</span></span>

<span data-ttu-id="e818f-213">您可以使用 Teams 緊急通話策略 (TeamsEmergencyCallingPolicy) 來設定在緊急通話期間應通知哪些人，以及通知方式：僅聊天、在會議中和靜音，或會議中和靜音，但能夠取消靜音。</span><span class="sxs-lookup"><span data-stu-id="e818f-213">You use a Teams emergency calling policy (TeamsEmergencyCallingPolicy) to configure who should be notified during an emergency call and how they are notified: chat only, conferenced in and muted, or conferenced in and muted but with the ability to unmute.</span></span>  <span data-ttu-id="e818f-214">您也可以指定使用者或群組的外部 PSTN 號碼，以撥打並加入緊急通話。</span><span class="sxs-lookup"><span data-stu-id="e818f-214">You can also specify an external PSTN number of a user or group to call and join the emergency call.</span></span> 

<span data-ttu-id="e818f-215">緊急通話政策可以授予Teams使用者帳戶、指派給網路網站，或兩者同時提供。</span><span class="sxs-lookup"><span data-stu-id="e818f-215">An emergency calling policy can be granted to a Teams user account, assigned to a network site, or both.</span></span>  <span data-ttu-id="e818f-216">當Teams用戶端啟動或變更網路Teams，系統會執行用戶端所在的網路網站的檢查：</span><span class="sxs-lookup"><span data-stu-id="e818f-216">When a Teams client starts or changes a network connection, Teams performs a lookup of the network site where the client is located:</span></span>

- <span data-ttu-id="e818f-217">如果緊急通話策略與網路網站相關聯，則網站策略會用來設定安全電話機通知。</span><span class="sxs-lookup"><span data-stu-id="e818f-217">If an emergency calling policy is associated with a network site, then the site policy is used to configure security desk notification.</span></span>

- <span data-ttu-id="e818f-218">如果沒有與網站相關聯的緊急通話政策，或用戶端是在未定義的網站上連接，則與使用者帳戶相關聯的緊急通話策略會用來設定安全性電話機通知。</span><span class="sxs-lookup"><span data-stu-id="e818f-218">If there is no emergency calling policy associated with the site, or if the client is connected at an undefined site, then the emergency calling policy associated with the user account is used to configure security desk notification.</span></span>  

- <span data-ttu-id="e818f-219">如果Teams用戶端無法取得緊急通話政策，則使用者不會啟用安全電話台通知。</span><span class="sxs-lookup"><span data-stu-id="e818f-219">If the Teams client is unable to obtain an emergency calling policy, then the user is not enabled for security desk notification.</span></span>

<span data-ttu-id="e818f-220">緊急通話期間，安全電話台會召開電話會議，而安全電話台使用者的體驗則根據緊急Teams控制。</span><span class="sxs-lookup"><span data-stu-id="e818f-220">During an emergency call, a security desk is conferenced into the call and the experience of the security desk user is controlled based upon the Teams emergency calling policy.</span></span> <span data-ttu-id="e818f-221">每個安全電話台成員會開始進行群組聊天，而緊急來電者的位置會透過重要訊息通知共用。</span><span class="sxs-lookup"><span data-stu-id="e818f-221">A group chat is started with each security desk member, and the location of the emergency caller is shared via an important message notification.</span></span>  <span data-ttu-id="e818f-222">如果會議選項已配置為策略的一部分，則每個安全電話台使用者會另外稱為會議的一部分。</span><span class="sxs-lookup"><span data-stu-id="e818f-222">If a conference option is configured as part of the policy, each security desk user is additionally called as part of the conference.</span></span>

    
## <a name="related-topics"></a><span data-ttu-id="e818f-223">相關主題</span><span class="sxs-lookup"><span data-stu-id="e818f-223">Related topics</span></span>

- [<span data-ttu-id="e818f-224">管理緊急電話原則</span><span class="sxs-lookup"><span data-stu-id="e818f-224">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="e818f-225">管理緊急通話路由策略 </span><span class="sxs-lookup"><span data-stu-id="e818f-225">Manage emergency call routing policies </span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="e818f-226">新增、變更或移除貴組織的緊急位置</span><span class="sxs-lookup"><span data-stu-id="e818f-226">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="e818f-227">指派或變更使用者的緊急位置</span><span class="sxs-lookup"><span data-stu-id="e818f-227">Assign or change an emergency location for your user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="e818f-228">規劃和設定動態緊急電話</span><span class="sxs-lookup"><span data-stu-id="e818f-228">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)
