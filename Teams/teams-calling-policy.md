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
ms.openlocfilehash: 7a67952854f608512e88786c2b49d1e2ad8dfcf9
ms.sourcegitcommit: 184f4f61a3e739a1cfa533c6d95d405d887ea25d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/06/2020
ms.locfileid: "44593006"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="e323b-103">在 Microsoft 團隊中呼叫原則</span><span class="sxs-lookup"><span data-stu-id="e323b-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="e323b-104">在 Microsoft 團隊中，通話原則控制使用者可以使用哪些通話和來電轉接功能。</span><span class="sxs-lookup"><span data-stu-id="e323b-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="e323b-105">通話原則決定使用者是否可以進行私人通話、使用來電轉接或同時撥打給其他使用者或外部電話號碼、將呼叫路由至語音信箱、傳送來電給通話群組、使用委派撥入和撥出通話等等。</span><span class="sxs-lookup"><span data-stu-id="e323b-105">Calling policies determine whether a user can make private calls, use call forwarding or simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to Call Groups, use delegation for inbound and outbound calls, and so on.</span></span> <span data-ttu-id="e323b-106">預設的全域原則會自動建立，但系統管理員也可以建立並指派自訂通話原則。</span><span class="sxs-lookup"><span data-stu-id="e323b-106">A default global policy is created automatically, but admins can also create and assign custom calling policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="e323b-107">建立自訂通話原則</span><span class="sxs-lookup"><span data-stu-id="e323b-107">Create a custom calling policy</span></span>

<span data-ttu-id="e323b-108">請依照這些步驟來建立自訂通話原則。</span><span class="sxs-lookup"><span data-stu-id="e323b-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="e323b-109">在 Microsoft 團隊系統管理中心的左導覽中，移至**語音**  >  **通話原則**。</span><span class="sxs-lookup"><span data-stu-id="e323b-109">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="e323b-110">選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="e323b-110">Select **Add**.</span></span>
3. <span data-ttu-id="e323b-111">開啟或關閉您想要在通話原則中使用的功能。</span><span class="sxs-lookup"><span data-stu-id="e323b-111">Turn on or turn off the features that you want to use in your calling policy.</span></span>
4. <span data-ttu-id="e323b-112">若要控制使用者是否可以將來電路由到語音信箱，請選取 [**已啟用**] 或 [**使用者控制**]。</span><span class="sxs-lookup"><span data-stu-id="e323b-112">To control whether users can route inbound calls to voicemail, select **Enabled** or **User controlled**.</span></span> <span data-ttu-id="e323b-113">若要避免傳送語音信箱，請選取 [**停用**]。</span><span class="sxs-lookup"><span data-stu-id="e323b-113">To prevent routing to voicemail, select **Disabled**.</span></span>
5. <span data-ttu-id="e323b-114">選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="e323b-114">Select **Save**.</span></span>

## <a name="modify-an-existing-calling-policy"></a><span data-ttu-id="e323b-115">修改現有的通話原則</span><span class="sxs-lookup"><span data-stu-id="e323b-115">Modify an existing calling policy</span></span>

<span data-ttu-id="e323b-116">請依照這些步驟來修改現有的通話原則。</span><span class="sxs-lookup"><span data-stu-id="e323b-116">Follow these steps to modify an existing calling policy.</span></span>

1. <span data-ttu-id="e323b-117">在 Microsoft [團隊管理中心] 的左導覽中，選取 [**語音**  >  **通話原則**]。</span><span class="sxs-lookup"><span data-stu-id="e323b-117">In the left navigation of the Microsoft Teams admin center, select **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="e323b-118">按一下您要修改的原則旁邊的，然後選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="e323b-118">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="e323b-119">進行您想要的變更，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="e323b-119">Make the changes that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-calling-policy-to-users"></a><span data-ttu-id="e323b-120">將自訂通話原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="e323b-120">Assign a custom calling policy to users</span></span>

<span data-ttu-id="e323b-121">若要將原則指派給一個使用者：</span><span class="sxs-lookup"><span data-stu-id="e323b-121">To assign a policy to one user:</span></span>

