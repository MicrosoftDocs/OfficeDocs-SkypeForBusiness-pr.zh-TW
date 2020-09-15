---
title: 團隊與 Skype 互通性
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: 瞭解貴組織中的團隊使用者與 Skype (消費者) 使用者之間的互通性功能。
localization_priority: Normal
ms.openlocfilehash: 551e39cdb496cc9e64ad962a8a50c06cb72f0aa2
ms.sourcegitcommit: f5ad0fc5be7201b71da4f13586972831c9961e51
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2020
ms.locfileid: "47651202"
---
# <a name="teams-and-skype-interoperability"></a><span data-ttu-id="3e3ec-103">團隊與 Skype 互通性</span><span class="sxs-lookup"><span data-stu-id="3e3ec-103">Teams and Skype interoperability</span></span>

<span data-ttu-id="3e3ec-104">本文將提供 Microsoft 團隊與 Skype (消費者) 之間的互通性功能概覽。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-104">This article gives you an overview of the interoperability capabilities between Microsoft Teams and Skype (Consumer).</span></span> <span data-ttu-id="3e3ec-105">瞭解團隊使用者與 Skype 使用者如何透過聊天和通話以及適用的管理控制項進行通訊。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-105">Learn how Teams users and Skype users can communicate through chats and calls and the admin controls that apply.</span></span>

<span data-ttu-id="3e3ec-106">貴組織中的小組使用者可以使用他們的電子郵件地址與撥號給 Skype 使用者，或相反地呼叫 Skype 使用者。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-106">Teams users in your organization can chat with and call Skype users by using their email address and vice versa.</span></span>

- <span data-ttu-id="3e3ec-107">團隊使用者可以使用 Skype 使用者搜尋並開始一對一的純文字交談或音訊/視頻通話。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-107">Teams users can search for and start a one-on-one text-only conversation or an audio/video call with a Skype user.</span></span>
- <span data-ttu-id="3e3ec-108">Skype 使用者可以搜尋並開始與小組使用者進行一對一的單一文字交談或音訊/視頻通話。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-108">Skype users can search for and start a one-on-one text-only conversation or an audio/video call with a Teams user.</span></span>

<span data-ttu-id="3e3ec-109">您可以在桌上型電腦、web 版和行動裝置 (Android 和 iOS 上使用這些功能，以供團隊和 Skype) 用戶端使用。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-109">These capabilities are available on the desktop, web, and mobile (Android and iOS) clients for both Teams and Skype.</span></span> <span data-ttu-id="3e3ec-110">為了獲得最佳體驗，我們建議使用 Skype 版本8.58 及更新版本。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-110">For an optimal experience, we recommend Skype version 8.58 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="3e3ec-111">在 GCC、GCC 高或 DOD 部署或私人雲端環境中，本文中討論的小組和 Skype 交互操作功能無法使用。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-111">The Teams and Skype interop capabilities discussed in this article aren't available in GCC, GCC High, or DOD deployments, or in private cloud environments.</span></span>

## <a name="chat-and-calling-experience"></a><span data-ttu-id="3e3ec-112">聊天和通話體驗</span><span class="sxs-lookup"><span data-stu-id="3e3ec-112">Chat and calling experience</span></span>

<span data-ttu-id="3e3ec-113">以下是聊天和通話體驗的概覽。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-113">Here's an overview of the chat and calling experience.</span></span>

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a><span data-ttu-id="3e3ec-114">團隊使用者與 Skype 使用者開始聊天或通話</span><span class="sxs-lookup"><span data-stu-id="3e3ec-114">Teams user starts a chat or call with a Skype user</span></span>

<span data-ttu-id="3e3ec-115">團隊使用者可以在新聊天或搜尋列中輸入他們的電子郵件地址，以搜尋 Skype 使用者。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-115">Teams users can search for a Skype user by typing their email address in a new chat or in the search bar.</span></span>  <span data-ttu-id="3e3ec-116">然後，小組使用者可以在搜尋結果中選取 Skype 使用者，以與他們開始聊天或進行通話。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-116">The Teams user can then select the Skype user in the search results to start a chat or call with them.</span></span>

<span data-ttu-id="3e3ec-117">Skype 使用者可以選擇不顯示在搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-117">A Skype user may choose not to appear in search results.</span></span> <span data-ttu-id="3e3ec-118">在這種情況下，它們不會顯示在團隊和團隊使用者無法找到的搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-118">In this case, they won't show up in the search results in Teams and Teams users won't be able to find them.</span></span>

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a><span data-ttu-id="3e3ec-119">Skype 使用者與團隊使用者開始聊天或通話</span><span class="sxs-lookup"><span data-stu-id="3e3ec-119">Skype user starts a chat or call with a Teams user</span></span>

