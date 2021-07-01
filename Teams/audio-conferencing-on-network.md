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
- m365initiative-meetings
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 下列說明音訊會議的網路。
ms.openlocfilehash: b7851bd2457debe8ee0de3144e24a15edb521222
ms.sourcegitcommit: b39bd1de0219a9e3a3b0c97fc485c9578ddb643c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230560"
---
# <a name="on-network-conferencing-for-audio-conferencing"></a><span data-ttu-id="461a8-103">音訊會議的網路會議</span><span class="sxs-lookup"><span data-stu-id="461a8-103">On-network Conferencing for Audio Conferencing</span></span>

<span data-ttu-id="461a8-104">網路會議可讓組織透過直接路由將輸入和撥出的音訊會議通話傳送至 Microsoft 撥入號碼。</span><span class="sxs-lookup"><span data-stu-id="461a8-104">On-network Conferencing allows organizations to send inbound and outbound Audio Conferencing calls to Microsoft dial-in numbers through Direct Routing.</span></span> <span data-ttu-id="461a8-105">此功能並不適合將音訊會議的支援延伸到協力廠商撥入號碼。</span><span class="sxs-lookup"><span data-stu-id="461a8-105">This capability is not intended to extend the support of Audio Conferencing to third party dial-in numbers.</span></span> <span data-ttu-id="461a8-106">如果網路會議是用來透過協力廠商撥入電話號碼或從 Microsoft 音訊會議橋接器撥出電話路由到 PSTN，則不支援網路會議。</span><span class="sxs-lookup"><span data-stu-id="461a8-106">On-network Conferencing is not supported if it is used to route inbound calls to the Audio Conferencing service through third party dial-in phone numbers or outbound calls to the PSTN from Microsoft Audio Conferencing Bridge.</span></span> 

<span data-ttu-id="461a8-107">本文將說明為貴組織啟用網路會議的先決條件和組組步驟。</span><span class="sxs-lookup"><span data-stu-id="461a8-107">This article describes the prerequisites and configuration steps required to enable On-network Conferencing for your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="461a8-108">網路會議不得與印度的任何電話設備一起部署。</span><span class="sxs-lookup"><span data-stu-id="461a8-108">On-network Conferencing must NOT be deployed with any telephony equipment in India.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="461a8-109">必要條件</span><span class="sxs-lookup"><span data-stu-id="461a8-109">Prerequisites</span></span>

<span data-ttu-id="461a8-110">在設置網路會議之前，請確定貴組織符合下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="461a8-110">Before configuring On-network Conferencing, make sure your organization meets the following prerequisites:</span></span> 

- <span data-ttu-id="461a8-111">請確保貴組織中已啟用或將會啟用音訊會議的所有使用者，Teams所有會議。</span><span class="sxs-lookup"><span data-stu-id="461a8-111">Ensure that all users in your organization who are enabled, or will be enabled, for Audio Conferencing are using Teams for all Meetings.</span></span> <span data-ttu-id="461a8-112">透過網路會議撥打和輸出音訊會議通話的路由僅支援Teams會議。</span><span class="sxs-lookup"><span data-stu-id="461a8-112">The routing of inbound and outbound Audio Conferencing calls through On-network Conferencing is only supported for Teams meetings.</span></span>

- <span data-ttu-id="461a8-113">指派音訊會議授權給將會使用網路會議的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="461a8-113">Assign Audio Conferencing licenses to all users who will be using On-network Conferencing.</span></span>

