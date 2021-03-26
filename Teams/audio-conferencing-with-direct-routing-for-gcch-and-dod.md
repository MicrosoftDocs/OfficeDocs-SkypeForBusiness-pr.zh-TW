---
title: 使用直接路由、GCCH 和 DoD 的音訊會議
author: cichur
ms.author: v-cichur
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
description: 系統管理員可以瞭解如何在 GCCH 和 DoD 環境中使用音訊會議與直接路由。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 577a9fe106cb5dae23049404b54433288e350b78
ms.sourcegitcommit: bd7847de9d1402476f8faaeae2ff97ec60d86a1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2021
ms.locfileid: "51262618"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="bfa6d-103">適用於 GCC High 和 DoD 的音訊會議搭配直接路由</span><span class="sxs-lookup"><span data-stu-id="bfa6d-103">Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="bfa6d-104">具有 GCC High 和 DoD 直接路由的音訊會議可讓參與者使用電話裝置加入 GCC High 或 DoD 組織中 Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-104">Audio Conferencing with Direct Routing for GCC High and DoD enables participants to join Teams meetings in your GCC High or DoD organization by using a phone device.</span></span> <span data-ttu-id="bfa6d-105">會議參與者可能偏好使用電話裝置加入 Teams 會議，例如網際網路連接受限或使用者在路上且無法存取 Teams。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-105">Meeting participants might prefer to use a phone device to join Teams meetings in scenarios such as when internet connectivity is limited or when users are on the road and don't have access to Teams.</span></span> <span data-ttu-id="bfa6d-106">參與者可以加入宣告會議，撥入貴組織的撥入電話號碼，或讓會議撥出到其電話裝置。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-106">Participants can choose to join meetings by either dialing in to a dial-in phone number for your organization or by having the meeting dial out to their phone device.</span></span>

<span data-ttu-id="bfa6d-107">使用具有 GCC High 和 DoD 直接路由的音訊會議，貴組織會使用自己的號碼做為撥入電話號碼，而所有電話裝置的會議撥出都透過直接路由路由。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-107">With Audio Conferencing with Direct Routing for GCC High and DoD, your organization uses its own numbers as dial-in phone numbers and all meeting dial-outs to phone devices are routed via Direct Routing.</span></span> <span data-ttu-id="bfa6d-108">若要啟用服務，組織必須設定直接路由，並設定可做為撥入電話號碼的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-108">To enable the service, organizations need to set up Direct Routing and configure phone numbers that can be used as dial-in phone numbers.</span></span> <span data-ttu-id="bfa6d-109">使用直接路由的需求與 Microsoft 提供撥入電話號碼的非 GCC High 和非 DoD 組織所提供的音訊會議服務不同。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-109">The requirement to use Direct Routing is different from the Audio Conferencing service that's offered to non-GCC High and non-DoD organizations where the dial-in phone numbers are provided by Microsoft.</span></span>

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="bfa6d-110">使用 GCC High 和 DoD 的直接路由部署音訊會議</span><span class="sxs-lookup"><span data-stu-id="bfa6d-110">Deploy Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a><span data-ttu-id="bfa6d-111">步驟 1：使用 GCC High 或 DoD 授權的直接路由取得音訊會議</span><span class="sxs-lookup"><span data-stu-id="bfa6d-111">Step 1: Get Audio Conferencing with Direct Routing for GCC High or DoD licenses</span></span> 

<span data-ttu-id="bfa6d-112">若要在 GCC High 或 DoD 中使用音訊會議，您的組織和貴組織的使用者必須指派具有直接路由授權的音訊會議。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-112">To use Audio Conferencing in GCC High or DoD, your organization and the users in your organization need to have an Audio Conferencing with Direct Routing license assigned.</span></span> <span data-ttu-id="bfa6d-113">以下是使用 GCC High 或 DoD 直接路由啟用音訊會議所需的授權。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-113">Here are the licenses you need to enable Audio Conferencing with Direct Routing for GCC High or DoD.</span></span>

