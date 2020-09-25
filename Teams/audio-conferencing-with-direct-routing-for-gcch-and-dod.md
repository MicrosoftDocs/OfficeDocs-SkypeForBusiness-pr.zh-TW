---
title: 含直接路線、GCCH 和 DoD 的音訊會議
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
description: 系統管理員可以瞭解如何在 GCCH 和 DoD 環境中搭配直接路由使用音訊會議。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 34fcb84ee0e5126188f47a4ccc231c04ffd093b2
ms.sourcegitcommit: 8924cd77923ca321de72edc3fed04425a4b13044
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262490"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="e3974-103">適用於 GCC High 和 DoD 的音訊會議搭配直接路由</span><span class="sxs-lookup"><span data-stu-id="e3974-103">Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="e3974-104">使用適用于 GCC 高和 DoD 之直接路由的音訊會議，可讓參與者透過電話裝置在您的 GCC 高或 DoD 組織中加入團隊會議。</span><span class="sxs-lookup"><span data-stu-id="e3974-104">Audio Conferencing with Direct Routing for GCC High and DoD enables participants to join Teams meetings in your GCC High or DoD organization by using a phone device.</span></span> <span data-ttu-id="e3974-105">會議參與者可能想要在案例中使用電話裝置加入小組會議，例如，當網際網路連線受到限制或使用者在路上且無法存取小組時。</span><span class="sxs-lookup"><span data-stu-id="e3974-105">Meeting participants might prefer to use a phone device to join Teams meetings in scenarios such as when internet connectivity is limited or when users are on the road and don't have access to Teams.</span></span> <span data-ttu-id="e3974-106">參與者可以選擇透過撥入您組織的撥入電話號碼，或將會議撥出到電話裝置，來加入會議。</span><span class="sxs-lookup"><span data-stu-id="e3974-106">Participants can choose to join meetings by either dialing in to a dial-in phone number for your organization or by having the meeting dial out to their phone device.</span></span>

<span data-ttu-id="e3974-107">透過使用具有直接路由的 GCC （適用于 GCC 高和 DoD），貴組織使用自己的號碼做為撥入電話號碼，而所有的會議撥出都是透過直接路由路由傳送給電話裝置。</span><span class="sxs-lookup"><span data-stu-id="e3974-107">With Audio Conferencing with Direct Routing for GCC High and DoD, your organization uses its own numbers as dial-in phone numbers and all meeting dial-outs to phone devices are routed via Direct Routing.</span></span> <span data-ttu-id="e3974-108">若要啟用服務，組織必須設定直接路由，並設定可做為撥入電話號碼的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="e3974-108">To enable the service, organizations need to set up Direct Routing and configure phone numbers that can be used as dial-in phone numbers.</span></span> <span data-ttu-id="e3974-109">使用直接路由的需求與提供給非 GCC 的高和非 DoD 組織（由 Microsoft 提供電話撥入式電話號碼）的音訊會議服務是不一樣的。</span><span class="sxs-lookup"><span data-stu-id="e3974-109">The requirement to use Direct Routing is different from the Audio Conferencing service that's offered to non-GCC High and non-DoD organizations where the dial-in phone numbers are provided by Microsoft.</span></span>

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="e3974-110">使用適用于 GCC 高和 DoD 的直接路由來部署音訊會議</span><span class="sxs-lookup"><span data-stu-id="e3974-110">Deploy Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a><span data-ttu-id="e3974-111">步驟1：使用適用于 GCC 高或 DoD 授權的直接路由取得音訊會議</span><span class="sxs-lookup"><span data-stu-id="e3974-111">Step 1: Get Audio Conferencing with Direct Routing for GCC High or DoD licenses</span></span> 

<span data-ttu-id="e3974-112">若要在 GCC 高或 DoD 中使用音訊會議，貴組織及貴組織中的使用者必須有指派直接傳送授權的音訊會議。</span><span class="sxs-lookup"><span data-stu-id="e3974-112">To use Audio Conferencing in GCC High or DoD, your organization and the users in your organization need to have an Audio Conferencing with Direct Routing license assigned.</span></span> <span data-ttu-id="e3974-113">以下是可使用適用于 GCC 高或 DoD 直接路由的音訊會議所需的授權。</span><span class="sxs-lookup"><span data-stu-id="e3974-113">Here are the licenses you need to enable Audio Conferencing with Direct Routing for GCC High or DoD.</span></span>

