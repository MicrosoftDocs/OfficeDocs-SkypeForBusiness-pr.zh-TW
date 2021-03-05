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
description: 使用 Microsoft Teams 的保留原則，保留符合內部原則、產業法規或法律需求所需的郵件，並刪除被視為責任或無法律商業價值的郵件。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9422fd2b47ac3d460ee10e8933c45964d78282c1
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460653"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a><span data-ttu-id="11782-103">管理 Microsoft Teams 的保留政策</span><span class="sxs-lookup"><span data-stu-id="11782-103">Manage retention policies for Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="11782-104">如果您在 Teams 中看到一則訊息，指出您的聊天或訊息已由保留政策刪除，請參閱 [Teams 關於保留原則的訊息](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。</span><span class="sxs-lookup"><span data-stu-id="11782-104">If you are seeing a message in Teams that your chats or messages have been deleted by a retention policy, see [Teams messages about retention policies](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span>
> 
> <span data-ttu-id="11782-105">本頁面上的資訊適用于管理這些保留原則的 IT 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="11782-105">The information on this page is for IT administrators who manage these retention policies.</span></span>

<span data-ttu-id="11782-106">Microsoft 365 的保留政策與保留標記可協助您更有效地管理貴組織的資訊。</span><span class="sxs-lookup"><span data-stu-id="11782-106">Retention policies and retention labels from Microsoft 365 help you to more effectively manage the information in your organization.</span></span> <span data-ttu-id="11782-107">您可以設定保留設定，以保留符合貴組織內部政策、產業法規或法律需求所需的資料。</span><span class="sxs-lookup"><span data-stu-id="11782-107">You can configure retention settings to keep data that's needed to comply with your organization's internal policies, industry regulations, or legal needs.</span></span> <span data-ttu-id="11782-108">您也可以設定保留設定，刪除被視為責任、不再需要保留，或沒有任何法律或商務價值的資料。</span><span class="sxs-lookup"><span data-stu-id="11782-108">You can also configure retention settings to delete data that's considered a liability, that you're no longer required to keep, or that has no legal or business value.</span></span>

<span data-ttu-id="11782-109">Teams 支援聊天和頻道訊息的保留政策，因此，您可以主動決定是否要保留、刪除或保留資料一段特定時間，然後再將其刪除。</span><span class="sxs-lookup"><span data-stu-id="11782-109">Teams supports retention policies for chat and channel messages so that as an admin, you can decide proactively whether to retain this data, delete it, or retain it for a specific period of time and then delete it.</span></span> <span data-ttu-id="11782-110">您可以將 Teams 保留原則適用于整個組織或特定的使用者和團隊。</span><span class="sxs-lookup"><span data-stu-id="11782-110">You can apply a Teams retention policy to your entire organization or to specific users and teams.</span></span> <span data-ttu-id="11782-111">Teams 不支援保留標記。</span><span class="sxs-lookup"><span data-stu-id="11782-111">Retention labels aren't supported for Teams.</span></span>

