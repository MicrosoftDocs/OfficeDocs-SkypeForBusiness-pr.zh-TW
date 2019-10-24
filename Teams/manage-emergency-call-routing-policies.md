---
title: 管理 Microsoft 團隊中的緊急通話路由原則
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
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中針對動態 E911 功能使用和管理緊急通話路由策略。
f1keywords: ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: e5fe0957ce0c329f8161690fea7128036e2e1777
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37639161"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a><span data-ttu-id="9d6f7-103">管理 Microsoft 團隊中的緊急通話路由原則</span><span class="sxs-lookup"><span data-stu-id="9d6f7-103">Manage emergency call routing policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="9d6f7-104">如果您已在組織中部署電話系統直接路由，您可以使用 Microsoft 團隊中的緊急呼叫路由策略來設定緊急電話號碼，並指定緊急通話的傳送方式。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-104">If you've deployed Phone System Direct Routing in your organization, you can use emergency call routing policies in Microsoft Teams to set up emergency numbers and specify how emergency calls are routed.</span></span> <span data-ttu-id="9d6f7-105">緊急呼叫路由策略會判斷是否針對獲指派原則的使用者、用來呼叫緊急服務的號碼（例如，911在美國），以及如何路由緊急服務通話。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-105">An emergency call routing policy determines whether enhanced emergency services is enabled for users who are assigned the policy, the numbers used to call emergency services (for example, 911 in the United States), and how calls to emergency services are routed.</span></span>

<span data-ttu-id="9d6f7-106">您可以在 Microsoft 團隊系統管理中心或使用 Windows PowerShell 移至**語音** > **緊急策略**，管理緊急通話路由原則。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-106">You manage emergency call routing policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="9d6f7-107">您可以將原則指派給使用者和[網路網站](location-based-routing-terminology.md)。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-107">The policies can be assigned to users and [network sites](location-based-routing-terminology.md).</span></span>

