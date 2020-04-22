---
title: 在 Microsoft 團隊中指派小組擁有者和成員
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中指派小組擁有者和成員角色及許可權，包括建立小組的許可權。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ba628bf3f58523dc37e2273b437f22af1a0ebc19
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778929"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a><span data-ttu-id="350e5-103">在 Microsoft 團隊中指派小組擁有者和成員</span><span class="sxs-lookup"><span data-stu-id="350e5-103">Assign team owners and members in Microsoft Teams</span></span>
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="350e5-104">在 Microsoft 團隊中，有兩個使用者角色： [**擁有**者] 和 [**成員**]。</span><span class="sxs-lookup"><span data-stu-id="350e5-104">Within Microsoft Teams there are two user roles: **owner** and **member**.</span></span> <span data-ttu-id="350e5-105">根據預設，會將建立新團隊的使用者授與擁有者狀態。</span><span class="sxs-lookup"><span data-stu-id="350e5-105">By default, a user who creates a new team is granted the owner status.</span></span> <span data-ttu-id="350e5-106">此外，擁有者和成員也可以擁有頻道的仲裁者功能（前提是已設定裁決）。</span><span class="sxs-lookup"><span data-stu-id="350e5-106">In addition, owners and members can have moderator capabilities for a channel (provided that moderation has been set up).</span></span> <span data-ttu-id="350e5-107">如果您是從現有的 Office 365 群組建立團隊，則會繼承許可權。</span><span class="sxs-lookup"><span data-stu-id="350e5-107">If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="350e5-108">下表顯示擁有者和成員之間許可權的差異。</span><span class="sxs-lookup"><span data-stu-id="350e5-108">The table below shows the difference in permissions between an owner and a member.</span></span>


