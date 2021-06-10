---
title: Teams和Skype互通性
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
description: 瞭解貴組織中Teams使用者與消費者使用者Skype (互通性) 功能。
localization_priority: Normal
ms.openlocfilehash: e3203c03043dbcdb04370cf3aa26b435fad4a728
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093953"
---
# <a name="teams-and-skype-interoperability"></a><span data-ttu-id="f8589-103">Teams和Skype互通性</span><span class="sxs-lookup"><span data-stu-id="f8589-103">Teams and Skype interoperability</span></span>

<span data-ttu-id="f8589-104">本文提供您與消費者使用者Microsoft Teams之間的互通性Skype (概) 。</span><span class="sxs-lookup"><span data-stu-id="f8589-104">This article gives you an overview of the interoperability capabilities between Microsoft Teams and Skype (Consumer).</span></span> <span data-ttu-id="f8589-105">瞭解Teams使用者Skype使用者如何透過聊天和通話以及適用之系統管理控制項進行溝通。</span><span class="sxs-lookup"><span data-stu-id="f8589-105">Learn how Teams users and Skype users can communicate through chats and calls and the admin controls that apply.</span></span>

<span data-ttu-id="f8589-106">Teams中的使用者可以使用Skype與使用者聊天和通話，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="f8589-106">Teams users in your organization can chat with and call Skype users by using their email address and vice versa.</span></span>

- <span data-ttu-id="f8589-107">Teams使用者可以搜尋並啟動一對一純文字交談，或與使用者進行音訊/視Skype通話。</span><span class="sxs-lookup"><span data-stu-id="f8589-107">Teams users can search for and start a one-on-one text-only conversation or an audio/video call with a Skype user.</span></span>
- <span data-ttu-id="f8589-108">Skype使用者可以搜尋並啟動一對一純文字交談，或與使用者進行音訊/視Teams通話。</span><span class="sxs-lookup"><span data-stu-id="f8589-108">Skype users can search for and start a one-on-one text-only conversation or an audio/video call with a Teams user.</span></span>

<span data-ttu-id="f8589-109">這些功能可在 Android 和 iOS (的桌面、Web 和行動) 用戶端Teams Skype。</span><span class="sxs-lookup"><span data-stu-id="f8589-109">These capabilities are available on the desktop, web, and mobile (Android and iOS) clients for both Teams and Skype.</span></span> <span data-ttu-id="f8589-110">為了獲得最佳體驗，建議您Skype版本 8.58 及更新版本。</span><span class="sxs-lookup"><span data-stu-id="f8589-110">For an optimal experience, we recommend Skype version 8.58 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="f8589-111">本文Teams和Skype的交互操作功能不適用於 GCC、GCC 高或 DOD 部署，或私人雲端環境中。</span><span class="sxs-lookup"><span data-stu-id="f8589-111">The Teams and Skype interop capabilities discussed in this article aren't available in GCC, GCC High, or DOD deployments, or in private cloud environments.</span></span>

## <a name="chat-and-calling-experience"></a><span data-ttu-id="f8589-112">聊天和通話體驗</span><span class="sxs-lookup"><span data-stu-id="f8589-112">Chat and calling experience</span></span>

<span data-ttu-id="f8589-113">以下是聊天和通話體驗概觀。</span><span class="sxs-lookup"><span data-stu-id="f8589-113">Here's an overview of the chat and calling experience.</span></span>

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a><span data-ttu-id="f8589-114">Teams使用者與使用者開始聊天或Skype通話</span><span class="sxs-lookup"><span data-stu-id="f8589-114">Teams user starts a chat or call with a Skype user</span></span>

<span data-ttu-id="f8589-115">Teams使用者可以在新的聊天或搜尋Skype中輸入其電子郵件地址，以搜尋使用者。</span><span class="sxs-lookup"><span data-stu-id="f8589-115">Teams users can search for a Skype user by typing their email address in a new chat or in the search bar.</span></span>  <span data-ttu-id="f8589-116">使用者Teams，然後選取搜尋結果Skype使用者開始聊天或通話。</span><span class="sxs-lookup"><span data-stu-id="f8589-116">The Teams user can then select the Skype user in the search results to start a chat or call with them.</span></span>