- <span data-ttu-id="bfa6d-114">GCC High：音訊會議 - 貴組織的 GCC 高租使用者授權和音訊會議 - 適用于使用者的 GCC 高授權。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-114">GCC High: An Audio Conferencing - GCC High Tenant license for your organization and Audio Conferencing - GCC High licenses for your users.</span></span>

- <span data-ttu-id="bfa6d-115">DoD：音訊會議 - 貴組織的 DoD 租使用者授權和音訊會議 - 使用者用 DoD 授權。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-115">DoD: An Audio Conferencing - DoD Tenant license for your organization and Audio Conferencing - DoD licenses for your users.</span></span>

<span data-ttu-id="bfa6d-116">啟用服務需要租使用者授權和至少一個使用者授權。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-116">A tenant license and at least one user license are required to enable the service.</span></span> <span data-ttu-id="bfa6d-117">您無法僅使用租使用者授權或僅以使用者授權啟用服務。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-117">You can't enable the service with only the tenant license or with only user licenses.</span></span> <span data-ttu-id="bfa6d-118">若要取得租使用者和貴組織使用者的服務授權，請聯絡您的帳戶小組。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-118">To get service licenses for your tenant and the users in your organization, contact your account team.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bfa6d-119">在設定撥入電話號碼之前，使用者無法啟用使用直接路由的音訊會議。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-119">Users can't be enabled for Audio Conferencing with Direct Routing until dial-in phone numbers are set up.</span></span> <span data-ttu-id="bfa6d-120">我們建議您在設定本文所述的撥入電話號碼之前，不要將具有 GCC High 或 DoD 授權的音訊會議指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-120">We recommend that you do not assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to users until you set up dial-in phone numbers as outlined in this article.</span></span>  <span data-ttu-id="bfa6d-121">若未遵循此指引，可能會導致 Teams 用戶端中的撥號鍵台完全遺失。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-121">Failure to follow this guidance may cause the dial pad to be completely missing in the Teams client.</span></span>

### <a name="step-2-set-up-direct-routing"></a><span data-ttu-id="bfa6d-122">步驟 2：設定直接路由</span><span class="sxs-lookup"><span data-stu-id="bfa6d-122">Step 2: Set up Direct Routing</span></span>

<span data-ttu-id="bfa6d-123">若要設定直接路由，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="bfa6d-123">To set up Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="bfa6d-124">規劃直接路由</span><span class="sxs-lookup"><span data-stu-id="bfa6d-124">Plan Direct Routing</span></span>](direct-routing-plan.md)

- [<span data-ttu-id="bfa6d-125">設定直接路由</span><span class="sxs-lookup"><span data-stu-id="bfa6d-125">Configure Direct Routing</span></span>](direct-routing-configure.md)

> [!NOTE]
> <span data-ttu-id="bfa6d-126">設定直接路由時，請記得使用這兩篇文章所述的 GCC High 或 DoD 私人 FQDN 和埠。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-126">When you set up Direct Routing, remember to use the GCC High or DoD-specific FQDNs and ports that are described in these two articles.</span></span>

### <a name="step-3-set-up-dial-in-phone-numbers"></a><span data-ttu-id="bfa6d-127">步驟 3：設定撥入電話號碼</span><span class="sxs-lookup"><span data-stu-id="bfa6d-127">Step 3: Set up dial-in phone numbers</span></span>

<span data-ttu-id="bfa6d-128">撥入電話號碼是與音訊會議橋接器相關聯的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-128">Dial-in phone numbers are the phone numbers that are associated to your Audio Conferencing bridge.</span></span> <span data-ttu-id="bfa6d-129">參與者會使用這些號碼加入貴組織中使用者排程的會議。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-129">These numbers are used by participants to join meetings scheduled by users in your organization.</span></span> <span data-ttu-id="bfa6d-130">這些號碼也會包含在組織中排程會議的使用者的會議邀請中，以及 「尋找當地號碼」頁面上。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-130">These numbers are also included in the meeting invites of the users who schedule meetings in your organization and on the "Find a local number" page.</span></span>