|                                   | <span data-ttu-id="350e5-109">小組擁有者</span><span class="sxs-lookup"><span data-stu-id="350e5-109">Team Owner</span></span> | <span data-ttu-id="350e5-110">小組成員</span><span class="sxs-lookup"><span data-stu-id="350e5-110">Team Member</span></span> |
|-----------------------------------|------------|-------------|
|          <span data-ttu-id="350e5-111">**建立小組**</span><span class="sxs-lookup"><span data-stu-id="350e5-111">**Create team**</span></span>          |    <span data-ttu-id="350e5-112">是<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="350e5-112">Yes<sup>1</sup></span></span>     |     <span data-ttu-id="350e5-113">否</span><span class="sxs-lookup"><span data-stu-id="350e5-113">No</span></span>      |
|          <span data-ttu-id="350e5-114">**離開團隊**</span><span class="sxs-lookup"><span data-stu-id="350e5-114">**Leave team**</span></span>           |    <span data-ttu-id="350e5-115">是</span><span class="sxs-lookup"><span data-stu-id="350e5-115">Yes</span></span>     |     <span data-ttu-id="350e5-116">是</span><span class="sxs-lookup"><span data-stu-id="350e5-116">Yes</span></span>     |
|  <span data-ttu-id="350e5-117">**編輯團隊名稱/描述**</span><span class="sxs-lookup"><span data-stu-id="350e5-117">**Edit team name/description**</span></span>   |    <span data-ttu-id="350e5-118">是</span><span class="sxs-lookup"><span data-stu-id="350e5-118">Yes</span></span>     |     <span data-ttu-id="350e5-119">否</span><span class="sxs-lookup"><span data-stu-id="350e5-119">No</span></span>      |
|          <span data-ttu-id="350e5-120">**刪除團隊**</span><span class="sxs-lookup"><span data-stu-id="350e5-120">**Delete team**</span></span>          |    <span data-ttu-id="350e5-121">是</span><span class="sxs-lookup"><span data-stu-id="350e5-121">Yes</span></span>     |     <span data-ttu-id="350e5-122">否</span><span class="sxs-lookup"><span data-stu-id="350e5-122">No</span></span>      |
|          <span data-ttu-id="350e5-123">**新增標準頻道**</span><span class="sxs-lookup"><span data-stu-id="350e5-123">**Add standard channel**</span></span>          |    <span data-ttu-id="350e5-124">是</span><span class="sxs-lookup"><span data-stu-id="350e5-124">Yes</span></span>     |    <span data-ttu-id="350e5-125">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="350e5-125">Yes<sup>2</sup></span></span>|
| <span data-ttu-id="350e5-126">**編輯標準頻道名稱/描述**</span><span class="sxs-lookup"><span data-stu-id="350e5-126">**Edit standard channel name/description**</span></span> |    <span data-ttu-id="350e5-127">是</span><span class="sxs-lookup"><span data-stu-id="350e5-127">Yes</span></span>     |    <span data-ttu-id="350e5-128">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="350e5-128">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="350e5-129">**刪除標準頻道**</span><span class="sxs-lookup"><span data-stu-id="350e5-129">**Delete standard channel**</span></span>         |    <span data-ttu-id="350e5-130">是</span><span class="sxs-lookup"><span data-stu-id="350e5-130">Yes</span></span>     |    <span data-ttu-id="350e5-131">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="350e5-131">Yes<sup>2</sup></span></span>|
|          <span data-ttu-id="350e5-132">\***新增私人頻道**</span><span class="sxs-lookup"><span data-stu-id="350e5-132">\***Add private channel**</span></span>          |    <span data-ttu-id="350e5-133">是</span><span class="sxs-lookup"><span data-stu-id="350e5-133">Yes</span></span>     |    <span data-ttu-id="350e5-134">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="350e5-134">Yes<sup>2</sup></span></span>|
| <span data-ttu-id="350e5-135">\***編輯私人頻道名稱/描述**</span><span class="sxs-lookup"><span data-stu-id="350e5-135">\***Edit private channel name/description**</span></span> |    <span data-ttu-id="350e5-136">否</span><span class="sxs-lookup"><span data-stu-id="350e5-136">No</span></span>     |    <span data-ttu-id="350e5-137">N/A</span><span class="sxs-lookup"><span data-stu-id="350e5-137">N/A</span></span>|
|        <span data-ttu-id="350e5-138">\***刪除私人頻道**</span><span class="sxs-lookup"><span data-stu-id="350e5-138">\***Delete private channel**</span></span>         |    <span data-ttu-id="350e5-139">是</span><span class="sxs-lookup"><span data-stu-id="350e5-139">Yes</span></span>     |    <span data-ttu-id="350e5-140">否</span><span class="sxs-lookup"><span data-stu-id="350e5-140">No</span></span>|
|          <span data-ttu-id="350e5-141">**新增成員**</span><span class="sxs-lookup"><span data-stu-id="350e5-141">**Add members**</span></span>          |  <span data-ttu-id="350e5-142">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="350e5-142">Yes<sup>3</sup></span></span>   |     <span data-ttu-id="350e5-143">無<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="350e5-143">No<sup>4</sup></span></span>    |
|          <span data-ttu-id="350e5-144">**要求新增成員**</span><span class="sxs-lookup"><span data-stu-id="350e5-144">**Request to add members**</span></span>          |  <span data-ttu-id="350e5-145">不適用</span><span class="sxs-lookup"><span data-stu-id="350e5-145">N/A</span></span>   |     <span data-ttu-id="350e5-146">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="350e5-146">Yes<sup>5</sup></span></span>     |
|           <span data-ttu-id="350e5-147">**新增應用程式**</span><span class="sxs-lookup"><span data-stu-id="350e5-147">**Add apps**</span></span>            |    <span data-ttu-id="350e5-148">是</span><span class="sxs-lookup"><span data-stu-id="350e5-148">Yes</span></span>     |    <span data-ttu-id="350e5-149">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="350e5-149">Yes<sup>2</sup></span></span>|

