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
description: 在本文中，您將瞭解如何在 Microsoft 團隊中封存或永久刪除小組。
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
ms.openlocfilehash: 334ecfdc387f1b3dd6d7f1312b90d81aee320df0
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582760"
---
<a name="archive-or-delete-a-team-in-microsoft-teams"></a><span data-ttu-id="5ddcb-103">在 Microsoft Teams 中封存或刪除團隊</span><span class="sxs-lookup"><span data-stu-id="5ddcb-103">Archive or delete a team in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="5ddcb-104">經過一段時間後，在 Microsoft Teams 中建立的小組可能不再使用，或是您可能想要在專案結束時封存或刪除小組。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-104">Over time, a team created in Microsoft Teams might fall out of use or you might want to archive or delete a team at the end of a project.</span></span> <span data-ttu-id="5ddcb-105">如果您是 Microsoft Teams 的系統管理員，請按照本文所述的步驟封存或刪除不再需要的小組。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-105">If you're a Microsoft Teams admin, follow the steps in this article to archive or delete a team that's no longer needed.</span></span>

<span data-ttu-id="5ddcb-106">當您封存小組時，該小組的所有活動都會停止。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-106">When you archive a team, all activity for that team ceases.</span></span> <span data-ttu-id="5ddcb-107">封存小組也會封存小組的私人頻道及其相關網站集合。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-107">Archiving a team also archives private channels in the team and their associated site collections.</span></span>  <span data-ttu-id="5ddcb-108">但是，您仍然可以新增或移除成員、更新角色，而且仍然可以在標準和私人頻道、檔案、聊天中檢視所有的小組活動。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-108">However, you can still add or remove members and update roles and you can still view all the team activity in standard and private channels, files, and chats.</span></span>

<span data-ttu-id="5ddcb-109">當您刪除小組時，也會刪除標準和私人頻道 (以及相關聯的網站集合)、檔案、聊天中的小組活動。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-109">When you delete a team, team activity in standard and private channels (and associated site collections), files, and chats is also deleted.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5ddcb-110">封存的小組可以重新啟用，但是您無法直接還原已刪除的小組。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-110">Archived teams can be reactivated, but you can’t directly restore a team that has been deleted.</span></span> <span data-ttu-id="5ddcb-111">請先考慮封存小組，並延後刪除，直到確定您不再需要小組。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-111">Consider archiving the team first, and postpone the deletion until you're sure that you no longer need the team.</span></span>

## <a name="archive-a-team"></a><span data-ttu-id="5ddcb-112">封存小組</span><span class="sxs-lookup"><span data-stu-id="5ddcb-112">Archive a team</span></span>

