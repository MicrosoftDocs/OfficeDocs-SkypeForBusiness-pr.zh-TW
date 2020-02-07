---
title: 在 Microsoft 團隊中封存或刪除小組
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: 瞭解如何封存或永久刪除小組。
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e367fe85f1af35391fa00b4a416b6e796383d962
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826401"
---
<a name="archive-or-delete-a-team-in-microsoft-teams"></a><span data-ttu-id="4714a-103">在 Microsoft 團隊中封存或刪除小組</span><span class="sxs-lookup"><span data-stu-id="4714a-103">Archive or delete a team in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="4714a-104">隨著時間的推移，在 Microsoft 團隊中建立的小組可能不在使用中，或者您可能想要在專案結束時封存或刪除小組。</span><span class="sxs-lookup"><span data-stu-id="4714a-104">Over time, a team created in Microsoft Teams might fall out of use or you might want to archive or delete a team at the end of a project.</span></span> <span data-ttu-id="4714a-105">如果您是 Microsoft 團隊管理員，請按照本文所述的步驟來封存或刪除不再需要的小組。</span><span class="sxs-lookup"><span data-stu-id="4714a-105">If you're a Microsoft Teams admin, follow the steps in this article to archive or delete a team that's no longer needed.</span></span>

<span data-ttu-id="4714a-106">當您封存小組時，該小組的所有活動都會停止。</span><span class="sxs-lookup"><span data-stu-id="4714a-106">When you archive a team, all activity for that team ceases.</span></span> <span data-ttu-id="4714a-107">封存小組也會將小組及其相關網站集合中的私人頻道存檔。</span><span class="sxs-lookup"><span data-stu-id="4714a-107">Archiving a team also archives private channels in the team and their associated site collections.</span></span>  <span data-ttu-id="4714a-108">不過，您仍然可以新增或移除成員並更新角色，您仍然可以在標準和私人通道、檔案和聊天中查看所有團隊活動。</span><span class="sxs-lookup"><span data-stu-id="4714a-108">However, you can still add or remove members and update roles and you can still view all the team activity in standard and private channels, files, and chats.</span></span>

<span data-ttu-id="4714a-109">刪除小組時，也會刪除標準和專用頻道（以及相關聯的網站集合）、檔案和聊天中的小組活動。</span><span class="sxs-lookup"><span data-stu-id="4714a-109">When you delete a team, team activity in standard and private channels (and associated site collections), files, and chats is also deleted.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4714a-110">封存的團隊可以重新啟用，但您無法直接還原已刪除的小組。</span><span class="sxs-lookup"><span data-stu-id="4714a-110">Archived teams can be reactivated, but you can’t directly restore a team that has been deleted.</span></span> <span data-ttu-id="4714a-111">考慮先封存團隊，然後推遲刪除，直到您確定不再需要團隊為止。</span><span class="sxs-lookup"><span data-stu-id="4714a-111">Consider archiving the team first, and postpone the deletion until you're sure that you no longer need the team.</span></span>

## <a name="archive-a-team"></a><span data-ttu-id="4714a-112">封存團隊</span><span class="sxs-lookup"><span data-stu-id="4714a-112">Archive a team</span></span>

<span data-ttu-id="4714a-113">請依照下列步驟封存小組。</span><span class="sxs-lookup"><span data-stu-id="4714a-113">Follow these steps to archive a team.</span></span>

1. <span data-ttu-id="4714a-114">在 Microsoft [團隊管理中心] 中，選取 [**團隊**]。</span><span class="sxs-lookup"><span data-stu-id="4714a-114">In the Microsoft Teams admin center, select **Teams**.</span></span>
2. <span data-ttu-id="4714a-115">按一下團隊名稱以選取團隊。</span><span class="sxs-lookup"><span data-stu-id="4714a-115">Select a team by clicking the team name.</span></span>
3. <span data-ttu-id="4714a-116">選取 **[** 封存]。</span><span class="sxs-lookup"><span data-stu-id="4714a-116">Select **Archive**.</span></span> <span data-ttu-id="4714a-117">隨後便會出現下列訊息。</span><span class="sxs-lookup"><span data-stu-id="4714a-117">The following message will appear.</span></span>

    ![[小組封存] 訊息的螢幕擷取畫面](media/teams-archive-message.png)

