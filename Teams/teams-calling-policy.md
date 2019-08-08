---
title: 在 Microsoft 團隊中呼叫原則
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 05/06/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中呼叫原則設定。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5c94a8c9ff9c1eef2017cf70d69a2308f5c94db6
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243850"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="53bf8-103">在 Microsoft 團隊中呼叫原則</span><span class="sxs-lookup"><span data-stu-id="53bf8-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="53bf8-104">在 Microsoft 團隊中, 通話原則控制使用者可以使用哪些通話和來電轉接功能。</span><span class="sxs-lookup"><span data-stu-id="53bf8-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="53bf8-105">通話原則決定使用者是否可以進行私人通話、使用來電轉接或同時撥打給其他使用者或外部電話號碼、將呼叫路由至語音信箱、傳送來電給通話群組、使用委派撥入和撥出通話等等。</span><span class="sxs-lookup"><span data-stu-id="53bf8-105">Calling policies determine whether a user can make private calls, use call forwarding or  simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to Call Groups, use delegation for inbound and outbound calls, and so on.</span></span> <span data-ttu-id="53bf8-106">預設的全域原則會自動建立, 但系統管理員也可以建立並指派自訂通話原則。</span><span class="sxs-lookup"><span data-stu-id="53bf8-106">A default global policy is created automatically, but admins can also create and assign custom calling policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="53bf8-107">建立自訂通話原則</span><span class="sxs-lookup"><span data-stu-id="53bf8-107">Create a custom calling policy</span></span>

<span data-ttu-id="53bf8-108">請依照這些步驟來建立自訂通話原則。</span><span class="sxs-lookup"><span data-stu-id="53bf8-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="53bf8-109">在 Microsoft [團隊管理中心] 中, 選取 [**語音** > **通話原則**]。</span><span class="sxs-lookup"><span data-stu-id="53bf8-109">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="53bf8-110">選取 [**新增原則**]。</span><span class="sxs-lookup"><span data-stu-id="53bf8-110">Select **New policy**.</span></span>
3. <span data-ttu-id="53bf8-111">開啟您想要在通話原則中使用的功能。</span><span class="sxs-lookup"><span data-stu-id="53bf8-111">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="53bf8-112">所有選取專案預設都是**關閉**的。</span><span class="sxs-lookup"><span data-stu-id="53bf8-112">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="53bf8-113">若要控制使用者是否可以將來電路由到語音信箱, 請選取 [**永遠啟用**] 或 [**使用者控制**]。</span><span class="sxs-lookup"><span data-stu-id="53bf8-113">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="53bf8-114">若要避免傳送語音信箱, 請選取 [**永遠停用**]。</span><span class="sxs-lookup"><span data-stu-id="53bf8-114">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="53bf8-115">選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="53bf8-115">Select **Save**.</span></span>

## <a name="modify-an-existing-calling-policy"></a><span data-ttu-id="53bf8-116">修改現有的通話原則</span><span class="sxs-lookup"><span data-stu-id="53bf8-116">Modify an existing calling policy</span></span>

<span data-ttu-id="53bf8-117">請依照這些步驟來修改現有的通話原則。</span><span class="sxs-lookup"><span data-stu-id="53bf8-117">Follow these steps to modify an existing calling policy.</span></span>

1. <span data-ttu-id="53bf8-118">在 Microsoft [團隊管理中心] 中, 選取 [**語音** > **通話原則**]。</span><span class="sxs-lookup"><span data-stu-id="53bf8-118">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="53bf8-119">按一下您要修改的原則旁邊的, 然後選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="53bf8-119">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="53bf8-120">開啟您想要在通話原則中使用的功能。</span><span class="sxs-lookup"><span data-stu-id="53bf8-120">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="53bf8-121">所有選取專案預設都是**關閉**的。</span><span class="sxs-lookup"><span data-stu-id="53bf8-121">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="53bf8-122">若要控制使用者是否可以將來電路由到語音信箱, 請選取 [**永遠啟用**] 或 [**使用者控制**]。</span><span class="sxs-lookup"><span data-stu-id="53bf8-122">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="53bf8-123">若要避免傳送語音信箱, 請選取 [**永遠停用**]。</span><span class="sxs-lookup"><span data-stu-id="53bf8-123">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="53bf8-124">選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="53bf8-124">Select **Save**.</span></span>

