---
title: 在 Microsoft Teams 中封存或刪除團隊
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: 本文將瞭解如何在 Microsoft Teams 中存檔或永久刪除團隊。
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
ms.openlocfilehash: da2d330986ca2fd924df75e0fcae6fc4388c5d48
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120835"
---
<a name="archive-or-delete-a-team-in-microsoft-teams"></a><span data-ttu-id="007d8-103">在 Microsoft Teams 中封存或刪除團隊</span><span class="sxs-lookup"><span data-stu-id="007d8-103">Archive or delete a team in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="007d8-104">經過一段時間後，在 Microsoft Teams 中建立的小組可能不再使用，或是您可能想要在專案結束時封存或刪除小組。</span><span class="sxs-lookup"><span data-stu-id="007d8-104">Over time, a team created in Microsoft Teams might fall out of use or you might want to archive or delete a team at the end of a project.</span></span> <span data-ttu-id="007d8-105">如果您是 Microsoft Teams 的系統管理員，請按照本文所述的步驟封存或刪除不再需要的小組。</span><span class="sxs-lookup"><span data-stu-id="007d8-105">If you're a Microsoft Teams admin, follow the steps in this article to archive or delete a team that's no longer needed.</span></span>

<span data-ttu-id="007d8-106">當您封存小組時，該小組的所有活動都會停止。</span><span class="sxs-lookup"><span data-stu-id="007d8-106">When you archive a team, all activity for that team ceases.</span></span> <span data-ttu-id="007d8-107">封存小組也會封存小組的私人頻道及其相關網站集合。</span><span class="sxs-lookup"><span data-stu-id="007d8-107">Archiving a team also archives private channels in the team and their associated site collections.</span></span>  <span data-ttu-id="007d8-108">但是，您仍然可以新增或移除成員、更新角色，而且仍然可以在標準和私人頻道、檔案、聊天中檢視所有的小組活動。</span><span class="sxs-lookup"><span data-stu-id="007d8-108">However, you can still add or remove members and update roles and you can still view all the team activity in standard and private channels, files, and chats.</span></span>

<span data-ttu-id="007d8-109">當您刪除小組時，也會刪除標準和私人頻道 (以及相關聯的網站集合)、檔案、聊天中的小組活動。</span><span class="sxs-lookup"><span data-stu-id="007d8-109">When you delete a team, team activity in standard and private channels (and associated site collections), files, and chats is also deleted.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="007d8-110">封存的小組可以重新啟用，但是您無法直接還原已刪除的小組。</span><span class="sxs-lookup"><span data-stu-id="007d8-110">Archived teams can be reactivated, but you can’t directly restore a team that has been deleted.</span></span> <span data-ttu-id="007d8-111">請先考慮封存小組，並延後刪除，直到確定您不再需要小組。</span><span class="sxs-lookup"><span data-stu-id="007d8-111">Consider archiving the team first, and postpone the deletion until you're sure that you no longer need the team.</span></span>

## <a name="archive-a-team"></a><span data-ttu-id="007d8-112">封存小組</span><span class="sxs-lookup"><span data-stu-id="007d8-112">Archive a team</span></span>

<span data-ttu-id="007d8-113">按照這些步驟以封存小組。</span><span class="sxs-lookup"><span data-stu-id="007d8-113">Follow these steps to archive a team.</span></span> <span data-ttu-id="007d8-114">您必須是 Teams 服務系統管理員才能進行這些變更。</span><span class="sxs-lookup"><span data-stu-id="007d8-114">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="007d8-115">請參閱[使用 Teams 系統管理員角色來管理 Teams](./using-admin-roles.md)，以了解取得系統管理員角色和權限。</span><span class="sxs-lookup"><span data-stu-id="007d8-115">See [Use Teams administrator roles to manage Teams](./using-admin-roles.md) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="007d8-116">在系統管理中心中，選取 **Teams**。</span><span class="sxs-lookup"><span data-stu-id="007d8-116">In the admin center, select **Teams**.</span></span>
2. <span data-ttu-id="007d8-117">按一下小組名稱以選取小組。</span><span class="sxs-lookup"><span data-stu-id="007d8-117">Select a team by clicking the team name.</span></span>
3. <span data-ttu-id="007d8-118">選取 [封存]。</span><span class="sxs-lookup"><span data-stu-id="007d8-118">Select **Archive**.</span></span> <span data-ttu-id="007d8-119">將會出現下列訊息。</span><span class="sxs-lookup"><span data-stu-id="007d8-119">The following message will appear.</span></span>

    ![螢幕擷取畫面：Teams 封存訊息](media/teams-archive-message.png)