<span data-ttu-id="350e5-150"><sup>1</sup>小組擁有者可以建立團隊，除非他們受到限制。</span><span class="sxs-lookup"><span data-stu-id="350e5-150"><sup>1</sup> Team owners can create teams unless they've been restricted from doing so.</span></span> <span data-ttu-id="350e5-151">[建立小組的許可權](#permissions-to-create-teams)。</span><span class="sxs-lookup"><span data-stu-id="350e5-151">[Permissions to create teams](#permissions-to-create-teams) below.</span></span><br>
<span data-ttu-id="350e5-152"><sup>2</sup>擁有者可以在小組層級關閉這些專案，在這種情況下，成員將無法存取它們。</span><span class="sxs-lookup"><span data-stu-id="350e5-152"><sup>2</sup> An owner can turn off these items at the team level, in which case members would not have access to them.</span></span><br>
<span data-ttu-id="350e5-153"><sup>3</sup>將成員新增至團隊之後，擁有者也可以將成員升級為擁有者狀態。</span><span class="sxs-lookup"><span data-stu-id="350e5-153"><sup>3</sup> After adding a member to a team, an owner can also promote a member to owner status.</span></span> <span data-ttu-id="350e5-154">您也可以讓擁有者將自己的狀態降級為成員。</span><span class="sxs-lookup"><span data-stu-id="350e5-154">It is also possible for an owner to demote their own status to a member.</span></span><br>
<span data-ttu-id="350e5-155"><sup>4 個</sup>小組成員可以將其他成員新增至公用小組。</span><span class="sxs-lookup"><span data-stu-id="350e5-155"><sup>4</sup> Team members can add other members to a public team.</span></span><br>
<span data-ttu-id="350e5-156"><sup>5</sup>當小組成員無法直接將成員新增到私人小組時，他們可以要求將某人新增至他們已成為其成員的小組。</span><span class="sxs-lookup"><span data-stu-id="350e5-156"><sup>5</sup> While a team member can't directly add members to a private team, they can request someone to be added to a team they're already a member of.</span></span> <span data-ttu-id="350e5-157">當成員要求將某人新增至小組時，小組擁有者會收到一則通知，提醒他們有可接受或拒絕的待定要求。</span><span class="sxs-lookup"><span data-stu-id="350e5-157">When a member requests someone to be added to a team, team owners receive an alert that they have a pending request that they can accept or deny.</span></span>

<span data-ttu-id="350e5-158">\* 若要深入瞭解私人頻道的許可權，請參閱[小組中的私人頻道](private-channels.md)。</span><span class="sxs-lookup"><span data-stu-id="350e5-158">\*To learn more about permissions for private channels, see [Private channels in Teams](private-channels.md).</span></span>

> [!NOTE]
> <span data-ttu-id="350e5-159">擁有者可以在 [**查看小組**] 選項中讓其他成員擁有者。</span><span class="sxs-lookup"><span data-stu-id="350e5-159">Owners can make other members owners in the **View teams** option.</span></span> <span data-ttu-id="350e5-160">團隊最多可以有100個擁有者。</span><span class="sxs-lookup"><span data-stu-id="350e5-160">A team can have up to 100 owners.</span></span> <span data-ttu-id="350e5-161">我們建議您至少有幾個擁有者協助管理團隊;這也會防止孤立的群組（如果擁有者離開您的組織）。</span><span class="sxs-lookup"><span data-stu-id="350e5-161">We recommend that you have at least a few owners to help manage the team; this will also prevent orphaned groups if a sole owner leaves your organization.</span></span> <span data-ttu-id="350e5-162">如需孤立群組的詳細資訊，請參閱[將新擁有者指派給孤立的群組](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)。</span><span class="sxs-lookup"><span data-stu-id="350e5-162">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>

## <a name="moderator-capabilities"></a><span data-ttu-id="350e5-163">版主功能</span><span class="sxs-lookup"><span data-stu-id="350e5-163">Moderator capabilities</span></span>

<span data-ttu-id="350e5-164">除了其他功能之外，小組擁有者和成員還可以擁有頻道的仲裁者功能（前提是針對團隊開啟裁決）。</span><span class="sxs-lookup"><span data-stu-id="350e5-164">In addition to other capabilities, team owners and members can have moderator capabilities for a channel (provided that moderation is turned on for a team).</span></span> <span data-ttu-id="350e5-165">版主可以在頻道中開始新的文章，並控制小組成員是否可以回復現有的頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="350e5-165">Moderators can start new posts in a channel and control whether team members can reply to existing channel messages.</span></span> <span data-ttu-id="350e5-166">他們也可以控制機器人與連接器是否能提交頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="350e5-166">They can also control whether bots and connectors can submit channel messages.</span></span>

