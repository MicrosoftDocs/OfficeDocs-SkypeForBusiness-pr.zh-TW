---
title: 管理小組中的訊息傳遞原則
ms.author: lolaj
author: lolajacobsen
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.messagingpolicies.overview
- seo-marvel-apr2020
description: 在本文中，您將瞭解訊息原則，以及如何使用它們來控制團隊中的聊天訊息。
ms.openlocfilehash: c29697c8ec4d235ed232616e34590351bea59e9e
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/06/2020
ms.locfileid: "45042975"
---
# <a name="manage-messaging-policies-in-teams"></a><span data-ttu-id="de0b4-103">管理小組中的訊息傳遞原則</span><span class="sxs-lookup"><span data-stu-id="de0b4-103">Manage messaging policies in Teams</span></span>

<!--- Add zone marker here--->

<span data-ttu-id="de0b4-104">管理原則是用來控制 Microsoft Teams. 中使用者可使用的聊天及頻道訊息功能。</span><span class="sxs-lookup"><span data-stu-id="de0b4-104">Messaging policies are used to control which chat and channel messaging features are available to users in Microsoft Teams.</span></span> <span data-ttu-id="de0b4-105">您可以使用 [全域（組織範圍預設值）] 原則，自動建立或建立及指派自訂的訊息原則。</span><span class="sxs-lookup"><span data-stu-id="de0b4-105">You can use the global (Org-wide default) policy that's created automatically or create and assign custom messaging policies.</span></span>

<span data-ttu-id="de0b4-106">除非您建立並指派自訂原則，否則貴組織中的使用者將會自動取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="de0b4-106">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="de0b4-107">您可以編輯全域原則中的設定，或建立並指派一或多個自訂原則，以開啟或關閉您想要的功能。</span><span class="sxs-lookup"><span data-stu-id="de0b4-107">You can edit the settings in the global policy or create and assign one or more custom policies to turn on or turn off the features that you want.</span></span>

## <a name="create-a-custom-messaging-policy"></a><span data-ttu-id="de0b4-108">建立自訂的訊息原則</span><span class="sxs-lookup"><span data-stu-id="de0b4-108">Create a custom messaging policy</span></span>

1. <span data-ttu-id="de0b4-109">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**訊息規則**]。</span><span class="sxs-lookup"><span data-stu-id="de0b4-109">In the left navigation of the Microsoft Teams admin center, go to **Messaging policies**.</span></span>
2. <span data-ttu-id="de0b4-110">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="de0b4-110">Click **Add**.</span></span>
3. <span data-ttu-id="de0b4-111">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="de0b4-111">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="de0b4-112">選擇您想要的設定。</span><span class="sxs-lookup"><span data-stu-id="de0b4-112">Choose the settings that you want.</span></span>
5. <span data-ttu-id="de0b4-113">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="de0b4-113">Click **Save**.</span></span>

<span data-ttu-id="de0b4-114">例如，假設您想要確認已傳送的郵件不會被刪除或變更。</span><span class="sxs-lookup"><span data-stu-id="de0b4-114">For example, say you want to make sure that sent messages aren't deleted or altered.</span></span> <span data-ttu-id="de0b4-115">建立名為「保留已傳送郵件」的新自訂原則，然後關閉下列設定：</span><span class="sxs-lookup"><span data-stu-id="de0b4-115">Create a new custom policy named "Retain sent messages" and turn off the following settings:</span></span>

- <span data-ttu-id="de0b4-116">擁有者可以刪除已傳送的郵件</span><span class="sxs-lookup"><span data-stu-id="de0b4-116">Owners can delete sent messages</span></span>
- <span data-ttu-id="de0b4-117">使用者可以刪除已傳送的訊息</span><span class="sxs-lookup"><span data-stu-id="de0b4-117">Users can delete sent messages</span></span>
- <span data-ttu-id="de0b4-118">使用者可以編輯已傳送的郵件</span><span class="sxs-lookup"><span data-stu-id="de0b4-118">Users can edit sent messages</span></span>