<span data-ttu-id="3e3ec-120">Skype 使用者可以使用他們的電子郵件地址，搜尋並開始與團隊使用者交談。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-120">Skype users can search for and start a chat with a Teams user by using their email address.</span></span> <span data-ttu-id="3e3ec-121">小組使用者會收到來自 Skype 使用者的新訊息通知。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-121">The Teams user is notified that they have a new message from a Skype user.</span></span> <span data-ttu-id="3e3ec-122">小組使用者必須先接受郵件，才能回復。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-122">The Teams user has to first accept the message before they can reply to it.</span></span>

- <span data-ttu-id="3e3ec-123">如果團隊使用者選取 [ **接受**]，就會接受該交談，且兩個使用者都可以相互聊天和呼叫對方。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-123">If the Teams user selects **Accept**, the conversation is accepted, and both users can chat and call each other.</span></span>
- <span data-ttu-id="3e3ec-124">如果團隊使用者選取 [ **封鎖**]，就會封鎖交談，隨後就會封鎖該 Skype 使用者的後續訊息和通話。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-124">If the Teams user selects **Block**, the conversation is blocked, and subsequent messages and calls from that Skype user are blocked.</span></span>
- <span data-ttu-id="3e3ec-125">如果小組使用者選取 [ **查看郵件**]，該訊息會顯示在 [小組] 中，協助使用者決定要接受還是封鎖交談。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-125">If the Teams user selects **View messages**, the message is displayed in Teams, which helps the user decide whether to accept or block the conversation.</span></span>

> [!NOTE]
> <span data-ttu-id="3e3ec-126">如果您是從商務用 Skype 升級至小組，且您的使用者是 [僅限團隊] 模式，則會將 Skype 使用者的聊天和呼叫傳送給小組。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-126">If you upgraded from Skype for Business to Teams and your users are in Teams Only mode, chats and calls from Skype users to Teams users are delivered to Teams.</span></span> <span data-ttu-id="3e3ec-127">如果您的使用者處於 [孤島] 模式，聊天和 Skype 使用者的呼叫會傳送到商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-127">If your users are in Islands mode, chats and calls from Skype users to Teams users are delivered to Skype for Business.</span></span>

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a><span data-ttu-id="3e3ec-128">小組使用者封鎖或解除封鎖 Skype 使用者</span><span class="sxs-lookup"><span data-stu-id="3e3ec-128">Teams user blocks or unblocks a Skype user</span></span>

<span data-ttu-id="3e3ec-129">在團隊使用者接受或封鎖來自 Skype 使用者的初始交談要求之後，就可以隨時選擇封鎖或解除封鎖該人員。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-129">After a Teams user accepts or blocks the initial conversation request from a Skype user, they can choose to block or unblock that person at any time.</span></span> <span data-ttu-id="3e3ec-130">他們可以在交談中或在小組中的隱私權設定中執行此動作。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-130">They can do this either in the conversation or in their privacy settings in Teams.</span></span> <span data-ttu-id="3e3ec-131">Skype 使用者不會知道他們已被封鎖。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-131">Skype users won't know that they've been blocked.</span></span>

<span data-ttu-id="3e3ec-132">已封鎖的 Skype 使用者以及其他人和公開交換的電話網絡 (PSTN) 小組使用者封鎖的電話號碼，會列在使用者的 [小組中的封鎖式連絡人] 清單中。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-132">Blocked Skype users, along with other people and public switched telephone network (PSTN) phone numbers that a Teams user has blocked, are listed on the user's blocked contact list in Teams.</span></span>

## <a name="limitations"></a><span data-ttu-id="3e3ec-133">有限</span><span class="sxs-lookup"><span data-stu-id="3e3ec-133">Limitations</span></span>