<span data-ttu-id="350e5-167">版主功能是在頻道層級指派。</span><span class="sxs-lookup"><span data-stu-id="350e5-167">Moderator capabilities are assigned at the channel level.</span></span> <span data-ttu-id="350e5-168">小組擁有者預設具有仲裁者的功能。</span><span class="sxs-lookup"><span data-stu-id="350e5-168">Team owners have moderator capabilities by default.</span></span> <span data-ttu-id="350e5-169">小組成員預設會關閉仲裁者的功能，但小組擁有者可以為小組成員提供頻道的仲裁者功能。</span><span class="sxs-lookup"><span data-stu-id="350e5-169">Team members have moderator capabilities turned off by default, but a team owner can give moderator capabilities for a channel to a team member.</span></span> <span data-ttu-id="350e5-170">頻道內的版主者可以在該頻道中新增及移除其他版主。</span><span class="sxs-lookup"><span data-stu-id="350e5-170">Moderators within a channel can add and remove other moderators within that channel.</span></span>

<span data-ttu-id="350e5-171">如需有關版主功能的詳細資訊，請參閱[在 Microsoft 團隊中設定及管理頻道裁決](manage-channel-moderation-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="350e5-171">For more information about moderator capabilities, see [Set up and manage channel moderation in Microsoft Teams](manage-channel-moderation-in-teams.md).</span></span>

## <a name="assign-a-user-role"></a><span data-ttu-id="350e5-172">指派使用者角色</span><span class="sxs-lookup"><span data-stu-id="350e5-172">Assign a user role</span></span>

<span data-ttu-id="350e5-173">若要指派使用者角色，請在 [團隊] 中選取團隊名稱，然後按一下 [**更多選項** > **管理團隊**]。</span><span class="sxs-lookup"><span data-stu-id="350e5-173">To assign a user role, in Teams, select the team name and click **More options** > **Manage team**.</span></span> <span data-ttu-id="350e5-174">您可以在 [**成員**] 索引標籤上新增成員，然後選擇 [擁有人] 和 [版主] （如果您有足夠的許可權）。</span><span class="sxs-lookup"><span data-stu-id="350e5-174">On the **Members** tab, you can add members and choose owners and moderators (if you have sufficient permissions).</span></span> <span data-ttu-id="350e5-175">如需詳細資訊，請參閱[變更團隊中的團隊設定](https://support.office.com/article/ce053b04-1b8e-4796-baa8-90dc427b3acc)。</span><span class="sxs-lookup"><span data-stu-id="350e5-175">For more information , see [Change team settings in Teams](https://support.office.com/article/ce053b04-1b8e-4796-baa8-90dc427b3acc).</span></span>

## <a name="permissions-to-create-teams"></a><span data-ttu-id="350e5-176">建立小組的許可權</span><span class="sxs-lookup"><span data-stu-id="350e5-176">Permissions to create teams</span></span>

<span data-ttu-id="350e5-177">根據預設，所有在 Exchange Online 中擁有信箱的使用者，都有權建立 Microsoft 365 群組，進而成為 Microsoft 團隊內的小組。</span><span class="sxs-lookup"><span data-stu-id="350e5-177">By default, all users with a mailbox in Exchange Online have permissions to create Microsoft 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="350e5-178">您可以透過將群組建立與管理許可權委派給一組使用者，讓您更嚴密地控制和限制新團隊的建立，從而建立新的 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="350e5-178">You can have tighter control and restrict the creation of new teams and thus the creation of new Microsoft 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="350e5-179">如需相關指示，請參閱[管理可以建立 Microsoft 365 群組的人員](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。</span><span class="sxs-lookup"><span data-stu-id="350e5-179">For instructions, see [Manage who can create Microsoft 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![代表決策點的圖示](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="350e5-181">決策點</span><span class="sxs-lookup"><span data-stu-id="350e5-181">Decision Point</span></span>         |<span data-ttu-id="350e5-182">所有 Microsoft 團隊使用者都可以建立小組（建議使用）嗎？</span><span class="sxs-lookup"><span data-stu-id="350e5-182">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![代表後續步驟的圖示](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="350e5-184">後續步驟</span><span class="sxs-lookup"><span data-stu-id="350e5-184">Next Steps</span></span>         |<span data-ttu-id="350e5-185">修改誰可以建立 Microsoft 365 群組的預設許可權（如果您需要限制誰可以建立團隊）</span><span class="sxs-lookup"><span data-stu-id="350e5-185">Modify the default permissions for who can create Microsoft 365 groups if you need to limit who can create Teams</span></span>         |