1. <span data-ttu-id="e323b-122">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]\*\*\*\*，然後按一下該使用者。</span><span class="sxs-lookup"><span data-stu-id="e323b-122">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="e323b-123">按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e323b-123">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="e323b-124">在 [**呼叫原則**] 底下，選取您要指派的通話原則，然後**按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="e323b-124">Under **Calling policy**, select the calling policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="e323b-125">若要一次將原則指派給多位使用者：</span><span class="sxs-lookup"><span data-stu-id="e323b-125">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="e323b-126">在 Microsoft Teams 系統管理中心的左側瀏覽中，移至 [使用者]\*\*\*\*，然後搜尋使用者或篩選檢視畫面，以顯示您想要的使用者。</span><span class="sxs-lookup"><span data-stu-id="e323b-126">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="e323b-127">在 [&#x2713;]\*\*\*\* (核取方塊) 欄中，選取使用者。</span><span class="sxs-lookup"><span data-stu-id="e323b-127">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="e323b-128">若要選取 [所有使用者]，請按一下表格頂端的 [&#x2713;] (核取方塊)。</span><span class="sxs-lookup"><span data-stu-id="e323b-128">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="e323b-129">按一下 [編輯設定]\*\*\*\*，進行所需的變更，然後按一下 [套用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e323b-129">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="e323b-130">或者，您也可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e323b-130">Or, you can also do the following:</span></span>

