---
title: 在 Teams 中管理訊息原則
ms.author: serdars
author: SerdarSoysal
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
description: 瞭解傳訊政策，以及如何在聊天訊息中控制聊天Teams。
ms.openlocfilehash: 5b202d0a1895c3fd9b4279d6a7db072cd18f72ad
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689781"
---
# <a name="manage-messaging-policies-in-teams"></a><span data-ttu-id="7f060-103">在 Teams 中管理訊息原則</span><span class="sxs-lookup"><span data-stu-id="7f060-103">Manage messaging policies in Teams</span></span>

<!--- Add zone marker here--->

<span data-ttu-id="7f060-104">傳訊政策是用來控制哪些聊天和頻道訊息功能可供使用者 (擁有者和成員[) 使用](assign-roles-permissions.md)Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="7f060-104">Messaging policies are used to control which chat and channel messaging features are available to [users (owners and members)](assign-roles-permissions.md) in Microsoft Teams.</span></span> <span data-ttu-id="7f060-105">您可以使用自動建立 (全組織的預設) ，或建立及指派自訂訊息策略。</span><span class="sxs-lookup"><span data-stu-id="7f060-105">You can use the global (Org-wide default) policy that's created automatically or create and assign custom messaging policies.</span></span>

<span data-ttu-id="7f060-106">除非您建立並指派自訂策略，否則貴組織中使用者會自動取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="7f060-106">Users in your organization will automatically get the global policy, unless you create and assign a custom policy.</span></span> <span data-ttu-id="7f060-107">編輯全域原則中的設定，或建立並指派一或多個自訂策略來開啟或關閉您想要的功能。</span><span class="sxs-lookup"><span data-stu-id="7f060-107">Edit the settings in the global policy or create and assign one or more custom policies to turn on or turn off the features that you want.</span></span>

## <a name="create-a-custom-messaging-policy"></a><span data-ttu-id="7f060-108">建立自訂訊息策略</span><span class="sxs-lookup"><span data-stu-id="7f060-108">Create a custom messaging policy</span></span>

1. <span data-ttu-id="7f060-109">在系統管理中心的左側導Microsoft Teams，請前往 **訊息策略**。</span><span class="sxs-lookup"><span data-stu-id="7f060-109">In the left navigation of the Microsoft Teams admin center, go to **Messaging policies**.</span></span>
2. <span data-ttu-id="7f060-110">選取 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="7f060-110">Select **Add**.</span></span>
3. <span data-ttu-id="7f060-111">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="7f060-111">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="7f060-112">選擇您想要的設定。</span><span class="sxs-lookup"><span data-stu-id="7f060-112">Choose the settings that you want.</span></span>
5. <span data-ttu-id="7f060-113">選取 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="7f060-113">Select **Save**.</span></span>

<span data-ttu-id="7f060-114">例如，您想要確認未刪除或變更已送出的郵件。</span><span class="sxs-lookup"><span data-stu-id="7f060-114">For example, you want to make sure that sent messages aren't deleted or altered.</span></span> <span data-ttu-id="7f060-115">建立名為「保留已寄郵件」的新自訂策略，並關閉下列設定：</span><span class="sxs-lookup"><span data-stu-id="7f060-115">Create a new custom policy named "Retain sent messages" and turn off the following settings:</span></span>

- <span data-ttu-id="7f060-116">擁有者可以刪除已送出的郵件</span><span class="sxs-lookup"><span data-stu-id="7f060-116">Owners can delete sent messages</span></span>
- <span data-ttu-id="7f060-117">使用者可以刪除已送出的郵件</span><span class="sxs-lookup"><span data-stu-id="7f060-117">Users can delete sent messages</span></span>
- <span data-ttu-id="7f060-118">使用者可以編輯已送出的郵件</span><span class="sxs-lookup"><span data-stu-id="7f060-118">Users can edit sent messages</span></span>

<span data-ttu-id="7f060-119">然後將該策略指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="7f060-119">Then assign the policy to users.</span></span>

## <a name="edit-a-messaging-policy"></a><span data-ttu-id="7f060-120">編輯訊息策略</span><span class="sxs-lookup"><span data-stu-id="7f060-120">Edit a messaging policy</span></span>