<span data-ttu-id="de0b4-119">然後將原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="de0b4-119">Then assign the policy to users.</span></span>

## <a name="edit-a-messaging-policy"></a><span data-ttu-id="de0b4-120">編輯訊息原則</span><span class="sxs-lookup"><span data-stu-id="de0b4-120">Edit a messaging policy</span></span>

<span data-ttu-id="de0b4-121">您可以為全域原則編輯您建立的任何自訂原則。</span><span class="sxs-lookup"><span data-stu-id="de0b4-121">You can edit the global policy an any custom policies that you create.</span></span> 

1. <span data-ttu-id="de0b4-122">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**訊息規則**]。</span><span class="sxs-lookup"><span data-stu-id="de0b4-122">In the left navigation of the Microsoft Teams admin center, go to **Messaging policies**.</span></span>
2. <span data-ttu-id="de0b4-123">按一下原則名稱左邊的，然後按一下 [**編輯**]，選取原則。</span><span class="sxs-lookup"><span data-stu-id="de0b4-123">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="de0b4-124">您可以從這裡進行所要的變更。</span><span class="sxs-lookup"><span data-stu-id="de0b4-124">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="de0b4-125">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="de0b4-125">Click **Save**.</span></span>

## <a name="assign-a-custom-messaging-policy-to-users"></a><span data-ttu-id="de0b4-126">將自訂訊息策略指派給使用者</span><span class="sxs-lookup"><span data-stu-id="de0b4-126">Assign a custom messaging policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="de0b4-127">一次只能有一個使用者指派一個郵件服務原則。</span><span class="sxs-lookup"><span data-stu-id="de0b4-127">A user can only be assigned one messaging policy at a time.</span></span>

> [!NOTE]
> <span data-ttu-id="de0b4-128">如果使用者已獲指派，您就無法刪除原則。</span><span class="sxs-lookup"><span data-stu-id="de0b4-128">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="de0b4-129">您必須先將其他原則指派給所有受影響的使用者，然後才能刪除原始原則。</span><span class="sxs-lookup"><span data-stu-id="de0b4-129">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a><span data-ttu-id="de0b4-130">訊息原則設定</span><span class="sxs-lookup"><span data-stu-id="de0b4-130">Messaging policy settings</span></span>

<span data-ttu-id="de0b4-131">以下是您可以設定的訊息原則設定。</span><span class="sxs-lookup"><span data-stu-id="de0b4-131">Here are the messaging policy settings that you can configure.</span></span>

