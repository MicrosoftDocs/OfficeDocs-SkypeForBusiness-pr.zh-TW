---
title: 在 Microsoft Teams 中建立全組織小組
author: LanaChin
ms.author: v-lanac
ms.reviewer: phlouie
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何建立及管理小組中的組織內小組，為中小型組織中的每個人提供自動方法來進行共同作業。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 84f34ee9af678613580beefeb52b08e9ce924be3
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2020
ms.locfileid: "47766867"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a><span data-ttu-id="deb0c-103">在 Microsoft Teams 中建立全組織小組</span><span class="sxs-lookup"><span data-stu-id="deb0c-103">Create an org-wide team in Microsoft Teams</span></span>

<span data-ttu-id="deb0c-104">全組織小組提供自動化方式，讓中小型組織中的每個人都成為單一小組的一部分來進行共同作業。</span><span class="sxs-lookup"><span data-stu-id="deb0c-104">Org-wide teams provide an automatic way for everyone in a small to medium-sized organization to be a part of a single team for collaboration.</span></span>

<span data-ttu-id="deb0c-105">透過全組織小組，全域系統管理員可以輕鬆建立一個公開的小組，將組織中的每個使用者都拉入，當使用者加入和離開組織時，讓成員資格能隨著 Active Directory 保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="deb0c-105">With org-wide teams, global admins can easily create a public team that pulls in every user in the organization and keeps the membership up to date with Active Directory as users join and leave the organization.</span></span> <span data-ttu-id="deb0c-106">只有全域管理員才能建立整個組織的團隊，而且目前組織範圍的小組僅限於5000使用者以外的組織。</span><span class="sxs-lookup"><span data-stu-id="deb0c-106">Only global admins can create org-wide teams and currently, an org-wide team is limited to organizations with no more than 5,000 users.</span></span> <span data-ttu-id="deb0c-107">另外還有一個限制是，每個租用戶只能有五個全組織小組。</span><span class="sxs-lookup"><span data-stu-id="deb0c-107">There's also a limit of five org-wide teams per tenant.</span></span> <span data-ttu-id="deb0c-108">如果符合這些需求，在建立小組時，全域系統管理員選取 [從頭建置小組]\*\*\*\* 時會看到 [全組織]\*\*\*\* 這個選項。</span><span class="sxs-lookup"><span data-stu-id="deb0c-108">If these requirements are met, global admins will see **Org-wide** as an option when they select **Build a team from scratch** when creating a team.</span></span> 