## <a name="assign-a-calling-policy-to-a-user"></a><span data-ttu-id="53bf8-125">指派通話原則給使用者</span><span class="sxs-lookup"><span data-stu-id="53bf8-125">Assign a calling policy to a user</span></span>

<span data-ttu-id="53bf8-126">請依照下列步驟, 將自訂通話原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="53bf8-126">Follow these steps to assign a custom calling policy to a user.</span></span>

1. <span data-ttu-id="53bf8-127">在 Microsoft [團隊管理中心] 中, 選取 [**語音** > **通話原則**]。</span><span class="sxs-lookup"><span data-stu-id="53bf8-127">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="53bf8-128">按一下 [原則名稱] 旁的, 選取它, 然後選取 [**管理使用者**]。</span><span class="sxs-lookup"><span data-stu-id="53bf8-128">Click next to the policy name to select it, and then select **Manage users**.</span></span>
3. <span data-ttu-id="53bf8-129">在 [**管理使用者**] 窗格中, 搜尋使用者的名稱。</span><span class="sxs-lookup"><span data-stu-id="53bf8-129">In the **Manage users** pane, search for the user’s name.</span></span> <span data-ttu-id="53bf8-130">(您必須至少輸入三個字元。)</span><span class="sxs-lookup"><span data-stu-id="53bf8-130">(You must enter at least three characters.)</span></span>
4. <span data-ttu-id="53bf8-131">選取使用者的名稱, 然後選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="53bf8-131">Select the user’s name, and then select **Add**.</span></span>
5. <span data-ttu-id="53bf8-132">選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="53bf8-132">Select **Save**.</span></span>

## <a name="calling-policy-settings"></a><span data-ttu-id="53bf8-133">通話原則設定</span><span class="sxs-lookup"><span data-stu-id="53bf8-133">Calling policy settings</span></span>

<span data-ttu-id="53bf8-134">使用下列設定來建立自訂通話原則。</span><span class="sxs-lookup"><span data-stu-id="53bf8-134">Use the following settings to create a custom calling policy.</span></span>

### <a name="user-can-make-private-calls"></a><span data-ttu-id="53bf8-135">使用者可以撥打私人電話</span><span class="sxs-lookup"><span data-stu-id="53bf8-135">User can make private calls</span></span>

<span data-ttu-id="53bf8-136">此設定控制團隊中的所有通話功能。</span><span class="sxs-lookup"><span data-stu-id="53bf8-136">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="53bf8-137">關閉 [關閉] 以關閉小組中的所有通話功能。</span><span class="sxs-lookup"><span data-stu-id="53bf8-137">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-other-users"></a><span data-ttu-id="53bf8-138">來電轉接及同時撥打給其他使用者</span><span class="sxs-lookup"><span data-stu-id="53bf8-138">Call forwarding and simultaneous ringing to other users</span></span>

<span data-ttu-id="53bf8-139">此設定控制是否可將來電轉寄給其他使用者, 或是同時撥打其他人。</span><span class="sxs-lookup"><span data-stu-id="53bf8-139">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="53bf8-140">來電轉接及同時撥打至外部電話號碼</span><span class="sxs-lookup"><span data-stu-id="53bf8-140">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="53bf8-141">此設定控制是否可將來電轉移至外部號碼, 或同時撥打外部號碼。</span><span class="sxs-lookup"><span data-stu-id="53bf8-141">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls-to-users"></a><span data-ttu-id="53bf8-142">[語音信箱] 可用於傳送來電給使用者</span><span class="sxs-lookup"><span data-stu-id="53bf8-142">Voicemail is available for routing inbound calls to users</span></span>