<span data-ttu-id="7f060-121">您可以編輯全域原則和您建立的任何自訂原則。</span><span class="sxs-lookup"><span data-stu-id="7f060-121">You can edit the global policy and any custom policies that you create.</span></span>

1. <span data-ttu-id="7f060-122">在系統管理中心的左側導Microsoft Teams，請前往 **訊息策略**。</span><span class="sxs-lookup"><span data-stu-id="7f060-122">In the left navigation of the Microsoft Teams admin center, go to **Messaging policies**.</span></span>
2. <span data-ttu-id="7f060-123">按一下原則名稱左側來選取原則，然後選取 [編輯 **]**。</span><span class="sxs-lookup"><span data-stu-id="7f060-123">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>
3. <span data-ttu-id="7f060-124">從此處，進行您需要的變更。</span><span class="sxs-lookup"><span data-stu-id="7f060-124">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="7f060-125">選取 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="7f060-125">Select **Save**.</span></span>

## <a name="assign-a-custom-messaging-policy-to-users"></a><span data-ttu-id="7f060-126">指派自訂訊息策略給使用者</span><span class="sxs-lookup"><span data-stu-id="7f060-126">Assign a custom messaging policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="7f060-127">一次只能指派一個訊息策略給使用者。</span><span class="sxs-lookup"><span data-stu-id="7f060-127">A user can only be assigned one messaging policy at a time.</span></span>

> [!NOTE]
> <span data-ttu-id="7f060-128">如果已將原則指派給使用者，就無法刪除該原則。</span><span class="sxs-lookup"><span data-stu-id="7f060-128">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="7f060-129">您必須先為所有受影響的使用者指派不同的原則，之後才可以刪除原始原則。</span><span class="sxs-lookup"><span data-stu-id="7f060-129">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a><span data-ttu-id="7f060-130">訊息策略設定</span><span class="sxs-lookup"><span data-stu-id="7f060-130">Messaging policy settings</span></span>

<span data-ttu-id="7f060-131">以下是您可以設定的訊息原則設定。</span><span class="sxs-lookup"><span data-stu-id="7f060-131">Here are the messaging policy settings that you can configure.</span></span>