#### <a name="define-service-phone-numbers-in-your-tenant"></a><span data-ttu-id="bfa6d-131">在租使用者中定義服務電話號碼</span><span class="sxs-lookup"><span data-stu-id="bfa6d-131">Define service phone numbers in your tenant</span></span>

<span data-ttu-id="bfa6d-132">您可以使用 New-csHybridTelephoneNumber PowerShell Cmdlet 定義租使用者中的服務電話號碼，以透過直接路由將通話路由至音訊會議服務。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-132">You can use the New-csHybridTelephoneNumber PowerShell cmdlet to define service phone numbers in your tenant that can be used to route calls to the Audio Conferencing service via Direct Routing.</span></span> 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

<span data-ttu-id="bfa6d-133">例如：</span><span class="sxs-lookup"><span data-stu-id="bfa6d-133">For example:</span></span>
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="bfa6d-134">將服務電話號碼指派給貴組織的音訊會議橋接器</span><span class="sxs-lookup"><span data-stu-id="bfa6d-134">Assign the service phone numbers to the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="bfa6d-135">您可以使用 Register-csOnlineDialInConferencingServiceNumber PowerShell Cmdlet，將服務電話號碼指派給貴組織的音訊會議橋接器。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-135">You can assign service phone numbers to the Audio Conferencing bridge of your organization by using the Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet.</span></span>

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

<span data-ttu-id="bfa6d-136">您可以使用 Get-CsOnlineDialInConferencing Bridge 查看音訊會議橋接器的識別碼。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-136">You can see the ID of your Audio Conferencing Bridge using Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="bfa6d-137">例如：</span><span class="sxs-lookup"><span data-stu-id="bfa6d-137">For example:</span></span>

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a><span data-ttu-id="bfa6d-138">步驟 4：定義全域語音路由策略，以啟用會議外接通話的路由</span><span class="sxs-lookup"><span data-stu-id="bfa6d-138">Step 4: Define a global voice routing policy to enable the routing of outbound calls from meetings</span></span>

<span data-ttu-id="bfa6d-139">從貴組織中使用者組織的會議撥打到 PSTN 的外發通話路由，是由貴組織的全域語音路由策略所定義。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-139">The routing of outbound calls that are made to the PSTN from meetings organized by users in your organization is defined by the global voice routing policy of your organization.</span></span> <span data-ttu-id="bfa6d-140">如果貴組織已定義全域語音路由策略，請確認全域語音路由策略允許從貴組織中使用者組織的會議發起的 PSTN 外接通話。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-140">If your organization has a global voice routing policy defined, please verify that the global voice routing policy allows the outbound calls to the PSTN that are expected to be initiated from meetings organized by users in your organization.</span></span> <span data-ttu-id="bfa6d-141">如果貴組織未定義全域語音路由策略，您必須定義一個策略，才能從貴組織中使用者組織的會議，將外線通話路由至 PSTN。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-141">If your organization doesn’t have a global voice routing policy defined, you will need to define one to enable the routing of outbound calls to the PSTN from meetings organized by users in your organization.</span></span> <span data-ttu-id="bfa6d-142">請注意，貴組織的全域語音路由原則也適用于貴組織中使用者對 PSTN 撥打的一對一通話。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-142">Please note that the global voice routing policy of your organization also applies to one-to-one calls made to the PSTN by users in your organization.</span></span> <span data-ttu-id="bfa6d-143">如果貴組織的使用者已啟用一對一的 PSTN 通話，請確定全域語音路由策略符合貴組織在這兩種類型的通話需求。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-143">If one-to-one calls to the PSTN are enabled for users in your organization, make sure that the global voice routing policy meets the needs of your organization for both types of calls.</span></span> 

