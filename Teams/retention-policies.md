---
title: Microsoft 團隊中的保留原則
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 在本文中，您將瞭解保留原則，以及如何在 Microsoft 團隊中建立及管理它們。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4b5ebfc4c626cac14439ef98420e219dd0d93df8
ms.sourcegitcommit: ce2a1239473ca88de799dc548bd7a2a934b3af6a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999257"
---
# <a name="retention-policies-in-microsoft-teams"></a><span data-ttu-id="c1eb5-103">Microsoft 團隊中的保留原則</span><span class="sxs-lookup"><span data-stu-id="c1eb5-103">Retention policies in Microsoft Teams</span></span>

<span data-ttu-id="c1eb5-104">保留原則可協助您更有效率地管理組織中的資訊。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-104">Retention policies help you to more effectively manage the information in your organization.</span></span> <span data-ttu-id="c1eb5-105">您可以使用保留原則來保留遵守貴組織的內部原則、行業管理法規或法律需求所需的資料，以及刪除被視為債務的資料，或是不需要保留，或是沒有合法或商業價值。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-105">Use retention policies to keep data that's needed to comply with your organization's internal policies, industry regulations, or legal needs, and to delete data that's considered a liability, that you're no longer required to keep, or has no legal or business value.</span></span>

<span data-ttu-id="c1eb5-106">根據預設，小組聊天、頻道和檔案資料會無限期保留，除非有人嘗試透過保留原則、使用者刪除、管理員刪除等來刪除內容。就像管理員一樣，您可以為聊天和頻道訊息設定小組保留原則，並提前決定是否要保留資料、刪除資料，或將資料保留一段特定的時間，然後將其刪除。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-106">By default, Teams chat, channel, and files data are retained indefinitely, unless there is an attempt to delete the content via retention policies, user deletes, admin deletes etc. As an admin, you can set up Teams retention policies for chat and channel messages and decide proactively whether to retain the data, delete it, or retain it for a specific period of time and then delete it.</span></span>