<span data-ttu-id="9d6f7-108">針對使用者，您可以使用全域（組織範圍預設值）原則，或建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-108">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="9d6f7-109">除非您建立並指派自訂原則，否則使用者會自動取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-109">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="9d6f7-110">請記住，您可以編輯全域原則中的設定，但無法重新命名或刪除。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-110">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="9d6f7-111">針對網路網站，您可以建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-111">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="9d6f7-112">如果您已將緊急呼叫路由原則指派給網路網站和使用者，而且如果該使用者是在該網路網站上，則指派給網路網站的原則會覆寫指派給使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-112">If you assigned an emergency call routing policy to a network site and to a user and if that  user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-call-routing-policy"></a><span data-ttu-id="9d6f7-113">建立自訂緊急通話路由策略</span><span class="sxs-lookup"><span data-stu-id="9d6f7-113">Create a custom emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="9d6f7-114">使用 Microsoft 團隊系統管理中心</span><span class="sxs-lookup"><span data-stu-id="9d6f7-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="9d6f7-115">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音** > **緊急原則**]，然後按一下 [**呼叫路由策略**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="9d6f7-116">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-116">Click **Add**.</span></span>
3. <span data-ttu-id="9d6f7-117">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-117">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="9d6f7-118">若要啟用 [增強的緊急服務]，請開啟 [**增強的緊急服務**]。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-118">To enable enhanced emergency services, turn on **Enhanced emergency services**.</span></span> <span data-ttu-id="9d6f7-119">啟用 [增強緊急服務] 時，小組會從服務中檢索原則和位置資訊，並將該資訊包含在緊急通話中。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-119">When enhanced emergency services is enabled, Teams retrieves policy and location information from the service and includes that information as part of the emergency call.</span></span>
5. <span data-ttu-id="9d6f7-120">定義其中一個緊急電話號碼。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-120">Define one of more emergency numbers.</span></span> <span data-ttu-id="9d6f7-121">若要執行此動作，請在 [**緊急數位**] 底下，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="9d6f7-121">To do this, under **Emergency numbers**, do the following:</span></span>
    1. <span data-ttu-id="9d6f7-122">[**緊急撥號字串**]：輸入 [緊急撥號字串]。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-122">**Emergency dial string**: Enter the emergency dial string.</span></span> <span data-ttu-id="9d6f7-123">這個撥號字串表示通話是緊急通話。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-123">This dial string indicates that a call is an emergency call.</span></span>
    2. <span data-ttu-id="9d6f7-124">**緊急撥號遮罩**：針對每個緊急電話號碼，您可以指定零個或多個緊急撥號遮罩。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-124">**Emergency dial mask**: For each emergency number, you can specify zero or more emergency dial masks.</span></span> <span data-ttu-id="9d6f7-125">撥號遮罩是您要翻譯成緊急撥號字串值的數位。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-125">A dial mask is the number that you want to translate into the value of the emergency dial string.</span></span> <span data-ttu-id="9d6f7-126">這可讓您撥打備用的緊急電話號碼，仍能取得緊急通話服務的來電。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-126">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services.</span></span> <br><span data-ttu-id="9d6f7-127">例如，您會將112新增為緊急撥號遮罩，這是大多數歐洲的緊急服務號碼，而911則是緊急撥號字串。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-127">For example, you add 112 as the emergency dial mask, which is the emergency service number for most of Europe, and 911 as the emergency dial string.</span></span> <span data-ttu-id="9d6f7-128">歐洲造訪的團隊使用者可能不知道911是美國的緊急電話號碼，而且當他們撥打112時，通話是911。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-128">A Teams user from Europe who is visiting may not know that 911 is the emergency number in the United States, and when they dial 112, the call is made to 911.</span></span> <span data-ttu-id="9d6f7-129">若要定義多個撥號遮罩，請以分號分隔每個值。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-129">To define multiple dial masks, separate each value by a semicolon.</span></span> <span data-ttu-id="9d6f7-130">例如，112; 212。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-130">For example, 112;212.</span></span>
    3. <span data-ttu-id="9d6f7-131">**PSTN 使用量**：選取 [公開交換電話網絡（PSTN）] 的使用方式。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-131">**PSTN Usage**: Select the public switched telephone network (PSTN) usage.</span></span> <span data-ttu-id="9d6f7-132">PSTN 使用量是用來判斷使用哪個路由來傳送緊急呼叫給有權使用的使用者。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-132">The PSTN usage is used to determine which route is used to route emergency calls from users who are authorized to use them.</span></span> <span data-ttu-id="9d6f7-133">與此使用相關聯的路線應該指向專用於緊急通話的 SIP 幹線，或指向將緊急呼叫路由到最接近的公用安全應答點（PSAP）的緊急位置識別號碼（ELIN）閘道。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-133">The route associated with this usage should point to an SIP trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>

    > [!NOTE]
    > <span data-ttu-id="9d6f7-134">撥號字串和撥號遮罩在原則中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-134">Dial strings and dial masks must be unique within a policy.</span></span> <span data-ttu-id="9d6f7-135">這表示對於原則而言，您可以定義多個緊急電話號碼，而且您可以為撥號字串設定多個撥號遮罩，但每個撥號字串和撥號遮罩只能使用一次。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-135">This means that for a policy, you can define multiple emergency numbers and you can set multiple dial masks for a dial string, but each dial string and dial mask must only be used one time.</span></span>

6. <span data-ttu-id="9d6f7-136">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-136">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="9d6f7-137">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d6f7-137">Using PowerShell</span></span>

