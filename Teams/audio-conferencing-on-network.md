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
description: 下列說明音訊會議網內開啟預覽功能。
ms.openlocfilehash: d6df81cc077c69fdeb4246d682797d2ebb26b875
ms.sourcegitcommit: 950387da2a2c094b7580bcf81ae5d8b6dfba0d6b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/08/2021
ms.locfileid: "51637835"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a><span data-ttu-id="a9eb4-103">開啟音訊會議網路會議預覽</span><span class="sxs-lookup"><span data-stu-id="a9eb4-103">Open Preview of On-network Conferencing for Audio Conferencing</span></span>

<span data-ttu-id="a9eb4-104">網內會議開啟預覽版可供所有客戶使用。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-104">The Open Preview of On-network Conferencing is available to all customers.</span></span> <span data-ttu-id="a9eb4-105">網路會議可讓組織透過直接路由將輸入和輸出的音訊會議通話傳送至 Microsoft 撥入號碼。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-105">On-network Conferencing allows organizations to send inbound and outbound Audio Conferencing calls to Microsoft dial-in numbers through Direct Routing.</span></span> <span data-ttu-id="a9eb4-106">此功能並不適合將音訊會議的支援延伸到協力廠商撥入號碼。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-106">This capability is not intended to extend the support of Audio Conferencing to third party dial-in numbers.</span></span> <span data-ttu-id="a9eb4-107">如果網路會議是用來透過協力廠商撥入電話號碼或從 Microsoft 音訊會議橋接器撥出電話路由到 PSTN，則不支援網路會議。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-107">On-network Conferencing is not supported if it is used to route inbound calls to the Audio Conferencing service through third party dial-in phone numbers or outbound calls to the PSTN from Microsoft Audio Conferencing Bridge.</span></span> 

<span data-ttu-id="a9eb4-108">本文將說明為貴組織啟用網路會議的先決條件和組組步驟。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-108">This article describes the prerequisites and configuration steps required to enable On-network Conferencing for your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a9eb4-109">網路會議不得與印度的任何電話設備一起部署。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-109">On-network Conferencing must NOT be deployed with any telephony equipment in India.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="a9eb4-110">必要條件</span><span class="sxs-lookup"><span data-stu-id="a9eb4-110">Prerequisites</span></span>

<span data-ttu-id="a9eb4-111">在設置網路會議之前，請確定貴組織符合下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="a9eb4-111">Before configuring On-network Conferencing, make sure your organization meets the following prerequisites:</span></span> 

- <span data-ttu-id="a9eb4-112">請確保貴組織中已啟用或將會啟用音訊會議的所有使用者使用 Teams 進行所有會議。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-112">Ensure that all users in your organization who are enabled, or will be enabled, for Audio Conferencing are using Teams for all Meetings.</span></span> <span data-ttu-id="a9eb4-113">僅 Teams 會議支援透過網內會議傳送輸入和輸出音訊會議通話的路由。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-113">The routing of inbound and outbound Audio Conferencing calls through On-network Conferencing is only supported for Teams meetings.</span></span>

- <span data-ttu-id="a9eb4-114">指派音訊會議授權給將會使用網路會議的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-114">Assign Audio Conferencing licenses to all users who will be using On-network Conferencing.</span></span>

- <span data-ttu-id="a9eb4-115">設定音訊會議服務。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-115">Set up the Audio Conferencing service.</span></span> <span data-ttu-id="a9eb4-116">有關其他資訊，請參閱 [設定 Microsoft Teams 的音訊會議](set-up-audio-conferencing-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-116">For additional information, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span></span>