<span data-ttu-id="f8589-117">使用者Skype選擇不顯示在搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="f8589-117">A Skype user may choose not to appear in search results.</span></span> <span data-ttu-id="f8589-118">在這種情況下，這些使用者不會顯示在搜尋結果中Teams Teams使用者將無法找到他們。</span><span class="sxs-lookup"><span data-stu-id="f8589-118">In this case, they won't show up in the search results in Teams and Teams users won't be able to find them.</span></span>

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a><span data-ttu-id="f8589-119">Skype使用者開始與使用者聊天或Teams通話</span><span class="sxs-lookup"><span data-stu-id="f8589-119">Skype user starts a chat or call with a Teams user</span></span>

<span data-ttu-id="f8589-120">Skype使用者可以使用使用者的電子郵件地址，搜尋Teams開始與使用者聊天。</span><span class="sxs-lookup"><span data-stu-id="f8589-120">Skype users can search for and start a chat with a Teams user by using their email address.</span></span> <span data-ttu-id="f8589-121">Teams收到通知，告知使用者有來自Skype的新郵件，且必須先接受郵件，才能回復郵件。</span><span class="sxs-lookup"><span data-stu-id="f8589-121">The Teams user is notified that they have a new message from a Skype user, and has to first accept the message before they can reply to it.</span></span>

- <span data-ttu-id="f8589-122">如果使用者Teams選取接受，即表示已接受交談，而且兩個使用者都可以彼此聊天和通話。</span><span class="sxs-lookup"><span data-stu-id="f8589-122">If the Teams user selects **Accept**, the conversation is accepted, and both users can chat and call each other.</span></span>
- <span data-ttu-id="f8589-123">如果使用者Teams封鎖，交談會封鎖，而來自該使用者的後續訊息Skype通話會封鎖。</span><span class="sxs-lookup"><span data-stu-id="f8589-123">If the Teams user selects **Block**, the conversation is blocked, and subsequent messages and calls from that Skype user are blocked.</span></span>
- <span data-ttu-id="f8589-124">如果使用者選取 Teams，郵件會顯示在Teams 中，這可協助使用者決定是否接受或封鎖交談。</span><span class="sxs-lookup"><span data-stu-id="f8589-124">If the Teams user selects **View messages**, the message is displayed in Teams, which helps the user decide whether to accept or block the conversation.</span></span>

> [!NOTE]
> <span data-ttu-id="f8589-125">如果您從 商務用 Skype 升級到 Teams，而您的使用者是使用 Teams 模式，Skype 使用者與 Teams 使用者的聊天和通話會傳送到 Teams。</span><span class="sxs-lookup"><span data-stu-id="f8589-125">If you upgraded from Skype for Business to Teams and your users are in Teams Only mode, chats and calls from Skype users to Teams users are delivered to Teams.</span></span> <span data-ttu-id="f8589-126">如果您的使用者是群島模式，則來自Skype使用者的聊天和Teams會傳送至商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="f8589-126">If your users are in Islands mode, chats and calls from Skype users to Teams users are delivered to Skype for Business.</span></span>

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a><span data-ttu-id="f8589-127">Teams使用者封鎖或解除封鎖Skype使用者</span><span class="sxs-lookup"><span data-stu-id="f8589-127">Teams user blocks or unblocks a Skype user</span></span>

<span data-ttu-id="f8589-128">在Teams使用者接受或封鎖使用者的初始交談Skype，他們可以選擇隨時封鎖或解除封鎖該人員。</span><span class="sxs-lookup"><span data-stu-id="f8589-128">After a Teams user accepts or blocks the initial conversation request from a Skype user, they can choose to block or unblock that person at any time.</span></span> <span data-ttu-id="f8589-129">他們可以在交談中或在交談中的隱私權設定中Teams。</span><span class="sxs-lookup"><span data-stu-id="f8589-129">They can do this either in the conversation or in their privacy settings in Teams.</span></span> <span data-ttu-id="f8589-130">Skype使用者不會知道他們遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="f8589-130">Skype users won't know that they've been blocked.</span></span>

<span data-ttu-id="f8589-131">封鎖Skype使用者，以及其他使用者和公用交換電話網路絡 (PSTN) Teams 使用者封鎖的電話號碼，會列在 Teams 使用者封鎖的連絡人清單中。</span><span class="sxs-lookup"><span data-stu-id="f8589-131">Blocked Skype users, along with other people and public switched telephone network (PSTN) phone numbers that a Teams user has blocked, are listed on the user's blocked contact list in Teams.</span></span>

