---
title: 管理緊急電話路由原則
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams 中使用和管理緊急電話路由策略來設定緊急號碼，並指定緊急電話的路由方式。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 0fb3a80bf5c1a064435754c4f999f6a62214b021
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096177"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a><span data-ttu-id="02ab0-103">在 Microsoft Teams 中管理緊急電話路由策略</span><span class="sxs-lookup"><span data-stu-id="02ab0-103">Manage emergency call routing policies in Microsoft Teams</span></span>

<span data-ttu-id="02ab0-104">如果您在組織中部署電話 [系統](direct-routing-landing-page.md) 直接路由，您可以使用 Microsoft Teams 中的緊急電話路由策略來設定緊急號碼，並指定緊急電話的路由方式。</span><span class="sxs-lookup"><span data-stu-id="02ab0-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you can use emergency call routing policies in Microsoft Teams to set up emergency numbers and specify how emergency calls are routed.</span></span> <span data-ttu-id="02ab0-105">緊急呼叫路由策略會決定為指派該策略的使用者啟用增強型緊急服務、用來撥打緊急服務 (例如美國) 的 911 號碼，以及撥打緊急服務電話的路由方式。</span><span class="sxs-lookup"><span data-stu-id="02ab0-105">An emergency call routing policy determines whether enhanced emergency services is enabled for users who are assigned the policy, the numbers used to call emergency services (for example, 911 in the United States), and how calls to emergency services are routed.</span></span>

