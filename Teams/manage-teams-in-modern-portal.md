---
title: 在 Microsoft 團隊系統管理中心管理團隊
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: 瞭解如何在 Microsoft 團隊系統管理中心中查看或更新貴組織已設定共同作業的團隊。
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
ms.openlocfilehash: b3c963e88d33928add9c7f5c611f44919250b847
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583150"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="7bf84-103">在 Microsoft 團隊系統管理中心管理團隊</span><span class="sxs-lookup"><span data-stu-id="7bf84-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="7bf84-104">概觀</span><span class="sxs-lookup"><span data-stu-id="7bf84-104">Overview</span></span>

<span data-ttu-id="7bf84-105">本文將為 Microsoft 團隊系統管理中心的小組提供管理工具的概覽。</span><span class="sxs-lookup"><span data-stu-id="7bf84-105">This article provides an overview of the management tools for Teams in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="7bf84-106">如果您是系統管理員，您可能需要查看或更新貴組織設定的共同作業小組，或者您可能需要執行修正動作，例如指派 ownerless 小組的擁有者。</span><span class="sxs-lookup"><span data-stu-id="7bf84-106">As an admin, you may need to view or update the teams that your organization set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="7bf84-107">您可以透過 Microsoft 團隊 PowerShell 模組和 Microsoft 團隊系統管理中心來管理組織中使用的團隊。</span><span class="sxs-lookup"><span data-stu-id="7bf84-107">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="7bf84-108">您可以存取系統管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="7bf84-108">You can access the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> <span data-ttu-id="7bf84-109">若要使用這兩種工具集的完整管理功能，您應該確認您已獲指派下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="7bf84-109">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="7bf84-110">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="7bf84-110">Global Administrator</span></span>
- <span data-ttu-id="7bf84-111">Teams 服務管理員</span><span class="sxs-lookup"><span data-stu-id="7bf84-111">Teams Service Administrator</span></span>

<span data-ttu-id="7bf84-112">您可以在團隊中進一步瞭解如何[使用 Microsoft 團隊管理員角色來管理團隊](using-admin-roles.md)，並進一步瞭解如何使用 PowerShell Cmdlet 來管理[Microsoft 團隊 Cmdlet 參考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)中的團隊。</span><span class="sxs-lookup"><span data-stu-id="7bf84-112">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>



## <a name="teams-overview-grid"></a><span data-ttu-id="7bf84-113">團隊概覽格線</span><span class="sxs-lookup"><span data-stu-id="7bf84-113">Teams overview grid</span></span>

<span data-ttu-id="7bf84-114">小組的管理工具位於 Microsoft 團隊系統管理中心的 [**小組**] 節點底下。</span><span class="sxs-lookup"><span data-stu-id="7bf84-114">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="7bf84-115"> (在系統管理中心中，選取 [**團隊**  >  **管理團隊**] ) 。每個團隊都是由 microsoft 365 群組所支援，而這個節點提供已在貴組織中啟用 Microsoft 團隊的群組視圖。</span><span class="sxs-lookup"><span data-stu-id="7bf84-115">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by a Microsoft 365 Group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![[團隊概覽] 格線的螢幕擷取畫面](media/manage-teams-in-modern-portal-grid.png)  

<span data-ttu-id="7bf84-117">格線會顯示下列屬性：</span><span class="sxs-lookup"><span data-stu-id="7bf84-117">The grid displays the following properties:</span></span>

