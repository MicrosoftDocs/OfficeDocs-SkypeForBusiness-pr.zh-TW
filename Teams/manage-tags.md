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
ms.openlocfilehash: 3ade2f47474fe8aaf16c568e8c141dcd84526d86
ms.sourcegitcommit: 561b9bab7d6f5a621436bc85ea28ea14657e7868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034494"
---
# <a name="manage-tags-in-microsoft-teams"></a><span data-ttu-id="8ebf5-103">管理 Microsoft 團隊中的標記</span><span class="sxs-lookup"><span data-stu-id="8ebf5-103">Manage tags in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="8ebf5-104">在 Microsoft 團隊系統管理中心中還沒看到這項功能嗎？</span><span class="sxs-lookup"><span data-stu-id="8ebf5-104">Don't see this feature in the Microsoft Teams admin center yet?</span></span> <span data-ttu-id="8ebf5-105">目前正在推出，您的組織可能無法使用。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-105">It's currently being rolled out and might not be available in your organization yet.</span></span> <span data-ttu-id="8ebf5-106">若要維持在即將到來的小組功能上，請參閱[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-106">To stay on top of upcoming Teams features, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).</span></span>

<span data-ttu-id="8ebf5-107">Microsoft 團隊中的標記可讓使用者與團隊中的人員子集進行通訊。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-107">Tags in Microsoft Teams let users communicate with a subset of people on a team.</span></span> <span data-ttu-id="8ebf5-108">您可以將標籤新增至一或多個小組成員，輕鬆地與正確的人員子集連線。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-108">Tags can be added to one or multiple team members to easily connect with the right subset of people.</span></span> <span data-ttu-id="8ebf5-109">小組擁有者和成員（如果已為他們啟用功能）可以在人員中新增一或多個標記。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-109">Team owners and members (if the feature is enabled for them) can add one or more tags to a person.</span></span> <span data-ttu-id="8ebf5-110">然後，您可以 @mentions 在頻道文章中，小組中的任何人都能使用這些標籤，只要與分派該標記的人員通訊即可。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-110">The tags can then be used in @mentions by anyone on the team in a channel post to communicate with only those people who are assigned that tag.</span></span>

> [!NOTE]
> <span data-ttu-id="8ebf5-111">在私有通道中尚不支援標記。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-111">Tags are not yet supported in private channels.</span></span>

## <a name="how-tags-work"></a><span data-ttu-id="8ebf5-112">標記的運作方式</span><span class="sxs-lookup"><span data-stu-id="8ebf5-112">How tags work</span></span>

<span data-ttu-id="8ebf5-113">您可以將標記新增至特定小組中的人員。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-113">A tag can be added to a person on a specific team.</span></span> <span data-ttu-id="8ebf5-114">新增標籤之後，就可以在團隊的任何標準頻道中 @mentions 使用。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-114">After a tag is added, it can be used in @mentions in any standard channel of the team.</span></span> <span data-ttu-id="8ebf5-115">以下是如何在團隊中使用標記的一些範例：</span><span class="sxs-lookup"><span data-stu-id="8ebf5-115">Here's some examples of how tags can be used in Teams:</span></span>

- <span data-ttu-id="8ebf5-116">商店管理員想要張貼公告至頻道並通知所有出納。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-116">A store manager wants to post an announcement to a channel and notify all cashiers.</span></span>
- <span data-ttu-id="8ebf5-117">群組產品經理想要將頻道中的所有產品經理宣傳。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-117">A group product manager wants to message all product managers in a channel.</span></span>
- <span data-ttu-id="8ebf5-118">醫院管理員想要傳送訊息給頻道中的所有 radiologists。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-118">A hospital administrator wants to send a message to all radiologists in a channel.</span></span>

<span data-ttu-id="8ebf5-119">若要深入瞭解，請參閱[在團隊中使用標記](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-119">To learn more, check out [Using tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span></span>

## <a name="manage-tags-for-your-organization"></a><span data-ttu-id="8ebf5-120">管理貴組織的標記</span><span class="sxs-lookup"><span data-stu-id="8ebf5-120">Manage tags for your organization</span></span>

<span data-ttu-id="8ebf5-121">身為系統管理員，您可以控制誰可以新增標記，以及如何在 Microsoft 團隊系統管理中心的整個組織中使用標記。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-121">As an admin, you can control who can add tags and how tags are used across your organization in the Microsoft Teams admin center.</span></span>

![Microsoft 團隊系統管理中心的標記設定的螢幕擷取畫面](media/manage-tags-admin-settings.png)

### <a name="set-who-can-add-tags"></a><span data-ttu-id="8ebf5-123">設定誰可以新增標記</span><span class="sxs-lookup"><span data-stu-id="8ebf5-123">Set who can add tags</span></span>

<span data-ttu-id="8ebf5-124">根據預設，小組擁有者可以新增標記。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-124">By default, team owners can add tags.</span></span> <span data-ttu-id="8ebf5-125">您可以變更此設定，以允許小組擁有者和小組成員新增標籤，或者您可以關閉組織的標記。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-125">You can change this setting to allow team owners and team members to add tags or you can turn off tags for your organization.</span></span>

1. <span data-ttu-id="8ebf5-126">在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**全組織性設定** > **團隊設定**]。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-126">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="8ebf5-127">在 [**標記**] 底下的 [**標記已啟用**] 旁，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="8ebf5-127">Under **Tagging**, next to **Tagging is enabled for**, select one of the following options:</span></span>

    - <span data-ttu-id="8ebf5-128">**小組擁有者和成員**：允許小組擁有者和成員新增標記。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-128">**Team owners and members**: Allow team owners and members to add tags.</span></span>
    - <span data-ttu-id="8ebf5-129">**小組擁有**者：允許小組擁有者新增標記。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-129">**Team owners**: Allow team owners to add tags.</span></span>
    - <span data-ttu-id="8ebf5-130">[**已停用**]：關閉標記。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-130">**Disabled**: Turn off tags.</span></span>