- <span data-ttu-id="e3974-114">GCC 高：適用于貴組織的音訊會議-GCC 高租使用者授權，以及音訊會議-適用于您的使用者的 GCC 高授權。</span><span class="sxs-lookup"><span data-stu-id="e3974-114">GCC High: An Audio Conferencing - GCC High Tenant license for your organization and Audio Conferencing - GCC High licenses for your users.</span></span>

- <span data-ttu-id="e3974-115">DoD：貴組織的音訊會議-DoD 租使用者授權，以及適用于您的使用者的音訊會議-DoD 授權。</span><span class="sxs-lookup"><span data-stu-id="e3974-115">DoD: An Audio Conferencing - DoD Tenant license for your organization and Audio Conferencing - DoD licenses for your users.</span></span>

<span data-ttu-id="e3974-116">您必須擁有租使用者授權，且至少需要一個使用者授權，才能啟用服務。</span><span class="sxs-lookup"><span data-stu-id="e3974-116">A tenant license and at least one user license are required to enable the service.</span></span> <span data-ttu-id="e3974-117">您無法啟用只有租使用者授權或只有使用者授權的服務。</span><span class="sxs-lookup"><span data-stu-id="e3974-117">You can't enable the service with only the tenant license or with only user licenses.</span></span> <span data-ttu-id="e3974-118">若要取得您的租使用者與您組織中的使用者服務授權，請與您的帳戶小組聯繫。</span><span class="sxs-lookup"><span data-stu-id="e3974-118">To get service licenses for your tenant and the users in your organization, contact your account team.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3974-119">在設定撥入電話號碼前，不能使用直接傳送的音訊會議來啟用使用者。</span><span class="sxs-lookup"><span data-stu-id="e3974-119">Users can't be enabled for Audio Conferencing with Direct Routing until dial-in phone numbers are set up.</span></span> <span data-ttu-id="e3974-120">我們建議您不要使用適用于 GCC 高或 DoD 授權給使用者的直接路由來指派音訊會議，直到您按照本文所述設定電話撥入式電話號碼。</span><span class="sxs-lookup"><span data-stu-id="e3974-120">We recommend that you not assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to users until you set up dial-in phone numbers as outlined in this article.</span></span>

### <a name="step-2-set-up-direct-routing"></a><span data-ttu-id="e3974-121">步驟2：設定直接路由</span><span class="sxs-lookup"><span data-stu-id="e3974-121">Step 2: Set up Direct Routing</span></span>

<span data-ttu-id="e3974-122">若要設定直接路由，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="e3974-122">To set up Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="e3974-123">規劃直接路由</span><span class="sxs-lookup"><span data-stu-id="e3974-123">Plan Direct Routing</span></span>](direct-routing-plan.md)

- [<span data-ttu-id="e3974-124">設定直接路由</span><span class="sxs-lookup"><span data-stu-id="e3974-124">Configure Direct Routing</span></span>](direct-routing-configure.md)

> [!NOTE]
> <span data-ttu-id="e3974-125">當您設定直接路由時，請記得使用這兩篇文章中所述的 GCC 高或 DoD 特定 Fqdn 和埠。</span><span class="sxs-lookup"><span data-stu-id="e3974-125">When you set up Direct Routing, remember to use the GCC High or DoD-specific FQDNs and ports that are described in these two articles.</span></span>

### <a name="step-3-set-up-dial-in-phone-numbers"></a><span data-ttu-id="e3974-126">步驟3：設定撥入電話號碼</span><span class="sxs-lookup"><span data-stu-id="e3974-126">Step 3: Set up dial-in phone numbers</span></span>

<span data-ttu-id="e3974-127">電話撥入式電話號碼是與您的音訊會議橋接器相關聯的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="e3974-127">Dial-in phone numbers are the phone numbers that are associated to your Audio Conferencing bridge.</span></span> <span data-ttu-id="e3974-128">參與者會使用這些數位來加入組織中使用者排程的會議。</span><span class="sxs-lookup"><span data-stu-id="e3974-128">These numbers are used by participants to join meetings scheduled by users in your organization.</span></span> <span data-ttu-id="e3974-129">在您的組織中，以及在 [尋找當地電話號碼] 頁面上排程會議的使用者，這些號碼也會包含在會議邀請中。</span><span class="sxs-lookup"><span data-stu-id="e3974-129">These numbers are also included in the meeting invites of the users who schedule meetings in your organization and on the "Find a local number" page.</span></span>