> [!NOTE]
> <span data-ttu-id="bfa6d-144">Location-Based在 Microsoft 365 政府社群雲端中無法 (GCC) 高或 DoD 部署。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-144">Location-Based Routing isn't available in Microsoft 365 Government Community Cloud (GCC) High or DoD deployments.</span></span> <span data-ttu-id="bfa6d-145">啟用音訊會議時，請確認 GCC High 或 DoD 環境中未啟用音訊會議使用者Location-Based路由。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-145">When enabling Audio Conferencing, please verify that no Audio Conferencing users in the GCC High or the DoD environments are enabled for Location-Based Routing.</span></span>

#### <a name="defining-a-global-voice-routing-policy"></a><span data-ttu-id="bfa6d-146">定義全域語音路由策略</span><span class="sxs-lookup"><span data-stu-id="bfa6d-146">Defining a global voice routing policy</span></span>

<span data-ttu-id="bfa6d-147">您可以定義 PSTN 使用方式、語音路由、語音路由策略，並將新的語音路由策略指派為貴組織的全域語音路由策略，以定義全域語音路由策略。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-147">A global voice routing policy can be defined by defining a PSTN usage, a voice route, a voice routing policy, and assigning the new voice routing policy as the global voice routing policy of your organization.</span></span>

<span data-ttu-id="bfa6d-148">下列步驟說明如何為沒有全域語音路由的組織定義新的全域語音路由策略。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-148">The following steps describe how to define a new global voice routing policy for an organization without one.</span></span> <span data-ttu-id="bfa6d-149">如果貴組織已定義語音路由策略，請確認下列組態與貴組織現有的語音路由策略沒有衝突。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-149">If your organization already has voice routing policies defined, verify that the following configuration doesn’t conflict with the existing voice routing policies of your organization.</span></span>

<span data-ttu-id="bfa6d-150">若要在商務用 Skype Online 的遠端 PowerShell 會話中建立新的 PSTN 使用方式，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="bfa6d-150">To create a new PSTN usage in a remote PowerShell session in Skype for Business Online, use the following command:</span></span>

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

<span data-ttu-id="bfa6d-151">有關其他資訊，請參閱 [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage)。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-151">For additional information, see [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage).</span></span>

<span data-ttu-id="bfa6d-152">若要建立新的語音路由，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="bfa6d-152">To create a new voice route, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

<span data-ttu-id="bfa6d-153">定義貴組織的新語音路由時，請指定在直接路由組態期間為貴組織定義的一或多個 PSTN 線上 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-153">When defining a new voice route for your organization, please specify one or multiple of the PSTN online PSTN gateways that have been defined for your organization during the configuration of Direct Routing.</span></span> 

<span data-ttu-id="bfa6d-154">號碼模式會根據通話的目的地電話號碼，指定哪些通話會透過指定的閘道清單路由。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-154">The number pattern specifies which calls will be routed through the specified list of gateways based on the destination phone number of the call.</span></span> <span data-ttu-id="bfa6d-155">在上例中，全球任何目的地的通話都會符合語音路由。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-155">In the example above, calls to any destinations in the world will match the voice route.</span></span> <span data-ttu-id="bfa6d-156">如果您想要限制可以從貴組織使用者會議撥打的電話號碼，您可以變更號碼模式，讓語音路由只符合目的地的號碼模式。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-156">If you would like to restrict the phone numbers that can be dialed from the meetings of users in your organization, you can change the number pattern to have the voice route match only the number patterns of the destinations allowed.</span></span> <span data-ttu-id="bfa6d-157">請注意，如果沒有任何語音路由符合所撥打之通話目的地電話號碼的號碼模式，將不會路由通話。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-157">Please note that if there are no voice routes that match the number pattern of the destination phone number of a given call, the call will not be routed.</span></span>

