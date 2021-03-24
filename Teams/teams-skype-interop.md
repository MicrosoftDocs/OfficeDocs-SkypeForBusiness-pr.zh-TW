---
title: Teams 和 Skype 互通性
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
description: 瞭解貴組織中 Teams 使用者與 Skype 使用者與消費者使用者 (互通性) 功能。
localization_priority: Normal
ms.openlocfilehash: e3203c03043dbcdb04370cf3aa26b435fad4a728
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093953"
---
# <a name="teams-and-skype-interoperability"></a><span data-ttu-id="e36bd-103">Teams 和 Skype 互通性</span><span class="sxs-lookup"><span data-stu-id="e36bd-103">Teams and Skype interoperability</span></span>

<span data-ttu-id="e36bd-104">本文提供 Microsoft Teams 與 Skype 與消費者帳戶之間的互通性 (概) 。</span><span class="sxs-lookup"><span data-stu-id="e36bd-104">This article gives you an overview of the interoperability capabilities between Microsoft Teams and Skype (Consumer).</span></span> <span data-ttu-id="e36bd-105">瞭解 Teams 使用者和 Skype 使用者如何透過聊天和通話以及適用之系統管理控制項來通訊。</span><span class="sxs-lookup"><span data-stu-id="e36bd-105">Learn how Teams users and Skype users can communicate through chats and calls and the admin controls that apply.</span></span>

<span data-ttu-id="e36bd-106">您組織的 Teams 使用者可以使用 Skype 使用者的電子郵件地址與 Skype 使用者聊天和通話，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="e36bd-106">Teams users in your organization can chat with and call Skype users by using their email address and vice versa.</span></span>

- <span data-ttu-id="e36bd-107">Teams 使用者可以搜尋並啟動一對一純文字交談，或與 Skype 使用者進行音訊/視音訊通話。</span><span class="sxs-lookup"><span data-stu-id="e36bd-107">Teams users can search for and start a one-on-one text-only conversation or an audio/video call with a Skype user.</span></span>
- <span data-ttu-id="e36bd-108">Skype 使用者可以搜尋和啟動一對一純文字交談，或與 Teams 使用者進行音訊/視音訊通話。</span><span class="sxs-lookup"><span data-stu-id="e36bd-108">Skype users can search for and start a one-on-one text-only conversation or an audio/video call with a Teams user.</span></span>

<span data-ttu-id="e36bd-109">這些功能可在 Android 和 iOS (Android 和 Skype 的桌面) 行動版用戶端上提供。</span><span class="sxs-lookup"><span data-stu-id="e36bd-109">These capabilities are available on the desktop, web, and mobile (Android and iOS) clients for both Teams and Skype.</span></span> <span data-ttu-id="e36bd-110">為了獲得最佳體驗，我們建議您使用 Skype 版本 8.58 及更新版本。</span><span class="sxs-lookup"><span data-stu-id="e36bd-110">For an optimal experience, we recommend Skype version 8.58 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="e36bd-111">本文中討論的 Teams 和 Skype 交互操作功能不適用於 GCC、GCC High 或 DOD 部署，或私人雲端環境。</span><span class="sxs-lookup"><span data-stu-id="e36bd-111">The Teams and Skype interop capabilities discussed in this article aren't available in GCC, GCC High, or DOD deployments, or in private cloud environments.</span></span>

## <a name="chat-and-calling-experience"></a><span data-ttu-id="e36bd-112">聊天和通話體驗</span><span class="sxs-lookup"><span data-stu-id="e36bd-112">Chat and calling experience</span></span>

<span data-ttu-id="e36bd-113">以下是聊天和通話體驗概觀。</span><span class="sxs-lookup"><span data-stu-id="e36bd-113">Here's an overview of the chat and calling experience.</span></span>

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a><span data-ttu-id="e36bd-114">Teams 使用者開始與 Skype 使用者聊天或通話</span><span class="sxs-lookup"><span data-stu-id="e36bd-114">Teams user starts a chat or call with a Skype user</span></span>

<span data-ttu-id="e36bd-115">Teams 使用者可以在新的聊天或搜尋欄中輸入其電子郵件地址，以搜尋 Skype 使用者。</span><span class="sxs-lookup"><span data-stu-id="e36bd-115">Teams users can search for a Skype user by typing their email address in a new chat or in the search bar.</span></span>  <span data-ttu-id="e36bd-116">然後，Teams 使用者可以在搜尋結果中選取 Skype 使用者，開始聊天或通話。</span><span class="sxs-lookup"><span data-stu-id="e36bd-116">The Teams user can then select the Skype user in the search results to start a chat or call with them.</span></span>