4. <span data-ttu-id="007d8-121">若要防止人員編輯與小組相關聯的 SharePoint 網站和 Wiki 選項卡中的內容，請選取將 **SharePoint 網站** 設定為小組成員的唯讀。</span><span class="sxs-lookup"><span data-stu-id="007d8-121">To prevent people from editing the content in the SharePoint site and Wiki tab associated with the team, select **Make the SharePoint site read-only for team members**.</span></span> <span data-ttu-id="007d8-122"> (Teams 擁有者仍然可以編輯此內容。) </span><span class="sxs-lookup"><span data-stu-id="007d8-122">(Teams owners will still be able to edit this content.)</span></span>
5. <span data-ttu-id="007d8-123">選取 [封存] 以封存小組。</span><span class="sxs-lookup"><span data-stu-id="007d8-123">Select **Archive** to archive the team.</span></span> <span data-ttu-id="007d8-124">小組的狀態會變更為 [已封存]。</span><span class="sxs-lookup"><span data-stu-id="007d8-124">The team’s status will change to **Archived**.</span></span>

## <a name="make-an-archived-team-active"></a><span data-ttu-id="007d8-125">讓封存的小組成為使用中</span><span class="sxs-lookup"><span data-stu-id="007d8-125">Make an archived team active</span></span>

<span data-ttu-id="007d8-126">按照下列步驟，讓封存的小組成為使用中。</span><span class="sxs-lookup"><span data-stu-id="007d8-126">Follow these steps to make an archived team active again.</span></span>

1. <span data-ttu-id="007d8-127">在系統管理中心中，選取 **Teams**。</span><span class="sxs-lookup"><span data-stu-id="007d8-127">In the admin center, select **Teams**.</span></span>
2. <span data-ttu-id="007d8-128">按一下小組名稱以選取小組。</span><span class="sxs-lookup"><span data-stu-id="007d8-128">Select a team by clicking the team name.</span></span>
3. <span data-ttu-id="007d8-129">選取 [解除封存]。</span><span class="sxs-lookup"><span data-stu-id="007d8-129">Select **Unarchive**.</span></span> <span data-ttu-id="007d8-130">小組的狀態會變更為 [使用中]。</span><span class="sxs-lookup"><span data-stu-id="007d8-130">The team’s status will change to **Active**.</span></span>

## <a name="delete-a-team"></a><span data-ttu-id="007d8-131">刪除小組</span><span class="sxs-lookup"><span data-stu-id="007d8-131">Delete a team</span></span>

<span data-ttu-id="007d8-132">如果未來不再需要小組，您可以將它刪除，而不只是封存。</span><span class="sxs-lookup"><span data-stu-id="007d8-132">If the team will not be required in the future, then you can delete it rather than archiving it.</span></span> <span data-ttu-id="007d8-133">按照下列步驟刪除小組。</span><span class="sxs-lookup"><span data-stu-id="007d8-133">Follow these steps to delete a team.</span></span>

1.  <span data-ttu-id="007d8-134">在系統管理中心中，選取 **Teams**。</span><span class="sxs-lookup"><span data-stu-id="007d8-134">In the admin center, select **Teams**.</span></span>
2.  <span data-ttu-id="007d8-135">按一下小組名稱以選取小組。</span><span class="sxs-lookup"><span data-stu-id="007d8-135">Select a team by clicking the team name.</span></span>
3.  <span data-ttu-id="007d8-136">選取 [刪除]。</span><span class="sxs-lookup"><span data-stu-id="007d8-136">Select **Delete**.</span></span> <span data-ttu-id="007d8-137">將會出現確認訊息。</span><span class="sxs-lookup"><span data-stu-id="007d8-137">A confirmation message will appear.</span></span>
4.  <span data-ttu-id="007d8-138">選取 [刪除] 以永久刪除小組。</span><span class="sxs-lookup"><span data-stu-id="007d8-138">Select **Delete** to permanently delete the team.</span></span>

## <a name="restore-a-deleted-team"></a><span data-ttu-id="007d8-139">還原刪除的小組</span><span class="sxs-lookup"><span data-stu-id="007d8-139">Restore a deleted team</span></span>

<span data-ttu-id="007d8-140">請遵循下列步驟還原已刪除的團隊，還原與小組相關聯的 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="007d8-140">Follow these steps to restore a deleted team by restoring the Microsoft 365 group that's associated with the team.</span></span> <span data-ttu-id="007d8-141">還原小組的 Microsoft 365 群組會還原小組內容，包括定位停駐點、標準頻道和私人頻道及其相關聯的網站集合。</span><span class="sxs-lookup"><span data-stu-id="007d8-141">Restoring the Microsoft 365 group for a team restores team content, including tabs, standard channels, and private channels and their associated site collections.</span></span>

