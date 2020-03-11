---
title: 管理 Microsoft 團隊中的 app 許可權原則
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: rarang
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
description: 瞭解 Microsoft 團隊中的 app 許可權原則，以及如何使用它們來控制貴組織中的使用者可以使用哪些應用程式。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: baf3f025dd9b2340f59aee18d72d3707e4cab8fd
ms.sourcegitcommit: dde63e1b92c0bc3dbb41d8670778b863c3bc9bec
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2020
ms.locfileid: "42601410"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a><span data-ttu-id="7f9c6-103">管理 Microsoft 團隊中的 app 許可權原則</span><span class="sxs-lookup"><span data-stu-id="7f9c6-103">Manage app permission policies in Microsoft Teams</span></span>

<span data-ttu-id="7f9c6-104">身為管理員，您可以使用應用程式許可權原則來控制貴組織中的 Microsoft 團隊使用者可以使用哪些應用程式。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-104">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="7f9c6-105">您可以允許或封鎖由 Microsoft、協力廠商及貴組織發佈的所有 app 或特定應用程式。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-105">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="7f9c6-106">當您封鎖 app 時，擁有原則的使用者將無法從 [小組 app store] 安裝該應用程式。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-106">When you block an app, users who have the policy are unable to install it from the Teams app store.</span></span> <span data-ttu-id="7f9c6-107">您必須是全域管理員或團隊服務系統管理員，才能管理這些原則。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-107">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="7f9c6-108">您可以在 Microsoft 團隊系統管理中心管理 app 許可權原則。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-108">You manage app permission policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="7f9c6-109">您可以使用全域（組織範圍預設值）原則，或建立並指派自訂原則給群組中的個別使用者或使用者。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-109">You can use the global (Org-wide default) policy or create and assign custom policies to individual users or users in a group.</span></span>  

![App 許可權原則的螢幕擷取畫面](media/app-permission-policies.png)

> [!NOTE]
> <span data-ttu-id="7f9c6-111">除非您建立並指派自訂原則，否則貴組織中的使用者會自動取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-111">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="7f9c6-112">整個組織內的應用程式設定會覆寫全域原則和您建立並指派給使用者的任何自訂原則。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-112">Org-wide app settings override the global policy and any custom policies that you create and assign to users.</span></span>

<span data-ttu-id="7f9c6-113">如果您的組織已在團隊中，您在 Microsoft 365 系統管理中心的 [整個租使用者]**設定**中所設定的應用程式設定會反映在 [[管理應用程式](manage-apps.md)] 頁面上的 [組織內應用程式設定] 中。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-113">If your organization is already on Teams, the app settings you configured in **Tenant-wide settings** in the Microsoft 365 admin center are reflected in org-wide app settings on the [Manage apps](manage-apps.md) page.</span></span> <span data-ttu-id="7f9c6-114">如果您是團隊新手，且剛開始使用，則預設會允許全域原則中的所有 app。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-114">If you're new to Teams and just getting started, by default, all apps are allowed in the global policy.</span></span> <span data-ttu-id="7f9c6-115">這包含由 Microsoft、協力廠商及貴組織發佈的應用程式。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-115">This includes apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="7f9c6-116">例如，您想要封鎖所有協力廠商應用程式，並允許 Microsoft 針對貴組織中的人力資源小組特定應用程式。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-116">Say, for example, you want to block all third-party apps and allow specific apps from Microsoft for the HR team in your organization.</span></span> <span data-ttu-id="7f9c6-117">首先，您會移至 [[管理應用程式](manage-apps.md)] 頁面，並確認您想要在人力資源團隊中允許的應用程式可在組織層級使用。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-117">First, you would go to the [Manage apps](manage-apps.md) page and make sure that the apps that you want to allow for the HR team are allowed at the org level.</span></span> <span data-ttu-id="7f9c6-118">接著，建立名為 HR App 許可權原則的自訂原則，將它設定為 [封鎖] 並允許您想要的 app，然後將它指派給 HR 小組的使用者。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-118">Then, create a custom policy named HR App Permission Policy, set it to block and allow the apps that you want, and assign it to users on the HR team.</span></span>