<span data-ttu-id="53bf8-143">此設定可讓撥入呼叫傳送至語音信箱。</span><span class="sxs-lookup"><span data-stu-id="53bf8-143">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="53bf8-144">有效的選項包括:</span><span class="sxs-lookup"><span data-stu-id="53bf8-144">Valid options are:</span></span>

   - <span data-ttu-id="53bf8-145">**永遠啟用**來電時, 語音信箱總是可以使用。</span><span class="sxs-lookup"><span data-stu-id="53bf8-145">**Always enabled** Voicemail is always available for inbound calls.</span></span> 
   - <span data-ttu-id="53bf8-146">**永遠停用** 來電無法使用語音信箱。</span><span class="sxs-lookup"><span data-stu-id="53bf8-146">**Always disabled**  Voicemail is not available for inbound calls.</span></span> 
   - <span data-ttu-id="53bf8-147">**使用者控制**。</span><span class="sxs-lookup"><span data-stu-id="53bf8-147">**User controlled**.</span></span> <span data-ttu-id="53bf8-148">使用者可以決定是否要使用語音信箱。</span><span class="sxs-lookup"><span data-stu-id="53bf8-148">Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="53bf8-149">輸入通話可以傳送給通話群組</span><span class="sxs-lookup"><span data-stu-id="53bf8-149">Inbound calls can be routed to call groups</span></span> 

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="53bf8-150">此設定控制是否可以將來電轉移到通話群組。</span><span class="sxs-lookup"><span data-stu-id="53bf8-150">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="53bf8-151">允許委派撥入和撥出通話</span><span class="sxs-lookup"><span data-stu-id="53bf8-151">Allow delegation for inbound and outbound calls</span></span>

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="53bf8-152">此設定可讓撥入呼叫路由至代理人, 允許代理人代表他們擁有委派許可權的使用者撥出電話。</span><span class="sxs-lookup"><span data-stu-id="53bf8-152">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="53bf8-153">如需詳細資訊, 請參閱[與代理人共用電話線路](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)。</span><span class="sxs-lookup"><span data-stu-id="53bf8-153">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>


### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="53bf8-154">透過 PSTN 避免付費旁路並傳送來電</span><span class="sxs-lookup"><span data-stu-id="53bf8-154">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="53bf8-155">將此設定為 [**開啟**] 會透過 PSTN 傳送呼叫並產生費用, 而不是透過網路傳送通話, 而是避開 tolls。</span><span class="sxs-lookup"><span data-stu-id="53bf8-155">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="53bf8-156">通話時可使用 [忙碌] 功能</span><span class="sxs-lookup"><span data-stu-id="53bf8-156">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="53bf8-157">繁忙 (忙選項)) 是小組通話原則中的新設定, 可讓您設定當使用者已在通話或會議中, 或有來電處於保留狀態時, 處理來電的方式。</span><span class="sxs-lookup"><span data-stu-id="53bf8-157">Busy on Busy (Busy Options)) is a new setting in Teams calling policies that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="53bf8-158">您可以使用占線信號拒絕新的或來電的通話。</span><span class="sxs-lookup"><span data-stu-id="53bf8-158">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="53bf8-159">您可以在租使用者層級或使用者層級啟用 busy 選項。</span><span class="sxs-lookup"><span data-stu-id="53bf8-159">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="53bf8-160">不論其忙碌選項的設定方式為何, 通話或會議中的使用者, 或使用保留通話的使用者, 都不會阻止您開始新的通話或會議。</span><span class="sxs-lookup"><span data-stu-id="53bf8-160">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="53bf8-161">此設定預設為停用。</span><span class="sxs-lookup"><span data-stu-id="53bf8-161">This setting is disabled by default.</span></span>

## <a name="see-also"></a><span data-ttu-id="53bf8-162">另請參閱</span><span class="sxs-lookup"><span data-stu-id="53bf8-162">See also</span></span>

[<span data-ttu-id="53bf8-163">Set-CSTeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="53bf8-163">Set-CSTeamsCallingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)