---
title: 在 Microsoft 團隊中管理語音路由策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords: ''
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中建立及管理語音路由原則。
ms.openlocfilehash: 061e8066e06c4514a27ea302dab96acfad004ac4
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350187"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a><span data-ttu-id="744e3-103">在 Microsoft 團隊中管理語音路由策略</span><span class="sxs-lookup"><span data-stu-id="744e3-103">Manage voice routing policies in Microsoft Teams</span></span>

<span data-ttu-id="744e3-104">如果您已在組織中部署[電話系統直接路由](direct-routing-landing-page.md)，您可以使用 [語音路由策略]，讓小組和商務用 Skype Online 使用者透過您的內部部署電話結構接收並撥打電話給公開的交換電話網絡（PSTN）。</span><span class="sxs-lookup"><span data-stu-id="744e3-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you use voice routing policies to allow Teams and Skype for Business Online users to receive and make phone calls to the Public Switched Telephone Network (PSTN) using your on-premises telephony infrastructure.</span></span>

<span data-ttu-id="744e3-105">[語音路由策略] 是 PSTN 使用記錄的容器。</span><span class="sxs-lookup"><span data-stu-id="744e3-105">A voice routing policy is a container for PSTN usage records.</span></span> <span data-ttu-id="744e3-106">您可以移至**Voice**  >  Microsoft 團隊系統管理中心的語音**語音路由策略**，或使用 Windows PowerShell，來建立及管理語音路由原則。</span><span class="sxs-lookup"><span data-stu-id="744e3-106">You create and manage voice routing policies by going to **Voice** > **Voice routing policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

<span data-ttu-id="744e3-107">您可以使用全域（組織範圍預設值）原則，或建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="744e3-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="744e3-108">除非您建立並指派自訂原則，否則使用者會自動取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="744e3-108">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="744e3-109">請記住，您可以編輯全域原則中的設定，但無法重新命名或刪除。</span><span class="sxs-lookup"><span data-stu-id="744e3-109">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span>

<span data-ttu-id="744e3-110">請務必注意，將語音路由策略指派給使用者並不能讓他們在團隊中進行 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="744e3-110">It's important to know that assigning a voice routing policy to a user doesn't enable them to make PSTN calls in Teams.</span></span> <span data-ttu-id="744e3-111">您也需要讓使用者使用 [電話系統直接路由]，並完成其他配置步驟。</span><span class="sxs-lookup"><span data-stu-id="744e3-111">You'll also need to enable the user for Phone System Direct Routing and complete other configuration steps.</span></span> <span data-ttu-id="744e3-112">若要深入瞭解，請參閱[設定直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="744e3-112">To learn more, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="create-a-custom-voice-routing-policy"></a><span data-ttu-id="744e3-113">建立自訂的語音路由策略</span><span class="sxs-lookup"><span data-stu-id="744e3-113">Create a custom voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="744e3-114">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="744e3-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="744e3-115">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音**  >  **語音路由策略**]，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="744e3-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span><br>
    <span data-ttu-id="744e3-116">![Microsoft 團隊系統管理中心 [新增語音路由策略] 頁面的螢幕擷取畫面](media/manage-voice-routing-policies.png)</span><span class="sxs-lookup"><span data-stu-id="744e3-116">![Screenshot of the Add voice routing policy page in the Microsoft Teams admin center ](media/manage-voice-routing-policies.png)</span></span> 
2. <span data-ttu-id="744e3-117">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="744e3-117">Enter a name and description for the policy.</span></span>
3. <span data-ttu-id="744e3-118">在 [ **PSTN 使用記錄**] 底下，按一下 [**新增 PSTN 使用量**]，然後選取您要新增的記錄。</span><span class="sxs-lookup"><span data-stu-id="744e3-118">Under **PSTN usage records**, click **Add PSTN usage**, and then select the records that you want to add.</span></span> <span data-ttu-id="744e3-119">如果您需要建立新的 PSTN 使用記錄，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="744e3-119">If you need to create a new PSTN usage record, click **Add**.</span></span>
4. <span data-ttu-id="744e3-120">如果您已新增多個 PSTN 使用記錄，請依您想要的順序排列它們。</span><span class="sxs-lookup"><span data-stu-id="744e3-120">If you added multiple PSTN usage records, arrange them in the order that you want.</span></span>
5. <span data-ttu-id="744e3-121">完成後，**請按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="744e3-121">When you're done, click **Apply**.</span></span>
6. <span data-ttu-id="744e3-122">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="744e3-122">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="744e3-123">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="744e3-123">Using PowerShell</span></span>

