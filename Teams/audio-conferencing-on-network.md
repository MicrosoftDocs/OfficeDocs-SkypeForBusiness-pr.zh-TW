---
title: 音訊會議的網路會議
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: oscarr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 下列描述音訊會議的 [在網路上開啟預覽] 功能。
ms.openlocfilehash: 3b33c67cc79f79d36cf2a11213dc934103b026fb
ms.sourcegitcommit: 19662d4bc4070f6031084d93e8794e0e02decd2b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/01/2020
ms.locfileid: "47321789"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a><span data-ttu-id="9145a-103">開啟音訊會議的網路會議預覽</span><span class="sxs-lookup"><span data-stu-id="9145a-103">Open Preview of On-network Conferencing for Audio Conferencing</span></span>

<span data-ttu-id="9145a-104">所有客戶都能使用網路會議的開啟預覽。</span><span class="sxs-lookup"><span data-stu-id="9145a-104">The Open Preview of On-network Conferencing is available to all customers.</span></span> <span data-ttu-id="9145a-105">[網路會議] 可讓組織透過直接路由傳送入站和出站音訊會議呼叫至 Microsoft 撥入號碼。</span><span class="sxs-lookup"><span data-stu-id="9145a-105">On-network Conferencing allows organizations to send inbound and outbound Audio Conferencing calls to Microsoft dial-in numbers through Direct Routing.</span></span> <span data-ttu-id="9145a-106">此功能不是為了將音訊會議支援延伸到協力廠商撥入號碼。</span><span class="sxs-lookup"><span data-stu-id="9145a-106">This capability is not intended to extend the support of Audio Conferencing to third party dial-in numbers.</span></span> <span data-ttu-id="9145a-107">如果使用網路會議，則無法透過協力廠商撥入電話號碼將來電傳送到音訊會議服務。</span><span class="sxs-lookup"><span data-stu-id="9145a-107">On-network Conferencing is not supported if it is used to route inbound calls to the Audio Conferencing service through third party dial-in phone numbers.</span></span>

<span data-ttu-id="9145a-108">本文將說明針對您的組織啟用網路會議時所需的先決條件及設定步驟。</span><span class="sxs-lookup"><span data-stu-id="9145a-108">This article describes the prerequisites and configuration steps required to enable On-network Conferencing for your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9145a-109">在印度的任何電話裝置上，都不能部署網路會議。</span><span class="sxs-lookup"><span data-stu-id="9145a-109">On-network Conferencing must NOT be deployed with any telephony equipment in India.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="9145a-110">必要條件</span><span class="sxs-lookup"><span data-stu-id="9145a-110">Prerequisites</span></span>

<span data-ttu-id="9145a-111">在設定網路會議之前，請確定貴組織符合下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="9145a-111">Before configuring On-network Conferencing, make sure your organization meets the following prerequisites:</span></span> 

- <span data-ttu-id="9145a-112">確定您組織中已啟用或將要啟用音訊會議的所有使用者都只使用 [小組] 模式。</span><span class="sxs-lookup"><span data-stu-id="9145a-112">Ensure that all users in your organization who are enabled, or will be enabled, for Audio Conferencing are in Teams Only mode.</span></span> <span data-ttu-id="9145a-113">只有在小組會議中才支援透過網路會議傳送入站與 outboud 音訊會議通話。</span><span class="sxs-lookup"><span data-stu-id="9145a-113">The routing of inbound and outboud Audio Conferencing calls through On-network Conferencing is only supported for Teams meetings.</span></span>

- <span data-ttu-id="9145a-114">將音訊會議授權指派給所有將使用網路會議的使用者。</span><span class="sxs-lookup"><span data-stu-id="9145a-114">Assign Audio Conferencing licenses to all users who will be using On-network Conferencing.</span></span>

