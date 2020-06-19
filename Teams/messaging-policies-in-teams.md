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
ms.openlocfilehash: 9e382f5dd23220cc1a97f2549430a75a79e47eb7
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756904"
---
# <a name="manage-messaging-policies-in-teams"></a><span data-ttu-id="6eb51-103">管理小組中的訊息傳遞原則</span><span class="sxs-lookup"><span data-stu-id="6eb51-103">Manage messaging policies in Teams</span></span>

<!--- Add zone marker here--->

<span data-ttu-id="6eb51-104">管理原則是用來控制 Microsoft Teams. 中使用者可使用的聊天及頻道訊息功能。</span><span class="sxs-lookup"><span data-stu-id="6eb51-104">Messaging policies are used to control which chat and channel messaging features are available to users in Microsoft Teams.</span></span> <span data-ttu-id="6eb51-105">您可以使用為貴組織中的人員自動建立或建立一或多個自訂訊息策略的預設原則。</span><span class="sxs-lookup"><span data-stu-id="6eb51-105">You can use the default policy that is created automatically or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="6eb51-106">建立原則之後，您可以將它指派給組織中的使用者或使用者群組。</span><span class="sxs-lookup"><span data-stu-id="6eb51-106">After you create a policy, you can assign it to a user or group of users in your organization.</span></span>

<span data-ttu-id="6eb51-107">根據預設，會建立名為 [全域] （組織範圍預設值）的原則。</span><span class="sxs-lookup"><span data-stu-id="6eb51-107">By default, a policy named Global (org-wide default) is created.</span></span> <span data-ttu-id="6eb51-108">貴組織中的所有使用者預設都會獲指派這項訊息原則。</span><span class="sxs-lookup"><span data-stu-id="6eb51-108">All users in your organization will be assigned this messaging policy by default.</span></span> <span data-ttu-id="6eb51-109">您可以對此原則進行變更，或是建立一或多個自訂原則，並將使用者指派給他們。</span><span class="sxs-lookup"><span data-stu-id="6eb51-109">You can either make changes to this policy or create one or more custom policies and assign users to them.</span></span> <span data-ttu-id="6eb51-110">當您建立自訂原則時，您可以允許或防止您的使用者使用某些功能，然後將它指派給將需要套用這些設定的一個或多個使用者。</span><span class="sxs-lookup"><span data-stu-id="6eb51-110">When you create a custom policy, you can allow or prevent certain features from being available to your users and then assign it to one or more users who will need the settings applied to them.</span></span>

## <a name="change-or-create-a-messaging-policy"></a><span data-ttu-id="6eb51-111">變更或建立訊息原則</span><span class="sxs-lookup"><span data-stu-id="6eb51-111">Change or create a messaging policy</span></span>

<span data-ttu-id="6eb51-112">您可以在 Microsoft 團隊系統管理中心輕鬆管理訊息原則（ https://admin.teams.microsoft.com) 方法是使用系統管理員認證登入，然後在左側流覽窗格中選擇 [**訊息原則**]）。</span><span class="sxs-lookup"><span data-stu-id="6eb51-112">You can easily manage messaging policies in the Microsoft Teams admin center (https://admin.teams.microsoft.com) by signing in with administrator credentials and choosing **Messaging policies** in the left navigation pane.</span></span> <span data-ttu-id="6eb51-113">若要編輯貴組織的現有預設訊息原則，請選取 [**全域（組織範圍預設值）** ] 列，然後進行您要的變更。</span><span class="sxs-lookup"><span data-stu-id="6eb51-113">To edit the existing default messaging policy for your organization, select the **Global (Org-wide default)** row, and then make your changes.</span></span> <span data-ttu-id="6eb51-114">若要建立新的自訂訊息原則，請選取 [**新增原則**]，為新原則命名，然後選取您的設定。</span><span class="sxs-lookup"><span data-stu-id="6eb51-114">To create a new custom messaging policy, select **New policy**, give the new policy a name, and then select your settings.</span></span> <span data-ttu-id="6eb51-115">完成後，請選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="6eb51-115">Choose **Save** when you are done.</span></span>

