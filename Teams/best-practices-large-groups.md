---
title: 管理大型團隊Microsoft Teams - 最佳做法
ms.reviewer: abgupta
author: lolaj
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 瞭解管理大型團隊的最佳作法Microsoft Teams以符合貴組織的需求。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fff84bd660eb19f01c6a7e3388f5289b09896401
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856342"
---
# <a name="manage-large-teams-in-microsoft-teams---best-practices"></a><span data-ttu-id="22313-103">管理大型團隊Microsoft Teams - 最佳做法</span><span class="sxs-lookup"><span data-stu-id="22313-103">Manage large teams in Microsoft Teams - Best practices</span></span>

<span data-ttu-id="22313-104">Microsoft Teams能促進與數十個成員和數千個成員的大型群組之間的溝通。</span><span class="sxs-lookup"><span data-stu-id="22313-104">Microsoft Teams is equally effective at facilitating communications between small groups with dozens of members and large groups with thousands of members.</span></span> <span data-ttu-id="22313-105">針對[小組大小更新Teams](limits-specifications-teams.md)限制和規格。</span><span class="sxs-lookup"><span data-stu-id="22313-105">Review [Limits and specifications for Teams](limits-specifications-teams.md) for updates on team sizes.</span></span> <span data-ttu-id="22313-106">團隊規模增加會導致獨特的管理和營運挑戰。</span><span class="sxs-lookup"><span data-stu-id="22313-106">Increase in team size leads to unique management and operational challenges.</span></span> <span data-ttu-id="22313-107">本文將說明建立及管理由數千個成員組成的大型團隊的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="22313-107">This article describes best practices for creating and managing large teams comprised of thousands of members.</span></span>

## <a name="value-of-large-teams"></a><span data-ttu-id="22313-108">大型團隊的價值</span><span class="sxs-lookup"><span data-stu-id="22313-108">Value of large teams</span></span>

<span data-ttu-id="22313-109">大型團隊在啟用下列共同合作案例時非常實用：</span><span class="sxs-lookup"><span data-stu-id="22313-109">Large teams are very useful in enabling the following collaboration scenarios:</span></span>

- <span data-ttu-id="22313-110">**全部門** 共同作業：如果貴組織有多個部門 ，例如財務、營運、R&D 等，則您可以建立一個包含特定部門中所有成員的小組。</span><span class="sxs-lookup"><span data-stu-id="22313-110">**Department-wide collaboration**: If your organization has multiple departments such as Finance, Operations, R&D etc., then you can create a single team that includes all members in a specific department.</span></span> <span data-ttu-id="22313-111">現在，所有與部門相關的通訊都可以在這個小組中共用，方便成員立即聯繫和互動。</span><span class="sxs-lookup"><span data-stu-id="22313-111">Now all communications relevant to a department can be shared in this team, which facilitates instant reach and engagement from members.</span></span>

- <span data-ttu-id="22313-112">**員工資源群組中的共同** 作業：組織通常有一大群具有共同興趣的人，他們屬於不同的部門或工作組。</span><span class="sxs-lookup"><span data-stu-id="22313-112">**Collaboration in employee resource groups**: Organizations often have large groups of people with mutual interests who belong to a different department or work group.</span></span> <span data-ttu-id="22313-113">舉個例說，可以有一群對個人財務與投資充滿熱忱的人。</span><span class="sxs-lookup"><span data-stu-id="22313-113">As an example, there can be a group of people who share a passion for personal finance and investing.</span></span> <span data-ttu-id="22313-114">在大型組織中通常難以聯繫。</span><span class="sxs-lookup"><span data-stu-id="22313-114">It's often hard to connect in a large organization.</span></span> <span data-ttu-id="22313-115">若要為這類群組開發社群，租使用者系統管理員可以建立大型團隊，做為全公司的公用資源群組，任何人都可以加入並利用。</span><span class="sxs-lookup"><span data-stu-id="22313-115">To develop communities for such groups, tenant admins can create a large team that serves as a public company-wide resource group that anyone can join and take advantage of.</span></span> <span data-ttu-id="22313-116">最後，這些社群會收集新成員和現有成員都可以享有的資訊。</span><span class="sxs-lookup"><span data-stu-id="22313-116">Eventually, these communities collect information that both new and existing members can enjoy.</span></span>