- <span data-ttu-id="461a8-114">設定音訊會議服務。</span><span class="sxs-lookup"><span data-stu-id="461a8-114">Set up the Audio Conferencing service.</span></span> <span data-ttu-id="461a8-115">有關其他資訊，請參閱[設定音訊會議Microsoft Teams。](set-up-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="461a8-115">For additional information, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span></span>

- <span data-ttu-id="461a8-116">設定會話邊界控制器 (SBC) 直接路由。</span><span class="sxs-lookup"><span data-stu-id="461a8-116">Set up your Session Border Controller (SBC) for Direct Routing.</span></span> <span data-ttu-id="461a8-117">有關其他資訊，請參閱 [規劃直接路由](direct-routing-plan.md) 和 [設定直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="461a8-117">For additional information, see [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span> 

  <span data-ttu-id="461a8-118">如果您只針對音訊會議的目的設定直接路由，則只需要完成「步驟 1：連線 SBC」的網內會議。</span><span class="sxs-lookup"><span data-stu-id="461a8-118">If you are setting up Direct Routing only for the purposes of Audio Conferencing, then you need only complete “Step 1: Connect your SBC” for On-network Conferencing.</span></span>
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a><span data-ttu-id="461a8-119">啟用透過直接路由將撥入式通話路由至 Microsoft 音訊會議</span><span class="sxs-lookup"><span data-stu-id="461a8-119">Enable the routing of dial-in calls to Microsoft Audio Conferencing through Direct Routing</span></span> 

<span data-ttu-id="461a8-120">若要透過直接路由，將內部部署使用者撥打的電話撥入電話路由至音訊會議服務，您必須為 SBC 和私人分支 Exchange (PBX)  (設定適當的路由規則) 。</span><span class="sxs-lookup"><span data-stu-id="461a8-120">To route dial-in calls made by your on-premises users to the Audio Conferencing service through Direct Routing, you need to configure appropriate routing rules for your SBCs and Private Branch Exchange(s) (PBXs).</span></span>

<span data-ttu-id="461a8-121">您需要設定網站的電話設備，以透過直接路由主幹將通話路由到貴組織會議橋接器的任何服務號碼。</span><span class="sxs-lookup"><span data-stu-id="461a8-121">You need to configure the telephony equipment of your sites to route calls to any service number of the conference bridge of your organization through a Direct Routing trunk.</span></span>

<span data-ttu-id="461a8-122">您可以在 Teams 系統管理中心會議 **->** 會議橋接器下，或使用 商務用 Skype Online PowerShell Cmdlet Get-CsOnlineDialInConferencingBridge 找到服務號碼。</span><span class="sxs-lookup"><span data-stu-id="461a8-122">You can find the service numbers in Teams admin center under **Meetings -> Conferencing Bridges** or by using the Skype for Business Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="461a8-123">有關其他資訊，請參閱 Microsoft Teams 中的[音訊會議號碼Microsoft Teams。](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="461a8-123">For additional information, see a list of [Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="461a8-124">此功能不適用於擁有每分鐘付費音訊會議授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="461a8-124">This feature is not available to users with the pay-per-minute Audio Conferencing license.</span></span>

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a><span data-ttu-id="461a8-125">啟用透過直接路由Teams撥出電話的路由</span><span class="sxs-lookup"><span data-stu-id="461a8-125">Enable the routing of Teams meeting dial-out calls through Direct Routing</span></span>

<span data-ttu-id="461a8-126">Teams會議撥出電話會從貴組織的會議內撥打 PSTN 號碼，包括電話-me-at 通話和通話，以將新參與者帶到會議。</span><span class="sxs-lookup"><span data-stu-id="461a8-126">Teams meeting dial-out calls are initiated from within a meeting in your organization to PSTN numbers, including call-me-at calls and calls to bring new participants to a meeting.</span></span> 

<span data-ttu-id="461a8-127">若要Teams直接路由傳送給網路使用者，您必須建立並指派稱為「OnlineAudioConferencingRoutingPolicy」的音訊會議路由策略。</span><span class="sxs-lookup"><span data-stu-id="461a8-127">To enable Teams meeting dial-out routing through Direct Routing to on-network users, you need to create and assign an Audio Conferencing routing policy called “OnlineAudioConferencingRoutingPolicy”.</span></span> 

<span data-ttu-id="461a8-128">OnlineAudioConferencingRoutingPolicy 政策相當於透過直接路由撥打 1：1 PSTN 通話的 CsOnlineVoiceRoutingPolicy。</span><span class="sxs-lookup"><span data-stu-id="461a8-128">The OnlineAudioConferencingRoutingPolicy policy is equivalent to the CsOnlineVoiceRoutingPolicy for 1:1 PSTN calls via Direct Routing.</span></span> <span data-ttu-id="461a8-129">您可以使用下列 Cmdlet 管理 OnlineAudioConferencingRoutingPolicy 政策：</span><span class="sxs-lookup"><span data-stu-id="461a8-129">The OnlineAudioConferencingRoutingPolicy policy can be managed by using the following cmdlets:</span></span>

-   <span data-ttu-id="461a8-130">New-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="461a8-130">New-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="461a8-131">Set-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="461a8-131">Set-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="461a8-132">Get-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="461a8-132">Get-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="461a8-133">Grant-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="461a8-133">Grant-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="461a8-134">Remove-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="461a8-134">Remove-CsOnlineAudioConferencingRoutingPolicy</span></span>

<span data-ttu-id="461a8-135">有關直接路由路由詳細資訊，請參閱 [設定直接路由的語音路由](direct-routing-voice-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="461a8-135">For more information about routing for Direct Routing, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md).</span></span>


<span data-ttu-id="461a8-136">若要透過直接路由啟用會議撥出電話的路由，您必須：</span><span class="sxs-lookup"><span data-stu-id="461a8-136">To enable the routing of meeting dial-out calls through Direct Routing, you need to:</span></span> 

- <span data-ttu-id="461a8-137">設定音訊會議路由策略</span><span class="sxs-lookup"><span data-stu-id="461a8-137">Configure Audio Conferencing routing policies</span></span>
- <span data-ttu-id="461a8-138">在貴組織的電話設備上設定路由</span><span class="sxs-lookup"><span data-stu-id="461a8-138">Configure the routing on the telephony equipment of your organization</span></span>
- <span data-ttu-id="461a8-139"> (選) 設定撥號方案</span><span class="sxs-lookup"><span data-stu-id="461a8-139">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="461a8-140">從會議撥出Teams電話來自會議橋接器上的預設服務號碼。</span><span class="sxs-lookup"><span data-stu-id="461a8-140">Dial-out calls from Teams meetings are coming from the default service number on the conference bridge.</span></span> <span data-ttu-id="461a8-141">有關音訊會議橋接器預設服務號碼的其他資訊，請參閱變更音訊會議橋接器 [上的電話號碼](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="461a8-141">For additional information on the default service number of your Audio Conferencing bridge, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

### <a name="configure-audio-conferencing-routing-policies"></a><span data-ttu-id="461a8-142">設定音訊會議路由策略</span><span class="sxs-lookup"><span data-stu-id="461a8-142">Configure Audio Conferencing routing policies</span></span>

<span data-ttu-id="461a8-143">音訊會議路由策略 OnlineAudioConferencingRoutingPolicy 會決定哪些會議撥出電話會路由至直接路由主幹。</span><span class="sxs-lookup"><span data-stu-id="461a8-143">The Audio Conferencing routing policy OnlineAudioConferencingRoutingPolicy determines which meeting dial-out calls are routed to Direct Routing trunks.</span></span> <span data-ttu-id="461a8-144">如果您熟悉 CsOnlineVoiceRoutingPolicy 政策，此政策運作方式非常類似。</span><span class="sxs-lookup"><span data-stu-id="461a8-144">If you are familiar with the CsOnlineVoiceRoutingPolicy policy, this policy works in a very similar way.</span></span>

<span data-ttu-id="461a8-145">設定音訊會議路由策略需要下列步驟：</span><span class="sxs-lookup"><span data-stu-id="461a8-145">The following steps are needed to set up Audio Conferencing routing policies:</span></span>
1.  <span data-ttu-id="461a8-146">建立 PSTN 使用方式</span><span class="sxs-lookup"><span data-stu-id="461a8-146">Create PSTN usages</span></span>
2.  <span data-ttu-id="461a8-147">設定語音路由</span><span class="sxs-lookup"><span data-stu-id="461a8-147">Configure voice routes</span></span>
3.  <span data-ttu-id="461a8-148">建立音訊會議語音路由策略</span><span class="sxs-lookup"><span data-stu-id="461a8-148">Create Audio Conferencing voice routing policies</span></span>
4.  <span data-ttu-id="461a8-149">指派策略給使用者</span><span class="sxs-lookup"><span data-stu-id="461a8-149">Assign a policy to your users</span></span>


#### <a name="create-pstn-usages"></a><span data-ttu-id="461a8-150">建立 PSTN 使用方式</span><span class="sxs-lookup"><span data-stu-id="461a8-150">Create PSTN usages</span></span>

<span data-ttu-id="461a8-151">PSTN 使用量是語音路由的集合。</span><span class="sxs-lookup"><span data-stu-id="461a8-151">PSTN usages are collections of voice routes.</span></span> <span data-ttu-id="461a8-152">當從特定召集人的會議啟動撥出通話時，語音路由會根據透過使用者的語音路由策略與使用者相關聯的 PSTN 使用狀況，來判斷通話的路由路徑。</span><span class="sxs-lookup"><span data-stu-id="461a8-152">When a dial-out call is initiated from the meeting of a given organizer, voice routes will be used to determine the routing path of the call based on the PSTN usages that are associated to the user via the user’s voice routing policy.</span></span>

<span data-ttu-id="461a8-153">您可以使用 「Set-CsOnlinePstnUsage」 Cmdlet 建立 PSTN 使用量。</span><span class="sxs-lookup"><span data-stu-id="461a8-153">You can create a PSTN usage by using the “Set-CsOnlinePstnUsage” cmdlet.</span></span> <span data-ttu-id="461a8-154">例如：</span><span class="sxs-lookup"><span data-stu-id="461a8-154">For Example:</span></span>

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a><span data-ttu-id="461a8-155">設定語音路由</span><span class="sxs-lookup"><span data-stu-id="461a8-155">Configure voice routes</span></span>

<span data-ttu-id="461a8-156">語音路由會決定 PSTN 閘道，該閘道應該用來根據從會議撥打的電話號碼來路由Teams號碼。</span><span class="sxs-lookup"><span data-stu-id="461a8-156">Voice routes determine the PSTN gateway that should be used to route a call based on the phone number that is dialed from a Teams meeting.</span></span> <span data-ttu-id="461a8-157">語音路由會決定 PSTN 閘道，該閘道應該用來路由給定通話，方法為使用 RegEx 模式Teams會議撥打的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="461a8-157">Voice routes determine the PSTN gateway that should be used to route a given call by matching the phone number dialed from a Teams meeting with a regex pattern.</span></span> <span data-ttu-id="461a8-158">建立語音路由時，路由必須與一或多個 PSTN 使用方式相關聯。</span><span class="sxs-lookup"><span data-stu-id="461a8-158">When creating a voice route, the route must be associated to one or more PSTN usages.</span></span>

<span data-ttu-id="461a8-159">您可以使用 「New-CsOnlineVoiceRoute」Cmdlet 建立語音路由，並定義要與語音路由相關聯的 RegEx 和閘道。</span><span class="sxs-lookup"><span data-stu-id="461a8-159">You can create a voice route and define the regex and gateways to be associated with the voice route by using the “New-CsOnlineVoiceRoute” cmdlet.</span></span> <span data-ttu-id="461a8-160">例如：</span><span class="sxs-lookup"><span data-stu-id="461a8-160">For Example:</span></span>

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a><span data-ttu-id="461a8-161">建立音訊會議語音路由策略</span><span class="sxs-lookup"><span data-stu-id="461a8-161">Create Audio Conferencing voice routing policies</span></span>

<span data-ttu-id="461a8-162">音訊會議語音路由策略會根據會議撥出通話的目標電話號碼，決定可用來路由來自會議召集人會議之通話的可能路由。</span><span class="sxs-lookup"><span data-stu-id="461a8-162">Audio Conferencing voice routing policies determine the possible routes that can be used to route a call originating from the meetings of an organizer based on the target phone number of the meeting dial-out call.</span></span> <span data-ttu-id="461a8-163">音訊會議語音路由策略與一或多個 PSTN 使用方式相關聯，進而決定將嘗試用於與該政策相關聯的會議撥出通話的可能路由。</span><span class="sxs-lookup"><span data-stu-id="461a8-163">Audio Conferencing voice routing policies are associated to one or more PSTN usages, which in turn, determine the possible routes that will be attempted to be used for the meeting dial-out calls of the organizers associated to the policy.</span></span>

<span data-ttu-id="461a8-164">您可以使用 「New- CsOnlineAudioConferencingRoutingPolicy」 Cmdlet 來建立音訊會議語音路由策略。</span><span class="sxs-lookup"><span data-stu-id="461a8-164">You can create an Audio Conferencing voice routing policy by using the “New- CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="461a8-165">例如：</span><span class="sxs-lookup"><span data-stu-id="461a8-165">For Example:</span></span>

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="461a8-166">將策略指派給使用者後，以及當從其中一個使用者的會議啟動會議撥出通話時，會評估透過使用者的語音路由策略與召集人相關聯的 PSTN 使用方式中的語音路由。</span><span class="sxs-lookup"><span data-stu-id="461a8-166">After the policy is assigned to a user, and when a meeting dial-out call is initiated from one of the user's meetings, the voice routes in the PSTN usages that are associated to the organizer through the user's voice routing policy will be evaluated.</span></span> <span data-ttu-id="461a8-167">如果會議撥出通話目的地與與召集人相關聯的其中一個語音路由中的 RegEx 符合，會議撥出電話會路由至語音路由中定義的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="461a8-167">If the meeting dial-out call destination matches a regex in one of the voice routes that are associated to the organizer, the meeting dial-out call will be routed to the PSTN gateway defined in the voice route.</span></span> <span data-ttu-id="461a8-168">如果會議撥出通話目的地不符合任何與召集人相關聯的語音路由，會議撥出電話會由 Microsoft 路由。</span><span class="sxs-lookup"><span data-stu-id="461a8-168">If the meeting dial-out call destination does not match any of the voice routes associated to the organizer, the meeting dial-out call will be routed by Microsoft.</span></span>

#### <a name="assign-a-policy-to-your-users"></a><span data-ttu-id="461a8-169">指派策略給使用者</span><span class="sxs-lookup"><span data-stu-id="461a8-169">Assign a policy to your users</span></span>

<span data-ttu-id="461a8-170">定義音訊會議路由策略之後，現在您可以將這些路由策略指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="461a8-170">After the Audio Conferencing routing policies are defined, you can now assign them to users.</span></span> <span data-ttu-id="461a8-171">將策略指派給他們之後，會議撥出電話會根據它進行評估，以決定其路由路徑。</span><span class="sxs-lookup"><span data-stu-id="461a8-171">After policies are assigned to them, the meeting dial-out calls will be evaluated against it to determine their routing path.</span></span> <span data-ttu-id="461a8-172">音訊會議路由策略一定根據會議的召集人進行評估，與啟動會議撥出電話的會議使用者無關。</span><span class="sxs-lookup"><span data-stu-id="461a8-172">Audio Conferencing routing policies are always evaluated based on the organizer of the meeting, independently from the user in the meeting that initiates a meeting dial-out call.</span></span>

<span data-ttu-id="461a8-173">您可以使用 「Grant-CsOnlineAudioConferencingRoutingPolicy」Cmdlet 將音訊會議語音路由策略指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="461a8-173">You can assign an Audio Conferencing voice routing policy to a user by using the “Grant-CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="461a8-174">例如：</span><span class="sxs-lookup"><span data-stu-id="461a8-174">For example:</span></span>

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a><span data-ttu-id="461a8-175">在貴組織的電話設備上設定路由</span><span class="sxs-lookup"><span data-stu-id="461a8-175">Configure routing on the telephony equipment of your organization</span></span>

<span data-ttu-id="461a8-176">在貴組織的電話設備上，您必須確保透過直接路由的會議撥出電話會路由至預定的網路目的地。</span><span class="sxs-lookup"><span data-stu-id="461a8-176">On the telephony equipment of your organization, you need to ensure that the meeting dial-out calls routed through Direct Routing are routed to the intended on-network destination.</span></span>


### <a name="optional-configure-a-dial-plan"></a><span data-ttu-id="461a8-177"> (選) 設定撥號方案</span><span class="sxs-lookup"><span data-stu-id="461a8-177">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="461a8-178">撥號方案是一組標準化規則，將個別使用者撥打的電話號碼轉換成替代格式 (通常是 E.164) ，用於通話授權和呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="461a8-178">A dial plan is a set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="461a8-179">根據預設，Teams以 E.164 格式撥入 PSTN 號碼，即 + \<country code\> \<number\> 。</span><span class="sxs-lookup"><span data-stu-id="461a8-179">By default, Teams users can dial-out to PSTN numbers in E.164 format, that is, +\<country code\>\<number\>.</span></span> <span data-ttu-id="461a8-180">不過，撥號方案可用來允許使用者以其他格式撥打電話號碼，例如 4 位數分機。</span><span class="sxs-lookup"><span data-stu-id="461a8-180">However, dial plans can be used to allow users to dial phone numbers in other formats, for instance 4-digit extensions.</span></span>

<span data-ttu-id="461a8-181">如果您想要透過網路會議啟用分機式撥號，您可以設定撥號方案，以將分機撥號模式與貴組織電話號碼的電話號碼範圍相符。</span><span class="sxs-lookup"><span data-stu-id="461a8-181">If you would like to enable extension-based dialing through On-network conferencing, you can set up dial plans to match the extension dialing pattern to the phone number ranges of the phone number of your organization.</span></span> <span data-ttu-id="461a8-182">若要設定撥號方案，請參閱 [建立和管理撥號方案](create-and-manage-dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="461a8-182">To set up dial plans, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="461a8-183">相關主題</span><span class="sxs-lookup"><span data-stu-id="461a8-183">Related topics</span></span>


