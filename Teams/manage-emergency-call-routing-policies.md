---
title: 管理緊急電話路由原則
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords: ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何使用及管理 Microsoft 團隊中的緊急呼叫路由策略，以設定緊急電話號碼，以及指定如何傳送緊急通話。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b573543483d41219d2795043f47042789bc855ba
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539520"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a><span data-ttu-id="16a0d-103">管理 Microsoft 團隊中的緊急通話路由原則</span><span class="sxs-lookup"><span data-stu-id="16a0d-103">Manage emergency call routing policies in Microsoft Teams</span></span>

<span data-ttu-id="16a0d-104">如果您已在組織中部署[電話系統直接路由](direct-routing-landing-page.md)，您可以使用 Microsoft 團隊中的緊急呼叫路由策略來設定緊急電話號碼，並指定緊急通話的傳送方式。</span><span class="sxs-lookup"><span data-stu-id="16a0d-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you can use emergency call routing policies in Microsoft Teams to set up emergency numbers and specify how emergency calls are routed.</span></span> <span data-ttu-id="16a0d-105">緊急呼叫路由策略會判斷是否針對獲指派原則的使用者、用來呼叫緊急服務的號碼（例如，911在美國），以及如何路由緊急服務通話。</span><span class="sxs-lookup"><span data-stu-id="16a0d-105">An emergency call routing policy determines whether enhanced emergency services is enabled for users who are assigned the policy, the numbers used to call emergency services (for example, 911 in the United States), and how calls to emergency services are routed.</span></span>

