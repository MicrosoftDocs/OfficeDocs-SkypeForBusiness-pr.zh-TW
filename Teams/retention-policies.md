---
title: Microsoft 團隊中的保留原則
author: cabailey
ms.author: cabailey
ms.reviewer: prvijay
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
ms.openlocfilehash: efa11a5ca91be13508ab518ab5be504743825b68
ms.sourcegitcommit: a5276a713697e089d0eb0d80bba83a7af8d48251
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/21/2020
ms.locfileid: "45202950"
---
# <a name="retention-policies-in-microsoft-teams"></a><span data-ttu-id="ccb41-103">Microsoft 團隊中的保留原則</span><span class="sxs-lookup"><span data-stu-id="ccb41-103">Retention policies in Microsoft Teams</span></span>

<span data-ttu-id="ccb41-104">保留原則可協助您更有效率地管理組織中的資訊。</span><span class="sxs-lookup"><span data-stu-id="ccb41-104">Retention policies help you to more effectively manage the information in your organization.</span></span> <span data-ttu-id="ccb41-105">您可以使用保留原則來保留遵守貴組織的內部原則、行業管理法規或法律需求所需的資料，以及刪除被視為債務的資料，或是不需要保留，或是沒有合法或商業價值。</span><span class="sxs-lookup"><span data-stu-id="ccb41-105">Use retention policies to keep data that's needed to comply with your organization's internal policies, industry regulations, or legal needs, and to delete data that's considered a liability, that you're no longer required to keep, or has no legal or business value.</span></span>

<span data-ttu-id="ccb41-106">根據預設，小組聊天、頻道和檔案資料會無限期保留，除非有人嘗試透過保留原則、使用者刪除、管理員刪除等來刪除內容。就像管理員一樣，您可以為聊天和頻道訊息設定小組保留原則，並提前決定是否要保留資料、刪除資料，或將資料保留一段特定的時間，然後將其刪除。</span><span class="sxs-lookup"><span data-stu-id="ccb41-106">By default, Teams chat, channel, and files data are retained indefinitely, unless there is an attempt to delete the content via retention policies, user deletes, admin deletes etc. As an admin, you can set up Teams retention policies for chat and channel messages and decide proactively whether to retain the data, delete it, or retain it for a specific period of time and then delete it.</span></span>