#### <a name="define-service-phone-numbers-in-your-tenant"></a><span data-ttu-id="e3974-130">在您的租使用者中定義服務電話號碼</span><span class="sxs-lookup"><span data-stu-id="e3974-130">Define service phone numbers in your tenant</span></span>

<span data-ttu-id="e3974-131">您可以使用 csHybridTelephoneNumber PowerShell Cmdlet 來定義您租使用者中的服務電話號碼，以透過直接路由將呼叫路由至音訊會議服務。</span><span class="sxs-lookup"><span data-stu-id="e3974-131">You can use the New-csHybridTelephoneNumber PowerShell cmdlet to define service phone numbers in your tenant that can be used to route calls to the Audio Conferencing service via Direct Routing.</span></span> 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

<span data-ttu-id="e3974-132">例如：</span><span class="sxs-lookup"><span data-stu-id="e3974-132">For example:</span></span>
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="e3974-133">將服務電話號碼指派給貴組織的音訊會議橋</span><span class="sxs-lookup"><span data-stu-id="e3974-133">Assign the service phone numbers to the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="e3974-134">您可以使用 csOnlineDialInConferencingServiceNumber PowerShell Cmdlet，將服務電話號碼指派給您組織的音訊會議橋。</span><span class="sxs-lookup"><span data-stu-id="e3974-134">You can assign service phone numbers to the Audio Conferencing bridge of your organization by using the Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet.</span></span>

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

<span data-ttu-id="e3974-135">您可以使用 CsOnlineDialInConferencingBridge 來查看音訊會議橋接器的 ID。</span><span class="sxs-lookup"><span data-stu-id="e3974-135">You can see the ID of your Audio Conferencing Bridge using Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="e3974-136">例如：</span><span class="sxs-lookup"><span data-stu-id="e3974-136">For example:</span></span>

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a><span data-ttu-id="e3974-137">步驟4：定義全域語音路由策略以啟用從會議傳送傳出通話的功能</span><span class="sxs-lookup"><span data-stu-id="e3974-137">Step 4: Define a global voice routing policy to enable the routing of outbound calls from meetings</span></span>

<span data-ttu-id="e3974-138">由貴組織中的使用者組織的會議對 PSTN 所做的撥出通話路由，是由貴組織的全域語音路由策略所定義。</span><span class="sxs-lookup"><span data-stu-id="e3974-138">The routing of outbound calls that are made to the PSTN from meetings organized by users in your organization is defined by the global voice routing policy of your organization.</span></span> <span data-ttu-id="e3974-139">如果您的組織已定義全域語音路由策略，請確認 [全域語音路由原則] 允許從組織中的使用者所組織的會議開始，對預期啟動的 PSTN 進行撥出通話。</span><span class="sxs-lookup"><span data-stu-id="e3974-139">If your organization has a global voice routing policy defined, please verify that the global voice routing policy allows the outbound calls to the PSTN that are expected to be initiated from meetings organized by users in your organization.</span></span> <span data-ttu-id="e3974-140">如果您的組織沒有定義全域語音路由策略，您將需要定義一個，才能從組織中的使用者組織的會議中，將撥出電話路由至 PSTN。</span><span class="sxs-lookup"><span data-stu-id="e3974-140">If your organization doesn’t have a global voice routing policy defined, you will need to define one to enable the routing of outbound calls to the PSTN from meetings organized by users in your organization.</span></span> <span data-ttu-id="e3974-141">請注意，貴組織的全域語音路由策略也適用于您組織中的使用者對 PSTN 所做的一對一通話。</span><span class="sxs-lookup"><span data-stu-id="e3974-141">Please note that the global voice routing policy of your organization also applies to one-to-one calls made to the PSTN by users in your organization.</span></span> <span data-ttu-id="e3974-142">如果針對您組織中的使用者啟用對 PSTN 的一對一呼叫，請確定全域語音路由策略符合您組織的兩種通話類型的需求。</span><span class="sxs-lookup"><span data-stu-id="e3974-142">If one-to-one calls to the PSTN are enabled for users in your organization, make sure that the global voice routing policy meets the needs of your organization for both types of calls.</span></span> 