- <span data-ttu-id="de0b4-132">**擁有者可以刪除已傳送的郵件** 使用此設定可讓擁有者刪除使用者在聊天中傳送的訊息。</span><span class="sxs-lookup"><span data-stu-id="de0b4-132">**Owners can delete sent messages**  Use this setting to let owners delete messages that users sent in chat.</span></span>
- <span data-ttu-id="de0b4-133">**使用者可以刪除已傳送的訊息**使用此設定可讓使用者刪除其在聊天中傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="de0b4-133">**Users can delete sent messages** Use this setting to let users delete messages that they sent in chat.</span></span>
- <span data-ttu-id="de0b4-134">**使用者可以編輯已傳送的郵件**使用此設定可讓使用者編輯其在聊天中傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="de0b4-134">**Users can edit sent messages** Use this setting to let users edit the messages that they sent in chat.</span></span>
- <span data-ttu-id="de0b4-135">已**讀回執**[已讀] 回執可讓聊天訊息的寄件者在1:1 和群組聊天20人或更少的收件者朗讀其郵件時收到通知。</span><span class="sxs-lookup"><span data-stu-id="de0b4-135">**Read receipts** Read receipts allow the sender of a chat message to be notified when their message was read by the recipient in 1:1 and group chats 20 people or less.</span></span> <span data-ttu-id="de0b4-136">郵件讀信回條移除郵件是否已讀取的 uncertainly，以及改善小組溝通。</span><span class="sxs-lookup"><span data-stu-id="de0b4-136">Message read receipts remove uncertainly about whether a message was read, and improve team communication.</span></span> <span data-ttu-id="de0b4-137">請注意，在 eDiscovery 報表中不會捕獲讀信回條。</span><span class="sxs-lookup"><span data-stu-id="de0b4-137">Please note that read receipts are not captured in eDiscovery reporting.</span></span>  
    - <span data-ttu-id="de0b4-138">**使用者控制**這表示使用者可以決定是否要開啟或關閉 [已讀] 回執。</span><span class="sxs-lookup"><span data-stu-id="de0b4-138">**User controlled** This means that users get to decide if they want read receipts ON or OFF.</span></span> <span data-ttu-id="de0b4-139">App 內的預設設定為 [開啟]。</span><span class="sxs-lookup"><span data-stu-id="de0b4-139">Default setting within the app is ON.</span></span> <span data-ttu-id="de0b4-140">然後，使用者就可以將它關閉。</span><span class="sxs-lookup"><span data-stu-id="de0b4-140">Users can then turn it OFF.</span></span>
    - <span data-ttu-id="de0b4-141">**針對所有人**這表示租使用者中的所有人都可以開啟此功能，沒有任何選項可將其關閉。</span><span class="sxs-lookup"><span data-stu-id="de0b4-141">**On for everyone** This means everyone in the tenant will have the feature ON with no option to turn it off.</span></span> <span data-ttu-id="de0b4-142">請注意，為整個租**使用者**設定回執的唯一方式，就是只針對整個租使用者（名為「全域（組織範圍的預設值）」的預設原則），或在租使用者中的所有訊息原則都使用相同的收據設定。</span><span class="sxs-lookup"><span data-stu-id="de0b4-142">Be aware that when using the **On for everyone** setting, the only way to set receipts for the whole tenant is either to have only one messaging policy for the whole tenant (the default policy named "Global (Org-wide Default)") or to have all messaging policies in the tenant use the same settings for receipts.</span></span> <span data-ttu-id="de0b4-143">當**針對所有人**啟用此功能時，[已讀] 的 [已讀] 功能最有效。</span><span class="sxs-lookup"><span data-stu-id="de0b4-143">The read receipts feature is most effective when the feature is enabled to **On for everyone**.</span></span>
    - <span data-ttu-id="de0b4-144">**針對所有人關閉**這表示該功能已停用，且租使用者沒有讀信回條，也無法將它開啟。</span><span class="sxs-lookup"><span data-stu-id="de0b4-144">**Off for everyone** This means the feature is disabled and no one in the tenant has read receipts nor can they turn it on.</span></span>
<span data-ttu-id="de0b4-145"><a name="bkchat"> </a></span><span class="sxs-lookup"><span data-stu-id="de0b4-145"><a name="bkchat"> </a></span></span>