<span data-ttu-id="bfa6d-158">有關其他資訊，請參閱 [New-CsOnlineVoiceRoute](/powershell/module/skype/new-csonlinevoiceroute)。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-158">For additional information, see [New-CsOnlineVoiceRoute](/powershell/module/skype/new-csonlinevoiceroute).</span></span>

<span data-ttu-id="bfa6d-159">若要建立新的語音路由策略，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="bfa6d-159">To create a new voice routing policy, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

<span data-ttu-id="bfa6d-160">如果在語音路由策略中定義多個 PSTN 使用方式，將會按照定義的順序進行評估。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-160">If multiple PSTN usages are being defined in the voice routing policy, they will be evaluated in the order in which they are defined.</span></span> <span data-ttu-id="bfa6d-161">建議根據與 PSTN 使用狀況相關聯的語音路由數模式，以較一般之最特定的順序定義 PSTN 使用量。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-161">It is recommended that the PSTN usages are defined in the order of the most specific to the more generic in terms of the number patterns of the voice routes associated with the PSTN usages.</span></span> <span data-ttu-id="bfa6d-162">例如，如果 PSTN 使用量定義為將通話路由到美國，而另一個 PSTN 使用量已定義為將通話路由到全球任何其他位置，則 PSTN 通話到美國的 PSTN 使用量應列在 PSTN 使用量之前，先于 PSTN 使用方式將通話路由到全球任何其他位置。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-162">For example, if a PSTN usage was defined to route calls to the United States, and another PSTN usage was defined to route calls to any other location in the world, the PSTN usage for calls to the United States should be listed in the voice routing policy ahead of the PSTN usage to route calls to any other location in the world.</span></span>