<span data-ttu-id="deb0c-109">![建立全組織小組的全組織選項螢幕擷取畫面](media/create-org-wide-team.png "建立全組織小組的全組織選項螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="deb0c-109">![Screenshot of the Org-wide option to create an org-wide team](media/create-org-wide-team.png "Screen shot of the Org-wide option to create an org-wide team")</span></span>

<span data-ttu-id="deb0c-110">建立組織範圍的小組後，所有全域管理員和團隊服務系統管理員都會新增為團隊擁有者，而所有作用中的使用者都會新增為小組成員。</span><span class="sxs-lookup"><span data-stu-id="deb0c-110">When an org-wide team is created, all global admins and Teams service administrators are added as team owners and all active users are added as team members.</span></span> <span data-ttu-id="deb0c-111">未授權的使用者也會新增至小組。</span><span class="sxs-lookup"><span data-stu-id="deb0c-111">Unlicensed users are also added to the team.</span></span> <span data-ttu-id="deb0c-112">未授權的使用者第一次登入小組時，系統會為該使用者指派 Microsoft 團隊探索性授權。</span><span class="sxs-lookup"><span data-stu-id="deb0c-112">The first time an unlicensed user signs in to Teams, the user is assigned a Microsoft Teams Exploratory license.</span></span> <span data-ttu-id="deb0c-113">若要深入瞭解探索授權，請參閱 [管理 Microsoft 團隊探索性授權](teams-exploratory.md)。</span><span class="sxs-lookup"><span data-stu-id="deb0c-113">To learn more about the Exploratory license, check out [Manage the Microsoft Teams Exploratory license](teams-exploratory.md).</span></span> 

<span data-ttu-id="deb0c-114">您的全組織小組將不會新增下列帳戶類型：</span><span class="sxs-lookup"><span data-stu-id="deb0c-114">These types of accounts won't be added to your org-wide team:</span></span>

- <span data-ttu-id="deb0c-115">被封鎖而無法登入的帳戶</span><span class="sxs-lookup"><span data-stu-id="deb0c-115">Accounts that are blocked from sign in</span></span>
- <span data-ttu-id="deb0c-116">來賓使用者</span><span class="sxs-lookup"><span data-stu-id="deb0c-116">Guest users</span></span>
- <span data-ttu-id="deb0c-117">服務帳戶</span><span class="sxs-lookup"><span data-stu-id="deb0c-117">Service accounts</span></span>
- <span data-ttu-id="deb0c-118">會議室或設備帳戶</span><span class="sxs-lookup"><span data-stu-id="deb0c-118">Room or equipment accounts</span></span>
- <span data-ttu-id="deb0c-119">共用信箱支援的帳戶</span><span class="sxs-lookup"><span data-stu-id="deb0c-119">Accounts backed by a shared mailbox</span></span>

<span data-ttu-id="deb0c-120">當貴組織的目錄更新為包含新的作用中使用者，或如果使用者已經不在您的公司工作，且已停用其帳戶時，則會自動同步處理變更，將使用者新增到小組中或從小組中移除。</span><span class="sxs-lookup"><span data-stu-id="deb0c-120">As your organization's directory is updated to include new active users or if users no longer work at your company and their account is disabled, changes are automatically synced and the users are added or removed from the team.</span></span> <span data-ttu-id="deb0c-121">小組成員不能離開全組織小組。</span><span class="sxs-lookup"><span data-stu-id="deb0c-121">Team members can't leave an org-wide team.</span></span> <span data-ttu-id="deb0c-122">如果您是小組擁有者，可以視需要手動新增或移除使用者。</span><span class="sxs-lookup"><span data-stu-id="deb0c-122">As a team owner, you can manually add or remove users if needed.</span></span>

> [!NOTE]
> - <span data-ttu-id="deb0c-123">如果您在建立小組時沒有看到 **組織範圍** 選項，而您是全域系統管理員，則您可能已達到5個組織範圍的小組限制，或貴組織的目前大小限制超過5000個成員。</span><span class="sxs-lookup"><span data-stu-id="deb0c-123">If you don't see the **Org-wide** option when creating a team and you're a global admin, you might have reached the five org-wide teams limit, or your organization might have more than the current size limit of 5,000 members.</span></span> <span data-ttu-id="deb0c-124">我們預計在未來增加這個限制。</span><span class="sxs-lookup"><span data-stu-id="deb0c-124">We're looking to increase this limit in the future.</span></span> <span data-ttu-id="deb0c-125">Teams 教育版目前無法使用全組織小組。</span><span class="sxs-lookup"><span data-stu-id="deb0c-125">Org-wide teams aren't yet available for Teams for Education.</span></span>
> - <span data-ttu-id="deb0c-126">您可能將不屬於會議室清單、設備和資源帳戶的會議室新增或同步處理到全組織小組。</span><span class="sxs-lookup"><span data-stu-id="deb0c-126">Rooms that aren't a part of a room list, equipment, and resource accounts might be added or synced to the org-wide team.</span></span> <span data-ttu-id="deb0c-127">小組擁有者可輕鬆地從小組移除這些帳戶。</span><span class="sxs-lookup"><span data-stu-id="deb0c-127">Team owners can easily remove these accounts from the team.</span></span>
> - <span data-ttu-id="deb0c-128">系統新增或移除成員的所有動作會張貼在 [一般] 頻道。</span><span class="sxs-lookup"><span data-stu-id="deb0c-128">All actions by the system to add or remove members are posted in the General channel.</span></span> <span data-ttu-id="deb0c-129">頻道也會標示為在 Teams 用戶端中有新的活動。</span><span class="sxs-lookup"><span data-stu-id="deb0c-129">The channel will also be marked as having new activity in the Teams client.</span></span>
> - <span data-ttu-id="deb0c-130">如果貴組織剛開始使用 Teams，且具有不超過 5000 個使用者，我們會自動為貴組織建立全組織小組。</span><span class="sxs-lookup"><span data-stu-id="deb0c-130">We'll automatically create an org-wide team for your organization if your organization is new to Teams and has no more than 5,000 users.</span></span> <span data-ttu-id="deb0c-131">小組名稱會反映租用戶名稱，並擁有 [一般] 頻道。</span><span class="sxs-lookup"><span data-stu-id="deb0c-131">The team name will reflect the tenant name and will have a General channel.</span></span> <span data-ttu-id="deb0c-132">全域系統管理員可以像其他任何小組一樣編輯這個小組。</span><span class="sxs-lookup"><span data-stu-id="deb0c-132">Global admins can edit this team like any other team.</span></span> 

## <a name="best-practices"></a><span data-ttu-id="deb0c-133">最佳做法</span><span class="sxs-lookup"><span data-stu-id="deb0c-133">Best practices</span></span>

<span data-ttu-id="deb0c-134">為了充分發揮您的全組織小組功能，我們建議小組擁有者執行下列動作。</span><span class="sxs-lookup"><span data-stu-id="deb0c-134">To get the most out of your org-wide team, we recommend team owners do the following.</span></span>

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a><span data-ttu-id="deb0c-135">只允許小組擁有者張貼到 [一般] 頻道</span><span class="sxs-lookup"><span data-stu-id="deb0c-135">Allow only team owners to post to the General channel</span></span>

<span data-ttu-id="deb0c-136">只允許小組擁有者張貼到 [一般] 頻道，以減少頻道「紛擾」。</span><span class="sxs-lookup"><span data-stu-id="deb0c-136">Reduce channel noise by having only team owners post to the General channel.</span></span> <span data-ttu-id="deb0c-137">移至團隊，找出 [一般] 頻道，然後選取 [ **̇̇̇其他選項**]  >  **管理頻道**。</span><span class="sxs-lookup"><span data-stu-id="deb0c-137">Go to the team, locate the General channel, and then select **˙˙˙ More options** > **Manage channel**.</span></span> <span data-ttu-id="deb0c-138">按一下 [ **頻道設定** ] 索引標籤上的 [ **許可權**]，然後選取 [ **只有擁有者可以張貼郵件**]。</span><span class="sxs-lookup"><span data-stu-id="deb0c-138">On the **Channel settings** tab, click **Permissions**, and then select **Only owners can post messages**.</span></span>

### <a name="turn-off-team-and-team-name-mentions"></a><span data-ttu-id="deb0c-139">關閉 @team 和 @[小組名稱] 提及項目</span><span class="sxs-lookup"><span data-stu-id="deb0c-139">Turn off @team and @[team name] mentions</span></span>

 <span data-ttu-id="deb0c-140">降低 @mentions 使其不會讓整個組織超載。</span><span class="sxs-lookup"><span data-stu-id="deb0c-140">Reduce @mentions to keep them from overloading the entire organization.</span></span> <span data-ttu-id="deb0c-141">移至小組，然後按一下 [更多選項]\*\*\*\*  >  [管理小組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="deb0c-141">Go to the team and click **˙˙˙ More options** > **Manage Team**.</span></span> <span data-ttu-id="deb0c-142">在 [設定]\*\*\*\* 索引標籤上，按一下 [@mentions]<strong></strong> > 關閉 [向成員顯示 @team 或 @[小組名稱] 選項]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="deb0c-142">On the **Settings** tab, click <strong>@mentions</strong> > turn off **Show members the option to @team or @[team name]**.</span></span> 

### <a name="automatically-show-important-channels"></a><span data-ttu-id="deb0c-143">自動顯示重要頻道</span><span class="sxs-lookup"><span data-stu-id="deb0c-143">Automatically show important channels</span></span>

<span data-ttu-id="deb0c-144">顯示重要的頻道以確保組織中的所有人都參與特定交談。</span><span class="sxs-lookup"><span data-stu-id="deb0c-144">Show important channels to ensure everyone in your organization engages in specific conversations.</span></span> <span data-ttu-id="deb0c-145">如需深入了解，請參閱[自動將頻道加入我的最愛方便整個團隊使用](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6)。</span><span class="sxs-lookup"><span data-stu-id="deb0c-145">To learn more, see [Auto-favorite channels for the whole team](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6).</span></span> 

### <a name="set-up-channel-moderation"></a><span data-ttu-id="deb0c-146">設定頻道裁決</span><span class="sxs-lookup"><span data-stu-id="deb0c-146">Set up channel moderation</span></span>

<span data-ttu-id="deb0c-147">請考量設定頻道裁決，並為特定小組成員提供仲裁者功能。</span><span class="sxs-lookup"><span data-stu-id="deb0c-147">Consider setting up channel moderation and giving moderator capabilities to certain team members.</span></span> <span data-ttu-id="deb0c-148">(設定仲裁時，會自動將仲裁者功能提供給小組擁有者。) 仲裁者能控制頻道中誰可以開始新文章、新增和移除仲裁者、控制小組成員是否可以回覆現有的頻道訊息，以及控制 Bot 和連接器是否可以提交頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="deb0c-148">(When moderation is set up, team owners are given moderator capabilities automatically.) Moderators can control who can start a new post in a channel, add and remove moderators, control whether team members can reply to existing channel messages, and control whether bots and connectors can submit channel messages.</span></span> <span data-ttu-id="deb0c-149">如需詳細資訊，請參閱[在 Microsoft Teams 中設定和管理頻道仲裁](manage-channel-moderation-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="deb0c-149">For more information, see [Set up and manage channel moderation in Microsoft Teams](manage-channel-moderation-in-teams.md).</span></span>

### <a name="remove-accounts-that-might-not-belong"></a><span data-ttu-id="deb0c-150">移除可能不屬於的帳戶</span><span class="sxs-lookup"><span data-stu-id="deb0c-150">Remove accounts that might not belong</span></span>

<span data-ttu-id="deb0c-151">即使成員不能離開組織內的小組（作為小組擁有者），您還是可以移除不屬於的帳戶來管理團隊名單。</span><span class="sxs-lookup"><span data-stu-id="deb0c-151">Even though members can't leave an org-wide team, as a team owner, you can manage the team roster by removing accounts that don't belong.</span></span> <span data-ttu-id="deb0c-152">**請確認您使用 Teams 移除全組織小組中的使用者**。</span><span class="sxs-lookup"><span data-stu-id="deb0c-152">**Make sure you use Teams to remove users from your org-wide team**.</span></span> <span data-ttu-id="deb0c-153">如果您使用其他方法 (例如 Microsoft 365 系統管理中心或從 Outlook 中的群組) 移除使用者，有可能會不小心將該使用者新增回全組織小組。</span><span class="sxs-lookup"><span data-stu-id="deb0c-153">If you use another way to remove a user, such as the Microsoft 365 admin center or from a group in Outlook, the user might be added back to the org-wide team.</span></span>

## <a name="faq"></a><span data-ttu-id="deb0c-154">常見問題集</span><span class="sxs-lookup"><span data-stu-id="deb0c-154">FAQ</span></span>

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a><span data-ttu-id="deb0c-155">有沒有使用 Teams 用戶端以外的建立全組織小組方法？</span><span class="sxs-lookup"><span data-stu-id="deb0c-155">Is there a way to create an org-wide team other than using the Teams client?</span></span>

<span data-ttu-id="deb0c-156">全域系統管理員只能使用 Teams 用戶端建立全組織小組。</span><span class="sxs-lookup"><span data-stu-id="deb0c-156">Global admins can only create an org-wide team by using the Teams client.</span></span> <span data-ttu-id="deb0c-157">如果貴組織將建立小組限制為使用 PowerShell，建議的因應措施是將您的全域系統管理員新增至可建立小組的使用者安全性群組。</span><span class="sxs-lookup"><span data-stu-id="deb0c-157">If your organization limits creating teams to using PowerShell, the recommended workaround is to add your global admins to the security group of users who can create a team.</span></span> <span data-ttu-id="deb0c-158">如需詳細資訊，請參閱 [管理可以建立群組的人員](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups)。</span><span class="sxs-lookup"><span data-stu-id="deb0c-158">For more information, see [Manage who can create groups](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups).</span></span>

<span data-ttu-id="deb0c-159">如果這不是選項，您可以使用 PowerShell 來建立公用小組，並將全域系統管理員新增為小組擁有者。</span><span class="sxs-lookup"><span data-stu-id="deb0c-159">If this isn't an option, you can use PowerShell to create a public team and add a global admin as the team owner.</span></span> <span data-ttu-id="deb0c-160">然後，讓全域系統管理員按一下小組名稱旁的 [更多選項]\*\*\*\*，按一下 [編輯小組]\*\*\*\*，然後將隱私權變更為 [全組織 - 貴組織中的所有人都會自動新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="deb0c-160">Then, have the global admin click **More options** next to the team name, click **Edit team**, and then change the privacy to **Org-wide - Everyone in your organization will be automatically added**.</span></span> <span data-ttu-id="deb0c-161">請注意，只有小組擁有者可以存取 [編輯小組]\*\*\*\* 選項，而且只有全域系統管理員才能查看 [全組織]\*\*\*\* 選項。</span><span class="sxs-lookup"><span data-stu-id="deb0c-161">Note that only team owners can access the **Edit team** option and only global admins can see the **Org-wide** option.</span></span>

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-org-wide-team"></a><span data-ttu-id="deb0c-162">有沒有方法可以將現有的小組轉換成全組織小組？</span><span class="sxs-lookup"><span data-stu-id="deb0c-162">Is there a way to convert an existing team to an org-wide team?</span></span>

<span data-ttu-id="deb0c-163">全域系統管理員可以在 Teams 用戶端中編輯現有的小組，將其轉換成全組織小組。</span><span class="sxs-lookup"><span data-stu-id="deb0c-163">Global admins can convert an existing team to an org-wide team by editing it in Teams client.</span></span> <span data-ttu-id="deb0c-164">移至小組名稱，按一下 [更多選項]\*\*\*\*  >  [編輯小組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="deb0c-164">Go to the team name, click **More options** > **Edit team**.</span></span>

### <a name="can-i-create-an-org-wide-team-using-a-team-template"></a><span data-ttu-id="deb0c-165">我可以使用小組範本建立組織範圍的團隊嗎？</span><span class="sxs-lookup"><span data-stu-id="deb0c-165">Can I create an org-wide team using a team template?</span></span>

<span data-ttu-id="deb0c-166">小組範本不能用來建立整個組織的小組。</span><span class="sxs-lookup"><span data-stu-id="deb0c-166">Team templates can't be used to create an org-wide team.</span></span> <span data-ttu-id="deb0c-167">目前正在進行此功能的工作。</span><span class="sxs-lookup"><span data-stu-id="deb0c-167">Work for this feature is currently in progress.</span></span> 

## <a name="see-also"></a><span data-ttu-id="deb0c-168">另請參閱</span><span class="sxs-lookup"><span data-stu-id="deb0c-168">See also</span></span>

<span data-ttu-id="deb0c-169">觀看有關 [在 Microsoft 團隊中建立整個公司小組](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3)的影片。</span><span class="sxs-lookup"><span data-stu-id="deb0c-169">Watch a video about [creating a company-wide team in Microsoft Teams](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3).</span></span>
