---
title: 管理 Microsoft 團隊中的團隊原則
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何使用及管理組織中的小組原則，以控制使用者可在團隊和頻道中執行的動作。
f1.keywords:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: 81192f405563c3f7eb023050745d68fcd4c067f9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41708319"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="1fcba-103">管理 Microsoft 團隊中的團隊原則</span><span class="sxs-lookup"><span data-stu-id="1fcba-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="1fcba-104">做為管理員，您可以使用 Microsoft 團隊中的小組原則來控制貴組織中的使用者可在團隊和頻道中進行的動作。</span><span class="sxs-lookup"><span data-stu-id="1fcba-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="1fcba-105">例如，您可以設定是否允許使用者在搜尋結果和小組圖庫中發現私人小組，以及是否允許使用者建立私人頻道。</span><span class="sxs-lookup"><span data-stu-id="1fcba-105">For example, you can set whether users are allowed to discover private teams in search results and in the team gallery and whether users are allowed to create private channels.</span></span>

<span data-ttu-id="1fcba-106">您可以移至 Microsoft 團隊系統管理中心的**小組** > **小組原則**，管理小組原則。</span><span class="sxs-lookup"><span data-stu-id="1fcba-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="1fcba-107">您可以使用全域（組織範圍預設值）原則，或建立自訂原則，並將它們指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="1fcba-107">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="1fcba-108">除非您建立並指派自訂原則，否則貴組織中的使用者會自動取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="1fcba-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="1fcba-109">您可以編輯全域原則，或建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="1fcba-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="1fcba-110">如果指派給使用者的是自訂原則，該原則會套用給使用者。</span><span class="sxs-lookup"><span data-stu-id="1fcba-110">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="1fcba-111">如果使用者未獲指派自訂原則，則全域原則會套用至使用者。</span><span class="sxs-lookup"><span data-stu-id="1fcba-111">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="1fcba-112">在您編輯全域原則或指派原則之後，變更才會生效24小時。</span><span class="sxs-lookup"><span data-stu-id="1fcba-112">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="1fcba-113">建立自訂團隊原則</span><span class="sxs-lookup"><span data-stu-id="1fcba-113">Create a custom teams policy</span></span>

1. <span data-ttu-id="1fcba-114">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊** > **小組原則**]。</span><span class="sxs-lookup"><span data-stu-id="1fcba-114">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="1fcba-115">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="1fcba-115">Click **Add**.</span></span>
3. <span data-ttu-id="1fcba-116">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="1fcba-116">Enter a name and description for the policy.</span></span>

    ![團隊原則設定的螢幕擷取畫面](media/teams-policies.png)
4. <span data-ttu-id="1fcba-118">選擇您想要的設定：</span><span class="sxs-lookup"><span data-stu-id="1fcba-118">Choose the settings that you want:</span></span>

- <span data-ttu-id="1fcba-119">**探索私人團隊**：<a name="discoverteams"> </a>開啟此設定可讓使用者在搜尋結果和小組圖庫中探索私人小組。</span><span class="sxs-lookup"><span data-stu-id="1fcba-119">**Discover private teams**:<a name="discoverteams"> </a> Turn on this setting to allow users to discover private teams in search results and in the team gallery.</span></span>
- <span data-ttu-id="1fcba-120">**建立私人頻道**： <a name="createchannels"></a>開啟此設定可允許使用者建立私人頻道。</span><span class="sxs-lookup"><span data-stu-id="1fcba-120">**Create private channels**: <a name="createchannels"> </a>Turn on this setting to allow users to create private channels.</span></span>

5. <span data-ttu-id="1fcba-121">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="1fcba-121">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="1fcba-122">編輯團隊原則</span><span class="sxs-lookup"><span data-stu-id="1fcba-122">Edit a teams policy</span></span>

<span data-ttu-id="1fcba-123">您可以編輯全域原則或您建立的任何自訂原則。</span><span class="sxs-lookup"><span data-stu-id="1fcba-123">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="1fcba-124">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊** > **小組原則**]。</span><span class="sxs-lookup"><span data-stu-id="1fcba-124">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="1fcba-125">按一下原則名稱左邊的，然後按一下 [**編輯**]，選取原則。</span><span class="sxs-lookup"><span data-stu-id="1fcba-125">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="1fcba-126">開啟或關閉您想要的設定，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="1fcba-126">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="1fcba-127">將自訂團隊原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="1fcba-127">Assign a custom teams policy to users</span></span>

<span data-ttu-id="1fcba-128">您可以使用 Microsoft 團隊系統管理中心，將自訂原則指派給一或多個使用者或商務用 Skype PowerShell 模組，將自訂原則指派給使用者群組，例如安全群組或通訊群組。</span><span class="sxs-lookup"><span data-stu-id="1fcba-128">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-teams-policy-to-a-user"></a><span data-ttu-id="1fcba-129">將自訂團隊原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="1fcba-129">Assign a custom teams policy to a user</span></span>

