---
title: 在 Microsoft 團隊系統管理中心管理團隊
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: 瞭解如何在 Microsoft 團隊系統管理中心中查看或更新您的小組。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c205c8d3b4f57935c1882530815643a90357d1aa
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/29/2019
ms.locfileid: "36183858"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="a120a-103">在 Microsoft 團隊系統管理中心管理團隊</span><span class="sxs-lookup"><span data-stu-id="a120a-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================


## <a name="overview"></a><span data-ttu-id="a120a-104">概觀</span><span class="sxs-lookup"><span data-stu-id="a120a-104">Overview</span></span>

<span data-ttu-id="a120a-105">做為 IT 系統管理員, 您可能需要查看或更新貴組織已設定共同作業的小組, 或者您可能需要執行修正動作, 例如指派 ownerless 小組的擁有者。</span><span class="sxs-lookup"><span data-stu-id="a120a-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="a120a-106">您可以透過 Microsoft 團隊 PowerShell 模組和 Microsoft 團隊系統管理中心來管理組織中使用的團隊。</span><span class="sxs-lookup"><span data-stu-id="a120a-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="a120a-107">若要使用這兩種工具集的完整管理功能, 您應該確認您已獲指派下列其中一個角色:</span><span class="sxs-lookup"><span data-stu-id="a120a-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="a120a-108">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="a120a-108">Global Administrator</span></span>
- <span data-ttu-id="a120a-109">團隊服務管理員</span><span class="sxs-lookup"><span data-stu-id="a120a-109">Teams Service Administrator</span></span>

<span data-ttu-id="a120a-110">您可以在團隊中進一步瞭解如何[使用 Microsoft 團隊管理員角色來管理團隊](using-admin-roles.md), 並進一步瞭解如何使用 PowerShell Cmdlet 來管理[Microsoft 團隊 Cmdlet 參考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)中的團隊。</span><span class="sxs-lookup"><span data-stu-id="a120a-110">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="a120a-111">本文將為 Microsoft 團隊系統管理中心的小組提供管理工具的概覽。</span><span class="sxs-lookup"><span data-stu-id="a120a-111">This article provides an overview of the management tools for teams in the Microsoft Teams admin center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="a120a-112">團隊概覽格線</span><span class="sxs-lookup"><span data-stu-id="a120a-112">Teams overview grid</span></span>