- <span data-ttu-id="3e3ec-134">交談為純文字。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-134">Conversations are text-only.</span></span> <span data-ttu-id="3e3ec-135">這表示沒有任何豐富的格式設定、@mentions、emoji 或其他任何其他適用于 [原生團隊聊天體驗](native-chat-for-external-users.md)的聊天功能。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-135">This means that there's no rich formatting, @mentions, emojis, or other any of the other chat features that are available in a [native Teams chat experience](native-chat-for-external-users.md).</span></span>
- <span data-ttu-id="3e3ec-136">[交談] 只是一對一的。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-136">Conversations are one-on-one only.</span></span> <span data-ttu-id="3e3ec-137">不支援群組聊天。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-137">Group chats aren't supported.</span></span>
- <span data-ttu-id="3e3ec-138">團隊使用者和 Skype 使用者彼此都看不到彼此的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-138">Teams users and Skype users can't see each other's presence.</span></span>
- <span data-ttu-id="3e3ec-139">不支援使用 Skype ID 或電話號碼搜尋 Skype 使用者。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-139">Searching for Skype users by using their Skype ID or phone number isn't supported.</span></span>
- <span data-ttu-id="3e3ec-140">Skype 使用者無法撥打設定來電轉接至其他使用者號碼、代理人號碼或公開交換電話網絡的小組使用者， (PSTN) 號碼。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-140">Skype users can't call Teams users who set up call forwarding to another user's number, a delegate's number, or a Public Switched Telephone Network (PSTN) number.</span></span>  <span data-ttu-id="3e3ec-141">僅支援語音信箱。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-141">Only voicemail is supported.</span></span>
- <span data-ttu-id="3e3ec-142">不支援互通性升級、群組通話及會議。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-142">Interop escalation, group calls, and meetings aren't supported.</span></span>
- <span data-ttu-id="3e3ec-143">代理人不支援代表小組使用者呼叫 Skype 使用者的功能。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-143">The ability for a delegate to call a Skype user on behalf of a Teams user isn't supported.</span></span>
- <span data-ttu-id="3e3ec-144">不支援使用聊天的螢幕共用。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-144">Screen sharing with chat isn't supported.</span></span>

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a><span data-ttu-id="3e3ec-145">設定團隊使用者是否可與 Skype 使用者通訊</span><span class="sxs-lookup"><span data-stu-id="3e3ec-145">Set whether Teams users can communicate with Skype users</span></span>

<span data-ttu-id="3e3ec-146">作為系統管理員，您可以使用 Microsoft 團隊系統管理中心或 PowerShell 來設定外部存取設定，以控制貴組織中的小組使用者是否可與 Skype 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-146">As an admin, you use the Microsoft Teams admin center or PowerShell to set external access settings to control whether Teams users in your organization can communicate with Skype users.</span></span> <span data-ttu-id="3e3ec-147">根據預設，此功能已針對新的租使用者開啟。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-147">By default, this capability is turned on for new tenants.</span></span>

<span data-ttu-id="3e3ec-148">如果您是從商務用 Skype 升級至小組，您在商務用 Skype 系統管理中心所設定的外部通訊設定會遷移至小組。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-148">If you upgraded from Skype for Business to Teams, the external communications settings that you configured in the Skype for Business admin center are migrated to Teams.</span></span>

### <a name="in-the-microsoft-teams-admin-center"></a><span data-ttu-id="3e3ec-149">在 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="3e3ec-149">In the Microsoft Teams admin center</span></span>

<span data-ttu-id="3e3ec-150">在 Microsoft 團隊系統管理中心中，移至 [**全組織設定**  >  **外部存取**]，然後開啟 [**使用者可以與 Skype 使用者通訊**]。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-150">In the Microsoft Teams admin center, go to **Org-wide settings** > **External access**, and then turn on **Users can communicate with Skype users**.</span></span> <span data-ttu-id="3e3ec-151">如需如何設定此和其他外部存取設定的逐步指導，請參閱 [管理團隊中的外部存取](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains)。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-151">For step-by-step guidance on how to configure this and other external access settings, see [Manage external access in Teams](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3e3ec-152">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="3e3ec-152">Using PowerShell</span></span>

<span data-ttu-id="3e3ec-153">搭配使用 [CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) Cmdlet 與 ```EnablePublicCloudAccess``` 參數，以控制團隊使用者是否可與 Skype 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-153">Use the [Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) cmdlet together with the ```EnablePublicCloudAccess``` parameter to control whether Teams users can communicate with Skype users.</span></span> <span data-ttu-id="3e3ec-154">設定參數以 ```true``` 允許團隊使用者與 Skype 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-154">Setting the parameter to ```true``` allows Teams users to communicate with Skype users.</span></span> <span data-ttu-id="3e3ec-155">您可以使用 ```EnablePublicCloudAudioVideoAccess``` 參數來啟用/停用音訊/視頻通話。</span><span class="sxs-lookup"><span data-stu-id="3e3ec-155">You can use the ```EnablePublicCloudAudioVideoAccess``` parameter to enable/disable audio/video calls.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3e3ec-156">相關主題</span><span class="sxs-lookup"><span data-stu-id="3e3ec-156">Related topics</span></span>

- [<span data-ttu-id="3e3ec-157">管理團隊中的外部存取</span><span class="sxs-lookup"><span data-stu-id="3e3ec-157">Manage external access in Teams</span></span>](manage-external-access.md)
- [<span data-ttu-id="3e3ec-158">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="3e3ec-158">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
