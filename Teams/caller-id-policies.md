---
title: 管理 Microsoft Teams 中的來電顯示原則。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz; jens
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
description: 瞭解如何在組織中使用及管理本機號碼Microsoft Teams變更或封鎖組織中Teams使用者的本機號碼。
ms.openlocfilehash: cd928af5213a1e6fa927662adaba0fefecb687d5
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308372"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="4519b-103">管理 Microsoft Teams 中的來電顯示原則。</span><span class="sxs-lookup"><span data-stu-id="4519b-103">Manage caller ID policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="4519b-104">若要將本機號碼設為資源帳戶電話號碼，並設定通話方名稱，請使用 Teams PowerShell 模組 2.3.1 或更高版本中的 PowerShell Cmdlet New-CsCallingLineIdentity 或 Set-CsCallingLineIdentity。</span><span class="sxs-lookup"><span data-stu-id="4519b-104">To set the caller ID to a resource account phone number and to set the calling party name, use the PowerShell cmdlets New-CsCallingLineIdentity or Set-CsCallingLineIdentity in the Teams PowerShell module 2.3.1 or later.</span></span> <span data-ttu-id="4519b-105"> (系統管理中心目前Microsoft Teams這些選項) </span><span class="sxs-lookup"><span data-stu-id="4519b-105">(These options are not currently available in the Microsoft Teams admin center.)</span></span> 

<span data-ttu-id="4519b-106">根據預設，當Teams使用者撥打 PSTN 電話時，系統Teams使用者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="4519b-106">By default, when a Teams user makes a call to a PSTN phone, the phone number of the Teams user is visible.</span></span> <span data-ttu-id="4519b-107">同樣地，當 PSTN 來電者撥打Teams，PSTN 來電者的電話號碼即會顯示。</span><span class="sxs-lookup"><span data-stu-id="4519b-107">Likewise, when a PSTN caller makes a call to a Teams user, the PSTN caller's phone number is visible.</span></span>

<span data-ttu-id="4519b-108">作為系統管理員，您可以使用本機號碼策略來變更或封鎖本機號碼 (也稱為電話線識別碼) 。</span><span class="sxs-lookup"><span data-stu-id="4519b-108">As an administrator, you can use caller ID policies to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="4519b-109">您可以使用本機號碼政策，為貴組織的 Teams 使用者顯示備用電話號碼、封鎖外發電話號碼、封鎖本機號碼，或設定呼叫方名稱 (CNAM) 。</span><span class="sxs-lookup"><span data-stu-id="4519b-109">You can use caller ID policies to display an alternate phone number for Teams users in your organization, block the outbound phone number, block an incoming number from being displayed, or set the Calling Party Name (CNAM).</span></span> <span data-ttu-id="4519b-110">例如，當使用者進行通話時，您可以變更本機號碼號碼，以顯示貴組織的主要電話號碼和公司名稱，而不是使用者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="4519b-110">For example, when a user makes a call, you can change the caller ID to display your organization's main phone number and company name instead of the user's phone number.</span></span>

<span data-ttu-id="4519b-111">您可以到系統管理中心中的 **語音** 本機號碼Microsoft Teams  >  管理本機號碼政策。</span><span class="sxs-lookup"><span data-stu-id="4519b-111">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="4519b-112">您可以使用全域 (全組織預設值) 原則，或建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="4519b-112">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="4519b-113">除非您建立並指派自訂原則，否則組織中的使用者將會自動取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="4519b-113">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="4519b-114">建立自訂本機號碼策略</span><span class="sxs-lookup"><span data-stu-id="4519b-114">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="4519b-115">在系統管理中心的左側導Microsoft Teams，請前往 **語音**  >  **本機號碼政策**。</span><span class="sxs-lookup"><span data-stu-id="4519b-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="4519b-116">按一下 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="4519b-116">Click **Add**.</span></span> <br>
<span data-ttu-id="4519b-117">![系統管理中心中新本機號碼政策頁面的螢幕擷取畫面](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="4519b-117">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="4519b-118">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="4519b-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="4519b-119">從這裡選擇您想要的設定：</span><span class="sxs-lookup"><span data-stu-id="4519b-119">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="4519b-120">**封鎖本機號碼**：開啟此設定以封鎖來電的本機號碼。</span><span class="sxs-lookup"><span data-stu-id="4519b-120">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="4519b-121">**重寫本機號碼規則**：開啟此設定，讓使用者在顯示號碼給來電者或不顯示號碼時，重寫該政策中的設定。</span><span class="sxs-lookup"><span data-stu-id="4519b-121">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="4519b-122">這表示使用者可以選擇是否要顯示本機號碼。</span><span class="sxs-lookup"><span data-stu-id="4519b-122">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="4519b-123">詳細資訊，請參閱 [使用者對外發本機號碼識別碼的控制項](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id)。</span><span class="sxs-lookup"><span data-stu-id="4519b-123">For more information, see [End user control of outbound caller ID](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="4519b-124">**將本機號碼取代為**：選取下列其中一項，設定要顯示給使用者的本機號碼：</span><span class="sxs-lookup"><span data-stu-id="4519b-124">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="4519b-125">**使用者編號**：顯示使用者編號。</span><span class="sxs-lookup"><span data-stu-id="4519b-125">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="4519b-126">**服務號碼**：可讓您將服務電話號碼設為顯示為本機號碼。</span><span class="sxs-lookup"><span data-stu-id="4519b-126">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="4519b-127">**匿名**：將本機號碼為匿名。</span><span class="sxs-lookup"><span data-stu-id="4519b-127">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="4519b-128">**以這個服務號碼取代來電** 顯示：選擇服務號碼以取代使用者的本機號碼。</span><span class="sxs-lookup"><span data-stu-id="4519b-128">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="4519b-129">如果您在 取代本機號碼中選取了 **服務號碼** ， **可以使用這個選項**。</span><span class="sxs-lookup"><span data-stu-id="4519b-129">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="4519b-130">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="4519b-130">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="4519b-131">編輯本機號碼策略</span><span class="sxs-lookup"><span data-stu-id="4519b-131">Edit a caller ID policy</span></span>

<span data-ttu-id="4519b-132">您可以編輯全域原則或任何您建立的任何自訂策略。</span><span class="sxs-lookup"><span data-stu-id="4519b-132">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="4519b-133">在系統管理中心的左側導Microsoft Teams，請前往 **語音**  >  **本機號碼政策**。</span><span class="sxs-lookup"><span data-stu-id="4519b-133">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="4519b-134">按一下原則名稱左側來選取原則，然後按一下 [編輯 **]**。</span><span class="sxs-lookup"><span data-stu-id="4519b-134">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="4519b-135">變更您想要的設定，然後按一下 [ **儲存**。</span><span class="sxs-lookup"><span data-stu-id="4519b-135">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="4519b-136">指派自訂本機號碼策略給使用者</span><span class="sxs-lookup"><span data-stu-id="4519b-136">Assign a custom caller ID policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="4519b-137">相關主題</span><span class="sxs-lookup"><span data-stu-id="4519b-137">Related topics</span></span>

[<span data-ttu-id="4519b-138">New-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="4519b-138">New-CsCallingLineIdentity</span></span>](/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="4519b-139">Set-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="4519b-139">Set-CsCallingLineIdentity</span></span>](/powershell/module/skype/set-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="4519b-140">在 Teams 中將原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="4519b-140">Assign policies to your users in Teams</span></span>](assign-policies.md)