<span data-ttu-id="11782-112">若要深入瞭解保留，以及如何在 Microsoft 365 中為其他工作負載使用保留原則或保留標籤來申請保留設定，請參閱瞭解保留原則 [與保留標籤](https://docs.microsoft.com/microsoft-365/compliance/retention)。</span><span class="sxs-lookup"><span data-stu-id="11782-112">To learn more about retention, and how you can apply retention settings by using retention policies or retention labels for other workloads in Microsoft 365, see [Learn about retention policies and retention labels](https://docs.microsoft.com/microsoft-365/compliance/retention).</span></span>

<span data-ttu-id="11782-113">Teams 保留原則的最低授權需求為 Microsoft 365 E3。</span><span class="sxs-lookup"><span data-stu-id="11782-113">The minimum licensing requirement for retention policies for Teams is Microsoft 365 E3.</span></span> <span data-ttu-id="11782-114">若要深入瞭解授權，請參閱 Microsoft [Teams 服務描述](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="11782-114">To learn more about licensing, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="how-teams-retentiondeletion-policies-work"></a><span data-ttu-id="11782-115">Teams 保留/刪除政策如何執行</span><span class="sxs-lookup"><span data-stu-id="11782-115">How Teams retention/deletion policies work</span></span>

<span data-ttu-id="11782-116">Teams 聊天訊息會儲存在兩個位置。</span><span class="sxs-lookup"><span data-stu-id="11782-116">Teams chat messages are stored in two locations.</span></span> <span data-ttu-id="11782-117">主要副本會儲存在 Azure 中，這是用於編譯策略的次要副本，會儲存在聊天中包含的每個使用者 Exchange 線上信箱的隱藏資料夾中，而 Teams 頻道訊息則儲存在小組群組信箱中的類似隱藏資料夾中。</span><span class="sxs-lookup"><span data-stu-id="11782-117">Primary copy is stored in Azure, a secondary copy, that is used for compilance policies, is stored in a hidden folder in the Exchange online mailbox of each user included in the chat, and Teams channel messages are stored in a similar hidden folder in the group mailbox for the team.</span></span> <span data-ttu-id="11782-118">當聊天訊息刪除原則已適用于使用者或小組時，次要副本會先刪除，再刪除主要副本。</span><span class="sxs-lookup"><span data-stu-id="11782-118">When a chat message deletion policy is applied to a user or Team, secondary copy is deleted first, followed by primary copy.</span></span> <span data-ttu-id="11782-119">eDiscovery 或 Teams 搜尋是根據儲存在次要副本中的郵件所產生，因此當次要副本刪除時，郵件便無法搜尋。</span><span class="sxs-lookup"><span data-stu-id="11782-119">eDiscovery or Teams search is based off of messages stored in secondary copy and hence messages become non discoverable when secondary copy is deleted.</span></span> 

<span data-ttu-id="11782-120">當聊天訊息保留問題已應用至使用者或小組，且郵件因其他刪除原則或使用者本身 (而刪除時) ，主要複本就會刪除，因此 Teams 用戶端會看到訊息消失，但次要複本會自動移至名為 **Holds** 的隱藏資料夾，此資料夾是 **Exchange** 可復原的專案資料夾中的子資料夾。</span><span class="sxs-lookup"><span data-stu-id="11782-120">When a chat message retention poilcy is applied to a user or Team, and if the messages are deleted (either due to another deletion policy or by user themselves), the primary copy is deleted, hence Teams client will see the message disappear, but secondary copy is automatically moved to a hidden folder named **SubstrateHolds** , which is as a subfolder in the Exchange **Recoverable Items** folder.</span></span> <span data-ttu-id="11782-121">在這些郵件從Holds 資料夾永久刪除之前，eDiscovery 工具仍然可以搜尋這些郵件。</span><span class="sxs-lookup"><span data-stu-id="11782-121">Until these messages are permanently deleted from the SubstrateHolds folder, they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="11782-122">如需 Teams 保留政策包含與排除之內容的詳細資訊，以及這些策略如何根據您的策略組組而執行，請參閱深入瞭解 Microsoft Teams 的[保留。](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)</span><span class="sxs-lookup"><span data-stu-id="11782-122">For detailed information about what's included and excluded for Teams retention policies, and how these policies work depending on your policy configuration, see [Learn about retention for Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="11782-123">此頁面會說明為什麼保留原則刪除郵件時，有時可能會看到延遲。</span><span class="sxs-lookup"><span data-stu-id="11782-123">That page explains why you might sometimes see delays when retention policies delete messages.</span></span> <span data-ttu-id="11782-124">例如，在您于保留政策中所配置的到期日後，最多 7 天可以看到郵件。</span><span class="sxs-lookup"><span data-stu-id="11782-124">For example, messages can be visible up to 7 days after the expiration period you've configured in the retention policy.</span></span>

<span data-ttu-id="11782-125">如果您使用不同的保留設定設定多個 Teams 保留原則，保留原則會解決任何衝突。</span><span class="sxs-lookup"><span data-stu-id="11782-125">If you set up multiple Teams retention policies with different retention settings, the principles of retention resolve any conflicts.</span></span> <span data-ttu-id="11782-126">例如：</span><span class="sxs-lookup"><span data-stu-id="11782-126">For example:</span></span>
- <span data-ttu-id="11782-127">如果保留或刪除相同內容之間發生衝突，則一直保留內容。</span><span class="sxs-lookup"><span data-stu-id="11782-127">If there is a conflict between retaining or deleting the same content, the content is always retained.</span></span>
- <span data-ttu-id="11782-128">如果保留相同內容的時間有衝突，會保留最長保留期間。</span><span class="sxs-lookup"><span data-stu-id="11782-128">If there is a conflict in how long to retain the same content, it is retained for the longest retention period.</span></span>

<span data-ttu-id="11782-129">這兩個保留原則可解決當您有多個 Teams 保留原則時所可能產生的衝突，但如需要詳細資訊，請參閱保留原則，或 [優先處理哪些專案？](https://docs.microsoft.com/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)</span><span class="sxs-lookup"><span data-stu-id="11782-129">These two principles of retention address most conflicts that might arise when you have multiple retention policies for Teams, but for more information, see [The principles of retention, or what takes precedence?](https://docs.microsoft.com/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)</span></span>

## <a name="when-to-use-retention-policies-for-teams"></a><span data-ttu-id="11782-130">何時使用 Teams 的保留政策</span><span class="sxs-lookup"><span data-stu-id="11782-130">When to use retention policies for Teams</span></span>

<span data-ttu-id="11782-131">在許多情況下，組織將私人聊天資料視為比頻道訊息更多的責任，頻道訊息通常更與專案相關的交談。</span><span class="sxs-lookup"><span data-stu-id="11782-131">In many cases, organizations consider private chat data as more of a liability than channel messages, which are typically more project-related conversations.</span></span>

<span data-ttu-id="11782-132">您可以針對私人聊天設定個別的保留 (1：1 或 1：) 和頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="11782-132">You can set up separate retention policies for private chats (1:1 or 1:many chats) and channel messages.</span></span> <span data-ttu-id="11782-133">您也可以設定適用于貴組織中特定使用者或團隊的唯一原則。</span><span class="sxs-lookup"><span data-stu-id="11782-133">You can also configure unique policies that apply to specific users or teams in your organization.</span></span> <span data-ttu-id="11782-134">對於 Teams 聊天，您可以選取原則所適用的使用者。</span><span class="sxs-lookup"><span data-stu-id="11782-134">For Teams chats, you can select which users the policy applies to.</span></span> <span data-ttu-id="11782-135">對於 Teams 頻道訊息，您可以選取原則所適用的團隊。</span><span class="sxs-lookup"><span data-stu-id="11782-135">For Teams channel messages, you can select which teams the policy applies to.</span></span>

<span data-ttu-id="11782-136">例如，針對頻道訊息，您可以將一年刪除原則適用于貴組織的特定團隊，並針對所有其他團隊使用三年刪除原則。</span><span class="sxs-lookup"><span data-stu-id="11782-136">For example, for channel messages, you can apply a one-year deletion policy to specific teams in your organization and apply a three-year deletion policy to all other teams.</span></span>

## <a name="create-and-manage-retention-policies-for-teams"></a><span data-ttu-id="11782-137">建立及管理 Teams 的保留政策</span><span class="sxs-lookup"><span data-stu-id="11782-137">Create and manage retention policies for Teams</span></span>

<span data-ttu-id="11782-138">若要建立 Teams 聊天和頻道訊息的保留政策，請使用 Teams 位置的保留政策 [指示](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)。</span><span class="sxs-lookup"><span data-stu-id="11782-138">To create a retention policy for Teams chats and channel messages, use the instructions from [Retention policy for Teams locations](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations).</span></span>

<span data-ttu-id="11782-139">該頁面包含有關在 Microsoft 365 中建立和管理其他工作負載保留原則的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="11782-139">That page has additional information about creating and managing retention policies for other workloads in Microsoft 365.</span></span> <span data-ttu-id="11782-140">例如，您可能也想要建立 Microsoft 365 群組的保留原則，以保留和刪除在 Teams 中存取並儲存在 OneDrive 或 SharePoint 中的檔案。</span><span class="sxs-lookup"><span data-stu-id="11782-140">For example, you might want to also create a retention policy for Microsoft 365 Groups to retain and delete files that are accessed in Teams and stored in OneDrive or SharePoint.</span></span>  

## <a name="end-user-experience"></a><span data-ttu-id="11782-141">使用者經驗</span><span class="sxs-lookup"><span data-stu-id="11782-141">End user experience</span></span>

<span data-ttu-id="11782-142">對於私人聊天 (1 對 1 聊天) 或群組聊天，使用者會看到比保留政策組組更舊的聊天被刪除，且會在尚未刪除的郵件上方顯示「我們已因為貴組織保留政策而刪除較舊的訊息」的自動產生訊息。</span><span class="sxs-lookup"><span data-stu-id="11782-142">For private chats (1:1 chats) or group chats, users will see that chats older than the retention policy configuration are deleted and an automatically generated message stating "We've deleted older messages due to your org's retention policy" is shown on top of yet undeleted messages.</span></span> <span data-ttu-id="11782-143">例如：</span><span class="sxs-lookup"><span data-stu-id="11782-143">For example:</span></span>

:::image type="content" source="media/retention-policies-image1.png" alt-text="在 Teams 中通知使用者，由於 Teams 保留政策而刪除聊天訊息":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Teams 中的使用者說明訊息會因為 Teams 保留政策而被刪除":::

<span data-ttu-id="11782-146">針對頻道訊息， (頻道成員) 會在郵件到期後看到已刪除的郵件從視野消失。</span><span class="sxs-lookup"><span data-stu-id="11782-146">For Channel messages, users (channel members) will see the deleted messages disappear from view after messages expire.</span></span> <span data-ttu-id="11782-147">如果刪除的郵件是對話對話的父郵件，則會顯示一則訊息，指出「此郵件已因保留政策而遭到刪除」，以做為父訊息。</span><span class="sxs-lookup"><span data-stu-id="11782-147">If the deleted message was a parent message of a threaded conversation, then, in place of parent message, a message stating "This message has been deleted because of a Retention Policy" will be displayed.</span></span> <span data-ttu-id="11782-148">例如：</span><span class="sxs-lookup"><span data-stu-id="11782-148">For example:</span></span>

:::image type="content" source="media/retention-policies-image3.png" alt-text="保留前頻道的螢幕擷取畫面":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="保留後頻道的螢幕擷取畫面":::

> [!NOTE]
> <span data-ttu-id="11782-151">使用者因刪除的郵件而看到的顯示訊息目前無法進行設置。</span><span class="sxs-lookup"><span data-stu-id="11782-151">The displayed messages that users see as a result of deleted messages are not configurable at this time.</span></span>

<span data-ttu-id="11782-152">這些顯示的郵件中的連結會前往 [Teams 關於保留政策的郵件](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。</span><span class="sxs-lookup"><span data-stu-id="11782-152">The links in these displayed messages go to [Teams messages about retention policies](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span> <span data-ttu-id="11782-153">本文適用于使用者，可協助回答使用者訊息為何遭到刪除的基本問題。</span><span class="sxs-lookup"><span data-stu-id="11782-153">This documentation for end users helps to answer basic questions about why their messages have been deleted.</span></span> <span data-ttu-id="11782-154">不過，在保留原則部署中，請務必與使用者及技術支援人員溝通您設定設定的影響。</span><span class="sxs-lookup"><span data-stu-id="11782-154">However, as part of your retention policy deployment, make sure that you communicate to users and your help desk the impact of your configured settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="11782-155">相關主題</span><span class="sxs-lookup"><span data-stu-id="11782-155">Related topics</span></span>

- [<span data-ttu-id="11782-156">開始使用保留原則和保留標記</span><span class="sxs-lookup"><span data-stu-id="11782-156">Get started with retention policies and retention labels</span></span>](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-retention)
- [<span data-ttu-id="11782-157">瞭解 Microsoft Teams 的保留</span><span class="sxs-lookup"><span data-stu-id="11782-157">Learn about retention for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)
- [<span data-ttu-id="11782-158">建立及設定保留原則</span><span class="sxs-lookup"><span data-stu-id="11782-158">Create and configure retention policies</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies)