<span data-ttu-id="007d8-142">根據預設，已刪除的 Microsoft 365 群組會保留 30 天。</span><span class="sxs-lookup"><span data-stu-id="007d8-142">By default, a deleted Microsoft 365 group is retained for 30 days.</span></span> <span data-ttu-id="007d8-143">此 30 天期間稱為「虛刪除」，因為您可還原該群組。</span><span class="sxs-lookup"><span data-stu-id="007d8-143">This 30-day period is called "soft-delete" because you can restore the group.</span></span> <span data-ttu-id="007d8-144">若要深入瞭解，請參閱 [還原已刪除的群組](/microsoft-365/admin/create-groups/restore-deleted-group)。</span><span class="sxs-lookup"><span data-stu-id="007d8-144">To learn more, see [Restore a deleted Group](/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

### <a name="install-the-azureadpreview-module"></a><span data-ttu-id="007d8-145">安裝 AzureADPreview 模組</span><span class="sxs-lookup"><span data-stu-id="007d8-145">Install the AzureADPreview module</span></span>

1. <span data-ttu-id="007d8-146">以系統管理員身分開啟 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="007d8-146">Open Windows PowerShell as an admin.</span></span>
2. <span data-ttu-id="007d8-147">如果您已安裝舊版 AzureADPreview 模組或 AzureAD 模組，請執行下列其中一項操作將其解除安裝：</span><span class="sxs-lookup"><span data-stu-id="007d8-147">If you have an earlier version of the AzureADPreview module installed or the AzureAD module installed, uninstall it by running one of the following:</span></span>

    ```PowerShell
    Uninstall-Module AzureADPreview
    ```

    ```PowerShell
    Uninstall-Module AzureAD
    ```
3. <span data-ttu-id="007d8-148">執行以下命令安裝最新版 AzureADPreview 模組：</span><span class="sxs-lookup"><span data-stu-id="007d8-148">Install the latest version of the AzureADPreview module by running the following:</span></span>

    ```PowerShell
    Install-Module AzureADPreview
    ```

### <a name="restore-the-deleted-microsoft-365-group"></a><span data-ttu-id="007d8-149">還原已刪除的 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="007d8-149">Restore the deleted Microsoft 365 group</span></span>

1. <span data-ttu-id="007d8-150">執行下列命令連線到 Azure AD：</span><span class="sxs-lookup"><span data-stu-id="007d8-150">Connect to Azure AD by running the following:</span></span>
    ```PowerShell
    Connect-AzureAD
    ```
    <span data-ttu-id="007d8-151">當您看到提示時，使用您的系統管理員帳戶和密碼登入。</span><span class="sxs-lookup"><span data-stu-id="007d8-151">When you're prompted, sign in using your admin account and password.</span></span>  
2. <span data-ttu-id="007d8-152">請執行下列操作，以顯示仍在 30 天保留期間內的所有 Microsoft 365 軟體刪除群組清單。</span><span class="sxs-lookup"><span data-stu-id="007d8-152">Run the following to display a list of all soft-deleted Microsoft 365 groups that are still within the 30-day retention period.</span></span> <span data-ttu-id="007d8-153">如果有大量群組，請使用 **-All $True** 參數。</span><span class="sxs-lookup"><span data-stu-id="007d8-153">Use the **-All $True** parameter if you have a lot of groups.</span></span>
    ```PowerShell
    Get-AzureADMSDeletedGroup
    ```
3. <span data-ttu-id="007d8-154">尋找您要還原的群組，然後記下識別碼。</span><span class="sxs-lookup"><span data-stu-id="007d8-154">Find the group that you want to restore, and then make a note of the Id.</span></span>
4. <span data-ttu-id="007d8-155">執行下列命令來還原群組，其中 [Id] 是群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="007d8-155">Run the following to restore the group, where [Id] is the group Id.</span></span>
    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  <span data-ttu-id="007d8-156">執行下列命令來確認群組還原是否成功，其中 [Id] 是群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="007d8-156">Run the following to verify the group was successfully restored, where [Id] is the group Id.</span></span>
    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    <span data-ttu-id="007d8-157">完成還原程序最多可能需要 24 小時，之後就會在 Teams 中顯示小組以及小組相關聯的內容 (包括索引標籤和頻道) 。</span><span class="sxs-lookup"><span data-stu-id="007d8-157">It can take up to 24 hours for the restore process to complete, after which the team and content associated with the team, including tabs and channels, is displayed in Teams.</span></span>