## <a name="limitations"></a><span data-ttu-id="f8589-132">限制</span><span class="sxs-lookup"><span data-stu-id="f8589-132">Limitations</span></span>

- <span data-ttu-id="f8589-133">交談是純文字的。</span><span class="sxs-lookup"><span data-stu-id="f8589-133">Conversations are text-only.</span></span> <span data-ttu-id="f8589-134">這表示沒有豐富的格式、@mentions、表情符號或其他任何原生聊天體驗中可用的聊天Teams[功能](native-chat-for-external-users.md)。</span><span class="sxs-lookup"><span data-stu-id="f8589-134">This means that there's no rich formatting, @mentions, emojis, or other any of the other chat features that are available in a [native Teams chat experience](native-chat-for-external-users.md).</span></span>
- <span data-ttu-id="f8589-135">交談是一對一。</span><span class="sxs-lookup"><span data-stu-id="f8589-135">Conversations are one-on-one only.</span></span> <span data-ttu-id="f8589-136">不支援群組聊天。</span><span class="sxs-lookup"><span data-stu-id="f8589-136">Group chats aren't supported.</span></span>
- <span data-ttu-id="f8589-137">Teams使用者Skype使用者無法看到彼此的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="f8589-137">Teams users and Skype users can't see each other's presence.</span></span>
- <span data-ttu-id="f8589-138">不支援Skype使用者使用Skype識別碼或電話號碼來搜尋使用者。</span><span class="sxs-lookup"><span data-stu-id="f8589-138">Searching for Skype users by using their Skype ID or phone number isn't supported.</span></span>
- <span data-ttu-id="f8589-139">Skype使用者無法撥打設定呼叫轉撥至其他使用者號碼、代理人號碼或公用交換電話網路 (PSTN) 號碼的 Teams使用者。</span><span class="sxs-lookup"><span data-stu-id="f8589-139">Skype users can't call Teams users who set up call forwarding to another user's number, a delegate's number, or a Public Switched Telephone Network (PSTN) number.</span></span>  <span data-ttu-id="f8589-140">僅支援語音信箱。</span><span class="sxs-lookup"><span data-stu-id="f8589-140">Only voicemail is supported.</span></span>
- <span data-ttu-id="f8589-141">不支援交互操作升級、群組通話和會議。</span><span class="sxs-lookup"><span data-stu-id="f8589-141">Interop escalation, group calls, and meetings aren't supported.</span></span>
- <span data-ttu-id="f8589-142">不支援代理人代表Skype使用者Teams呼叫使用者的能力。</span><span class="sxs-lookup"><span data-stu-id="f8589-142">The ability for a delegate to call a Skype user on behalf of a Teams user isn't supported.</span></span>
- <span data-ttu-id="f8589-143">不支援使用聊天進行螢幕共用。</span><span class="sxs-lookup"><span data-stu-id="f8589-143">Screen sharing with chat isn't supported.</span></span>

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a><span data-ttu-id="f8589-144">設定Teams使用者是否可以與Skype通訊</span><span class="sxs-lookup"><span data-stu-id="f8589-144">Set whether Teams users can communicate with Skype users</span></span>

<span data-ttu-id="f8589-145">做為系統管理員，您可以使用 Microsoft Teams系統管理中心或 PowerShell 來設定外部存取設定，Teams貴組織的使用者是否可以與Skype通訊。</span><span class="sxs-lookup"><span data-stu-id="f8589-145">As an admin, you use the Microsoft Teams admin center or PowerShell to set external access settings to control whether Teams users in your organization can communicate with Skype users.</span></span> <span data-ttu-id="f8589-146">根據預設，此功能會針對新租使用者開啟。</span><span class="sxs-lookup"><span data-stu-id="f8589-146">By default, this capability is turned on for new tenants.</span></span> <span data-ttu-id="f8589-147">不過，如果網域尚未提供下列 DNS SRV 記錄，例如 _sipfederationtls.contoso.com，則 IT 系統管理員必須配置下列 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="f8589-147">However, there's a prerequisite that the following DNS SRV record needs to be configured by the IT Admin if not already available for your domain, for example _sipfederationtls.contoso.com.</span></span>  