4. <span data-ttu-id="4714a-119">如果您想要將小組的 SharePoint 網站設為唯讀，請選取核取方塊。</span><span class="sxs-lookup"><span data-stu-id="4714a-119">If you would like to make the SharePoint site for the team read-only, select the check box.</span></span>
5. <span data-ttu-id="4714a-120">選取 **[** 封存] 以封存小組。</span><span class="sxs-lookup"><span data-stu-id="4714a-120">Select **Archive** to archive the team.</span></span> <span data-ttu-id="4714a-121">團隊的狀態將會變更為 [已**存檔**]。</span><span class="sxs-lookup"><span data-stu-id="4714a-121">The team’s status will change to **Archived**.</span></span>

## <a name="make-an-archived-team-active"></a><span data-ttu-id="4714a-122">使封存的小組成為使用中狀態</span><span class="sxs-lookup"><span data-stu-id="4714a-122">Make an archived team active</span></span>

<span data-ttu-id="4714a-123">請依照下列步驟，讓封存的小組再次生效。</span><span class="sxs-lookup"><span data-stu-id="4714a-123">Follow these steps to make an archived team active again.</span></span>

1. <span data-ttu-id="4714a-124">在 Microsoft [團隊管理中心] 中，選取 [**團隊**]。</span><span class="sxs-lookup"><span data-stu-id="4714a-124">In the Microsoft Teams admin center, select **Teams**.</span></span>
2. <span data-ttu-id="4714a-125">按一下團隊名稱以選取團隊。</span><span class="sxs-lookup"><span data-stu-id="4714a-125">Select a team by clicking the team name.</span></span>
3. <span data-ttu-id="4714a-126">選取 [ **Unarchive**]。</span><span class="sxs-lookup"><span data-stu-id="4714a-126">Select **Unarchive**.</span></span> <span data-ttu-id="4714a-127">團隊的狀態將會**變更為 [作用中]**。</span><span class="sxs-lookup"><span data-stu-id="4714a-127">The team’s status will change to **Active**.</span></span>

## <a name="delete-a-team"></a><span data-ttu-id="4714a-128">刪除小組</span><span class="sxs-lookup"><span data-stu-id="4714a-128">Delete a team</span></span>

<span data-ttu-id="4714a-129">如果將來不需要該小組，您可以將它刪除，而不是將它封存。</span><span class="sxs-lookup"><span data-stu-id="4714a-129">If the team will not be required in the future, then you can delete it rather than archiving it.</span></span> <span data-ttu-id="4714a-130">請依照下列步驟刪除小組。</span><span class="sxs-lookup"><span data-stu-id="4714a-130">Follow these steps to delete a team.</span></span>

1.  <span data-ttu-id="4714a-131">在 Microsoft [團隊管理中心] 中，選取 [**團隊**]。</span><span class="sxs-lookup"><span data-stu-id="4714a-131">In the Microsoft Teams admin center, select **Teams**.</span></span>
2.  <span data-ttu-id="4714a-132">按一下團隊名稱以選取團隊。</span><span class="sxs-lookup"><span data-stu-id="4714a-132">Select a team by clicking the team name.</span></span>
3.  <span data-ttu-id="4714a-133">選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="4714a-133">Select **Delete**.</span></span> <span data-ttu-id="4714a-134">隨即會出現一則確認訊息。</span><span class="sxs-lookup"><span data-stu-id="4714a-134">A confirmation message will appear.</span></span>
4.  <span data-ttu-id="4714a-135">選取 [**刪除**] 以永久刪除該小組。</span><span class="sxs-lookup"><span data-stu-id="4714a-135">Select **Delete** to permanently delete the team.</span></span>

## <a name="restore-a-deleted-team"></a><span data-ttu-id="4714a-136">還原已刪除的小組</span><span class="sxs-lookup"><span data-stu-id="4714a-136">Restore a deleted team</span></span>

<span data-ttu-id="4714a-137">若要還原已刪除的小組，請執行下列步驟，還原與小組相關聯的 Office 365 群組。</span><span class="sxs-lookup"><span data-stu-id="4714a-137">Follow these steps to restore a deleted team by restoring the Office 365 group that's associated with the team.</span></span> <span data-ttu-id="4714a-138">還原小組的 Office 365 群組、還原小組內容，包括索引標籤、標準通道、專用通道及其相關網站集合。</span><span class="sxs-lookup"><span data-stu-id="4714a-138">Restoring the Office 365 group for a team, restores team content, including tabs, standard channels, and private channels and their associated site collections.</span></span>