> [!NOTE]
> <span data-ttu-id="e3974-143">Microsoft 365 政府社區雲端 (GCC) 高或 DoD 部署中，不提供以位置為基礎的路由。</span><span class="sxs-lookup"><span data-stu-id="e3974-143">Location-Based Routing isn't available in Microsoft 365 Government Community Cloud (GCC) High or DoD deployments.</span></span> <span data-ttu-id="e3974-144">啟用音訊會議時，請確認不在 GCC 或 DoD 環境中的音訊會議使用者已啟用位置路由。</span><span class="sxs-lookup"><span data-stu-id="e3974-144">When enabling Audio Conferencing, please verify that no Audio Conferencing users in the GCC High or the DoD environments are enabled for Location-Based Routing.</span></span>

#### <a name="defining-a-global-voice-routing-policy"></a><span data-ttu-id="e3974-145">定義全域語音路由策略</span><span class="sxs-lookup"><span data-stu-id="e3974-145">Defining a global voice routing policy</span></span>

<span data-ttu-id="e3974-146">您可以透過定義 PSTN 使用量、語音路線、語音路由策略，以及將新的語音路由策略指派為貴組織的全域語音路由策略，來定義全域語音路由策略。</span><span class="sxs-lookup"><span data-stu-id="e3974-146">A global voice routing policy can be defined by defining a PSTN usage, a voice route, a voice routing policy, and assigning the new voice routing policy as the global voice routing policy of your organization.</span></span>

<span data-ttu-id="e3974-147">下列步驟說明如何為組織定義新的全域語音路由策略（無人）。</span><span class="sxs-lookup"><span data-stu-id="e3974-147">The following steps describe how to define a new global voice routing policy for an organization without one.</span></span> <span data-ttu-id="e3974-148">如果您的組織已定義 [語音路由策略]，請確認下列設定沒有與貴組織的現有語音路由策略發生衝突。</span><span class="sxs-lookup"><span data-stu-id="e3974-148">If your organization already has voice routing policies defined, verify that the following configuration doesn’t conflict with the existing voice routing policies of your organization.</span></span>

<span data-ttu-id="e3974-149">若要在商務用 Skype Online 的遠端 PowerShell 會話中建立新的 PSTN 使用量，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="e3974-149">To create a new PSTN usage in a remote PowerShell session in Skype for Business Online, use the following command:</span></span>

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

<span data-ttu-id="e3974-150">如需其他資訊，請參閱 [設定 CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage)。</span><span class="sxs-lookup"><span data-stu-id="e3974-150">For additional information, see [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage).</span></span>

<span data-ttu-id="e3974-151">若要建立新的語音路線，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="e3974-151">To create a new voice route, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

<span data-ttu-id="e3974-152">為您的組織定義新的語音路線時，請指定直接路由設定期間，為您的組織定義的一或多個 PSTN 線上 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="e3974-152">When defining a new voice route for your organization, please specify one or multiple of the PSTN online PSTN gateways that have been defined for your organization during the configuration of Direct Routing.</span></span> 

<span data-ttu-id="e3974-153">數位模式指定哪些通話會透過指定的閘道清單來傳送，這些呼叫是依據通話的目的地電話號碼。</span><span class="sxs-lookup"><span data-stu-id="e3974-153">The number pattern specifies which calls will be routed through the specified list of gateways based on the destination phone number of the call.</span></span> <span data-ttu-id="e3974-154">在上述範例中，對世界上的任何目的地的呼叫都會與語音路線相符。</span><span class="sxs-lookup"><span data-stu-id="e3974-154">In the example above, calls to any destinations in the world will match the voice route.</span></span> <span data-ttu-id="e3974-155">如果您想要限制可從組織中的使用者的會議撥打電話的電話號碼，您可以變更 [數位] 模式，讓語音路線只符合所允許的目的地數位模式。</span><span class="sxs-lookup"><span data-stu-id="e3974-155">If you would like to restrict the phone numbers that can be dialed from the meetings of users in your organization, you can change the number pattern to have the voice route match only the number patterns of the destinations allowed.</span></span> <span data-ttu-id="e3974-156">請注意，如果沒有符合指定通話目的地電話號碼之數位模式的語音路由，該通話就不會傳送。</span><span class="sxs-lookup"><span data-stu-id="e3974-156">Please note that if there are no voice routes that match the number pattern of the destination phone number of a given call, the call will not be routed.</span></span>

