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
ms.openlocfilehash: cd2c2e69054923ccf287f35a15fcebb870d6a5d5
ms.sourcegitcommit: 545e466f1fa9163bb00cc96c8db70a70b02af697
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "42928446"
---
# <a name="manage-tags-in-microsoft-teams"></a><span data-ttu-id="8d443-103">管理 Microsoft 團隊中的標記</span><span class="sxs-lookup"><span data-stu-id="8d443-103">Manage tags in Microsoft Teams</span></span>

<span data-ttu-id="8d443-104">Microsoft 團隊中的標記可讓使用者與團隊中的人員子集進行通訊。</span><span class="sxs-lookup"><span data-stu-id="8d443-104">Tags in Microsoft Teams let users communicate with a subset of people on a team.</span></span> <span data-ttu-id="8d443-105">您可以將標籤新增至一或多個小組成員，輕鬆地與正確的人員子集連線。</span><span class="sxs-lookup"><span data-stu-id="8d443-105">Tags can be added to one or multiple team members to easily connect with the right subset of people.</span></span> <span data-ttu-id="8d443-106">小組擁有者和成員（如果已為他們啟用功能）可以在人員中新增一或多個標記。</span><span class="sxs-lookup"><span data-stu-id="8d443-106">Team owners and members (if the feature is enabled for them) can add one or more tags to a person.</span></span> <span data-ttu-id="8d443-107">然後，您就可以 @mentions 使用這些標籤，讓團隊中的任何人都能使用這些標籤，或只與已分派該標記的人員開始交談。</span><span class="sxs-lookup"><span data-stu-id="8d443-107">The tags can then be used in @mentions by anyone on the team in a channel post or to start a conversation with only those people who are assigned that tag.</span></span>

> [!NOTE]
> <span data-ttu-id="8d443-108">在私有通道中尚不支援標記。</span><span class="sxs-lookup"><span data-stu-id="8d443-108">Tags are not yet supported in private channels.</span></span>

## <a name="how-tags-work"></a><span data-ttu-id="8d443-109">標記的運作方式</span><span class="sxs-lookup"><span data-stu-id="8d443-109">How tags work</span></span>

<span data-ttu-id="8d443-110">您可以將標記新增至特定小組中的人員。</span><span class="sxs-lookup"><span data-stu-id="8d443-110">A tag can be added to a person on a specific team.</span></span> <span data-ttu-id="8d443-111">新增標籤之後，就可以在聊天的 @mentions 中或在團隊的任何標準頻道中使用它。</span><span class="sxs-lookup"><span data-stu-id="8d443-111">After a tag is added, it can be used in @mentions in a chat or in any standard channel of the team.</span></span> <span data-ttu-id="8d443-112">以下是如何在團隊中使用標記的一些範例：</span><span class="sxs-lookup"><span data-stu-id="8d443-112">Here's some examples of how tags can be used in Teams:</span></span>

- <span data-ttu-id="8d443-113">商店管理員想要張貼公告至頻道並通知所有出納。</span><span class="sxs-lookup"><span data-stu-id="8d443-113">A store manager wants to post an announcement to a channel and notify all cashiers.</span></span>
- <span data-ttu-id="8d443-114">群組產品經理想要將頻道中的所有產品經理宣傳。</span><span class="sxs-lookup"><span data-stu-id="8d443-114">A group product manager wants to message all product managers in a channel.</span></span>
- <span data-ttu-id="8d443-115">醫院管理員想要傳送訊息給頻道中的所有 radiologists。</span><span class="sxs-lookup"><span data-stu-id="8d443-115">A hospital administrator wants to send a message to all radiologists in a channel.</span></span>
- <span data-ttu-id="8d443-116">行銷經理想要與所有設計人員一起開始進行群組聊天。</span><span class="sxs-lookup"><span data-stu-id="8d443-116">A marketing manager wants to start a group chat with all designers.</span></span> 

