---
title: 管理 Microsoft 團隊中的標記
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: acolonna
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中管理組織中使用標記的方式。
ms.openlocfilehash: b19613268384831aaaa2608fc183b62fdc1b0445
ms.sourcegitcommit: 0979fae58ecd713f8317ed99caae015b5cc2c8e4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2020
ms.locfileid: "44877934"
---
# <a name="manage-tags-in-microsoft-teams"></a><span data-ttu-id="2a39f-103">管理 Microsoft 團隊中的標記</span><span class="sxs-lookup"><span data-stu-id="2a39f-103">Manage tags in Microsoft Teams</span></span>

<span data-ttu-id="2a39f-104">Microsoft 團隊中的標記可讓使用者與團隊中的人員子集進行通訊。</span><span class="sxs-lookup"><span data-stu-id="2a39f-104">Tags in Microsoft Teams let users communicate with a subset of people on a team.</span></span> <span data-ttu-id="2a39f-105">您可以將標籤新增至一或多個小組成員，輕鬆地與正確的人員子集連線。</span><span class="sxs-lookup"><span data-stu-id="2a39f-105">Tags can be added to one or multiple team members to easily connect with the right subset of people.</span></span> <span data-ttu-id="2a39f-106">小組擁有者和成員（如果已為他們啟用功能）可以在人員中新增一或多個標記。</span><span class="sxs-lookup"><span data-stu-id="2a39f-106">Team owners and members (if the feature is enabled for them) can add one or more tags to a person.</span></span> <span data-ttu-id="2a39f-107">然後，您就可以 @mentions 使用這些標籤，讓團隊中的任何人都能使用這些標籤，或只與已分派該標記的人員開始交談。</span><span class="sxs-lookup"><span data-stu-id="2a39f-107">The tags can then be used in @mentions by anyone on the team in a channel post or to start a conversation with only those people who are assigned that tag.</span></span>

> [!NOTE]
> <span data-ttu-id="2a39f-108">在私有通道中尚不支援標記。</span><span class="sxs-lookup"><span data-stu-id="2a39f-108">Tags are not yet supported in private channels.</span></span> <span data-ttu-id="2a39f-109">在美國政府社區雲端（GCC）、GCC 高或國防（DoD）組織中尚不提供標記。</span><span class="sxs-lookup"><span data-stu-id="2a39f-109">Tags are not yet available in US Government Community Cloud (GCC), GCC High, or Department of Defense (DoD) organizations.</span></span>

## <a name="how-tags-work"></a><span data-ttu-id="2a39f-110">標記的運作方式</span><span class="sxs-lookup"><span data-stu-id="2a39f-110">How tags work</span></span>

<span data-ttu-id="2a39f-111">您可以將標記新增至特定小組中的人員。</span><span class="sxs-lookup"><span data-stu-id="2a39f-111">A tag can be added to a person on a specific team.</span></span> <span data-ttu-id="2a39f-112">新增標籤之後，就可以在聊天的 @mentions 中或在團隊的任何標準頻道中使用它。</span><span class="sxs-lookup"><span data-stu-id="2a39f-112">After a tag is added, it can be used in @mentions in a chat or in any standard channel of the team.</span></span> <span data-ttu-id="2a39f-113">以下是如何在團隊中使用標記的一些範例：</span><span class="sxs-lookup"><span data-stu-id="2a39f-113">Here's some examples of how tags can be used in Teams:</span></span>

- <span data-ttu-id="2a39f-114">商店管理員想要張貼公告至頻道並通知所有出納。</span><span class="sxs-lookup"><span data-stu-id="2a39f-114">A store manager wants to post an announcement to a channel and notify all cashiers.</span></span>
- <span data-ttu-id="2a39f-115">群組產品經理想要將頻道中的所有產品經理宣傳。</span><span class="sxs-lookup"><span data-stu-id="2a39f-115">A group product manager wants to message all product managers in a channel.</span></span>
- <span data-ttu-id="2a39f-116">醫院管理員想要傳送訊息給頻道中的所有 radiologists。</span><span class="sxs-lookup"><span data-stu-id="2a39f-116">A hospital administrator wants to send a message to all radiologists in a channel.</span></span>
- <span data-ttu-id="2a39f-117">行銷經理想要與所有設計人員一起開始進行群組聊天。</span><span class="sxs-lookup"><span data-stu-id="2a39f-117">A marketing manager wants to start a group chat with all designers.</span></span>

<span data-ttu-id="2a39f-118">當您在頻道交談中 @mentioned 標籤時，與標籤相關聯的小組成員就會收到通知，就像任何其他的 @mention 一樣。</span><span class="sxs-lookup"><span data-stu-id="2a39f-118">When a tag is @mentioned in a channel conversation, team members associated with the tag will get notified, just like any other @mention.</span></span>