<span data-ttu-id="6eb51-116">例如，假設您想要確認已傳送的郵件不會被刪除或變更。</span><span class="sxs-lookup"><span data-stu-id="6eb51-116">For example, say you want to make sure that sent messages aren't deleted or altered.</span></span> <span data-ttu-id="6eb51-117">您可以建立名為「保留已傳送的郵件」的新自訂原則，然後關閉下列設定：</span><span class="sxs-lookup"><span data-stu-id="6eb51-117">You would create a new custom policy named "Retain sent messages" and turn off the following settings:</span></span>

- <span data-ttu-id="6eb51-118">擁有者可以刪除已傳送的郵件</span><span class="sxs-lookup"><span data-stu-id="6eb51-118">Owners can delete sent messages</span></span>
- <span data-ttu-id="6eb51-119">使用者可以刪除已傳送的訊息</span><span class="sxs-lookup"><span data-stu-id="6eb51-119">Users can delete sent messages</span></span>
- <span data-ttu-id="6eb51-120">使用者可以編輯已傳送的郵件</span><span class="sxs-lookup"><span data-stu-id="6eb51-120">Users can edit sent messages</span></span>

<span data-ttu-id="6eb51-121">然後，將原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="6eb51-121">Then assign the policy to the users.</span></span>

> [!NOTE]
> <span data-ttu-id="6eb51-122">一次只能有一個使用者指派一個郵件服務原則。</span><span class="sxs-lookup"><span data-stu-id="6eb51-122">A user can only be assigned one messaging policy at a time.</span></span>

## <a name="assign-a-messaging-policy-to-a-user"></a><span data-ttu-id="6eb51-123">指派訊息策略給使用者</span><span class="sxs-lookup"><span data-stu-id="6eb51-123">Assign a messaging policy to a user</span></span>

<span data-ttu-id="6eb51-124">如果您建立自訂的訊息策略，則只有在指派給該使用者的原則時，使用者才會使用該原則。</span><span class="sxs-lookup"><span data-stu-id="6eb51-124">If you create a custom messaging policy, it will only be active for a user if the policy is assigned to the user.</span></span> <span data-ttu-id="6eb51-125">若要將自訂原則指派給使用者，請移至 Microsoft 團隊系統管理中心，選擇左側功能窗格中的 [**使用者**]，然後選取您要指派原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="6eb51-125">To assign a custom policy to a user, go to the Microsoft Teams admin center, choose **Users** in the left navigation pane, and select the user you want to assign the policy to.</span></span> <span data-ttu-id="6eb51-126">在使用者的頁面上，選擇 [指派的**原則**] 旁的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="6eb51-126">On the user's page, choose **Edit** next to **Assigned policies**.</span></span> <span data-ttu-id="6eb51-127">接著，在 [**編輯使用者原則**] 窗格的 [**訊息原則**] 底下，從下拉式清單中選取 [訊息原則]，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="6eb51-127">Then, in the **Edit user policies** pane, under **Messaging policy**, select the messaging policy from the drop-down list, and select **Save**.</span></span> <span data-ttu-id="6eb51-128">您也可以在使用者清單中編輯設定。</span><span class="sxs-lookup"><span data-stu-id="6eb51-128">You can also edit settings from the list of users.</span></span> <span data-ttu-id="6eb51-129">若要這樣做，請按一下使用者的顯示名稱左方來選取使用者。</span><span class="sxs-lookup"><span data-stu-id="6eb51-129">To do this, select the user by clicking to the left of the user's display name.</span></span> <span data-ttu-id="6eb51-130">選取 [**編輯設定**]。</span><span class="sxs-lookup"><span data-stu-id="6eb51-130">Select **Edit settings**.</span></span> <span data-ttu-id="6eb51-131">接著，在 [**編輯設定**] 窗格的 [**訊息原則**] 底下，從下拉式清單中選取原則，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="6eb51-131">Then, on the **Edit settings** pane, under **Messaging policy**, select the policy from the drop-down list and then select **Save**.</span></span>