<span data-ttu-id="744e3-124">請參閱[新-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="744e3-124">See [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

## <a name="edit-a-voice-routing-policy"></a><span data-ttu-id="744e3-125">編輯語音路由策略</span><span class="sxs-lookup"><span data-stu-id="744e3-125">Edit a voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="744e3-126">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="744e3-126">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="744e3-127">您可以編輯全域原則或您建立的任何自訂原則。</span><span class="sxs-lookup"><span data-stu-id="744e3-127">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="744e3-128">在 Microsoft [團隊管理中心] 的左導覽中，移至 [**語音**  >  **語音路由策略**]。</span><span class="sxs-lookup"><span data-stu-id="744e3-128">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="744e3-129">按一下原則名稱左邊的，然後按一下 [**編輯**]，選取原則。</span><span class="sxs-lookup"><span data-stu-id="744e3-129">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="744e3-130">按一下 [**新增/移除 PSTN 使用記錄**]，進行您要的變更，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="744e3-130">Click **Add/remove PSTN usage records**, make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="744e3-131">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="744e3-131">Using PowerShell</span></span>

<span data-ttu-id="744e3-132">請參閱[設定 CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="744e3-132">See [Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span></span>

## <a name="assign-a-custom-voice-routing-policy-to-users"></a><span data-ttu-id="744e3-133">指派自訂的語音路由策略給使用者</span><span class="sxs-lookup"><span data-stu-id="744e3-133">Assign a custom voice routing policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="744e3-134">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="744e3-134">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="744e3-135">若要將原則指派給一個使用者：</span><span class="sxs-lookup"><span data-stu-id="744e3-135">To assign a policy to one user:</span></span>

1. <span data-ttu-id="744e3-136">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]\*\*\*\*，然後按一下該使用者。</span><span class="sxs-lookup"><span data-stu-id="744e3-136">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="744e3-137">按一下 [**原則**]，然後在 [**指派的原則**] 旁，按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="744e3-137">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="744e3-138">在 [**語音路由策略**] 底下，選取您要指派的原則，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="744e3-138">Under **Voice routing policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="744e3-139">若要一次將原則指派給多位使用者：</span><span class="sxs-lookup"><span data-stu-id="744e3-139">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="744e3-140">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**使用者**]，然後搜尋使用者或篩選視圖，以顯示您想要的使用者。</span><span class="sxs-lookup"><span data-stu-id="744e3-140">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="744e3-141">在 [ **&#x2713;** （核取符號）] 欄中，選取使用者。</span><span class="sxs-lookup"><span data-stu-id="744e3-141">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="744e3-142">若要選取 [所有使用者]，請按一下表格頂端的 [&#x2713; （核取符號）。</span><span class="sxs-lookup"><span data-stu-id="744e3-142">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="744e3-143">按一下 [**編輯設定**]，進行您想要的變更，然後按一下 [套用 **]。**</span><span class="sxs-lookup"><span data-stu-id="744e3-143">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="744e3-144">或者，您也可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="744e3-144">Or, you can also do the following:</span></span>

1. <span data-ttu-id="744e3-145">在 Microsoft [團隊管理中心] 的左導覽中，移至 [**語音**  >  **語音路由策略**]。</span><span class="sxs-lookup"><span data-stu-id="744e3-145">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="744e3-146">按一下原則名稱的左側來選取原則。</span><span class="sxs-lookup"><span data-stu-id="744e3-146">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="744e3-147">選取 [管理使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="744e3-147">Select **Manage users**.</span></span>
4. <span data-ttu-id="744e3-148">在 **[管理使用者]** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="744e3-148">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="744e3-149">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="744e3-149">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="744e3-150">完成新增使用者後，請按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="744e3-150">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="744e3-151">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="744e3-151">Using PowerShell</span></span>

<span data-ttu-id="744e3-152">請參閱[授與 CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="744e3-152">See [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="744e3-153">相關主題</span><span class="sxs-lookup"><span data-stu-id="744e3-153">Related topics</span></span>

- [<span data-ttu-id="744e3-154">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="744e3-154">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="744e3-155">設定直接路由的語音路由</span><span class="sxs-lookup"><span data-stu-id="744e3-155">Configure voice routing for Direct Routing</span></span>](direct-routing-voice-routing.md)
- [<span data-ttu-id="744e3-156">啟用直接路由的依位置路由</span><span class="sxs-lookup"><span data-stu-id="744e3-156">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
- [<span data-ttu-id="744e3-157">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="744e3-157">Assign policies to your users in Teams</span></span>](assign-policies.md)
