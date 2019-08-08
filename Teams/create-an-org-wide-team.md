---
title: 在 Microsoft 團隊中建立組織範圍的小組
author: LanaChin
ms.author: v-lanac
ms.reviewer: phlouie
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何在團隊中建立和管理組織範圍的團隊。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 881996d5f8acbc7458a775e02adfad9b38a231a9
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241232"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a><span data-ttu-id="fc7b8-103">在 Microsoft 團隊中建立組織範圍的小組</span><span class="sxs-lookup"><span data-stu-id="fc7b8-103">Create an org-wide team in Microsoft Teams</span></span>

<span data-ttu-id="fc7b8-104">組織範圍的小組為一個中小型組織中的每個人提供自動方法, 讓他們成為單一小組共同作業的一部分。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-104">Org-wide teams provide an automatic way for everyone in a small to medium-sized organization to be a part of a single team for collaboration.</span></span>

<span data-ttu-id="fc7b8-105">有了組織範圍的小組, 全域管理員就能輕鬆地建立一份公開小組, 在組織中的每位使用者都能拉入, 並在使用者加入並離開組織時, 將成員資格保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-105">With org-wide teams, global admins can easily create a public team that pulls in every user in the organization and keeps the membership up to date with Active Directory as users join and leave the organization.</span></span> <span data-ttu-id="fc7b8-106">只有全域管理員才能建立整個組織的團隊, 而且目前組織範圍的小組僅限於5000使用者以外的組織。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-106">Only global admins can create org-wide teams and currently an org-wide team is limited to organizations with no more than 5,000 users.</span></span> <span data-ttu-id="fc7b8-107">此外, 每個租使用者最多隻能有五個組織範圍的團隊。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-107">There's also a limit of five org-wide teams per tenant.</span></span> <span data-ttu-id="fc7b8-108">如果符合這些需求, 全域系統管理員會在建立小組時, 看到**組織外**的選項, 讓他們選取 [**從頭開始建立小組**]。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-108">If these requirements are met, global admins will see **Org-wide** as an option when they select **Build a team from scratch** when creating a team.</span></span> 

<span data-ttu-id="fc7b8-109">![[組織範圍] 選項的螢幕擷取畫面, 可用於建立整個組織的小組](media/create-org-wide-team.png "[組織範圍] 選項的螢幕擷取畫面, 可用於建立整個組織的小組")</span><span class="sxs-lookup"><span data-stu-id="fc7b8-109">![Screen shot of the Org-wide option to create an org-wide team](media/create-org-wide-team.png "Screen shot of the Org-wide option to create an org-wide team")</span></span>

<span data-ttu-id="fc7b8-110">建立組織範圍的小組後, 所有全域管理員都會新增為團隊擁有者, 而所有作用中的使用者都會新增為小組成員。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-110">When an org-wide team is created, all global admins are added as team owners and all active users are added as team members.</span></span> <span data-ttu-id="fc7b8-111">未授權的使用者也會新增至小組。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-111">Unlicensed users are also added to the team.</span></span> <span data-ttu-id="fc7b8-112">未授權的使用者第一次登入小組時, 系統會為該使用者指派 Microsoft 團隊商業雲端試用版授權。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-112">The first time an unlicensed user signs in to Teams, the user is assigned a Microsoft Teams Commercial Cloud Trial license.</span></span> <span data-ttu-id="fc7b8-113">若要深入瞭解試用版授權, 請參閱[管理團隊商業雲端試用版優惠](iw-trial-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-113">To learn more about the trial license, check out [Manage the Teams Commercial Cloud Trial offer](iw-trial-teams.md).</span></span> 

<span data-ttu-id="fc7b8-114">這些類型的帳戶不會新增至您的組織內小組:</span><span class="sxs-lookup"><span data-stu-id="fc7b8-114">These types of accounts won't be added to your org-wide team:</span></span>

- <span data-ttu-id="fc7b8-115">已封鎖登入的帳戶</span><span class="sxs-lookup"><span data-stu-id="fc7b8-115">Accounts that are blocked from sign in</span></span>
- <span data-ttu-id="fc7b8-116">來賓使用者</span><span class="sxs-lookup"><span data-stu-id="fc7b8-116">Guest users</span></span>
- <span data-ttu-id="fc7b8-117">服務帳戶</span><span class="sxs-lookup"><span data-stu-id="fc7b8-117">Service accounts</span></span>
- <span data-ttu-id="fc7b8-118">會議室或設備帳戶</span><span class="sxs-lookup"><span data-stu-id="fc7b8-118">Room or equipment accounts</span></span>
- <span data-ttu-id="fc7b8-119">受共用信箱支援的帳戶</span><span class="sxs-lookup"><span data-stu-id="fc7b8-119">Accounts backed by a shared mailbox</span></span>

