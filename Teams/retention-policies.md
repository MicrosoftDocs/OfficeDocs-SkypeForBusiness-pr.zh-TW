---
title: 管理保留Microsoft Teams
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 使用適用于 Microsoft Teams 的保留原則，保留貴組織需要遵守內部原則、產業法規或法律要求的郵件，以及刪除被視為責任或沒有法律商業價值的郵件。
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
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/07/2021
ms.locfileid: "51617755"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a><span data-ttu-id="19edf-103">管理保留Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="19edf-103">Manage retention policies for Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="19edf-104">如果您在郵件中看到一則Teams聊天或訊息已被保留政策刪除，請參閱Teams[保留政策相關訊息](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。</span><span class="sxs-lookup"><span data-stu-id="19edf-104">If you are seeing a message in Teams that your chats or messages have been deleted by a retention policy, see [Teams messages about retention policies](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span>
> 
> <span data-ttu-id="19edf-105">此頁面的資訊適用于管理這些保留原則的 IT 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="19edf-105">The information on this page is for IT administrators who manage these retention policies.</span></span>

<span data-ttu-id="19edf-106">來自貴組織的保留Microsoft 365保留標籤，可協助您更有效地管理貴組織的資訊。</span><span class="sxs-lookup"><span data-stu-id="19edf-106">Retention policies and retention labels from Microsoft 365 help you to more effectively manage the information in your organization.</span></span> <span data-ttu-id="19edf-107">您可以設定保留設定，以保留符合貴組織的內部政策、產業法規或法律要求所需的資料。</span><span class="sxs-lookup"><span data-stu-id="19edf-107">You can configure retention settings to keep data that's needed to comply with your organization's internal policies, industry regulations, or legal requirements.</span></span> <span data-ttu-id="19edf-108">您也可以設定保留設定，刪除被視為責任、不再需要保留或沒有法律或商務價值的資料。</span><span class="sxs-lookup"><span data-stu-id="19edf-108">You can also configure retention settings to delete data that's considered a liability, that you're no longer required to keep, or that has no legal or business value.</span></span>

<span data-ttu-id="19edf-109">Teams聊天和頻道訊息的保留政策，這樣您才能主動決定是否要保留、刪除或保留資料一段時間，然後再刪除。</span><span class="sxs-lookup"><span data-stu-id="19edf-109">Teams supports retention policies for chat and channel messages so that as an admin, you can decide proactively whether to retain this data, delete it, or retain it for a specific period of time and then delete it.</span></span> <span data-ttu-id="19edf-110">這些動作的保留期間開始一直取決於郵件的建立時間。</span><span class="sxs-lookup"><span data-stu-id="19edf-110">The start of the retention period for these actions is always based on when a message is created.</span></span> <span data-ttu-id="19edf-111">您可以將保留原則Teams整個組織或特定使用者和團隊。</span><span class="sxs-lookup"><span data-stu-id="19edf-111">You can apply a Teams retention policy to your entire organization or to specific users and teams.</span></span> <span data-ttu-id="19edf-112">系統不支援保留Teams。</span><span class="sxs-lookup"><span data-stu-id="19edf-112">Retention labels aren't supported for Teams.</span></span>

<span data-ttu-id="19edf-113">若要進一Microsoft 365保留解決方案，請參閱瞭解保留[策略和保留標籤](/microsoft-365/compliance/retention)。</span><span class="sxs-lookup"><span data-stu-id="19edf-113">To learn more about retention solutions in Microsoft 365, see [Learn about retention policies and retention labels](/microsoft-365/compliance/retention).</span></span>

<span data-ttu-id="19edf-114">受系統保留政策Teams使用者必須擁有適當的授權，Office 365 E3 或 Office 365 A3。</span><span class="sxs-lookup"><span data-stu-id="19edf-114">Users who are subject to a retention policy for Teams must have an appropriate license, such as Office 365 E3 or Office 365 A3.</span></span> <span data-ttu-id="19edf-115">有關這些保留原則的其他授權選項，請參閱安全性與合規性[](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance)Microsoft 365授權指南[&>一節](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance)。</span><span class="sxs-lookup"><span data-stu-id="19edf-115">For other licensing options for these retention policies, see the [Information Governance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) section from [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance).</span></span> <span data-ttu-id="19edf-116">若要深入瞭解授權服務Teams，請參閱Microsoft Teams[描述](/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="19edf-116">To learn more about licensing for Teams, see [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="how-teams-retention-policies-support-retain-and-delete-actions"></a><span data-ttu-id="19edf-117">保留Teams如何支援保留和刪除動作</span><span class="sxs-lookup"><span data-stu-id="19edf-117">How Teams retention policies support retain and delete actions</span></span>

<span data-ttu-id="19edf-118">如果您設定保留Teams保留聊天或頻道訊息，使用者仍然可以編輯及刪除其應用程式中的郵件Teams訊息。</span><span class="sxs-lookup"><span data-stu-id="19edf-118">If you configure a Teams retention policy to retain chats or channel messages, users can still edit and delete their messages in their Teams app.</span></span> <span data-ttu-id="19edf-119">雖然使用者在 Teams 中不會再看到其預先編輯或刪除的郵件，但來自這些郵件的資料會儲存在安全的位置，該位置是專為合規性系統管理員為 eDiscovery 搜尋所設計。</span><span class="sxs-lookup"><span data-stu-id="19edf-119">Although users no longer see their pre-edited or deleted messages in Teams, data from these messages is stored in a secured location that's designed for eDiscovery searches by compliance administrators.</span></span> <span data-ttu-id="19edf-120">此資料的永久刪除不會在已配置的保留期間結束之前，或如果另一個保留原則已配置為保留此資料，或受到 [eDiscovery](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds)保留。</span><span class="sxs-lookup"><span data-stu-id="19edf-120">Permanent deletion of this data doesn't happen before the end of the configured retention period, or if another retention policy is configured to retain this data, or it is subject to an [eDiscovery hold](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds).</span></span>

<span data-ttu-id="19edf-121">當保留原則已配置為刪除聊天和頻道訊息時，這些郵件就符合自動刪除資格。</span><span class="sxs-lookup"><span data-stu-id="19edf-121">When a retention policy is configured to delete chats and channel messages, these messages become eligible for automatic deletion.</span></span> <span data-ttu-id="19edf-122">如果郵件仍顯示在 Teams應用程式中，這些郵件會從該位置消失，且使用者會得知保留原則已刪除[這些郵件](#end-user-experience)。</span><span class="sxs-lookup"><span data-stu-id="19edf-122">If the messages are still displayed in the Teams app, they will disappear from there and [users are informed that a retention policy has deleted these messages](#end-user-experience).</span></span> <span data-ttu-id="19edf-123">如果郵件先前受保留動作所保護，且使用者已編輯或刪除，這些郵件現在會從安全位置刪除，且不會再在 eDiscovery 搜尋中退回。</span><span class="sxs-lookup"><span data-stu-id="19edf-123">If the messages were previously subject to a retain action and have been edited or deleted by users, these messages will now be deleted from the secured location and no longer returned in eDiscovery searches.</span></span>

<span data-ttu-id="19edf-124">如需根據您的策略組組和使用者動作，以及 Teams 保留政策包含及排除哪些郵件資料的詳細資訊，請參閱瞭解保留[Microsoft Teams。](/microsoft-365/compliance/retention-policies-teams)</span><span class="sxs-lookup"><span data-stu-id="19edf-124">For detailed information about how these policies work depending on your policy configuration and user actions, and what message data is included and excluded for Teams retention policies, see [Learn about retention for Microsoft Teams](/microsoft-365/compliance/retention-policies-teams).</span></span> <span data-ttu-id="19edf-125">該頁面也會說明為什麼保留原則刪除郵件時，您有時會遇到延遲。</span><span class="sxs-lookup"><span data-stu-id="19edf-125">That page also explains why you might sometimes experience delays when retention policies delete messages.</span></span> <span data-ttu-id="19edf-126">例如，在保留政策中Teams期限後 7 天內，Teams App 中的使用者可以看到郵件。</span><span class="sxs-lookup"><span data-stu-id="19edf-126">For example, messages can be visible to users in the Teams app up to 7 days after the expiration period you've configured in the retention policy.</span></span>

<span data-ttu-id="19edf-127">如果您使用不同的保留設定Teams多個保留原則，保留原則會解決任何衝突。</span><span class="sxs-lookup"><span data-stu-id="19edf-127">If you set up multiple Teams retention policies with different retention settings, the principles of retention resolve any conflicts.</span></span> <span data-ttu-id="19edf-128">例如：</span><span class="sxs-lookup"><span data-stu-id="19edf-128">For example:</span></span>

- <span data-ttu-id="19edf-129">如果保留或刪除相同內容之間發生衝突，內容會一直保留在安全的位置，以便合規性系統管理員使用 eDiscovery 來搜尋內容。</span><span class="sxs-lookup"><span data-stu-id="19edf-129">If there is a conflict between retaining or deleting the same content, the content is always retained in the secured location so that it remains searchable with eDiscovery for compliance administrators.</span></span>
    
    <span data-ttu-id="19edf-130">這項原則也適用于因法律或調查理由而以電子檔探索保留為理由的郵件。</span><span class="sxs-lookup"><span data-stu-id="19edf-130">This principle also applies to messages that are under eDiscovery holds for legal or investigative reasons.</span></span>

- <span data-ttu-id="19edf-131">如果保留相同內容的時間有衝突，該內容會保留于安全位置中最長保留期間。</span><span class="sxs-lookup"><span data-stu-id="19edf-131">If there is a conflict in how long to retain the same content, it is retained in the secured location for the longest retention period.</span></span>

<span data-ttu-id="19edf-132">這兩個保留原則可解決當您有多個 Teams 保留原則時，可能會出現的衝突，但如需要詳細資訊，請參閱保留原則，或優先處理[哪些原則？](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)</span><span class="sxs-lookup"><span data-stu-id="19edf-132">These two principles of retention address most conflicts that might arise when you have multiple retention policies for Teams, but for more information, see [The principles of retention, or what takes precedence?](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)</span></span>

## <a name="when-to-use-retention-policies-for-teams"></a><span data-ttu-id="19edf-133">何時使用保留Teams</span><span class="sxs-lookup"><span data-stu-id="19edf-133">When to use retention policies for Teams</span></span>

<span data-ttu-id="19edf-134">在許多情況下，組織將私人聊天資料視為比頻道訊息更相關的責任，而頻道訊息通常更與專案相關的交談。</span><span class="sxs-lookup"><span data-stu-id="19edf-134">In many cases, organizations consider private chat data as more of a liability than channel messages, which are typically more project-related conversations.</span></span>

<span data-ttu-id="19edf-135">您可以針對私人聊天設定個別的保留 (1：1 或 1：多聊天) 頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="19edf-135">You can set up separate retention policies for private chats (1:1 or 1:many chats) and channel messages.</span></span> <span data-ttu-id="19edf-136">您也可以設定適用于貴組織中特定使用者或團隊的唯一原則。</span><span class="sxs-lookup"><span data-stu-id="19edf-136">You can also configure unique policies that apply to specific users or teams in your organization.</span></span> <span data-ttu-id="19edf-137">針對Teams聊天，您可以選取原則所適用的使用者。</span><span class="sxs-lookup"><span data-stu-id="19edf-137">For Teams chats, you can select which users the policy applies to.</span></span> <span data-ttu-id="19edf-138">針對Teams訊息，您可以選取原則所適用的團隊。</span><span class="sxs-lookup"><span data-stu-id="19edf-138">For Teams channel messages, you can select which teams the policy applies to.</span></span>

<span data-ttu-id="19edf-139">例如，針對頻道訊息，您可以將保留原則適用于貴組織的特定團隊，且該原則在 1 年後會以刪除動作進行配置。</span><span class="sxs-lookup"><span data-stu-id="19edf-139">For example, for channel messages, you can apply a retention policy to specific teams in your organization and that policy is configured with a delete action after 1 year.</span></span> <span data-ttu-id="19edf-140">然後，將另一個保留原則適用于所有其他團隊，且該原則在 3 年後會以刪除動作進行配置。</span><span class="sxs-lookup"><span data-stu-id="19edf-140">Then apply another retention policy to all other teams and that policy is configured with a delete action after 3 years.</span></span>

## <a name="create-and-manage-retention-policies-for-teams"></a><span data-ttu-id="19edf-141">建立及管理保留Teams</span><span class="sxs-lookup"><span data-stu-id="19edf-141">Create and manage retention policies for Teams</span></span>

<span data-ttu-id="19edf-142">若要建立或編輯聊天和Teams訊息的保留政策，請使用保留Teams[指示](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)。</span><span class="sxs-lookup"><span data-stu-id="19edf-142">To create or edit a retention policy for Teams chats and channel messages, use the instructions from [Retention policy for Teams locations](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations).</span></span>

<span data-ttu-id="19edf-143">該頁面包含有關在 Microsoft 365 中建立及管理其他工作負載的保留Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="19edf-143">That page has additional information about creating and managing retention policies for other workloads in Microsoft 365.</span></span> <span data-ttu-id="19edf-144">例如，您可能也想要為 Microsoft 365 群組建立保留原則，以保留和刪除在 Teams 中存取並儲存在 OneDrive 或 SharePoint 中的檔案。</span><span class="sxs-lookup"><span data-stu-id="19edf-144">For example, you might want to also create a retention policy for Microsoft 365 Groups to retain and delete files that are accessed in Teams and stored in OneDrive or SharePoint.</span></span>  

## <a name="end-user-experience"></a><span data-ttu-id="19edf-145">使用者體驗</span><span class="sxs-lookup"><span data-stu-id="19edf-145">End-user experience</span></span>

<span data-ttu-id="19edf-146">對於私人聊天 (1：1 聊天) 或群組聊天，使用者會看到刪除保留原則組配置的較舊的聊天，而自動產生的訊息會指出「我們已因為貴組織保留政策而刪除較舊的訊息」，會顯示在尚未刪除的郵件上方。</span><span class="sxs-lookup"><span data-stu-id="19edf-146">For private chats (1:1 chats) or group chats, users will see that chats older than the retention policy configuration are deleted and an automatically generated message stating "We've deleted older messages due to your org's retention policy" is shown on top of yet undeleted messages.</span></span> <span data-ttu-id="19edf-147">例如：</span><span class="sxs-lookup"><span data-stu-id="19edf-147">For example:</span></span>

:::image type="content" source="media/retention-policies-image1.png" alt-text="使用者Teams聊天訊息會因為保留Teams而刪除":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="在Teams中說明郵件的使用者會因為保留Teams而刪除":::

<span data-ttu-id="19edf-150">針對頻道訊息， (頻道) 使用者會看到已刪除的郵件在郵件過期後從視圖中消失。</span><span class="sxs-lookup"><span data-stu-id="19edf-150">For Channel messages, users (channel members) will see the deleted messages disappear from view after messages expire.</span></span> <span data-ttu-id="19edf-151">如果刪除的郵件是討論執行緒交談的父郵件，則會顯示一則訊息，指出「此郵件已因保留政策而遭到刪除」，以代之父訊息。</span><span class="sxs-lookup"><span data-stu-id="19edf-151">If the deleted message was a parent message of a threaded conversation, then, in place of parent message, a message stating "This message has been deleted because of a Retention Policy" will be displayed.</span></span> <span data-ttu-id="19edf-152">例如：</span><span class="sxs-lookup"><span data-stu-id="19edf-152">For example:</span></span>

:::image type="content" source="media/retention-policies-image3.png" alt-text="保留前頻道的螢幕擷取畫面":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="保留後的頻道螢幕擷取畫面":::

> [!NOTE]
> <span data-ttu-id="19edf-155">使用者目前無法針對已刪除的郵件看到顯示的郵件進行配置。</span><span class="sxs-lookup"><span data-stu-id="19edf-155">The displayed messages that users see as a result of deleted messages are not configurable at this time.</span></span>

<span data-ttu-id="19edf-156">這些顯示的郵件中的連結會Teams[保留政策相關之郵件](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。</span><span class="sxs-lookup"><span data-stu-id="19edf-156">The links in these displayed messages go to [Teams messages about retention policies](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span> <span data-ttu-id="19edf-157">此適用于使用者的檔可協助回答有關其郵件為何遭到刪除的基本問題。</span><span class="sxs-lookup"><span data-stu-id="19edf-157">This documentation for end users helps to answer basic questions about why their messages have been deleted.</span></span> <span data-ttu-id="19edf-158">不過，在保留原則部署中，請確定您與使用者和技術支援人員溝通您設定設定的影響。</span><span class="sxs-lookup"><span data-stu-id="19edf-158">However, as part of your retention policy deployment, make sure that you communicate to users and your help desk the impact of your configured settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="19edf-159">相關主題</span><span class="sxs-lookup"><span data-stu-id="19edf-159">Related topics</span></span>

- [<span data-ttu-id="19edf-160">開始使用保留原則和保留標籤</span><span class="sxs-lookup"><span data-stu-id="19edf-160">Get started with retention policies and retention labels</span></span>](/microsoft-365/compliance/get-started-with-retention)
- [<span data-ttu-id="19edf-161">瞭解保留Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="19edf-161">Learn about retention for Microsoft Teams</span></span>](/microsoft-365/compliance/retention-policies-teams)
- [<span data-ttu-id="19edf-162">建立及設定保留政策</span><span class="sxs-lookup"><span data-stu-id="19edf-162">Create and configure retention policies</span></span>](/microsoft-365/compliance/create-retention-policies)
