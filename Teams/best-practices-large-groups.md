---
title: 在 Microsoft 團隊中管理大型團隊-最佳做法
ms.reviewer: abgupta
author: lolaj
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 瞭解在 Microsoft 團隊中管理大型團隊以滿足貴組織的需求的最佳做法。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d939b4be4fcd5f3a1045f2f9adde750197b92f29
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638903"
---
<a name="manage-large-teams-in-microsoft-teams---best-practices"></a><span data-ttu-id="abb2e-103">在 Microsoft 團隊中管理大型團隊-最佳做法</span><span class="sxs-lookup"><span data-stu-id="abb2e-103">Manage large teams in Microsoft Teams - Best practices</span></span>
======================================================

<span data-ttu-id="abb2e-104">Microsoft 團隊也相當高效，可促進含數十個成員的小型群組之間的通訊，以及含上千個成員的大型群組。</span><span class="sxs-lookup"><span data-stu-id="abb2e-104">Microsoft Teams is equally effective at facilitating communications between small groups with dozens of members and large groups with thousands of members.</span></span> <span data-ttu-id="abb2e-105">針對小組規模的更新[，查看小組的限制與規格](limits-specifications-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="abb2e-105">Review [Limits and specifications for Teams](limits-specifications-teams.md) for updates on team sizes.</span></span> <span data-ttu-id="abb2e-106">團隊規模增加會帶來獨特的管理與操作難題。</span><span class="sxs-lookup"><span data-stu-id="abb2e-106">Increase in team size leads to unique management and operational challenges.</span></span> <span data-ttu-id="abb2e-107">本文將說明建立及管理數千個成員組成的大型小組的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="abb2e-107">This article describes best practices for creating and managing large teams comprised of thousands of members.</span></span>

## <a name="value-of-large-teams"></a><span data-ttu-id="abb2e-108">大型團隊的價值</span><span class="sxs-lookup"><span data-stu-id="abb2e-108">Value of large teams</span></span>

<span data-ttu-id="abb2e-109">大型團隊在啟用下列共同作業案例時非常有用：</span><span class="sxs-lookup"><span data-stu-id="abb2e-109">Large teams are very useful in enabling the following collaboration scenarios:</span></span>

- <span data-ttu-id="abb2e-110">**整個部門共同**作業：如果您的組織有多個部門（例如財務、運營、R&D 等），則您可以建立單一小組，其中包含特定部門中的所有成員。</span><span class="sxs-lookup"><span data-stu-id="abb2e-110">**Department-wide collaboration**: If your organization has multiple departments such as Finance, Operations, R&D etc., then you can create a single team that includes all members in a specific department.</span></span> <span data-ttu-id="abb2e-111">現在，所有與部門相關的通訊都可以在這個小組中共用，這可協助成員進行立即接觸和參與。</span><span class="sxs-lookup"><span data-stu-id="abb2e-111">Now all communications relevant to a department can be shared in this team, which facilitates instant reach and engagement from members.</span></span>

- <span data-ttu-id="abb2e-112">**員工資源群組中**的共同作業：組織通常會有大量的人員，這些人屬於不同的部門或公司群組。</span><span class="sxs-lookup"><span data-stu-id="abb2e-112">**Collaboration in employee resource groups**: Organizations often have large groups of people with mutual interests who belong to a different department or work group.</span></span> <span data-ttu-id="abb2e-113">舉例來說，您可以有一群人分享個人財務及投資的熱情。</span><span class="sxs-lookup"><span data-stu-id="abb2e-113">As an example, there can be a group of people who share a passion for personal finance and investing.</span></span> <span data-ttu-id="abb2e-114">在大型組織中，通常很難連接。</span><span class="sxs-lookup"><span data-stu-id="abb2e-114">It's often hard to connect in a large organization.</span></span> <span data-ttu-id="abb2e-115">若要為這類群組開發社區，租使用者管理員可以建立大型小組，以成為任何人都可以加入並利用的公用公司範圍資源群組。</span><span class="sxs-lookup"><span data-stu-id="abb2e-115">To develop communities for such groups, tenant admins can create a large team that serves as a public company-wide resource group that anyone can join and take advantage of.</span></span> <span data-ttu-id="abb2e-116">最終，這些社區會收集新的和現有成員都可以欣賞的資訊。</span><span class="sxs-lookup"><span data-stu-id="abb2e-116">Eventually, these communities collect information that both new and existing members can enjoy.</span></span>

- <span data-ttu-id="abb2e-117">**內部與外部成員之間**的共同作業：常見的產品通常會開發一個早期開發人員群組，讓他們積極嘗試新版產品發行並提供意見反應。</span><span class="sxs-lookup"><span data-stu-id="abb2e-117">**Collaboration between internal and external members**: Popular products often develop a community of early adopters who are eager to try new product releases and provide feedback.</span></span> <span data-ttu-id="abb2e-118">早期的使用方式開發與產品群組的關聯，以協助形成產品。</span><span class="sxs-lookup"><span data-stu-id="abb2e-118">Early adopters develop a relationship with product groups to help shape the product.</span></span> <span data-ttu-id="abb2e-119">在這種情況下，租使用者管理員可以設定大型小組，其中包含內部產品群組和外部產品評估程式，以協助豐富的產品開發流程。</span><span class="sxs-lookup"><span data-stu-id="abb2e-119">In such scenarios, tenant admins can set up a large team which includes both internal product groups and external product evaluators to facilitate a rich product development process.</span></span> <span data-ttu-id="abb2e-120">這些團隊也可以為一組選取的客戶提供客戶支援。</span><span class="sxs-lookup"><span data-stu-id="abb2e-120">These teams can also provide customer support to a select set of customers.</span></span>

## <a name="create-teams-from-existing-groups"></a><span data-ttu-id="abb2e-121">從現有的群組建立團隊</span><span class="sxs-lookup"><span data-stu-id="abb2e-121">Create teams from existing groups</span></span>

<span data-ttu-id="abb2e-122">使用連絡人群組、安全性群組或 Office 群組快速開始您的小組。</span><span class="sxs-lookup"><span data-stu-id="abb2e-122">Use contact groups, security groups, or Office groups to jump start your team.</span></span> <span data-ttu-id="abb2e-123">您可以匯入群組來製作小組，或從 Office 群組建立小組。</span><span class="sxs-lookup"><span data-stu-id="abb2e-123">You can import a group to make a team or create a team from an Office group.</span></span>

<span data-ttu-id="abb2e-124">匯**入群組以製作小組**：當您將含有最多3500成員的群組匯入小組時，小組會自動計算群組中的成員總數。</span><span class="sxs-lookup"><span data-stu-id="abb2e-124">**Import a group to make a team**: When you import a group with up to 3,500 members into Teams, Teams automatically calculates the total number of members in the group.</span></span> <span data-ttu-id="abb2e-125">這只是一次性的匯入作業，而且小組中的未來變更將不會自動更新。</span><span class="sxs-lookup"><span data-stu-id="abb2e-125">This is a one-time import only and future changes in the group will not automatically be updated in Teams.</span></span>

<span data-ttu-id="abb2e-126">**從大型 microsoft 365 群組建立小組**：當您從大型 microsoft 365 群組建立小組時，成員會自動成為 Microsoft 365 群組**和**小組的一部分。</span><span class="sxs-lookup"><span data-stu-id="abb2e-126">**Create a team from a large Microsoft 365 group**: When you create a team from a large Microsoft 365 group, members are automatically part of the Microsoft 365 group **and** the team.</span></span> <span data-ttu-id="abb2e-127">在將來，當小組成員加入或離開 Microsoft 365 群組時，系統會自動在小組中新增或移除他們。</span><span class="sxs-lookup"><span data-stu-id="abb2e-127">In the future, as team members join or leave the Microsoft 365 group, they're automatically added or removed from the team.</span></span>

## <a name="create-channels-to-focus-discussions"></a><span data-ttu-id="abb2e-128">建立頻道來聚焦討論</span><span class="sxs-lookup"><span data-stu-id="abb2e-128">Create channels to focus discussions</span></span>

<span data-ttu-id="abb2e-129">您可以建立焦點頻道，以縮小群組討論的範圍。</span><span class="sxs-lookup"><span data-stu-id="abb2e-129">You can narrow the group discussions by creating focused channels.</span></span> <span data-ttu-id="abb2e-130">請參閱[組織團隊的最佳做法](best-practices-organizing.md)。</span><span class="sxs-lookup"><span data-stu-id="abb2e-130">See [Best practices for organizing teams](best-practices-organizing.md).</span></span>

## <a name="restrict-channel-creation"></a><span data-ttu-id="abb2e-131">限制頻道建立</span><span class="sxs-lookup"><span data-stu-id="abb2e-131">Restrict channel creation</span></span>

<span data-ttu-id="abb2e-132">如果有任何小組成員允許建立頻道，該小組就可以進行頻道蔓延。</span><span class="sxs-lookup"><span data-stu-id="abb2e-132">If any team member is allowed to create channels, that team can have channel sprawl.</span></span> <span data-ttu-id="abb2e-133">小組擁有者應該針對 [**設定] > 成員許可權**中的成員關閉頻道建立、更新、刪除及還原。</span><span class="sxs-lookup"><span data-stu-id="abb2e-133">Team owners should turn off channel create, update, delete, and restore for members in **Settings > Member permissions**.</span></span> <span data-ttu-id="abb2e-134">請參閱[團隊和頻道的概覽](teams-channels-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="abb2e-134">See [Overview of teams and channels](teams-channels-overview.md).</span></span>

<span data-ttu-id="abb2e-135">![顯示 [管理員主控台設定] 索引標籤的 [成員許可權] 區段的螢幕圖像。](media/no-channel-creation.png "[管理員主控台設定] 索引標籤的 [成員許可權] 區段的螢幕圖像。[允許建立或刪除頻道的成員] 選項未核取。")</span><span class="sxs-lookup"><span data-stu-id="abb2e-135">![Screen image that shows the member permissions section of the admin console Settings tab.](media/no-channel-creation.png "Screen image that member permissions section of the admin console Settings tab. The allow members to create or delete channels options are unchecked.")</span></span>

## <a name="add-favorite-channels"></a><span data-ttu-id="abb2e-136">新增最愛頻道</span><span class="sxs-lookup"><span data-stu-id="abb2e-136">Add favorite channels</span></span>

<span data-ttu-id="abb2e-137">為了加速新的使用者參與與內容探索，您可以選取預設提供給使用者的最愛頻道。</span><span class="sxs-lookup"><span data-stu-id="abb2e-137">In order to speed up new user engagement and content discovery, you can select favorite channels that are available to the user by default.</span></span> <span data-ttu-id="abb2e-138">在系統管理中心的 [**頻道**] 窗格中，核取 [**成員顯示**] 欄下的頻道。</span><span class="sxs-lookup"><span data-stu-id="abb2e-138">In the **Channels** pane of the admin center, check the channels under the **Show for members** column.</span></span>

<span data-ttu-id="abb2e-139">![顯示系統管理主控台 [頻道] 窗格的螢幕圖像。](media/favorite-channels.png "顯示系統管理主控台 [頻道] 窗格的螢幕影像。已核取 [針對成員顯示] 的一些頻道。")</span><span class="sxs-lookup"><span data-stu-id="abb2e-139">![Screen image that shows the channels pane of the admin console.](media/favorite-channels.png "Screen image that shows channels pane of the admin console. Some channels are checked for Show for members.")</span></span>

 <span data-ttu-id="abb2e-140">如需詳細資訊，請參閱[建立您的第一份團隊和頻道](get-started-with-teams-create-your-first-teams-and-channels.md)。</span><span class="sxs-lookup"><span data-stu-id="abb2e-140">See [Create your first teams and channels](get-started-with-teams-create-your-first-teams-and-channels.md) for details.</span></span>

## <a name="regulate-applications-and-bots-in-large-teams"></a><span data-ttu-id="abb2e-141">在大型團隊中調整應用程式和 bot</span><span class="sxs-lookup"><span data-stu-id="abb2e-141">Regulate applications and bots in large teams</span></span>

<span data-ttu-id="abb2e-142">為了避免加入干擾應用程式或 bot，小組擁有者可以停用、新增、移除及上傳小組成員的 app 與連接器。</span><span class="sxs-lookup"><span data-stu-id="abb2e-142">To prevent addition of distracting applications or bots, team owners can disable, add, remove, and upload apps and connectors for team members.</span></span> <span data-ttu-id="abb2e-143">在系統管理中心的 [設定] 底下的 [ **> 成員許可權**] 底下，取消核取允許成員新增 app 或連接器的三個選項。</span><span class="sxs-lookup"><span data-stu-id="abb2e-143">In the admin center under **Settings > Member permissions**, uncheck the three options that allow members to add apps or connectors.</span></span>

<span data-ttu-id="abb2e-144">![顯示 [設定] 窗格的 [成員許可權] 區段的螢幕圖像。](media/disable-bots-connectors.png "顯示 [設定] 窗格的 [成員許可權] 區段的螢幕圖像。[允許成員新增應用程式或連接器] 選項未核取。")</span><span class="sxs-lookup"><span data-stu-id="abb2e-144">![Screen image that shows the Member permissions section of the Settings pane.](media/disable-bots-connectors.png "Screen image that shows the Member permission section of the Settings pane. The options for allow members to add apps or connectors are unchecked.")</span></span>

<span data-ttu-id="abb2e-145">請參閱[app、bot、& 連接器](deploy-apps-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="abb2e-145">See [Apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md).</span></span>

## <a name="regulate-team-and-channel-mentions"></a><span data-ttu-id="abb2e-146">控制小組與頻道提及</span><span class="sxs-lookup"><span data-stu-id="abb2e-146">Regulate team and channel mentions</span></span>

<span data-ttu-id="abb2e-147">小組和頻道提及可用來繪製整個小組對特定頻道文章的注意。</span><span class="sxs-lookup"><span data-stu-id="abb2e-147">Team and channel mentions can be used to draw the attention of the whole team to certain channel posts.</span></span> <span data-ttu-id="abb2e-148">在文章中使用提及之後，就會傳送通知給數以千計的小組成員。</span><span class="sxs-lookup"><span data-stu-id="abb2e-148">Once a mention is used in a post, a notification is sent to thousands of team members.</span></span> <span data-ttu-id="abb2e-149">如果通知太頻繁，小組成員可能會遭到超載，而且可能會抱怨小組擁有者。</span><span class="sxs-lookup"><span data-stu-id="abb2e-149">If the notifications are too frequent, then team members can become overloaded and might complain to team owners.</span></span> <span data-ttu-id="abb2e-150">若要避免小組或頻道提及，請取消核取 [團隊**設定] > @mentions**窗格中的方塊，以關閉成員的小組和頻道提及。</span><span class="sxs-lookup"><span data-stu-id="abb2e-150">To prevent team or channel mentions, turn off team and channel mentions for members by unchecking the boxes in the teams **Settings > @mentions** pane.</span></span>

<span data-ttu-id="abb2e-151">![顯示 [設定] 窗格中 [時間提及] 區段的螢幕圖像。](media/no-at-mentions.png "顯示 [設定] 窗格中 [時間提及] 區段的螢幕圖像。未核取 [顯示] 和 [賦予成員對提及的存取權] 的選項。")</span><span class="sxs-lookup"><span data-stu-id="abb2e-151">![Screen image that shows the at Mentions section of the Settings pane.](media/no-at-mentions.png "Screen image that shows the at Mentions section of the Settings pane. The options for show and give members access to at mentions are unchecked.")</span></span>

## <a name="consider-setting-up-moderation-in-your-channels"></a><span data-ttu-id="abb2e-152">請考量在您的頻道中設定仲裁</span><span class="sxs-lookup"><span data-stu-id="abb2e-152">Consider setting up moderation in your channels</span></span>

<span data-ttu-id="abb2e-153">小組擁有者可以針對頻道開啟仲裁，以控制誰可以開始新的文章，以及回覆該頻道中的文章。</span><span class="sxs-lookup"><span data-stu-id="abb2e-153">Team owners can turn on moderation for a channel to control who can start new posts and reply to posts in that channel.</span></span> <span data-ttu-id="abb2e-154">當您設定仲裁時，您可以選擇讓一或多個小組成員成為仲裁者。</span><span class="sxs-lookup"><span data-stu-id="abb2e-154">When you set up moderation, you can choose one or more team members to be moderators.</span></span> <span data-ttu-id="abb2e-155">小組擁有者預設為版主。</span><span class="sxs-lookup"><span data-stu-id="abb2e-155">Team owners are moderators by default.</span></span> <span data-ttu-id="abb2e-156">如需詳細資訊，請參閱[設定及管理通道裁決](manage-channel-moderation-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="abb2e-156">For more information, see [Set up and manage channel moderation](manage-channel-moderation-in-teams.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="abb2e-157">相關主題</span><span class="sxs-lookup"><span data-stu-id="abb2e-157">Related topics</span></span>

- [<span data-ttu-id="abb2e-158">組織團隊的最佳做法</span><span class="sxs-lookup"><span data-stu-id="abb2e-158">Best practices for organizing Teams</span></span>](best-practices-organizing.md)
- [<span data-ttu-id="abb2e-159">建立組織範圍的小組</span><span class="sxs-lookup"><span data-stu-id="abb2e-159">Create an org-wide team</span></span>](create-an-org-wide-team.md)
