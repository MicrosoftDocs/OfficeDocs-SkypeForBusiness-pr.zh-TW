---
title: 在 Microsoft 團隊系統管理中心管理團隊
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: 瞭解如何在 Microsoft 團隊系統管理中心中查看或更新您的小組。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8e0e96b05aff2d1c0e54bf6f1edb33f9b91aad6d
ms.sourcegitcommit: 4060f20e8e3ce5a0464c12cfebdf8fe3473733fe
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/14/2019
ms.locfileid: "38627029"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="8f0d8-103">在 Microsoft 團隊系統管理中心管理團隊</span><span class="sxs-lookup"><span data-stu-id="8f0d8-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="8f0d8-104">概觀</span><span class="sxs-lookup"><span data-stu-id="8f0d8-104">Overview</span></span>

<span data-ttu-id="8f0d8-105">本文將為 Microsoft 團隊系統管理中心的小組提供管理工具的概覽。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-105">This article provides an overview of the management tools for Teams in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="8f0d8-106">如果您是系統管理員，您可能需要查看或更新貴組織設定的共同作業小組，或者您可能需要執行修正動作，例如指派 ownerless 小組的擁有者。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-106">As an admin, you may need to view or update the teams that your organization set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="8f0d8-107">您可以透過 Microsoft 團隊 PowerShell 模組和 Microsoft 團隊系統管理中心來管理組織中使用的團隊。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-107">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="8f0d8-108">若要使用這兩種工具集的完整管理功能，您應該確認您已獲指派下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="8f0d8-108">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="8f0d8-109">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="8f0d8-109">Global Administrator</span></span>
- <span data-ttu-id="8f0d8-110">Teams 服務管理員</span><span class="sxs-lookup"><span data-stu-id="8f0d8-110">Teams Service Administrator</span></span>

<span data-ttu-id="8f0d8-111">您可以在團隊中進一步瞭解如何[使用 Microsoft 團隊管理員角色來管理團隊](using-admin-roles.md)，並進一步瞭解如何使用 PowerShell Cmdlet 來管理[Microsoft 團隊 Cmdlet 參考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)中的團隊。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-111">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>



## <a name="teams-overview-grid"></a><span data-ttu-id="8f0d8-112">團隊概覽格線</span><span class="sxs-lookup"><span data-stu-id="8f0d8-112">Teams overview grid</span></span>

<span data-ttu-id="8f0d8-113">小組的管理工具位於 Microsoft 團隊系統管理中心的 [**小組**] 節點底下。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-113">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="8f0d8-114">（在系統管理中心中，選取 [**團隊** > **管理團隊**]）。每個團隊都受 Office 365 群組的支援，而且這個節點提供已在貴組織中啟用 Microsoft 團隊的群組視圖。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![[團隊概覽] 格線的螢幕擷取畫面](media/manage-teams-in-modern-portal-grid.png)  

