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
ms.openlocfilehash: 55efdc0c79f80a2a7b7ca44fd9c80481b163c63f
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868590"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="4d542-103">適用於 GCC High 和 DoD 的音訊會議搭配直接路由</span><span class="sxs-lookup"><span data-stu-id="4d542-103">Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="4d542-104">使用適用于 GCC 高和 DoD 之直接路由的音訊會議，可讓參與者透過電話裝置在您的 GCC 高或 DoD 組織中加入團隊會議。</span><span class="sxs-lookup"><span data-stu-id="4d542-104">Audio Conferencing with Direct Routing for GCC High and DoD enables participants to join Teams meetings in your GCC High or DoD organization by using a phone device.</span></span> <span data-ttu-id="4d542-105">會議參與者可能想要在案例中使用電話裝置加入小組會議，例如，當網際網路連線受到限制或使用者在路上且無法存取小組時。</span><span class="sxs-lookup"><span data-stu-id="4d542-105">Meeting participants might prefer to use a phone device to join Teams meetings in scenarios such as when internet connectivity is limited or when users are on the road and don't have access to Teams.</span></span> <span data-ttu-id="4d542-106">參與者可以選擇透過撥入您組織的撥入電話號碼，或將會議撥出到電話裝置，來加入會議。</span><span class="sxs-lookup"><span data-stu-id="4d542-106">Participants can choose to join meetings by either dialing in to a dial-in phone number for your organization or by having the meeting dial out to their phone device.</span></span>

<span data-ttu-id="4d542-107">透過使用具有直接路由的 GCC （適用于 GCC 高和 DoD），貴組織使用自己的號碼做為撥入電話號碼，而所有的會議撥出都是透過直接路由路由傳送給電話裝置。</span><span class="sxs-lookup"><span data-stu-id="4d542-107">With Audio Conferencing with Direct Routing for GCC High and DoD, your organization uses its own numbers as dial-in phone numbers and all meeting dial-outs to phone devices are routed via Direct Routing.</span></span> <span data-ttu-id="4d542-108">若要啟用服務，組織必須設定直接路由，並設定可做為撥入電話號碼的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="4d542-108">To enable the service, organizations need to set up Direct Routing and configure phone numbers that can be used as dial-in phone numbers.</span></span> <span data-ttu-id="4d542-109">使用直接路由的需求與提供給非 GCC 的高和非 DoD 組織（由 Microsoft 提供電話撥入式電話號碼）的音訊會議服務是不一樣的。</span><span class="sxs-lookup"><span data-stu-id="4d542-109">The requirement to use Direct Routing is different from the Audio Conferencing service that's offered to non-GCC High and non-DoD organizations where the dial-in phone numbers are provided by Microsoft.</span></span>

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="4d542-110">使用適用于 GCC 高和 DoD 的直接路由來部署音訊會議</span><span class="sxs-lookup"><span data-stu-id="4d542-110">Deploy Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a><span data-ttu-id="4d542-111">步驟1：使用適用于 GCC 高或 DoD 授權的直接路由取得音訊會議</span><span class="sxs-lookup"><span data-stu-id="4d542-111">Step 1: Get Audio Conferencing with Direct Routing for GCC High or DoD licenses</span></span> 

<span data-ttu-id="4d542-112">若要在 GCC 高或 DoD 中使用音訊會議，貴組織及貴組織中的使用者必須有指派直接傳送授權的音訊會議。</span><span class="sxs-lookup"><span data-stu-id="4d542-112">To use Audio Conferencing in GCC High or DoD, your organization and the users in your organization need to have an Audio Conferencing with Direct Routing license assigned.</span></span> <span data-ttu-id="4d542-113">以下是可使用適用于 GCC 高或 DoD 直接路由的音訊會議所需的授權。</span><span class="sxs-lookup"><span data-stu-id="4d542-113">Here are the licenses you need to enable Audio Conferencing with Direct Routing for GCC High or DoD.</span></span>