> [!NOTE]
> <span data-ttu-id="7f9c6-119">如果您已在 Microsoft 365 政府版的環境中部署團隊，請參閱適用于[gcc 的 App 許可權原則](#app-permission-policies-for-gcc)，以深入瞭解適用于 GCC 的協力廠商應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-119">If you deployed Teams in a Microsoft 365 Government - GCC environment, see [App permission policies for GCC](#app-permission-policies-for-gcc) to learn more about third-party app settings that are unique to GCC.</span></span>

## <a name="create-a-custom-app-permission-policy"></a><span data-ttu-id="7f9c6-120">建立自訂應用程式許可權原則</span><span class="sxs-lookup"><span data-stu-id="7f9c6-120">Create a custom app permission policy</span></span>

<span data-ttu-id="7f9c6-121">如果您想要控制貴組織中不同群組使用者的可用應用程式，請建立並指派一或多個自訂應用程式許可權原則。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-121">If you want to control the apps that are available for different groups of users in your organization, create and assign one or more custom app permission policies.</span></span> <span data-ttu-id="7f9c6-122">您可以根據 Microsoft、協力廠商或您的組織發佈的應用程式，建立並指派個別的自訂原則。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-122">You can create and assign separate custom policies based on whether apps are published by Microsoft, third-parties, or your organization.</span></span> <span data-ttu-id="7f9c6-123">您必須知道，在您建立自訂原則之後，如果已停用組織內應用程式設定中的協力廠商應用程式，就無法變更它。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-123">It's important to know that after you create a custom policy, you can't change it if third-party apps are disabled in org-wide app settings.</span></span>

1. <span data-ttu-id="7f9c6-124">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app** > ]**許可權原則**。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-124">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="7f9c6-125">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-125">Click **Add**.</span></span>
    <span data-ttu-id="7f9c6-126">![新應用程式許可權原則的螢幕擷取畫面](media/app-permission-policies-new-policy.png)</span><span class="sxs-lookup"><span data-stu-id="7f9c6-126">![Screenshot of new app permission policy](media/app-permission-policies-new-policy.png)</span></span>
3. <span data-ttu-id="7f9c6-127">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-127">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="7f9c6-128">在 [ **Microsoft app**]、**協力廠商應用程式**和**租使用者應用**程式底下，選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="7f9c6-128">Under **Microsoft apps**, **Third-party apps**, and **Tenant apps**, select one of the following:</span></span>

    - <span data-ttu-id="7f9c6-129">**允許所有 app**</span><span class="sxs-lookup"><span data-stu-id="7f9c6-129">**Allow all apps**</span></span>
    - <span data-ttu-id="7f9c6-130">**允許特定的 app 和封鎖所有人**</span><span class="sxs-lookup"><span data-stu-id="7f9c6-130">**Allow specific apps and block all others**</span></span>
    - <span data-ttu-id="7f9c6-131">**封鎖特定應用程式並允許所有其他 app**</span><span class="sxs-lookup"><span data-stu-id="7f9c6-131">**Block specific apps and allow all others**</span></span>
    - <span data-ttu-id="7f9c6-132">**封鎖所有 app**</span><span class="sxs-lookup"><span data-stu-id="7f9c6-132">**Block all apps**</span></span>