- <span data-ttu-id="a9eb4-117">設定會話邊界控制器 (SBC) 直接路由。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-117">Set up your Session Border Controller (SBC) for Direct Routing.</span></span> <span data-ttu-id="a9eb4-118">有關其他資訊，請參閱 [規劃直接路由](direct-routing-plan.md) 和 [設定直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-118">For additional information, see [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span> 

  <span data-ttu-id="a9eb4-119">如果您只針對音訊會議的目的設定直接路由，則只需要完成「步驟 1：連接您的 SBC」，才能進行網路會議。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-119">If you are setting up Direct Routing only for the purposes of Audio Conferencing, then you need only complete “Step 1: Connect your SBC” for On-network Conferencing.</span></span>
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a><span data-ttu-id="a9eb4-120">啟用透過直接路由將撥入式通話路由至 Microsoft 音訊會議</span><span class="sxs-lookup"><span data-stu-id="a9eb4-120">Enable the routing of dial-in calls to Microsoft Audio Conferencing through Direct Routing</span></span> 

<span data-ttu-id="a9eb4-121">若要透過直接路由，將內部部署使用者撥打的撥入電話路由至音訊會議服務，您必須為 SBC 和私人分支 Exchange (PBX)  (設定適當的路由規則) 。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-121">To route dial-in calls made by your on-premises users to the Audio Conferencing service through Direct Routing, you need to configure appropriate routing rules for your SBCs and Private Branch Exchange(s) (PBXs).</span></span>

<span data-ttu-id="a9eb4-122">您需要設定網站的電話設備，以透過直接路由主幹將通話路由到貴組織會議橋接器的任何服務號碼。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-122">You need to configure the telephony equipment of your sites to route calls to any service number of the conference bridge of your organization through a Direct Routing trunk.</span></span>

<span data-ttu-id="a9eb4-123">您可以在 Teams 系統管理中心的會議 **->** 會議橋接器下，或使用商務用 Skype Online PowerShell Cmdlet Get-CsOnlineDialInConferencingBridge 找到服務號碼。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-123">You can find the service numbers in Teams admin center under **Meetings -> Conferencing Bridges** or by using the Skype for Business Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="a9eb4-124">有關其他資訊，請參閱 Microsoft Teams 中的音訊 [會議號碼清單](see-a-list-of-audio-conferencing-numbers-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-124">For additional information, see a list of [Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a9eb4-125">此功能不適用於擁有每分鐘付費音訊會議授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-125">This feature is not available to users with the pay-per-minute Audio Conferencing license.</span></span>

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a><span data-ttu-id="a9eb4-126">透過直接路由啟用 Teams 會議撥出通話的路由</span><span class="sxs-lookup"><span data-stu-id="a9eb4-126">Enable the routing of Teams meeting dial-out calls through Direct Routing</span></span>

<span data-ttu-id="a9eb4-127">Teams 會議撥出電話會從您組織的會議內撥打 PSTN 號碼，包括電話-me-at 通話和通話，以將新參與者帶到會議。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-127">Teams meeting dial-out calls are initiated from within a meeting in your organization to PSTN numbers, including call-me-at calls and calls to bring new participants to a meeting.</span></span> 

<span data-ttu-id="a9eb4-128">若要透過直接路由將 Teams 會議撥出路由傳送給網路使用者，您必須建立並指派稱為「OnlineAudioConferencingRoutingPolicy」的音訊會議路由策略。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-128">To enable Teams meeting dial-out routing through Direct Routing to on-network users, you need to create and assign an Audio Conferencing routing policy called “OnlineAudioConferencingRoutingPolicy”.</span></span> 

<span data-ttu-id="a9eb4-129">OnlineAudioConferencingRoutingPolicy 政策相當於透過直接路由撥打 1：1 PSTN 通話的 CsOnlineVoiceRoutingPolicy。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-129">The OnlineAudioConferencingRoutingPolicy policy is equivalent to the CsOnlineVoiceRoutingPolicy for 1:1 PSTN calls via Direct Routing.</span></span> <span data-ttu-id="a9eb4-130">您可以使用下列 Cmdlet 管理 OnlineAudioConferencingRoutingPolicy 政策：</span><span class="sxs-lookup"><span data-stu-id="a9eb4-130">The OnlineAudioConferencingRoutingPolicy policy can be managed by using the following cmdlets:</span></span>

-   <span data-ttu-id="a9eb4-131">New-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="a9eb4-131">New-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="a9eb4-132">Set-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="a9eb4-132">Set-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="a9eb4-133">Get-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="a9eb4-133">Get-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="a9eb4-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="a9eb4-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="a9eb4-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="a9eb4-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span></span>

<span data-ttu-id="a9eb4-136">有關直接路由路由的路由詳細資訊，請參閱 [設定直接路由的語音路由](direct-routing-voice-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-136">For more information about routing for Direct Routing, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md).</span></span>


<span data-ttu-id="a9eb4-137">若要透過直接路由啟用會議撥出電話的路由，您必須：</span><span class="sxs-lookup"><span data-stu-id="a9eb4-137">To enable the routing of meeting dial-out calls through Direct Routing, you need to:</span></span> 

- <span data-ttu-id="a9eb4-138">設定音訊會議路由策略</span><span class="sxs-lookup"><span data-stu-id="a9eb4-138">Configure Audio Conferencing routing policies</span></span>
- <span data-ttu-id="a9eb4-139">在貴組織的電話設備上設定路由</span><span class="sxs-lookup"><span data-stu-id="a9eb4-139">Configure the routing on the telephony equipment of your organization</span></span>
- <span data-ttu-id="a9eb4-140"> (選) 設定撥號方案</span><span class="sxs-lookup"><span data-stu-id="a9eb4-140">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="a9eb4-141">Teams 會議的撥出電話來自會議橋接器上的預設服務號碼。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-141">Dial-out calls from Teams meetings are coming from the default service number on the conference bridge.</span></span> <span data-ttu-id="a9eb4-142">有關音訊會議橋接器預設服務號碼的其他資訊，請參閱變更音訊會議橋接器 [上的電話號碼](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-142">For additional information on the default service number of your Audio Conferencing bridge, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

### <a name="configure-audio-conferencing-routing-policies"></a><span data-ttu-id="a9eb4-143">設定音訊會議路由策略</span><span class="sxs-lookup"><span data-stu-id="a9eb4-143">Configure Audio Conferencing routing policies</span></span>

<span data-ttu-id="a9eb4-144">音訊會議路由策略 OnlineAudioConferencingRoutingPolicy 會決定哪些會議撥出電話會路由至直接路由主幹。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-144">The Audio Conferencing routing policy OnlineAudioConferencingRoutingPolicy determines which meeting dial-out calls are routed to Direct Routing trunks.</span></span> <span data-ttu-id="a9eb4-145">如果您熟悉 CsOnlineVoiceRoutingPolicy 政策，此政策運作方式非常類似。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-145">If you are familiar with the CsOnlineVoiceRoutingPolicy policy, this policy works in a very similar way.</span></span>

<span data-ttu-id="a9eb4-146">設定音訊會議路由策略需要下列步驟：</span><span class="sxs-lookup"><span data-stu-id="a9eb4-146">The following steps are needed to set up Audio Conferencing routing policies:</span></span>
1.  <span data-ttu-id="a9eb4-147">建立 PSTN 使用狀況</span><span class="sxs-lookup"><span data-stu-id="a9eb4-147">Create PSTN usages</span></span>
2.  <span data-ttu-id="a9eb4-148">設定語音路由</span><span class="sxs-lookup"><span data-stu-id="a9eb4-148">Configure voice routes</span></span>
3.  <span data-ttu-id="a9eb4-149">建立音訊會議語音路由策略</span><span class="sxs-lookup"><span data-stu-id="a9eb4-149">Create Audio Conferencing voice routing policies</span></span>
4.  <span data-ttu-id="a9eb4-150">指派策略給使用者</span><span class="sxs-lookup"><span data-stu-id="a9eb4-150">Assign a policy to your users</span></span>


#### <a name="create-pstn-usages"></a><span data-ttu-id="a9eb4-151">建立 PSTN 使用狀況</span><span class="sxs-lookup"><span data-stu-id="a9eb4-151">Create PSTN usages</span></span>

<span data-ttu-id="a9eb4-152">PSTN 使用量是語音路由的集合。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-152">PSTN usages are collections of voice routes.</span></span> <span data-ttu-id="a9eb4-153">當從特定召集人的會議啟動撥出通話時，語音路由會用來根據透過使用者的語音路由策略與使用者相關聯的 PSTN 使用方式，判斷通話的路由路徑。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-153">When a dial-out call is initiated from the meeting of a given organizer, voice routes will be used to determine the routing path of the call based on the PSTN usages that are associated to the user via the user’s voice routing policy.</span></span>

<span data-ttu-id="a9eb4-154">您可以使用 「Set-CsOnlinePstnUsage」 Cmdlet 建立 PSTN 使用量。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-154">You can create a PSTN usage by using the “Set-CsOnlinePstnUsage” cmdlet.</span></span> <span data-ttu-id="a9eb4-155">例如：</span><span class="sxs-lookup"><span data-stu-id="a9eb4-155">For Example:</span></span>

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a><span data-ttu-id="a9eb4-156">設定語音路由</span><span class="sxs-lookup"><span data-stu-id="a9eb4-156">Configure voice routes</span></span>

<span data-ttu-id="a9eb4-157">語音路由會根據 Teams 會議撥打的電話號碼，決定應該用來路由通話的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-157">Voice routes determine the PSTN gateway that should be used to route a call based on the phone number that is dialed from a Teams meeting.</span></span> <span data-ttu-id="a9eb4-158">語音路由會決定應該用來路由給定通話的 PSTN 閘道，方法就是將 Teams 會議撥打的電話號碼與 RegEx 模式比對。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-158">Voice routes determine the PSTN gateway that should be used to route a given call by matching the phone number dialed from a Teams meeting with a regex pattern.</span></span> <span data-ttu-id="a9eb4-159">建立語音路由時，路由必須與一或多個 PSTN 使用方式相關聯。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-159">When creating a voice route, the route must be associated to one or more PSTN usages.</span></span>

<span data-ttu-id="a9eb4-160">您可以使用 「New-CsOnlineVoiceRoute」Cmdlet 建立語音路由，並定義要與語音路由相關聯的 RegEx 和閘道。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-160">You can create a voice route and define the regex and gateways to be associated with the voice route by using the “New-CsOnlineVoiceRoute” cmdlet.</span></span> <span data-ttu-id="a9eb4-161">例如：</span><span class="sxs-lookup"><span data-stu-id="a9eb4-161">For Example:</span></span>

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a><span data-ttu-id="a9eb4-162">建立音訊會議語音路由策略</span><span class="sxs-lookup"><span data-stu-id="a9eb4-162">Create Audio Conferencing voice routing policies</span></span>

<span data-ttu-id="a9eb4-163">音訊會議語音路由策略會根據會議撥出通話的目標電話號碼，決定可用來路由來自會議召集人會議之通話的可能路由。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-163">Audio Conferencing voice routing policies determine the possible routes that can be used to route a call originating from the meetings of an organizer based on the target phone number of the meeting dial-out call.</span></span> <span data-ttu-id="a9eb4-164">音訊會議語音路由策略與一或多個 PSTN 使用方式相關聯，進而決定將嘗試用於與該策略相關聯的會議撥出通話的可能路由。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-164">Audio Conferencing voice routing policies are associated to one or more PSTN usages, which in turn, determine the possible routes that will be attempted to be used for the meeting dial-out calls of the organizers associated to the policy.</span></span>

<span data-ttu-id="a9eb4-165">您可以使用 「New- CsOnlineAudioConferencingRoutingPolicy」Cmdlet 來建立音訊會議語音路由策略。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-165">You can create an Audio Conferencing voice routing policy by using the “New- CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="a9eb4-166">例如：</span><span class="sxs-lookup"><span data-stu-id="a9eb4-166">For Example:</span></span>

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="a9eb4-167">將策略指派給使用者後，以及當從其中一個使用者的會議啟動會議撥出通話時，會評估透過使用者的語音路由策略與召集人相關聯的 PSTN 使用方式中的語音路由。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-167">After the policy is assigned to a user, and when a meeting dial-out call is initiated from one of the user's meetings, the voice routes in the PSTN usages that are associated to the organizer through the user's voice routing policy will be evaluated.</span></span> <span data-ttu-id="a9eb4-168">如果會議撥出通話目的地與與召集人相關聯的其中一個語音路由中的 RegEx 符合，會議撥出電話會路由至語音路由中定義的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-168">If the meeting dial-out call destination matches a regex in one of the voice routes that are associated to the organizer, the meeting dial-out call will be routed to the PSTN gateway defined in the voice route.</span></span> <span data-ttu-id="a9eb4-169">如果會議撥出通話目的地不符合任何與召集人相關聯的語音路由，會議撥出電話會由 Microsoft 路由。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-169">If the meeting dial-out call destination does not match any of the voice routes associated to the organizer, the meeting dial-out call will be routed by Microsoft.</span></span>

#### <a name="assign-a-policy-to-your-users"></a><span data-ttu-id="a9eb4-170">指派策略給使用者</span><span class="sxs-lookup"><span data-stu-id="a9eb4-170">Assign a policy to your users</span></span>

<span data-ttu-id="a9eb4-171">定義音訊會議路由策略之後，現在您可以將這些路由策略指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-171">After the Audio Conferencing routing policies are defined, you can now assign them to users.</span></span> <span data-ttu-id="a9eb4-172">將策略指派給他們之後，會議撥出電話會根據它進行評估，以決定其路由路徑。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-172">After policies are assigned to them, the meeting dial-out calls will be evaluated against it to determine their routing path.</span></span> <span data-ttu-id="a9eb4-173">音訊會議路由策略一定根據會議的召集人進行評估，與啟動會議撥出電話的會議使用者無關。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-173">Audio Conferencing routing policies are always evaluated based on the organizer of the meeting, independently from the user in the meeting that initiates a meeting dial-out call.</span></span>

<span data-ttu-id="a9eb4-174">您可以使用 「Grant-CsOnlineAudioConferencingRoutingPolicy」Cmdlet 將音訊會議語音路由策略指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-174">You can assign an Audio Conferencing voice routing policy to a user by using the “Grant-CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="a9eb4-175">例如：</span><span class="sxs-lookup"><span data-stu-id="a9eb4-175">For example:</span></span>

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a><span data-ttu-id="a9eb4-176">在貴組織的電話設備上設定路由</span><span class="sxs-lookup"><span data-stu-id="a9eb4-176">Configure routing on the telephony equipment of your organization</span></span>

<span data-ttu-id="a9eb4-177">在貴組織的電話設備上，您必須確保透過直接路由的會議撥出電話會路由至預定的網路目的地。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-177">On the telephony equipment of your organization, you need to ensure that the meeting dial-out calls routed through Direct Routing are routed to the intended on-network destination.</span></span>


### <a name="optional-configure-a-dial-plan"></a><span data-ttu-id="a9eb4-178"> (選) 設定撥號方案</span><span class="sxs-lookup"><span data-stu-id="a9eb4-178">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="a9eb4-179">撥號方案是一組標準化規則，將個別使用者撥打的電話號碼轉換成替代格式 (通常是 E.164) ，用於通話授權和呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-179">A dial plan is a set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="a9eb4-180">根據預設，Teams 使用者可以以 E.164 格式撥入 PSTN 號碼，即 + \<country code\> \<number\> 。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-180">By default, Teams users can dial-out to PSTN numbers in E.164 format, that is, +\<country code\>\<number\>.</span></span> <span data-ttu-id="a9eb4-181">不過，撥號方案可用來允許使用者以其他格式撥打電話號碼，例如 4 位數的分機號碼。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-181">However, dial plans can be used to allow users to dial phone numbers in other formats, for instance 4-digit extensions.</span></span>

<span data-ttu-id="a9eb4-182">如果您想要透過網內會議啟用分機式撥號，您可以設定撥號方案，讓分機撥號模式符合貴組織電話號碼的電話號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-182">If you would like to enable extension-based dialing through On-network conferencing, you can set up dial plans to match the extension dialing pattern to the phone number ranges of the phone number of your organization.</span></span> <span data-ttu-id="a9eb4-183">若要設定撥號方案，請參閱 [建立和管理撥號方案](create-and-manage-dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-183">To set up dial plans, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>


## <a name="known-issues-in-open-preview"></a><span data-ttu-id="a9eb4-184">Open Preview 中的已知問題</span><span class="sxs-lookup"><span data-stu-id="a9eb4-184">Known issues in Open Preview</span></span>

<span data-ttu-id="a9eb4-185">以下是目前線上會議 Open Preview 版本中的已知問題清單。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-185">The following is a list of known issues that are currently present in the Open Preview release of On-network conferencing.</span></span> <span data-ttu-id="a9eb4-186">Microsoft 正在努力解決這些問題。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-186">Microsoft is working on addressing these issues.</span></span>

| <span data-ttu-id="a9eb4-187">問題</span><span class="sxs-lookup"><span data-stu-id="a9eb4-187">Issue</span></span> | <span data-ttu-id="a9eb4-188">解決 方案</span><span class="sxs-lookup"><span data-stu-id="a9eb4-188">Workaround</span></span> |
| :--- | :--- |
| <span data-ttu-id="a9eb4-189">透過網路會議路由的匿名/隱藏本機號碼電話無法連接到會議。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-189">Dial-in calls with anonymous/hidden caller IDs that are routed through On-network conferencing cannot be connected to the meeting.</span></span> | <span data-ttu-id="a9eb4-190">如果可能的話，在 PBX 或 SBC 中設定設定，一直傳送本機號碼給透過網路會議路由的來電。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-190">If possible, set a configuration in your PBX or SBC to always send a caller ID for calls routed via On-network conferencing.</span></span>|
| <span data-ttu-id="a9eb4-191">在某些情況下，當使用者撥入服務時播放的歡迎訊息 (「歡迎使用音訊會議服務...」) 會截斷，而且使用者不會聽到「歡迎」一詞。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-191">In some cases, the welcome message that is played to users when they dial in to the service (“Welcome to the Audio Conferencing service…”) is truncated and users do not hear the “Welcome” word.</span></span>| <span data-ttu-id="a9eb4-192">目前沒有此問題的解決方法。</span><span class="sxs-lookup"><span data-stu-id="a9eb4-192">There are no workarounds for this issue at the moment.</span></span> |




## <a name="related-topics"></a><span data-ttu-id="a9eb4-193">相關主題</span><span class="sxs-lookup"><span data-stu-id="a9eb4-193">Related topics</span></span>