<span data-ttu-id="fc7b8-120">隨著貴組織的目錄已更新, 以包含新的作用中使用者, 或者如果使用者不在貴公司且其小組授權已停用, 變更會自動同步處理, 並在團隊中新增或移除使用者。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-120">As your organization's directory is updated to include new active users or if users no longer work at your company and their Teams license is disabled, changes are automatically synced and the users are added or removed from the team.</span></span> <span data-ttu-id="fc7b8-121">小組成員無法離開組織範圍的小組。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-121">Team members can't leave an org-wide team.</span></span> <span data-ttu-id="fc7b8-122">在小組擁有者中, 您可以視需要手動新增或移除使用者。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-122">As a team owner, you can manually add or remove users if needed.</span></span>

> [!NOTE]
> - <span data-ttu-id="fc7b8-123">如果您在建立小組時沒有看到**組織範圍**選項, 且您是全域系統管理員, 則該功能可能仍在推出, 或貴組織可能超出5000成員的目前大小限制。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-123">If you don't see the **Org-wide** option when creating a team and you're a global admin, the feature might still be rolling out or your organization might have more than the current size limit of 5,000 members.</span></span> <span data-ttu-id="fc7b8-124">我們正在想要在未來增加此限制。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-124">We're looking to increase this limit in the future.</span></span>
> - <span data-ttu-id="fc7b8-125">不屬於會議室清單、裝置和資源帳戶的會議室, 可能會新增或同步處理到整個組織的小組。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-125">Rooms that aren't a part of a room list, equipment, and resource accounts might be added or synced to the org-wide team.</span></span> <span data-ttu-id="fc7b8-126">小組擁有者可以輕鬆地將這些帳戶從小組中移除。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-126">Team owners can easily remove these accounts from the team.</span></span>

## <a name="best-practices"></a><span data-ttu-id="fc7b8-127">最佳做法</span><span class="sxs-lookup"><span data-stu-id="fc7b8-127">Best practices</span></span>

<span data-ttu-id="fc7b8-128">若要充分發揮整個組織的小組, 我們建議小組擁有者執行下列操作。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-128">To get the most out of your org-wide team, we recommend team owners do the following.</span></span>

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a><span data-ttu-id="fc7b8-129">僅允許團隊擁有者張貼至 [一般] 頻道</span><span class="sxs-lookup"><span data-stu-id="fc7b8-129">Allow only team owners to post to the General channel</span></span>

<span data-ttu-id="fc7b8-130">只要將小組擁有者張貼到 [一般] 頻道, 即可減少通道噪音。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-130">Reduce channel noise by having only team owners post to the General channel.</span></span> <span data-ttu-id="fc7b8-131">移至團隊, 然後按一下 [ **̇̇̇其他選項** > [**管理團隊**]。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-131">Go to the team and click **˙˙˙ More options** > **Manage Team**.</span></span> <span data-ttu-id="fc7b8-132">按一下 [**設定**] 索引標籤上的 [**成員許可權**] > 選取 [**只有擁有者可以張貼郵件**]。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-132">On the **Settings** tab, click **Member permissions** > select **Only owners can post messages**.</span></span>

### <a name="turn-off-team-and-team-name-mentions"></a><span data-ttu-id="fc7b8-133">關閉 @team 和 @ [團隊名稱] 提及</span><span class="sxs-lookup"><span data-stu-id="fc7b8-133">Turn off @team and @[team name] mentions</span></span>

 <span data-ttu-id="fc7b8-134">減少 @mentions 讓他們避免整個組織超載。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-134">Reduce @mentions to keep them from overloading the entire organization.</span></span> <span data-ttu-id="fc7b8-135">移至團隊, 然後按一下 [ **̇̇̇其他選項** > [**管理團隊**]。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-135">Go to the team and click **˙˙˙ More options** > **Manage Team**.</span></span> <span data-ttu-id="fc7b8-136">按一下 [**設定**] 索引標籤上的 [ <strong>@mentions</strong> ] > 關閉 **[顯示成員] 選項以 @team 或 @ [團隊名稱]]**。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-136">On the **Settings** tab, click <strong>@mentions</strong> > turn off **Show members the option to @team or @[team name]**.</span></span> 

### <a name="automatically-favorite-important-channels"></a><span data-ttu-id="fc7b8-137">自動將重要頻道設為最愛</span><span class="sxs-lookup"><span data-stu-id="fc7b8-137">Automatically favorite important channels</span></span>

<span data-ttu-id="fc7b8-138">我最愛的重要頻道, 以確保貴組織中的每個人都參與特定交談。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-138">Favorite important channels to ensure everyone in your organization engages in specific conversations.</span></span> <span data-ttu-id="fc7b8-139">若要深入瞭解, 請參閱[適用于整個團隊的自動最愛頻道](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6)。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-139">To learn more, see [Auto-favorite channels for the whole team](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6).</span></span>

### <a name="set-up-channel-moderation"></a><span data-ttu-id="fc7b8-140">設定頻道裁決</span><span class="sxs-lookup"><span data-stu-id="fc7b8-140">Set up channel moderation</span></span>