<span data-ttu-id="8d443-117">若要深入瞭解，請參閱[在團隊中使用標記](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)。</span><span class="sxs-lookup"><span data-stu-id="8d443-117">To learn more, check out [Using tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span></span>

## <a name="manage-tags-for-your-organization"></a><span data-ttu-id="8d443-118">管理貴組織的標記</span><span class="sxs-lookup"><span data-stu-id="8d443-118">Manage tags for your organization</span></span>

<span data-ttu-id="8d443-119">身為系統管理員，您可以控制誰可以新增標記，以及如何在 Microsoft 團隊系統管理中心的整個組織中使用標記。</span><span class="sxs-lookup"><span data-stu-id="8d443-119">As an admin, you can control who can add tags and how tags are used across your organization in the Microsoft Teams admin center.</span></span>

![Microsoft 團隊系統管理中心的標記設定的螢幕擷取畫面](media/manage-tags-admin-settings.png)

### <a name="set-who-can-add-tags"></a><span data-ttu-id="8d443-121">設定誰可以新增標記</span><span class="sxs-lookup"><span data-stu-id="8d443-121">Set who can add tags</span></span>

<span data-ttu-id="8d443-122">根據預設，小組擁有者可以新增標記。</span><span class="sxs-lookup"><span data-stu-id="8d443-122">By default, team owners can add tags.</span></span> <span data-ttu-id="8d443-123">您可以變更此設定，以允許小組擁有者和小組成員新增標籤，或者您可以關閉組織的標記。</span><span class="sxs-lookup"><span data-stu-id="8d443-123">You can change this setting to allow team owners and team members to add tags or you can turn off tags for your organization.</span></span>

1. <span data-ttu-id="8d443-124">在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**全組織性設定** > **團隊設定**]。</span><span class="sxs-lookup"><span data-stu-id="8d443-124">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="8d443-125">在 [**標記**] 底下的 [**標記已啟用**] 旁，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="8d443-125">Under **Tagging**, next to **Tagging is enabled for**, select one of the following options:</span></span>

    - <span data-ttu-id="8d443-126">**小組擁有者和成員**：允許小組擁有者和成員新增標記。</span><span class="sxs-lookup"><span data-stu-id="8d443-126">**Team owners and members**: Allow team owners and members to add tags.</span></span>
    - <span data-ttu-id="8d443-127">**小組擁有**者：允許小組擁有者新增標記。</span><span class="sxs-lookup"><span data-stu-id="8d443-127">**Team owners**: Allow team owners to add tags.</span></span>
    - <span data-ttu-id="8d443-128">[**已停用**]：關閉標記。</span><span class="sxs-lookup"><span data-stu-id="8d443-128">**Disabled**: Turn off tags.</span></span>

### <a name="configure-tags-settings"></a><span data-ttu-id="8d443-129">設定標籤設定</span><span class="sxs-lookup"><span data-stu-id="8d443-129">Configure tags settings</span></span>

<span data-ttu-id="8d443-130">您可以設定下列標記設定，以控制如何在整個組織中使用標記。</span><span class="sxs-lookup"><span data-stu-id="8d443-130">You can configure the following tags settings to control how tags are used across your organization.</span></span>