- <span data-ttu-id="de0b4-146">**聊天** 如果您希望貴組織中的使用者能夠使用 [團隊] app 與其他人聊天，請開啟此設定。</span><span class="sxs-lookup"><span data-stu-id="de0b4-146">**Chat**  Turn this setting on if you want users in your organization to be able to use the Teams app to chat with other people.</span></span>
- <span data-ttu-id="de0b4-147">**在交談中使用 giphy** 如果您開啟此選項，使用者可以在與其他人的聊天交談中加入 Giphy。</span><span class="sxs-lookup"><span data-stu-id="de0b4-147">**Use Giphys in conversations**  If you turn this on, users can include Giphys in chat conversations with other people.</span></span> <span data-ttu-id="de0b4-148">Giphy 是線上資料庫和搜尋引擎，可讓使用者搜尋及共用動畫 GIF 檔案。</span><span class="sxs-lookup"><span data-stu-id="de0b4-148">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="de0b4-149">每個 Giphy 都會獲指派內容評級。</span><span class="sxs-lookup"><span data-stu-id="de0b4-149">Each Giphy is assigned a content rating.</span></span>
- <span data-ttu-id="de0b4-150">**Giphy 內容評等**</span><span class="sxs-lookup"><span data-stu-id="de0b4-150">**Giphy content rating**</span></span>
    - <span data-ttu-id="de0b4-151">**無限制**這表示無論內容分級為何，您的使用者都能在聊天中插入任何 Giphy。</span><span class="sxs-lookup"><span data-stu-id="de0b4-151">**No restriction** This means that your users will be able to insert any Giphy in chats regardless of the content rating.</span></span>
    - <span data-ttu-id="de0b4-152">**中等** 這表示您的使用者可以在聊天中插入 Giphy，但會將其從成人內容適度限制。</span><span class="sxs-lookup"><span data-stu-id="de0b4-152">**Moderate**  This means that your users will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
    - <span data-ttu-id="de0b4-153">**嚴格** 這表示您的使用者將能夠在聊天中插入 Giphy，但會嚴格限制成人內容。</span><span class="sxs-lookup"><span data-stu-id="de0b4-153">**Strict**  This means that your users will be able to insert Giphys in chats, but will be strictly restricted from adult content.</span></span>
- <span data-ttu-id="de0b4-154">**在交談中使用 meme**如果您開啟此選項，使用者可以在與其他人的聊天交談中加入 Meme。</span><span class="sxs-lookup"><span data-stu-id="de0b4-154">**Use Memes in conversations** If you turn this on, users can include Memes in chat conversations with other people.</span></span>
- <span data-ttu-id="de0b4-155">**在交談中使用不乾膠標籤**如果您開啟此選項，使用者可以在聊天與其他人交談中加入貼紙。</span><span class="sxs-lookup"><span data-stu-id="de0b4-155">**Use Stickers in conversations** If you turn this on, users can include Stickers in chat conversations with other people.</span></span>
- <span data-ttu-id="de0b4-156">**允許 URL 預覽**使用此設定可開啟或關閉郵件的自動 URL 預覽。</span><span class="sxs-lookup"><span data-stu-id="de0b4-156">**Allow URL previews** Use this setting to turn automatic URL previewing on or off in messages.</span></span>
- <span data-ttu-id="de0b4-157">**允許使用者翻譯郵件**開啟此設定可讓使用者自動將小組郵件翻譯成由 Microsoft 365 或 Office 365 的個人語言設定所指定的語言。</span><span class="sxs-lookup"><span data-stu-id="de0b4-157">**Allow users to translate messages** Turn this setting on to let users automatically translate Teams messages into the language specified by their personal language settings for Microsoft 365 or Office 365.</span></span>
- <span data-ttu-id="de0b4-158">**允許沉浸式閱讀程式查看郵件**開啟此設定可讓使用者在 Microsoft 沉浸式閱讀程式中查看郵件。</span><span class="sxs-lookup"><span data-stu-id="de0b4-158">**Allow immersive reader for viewing messages** Turn this setting on to let users view messages in Microsoft Immersive Reader.</span></span> <span data-ttu-id="de0b4-159">沉浸式閱讀程式是一種學習工具，可提供全螢幕閱讀體驗，以增強文字的可讀性。</span><span class="sxs-lookup"><span data-stu-id="de0b4-159">Immersive Reader is a learning tool that provides a full screen reading experience to increase readability of text.</span></span>
- <span data-ttu-id="de0b4-160">**使用優先順序通知傳送緊急郵件**如果您開啟此選項，使用者可以使用[優先順序通知](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462)傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="de0b4-160">**Send urgent messages using priority notifications** If you turn this on, users can send messages using [priority notifications](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462).</span></span> <span data-ttu-id="de0b4-161">[優先順序通知] 會每隔兩分鐘通知使用者一段20分鐘，或直到收件者收到標示為*緊急*的郵件，以及時最大限度地處理郵件的可能性。</span><span class="sxs-lookup"><span data-stu-id="de0b4-161">Priority notifications notify users every 2 minutes for a period of 20 minutes or until messages that are marked as *urgent* are picked up and read by the recipient, maximizing the likelihood that the message is acted upon in a timely manner.</span></span>
- <span data-ttu-id="de0b4-162">**建立音訊訊息**</span><span class="sxs-lookup"><span data-stu-id="de0b4-162">**Audio message creation**</span></span> 
  > [!Important]
  > <span data-ttu-id="de0b4-163">不會在 eDiscovery 報表中捕獲音訊訊息。</span><span class="sxs-lookup"><span data-stu-id="de0b4-163">Audio messages are not captured in eDiscovery reporting.</span></span>
    - <span data-ttu-id="de0b4-164">**在聊天和頻道中允許**這表示使用者可以在聊天和頻道中留下音訊訊息。</span><span class="sxs-lookup"><span data-stu-id="de0b4-164">**Allowed in chats and channels** This means that users can leave audio messages in both chats and channels.</span></span>
    - <span data-ttu-id="de0b4-165">**僅允許在聊天中使用**這表示使用者可以將音訊訊息留在聊天中，而不是頻道中。</span><span class="sxs-lookup"><span data-stu-id="de0b4-165">**Allowed in chats only** This means that users can leave audio messages in chats, but not in channels.</span></span>
    - <span data-ttu-id="de0b4-166">**停用**這表示使用者無法在聊天或頻道中建立音訊訊息。</span><span class="sxs-lookup"><span data-stu-id="de0b4-166">**Disabled** This means that users cannot create audio messages in chats or channels.</span></span>  
