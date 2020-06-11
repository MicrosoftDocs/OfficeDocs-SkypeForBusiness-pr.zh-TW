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
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中使用和管理本機號碼原則，以變更或封鎖貴組織中的小組使用者本機號碼。
ms.openlocfilehash: 67b5abef6cdbdab9a127dd2957c2fdfefbaf2927
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691419"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="d491e-103">管理 Microsoft 團隊中的呼叫者識別碼原則</span><span class="sxs-lookup"><span data-stu-id="d491e-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="d491e-104">做為管理員，您可以使用 Microsoft 團隊中的本機號碼原則來變更或封鎖本機號碼（也稱為呼叫線路識別碼）。</span><span class="sxs-lookup"><span data-stu-id="d491e-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="d491e-105">根據預設，當使用者撥打電話給 PSTN 手機時，可以看到他們的電話號碼，以及當他們呼叫團隊使用者時，可以看到 PSTN 呼叫者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d491e-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="d491e-106">您可以使用本機號碼原則，為您組織中的小組使用者顯示備用電話號碼，或封鎖要顯示的傳入號碼。</span><span class="sxs-lookup"><span data-stu-id="d491e-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="d491e-107">例如，當使用者撥打電話時，您可以變更本機號碼，以顯示貴組織的主要電話號碼，而不是使用者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d491e-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="d491e-108">您可以移至**Voice**  >  Microsoft 團隊系統管理中心的語音**本機號碼原則**來管理本機號碼原則。</span><span class="sxs-lookup"><span data-stu-id="d491e-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="d491e-109">您可以使用全域 (預設為全組織) 原則或建立自訂原則，並指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="d491e-109">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="d491e-110">除非您建立並指派自訂原則，否則貴組織中的使用者將會自動取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="d491e-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="d491e-111">您可以編輯全域原則，或建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="d491e-111">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="d491e-112">如果指派給使用者的是自訂原則，該原則會套用給使用者。</span><span class="sxs-lookup"><span data-stu-id="d491e-112">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="d491e-113">如果使用者未獲指派自訂原則，則全域原則會套用至使用者。</span><span class="sxs-lookup"><span data-stu-id="d491e-113">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="d491e-114">建立自訂本機號碼原則</span><span class="sxs-lookup"><span data-stu-id="d491e-114">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="d491e-115">在 Microsoft [團隊管理中心] 的左導覽中，移至 [**語音**  >  **本機號碼原則**]。</span><span class="sxs-lookup"><span data-stu-id="d491e-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="d491e-116">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="d491e-116">Click **Add**.</span></span> <br>
<span data-ttu-id="d491e-117">![系統管理中心 [新增本機號碼原則] 頁面的螢幕擷取畫面](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="d491e-117">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="d491e-118">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="d491e-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="d491e-119">從這裡選擇您想要的設定：</span><span class="sxs-lookup"><span data-stu-id="d491e-119">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="d491e-120">**封鎖來電**的本機號碼：開啟此設定可封鎖來電的本機號碼。</span><span class="sxs-lookup"><span data-stu-id="d491e-120">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="d491e-121">覆**寫本機號碼原則**：開啟此設定可讓使用者覆寫原則中的設定，以將他們的號碼顯示在 callees 中。</span><span class="sxs-lookup"><span data-stu-id="d491e-121">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="d491e-122">這表示使用者可以選擇是否要顯示其本機號碼。</span><span class="sxs-lookup"><span data-stu-id="d491e-122">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="d491e-123">如需詳細資訊，請參閱[結束使用者對輸出來電者識別碼的控制](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id)。</span><span class="sxs-lookup"><span data-stu-id="d491e-123">For more information, see [End user control of outbound caller ID](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="d491e-124">**使用本機號碼取代來電**顯示：若要為使用者設定本機號碼，請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d491e-124">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="d491e-125">**使用者號碼**：顯示使用者的號碼。</span><span class="sxs-lookup"><span data-stu-id="d491e-125">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="d491e-126">[**服務號碼**]：可讓您設定要顯示為本機號碼的服務電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d491e-126">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="d491e-127">**匿名**：以匿名方式顯示本機號碼。</span><span class="sxs-lookup"><span data-stu-id="d491e-127">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="d491e-128">**以這個服務號碼取代本機號碼**：選擇服務號碼來取代使用者的本機號碼。</span><span class="sxs-lookup"><span data-stu-id="d491e-128">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="d491e-129">如果您在 [**取代本機號碼者識別碼**] 中選取了 [**服務號碼**]，就可以使用此選項。</span><span class="sxs-lookup"><span data-stu-id="d491e-129">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="d491e-130">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d491e-130">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="d491e-131">編輯本機號碼原則</span><span class="sxs-lookup"><span data-stu-id="d491e-131">Edit a caller ID policy</span></span>

<span data-ttu-id="d491e-132">您可以編輯全域原則或您建立的任何自訂原則。</span><span class="sxs-lookup"><span data-stu-id="d491e-132">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="d491e-133">在 Microsoft [團隊管理中心] 的左導覽中，移至 [**語音**  >  **本機號碼原則**]。</span><span class="sxs-lookup"><span data-stu-id="d491e-133">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="d491e-134">按一下原則名稱左邊的，然後按一下 [**編輯**]，選取原則。</span><span class="sxs-lookup"><span data-stu-id="d491e-134">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="d491e-135">變更您想要的設定，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d491e-135">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="d491e-136">將自訂本機號碼原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="d491e-136">Assign a custom caller ID policy to users</span></span>

<span data-ttu-id="d491e-137">您可以使用 Microsoft 團隊系統管理中心，將自訂原則指派給一或多個使用者或商務用 Skype PowerShell 模組，將自訂原則指派給群組中的使用者，例如安全群組或通訊群組。</span><span class="sxs-lookup"><span data-stu-id="d491e-137">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to users in a group, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-caller-line-id-policy-to-users"></a><span data-ttu-id="d491e-138">為使用者指派自訂來電者行識別碼原則</span><span class="sxs-lookup"><span data-stu-id="d491e-138">Assign a custom caller line ID policy to users</span></span>

<span data-ttu-id="d491e-139">若要將原則指派給一個使用者：</span><span class="sxs-lookup"><span data-stu-id="d491e-139">To assign a policy to one user:</span></span>

1. <span data-ttu-id="d491e-140">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]\*\*\*\*，然後按一下該使用者。</span><span class="sxs-lookup"><span data-stu-id="d491e-140">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="d491e-141">按一下 [**原則**]，然後在 [**指派的原則**] 旁，按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="d491e-141">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="d491e-142">在 [**本機號碼原則**] 底下，選取您要指派的原則，然後選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d491e-142">Under **Caller ID policy**, select the policy you want to assign, and then choose **Save**.</span></span>

