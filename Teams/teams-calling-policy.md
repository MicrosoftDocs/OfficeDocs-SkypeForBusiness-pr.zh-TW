---
title: 在 Microsoft 團隊中呼叫原則
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中建立、修改及新增使用者至自訂通話原則，以及各種通話原則設定。
localization_priority: Normal
ms.custom:
- ms.teamsadmincenter.callingpolicies.overview
- seo-marvel-apr2020
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 030be626574e7acd3aa2116595acaba757eaa5af
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44942038"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="588df-103">在 Microsoft 團隊中呼叫原則</span><span class="sxs-lookup"><span data-stu-id="588df-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="588df-104">在 Microsoft 團隊中，通話原則控制使用者可以使用哪些通話和來電轉接功能。</span><span class="sxs-lookup"><span data-stu-id="588df-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="588df-105">通話原則決定使用者是否可以進行私人通話、使用來電轉接或同時撥打給其他使用者或外部電話號碼、將呼叫路由至語音信箱、傳送來電給通話群組、使用委派撥入和撥出通話等等。</span><span class="sxs-lookup"><span data-stu-id="588df-105">Calling policies determine whether a user can make private calls, use call forwarding or simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to call groups, use delegation for inbound and outbound calls, and so on.</span></span>

<span data-ttu-id="588df-106">您可以使用自動建立的全域（組織範圍預設值）原則，或建立及指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="588df-106">You can use the global (Org-wide default) policy that's created automatically or create and assign custom policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="588df-107">建立自訂通話原則</span><span class="sxs-lookup"><span data-stu-id="588df-107">Create a custom calling policy</span></span>

<span data-ttu-id="588df-108">請依照這些步驟來建立自訂通話原則。</span><span class="sxs-lookup"><span data-stu-id="588df-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="588df-109">在 Microsoft 團隊系統管理中心的左導覽中，移至**語音**  >  **通話原則**。</span><span class="sxs-lookup"><span data-stu-id="588df-109">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="588df-110">選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="588df-110">Select **Add**.</span></span>
3. <span data-ttu-id="588df-111">開啟或關閉您想要在通話原則中使用的功能。</span><span class="sxs-lookup"><span data-stu-id="588df-111">Turn on or turn off the features that you want to use in your calling policy.</span></span>
4. <span data-ttu-id="588df-112">若要控制使用者是否可以將來電路由到語音信箱，請選取 [**已啟用**] 或 [**使用者控制**]。</span><span class="sxs-lookup"><span data-stu-id="588df-112">To control whether users can route inbound calls to voicemail, select **Enabled** or **User controlled**.</span></span> <span data-ttu-id="588df-113">若要避免傳送語音信箱，請選取 [**停用**]。</span><span class="sxs-lookup"><span data-stu-id="588df-113">To prevent routing to voicemail, select **Disabled**.</span></span>
5. <span data-ttu-id="588df-114">選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="588df-114">Select **Save**.</span></span>

## <a name="edit-a-calling-policy"></a><span data-ttu-id="588df-115">編輯通話原則</span><span class="sxs-lookup"><span data-stu-id="588df-115">Edit a calling policy</span></span>

<span data-ttu-id="588df-116">請依照下列步驟編輯現有的通話原則。</span><span class="sxs-lookup"><span data-stu-id="588df-116">Follow these steps to edit an existing calling policy.</span></span>

1. <span data-ttu-id="588df-117">在 Microsoft [團隊管理中心] 的左導覽中，選取 [**語音**  >  **通話原則**]。</span><span class="sxs-lookup"><span data-stu-id="588df-117">In the left navigation of the Microsoft Teams admin center, select **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="588df-118">按一下您要修改的原則旁邊的，然後選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="588df-118">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="588df-119">進行您想要的變更，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="588df-119">Make the changes that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-calling-policy-to-users"></a><span data-ttu-id="588df-120">將自訂通話原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="588df-120">Assign a custom calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a><span data-ttu-id="588df-121">通話原則設定</span><span class="sxs-lookup"><span data-stu-id="588df-121">Calling policy settings</span></span>

<span data-ttu-id="588df-122">以下是您可以針對通話原則設定的設定。</span><span class="sxs-lookup"><span data-stu-id="588df-122">Here's the settings that you can configure for calling policies.</span></span>

### <a name="make-private-calls"></a><span data-ttu-id="588df-123">可進行私人通話</span><span class="sxs-lookup"><span data-stu-id="588df-123">Make private calls</span></span>

<span data-ttu-id="588df-124">此設定控制團隊中的所有通話功能。</span><span class="sxs-lookup"><span data-stu-id="588df-124">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="588df-125">關閉 [關閉] 以關閉小組中的所有通話功能。</span><span class="sxs-lookup"><span data-stu-id="588df-125">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a><span data-ttu-id="588df-126">來電轉接及同時撥打給組織中的人員</span><span class="sxs-lookup"><span data-stu-id="588df-126">Call forwarding and simultaneous ringing to people in your organization</span></span>

<span data-ttu-id="588df-127">此設定控制是否可將來電轉寄給其他使用者，或是同時撥打其他人。</span><span class="sxs-lookup"><span data-stu-id="588df-127">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="588df-128">來電轉接及同時撥打至外部電話號碼</span><span class="sxs-lookup"><span data-stu-id="588df-128">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="588df-129">此設定控制是否可將來電轉移至外部號碼，或同時撥打外部號碼。</span><span class="sxs-lookup"><span data-stu-id="588df-129">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls"></a><span data-ttu-id="588df-130">可傳送來電的語音信箱</span><span class="sxs-lookup"><span data-stu-id="588df-130">Voicemail is available for routing inbound calls</span></span>

