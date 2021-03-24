---
title: Microsoft Teams 中的通話政策
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams 中建立、修改及新增使用者至自訂通話策略，以及各種通話策略設定。
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callingpolicies.overview
- seo-marvel-apr2020
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5e3cc466d855f55f63f34e798443fb285dc36c9e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51162698"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="c625c-103">Microsoft Teams 中的通話政策</span><span class="sxs-lookup"><span data-stu-id="c625c-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="c625c-104">在 Microsoft Teams 中，通話政策會控制哪些通話和呼叫轉呼叫功能可供使用者使用。</span><span class="sxs-lookup"><span data-stu-id="c625c-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="c625c-105">通話政策會決定使用者是否可以撥打私人電話、使用呼叫轉寄或同時撥打給其他使用者或外部電話號碼、將通話路由至語音信箱、將通話傳送給通話群組、使用委派進行輸入和外寄通話等等。</span><span class="sxs-lookup"><span data-stu-id="c625c-105">Calling policies determine whether a user can make private calls, use call forwarding or simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to call groups, use delegation for inbound and outbound calls, and so on.</span></span>

<span data-ttu-id="c625c-106">您可以使用自動建立 (全組織的預設) ，或建立及指派自訂策略。</span><span class="sxs-lookup"><span data-stu-id="c625c-106">You can use the global (Org-wide default) policy that's created automatically or create and assign custom policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="c625c-107">建立自訂通話策略</span><span class="sxs-lookup"><span data-stu-id="c625c-107">Create a custom calling policy</span></span>

<span data-ttu-id="c625c-108">請遵循下列步驟建立自訂通話策略。</span><span class="sxs-lookup"><span data-stu-id="c625c-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="c625c-109">在 Microsoft Teams 系統管理中心的左側流覽中，前往 **語音**  >  **通話政策**。</span><span class="sxs-lookup"><span data-stu-id="c625c-109">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="c625c-110">選取 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="c625c-110">Select **Add**.</span></span>
3. <span data-ttu-id="c625c-111">開啟或關閉您想要在通話政策中使用的功能。</span><span class="sxs-lookup"><span data-stu-id="c625c-111">Turn on or turn off the features that you want to use in your calling policy.</span></span>
4. <span data-ttu-id="c625c-112">若要控制使用者是否可以將輸入通話路由至語音信箱， **請選取** 啟用或 **使用者控制**。</span><span class="sxs-lookup"><span data-stu-id="c625c-112">To control whether users can route inbound calls to voicemail, select **Enabled** or **User controlled**.</span></span> <span data-ttu-id="c625c-113">若要防止路由至語音信箱，請選取 **已停用**。</span><span class="sxs-lookup"><span data-stu-id="c625c-113">To prevent routing to voicemail, select **Disabled**.</span></span>
5. <span data-ttu-id="c625c-114">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="c625c-114">Select **Save**.</span></span>

## <a name="edit-a-calling-policy"></a><span data-ttu-id="c625c-115">編輯通話政策</span><span class="sxs-lookup"><span data-stu-id="c625c-115">Edit a calling policy</span></span>

<span data-ttu-id="c625c-116">請遵循這些步驟來編輯現有的通話政策。</span><span class="sxs-lookup"><span data-stu-id="c625c-116">Follow these steps to edit an existing calling policy.</span></span>