<span data-ttu-id="d491e-143">若要一次將原則指派給多位使用者：</span><span class="sxs-lookup"><span data-stu-id="d491e-143">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="d491e-144">在 Microsoft Teams 系統管理中心的左側瀏覽中，移至 [使用者]\*\*\*\*，然後搜尋使用者或篩選檢視畫面，以顯示您想要的使用者。</span><span class="sxs-lookup"><span data-stu-id="d491e-144">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="d491e-145">在 [&#x2713;]\*\*\*\* (核取方塊) 欄中，選取使用者。</span><span class="sxs-lookup"><span data-stu-id="d491e-145">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="d491e-146">若要選取 [所有使用者]，請按一下表格頂端的 [&#x2713;] (核取方塊)。</span><span class="sxs-lookup"><span data-stu-id="d491e-146">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="d491e-147">按一下 [編輯設定]\*\*\*\*，進行所需的變更，然後按一下 [套用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d491e-147">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="d491e-148">或者，您也可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d491e-148">Or, you can also do the following:</span></span>

1. <span data-ttu-id="d491e-149">移至**Microsoft 團隊系統管理中心**的  >  **語音**  >  **本機號碼原則**。</span><span class="sxs-lookup"><span data-stu-id="d491e-149">Go to **Microsoft Teams admin center** > **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="d491e-150">按一下原則名稱的左側來選取原則。</span><span class="sxs-lookup"><span data-stu-id="d491e-150">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="d491e-151">選取 [管理使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d491e-151">Select **Manage users**.</span></span>
4. <span data-ttu-id="d491e-152">在 **[管理使用者]** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="d491e-152">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="d491e-153">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="d491e-153">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="d491e-154">完成新增使用者後，請選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d491e-154">When you're finished adding users, select **Save**.</span></span>

### <a name="assign-a-custom-caller-id-policy-to-users-in-a-group"></a><span data-ttu-id="d491e-155">將自訂本機號碼原則指派給群組中的使用者</span><span class="sxs-lookup"><span data-stu-id="d491e-155">Assign a custom caller ID policy to users in a group</span></span>

<span data-ttu-id="d491e-156">您可能會想要將自訂原則指派給已識別的多個使用者。</span><span class="sxs-lookup"><span data-stu-id="d491e-156">You may want to assign a custom  policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="d491e-157">例如，您可能會想要將原則指派給安全性群組中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="d491e-157">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="d491e-158">您可以透過連線到 Azure Active Directory PowerShell for Graph 模組及商務用 Skype PowerShell 模組來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="d491e-158">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="d491e-159">如需有關使用 PowerShell 來管理團隊的詳細資訊，請參閱[團隊 PowerShell 概覽](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d491e-159">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="d491e-160">在這個範例中，我們會將自訂來電者蓋原則（稱為支援本機號碼原則）指派給 Contoso 支援群組中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="d491e-160">In this example, we assign a custom caller lID policy called Support Caller ID Policy to all users in the Contoso Support group.</span></span>  

> [!NOTE]
> <span data-ttu-id="d491e-161">請依照在[單一 Windows PowerShell 視窗中連線至 [所有 Microsoft 365] 或 [Office 365 服務](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)] 中的步驟，確認您首先連線至 [圖形模組] 和 [商務用 Skype] powershell 模組的 [Azure Active Directory PowerShell]。</span><span class="sxs-lookup"><span data-stu-id="d491e-161">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="d491e-162">取得特定群組的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="d491e-162">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Support"
```
<span data-ttu-id="d491e-163">取得指定群組的成員。</span><span class="sxs-lookup"><span data-stu-id="d491e-163">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="d491e-164">將群組中的所有使用者指派給特定的呼叫者 ID 原則。</span><span class="sxs-lookup"><span data-stu-id="d491e-164">Assign all users in the group to a particular caller ID policy.</span></span> <span data-ttu-id="d491e-165">在這個範例中，它支援本機號碼原則。</span><span class="sxs-lookup"><span data-stu-id="d491e-165">In this example, it's Support Caller ID Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsCallingLineIdentity -PolicyName "Support Caller ID Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="d491e-166">根據群組中的成員數目而定，此命令可能需要幾分鐘的時間執行。</span><span class="sxs-lookup"><span data-stu-id="d491e-166">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="d491e-167">相關主題</span><span class="sxs-lookup"><span data-stu-id="d491e-167">Related topics</span></span>

- [<span data-ttu-id="d491e-168">新-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="d491e-168">New-CsCallingLineIdentity</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)
- [<span data-ttu-id="d491e-169">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="d491e-169">Assign policies to your users in Teams</span></span>](assign-policies.md)
