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
description: 使用 Microsoft 團隊的保留原則來保留遵守內部原則、行業法規或法律需求所需的訊息，以及刪除被視為責任或沒有合法商業價值的訊息。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aba9858466b43693603aa4a1cd396748d2c83d6e
ms.sourcegitcommit: def4b475b785a7b963f499cf9a1044e842ff66a5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2021
ms.locfileid: "49786825"
---
# <a name="retention-policies-in-microsoft-teams"></a><span data-ttu-id="f1be7-103">Microsoft 團隊中的保留原則</span><span class="sxs-lookup"><span data-stu-id="f1be7-103">Retention policies in Microsoft Teams</span></span>

<span data-ttu-id="f1be7-104">Microsoft 365 的保留原則和保留標籤可協助您更有效率地管理組織中的資訊。</span><span class="sxs-lookup"><span data-stu-id="f1be7-104">Retention policies and retention labels from Microsoft 365 help you to more effectively manage the information in your organization.</span></span> <span data-ttu-id="f1be7-105">您可以設定保留設定，以保留遵守貴組織的內部原則、行業法規或法律需求所需的資料。</span><span class="sxs-lookup"><span data-stu-id="f1be7-105">You can configure retention settings to keep data that's needed to comply with your organization's internal policies, industry regulations, or legal needs.</span></span> <span data-ttu-id="f1be7-106">您也可以設定保留設定，以刪除被視為債務的資料、您不再需要保留的資料，或是沒有任何法律或業務價值的資料。</span><span class="sxs-lookup"><span data-stu-id="f1be7-106">You can also configure retention settings to delete data that's considered a liability, that you're no longer required to keep, or that has no legal or business value.</span></span>

<span data-ttu-id="f1be7-107">團隊支援聊天和通道訊息的保留原則，以便管理員決定是否要保留這些資料、刪除該資料，或保留一段特定的時間，然後刪除。</span><span class="sxs-lookup"><span data-stu-id="f1be7-107">Teams supports retention policies for chat and channel messages so that as an admin, you can decide proactively whether to retain this data, delete it, or retain it for a specific period of time and then delete it.</span></span> <span data-ttu-id="f1be7-108">您可以將團隊保留原則套用到整個組織或特定的使用者與團隊。</span><span class="sxs-lookup"><span data-stu-id="f1be7-108">You can apply a Teams retention policy to your entire organization or to specific users and teams.</span></span> <span data-ttu-id="f1be7-109">小組不支援保留標籤。</span><span class="sxs-lookup"><span data-stu-id="f1be7-109">Retention labels aren't supported for Teams.</span></span>