<span data-ttu-id="e36bd-117">Skype 使用者可能會選擇不顯示在搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="e36bd-117">A Skype user may choose not to appear in search results.</span></span> <span data-ttu-id="e36bd-118">在這種情況下，這些人員不會顯示在 Teams 的搜尋結果中，而 Teams 使用者將無法找到他們。</span><span class="sxs-lookup"><span data-stu-id="e36bd-118">In this case, they won't show up in the search results in Teams and Teams users won't be able to find them.</span></span>

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a><span data-ttu-id="e36bd-119">Skype 使用者開始與 Teams 使用者聊天或通話</span><span class="sxs-lookup"><span data-stu-id="e36bd-119">Skype user starts a chat or call with a Teams user</span></span>

<span data-ttu-id="e36bd-120">Skype 使用者可以使用 Teams 使用者的電子郵件地址搜尋並開始與 Teams 使用者聊天。</span><span class="sxs-lookup"><span data-stu-id="e36bd-120">Skype users can search for and start a chat with a Teams user by using their email address.</span></span> <span data-ttu-id="e36bd-121">Teams 使用者會收到來自 Skype 使用者的新訊息的通知，且必須先接受該訊息，才能回復。</span><span class="sxs-lookup"><span data-stu-id="e36bd-121">The Teams user is notified that they have a new message from a Skype user, and has to first accept the message before they can reply to it.</span></span>

- <span data-ttu-id="e36bd-122">如果 Teams 使用者選取了 **接受**，系統即會接受交談，而且兩個使用者都可以彼此聊天和通話。</span><span class="sxs-lookup"><span data-stu-id="e36bd-122">If the Teams user selects **Accept**, the conversation is accepted, and both users can chat and call each other.</span></span>
- <span data-ttu-id="e36bd-123">如果 Teams 使用者選取了封鎖，交談會封鎖，而來自該 Skype 使用者的後續訊息和通話會封鎖。</span><span class="sxs-lookup"><span data-stu-id="e36bd-123">If the Teams user selects **Block**, the conversation is blocked, and subsequent messages and calls from that Skype user are blocked.</span></span>
- <span data-ttu-id="e36bd-124">如果 Teams 使用者選取了查看 **郵件**，郵件會顯示在 Teams 中，這可協助使用者決定是否要接受或封鎖交談。</span><span class="sxs-lookup"><span data-stu-id="e36bd-124">If the Teams user selects **View messages**, the message is displayed in Teams, which helps the user decide whether to accept or block the conversation.</span></span>

> [!NOTE]
> <span data-ttu-id="e36bd-125">如果您從商務用 Skype 升級至 Teams，而您的使用者是使用 Teams 模式，Skype 使用者與 Teams 使用者的聊天和通話會傳送到 Teams。</span><span class="sxs-lookup"><span data-stu-id="e36bd-125">If you upgraded from Skype for Business to Teams and your users are in Teams Only mode, chats and calls from Skype users to Teams users are delivered to Teams.</span></span> <span data-ttu-id="e36bd-126">如果您的使用者是群島模式，Skype 使用者與 Teams 使用者的聊天和通話會傳送到商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="e36bd-126">If your users are in Islands mode, chats and calls from Skype users to Teams users are delivered to Skype for Business.</span></span>

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a><span data-ttu-id="e36bd-127">Teams 使用者封鎖或解除封鎖 Skype 使用者</span><span class="sxs-lookup"><span data-stu-id="e36bd-127">Teams user blocks or unblocks a Skype user</span></span>

<span data-ttu-id="e36bd-128">在 Teams 使用者接受或封鎖 Skype 使用者的初始交談要求之後，他們可以選擇隨時封鎖或解除封鎖該人員。</span><span class="sxs-lookup"><span data-stu-id="e36bd-128">After a Teams user accepts or blocks the initial conversation request from a Skype user, they can choose to block or unblock that person at any time.</span></span> <span data-ttu-id="e36bd-129">他們可以在交談中或在 Teams 中的隱私權設定中執行這項操作。</span><span class="sxs-lookup"><span data-stu-id="e36bd-129">They can do this either in the conversation or in their privacy settings in Teams.</span></span> <span data-ttu-id="e36bd-130">Skype 使用者不會知道他們遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="e36bd-130">Skype users won't know that they've been blocked.</span></span>