<span data-ttu-id="16a0d-106">您可以**Voice**  >  在 Microsoft 團隊系統管理中心或使用 Windows PowerShell 移至語音**緊急策略**，管理緊急通話路由原則。</span><span class="sxs-lookup"><span data-stu-id="16a0d-106">You manage emergency call routing policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="16a0d-107">您可以將原則指派給使用者和[網路網站](cloud-voice-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="16a0d-107">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="16a0d-108">針對使用者，您可以使用全域（組織範圍預設值）原則，或建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="16a0d-108">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="16a0d-109">除非您建立並指派自訂原則，否則使用者會自動取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="16a0d-109">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="16a0d-110">請記住，您可以編輯全域原則中的設定，但無法重新命名或刪除。</span><span class="sxs-lookup"><span data-stu-id="16a0d-110">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="16a0d-111">針對網路網站，您可以建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="16a0d-111">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="16a0d-112">如果您已將緊急呼叫路由原則指派給網路網站和使用者，而且如果該使用者是在該網路網站上，則指派給網路網站的原則會覆寫指派給使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="16a0d-112">If you assigned an emergency call routing policy to a network site and to a user and if that  user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-call-routing-policy"></a><span data-ttu-id="16a0d-113">建立自訂緊急通話路由策略</span><span class="sxs-lookup"><span data-stu-id="16a0d-113">Create a custom emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="16a0d-114">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="16a0d-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="16a0d-115">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音**  >  **緊急原則**]，然後按一下 [**呼叫路由策略**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="16a0d-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="16a0d-116">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="16a0d-116">Click **Add**.</span></span>
3. <span data-ttu-id="16a0d-117">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="16a0d-117">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="16a0d-118">若要啟用動態緊急通話，請開啟 [**動態緊急通話**]。</span><span class="sxs-lookup"><span data-stu-id="16a0d-118">To enable dynamic emergency calling, turn on **Dynamic emergency calling**.</span></span> <span data-ttu-id="16a0d-119">啟用動態緊急通話時，小組會從服務中檢索原則和位置資訊，並將該資訊包含在緊急通話中。</span><span class="sxs-lookup"><span data-stu-id="16a0d-119">When dynamic emergency calling is enabled, Teams retrieves policy and location information from the service and includes that information as part of the emergency call.</span></span>
5. <span data-ttu-id="16a0d-120">定義一或多個緊急電話號碼。</span><span class="sxs-lookup"><span data-stu-id="16a0d-120">Define one or more emergency numbers.</span></span> <span data-ttu-id="16a0d-121">若要這樣做，請在 [**緊急數位**] 底下，按一下 [**新增**]，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="16a0d-121">To do this, under **Emergency numbers**, click **Add**, and then do the following:</span></span>
    1. <span data-ttu-id="16a0d-122">[**緊急撥號字串**]：輸入 [緊急撥號字串]。</span><span class="sxs-lookup"><span data-stu-id="16a0d-122">**Emergency dial string**: Enter the emergency dial string.</span></span> <span data-ttu-id="16a0d-123">這個撥號字串表示通話是緊急通話。</span><span class="sxs-lookup"><span data-stu-id="16a0d-123">This dial string indicates that a call is an emergency call.</span></span>
        > [!NOTE]
        > <span data-ttu-id="16a0d-124">在直接路由中，我們正從緊急撥號字串前面的「+」傳送緊急通話的小組用戶端轉移。</span><span class="sxs-lookup"><span data-stu-id="16a0d-124">For Direct Routing, we're transitioning away from Teams clients sending emergency calls with a "+" in front of the emergency dial string.</span></span> <span data-ttu-id="16a0d-125">在轉換完成之前，與緊急撥號字串相符的語音路由模式應該可確保符合的字串有且沒有前面的 "+" （例如911和 + 911）。</span><span class="sxs-lookup"><span data-stu-id="16a0d-125">Until the transition is completed, the voice route pattern to match an emergency dial string should ensure a match is made for strings that have and don't have a preceding "+", such as 911 and +911.</span></span> <span data-ttu-id="16a0d-126">例如，^ \\ +？911或. \*。</span><span class="sxs-lookup"><span data-stu-id="16a0d-126">For example, ^\\+?911 or .\*.</span></span>
    2. <span data-ttu-id="16a0d-127">**緊急撥號遮罩**：針對每個緊急電話號碼，您可以指定零個或多個緊急撥號遮罩。</span><span class="sxs-lookup"><span data-stu-id="16a0d-127">**Emergency dial mask**: For each emergency number, you can specify zero or more emergency dial masks.</span></span> <span data-ttu-id="16a0d-128">撥號遮罩是您要翻譯成緊急撥號字串值的數位。</span><span class="sxs-lookup"><span data-stu-id="16a0d-128">A dial mask is the number that you want to translate into the value of the emergency dial string.</span></span> <span data-ttu-id="16a0d-129">這可讓您撥打備用的緊急電話號碼，仍能取得緊急通話服務的來電。</span><span class="sxs-lookup"><span data-stu-id="16a0d-129">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services.</span></span> <br><span data-ttu-id="16a0d-130">例如，您會將112新增為緊急撥號遮罩，這是大多數歐洲的緊急服務號碼，而911則是緊急撥號字串。</span><span class="sxs-lookup"><span data-stu-id="16a0d-130">For example, you add 112 as the emergency dial mask, which is the emergency service number for most of Europe, and 911 as the emergency dial string.</span></span> <span data-ttu-id="16a0d-131">歐洲造訪的團隊使用者可能不知道911是美國的緊急電話號碼，而且當他們撥打112時，通話是911。</span><span class="sxs-lookup"><span data-stu-id="16a0d-131">A Teams user from Europe who is visiting may not know that 911 is the emergency number in the United States, and when they dial 112, the call is made to 911.</span></span> <span data-ttu-id="16a0d-132">若要定義多個撥號遮罩，請以分號分隔每個值。</span><span class="sxs-lookup"><span data-stu-id="16a0d-132">To define multiple dial masks, separate each value by a semicolon.</span></span> <span data-ttu-id="16a0d-133">例如，112; 212。</span><span class="sxs-lookup"><span data-stu-id="16a0d-133">For example, 112;212.</span></span>
    3. <span data-ttu-id="16a0d-134">**PSTN 使用記錄**：選取 [公用交換電話網絡（PSTN）使用量] 記錄。</span><span class="sxs-lookup"><span data-stu-id="16a0d-134">**PSTN usage record**: Select the Public Switched Telephone Network (PSTN) usage record.</span></span> <span data-ttu-id="16a0d-135">PSTN 使用記錄是用來判斷使用哪個路由來傳送緊急呼叫給有權使用的使用者。</span><span class="sxs-lookup"><span data-stu-id="16a0d-135">The PSTN usage record is used to determine which route is used to route emergency calls from users who are authorized to use them.</span></span> <span data-ttu-id="16a0d-136">與此使用相關聯的路由應該指向專用於緊急通話的會話初始通訊協定（SIP）主幹，或傳送緊急位置識別號碼（ELIN）閘道，並將緊急呼叫路由到最接近的公用安全應答點（PSAP）。</span><span class="sxs-lookup"><span data-stu-id="16a0d-136">The route associated with this usage should point to a Session Initiation Protocol (SIP) trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>

    > [!NOTE]
    > <span data-ttu-id="16a0d-137">撥號字串和撥號遮罩在原則中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="16a0d-137">Dial strings and dial masks must be unique within a policy.</span></span> <span data-ttu-id="16a0d-138">這表示對於原則而言，您可以定義多個緊急電話號碼，而且您可以為撥號字串設定多個撥號遮罩，但每個撥號字串和撥號遮罩只能使用一次。</span><span class="sxs-lookup"><span data-stu-id="16a0d-138">This means that for a policy, you can define multiple emergency numbers and you can set multiple dial masks for a dial string, but each dial string and dial mask must only be used one time.</span></span>

6. <span data-ttu-id="16a0d-139">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="16a0d-139">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="16a0d-140">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="16a0d-140">Using PowerShell</span></span>

<span data-ttu-id="16a0d-141">請參閱[新-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="16a0d-141">See [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span></span>

## <a name="edit-an-emergency-call-routing-policy"></a><span data-ttu-id="16a0d-142">編輯緊急通話路由策略</span><span class="sxs-lookup"><span data-stu-id="16a0d-142">Edit an emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="16a0d-143">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="16a0d-143">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="16a0d-144">您可以編輯全域原則或您建立的任何自訂原則。</span><span class="sxs-lookup"><span data-stu-id="16a0d-144">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="16a0d-145">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音**  >  **緊急原則**]，然後按一下 [**呼叫路由策略**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="16a0d-145">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="16a0d-146">按一下原則名稱左邊的，然後按一下 [**編輯**]，選取原則。</span><span class="sxs-lookup"><span data-stu-id="16a0d-146">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="16a0d-147">進行您想要的變更，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="16a0d-147">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="16a0d-148">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="16a0d-148">Using PowerShell</span></span>

<span data-ttu-id="16a0d-149">請參閱[設定 CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="16a0d-149">See [Set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a><span data-ttu-id="16a0d-150">將自訂緊急通話路由原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="16a0d-150">Assign a custom emergency call routing policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="16a0d-151">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="16a0d-151">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="16a0d-152">若要將原則指派給一個使用者：</span><span class="sxs-lookup"><span data-stu-id="16a0d-152">To assign a policy to one user:</span></span>

1. <span data-ttu-id="16a0d-153">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]\*\*\*\*，然後按一下該使用者。</span><span class="sxs-lookup"><span data-stu-id="16a0d-153">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="16a0d-154">按一下 [**原則**]，然後在 [**指派的原則**] 旁，按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="16a0d-154">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="16a0d-155">在 [**緊急呼叫路由策略**] 底下，選取您要指派的原則，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="16a0d-155">Under **Emergency call routing policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="16a0d-156">若要一次將原則指派給多位使用者：</span><span class="sxs-lookup"><span data-stu-id="16a0d-156">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="16a0d-157">在 Microsoft Teams 系統管理中心的左側瀏覽中，移至 [使用者]\*\*\*\*，然後搜尋使用者或篩選檢視畫面，以顯示您想要的使用者。</span><span class="sxs-lookup"><span data-stu-id="16a0d-157">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="16a0d-158">在 [&#x2713;]\*\*\*\* (核取方塊) 欄中，選取使用者。</span><span class="sxs-lookup"><span data-stu-id="16a0d-158">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="16a0d-159">若要選取 [所有使用者]，請按一下表格頂端的 [&#x2713;] (核取方塊)。</span><span class="sxs-lookup"><span data-stu-id="16a0d-159">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="16a0d-160">按一下 [編輯設定]\*\*\*\*，進行所需的變更，然後按一下 [套用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="16a0d-160">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="16a0d-161">或者，您也可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="16a0d-161">Or, you can also do the following:</span></span>

1. <span data-ttu-id="16a0d-162">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音**  >  **緊急原則**]，然後按一下 [**呼叫路由策略**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="16a0d-162">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="16a0d-163">按一下原則名稱的左側來選取原則。</span><span class="sxs-lookup"><span data-stu-id="16a0d-163">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="16a0d-164">選取 [管理使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="16a0d-164">Select **Manage users**.</span></span>
4. <span data-ttu-id="16a0d-165">在 **[管理使用者]** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="16a0d-165">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="16a0d-166">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="16a0d-166">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="16a0d-167">完成新增使用者後，請按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="16a0d-167">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="16a0d-168">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="16a0d-168">Using PowerShell</span></span>

#### <a name="assign-a-custom-emergency-call-routing-policy-to-a-user"></a><span data-ttu-id="16a0d-169">將自訂緊急通話路由原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="16a0d-169">Assign a custom emergency call routing policy to a user</span></span>

<span data-ttu-id="16a0d-170">請參閱[授與 CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="16a0d-170">See [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span></span>

### <a name="assign-a-custom-emergency-call-routing-policy-to-users-in-a-group"></a><span data-ttu-id="16a0d-171">將自訂緊急通話路由原則指派給群組中的使用者</span><span class="sxs-lookup"><span data-stu-id="16a0d-171">Assign a custom emergency call routing policy to users in a group</span></span>

<span data-ttu-id="16a0d-172">您可能會想要將自訂緊急呼叫路由策略指派給已識別的多個使用者。</span><span class="sxs-lookup"><span data-stu-id="16a0d-172">You may want to assign a custom emergency call routing policy to multiple users that you've already identified.</span></span> <span data-ttu-id="16a0d-173">例如，您可能會想要將原則指派給安全性或通訊群組中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="16a0d-173">For example, you may want to assign a policy to all users in a security or distribution group.</span></span> <span data-ttu-id="16a0d-174">您可以透過連線到 Azure Active Directory PowerShell for Graph 模組及商務用 Skype PowerShell 模組來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="16a0d-174">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span>

<span data-ttu-id="16a0d-175">在這個範例中，我們將稱為 [人力資源緊急呼叫路由策略] 的原則指派給 [Contoso HR] 群組中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="16a0d-175">In this example, we assign a policy called HR Emergency Call Routing Policy to all users in the Contoso HR group.</span></span>  

> [!NOTE]
> <span data-ttu-id="16a0d-176">請依照在[單一 Windows PowerShell 視窗中連線至 [所有 Office 365 服務]](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步驟，確認您首先連線至 [圖形模組] 和 [商務用 Skype] powershell 模組的 [Azure Active Directory PowerShell]。</span><span class="sxs-lookup"><span data-stu-id="16a0d-176">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="16a0d-177">取得特定群組的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="16a0d-177">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso HR"
```
<span data-ttu-id="16a0d-178">取得指定群組的成員。</span><span class="sxs-lookup"><span data-stu-id="16a0d-178">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="16a0d-179">將群組中的所有使用者指派給特定的團隊原則。</span><span class="sxs-lookup"><span data-stu-id="16a0d-179">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="16a0d-180">在這個範例中，它是 HR 緊急通話路由原則。</span><span class="sxs-lookup"><span data-stu-id="16a0d-180">In this example, it's HR Emergency Call Routing Policy.</span></span>
```PowerShell
$members | ForEach-Object {Grant-CsTeamsEmergencyCallRoutingPolicy -PolicyName "HR Emergency Call Routing Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="16a0d-181">根據群組中的成員數目而定，此命令可能需要幾分鐘的時間執行。</span><span class="sxs-lookup"><span data-stu-id="16a0d-181">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a><span data-ttu-id="16a0d-182">將自訂緊急通話路由原則指派給網路網站</span><span class="sxs-lookup"><span data-stu-id="16a0d-182">Assign a custom emergency call routing policy to a network site</span></span>

<span data-ttu-id="16a0d-183">使用[CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) Cmdlet，將緊急呼叫路由策略指派給網路網站。</span><span class="sxs-lookup"><span data-stu-id="16a0d-183">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling routing policy to a network site.</span></span>

<span data-ttu-id="16a0d-184">這個範例示範如何將稱為緊急呼叫路由策略1的原則指派給 Site1 網站。</span><span class="sxs-lookup"><span data-stu-id="16a0d-184">This example shows how to assign a policy called Emergency Call Routing Policy 1 to the Site1 site.</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="16a0d-185">相關主題</span><span class="sxs-lookup"><span data-stu-id="16a0d-185">Related topics</span></span>

- [<span data-ttu-id="16a0d-186">管理團隊中的緊急通話原則</span><span class="sxs-lookup"><span data-stu-id="16a0d-186">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="16a0d-187">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="16a0d-187">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="16a0d-188">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="16a0d-188">Assign policies to your users in Teams</span></span>](assign-policies.md)
