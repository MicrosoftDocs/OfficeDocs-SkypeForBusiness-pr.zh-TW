---
title: 在 Microsoft Teams 系統管理中心管理團隊
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: 瞭解如何在 Microsoft Teams 系統管理中心中，查看或更新貴組織為共同合作所設定的團隊。
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6bf864fefd3ac60c7531bd339a5587c8f2f0dd72
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094233"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="2fc77-103">在 Microsoft Teams 系統管理中心管理團隊</span><span class="sxs-lookup"><span data-stu-id="2fc77-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="2fc77-104">概觀</span><span class="sxs-lookup"><span data-stu-id="2fc77-104">Overview</span></span>

<span data-ttu-id="2fc77-105">本文提供 Microsoft Teams 系統管理中心的 Teams 管理工具概觀。</span><span class="sxs-lookup"><span data-stu-id="2fc77-105">This article provides an overview of the management tools for Teams in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="2fc77-106">作為系統管理員，您可能需要查看或更新貴組織為共同合作所設定的團隊，或者您可能需要執行補救動作，例如指派無擁有者團隊的擁有者。</span><span class="sxs-lookup"><span data-stu-id="2fc77-106">As an admin, you may need to view or update the teams that your organization set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="2fc77-107">您可以透過 Microsoft Teams PowerShell 模組和 Microsoft Teams 系統管理中心來管理貴組織中所使用的團隊。</span><span class="sxs-lookup"><span data-stu-id="2fc77-107">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="2fc77-108">您可以在 存取系統管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="2fc77-108">You can access the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> <span data-ttu-id="2fc77-109">針對使用這兩個工具集的完整管理功能，您應該確定已指派下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="2fc77-109">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="2fc77-110">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="2fc77-110">Global Administrator</span></span>
- <span data-ttu-id="2fc77-111">Teams 服務管理員</span><span class="sxs-lookup"><span data-stu-id="2fc77-111">Teams Service Administrator</span></span>

<span data-ttu-id="2fc77-112">您可以在使用 [Microsoft Teams](using-admin-roles.md)系統管理員角色管理 Teams 中深入瞭解 Teams 中的系統管理員角色，並深入瞭解如何使用 PowerShell Cmdlet 在 Microsoft [Teams Cmdlet](/powershell/teams/?view=teams-ps)參照中管理團隊。</span><span class="sxs-lookup"><span data-stu-id="2fc77-112">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](/powershell/teams/?view=teams-ps).</span></span>



## <a name="teams-overview-grid"></a><span data-ttu-id="2fc77-113">Teams 概觀格線</span><span class="sxs-lookup"><span data-stu-id="2fc77-113">Teams overview grid</span></span>

<span data-ttu-id="2fc77-114">團隊管理工具位於 Microsoft Teams 系統管理中心的 **Teams** 節點下。</span><span class="sxs-lookup"><span data-stu-id="2fc77-114">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="2fc77-115"> (在系統管理中心中，選取Teams Manage teams .) 每個團隊都有 Microsoft 365 群組的支援，此節點會提供組織中已啟用 Microsoft Teams 的群組  >  的視圖。</span><span class="sxs-lookup"><span data-stu-id="2fc77-115">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by a Microsoft 365 Group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Teams 概觀格線螢幕擷取畫面](media/manage-teams-in-modern-portal-grid.png)  

<span data-ttu-id="2fc77-117">格線會顯示下列屬性：</span><span class="sxs-lookup"><span data-stu-id="2fc77-117">The grid displays the following properties:</span></span>