- <span data-ttu-id="de0b4-167">**在行動裝置上，顯示最近聊天上的最愛頻道**啟用此設定可將最愛的頻道移至行動裝置畫面頂端，這樣使用者就不需要滾動就能找到。</span><span class="sxs-lookup"><span data-stu-id="de0b4-167">**On mobile devices, display favorite channels above recent chats** Enable this setting to move favorite channels to the top of the mobile device screen so that a user doesn't need to scroll to find them.</span></span>
- <span data-ttu-id="de0b4-168">**允許使用者從群組聊天中移除使用者**開啟此設定可讓使用者從群組聊天中移除其他使用者。</span><span class="sxs-lookup"><span data-stu-id="de0b4-168">**Allow a user to remove users from a group chat** Turn this setting on to let a user remove other users from a group chat.</span></span> <span data-ttu-id="de0b4-169">此功能可讓您繼續與較少的人進行交談，而不會遺失聊天歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="de0b4-169">This feature lets you continue a chat with a smaller group of people without losing the chat history.</span></span>
- <span data-ttu-id="de0b4-170">**啟用建議的回復** 開啟此設定以啟用聊天訊息的建議回復。</span><span class="sxs-lookup"><span data-stu-id="de0b4-170">**Enable suggested replies**  Turn this setting on to enable suggested replies for chat messages.</span></span>

> [!NOTE]
> <span data-ttu-id="de0b4-171">某些設定（例如使用 Giphy）也可以由小組擁有者在小組階層和私人通道擁有者設定為私人通道層級。</span><span class="sxs-lookup"><span data-stu-id="de0b4-171">Some of these settings, such using Giphys, can also be configured at the team level by team owners and at the private channel level by private channel owners.</span></span>

### <a name="related-topics"></a><span data-ttu-id="de0b4-172">相關主題</span><span class="sxs-lookup"><span data-stu-id="de0b4-172">Related topics</span></span>

- [<span data-ttu-id="de0b4-173">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="de0b4-173">Assign policies to your users in Teams</span></span>](assign-policies.md)