<span data-ttu-id="2a39f-119">若要深入瞭解，請參閱[在團隊中使用標記](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)。</span><span class="sxs-lookup"><span data-stu-id="2a39f-119">To learn more, check out [Using tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span></span>

## <a name="manage-tags-for-your-organization"></a><span data-ttu-id="2a39f-120">管理貴組織的標記</span><span class="sxs-lookup"><span data-stu-id="2a39f-120">Manage tags for your organization</span></span>

<span data-ttu-id="2a39f-121">身為系統管理員，您可以控制誰可以新增標記，以及如何在 Microsoft 團隊系統管理中心的整個組織中使用標記。</span><span class="sxs-lookup"><span data-stu-id="2a39f-121">As an admin, you can control who can add tags and how tags are used across your organization in the Microsoft Teams admin center.</span></span>

![Microsoft 團隊系統管理中心的標記設定的螢幕擷取畫面](media/manage-tags-admin-settings.png)

<span data-ttu-id="2a39f-123">團隊最多可以有100個標籤，最多可將100個小組成員指派給一個標籤，而且最多25個標籤可以指派給單一使用者。</span><span class="sxs-lookup"><span data-stu-id="2a39f-123">A team can have up to 100 tags, up to 100 team members can be assigned to a tag, and up to 25 tags can be assigned to a single user.</span></span> 

### <a name="set-who-can-add-tags"></a><span data-ttu-id="2a39f-124">設定誰可以新增標記</span><span class="sxs-lookup"><span data-stu-id="2a39f-124">Set who can add tags</span></span>

<span data-ttu-id="2a39f-125">根據預設，小組擁有者可以新增標記。</span><span class="sxs-lookup"><span data-stu-id="2a39f-125">By default, team owners can add tags.</span></span> <span data-ttu-id="2a39f-126">您可以變更此設定，以允許小組擁有者和小組成員新增標籤，或者您可以關閉組織的標記。</span><span class="sxs-lookup"><span data-stu-id="2a39f-126">You can change this setting to allow team owners and team members to add tags or you can turn off tags for your organization.</span></span>

1. <span data-ttu-id="2a39f-127">在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**全組織性設定**  >  **團隊設定**]。</span><span class="sxs-lookup"><span data-stu-id="2a39f-127">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="2a39f-128">在 [**標記**] 底下的 [**標記已啟用**] 旁，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="2a39f-128">Under **Tagging**, next to **Tagging is enabled for**, select one of the following options:</span></span>

    - <span data-ttu-id="2a39f-129">**小組擁有者和成員**：允許小組擁有者和成員新增標記。</span><span class="sxs-lookup"><span data-stu-id="2a39f-129">**Team owners and members**: Allow team owners and members to add tags.</span></span>
    - <span data-ttu-id="2a39f-130">**小組擁有**者：允許小組擁有者新增標記。</span><span class="sxs-lookup"><span data-stu-id="2a39f-130">**Team owners**: Allow team owners to add tags.</span></span>
    - <span data-ttu-id="2a39f-131">[**已停用**]：關閉標記。</span><span class="sxs-lookup"><span data-stu-id="2a39f-131">**Disabled**: Turn off tags.</span></span>

### <a name="configure-tags-settings"></a><span data-ttu-id="2a39f-132">設定標籤設定</span><span class="sxs-lookup"><span data-stu-id="2a39f-132">Configure tags settings</span></span>

<span data-ttu-id="2a39f-133">您可以設定下列標記設定，以控制如何在整個組織中使用標記。</span><span class="sxs-lookup"><span data-stu-id="2a39f-133">You can configure the following tags settings to control how tags are used across your organization.</span></span>