- <span data-ttu-id="22313-117">**內部和外部成員** 之間的共同合作：熱門產品通常會開發一個早期採用者社群，他們急迫嘗試新產品發行，並提供意見回饋。</span><span class="sxs-lookup"><span data-stu-id="22313-117">**Collaboration between internal and external members**: Popular products often develop a community of early adopters who are eager to try new product releases and provide feedback.</span></span> <span data-ttu-id="22313-118">早期採用者會與產品群組建立關係，協助塑造產品。</span><span class="sxs-lookup"><span data-stu-id="22313-118">Early adopters develop a relationship with product groups to help shape the product.</span></span> <span data-ttu-id="22313-119">在這種情況下，租使用者系統管理員可以設定包含內部產品群組和外部產品評估員的大型小組，以協助豐富的產品開發程式。</span><span class="sxs-lookup"><span data-stu-id="22313-119">In such scenarios, tenant admins can set up a large team which includes both internal product groups and external product evaluators to facilitate a rich product development process.</span></span> <span data-ttu-id="22313-120">這些團隊也可以為一組選取的客戶提供客戶支援。</span><span class="sxs-lookup"><span data-stu-id="22313-120">These teams can also provide customer support to a select set of customers.</span></span>

## <a name="create-teams-from-existing-groups"></a><span data-ttu-id="22313-121">從現有的群組建立團隊</span><span class="sxs-lookup"><span data-stu-id="22313-121">Create teams from existing groups</span></span>

<span data-ttu-id="22313-122">使用連絡人群組、安全性群組或Office群組來快速啟動您的小組。</span><span class="sxs-lookup"><span data-stu-id="22313-122">Use contact groups, security groups, or Office groups to jump start your team.</span></span> <span data-ttu-id="22313-123">您可以輸入群組來建立團隊，或從群組建立Office團隊。</span><span class="sxs-lookup"><span data-stu-id="22313-123">You can import a group to make a team or create a team from an Office group.</span></span>

<span data-ttu-id="22313-124">將 **群組** 輸入成團隊：當您將最多 3，500 個成員的群組Teams，Teams會自動計算群組中的成員總數。</span><span class="sxs-lookup"><span data-stu-id="22313-124">**Import a group to make a team**: When you import a group with up to 3,500 members into Teams, Teams automatically calculates the total number of members in the group.</span></span> <span data-ttu-id="22313-125">這是一次導入，群組中未來的變更將不會在 Teams。</span><span class="sxs-lookup"><span data-stu-id="22313-125">This is a one-time import only and future changes in the group will not automatically be updated in Teams.</span></span>

<span data-ttu-id="22313-126">**從大型群組建立** Microsoft 365：當您從大型群組Microsoft 365團隊時，成員會自動成為群組 **Microsoft 365團隊的** 一部分。</span><span class="sxs-lookup"><span data-stu-id="22313-126">**Create a team from a large Microsoft 365 group**: When you create a team from a large Microsoft 365 group, members are automatically part of the Microsoft 365 group **and** the team.</span></span> <span data-ttu-id="22313-127">日後，當小組成員加入或離開Microsoft 365群組時，系統會自動新增或移除他們。</span><span class="sxs-lookup"><span data-stu-id="22313-127">In the future, as team members join or leave the Microsoft 365 group, they're automatically added or removed from the team.</span></span>

## <a name="bulk-importexportremove-members-in-a-team"></a><span data-ttu-id="22313-128">大量匯出/匯出/移除團隊中的成員</span><span class="sxs-lookup"><span data-stu-id="22313-128">Bulk import/export/remove members in a team</span></span>