- <span data-ttu-id="7bf84-118">**團隊名稱**</span><span class="sxs-lookup"><span data-stu-id="7bf84-118">**Team name**</span></span>
- <span data-ttu-id="7bf84-119">[**頻道**]-團隊中所有頻道的計數，包括預設的 [一般] 頻道。</span><span class="sxs-lookup"><span data-stu-id="7bf84-119">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="7bf84-120">**小組成員**-總使用者數目，包括來自您租使用者的擁有者、來賓和成員。</span><span class="sxs-lookup"><span data-stu-id="7bf84-120">**Team members** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="7bf84-121">[**擁有**者]-此小組的擁有者人數。</span><span class="sxs-lookup"><span data-stu-id="7bf84-121">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="7bf84-122">**來賓**-此團隊成員的 Azure ACTIVE Directory B2B 來賓使用者的計數。</span><span class="sxs-lookup"><span data-stu-id="7bf84-122">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="7bf84-123">**隱私權**-支援的 Microsoft 365 群組的可見度/AccessType。</span><span class="sxs-lookup"><span data-stu-id="7bf84-123">**Privacy** - the Visibility/AccessType of the backing Microsoft 365 group.</span></span>
- <span data-ttu-id="7bf84-124">[**狀態**]-此小組的已存檔或活動狀態。</span><span class="sxs-lookup"><span data-stu-id="7bf84-124">**Status** - the Archived or Active status for this team.</span></span> <span data-ttu-id="7bf84-125">進一步瞭解封存[或還原小組中的](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)團隊。</span><span class="sxs-lookup"><span data-stu-id="7bf84-125">Learn more about archiving teams in [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="7bf84-126">**描述**-支援的 Microsoft 365 群組的描述。</span><span class="sxs-lookup"><span data-stu-id="7bf84-126">**Description** - the description of the backing Microsoft 365 group.</span></span>
- <span data-ttu-id="7bf84-127">**分類**-在您的組織中使用的分類 () 指派給支援的 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="7bf84-127">**Classification** - the classification (if used in your organization) assigned to the backing Microsoft 365 group.</span></span> <span data-ttu-id="7bf84-128">深入瞭解[貴組織中 Office 群組的建立分類](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="7bf84-128">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="7bf84-129">**GroupID** -支援的 Microsoft 365 群組的唯一 GroupID。</span><span class="sxs-lookup"><span data-stu-id="7bf84-129">**GroupID** - the unique GroupID of the backing Microsoft 365 group.</span></span>

> [!NOTE]
> <span data-ttu-id="7bf84-130">如果您沒有在格線中看到所有這些屬性，請按一下 [**編輯欄**] 圖示。</span><span class="sxs-lookup"><span data-stu-id="7bf84-130">If you don't see all these properties in the grid, click the **Edit columns** icon.</span></span> <span data-ttu-id="7bf84-131">在 [**編輯欄**] 窗格中，您可以使用切換來開啟或關閉格線中的欄。</span><span class="sxs-lookup"><span data-stu-id="7bf84-131">In the **Edit columns** pane, you can use the toggles to turn on or turn off columns in the grid.</span></span> <span data-ttu-id="7bf84-132">完成後，**請按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="7bf84-132">When you're finished, click **Apply**.</span></span>

### <a name="add"></a><span data-ttu-id="7bf84-133">Add</span><span class="sxs-lookup"><span data-stu-id="7bf84-133">Add</span></span>

<span data-ttu-id="7bf84-134">若要新增團隊，**請按一下 [新增]**。</span><span class="sxs-lookup"><span data-stu-id="7bf84-134">To add a new team, click **Add**.</span></span> <span data-ttu-id="7bf84-135">在 [**新增團隊**] 窗格中，給予團隊名稱和描述，設定您要將它設為私人小組或公開團隊，並設定分類。</span><span class="sxs-lookup"><span data-stu-id="7bf84-135">In the **Add a new team** pane, give the team a name and description, set whether you want to make it a private or public team, and set the classification.</span></span>

### <a name="edit"></a><span data-ttu-id="7bf84-136">編輯</span><span class="sxs-lookup"><span data-stu-id="7bf84-136">Edit</span></span>

<span data-ttu-id="7bf84-137">若要編輯群組和小組專用的設定，請按一下團隊名稱左方，然後選取 [**編輯**]，以選取團隊。</span><span class="sxs-lookup"><span data-stu-id="7bf84-137">To edit group and team-specific settings, select the team by clicking to the left of the team name, and then select **Edit**.</span></span>

### <a name="archive"></a><span data-ttu-id="7bf84-138">壓縮</span><span class="sxs-lookup"><span data-stu-id="7bf84-138">Archive</span></span>

<span data-ttu-id="7bf84-139">您可以封存小組。</span><span class="sxs-lookup"><span data-stu-id="7bf84-139">You can archive a team.</span></span> <span data-ttu-id="7bf84-140">封存小組會將小組放入小組中的唯讀模式。</span><span class="sxs-lookup"><span data-stu-id="7bf84-140">Archiving a team puts the team into read-only mode within Teams.</span></span> <span data-ttu-id="7bf84-141">做為管理員，您可以在系統管理中心中代表您的組織封存和取消封存小組。</span><span class="sxs-lookup"><span data-stu-id="7bf84-141">As an admin, you can archive and un-archive teams on behalf of your organization in the admin center.</span></span> 

### <a name="delete"></a><span data-ttu-id="7bf84-142">Delete</span><span class="sxs-lookup"><span data-stu-id="7bf84-142">Delete</span></span>

<span data-ttu-id="7bf84-143">刪除小組是小組及對應的 Microsoft 365 群組的虛刪除。</span><span class="sxs-lookup"><span data-stu-id="7bf84-143">Deleting a team is a soft-delete of the team and corresponding Microsoft 365 group.</span></span> <span data-ttu-id="7bf84-144">若要還原錯誤刪除的小組，請依照[還原已刪除的群組](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="7bf84-144">To restore a mistakenly deleted team, follow the instructions in [Restore a deleted Group](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

### <a name="search"></a><span data-ttu-id="7bf84-145">檢索</span><span class="sxs-lookup"><span data-stu-id="7bf84-145">Search</span></span>

<span data-ttu-id="7bf84-146">搜尋目前支援字串「開始于」，並搜尋 [**小組名稱**] 欄位。</span><span class="sxs-lookup"><span data-stu-id="7bf84-146">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

## <a name="team-profile"></a><span data-ttu-id="7bf84-147">小組設定檔</span><span class="sxs-lookup"><span data-stu-id="7bf84-147">Team profile</span></span>

<span data-ttu-id="7bf84-148">您可以按一下 [團隊名稱]，從 [主要團隊概覽] 格線流覽至任何團隊的 [團隊個人檔案] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7bf84-148">You can navigate to the team profile page of any team from the main teams overview grid by clicking  the team name.</span></span> <span data-ttu-id="7bf84-149">[小組個人檔案] 頁面會顯示屬於團隊 (及其支援的 Microsoft 365 群組) ，以及小組的頻道與設定的成員、擁有者和來賓。</span><span class="sxs-lookup"><span data-stu-id="7bf84-149">The team profile page shows the members, owners, and guests that belong to the team (and its backing Microsoft 365 group), as well as the team's channels and settings.</span></span> <span data-ttu-id="7bf84-150">您可以從 [團隊設定檔] 頁面進行下列動作：</span><span class="sxs-lookup"><span data-stu-id="7bf84-150">From the team profile page, you can:</span></span>

- <span data-ttu-id="7bf84-151">新增或移除成員和擁有者。</span><span class="sxs-lookup"><span data-stu-id="7bf84-151">Add or remove members and owners.</span></span>
- <span data-ttu-id="7bf84-152">新增或移除頻道 (請注意，您無法) 中移除 [一般] 頻道。</span><span class="sxs-lookup"><span data-stu-id="7bf84-152">Add or remove channels (note that you can't remove the General channel).</span></span>
- <span data-ttu-id="7bf84-153">變更小組和群組設定。</span><span class="sxs-lookup"><span data-stu-id="7bf84-153">Change team and group settings.</span></span>
 
![範例小組設定檔的螢幕擷取畫面](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="7bf84-155">對團隊進行變更</span><span class="sxs-lookup"><span data-stu-id="7bf84-155">Making changes to teams</span></span>

<span data-ttu-id="7bf84-156">在團隊的 [設定檔] 頁面上，您可以變更團隊的下列元素：</span><span class="sxs-lookup"><span data-stu-id="7bf84-156">On the team's profile page, you can change the following elements of a team:</span></span>

- <span data-ttu-id="7bf84-157">[**成員**]-新增或移除成員以及提升或降級擁有者。</span><span class="sxs-lookup"><span data-stu-id="7bf84-157">**Members** - add or remove members and promote or demote owners.</span></span>
- <span data-ttu-id="7bf84-158">**頻道**-新增頻道，以及編輯或移除現有頻道。</span><span class="sxs-lookup"><span data-stu-id="7bf84-158">**Channels** - add new channels, and edit or remove existing channels.</span></span> <span data-ttu-id="7bf84-159">請記住，您無法刪除預設的 [一般] 頻道。</span><span class="sxs-lookup"><span data-stu-id="7bf84-159">Remember that you can't delete the default General channel.</span></span>
- <span data-ttu-id="7bf84-160">**團隊名稱**</span><span class="sxs-lookup"><span data-stu-id="7bf84-160">**Team name**</span></span>
- <span data-ttu-id="7bf84-161">**描述**</span><span class="sxs-lookup"><span data-stu-id="7bf84-161">**Description**</span></span>
- <span data-ttu-id="7bf84-162">**隱私權**-設定團隊是否為公用或私人。</span><span class="sxs-lookup"><span data-stu-id="7bf84-162">**Privacy** - set whether the team is public or private.</span></span>
- <span data-ttu-id="7bf84-163">**分類**-這是由您的 Microsoft 365 群組分類所支援。</span><span class="sxs-lookup"><span data-stu-id="7bf84-163">**Classification** - this is backed by your Microsoft 365 group classifications.</span></span> <span data-ttu-id="7bf84-164">選擇 [**機密**]、[**高度機密**] 或 **[一般**]。</span><span class="sxs-lookup"><span data-stu-id="7bf84-164">Choose **Confidential**, **Highly Confidential**, or **General**.</span></span>
- <span data-ttu-id="7bf84-165">[**交談設定**]-設定成員是否可以編輯及刪除已傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="7bf84-165">**Conversations settings** - set whether members can edit and delete sent messages.</span></span>
- <span data-ttu-id="7bf84-166">**頻道設定**-設定成員是否可以建立新的頻道，以及編輯現有的頻道，以及新增、編輯及移除索引標籤、連接器及應用程式。</span><span class="sxs-lookup"><span data-stu-id="7bf84-166">**Channels settings** - set whether members can create new channels and edit existing ones, and add, edit, and remove tabs, connectors, and apps.</span></span>

<span data-ttu-id="7bf84-167">您對小組所做的變更會記錄下來。</span><span class="sxs-lookup"><span data-stu-id="7bf84-167">The changes that you make to a team are logged.</span></span> <span data-ttu-id="7bf84-168">如果您正在修改 [群組設定] (變更名稱、描述、相片、隱私權、分類或團隊成員) ，這些變更會透過審核管線進行變更。</span><span class="sxs-lookup"><span data-stu-id="7bf84-168">If you're modifying group settings (changing the name, description, photo, privacy, classification, or team members), the changes are attributed to you through the audit pipeline.</span></span> <span data-ttu-id="7bf84-169">如果您要針對特定團隊的設定執行動作，您的變更會在團隊的 [一般] 頻道中追蹤並設定為 [已設定]。</span><span class="sxs-lookup"><span data-stu-id="7bf84-169">If you're performing actions against Teams-specific settings, your changes are tracked and attributed to you in the General channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="7bf84-170">疑難排解</span><span class="sxs-lookup"><span data-stu-id="7bf84-170">Troubleshooting</span></span>

<span data-ttu-id="7bf84-171">**問題：團隊概覽格線中缺少團隊**</span><span class="sxs-lookup"><span data-stu-id="7bf84-171">**Issue: Teams missing from the Team overview grid**</span></span>

<span data-ttu-id="7bf84-172">[團隊概述] 網格中的小組清單中遺失了一些團隊。</span><span class="sxs-lookup"><span data-stu-id="7bf84-172">Some of your teams are missing from the list of teams in the Teams overview grid.</span></span>

<span data-ttu-id="7bf84-173">**原因**：當小組不正確 (或尚未) 系統所分析，可能會導致它無法辨識的屬性，就會發生此問題。</span><span class="sxs-lookup"><span data-stu-id="7bf84-173">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="7bf84-174">**解析度：透過 MS Graph 將屬性手動設定為正確的值**</span><span class="sxs-lookup"><span data-stu-id="7bf84-174">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="7bf84-175">在查詢中，使用「 \*\* [UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps) \*\* 」 Cmdlet 做為「**ExternalDirectoryObjectId**」屬性，取代 **{GroupId}** ，以取得實際的 groupid，您可以透過 Exchange Online powershell 取得該問題。</span><span class="sxs-lookup"><span data-stu-id="7bf84-175">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="7bf84-176">Access[圖形瀏覽器](https://developer.microsoft.com/graph/graph-explorer)。</span><span class="sxs-lookup"><span data-stu-id="7bf84-176">Access [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

2. <span data-ttu-id="7bf84-177">在左側功能表中登入圖表資源管理器。</span><span class="sxs-lookup"><span data-stu-id="7bf84-177">Sign in to Graph Explorer on the left menu.</span></span>

3. <span data-ttu-id="7bf84-178">將查詢行變更為： PATCH > v 1.0 > https://graph.microsoft.com/v1.0/groups/{groupid} 。</span><span class="sxs-lookup"><span data-stu-id="7bf84-178">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.</span></span>

4. <span data-ttu-id="7bf84-179">在要求主體上加上下列值： {"resourceProvisioningOptions"： ["團隊"]}。</span><span class="sxs-lookup"><span data-stu-id="7bf84-179">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}.</span></span>

5. <span data-ttu-id="7bf84-180">在右上方執行查詢。</span><span class="sxs-lookup"><span data-stu-id="7bf84-180">Run the query on the top-right.</span></span>

6. <span data-ttu-id="7bf84-181">確認小組已正確顯示在 Microsoft 團隊系統管理中心-小組概述中。</span><span class="sxs-lookup"><span data-stu-id="7bf84-181">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview.</span></span>

## <a name="learn-more"></a><span data-ttu-id="7bf84-182">深入了解</span><span class="sxs-lookup"><span data-stu-id="7bf84-182">Learn more</span></span>

- [<span data-ttu-id="7bf84-183">團隊 Cmdlet 參考</span><span class="sxs-lookup"><span data-stu-id="7bf84-183">Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
- [<span data-ttu-id="7bf84-184">使用團隊管理員角色管理團隊</span><span class="sxs-lookup"><span data-stu-id="7bf84-184">Use Teams administrator roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="7bf84-185">Teams 中的生命週期管理方案</span><span class="sxs-lookup"><span data-stu-id="7bf84-185">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)