<span data-ttu-id="ccb41-107">您可以在[Microsoft 365 合規性中心](https://protection.office.com/)或使用安全性 & 合規性中心 PowerShell Cmdlet 中，建立及管理小組和其他工作負載的保留原則。</span><span class="sxs-lookup"><span data-stu-id="ccb41-107">You create and manage retention policies for Teams and other workloads in the [Microsoft 365 compliance center](https://protection.office.com/) or by using the Security & Compliance Center PowerShell cmdlets.</span></span> <span data-ttu-id="ccb41-108">您可以將團隊保留原則套用到整個組織或特定的使用者與團隊。</span><span class="sxs-lookup"><span data-stu-id="ccb41-108">You can apply a Teams retention policy to your entire organization or to specific users and teams.</span></span>

> [!NOTE]
> <span data-ttu-id="ccb41-109">我們還不支援保留私人通道訊息的設定。</span><span class="sxs-lookup"><span data-stu-id="ccb41-109">We don't yet support configuration for retention of private channel messages.</span></span> <span data-ttu-id="ccb41-110">支援在私人通道中共用的檔案保留。</span><span class="sxs-lookup"><span data-stu-id="ccb41-110">Retention of files shared in private channels is supported.</span></span>

<span data-ttu-id="ccb41-111">若要深入瞭解 Microsoft 365 或 Office 365 的保留原則，請參閱[保留原則概覽](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)。</span><span class="sxs-lookup"><span data-stu-id="ccb41-111">To learn more about retention policies for Microsoft 365 or Office 365, see [Overview of retention policies](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>

## <a name="what-are-retention-policies-for-teams"></a><span data-ttu-id="ccb41-112">團隊的保留原則</span><span class="sxs-lookup"><span data-stu-id="ccb41-112">What are retention policies for Teams</span></span>

<span data-ttu-id="ccb41-113">當您設定團隊或任何其他工作負荷的保留原則時，您可以將其設定為：</span><span class="sxs-lookup"><span data-stu-id="ccb41-113">When you set up a retention policy for Teams or any other workload, you can set them up to:</span></span>

- <span data-ttu-id="ccb41-114">**保留資料**：使用保留原則，確保您的資料在指定的一段時間內保留，不論使用者應用程式中發生什麼情況。</span><span class="sxs-lookup"><span data-stu-id="ccb41-114">**Retain data**: Use a retention policy to ensure that your data is retained for a specified period of time, regardless of what happens in the user app.</span></span> <span data-ttu-id="ccb41-115">出於合規性原因，仍會保留資料，且可在電子檔探索期間到期前取得資料，在此之後，您的原則會指出是不執行任何動作，或刪除資料。</span><span class="sxs-lookup"><span data-stu-id="ccb41-115">Data is retained for compliance reasons and is available for eDiscovery until the retention period expires, after which your policy indicates whether to do nothing or delete the data.</span></span> <span data-ttu-id="ccb41-116">例如，如果您建立團隊保留原則來保留頻道訊息7年，則郵件會保留7年，即使使用者已在小組中刪除他們的郵件也一樣。</span><span class="sxs-lookup"><span data-stu-id="ccb41-116">For example, if you create a Teams retention policy to retain channel messages for 7 years, the messages are retained for eDiscovery for 7 years, even if users delete their messages in Teams.</span></span>
- <span data-ttu-id="ccb41-117">**刪除資料**：使用保留原則刪除資料，以確保它不是貴組織的責任。</span><span class="sxs-lookup"><span data-stu-id="ccb41-117">**Delete data**: Use a retention policy to delete data to ensure that it's not a liability for your organization.</span></span> <span data-ttu-id="ccb41-118">使用團隊保留原則時，當您刪除資料時，系統會從團隊服務上的所有儲存位置永久刪除該資料。</span><span class="sxs-lookup"><span data-stu-id="ccb41-118">With a Teams retention policy, when you delete data, it's permanently deleted from all storage locations on the Teams service.</span></span>

<span data-ttu-id="ccb41-119">使用小組的保留原則，您可以：</span><span class="sxs-lookup"><span data-stu-id="ccb41-119">With retention policies for Teams, you can:</span></span>

- <span data-ttu-id="ccb41-120">針對指定的持續時間保留團隊聊天和/或頻道訊息，然後不執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="ccb41-120">Retain Teams chats and/or channel messages for a specified duration and then do nothing.</span></span>
- <span data-ttu-id="ccb41-121">針對指定的持續時間保留團隊聊天和/或頻道訊息，然後刪除資料。</span><span class="sxs-lookup"><span data-stu-id="ccb41-121">Retain Teams chats and/or channel messages for a specified duration and then delete the data.</span></span>
- <span data-ttu-id="ccb41-122">在指定的持續時間之後刪除小組聊天和/或頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="ccb41-122">Delete Teams chats and/or channel messages after a specified duration.</span></span>

> [!NOTE]
> <span data-ttu-id="ccb41-123">請記住，在小組中，使用者在私人聊天中共用的檔案，會儲存在共用檔案之使用者的商務用 OneDrive 帳戶中。</span><span class="sxs-lookup"><span data-stu-id="ccb41-123">Remember that in Teams, files that users share in private chats are stored in the OneDrive for Business account of the user who shared the file.</span></span> <span data-ttu-id="ccb41-124">而且，小組成員上傳到頻道交談的檔案會儲存在小組的 SharePoint 網站上。</span><span class="sxs-lookup"><span data-stu-id="ccb41-124">And, files that team members upload to a channel conversation are stored in the team's SharePoint site.</span></span> <span data-ttu-id="ccb41-125">因此，若要保留或刪除小組中的檔案，請建立適用于商務用 OneDrive 和 SharePoint Online 的保留原則。</span><span class="sxs-lookup"><span data-stu-id="ccb41-125">Therefore, to retain or delete files in Teams, create retention policies that apply to OneDrive for Business and SharePoint Online.</span></span>

<span data-ttu-id="ccb41-126">當資料服從保留原則時，使用者可以繼續使用它，因為資料會保留在原來的位置。</span><span class="sxs-lookup"><span data-stu-id="ccb41-126">When data is subject to a retention policy, users can continue to work with it because the data is retained in place, in its original location.</span></span> <span data-ttu-id="ccb41-127">如果使用者編輯或刪除受原則制約的資料，則會將複本儲存到在原則生效時保留的安全位置。</span><span class="sxs-lookup"><span data-stu-id="ccb41-127">If a user edits or deletes data that's subject to the policy, a copy is saved to a secure location where it's retained while the policy is in effect.</span></span>

<span data-ttu-id="ccb41-128">保留原則的最低授權需求是 Office 365 E3。</span><span class="sxs-lookup"><span data-stu-id="ccb41-128">The minimum licensing requirement for retention policies is Office 365 E3.</span></span> <span data-ttu-id="ccb41-129">若要深入瞭解授權，請參閱[Microsoft 團隊服務說明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="ccb41-129">To learn more about licensing, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="how-teams-retention-policies-work"></a><span data-ttu-id="ccb41-130">團隊保留原則的運作方式</span><span class="sxs-lookup"><span data-stu-id="ccb41-130">How Teams retention policies work</span></span>

<span data-ttu-id="ccb41-131">團隊聊天是儲存在聊天中每位使用者信箱的隱藏資料夾（Teamschat）中，而團隊頻道訊息則會儲存在團隊群組信箱中的隱藏資料夾（Teamschat）中。</span><span class="sxs-lookup"><span data-stu-id="ccb41-131">Teams chats are stored in a hidden folder (Teamschat) in the mailbox of each user in the chat, and Teams channel messages are stored in a hidden folder(Teamschat) in the group mailbox for a team.</span></span> <span data-ttu-id="ccb41-132">小組使用一個支援 Azure 的聊天服務來儲存這個資料，而且根據預設，此服務會永久儲存資料。</span><span class="sxs-lookup"><span data-stu-id="ccb41-132">Teams uses an Azure-powered chat service that also stores this data, and by default this service stores the data forever.</span></span> <span data-ttu-id="ccb41-133">使用團隊保留原則時，當您刪除資料時，會從 Exchange 信箱和基礎聊天服務中永久刪除該資料。</span><span class="sxs-lookup"><span data-stu-id="ccb41-133">With a Teams retention policy, when you delete data, the data is permanently deleted from both the Exchange mailboxes and the underlying chat service.</span></span>

<span data-ttu-id="ccb41-134">當您將**保留期間保留**原則套用至小組聊天或頻道訊息時，會發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="ccb41-134">When you apply a **retention-hold** policy to Teams chats or channel messages, here's what happens:</span></span>

- <span data-ttu-id="ccb41-135">如果使用者在保留期間保留期間內編輯或刪除聊天或頻道訊息，則會將郵件複製（如果已編輯）或移動（如果已刪除）至 SubstrateHolds 資料夾，並儲存在保留期間到期的位置。</span><span class="sxs-lookup"><span data-stu-id="ccb41-135">If a chat or channel message is edited or deleted by a user during the retention-hold period, the message is copied (if it was edited) or moved (if it was deleted) to the SubstrateHolds folder and stored there until the retention period expires.</span></span> <span data-ttu-id="ccb41-136">如果原則已設定為在保留期間到期後刪除資料，郵件會在保留期間到期日永久刪除。</span><span class="sxs-lookup"><span data-stu-id="ccb41-136">If the policy is configured to delete data when the retention period expires, messages are permanently deleted on the day the retention period expires.</span></span>
- <span data-ttu-id="ccb41-137">如果使用者不會在**保留**期間內刪除聊天或頻道訊息，郵件會在保留期間到期後的一天內移至 [SubstrateHolds] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="ccb41-137">If a chat or channel message isn't deleted by a user during the **retention-hold** period, the message is moved to the SubstrateHolds folder within one day after the retention period expires.</span></span> <span data-ttu-id="ccb41-138">如果將原則設定為在保留期間到期後刪除資料，郵件移至資料夾後，就會永久刪除一天。</span><span class="sxs-lookup"><span data-stu-id="ccb41-138">If the policy is configured to delete data when the retention period expires, the message is permanently deleted one day after it's moved to the folder.</span></span>

<span data-ttu-id="ccb41-139">當您將**保留刪除**原則套用至團隊聊天和頻道訊息時，會發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="ccb41-139">When you apply a **retention-delete** policy to Teams chats and channel messages, here's what happens:</span></span>

- <span data-ttu-id="ccb41-140">當聊天或頻道訊息到期時，即**保留刪除**原則、後端服務、確認過期的訊息，並開始將它們刪除在後端儲存體（使用者或群組信箱）中。</span><span class="sxs-lookup"><span data-stu-id="ccb41-140">When a chat or channel message expires i.e. age of message is more than allowed by **retention-delete** policy, a back-end service, identifies expired messages and starts deleting them in the backend storage (user or group mailbox).</span></span>
- <span data-ttu-id="ccb41-141">在後端儲存區中刪除郵件之後，就會觸發一個處理常式，以刪除 Azure 已加電的聊天服務與使用者的小組 app 中的相同訊息。</span><span class="sxs-lookup"><span data-stu-id="ccb41-141">Once a message is deleted in back-end storage, a process is triggered to delete the same message in the Azure-powered chat service and user’s Teams app.</span></span> <span data-ttu-id="ccb41-142">若要在 [團隊] app 中刪除的郵件，應用程式必須連線到網際網路並處於空閒狀態（無使用者活動），才能讓刪除程式不會影響使用者的使用體驗。</span><span class="sxs-lookup"><span data-stu-id="ccb41-142">For the messages to be deleted in Teams app, the app needs to be connected to internet and to be in idle state (no user activity), so that the deletion process would not interfere in user experience.</span></span> <span data-ttu-id="ccb41-143">因為使用者可能會有多個裝置，而且可能處於不同的狀態，所以保留刪除不會完全與這些裝置同步處理。</span><span class="sxs-lookup"><span data-stu-id="ccb41-143">Since a user might have multiple devices, which might be in different states, retention deletes would not sync up with those devices at exactly same time.</span></span>
- <span data-ttu-id="ccb41-144">在後端儲存體中刪除郵件之後，這些訊息就會停止顯示在合規性搜尋報告（例如 eDiscovery）中。</span><span class="sxs-lookup"><span data-stu-id="ccb41-144">Once the deletion of messages in backend storage is complete, those messages will stop showing up in compliance search reports such as eDiscovery.</span></span>

> [!NOTE]
> <span data-ttu-id="ccb41-145">在商務用 Skype Online 和小組交互操作聊天中，相同的流程都是可行的。</span><span class="sxs-lookup"><span data-stu-id="ccb41-145">The same flow works for Skype for Business Online and Teams interop chats.</span></span> <span data-ttu-id="ccb41-146">當商務用 Skype Online 聊天加入小組時，會成為小組聊天線索中的訊息，並 ingested 至適當的信箱。</span><span class="sxs-lookup"><span data-stu-id="ccb41-146">When a Skype for Business Online chat comes into Teams, it becomes a message in a Teams chat thread and is ingested into the appropriate mailbox.</span></span> <span data-ttu-id="ccb41-147">團隊保留原則將會從小組執行緒中刪除這些訊息。</span><span class="sxs-lookup"><span data-stu-id="ccb41-147">Teams retention policies will delete these messages from the Teams thread.</span></span> <span data-ttu-id="ccb41-148">不過，如果已開啟商務用 Skype Online 與商務用 Skype Online 用戶端的 [交談記錄]，且這些資訊是儲存在信箱中，則該聊天資料不會由小組保留原則處理。</span><span class="sxs-lookup"><span data-stu-id="ccb41-148">However, if conversation history is turned on for Skype for Business Online and from the Skype for Business Online client side those are being saved into a mailbox, that chat data isn't handled by a Teams retention policy.</span></span>

> [!NOTE]
> <span data-ttu-id="ccb41-149">郵件刪除是永久性且無法復原。</span><span class="sxs-lookup"><span data-stu-id="ccb41-149">The deletion of messages is permanent and irreversible.</span></span>

<span data-ttu-id="ccb41-150">小組中的保留原則是以聊天或頻道訊息的建立日期為基礎，並回溯性。</span><span class="sxs-lookup"><span data-stu-id="ccb41-150">Retention policies in Teams are based on the date the chat or channel messages were created and are retroactive.</span></span> <span data-ttu-id="ccb41-151">換句話說，如果您建立保留原則來刪除超過90天的資料，則會刪除超過90天之前建立的小組資料。</span><span class="sxs-lookup"><span data-stu-id="ccb41-151">In other words, if you create a retention policy to delete data older than 90 days, Teams data created more than 90 days ago is deleted.</span></span>

<span data-ttu-id="ccb41-152">您可以將已套用至 SharePoint Online 或商務用 OneDrive 的保留原則刪除，在刪除前，在小組聊天或頻道訊息中所參照的檔案。</span><span class="sxs-lookup"><span data-stu-id="ccb41-152">It's possible that a retention policy that's applied to SharePoint Online or OneDrive for Business could delete a file that's referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="ccb41-153">在這種情況下，檔案仍會顯示在 [小組] 訊息中，當使用者按一下檔案時，會收到「找不到檔案」錯誤。</span><span class="sxs-lookup"><span data-stu-id="ccb41-153">In this scenario, the file will still show up in the Teams message, but when users click the file, they'll get a "File not found" error.</span></span> <span data-ttu-id="ccb41-154">如果有人手動刪除 SharePoint Online 或商務用 OneDrive 中的檔案，也可能會在沒有原則的情況下發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="ccb41-154">This can also happen in the absence of a policy, if someone manually deletes a file from SharePoint Online or OneDrive for Business.</span></span>

### <a name="considerations-and-limitations"></a><span data-ttu-id="ccb41-155">考慮與限制</span><span class="sxs-lookup"><span data-stu-id="ccb41-155">Considerations and limitations</span></span>

<span data-ttu-id="ccb41-156">以下是使用團隊保留原則時應注意的一些考慮事項與限制：</span><span class="sxs-lookup"><span data-stu-id="ccb41-156">Here's some considerations and limitations to be aware of when working with Teams retention policies:</span></span>

- <span data-ttu-id="ccb41-157">小組需要與其他工作負載分開的保留原則。</span><span class="sxs-lookup"><span data-stu-id="ccb41-157">Teams requires a retention policy that's separate from other workloads.</span></span> <span data-ttu-id="ccb41-158">換句話說，您必須為小組聊天與/或傳送頻道訊息建立特定的保留原則。</span><span class="sxs-lookup"><span data-stu-id="ccb41-158">In other words, you have to create specific retention policies for Teams chats and/or channel messages.</span></span> <span data-ttu-id="ccb41-159">基於這個原因，您無法將團隊納入組織內的保留原則。</span><span class="sxs-lookup"><span data-stu-id="ccb41-159">For this reason, you can't include Teams in org-wide retention policies.</span></span>

- <span data-ttu-id="ccb41-160">不支援私人通道訊息。</span><span class="sxs-lookup"><span data-stu-id="ccb41-160">Private channel messages aren't supported.</span></span> <span data-ttu-id="ccb41-161">目前，小組的保留原則只適用于標準通道訊息。</span><span class="sxs-lookup"><span data-stu-id="ccb41-161">At this time, retention policies for Teams only apply to standard channel messages.</span></span>

- <span data-ttu-id="ccb41-162">小組不支援 [高級保留] 設定，例如，將原則套用至包含關鍵字或機密資訊的內容。</span><span class="sxs-lookup"><span data-stu-id="ccb41-162">Teams doesn't support advanced retention settings, such as the ability to apply a policy to content that contains keywords or sensitive information.</span></span> <span data-ttu-id="ccb41-163">目前，小組中的保留原則會套用至所有聊天和/或通道郵件內容。</span><span class="sxs-lookup"><span data-stu-id="ccb41-163">Currently, retention policies in Teams apply to all chat and/or channel message content.</span></span>

- <span data-ttu-id="ccb41-164">團隊保留原則會觸發刪除聊天和頻道訊息的程式，以便在這些訊息到期時（根據郵件建立日期）。</span><span class="sxs-lookup"><span data-stu-id="ccb41-164">A Teams retention policy will trigger a process to delete chat and channel messages when those messages expire (based on message creation date).</span></span> <span data-ttu-id="ccb41-165">不過，視服務負載而定，可能需要長達7天的時間，才能從後端儲存空間和小組 app 永久刪除這些訊息。</span><span class="sxs-lookup"><span data-stu-id="ccb41-165">However, depending on service load, it may take up-to seven days to permanently delete these messages from backend storage and Teams app.</span></span> <span data-ttu-id="ccb41-166">此外，您也可以使用合規性工具（eDiscovery、結束使用者搜尋）來搜尋這些訊息，直到它們永久地從後端儲存體中刪除為止。</span><span class="sxs-lookup"><span data-stu-id="ccb41-166">Also, these messages will be searchable with compliance tools (eDiscovery, end user search) till they are permanently deleted from backend storage.</span></span>

### <a name="multiple-retention-policies-and-the-principles-of-retention"></a><span data-ttu-id="ccb41-167">多種保留原則和保留原則</span><span class="sxs-lookup"><span data-stu-id="ccb41-167">Multiple retention policies and the principles of retention</span></span>

<span data-ttu-id="ccb41-168">如果您使用不同的期間設定多個小組保留原則，將會套用[保留原則的原則](https://docs.microsoft.com/microsoft-365/compliance/retention-policies#the-principles-of-retention-or-what-takes-precedence)。</span><span class="sxs-lookup"><span data-stu-id="ccb41-168">If you set up multiple Teams retention policies with varying durations, the [principles of retention policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies#the-principles-of-retention-or-what-takes-precedence) apply.</span></span> <span data-ttu-id="ccb41-169">以下是優先考慮的事項：</span><span class="sxs-lookup"><span data-stu-id="ccb41-169">Here's an overview of what takes precedence:</span></span>

- <span data-ttu-id="ccb41-170">保留 [永遠刪除 wins]</span><span class="sxs-lookup"><span data-stu-id="ccb41-170">Preservation always wins over deletion</span></span>
- <span data-ttu-id="ccb41-171">最長保留期間總是獲勝</span><span class="sxs-lookup"><span data-stu-id="ccb41-171">Longest preservation period always wins</span></span>
- <span data-ttu-id="ccb41-172">明確包含在位置的隱式包含 wins</span><span class="sxs-lookup"><span data-stu-id="ccb41-172">Explicit inclusion wins over implicit inclusion in terms of locations</span></span>
- <span data-ttu-id="ccb41-173">最短刪除期間獲勝</span><span class="sxs-lookup"><span data-stu-id="ccb41-173">Shortest deletion period wins</span></span>

## <a name="when-to-use-retention-policies-for-teams"></a><span data-ttu-id="ccb41-174">何時使用小組的保留原則</span><span class="sxs-lookup"><span data-stu-id="ccb41-174">When to use retention policies for Teams</span></span>

<span data-ttu-id="ccb41-175">在許多情況下，組織會考慮使用私人聊天資料，而不是頻道訊息，通常是更多與專案相關的交談。</span><span class="sxs-lookup"><span data-stu-id="ccb41-175">In many cases, organizations consider private chat data as more of a liability than channel messages, which are typically more project-related conversations.</span></span>

<span data-ttu-id="ccb41-176">您可以針對私人聊天設定個別保留原則（1:1 或1：許多聊天）和頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="ccb41-176">You can set up separate retention policies for private chats (1:1 or 1:many chats) and channel messages.</span></span> <span data-ttu-id="ccb41-177">您也可以設定適用于組織中特定使用者或團隊的唯一原則。</span><span class="sxs-lookup"><span data-stu-id="ccb41-177">You can also configure unique policies that apply to specific users or teams in your organization.</span></span> <span data-ttu-id="ccb41-178">針對 [團隊聊天]，您可以選取要套用原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="ccb41-178">For Teams chats, you can select which users the policy applies to.</span></span> <span data-ttu-id="ccb41-179">針對團隊頻道訊息，您可以選取要套用原則的小組。</span><span class="sxs-lookup"><span data-stu-id="ccb41-179">For Teams channel messages, you can select which teams the policy applies to.</span></span>

<span data-ttu-id="ccb41-180">例如，對於頻道訊息，您可以將一年刪除原則套用到貴組織中的特定小組，並將三年的刪除原則套用至所有其他團隊。</span><span class="sxs-lookup"><span data-stu-id="ccb41-180">For example, for channel messages, you can apply a one-year deletion policy to specific teams in your organization and apply a three-year deletion policy to all other teams.</span></span>

## <a name="manage-retention-policies-for-teams"></a><span data-ttu-id="ccb41-181">管理團隊的保留原則</span><span class="sxs-lookup"><span data-stu-id="ccb41-181">Manage retention policies for Teams</span></span>

### <a name="using-the-security--compliance-center"></a><span data-ttu-id="ccb41-182">使用安全性 & 合規性中心</span><span class="sxs-lookup"><span data-stu-id="ccb41-182">Using the Security & Compliance Center</span></span>

#### <a name="create-a-retention-policy"></a><span data-ttu-id="ccb41-183">建立保留原則</span><span class="sxs-lookup"><span data-stu-id="ccb41-183">Create a retention policy</span></span>

<span data-ttu-id="ccb41-184">若要建立小組聊天與頻道訊息的保留原則，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ccb41-184">To create a retention policy for Teams chats and channel messages, do the following:</span></span>

1. <span data-ttu-id="ccb41-185">在安全性 & 合規性中心的左側導覽中，移至 [**資訊管理**  >  **保留**]。</span><span class="sxs-lookup"><span data-stu-id="ccb41-185">In the left navigation of the Security & Compliance Center, go to **Information governance** > **Retention**.</span></span>
2. <span data-ttu-id="ccb41-186">選取 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="ccb41-186">Select **Create**.</span></span>
3. <span data-ttu-id="ccb41-187">在 [**命名您的原則**] 頁面上，輸入原則的名稱和描述，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ccb41-187">On the **Name your policy** page, enter a name and description for your policy, and then click **Next**.</span></span>
4. <span data-ttu-id="ccb41-188">在 [**設定**] 頁面上，指定您是否要保留資料、刪除（或兩者）保留期間，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ccb41-188">On the **Settings** page, specify whether you want to retain data, delete it, or both, the retention period, and then click **Next**.</span></span>
5. <span data-ttu-id="ccb41-189">在 [**選擇位置**] 頁面上，執行下列動作，然後按一下 **[下一步]**：</span><span class="sxs-lookup"><span data-stu-id="ccb41-189">On the **Choose locations** page, do the following, and then click **Next**:</span></span>

    - <span data-ttu-id="ccb41-190">若要將原則套用到頻道訊息，請開啟 [**小組頻道] 訊息**。</span><span class="sxs-lookup"><span data-stu-id="ccb41-190">To apply the policy to channel messages, turn on **Teams channel messages**.</span></span>  <span data-ttu-id="ccb41-191">如果您想要將原則套用到貴組織中的特定小組，請選取 **[選擇團隊**]，然後選取您想要的小組。</span><span class="sxs-lookup"><span data-stu-id="ccb41-191">If you want to apply the policy to specific teams in your organization, select **Choose teams**, and then select the teams that you want.</span></span>
    - <span data-ttu-id="ccb41-192">若要將原則套用至聊天，請開啟 [**小組聊天**]。</span><span class="sxs-lookup"><span data-stu-id="ccb41-192">To apply the policy to chats, turn on **Teams chats**.</span></span> <span data-ttu-id="ccb41-193">如果您想要將原則套用到貴組織中的特定使用者，請選取 **[選擇使用者**]，然後選取您想要的使用者。</span><span class="sxs-lookup"><span data-stu-id="ccb41-193">If you want to apply the policy to specific users in your organization, select **Choose users**, and then select the users that you want.</span></span>
      > [!NOTE]
      > <span data-ttu-id="ccb41-194">當您開啟 [**小組頻道] 訊息**和/或 [**小組聊天**] 時，所有其他位置都會自動關閉。</span><span class="sxs-lookup"><span data-stu-id="ccb41-194">When you turn on **Teams channel messages** and/or **Teams chats**, all other locations are  automatically turned off.</span></span> <span data-ttu-id="ccb41-195">團隊保留原則只能包含團隊位置。</span><span class="sxs-lookup"><span data-stu-id="ccb41-195">A Teams retention policy can only include Teams locations.</span></span>

        ![[選擇位置] 頁面上的 [團隊頻道訊息] 和 [團隊聊天] 選項的螢幕擷取畫面](media/retention-policies-create.png)

      > [!IMPORTANT]
      > <span data-ttu-id="ccb41-197">在**Exchange 電子郵件**或**Microsoft 365 群組**位置中，對於使用者或群組信箱套用的保留原則，不會影響團隊聊天與頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="ccb41-197">Teams chats and channel messages aren't affected by retention policies applied to user or group mailboxes in the **Exchange email** or **Microsoft 365 groups** locations.</span></span> <span data-ttu-id="ccb41-198">雖然團隊聊天和頻道訊息會儲存在 Exchange 中，但它們只能受到團隊位置所套用的保留原則影響。</span><span class="sxs-lookup"><span data-stu-id="ccb41-198">Even though Teams chats and channel messages are stored in Exchange, they're only affected by retention policies applied to the Teams locations.</span></span>

6. <span data-ttu-id="ccb41-199">檢查您的設定，當您準備好時，請選取 [**建立此原則**]。</span><span class="sxs-lookup"><span data-stu-id="ccb41-199">Review your settings, and then when you're ready, select **Create this policy**.</span></span>

#### <a name="edit-a-retention-policy"></a><span data-ttu-id="ccb41-200">編輯保留原則</span><span class="sxs-lookup"><span data-stu-id="ccb41-200">Edit a retention policy</span></span>

<span data-ttu-id="ccb41-201">若要編輯團隊保留原則，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ccb41-201">To edit a Teams retention policy, do the following:</span></span>

1. <span data-ttu-id="ccb41-202">在安全性 & 合規性中心的左側導覽中，移至 [**資訊管理**  >  **保留**]。</span><span class="sxs-lookup"><span data-stu-id="ccb41-202">In the left navigation of the Security & Compliance Center, go to **Information governance** > **Retention**.</span></span>
2. <span data-ttu-id="ccb41-203">在保留原則清單中，選取您要編輯之保留原則旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ccb41-203">In the list of retention policies, select the check box next to the retention policy you want to edit.</span></span>
3. <span data-ttu-id="ccb41-204">選取您要編輯的專案旁的 [**編輯**]，進行變更，按一下 [**儲存**]，然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="ccb41-204">Select **Edit** next to what you want to edit, make your changes, click **Save**, and then click **Close**.</span></span>

    ![[選擇位置] 頁面上的 [團隊頻道訊息] 和 [團隊聊天] 選項的螢幕擷取畫面](media/retention-policies-edit.png)

#### <a name="delete-a-retention-policy"></a><span data-ttu-id="ccb41-206">刪除保留原則</span><span class="sxs-lookup"><span data-stu-id="ccb41-206">Delete a retention policy</span></span>

<span data-ttu-id="ccb41-207">若要刪除團隊保留原則，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ccb41-207">To delete a Teams retention policy, do the following:</span></span>

1. <span data-ttu-id="ccb41-208">在安全性 & 合規性中心的左側導覽中，移至 [**資訊管理**  >  **保留**]。</span><span class="sxs-lookup"><span data-stu-id="ccb41-208">In the left navigation of the Security & Compliance Center, go to **Information governance** > **Retention**.</span></span>
2. <span data-ttu-id="ccb41-209">在保留原則清單中，選取您要刪除之保留原則旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ccb41-209">In the list of retention policies, select the check box next to the retention policy you want to delete.</span></span>
3. <span data-ttu-id="ccb41-210">選取 [**刪除原則**]。</span><span class="sxs-lookup"><span data-stu-id="ccb41-210">Select **Delete policy**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="ccb41-211">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ccb41-211">Using PowerShell</span></span>

<span data-ttu-id="ccb41-212">若要使用[安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)來建立及管理小組保留原則，請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ccb41-212">To create and manage Teams retention policies by using [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell), use the following cmdlets:</span></span>

|<span data-ttu-id="ccb41-213">原則</span><span class="sxs-lookup"><span data-stu-id="ccb41-213">Policy</span></span>|<span data-ttu-id="ccb41-214">基準</span><span class="sxs-lookup"><span data-stu-id="ccb41-214">Rule</span></span>|
|---|---|
|[<span data-ttu-id="ccb41-215">新-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="ccb41-215">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy?view=exchange-ps)| [<span data-ttu-id="ccb41-216">新-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="ccb41-216">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule?view=exchange-ps)|
|[<span data-ttu-id="ccb41-217">RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="ccb41-217">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancepolicy?view=exchange-ps)| [<span data-ttu-id="ccb41-218">RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="ccb41-218">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps)|
|[<span data-ttu-id="ccb41-219">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="ccb41-219">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy?view=exchange-ps)| [<span data-ttu-id="ccb41-220">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="ccb41-220">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancerule?view=exchange-ps)|
|[<span data-ttu-id="ccb41-221">移除-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="ccb41-221">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancepolicy?view=exchange-ps)| [<span data-ttu-id="ccb41-222">移除-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="ccb41-222">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancerule?view=exchange-ps)|

## <a name="known-issues"></a><span data-ttu-id="ccb41-223">已知問題</span><span class="sxs-lookup"><span data-stu-id="ccb41-223">Known issues</span></span>

<span data-ttu-id="ccb41-224">下列是追蹤及調查之小組中保留原則的已知問題。</span><span class="sxs-lookup"><span data-stu-id="ccb41-224">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="ccb41-225">在 [**小組頻道訊息**位置] 列中的 **[選擇團隊**] 底下，您可能會看到不是「團隊」的 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="ccb41-225">Under **Choose teams** in the **Teams channel messages** location row, you may see Microsoft 365 Groups that aren't also Teams.</span></span> <span data-ttu-id="ccb41-226">未來將會解決這個問題。</span><span class="sxs-lookup"><span data-stu-id="ccb41-226">This will be addressed in the future.</span></span>

- <span data-ttu-id="ccb41-227">在 [**小組聊天**位置] 列中的 **[選擇使用者**] 底下，您可能會看到 [來賓] 和 [非信箱] 使用者。</span><span class="sxs-lookup"><span data-stu-id="ccb41-227">Under **Choose users** in the **Teams chats** location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="ccb41-228">保留原則並非要針對來賓進行設定，我們正在努力從清單中移除這些原則。</span><span class="sxs-lookup"><span data-stu-id="ccb41-228">Retention policies aren't meant to be set for guests, and we're working to remove these from the list.</span></span>

- <span data-ttu-id="ccb41-229">Exchange 生命週期助理（ELC）每天都會執行一次，但其 SLA 是7天。</span><span class="sxs-lookup"><span data-stu-id="ccb41-229">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="ccb41-230">因此，如果您有小組保留原則刪除超過60天的專案，這些專案可能會持續到67天。</span><span class="sxs-lookup"><span data-stu-id="ccb41-230">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="ccb41-231">這不是一種新的情況-它是在 Exchange 模型之後。</span><span class="sxs-lookup"><span data-stu-id="ccb41-231">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="ccb41-232">當然，在大多數情況下，不會有延遲。</span><span class="sxs-lookup"><span data-stu-id="ccb41-232">Of course, in most cases, there's no delay.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ccb41-233">相關主題</span><span class="sxs-lookup"><span data-stu-id="ccb41-233">Related topics</span></span>

- [<span data-ttu-id="ccb41-234">保留原則概述</span><span class="sxs-lookup"><span data-stu-id="ccb41-234">Overview of retention policies</span></span>](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)