- <span data-ttu-id="2fc77-118">**團隊名稱**</span><span class="sxs-lookup"><span data-stu-id="2fc77-118">**Team name**</span></span>
- <span data-ttu-id="2fc77-119">**頻道** - 團隊中所有頻道的計數，包括預設的一般頻道。</span><span class="sxs-lookup"><span data-stu-id="2fc77-119">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="2fc77-120">**小組成員** - 來自租使用者的使用者總數，包括擁有者、來賓和成員。</span><span class="sxs-lookup"><span data-stu-id="2fc77-120">**Team members** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="2fc77-121">**擁有者** - 此團隊的擁有者計數。</span><span class="sxs-lookup"><span data-stu-id="2fc77-121">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="2fc77-122">**來賓** - 此小組成員的 Azure Active Directory B2B 來賓使用者計數。</span><span class="sxs-lookup"><span data-stu-id="2fc77-122">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="2fc77-123">**隱私權** - 支援 Microsoft 365 群組的可見度/AccessType。</span><span class="sxs-lookup"><span data-stu-id="2fc77-123">**Privacy** - the Visibility/AccessType of the backing Microsoft 365 group.</span></span>
- <span data-ttu-id="2fc77-124">**狀態** - 此團隊的已存檔或活動狀態。</span><span class="sxs-lookup"><span data-stu-id="2fc77-124">**Status** - the Archived or Active status for this team.</span></span> <span data-ttu-id="2fc77-125">深入瞭解在檔案或還原團隊中[將團隊存檔。](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)</span><span class="sxs-lookup"><span data-stu-id="2fc77-125">Learn more about archiving teams in [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="2fc77-126">**描述** - 支援 Microsoft 365 群組的描述。</span><span class="sxs-lookup"><span data-stu-id="2fc77-126">**Description** - the description of the backing Microsoft 365 group.</span></span>
- <span data-ttu-id="2fc77-127">**分類** ： (組織中使用的分類) 指派給支援 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="2fc77-127">**Classification** - the classification (if used in your organization) assigned to the backing Microsoft 365 group.</span></span> <span data-ttu-id="2fc77-128">若要深入瞭解分類，請至為貴組織的 [Office 群組建立分類](/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="2fc77-128">Learn more about classifications at [Create classifications for Office groups in your organization](/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="2fc77-129">**GroupID** - 支援 Microsoft 365 群組的唯一 GroupID。</span><span class="sxs-lookup"><span data-stu-id="2fc77-129">**GroupID** - the unique GroupID of the backing Microsoft 365 group.</span></span>

> [!NOTE]
> <span data-ttu-id="2fc77-130">如果您在格線中沒看到所有這些屬性，請按一下 [ **編輯欄圖示** 。</span><span class="sxs-lookup"><span data-stu-id="2fc77-130">If you don't see all these properties in the grid, click the **Edit columns** icon.</span></span> <span data-ttu-id="2fc77-131">在編輯 **欄** 窗格中，您可以使用切換開關來開啟或關閉格線中的欄。</span><span class="sxs-lookup"><span data-stu-id="2fc77-131">In the **Edit columns** pane, you can use the toggles to turn on or turn off columns in the grid.</span></span> <span data-ttu-id="2fc77-132">完成後，按一下 **[Apply.**</span><span class="sxs-lookup"><span data-stu-id="2fc77-132">When you're finished, click **Apply**.</span></span>

### <a name="add"></a><span data-ttu-id="2fc77-133">添加</span><span class="sxs-lookup"><span data-stu-id="2fc77-133">Add</span></span>

<span data-ttu-id="2fc77-134">若要新增團隊，請按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="2fc77-134">To add a new team, click **Add**.</span></span> <span data-ttu-id="2fc77-135">在新增 **團隊窗格中** ，為團隊命名和描述，設定您是否要將其設為私人或公開團隊，並設定分類。</span><span class="sxs-lookup"><span data-stu-id="2fc77-135">In the **Add a new team** pane, give the team a name and description, set whether you want to make it a private or public team, and set the classification.</span></span>

> [!NOTE]
> <span data-ttu-id="2fc77-136">新建立的團隊可以馬上在 Teams 系統管理中心管理，不像 Outlook 等其他用戶端的體驗。</span><span class="sxs-lookup"><span data-stu-id="2fc77-136">Newly created teams can be managed right away in the Teams Admin Center, unlike the experience in other clients like, Outlook.</span></span>

### <a name="edit"></a><span data-ttu-id="2fc77-137">編輯</span><span class="sxs-lookup"><span data-stu-id="2fc77-137">Edit</span></span>

<span data-ttu-id="2fc77-138">若要編輯群組和團隊特定設定，請按一下團隊名稱左側的選取團隊，然後 **選取編輯**。</span><span class="sxs-lookup"><span data-stu-id="2fc77-138">To edit group and team-specific settings, select the team by clicking to the left of the team name, and then select **Edit**.</span></span>

### <a name="archive"></a><span data-ttu-id="2fc77-139">檔案</span><span class="sxs-lookup"><span data-stu-id="2fc77-139">Archive</span></span>

<span data-ttu-id="2fc77-140">您可以存檔團隊。</span><span class="sxs-lookup"><span data-stu-id="2fc77-140">You can archive a team.</span></span> <span data-ttu-id="2fc77-141">將小組歸檔後，團隊會進入 Teams 中的唯讀模式。</span><span class="sxs-lookup"><span data-stu-id="2fc77-141">Archiving a team puts the team into read-only mode within Teams.</span></span> <span data-ttu-id="2fc77-142">做為系統管理員，您可以在系統管理中心代表貴組織來存檔和取消存檔團隊。</span><span class="sxs-lookup"><span data-stu-id="2fc77-142">As an admin, you can archive and un-archive teams on behalf of your organization in the admin center.</span></span> 

### <a name="delete"></a><span data-ttu-id="2fc77-143">刪除</span><span class="sxs-lookup"><span data-stu-id="2fc77-143">Delete</span></span>

<span data-ttu-id="2fc77-144">刪除團隊是小組和對應的 Microsoft 365 群組的輕柔刪除。</span><span class="sxs-lookup"><span data-stu-id="2fc77-144">Deleting a team is a soft-delete of the team and corresponding Microsoft 365 group.</span></span> <span data-ttu-id="2fc77-145">若要還原誤刪除的團隊，請遵循還原已刪除的群組 [中的指示](/microsoft-365/admin/create-groups/restore-deleted-group)。</span><span class="sxs-lookup"><span data-stu-id="2fc77-145">To restore a mistakenly deleted team, follow the instructions in [Restore a deleted Group](/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

### <a name="search"></a><span data-ttu-id="2fc77-146">搜索</span><span class="sxs-lookup"><span data-stu-id="2fc77-146">Search</span></span>

<span data-ttu-id="2fc77-147">搜尋目前支援字串「開頭」，並搜尋 **團隊名稱** 欄位。</span><span class="sxs-lookup"><span data-stu-id="2fc77-147">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

## <a name="team-profile"></a><span data-ttu-id="2fc77-148">小組設定檔</span><span class="sxs-lookup"><span data-stu-id="2fc77-148">Team profile</span></span>

<span data-ttu-id="2fc77-149">您可以按一下團隊名稱，從主要團隊概觀格線流覽至任何團隊的小組設定檔頁面面。</span><span class="sxs-lookup"><span data-stu-id="2fc77-149">You can navigate to the team profile page of any team from the main teams overview grid by clicking  the team name.</span></span> <span data-ttu-id="2fc77-150">小組設定檔頁面面會顯示屬於小組 (的成員、擁有者和來賓及其支援 Microsoft 365 群組) ，以及團隊的頻道和設定。</span><span class="sxs-lookup"><span data-stu-id="2fc77-150">The team profile page shows the members, owners, and guests that belong to the team (and its backing Microsoft 365 group), as well as the team's channels and settings.</span></span> <span data-ttu-id="2fc77-151">從小組設定檔頁面面，您可以：</span><span class="sxs-lookup"><span data-stu-id="2fc77-151">From the team profile page, you can:</span></span>

- <span data-ttu-id="2fc77-152">新增或移除成員和擁有者。</span><span class="sxs-lookup"><span data-stu-id="2fc77-152">Add or remove members and owners.</span></span>
- <span data-ttu-id="2fc77-153">新增或移除 (，請注意，您無法移除一般) 。</span><span class="sxs-lookup"><span data-stu-id="2fc77-153">Add or remove channels (note that you can't remove the General channel).</span></span>
- <span data-ttu-id="2fc77-154">變更小組和群組設定。</span><span class="sxs-lookup"><span data-stu-id="2fc77-154">Change team and group settings.</span></span>
 
![範例小組設定檔的螢幕擷取畫面](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="2fc77-156">變更團隊</span><span class="sxs-lookup"><span data-stu-id="2fc77-156">Making changes to teams</span></span>

<span data-ttu-id="2fc77-157">在小組的設定檔頁面面上，您可以變更團隊的下列元素：</span><span class="sxs-lookup"><span data-stu-id="2fc77-157">On the team's profile page, you can change the following elements of a team:</span></span>

- <span data-ttu-id="2fc77-158">**成員** - 新增或移除成員，並提升或降級擁有者。</span><span class="sxs-lookup"><span data-stu-id="2fc77-158">**Members** - add or remove members and promote or demote owners.</span></span>
- <span data-ttu-id="2fc77-159">**頻道** - 新增頻道，以及編輯或移除現有的頻道。</span><span class="sxs-lookup"><span data-stu-id="2fc77-159">**Channels** - add new channels, and edit or remove existing channels.</span></span> <span data-ttu-id="2fc77-160">請記住，您無法刪除預設的一般頻道。</span><span class="sxs-lookup"><span data-stu-id="2fc77-160">Remember that you can't delete the default General channel.</span></span>
- <span data-ttu-id="2fc77-161">**團隊名稱**</span><span class="sxs-lookup"><span data-stu-id="2fc77-161">**Team name**</span></span>
- <span data-ttu-id="2fc77-162">**描述**</span><span class="sxs-lookup"><span data-stu-id="2fc77-162">**Description**</span></span>
- <span data-ttu-id="2fc77-163">**隱私權** - 設定團隊是公開還是私人。</span><span class="sxs-lookup"><span data-stu-id="2fc77-163">**Privacy** - set whether the team is public or private.</span></span>
- <span data-ttu-id="2fc77-164">**分類** - 這是由您的 Microsoft 365 群組分類所支援。</span><span class="sxs-lookup"><span data-stu-id="2fc77-164">**Classification** - this is backed by your Microsoft 365 group classifications.</span></span> <span data-ttu-id="2fc77-165">選擇 **機密**、 **高度機密** 或 **一般**。</span><span class="sxs-lookup"><span data-stu-id="2fc77-165">Choose **Confidential**, **Highly Confidential**, or **General**.</span></span>
- <span data-ttu-id="2fc77-166">**交談設定** - 設定成員是否可以編輯和刪除已送出的郵件。</span><span class="sxs-lookup"><span data-stu-id="2fc77-166">**Conversations settings** - set whether members can edit and delete sent messages.</span></span>
- <span data-ttu-id="2fc77-167">**頻道設定** - 設定成員是否可以建立新頻道及編輯現有的頻道，以及新增、編輯及移除定位停駐點、連接器和應用程式。</span><span class="sxs-lookup"><span data-stu-id="2fc77-167">**Channels settings** - set whether members can create new channels and edit existing ones, and add, edit, and remove tabs, connectors, and apps.</span></span>

<span data-ttu-id="2fc77-168">您對團隊的變更會記錄。</span><span class="sxs-lookup"><span data-stu-id="2fc77-168">The changes that you make to a team are logged.</span></span> <span data-ttu-id="2fc77-169">如果您要修改群組設定 (變更名稱、描述、相片、隱私權、分類或小組成員) ，這些變更會透過稽核管道歸您所有。</span><span class="sxs-lookup"><span data-stu-id="2fc77-169">If you're modifying group settings (changing the name, description, photo, privacy, classification, or team members), the changes are attributed to you through the audit pipeline.</span></span> <span data-ttu-id="2fc77-170">如果您針對 Teams 特定設定執行動作，系統會追蹤您的變更，並歸結于團隊的一般頻道中。</span><span class="sxs-lookup"><span data-stu-id="2fc77-170">If you're performing actions against Teams-specific settings, your changes are tracked and attributed to you in the General channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="2fc77-171">疑難排解</span><span class="sxs-lookup"><span data-stu-id="2fc77-171">Troubleshooting</span></span>

<span data-ttu-id="2fc77-172">**問題：團隊概觀格線中缺少團隊**</span><span class="sxs-lookup"><span data-stu-id="2fc77-172">**Issue: Teams missing from the Team overview grid**</span></span>

<span data-ttu-id="2fc77-173">Teams 概觀格線中的團隊清單中缺少部分團隊。</span><span class="sxs-lookup"><span data-stu-id="2fc77-173">Some of your teams are missing from the list of teams in the Teams overview grid.</span></span>

<span data-ttu-id="2fc77-174">**原因**：當小組未正確 (或尚未) 系統所設定檔時，會發生此問題，可能會導致屬性遺失，無法識別。</span><span class="sxs-lookup"><span data-stu-id="2fc77-174">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="2fc77-175">**解析度：透過 MS Graph 手動將屬性設定為正確的值**</span><span class="sxs-lookup"><span data-stu-id="2fc77-175">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="2fc77-176">在查詢中將 **{groupid}** 取代為問題的實際 GroupId，您可以透過 Exchange Online Powershell 取得此名稱，以 **[「Get-UnifiedGroup」](/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)** Cmdlet 取代為 **「ExternalDirectoryObjectId」** 屬性。</span><span class="sxs-lookup"><span data-stu-id="2fc77-176">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="2fc77-177">Access [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer)。</span><span class="sxs-lookup"><span data-stu-id="2fc77-177">Access [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

2. <span data-ttu-id="2fc77-178">在左側功能表上，請登錄 Graph Explorer。</span><span class="sxs-lookup"><span data-stu-id="2fc77-178">Sign in to Graph Explorer on the left menu.</span></span>

3. <span data-ttu-id="2fc77-179">將查詢行變更為：PATCH > v1.0 https://graph.microsoft.com/v1.0/groups/{groupid} >。</span><span class="sxs-lookup"><span data-stu-id="2fc77-179">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.</span></span>

4. <span data-ttu-id="2fc77-180">在要求主體上新增下列值：{"resourceProvisioningOptions"：["Team"]}。</span><span class="sxs-lookup"><span data-stu-id="2fc77-180">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}.</span></span>

5. <span data-ttu-id="2fc77-181">在右上方執行查詢。</span><span class="sxs-lookup"><span data-stu-id="2fc77-181">Run the query on the top-right.</span></span>

6. <span data-ttu-id="2fc77-182">確認小組正確顯示在 Microsoft Teams 系統管理中心 - 團隊概觀中。</span><span class="sxs-lookup"><span data-stu-id="2fc77-182">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview.</span></span>

## <a name="learn-more"></a><span data-ttu-id="2fc77-183">深入了解</span><span class="sxs-lookup"><span data-stu-id="2fc77-183">Learn more</span></span>

- [<span data-ttu-id="2fc77-184">Teams Cmdlet 參照</span><span class="sxs-lookup"><span data-stu-id="2fc77-184">Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)  
- [<span data-ttu-id="2fc77-185">使用 Teams 系統管理員角色來管理 Teams</span><span class="sxs-lookup"><span data-stu-id="2fc77-185">Use Teams administrator roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="2fc77-186">Teams 中的生命週期管理方案</span><span class="sxs-lookup"><span data-stu-id="2fc77-186">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)