1. <span data-ttu-id="c625c-117">在 Microsoft Teams 系統管理中心的左側流覽中，選取 **語音**  >  **通話政策**。</span><span class="sxs-lookup"><span data-stu-id="c625c-117">In the left navigation of the Microsoft Teams admin center, select **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="c625c-118">按一下要修改之政策旁的 ，然後選取 [ **編輯**。</span><span class="sxs-lookup"><span data-stu-id="c625c-118">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="c625c-119">進行您想要的變更，然後按一下 [ **儲存**。</span><span class="sxs-lookup"><span data-stu-id="c625c-119">Make the changes that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-calling-policy-to-users"></a><span data-ttu-id="c625c-120">指派自訂通話策略給使用者</span><span class="sxs-lookup"><span data-stu-id="c625c-120">Assign a custom calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a><span data-ttu-id="c625c-121">通話策略設定</span><span class="sxs-lookup"><span data-stu-id="c625c-121">Calling policy settings</span></span>

<span data-ttu-id="c625c-122">以下是您可以針對通話策略所設定設定。</span><span class="sxs-lookup"><span data-stu-id="c625c-122">Here's the settings that you can configure for calling policies.</span></span>

### <a name="make-private-calls"></a><span data-ttu-id="c625c-123">可進行私人通話</span><span class="sxs-lookup"><span data-stu-id="c625c-123">Make private calls</span></span>

<span data-ttu-id="c625c-124">此設定控制 Teams 中所有的通話功能。</span><span class="sxs-lookup"><span data-stu-id="c625c-124">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="c625c-125">關閉此功能以關閉 Teams 中所有的通話功能。</span><span class="sxs-lookup"><span data-stu-id="c625c-125">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a><span data-ttu-id="c625c-126">呼叫轉譯和同時撥打給貴組織人員</span><span class="sxs-lookup"><span data-stu-id="c625c-126">Call forwarding and simultaneous ringing to people in your organization</span></span>

<span data-ttu-id="c625c-127">此設定可控制來電是否可以轉往其他使用者，或可以同時撥打給其他人。</span><span class="sxs-lookup"><span data-stu-id="c625c-127">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="c625c-128">呼叫轉轉和同時撥打到外部電話號碼</span><span class="sxs-lookup"><span data-stu-id="c625c-128">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="c625c-129">此設定可控制來電是否可以轉往外部號碼，或是否可以同時撥打外部號碼。</span><span class="sxs-lookup"><span data-stu-id="c625c-129">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls"></a><span data-ttu-id="c625c-130">語音信箱可用於路由輸入通話</span><span class="sxs-lookup"><span data-stu-id="c625c-130">Voicemail is available for routing inbound calls</span></span>

<span data-ttu-id="c625c-131">此設定可讓您將來電傳入語音信箱。</span><span class="sxs-lookup"><span data-stu-id="c625c-131">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="c625c-132">有效的選項為：</span><span class="sxs-lookup"><span data-stu-id="c625c-132">Valid options are:</span></span>

- <span data-ttu-id="c625c-133">**已啟用** 語音信箱隨時可供輸入通話使用。</span><span class="sxs-lookup"><span data-stu-id="c625c-133">**Enabled** Voicemail is always available for inbound calls.</span></span>
- <span data-ttu-id="c625c-134">**已停用**  語音信箱不適用於來電。</span><span class="sxs-lookup"><span data-stu-id="c625c-134">**Disabled**  Voicemail is not available for inbound calls.</span></span>
- <span data-ttu-id="c625c-135">**使用者控制** 使用者可以決定是否想要語音信箱可用。</span><span class="sxs-lookup"><span data-stu-id="c625c-135">**User controlled** Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="c625c-136">可路由來電至通話群組</span><span class="sxs-lookup"><span data-stu-id="c625c-136">Inbound calls can be routed to call groups</span></span> 

<span data-ttu-id="c625c-137">此設定會控制是否可以將來電轉往通話群組。</span><span class="sxs-lookup"><span data-stu-id="c625c-137">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="c625c-138">允許委派傳入和外接通話</span><span class="sxs-lookup"><span data-stu-id="c625c-138">Allow delegation for inbound and outbound calls</span></span>

<span data-ttu-id="c625c-139">此設定可讓來電路由至代理人，允許代理人代表他們擁有委派許可權的使用者進行外接通話。</span><span class="sxs-lookup"><span data-stu-id="c625c-139">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="c625c-140">詳細資訊，請參閱 [與代理人共用電話線](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)。</span><span class="sxs-lookup"><span data-stu-id="c625c-140">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="c625c-141">防止免付費，並透過 PSTN 傳送通話</span><span class="sxs-lookup"><span data-stu-id="c625c-141">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="c625c-142">將此選項設定為 **[開** 」 會透過 PSTN 傳送通話，並產生費用，而不是透過網路傳送電話並忽略付費。</span><span class="sxs-lookup"><span data-stu-id="c625c-142">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="c625c-143">通話時可在忙碌中忙碌</span><span class="sxs-lookup"><span data-stu-id="c625c-143">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="c625c-144">在忙碌 (忙碌選項) 是一個新的設定，可讓您設定當使用者已經在通話或會議或保留通話時如何處理來電。</span><span class="sxs-lookup"><span data-stu-id="c625c-144">Busy on Busy (Busy Options) is a new setting that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="c625c-145">新的或來電可能會以忙碌訊號拒絕。</span><span class="sxs-lookup"><span data-stu-id="c625c-145">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="c625c-146">您可以在租使用者層級或使用者層級啟用忙碌選項。</span><span class="sxs-lookup"><span data-stu-id="c625c-146">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="c625c-147">無論其忙碌選項的組組方式如何，通話或會議中的使用者或保留通話的使用者，都不得啟動新的通話或會議。</span><span class="sxs-lookup"><span data-stu-id="c625c-147">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="c625c-148">此設定預設為停用。</span><span class="sxs-lookup"><span data-stu-id="c625c-148">This setting is disabled by default.</span></span>

### <a name="allow-web-pstn-calling"></a><span data-ttu-id="c625c-149">允許 Web PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="c625c-149">Allow web PSTN calling</span></span>

<span data-ttu-id="c625c-150">此設定可讓使用者使用 Teams Web 用戶端撥打 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="c625c-150">This setting enables users to call PSTN numbers using the Teams web client.</span></span>

### <a name="allow-music-on-hold"></a><span data-ttu-id="c625c-151">允許等候音樂</span><span class="sxs-lookup"><span data-stu-id="c625c-151">Allow music on hold</span></span>

<span data-ttu-id="c625c-152">這項設定可讓您在 PSTN 來電者處於保留狀態時開啟或關閉等候音樂。</span><span class="sxs-lookup"><span data-stu-id="c625c-152">This setting allows you to turn on or turn off music on hold when a PSTN caller is placed on hold.</span></span> <span data-ttu-id="c625c-153">預設為開啟。</span><span class="sxs-lookup"><span data-stu-id="c625c-153">It's turned on by default.</span></span> <span data-ttu-id="c625c-154">此設定不適用於通話駐場和老闆代理人功能，目前僅能透過 PowerShell 使用。</span><span class="sxs-lookup"><span data-stu-id="c625c-154">This setting doesn't apply to call park and boss delegate features, and is currently only available via PowerShell.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c625c-155">相關主題</span><span class="sxs-lookup"><span data-stu-id="c625c-155">Related topics</span></span>

[<span data-ttu-id="c625c-156">Set-CSTeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="c625c-156">Set-CSTeamsCallingPolicy</span></span>](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[<span data-ttu-id="c625c-157">在 Teams 中將原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="c625c-157">Assign policies to your users in Teams</span></span>](assign-policies.md)