- <span data-ttu-id="7f060-132">**擁有者可以刪除已送出的郵件**  使用此設定，讓擁有者刪除使用者在聊天中送出的郵件。</span><span class="sxs-lookup"><span data-stu-id="7f060-132">**Owners can delete sent messages**  Use this setting to let owners delete messages that users sent in chat.</span></span>
- <span data-ttu-id="7f060-133">**使用者可以刪除已送出的郵件** 使用此設定可讓使用者刪除他們在聊天中送出的郵件。</span><span class="sxs-lookup"><span data-stu-id="7f060-133">**Users can delete sent messages** Use this setting to let users delete messages that they sent in chat.</span></span>
- <span data-ttu-id="7f060-134">**使用者可以編輯已送出的郵件** 使用此設定可讓使用者編輯他們在聊天中送出的郵件。</span><span class="sxs-lookup"><span data-stu-id="7f060-134">**Users can edit sent messages** Use this setting to let users edit the messages that they sent in chat.</span></span>
- <span data-ttu-id="7f060-135">**已讀取回條** 讀取回條允許當收件者以 1：1 讀取其訊息，以及群組聊天 20 人以下時，通知聊天訊息的寄件者。</span><span class="sxs-lookup"><span data-stu-id="7f060-135">**Read receipts** Read receipts allow the sender of a chat message to be notified when their message was read by the recipient in 1:1 and group chats 20 people or fewer.</span></span> <span data-ttu-id="7f060-136">郵件讀信回條會不確定地移除郵件是否已讀取，並改善小組溝通。</span><span class="sxs-lookup"><span data-stu-id="7f060-136">Message read receipts remove uncertainly about whether a message was read, and improve team communication.</span></span> <span data-ttu-id="7f060-137">電子資料探索報告不會捕獲已讀回條。</span><span class="sxs-lookup"><span data-stu-id="7f060-137">Read receipts aren't captured in eDiscovery reporting.</span></span>  
    - <span data-ttu-id="7f060-138">**使用者控制** 這表示使用者可以決定是否要讀取回條為 ON 或 OFF。</span><span class="sxs-lookup"><span data-stu-id="7f060-138">**User controlled** This means that users get to decide if they want read receipts ON or OFF.</span></span> <span data-ttu-id="7f060-139">應用程式內的預設設定為 ON。</span><span class="sxs-lookup"><span data-stu-id="7f060-139">Default setting within the app is ON.</span></span> <span data-ttu-id="7f060-140">使用者接著可以將其關閉。</span><span class="sxs-lookup"><span data-stu-id="7f060-140">Users can then turn it OFF.</span></span>
    - <span data-ttu-id="7f060-141">**適用于所有人的 On** 這表示租使用者中的每個人都將擁有開啟功能，沒有關閉功能的選項。</span><span class="sxs-lookup"><span data-stu-id="7f060-141">**On for everyone** This means everyone in the tenant will have the feature ON with no option to turn it off.</span></span> <span data-ttu-id="7f060-142">使用適用于所有人的 On 設定時，為整個租使用者設定回條的唯一方法，就是為整個租使用者設定一個訊息策略 (稱為「全域 (全組織預設) 」) ，或是讓租使用者中所有的訊息策略都使用相同的接收設定。</span><span class="sxs-lookup"><span data-stu-id="7f060-142">When using the **On for everyone** setting, the only way to set receipts for the whole tenant is either to have only one messaging policy for the whole tenant (the default policy named "Global (Org-wide Default)") or to have all messaging policies in the tenant use the same settings for receipts.</span></span> <span data-ttu-id="7f060-143">當此功能對 [針對每個人開啟 **]** 啟用時，讀信回條功能最為有效。</span><span class="sxs-lookup"><span data-stu-id="7f060-143">The read receipts feature is most effective when the feature is enabled to **On for everyone**.</span></span>
    - <span data-ttu-id="7f060-144">**針對所有人關閉** 這表示此功能已停用，而且租使用者中沒有人已讀取回條，也無法開啟。</span><span class="sxs-lookup"><span data-stu-id="7f060-144">**Off for everyone** This means the feature is disabled and no one in the tenant has read receipts nor can they turn it on.</span></span>
<span data-ttu-id="7f060-145"><a name="bkchat"> </a></span><span class="sxs-lookup"><span data-stu-id="7f060-145"><a name="bkchat"> </a></span></span>