5. <span data-ttu-id="7f9c6-133">如果您已選取 [**允許特定應用程式並封鎖其他 app**]，請新增您想要允許的應用程式：</span><span class="sxs-lookup"><span data-stu-id="7f9c6-133">If you selected **Allow specific apps and block others**, add the apps that you want to allow:</span></span>

    1. <span data-ttu-id="7f9c6-134">選取 [**允許應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-134">Select **Allow apps**.</span></span>
    1. <span data-ttu-id="7f9c6-135">搜尋您要允許的應用程式，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-135">Search for the apps that you want to allow, and then click **Add**.</span></span> <span data-ttu-id="7f9c6-136">搜尋結果會篩選到應用程式發行者（**Microsoft**app、**協力廠商應用程式**或**租**使用者 app）。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-136">The search results are filtered to the app publisher (**Microsoft apps**, **Third-party apps**, or **Tenant apps**).</span></span>
    1. <span data-ttu-id="7f9c6-137">當您選取 app 清單後，請按一下 [**允許**]。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-137">When you've chosen the list of apps, click **Allow**.</span></span>

6. <span data-ttu-id="7f9c6-138">同樣地，如果您已選取 [**封鎖特定應用程式並允許所有人**]，請搜尋並新增您想要封鎖的 app。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-138">Similarly, if you selected **Block specific apps and allow all others**, search for and add the apps that you want to block.</span></span>
7. <span data-ttu-id="7f9c6-139">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-139">Click **Save**.</span></span>

## <a name="edit-an-app-permission-policy"></a><span data-ttu-id="7f9c6-140">編輯應用程式許可權原則</span><span class="sxs-lookup"><span data-stu-id="7f9c6-140">Edit an app permission policy</span></span>

<span data-ttu-id="7f9c6-141">您可以使用 Microsoft 團隊系統管理中心來編輯原則，包括您建立的全域原則和自訂原則。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-141">You can use the Microsoft Teams admin center to edit a policy, including the global policy and custom policies that you create.</span></span>

1. <span data-ttu-id="7f9c6-142">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app** > ]**許可權原則**。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="7f9c6-143">按一下原則名稱左邊的，然後按一下 [**編輯**]，選取原則。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-143">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="7f9c6-144">您可以從這裡進行所要的變更。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-144">From here, make the changes that you want.</span></span> <span data-ttu-id="7f9c6-145">您可以根據應用程式發行者管理設定，然後根據 [允許/封鎖] 設定新增及移除應用程式。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-145">You can manage settings based on the app publisher and add and remove apps based on the allow/block setting.</span></span>
4. <span data-ttu-id="7f9c6-146">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-146">Click **Save**.</span></span>

## <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="7f9c6-147">將自訂應用程式許可權原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="7f9c6-147">Assign a custom app permission policy to users</span></span>

<span data-ttu-id="7f9c6-148">您可以使用 Microsoft 團隊系統管理中心，將自訂原則指派給一或多個使用者或商務用 Skype PowerShell 模組，將自訂原則指派給使用者群組，例如安全群組或通訊群組中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-148">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as all users in a security group or distribution group.</span></span>

### <a name="assign-a-custom-app-permission-policy-to-a-user"></a><span data-ttu-id="7f9c6-149">將自訂應用程式許可權原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="7f9c6-149">Assign a custom app permission policy to a user</span></span>

1. <span data-ttu-id="7f9c6-150">在 Microsoft 團隊系統管理中心的左導覽中，前往 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-150">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="7f9c6-151">按一下使用者名稱左邊的，然後按一下 [**編輯設定**]，選取使用者。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-151">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="7f9c6-152">在 [**應用程式許可權原則**] 底下，選取您要指派的 App 許可權原則，**然後按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-152">Under **App permission policy**, select the app permission policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="7f9c6-153">若要一次將原則指派給多位使用者，請參閱[大量編輯團隊使用者設定](edit-user-settings-in-bulk.md)。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-153">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="7f9c6-154">或者，您也可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="7f9c6-154">Or, you can also do the following:</span></span>

1. <span data-ttu-id="7f9c6-155">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app** > ]**許可權原則**。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-155">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="7f9c6-156">按一下原則名稱左方，選取原則。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-156">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="7f9c6-157">選取 [**管理使用者**]。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-157">Select **Manage users**.</span></span>
4. <span data-ttu-id="7f9c6-158">在 [**管理使用者**] 窗格中，依 [顯示名稱] 或 [使用者名稱] 搜尋使用者，選取名稱，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-158">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="7f9c6-159">針對您要新增的每個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-159">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="7f9c6-160">完成新增使用者後，請按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-160">When you're finished adding users, click **Save**.</span></span>

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a><span data-ttu-id="7f9c6-161">將自訂應用程式許可權原則指派給群組中的使用者</span><span class="sxs-lookup"><span data-stu-id="7f9c6-161">Assign a custom app permission policy to users in a group</span></span>