<span data-ttu-id="588df-131">此設定可讓撥入呼叫傳送至語音信箱。</span><span class="sxs-lookup"><span data-stu-id="588df-131">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="588df-132">有效的選項包括：</span><span class="sxs-lookup"><span data-stu-id="588df-132">Valid options are:</span></span>

- <span data-ttu-id="588df-133">**已啟用**來電時，語音信箱總是可以使用。</span><span class="sxs-lookup"><span data-stu-id="588df-133">**Enabled** Voicemail is always available for inbound calls.</span></span>
- <span data-ttu-id="588df-134">**停用** 來電無法使用語音信箱。</span><span class="sxs-lookup"><span data-stu-id="588df-134">**Disabled**  Voicemail is not available for inbound calls.</span></span>
- <span data-ttu-id="588df-135">**使用者控制**使用者可以決定是否要使用語音信箱。</span><span class="sxs-lookup"><span data-stu-id="588df-135">**User controlled** Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="588df-136">輸入通話可以傳送給通話群組</span><span class="sxs-lookup"><span data-stu-id="588df-136">Inbound calls can be routed to call groups</span></span> 

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="588df-137">此設定控制是否可以將來電轉移到通話群組。</span><span class="sxs-lookup"><span data-stu-id="588df-137">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="588df-138">允許委派撥入和撥出通話</span><span class="sxs-lookup"><span data-stu-id="588df-138">Allow delegation for inbound and outbound calls</span></span>

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="588df-139">此設定可讓撥入呼叫路由至代理人，允許代理人代表他們擁有委派許可權的使用者撥出電話。</span><span class="sxs-lookup"><span data-stu-id="588df-139">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="588df-140">如需詳細資訊，請參閱[與代理人共用電話線路](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)。</span><span class="sxs-lookup"><span data-stu-id="588df-140">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="588df-141">透過 PSTN 避免付費旁路並傳送來電</span><span class="sxs-lookup"><span data-stu-id="588df-141">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="588df-142">將此設定為 [**開啟**] 會透過 PSTN 傳送呼叫並產生費用，而不是透過網路傳送通話，而是避開 tolls。</span><span class="sxs-lookup"><span data-stu-id="588df-142">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="588df-143">通話時可使用 [忙碌] 功能</span><span class="sxs-lookup"><span data-stu-id="588df-143">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="588df-144">繁忙（忙碌選項）是一種新的設定，可讓您設定當使用者已在通話或會議中，或有來電處於保留狀態時，處理來電的方式。</span><span class="sxs-lookup"><span data-stu-id="588df-144">Busy on Busy (Busy Options) is a new setting that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="588df-145">您可以使用占線信號拒絕新的或來電的通話。</span><span class="sxs-lookup"><span data-stu-id="588df-145">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="588df-146">您可以在租使用者層級或使用者層級啟用 busy 選項。</span><span class="sxs-lookup"><span data-stu-id="588df-146">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="588df-147">不論其忙碌選項的設定方式為何，通話或會議中的使用者，或使用保留通話的使用者，都不會阻止您開始新的通話或會議。</span><span class="sxs-lookup"><span data-stu-id="588df-147">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="588df-148">此設定預設為停用。</span><span class="sxs-lookup"><span data-stu-id="588df-148">This setting is disabled by default.</span></span>

### <a name="allow-web-pstn-calling"></a><span data-ttu-id="588df-149">允許網路 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="588df-149">Allow web PSTN calling</span></span>

<span data-ttu-id="588df-150">此設定可讓使用者使用團隊網頁用戶端呼叫 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="588df-150">This setting enables users to call PSTN numbers using the Teams web client.</span></span>

### <a name="allow-music-on-hold"></a><span data-ttu-id="588df-151">允許暫停音樂</span><span class="sxs-lookup"><span data-stu-id="588df-151">Allow music on hold</span></span>

<span data-ttu-id="588df-152">此設定可讓您在保留 PSTN 呼叫者時，開啟或關閉 [等候音樂]。</span><span class="sxs-lookup"><span data-stu-id="588df-152">This setting allows you to turn on or turn off music on hold when a PSTN caller is placed on hold.</span></span> <span data-ttu-id="588df-153">預設為開啟。</span><span class="sxs-lookup"><span data-stu-id="588df-153">It's turned on by default.</span></span> <span data-ttu-id="588df-154">此設定不適用於通話駐留和上司委派功能，目前僅可透過 PowerShell 取得。</span><span class="sxs-lookup"><span data-stu-id="588df-154">This setting doesn't apply to call park and boss delegate features, and is currently only available via PowerShell.</span></span>

## <a name="related-topics"></a><span data-ttu-id="588df-155">相關主題</span><span class="sxs-lookup"><span data-stu-id="588df-155">Related topics</span></span>

[<span data-ttu-id="588df-156">Set-CSTeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="588df-156">Set-CSTeamsCallingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[<span data-ttu-id="588df-157">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="588df-157">Assign policies to your users in Teams</span></span>](assign-policies.md)