<span data-ttu-id="22313-129">Azure 入口網站允許使用者大量匯出/匯出/移除群組Microsoft 365成員。</span><span class="sxs-lookup"><span data-stu-id="22313-129">The Azure portal allows users to bulk import/export/remove members in a Microsoft 365 Group.</span></span> <span data-ttu-id="22313-130">詳細資訊，請參閱 [大量導入群組成員](/azure/active-directory/enterprise-users/groups-bulk-import-members#to-bulk-import-group-members)。</span><span class="sxs-lookup"><span data-stu-id="22313-130">For more information, see [To bulk import group members](/azure/active-directory/enterprise-users/groups-bulk-import-members#to-bulk-import-group-members).</span></span>

<span data-ttu-id="22313-131">由於每個團隊都有一個Microsoft 365，您可以使用 Azure 入口網站，在對應該團隊的群組中執行這些作業。</span><span class="sxs-lookup"><span data-stu-id="22313-131">Since every team is backed by a Microsoft 365 Group, you can use the Azure portal to perform these operations in the group corresponding to the team.</span></span> <span data-ttu-id="22313-132">成員作業將在 24 小時內反映在團隊中。</span><span class="sxs-lookup"><span data-stu-id="22313-132">The member operations will be reflected in the team within 24 hours.</span></span>

## <a name="create-channels-to-focus-discussions"></a><span data-ttu-id="22313-133">建立頻道來聚焦討論</span><span class="sxs-lookup"><span data-stu-id="22313-133">Create channels to focus discussions</span></span>

<span data-ttu-id="22313-134">您可以建立焦點頻道來縮小群組討論範圍。</span><span class="sxs-lookup"><span data-stu-id="22313-134">You can narrow the group discussions by creating focused channels.</span></span> <span data-ttu-id="22313-135">請參閱 [組織團隊的最佳作法](best-practices-organizing.md)。</span><span class="sxs-lookup"><span data-stu-id="22313-135">See [Best practices for organizing teams](best-practices-organizing.md).</span></span>

## <a name="restrict-channel-creation"></a><span data-ttu-id="22313-136">限制頻道建立</span><span class="sxs-lookup"><span data-stu-id="22313-136">Restrict channel creation</span></span>

<span data-ttu-id="22313-137">如果允許任何團隊成員建立頻道，該團隊可以擴大頻道。</span><span class="sxs-lookup"><span data-stu-id="22313-137">If any team member is allowed to create channels, that team can have channel sprawl.</span></span> <span data-ttu-id="22313-138">團隊擁有者應在成員許可權中關閉成員頻道的建立、更新、刪除 **設定 >還原**。</span><span class="sxs-lookup"><span data-stu-id="22313-138">Team owners should turn off channel create, update, delete, and restore for members in **Settings > Member permissions**.</span></span> <span data-ttu-id="22313-139">請參閱 [團隊和頻道概觀](teams-channels-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="22313-139">See [Overview of teams and channels](teams-channels-overview.md).</span></span>

<span data-ttu-id="22313-140">![顯示系統管理主控台中成員許可權區段的螢幕設定畫面。](media/no-channel-creation.png "系統管理主控台中成員許可權區段的螢幕設定畫面。未取消勾選允許成員建立或刪除頻道選項。")</span><span class="sxs-lookup"><span data-stu-id="22313-140">![Screen image that shows the member permissions section of the admin console Settings tab.](media/no-channel-creation.png "Screen image that member permissions section of the admin console Settings tab. The allow members to create or delete channels options are unchecked.")</span></span>

## <a name="add-favorite-channels"></a><span data-ttu-id="22313-141">新增我的最愛頻道</span><span class="sxs-lookup"><span data-stu-id="22313-141">Add favorite channels</span></span>

<span data-ttu-id="22313-142">若要加快新的使用者互動和內容探索，您可以選取使用者預設可用的最愛頻道。</span><span class="sxs-lookup"><span data-stu-id="22313-142">In order to speed up new user engagement and content discovery, you can select favorite channels that are available to the user by default.</span></span> <span data-ttu-id="22313-143">在 **系統管理中心的** 頻道窗格中，檢查顯示成員欄下的 **頻道** 。</span><span class="sxs-lookup"><span data-stu-id="22313-143">In the **Channels** pane of the admin center, check the channels under the **Show for members** column.</span></span>

<span data-ttu-id="22313-144">![顯示系統管理主控台的頻道窗格的螢幕圖像。](media/favorite-channels.png "顯示系統管理主控台的頻道窗格的螢幕圖像。某些頻道會檢查為成員顯示。")</span><span class="sxs-lookup"><span data-stu-id="22313-144">![Screen image that shows the channels pane of the admin console.](media/favorite-channels.png "Screen image that shows channels pane of the admin console. Some channels are checked for Show for members.")</span></span>

 <span data-ttu-id="22313-145">請參閱 [建立您的第一個團隊和頻道以](get-started-with-teams-create-your-first-teams-and-channels.md) 瞭解詳細資料。</span><span class="sxs-lookup"><span data-stu-id="22313-145">See [Create your first teams and channels](get-started-with-teams-create-your-first-teams-and-channels.md) for details.</span></span>

## <a name="regulate-applications-and-bots-in-large-teams"></a><span data-ttu-id="22313-146">在大型團隊中規範應用程式和 Bot</span><span class="sxs-lookup"><span data-stu-id="22313-146">Regulate applications and bots in large teams</span></span>

<span data-ttu-id="22313-147">為了防止新增令人分心的應用程式或 Bot，團隊擁有者可以針對小組成員停用、新增、移除及上傳應用程式和連接器。</span><span class="sxs-lookup"><span data-stu-id="22313-147">To prevent addition of distracting applications or bots, team owners can disable, add, remove, and upload apps and connectors for team members.</span></span> <span data-ttu-id="22313-148">在系統管理 **中心設定 >**，取消勾選允許成員新增 App 或連接器的三個選項。</span><span class="sxs-lookup"><span data-stu-id="22313-148">In the admin center under **Settings > Member permissions**, uncheck the three options that allow members to add apps or connectors.</span></span>

<span data-ttu-id="22313-149">![顯示窗格之成員許可權區段的設定圖像。](media/disable-bots-connectors.png "顯示窗格之成員許可權區段的設定圖像。允許成員新增 App 或連接器的選項會取消勾選。")</span><span class="sxs-lookup"><span data-stu-id="22313-149">![Screen image that shows the Member permissions section of the Settings pane.](media/disable-bots-connectors.png "Screen image that shows the Member permission section of the Settings pane. The options for allow members to add apps or connectors are unchecked.")</span></span>

<span data-ttu-id="22313-150">請參閱 [應用程式、bot、&連接器](deploy-apps-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="22313-150">See [Apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md).</span></span>

## <a name="regulate-team-and-channel-mentions"></a><span data-ttu-id="22313-151">規範團隊和頻道提及</span><span class="sxs-lookup"><span data-stu-id="22313-151">Regulate team and channel mentions</span></span>

<span data-ttu-id="22313-152">小組和頻道提及可以用來吸引整個團隊對特定頻道文章的注意。</span><span class="sxs-lookup"><span data-stu-id="22313-152">Team and channel mentions can be used to draw the attention of the whole team to certain channel posts.</span></span> <span data-ttu-id="22313-153">在文章使用提及後，通知會發送給數千名小組成員。</span><span class="sxs-lookup"><span data-stu-id="22313-153">Once a mention is used in a post, a notification is sent to thousands of team members.</span></span> <span data-ttu-id="22313-154">如果通知過於頻繁，則小組成員可能會超載，並可能會向團隊擁有者抱怨。</span><span class="sxs-lookup"><span data-stu-id="22313-154">If the notifications are too frequent, then team members can become overloaded and might complain to team owners.</span></span> <span data-ttu-id="22313-155">若要避免團隊或頻道提及，請取消勾選團隊或頻道窗格中的 **設定 > @mentions提及。**</span><span class="sxs-lookup"><span data-stu-id="22313-155">To prevent team or channel mentions, turn off team and channel mentions for members by unchecking the boxes in the teams **Settings > @mentions** pane.</span></span>

<span data-ttu-id="22313-156">![Screen image that shows the at Mentions section of the Settings pane.](media/no-at-mentions.png "顯示窗格的 <提及> 區段的設定圖像。未勾選顯示和給予成員提及存取權的選項。")</span><span class="sxs-lookup"><span data-stu-id="22313-156">![Screen image that shows the at Mentions section of the Settings pane.](media/no-at-mentions.png "Screen image that shows the at Mentions section of the Settings pane. The options for show and give members access to at mentions are unchecked.")</span></span>

## <a name="consider-setting-up-moderation-in-your-channels"></a><span data-ttu-id="22313-157">請考量在您的頻道中設定仲裁</span><span class="sxs-lookup"><span data-stu-id="22313-157">Consider setting up moderation in your channels</span></span>

<span data-ttu-id="22313-158">小組擁有者可以針對頻道開啟仲裁，以控制誰可以開始新的文章，以及回覆該頻道中的文章。</span><span class="sxs-lookup"><span data-stu-id="22313-158">Team owners can turn on moderation for a channel to control who can start new posts and reply to posts in that channel.</span></span> <span data-ttu-id="22313-159">當您設定仲裁時，您可以選擇讓一或多個小組成員成為仲裁者。</span><span class="sxs-lookup"><span data-stu-id="22313-159">When you set up moderation, you can choose one or more team members to be moderators.</span></span> <span data-ttu-id="22313-160">團隊擁有者預設為仲裁者。</span><span class="sxs-lookup"><span data-stu-id="22313-160">Team owners are moderators by default.</span></span> <span data-ttu-id="22313-161">詳細資訊，請參閱[設定及管理通道管理。](manage-channel-moderation-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="22313-161">For more information, see [Set up and manage channel moderation](manage-channel-moderation-in-teams.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="22313-162">相關主題</span><span class="sxs-lookup"><span data-stu-id="22313-162">Related topics</span></span>

- [<span data-ttu-id="22313-163">組織活動的最佳Teams</span><span class="sxs-lookup"><span data-stu-id="22313-163">Best practices for organizing Teams</span></span>](best-practices-organizing.md)
- [<span data-ttu-id="22313-164">建立全組織團隊</span><span class="sxs-lookup"><span data-stu-id="22313-164">Create an org-wide team</span></span>](create-an-org-wide-team.md)