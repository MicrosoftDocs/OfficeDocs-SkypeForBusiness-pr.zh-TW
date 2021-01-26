---
title: 管理 Microsoft 團隊中的緊急通話原則
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中使用和管理緊急通話原則，定義貴組織中的小組使用者撥打緊急通話時，會發生什麼情況。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: e58f428fbaa25b03534ce9f168ecf347b183eda3
ms.sourcegitcommit: d6e97621b1bfe9c3fbd8bc41b30a94bafd17b28f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2021
ms.locfileid: "49973137"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="75935-103">管理 Microsoft 團隊中的緊急通話原則</span><span class="sxs-lookup"><span data-stu-id="75935-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="75935-104">如果您的組織使用 [通話方案](set-up-calling-plans.md) 或部署的 [電話系統直傳送](direct-routing-landing-page.md)，您可以在 Microsoft 團隊中使用緊急通話原則，定義貴組織中的小組使用者進行緊急通話時所發生的動作。</span><span class="sxs-lookup"><span data-stu-id="75935-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="75935-105">您可以設定當指派策略呼叫緊急服務的使用者時，要通知的人員，以及傳送通知的方式。</span><span class="sxs-lookup"><span data-stu-id="75935-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="75935-106">例如，您可以將原則設定設定為自動通知貴組織的安全服務台，並讓他們聆聽緊急通話。</span><span class="sxs-lookup"><span data-stu-id="75935-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="75935-107">您可以移至  >  Microsoft 團隊系統管理中心的語音 **緊急策略** 或使用 Windows PowerShell 來管理緊急通話原則。</span><span class="sxs-lookup"><span data-stu-id="75935-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="75935-108">您可以將原則指派給使用者和 [網路網站](cloud-voice-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="75935-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="75935-109">針對使用者，您可以使用全域 (組織範圍的預設) 原則，或是建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="75935-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="75935-110">除非您建立並指派自訂原則，否則使用者會自動取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="75935-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="75935-111">請記住，您可以編輯全域原則中的設定，但無法重新命名或刪除。</span><span class="sxs-lookup"><span data-stu-id="75935-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="75935-112">針對網路網站，您可以建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="75935-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="75935-113">如果您已將緊急呼叫原則指派給網路網站和使用者，而且如果該使用者是在該網路網站上，則指派給網路網站的原則會覆寫指派給使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="75935-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="75935-114">建立自訂緊急通話原則</span><span class="sxs-lookup"><span data-stu-id="75935-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="75935-115">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="75935-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="75935-116">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音**  >  **緊急原則**]，然後按一下 [**通話原則**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="75935-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="75935-117">按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="75935-117">Click **Add**.</span></span>
3. <span data-ttu-id="75935-118">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="75935-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="75935-119">在進行緊急通話時，設定您想要如何通知組織中的人員（通常是安全服務台）。</span><span class="sxs-lookup"><span data-stu-id="75935-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="75935-120">若要執行此動作，請在 [ **通知模式]** 底下，選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="75935-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="75935-121">**僅傳送通知**： [小組聊天] 訊息會傳送給您指定的使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="75935-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="75935-122">**Conferenced 為靜音且無法取消靜音**： [小組聊天] 訊息會傳送給您指定的使用者和群組，而且他們可以偵聽 (但無法參與呼叫者與 PSAP 運算子之間交談中的) 。</span><span class="sxs-lookup"><span data-stu-id="75935-122">**Conferenced in muted and unable to unmute**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="75935-123">**Conferenced** 為 [已靜音]，但可以取消靜音： [團隊聊天] 訊息會傳送給您指定的使用者和群組，而且可以取消靜音來偵聽來電者與 PSAP 運算子之間的交談。</span><span class="sxs-lookup"><span data-stu-id="75935-123">**Conferenced in muted but are able to unmute**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="75935-124">如果您 **在靜音** 通知模式中選取了其中一個會議，請在 [ **撥打緊急電話通知的號碼** ] 方塊中，輸入使用者或群組的 PSTN 電話號碼來撥打電話並加入緊急通話。</span><span class="sxs-lookup"><span data-stu-id="75935-124">If you selected either of the **Conference in muted** notification modes, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="75935-125">例如，輸入貴組織的 security 辦公桌編號，該號碼會在發出緊急通話時接聽來電，然後可以接聽通話。</span><span class="sxs-lookup"><span data-stu-id="75935-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span> <span data-ttu-id="75935-126">即使將模式設定為靜音中的 [Conferenced]， **但卻可以取消靜音**，否則 PSTN 手機無法進行已取消靜音。</span><span class="sxs-lookup"><span data-stu-id="75935-126">The PSTN phone cannot be unmuted even when the mode is set to **Conferenced in muted but are able to unmute**.</span></span>
6. <span data-ttu-id="75935-127">搜尋並選取一或多個使用者或群組（例如貴組織的安全服務台），以在進行緊急通話時通知您。</span><span class="sxs-lookup"><span data-stu-id="75935-127">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="75935-128">通知可以傳送到使用者、通訊群組和安全性群組的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="75935-128">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="75935-129">最多可以通知50使用者。</span><span class="sxs-lookup"><span data-stu-id="75935-129">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="75935-130">按一下 **[** 套用]。</span><span class="sxs-lookup"><span data-stu-id="75935-130">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="75935-131">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="75935-131">Using PowerShell</span></span>

<span data-ttu-id="75935-132">請參閱 [新-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="75935-132">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="75935-133">編輯緊急通話原則</span><span class="sxs-lookup"><span data-stu-id="75935-133">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="75935-134">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="75935-134">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="75935-135">您可以編輯全域原則或您建立的任何自訂原則。</span><span class="sxs-lookup"><span data-stu-id="75935-135">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="75935-136">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音**  >  **緊急原則**]，然後按一下 [**通話原則**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="75935-136">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="75935-137">按一下原則名稱左邊的，然後按一下 [ **編輯**]，選取原則。</span><span class="sxs-lookup"><span data-stu-id="75935-137">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="75935-138">進行您想要的變更， **然後按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="75935-138">Make the changes that you want, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="75935-139">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="75935-139">Using PowerShell</span></span>

<span data-ttu-id="75935-140">請參閱 [設定 CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="75935-140">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="75935-141">將自訂緊急通話原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="75935-141">Assign a custom emergency calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="75935-142">另請參閱 [授與 CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="75935-142">See also [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="75935-143">將自訂緊急通話原則指派給網路網站</span><span class="sxs-lookup"><span data-stu-id="75935-143">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="75935-144">使用 [CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) Cmdlet 將緊急呼叫原則指派給網路網站。</span><span class="sxs-lookup"><span data-stu-id="75935-144">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="75935-145">下列範例顯示如何將稱為 Contoso 緊急呼叫原則1的原則指派給 Site1 網站。</span><span class="sxs-lookup"><span data-stu-id="75935-145">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="75935-146">相關主題</span><span class="sxs-lookup"><span data-stu-id="75935-146">Related topics</span></span>

[<span data-ttu-id="75935-147">管理團隊中的緊急通話路由策略</span><span class="sxs-lookup"><span data-stu-id="75935-147">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)

[<span data-ttu-id="75935-148">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="75935-148">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="75935-149">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="75935-149">Assign policies to your users in Teams</span></span>](assign-policies.md)