<span data-ttu-id="5ddcb-113">按照這些步驟以封存小組。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-113">Follow these steps to archive a team.</span></span> <span data-ttu-id="5ddcb-114">您必須是團隊服務管理員，才能進行這些變更。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-114">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="5ddcb-115">請參閱[使用團隊管理員角色管理團隊](https://docs.microsoft.com/microsoftteams/using-admin-roles)，瞭解如何取得管理員角色和許可權。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-115">See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="5ddcb-116">在系統管理中心中，選取 [**團隊**]。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-116">In the admin center, select **Teams**.</span></span>
2. <span data-ttu-id="5ddcb-117">按一下小組名稱以選取小組。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-117">Select a team by clicking the team name.</span></span>
3. <span data-ttu-id="5ddcb-118">選取 [封存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-118">Select **Archive**.</span></span> <span data-ttu-id="5ddcb-119">將會出現下列訊息。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-119">The following message will appear.</span></span>

    ![螢幕擷取畫面：Teams 封存訊息](media/teams-archive-message.png)

4. <span data-ttu-id="5ddcb-121">若要防止使用者編輯 SharePoint 網站與小組相關的 [Wiki] 索引標籤中的內容，請選取 **[將 sharepoint 網站設為唯讀] 給小組成員**。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-121">To prevent people from editing the content in the SharePoint site and Wiki tab associated with the team, select **Make the SharePoint site read-only for team members**.</span></span> <span data-ttu-id="5ddcb-122"> (團隊擁有者仍能編輯此內容。 ) </span><span class="sxs-lookup"><span data-stu-id="5ddcb-122">(Teams owners will still be able to edit this content.)</span></span>
5. <span data-ttu-id="5ddcb-123">選取 [封存]\*\*\*\* 以封存小組。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-123">Select **Archive** to archive the team.</span></span> <span data-ttu-id="5ddcb-124">小組的狀態會變更為 [已封存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-124">The team’s status will change to **Archived**.</span></span>

## <a name="make-an-archived-team-active"></a><span data-ttu-id="5ddcb-125">讓封存的小組成為使用中</span><span class="sxs-lookup"><span data-stu-id="5ddcb-125">Make an archived team active</span></span>

<span data-ttu-id="5ddcb-126">按照下列步驟，讓封存的小組成為使用中。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-126">Follow these steps to make an archived team active again.</span></span>

1. <span data-ttu-id="5ddcb-127">在系統管理中心中，選取 [**團隊**]。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-127">In the admin center, select **Teams**.</span></span>
2. <span data-ttu-id="5ddcb-128">按一下小組名稱以選取小組。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-128">Select a team by clicking the team name.</span></span>
3. <span data-ttu-id="5ddcb-129">選取 [解除封存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-129">Select **Unarchive**.</span></span> <span data-ttu-id="5ddcb-130">小組的狀態會變更為 [使用中]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-130">The team’s status will change to **Active**.</span></span>

## <a name="delete-a-team"></a><span data-ttu-id="5ddcb-131">刪除小組</span><span class="sxs-lookup"><span data-stu-id="5ddcb-131">Delete a team</span></span>

<span data-ttu-id="5ddcb-132">如果未來不再需要小組，您可以將它刪除，而不只是封存。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-132">If the team will not be required in the future, then you can delete it rather than archiving it.</span></span> <span data-ttu-id="5ddcb-133">按照下列步驟刪除小組。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-133">Follow these steps to delete a team.</span></span>

1.  <span data-ttu-id="5ddcb-134">在系統管理中心中，選取 [**團隊**]。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-134">In the admin center, select **Teams**.</span></span>
2.  <span data-ttu-id="5ddcb-135">按一下小組名稱以選取小組。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-135">Select a team by clicking the team name.</span></span>
3.  <span data-ttu-id="5ddcb-136">選取 [刪除]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-136">Select **Delete**.</span></span> <span data-ttu-id="5ddcb-137">將會出現確認訊息。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-137">A confirmation message will appear.</span></span>
4.  <span data-ttu-id="5ddcb-138">選取 [刪除]\*\*\*\* 以永久刪除小組。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-138">Select **Delete** to permanently delete the team.</span></span>

## <a name="restore-a-deleted-team"></a><span data-ttu-id="5ddcb-139">還原刪除的小組</span><span class="sxs-lookup"><span data-stu-id="5ddcb-139">Restore a deleted team</span></span>

<span data-ttu-id="5ddcb-140">若要還原已刪除的小組，請執行下列步驟，還原與小組相關聯的 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-140">Follow these steps to restore a deleted team by restoring the Microsoft 365 group that's associated with the team.</span></span> <span data-ttu-id="5ddcb-141">還原小組的 Microsoft 365 群組會復原小組內容，包括索引標籤、標準通道、私人頻道以及其相關的網站集合。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-141">Restoring the Microsoft 365 group for a team restores team content, including tabs, standard channels, and private channels and their associated site collections.</span></span>

<span data-ttu-id="5ddcb-142">根據預設，已刪除的 Microsoft 365 群組會保留30天。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-142">By default, a deleted Microsoft 365 group is retained for 30 days.</span></span> <span data-ttu-id="5ddcb-143">此 30 天期間稱為「虛刪除」，因為您可還原該群組。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-143">This 30-day period is called "soft-delete" because you can restore the group.</span></span> <span data-ttu-id="5ddcb-144">若要深入瞭解，請參閱[還原已刪除的群組](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-144">To learn more, see [Restore a deleted Group](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

### <a name="install-the-azureadpreview-module"></a><span data-ttu-id="5ddcb-145">安裝 AzureADPreview 模組</span><span class="sxs-lookup"><span data-stu-id="5ddcb-145">Install the AzureADPreview module</span></span>

1. <span data-ttu-id="5ddcb-146">以系統管理員身分開啟 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-146">Open Windows PowerShell as an admin.</span></span>
2. <span data-ttu-id="5ddcb-147">如果您已安裝舊版 AzureADPreview 模組或 AzureAD 模組，請執行下列其中一項操作將其解除安裝：</span><span class="sxs-lookup"><span data-stu-id="5ddcb-147">If you have an earlier version of the AzureADPreview module installed or the AzureAD module installed, uninstall it by running one of the following:</span></span>

    ```PowerShell
    Uninstall-Module AzureADPreview
    ```

    ```PowerShell
    Uninstall-Module AzureAD
    ```
3. <span data-ttu-id="5ddcb-148">執行以下命令安裝最新版 AzureADPreview 模組：</span><span class="sxs-lookup"><span data-stu-id="5ddcb-148">Install the latest version of the AzureADPreview module by running the following:</span></span>

    ```PowerShell
    Install-Module AzureADPreview
    ```

### <a name="restore-the-deleted-microsoft-365-group"></a><span data-ttu-id="5ddcb-149">還原已刪除的 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="5ddcb-149">Restore the deleted Microsoft 365 group</span></span>

1. <span data-ttu-id="5ddcb-150">執行下列命令連線到 Azure AD：</span><span class="sxs-lookup"><span data-stu-id="5ddcb-150">Connect to Azure AD by running the following:</span></span>
    ```PowerShell
    Connect-AzureAD
    ```
    <span data-ttu-id="5ddcb-151">當您看到提示時，使用您的系統管理員帳戶和密碼登入。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-151">When you're prompted, sign in using your admin account and password.</span></span>  
2. <span data-ttu-id="5ddcb-152">執行下列動作，以顯示仍在30天保留期間內的所有虛刪除 Microsoft 365 群組清單。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-152">Run the following to display a list of all soft-deleted Microsoft 365 groups that are still within the 30-day retention period.</span></span> <span data-ttu-id="5ddcb-153">如果有大量群組，請使用 **-All $True** 參數。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-153">Use the **-All $True** parameter if you have a lot of groups.</span></span>
    ```PowerShell
    Get-AzureADMSDeletedGroup
    ```
3. <span data-ttu-id="5ddcb-154">尋找您要還原的群組，然後記下識別碼。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-154">Find the group that you want to restore, and then make a note of the Id.</span></span>
4. <span data-ttu-id="5ddcb-155">執行下列命令來還原群組，其中 [Id] 是群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-155">Run the following to restore the group, where [Id] is the group Id.</span></span>
    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  <span data-ttu-id="5ddcb-156">執行下列命令來確認群組還原是否成功，其中 [Id] 是群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-156">Run the following to verify the group was successfully restored, where [Id] is the group Id.</span></span>
    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    <span data-ttu-id="5ddcb-157">完成還原程序最多可能需要 24 小時，之後就會在 Teams 中顯示小組以及小組相關聯的內容 (包括索引標籤和頻道) 。</span><span class="sxs-lookup"><span data-stu-id="5ddcb-157">It can take up to 24 hours for the restore process to complete, after which the team and content associated with the team, including tabs and channels, is displayed in Teams.</span></span>