<span data-ttu-id="e3974-157">如需其他資訊，請參閱 [新 CsOnlineVoiceRoute](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute)。</span><span class="sxs-lookup"><span data-stu-id="e3974-157">For additional information, see [New-CsOnlineVoiceRoute](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute).</span></span>

<span data-ttu-id="e3974-158">若要建立新的語音路由策略，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="e3974-158">To create a new voice routing policy, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

<span data-ttu-id="e3974-159">如果在 [語音路由原則] 中定義了多個 PSTN 用法，就會按照定義的順序來評估它們。</span><span class="sxs-lookup"><span data-stu-id="e3974-159">If multiple PSTN usages are being defined in the voice routing policy, they will be evaluated in the order in which they are defined.</span></span> <span data-ttu-id="e3974-160">根據與 PSTN 使用相關的語音路由的數位模式，建議 PSTN 使用的順序是從最具體到更一般的順序來定義。</span><span class="sxs-lookup"><span data-stu-id="e3974-160">It is recommended that the PSTN usages are defined in the order of the most specific to the more generic in terms of the number patterns of the voice routes associated with the PSTN usages.</span></span> <span data-ttu-id="e3974-161">例如，如果 PSTN 使用量已定義為將呼叫路由至美國，而另一個 PSTN 使用量已定義為將呼叫路由至世界上的任何其他位置，則撥打至美國的 PSTN 使用量應列在全球的語音路由原則中，以將呼叫路由至世界上的任何其他位置。</span><span class="sxs-lookup"><span data-stu-id="e3974-161">For example, if a PSTN usage was defined to route calls to the United States, and another PSTN usage was defined to route calls to any other location in the world, the PSTN usage for calls to the United States should be listed in the voice routing policy ahead of the PSTN usage to route calls to any other location in the world.</span></span>