<span data-ttu-id="c1eb5-107">您可以在 [Microsoft 365 合規性中心](https://protection.office.com/) 或使用安全性 & 合規性中心 PowerShell Cmdlet 中，建立及管理小組和其他工作負載的保留原則。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-107">You create and manage retention policies for Teams and other workloads in the [Microsoft 365 compliance center](https://protection.office.com/) or by using the Security & Compliance Center PowerShell cmdlets.</span></span> <span data-ttu-id="c1eb5-108">您可以將團隊保留原則套用到整個組織或特定的使用者與團隊。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-108">You can apply a Teams retention policy to your entire organization or to specific users and teams.</span></span>

> [!NOTE]
> <span data-ttu-id="c1eb5-109">我們還不支援保留私人通道訊息的設定。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-109">We don't yet support configuration for retention of private channel messages.</span></span> <span data-ttu-id="c1eb5-110">支援在私人通道中共用的檔案保留。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-110">Retention of files shared in private channels is supported.</span></span>

<span data-ttu-id="c1eb5-111">若要深入瞭解 Microsoft 365 或 Office 365 的保留原則，請參閱 [保留原則概覽](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-111">To learn more about retention policies for Microsoft 365 or Office 365, see [Overview of retention policies](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>

## <a name="what-are-retention-policies-for-teams"></a><span data-ttu-id="c1eb5-112">團隊的保留原則</span><span class="sxs-lookup"><span data-stu-id="c1eb5-112">What are retention policies for Teams</span></span>

<span data-ttu-id="c1eb5-113">當您設定團隊或任何其他工作負荷的保留原則時，您可以將其設定為：</span><span class="sxs-lookup"><span data-stu-id="c1eb5-113">When you set up a retention policy for Teams or any other workload, you can set them up to:</span></span>

- <span data-ttu-id="c1eb5-114">**保留資料** ：使用保留原則，確保您的資料在指定的一段時間內保留，不論使用者應用程式中發生什麼情況。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-114">**Retain data** : Use a retention policy to ensure that your data is retained for a specified period of time, regardless of what happens in the user app.</span></span> <span data-ttu-id="c1eb5-115">出於合規性原因，仍會保留資料，且可在電子檔探索期間到期前取得資料，在此之後，您的原則會指出是不執行任何動作，或刪除資料。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-115">Data is retained for compliance reasons and is available for eDiscovery until the retention period expires, after which your policy indicates whether to do nothing or delete the data.</span></span> <span data-ttu-id="c1eb5-116">例如，如果您建立團隊保留原則來保留頻道訊息7年，則郵件會保留7年，即使使用者已在小組中刪除他們的郵件也一樣。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-116">For example, if you create a Teams retention policy to retain channel messages for 7 years, the messages are retained for eDiscovery for 7 years, even if users delete their messages in Teams.</span></span>
- <span data-ttu-id="c1eb5-117">**刪除資料** ：使用保留原則刪除資料，以確保它不是貴組織的責任。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-117">**Delete data** : Use a retention policy to delete data to ensure that it's not a liability for your organization.</span></span> <span data-ttu-id="c1eb5-118">使用團隊保留原則時，當您刪除資料時，系統會從團隊服務上的所有儲存位置永久刪除該資料。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-118">With a Teams retention policy, when you delete data, it's permanently deleted from all storage locations on the Teams service.</span></span>

<span data-ttu-id="c1eb5-119">使用小組的保留原則，您可以：</span><span class="sxs-lookup"><span data-stu-id="c1eb5-119">With retention policies for Teams, you can:</span></span>

- <span data-ttu-id="c1eb5-120">針對指定的持續時間保留團隊聊天和/或頻道訊息，然後不執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-120">Retain Teams chats and/or channel messages for a specified duration and then do nothing.</span></span>
- <span data-ttu-id="c1eb5-121">針對指定的持續時間保留團隊聊天和/或頻道訊息，然後刪除資料。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-121">Retain Teams chats and/or channel messages for a specified duration and then delete the data.</span></span>
- <span data-ttu-id="c1eb5-122">在指定的持續時間之後刪除小組聊天和/或頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-122">Delete Teams chats and/or channel messages after a specified duration.</span></span>

> [!NOTE]
> <span data-ttu-id="c1eb5-123">請記住，在小組中，使用者在私人聊天中共用的檔案，會儲存在共用檔案之使用者的商務用 OneDrive 帳戶中。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-123">Remember that in Teams, files that users share in private chats are stored in the OneDrive for Business account of the user who shared the file.</span></span> <span data-ttu-id="c1eb5-124">而且，小組成員上傳到頻道交談的檔案會儲存在小組的 SharePoint 網站上。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-124">And, files that team members upload to a channel conversation are stored in the team's SharePoint site.</span></span> <span data-ttu-id="c1eb5-125">因此，若要保留或刪除小組中的檔案，請建立適用于商務用 OneDrive 和 SharePoint Online 的保留原則。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-125">Therefore, to retain or delete files in Teams, create retention policies that apply to OneDrive for Business and SharePoint Online.</span></span>

<span data-ttu-id="c1eb5-126">當資料服從保留原則時，使用者可以繼續使用它，因為資料會保留在原來的位置。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-126">When data is subject to a retention policy, users can continue to work with it because the data is retained in place, in its original location.</span></span> <span data-ttu-id="c1eb5-127">如果使用者編輯或刪除受原則制約的資料，則會將複本儲存到在原則生效時保留的安全位置。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-127">If a user edits or deletes data that's subject to the policy, a copy is saved to a secure location where it's retained while the policy is in effect.</span></span>

<span data-ttu-id="c1eb5-128">保留原則的最低授權需求是 Office 365 E3。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-128">The minimum licensing requirement for retention policies is Office 365 E3.</span></span> <span data-ttu-id="c1eb5-129">若要深入瞭解授權，請參閱 [Microsoft 團隊服務說明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-129">To learn more about licensing, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="how-teams-retention-policies-work"></a><span data-ttu-id="c1eb5-130">團隊保留原則的運作方式</span><span class="sxs-lookup"><span data-stu-id="c1eb5-130">How Teams retention policies work</span></span>

<span data-ttu-id="c1eb5-131">[團隊聊天] 會儲存在) Teamschat 中每位使用者信箱的隱藏 (資料夾中，而 [團隊頻道] 訊息會儲存在小組的群組信箱中的隱藏資料夾中 ([) Teamschat]。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-131">Teams chats are stored in a hidden folder (Teamschat) in the mailbox of each user in the chat, and Teams channel messages are stored in a hidden folder (Teamschat) in the group mailbox for a team.</span></span> <span data-ttu-id="c1eb5-132">小組使用一個支援 Azure 的聊天服務來儲存這個資料，而且根據預設，此服務會永久儲存資料。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-132">Teams uses an Azure-powered chat service that also stores this data, and by default this service stores the data forever.</span></span> <span data-ttu-id="c1eb5-133">使用團隊保留原則時，當您刪除資料時，會從 Exchange 信箱和基礎聊天服務中永久刪除該資料。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-133">With a Teams retention policy, when you delete data, the data is permanently deleted from both the Exchange mailboxes and the underlying chat service.</span></span>

<span data-ttu-id="c1eb5-134">當您將 **保留期間保留** 原則套用至小組聊天或頻道訊息時，會發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="c1eb5-134">When you apply a **retention-hold** policy to Teams chats or channel messages, here's what happens:</span></span>

- <span data-ttu-id="c1eb5-135">如果您在保留期間結束時，由使用者編輯或刪除聊天或頻道訊息，則會將郵件複製 (（如果已) 或移動的話），)  (移至 SubstrateHolds 資料夾並儲存在保留期間為止。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-135">If a chat or channel message is edited or deleted by a user during the retention-hold period, the message is copied (if it was edited) or moved (if it was deleted) to the SubstrateHolds folder and stored there until the retention period expires.</span></span> <span data-ttu-id="c1eb5-136">如果原則已設定為在保留期間到期後刪除資料，郵件會在保留期間到期日永久刪除。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-136">If the policy is configured to delete data when the retention period expires, messages are permanently deleted on the day the retention period expires.</span></span>
- <span data-ttu-id="c1eb5-137">如果使用者不會在 **保留** 期間內刪除聊天或頻道訊息，郵件會在保留期間到期後的一天內移至 [SubstrateHolds] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-137">If a chat or channel message isn't deleted by a user during the **retention-hold** period, the message is moved to the SubstrateHolds folder within one day after the retention period expires.</span></span> <span data-ttu-id="c1eb5-138">如果將原則設定為在保留期間到期後刪除資料，郵件移至資料夾後，就會永久刪除一天。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-138">If the policy is configured to delete data when the retention period expires, the message is permanently deleted one day after it's moved to the folder.</span></span>

<span data-ttu-id="c1eb5-139">當您將 **保留刪除** 原則套用至團隊聊天和頻道訊息時，會發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="c1eb5-139">When you apply a **retention-delete** policy to Teams chats and channel messages, here's what happens:</span></span>

- <span data-ttu-id="c1eb5-140">當聊天或頻道訊息到期時（例如，郵件老化超過 **保留式刪除** 原則、後端服務、識別過期的郵件，並開始在後端儲存 (使用者或群組信箱) 中刪除。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-140">When a chat or channel message expires i.e. age of message is more than allowed by **retention-delete** policy, a back-end service, identifies expired messages and starts deleting them in the backend storage (user or group mailbox).</span></span>
- <span data-ttu-id="c1eb5-141">在後端儲存區中刪除郵件之後，就會觸發一個處理常式，以刪除 Azure 已加電的聊天服務與使用者的小組 app 中的相同訊息。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-141">Once a message is deleted in back-end storage, a process is triggered to delete the same message in the Azure-powered chat service and user’s Teams app.</span></span> <span data-ttu-id="c1eb5-142">若要在 [團隊] app 中刪除的郵件，應用程式必須連線到網際網路，且處於空閒狀態， (沒有使用者活動) ，因此刪除程式不會影響使用者的使用體驗。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-142">For the messages to be deleted in Teams app, the app needs to be connected to internet and to be in idle state (no user activity), so that the deletion process would not interfere in user experience.</span></span> <span data-ttu-id="c1eb5-143">因為使用者可能會有多個裝置，而且可能處於不同的狀態，所以保留刪除不會完全與這些裝置同步處理。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-143">Since a user might have multiple devices, which might be in different states, retention deletes would not sync up with those devices at exactly same time.</span></span>
- <span data-ttu-id="c1eb5-144">在後端儲存體中刪除郵件之後，這些訊息就會停止顯示在合規性搜尋報告（例如 eDiscovery）中。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-144">Once the deletion of messages in backend storage is complete, those messages will stop showing up in compliance search reports such as eDiscovery.</span></span>

> [!NOTE]
> <span data-ttu-id="c1eb5-145">在商務用 Skype Online 和小組交互操作聊天中，相同的流程都是可行的。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-145">The same flow works for Skype for Business Online and Teams interop chats.</span></span> <span data-ttu-id="c1eb5-146">當商務用 Skype Online 聊天加入小組時，會成為小組聊天線索中的訊息，並 ingested 至適當的信箱。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-146">When a Skype for Business Online chat comes into Teams, it becomes a message in a Teams chat thread and is ingested into the appropriate mailbox.</span></span> <span data-ttu-id="c1eb5-147">團隊保留原則將會從小組執行緒中刪除這些訊息。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-147">Teams retention policies will delete these messages from the Teams thread.</span></span> <span data-ttu-id="c1eb5-148">不過，如果已開啟商務用 Skype Online 與商務用 Skype Online 用戶端的 [交談記錄]，且這些資訊是儲存在信箱中，則該聊天資料不會由小組保留原則處理。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-148">However, if conversation history is turned on for Skype for Business Online and from the Skype for Business Online client side those are being saved into a mailbox, that chat data isn't handled by a Teams retention policy.</span></span>

> [!NOTE]
> <span data-ttu-id="c1eb5-149">郵件刪除是永久性且無法復原。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-149">The deletion of messages is permanent and irreversible.</span></span>

<span data-ttu-id="c1eb5-150">小組中的保留原則是以聊天或頻道訊息的建立日期為基礎，並回溯性。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-150">Retention policies in Teams are based on the date the chat or channel messages were created and are retroactive.</span></span> <span data-ttu-id="c1eb5-151">換句話說，如果您建立保留原則來刪除超過90天的資料，則會刪除超過90天之前建立的小組資料。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-151">In other words, if you create a retention policy to delete data older than 90 days, Teams data created more than 90 days ago is deleted.</span></span>

<span data-ttu-id="c1eb5-152">您可以將已套用至 SharePoint Online 或商務用 OneDrive 的保留原則刪除，在刪除前，在小組聊天或頻道訊息中所參照的檔案。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-152">It's possible that a retention policy that's applied to SharePoint Online or OneDrive for Business could delete a file that's referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="c1eb5-153">在這種情況下，檔案仍會顯示在 [小組] 訊息中，當使用者按一下檔案時，會收到「找不到檔案」錯誤。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-153">In this scenario, the file will still show up in the Teams message, but when users click the file, they'll get a "File not found" error.</span></span> <span data-ttu-id="c1eb5-154">如果有人手動刪除 SharePoint Online 或商務用 OneDrive 中的檔案，也可能會在沒有原則的情況下發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-154">This can also happen in the absence of a policy, if someone manually deletes a file from SharePoint Online or OneDrive for Business.</span></span>

### <a name="considerations-and-limitations"></a><span data-ttu-id="c1eb5-155">考慮與限制</span><span class="sxs-lookup"><span data-stu-id="c1eb5-155">Considerations and limitations</span></span>

<span data-ttu-id="c1eb5-156">以下是使用團隊保留原則時應注意的一些考慮事項與限制：</span><span class="sxs-lookup"><span data-stu-id="c1eb5-156">Here's some considerations and limitations to be aware of when working with Teams retention policies:</span></span>

- <span data-ttu-id="c1eb5-157">小組需要與其他工作負載分開的保留原則。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-157">Teams requires a retention policy that's separate from other workloads.</span></span> <span data-ttu-id="c1eb5-158">換句話說，您必須為小組聊天與/或傳送頻道訊息建立特定的保留原則。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-158">In other words, you have to create specific retention policies for Teams chats and/or channel messages.</span></span> <span data-ttu-id="c1eb5-159">基於這個原因，您無法將團隊納入組織內的保留原則。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-159">For this reason, you can't include Teams in org-wide retention policies.</span></span>

- <span data-ttu-id="c1eb5-160">不支援私人通道訊息。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-160">Private channel messages aren't supported.</span></span> <span data-ttu-id="c1eb5-161">目前，小組的保留原則只適用于標準通道訊息。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-161">At this time, retention policies for Teams only apply to standard channel messages.</span></span>

- <span data-ttu-id="c1eb5-162">小組不支援 [高級保留] 設定，例如，將原則套用至包含關鍵字或機密資訊的內容。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-162">Teams doesn't support advanced retention settings, such as the ability to apply a policy to content that contains keywords or sensitive information.</span></span> <span data-ttu-id="c1eb5-163">目前，小組中的保留原則會套用至所有聊天和/或通道郵件內容。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-163">Currently, retention policies in Teams apply to all chat and/or channel message content.</span></span>

- <span data-ttu-id="c1eb5-164">小組保留原則會觸發刪除聊天和頻道訊息的程式，以根據郵件建立日期)  (。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-164">A Teams retention policy will trigger a process to delete chat and channel messages when those messages expire (based on message creation date).</span></span> <span data-ttu-id="c1eb5-165">不過，視服務負載而定，可能需要長達7天的時間，才能從後端儲存空間和小組 app 永久刪除這些訊息。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-165">However, depending on service load, it may take up-to seven days to permanently delete these messages from backend storage and Teams app.</span></span> <span data-ttu-id="c1eb5-166">此外，您也可以使用相容性工具 (eDiscovery、使用者搜尋) ，直到它們永久地從後端儲存體中刪除為止，才能搜尋這些訊息。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-166">Also, these messages will be searchable with compliance tools (eDiscovery, end user search) till they are permanently deleted from backend storage.</span></span>

### <a name="multiple-retention-policies-and-the-principles-of-retention"></a><span data-ttu-id="c1eb5-167">多種保留原則和保留原則</span><span class="sxs-lookup"><span data-stu-id="c1eb5-167">Multiple retention policies and the principles of retention</span></span>

<span data-ttu-id="c1eb5-168">如果您使用不同的期間設定多個小組保留原則，將會套用 [保留原則的原則](https://docs.microsoft.com/microsoft-365/compliance/retention-policies#the-principles-of-retention-or-what-takes-precedence) 。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-168">If you set up multiple Teams retention policies with varying durations, the [principles of retention policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies#the-principles-of-retention-or-what-takes-precedence) apply.</span></span> <span data-ttu-id="c1eb5-169">以下是優先考慮的事項：</span><span class="sxs-lookup"><span data-stu-id="c1eb5-169">Here's an overview of what takes precedence:</span></span>

- <span data-ttu-id="c1eb5-170">保留 [永遠刪除 wins]</span><span class="sxs-lookup"><span data-stu-id="c1eb5-170">Preservation always wins over deletion</span></span>
- <span data-ttu-id="c1eb5-171">最長保留期間總是獲勝</span><span class="sxs-lookup"><span data-stu-id="c1eb5-171">Longest preservation period always wins</span></span>
- <span data-ttu-id="c1eb5-172">明確包含在位置的隱式包含 wins</span><span class="sxs-lookup"><span data-stu-id="c1eb5-172">Explicit inclusion wins over implicit inclusion in terms of locations</span></span>
- <span data-ttu-id="c1eb5-173">最短刪除期間獲勝</span><span class="sxs-lookup"><span data-stu-id="c1eb5-173">Shortest deletion period wins</span></span>

## <a name="when-to-use-retention-policies-for-teams"></a><span data-ttu-id="c1eb5-174">何時使用小組的保留原則</span><span class="sxs-lookup"><span data-stu-id="c1eb5-174">When to use retention policies for Teams</span></span>

<span data-ttu-id="c1eb5-175">在許多情況下，組織會考慮使用私人聊天資料，而不是頻道訊息，通常是更多與專案相關的交談。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-175">In many cases, organizations consider private chat data as more of a liability than channel messages, which are typically more project-related conversations.</span></span>

<span data-ttu-id="c1eb5-176">您可以針對私人聊天 (1:1 或1：設定個別的保留原則，) 與頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-176">You can set up separate retention policies for private chats (1:1 or 1:many chats) and channel messages.</span></span> <span data-ttu-id="c1eb5-177">您也可以設定適用于組織中特定使用者或團隊的唯一原則。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-177">You can also configure unique policies that apply to specific users or teams in your organization.</span></span> <span data-ttu-id="c1eb5-178">針對 [團隊聊天]，您可以選取要套用原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-178">For Teams chats, you can select which users the policy applies to.</span></span> <span data-ttu-id="c1eb5-179">針對團隊頻道訊息，您可以選取要套用原則的小組。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-179">For Teams channel messages, you can select which teams the policy applies to.</span></span>

<span data-ttu-id="c1eb5-180">例如，對於頻道訊息，您可以將一年刪除原則套用到貴組織中的特定小組，並將三年的刪除原則套用至所有其他團隊。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-180">For example, for channel messages, you can apply a one-year deletion policy to specific teams in your organization and apply a three-year deletion policy to all other teams.</span></span>

## <a name="manage-retention-policies-for-teams"></a><span data-ttu-id="c1eb5-181">管理團隊的保留原則</span><span class="sxs-lookup"><span data-stu-id="c1eb5-181">Manage retention policies for Teams</span></span>

### <a name="using-the-security--compliance-center"></a><span data-ttu-id="c1eb5-182">使用安全性 & 合規性中心</span><span class="sxs-lookup"><span data-stu-id="c1eb5-182">Using the Security & Compliance Center</span></span>

#### <a name="create-a-retention-policy"></a><span data-ttu-id="c1eb5-183">建立保留原則</span><span class="sxs-lookup"><span data-stu-id="c1eb5-183">Create a retention policy</span></span>

<span data-ttu-id="c1eb5-184">若要建立小組聊天與頻道訊息的保留原則，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c1eb5-184">To create a retention policy for Teams chats and channel messages, do the following:</span></span>

1. <span data-ttu-id="c1eb5-185">在安全性 & 合規性中心的左側導覽中，移至 [ **資訊管理**  >  **保留** ]。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-185">In the left navigation of the Security & Compliance Center, go to **Information governance** > **Retention**.</span></span>
2. <span data-ttu-id="c1eb5-186">選取 [ **建立** ]。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-186">Select **Create**.</span></span>
3. <span data-ttu-id="c1eb5-187">在 [ **命名您的原則** ] 頁面上，輸入原則的名稱和描述，然後按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-187">On the **Name your policy** page, enter a name and description for your policy, and then click **Next**.</span></span>
4. <span data-ttu-id="c1eb5-188">在 [ **設定** ] 頁面上，指定您是否要保留資料、刪除（或兩者）保留期間，然後按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-188">On the **Settings** page, specify whether you want to retain data, delete it, or both, the retention period, and then click **Next**.</span></span>
5. <span data-ttu-id="c1eb5-189">在 [ **選擇位置** ] 頁面上，執行下列動作，然後按一下 **[下一步]** ：</span><span class="sxs-lookup"><span data-stu-id="c1eb5-189">On the **Choose locations** page, do the following, and then click **Next** :</span></span>

    - <span data-ttu-id="c1eb5-190">若要將原則套用到頻道訊息，請開啟 [ **小組頻道] 訊息** 。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-190">To apply the policy to channel messages, turn on **Teams channel messages**.</span></span>  <span data-ttu-id="c1eb5-191">如果您想要將原則套用到貴組織中的特定小組，請選取 **[選擇團隊** ]，然後選取您想要的小組。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-191">If you want to apply the policy to specific teams in your organization, select **Choose teams** , and then select the teams that you want.</span></span>
    - <span data-ttu-id="c1eb5-192">若要將原則套用至聊天，請開啟 [ **小組聊天** ]。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-192">To apply the policy to chats, turn on **Teams chats**.</span></span> <span data-ttu-id="c1eb5-193">如果您想要將原則套用到貴組織中的特定使用者，請選取 **[選擇使用者** ]，然後選取您想要的使用者。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-193">If you want to apply the policy to specific users in your organization, select **Choose users** , and then select the users that you want.</span></span>
      > [!NOTE]
      > <span data-ttu-id="c1eb5-194">當您開啟 [ **小組頻道] 訊息** 和/或 [ **小組聊天** ] 時，所有其他位置都會自動關閉。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-194">When you turn on **Teams channel messages** and/or **Teams chats** , all other locations are  automatically turned off.</span></span> <span data-ttu-id="c1eb5-195">團隊保留原則只能包含團隊位置。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-195">A Teams retention policy can only include Teams locations.</span></span>

        ![[選擇位置] 頁面上的 [團隊頻道訊息] 和 [團隊聊天] 選項的螢幕擷取畫面](media/retention-policies-create.png)

      > [!IMPORTANT]
      > <span data-ttu-id="c1eb5-197">在 **Exchange 電子郵件** 或 **Microsoft 365 群組** 位置中，對於使用者或群組信箱套用的保留原則，不會影響團隊聊天與頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-197">Teams chats and channel messages aren't affected by retention policies applied to user or group mailboxes in the **Exchange email** or **Microsoft 365 groups** locations.</span></span> <span data-ttu-id="c1eb5-198">雖然團隊聊天和頻道訊息會儲存在 Exchange 中，但它們只能受到團隊位置所套用的保留原則影響。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-198">Even though Teams chats and channel messages are stored in Exchange, they're only affected by retention policies applied to the Teams locations.</span></span>

6. <span data-ttu-id="c1eb5-199">檢查您的設定，當您準備好時，請選取 [ **建立此原則** ]。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-199">Review your settings, and then when you're ready, select **Create this policy**.</span></span>

#### <a name="edit-a-retention-policy"></a><span data-ttu-id="c1eb5-200">編輯保留原則</span><span class="sxs-lookup"><span data-stu-id="c1eb5-200">Edit a retention policy</span></span>

<span data-ttu-id="c1eb5-201">若要編輯團隊保留原則，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c1eb5-201">To edit a Teams retention policy, do the following:</span></span>

1. <span data-ttu-id="c1eb5-202">在安全性 & 合規性中心的左側導覽中，移至 [ **資訊管理**  >  **保留** ]。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-202">In the left navigation of the Security & Compliance Center, go to **Information governance** > **Retention**.</span></span>
2. <span data-ttu-id="c1eb5-203">在保留原則清單中，選取您要編輯之保留原則旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-203">In the list of retention policies, select the check box next to the retention policy you want to edit.</span></span>
3. <span data-ttu-id="c1eb5-204">選取您要編輯的專案旁的 [ **編輯** ]，進行變更，按一下 [ **儲存** ]，然後按一下 [ **關閉** ]。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-204">Select **Edit** next to what you want to edit, make your changes, click **Save** , and then click **Close**.</span></span>

    ![[選擇位置] 頁面上的 [團隊頻道訊息] 和 [團隊聊天] 選項的螢幕擷取畫面](media/retention-policies-edit.png)

> [!WARNING]
> <span data-ttu-id="c1eb5-206">如果您已將特定團隊或特定使用者設定為納入團隊頻道訊息或團隊聊天，然後編輯這些專案來移除該位置的最後一個專案，則該位置的設定就會還原為 [ **全部** ]。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-206">If you have configured specific teams or specific users to include for Teams channel messages or Teams chats, and edit these to remove the last one for the location, the configuration for that location reverts to **All**.</span></span> <span data-ttu-id="c1eb5-207">在儲存原則前，請確定這是您想要的設定。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-207">Make sure this is the configuration that you intend before you save the policy.</span></span>
> 
> <span data-ttu-id="c1eb5-208">例如，如果您指定一個小組聊天使用者，並將它納入已設定為刪除資料的保留原則，然後編輯策略來移除此使用者，預設情況下，所有使用者都會受到永久刪除其小組聊天訊息的保留原則的制約。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-208">For example, if you have specified one Teams chat user to include in your retention policy that's configured to delete data, and then edit the policy to remove this user, by default all users will then be subject to the retention policy that permanently deletes their Teams chat messages.</span></span> <span data-ttu-id="c1eb5-209">對於團隊通道訊息而言，也是如此。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-209">The same applies to includes for Teams channel messages.</span></span>
> 
> <span data-ttu-id="c1eb5-210">在這種情況下，如果您不想讓小組頻道訊息或小組聊天訊息的 **所有** 設定都遵守保留原則，請將位置切換為 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-210">In this scenario, toggle the location off if you don't want the **All** setting for the Teams channel messages or Teams chat messages to be subject to the retention policy.</span></span> <span data-ttu-id="c1eb5-211">或者，請指定 [排除] 以免除原則。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-211">Alternatively, specify excludes to be exempt from the policy.</span></span>


#### <a name="delete-a-retention-policy"></a><span data-ttu-id="c1eb5-212">刪除保留原則</span><span class="sxs-lookup"><span data-stu-id="c1eb5-212">Delete a retention policy</span></span>

<span data-ttu-id="c1eb5-213">若要刪除團隊保留原則，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c1eb5-213">To delete a Teams retention policy, do the following:</span></span>

1. <span data-ttu-id="c1eb5-214">在安全性 & 合規性中心的左側導覽中，移至 [ **資訊管理**  >  **保留** ]。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-214">In the left navigation of the Security & Compliance Center, go to **Information governance** > **Retention**.</span></span>
2. <span data-ttu-id="c1eb5-215">在保留原則清單中，選取您要刪除之保留原則旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-215">In the list of retention policies, select the check box next to the retention policy you want to delete.</span></span>
3. <span data-ttu-id="c1eb5-216">選取 [ **刪除原則** ]。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-216">Select **Delete policy**.</span></span>

### <a name="end-user-experience"></a><span data-ttu-id="c1eb5-217">使用者體驗</span><span class="sxs-lookup"><span data-stu-id="c1eb5-217">End user experience</span></span>

<span data-ttu-id="c1eb5-218">針對私人聊天 (1:1 聊天) 或群組聊天，最終使用者將會看到舊版的聊天與保留原則設定會被刪除，而「我們已刪除較舊的 messaged，因為您組織的保留原則」會顯示在尚未刪除的郵件上方。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-218">For private chats (1:1 chats) or group chats, the end users will see that chats older than the retention policy configuration are deleted and a control message stating" We've deleted older messaged due to your org's retention policy" is shown on top of yet undeleted messages.</span></span>
:::image type="content" source="media/retention-policies-image1.png" alt-text="聊天保留畫面的螢幕擷取畫面":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="群組聊天保留的螢幕擷取畫面":::

<span data-ttu-id="c1eb5-221">對於頻道訊息，) 的使用者 (頻道成員將會看到郵件過期後，已刪除的郵件會從視野中消失。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-221">For Channel messages, the end users (channel members) will see the deleted messages disappear from view after messages expire.</span></span> <span data-ttu-id="c1eb5-222">如果已刪除的郵件是有線程交談的父郵件，則會顯示一則訊息，指出「此郵件已因保留原則而刪除」。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-222">If the deleted message was a parent message of a threaded conversation, then, in place of parent message, a message stating "This message has been deleted because of a Retention Policy" will be displayed.</span></span>

:::image type="content" source="media/retention-policies-image3.png" alt-text="在保留之前先頻道的螢幕擷取畫面":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="保留期間的頻道螢幕擷取畫面":::

> [!NOTE]
> <span data-ttu-id="c1eb5-225">使用者目前不能修改使用者或系統管理員。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-225">End user messaging is not user or admin modifiable at this time.</span></span>


### <a name="using-powershell"></a><span data-ttu-id="c1eb5-226">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1eb5-226">Using PowerShell</span></span>

<span data-ttu-id="c1eb5-227">若要使用 [安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)來建立及管理小組保留原則，請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c1eb5-227">To create and manage Teams retention policies by using [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell), use the following cmdlets:</span></span>

|<span data-ttu-id="c1eb5-228">原則</span><span class="sxs-lookup"><span data-stu-id="c1eb5-228">Policy</span></span>|<span data-ttu-id="c1eb5-229">基準</span><span class="sxs-lookup"><span data-stu-id="c1eb5-229">Rule</span></span>|
|---|---|
|[<span data-ttu-id="c1eb5-230">新-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="c1eb5-230">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy?view=exchange-ps)| [<span data-ttu-id="c1eb5-231">新-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="c1eb5-231">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule?view=exchange-ps)|
|[<span data-ttu-id="c1eb5-232">RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="c1eb5-232">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancepolicy?view=exchange-ps)| [<span data-ttu-id="c1eb5-233">RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="c1eb5-233">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps)|
|[<span data-ttu-id="c1eb5-234">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="c1eb5-234">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy?view=exchange-ps)| [<span data-ttu-id="c1eb5-235">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="c1eb5-235">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancerule?view=exchange-ps)|
|[<span data-ttu-id="c1eb5-236">移除-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="c1eb5-236">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancepolicy?view=exchange-ps)| [<span data-ttu-id="c1eb5-237">移除-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="c1eb5-237">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancerule?view=exchange-ps)|

## <a name="known-issues"></a><span data-ttu-id="c1eb5-238">已知問題</span><span class="sxs-lookup"><span data-stu-id="c1eb5-238">Known issues</span></span>

<span data-ttu-id="c1eb5-239">下列是追蹤及調查之小組中保留原則的已知問題。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-239">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="c1eb5-240">在 [ **小組頻道訊息** 位置] 列中的 **[選擇團隊** ] 底下，您可能會看到不是「團隊」的 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-240">Under **Choose teams** in the **Teams channel messages** location row, you may see Microsoft 365 Groups that aren't also Teams.</span></span> <span data-ttu-id="c1eb5-241">未來將會解決這個問題。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-241">This will be addressed in the future.</span></span>

- <span data-ttu-id="c1eb5-242">在 [ **小組聊天** 位置] 列中的 **[選擇使用者** ] 底下，您可能會看到 [來賓] 和 [非信箱] 使用者。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-242">Under **Choose users** in the **Teams chats** location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="c1eb5-243">保留原則並非要針對來賓進行設定，我們正在努力從清單中移除這些原則。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-243">Retention policies aren't meant to be set for guests, and we're working to remove these from the list.</span></span>

- <span data-ttu-id="c1eb5-244">保留處理作業每天都會執行一次，但在某些情況下，該延遲已被認為已執行最長7天的時間。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-244">Retention processing jobs run daily, but the latency is known to have run upto 7 days, in some cases.</span></span> <span data-ttu-id="c1eb5-245">因此，如果您有小組保留原則刪除超過60天的專案，這些專案可能會持續到67天。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-245">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="c1eb5-246">這不是一種新的情況-它是在 Exchange 模型之後。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-246">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="c1eb5-247">當然，在大多數情況下，不會有延遲。</span><span class="sxs-lookup"><span data-stu-id="c1eb5-247">Of course, in most cases, there's no delay.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c1eb5-248">相關主題</span><span class="sxs-lookup"><span data-stu-id="c1eb5-248">Related topics</span></span>

- [<span data-ttu-id="c1eb5-249">保留原則概述</span><span class="sxs-lookup"><span data-stu-id="c1eb5-249">Overview of retention policies</span></span>](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)