### <a name="configure-tags-settings"></a><span data-ttu-id="8ebf5-131">設定標籤設定</span><span class="sxs-lookup"><span data-stu-id="8ebf5-131">Configure tags settings</span></span>

<span data-ttu-id="8ebf5-132">您可以設定下列標記設定，以控制如何在整個組織中使用標記。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-132">You can configure the following tags settings to control how tags are used across your organization.</span></span>

1. <span data-ttu-id="8ebf5-133">在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**全組織性設定** > **團隊設定**]。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-133">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="8ebf5-134">根據貴組織的需求，在 [**標記**] 底下設定下列各項。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-134">Under **Tagging**, set the following, depending on the needs of your organization.</span></span>

    - <span data-ttu-id="8ebf5-135">**小組擁有者可以覆寫可以**套用標籤的人員：開啟此選項時，小組擁有者可以允許或不允許成員在團隊設定中新增標記。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-135">**Team owner can override who can apply tags**: When this is turned on, team owners can allow or disallow members to add tags in team settings.</span></span>
    - <span data-ttu-id="8ebf5-136">**成員可以新增其他**標籤：如果您允許小組成員新增標籤，請開啟此選項，讓小組成員新增除了您所設定的預設標記以外的其他標記。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-136">**Members can add additional tags**: If you allow team members to add tags, turn this on to let team members add tags other than the suggested default tags that you set.</span></span> <span data-ttu-id="8ebf5-137">如果您關閉此功能，小組成員只能使用預設的標記。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-137">If this is turned off, team members can only use the default tags.</span></span>
    - <span data-ttu-id="8ebf5-138">**建議的預設**標籤：使用這個功能來新增一組預設的標籤。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-138">**Suggested default tags**: Use this to add a set of default tags.</span></span> <span data-ttu-id="8ebf5-139">您可以新增最多25個標籤，每個標籤最多可包含25個字元。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-139">You can add up to 25 tags, and each tag can contain a maximum of 25 characters.</span></span> <span data-ttu-id="8ebf5-140">小組擁有者和成員（如果已為他們啟用功能）可以使用這些建議、新增至他們，或建立一組新的標記。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-140">Team owners and members (if the feature is enabled for them) can use these suggestions, add to them, or create a new set of tags.</span></span>

## <a name="manage-tags-settings-for-a-team"></a><span data-ttu-id="8ebf5-141">管理團隊的標記設定</span><span class="sxs-lookup"><span data-stu-id="8ebf5-141">Manage tags settings for a team</span></span>

<span data-ttu-id="8ebf5-142">如果您開啟 [**小組擁有者可以覆寫**Microsoft 團隊系統管理中心中可以套用標籤] 設定的人員，小組擁有者可以設定成員是否可以在小組層級新增標記。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-142">If you turned on the **Team owner can override who can apply tags** setting in the Microsoft Teams admin center, team owners can set whether members can add tags at the team level.</span></span> <span data-ttu-id="8ebf5-143">若要這樣做，請在團隊的 [**設定**] 索引標籤上，移至 [標籤 **]，然後**選擇誰可以新增標記。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-143">To do this, on the **Settings** tab for a team, go to **Tags**, and then choose who can add tags.</span></span>

![小組層次上的 [標籤] 設定的螢幕擷取畫面](media/manage-tags-team-settings.png)

## <a name="add-tags-in-teams"></a><span data-ttu-id="8ebf5-145">在團隊中新增標記</span><span class="sxs-lookup"><span data-stu-id="8ebf5-145">Add tags in Teams</span></span>

<span data-ttu-id="8ebf5-146">在團隊中，小組的 [管理團隊] 頁面上的 [**成員**] 索引標籤包含 [**標記**] 欄。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-146">In Teams, the **Members** tab of the Manage team page for a team includes a **Tags** column.</span></span> <span data-ttu-id="8ebf5-147">小組擁有者和成員（如果已為他們啟用功能）可以按一下成員旁的 [**管理標記**]，即可查看該成員的建議標記清單，並將標記新增到清單中。</span><span class="sxs-lookup"><span data-stu-id="8ebf5-147">Team owners and members (if the feature is enabled for them) can click **Manage tags** next to a member to see the list of suggested tags for that member and add tags to the list.</span></span>

![<span data-ttu-id="8ebf5-148">如何在團隊用戶端套用標記的螢幕擷取畫面</span><span class="sxs-lookup"><span data-stu-id="8ebf5-148">Screenshot of how to apply tags in the Teams client</span></span> ](media/manage-tags-teams.png) 
