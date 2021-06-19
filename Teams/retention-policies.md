---
title: 管理 Microsoft Teams 的保留原則
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 使用 Microsoft Teams 保留原則，以保留有關貴組織需要遵守的內部原則、產業法規或法律要求的訊息，並刪除視為有責任或沒有法律商業價值的郵件。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ec6b257f91c7e5003a4a69079e37b20b5f338528
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/07/2021
ms.locfileid: "51617755"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a><span data-ttu-id="795d9-103">管理 Microsoft Teams 的保留原則</span><span class="sxs-lookup"><span data-stu-id="795d9-103">Manage retention policies for Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="795d9-104">如果您在 Teams 訊息中得知保留原則已刪除聊天或訊息，請參閱 [關於保留原則的 Teams 訊息](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。</span><span class="sxs-lookup"><span data-stu-id="795d9-104">If you are seeing a message in Teams that your chats or messages have been deleted by a retention policy, see [Teams messages about retention policies](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span>
> 
> <span data-ttu-id="795d9-105">本頁面上的資訊適用於管理這些保留原則的 IT 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="795d9-105">The information on this page is for IT administrators who manage these retention policies.</span></span>

<span data-ttu-id="795d9-106">Microsoft 365 的保留原則和保留標籤可協助您更有效地管理組織中的資訊。</span><span class="sxs-lookup"><span data-stu-id="795d9-106">Retention policies and retention labels from Microsoft 365 help you to more effectively manage the information in your organization.</span></span> <span data-ttu-id="795d9-107">您可以設定保留原則，以保留符合貴組織的內部原則、產業法規或法律要求所需的資料。</span><span class="sxs-lookup"><span data-stu-id="795d9-107">You can configure retention settings to keep data that's needed to comply with your organization's internal policies, industry regulations, or legal requirements.</span></span> <span data-ttu-id="795d9-108">您也可以設定保留設定以刪除被視為負債的資料、不再需要保留的資料，或沒有法律或商業價值的資料。</span><span class="sxs-lookup"><span data-stu-id="795d9-108">You can also configure retention settings to delete data that's considered a liability, that you're no longer required to keep, or that has no legal or business value.</span></span>

<span data-ttu-id="795d9-109">Microsoft Teams 支援適用於聊天和頻道訊息的保留原則，所以身為系統管理員，您可以主動決定是否要保留資料、刪除資料，或保留特定的一段時間然後刪除。</span><span class="sxs-lookup"><span data-stu-id="795d9-109">Teams supports retention policies for chat and channel messages so that as an admin, you can decide proactively whether to retain this data, delete it, or retain it for a specific period of time and then delete it.</span></span> <span data-ttu-id="795d9-110">這些動作的保留期間啟動一律取決於訊息建立的時間。</span><span class="sxs-lookup"><span data-stu-id="795d9-110">The start of the retention period for these actions is always based on when a message is created.</span></span> <span data-ttu-id="795d9-111">您可以將 Teams 保留原則套用到整個組織或特定的使用者和小組。</span><span class="sxs-lookup"><span data-stu-id="795d9-111">You can apply a Teams retention policy to your entire organization or to specific users and teams.</span></span> <span data-ttu-id="795d9-112">Microsoft Teams 不支援保留標籤。</span><span class="sxs-lookup"><span data-stu-id="795d9-112">Retention labels aren't supported for Teams.</span></span>

<span data-ttu-id="795d9-113">若要深入了解 Microsoft 365 中的保留解決方案，請參閱 [瞭解保留原則和保留標籤](/microsoft-365/compliance/retention)。</span><span class="sxs-lookup"><span data-stu-id="795d9-113">To learn more about retention solutions in Microsoft 365, see [Learn about retention policies and retention labels](/microsoft-365/compliance/retention).</span></span>

<span data-ttu-id="795d9-114">受 Microsoft Teams 保留原則限制的使用者必須擁有適當的授權，例如 Office 365 E3 或 Office 365 A3。</span><span class="sxs-lookup"><span data-stu-id="795d9-114">Users who are subject to a retention policy for Teams must have an appropriate license, such as Office 365 E3 or Office 365 A3.</span></span> <span data-ttu-id="795d9-115">有關這些保留原則的其他授權選項，請參閱 [Microsoft 365 安全性與合規性的授權指引](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) 中的 [資訊控管](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) 章節。</span><span class="sxs-lookup"><span data-stu-id="795d9-115">For other licensing options for these retention policies, see the [Information Governance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) section from [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance).</span></span> <span data-ttu-id="795d9-116">若要深入瞭解 Microsoft Teams 授權，請參閱 [Microsoft Teams 服務描述](/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="795d9-116">To learn more about licensing for Teams, see [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="how-teams-retention-policies-support-retain-and-delete-actions"></a><span data-ttu-id="795d9-117">Microsoft Teams 保留原則支援保留和刪除動作的方式</span><span class="sxs-lookup"><span data-stu-id="795d9-117">How Teams retention policies support retain and delete actions</span></span>

<span data-ttu-id="795d9-118">如果您將 Teams 保留原則設定為保留聊天或頻道訊息，使用者仍然可以在 Microsoft Teams 應用程式中編輯和刪除其訊息。</span><span class="sxs-lookup"><span data-stu-id="795d9-118">If you configure a Teams retention policy to retain chats or channel messages, users can still edit and delete their messages in their Teams app.</span></span> <span data-ttu-id="795d9-119">雖然使用者不會再看到他們在 Teams 中預先編輯或刪除的訊息，但來自這些訊息的資料會儲存在安全的位置，該位置是專為合規性系統管理員的電子文件探索搜尋所設計。</span><span class="sxs-lookup"><span data-stu-id="795d9-119">Although users no longer see their pre-edited or deleted messages in Teams, data from these messages is stored in a secured location that's designed for eDiscovery searches by compliance administrators.</span></span> <span data-ttu-id="795d9-120">此資料不會遭到永久刪除直到已設定的保留期間結束，或如果已設定其他保留原則保留此資料，或受到 [eDiscovery 保留](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds)。</span><span class="sxs-lookup"><span data-stu-id="795d9-120">Permanent deletion of this data doesn't happen before the end of the configured retention period, or if another retention policy is configured to retain this data, or it is subject to an [eDiscovery hold](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds).</span></span>

<span data-ttu-id="795d9-121">當保留原則已設定為刪除聊天和頻道訊息時，這些訊息就符合自動刪除的資格。</span><span class="sxs-lookup"><span data-stu-id="795d9-121">When a retention policy is configured to delete chats and channel messages, these messages become eligible for automatic deletion.</span></span> <span data-ttu-id="795d9-122">如果訊息仍在 Teams 應用程式中顯示，這些訊息都將在此處消失，且 [使用者會收到通知表示保留原則已刪除這些訊息](#end-user-experience)。</span><span class="sxs-lookup"><span data-stu-id="795d9-122">If the messages are still displayed in the Teams app, they will disappear from there and [users are informed that a retention policy has deleted these messages](#end-user-experience).</span></span> <span data-ttu-id="795d9-123">如果訊息先前受到保留動作的限制，且已由使用者進行編輯或刪除，這些訊息將會在安全的位置遭到刪除，且不會再於電子文件探索搜尋中傳回。</span><span class="sxs-lookup"><span data-stu-id="795d9-123">If the messages were previously subject to a retain action and have been edited or deleted by users, these messages will now be deleted from the secured location and no longer returned in eDiscovery searches.</span></span>

<span data-ttu-id="795d9-124">如需根據原則設定和使用者動作的原則運作方式，以及 Teams 保留原則包含和排除哪些訊息資料的詳細資訊，請參閱 [瞭解 Microsoft Teams 的保留](/microsoft-365/compliance/retention-policies-teams)。</span><span class="sxs-lookup"><span data-stu-id="795d9-124">For detailed information about how these policies work depending on your policy configuration and user actions, and what message data is included and excluded for Teams retention policies, see [Learn about retention for Microsoft Teams](/microsoft-365/compliance/retention-policies-teams).</span></span> <span data-ttu-id="795d9-125">該頁面也會說明為什麼當保留原則刪除郵件時，您有時可能會遇到延遲的原因。</span><span class="sxs-lookup"><span data-stu-id="795d9-125">That page also explains why you might sometimes experience delays when retention policies delete messages.</span></span> <span data-ttu-id="795d9-126">例如，在保留原則中，在到期期間後的 7 天內，Teams 應用程式中的使用者可以看到訊息。</span><span class="sxs-lookup"><span data-stu-id="795d9-126">For example, messages can be visible to users in the Teams app up to 7 days after the expiration period you've configured in the retention policy.</span></span>

<span data-ttu-id="795d9-127">如果您使用不同的保留設定設定多個 Teams 保留原則，保留的原則會解決任何衝突。</span><span class="sxs-lookup"><span data-stu-id="795d9-127">If you set up multiple Teams retention policies with different retention settings, the principles of retention resolve any conflicts.</span></span> <span data-ttu-id="795d9-128">例如：</span><span class="sxs-lookup"><span data-stu-id="795d9-128">For example:</span></span>

- <span data-ttu-id="795d9-129">如果保留或刪除相同內容之間發生衝突，內容會一律保留在安全的位置，以便維持其可搜尋性使合規性系統管理員使用 eDiscovery 進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="795d9-129">If there is a conflict between retaining or deleting the same content, the content is always retained in the secured location so that it remains searchable with eDiscovery for compliance administrators.</span></span>
    
    <span data-ttu-id="795d9-130">此原則也會套用至因法律或調查理由而受到電子文件探索保留的訊息。</span><span class="sxs-lookup"><span data-stu-id="795d9-130">This principle also applies to messages that are under eDiscovery holds for legal or investigative reasons.</span></span>

- <span data-ttu-id="795d9-131">如果保留相同內容的時間長短出現衝突，系統會將此內容以最長的保留期間保留在安全的位置中。</span><span class="sxs-lookup"><span data-stu-id="795d9-131">If there is a conflict in how long to retain the same content, it is retained in the secured location for the longest retention period.</span></span>

<span data-ttu-id="795d9-132">當您擁有多個 Teams 保留原則時，這兩個保留原則可以解決大多數可能發生的衝突，但如需詳細資訊，請參閱 [原則保留或何者優先？](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)</span><span class="sxs-lookup"><span data-stu-id="795d9-132">These two principles of retention address most conflicts that might arise when you have multiple retention policies for Teams, but for more information, see [The principles of retention, or what takes precedence?](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)</span></span>

## <a name="when-to-use-retention-policies-for-teams"></a><span data-ttu-id="795d9-133">何時要使用 Teams 的保留原則？</span><span class="sxs-lookup"><span data-stu-id="795d9-133">When to use retention policies for Teams</span></span>

<span data-ttu-id="795d9-134">在許多情況下，組織會認為私人聊天資料比頻道訊息有更多的責任，通常是和專案更相關的交談。</span><span class="sxs-lookup"><span data-stu-id="795d9-134">In many cases, organizations consider private chat data as more of a liability than channel messages, which are typically more project-related conversations.</span></span>

<span data-ttu-id="795d9-135">您可以為私人聊天和頻道訊息設定不同的保留原則  (1 原則對 1 聊天，或 1 原則對許多聊天) 。</span><span class="sxs-lookup"><span data-stu-id="795d9-135">You can set up separate retention policies for private chats (1:1 or 1:many chats) and channel messages.</span></span> <span data-ttu-id="795d9-136">您也可以設定唯一原則，然後套用到組織中的特定使用者或小組。</span><span class="sxs-lookup"><span data-stu-id="795d9-136">You can also configure unique policies that apply to specific users or teams in your organization.</span></span> <span data-ttu-id="795d9-137">如果是使用 Teams 聊天，您可以選取原則要套用到哪些使用者。</span><span class="sxs-lookup"><span data-stu-id="795d9-137">For Teams chats, you can select which users the policy applies to.</span></span> <span data-ttu-id="795d9-138">如果是使用 Teams 頻道訊息，您可以選取原則要套用到哪些小組。</span><span class="sxs-lookup"><span data-stu-id="795d9-138">For Teams channel messages, you can select which teams the policy applies to.</span></span>

<span data-ttu-id="795d9-139">例如，針對頻道訊息，您可以將保留原則套用到貴組織的特定小組，且該原則設定為在 1 年後執行的刪除動作。</span><span class="sxs-lookup"><span data-stu-id="795d9-139">For example, for channel messages, you can apply a retention policy to specific teams in your organization and that policy is configured with a delete action after 1 year.</span></span> <span data-ttu-id="795d9-140">然後，將另一個保留原則套用至所有其他團隊，且將該原則設定為在 3 年後執行的刪除動作。</span><span class="sxs-lookup"><span data-stu-id="795d9-140">Then apply another retention policy to all other teams and that policy is configured with a delete action after 3 years.</span></span>

## <a name="create-and-manage-retention-policies-for-teams"></a><span data-ttu-id="795d9-141">建立和管理 Microsoft Teams 保留原則</span><span class="sxs-lookup"><span data-stu-id="795d9-141">Create and manage retention policies for Teams</span></span>

<span data-ttu-id="795d9-142">若要建立或編輯 Teams 聊天和頻道訊息的保留原則，請使用 [Teams 位置的保留原則](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)。</span><span class="sxs-lookup"><span data-stu-id="795d9-142">To create or edit a retention policy for Teams chats and channel messages, use the instructions from [Retention policy for Teams locations](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations).</span></span>

<span data-ttu-id="795d9-143">該頁面提供有關為 Microsoft 365 中的其他工作負載，建立和管理保留原則的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="795d9-143">That page has additional information about creating and managing retention policies for other workloads in Microsoft 365.</span></span> <span data-ttu-id="795d9-144">例如，您可能也想要為 Microsoft 365 群組建立保留原則，以保留和刪除在 Teams 中存取並儲存於 OneDrive 或 SharePoint 中的檔案。</span><span class="sxs-lookup"><span data-stu-id="795d9-144">For example, you might want to also create a retention policy for Microsoft 365 Groups to retain and delete files that are accessed in Teams and stored in OneDrive or SharePoint.</span></span>  

## <a name="end-user-experience"></a><span data-ttu-id="795d9-145">使用者體驗</span><span class="sxs-lookup"><span data-stu-id="795d9-145">End-user experience</span></span>

<span data-ttu-id="795d9-146">對於私人聊天 (1:1 聊天) 或群組聊天，使用者會看到時間早於保留原則組態的聊天遭到刪除，並在在尚未刪除的訊息上方顯示一個自動產生的訊息，表示「我們已因貴組織保留原則而刪除較舊的訊息」。</span><span class="sxs-lookup"><span data-stu-id="795d9-146">For private chats (1:1 chats) or group chats, users will see that chats older than the retention policy configuration are deleted and an automatically generated message stating "We've deleted older messages due to your org's retention policy" is shown on top of yet undeleted messages.</span></span> <span data-ttu-id="795d9-147">例如：</span><span class="sxs-lookup"><span data-stu-id="795d9-147">For example:</span></span>

:::image type="content" source="media/retention-policies-image1.png" alt-text="使用者在 Teams 中接到通知，表示聊天訊息因 Teams 保留政策而遭刪除":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Teams 中的使用者說明訊息因 Teams 保留政策而遭刪除":::

<span data-ttu-id="795d9-150">對於頻道訊息，使用者 (頻道成員) 會在訊息過期後看到已刪除的訊息在檢視中消失。</span><span class="sxs-lookup"><span data-stu-id="795d9-150">For Channel messages, users (channel members) will see the deleted messages disappear from view after messages expire.</span></span> <span data-ttu-id="795d9-151">如果刪除的訊息是往來交談的父郵件，則會顯示一則訊息，說明「此訊息已因保留原則而遭到刪除」。</span><span class="sxs-lookup"><span data-stu-id="795d9-151">If the deleted message was a parent message of a threaded conversation, then, in place of parent message, a message stating "This message has been deleted because of a Retention Policy" will be displayed.</span></span> <span data-ttu-id="795d9-152">例如：</span><span class="sxs-lookup"><span data-stu-id="795d9-152">For example:</span></span>

:::image type="content" source="media/retention-policies-image3.png" alt-text="保留前的頻道螢幕擷取畫面":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="保留後的頻道螢幕擷取畫面":::

> [!NOTE]
> <span data-ttu-id="795d9-155">使用者因刪除郵件而看到的訊息顯示為目前無法進行設定。</span><span class="sxs-lookup"><span data-stu-id="795d9-155">The displayed messages that users see as a result of deleted messages are not configurable at this time.</span></span>

<span data-ttu-id="795d9-156">這些顯示訊息中的連結會移至 [Teams 保留原則的訊息](https://support.microsoft.com/zh-TW/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。</span><span class="sxs-lookup"><span data-stu-id="795d9-156">The links in these displayed messages go to [Teams messages about retention policies](https://support.microsoft.com/zh-TW/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span> <span data-ttu-id="795d9-157">此份使用者的文件可協助回答有關為何訊息遭到刪除的基本問題。</span><span class="sxs-lookup"><span data-stu-id="795d9-157">This documentation for end users helps to answer basic questions about why their messages have been deleted.</span></span> <span data-ttu-id="795d9-158">不過，作為保留原則部署的一部分，請確定您向使用者和技術支援中心表達您已配置的設定影響。</span><span class="sxs-lookup"><span data-stu-id="795d9-158">However, as part of your retention policy deployment, make sure that you communicate to users and your help desk the impact of your configured settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="795d9-159">相關主題</span><span class="sxs-lookup"><span data-stu-id="795d9-159">Related topics</span></span>

- [<span data-ttu-id="795d9-160">開始使用保留原則和保留標籤</span><span class="sxs-lookup"><span data-stu-id="795d9-160">Get started with retention policies and retention labels</span></span>](/microsoft-365/compliance/get-started-with-retention)
- [<span data-ttu-id="795d9-161">了解 Microsoft Teams 保留</span><span class="sxs-lookup"><span data-stu-id="795d9-161">Learn about retention for Microsoft Teams</span></span>](/microsoft-365/compliance/retention-policies-teams)
- [<span data-ttu-id="795d9-162">建立及設定保留原則</span><span class="sxs-lookup"><span data-stu-id="795d9-162">Create and configure retention policies</span></span>](/microsoft-365/compliance/create-retention-policies)