<span data-ttu-id="02ab0-106">您可以到 Microsoft Teams 系統管理中心的語音緊急策略，或使用  >  \*\*\*\* Windows PowerShell 來管理緊急電話路由策略。</span><span class="sxs-lookup"><span data-stu-id="02ab0-106">You manage emergency call routing policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="02ab0-107">可以將策略指派給使用者和網路 [網站](cloud-voice-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="02ab0-107">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="02ab0-108">對於使用者，您可以使用全域 (全組織的預設) ，或建立及指派自訂策略。</span><span class="sxs-lookup"><span data-stu-id="02ab0-108">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="02ab0-109">除非您建立並指派自訂策略，否則使用者會自動取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="02ab0-109">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="02ab0-110">請記住，您可以編輯全域原則中的設定，但無法重新命名或刪除。</span><span class="sxs-lookup"><span data-stu-id="02ab0-110">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="02ab0-111">針對網路網站，您可以建立並指派自訂策略。</span><span class="sxs-lookup"><span data-stu-id="02ab0-111">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="02ab0-112">如果您將緊急通話路由策略指派給網路網站和使用者，且該使用者位於該網路網站，則指派給網路網站的策略會重寫指派給使用者的策略。</span><span class="sxs-lookup"><span data-stu-id="02ab0-112">If you assigned an emergency call routing policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-call-routing-policy"></a><span data-ttu-id="02ab0-113">建立自訂緊急電話路由策略</span><span class="sxs-lookup"><span data-stu-id="02ab0-113">Create a custom emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="02ab0-114">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="02ab0-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="02ab0-115">在 Microsoft Teams 系統管理中心的左側導航中，前往 **[語音** 緊急處理政策>，  >  然後按一下 [**通話路由策略> 定位** 點。</span><span class="sxs-lookup"><span data-stu-id="02ab0-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="02ab0-116">按一下 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="02ab0-116">Click **Add**.</span></span>
3. <span data-ttu-id="02ab0-117">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="02ab0-117">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="02ab0-118">若要啟用動態緊急電話，請開啟 **動態緊急電話**。</span><span class="sxs-lookup"><span data-stu-id="02ab0-118">To enable dynamic emergency calling, turn on **Dynamic emergency calling**.</span></span> <span data-ttu-id="02ab0-119">啟用動態緊急電話時，Teams 會從服務中取回策略和位置資訊，並包含該資訊做為緊急通話的一部分。</span><span class="sxs-lookup"><span data-stu-id="02ab0-119">When dynamic emergency calling is enabled, Teams retrieves policy and location information from the service and includes that information as part of the emergency call.</span></span>
5. <span data-ttu-id="02ab0-120">定義一或多個緊急號碼。</span><span class="sxs-lookup"><span data-stu-id="02ab0-120">Define one or more emergency numbers.</span></span> <span data-ttu-id="02ab0-121">若要執行此操作，請按一下 [ **緊急** 號碼> 下的 [ **新增**，然後執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="02ab0-121">To do this, under **Emergency numbers**, click **Add**, and then do the following:</span></span>
    1. <span data-ttu-id="02ab0-122">**緊急撥號字串**：輸入緊急撥號字串。</span><span class="sxs-lookup"><span data-stu-id="02ab0-122">**Emergency dial string**: Enter the emergency dial string.</span></span> <span data-ttu-id="02ab0-123">此撥號字串表示通話是緊急通話。</span><span class="sxs-lookup"><span data-stu-id="02ab0-123">This dial string indicates that a call is an emergency call.</span></span>
        > [!NOTE]
        > <span data-ttu-id="02ab0-124">針對直接路由，我們正在從 Teams 用戶端轉場，在緊急撥號字串前面傳送緊急電話時，會以「+」表示。</span><span class="sxs-lookup"><span data-stu-id="02ab0-124">For Direct Routing, we're transitioning away from Teams clients sending emergency calls with a "+" in front of the emergency dial string.</span></span> <span data-ttu-id="02ab0-125">在轉換完成之前，符合緊急撥號字串的語音路由模式應確保符合具有且沒有前面 "+" 的字串，例如 911 和 +911。</span><span class="sxs-lookup"><span data-stu-id="02ab0-125">Until the transition is completed, the voice route pattern to match an emergency dial string should ensure a match is made for strings that have and don't have a preceding "+", such as 911 and +911.</span></span> <span data-ttu-id="02ab0-126">例如，^ \\ +？？911 或 .\*。</span><span class="sxs-lookup"><span data-stu-id="02ab0-126">For example, ^\\+?911 or .\*.</span></span>
    2. <span data-ttu-id="02ab0-127">**緊急撥號遮罩**：針對每個緊急號碼，您可以指定零個或多個緊急撥號遮罩。</span><span class="sxs-lookup"><span data-stu-id="02ab0-127">**Emergency dial mask**: For each emergency number, you can specify zero or more emergency dial masks.</span></span> <span data-ttu-id="02ab0-128">撥號遮罩是您想要轉換成緊急撥號字串值的號碼。</span><span class="sxs-lookup"><span data-stu-id="02ab0-128">A dial mask is the number that you want to translate into the value of the emergency dial string.</span></span> <span data-ttu-id="02ab0-129">這可讓您撥打替代的緊急號碼，而且仍可撥打到緊急服務。</span><span class="sxs-lookup"><span data-stu-id="02ab0-129">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services.</span></span> <br><span data-ttu-id="02ab0-130">例如，您新增 112 做為緊急撥號遮罩，這是歐洲大部分地區緊急服務號碼，而 911 則做為緊急撥號字串。</span><span class="sxs-lookup"><span data-stu-id="02ab0-130">For example, you add 112 as the emergency dial mask, which is the emergency service number for most of Europe, and 911 as the emergency dial string.</span></span> <span data-ttu-id="02ab0-131">來自歐洲的 Teams 使用者可能不知道 911 是美國的緊急號碼，當他們撥打 112 時，撥打到 911。</span><span class="sxs-lookup"><span data-stu-id="02ab0-131">A Teams user from Europe who is visiting may not know that 911 is the emergency number in the United States, and when they dial 112, the call is made to 911.</span></span> <span data-ttu-id="02ab0-132">若要定義多個撥號遮罩，請以分號分隔每個值。</span><span class="sxs-lookup"><span data-stu-id="02ab0-132">To define multiple dial masks, separate each value by a semicolon.</span></span> <span data-ttu-id="02ab0-133">例如，112;212。</span><span class="sxs-lookup"><span data-stu-id="02ab0-133">For example, 112;212.</span></span>
    3. <span data-ttu-id="02ab0-134">**PSTN 使用記錄**：選取 [公用交換電話網路絡 (PSTN) 使用記錄。</span><span class="sxs-lookup"><span data-stu-id="02ab0-134">**PSTN usage record**: Select the Public Switched Telephone Network (PSTN) usage record.</span></span> <span data-ttu-id="02ab0-135">PSTN 使用量記錄是用來判斷使用哪一個路由路由從有權使用緊急電話的使用者路由緊急電話。</span><span class="sxs-lookup"><span data-stu-id="02ab0-135">The PSTN usage record is used to determine which route is used to route emergency calls from users who are authorized to use them.</span></span> <span data-ttu-id="02ab0-136">與此使用關聯的路由應指向會話初始通訊協定 (SIP) 主幹，專門用於緊急通話，或指向緊急位置識別號碼 (ELIN) 閘道，將緊急電話路由到最近的公用安全應答點 (PSAP) 。</span><span class="sxs-lookup"><span data-stu-id="02ab0-136">The route associated with this usage should point to a Session Initiation Protocol (SIP) trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>

    > [!NOTE]
    > <span data-ttu-id="02ab0-137">撥號字串和撥號遮罩在策略中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="02ab0-137">Dial strings and dial masks must be unique within a policy.</span></span> <span data-ttu-id="02ab0-138">這表示針對一個策略，您可以定義多個緊急號碼，也可以為撥號字串設定多個撥號遮罩，但每個撥號字串和撥號遮罩只能使用一次。</span><span class="sxs-lookup"><span data-stu-id="02ab0-138">This means that for a policy, you can define multiple emergency numbers and you can set multiple dial masks for a dial string, but each dial string and dial mask must only be used one time.</span></span>

6. <span data-ttu-id="02ab0-139">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="02ab0-139">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="02ab0-140">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="02ab0-140">Using PowerShell</span></span>

<span data-ttu-id="02ab0-141">請參閱 [New-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/new-csteamsemergencycallroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="02ab0-141">See [New-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span></span>

## <a name="edit-an-emergency-call-routing-policy"></a><span data-ttu-id="02ab0-142">編輯緊急通話路由策略</span><span class="sxs-lookup"><span data-stu-id="02ab0-142">Edit an emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="02ab0-143">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="02ab0-143">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="02ab0-144">您可以編輯全域原則或任何您建立的任何自訂策略。</span><span class="sxs-lookup"><span data-stu-id="02ab0-144">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="02ab0-145">在 Microsoft Teams 系統管理中心的左側導航中，前往 **[語音** 緊急處理政策>，  >  然後按一下 [**通話路由策略> 定位** 點。</span><span class="sxs-lookup"><span data-stu-id="02ab0-145">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="02ab0-146">按一下原則名稱左側來選取原則，然後按一下 [編輯 **]**。</span><span class="sxs-lookup"><span data-stu-id="02ab0-146">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="02ab0-147">進行您想要的變更，然後按一下 [ **儲存**。</span><span class="sxs-lookup"><span data-stu-id="02ab0-147">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="02ab0-148">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="02ab0-148">Using PowerShell</span></span>

<span data-ttu-id="02ab0-149">請參閱 [Set-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/set-csteamsemergencycallroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="02ab0-149">See [Set-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a><span data-ttu-id="02ab0-150">指派自訂緊急電話路由策略給使用者</span><span class="sxs-lookup"><span data-stu-id="02ab0-150">Assign a custom emergency call routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="02ab0-151">另請參閱 [Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="02ab0-151">See also [Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a><span data-ttu-id="02ab0-152">將自訂緊急電話路由策略指派給網路網站</span><span class="sxs-lookup"><span data-stu-id="02ab0-152">Assign a custom emergency call routing policy to a network site</span></span>

<span data-ttu-id="02ab0-153">使用 [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) Cmdlet 將緊急通話路由策略指派給網路網站。</span><span class="sxs-lookup"><span data-stu-id="02ab0-153">Use the [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling routing policy to a network site.</span></span>

<span data-ttu-id="02ab0-154">此範例顯示如何將稱為緊急電話路由策略 1 的策略指派給 Site1 網站。</span><span class="sxs-lookup"><span data-stu-id="02ab0-154">This example shows how to assign a policy called Emergency Call Routing Policy 1 to the Site1 site.</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="02ab0-155">相關主題</span><span class="sxs-lookup"><span data-stu-id="02ab0-155">Related topics</span></span>

[<span data-ttu-id="02ab0-156">在 Teams 中管理緊急通話政策</span><span class="sxs-lookup"><span data-stu-id="02ab0-156">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)

[<span data-ttu-id="02ab0-157">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="02ab0-157">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="02ab0-158">在 Teams 中將原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="02ab0-158">Assign policies to your users in Teams</span></span>](assign-policies.md)