- <span data-ttu-id="7f060-146">**聊天** 如果您希望貴組織的使用者能夠使用 Teams應用程式與其他人員聊天，請開啟此設定。</span><span class="sxs-lookup"><span data-stu-id="7f060-146">**Chat**  Turn this setting on if you want users in your organization to be able to use the Teams app to chat with other people.</span></span>
- <span data-ttu-id="7f060-147">**在交談中使用 Giphys**  如果您開啟 Giphys，使用者可以在與他人的聊天交談中納入 Giphys。</span><span class="sxs-lookup"><span data-stu-id="7f060-147">**Use Giphys in conversations**  If you turn on Giphys, users can include Giphys in chat conversations with other people.</span></span> <span data-ttu-id="7f060-148">Giphy 是線上資料庫和搜尋引擎，允許使用者搜尋和共用 GIF 動畫檔案。</span><span class="sxs-lookup"><span data-stu-id="7f060-148">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="7f060-149">每個 Giphy 都有內容分級。</span><span class="sxs-lookup"><span data-stu-id="7f060-149">Each Giphy is assigned a content rating.</span></span> <span data-ttu-id="7f060-150">除了開啟此設定之外，您還需要啟用選擇性連線 [體驗](/deployoffice/privacy/manage-privacy-controls#policy-setting-for-optional-connected-experiences) ，才能在交談中允許 Giphys。</span><span class="sxs-lookup"><span data-stu-id="7f060-150">In addition to turning on this setting, you need to enable [Optional Connected Experiences](/deployoffice/privacy/manage-privacy-controls#policy-setting-for-optional-connected-experiences) to allow Giphys in conversations.</span></span>
- <span data-ttu-id="7f060-151">**Giphy 內容分級**</span><span class="sxs-lookup"><span data-stu-id="7f060-151">**Giphy content rating**</span></span>
    - <span data-ttu-id="7f060-152">**沒有限制** 這表示無論內容分級如何，您的使用者都能在聊天中插入任何 Giphy。</span><span class="sxs-lookup"><span data-stu-id="7f060-152">**No restriction** This means that your users will be able to insert any Giphy in chats regardless of the content rating.</span></span>
    - <span data-ttu-id="7f060-153">**中等**  這表示您的使用者將能夠在聊天中插入 Giphys，但會受到成人內容的中等限制。</span><span class="sxs-lookup"><span data-stu-id="7f060-153">**Moderate**  This means that your users will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
    - <span data-ttu-id="7f060-154">**嚴格**  這表示您的使用者將能夠在聊天中插入 Giphys，但會嚴格限制成人內容。</span><span class="sxs-lookup"><span data-stu-id="7f060-154">**Strict**  This means that your users will be able to insert Giphys in chats, but will be strictly restricted from adult content.</span></span>
- <span data-ttu-id="7f060-155">**在交談中使用 Meme** 如果您開啟 Memes，使用者可以在與他人的聊天交談中納入 Memes。</span><span class="sxs-lookup"><span data-stu-id="7f060-155">**Use Memes in conversations** If you turn Memes on, users can include Memes in chat conversations with other people.</span></span>
- <span data-ttu-id="7f060-156">**在交談中使用貼圖** 如果您開啟此選項，使用者可以在與他人的聊天交談中納入貼圖。</span><span class="sxs-lookup"><span data-stu-id="7f060-156">**Use Stickers in conversations** If you turn this on, users can include Stickers in chat conversations with other people.</span></span>
- <span data-ttu-id="7f060-157">**允許 URL 預覽** 使用此設定可開啟或關閉郵件中的自動 URL 預覽。</span><span class="sxs-lookup"><span data-stu-id="7f060-157">**Allow URL previews** Use this setting to turn automatic URL previewing on or off in messages.</span></span>
- <span data-ttu-id="7f060-158">**允許使用者翻譯郵件** 開啟此設定，讓使用者自動將Teams訊息翻譯成其個人語言設定所指定的語言，Microsoft 365或Office 365。</span><span class="sxs-lookup"><span data-stu-id="7f060-158">**Allow users to translate messages** Turn this setting on to let users automatically translate Teams messages into the language specified by their personal language settings for Microsoft 365 or Office 365.</span></span>
- <span data-ttu-id="7f060-159">**允許沉浸式閱讀程式檢視郵件** 開啟此設定，讓使用者在 Microsoft 沈浸式閱讀程式。</span><span class="sxs-lookup"><span data-stu-id="7f060-159">**Allow immersive reader for viewing messages** Turn this setting on to let users view messages in Microsoft Immersive Reader.</span></span> <span data-ttu-id="7f060-160">沈浸式閱讀程式是一種學習工具，可提供全螢幕閱讀體驗，提高文字的可讀性。</span><span class="sxs-lookup"><span data-stu-id="7f060-160">Immersive Reader is a learning tool that provides a full screen reading experience to increase readability of text.</span></span>
- <span data-ttu-id="7f060-161">**使用優先順序通知傳送緊急郵件** 如果您開啟此選項，使用者可以使用優先順序通知 [傳送郵件](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462)。</span><span class="sxs-lookup"><span data-stu-id="7f060-161">**Send urgent messages using priority notifications** If you turn this on, users can send messages using [priority notifications](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462).</span></span> <span data-ttu-id="7f060-162">優先順序通知會每隔 2 分鐘通知使用者 20 分鐘，或直到收件者選取並讀取標示為緊急的郵件。</span><span class="sxs-lookup"><span data-stu-id="7f060-162">Priority notifications notify users every 2 minutes for 20 minutes or until messages that are marked as *urgent* are picked up and read by the recipient.</span></span> <span data-ttu-id="7f060-163">這項功能會增加郵件及時處理的可能性。</span><span class="sxs-lookup"><span data-stu-id="7f060-163">This feature increases the likelihood that the message is acted upon in a timely manner.</span></span>
- <span data-ttu-id="7f060-164">**音訊訊息建立**</span><span class="sxs-lookup"><span data-stu-id="7f060-164">**Audio message creation**</span></span>
  > [!Important]
  > <span data-ttu-id="7f060-165">eDiscovery 報表不會捕獲音訊訊息。</span><span class="sxs-lookup"><span data-stu-id="7f060-165">Audio messages are not captured in eDiscovery reporting.</span></span>
    - <span data-ttu-id="7f060-166">**在聊天和頻道中允許** 這表示使用者可以在聊天和頻道中留下音訊訊息。</span><span class="sxs-lookup"><span data-stu-id="7f060-166">**Allowed in chats and channels** This means that users can leave audio messages in both chats and channels.</span></span>
    - <span data-ttu-id="7f060-167">**僅允許在聊天中** 這表示使用者可以在聊天中保留音訊訊息，但不能在頻道中留言。</span><span class="sxs-lookup"><span data-stu-id="7f060-167">**Allowed in chats only** This means that users can leave audio messages in chats, but not in channels.</span></span>
    - <span data-ttu-id="7f060-168">**已停用** 這表示使用者無法在聊天或頻道中建立音訊訊息。</span><span class="sxs-lookup"><span data-stu-id="7f060-168">**Disabled** This means that users cannot create audio messages in chats or channels.</span></span>  
- <span data-ttu-id="7f060-169">**在行動裝置上，顯示最近聊天上方的最愛頻道** 啟用此設定，將最愛的頻道移至行動裝置畫面的頂端，讓使用者不需要捲動來尋找。</span><span class="sxs-lookup"><span data-stu-id="7f060-169">**On mobile devices, display favorite channels above recent chats** Enable this setting to move favorite channels to the top of the mobile device screen so that a user doesn't need to scroll to find them.</span></span>
- <span data-ttu-id="7f060-170">**允許使用者從群組聊天移除使用者** 開啟此設定，讓使用者從群組聊天移除其他使用者。</span><span class="sxs-lookup"><span data-stu-id="7f060-170">**Allow a user to remove users from a group chat** Turn this setting on to let a user remove other users from a group chat.</span></span> <span data-ttu-id="7f060-171">這項功能可讓您繼續與較小的一群人員聊天，而不會失去聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="7f060-171">This feature lets you continue a chat with a smaller group of people without losing the chat history.</span></span>
- <span data-ttu-id="7f060-172">**啟用建議的回復**  開啟此設定以啟用聊天訊息的建議回復。</span><span class="sxs-lookup"><span data-stu-id="7f060-172">**Enable suggested replies**  Turn this setting on to enable suggested replies for chat messages.</span></span>
- <span data-ttu-id="7f060-173">**聊天許可權角色** 使用此設定可定義使用者的監督聊天角色。</span><span class="sxs-lookup"><span data-stu-id="7f060-173">**Chat permission role** Use this setting to define the supervised chat role of the user.</span></span>  <span data-ttu-id="7f060-174">深入了解[監督的聊天](supervise-chats-edu.md)。</span><span class="sxs-lookup"><span data-stu-id="7f060-174">Learn more about [supervised chat](supervise-chats-edu.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7f060-175">其中一些設定 ，例如使用 Giphys，也可以由團隊擁有者在團隊層級設定，而私人頻道擁有者也可以設定在私人頻道層級。</span><span class="sxs-lookup"><span data-stu-id="7f060-175">Some of these settings, such using Giphys, can also be configured at the team level by team owners and at the private channel level by private channel owners.</span></span>

### <a name="related-topics"></a><span data-ttu-id="7f060-176">相關主題</span><span class="sxs-lookup"><span data-stu-id="7f060-176">Related topics</span></span>

- [<span data-ttu-id="7f060-177">為使用者和群組指派Teams</span><span class="sxs-lookup"><span data-stu-id="7f060-177">Assign policies to users and groups in Teams</span></span>](assign-policies-users-and-groups.md)
- [<span data-ttu-id="7f060-178">在 Microsoft Teams 中指派 Teams 擁有者和成員</span><span class="sxs-lookup"><span data-stu-id="7f060-178">Assign team owners and members in Microsoft Teams</span></span>](assign-roles-permissions.md)