1. <span data-ttu-id="8d443-131">在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**全組織性設定** > **團隊設定**]。</span><span class="sxs-lookup"><span data-stu-id="8d443-131">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="8d443-132">根據貴組織的需求，在 [**標記**] 底下設定下列各項。</span><span class="sxs-lookup"><span data-stu-id="8d443-132">Under **Tagging**, set the following, depending on the needs of your organization.</span></span>

    - <span data-ttu-id="8d443-133">**小組擁有者可以覆寫可以**套用標籤的人員：開啟此選項時，小組擁有者可以允許或不允許成員在團隊設定中新增標記。</span><span class="sxs-lookup"><span data-stu-id="8d443-133">**Team owner can override who can apply tags**: When this is turned on, team owners can allow or disallow members to add tags in team settings.</span></span>
    - <span data-ttu-id="8d443-134">**成員可以新增其他**標籤：如果您允許小組成員新增標籤，請開啟此選項，讓小組成員新增除了您所設定的預設標記以外的其他標記。</span><span class="sxs-lookup"><span data-stu-id="8d443-134">**Members can add additional tags**: If you allow team members to add tags, turn this on to let team members add tags other than the suggested default tags that you set.</span></span> <span data-ttu-id="8d443-135">如果您關閉此功能，小組成員只能使用預設的標記。</span><span class="sxs-lookup"><span data-stu-id="8d443-135">If this is turned off, team members can only use the default tags.</span></span>
    - <span data-ttu-id="8d443-136">**建議的預設**標籤：使用這個功能來新增一組預設的標籤。</span><span class="sxs-lookup"><span data-stu-id="8d443-136">**Suggested default tags**: Use this to add a set of default tags.</span></span> <span data-ttu-id="8d443-137">您可以新增最多25個標籤，每個標籤最多可包含25個字元。</span><span class="sxs-lookup"><span data-stu-id="8d443-137">You can add up to 25 tags, and each tag can contain a maximum of 25 characters.</span></span> <span data-ttu-id="8d443-138">小組擁有者和成員（如果已為他們啟用功能）可以使用這些建議、新增至他們，或建立一組新的標記。</span><span class="sxs-lookup"><span data-stu-id="8d443-138">Team owners and members (if the feature is enabled for them) can use these suggestions, add to them, or create a new set of tags.</span></span>

## <a name="manage-tags-settings-for-a-team"></a><span data-ttu-id="8d443-139">管理團隊的標記設定</span><span class="sxs-lookup"><span data-stu-id="8d443-139">Manage tags settings for a team</span></span>

<span data-ttu-id="8d443-140">如果您開啟 [**小組擁有者可以覆寫**Microsoft 團隊系統管理中心中可以套用標籤] 設定的人員，小組擁有者可以設定成員是否可以在小組層級新增標記。</span><span class="sxs-lookup"><span data-stu-id="8d443-140">If you turned on the **Team owner can override who can apply tags** setting in the Microsoft Teams admin center, team owners can set whether members can add tags at the team level.</span></span> <span data-ttu-id="8d443-141">若要這樣做，請在團隊的 [**設定**] 索引標籤上，移至 [標籤 **]，然後**選擇誰可以新增標記。</span><span class="sxs-lookup"><span data-stu-id="8d443-141">To do this, on the **Settings** tab for a team, go to **Tags**, and then choose who can add tags.</span></span>

![小組層次上的 [標籤] 設定的螢幕擷取畫面](media/manage-tags-team-settings.png)

## <a name="add-tags-in-teams"></a><span data-ttu-id="8d443-143">在團隊中新增標記</span><span class="sxs-lookup"><span data-stu-id="8d443-143">Add tags in Teams</span></span>

<span data-ttu-id="8d443-144">在團隊中，小組的 [管理團隊] 頁面上的 [**成員**] 索引標籤包含 [**標記**] 欄。</span><span class="sxs-lookup"><span data-stu-id="8d443-144">In Teams, the **Members** tab of the Manage team page for a team includes a **Tags** column.</span></span> <span data-ttu-id="8d443-145">小組擁有者和成員（如果已為他們啟用功能）可以按一下成員旁的 [**管理標記**]，即可查看該成員的建議標記清單，並將標記新增到清單中。</span><span class="sxs-lookup"><span data-stu-id="8d443-145">Team owners and members (if the feature is enabled for them) can click **Manage tags** next to a member to see the list of suggested tags for that member and add tags to the list.</span></span>

![<span data-ttu-id="8d443-146">如何在團隊用戶端套用標記的螢幕擷取畫面</span><span class="sxs-lookup"><span data-stu-id="8d443-146">Screenshot of how to apply tags in the Teams client</span></span> ](media/manage-tags-teams.png) 