- <span data-ttu-id="4d542-114">GCC 高：適用于貴組織的音訊會議-GCC 高租使用者授權，以及音訊會議-適用于您的使用者的 GCC 高授權。</span><span class="sxs-lookup"><span data-stu-id="4d542-114">GCC High: An Audio Conferencing - GCC High Tenant license for your organization and Audio Conferencing - GCC High licenses for your users.</span></span>

- <span data-ttu-id="4d542-115">DoD：貴組織的音訊會議-DoD 租使用者授權，以及適用于您的使用者的音訊會議-DoD 授權。</span><span class="sxs-lookup"><span data-stu-id="4d542-115">DoD: An Audio Conferencing - DoD Tenant license for your organization and Audio Conferencing - DoD licenses for your users.</span></span>

<span data-ttu-id="4d542-116">您必須擁有租使用者授權，且至少需要一個使用者授權，才能啟用服務。</span><span class="sxs-lookup"><span data-stu-id="4d542-116">A tenant license and at least one user license are required to enable the service.</span></span> <span data-ttu-id="4d542-117">您無法啟用只有租使用者授權或只有使用者授權的服務。</span><span class="sxs-lookup"><span data-stu-id="4d542-117">You can't enable the service with only the tenant license or with only user licenses.</span></span> <span data-ttu-id="4d542-118">若要取得您的租使用者與您組織中的使用者服務授權，請與您的帳戶小組聯繫。</span><span class="sxs-lookup"><span data-stu-id="4d542-118">To get service licenses for your tenant and the users in your organization, contact your account team.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d542-119">在設定撥入電話號碼前，不能使用直接傳送的音訊會議來啟用使用者。</span><span class="sxs-lookup"><span data-stu-id="4d542-119">Users can't be enabled for Audio Conferencing with Direct Routing until dial-in phone numbers are set up.</span></span> <span data-ttu-id="4d542-120">我們建議您不要使用適用于 GCC 高或 DoD 授權給使用者的直接路由來指派音訊會議，直到您按照本文所述設定電話撥入式電話號碼。</span><span class="sxs-lookup"><span data-stu-id="4d542-120">We recommend that you not assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to users until you set up dial-in phone numbers as outlined in this article.</span></span>

### <a name="step-2-set-up-direct-routing"></a><span data-ttu-id="4d542-121">步驟2：設定直接路由</span><span class="sxs-lookup"><span data-stu-id="4d542-121">Step 2: Set up Direct Routing</span></span>

<span data-ttu-id="4d542-122">若要設定直接路由，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="4d542-122">To set up Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="4d542-123">規劃直接路由</span><span class="sxs-lookup"><span data-stu-id="4d542-123">Plan Direct Routing</span></span>](direct-routing-plan.md)

- [<span data-ttu-id="4d542-124">設定直接路由</span><span class="sxs-lookup"><span data-stu-id="4d542-124">Configure Direct Routing</span></span>](direct-routing-configure.md)

> [!NOTE]
> <span data-ttu-id="4d542-125">當您設定直接路由時，請記得使用這兩篇文章中所述的 GCC 高或 DoD 特定 Fqdn 和埠。</span><span class="sxs-lookup"><span data-stu-id="4d542-125">When you set up Direct Routing, remember to use the GCC High or DoD-specific FQDNs and ports that are described in these two articles.</span></span>

### <a name="step-3-set-up-dial-in-phone-numbers"></a><span data-ttu-id="4d542-126">步驟3：設定撥入電話號碼</span><span class="sxs-lookup"><span data-stu-id="4d542-126">Step 3: Set up dial-in phone numbers</span></span>