<span data-ttu-id="9d6f7-138">請參閱[新-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-138">See [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span></span>

## <a name="edit-an-emergency-call-routing-policy"></a><span data-ttu-id="9d6f7-139">編輯緊急通話路由策略</span><span class="sxs-lookup"><span data-stu-id="9d6f7-139">Edit an emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="9d6f7-140">使用 Microsoft 團隊系統管理中心</span><span class="sxs-lookup"><span data-stu-id="9d6f7-140">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="9d6f7-141">您可以編輯全域原則或您建立的任何自訂原則。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-141">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="9d6f7-142">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音** > **緊急原則**]，然後按一下 [**呼叫路由策略**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-142">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="9d6f7-143">按一下原則名稱左邊的，然後按一下 [**編輯**]，選取原則。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-143">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="9d6f7-144">進行您想要的變更，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-144">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="9d6f7-145">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d6f7-145">Using PowerShell</span></span>

<span data-ttu-id="9d6f7-146">請參閱[設定 CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-146">See [Set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a><span data-ttu-id="9d6f7-147">將自訂緊急通話路由原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="9d6f7-147">Assign a custom emergency call routing policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="9d6f7-148">使用 Microsoft 團隊系統管理中心</span><span class="sxs-lookup"><span data-stu-id="9d6f7-148">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="9d6f7-149">在 Microsoft 團隊系統管理中心的左導覽中，前往 [**使用者**]，然後按一下使用者。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-149">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="9d6f7-150">按一下 [**原則**]，然後在 [**指派的原則**] 旁，按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-150">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="9d6f7-151">在 [**緊急呼叫路由策略**] 底下，選取您要指派的原則，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-151">Under **Emergency call routing policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="9d6f7-152">若要一次將自訂團隊原則指派給多位使用者，請參閱[大量編輯團隊使用者設定](edit-user-settings-in-bulk.md)。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-152">To assign a custom teams policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="9d6f7-153">或者，您也可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="9d6f7-153">Or, you can also do the following:</span></span>

1. <span data-ttu-id="9d6f7-154">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音** > **緊急原則**]，然後按一下 [**呼叫路由策略**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-154">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="9d6f7-155">按一下原則名稱左方，選取原則。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-155">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="9d6f7-156">選取 [**管理使用者**]。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-156">Select **Manage users**.</span></span>
4. <span data-ttu-id="9d6f7-157">在 [**管理使用者**] 窗格中，依 [顯示名稱] 或 [使用者名稱] 搜尋使用者，選取名稱，然後選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-157">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="9d6f7-158">針對您要新增的每個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-158">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="9d6f7-159">完成新增使用者後，請按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-159">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="9d6f7-160">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d6f7-160">Using PowerShell</span></span>

#### <a name="assign-a-custom-emergency-call-routing-policy-to-a-user"></a><span data-ttu-id="9d6f7-161">將自訂緊急通話路由原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="9d6f7-161">Assign a custom emergency call routing policy to a user</span></span>

<span data-ttu-id="9d6f7-162">請參閱[授與 CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-162">See [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span></span>

### <a name="assign-a-custom-emergency-call-routing-policy-to-users-in-a-group"></a><span data-ttu-id="9d6f7-163">將自訂緊急通話路由原則指派給群組中的使用者</span><span class="sxs-lookup"><span data-stu-id="9d6f7-163">Assign a custom emergency call routing policy to users in a group</span></span>

<span data-ttu-id="9d6f7-164">您可能會想要將自訂緊急呼叫路由策略指派給已識別的多個使用者。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-164">You may want to assign a custom emergency call routing policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="9d6f7-165">例如，您可能會想要將原則指派給安全性或通訊群組中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-165">For example, you may want to assign a policy to all users in a security or distribution group.</span></span> <span data-ttu-id="9d6f7-166">您可以透過連線到 Azure Active Directory PowerShell for Graph 模組及商務用 Skype PowerShell 模組來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-166">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span>

<span data-ttu-id="9d6f7-167">在這個範例中，我們將稱為 [人力資源緊急呼叫路由策略] 的原則指派給 [Contoso HR] 群組中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-167">In this example, we assign a policy called HR Emergency Call Routing Policy to all users in the Contoso HR group.</span></span>  

> [!NOTE]
> <span data-ttu-id="9d6f7-168">請依照在[單一 Windows PowerShell 視窗中連線至 [所有 Office 365 服務]](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步驟，確認您首先連線至 [圖形模組] 和 [商務用 Skype] powershell 模組的 [Azure Active Directory PowerShell]。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-168">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="9d6f7-169">取得特定群組的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-169">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso HR"
```
<span data-ttu-id="9d6f7-170">取得指定群組的成員。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-170">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="9d6f7-171">將群組中的所有使用者指派給特定的團隊原則。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-171">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="9d6f7-172">在這個範例中，它是 HR 緊急通話路由原則。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-172">In this example, it's HR Emergency Call Routing Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "HR Emergency Call Routing Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="9d6f7-173">根據群組中的成員數目而定，此命令可能需要幾分鐘的時間執行。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-173">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a><span data-ttu-id="9d6f7-174">將自訂緊急通話路由原則指派給網路網站</span><span class="sxs-lookup"><span data-stu-id="9d6f7-174">Assign a custom emergency call routing policy to a network site</span></span>

<span data-ttu-id="9d6f7-175">使用[CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) Cmdlet，將緊急呼叫路由策略指派給網路網站。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-175">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling routing policy to a network site.</span></span>

<span data-ttu-id="9d6f7-176">這個範例示範如何將稱為緊急呼叫路由策略1的原則指派給 Site1 網站。</span><span class="sxs-lookup"><span data-stu-id="9d6f7-176">This example shows how to assign a policy called Emergency Call Routing Policy 1 to the Site1 site.</span></span>

```
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="9d6f7-177">相關主題</span><span class="sxs-lookup"><span data-stu-id="9d6f7-177">Related topics</span></span>

- [<span data-ttu-id="9d6f7-178">管理團隊中的緊急通話原則</span><span class="sxs-lookup"><span data-stu-id="9d6f7-178">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="9d6f7-179">團隊 PowerShell 概覽</span><span class="sxs-lookup"><span data-stu-id="9d6f7-179">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
