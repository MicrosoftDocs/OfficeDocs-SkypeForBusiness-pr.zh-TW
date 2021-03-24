---
title: 管理 Microsoft Teams 中的來電顯示原則。
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: 瞭解如何在 Microsoft Teams 中使用和管理本機號碼政策來變更或封鎖貴組織中 Teams 使用者的本機號碼。
ms.openlocfilehash: cd15245523cdc3f5fb3625a2b4cfdae4deebb7d3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102779"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="13fdb-103">管理 Microsoft Teams 中的來電顯示原則。</span><span class="sxs-lookup"><span data-stu-id="13fdb-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="13fdb-104">做為系統管理員，您可以使用 Microsoft Teams 中的本機號碼政策來變更或封鎖本機號碼 (也稱為電話線識別碼) 。</span><span class="sxs-lookup"><span data-stu-id="13fdb-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="13fdb-105">根據預設，在 Teams 使用者撥打 PSTN 電話時，可以看到 Teams 使用者的電話號碼，而 PSTN 來電者撥打 Teams 使用者時，可以看到他們的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="13fdb-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="13fdb-106">您可以使用本機號碼政策來顯示貴組織中 Teams 使用者的備用電話號碼，或封鎖本機號碼。</span><span class="sxs-lookup"><span data-stu-id="13fdb-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="13fdb-107">例如，當使用者進行通話時，您可以將本機號碼變更為顯示貴組織的主要電話號碼，而不是使用者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="13fdb-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="13fdb-108">您可以到 Microsoft Teams 系統管理中心的 **語音**  >  **本機號碼政策** 來管理本機號碼政策。</span><span class="sxs-lookup"><span data-stu-id="13fdb-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="13fdb-109">您可以使用全域 (全組織預設值) 原則，或建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="13fdb-109">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="13fdb-110">除非您建立並指派自訂原則，否則組織中的使用者將會自動取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="13fdb-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="13fdb-111">建立自訂本機號碼策略</span><span class="sxs-lookup"><span data-stu-id="13fdb-111">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="13fdb-112">在 Microsoft Teams 系統管理中心的左側流覽中，前往 **語音**  >  **本機號碼政策**。</span><span class="sxs-lookup"><span data-stu-id="13fdb-112">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="13fdb-113">按一下 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="13fdb-113">Click **Add**.</span></span> <br>
<span data-ttu-id="13fdb-114">![系統管理中心中新本機號碼政策頁面的螢幕擷取畫面](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="13fdb-114">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="13fdb-115">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="13fdb-115">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="13fdb-116">從這裡選擇您想要的設定：</span><span class="sxs-lookup"><span data-stu-id="13fdb-116">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="13fdb-117">**封鎖本機號碼**：開啟此設定以封鎖來電的本機號碼。</span><span class="sxs-lookup"><span data-stu-id="13fdb-117">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="13fdb-118">**重寫本機號碼規則**：開啟此設定，讓使用者在顯示號碼給來電者或不顯示號碼時，重寫該政策中的設定。</span><span class="sxs-lookup"><span data-stu-id="13fdb-118">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="13fdb-119">這表示使用者可以選擇是否要顯示本機號碼。</span><span class="sxs-lookup"><span data-stu-id="13fdb-119">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="13fdb-120">詳細資訊，請參閱 [使用者對外發本機號碼識別碼的控制項](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id)。</span><span class="sxs-lookup"><span data-stu-id="13fdb-120">For more information, see [End user control of outbound caller ID](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="13fdb-121">**將本機號碼取代為**：選取下列其中一項，設定要顯示給使用者的本機號碼：</span><span class="sxs-lookup"><span data-stu-id="13fdb-121">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="13fdb-122">**使用者編號**：顯示使用者編號。</span><span class="sxs-lookup"><span data-stu-id="13fdb-122">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="13fdb-123">**服務號碼**：可讓您將服務電話號碼設為顯示為本機號碼。</span><span class="sxs-lookup"><span data-stu-id="13fdb-123">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="13fdb-124">**匿名**：將本機號碼為匿名。</span><span class="sxs-lookup"><span data-stu-id="13fdb-124">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="13fdb-125">**以這個服務號碼取代來電** 顯示：選擇服務號碼以取代使用者的本機號碼。</span><span class="sxs-lookup"><span data-stu-id="13fdb-125">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="13fdb-126">如果您在 將本機號碼取代為 **中選取** 了服務號碼 **，可以使用這個選項**。</span><span class="sxs-lookup"><span data-stu-id="13fdb-126">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="13fdb-127">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="13fdb-127">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="13fdb-128">編輯本機號碼策略</span><span class="sxs-lookup"><span data-stu-id="13fdb-128">Edit a caller ID policy</span></span>

<span data-ttu-id="13fdb-129">您可以編輯全域原則或任何您建立的任何自訂策略。</span><span class="sxs-lookup"><span data-stu-id="13fdb-129">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="13fdb-130">在 Microsoft Teams 系統管理中心的左側流覽中，前往 **語音**  >  **本機號碼政策**。</span><span class="sxs-lookup"><span data-stu-id="13fdb-130">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="13fdb-131">按一下原則名稱左側來選取原則，然後按一下 [編輯 **]**。</span><span class="sxs-lookup"><span data-stu-id="13fdb-131">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="13fdb-132">變更您想要的設定，然後按一下 [ **儲存**。</span><span class="sxs-lookup"><span data-stu-id="13fdb-132">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="13fdb-133">指派自訂本機號碼策略給使用者</span><span class="sxs-lookup"><span data-stu-id="13fdb-133">Assign a custom caller ID policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="13fdb-134">相關主題</span><span class="sxs-lookup"><span data-stu-id="13fdb-134">Related topics</span></span>

[<span data-ttu-id="13fdb-135">New-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="13fdb-135">New-CsCallingLineIdentity</span></span>](/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="13fdb-136">在 Teams 中將原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="13fdb-136">Assign policies to your users in Teams</span></span>](assign-policies.md)