<span data-ttu-id="e36bd-131">已封鎖的 Skype 使用者，以及其他人和公用交換電話網路絡 (PSTN) Teams 使用者封鎖的電話號碼，會列在 Teams 中使用者封鎖的連絡人清單中。</span><span class="sxs-lookup"><span data-stu-id="e36bd-131">Blocked Skype users, along with other people and public switched telephone network (PSTN) phone numbers that a Teams user has blocked, are listed on the user's blocked contact list in Teams.</span></span>

## <a name="limitations"></a><span data-ttu-id="e36bd-132">限制</span><span class="sxs-lookup"><span data-stu-id="e36bd-132">Limitations</span></span>

- <span data-ttu-id="e36bd-133">交談為純文字。</span><span class="sxs-lookup"><span data-stu-id="e36bd-133">Conversations are text-only.</span></span> <span data-ttu-id="e36bd-134">這表示沒有豐富的格式、@mentions、表情符號或其他任何原生 Teams 聊天體驗中可用的聊天 [功能](native-chat-for-external-users.md)。</span><span class="sxs-lookup"><span data-stu-id="e36bd-134">This means that there's no rich formatting, @mentions, emojis, or other any of the other chat features that are available in a [native Teams chat experience](native-chat-for-external-users.md).</span></span>
- <span data-ttu-id="e36bd-135">交談是一對一。</span><span class="sxs-lookup"><span data-stu-id="e36bd-135">Conversations are one-on-one only.</span></span> <span data-ttu-id="e36bd-136">不支援群組聊天。</span><span class="sxs-lookup"><span data-stu-id="e36bd-136">Group chats aren't supported.</span></span>
- <span data-ttu-id="e36bd-137">Teams 使用者和 Skype 使用者無法看到彼此的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="e36bd-137">Teams users and Skype users can't see each other's presence.</span></span>
- <span data-ttu-id="e36bd-138">不支援使用 Skype 識別碼或電話號碼搜尋 Skype 使用者。</span><span class="sxs-lookup"><span data-stu-id="e36bd-138">Searching for Skype users by using their Skype ID or phone number isn't supported.</span></span>
- <span data-ttu-id="e36bd-139">Skype 使用者無法撥打設定呼叫轉撥至其他使用者號碼、代理人號碼或公用交換電話網路 (PSTN) 的 Teams 使用者。</span><span class="sxs-lookup"><span data-stu-id="e36bd-139">Skype users can't call Teams users who set up call forwarding to another user's number, a delegate's number, or a Public Switched Telephone Network (PSTN) number.</span></span>  <span data-ttu-id="e36bd-140">僅支援語音信箱。</span><span class="sxs-lookup"><span data-stu-id="e36bd-140">Only voicemail is supported.</span></span>
- <span data-ttu-id="e36bd-141">不支援交互操作升級、群組通話和會議。</span><span class="sxs-lookup"><span data-stu-id="e36bd-141">Interop escalation, group calls, and meetings aren't supported.</span></span>
- <span data-ttu-id="e36bd-142">不支援代理人代表 Teams 使用者打電話給 Skype 使用者的能力。</span><span class="sxs-lookup"><span data-stu-id="e36bd-142">The ability for a delegate to call a Skype user on behalf of a Teams user isn't supported.</span></span>
- <span data-ttu-id="e36bd-143">不支援使用聊天進行螢幕共用。</span><span class="sxs-lookup"><span data-stu-id="e36bd-143">Screen sharing with chat isn't supported.</span></span>

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a><span data-ttu-id="e36bd-144">設定 Teams 使用者是否可以與 Skype 使用者通訊</span><span class="sxs-lookup"><span data-stu-id="e36bd-144">Set whether Teams users can communicate with Skype users</span></span>

<span data-ttu-id="e36bd-145">做為系統管理員，您可以使用 Microsoft Teams 系統管理中心或 PowerShell 來設定外部存取設定，以控制貴組織的 Teams 使用者是否可以與 Skype 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="e36bd-145">As an admin, you use the Microsoft Teams admin center or PowerShell to set external access settings to control whether Teams users in your organization can communicate with Skype users.</span></span> <span data-ttu-id="e36bd-146">根據預設，此功能會針對新租使用者開啟。</span><span class="sxs-lookup"><span data-stu-id="e36bd-146">By default, this capability is turned on for new tenants.</span></span> <span data-ttu-id="e36bd-147">不過，如果網域尚未提供下列 DNS SRV 記錄 ，例如 _sipfederationtls.contoso.com，則 IT 系統管理員必須配置下列 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="e36bd-147">However, there's a prerequisite that the following DNS SRV record needs to be configured by the IT Admin if not already available for your domain, for example _sipfederationtls.contoso.com.</span></span>  