<span data-ttu-id="fc7b8-141">考慮設定頻道裁決, 並向特定小組成員提供仲裁者的功能。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-141">Consider setting up channel moderation and giving moderator capabilities to certain team members.</span></span> <span data-ttu-id="fc7b8-142">(設定裁決後, 系統會自動為團隊擁有者提供仲裁者的功能。)版主可以控制誰可以在頻道中開始新文章、新增及移除版主、控制小組成員是否可以回復現有的頻道訊息, 以及控制機器人與連接器是否可以提交頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-142">(When moderation is set up, team owners are given moderator capabilities automatically.) Moderators can control who can start a new post in a channel, add and remove moderators, control whether team members can reply to existing channel messages, and control whether bots and connectors can submit channel messages.</span></span> <span data-ttu-id="fc7b8-143">如需詳細資訊, 請參閱[在 Microsoft 團隊中設定和管理 [頻道裁決](manage-channel-moderation-in-teams.md)]。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-143">For more information, see [Set up and manage channel moderation in Microsoft Teams](manage-channel-moderation-in-teams.md).</span></span>

### <a name="remove-accounts-that-might-not-belong"></a><span data-ttu-id="fc7b8-144">移除可能不屬於的帳戶</span><span class="sxs-lookup"><span data-stu-id="fc7b8-144">Remove accounts that might not belong</span></span>

<span data-ttu-id="fc7b8-145">即使成員不能離開組織內的小組 (作為小組擁有者), 您還是可以移除不屬於的帳戶來管理團隊名單。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-145">Even though members can’t leave an org-wide team, as a team owner, you can manage the team roster by removing accounts that don’t belong.</span></span> <span data-ttu-id="fc7b8-146">請確定您使用團隊從組織範圍的小組中移除使用者。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-146">Make sure you use Teams to remove users from your org-wide team.</span></span> <span data-ttu-id="fc7b8-147">如果您使用另一個方法來移除使用者 (例如 Microsoft 365 系統管理中心或 Outlook 中的群組), 使用者可能會新增回組織範圍的小組。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-147">If you use another way to remove a user, such as the Microsoft 365 admin center or from a group in Outlook, the user might be added back to the org-wide team.</span></span>

## <a name="faq"></a><span data-ttu-id="fc7b8-148">常見問題</span><span class="sxs-lookup"><span data-stu-id="fc7b8-148">FAQ</span></span>

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a><span data-ttu-id="fc7b8-149">是否有任何方式可以使用團隊用戶端來建立組織範圍以外的團隊？</span><span class="sxs-lookup"><span data-stu-id="fc7b8-149">Is there a way to create an org-wide team other than using the Teams client?</span></span>

<span data-ttu-id="fc7b8-150">全域管理員只能使用 [團隊用戶端] 來建立組織範圍的小組。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-150">Global admins can only create an org-wide team by using the Teams client.</span></span> <span data-ttu-id="fc7b8-151">如果您的組織限制建立團隊使用 PowerShell, 建議的解決方法是將您的全域管理員新增至可建立小組的使用者安全性群組。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-151">If your organization limits creating teams to using PowerShell, the recommended workaround is to add your global admins to the security group of users who can create a team.</span></span> <span data-ttu-id="fc7b8-152">如需詳細資訊, 請參閱[管理可建立 Office 365 群組的人員](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-152">For more information, see [Manage who can create Office 365 Groups](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups).</span></span>

<span data-ttu-id="fc7b8-153">如果這不是選項, 您可以使用 PowerShell 建立公開團隊, 並將全域管理員新增為團隊擁有者。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-153">If this isn't an option, you can use PowerShell to create a public team and add a global admin as the team owner.</span></span> <span data-ttu-id="fc7b8-154">接著, 讓全域管理員按一下團隊名稱旁的 [**更多選項**], 按一下 [**編輯團隊**], 然後將隱私權變更為 [**全組織性]-您組織中的所有人都會自動新增**。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-154">Then, have the global admin click **More options** next to the team name, click **Edit team**, and then change the privacy to **Org-wide - Everyone in your organization will be automatically added**.</span></span> <span data-ttu-id="fc7b8-155">請注意, 只有團隊擁有者可以存取 [**編輯團隊**] 選項, 而且只有全域管理員才能看到**整個組織**的選項。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-155">Note that only team owners can access the **Edit team** option and only global admins can see the **Org-wide** option.</span></span>

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-org-wide-team"></a><span data-ttu-id="fc7b8-156">是否有任何方式可將現有團隊轉換為組織範圍的團隊？</span><span class="sxs-lookup"><span data-stu-id="fc7b8-156">Is there a way to convert an existing team to an org-wide team?</span></span>

<span data-ttu-id="fc7b8-157">全域管理員可以在團隊用戶端中編輯現有的團隊, 將其轉換為組織範圍的團隊。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-157">Global admins can convert an existing team to an org-wide team by editing it in Teams client.</span></span> <span data-ttu-id="fc7b8-158">移至團隊名稱, 按一下 [**更多選項** > [**編輯團隊**]。</span><span class="sxs-lookup"><span data-stu-id="fc7b8-158">Go to the team name, click **More options** > **Edit team**.</span></span>