1. <span data-ttu-id="e323b-131">在 Microsoft 團隊系統管理中心的左導覽中，移至**語音**  >  **通話原則**。</span><span class="sxs-lookup"><span data-stu-id="e323b-131">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="e323b-132">按一下原則名稱的左側來選取原則。</span><span class="sxs-lookup"><span data-stu-id="e323b-132">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="e323b-133">選取 [管理使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e323b-133">Select **Manage users**.</span></span>
4. <span data-ttu-id="e323b-134">在 **[管理使用者]** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="e323b-134">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="e323b-135">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="e323b-135">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="e323b-136">完成新增使用者之後，請選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="e323b-136">After you finish adding users, select **Save**.</span></span>

## <a name="calling-policy-settings"></a><span data-ttu-id="e323b-137">通話原則設定</span><span class="sxs-lookup"><span data-stu-id="e323b-137">Calling policy settings</span></span>

<span data-ttu-id="e323b-138">以下是您可以針對通話原則設定的設定。</span><span class="sxs-lookup"><span data-stu-id="e323b-138">Here's the settings that you can configure for calling policies.</span></span>

### <a name="make-private-calls"></a><span data-ttu-id="e323b-139">可進行私人通話</span><span class="sxs-lookup"><span data-stu-id="e323b-139">Make private calls</span></span>

<span data-ttu-id="e323b-140">此設定控制團隊中的所有通話功能。</span><span class="sxs-lookup"><span data-stu-id="e323b-140">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="e323b-141">關閉 [關閉] 以關閉小組中的所有通話功能。</span><span class="sxs-lookup"><span data-stu-id="e323b-141">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a><span data-ttu-id="e323b-142">來電轉接及同時撥打給組織中的人員</span><span class="sxs-lookup"><span data-stu-id="e323b-142">Call forwarding and simultaneous ringing to people in your organization</span></span>

<span data-ttu-id="e323b-143">此設定控制是否可將來電轉寄給其他使用者，或是同時撥打其他人。</span><span class="sxs-lookup"><span data-stu-id="e323b-143">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="e323b-144">來電轉接及同時撥打至外部電話號碼</span><span class="sxs-lookup"><span data-stu-id="e323b-144">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="e323b-145">此設定控制是否可將來電轉移至外部號碼，或同時撥打外部號碼。</span><span class="sxs-lookup"><span data-stu-id="e323b-145">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls"></a><span data-ttu-id="e323b-146">可傳送來電的語音信箱</span><span class="sxs-lookup"><span data-stu-id="e323b-146">Voicemail is available for routing inbound calls</span></span>

<span data-ttu-id="e323b-147">此設定可讓撥入呼叫傳送至語音信箱。</span><span class="sxs-lookup"><span data-stu-id="e323b-147">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="e323b-148">有效的選項包括：</span><span class="sxs-lookup"><span data-stu-id="e323b-148">Valid options are:</span></span>

- <span data-ttu-id="e323b-149">**已啟用**來電時，語音信箱總是可以使用。</span><span class="sxs-lookup"><span data-stu-id="e323b-149">**Enabled** Voicemail is always available for inbound calls.</span></span> 
- <span data-ttu-id="e323b-150">**停用** 來電無法使用語音信箱。</span><span class="sxs-lookup"><span data-stu-id="e323b-150">**Disabled**  Voicemail is not available for inbound calls.</span></span> 
- <span data-ttu-id="e323b-151">**使用者控制**使用者可以決定是否要使用語音信箱。</span><span class="sxs-lookup"><span data-stu-id="e323b-151">**User controlled** Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="e323b-152">輸入通話可以傳送給通話群組</span><span class="sxs-lookup"><span data-stu-id="e323b-152">Inbound calls can be routed to call groups</span></span> 

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="e323b-153">此設定控制是否可以將來電轉移到通話群組。</span><span class="sxs-lookup"><span data-stu-id="e323b-153">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="e323b-154">允許委派撥入和撥出通話</span><span class="sxs-lookup"><span data-stu-id="e323b-154">Allow delegation for inbound and outbound calls</span></span>

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="e323b-155">此設定可讓撥入呼叫路由至代理人，允許代理人代表他們擁有委派許可權的使用者撥出電話。</span><span class="sxs-lookup"><span data-stu-id="e323b-155">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="e323b-156">如需詳細資訊，請參閱[與代理人共用電話線路](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)。</span><span class="sxs-lookup"><span data-stu-id="e323b-156">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="e323b-157">透過 PSTN 避免付費旁路並傳送來電</span><span class="sxs-lookup"><span data-stu-id="e323b-157">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="e323b-158">將此設定為 [**開啟**] 會透過 PSTN 傳送呼叫並產生費用，而不是透過網路傳送通話，而是避開 tolls。</span><span class="sxs-lookup"><span data-stu-id="e323b-158">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="e323b-159">通話時可使用 [忙碌] 功能</span><span class="sxs-lookup"><span data-stu-id="e323b-159">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="e323b-160">繁忙（忙碌選項）是一種新的設定，可讓您設定當使用者已在通話或會議中，或有來電處於保留狀態時，處理來電的方式。</span><span class="sxs-lookup"><span data-stu-id="e323b-160">Busy on Busy (Busy Options) is a new setting that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="e323b-161">您可以使用占線信號拒絕新的或來電的通話。</span><span class="sxs-lookup"><span data-stu-id="e323b-161">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="e323b-162">您可以在租使用者層級或使用者層級啟用 busy 選項。</span><span class="sxs-lookup"><span data-stu-id="e323b-162">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="e323b-163">不論其忙碌選項的設定方式為何，通話或會議中的使用者，或使用保留通話的使用者，都不會阻止您開始新的通話或會議。</span><span class="sxs-lookup"><span data-stu-id="e323b-163">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="e323b-164">此設定預設為停用。</span><span class="sxs-lookup"><span data-stu-id="e323b-164">This setting is disabled by default.</span></span>

### <a name="allow-web-pstn-calling"></a><span data-ttu-id="e323b-165">允許網路 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="e323b-165">Allow web PSTN calling</span></span>

<span data-ttu-id="e323b-166">此設定可讓使用者使用團隊網頁用戶端呼叫 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="e323b-166">This setting enables users to call PSTN numbers using the Teams web client.</span></span>

### <a name="allow-music-on-hold"></a><span data-ttu-id="e323b-167">允許暫停音樂</span><span class="sxs-lookup"><span data-stu-id="e323b-167">Allow music on hold</span></span>

<span data-ttu-id="e323b-168">此設定可讓您在保留 PSTN 呼叫者時，開啟或關閉 [等候音樂]。</span><span class="sxs-lookup"><span data-stu-id="e323b-168">This setting allows you to turn on or turn off music on hold when a PSTN caller is placed on hold.</span></span> <span data-ttu-id="e323b-169">預設為開啟。</span><span class="sxs-lookup"><span data-stu-id="e323b-169">It's turned on by default.</span></span> <span data-ttu-id="e323b-170">此設定不適用於通話駐留和上司委派功能，目前僅可透過 PowerShell 取得。</span><span class="sxs-lookup"><span data-stu-id="e323b-170">This setting doesn't apply to call park and boss delegate features, and is currently only available via PowerShell.</span></span>

## <a name="see-also"></a><span data-ttu-id="e323b-171">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e323b-171">See also</span></span>

[<span data-ttu-id="e323b-172">Set-CSTeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="e323b-172">Set-CSTeamsCallingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)