<span data-ttu-id="4d542-127">電話撥入式電話號碼是與您的音訊會議橋接器相關聯的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="4d542-127">Dial-in phone numbers are the phone numbers that are associated to your Audio Conferencing bridge.</span></span> <span data-ttu-id="4d542-128">參與者會使用這些數位來加入組織中使用者排程的會議。</span><span class="sxs-lookup"><span data-stu-id="4d542-128">These numbers are used by participants to join meetings scheduled by users in your organization.</span></span> <span data-ttu-id="4d542-129">在您的組織中，以及在 [尋找當地電話號碼] 頁面上排程會議的使用者，這些號碼也會包含在會議邀請中。</span><span class="sxs-lookup"><span data-stu-id="4d542-129">These numbers are also included in the meeting invites of the users who schedule meetings in your organization and on the "Find a local number" page.</span></span>

#### <a name="define-service-phone-numbers-in-your-tenant"></a><span data-ttu-id="4d542-130">在您的租使用者中定義服務電話號碼</span><span class="sxs-lookup"><span data-stu-id="4d542-130">Define service phone numbers in your tenant</span></span>

<span data-ttu-id="4d542-131">您可以使用 csHybridTelephoneNumber PowerShell Cmdlet 來定義您租使用者中的服務電話號碼，以透過直接路由將呼叫路由至音訊會議服務。</span><span class="sxs-lookup"><span data-stu-id="4d542-131">You can use the New-csHybridTelephoneNumber PowerShell cmdlet to define service phone numbers in your tenant that can be used to route calls to the Audio Conferencing service via Direct Routing.</span></span> 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

<span data-ttu-id="4d542-132">例如：</span><span class="sxs-lookup"><span data-stu-id="4d542-132">For example:</span></span>
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="4d542-133">將服務電話號碼指派給貴組織的音訊會議橋</span><span class="sxs-lookup"><span data-stu-id="4d542-133">Assign the service phone numbers to the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="4d542-134">您可以使用 csOnlineDialInConferencingServiceNumber PowerShell Cmdlet，將服務電話號碼指派給您組織的音訊會議橋。</span><span class="sxs-lookup"><span data-stu-id="4d542-134">You can assign service phone numbers to the Audio Conferencing bridge of your organization by using the Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet.</span></span>

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