<span data-ttu-id="4714a-139">根據預設，已刪除的 Office 365 群組會保留30天。</span><span class="sxs-lookup"><span data-stu-id="4714a-139">By default, a deleted Office 365 group is retained for 30 days.</span></span> <span data-ttu-id="4714a-140">此30天期間稱為「虛刪除」，因為您可以還原該群組。</span><span class="sxs-lookup"><span data-stu-id="4714a-140">This 30-day period is called "soft-delete" because you can restore the group.</span></span> <span data-ttu-id="4714a-141">若要深入瞭解，請參閱[還原已刪除的 Office 365 群組](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group)。</span><span class="sxs-lookup"><span data-stu-id="4714a-141">To learn more, see [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group).</span></span>

### <a name="install-the-azureadpreview-module"></a><span data-ttu-id="4714a-142">安裝 AzureADPreview 模組</span><span class="sxs-lookup"><span data-stu-id="4714a-142">Install the AzureADPreview module</span></span>

1. <span data-ttu-id="4714a-143">以系統管理員身分開啟 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4714a-143">Open Windows PowerShell as an admin.</span></span>
2. <span data-ttu-id="4714a-144">如果您已安裝舊版的 AzureADPreview 模組，或已安裝 AzureAD 模組，請執行下列其中一項操作以將它卸載：</span><span class="sxs-lookup"><span data-stu-id="4714a-144">If you have an earlier version of the AzureADPreview module installed or the AzureAD module installed, uninstall it by running one of the following:</span></span>

    ```PowerShell 
    Uninstall-Module AzureADPreview
    ```

    ```PowerShell
    Uninstall-Module AzureAD
    ```
3. <span data-ttu-id="4714a-145">若要安裝最新版本的 AzureADPreview 模組，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="4714a-145">Install the latest version of the AzureADPreview module by running the following:</span></span>

    ```PowerShell
    Install-Module AzureADPreview
    ```    

### <a name="restore-the-deleted-office-365-group"></a><span data-ttu-id="4714a-146">還原已刪除的 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="4714a-146">Restore the deleted Office 365 group</span></span>

1. <span data-ttu-id="4714a-147">若要連線到 Azure AD，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="4714a-147">Connect to Azure AD by running the following:</span></span>
    ```PowerShell
    Connect-AzureAD
    ```
    <span data-ttu-id="4714a-148">出現提示時，請使用您的系統管理員帳戶和密碼登入。</span><span class="sxs-lookup"><span data-stu-id="4714a-148">When you're prompted, sign in using your admin account and password.</span></span>  
2. <span data-ttu-id="4714a-149">執行下列動作，以顯示仍在30天保留期間內的所有虛刪除 Office 365 群組清單。</span><span class="sxs-lookup"><span data-stu-id="4714a-149">Run the following to display a list of all soft-deleted Office 365 groups that are still within the 30-day retention period.</span></span> <span data-ttu-id="4714a-150">如果您有許多群組，請使用 **-All $True**參數。</span><span class="sxs-lookup"><span data-stu-id="4714a-150">Use the **-All $True** parameter if you have a lot of groups.</span></span>
    ```PowerShell
    Get-AzureADMSDeletedGroup
    ``` 
3. <span data-ttu-id="4714a-151">找出您要還原的群組，然後記下 Id。</span><span class="sxs-lookup"><span data-stu-id="4714a-151">Find the group that you want to restore, and then make a note of the Id.</span></span>
4. <span data-ttu-id="4714a-152">執行下列動作來還原群組，其中 [Id] 是 [群組識別碼]。</span><span class="sxs-lookup"><span data-stu-id="4714a-152">Run the following to restore the group, where [Id] is the group Id.</span></span>
    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  <span data-ttu-id="4714a-153">執行下列動作以驗證群組已順利還原，其中 [Id] 是群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="4714a-153">Run the following to verify the group was successfully restored, where [Id] is the group Id.</span></span>
    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    <span data-ttu-id="4714a-154">完成還原程式最多可能需要24小時，之後，小組中就會顯示與小組相關的小組和內容，包括索引標籤和頻道。</span><span class="sxs-lookup"><span data-stu-id="4714a-154">It can take up to 24 hours for the restore process to complete, after which the team and content associated with the team, including tabs and channels, is displayed in Teams.</span></span>
