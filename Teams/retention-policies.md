---
title: 管理 Microsoft Teams 的保留政策
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 使用 Microsoft Teams 的保留原則，保留符合內部原則、產業法規或法律要求所需的郵件，以及刪除被視為責任或沒有法律商業價值的郵件。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 748106de5ed7e2f0147a182716ca8bce1571b82f
ms.sourcegitcommit: 6505dd1fb891ab27fcc9f36423fda67aae6fcfd7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2021
ms.locfileid: "51418811"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a><span data-ttu-id="71b30-103">管理 Microsoft Teams 的保留政策</span><span class="sxs-lookup"><span data-stu-id="71b30-103">Manage retention policies for Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="71b30-104">如果您在 Teams 中看到一則訊息，指出您的聊天或訊息已由保留原則刪除，請參閱 [Teams 關於保留政策的郵件](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。</span><span class="sxs-lookup"><span data-stu-id="71b30-104">If you are seeing a message in Teams that your chats or messages have been deleted by a retention policy, see [Teams messages about retention policies](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span>
> 
> <span data-ttu-id="71b30-105">此頁面的資訊適用于管理這些保留原則的 IT 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="71b30-105">The information on this page is for IT administrators who manage these retention policies.</span></span>

<span data-ttu-id="71b30-106">Microsoft 365 的保留原則和保留標籤可協助您更有效地管理貴組織的資訊。</span><span class="sxs-lookup"><span data-stu-id="71b30-106">Retention policies and retention labels from Microsoft 365 help you to more effectively manage the information in your organization.</span></span> <span data-ttu-id="71b30-107">您可以設定保留設定，以保留符合貴組織的內部政策、產業法規或法律要求所需的資料。</span><span class="sxs-lookup"><span data-stu-id="71b30-107">You can configure retention settings to keep data that's needed to comply with your organization's internal policies, industry regulations, or legal requirements.</span></span> <span data-ttu-id="71b30-108">您也可以設定保留設定，刪除被視為責任、不再需要保留或沒有法律或商務價值的資料。</span><span class="sxs-lookup"><span data-stu-id="71b30-108">You can also configure retention settings to delete data that's considered a liability, that you're no longer required to keep, or that has no legal or business value.</span></span>

<span data-ttu-id="71b30-109">Teams 支援聊天和頻道訊息的保留政策，這樣您才能主動決定是否要保留、刪除或保留資料一段時間，然後再刪除。</span><span class="sxs-lookup"><span data-stu-id="71b30-109">Teams supports retention policies for chat and channel messages so that as an admin, you can decide proactively whether to retain this data, delete it, or retain it for a specific period of time and then delete it.</span></span> <span data-ttu-id="71b30-110">這些動作的保留期間開始一直取決於郵件的建立時間。</span><span class="sxs-lookup"><span data-stu-id="71b30-110">The start of the retention period for these actions is always based on when a message is created.</span></span> <span data-ttu-id="71b30-111">您可以將 Teams 保留原則適用于整個組織或特定使用者和團隊。</span><span class="sxs-lookup"><span data-stu-id="71b30-111">You can apply a Teams retention policy to your entire organization or to specific users and teams.</span></span> <span data-ttu-id="71b30-112">Teams 不支援保留標籤。</span><span class="sxs-lookup"><span data-stu-id="71b30-112">Retention labels aren't supported for Teams.</span></span>

<span data-ttu-id="71b30-113">若要深入瞭解保留，以及如何針對 Microsoft 365 中其他工作負載使用保留原則或保留標籤來適用保留設定，請參閱瞭解保留原則與保留 [標籤](/microsoft-365/compliance/retention)。</span><span class="sxs-lookup"><span data-stu-id="71b30-113">To learn more about retention, and how you can apply retention settings by using retention policies or retention labels for other workloads in Microsoft 365, see [Learn about retention policies and retention labels](/microsoft-365/compliance/retention).</span></span>

<span data-ttu-id="71b30-114">Teams 保留政策的最低授權需求為 Microsoft 365 E3。</span><span class="sxs-lookup"><span data-stu-id="71b30-114">The minimum licensing requirement for retention policies for Teams is Microsoft 365 E3.</span></span> <span data-ttu-id="71b30-115">若要深入瞭解授權，請參閱 Microsoft [Teams 服務描述](/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="71b30-115">To learn more about licensing, see [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="how-teams-retentiondeletion-policies-work"></a><span data-ttu-id="71b30-116">Teams 保留/刪除政策如何工作</span><span class="sxs-lookup"><span data-stu-id="71b30-116">How Teams retention/deletion policies work</span></span>

<span data-ttu-id="71b30-117">Teams 聊天訊息會儲存在兩個位置。</span><span class="sxs-lookup"><span data-stu-id="71b30-117">Teams chat messages are stored in two locations.</span></span> <span data-ttu-id="71b30-118">主要副本會儲存在 Azure 中，這是用於合規性策略的次要副本，會儲存在聊天中包含的每個使用者的 Exchange Online 信箱中的隱藏資料夾中，而 Teams 頻道訊息則儲存在小組群組信箱中的類似隱藏資料夾中。</span><span class="sxs-lookup"><span data-stu-id="71b30-118">Primary copy is stored in Azure, a secondary copy, that is used for compliance policies, is stored in a hidden folder in the Exchange online mailbox of each user included in the chat, and Teams channel messages are stored in a similar hidden folder in the group mailbox for the team.</span></span> <span data-ttu-id="71b30-119">當聊天訊息刪除原則適用于使用者或小組時，次要副本會先刪除，後面接著主要副本。</span><span class="sxs-lookup"><span data-stu-id="71b30-119">When a chat message deletion policy is applied to a user or Team, secondary copy is deleted first, followed by primary copy.</span></span> <span data-ttu-id="71b30-120">eDiscovery 或 Teams 搜尋是根據儲存在次要副本中的郵件所產生，因此當次要副本刪除時，郵件便無法探索。</span><span class="sxs-lookup"><span data-stu-id="71b30-120">eDiscovery or Teams search is based off of messages stored in secondary copy and hence messages become non-discoverable when secondary copy is deleted.</span></span> 

<span data-ttu-id="71b30-121">當聊天訊息保留原則適用于使用者或小組時，如果郵件因其他刪除原則 (或使用者本身) 而刪除，主複本就會刪除，因此 Teams 用戶端會看到郵件消失，但次要複本會自動移至名為 **Holds** 的隱藏資料夾 ，該資料夾是 Exchange 可復原專案資料夾中的子資料夾。 </span><span class="sxs-lookup"><span data-stu-id="71b30-121">When a chat message retention policy is applied to a user or Team, and if the messages are deleted (either due to another deletion policy or by user themselves), the primary copy is deleted, hence Teams client will see the message disappear, but secondary copy is automatically moved to a hidden folder named **SubstrateHolds** , which is as a subfolder in the Exchange **Recoverable Items** folder.</span></span> <span data-ttu-id="71b30-122">在這些郵件從Holds 資料夾永久刪除之前，這些郵件仍然可于 eDiscovery 工具中搜尋。</span><span class="sxs-lookup"><span data-stu-id="71b30-122">Until these messages are permanently deleted from the SubstrateHolds folder, they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="71b30-123">如需 Teams 保留政策包含和排除哪些內容，以及這些策略如何根據您的策略組組而執行的詳細資訊，請參閱瞭解[Microsoft Teams 的保留。](/microsoft-365/compliance/retention-policies-teams)</span><span class="sxs-lookup"><span data-stu-id="71b30-123">For detailed information about what's included and excluded for Teams retention policies, and how these policies work depending on your policy configuration, see [Learn about retention for Microsoft Teams](/microsoft-365/compliance/retention-policies-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="71b30-124">此頁面說明為什麼保留原則刪除郵件時，有時候可能會看到延遲。</span><span class="sxs-lookup"><span data-stu-id="71b30-124">That page explains why you might sometimes see delays when retention policies delete messages.</span></span> <span data-ttu-id="71b30-125">例如，在您于保留政策中所配置的到期日後，最多 7 天可以看見郵件。</span><span class="sxs-lookup"><span data-stu-id="71b30-125">For example, messages can be visible up to 7 days after the expiration period you've configured in the retention policy.</span></span>

<span data-ttu-id="71b30-126">如果您使用不同的保留設定設定多個 Teams 保留原則，保留原則會解決任何衝突。</span><span class="sxs-lookup"><span data-stu-id="71b30-126">If you set up multiple Teams retention policies with different retention settings, the principles of retention resolve any conflicts.</span></span> <span data-ttu-id="71b30-127">例如：</span><span class="sxs-lookup"><span data-stu-id="71b30-127">For example:</span></span>
- <span data-ttu-id="71b30-128">如果保留或刪除相同內容之間發生衝突，內容會一直保留。</span><span class="sxs-lookup"><span data-stu-id="71b30-128">If there is a conflict between retaining or deleting the same content, the content is always retained.</span></span>
- <span data-ttu-id="71b30-129">如果保留相同內容的時間有衝突，該內容會保留最長保留期間。</span><span class="sxs-lookup"><span data-stu-id="71b30-129">If there is a conflict in how long to retain the same content, it is retained for the longest retention period.</span></span>

<span data-ttu-id="71b30-130">這兩個保留原則可解決當您有多個 Teams 保留原則時，可能會出現的衝突，但如需要詳細資訊，請參閱保留原則，或優先處理 [哪些原則？](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)</span><span class="sxs-lookup"><span data-stu-id="71b30-130">These two principles of retention address most conflicts that might arise when you have multiple retention policies for Teams, but for more information, see [The principles of retention, or what takes precedence?](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)</span></span>

## <a name="when-to-use-retention-policies-for-teams"></a><span data-ttu-id="71b30-131">何時使用 Teams 的保留政策</span><span class="sxs-lookup"><span data-stu-id="71b30-131">When to use retention policies for Teams</span></span>

<span data-ttu-id="71b30-132">在許多情況下，組織將私人聊天資料視為比頻道訊息更相關的責任，而頻道訊息通常更與專案相關的交談。</span><span class="sxs-lookup"><span data-stu-id="71b30-132">In many cases, organizations consider private chat data as more of a liability than channel messages, which are typically more project-related conversations.</span></span>

<span data-ttu-id="71b30-133">您可以針對私人聊天設定個別的保留 (1：1 或 1：) 和頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="71b30-133">You can set up separate retention policies for private chats (1:1 or 1:many chats) and channel messages.</span></span> <span data-ttu-id="71b30-134">您也可以設定適用于貴組織中特定使用者或團隊的唯一原則。</span><span class="sxs-lookup"><span data-stu-id="71b30-134">You can also configure unique policies that apply to specific users or teams in your organization.</span></span> <span data-ttu-id="71b30-135">針對 Teams 聊天，您可以選取原則所適用的使用者。</span><span class="sxs-lookup"><span data-stu-id="71b30-135">For Teams chats, you can select which users the policy applies to.</span></span> <span data-ttu-id="71b30-136">針對 Teams 頻道訊息，您可以選取原則所適用的團隊。</span><span class="sxs-lookup"><span data-stu-id="71b30-136">For Teams channel messages, you can select which teams the policy applies to.</span></span>

<span data-ttu-id="71b30-137">例如，針對頻道訊息，您可以將一年的刪除原則適用于貴組織的特定團隊，並針對所有其他團隊適用三年刪除原則。</span><span class="sxs-lookup"><span data-stu-id="71b30-137">For example, for channel messages, you can apply a one-year deletion policy to specific teams in your organization and apply a three-year deletion policy to all other teams.</span></span>

## <a name="create-and-manage-retention-policies-for-teams"></a><span data-ttu-id="71b30-138">建立及管理 Teams 的保留政策</span><span class="sxs-lookup"><span data-stu-id="71b30-138">Create and manage retention policies for Teams</span></span>

<span data-ttu-id="71b30-139">若要為 Teams 聊天和頻道訊息建立保留原則，請使用 Teams 位置的保留政策 [中的指示](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)。</span><span class="sxs-lookup"><span data-stu-id="71b30-139">To create a retention policy for Teams chats and channel messages, use the instructions from [Retention policy for Teams locations](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations).</span></span>

<span data-ttu-id="71b30-140">此頁面提供有關在 Microsoft 365 中建立及管理其他工作負載保留原則的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="71b30-140">That page has additional information about creating and managing retention policies for other workloads in Microsoft 365.</span></span> <span data-ttu-id="71b30-141">例如，您可能也想要為 Microsoft 365 群組建立保留原則，以保留和刪除 Teams 中存取並儲存在 OneDrive 或 SharePoint 中的檔案。</span><span class="sxs-lookup"><span data-stu-id="71b30-141">For example, you might want to also create a retention policy for Microsoft 365 Groups to retain and delete files that are accessed in Teams and stored in OneDrive or SharePoint.</span></span>  

## <a name="end-user-experience"></a><span data-ttu-id="71b30-142">使用者體驗</span><span class="sxs-lookup"><span data-stu-id="71b30-142">End-user experience</span></span>

<span data-ttu-id="71b30-143">對於私人聊天 (1：1 聊天) 或群組聊天，使用者會看到刪除保留原則組配置的較舊的聊天，而自動產生的訊息會指出「我們已因為貴組織保留政策而刪除較舊的訊息」，顯示在尚未刪除的郵件上方。</span><span class="sxs-lookup"><span data-stu-id="71b30-143">For private chats (1:1 chats) or group chats, users will see that chats older than the retention policy configuration are deleted and an automatically generated message stating "We've deleted older messages due to your org's retention policy" is shown on top of yet undeleted messages.</span></span> <span data-ttu-id="71b30-144">例如：</span><span class="sxs-lookup"><span data-stu-id="71b30-144">For example:</span></span>

:::image type="content" source="media/retention-policies-image1.png" alt-text="在 Teams 中通知使用者聊天訊息會因為 Teams 保留政策而刪除":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Teams 中的使用者說明訊息會因為 Teams 保留政策而刪除":::

<span data-ttu-id="71b30-147">針對頻道訊息， (頻道) 使用者會看到已刪除的郵件在郵件過期後從視圖中消失。</span><span class="sxs-lookup"><span data-stu-id="71b30-147">For Channel messages, users (channel members) will see the deleted messages disappear from view after messages expire.</span></span> <span data-ttu-id="71b30-148">如果刪除的郵件是對話對話的父郵件，則會顯示一則訊息，指出「此郵件已因保留政策而遭到刪除」，以代之父訊息。</span><span class="sxs-lookup"><span data-stu-id="71b30-148">If the deleted message was a parent message of a threaded conversation, then, in place of parent message, a message stating "This message has been deleted because of a Retention Policy" will be displayed.</span></span> <span data-ttu-id="71b30-149">例如：</span><span class="sxs-lookup"><span data-stu-id="71b30-149">For example:</span></span>

:::image type="content" source="media/retention-policies-image3.png" alt-text="保留前頻道的螢幕擷取畫面":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="保留後頻道的螢幕擷取畫面":::

> [!NOTE]
> <span data-ttu-id="71b30-152">使用者目前無法針對已刪除的郵件所看見的顯示訊息進行配置。</span><span class="sxs-lookup"><span data-stu-id="71b30-152">The displayed messages that users see as a result of deleted messages are not configurable at this time.</span></span>

<span data-ttu-id="71b30-153">這些顯示的郵件中的連結會前往 [Teams 關於保留原則的郵件](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。</span><span class="sxs-lookup"><span data-stu-id="71b30-153">The links in these displayed messages go to [Teams messages about retention policies](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span> <span data-ttu-id="71b30-154">此適用于使用者的檔可協助回答有關其郵件為何遭到刪除的基本問題。</span><span class="sxs-lookup"><span data-stu-id="71b30-154">This documentation for end users helps to answer basic questions about why their messages have been deleted.</span></span> <span data-ttu-id="71b30-155">不過，在保留原則部署中，請確定您與使用者和技術支援人員溝通您設定設定的影響。</span><span class="sxs-lookup"><span data-stu-id="71b30-155">However, as part of your retention policy deployment, make sure that you communicate to users and your help desk the impact of your configured settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="71b30-156">相關主題</span><span class="sxs-lookup"><span data-stu-id="71b30-156">Related topics</span></span>

- [<span data-ttu-id="71b30-157">開始使用保留原則和保留標籤</span><span class="sxs-lookup"><span data-stu-id="71b30-157">Get started with retention policies and retention labels</span></span>](/microsoft-365/compliance/get-started-with-retention)
- [<span data-ttu-id="71b30-158">瞭解 Microsoft Teams 的保留</span><span class="sxs-lookup"><span data-stu-id="71b30-158">Learn about retention for Microsoft Teams</span></span>](/microsoft-365/compliance/retention-policies-teams)
- [<span data-ttu-id="71b30-159">建立及設定保留政策</span><span class="sxs-lookup"><span data-stu-id="71b30-159">Create and configure retention policies</span></span>](/microsoft-365/compliance/create-retention-policies)