<span data-ttu-id="7f9c6-162">您可能會想要將自訂應用程式許可權原則指派給已識別的多個使用者。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-162">You may want to assign a custom app permission policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="7f9c6-163">例如，您可能會想要將原則指派給安全性群組中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-163">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="7f9c6-164">您可以透過連線到 Azure Active Directory PowerShell for Graph 模組及商務用 Skype PowerShell 模組來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-164">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="7f9c6-165">如需有關使用 PowerShell 來管理團隊的詳細資訊，請參閱[團隊 PowerShell 概覽](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-165">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="7f9c6-166">在這個範例中，我們會將名為「人力資源 App」許可權原則的自訂應用程式許可權原則指派給 Contoso 製藥人力資源專案群組中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-166">In this example, we assign a custom app permission policy called HR App Permission Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="7f9c6-167">請依照在[單一 Windows PowerShell 視窗中連線至 [所有 Office 365 服務]](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步驟，確認您首先連線至 [圖形模組] 和 [商務用 Skype] powershell 模組的 [Azure Active Directory PowerShell]。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-167">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="7f9c6-168">取得特定群組的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-168">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="7f9c6-169">取得指定群組的成員。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-169">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="7f9c6-170">將群組中的所有使用者指派給特定的 app 許可權原則。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-170">Assign all users in the group to a particular app permission policy.</span></span> <span data-ttu-id="7f9c6-171">在這個範例中，它是人力資源應用程式許可權原則。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-171">In this example, it's HR App Permission Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="7f9c6-172">根據群組中的成員數目而定，此命令可能需要幾分鐘的時間執行。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-172">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="app-permission-policies-for-gcc"></a><span data-ttu-id="7f9c6-173">適用于 GCC 的 App 許可權原則</span><span class="sxs-lookup"><span data-stu-id="7f9c6-173">App permission policies for GCC</span></span>

<span data-ttu-id="7f9c6-174">在 Microsoft 365 政府版的團隊部署中，請務必瞭解下列關於適用于 GCC 的協力廠商應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-174">In a Microsoft 365 Government - GCC deployment of Teams, it's important to know the following about third-party app settings, which are unique to GCC.</span></span>

<span data-ttu-id="7f9c6-175">在 GCC 中，預設會封鎖所有協力廠商應用程式。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-175">In GCC, all third-party apps are blocked by default.</span></span> <span data-ttu-id="7f9c6-176">此外，您會在 Microsoft 團隊系統管理中心的 [應用程式許可權原則] 頁面上，看到有關管理協力廠商應用程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-176">Additionally, you'll see the following note about managing third-party apps on the app permission policies page in the Microsoft Teams admin center.</span></span>

![在 GCC 中應用程式許可權原則的螢幕擷取畫面](media/app-permission-policies-gcc.png)

<span data-ttu-id="7f9c6-178">若要為您組織中的使用者或一組使用者啟用協力廠商應用程式，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="7f9c6-178">To enable a third-party app for a user or a set of users in your organization, do the following:</span></span>

1. <span data-ttu-id="7f9c6-179">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app** > **管理應用程式**]，然後在應用程式清單中，確認您要允許一組使用者使用的協力廠商應用程式已設定為 [在組織層級**封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-179">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then in the list of apps, confirm that the third-party app that you want to allow for a set of users is set to **Blocked** at the org level.</span></span>

2. <span data-ttu-id="7f9c6-180">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app** > **許可權原則**]，然後編輯全域原則來封鎖協力廠商應用程式。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-180">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**, and then edit the global policy to block the third-party app.</span></span> <span data-ttu-id="7f9c6-181">若要執行此動作：</span><span class="sxs-lookup"><span data-stu-id="7f9c6-181">To do this:</span></span>
    1. <span data-ttu-id="7f9c6-182">在 [應用程式許可權原則] 頁面上，按一下 [**全域（組織範圍預設值）**]，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-182">On the App permission policies page, click **Global (Org-wide default)**, and then click **Edit**.</span></span>
    2. <span data-ttu-id="7f9c6-183">在 [**協力廠商應用程式**] 底下，選取 [**封鎖特定的 app 並允許所有其他**app]，新增應用程式，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-183">Under **Third-party apps**, select **Block specific apps and allow all others**, add the app, and then click **Save**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7f9c6-184">在您移至下一個步驟之前，請務必先執行此動作，才能允許組織層級的 app。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-184">It's important to do this before you go to the next step to allow the app at the org level.</span></span> <span data-ttu-id="7f9c6-185">這是因為如果協力廠商應用程式未封鎖在全域應用程式許可權原則中，則全域原則適用的所有使用者，都可以在組織階層時存取協力廠商 app。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-185">This is because if the third-party app isn't blocked in the global app permission policy, all users that the global policy applies to will be able to access the third-party app when you allow it at the org level.</span></span>