<span data-ttu-id="6eb51-132">如果您要將原則套用到一個以上的使用者，請按一下使用者名稱左邊的，然後選取 [**編輯設定**]，選取每個使用者。</span><span class="sxs-lookup"><span data-stu-id="6eb51-132">If you are applying a policy to more than one user, select each of the users by clicking to the left of the user name, and then select **Edit settings**.</span></span> <span data-ttu-id="6eb51-133">在 [**編輯設定**] 窗格的 [**訊息原則**] 底下，從下拉式清單中選取原則，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="6eb51-133">On the **Edit Settings** pane, under **Messaging policy**, select the policy from the drop-down list and then select **Save**.</span></span>

<span data-ttu-id="6eb51-134">您也可以將訊息策略指派給一或多個使用者，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6eb51-134">You can also assign a messaging policy to one or more users as follows:</span></span>

1. <span data-ttu-id="6eb51-135">移至**Microsoft 團隊**  >  **系統管理中心訊息原則**。</span><span class="sxs-lookup"><span data-stu-id="6eb51-135">Go to **Microsoft Teams admin center** > **Messaging policies**.</span></span>
2. <span data-ttu-id="6eb51-136">按一下原則名稱的左側來選取原則。</span><span class="sxs-lookup"><span data-stu-id="6eb51-136">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="6eb51-137">選取 [管理使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6eb51-137">Select **Manage users**.</span></span>
4. <span data-ttu-id="6eb51-138">在 **[管理使用者]** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="6eb51-138">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="6eb51-139">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="6eb51-139">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="6eb51-140">完成新增使用者時，選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="6eb51-140">When you are finished adding users, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="6eb51-141">如果使用者已獲指派，您就無法刪除原則。</span><span class="sxs-lookup"><span data-stu-id="6eb51-141">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="6eb51-142">您必須先將其他原則指派給所有受影響的使用者，然後才能刪除原始原則。</span><span class="sxs-lookup"><span data-stu-id="6eb51-142">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a><span data-ttu-id="6eb51-143">訊息原則設定</span><span class="sxs-lookup"><span data-stu-id="6eb51-143">Messaging policy settings</span></span>

<span data-ttu-id="6eb51-144">使用下列設定來變更全域訊息策略，或建立新的自訂原則：</span><span class="sxs-lookup"><span data-stu-id="6eb51-144">Use the following settings to change the global messaging policy or create a new custom policy:</span></span>

- <span data-ttu-id="6eb51-145">**擁有者可以刪除已傳送的郵件** 使用此設定可讓擁有者刪除使用者在聊天中傳送的訊息。</span><span class="sxs-lookup"><span data-stu-id="6eb51-145">**Owners can delete sent messages**  Use this setting to let owners delete messages that users sent in chat.</span></span>
- <span data-ttu-id="6eb51-146">**使用者可以刪除已傳送的訊息**使用此設定可讓使用者刪除其在聊天中傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="6eb51-146">**Users can delete sent messages** Use this setting to let users delete messages that they sent in chat.</span></span>
- <span data-ttu-id="6eb51-147">**使用者可以編輯已傳送的郵件**使用此設定可讓使用者編輯其在聊天中傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="6eb51-147">**Users can edit sent messages** Use this setting to let users edit the messages that they sent in chat.</span></span>
- <span data-ttu-id="6eb51-148">已**讀回執**[已讀] 回執可讓聊天訊息的寄件者在1:1 和群組聊天20人或更少的收件者朗讀其郵件時收到通知。</span><span class="sxs-lookup"><span data-stu-id="6eb51-148">**Read receipts** Read receipts allow the sender of a chat message to be notified when their message was read by the recipient in 1:1 and group chats 20 people or less.</span></span> <span data-ttu-id="6eb51-149">郵件讀信回條移除郵件是否已讀取的 uncertainly，以及改善小組溝通。</span><span class="sxs-lookup"><span data-stu-id="6eb51-149">Message read receipts remove uncertainly about whether a message was read, and improve team communication.</span></span> <span data-ttu-id="6eb51-150">請注意，在 eDiscovery 報表中不會捕獲讀信回條。</span><span class="sxs-lookup"><span data-stu-id="6eb51-150">Please note that read receipts are not captured in eDiscovery reporting.</span></span>  
    - <span data-ttu-id="6eb51-151">**使用者控制**這表示使用者可以決定是否要開啟或關閉 [已讀] 回執。</span><span class="sxs-lookup"><span data-stu-id="6eb51-151">**User controlled** This means that users get to decide if they want read receipts ON or OFF.</span></span> <span data-ttu-id="6eb51-152">App 內的預設設定為 [開啟]。</span><span class="sxs-lookup"><span data-stu-id="6eb51-152">Default setting within the app is ON.</span></span> <span data-ttu-id="6eb51-153">然後，使用者就可以將它關閉。</span><span class="sxs-lookup"><span data-stu-id="6eb51-153">Users can then turn it OFF.</span></span>
    - <span data-ttu-id="6eb51-154">**針對所有人**這表示租使用者中的所有人都可以開啟此功能，沒有任何選項可將其關閉。</span><span class="sxs-lookup"><span data-stu-id="6eb51-154">**On for everyone** This means everyone in the tenant will have the feature ON with no option to turn it off.</span></span> <span data-ttu-id="6eb51-155">請注意，為整個租**使用者**設定回執的唯一方式，就是只針對整個租使用者（名為「全域（組織範圍的預設值）」的預設原則），或在租使用者中的所有訊息原則都使用相同的收據設定。</span><span class="sxs-lookup"><span data-stu-id="6eb51-155">Be aware that when using the **On for everyone** setting, the only way to set receipts for the whole tenant is either to have only one messaging policy for the whole tenant (the default policy named "Global (Org-wide Default)") or to have all messaging policies in the tenant use the same settings for receipts.</span></span> <span data-ttu-id="6eb51-156">當**針對所有人**啟用此功能時，[已讀] 的 [已讀] 功能最有效。</span><span class="sxs-lookup"><span data-stu-id="6eb51-156">The read receipts feature is most effective when the feature is enabled to **On for everyone**.</span></span>
    - <span data-ttu-id="6eb51-157">**針對所有人關閉**這表示該功能已停用，且租使用者沒有讀信回條，也無法將它開啟。</span><span class="sxs-lookup"><span data-stu-id="6eb51-157">**Off for everyone** This means the feature is disabled and no one in the tenant has read receipts nor can they turn it on.</span></span>
<span data-ttu-id="6eb51-158"><a name="bkchat"> </a></span><span class="sxs-lookup"><span data-stu-id="6eb51-158"><a name="bkchat"> </a></span></span>

- <span data-ttu-id="6eb51-159">**聊天** 如果您希望貴組織中的使用者能夠使用 [團隊] app 與其他人聊天，請開啟此設定。</span><span class="sxs-lookup"><span data-stu-id="6eb51-159">**Chat**  Turn this setting on if you want users in your organization to be able to use the Teams app to chat with other people.</span></span>
- <span data-ttu-id="6eb51-160">**在交談中使用 giphy** 如果您開啟此選項，使用者可以在與其他人的聊天交談中加入 Giphy。</span><span class="sxs-lookup"><span data-stu-id="6eb51-160">**Use Giphys in conversations**  If you turn this on, users can include Giphys in chat conversations with other people.</span></span> <span data-ttu-id="6eb51-161">Giphy 是線上資料庫和搜尋引擎，可讓使用者搜尋及共用動畫 GIF 檔案。</span><span class="sxs-lookup"><span data-stu-id="6eb51-161">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="6eb51-162">每個 Giphy 都會獲指派內容評級。</span><span class="sxs-lookup"><span data-stu-id="6eb51-162">Each Giphy is assigned a content rating.</span></span>
- <span data-ttu-id="6eb51-163">**Giphy 內容評等**</span><span class="sxs-lookup"><span data-stu-id="6eb51-163">**Giphy content rating**</span></span>
    - <span data-ttu-id="6eb51-164">**無限制**這表示無論內容分級為何，您的使用者都能在聊天中插入任何 Giphy。</span><span class="sxs-lookup"><span data-stu-id="6eb51-164">**No restriction** This means that your users will be able to insert any Giphy in chats regardless of the content rating.</span></span>
    - <span data-ttu-id="6eb51-165">**中等** 這表示您的使用者可以在聊天中插入 Giphy，但會將其從成人內容適度限制。</span><span class="sxs-lookup"><span data-stu-id="6eb51-165">**Moderate**  This means that your users will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
    - <span data-ttu-id="6eb51-166">**嚴格** 這表示您的使用者將能夠在聊天中插入 Giphy，但會嚴格限制成人內容。</span><span class="sxs-lookup"><span data-stu-id="6eb51-166">**Strict**  This means that your users will be able to insert Giphys in chats, but will be strictly restricted from adult content.</span></span>
- <span data-ttu-id="6eb51-167">**在交談中使用 meme**如果您開啟此選項，使用者可以在與其他人的聊天交談中加入 Meme。</span><span class="sxs-lookup"><span data-stu-id="6eb51-167">**Use Memes in conversations** If you turn this on, users can include Memes in chat conversations with other people.</span></span>
- <span data-ttu-id="6eb51-168">**在交談中使用不乾膠標籤**如果您開啟此選項，使用者可以在聊天與其他人交談中加入貼紙。</span><span class="sxs-lookup"><span data-stu-id="6eb51-168">**Use Stickers in conversations** If you turn this on, users can include Stickers in chat conversations with other people.</span></span>
- <span data-ttu-id="6eb51-169">**允許 URL 預覽**使用此設定可開啟或關閉郵件的自動 URL 預覽。</span><span class="sxs-lookup"><span data-stu-id="6eb51-169">**Allow URL previews** Use this setting to turn automatic URL previewing on or off in messages.</span></span>
- <span data-ttu-id="6eb51-170">**允許使用者翻譯郵件**開啟此設定可讓使用者自動將小組郵件翻譯成由 Microsoft 365 或 Office 365 的個人語言設定所指定的語言。</span><span class="sxs-lookup"><span data-stu-id="6eb51-170">**Allow users to translate messages** Turn this setting on to let users automatically translate Teams messages into the language specified by their personal language settings for Microsoft 365 or Office 365.</span></span>
- <span data-ttu-id="6eb51-171">**允許沉浸式閱讀程式查看郵件**開啟此設定可讓使用者在 Microsoft 沉浸式閱讀程式中查看郵件。</span><span class="sxs-lookup"><span data-stu-id="6eb51-171">**Allow immersive reader for viewing messages** Turn this setting on to let users view messages in Microsoft Immersive Reader.</span></span> <span data-ttu-id="6eb51-172">沉浸式閱讀程式是一種學習工具，可提供全螢幕閱讀體驗，以增強文字的可讀性。</span><span class="sxs-lookup"><span data-stu-id="6eb51-172">Immersive Reader is a learning tool that provides a full screen reading experience to increase readability of text.</span></span>
- <span data-ttu-id="6eb51-173">**使用優先順序通知傳送緊急郵件**如果您開啟此選項，使用者可以使用[優先順序通知](https://support.microsoft.com/en-us/office/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462)傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="6eb51-173">**Send urgent messages using priority notifications** If you turn this on, users can send messages using [priority notifications](https://support.microsoft.com/en-us/office/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462).</span></span> <span data-ttu-id="6eb51-174">[優先順序通知] 會每隔兩分鐘通知使用者一段20分鐘，或直到收件者收到標示為*緊急*的郵件，以及時最大限度地處理郵件的可能性。</span><span class="sxs-lookup"><span data-stu-id="6eb51-174">Priority notifications notify users every 2 minutes for a period of 20 minutes or until messages that are marked as *urgent* are picked up and read by the recipient, maximizing the likelihood that the message is acted upon in a timely manner.</span></span>
- <span data-ttu-id="6eb51-175">**建立音訊訊息**</span><span class="sxs-lookup"><span data-stu-id="6eb51-175">**Audio message creation**</span></span> 
  > [!Important]
  > <span data-ttu-id="6eb51-176">不會在 eDiscovery 報表中捕獲音訊訊息。</span><span class="sxs-lookup"><span data-stu-id="6eb51-176">Audio messages are not captured in eDiscovery reporting.</span></span>
    - <span data-ttu-id="6eb51-177">**在聊天和頻道中允許**這表示使用者可以在聊天和頻道中留下音訊訊息。</span><span class="sxs-lookup"><span data-stu-id="6eb51-177">**Allowed in chats and channels** This means that users can leave audio messages in both chats and channels.</span></span>
    - <span data-ttu-id="6eb51-178">**僅允許在聊天中使用**這表示使用者可以將音訊訊息留在聊天中，而不是頻道中。</span><span class="sxs-lookup"><span data-stu-id="6eb51-178">**Allowed in chats only** This means that users can leave audio messages in chats, but not in channels.</span></span>
    - <span data-ttu-id="6eb51-179">**停用**這表示使用者無法在聊天或頻道中建立音訊訊息。</span><span class="sxs-lookup"><span data-stu-id="6eb51-179">**Disabled** This means that users cannot create audio messages in chats or channels.</span></span>  
- <span data-ttu-id="6eb51-180">**在行動裝置上，顯示最近聊天上的最愛頻道**啟用此設定可將最愛的頻道移至行動裝置畫面頂端，這樣使用者就不需要滾動就能找到。</span><span class="sxs-lookup"><span data-stu-id="6eb51-180">**On mobile devices, display favorite channels above recent chats** Enable this setting to move favorite channels to the top of the mobile device screen so that a user doesn't need to scroll to find them.</span></span>
- <span data-ttu-id="6eb51-181">**允許使用者從群組聊天中移除使用者**開啟此設定可讓使用者從群組聊天中移除其他使用者。</span><span class="sxs-lookup"><span data-stu-id="6eb51-181">**Allow a user to remove users from a group chat** Turn this setting on to let a user remove other users from a group chat.</span></span> <span data-ttu-id="6eb51-182">此功能可讓您繼續與較少的人進行交談，而不會遺失聊天歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="6eb51-182">This feature lets you continue a chat with a smaller group of people without losing the chat history.</span></span>
- <span data-ttu-id="6eb51-183">**啟用建議的回復** 開啟此設定以啟用聊天訊息的建議回復。</span><span class="sxs-lookup"><span data-stu-id="6eb51-183">**Enable suggested replies**  Turn this setting on to enable suggested replies for chat messages.</span></span>

> [!NOTE]
> <span data-ttu-id="6eb51-184">某些設定（例如使用 Giphy）也可以由小組擁有者在小組階層和私人通道擁有者設定為私人通道層級。</span><span class="sxs-lookup"><span data-stu-id="6eb51-184">Some of these settings, such using Giphys, can also be configured at the team level by team owners and at the private channel level by private channel owners.</span></span>

### <a name="related-topics"></a><span data-ttu-id="6eb51-185">相關主題</span><span class="sxs-lookup"><span data-stu-id="6eb51-185">Related topics</span></span>

- [<span data-ttu-id="6eb51-186">團隊中的會議原則</span><span class="sxs-lookup"><span data-stu-id="6eb51-186">Meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