<span data-ttu-id="f1be7-110">若要深入瞭解保留，以及如何在 Microsoft 365 中使用保留原則或其他工作負荷的保留標籤來套用保留設定，請參閱 [瞭解保留原則和保留標籤](https://docs.microsoft.com/microsoft-365/compliance/retention)。</span><span class="sxs-lookup"><span data-stu-id="f1be7-110">To learn more about retention, and how you can apply retention settings by using retention policies or retention labels for other workloads in Microsoft 365, see [Learn about retention policies and retention labels](https://docs.microsoft.com/microsoft-365/compliance/retention).</span></span>

<span data-ttu-id="f1be7-111">小組保留原則的最低授權需求是 Microsoft 365 E3。</span><span class="sxs-lookup"><span data-stu-id="f1be7-111">The minimum licensing requirement for retention policies for Teams is Microsoft 365 E3.</span></span> <span data-ttu-id="f1be7-112">若要深入瞭解授權，請參閱 [Microsoft 團隊服務說明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="f1be7-112">To learn more about licensing, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="how-teams-retention-policies-work"></a><span data-ttu-id="f1be7-113">團隊保留原則的運作方式</span><span class="sxs-lookup"><span data-stu-id="f1be7-113">How Teams retention policies work</span></span>

<span data-ttu-id="f1be7-114">團隊聊天訊息會儲存在聊天中每位使用者信箱的隱藏資料夾中，而團隊頻道訊息則會儲存在小組的群組信箱中類似的隱藏資料夾中。</span><span class="sxs-lookup"><span data-stu-id="f1be7-114">Teams chat messages are stored in a hidden folder in the mailbox of each user included in the chat, and Teams channel messages are stored in a similar hidden folder in the group mailbox for the team.</span></span> <span data-ttu-id="f1be7-115">若要保留受保留原則制約的郵件，內容的複本會自動保留在名為 **SubstrateHolds** 的隱藏資料夾中，做為 [Exchange 可復原的 **專案** ] 資料夾中的子資料夾。</span><span class="sxs-lookup"><span data-stu-id="f1be7-115">To retain messages that are subject to a retention policy, a copy of the content is automatically kept in a hidden folder named **SubstrateHolds** as a subfolder in the Exchange **Recoverable Items** folder.</span></span> <span data-ttu-id="f1be7-116">在這些郵件從 SubstrateHolds 資料夾中永久刪除前，這些訊息會保持透過 eDiscovery 工具的搜尋。</span><span class="sxs-lookup"><span data-stu-id="f1be7-116">Until these messages are permanently deleted from the SubstrateHolds folder, they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="f1be7-117">如需小組保留原則所包含及排除之內容的詳細資訊，以及這些原則的運作方式，請參閱 [瞭解 Microsoft 團隊的保留](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)情況。</span><span class="sxs-lookup"><span data-stu-id="f1be7-117">For detailed information about what's included and excluded for Teams retention policies, and how these policies work depending on your policy configuration, see [Learn about retention for Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="f1be7-118">這個頁面會說明為何保留原則刪除郵件時，可能會發生延遲。</span><span class="sxs-lookup"><span data-stu-id="f1be7-118">That page explains why you might sometimes see delays when retention policies delete messages.</span></span> <span data-ttu-id="f1be7-119">例如，郵件在保留原則中設定的到期期限之後，最多可顯示7天。</span><span class="sxs-lookup"><span data-stu-id="f1be7-119">For example, messages can be visible up to 7 days after the expiration period you've configured in the retention policy.</span></span>

<span data-ttu-id="f1be7-120">如果您使用不同的保留設定設定多個小組保留原則，保留原則會解決任何衝突。</span><span class="sxs-lookup"><span data-stu-id="f1be7-120">If you set up multiple Teams retention policies with different retention settings, the principles of retention resolve any conflicts.</span></span> <span data-ttu-id="f1be7-121">例如：</span><span class="sxs-lookup"><span data-stu-id="f1be7-121">For example:</span></span>
- <span data-ttu-id="f1be7-122">如果在保留或刪除相同內容時發生衝突，該內容會一直保留下來。</span><span class="sxs-lookup"><span data-stu-id="f1be7-122">If there is a conflict between retaining or deleting the same content, the content is always retained.</span></span>
- <span data-ttu-id="f1be7-123">如果您保留相同內容的時間有多長，則會保留較長的保留期間。</span><span class="sxs-lookup"><span data-stu-id="f1be7-123">If there is a conflict in how long to retain the same content, it is retained for the longest retention period.</span></span>

<span data-ttu-id="f1be7-124">當您有多個小組保留原則時，這些保留位址的兩個原則可能會產生大多數衝突，但如需詳細資訊，請參閱 [保留原則或優先順序為何？](https://docs.microsoft.com/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)</span><span class="sxs-lookup"><span data-stu-id="f1be7-124">These two principles of retention address most conflicts that might arise when you have multiple retention policies for Teams, but for more information, see [The principles of retention, or what takes precedence?](https://docs.microsoft.com/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)</span></span>

## <a name="when-to-use-retention-policies-for-teams"></a><span data-ttu-id="f1be7-125">何時使用小組的保留原則</span><span class="sxs-lookup"><span data-stu-id="f1be7-125">When to use retention policies for Teams</span></span>

<span data-ttu-id="f1be7-126">在許多情況下，組織會考慮使用私人聊天資料，而不是頻道訊息，通常是更多與專案相關的交談。</span><span class="sxs-lookup"><span data-stu-id="f1be7-126">In many cases, organizations consider private chat data as more of a liability than channel messages, which are typically more project-related conversations.</span></span>

<span data-ttu-id="f1be7-127">您可以針對私人聊天 (1:1 或1：設定個別的保留原則，) 與頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="f1be7-127">You can set up separate retention policies for private chats (1:1 or 1:many chats) and channel messages.</span></span> <span data-ttu-id="f1be7-128">您也可以設定適用于組織中特定使用者或團隊的唯一原則。</span><span class="sxs-lookup"><span data-stu-id="f1be7-128">You can also configure unique policies that apply to specific users or teams in your organization.</span></span> <span data-ttu-id="f1be7-129">針對 [團隊聊天]，您可以選取要套用原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="f1be7-129">For Teams chats, you can select which users the policy applies to.</span></span> <span data-ttu-id="f1be7-130">針對團隊頻道訊息，您可以選取要套用原則的小組。</span><span class="sxs-lookup"><span data-stu-id="f1be7-130">For Teams channel messages, you can select which teams the policy applies to.</span></span>

<span data-ttu-id="f1be7-131">例如，對於頻道訊息，您可以將一年刪除原則套用到貴組織中的特定小組，並將三年的刪除原則套用至所有其他團隊。</span><span class="sxs-lookup"><span data-stu-id="f1be7-131">For example, for channel messages, you can apply a one-year deletion policy to specific teams in your organization and apply a three-year deletion policy to all other teams.</span></span>

## <a name="create-and-manage-retention-policies-for-teams"></a><span data-ttu-id="f1be7-132">建立及管理團隊的保留原則</span><span class="sxs-lookup"><span data-stu-id="f1be7-132">Create and manage retention policies for Teams</span></span>

<span data-ttu-id="f1be7-133">若要建立小組聊天與頻道訊息的保留原則，請使用 [小組位置的保留原則](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)中的指示。</span><span class="sxs-lookup"><span data-stu-id="f1be7-133">To create a retention policy for Teams chats and channel messages, use the instructions from [Retention policy for Teams locations](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations).</span></span>

<span data-ttu-id="f1be7-134">此頁面包含有關在 Microsoft 365 中建立及管理其他工作負荷之保留原則的其他相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f1be7-134">That page has additional information about creating and managing retention policies for other workloads in Microsoft 365.</span></span> <span data-ttu-id="f1be7-135">例如，您可能會想要為 Microsoft 365 群組建立保留原則，以保留並刪除在小組中存取並儲存在 OneDrive 或 SharePoint 中的檔案。</span><span class="sxs-lookup"><span data-stu-id="f1be7-135">For example, you might want to also create a retention policy for Microsoft 365 Groups to retain and delete files that are accessed in Teams and stored in OneDrive or SharePoint.</span></span>  

## <a name="end-user-experience"></a><span data-ttu-id="f1be7-136">使用者體驗</span><span class="sxs-lookup"><span data-stu-id="f1be7-136">End user experience</span></span>

<span data-ttu-id="f1be7-137">針對私人聊天 (1:1 聊天) 或群組聊天，最終使用者將會看到舊版的聊天與保留原則設定會被刪除，而「我們已刪除您組織的保留原則」等「我們已刪除較舊的郵件」的控制訊息會顯示在尚未刪除的郵件上。</span><span class="sxs-lookup"><span data-stu-id="f1be7-137">For private chats (1:1 chats) or group chats, the end users will see that chats older than the retention policy configuration are deleted and a control message stating "We've deleted older messages due to your org's retention policy" is shown on top of yet undeleted messages.</span></span>

:::image type="content" source="media/retention-policies-image1.png" alt-text="因團隊保留原則而刪除聊天訊息的小組中的使用者":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="小組中的使用者會因小組保留原則而刪除訊息":::

<span data-ttu-id="f1be7-140">對於頻道訊息，) 的使用者 (頻道成員將會看到郵件過期後，已刪除的郵件會從視野中消失。</span><span class="sxs-lookup"><span data-stu-id="f1be7-140">For Channel messages, the end users (channel members) will see the deleted messages disappear from view after messages expire.</span></span> <span data-ttu-id="f1be7-141">如果已刪除的郵件是有線程交談的父郵件，則會顯示一則訊息，指出「此郵件已因保留原則而刪除」。</span><span class="sxs-lookup"><span data-stu-id="f1be7-141">If the deleted message was a parent message of a threaded conversation, then, in place of parent message, a message stating "This message has been deleted because of a Retention Policy" will be displayed.</span></span>

:::image type="content" source="media/retention-policies-image3.png" alt-text="在保留之前先頻道的螢幕擷取畫面":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="保留期間的頻道螢幕擷取畫面":::

> [!NOTE]
> <span data-ttu-id="f1be7-144">最終使用者看到的已刪除訊息結果的顯示訊息，此時無法進行設定。</span><span class="sxs-lookup"><span data-stu-id="f1be7-144">The displayed messages that end users see as a result of deleted messaging are not configurable at this time.</span></span>


## <a name="related-topics"></a><span data-ttu-id="f1be7-145">相關主題</span><span class="sxs-lookup"><span data-stu-id="f1be7-145">Related topics</span></span>

- [<span data-ttu-id="f1be7-146">開始使用保留原則和保留標籤</span><span class="sxs-lookup"><span data-stu-id="f1be7-146">Get started with retention policies and retention labels</span></span>](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-retention)
- [<span data-ttu-id="f1be7-147">瞭解 Microsoft 團隊的保留</span><span class="sxs-lookup"><span data-stu-id="f1be7-147">Learn about retention for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)
- [<span data-ttu-id="f1be7-148">建立及設定保留原則</span><span class="sxs-lookup"><span data-stu-id="f1be7-148">Create and configure retention policies</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies)