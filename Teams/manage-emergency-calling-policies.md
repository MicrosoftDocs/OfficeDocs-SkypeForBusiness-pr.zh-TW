---
title: 管理 Microsoft 團隊中的緊急通話原則
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords: ms.teamsadmincenter.voice.emergencycallingpolicies.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中使用和管理緊急通話原則。
ms.openlocfilehash: 73404749b350f19abe248743dec7d3e740d50fc6
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836493"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="bf441-103">管理 Microsoft 團隊中的緊急通話原則</span><span class="sxs-lookup"><span data-stu-id="bf441-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="bf441-104">如果您的組織使用通話方案或部署的電話系統直傳送，您可以在 Microsoft 團隊中使用緊急通話原則，定義貴組織中的小組使用者進行緊急通話時所發生的動作。</span><span class="sxs-lookup"><span data-stu-id="bf441-104">If your organization uses Calling Plans or deployed Phone System Direct Routing, you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="bf441-105">您可以設定當指派策略呼叫緊急服務的使用者時，要通知的人員，以及傳送通知的方式。</span><span class="sxs-lookup"><span data-stu-id="bf441-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="bf441-106">例如，您可以將原則設定設定為自動通知貴組織的安全服務台，並讓他們聆聽緊急通話。</span><span class="sxs-lookup"><span data-stu-id="bf441-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="bf441-107">您可以移至 Microsoft 團隊系統管理中心的**語音** > **緊急策略**或使用 Windows PowerShell 來管理緊急通話原則。</span><span class="sxs-lookup"><span data-stu-id="bf441-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="bf441-108">您可以將原則指派給使用者和[網路網站](cloud-voice-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="bf441-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="bf441-109">針對使用者，您可以使用全域（組織範圍預設值）原則，或建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="bf441-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="bf441-110">除非您建立並指派自訂原則，否則使用者會自動取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="bf441-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="bf441-111">請記住，您可以編輯全域原則中的設定，但無法重新命名或刪除。</span><span class="sxs-lookup"><span data-stu-id="bf441-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="bf441-112">針對網路網站，您可以建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="bf441-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="bf441-113">如果您已將緊急呼叫原則指派給網路網站和使用者，而且如果該使用者是在該網路網站上，則指派給網路網站的原則會覆寫指派給使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="bf441-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="bf441-114">建立自訂緊急通話原則</span><span class="sxs-lookup"><span data-stu-id="bf441-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="bf441-115">使用 Microsoft 團隊系統管理中心</span><span class="sxs-lookup"><span data-stu-id="bf441-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="bf441-116">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音** > **緊急原則**]，然後按一下 [**通話原則**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="bf441-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="bf441-117">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="bf441-117">Click **Add**.</span></span>
3. <span data-ttu-id="bf441-118">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="bf441-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="bf441-119">在進行緊急通話時，設定您想要如何通知組織中的人員（通常是安全服務台）。</span><span class="sxs-lookup"><span data-stu-id="bf441-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="bf441-120">若要執行此動作，請在 [**通知模式]** 底下，選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="bf441-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="bf441-121">**僅通知**： [團隊聊天] 訊息會傳送給您指定的使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="bf441-121">**Notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="bf441-122">**Conferenced in 但已靜音**： [團隊聊天] 訊息會傳送給您指定的使用者和群組，而且他們可以在來電者與 PSAP 運算子之間的交談中聆聽（但不參與）。</span><span class="sxs-lookup"><span data-stu-id="bf441-122">**Conferenced in but are muted**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="bf441-123">如果您已選取 [Conferenced]，**但處於靜音**通知模式，請在 [**撥出電話號碼**] 方塊中輸入使用者或群組的 PSTN 電話號碼，即可呼叫並加入緊急通話。</span><span class="sxs-lookup"><span data-stu-id="bf441-123">If you selected the **Conferenced in but are muted** notification mode, in the **Dial-out number for notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="bf441-124">例如，輸入貴組織的 security 辦公桌編號，該號碼會在發出緊急通話時接聽來電，然後可以接聽電話或參與通話。</span><span class="sxs-lookup"><span data-stu-id="bf441-124">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in or participate in the call.</span></span>
6. <span data-ttu-id="bf441-125">搜尋並選取一或多個使用者或群組（例如貴組織的安全服務台），以在進行緊急通話時通知您。</span><span class="sxs-lookup"><span data-stu-id="bf441-125">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="bf441-126">通知可以傳送到使用者、通訊群組和安全性群組的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="bf441-126">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="bf441-127">最多可以通知50使用者。</span><span class="sxs-lookup"><span data-stu-id="bf441-127">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="bf441-128">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="bf441-128">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="bf441-129">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="bf441-129">Using PowerShell</span></span>