<span data-ttu-id="8f0d8-116">格線會顯示下列屬性：</span><span class="sxs-lookup"><span data-stu-id="8f0d8-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="8f0d8-117">**團隊名稱**</span><span class="sxs-lookup"><span data-stu-id="8f0d8-117">**Team name**</span></span>
- <span data-ttu-id="8f0d8-118">[**頻道**]-團隊中所有頻道的計數，包括預設的 [一般] 頻道。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="8f0d8-119">**小組成員**-總使用者數目，包括來自您租使用者的擁有者、來賓和成員。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-119">**Team members** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="8f0d8-120">[**擁有**者]-此小組的擁有者人數。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="8f0d8-121">**來賓**-此團隊成員的 Azure ACTIVE Directory B2B 來賓使用者的計數。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="8f0d8-122">**隱私權**-支援 Office 365 群組的可見度/AccessType。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-122">**Privacy** - the Visibility/AccessType of the backing Office 365 group.</span></span>
- <span data-ttu-id="8f0d8-123">[**狀態**]-此小組的已存檔或活動狀態。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-123">**Status** - the Archived or Active status for this team.</span></span> <span data-ttu-id="8f0d8-124">進一步瞭解封存[或還原小組中的](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)團隊。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-124">Learn more about archiving teams in [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="8f0d8-125">**描述**-支援 Office 365 群組的描述。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-125">**Description** - the description of the backing Office 365 group.</span></span>
- <span data-ttu-id="8f0d8-126">**分類**-指派給支援 Office 365 群組的分類（如果您的組織使用的話）。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-126">**Classification** - the classification (if used in your organization) assigned to the backing Office 365 group.</span></span> <span data-ttu-id="8f0d8-127">深入瞭解[貴組織中 Office 群組的建立分類](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-127">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="8f0d8-128">**GroupID** -支援 Office 365 群組的唯一 GroupID。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-128">**GroupID** - the unique GroupID of the backing Office 365 group.</span></span>

> [!NOTE]
> <span data-ttu-id="8f0d8-129">如果您沒有在格線中看到所有這些屬性，請按一下 [**編輯欄**] 圖示。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-129">If you don't see all these properties in the grid, click the **Edit columns** icon.</span></span> <span data-ttu-id="8f0d8-130">在 [**編輯欄**] 窗格中，您可以使用切換來開啟或關閉格線中的欄。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-130">In the **Edit columns** pane, you can use the toggles to turn on or turn off columns in the grid.</span></span> <span data-ttu-id="8f0d8-131">完成後，**請按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-131">When you're finished, click **Apply**.</span></span>

### <a name="add"></a><span data-ttu-id="8f0d8-132">Add</span><span class="sxs-lookup"><span data-stu-id="8f0d8-132">Add</span></span>

<span data-ttu-id="8f0d8-133">若要新增團隊，**請按一下 [新增]**。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-133">To add a new team, click **Add**.</span></span> <span data-ttu-id="8f0d8-134">在 [**新增團隊**] 窗格中，給予團隊名稱和描述，設定您要將它設為私人小組或公開團隊，並設定分類。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-134">In the **Add a new team** pane, give the team a name and description, set whether you want to make it a private or public team, and set the classification.</span></span>

### <a name="edit"></a><span data-ttu-id="8f0d8-135">編輯</span><span class="sxs-lookup"><span data-stu-id="8f0d8-135">Edit</span></span>

<span data-ttu-id="8f0d8-136">若要編輯群組和小組專用的設定，請按一下團隊名稱左方，然後選取 [**編輯**]，以選取團隊。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-136">To edit group and team-specific settings, select the team by clicking to the left of the team name, and then select **Edit**.</span></span>

### <a name="archive"></a><span data-ttu-id="8f0d8-137">壓縮</span><span class="sxs-lookup"><span data-stu-id="8f0d8-137">Archive</span></span>

<span data-ttu-id="8f0d8-138">您可以封存小組。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-138">You can archive a team.</span></span> <span data-ttu-id="8f0d8-139">封存小組會將小組放入小組中的唯讀模式。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-139">Archiving a team puts the team into read-only mode within Teams.</span></span> <span data-ttu-id="8f0d8-140">做為管理員，您可以在系統管理中心中代表您的組織封存和取消封存小組。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-140">As an admin, you can archive and un-archive teams on behalf of your organization in the admin center.</span></span> 

### <a name="delete"></a><span data-ttu-id="8f0d8-141">Delete</span><span class="sxs-lookup"><span data-stu-id="8f0d8-141">Delete</span></span>

<span data-ttu-id="8f0d8-142">刪除小組就是一項虛刪除的小組及對應的 Office 365 群組。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-142">Deleting a team is a soft-delete of the team and corresponding Office 365 group.</span></span> <span data-ttu-id="8f0d8-143">若要還原錯誤刪除的小組，請依照[還原已刪除的 Office 365 群組](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-143">To restore a mistakenly deleted team, follow the instructions in [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span></span>

### <a name="search"></a><span data-ttu-id="8f0d8-144">檢索</span><span class="sxs-lookup"><span data-stu-id="8f0d8-144">Search</span></span>

<span data-ttu-id="8f0d8-145">搜尋目前支援字串「開始于」，並搜尋 [**小組名稱**] 欄位。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-145">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

## <a name="team-profile"></a><span data-ttu-id="8f0d8-146">小組設定檔</span><span class="sxs-lookup"><span data-stu-id="8f0d8-146">Team profile</span></span>

<span data-ttu-id="8f0d8-147">您可以按一下 [團隊名稱]，從 [主要團隊概覽] 格線流覽至任何團隊的 [團隊個人檔案] 頁面。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-147">You can navigate to the team profile page of any team from the main teams overview grid by clicking  the team name.</span></span> <span data-ttu-id="8f0d8-148">[小組個人檔案] 頁面會顯示屬於小組（及其支援的 Office 365 群組），以及小組的頻道與設定的成員、擁有者和來賓。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-148">The team profile page shows the members, owners, and guests that belong to the team (and its backing Office 365 group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="8f0d8-149">您可以從 [團隊設定檔] 頁面進行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8f0d8-149">From the team profile page, you can:</span></span>

- <span data-ttu-id="8f0d8-150">新增或移除成員和擁有者。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-150">Add or remove members and owners.</span></span>
- <span data-ttu-id="8f0d8-151">新增或移除頻道（請注意，您無法移除 [一般] 頻道）。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-151">Add or remove channels (note that you can't remove the General channel).</span></span>
- <span data-ttu-id="8f0d8-152">變更小組和群組設定。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-152">Change team and group settings.</span></span>
 
![範例小組設定檔的螢幕擷取畫面](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="8f0d8-154">對團隊進行變更</span><span class="sxs-lookup"><span data-stu-id="8f0d8-154">Making changes to teams</span></span>

<span data-ttu-id="8f0d8-155">在團隊的 [設定檔] 頁面上，您可以變更團隊的下列元素：</span><span class="sxs-lookup"><span data-stu-id="8f0d8-155">On the team's profile page, you can change the following elements of a team:</span></span>

- <span data-ttu-id="8f0d8-156">[**成員**]-新增或移除成員以及提升或降級擁有者。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-156">**Members** - add or remove members and promote or demote owners.</span></span>
- <span data-ttu-id="8f0d8-157">**頻道**-新增頻道，以及編輯或移除現有頻道。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-157">**Channels** - add new channels, and edit or remove existing channels.</span></span> <span data-ttu-id="8f0d8-158">請記住，您無法刪除預設的 [一般] 頻道。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-158">Remember that you can't delete the default General channel.</span></span>
- <span data-ttu-id="8f0d8-159">**團隊名稱**</span><span class="sxs-lookup"><span data-stu-id="8f0d8-159">**Team name**</span></span>
- <span data-ttu-id="8f0d8-160">**描述**</span><span class="sxs-lookup"><span data-stu-id="8f0d8-160">**Description**</span></span>
- <span data-ttu-id="8f0d8-161">**隱私權**-設定團隊是否為公用或私人。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-161">**Privacy** - set whether the team is public or private.</span></span>
- <span data-ttu-id="8f0d8-162">**分類**-這是由您的 Office 365 群組分類所支援。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-162">**Classification** - this is backed by your Office 365 group classifications.</span></span> <span data-ttu-id="8f0d8-163">選擇 [**機密**]、[**高度機密**] 或 **[一般**]。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-163">Choose **Confidential**, **Highly Confidential**, or **General**.</span></span>
- <span data-ttu-id="8f0d8-164">[**交談設定**]-設定成員是否可以編輯及刪除已傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-164">**Conversations settings** - set whether members can edit and delete sent messages.</span></span>
- <span data-ttu-id="8f0d8-165">**頻道設定**-設定成員是否可以建立新的頻道，以及編輯現有的頻道，以及新增、編輯及移除索引標籤、連接器及應用程式。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-165">**Channels settings** - set whether members can create new channels and edit existing ones, and add, edit, and remove tabs, connectors, and apps.</span></span>

<span data-ttu-id="8f0d8-166">您對小組所做的變更會記錄下來。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-166">The changes that you make to a team are logged.</span></span> <span data-ttu-id="8f0d8-167">如果您要修改群組設定（變更名稱、描述、相片、隱私權、分類或團隊成員），這些變更將會透過審核管線進行設定。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-167">If you're modifying group settings (changing the name, description, photo, privacy, classification, or team members), the changes are attributed to you through the audit pipeline.</span></span> <span data-ttu-id="8f0d8-168">如果您要針對特定團隊的設定執行動作，您的變更會在團隊的 [一般] 頻道中追蹤並設定為 [已設定]。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-168">If you're performing actions against Teams-specific settings, your changes are tracked and attributed to you in the General channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="8f0d8-169">疑難排解</span><span class="sxs-lookup"><span data-stu-id="8f0d8-169">Troubleshooting</span></span>

<span data-ttu-id="8f0d8-170">**問題：團隊概覽格線中缺少團隊**</span><span class="sxs-lookup"><span data-stu-id="8f0d8-170">**Issue: Teams missing from the Team overview grid**</span></span>

<span data-ttu-id="8f0d8-171">[團隊概述] 網格中的小組清單中遺失了一些團隊。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-171">Some of your teams are missing from the list of teams in the Teams overview grid.</span></span>

<span data-ttu-id="8f0d8-172">**原因**：當小組不正確（或尚未）由系統所分析，可能會導致其無法辨識某個缺少的屬性時，就會發生這個問題。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-172">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="8f0d8-173">**解析度：透過 MS Graph 將屬性手動設定為正確的值**</span><span class="sxs-lookup"><span data-stu-id="8f0d8-173">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="8f0d8-174">在查詢中，使用「 \*\* [UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps) \*\* 」 Cmdlet 做為「**ExternalDirectoryObjectId**」屬性，取代 **{GroupId}** ，以取得實際的 groupid，您可以透過 Exchange Online powershell 取得該問題。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-174">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="8f0d8-175">Access[圖形瀏覽器](https://developer.microsoft.com/graph/graph-explorer)。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-175">Access [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

2. <span data-ttu-id="8f0d8-176">在左側功能表中登入圖表資源管理器。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-176">Sign in to Graph Explorer on the left menu.</span></span>

3. <span data-ttu-id="8f0d8-177">將查詢行變更為： PATCH > v 1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-177">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.</span></span>

4. <span data-ttu-id="8f0d8-178">在要求主體上加上下列值： {"resourceProvisioningOptions"： ["團隊"]}。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-178">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}.</span></span>

5. <span data-ttu-id="8f0d8-179">在右上方執行查詢。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-179">Run the query on the top-right.</span></span>

6. <span data-ttu-id="8f0d8-180">確認小組已正確顯示在 Microsoft 團隊系統管理中心-小組概述中。</span><span class="sxs-lookup"><span data-stu-id="8f0d8-180">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview.</span></span>

## <a name="learn-more"></a><span data-ttu-id="8f0d8-181">瞭解更多資訊</span><span class="sxs-lookup"><span data-stu-id="8f0d8-181">Learn more</span></span>

- [<span data-ttu-id="8f0d8-182">團隊 Cmdlet 參考</span><span class="sxs-lookup"><span data-stu-id="8f0d8-182">Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
- [<span data-ttu-id="8f0d8-183">使用團隊管理員角色管理團隊</span><span class="sxs-lookup"><span data-stu-id="8f0d8-183">Use Teams administrator roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="8f0d8-184">Teams 中的生命週期管理方案</span><span class="sxs-lookup"><span data-stu-id="8f0d8-184">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)