1. <span data-ttu-id="1fcba-130">在 Microsoft 團隊系統管理中心的左導覽中，前往 [**使用者**]，然後按一下使用者。</span><span class="sxs-lookup"><span data-stu-id="1fcba-130">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click  the user.</span></span>
2. <span data-ttu-id="1fcba-131">按一下 [**原則**]，然後在 [**指派的原則**] 旁，按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="1fcba-131">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="1fcba-132">在 [**團隊原則**] 底下，選取您要指派的原則，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="1fcba-132">Under **Teams policies**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="1fcba-133">若要一次將自訂團隊原則指派給多位使用者，請參閱[大量編輯團隊使用者設定](edit-user-settings-in-bulk.md)。</span><span class="sxs-lookup"><span data-stu-id="1fcba-133">To assign a custom teams policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="1fcba-134">或者，您也可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="1fcba-134">Or, you can also do the following:</span></span>

1. <span data-ttu-id="1fcba-135">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊** > **小組原則**]。</span><span class="sxs-lookup"><span data-stu-id="1fcba-135">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="1fcba-136">按一下原則名稱左方，選取原則。</span><span class="sxs-lookup"><span data-stu-id="1fcba-136">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="1fcba-137">選取 [**管理使用者**]。</span><span class="sxs-lookup"><span data-stu-id="1fcba-137">Select **Manage users**.</span></span>
4. <span data-ttu-id="1fcba-138">在 [**管理使用者**] 窗格中，依 [顯示名稱] 或 [使用者名稱] 搜尋使用者，選取名稱，然後選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="1fcba-138">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="1fcba-139">針對您要新增的每個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="1fcba-139">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="1fcba-140">完成新增使用者後，請按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="1fcba-140">When you're finished adding users, click **Save**.</span></span>

### <a name="assign-a-custom-teams-policy-to-users-in-a-group"></a><span data-ttu-id="1fcba-141">將自訂團隊原則指派給群組中的使用者</span><span class="sxs-lookup"><span data-stu-id="1fcba-141">Assign a custom teams policy to users in a group</span></span>

<span data-ttu-id="1fcba-142">您可能會想要將自訂團隊原則指派給已識別的多個使用者。</span><span class="sxs-lookup"><span data-stu-id="1fcba-142">You may want to assign a custom teams policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="1fcba-143">例如，您可能會想要將原則指派給安全性群組中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="1fcba-143">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="1fcba-144">您可以透過連線到 Azure Active Directory PowerShell for Graph 模組及商務用 Skype PowerShell 模組來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="1fcba-144">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="1fcba-145">如需有關使用 PowerShell 來管理團隊的詳細資訊，請參閱[團隊 PowerShell 概覽](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="1fcba-145">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="1fcba-146">在這個範例中，我們會將名為「行銷團隊」原則的小組原則指派給 Contoso 行銷群組中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="1fcba-146">In this example, we assign a teams policy called Marketing Teams Policy to all users in the Contoso Marketing group.</span></span>  

> [!NOTE]
> <span data-ttu-id="1fcba-147">請依照在[單一 Windows PowerShell 視窗中連線至 [所有 Office 365 服務]](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步驟，確認您首先連線至 [圖形模組] 和 [商務用 Skype] powershell 模組的 [Azure Active Directory PowerShell]。</span><span class="sxs-lookup"><span data-stu-id="1fcba-147">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="1fcba-148">取得特定群組的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="1fcba-148">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Marketing"
```
<span data-ttu-id="1fcba-149">取得指定群組的成員。</span><span class="sxs-lookup"><span data-stu-id="1fcba-149">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="1fcba-150">將群組中的所有使用者指派給特定的團隊原則。</span><span class="sxs-lookup"><span data-stu-id="1fcba-150">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="1fcba-151">在這個範例中，它是行銷團隊原則。</span><span class="sxs-lookup"><span data-stu-id="1fcba-151">In this example, it's Marketing Teams Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Marketing Teams Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="1fcba-152">根據群組中的成員數目而定，此命令可能需要幾分鐘的時間執行。</span><span class="sxs-lookup"><span data-stu-id="1fcba-152">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1fcba-153">相關主題</span><span class="sxs-lookup"><span data-stu-id="1fcba-153">Related topics</span></span>

- [<span data-ttu-id="1fcba-154">在 Teams 中管理私人小組的探索</span><span class="sxs-lookup"><span data-stu-id="1fcba-154">Manage discovery of private teams in Teams</span></span>](manage-discovery-of-private-teams.md)
- [<span data-ttu-id="1fcba-155">團隊中的私人頻道</span><span class="sxs-lookup"><span data-stu-id="1fcba-155">Private channels in Teams</span></span>](private-channels.md)
