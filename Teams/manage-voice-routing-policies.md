---
title: 在 Microsoft Teams 中管理語音路由策略
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams 中建立和管理語音路由策略。
ms.openlocfilehash: ac856ef05d425208af43307ebe12ff0c4776ca51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101069"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a><span data-ttu-id="61a28-103">在 Microsoft Teams 中管理語音路由策略</span><span class="sxs-lookup"><span data-stu-id="61a28-103">Manage voice routing policies in Microsoft Teams</span></span>

<span data-ttu-id="61a28-104">如果您已經部署貴組織的電話[](direct-routing-landing-page.md)系統直接路由，您可以使用語音路由策略，允許 Teams 和商務用 Skype Online 使用者使用您的內部部署電話基礎結構接收及撥打公用交換電話網絡 (PSTN) 。</span><span class="sxs-lookup"><span data-stu-id="61a28-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you use voice routing policies to allow Teams and Skype for Business Online users to receive and make phone calls to the Public Switched Telephone Network (PSTN) using your on-premises telephony infrastructure.</span></span>

<span data-ttu-id="61a28-105">語音路由策略是 PSTN 使用方式記錄的容器。</span><span class="sxs-lookup"><span data-stu-id="61a28-105">A voice routing policy is a container for PSTN usage records.</span></span> <span data-ttu-id="61a28-106">若要建立和管理語音路由策略，請到Microsoft Teams 系統管理中心中的語音語音路由策略，或是  >  使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="61a28-106">You create and manage voice routing policies by going to **Voice** > **Voice routing policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

<span data-ttu-id="61a28-107">您可以使用全域 (全組織預設值) 原則，或建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="61a28-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="61a28-108">除非您建立並指派自訂策略，否則使用者會自動取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="61a28-108">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="61a28-109">請記住，您可以編輯全域原則中的設定，但無法重新命名或刪除。</span><span class="sxs-lookup"><span data-stu-id="61a28-109">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span>

<span data-ttu-id="61a28-110">請務必瞭解，指派語音路由策略給使用者無法讓他們在 Teams 中撥打 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="61a28-110">It's important to know that assigning a voice routing policy to a user doesn't enable them to make PSTN calls in Teams.</span></span> <span data-ttu-id="61a28-111">您也需要啟用電話系統直接路由的使用者，並完成其他組組步驟。</span><span class="sxs-lookup"><span data-stu-id="61a28-111">You'll also need to enable the user for Phone System Direct Routing and complete other configuration steps.</span></span> <span data-ttu-id="61a28-112">若要深入瞭解，請參閱 [設定直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="61a28-112">To learn more, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="create-a-custom-voice-routing-policy"></a><span data-ttu-id="61a28-113">建立自訂語音路由策略</span><span class="sxs-lookup"><span data-stu-id="61a28-113">Create a custom voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="61a28-114">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="61a28-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="61a28-115">在 Microsoft Teams 系統管理中心的左側導航中，前往 **[**  >  **語音語音路由規則**，然後按一下 [**新增**> 。</span><span class="sxs-lookup"><span data-stu-id="61a28-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span><br>
    <span data-ttu-id="61a28-116">![Microsoft Teams 系統管理中心中新增語音路由策略頁面的螢幕擷取畫面 ](media/manage-voice-routing-policies.png)</span><span class="sxs-lookup"><span data-stu-id="61a28-116">![Screenshot of the Add voice routing policy page in the Microsoft Teams admin center ](media/manage-voice-routing-policies.png)</span></span> 
2. <span data-ttu-id="61a28-117">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="61a28-117">Enter a name and description for the policy.</span></span>
3. <span data-ttu-id="61a28-118">在 **PSTN 使用量記錄下**，按一下 **[新增 PSTN 使用量**，然後選取要新增的記錄。</span><span class="sxs-lookup"><span data-stu-id="61a28-118">Under **PSTN usage records**, click **Add PSTN usage**, and then select the records that you want to add.</span></span> <span data-ttu-id="61a28-119">如果您需要建立新的 PSTN 使用記錄，請按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="61a28-119">If you need to create a new PSTN usage record, click **Add**.</span></span>
4. <span data-ttu-id="61a28-120">如果您新增了多個 PSTN 使用記錄，請以您想要的順序排列。</span><span class="sxs-lookup"><span data-stu-id="61a28-120">If you added multiple PSTN usage records, arrange them in the order that you want.</span></span>
5. <span data-ttu-id="61a28-121">完成後，請按一下 **[Apply.**</span><span class="sxs-lookup"><span data-stu-id="61a28-121">When you're done, click **Apply**.</span></span>
6. <span data-ttu-id="61a28-122">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="61a28-122">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="61a28-123">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="61a28-123">Using PowerShell</span></span>

<span data-ttu-id="61a28-124">請參閱 [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="61a28-124">See [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

## <a name="edit-a-voice-routing-policy"></a><span data-ttu-id="61a28-125">編輯語音路由策略</span><span class="sxs-lookup"><span data-stu-id="61a28-125">Edit a voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="61a28-126">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="61a28-126">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="61a28-127">您可以編輯全域原則或任何您建立的任何自訂策略。</span><span class="sxs-lookup"><span data-stu-id="61a28-127">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="61a28-128">在 Microsoft Teams 系統管理中心的左側流覽中，前往 **語音**  >  **語音路由策略**。</span><span class="sxs-lookup"><span data-stu-id="61a28-128">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="61a28-129">按一下原則名稱左側來選取原則，然後按一下 [編輯 **]**。</span><span class="sxs-lookup"><span data-stu-id="61a28-129">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="61a28-130">按一下 **[新增/移除 PSTN 使用** 記錄，進行您想要的變更，然後按一下 [ **儲存**。</span><span class="sxs-lookup"><span data-stu-id="61a28-130">Click **Add/remove PSTN usage records**, make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="61a28-131">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="61a28-131">Using PowerShell</span></span>

<span data-ttu-id="61a28-132">請參閱 [Set-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/set-csonlinevoiceroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="61a28-132">See [Set-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span></span>

## <a name="assign-a-custom-voice-routing-policy-to-users"></a><span data-ttu-id="61a28-133">指派自訂語音路由策略給使用者</span><span class="sxs-lookup"><span data-stu-id="61a28-133">Assign a custom voice routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="61a28-134">另請參閱 [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="61a28-134">See also [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="61a28-135">相關主題</span><span class="sxs-lookup"><span data-stu-id="61a28-135">Related topics</span></span>

[<span data-ttu-id="61a28-136">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="61a28-136">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="61a28-137">設定直接路由的語音路由</span><span class="sxs-lookup"><span data-stu-id="61a28-137">Configure voice routing for Direct Routing</span></span>](direct-routing-voice-routing.md)

[<span data-ttu-id="61a28-138">啟用直接路由的依位置路由</span><span class="sxs-lookup"><span data-stu-id="61a28-138">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)

[<span data-ttu-id="61a28-139">在 Teams 中將原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="61a28-139">Assign policies to your users in Teams</span></span>](assign-policies.md)