<span data-ttu-id="a120a-113">小組的管理工具位於 Microsoft 團隊系統管理中心的 [**小組**] 節點底下。</span><span class="sxs-lookup"><span data-stu-id="a120a-113">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="a120a-114">(在系統管理中心中, 選取 [**團隊** > **管理團隊**])。每個團隊都受 Office 365 群組的支援, 而且這個節點提供已在貴組織中啟用 Microsoft 團隊的群組視圖。</span><span class="sxs-lookup"><span data-stu-id="a120a-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![[團隊概述] 格線的螢幕擷取畫面](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="a120a-116">格線會顯示下列屬性:</span><span class="sxs-lookup"><span data-stu-id="a120a-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="a120a-117">**團隊名稱**</span><span class="sxs-lookup"><span data-stu-id="a120a-117">**Team name**</span></span>
- <span data-ttu-id="a120a-118">[**頻道**]-團隊中所有頻道的計數, 包括預設的 [一般] 頻道。</span><span class="sxs-lookup"><span data-stu-id="a120a-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="a120a-119">**使用者**-使用者總數, 包括您租使用者的擁有者、來賓和成員。</span><span class="sxs-lookup"><span data-stu-id="a120a-119">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="a120a-120">[**擁有**者]-此小組的擁有者人數。</span><span class="sxs-lookup"><span data-stu-id="a120a-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="a120a-121">**來賓**-此團隊成員的 Azure ACTIVE Directory B2B 來賓使用者的計數。</span><span class="sxs-lookup"><span data-stu-id="a120a-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="a120a-122">**隱私權**-支援 Office 365 群組的可見度/AccessType。</span><span class="sxs-lookup"><span data-stu-id="a120a-122">**Privacy** - the Visibility/AccessType of the backing Office 365 group.</span></span>
- <span data-ttu-id="a120a-123">[**狀態**]-此小組的已存檔或活動狀態。</span><span class="sxs-lookup"><span data-stu-id="a120a-123">**Status** - the Archived or Active status for this team.</span></span>  <span data-ttu-id="a120a-124">進一步瞭解封存[或還原小組](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)中的團隊。</span><span class="sxs-lookup"><span data-stu-id="a120a-124">Learn more about archiving teams in the [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="a120a-125">**GroupID** -支援 Office 365 群組的唯一 GroupID</span><span class="sxs-lookup"><span data-stu-id="a120a-125">**GroupID** - the unique GroupID of the backing Office 365 group</span></span>
- <span data-ttu-id="a120a-126">**分類**-指派給支援 Office 365 群組的分類 (如果您的組織使用的話)。</span><span class="sxs-lookup"><span data-stu-id="a120a-126">**Classification** - the classification (if used in your organization) assigned to the backing Office 365 group.</span></span>  <span data-ttu-id="a120a-127">深入瞭解[貴組織中 Office 群組的建立分類](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="a120a-127">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="a120a-128">**描述**-針對支援的 Office 365 群組設定的描述</span><span class="sxs-lookup"><span data-stu-id="a120a-128">**Description** - the description set for the backing Office 365 group</span></span>

### <a name="search"></a><span data-ttu-id="a120a-129">檢索</span><span class="sxs-lookup"><span data-stu-id="a120a-129">Search</span></span>

<span data-ttu-id="a120a-130">搜尋目前支援字串「開始于」, 並搜尋 [**小組名稱**] 欄位。</span><span class="sxs-lookup"><span data-stu-id="a120a-130">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="a120a-131">編輯</span><span class="sxs-lookup"><span data-stu-id="a120a-131">Edit</span></span>

<span data-ttu-id="a120a-132">您可以從格線選取小組, 然後選取 [**編輯**] 按鈕, 以編輯群組和小組特定的設定。</span><span class="sxs-lookup"><span data-stu-id="a120a-132">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![[編輯團隊選項] 的螢幕擷取畫面](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="a120a-134">小組設定檔</span><span class="sxs-lookup"><span data-stu-id="a120a-134">Team profile</span></span>

<span data-ttu-id="a120a-135">您可以按一下團隊名稱, 從 [主要團隊概覽] 格線流覽至任何團隊的 [團隊個人檔案] 頁面。</span><span class="sxs-lookup"><span data-stu-id="a120a-135">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="a120a-136">[小組個人檔案] 頁面會顯示屬於小組 (及其後備 O365 群組), 以及小組的頻道與設定的成員、擁有者和來賓。</span><span class="sxs-lookup"><span data-stu-id="a120a-136">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="a120a-137">您可以從 [團隊設定檔] 頁面進行下列動作:</span><span class="sxs-lookup"><span data-stu-id="a120a-137">From the team profile page, you can:</span></span>

- <span data-ttu-id="a120a-138">新增或移除成員和擁有者。</span><span class="sxs-lookup"><span data-stu-id="a120a-138">Add or remove members and owners.</span></span>
- <span data-ttu-id="a120a-139">新增或移除頻道 (請注意, 您無法移除 [一般] 頻道)。</span><span class="sxs-lookup"><span data-stu-id="a120a-139">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="a120a-140">更新小組和群組設定。</span><span class="sxs-lookup"><span data-stu-id="a120a-140">Update team and group settings.</span></span>
 
![範例小組設定檔的螢幕擷取畫面](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="a120a-142">對團隊進行變更</span><span class="sxs-lookup"><span data-stu-id="a120a-142">Making changes to teams</span></span>

<span data-ttu-id="a120a-143">您可以變更團隊的下列元素:</span><span class="sxs-lookup"><span data-stu-id="a120a-143">You can change the following elements of a team:</span></span>
- <span data-ttu-id="a120a-144">**小組中的使用者**-您可以新增或移除成員, 以及提升或降級擁有者</span><span class="sxs-lookup"><span data-stu-id="a120a-144">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="a120a-145">**頻道**-您可以新增頻道, 或移除現有的頻道。</span><span class="sxs-lookup"><span data-stu-id="a120a-145">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="a120a-146">您無法刪除預設的「一般」通道, 一旦建立之後就只能編輯頻道名稱, 不能編輯描述。</span><span class="sxs-lookup"><span data-stu-id="a120a-146">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="a120a-147">**團隊名稱**</span><span class="sxs-lookup"><span data-stu-id="a120a-147">**Team name**</span></span>
- <span data-ttu-id="a120a-148">**團隊描述**</span><span class="sxs-lookup"><span data-stu-id="a120a-148">**Team description**</span></span>
- <span data-ttu-id="a120a-149">**小組隱私權**-公開或私人</span><span class="sxs-lookup"><span data-stu-id="a120a-149">**Team privacy** - public or private</span></span>
- <span data-ttu-id="a120a-150">**團隊分類**-由您的 Office 365 群組分類支援</span><span class="sxs-lookup"><span data-stu-id="a120a-150">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="a120a-151">**小組成員設定**-選取團隊成員設定</span><span class="sxs-lookup"><span data-stu-id="a120a-151">**Team member settings** - select team member settings</span></span>

## <a name="other-supported-changes-to-teams"></a><span data-ttu-id="a120a-152">小組所支援的其他變更</span><span class="sxs-lookup"><span data-stu-id="a120a-152">Other supported changes to teams</span></span>

- <span data-ttu-id="a120a-153">**刪除**-刪除小組是小組和對應 Office 365 群組的虛刪除。</span><span class="sxs-lookup"><span data-stu-id="a120a-153">**Delete** - Deleting a team is a soft-delete of the team and corresponding Office 365 group.</span></span>  <span data-ttu-id="a120a-154">若要還原錯誤刪除的小組, 請依照[還原已刪除的 Office 365 群組](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="a120a-154">To restore a mistakenly deleted team, follow the instructions at [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span></span>
- <span data-ttu-id="a120a-155">\*\*\*\* 封存封存小組會將小組放入 Microsoft 團隊中的唯讀模式。</span><span class="sxs-lookup"><span data-stu-id="a120a-155">**Archive** - Archiving a team puts the team into read-only mode within Microsoft Teams.</span></span>  <span data-ttu-id="a120a-156">做為管理員, 您可以透過管理入口網站代表您的組織來封存及 unarchive 小組。</span><span class="sxs-lookup"><span data-stu-id="a120a-156">As an admin, you can archive and unarchive teams on behalf of your organization via the admin portal.</span></span>


<span data-ttu-id="a120a-157">您對小組所做的變更會記錄下來。</span><span class="sxs-lookup"><span data-stu-id="a120a-157">The changes that you make to a team are logged.</span></span> <span data-ttu-id="a120a-158">如果您要修改群組設定 (變更名稱、描述、相片、隱私權、分類或團隊成員), 這些變更將會透過審核管線進行設定。</span><span class="sxs-lookup"><span data-stu-id="a120a-158">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="a120a-159">如果您要針對團隊特定設定執行動作, 您的變更將會在團隊的 [一般] 頻道中追蹤並設定為 [已設定]。</span><span class="sxs-lookup"><span data-stu-id="a120a-159">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="a120a-160">疑難排解</span><span class="sxs-lookup"><span data-stu-id="a120a-160">Troubleshooting</span></span>

<span data-ttu-id="a120a-161">**問題: 團隊概覽格線中缺少團隊**</span><span class="sxs-lookup"><span data-stu-id="a120a-161">**Issue: Teams missing from the Team Overview Grid**</span></span>

<span data-ttu-id="a120a-162">當您輸入 Microsoft 團隊系統管理中心時, 請在 [**團隊**] 選項下的 [團隊總覽] 格線清單中找不到某些團隊。</span><span class="sxs-lookup"><span data-stu-id="a120a-162">When you enter the Microsoft Teams admin center, under the **Teams** option some of your teams are missing from the listing in the Teams Overview Grid.</span></span>

<span data-ttu-id="a120a-163">**原因**: 當小組不正確 (或尚未) 由系統所分析, 可能會導致其無法辨識某個缺少的屬性時, 就會發生這個問題。</span><span class="sxs-lookup"><span data-stu-id="a120a-163">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="a120a-164">**解析度: 透過 MS Graph 將屬性手動設定為正確的值**</span><span class="sxs-lookup"><span data-stu-id="a120a-164">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="a120a-165">在查詢中, 使用「 \*\* [UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps) \*\* 」 Cmdlet 做為「**ExternalDirectoryObjectId**」屬性, 取代 **{GroupId}** , 以取得實際的 groupid, 您可以透過 Exchange Online powershell 取得該問題。</span><span class="sxs-lookup"><span data-stu-id="a120a-165">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="a120a-166">Access[圖形瀏覽器](https://developer.microsoft.com/en-us/graph/graph-explorer)</span><span class="sxs-lookup"><span data-stu-id="a120a-166">Access [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)</span></span>

2. <span data-ttu-id="a120a-167">在左側功能表中登入圖表資源管理器</span><span class="sxs-lookup"><span data-stu-id="a120a-167">Sign in to Graph Explorer on the left menu</span></span>

3. <span data-ttu-id="a120a-168">將查詢行變更為: PATCH > v 1.0 >https://graph.microsoft.com/v1.0/groups/{groupid}</span><span class="sxs-lookup"><span data-stu-id="a120a-168">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}</span></span>

4. <span data-ttu-id="a120a-169">在要求主體上加上下列值: {"resourceProvisioningOptions": ["團隊"]}</span><span class="sxs-lookup"><span data-stu-id="a120a-169">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}</span></span>

5. <span data-ttu-id="a120a-170">在右上方執行查詢。</span><span class="sxs-lookup"><span data-stu-id="a120a-170">Run the query on the top-right.</span></span>

6. <span data-ttu-id="a120a-171">確認團隊在 Microsoft 團隊系統管理中心中正確顯示-小組概述</span><span class="sxs-lookup"><span data-stu-id="a120a-171">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview</span></span>


## <a name="learn-more"></a><span data-ttu-id="a120a-172">瞭解更多資訊</span><span class="sxs-lookup"><span data-stu-id="a120a-172">Learn more</span></span>

[<span data-ttu-id="a120a-173">Microsoft 團隊 Cmdlet 參考</span><span class="sxs-lookup"><span data-stu-id="a120a-173">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="a120a-174">Microsoft 團隊中的管理員角色</span><span class="sxs-lookup"><span data-stu-id="a120a-174">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