<span data-ttu-id="bf441-130">請參閱[新-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="bf441-130">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="bf441-131">編輯緊急通話原則</span><span class="sxs-lookup"><span data-stu-id="bf441-131">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="bf441-132">使用 Microsoft 團隊系統管理中心</span><span class="sxs-lookup"><span data-stu-id="bf441-132">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="bf441-133">您可以編輯全域原則或您建立的任何自訂原則。</span><span class="sxs-lookup"><span data-stu-id="bf441-133">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="bf441-134">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音** > **緊急原則**]，然後按一下 [**通話原則**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="bf441-134">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="bf441-135">按一下原則名稱左邊的，然後按一下 [**編輯**]，選取原則。</span><span class="sxs-lookup"><span data-stu-id="bf441-135">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="bf441-136">進行您想要的變更，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="bf441-136">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="bf441-137">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="bf441-137">Using PowerShell</span></span>

<span data-ttu-id="bf441-138">請參閱[設定 CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="bf441-138">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="bf441-139">將自訂緊急通話原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="bf441-139">Assign a custom emergency calling policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="bf441-140">使用 Microsoft 團隊系統管理中心</span><span class="sxs-lookup"><span data-stu-id="bf441-140">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="bf441-141">在 Microsoft 團隊系統管理中心的左導覽中，前往 [**使用者**]，然後按一下使用者。</span><span class="sxs-lookup"><span data-stu-id="bf441-141">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="bf441-142">按一下 [**原則**]，然後在 [**指派的原則**] 旁，按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="bf441-142">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="bf441-143">在 [**緊急通話原則**] 底下，選取您要指派的原則，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="bf441-143">Under **Emergency calling policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="bf441-144">若要一次將自訂團隊原則指派給多位使用者，請參閱[大量編輯團隊使用者設定](edit-user-settings-in-bulk.md)。</span><span class="sxs-lookup"><span data-stu-id="bf441-144">To assign a custom teams policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="bf441-145">或者，您也可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="bf441-145">Or, you can also do the following:</span></span>

1. <span data-ttu-id="bf441-146">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音** > **緊急原則**]，然後按一下 [**通話原則**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="bf441-146">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="bf441-147">按一下原則名稱左方，選取原則。</span><span class="sxs-lookup"><span data-stu-id="bf441-147">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="bf441-148">選取 [**管理使用者**]。</span><span class="sxs-lookup"><span data-stu-id="bf441-148">Select **Manage users**.</span></span>
4. <span data-ttu-id="bf441-149">在 [**管理使用者**] 窗格中，依 [顯示名稱] 或 [使用者名稱] 搜尋使用者，選取名稱，然後選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="bf441-149">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="bf441-150">針對您要新增的每個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="bf441-150">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="bf441-151">完成新增使用者後，請按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="bf441-151">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="bf441-152">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="bf441-152">Using PowerShell</span></span>

#### <a name="assign-a-custom-emergency-calling-policy-to-a-user"></a><span data-ttu-id="bf441-153">將自訂緊急通話原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="bf441-153">Assign a custom emergency calling policy to a user</span></span>

<span data-ttu-id="bf441-154">請參閱[授與 CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="bf441-154">See [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

#### <a name="assign-a-custom-emergency-calling-policy-to-users-in-a-group"></a><span data-ttu-id="bf441-155">將自訂緊急通話原則指派給群組中的使用者</span><span class="sxs-lookup"><span data-stu-id="bf441-155">Assign a custom emergency calling policy to users in a group</span></span>

<span data-ttu-id="bf441-156">您可能會想要將自訂緊急通話原則指派給已識別的多位使用者。</span><span class="sxs-lookup"><span data-stu-id="bf441-156">You may want to assign a custom emergency calling policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="bf441-157">例如，您可能會想要將原則指派給安全性群組中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="bf441-157">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="bf441-158">您可以透過連線到 Azure Active Directory PowerShell for Graph 模組及商務用 Skype PowerShell 模組來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="bf441-158">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span>

<span data-ttu-id="bf441-159">在這個範例中，我們會將一個名為「作業緊急通話」原則的原則指派給 Contoso 作業群組中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="bf441-159">In this example, we assign a policy called Operations Emergency Calling Policy to all users in the Contoso Operations group.</span></span>  

> [!NOTE]
> <span data-ttu-id="bf441-160">請依照在[單一 Windows PowerShell 視窗中連線至 [所有 Office 365 服務]](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步驟，確認您首先連線至 [圖形模組] 和 [商務用 Skype] powershell 模組的 [Azure Active Directory PowerShell]。</span><span class="sxs-lookup"><span data-stu-id="bf441-160">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="bf441-161">取得特定群組的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="bf441-161">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Operations"
```
<span data-ttu-id="bf441-162">取得指定群組的成員。</span><span class="sxs-lookup"><span data-stu-id="bf441-162">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="bf441-163">將群組中的所有使用者指派給特定的團隊原則。</span><span class="sxs-lookup"><span data-stu-id="bf441-163">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="bf441-164">在這個範例中，它是緊急呼叫路由策略的作業。</span><span class="sxs-lookup"><span data-stu-id="bf441-164">In this example, it's Operations Emergency Call Routing Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Operations Emergency Calling Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="bf441-165">根據群組中的成員數目而定，此命令可能需要幾分鐘的時間執行。</span><span class="sxs-lookup"><span data-stu-id="bf441-165">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="bf441-166">將自訂緊急通話原則指派給網路網站</span><span class="sxs-lookup"><span data-stu-id="bf441-166">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="bf441-167">使用[CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) Cmdlet 將緊急呼叫原則指派給網路網站。</span><span class="sxs-lookup"><span data-stu-id="bf441-167">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="bf441-168">下列範例顯示如何將稱為 Contoso 緊急呼叫原則1的原則指派給 Site1 網站。</span><span class="sxs-lookup"><span data-stu-id="bf441-168">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

    ```
    Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
    ```

## <a name="related-topics"></a><span data-ttu-id="bf441-169">相關主題</span><span class="sxs-lookup"><span data-stu-id="bf441-169">Related topics</span></span>

- [<span data-ttu-id="bf441-170">管理團隊中的緊急通話路由策略</span><span class="sxs-lookup"><span data-stu-id="bf441-170">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="bf441-171">團隊 PowerShell 概覽</span><span class="sxs-lookup"><span data-stu-id="bf441-171">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