<span data-ttu-id="e36bd-148">**服務**：sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="e36bd-148">**Service**: sipfederationtls</span></span><br/>
<span data-ttu-id="e36bd-149">**通訊協定**：TCP</span><span class="sxs-lookup"><span data-stu-id="e36bd-149">**Protocol**: TCP</span></span><br/>
<span data-ttu-id="e36bd-150">**優先順序**：100</span><span class="sxs-lookup"><span data-stu-id="e36bd-150">**Priority**: 100</span></span><br/>
<span data-ttu-id="e36bd-151">**粗** 細：1</span><span class="sxs-lookup"><span data-stu-id="e36bd-151">**Weight**: 1</span></span><br/>
<span data-ttu-id="e36bd-152">**埠**：5061</span><span class="sxs-lookup"><span data-stu-id="e36bd-152">**Port**: 5061</span></span><br/>
<span data-ttu-id="e36bd-153">**目標**：sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e36bd-153">**Target**: sipfed.online.lync.com</span></span>

<span data-ttu-id="e36bd-154">如果您從商務用 Skype 升級至 Teams，您于商務用 Skype 系統管理中心所設定的外部通訊設定會移至 Teams。</span><span class="sxs-lookup"><span data-stu-id="e36bd-154">If you upgraded from Skype for Business to Teams, the external communications settings that you configured in the Skype for Business admin center are migrated to Teams.</span></span>

### <a name="in-the-microsoft-teams-admin-center"></a><span data-ttu-id="e36bd-155">在 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="e36bd-155">In the Microsoft Teams admin center</span></span>

<span data-ttu-id="e36bd-156">在 Microsoft Teams 系統管理中心，前往 **全組織** 設定外部存取，然後開啟  >  \*\*\*\*\*\*使用者可以與 Skype 使用者通訊\*\*。</span><span class="sxs-lookup"><span data-stu-id="e36bd-156">In the Microsoft Teams admin center, go to **Org-wide settings** > **External access**, and then turn on **Users can communicate with Skype users**.</span></span> <span data-ttu-id="e36bd-157">若要取得如何設定此及其他外部存取設定之逐步指南，請參閱在 Teams 中管理 [外部存取](./manage-external-access.md#allow-or-block-domains)。</span><span class="sxs-lookup"><span data-stu-id="e36bd-157">For step-by-step guidance on how to configure this and other external access settings, see [Manage external access in Teams](./manage-external-access.md#allow-or-block-domains).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e36bd-158">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e36bd-158">Using PowerShell</span></span>

<span data-ttu-id="e36bd-159">請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e36bd-159">Do the following:</span></span> 
1. <span data-ttu-id="e36bd-160">使用 [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) Cmdlet 與參數一起控制 Teams 使用者是否能與 ```EnablePublicCloudAccess``` Skype 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="e36bd-160">Use the [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) cmdlet together with the ```EnablePublicCloudAccess``` parameter to control whether Teams users can communicate with Skype users.</span></span> <span data-ttu-id="e36bd-161">將參數設定 ```true``` 為允許 Teams 使用者與 Skype 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="e36bd-161">Setting the parameter to ```true``` allows Teams users to communicate with Skype users.</span></span> <span data-ttu-id="e36bd-162">您可以使用參數 ```EnablePublicCloudAudioVideoAccess``` 來啟用/停用音訊/視音訊通話。</span><span class="sxs-lookup"><span data-stu-id="e36bd-162">You can use the ```EnablePublicCloudAudioVideoAccess``` parameter to enable/disable audio/video calls.</span></span>

2. <span data-ttu-id="e36bd-163">使用 [Set-CsTenantPublicProvider Cmdlet](/powershell/module/skype/Set-CsTenantPublicProvider) 與參數集，讓 Teams 使用者可以與 ```Provider``` Skype ```"WindowsLive"``` 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="e36bd-163">Use the [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) cmdlet together with the ```Provider``` parameter set to ```"WindowsLive"``` so that Teams users can communicate with Skype users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e36bd-164">相關主題</span><span class="sxs-lookup"><span data-stu-id="e36bd-164">Related topics</span></span>

- [<span data-ttu-id="e36bd-165">在 Teams 中管理外部存取</span><span class="sxs-lookup"><span data-stu-id="e36bd-165">Manage external access in Teams</span></span>](manage-external-access.md)
- [<span data-ttu-id="e36bd-166">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="e36bd-166">Teams PowerShell overview</span></span>](teams-powershell-overview.md)