---
title: 管理 Microsoft 團隊中的呼叫者識別碼原則
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1keywords: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中使用和管理本機號碼原則，以變更或封鎖貴組織中的小組使用者本機號碼。
ms.openlocfilehash: aed6e3cbe2053ddc16b049608247f56705626249
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992883"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="45054-103">管理 Microsoft 團隊中的呼叫者識別碼原則</span><span class="sxs-lookup"><span data-stu-id="45054-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="45054-104">做為管理員，您可以使用 Microsoft 團隊中的本機號碼原則來變更或封鎖本機號碼（也稱為呼叫線路識別碼）。</span><span class="sxs-lookup"><span data-stu-id="45054-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="45054-105">根據預設，當使用者撥打電話給 PSTN 手機時，可以看到他們的電話號碼，以及當他們呼叫團隊使用者時，可以看到 PSTN 呼叫者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="45054-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="45054-106">您可以使用本機號碼原則，為您組織中的小組使用者顯示備用電話號碼，或封鎖要顯示的傳入號碼。</span><span class="sxs-lookup"><span data-stu-id="45054-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="45054-107">例如，當使用者撥打電話時，您可以變更本機號碼，以顯示貴組織的主要電話號碼，而不是使用者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="45054-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="45054-108">您可以移至 Microsoft 團隊系統管理中心的**語音** > **本機號碼原則**來管理本機號碼原則。</span><span class="sxs-lookup"><span data-stu-id="45054-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="45054-109">您可以使用全域（組織範圍預設值）原則，或建立自訂原則，並將它們指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="45054-109">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="45054-110">除非您建立並指派自訂原則，否則貴組織中的使用者會自動取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="45054-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="45054-111">您可以編輯全域原則，或建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="45054-111">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="45054-112">如果指派給使用者的是自訂原則，該原則會套用給使用者。</span><span class="sxs-lookup"><span data-stu-id="45054-112">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="45054-113">如果使用者未獲指派自訂原則，則全域原則會套用至使用者。</span><span class="sxs-lookup"><span data-stu-id="45054-113">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="45054-114">建立自訂本機號碼原則</span><span class="sxs-lookup"><span data-stu-id="45054-114">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="45054-115">在 Microsoft [團隊管理中心] 的左導覽中，移至 [**語音** > **本機號碼原則**]。</span><span class="sxs-lookup"><span data-stu-id="45054-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="45054-116">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="45054-116">Click **Add**.</span></span>
<span data-ttu-id="45054-117">![系統管理中心 [新增本機號碼原則] 頁面的螢幕擷取畫面](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="45054-117">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="45054-118">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="45054-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="45054-119">從這裡選擇您想要的設定：</span><span class="sxs-lookup"><span data-stu-id="45054-119">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="45054-120">**封鎖來電**的本機號碼：開啟此設定可封鎖來電的本機號碼。</span><span class="sxs-lookup"><span data-stu-id="45054-120">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="45054-121">**使用者可以覆寫本機號碼原則**：開啟此設定可讓使用者覆寫原則中的設定，以將他們的數字顯示為 callees。</span><span class="sxs-lookup"><span data-stu-id="45054-121">**Users can override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="45054-122">這表示使用者可以選擇是否要顯示其本機號碼。</span><span class="sxs-lookup"><span data-stu-id="45054-122">This means that users can choose whether to display their caller ID.</span></span>
    - <span data-ttu-id="45054-123">**取代來電**顯示：您可以選取下列其中一項，以將本機號碼設定為供使用者使用：</span><span class="sxs-lookup"><span data-stu-id="45054-123">**Replace caller ID**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="45054-124">**使用者號碼**：顯示使用者的號碼。</span><span class="sxs-lookup"><span data-stu-id="45054-124">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="45054-125">[**服務號碼**]：可讓您設定要顯示為本機號碼的服務電話號碼。</span><span class="sxs-lookup"><span data-stu-id="45054-125">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="45054-126">**匿名**：以匿名方式顯示本機號碼。</span><span class="sxs-lookup"><span data-stu-id="45054-126">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="45054-127">**用來取代本機號碼的服務號碼**：選擇服務號碼來取代使用者的本機號碼。</span><span class="sxs-lookup"><span data-stu-id="45054-127">**Service number to use to replace the caller ID**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="45054-128">如果您在 [**取代來電**顯示] 中選取了 [**服務號碼**]，就可以使用這個選項。</span><span class="sxs-lookup"><span data-stu-id="45054-128">This option is available if you selected **Service number** in **Replace caller ID**.</span></span>

5. <span data-ttu-id="45054-129">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="45054-129">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="45054-130">編輯本機號碼原則</span><span class="sxs-lookup"><span data-stu-id="45054-130">Edit a caller ID policy</span></span>

<span data-ttu-id="45054-131">您可以編輯全域原則或您建立的任何自訂原則。</span><span class="sxs-lookup"><span data-stu-id="45054-131">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="45054-132">在 Microsoft [團隊管理中心] 的左導覽中，移至 [**語音** > **本機號碼原則**]。</span><span class="sxs-lookup"><span data-stu-id="45054-132">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="45054-133">按一下原則名稱左邊的，然後按一下 [**編輯**]，選取原則。</span><span class="sxs-lookup"><span data-stu-id="45054-133">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="45054-134">變更您想要的設定，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="45054-134">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="45054-135">將自訂本機號碼原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="45054-135">Assign a custom caller ID policy to users</span></span>

<span data-ttu-id="45054-136">您可以使用 Microsoft 團隊系統管理中心，將自訂原則指派給一或多個使用者或商務用 Skype PowerShell 模組，將自訂原則指派給使用者群組，例如安全群組或通訊群組。</span><span class="sxs-lookup"><span data-stu-id="45054-136">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-caller-line-id-policy-to-a-user"></a><span data-ttu-id="45054-137">為使用者指派自訂來電者行識別碼原則</span><span class="sxs-lookup"><span data-stu-id="45054-137">Assign a custom caller line ID policy to a user</span></span>

1. <span data-ttu-id="45054-138">在 Microsoft 團隊系統管理中心的左導覽中，前往 [**使用者**]，然後按一下使用者。</span><span class="sxs-lookup"><span data-stu-id="45054-138">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="45054-139">按一下 [**原則**]，然後在 [**指派的原則**] 旁，按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="45054-139">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="45054-140">在 [**本機號碼原則**] 底下，選取您要指派的原則，然後選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="45054-140">Under **Caller ID policy**, select the policy you want to assign, and then choose **Save**.</span></span>

### <a name="assign-a-custom-calling-line-id-policy-to-multiple-users-at-a-time"></a><span data-ttu-id="45054-141">一次將自訂通話行識別碼原則指派給多位使用者</span><span class="sxs-lookup"><span data-stu-id="45054-141">Assign a custom calling line ID policy to multiple users at a time</span></span>

<span data-ttu-id="45054-142">若要一次將自訂通話行識別碼原則指派給多位使用者，請參閱[大量編輯團隊使用者設定](edit-user-settings-in-bulk.md)。</span><span class="sxs-lookup"><span data-stu-id="45054-142">To assign a custom calling line Id policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="45054-143">或者，您也可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="45054-143">Or, you can also do the following:</span></span>

1. <span data-ttu-id="45054-144">移至**Microsoft 團隊系統管理中心** > **的語音** > **本機號碼原則**。</span><span class="sxs-lookup"><span data-stu-id="45054-144">Go to **Microsoft Teams admin center** > **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="45054-145">按一下原則名稱左方，選取原則。</span><span class="sxs-lookup"><span data-stu-id="45054-145">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="45054-146">選取 [**管理使用者**]。</span><span class="sxs-lookup"><span data-stu-id="45054-146">Select **Manage users**.</span></span>
4. <span data-ttu-id="45054-147">在 [**管理使用者**] 窗格中，依 [顯示名稱] 或 [使用者名稱] 搜尋使用者，選取名稱，然後選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="45054-147">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="45054-148">針對您要新增的每個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="45054-148">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="45054-149">完成新增使用者後，請選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="45054-149">When you're finished adding users, select **Save**.</span></span>

### <a name="assign-a-custom-caller-id-policy-to-users-in-a-group"></a><span data-ttu-id="45054-150">將自訂本機號碼原則指派給群組中的使用者</span><span class="sxs-lookup"><span data-stu-id="45054-150">Assign a custom caller ID policy to users in a group</span></span>

<span data-ttu-id="45054-151">您可能會想要將自訂原則指派給已識別的多個使用者。</span><span class="sxs-lookup"><span data-stu-id="45054-151">You may want to assign a custom  policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="45054-152">例如，您可能會想要將原則指派給安全性群組中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="45054-152">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="45054-153">您可以透過連線到 Azure Active Directory PowerShell for Graph 模組及商務用 Skype PowerShell 模組來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="45054-153">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="45054-154">如需有關使用 PowerShell 來管理團隊的詳細資訊，請參閱[團隊 PowerShell 概覽](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="45054-154">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="45054-155">在這個範例中，我們會將自訂來電者蓋原則（稱為支援本機號碼原則）指派給 Contoso 支援群組中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="45054-155">In this example, we assign a custom caller lID policy called Support Caller ID Policy to all users in the Contoso Support group.</span></span>  

> [!NOTE]
> <span data-ttu-id="45054-156">請依照在[單一 Windows PowerShell 視窗中連線至 [所有 Office 365 服務]](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步驟，確認您首先連線至 [圖形模組] 和 [商務用 Skype] powershell 模組的 [Azure Active Directory PowerShell]。</span><span class="sxs-lookup"><span data-stu-id="45054-156">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="45054-157">取得特定群組的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="45054-157">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Support"
```
<span data-ttu-id="45054-158">取得指定群組的成員。</span><span class="sxs-lookup"><span data-stu-id="45054-158">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="45054-159">將群組中的所有使用者指派給特定的呼叫者 ID 原則。</span><span class="sxs-lookup"><span data-stu-id="45054-159">Assign all users in the group to a particular caller ID policy.</span></span> <span data-ttu-id="45054-160">在這個範例中，它支援本機號碼原則。</span><span class="sxs-lookup"><span data-stu-id="45054-160">In this example, it's Support Caller ID Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsCallingLineIdentity -PolicyName "Support Caller ID Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="45054-161">根據群組中的成員數目而定，此命令可能需要幾分鐘的時間執行。</span><span class="sxs-lookup"><span data-stu-id="45054-161">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="45054-162">相關主題</span><span class="sxs-lookup"><span data-stu-id="45054-162">Related topics</span></span>

- [<span data-ttu-id="45054-163">新-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="45054-163">New-CsCallingLineIdentity</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