<span data-ttu-id="bfa6d-163">有關其他資訊，請參閱 [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-163">For additional information, see [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="bfa6d-164">若要將新的語音路由指派給貴組織的全域語音路由策略，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="bfa6d-164">To assign the new voice route to the global voice routing policy of your organization, use the following command:</span></span>

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

<span data-ttu-id="bfa6d-165">有關其他資訊，請參閱 [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-165">For additional information, see [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="bfa6d-166">定義全域語音路由策略之後，貴組織中使用者組織的任何會議所撥打的任何外接電話，都會根據與全域語音路由策略 PSTN 使用關聯的語音路由進行評估。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-166">Once the global voice routing policy has been defined, any outbound calls made from meetings organized by users in your organization will be evaluated against the voice routes associated to the PSTN usages of the global voice routing policy.</span></span> <span data-ttu-id="bfa6d-167">撥出電話會依據符合撥號電話號碼號碼模式的第一個語音路由。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-167">The outbound calls will be routed according to the first voice route that matches the number pattern of the dialed phone number.</span></span>

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a><span data-ttu-id="bfa6d-168">步驟 5：將具有 GCC High 或 DoD 授權直接路由的音訊會議指派給使用者</span><span class="sxs-lookup"><span data-stu-id="bfa6d-168">Step 5: Assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your users</span></span>

<span data-ttu-id="bfa6d-169">若要將具有 GCC High 或 DoD 授權直接路由的音訊會議指派給使用者，請參閱 [指派授權給使用者](/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-169">To assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your user, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a><span data-ttu-id="bfa6d-170">步驟 6： (選) 查看 Teams 中的音訊會議號碼清單</span><span class="sxs-lookup"><span data-stu-id="bfa6d-170">Step 6: (Optional) See a list of Audio Conferencing numbers in Teams</span></span>

<span data-ttu-id="bfa6d-171">若要查看貴組織的音訊會議號碼清單，請前往查看 Microsoft Teams 中的音訊 [會議號碼清單](see-a-list-of-audio-conferencing-numbers-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-171">To see the list of Audio Conferencing numbers of your organization, go to [See a list of Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a><span data-ttu-id="bfa6d-172">步驟 7： (選擇性) 為貴組織的音訊會議電話撥入號碼設定自動語音語音處理語言</span><span class="sxs-lookup"><span data-stu-id="bfa6d-172">Step 7: (Optional) Set auto attendant languages for the Audio Conferencing dial-in numbers of you organization</span></span>

<span data-ttu-id="bfa6d-173">若要變更貴組織音訊會議撥入號碼的語言，請參閱在 [Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)中設定音訊會議自動語音語音處理語言。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-173">To change the languages of the Audio Conferencing dial-in numbers of your organization, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="bfa6d-174">步驟 8： (選擇性) 變更貴組織音訊會議橋接器的設定</span><span class="sxs-lookup"><span data-stu-id="bfa6d-174">Step 8: (Optional) Change the settings of the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="bfa6d-175">若要變更貴組織的音訊會議橋接器的設定，請參閱變更音訊會議橋接器 [的設定](change-the-settings-for-an-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-175">To change the settings of the Audio Conferencing bridge of your organization, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a><span data-ttu-id="bfa6d-176">步驟 9： (選) 設定貴組織使用者會議邀請中包含的電話號碼</span><span class="sxs-lookup"><span data-stu-id="bfa6d-176">Step 9: (Optional) Set the phone numbers included in the meeting invites of the users in your organization</span></span>

<span data-ttu-id="bfa6d-177">若要變更使用者會議邀請中包含的一組電話號碼，請參閱在 [Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md)中設定邀請中包含的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-177">To change the set of phone numbers that are included in the meeting invites of the users is your organization, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="bfa6d-178">使用 GCC High 和 DoD 直接路由的音訊會議功能不支援音訊會議功能</span><span class="sxs-lookup"><span data-stu-id="bfa6d-178">Audio Conferencing capabilities not supported in Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="bfa6d-179">以下是音訊會議功能，在具有 GCC High 和 DoD 直接路由的音訊會議中不支援：</span><span class="sxs-lookup"><span data-stu-id="bfa6d-179">The following are Audio Conferencing capabilities that are not supported in Audio Conferencing with Direct Routing for GCC High and DoD:</span></span>

- <span data-ttu-id="bfa6d-180">使用名稱錄製進入和離開通知。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-180">Entry and exit notifications using name recording.</span></span> <span data-ttu-id="bfa6d-181">對於使用直接路由的音訊會議，進入和離開通知會以鈴聲在會議中播放。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-181">For Audio Conferencing with Direct Routing, entry and exit notifications are played in the meeting as tones.</span></span>

- <span data-ttu-id="bfa6d-182">音訊會議的外發通話限制政策。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-182">Outbound calling restriction policies for Audio Conferencing.</span></span> <span data-ttu-id="bfa6d-183">限制撥出通話的使用者層級控制項不適用於透過直接路由路由的會議撥出電話。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-183">User-level controls to restrict outbound calls aren't applicable to meeting dial-out calls routed via Direct Routing.</span></span>

- <span data-ttu-id="bfa6d-184">停用特定會議召集人免付費號碼的使用方式。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-184">Disable the usage of toll-free numbers for the meetings specific organizer.</span></span> <span data-ttu-id="bfa6d-185">限制使用免付費號碼加入貴組織會議的使用者層級控制項不適用於透過直接路由路由的通話。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-185">User-level controls to restrict the usage of toll-free numbers to join the meetings of your organization aren't applicable to calls routed via Direct Routing.</span></span>

- <span data-ttu-id="bfa6d-186">當使用者的設定變更時，傳送通知電子郵件給使用者。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-186">Sending notification emails to users when their settings change.</span></span> <span data-ttu-id="bfa6d-187">音訊會議通知電子郵件不支援使用 GCC High 和 DoD 直接路由的音訊會議。</span><span class="sxs-lookup"><span data-stu-id="bfa6d-187">Audio Conferencing notification emails aren't supported for Audio Conferencing with Direct Routing for GCC High and DoD.</span></span>