<span data-ttu-id="f8589-148">**服務**：sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="f8589-148">**Service**: sipfederationtls</span></span><br/>
<span data-ttu-id="f8589-149">**通訊協定**：TCP</span><span class="sxs-lookup"><span data-stu-id="f8589-149">**Protocol**: TCP</span></span><br/>
<span data-ttu-id="f8589-150">**優先順序**：100</span><span class="sxs-lookup"><span data-stu-id="f8589-150">**Priority**: 100</span></span><br/>
<span data-ttu-id="f8589-151">**粗** 細：1</span><span class="sxs-lookup"><span data-stu-id="f8589-151">**Weight**: 1</span></span><br/>
<span data-ttu-id="f8589-152">**埠**：5061</span><span class="sxs-lookup"><span data-stu-id="f8589-152">**Port**: 5061</span></span><br/>
<span data-ttu-id="f8589-153">**目標**：sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f8589-153">**Target**: sipfed.online.lync.com</span></span>

<span data-ttu-id="f8589-154">如果您從 商務用 Skype 升級Teams，您于系統管理中心商務用 Skype設定的外部通訊設定會移Teams。</span><span class="sxs-lookup"><span data-stu-id="f8589-154">If you upgraded from Skype for Business to Teams, the external communications settings that you configured in the Skype for Business admin center are migrated to Teams.</span></span>

### <a name="in-the-microsoft-teams-admin-center"></a><span data-ttu-id="f8589-155">在 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="f8589-155">In the Microsoft Teams admin center</span></span>

<span data-ttu-id="f8589-156">在 Microsoft Teams系統管理中心，前往全 **組織** 設定 外部存取，然後開啟 使用者可以與Skype  >  \*\*\*\*\*\*通訊\*\*。</span><span class="sxs-lookup"><span data-stu-id="f8589-156">In the Microsoft Teams admin center, go to **Org-wide settings** > **External access**, and then turn on **Users can communicate with Skype users**.</span></span> <span data-ttu-id="f8589-157">若要取得如何設定此及其他外部存取設定之逐步指南，請參閱在 Teams 中[管理外部Teams。](./manage-external-access.md#allow-or-block-domains)</span><span class="sxs-lookup"><span data-stu-id="f8589-157">For step-by-step guidance on how to configure this and other external access settings, see [Manage external access in Teams](./manage-external-access.md#allow-or-block-domains).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="f8589-158">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8589-158">Using PowerShell</span></span>

<span data-ttu-id="f8589-159">請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="f8589-159">Do the following:</span></span> 
1. <span data-ttu-id="f8589-160">使用[Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) Cmdlet 與參數一起控制Teams使用者是否能Skype ```EnablePublicCloudAccess``` 通訊。</span><span class="sxs-lookup"><span data-stu-id="f8589-160">Use the [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) cmdlet together with the ```EnablePublicCloudAccess``` parameter to control whether Teams users can communicate with Skype users.</span></span> <span data-ttu-id="f8589-161">將參數設定 ```true``` 為Teams使用者與Skype通訊。</span><span class="sxs-lookup"><span data-stu-id="f8589-161">Setting the parameter to ```true``` allows Teams users to communicate with Skype users.</span></span> <span data-ttu-id="f8589-162">您可以使用參數 ```EnablePublicCloudAudioVideoAccess``` 來啟用/停用音訊/視音訊通話。</span><span class="sxs-lookup"><span data-stu-id="f8589-162">You can use the ```EnablePublicCloudAudioVideoAccess``` parameter to enable/disable audio/video calls.</span></span>

2. <span data-ttu-id="f8589-163">使用[Set-CsTenantPublicProvider Cmdlet](/powershell/module/skype/Set-CsTenantPublicProvider)與參數集，Teams使用者與Skype ```Provider``` ```"WindowsLive"``` 通訊。</span><span class="sxs-lookup"><span data-stu-id="f8589-163">Use the [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) cmdlet together with the ```Provider``` parameter set to ```"WindowsLive"``` so that Teams users can communicate with Skype users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f8589-164">相關主題</span><span class="sxs-lookup"><span data-stu-id="f8589-164">Related topics</span></span>

- [<span data-ttu-id="f8589-165">管理外部存取Teams</span><span class="sxs-lookup"><span data-stu-id="f8589-165">Manage external access in Teams</span></span>](manage-external-access.md)
- [<span data-ttu-id="f8589-166">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="f8589-166">Teams PowerShell overview</span></span>](teams-powershell-overview.md)