<span data-ttu-id="e3974-162">如需其他資訊，請參閱 [新 CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="e3974-162">For additional information, see [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="e3974-163">若要將新的語音路由指派給貴組織的全域語音路由策略，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="e3974-163">To assign the new voice route to the global voice routing policy of your organization, use the following command:</span></span>

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

<span data-ttu-id="e3974-164">如需其他資訊，請參閱 [授與 CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="e3974-164">For additional information, see [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="e3974-165">在已定義全域語音路由策略之後，您組織中的使用者所做的任何出站通話，都將會針對與全域語音路由策略的 PSTN 使用相關的語音路由進行評估。</span><span class="sxs-lookup"><span data-stu-id="e3974-165">Once the global voice routing policy has been defined, any outbound calls made from meetings organized by users in your organization will be evaluated against the voice routes associated to the PSTN usages of the global voice routing policy.</span></span> <span data-ttu-id="e3974-166">[撥出電話] 會根據與撥打的電話號碼之數位模式相符的第一個語音路線來傳送。</span><span class="sxs-lookup"><span data-stu-id="e3974-166">The outbound calls will be routed according to the first voice route that matches the number pattern of the dialed phone number.</span></span>

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a><span data-ttu-id="e3974-167">步驟5：使用適用于 GCC 的直接路由或 DoD 授權向使用者指派音訊會議</span><span class="sxs-lookup"><span data-stu-id="e3974-167">Step 5: Assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your users</span></span>

<span data-ttu-id="e3974-168">若要為您的使用者指派可直接傳送給 GCC 高或 DoD 授權的音訊會議，請參閱 [指派授權給使用者](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="e3974-168">To assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your user, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a><span data-ttu-id="e3974-169">步驟6： (選用) 在團隊中查看音訊會議號碼清單</span><span class="sxs-lookup"><span data-stu-id="e3974-169">Step 6: (Optional) See a list of Audio Conferencing numbers in Teams</span></span>

<span data-ttu-id="e3974-170">若要查看貴組織的音訊會議號碼清單，請移至 [在 Microsoft 團隊中查看音訊會議號碼清單](see-a-list-of-audio-conferencing-numbers-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="e3974-170">To see the list of Audio Conferencing numbers of your organization, go to [See a list of Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a><span data-ttu-id="e3974-171">步驟7： (選用) 設定您組織之音訊會議撥入號碼的自動助理語言</span><span class="sxs-lookup"><span data-stu-id="e3974-171">Step 7: (Optional) Set auto attendant languages for the Audio Conferencing dial-in numbers of you organization</span></span>

<span data-ttu-id="e3974-172">若要變更貴組織之音訊會議撥入號碼的語言，請參閱 [在 Microsoft 團隊中設定音訊會議的自動助理語言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="e3974-172">To change the languages of the Audio Conferencing dial-in numbers of your organization, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="e3974-173">步驟8： (選用) 變更貴組織的音訊會議橋接設定</span><span class="sxs-lookup"><span data-stu-id="e3974-173">Step 8: (Optional) Change the settings of the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="e3974-174">若要變更貴組織的音訊會議橋設定，請參閱 [變更音訊會議橋接器的設定](change-the-settings-for-an-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="e3974-174">To change the settings of the Audio Conferencing bridge of your organization, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a><span data-ttu-id="e3974-175">步驟9： (選用) 設定您組織中的使用者在會議邀請中所包含的電話號碼</span><span class="sxs-lookup"><span data-stu-id="e3974-175">Step 9: (Optional) Set the phone numbers included in the meeting invites of the users in your organization</span></span>

<span data-ttu-id="e3974-176">若要變更您的組織在會議邀請中所包含的一組電話號碼，請參閱 [在 Microsoft 團隊中設定邀請中包含的電話號碼](set-the-phone-numbers-included-on-invites-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="e3974-176">To change the set of phone numbers that are included in the meeting invites of the users is your organization, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="e3974-177">在適用于 GCC 高和 DoD 的直接佈線中，音訊會議不支援音訊會議功能</span><span class="sxs-lookup"><span data-stu-id="e3974-177">Audio Conferencing capabilities not supported in Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="e3974-178">下列是在使用 GCC 高和 DoD 直接路由的音訊會議中不支援的音訊會議功能：</span><span class="sxs-lookup"><span data-stu-id="e3974-178">The following are Audio Conferencing capabilities that are not supported in Audio Conferencing with Direct Routing for GCC High and DoD:</span></span>

- <span data-ttu-id="e3974-179">使用名稱錄製進入及結束通知。</span><span class="sxs-lookup"><span data-stu-id="e3974-179">Entry and exit notifications using name recording.</span></span> <span data-ttu-id="e3974-180">對於有直接傳送的音訊會議，進入和結束通知會在會議中以鈴聲的方式播放。</span><span class="sxs-lookup"><span data-stu-id="e3974-180">For Audio Conferencing with Direct Routing, entry and exit notifications are played in the meeting as tones.</span></span>

- <span data-ttu-id="e3974-181">音訊會議的出站通話限制原則。</span><span class="sxs-lookup"><span data-stu-id="e3974-181">Outbound calling restriction policies for Audio Conferencing.</span></span> <span data-ttu-id="e3974-182">限制輸出呼叫的使用者層級控制措施不適用於透過直接路由路由的會議撥出通話。</span><span class="sxs-lookup"><span data-stu-id="e3974-182">User-level controls to restrict outbound calls aren't applicable to meeting dial-out calls routed via Direct Routing.</span></span>

- <span data-ttu-id="e3974-183">停用會議特定召集人的免付費電話號碼使用量。</span><span class="sxs-lookup"><span data-stu-id="e3974-183">Disable the usage of toll-free numbers for the meetings specific organizer.</span></span> <span data-ttu-id="e3974-184">限制使用免付費電話號碼以加入組織會議的使用者層級控制項，不適用於透過直接佈線進行路由的通話。</span><span class="sxs-lookup"><span data-stu-id="e3974-184">User-level controls to restrict the usage of toll-free numbers to join the meetings of your organization aren't applicable to calls routed via Direct Routing.</span></span>

- <span data-ttu-id="e3974-185">當使用者的設定變更時，傳送通知電子郵件給使用者。</span><span class="sxs-lookup"><span data-stu-id="e3974-185">Sending notification emails to users when their settings change.</span></span> <span data-ttu-id="e3974-186">使用適用于 GCC 高和 DoD 之直接路由的音訊會議，不支援音訊會議通知電子郵件。</span><span class="sxs-lookup"><span data-stu-id="e3974-186">Audio Conferencing notification emails aren't supported for Audio Conferencing with Direct Routing for GCC High and DoD.</span></span>