3. <span data-ttu-id="7f9c6-186">允許組織階層的協力廠商應用程式。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-186">Allow the third-party app at the org level.</span></span> <span data-ttu-id="7f9c6-187">若要執行此動作，請在左側導覽中，移至 [**團隊 app** > **管理應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-187">To do this, in the left navigation, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="7f9c6-188">在應用程式清單中，按一下應用程式名稱的左邊以選取 app，然後選取 [**允許**]。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-188">In the list of apps, click to the left of the app name to select the app, and then select **Allow**.</span></span>
4. <span data-ttu-id="7f9c6-189">[建立自訂應用程式許可權原則](#create-a-custom-app-permission-policy)以允許 app，然後[將原則指派](#assign-a-custom-app-permission-policy-to-users)給您想要的使用者。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-189">[Create a custom app permission policy](#create-a-custom-app-permission-policy) to allow the app, and then [assign the policy](#assign-a-custom-app-permission-policy-to-users) to the users you want.</span></span>

## <a name="faq"></a><span data-ttu-id="7f9c6-190">常見問題集</span><span class="sxs-lookup"><span data-stu-id="7f9c6-190">FAQ</span></span>

### <a name="working-with-app-permission-policies"></a><span data-ttu-id="7f9c6-191">使用應用程式許可權原則</span><span class="sxs-lookup"><span data-stu-id="7f9c6-191">Working with app permission policies</span></span>

#### <a name="can-i-control-line-of-business-lob-apps"></a><span data-ttu-id="7f9c6-192">我可以控制商務用線（LOB）應用程式嗎？</span><span class="sxs-lookup"><span data-stu-id="7f9c6-192">Can I control line of business (LOB) apps?</span></span>
<span data-ttu-id="7f9c6-193">是的，您可以使用應用程式許可權原則來控制自訂（LOB）應用程式的推出與發佈。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-193">Yes, you can use app permission policies to control the rollout and distribution of custom (LOB) apps.</span></span> <span data-ttu-id="7f9c6-194">您可以建立自訂原則或編輯全域原則，以根據貴組織的需求來允許或封鎖自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-194">You can create a custom policy or edit the global policy to allow or block custom apps based on the needs of your organization.</span></span>

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a><span data-ttu-id="7f9c6-195">App 許可權原則如何與釘選的 app 和 app 設定原則相關？</span><span class="sxs-lookup"><span data-stu-id="7f9c6-195">How do app permission policies relate to pinned apps and app setup policies?</span></span>

<span data-ttu-id="7f9c6-196">您可以將應用程式設定原則與 app 許可權原則搭配使用。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-196">You can use app setup policies together with app permission policies.</span></span> <span data-ttu-id="7f9c6-197">已從使用者的已啟用應用程式集中選取預先固定的 app。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-197">Pre-pinned apps are selected from the set of enabled apps for a user.</span></span> <span data-ttu-id="7f9c6-198">此外，如果使用者有應用程式許可權原則，而該策略封鎖 app 設定原則中的 app，該 app 就不會出現在小組中。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-198">Additionally, if a user has an app permission policy that blocks an app in their app setup policy, that app won't appear in Teams.</span></span>

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a><span data-ttu-id="7f9c6-199">我可以使用應用程式許可權原則來限制上傳自訂應用程式嗎？</span><span class="sxs-lookup"><span data-stu-id="7f9c6-199">Can I use app permission policies to restrict uploading custom apps?</span></span>

<span data-ttu-id="7f9c6-200">您可以在 [**管理**app] 頁面上使用整個組織的設定，或按一下 [應用程式設定原則]，限制您的組織上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-200">You can use org-wide settings on the **Manage apps** page, or app setup policies to restrict uploading custom apps for your organization.</span></span>  

<span data-ttu-id="7f9c6-201">若要限制特定使用者上傳自訂應用程式，請使用自訂 app 原則。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-201">To restrict specific users from uploading custom apps, use custom app policies.</span></span> <span data-ttu-id="7f9c6-202">若要深入瞭解，請參閱[管理團隊中的自訂應用程式原則和設定](teams-custom-app-policies-and-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-202">To learn more, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a><span data-ttu-id="7f9c6-203">封鎖應用程式適用于團隊行動用戶端嗎？</span><span class="sxs-lookup"><span data-stu-id="7f9c6-203">Does blocking an app apply to Teams mobile clients?</span></span>

<span data-ttu-id="7f9c6-204">是的，當您封鎖應用程式時，該應用程式會在所有團隊用戶端間封鎖。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-204">Yes, when you block an app, that app is blocked across all Teams clients.</span></span>  

### <a name="user-experience"></a><span data-ttu-id="7f9c6-205">使用者體驗</span><span class="sxs-lookup"><span data-stu-id="7f9c6-205">User experience</span></span>

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a><span data-ttu-id="7f9c6-206">當應用程式遭到封鎖時，使用者有何體驗？</span><span class="sxs-lookup"><span data-stu-id="7f9c6-206">What does a user experience when an app is blocked?</span></span>

<span data-ttu-id="7f9c6-207">使用者無法與封鎖的 app 或其功能（例如 bot、索引標籤和訊息延伸）互動。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-207">Users can't interact with a blocked app or its capabilities, such bots, tabs, and messaging extensions.</span></span> <span data-ttu-id="7f9c6-208">在共用的內容（例如小組或群組聊天）中，機器人仍可以傳送訊息給該內容的所有參與者。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-208">In a shared context, such as a team or group chat, bots can still send messages to all participants of that context.</span></span> <span data-ttu-id="7f9c6-209">小組會在應用程式遭到封鎖時向使用者顯示。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-209">Teams indicates to the user when an app is blocked.</span></span>

<span data-ttu-id="7f9c6-210">例如，當應用程式遭到封鎖時，使用者就不能執行下列任何一項動作：</span><span class="sxs-lookup"><span data-stu-id="7f9c6-210">For example, when an app is blocked, users can't do any of the following:</span></span>

- <span data-ttu-id="7f9c6-211">將 app 新增至個人或加入聊天或團隊</span><span class="sxs-lookup"><span data-stu-id="7f9c6-211">Add the app personally or to a chat or team</span></span>
- <span data-ttu-id="7f9c6-212">傳送訊息給應用程式的 bot</span><span class="sxs-lookup"><span data-stu-id="7f9c6-212">Send messages to the app’s bot</span></span>
- <span data-ttu-id="7f9c6-213">執行傳送資訊回到應用程式的按鈕動作，例如可操作的訊息</span><span class="sxs-lookup"><span data-stu-id="7f9c6-213">Perform button actions that send information back to the app, such as actionable messages</span></span>  
- <span data-ttu-id="7f9c6-214">[查看] 應用程式的索引標籤</span><span class="sxs-lookup"><span data-stu-id="7f9c6-214">View the app’s tab</span></span>
- <span data-ttu-id="7f9c6-215">設定連接器接收通知</span><span class="sxs-lookup"><span data-stu-id="7f9c6-215">Set up connectors to receive notifications</span></span>
- <span data-ttu-id="7f9c6-216">使用應用程式的訊息延伸</span><span class="sxs-lookup"><span data-stu-id="7f9c6-216">Use the app’s messaging extension</span></span>

<span data-ttu-id="7f9c6-217">舊版入口網站允許您在組織階層控制應用程式，這表示當應用程式遭到封鎖時，系統會封鎖組織中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-217">The legacy portal allowed controlling apps at the organization level, which means when an app is blocked, it's blocked for all users in the organization.</span></span> <span data-ttu-id="7f9c6-218">封鎖 [[管理應用程式](manage-apps.md)] 頁面上的應用程式的運作方式與此完全相同。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-218">Blocking an app on the [Manage apps](manage-apps.md) page works exactly the same way.</span></span>

<span data-ttu-id="7f9c6-219">針對指派給特定使用者的 app 許可權原則，如果允許並封鎖含 bot 或連接器功能的應用程式，而且如果在共用的內容中則只允許部分使用者使用該應用程式的群組聊天或頻道成員，就不會有該應用程式的許可權 可以查看由 bot 或連接器所張貼的訊息歷程記錄和訊息，但無法與它互動。</span><span class="sxs-lookup"><span data-stu-id="7f9c6-219">For app permission policies assigned to specific users, if an app with bot or connector capability was allowed and then blocked, and if the app is then allowed only for some users in a shared context, members of a group chat or channel that don't have permission to that app can see the message history and messages that were posted by the bot or connector, but can't interact with it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7f9c6-220">相關主題</span><span class="sxs-lookup"><span data-stu-id="7f9c6-220">Related topics</span></span>

- [<span data-ttu-id="7f9c6-221">在 Teams 中的應用程式系統管理設定</span><span class="sxs-lookup"><span data-stu-id="7f9c6-221">Admin settings for apps in Teams</span></span>](admin-settings.md)