1. <span data-ttu-id="2a39f-134">在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**全組織性設定**  >  **團隊設定**]。</span><span class="sxs-lookup"><span data-stu-id="2a39f-134">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="2a39f-135">根據貴組織的需求，在 [**標記**] 底下設定下列各項。</span><span class="sxs-lookup"><span data-stu-id="2a39f-135">Under **Tagging**, set the following, depending on the needs of your organization.</span></span>

    - <span data-ttu-id="2a39f-136">**小組擁有者可以覆寫可以**套用標籤的人員：開啟此選項時，小組擁有者可以允許或不允許成員在團隊設定中新增標記。</span><span class="sxs-lookup"><span data-stu-id="2a39f-136">**Team owner can override who can apply tags**: When this is turned on, team owners can allow or disallow members to add tags in team settings.</span></span>
    - <span data-ttu-id="2a39f-137">**成員可以新增其他**標籤：如果您允許小組成員新增標籤，請開啟此選項，讓小組成員新增除了您所設定的預設標記以外的其他標記。</span><span class="sxs-lookup"><span data-stu-id="2a39f-137">**Members can add additional tags**: If you allow team members to add tags, turn this on to let team members add tags other than the suggested default tags that you set.</span></span> <span data-ttu-id="2a39f-138">如果您關閉此功能，小組成員只能使用預設的標記。</span><span class="sxs-lookup"><span data-stu-id="2a39f-138">If this is turned off, team members can only use the default tags.</span></span>
    - <span data-ttu-id="2a39f-139">**建議的預設**標籤：使用這個功能來新增一組預設的標籤。</span><span class="sxs-lookup"><span data-stu-id="2a39f-139">**Suggested default tags**: Use this to add a set of default tags.</span></span> <span data-ttu-id="2a39f-140">您可以新增最多25個標籤，每個標籤最多可包含25個字元。</span><span class="sxs-lookup"><span data-stu-id="2a39f-140">You can add up to 25 tags, and each tag can contain a maximum of 25 characters.</span></span> <span data-ttu-id="2a39f-141">小組擁有者和成員（如果已為他們啟用功能）可以使用這些建議、新增至他們，或建立一組新的標記。</span><span class="sxs-lookup"><span data-stu-id="2a39f-141">Team owners and members (if the feature is enabled for them) can use these suggestions, add to them, or create a new set of tags.</span></span>

## <a name="manage-tags-settings-for-a-team"></a><span data-ttu-id="2a39f-142">管理團隊的標記設定</span><span class="sxs-lookup"><span data-stu-id="2a39f-142">Manage tags settings for a team</span></span>

<span data-ttu-id="2a39f-143">如果您開啟 [**小組擁有者可以覆寫**Microsoft 團隊系統管理中心中可以套用標籤] 設定的人員，小組擁有者可以設定成員是否可以在小組層級新增標記。</span><span class="sxs-lookup"><span data-stu-id="2a39f-143">If you turned on the **Team owner can override who can apply tags** setting in the Microsoft Teams admin center, team owners can set whether members can add tags at the team level.</span></span> <span data-ttu-id="2a39f-144">若要這樣做，請在團隊的 [**設定**] 索引標籤上，移至 [標籤 **]，然後**選擇誰可以新增標記。</span><span class="sxs-lookup"><span data-stu-id="2a39f-144">To do this, on the **Settings** tab for a team, go to **Tags**, and then choose who can add tags.</span></span>

![小組層次上的 [標籤] 設定的螢幕擷取畫面](media/manage-tags-team-settings.png)

## <a name="use-tags"></a><span data-ttu-id="2a39f-146">使用標記</span><span class="sxs-lookup"><span data-stu-id="2a39f-146">Use tags</span></span>

### <a name="add-tags"></a><span data-ttu-id="2a39f-147">新增標記</span><span class="sxs-lookup"><span data-stu-id="2a39f-147">Add tags</span></span>

<span data-ttu-id="2a39f-148">若要建立並指派標籤，請選取應用程式左側的 [**小組**]，然後在清單中尋找您的小組。</span><span class="sxs-lookup"><span data-stu-id="2a39f-148">To create and assign tags, select **Teams** on the left side of the app, and then find your team in the list.</span></span> <span data-ttu-id="2a39f-149">選取 [**更多選項**]，然後選擇 [**管理**標籤]。</span><span class="sxs-lookup"><span data-stu-id="2a39f-149">Select **More options**, and then choose **Manage tags**.</span></span>

<span data-ttu-id="2a39f-150">您可以在這裡建立標籤，並將其指派給小組中的人員。</span><span class="sxs-lookup"><span data-stu-id="2a39f-150">Here, you can create tags and assign them to people on your team.</span></span>

![<span data-ttu-id="2a39f-151">如何在團隊用戶端套用標記的螢幕擷取畫面</span><span class="sxs-lookup"><span data-stu-id="2a39f-151">Screenshot of how to apply tags in the Teams client</span></span> ](media/manage-tags-teams.png)

### <a name="delete-tags"></a><span data-ttu-id="2a39f-152">刪除標記</span><span class="sxs-lookup"><span data-stu-id="2a39f-152">Delete tags</span></span>

<span data-ttu-id="2a39f-153">移除所有與標籤相關聯的小組成員，並刪除該標記。</span><span class="sxs-lookup"><span data-stu-id="2a39f-153">Remove all team members associated with the tag and the tag will be deleted.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2a39f-154">相關主題</span><span class="sxs-lookup"><span data-stu-id="2a39f-154">Related topics</span></span>

[<span data-ttu-id="2a39f-155">在團隊中使用標記</span><span class="sxs-lookup"><span data-stu-id="2a39f-155">Using tags in Teams</span></span>](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)
