---
title: 在 Microsoft Teams
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
description: 瞭解如何在組織中使用及管理緊急Microsoft Teams，以定義當貴組織中Teams使用者撥打緊急電話時會發生什麼情況。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 34f6e901049dd080ee070e7858f24b70535ee189
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120564"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="b2396-103">在 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b2396-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="b2396-104">如果貴組織使用[](set-up-calling-plans.md)通話方案或部署[電話系統 直接](direct-routing-landing-page.md)路由，您可以使用 Microsoft Teams 中的緊急通話策略來定義當貴組織的 Teams 使用者撥打緊急電話時會發生什麼情況。</span><span class="sxs-lookup"><span data-stu-id="b2396-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="b2396-105">您可以設定指派策略的使用者撥打緊急服務時要通知哪些人，以及如何通知他們。</span><span class="sxs-lookup"><span data-stu-id="b2396-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="b2396-106">例如，您可以設定策略設定，以自動通知貴組織的安全電話台，讓他們聆聽緊急電話。</span><span class="sxs-lookup"><span data-stu-id="b2396-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="b2396-107">您可以到系統管理中心中的語音緊急Microsoft Teams，或使用語音  >  \*\*\*\* Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b2396-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="b2396-108">可以將策略指派給使用者和網路 [網站](cloud-voice-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="b2396-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="b2396-109">對於使用者，您可以使用全域 (全組織的預設) ，或建立及指派自訂策略。</span><span class="sxs-lookup"><span data-stu-id="b2396-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="b2396-110">除非您建立並指派自訂策略，否則使用者會自動取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="b2396-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="b2396-111">請記住，您可以編輯全域原則中的設定，但無法重新命名或刪除。</span><span class="sxs-lookup"><span data-stu-id="b2396-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="b2396-112">針對網路網站，您可以建立並指派自訂策略。</span><span class="sxs-lookup"><span data-stu-id="b2396-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="b2396-113">如果您將緊急通話策略指派給網路網站和使用者，且該使用者位於該網路網站，則指派給網路網站的策略會重寫指派給使用者的政策。</span><span class="sxs-lookup"><span data-stu-id="b2396-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="b2396-114">建立自訂緊急通話政策</span><span class="sxs-lookup"><span data-stu-id="b2396-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b2396-115">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="b2396-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="b2396-116">在系統管理中心的左側導Microsoft Teams，前往 **[語音** 緊急處理政策>，然後按一下 [  >  \*\*\*\*\*\*通話政策> 定位\*\* 點。</span><span class="sxs-lookup"><span data-stu-id="b2396-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="b2396-117">按一下 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="b2396-117">Click **Add**.</span></span>
3. <span data-ttu-id="b2396-118">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="b2396-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="b2396-119">設定當您撥打緊急電話時，您希望如何通知貴組織人員 ，通常是安全電話機。</span><span class="sxs-lookup"><span data-stu-id="b2396-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="b2396-120">若要這麼做，請在通知 **模式** 下，選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="b2396-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="b2396-121">**僅傳送通知**：Teams聊天訊息會傳送至您指定的使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="b2396-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="b2396-122">以 **靜音** 方式會議且無法取消靜音：Teams 聊天訊息會寄給您指定的使用者和群組，他們可以聆聽 (但無法參與) 來電者與 PSAP 運算子之間的交談。</span><span class="sxs-lookup"><span data-stu-id="b2396-122">**Conferenced in muted and unable to unmute**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="b2396-123">以 **靜音** 方式會議，但可以取消靜音：Teams 聊天訊息會寄給您指定的使用者和群組，他們可以取消靜音，以聆聽並參與來電者與 PSAP 運算子之間的交談。</span><span class="sxs-lookup"><span data-stu-id="b2396-123">**Conferenced in muted but are able to unmute**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="b2396-124">如果您在靜音通知模式中選取了其中一個會議，您可以在 [撥打緊急電話通知的號碼> 方塊中，輸入使用者或群組的 PSTN 電話號碼，以撥打並加入緊急通話。</span><span class="sxs-lookup"><span data-stu-id="b2396-124">If you selected either of the **Conference in muted** notification modes, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="b2396-125">例如，輸入貴組織安全電話台的號碼，該號碼在撥打緊急電話時會接到來電，然後可以聆聽通話。</span><span class="sxs-lookup"><span data-stu-id="b2396-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span> <span data-ttu-id="b2396-126">PSTN 電話無法取消靜音，即使模式設定為 [以靜音方式會議，但 **可以取消靜音**。</span><span class="sxs-lookup"><span data-stu-id="b2396-126">The PSTN phone cannot be unmuted even when the mode is set to **Conferenced in muted but are able to unmute**.</span></span>
6. <span data-ttu-id="b2396-127">搜尋並選取一或多個使用者或群組 ，例如貴組織的安全電話台，以在緊急電話撥打時通知。</span><span class="sxs-lookup"><span data-stu-id="b2396-127">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="b2396-128">通知可以寄到使用者、通訊群組和安全性群組的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="b2396-128">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="b2396-129">最多可以通知 50 個使用者。</span><span class="sxs-lookup"><span data-stu-id="b2396-129">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="b2396-130">按一下 **[Apply.**</span><span class="sxs-lookup"><span data-stu-id="b2396-130">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b2396-131">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2396-131">Using PowerShell</span></span>

<span data-ttu-id="b2396-132">請參閱 [New-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/new-csteamsemergencycallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="b2396-132">See [New-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="b2396-133">編輯緊急通話政策</span><span class="sxs-lookup"><span data-stu-id="b2396-133">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b2396-134">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="b2396-134">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="b2396-135">您可以編輯全域原則或任何您建立的任何自訂策略。</span><span class="sxs-lookup"><span data-stu-id="b2396-135">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="b2396-136">在系統管理中心的左側導Microsoft Teams，前往 **[語音** 緊急處理政策>，然後按一下 [  >  \*\*\*\*\*\*通話政策> 定位\*\* 點。</span><span class="sxs-lookup"><span data-stu-id="b2396-136">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="b2396-137">按一下原則名稱左側來選取原則，然後按一下 [編輯 **]**。</span><span class="sxs-lookup"><span data-stu-id="b2396-137">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="b2396-138">進行您想要的變更，然後按一下 **[Apply.**</span><span class="sxs-lookup"><span data-stu-id="b2396-138">Make the changes that you want, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b2396-139">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2396-139">Using PowerShell</span></span>

<span data-ttu-id="b2396-140">請參閱 [Set-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/set-csteamsemergencycallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="b2396-140">See [Set-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="b2396-141">指派自訂緊急電話策略給使用者</span><span class="sxs-lookup"><span data-stu-id="b2396-141">Assign a custom emergency calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="b2396-142">另請參閱 [Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="b2396-142">See also [Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="b2396-143">將自訂緊急通話策略指派給網路網站</span><span class="sxs-lookup"><span data-stu-id="b2396-143">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="b2396-144">使用 [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) Cmdlet 將緊急通話策略指派給網路網站。</span><span class="sxs-lookup"><span data-stu-id="b2396-144">Use the [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="b2396-145">下列範例顯示如何將稱為 Contoso 緊急電話策略 1 的策略指派給 Site1 網站。</span><span class="sxs-lookup"><span data-stu-id="b2396-145">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="b2396-146">相關主題</span><span class="sxs-lookup"><span data-stu-id="b2396-146">Related topics</span></span>

[<span data-ttu-id="b2396-147">在 Teams</span><span class="sxs-lookup"><span data-stu-id="b2396-147">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)

[<span data-ttu-id="b2396-148">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="b2396-148">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="b2396-149">將原則指派給 Teams 中的使用者</span><span class="sxs-lookup"><span data-stu-id="b2396-149">Assign policies to your users in Teams</span></span>](assign-policies.md)