<span data-ttu-id="4d542-135">您可以使用 CsOnlineDialInConferencingBridge 來查看音訊會議橋接器的 ID。</span><span class="sxs-lookup"><span data-stu-id="4d542-135">You can see the ID of your Audio Conferencing Bridge using Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="4d542-136">例如：</span><span class="sxs-lookup"><span data-stu-id="4d542-136">For example:</span></span>

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```

### <a name="step-4-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a><span data-ttu-id="4d542-137">步驟4：使用針對 GCC 高或 DoD 授權的直接路由指派音訊會議給您的使用者</span><span class="sxs-lookup"><span data-stu-id="4d542-137">Step 4: Assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your users</span></span>

<span data-ttu-id="4d542-138">若要為您的使用者指派可直接傳送給 GCC 高或 DoD 授權的音訊會議，請參閱[指派授權給使用者](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="4d542-138">To assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your user, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="step-5-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a><span data-ttu-id="4d542-139">步驟5：（選用）查看團隊中的音訊會議號碼清單</span><span class="sxs-lookup"><span data-stu-id="4d542-139">Step 5: (Optional) See a list of Audio Conferencing numbers in Teams</span></span>

<span data-ttu-id="4d542-140">若要查看貴組織的音訊會議號碼清單，請移至[在 Microsoft 團隊中查看音訊會議號碼清單](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="4d542-140">To see the list of Audio Conferencing numbers of your organization, go to [See a list of Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span></span>

### <a name="step-6-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a><span data-ttu-id="4d542-141">步驟6：（選用）為貴組織的音訊會議撥入號碼設定自動助理語言</span><span class="sxs-lookup"><span data-stu-id="4d542-141">Step 6: (Optional) Set auto attendant languages for the Audio Conferencing dial-in numbers of you organization</span></span>

<span data-ttu-id="4d542-142">若要變更貴組織之音訊會議撥入號碼的語言，請參閱[在 Microsoft 團隊中設定音訊會議的自動助理語言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="4d542-142">To change the languages of the Audio Conferencing dial-in numbers of your organization, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)</span></span>

### <a name="step-7-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="4d542-143">步驟7：（選用）變更組織的音訊會議橋設定</span><span class="sxs-lookup"><span data-stu-id="4d542-143">Step 7: (Optional) Change the settings of the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="4d542-144">若要變更貴組織的音訊會議橋設定，請參閱[變更音訊會議橋接器的設定](change-the-settings-for-an-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="4d542-144">To change the settings of the Audio Conferencing bridge of your organization, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md)</span></span>

### <a name="step-8-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a><span data-ttu-id="4d542-145">步驟8：（選用）設定您組織中的使用者在會議邀請中所包含的電話號碼</span><span class="sxs-lookup"><span data-stu-id="4d542-145">Step 8: (Optional) Set the phone numbers included in the meeting invites of the users in your organization</span></span>

<span data-ttu-id="4d542-146">若要變更您的組織在會議邀請中所包含的一組電話號碼，請參閱[在 Microsoft 團隊中設定邀請中包含的電話號碼](set-the-phone-numbers-included-on-invites-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="4d542-146">To change the set of phone numbers that are included in the meeting invites of the users is your organization, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md)</span></span>

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="4d542-147">在適用于 GCC 高和 DoD 的直接佈線中，音訊會議不支援音訊會議功能</span><span class="sxs-lookup"><span data-stu-id="4d542-147">Audio Conferencing capabilities not supported in Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="4d542-148">下列是在使用 GCC 高和 DoD 直接路由的音訊會議中不支援的音訊會議功能：</span><span class="sxs-lookup"><span data-stu-id="4d542-148">The following are Audio Conferencing capabilities that are not supported in Audio Conferencing with Direct Routing for GCC High and DoD:</span></span>

- <span data-ttu-id="4d542-149">使用名稱錄製進入及結束通知。</span><span class="sxs-lookup"><span data-stu-id="4d542-149">Entry and exit notifications using name recording.</span></span> <span data-ttu-id="4d542-150">對於有直接傳送的音訊會議，進入和結束通知會在會議中以鈴聲的方式播放。</span><span class="sxs-lookup"><span data-stu-id="4d542-150">For Audio Conferencing with Direct Routing, entry and exit notifications are played in the meeting as tones.</span></span>

- <span data-ttu-id="4d542-151">音訊會議的出站通話限制原則。</span><span class="sxs-lookup"><span data-stu-id="4d542-151">Outbound calling restriction policies for Audio Conferencing.</span></span> <span data-ttu-id="4d542-152">限制輸出呼叫的使用者層級控制措施不適用於透過直接路由路由的會議撥出通話。</span><span class="sxs-lookup"><span data-stu-id="4d542-152">User-level controls to restrict outbound calls aren't applicable to meeting dial-out calls routed via Direct Routing.</span></span>

- <span data-ttu-id="4d542-153">停用會議特定召集人的免付費電話號碼使用量。</span><span class="sxs-lookup"><span data-stu-id="4d542-153">Disable the usage of toll-free numbers for the meetings specific organizer.</span></span> <span data-ttu-id="4d542-154">限制使用免付費電話號碼以加入組織會議的使用者層級控制項，不適用於透過直接佈線進行路由的通話。</span><span class="sxs-lookup"><span data-stu-id="4d542-154">User-level controls to restrict the usage of toll-free numbers to join the meetings of your organization aren't applicable to calls routed via Direct Routing.</span></span>

- <span data-ttu-id="4d542-155">當使用者的設定變更時，傳送通知電子郵件給使用者。</span><span class="sxs-lookup"><span data-stu-id="4d542-155">Sending notification emails to users when their settings change.</span></span> <span data-ttu-id="4d542-156">使用適用于 GCC 高和 DoD 之直接路由的音訊會議，不支援音訊會議通知電子郵件。</span><span class="sxs-lookup"><span data-stu-id="4d542-156">Audio Conferencing notification emails aren't supported for Audio Conferencing with Direct Routing for GCC High and DoD.</span></span>