- <span data-ttu-id="9145a-115">設定音訊會議服務。</span><span class="sxs-lookup"><span data-stu-id="9145a-115">Set up the Audio Conferencing service.</span></span> <span data-ttu-id="9145a-116">如需其他資訊，請參閱 [設定 Microsoft 團隊的音訊會議](set-up-audio-conferencing-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="9145a-116">For additional information, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span></span>

- <span data-ttu-id="9145a-117">針對直接路由 (SBC) 設定您的會話邊界控制器。</span><span class="sxs-lookup"><span data-stu-id="9145a-117">Set up your Session Border Controller (SBC) for Direct Routing.</span></span> <span data-ttu-id="9145a-118">如需其他資訊，請參閱 [規劃直接路由](direct-routing-plan.md) 及 [設定直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="9145a-118">For additional information, see [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span> 

  <span data-ttu-id="9145a-119">如果您只是為了進行音訊會議而設定直接傳送路線，則只需要完成「步驟1：將您的 SBC 連接到網路會議」。</span><span class="sxs-lookup"><span data-stu-id="9145a-119">If you are setting up Direct Routing only for the purposes of Audio Conferencing, then you need only complete “Step 1: Connect your SBC” for On-network Conferencing.</span></span>
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a><span data-ttu-id="9145a-120">透過直接路由啟用電話撥入呼叫路由至 Microsoft 音訊會議</span><span class="sxs-lookup"><span data-stu-id="9145a-120">Enable the routing of dial-in calls to Microsoft Audio Conferencing through Direct Routing</span></span> 

<span data-ttu-id="9145a-121">若要透過直接路由將內部部署使用者所進行的撥入呼叫路由至音訊會議服務，您必須針對 SBCs 和私人分支 Exchange 設定適當的路由規則， (s)  (Pbx) ]。</span><span class="sxs-lookup"><span data-stu-id="9145a-121">To route dial-in calls made by your on-premises users to the Audio Conferencing service through Direct Routing, you need to configure appropriate routing rules for your SBCs and Private Branch Exchange(s) (PBXs).</span></span>

<span data-ttu-id="9145a-122">您必須設定您的網站的電話語音裝置，以透過直接路由主幹將呼叫路由到貴組織的任何服務號碼。</span><span class="sxs-lookup"><span data-stu-id="9145a-122">You need to configure the telephony equipment of your sites to route calls to any service number of the conference bridge of your organization through a Direct Routing trunk.</span></span>

<span data-ttu-id="9145a-123">您可以在 [ **會議-> 會議橋** 接或使用商務用 Skype Online PowerShell Cmdlet CsOnlineDialInConferencingBridge，找到 [團隊系統管理中心] 中的服務號碼。</span><span class="sxs-lookup"><span data-stu-id="9145a-123">You can find the service numbers in Teams admin center under **Meetings -> Conferencing Bridges** or by using the Skype for Business Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="9145a-124">如需其他資訊，請參閱 [Microsoft 團隊中的音訊會議號碼](see-a-list-of-audio-conferencing-numbers-in-teams.md)清單。</span><span class="sxs-lookup"><span data-stu-id="9145a-124">For additional information, see a list of [Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>


## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a><span data-ttu-id="9145a-125">透過直接路由啟用團隊會議撥出通話的路由</span><span class="sxs-lookup"><span data-stu-id="9145a-125">Enable the routing of Teams meeting dial-out calls through Direct Routing</span></span>

<span data-ttu-id="9145a-126">團隊會議撥出通話是從貴組織中的會議開始，到 PSTN 號碼，包括呼叫我接聽電話和通話，讓新參與者加入會議。</span><span class="sxs-lookup"><span data-stu-id="9145a-126">Teams meeting dial-out calls are initiated from within a meeting in your organization to PSTN numbers, including call-me-at calls and calls to bring new participants to a meeting.</span></span> 

<span data-ttu-id="9145a-127">若要讓團隊透過直接路由來會議撥出路由，您需要建立並指派音訊會議路由策略，名為「OnlineAudioConferencingRoutingPolicy」。</span><span class="sxs-lookup"><span data-stu-id="9145a-127">To enable Teams meeting dial-out routing through Direct Routing, you need to create and assign an Audio Conferencing routing policy called “OnlineAudioConferencingRoutingPolicy”.</span></span> 

<span data-ttu-id="9145a-128">OnlineAudioConferencingRoutingPolicy 原則相當於經由直接路由的 1:1 PSTN 呼叫 CsOnlineVoiceRoutingPolicy。</span><span class="sxs-lookup"><span data-stu-id="9145a-128">The OnlineAudioConferencingRoutingPolicy policy is equivalent to the CsOnlineVoiceRoutingPolicy for 1:1 PSTN calls via Direct Routing.</span></span> <span data-ttu-id="9145a-129">您可以使用下列 Cmdlet 來管理 OnlineAudioConferencingRoutingPolicy 原則：</span><span class="sxs-lookup"><span data-stu-id="9145a-129">The OnlineAudioConferencingRoutingPolicy policy can be managed by using the following cmdlets:</span></span>

-   <span data-ttu-id="9145a-130">新-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="9145a-130">New-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="9145a-131">Set-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="9145a-131">Set-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="9145a-132">CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="9145a-132">Get-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="9145a-133">授與 CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="9145a-133">Grant-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="9145a-134">移除-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="9145a-134">Remove-CsOnlineAudioConferencingRoutingPolicy</span></span>

<span data-ttu-id="9145a-135">如需直接路由路由的詳細資訊，請參閱 [設定直接路由的語音路由](direct-routing-voice-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="9145a-135">For more information about routing for Direct Routing, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md).</span></span>


<span data-ttu-id="9145a-136">若要啟用透過直接路由傳送會議撥出通話的功能，您需要：</span><span class="sxs-lookup"><span data-stu-id="9145a-136">To enable the routing of meeting dial-out calls through Direct Routing, you need to:</span></span> 

- <span data-ttu-id="9145a-137">設定音訊會議路由策略</span><span class="sxs-lookup"><span data-stu-id="9145a-137">Configure Audio Conferencing routing policies</span></span>
- <span data-ttu-id="9145a-138">在組織的電話裝置上設定路由</span><span class="sxs-lookup"><span data-stu-id="9145a-138">Configure the routing on the telephony equipment of your organization</span></span>
- <span data-ttu-id="9145a-139"> (選用) 設定撥號方案</span><span class="sxs-lookup"><span data-stu-id="9145a-139">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="9145a-140">來自團隊會議的撥出通話是來自于會議橋接器上的預設服務號碼。</span><span class="sxs-lookup"><span data-stu-id="9145a-140">Dial-out calls from Teams meetings are coming from the default service number on the conference bridge.</span></span> <span data-ttu-id="9145a-141">如需音訊會議橋接器預設服務號碼的其他資訊，請參閱在 [音訊會議橋中變更電話號碼](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="9145a-141">For additional information on the default service number of your Audio Conferencing bridge, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

### <a name="configure-audio-conferencing-routing-policies"></a><span data-ttu-id="9145a-142">設定音訊會議路由策略</span><span class="sxs-lookup"><span data-stu-id="9145a-142">Configure Audio Conferencing routing policies</span></span>

<span data-ttu-id="9145a-143">[音訊會議路由原則] OnlineAudioConferencingRoutingPolicy 會判斷哪個會議撥出通話是路由至直接路由 trunks。</span><span class="sxs-lookup"><span data-stu-id="9145a-143">The Audio Conferencing routing policy OnlineAudioConferencingRoutingPolicy determines which meeting dial-out calls are routed to Direct Routing trunks.</span></span> <span data-ttu-id="9145a-144">如果您熟悉 CsOnlineVoiceRoutingPolicy 原則，此原則的運作方式會非常類似。</span><span class="sxs-lookup"><span data-stu-id="9145a-144">If you are familiar with the CsOnlineVoiceRoutingPolicy policy, this policy works in a very similar way.</span></span>

<span data-ttu-id="9145a-145">若要設定音訊會議路由策略，您需要執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="9145a-145">The following steps are needed to set up Audio Conferencing routing policies:</span></span>
1.  <span data-ttu-id="9145a-146">建立 PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="9145a-146">Create PSTN usages</span></span>
2.  <span data-ttu-id="9145a-147">設定語音路由</span><span class="sxs-lookup"><span data-stu-id="9145a-147">Configure voice routes</span></span>
3.  <span data-ttu-id="9145a-148">建立音訊會議語音路由策略</span><span class="sxs-lookup"><span data-stu-id="9145a-148">Create Audio Conferencing voice routing policies</span></span>
4.  <span data-ttu-id="9145a-149">指派原則給您的使用者</span><span class="sxs-lookup"><span data-stu-id="9145a-149">Assign a policy to your users</span></span>


#### <a name="create-pstn-usages"></a><span data-ttu-id="9145a-150">建立 PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="9145a-150">Create PSTN usages</span></span>

<span data-ttu-id="9145a-151">PSTN 用法是語音路由的集合。</span><span class="sxs-lookup"><span data-stu-id="9145a-151">PSTN usages are collections of voice routes.</span></span> <span data-ttu-id="9145a-152">從指定召集人的會議啟動撥出通話時，語音路由會根據使用者的語音路由策略，根據與使用者相關聯的 PSTN 使用量來判斷通話的路由路徑。</span><span class="sxs-lookup"><span data-stu-id="9145a-152">When a dial-out call is initiated from the meeting of a given organizer, voice routes will be used to determine the routing path of the call based on the PSTN usages that are associated to the user via the user’s voice routing policy.</span></span>

<span data-ttu-id="9145a-153">您可以使用「CsOnlinePstnUsage」 Cmdlet 來建立 PSTN 使用量。</span><span class="sxs-lookup"><span data-stu-id="9145a-153">You can create a PSTN usage by using the “Set-CsOnlinePstnUsage” cmdlet.</span></span> <span data-ttu-id="9145a-154">例如：</span><span class="sxs-lookup"><span data-stu-id="9145a-154">For Example:</span></span>

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a><span data-ttu-id="9145a-155">設定語音路由</span><span class="sxs-lookup"><span data-stu-id="9145a-155">Configure voice routes</span></span>

<span data-ttu-id="9145a-156">語音路由依據從團隊會議撥打的電話號碼，決定應該用來傳送通話的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="9145a-156">Voice routes determine the PSTN gateway that should be used to route a call based on the phone number that is dialed from a Teams meeting.</span></span> <span data-ttu-id="9145a-157">語音路由決定應該用來傳送指定通話的 PSTN 閘道，方法是將從使用 RegEx 模式的小組會議所撥的電話號碼相較。</span><span class="sxs-lookup"><span data-stu-id="9145a-157">Voice routes determine the PSTN gateway that should be used to route a given call by matching the phone number dialed from a Teams meeting with a regex pattern.</span></span> <span data-ttu-id="9145a-158">建立語音路線時，必須將路由與一或多個 PSTN 用途產生關聯。</span><span class="sxs-lookup"><span data-stu-id="9145a-158">When creating a voice route, the route must be associated to one or more PSTN usages.</span></span>

<span data-ttu-id="9145a-159">您可以使用「新-CsOnlineVoiceRoute」 Cmdlet，建立語音路由並定義要與語音路由相關聯的 RegEx 和閘道。</span><span class="sxs-lookup"><span data-stu-id="9145a-159">You can create a voice route and define the regex and gateways to be associated with the voice route by using the “New-CsOnlineVoiceRoute” cmdlet.</span></span> <span data-ttu-id="9145a-160">例如：</span><span class="sxs-lookup"><span data-stu-id="9145a-160">For Example:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a><span data-ttu-id="9145a-161">建立音訊會議語音路由策略</span><span class="sxs-lookup"><span data-stu-id="9145a-161">Create Audio Conferencing voice routing policies</span></span>

<span data-ttu-id="9145a-162">音訊會議語音路由策略會根據會議撥出通話通話的目標電話號碼，決定您可以用來傳送來自召集人會議之通話的可能路線。</span><span class="sxs-lookup"><span data-stu-id="9145a-162">Audio Conferencing voice routing policies determine the possible routes that can be used to route a call originating from the meetings of an organizer based on the target phone number of the meeting dial-out call.</span></span> <span data-ttu-id="9145a-163">音訊會議語音路由策略會與一或多個 PSTN 用途相關聯，然後，決定將嘗試用於會議撥出呼叫（與原則相關的召集人）的可能路由。</span><span class="sxs-lookup"><span data-stu-id="9145a-163">Audio Conferencing voice routing policies are associated to one or more PSTN usages, which in turn, determine the possible routes that will be attempted to be used for the meeting dial-out calls of the organizers associated to the policy.</span></span>

<span data-ttu-id="9145a-164">您可以使用「新-CsOnlineAudioConferencingRoutingPolicy」 Cmdlet 來建立音訊會議語音路由原則。</span><span class="sxs-lookup"><span data-stu-id="9145a-164">You can create an Audio Conferencing voice routing policy by using the “New- CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="9145a-165">例如：</span><span class="sxs-lookup"><span data-stu-id="9145a-165">For Example:</span></span>

```
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="9145a-166">在將原則指派給使用者，並從使用者的其中一個會議啟動會議撥出通話時，系統會評估 PSTN 用法中與召集人相關聯的語音路由（透過使用者的語音路由策略）。</span><span class="sxs-lookup"><span data-stu-id="9145a-166">After the policy is assigned to a user, and when a meeting dial-out call is initiated from one of the user's meetings, the voice routes in the PSTN usages that are associated to the organizer through the user's voice routing policy will be evaluated.</span></span> <span data-ttu-id="9145a-167">如果會議撥出通話目的地與與召集人相關的其中一個語音路由中的 RegEx 相符，會議撥出呼叫將會路由到語音路由中定義的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="9145a-167">If the meeting dial-out call destination matches a regex in one of the voice routes that are associated to the organizer, the meeting dial-out call will be routed to the PSTN gateway defined in the voice route.</span></span> <span data-ttu-id="9145a-168">如果會議撥出通話目的地不符合任何與召集人相關的語音路由，會議撥出呼叫將由 Microsoft 傳送。</span><span class="sxs-lookup"><span data-stu-id="9145a-168">If the meeting dial-out call destination does not match any of the voice routes associated to the organizer, the meeting dial-out call will be routed by Microsoft.</span></span>

#### <a name="assign-a-policy-to-your-users"></a><span data-ttu-id="9145a-169">指派原則給您的使用者</span><span class="sxs-lookup"><span data-stu-id="9145a-169">Assign a policy to your users</span></span>

<span data-ttu-id="9145a-170">在定義音訊會議路由策略之後，您現在可以將它們指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="9145a-170">After the Audio Conferencing routing policies are defined, you can now assign them to users.</span></span> <span data-ttu-id="9145a-171">將原則指派給它們之後，就會針對會議撥出通話進行評估，以判斷其路由路徑。</span><span class="sxs-lookup"><span data-stu-id="9145a-171">After policies are assigned to them, the meeting dial-out calls will be evaluated against it to determine their routing path.</span></span> <span data-ttu-id="9145a-172">音訊會議路由策略總是根據會議召集人的評估，與會議中啟動會議撥出通話的使用者無關。</span><span class="sxs-lookup"><span data-stu-id="9145a-172">Audio Conferencing routing policies are always evaluated based on the organizer of the meeting, independently from the user in the meeting that initiates a meeting dial-out call.</span></span>

<span data-ttu-id="9145a-173">您可以使用「授與 CsOnlineAudioConferencingRoutingPolicy」 Cmdlet，將音訊會議語音路由原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="9145a-173">You can assign an Audio Conferencing voice routing policy to a user by using the “Grant-CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="9145a-174">例如：</span><span class="sxs-lookup"><span data-stu-id="9145a-174">For example:</span></span>

```
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a><span data-ttu-id="9145a-175">在組織的電話語音裝置上設定路由</span><span class="sxs-lookup"><span data-stu-id="9145a-175">Configure routing on the telephony equipment of your organization</span></span>

<span data-ttu-id="9145a-176">在貴組織的電話裝置上，您必須確認透過直接路由路由的會議撥出電話會傳送到預定的目的地。</span><span class="sxs-lookup"><span data-stu-id="9145a-176">On the telephony equipment of your organization, you need to ensure that the meeting dial-out calls routed through Direct Routing are routed to the intended destination.</span></span>


### <a name="optional-configure-a-dial-plan"></a><span data-ttu-id="9145a-177"> (選用) 設定撥號方案</span><span class="sxs-lookup"><span data-stu-id="9145a-177">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="9145a-178">撥號方案是一組正常化規則，其中個別使用者將撥打的電話號碼轉換成替代格式 (通常是) 的 E. 164，以進行呼叫授權及呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="9145a-178">A dial plan is a set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="9145a-179">根據預設，團隊使用者可以使用164格式的 PSTN 號碼撥出（即 +） \<country code\> \<number\> 。</span><span class="sxs-lookup"><span data-stu-id="9145a-179">By default, Teams users can dial-out to PSTN numbers in E.164 format, that is, +\<country code\>\<number\>.</span></span> <span data-ttu-id="9145a-180">不過，您可以使用撥號方案，讓使用者以其他格式撥打電話號碼（例如4位數延伸）。</span><span class="sxs-lookup"><span data-stu-id="9145a-180">However, dial plans can be used to allow users to dial phone numbers in other formats, for instance 4-digit extensions.</span></span>

<span data-ttu-id="9145a-181">如果您想要透過網路會議啟用延伸式撥號，您可以設定撥號方案，讓 [擴充撥號模式] 符合您組織之電話號碼的電話號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="9145a-181">If you would like to enable extension-based dialing through On-network conferencing, you can set up dial plans to match the extension dialing pattern to the phone number ranges of the phone number of your organization.</span></span> <span data-ttu-id="9145a-182">若要設定撥號方案，請參閱 [建立及管理撥號方案](create-and-manage-dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="9145a-182">To set up dial plans, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>


## <a name="known-issues-in-open-preview"></a><span data-ttu-id="9145a-183">開啟預覽中的已知問題</span><span class="sxs-lookup"><span data-stu-id="9145a-183">Known issues in Open Preview</span></span>

<span data-ttu-id="9145a-184">下列是目前在「網路會議」開啟預覽版中的已知問題清單。</span><span class="sxs-lookup"><span data-stu-id="9145a-184">The following is a list of known issues that are currently present in the Open Preview release of On-network conferencing.</span></span> <span data-ttu-id="9145a-185">Microsoft 正在努力解決這些問題。</span><span class="sxs-lookup"><span data-stu-id="9145a-185">Microsoft is working on addressing these issues.</span></span>

| <span data-ttu-id="9145a-186">問題</span><span class="sxs-lookup"><span data-stu-id="9145a-186">Issue</span></span> | <span data-ttu-id="9145a-187">避免</span><span class="sxs-lookup"><span data-stu-id="9145a-187">Workaround</span></span> |
| :--- | :--- |
| <span data-ttu-id="9145a-188">透過網路會議路由的匿名/隱藏呼叫者 Id 的撥入呼叫無法連線至會議。</span><span class="sxs-lookup"><span data-stu-id="9145a-188">Dial-in calls with anonymous/hidden caller IDs that are routed through On-network conferencing cannot be connected to the meeting.</span></span> | <span data-ttu-id="9145a-189">如果可能的話，請在您的 PBX 或 SBC 中設定一個配置，以隨時透過網路會議傳送來電 ID 以進行路由。</span><span class="sxs-lookup"><span data-stu-id="9145a-189">If possible, set a configuration in your PBX or SBC to always send a caller ID for calls routed via On-network conferencing.</span></span>|
| <span data-ttu-id="9145a-190">在某些情況下，當使用者撥入服務 ( 「歡迎使用音訊會議服務 ) ...」時，會向使用者播放的歡迎訊息會被截斷，且使用者不會聽到「歡迎」 word。</span><span class="sxs-lookup"><span data-stu-id="9145a-190">In some cases, the welcome message that is played to users when they dial in to the service (“Welcome to the Audio Conferencing service…”) is truncated and users do not hear the “Welcome” word.</span></span>| <span data-ttu-id="9145a-191">目前沒有此問題的解決方法。</span><span class="sxs-lookup"><span data-stu-id="9145a-191">There are no workarounds for this issue at the moment.</span></span> |




## <a name="related-topics"></a><span data-ttu-id="9145a-192">相關主題</span><span class="sxs-lookup"><span data-stu-id="9145a-192">Related topics</span></span>


