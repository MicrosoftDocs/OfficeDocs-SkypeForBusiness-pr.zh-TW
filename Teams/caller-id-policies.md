---
title: 管理 Microsoft 團隊中的呼叫者識別碼原則
author: lanachin
ms.author: v-lanac
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
description: 瞭解如何在 Microsoft 團隊中使用和管理本機號碼原則，以變更或封鎖貴組織中的小組使用者本機號碼。
ms.openlocfilehash: 41466640f33769a64ce14d5d3dc47959c876a5bc
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938462"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="3bd3f-103">管理 Microsoft 團隊中的呼叫者識別碼原則</span><span class="sxs-lookup"><span data-stu-id="3bd3f-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="3bd3f-104">做為管理員，您可以使用 Microsoft 團隊中的本機號碼原則來變更或封鎖本機號碼（也稱為呼叫線路識別碼）。</span><span class="sxs-lookup"><span data-stu-id="3bd3f-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="3bd3f-105">根據預設，當使用者撥打電話給 PSTN 手機時，可以看到他們的電話號碼，以及當他們呼叫團隊使用者時，可以看到 PSTN 呼叫者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="3bd3f-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="3bd3f-106">您可以使用本機號碼原則，為您組織中的小組使用者顯示備用電話號碼，或封鎖要顯示的傳入號碼。</span><span class="sxs-lookup"><span data-stu-id="3bd3f-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="3bd3f-107">例如，當使用者撥打電話時，您可以變更本機號碼，以顯示貴組織的主要電話號碼，而不是使用者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="3bd3f-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="3bd3f-108">您可以移至**Voice**  >  Microsoft 團隊系統管理中心的語音**本機號碼原則**來管理本機號碼原則。</span><span class="sxs-lookup"><span data-stu-id="3bd3f-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="3bd3f-109">您可以使用全域（組織範圍預設值）原則，或建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="3bd3f-109">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="3bd3f-110">除非您建立並指派自訂原則，否則貴組織中的使用者將會自動取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="3bd3f-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="3bd3f-111">建立自訂本機號碼原則</span><span class="sxs-lookup"><span data-stu-id="3bd3f-111">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="3bd3f-112">在 Microsoft [團隊管理中心] 的左導覽中，移至 [**語音**  >  **本機號碼原則**]。</span><span class="sxs-lookup"><span data-stu-id="3bd3f-112">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="3bd3f-113">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="3bd3f-113">Click **Add**.</span></span> <br>
<span data-ttu-id="3bd3f-114">![系統管理中心 [新增本機號碼原則] 頁面的螢幕擷取畫面](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="3bd3f-114">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="3bd3f-115">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="3bd3f-115">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="3bd3f-116">從這裡選擇您想要的設定：</span><span class="sxs-lookup"><span data-stu-id="3bd3f-116">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="3bd3f-117">**封鎖來電**的本機號碼：開啟此設定可封鎖來電的本機號碼。</span><span class="sxs-lookup"><span data-stu-id="3bd3f-117">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="3bd3f-118">覆**寫本機號碼原則**：開啟此設定可讓使用者覆寫原則中的設定，以將他們的號碼顯示在 callees 中。</span><span class="sxs-lookup"><span data-stu-id="3bd3f-118">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="3bd3f-119">這表示使用者可以選擇是否要顯示其本機號碼。</span><span class="sxs-lookup"><span data-stu-id="3bd3f-119">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="3bd3f-120">如需詳細資訊，請參閱[結束使用者對輸出來電者識別碼的控制](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id)。</span><span class="sxs-lookup"><span data-stu-id="3bd3f-120">For more information, see [End user control of outbound caller ID](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="3bd3f-121">**使用本機號碼取代來電**顯示：若要為使用者設定本機號碼，請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="3bd3f-121">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="3bd3f-122">**使用者號碼**：顯示使用者的號碼。</span><span class="sxs-lookup"><span data-stu-id="3bd3f-122">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="3bd3f-123">[**服務號碼**]：可讓您設定要顯示為本機號碼的服務電話號碼。</span><span class="sxs-lookup"><span data-stu-id="3bd3f-123">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="3bd3f-124">**匿名**：以匿名方式顯示本機號碼。</span><span class="sxs-lookup"><span data-stu-id="3bd3f-124">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="3bd3f-125">**以這個服務號碼取代本機號碼**：選擇服務號碼來取代使用者的本機號碼。</span><span class="sxs-lookup"><span data-stu-id="3bd3f-125">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="3bd3f-126">如果您在 [**取代本機號碼者識別碼**] 中選取了 [**服務號碼**]，就可以使用此選項。</span><span class="sxs-lookup"><span data-stu-id="3bd3f-126">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="3bd3f-127">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3bd3f-127">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="3bd3f-128">編輯本機號碼原則</span><span class="sxs-lookup"><span data-stu-id="3bd3f-128">Edit a caller ID policy</span></span>

<span data-ttu-id="3bd3f-129">您可以編輯全域原則或您建立的任何自訂原則。</span><span class="sxs-lookup"><span data-stu-id="3bd3f-129">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="3bd3f-130">在 Microsoft [團隊管理中心] 的左導覽中，移至 [**語音**  >  **本機號碼原則**]。</span><span class="sxs-lookup"><span data-stu-id="3bd3f-130">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="3bd3f-131">按一下原則名稱左邊的，然後按一下 [**編輯**]，選取原則。</span><span class="sxs-lookup"><span data-stu-id="3bd3f-131">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="3bd3f-132">變更您想要的設定，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="3bd3f-132">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="3bd3f-133">將自訂本機號碼原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="3bd3f-133">Assign a custom caller ID policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="3bd3f-134">相關主題</span><span class="sxs-lookup"><span data-stu-id="3bd3f-134">Related topics</span></span>

[<span data-ttu-id="3bd3f-135">新-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="3bd3f-135">New-CsCallingLineIdentity</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="3bd3f-136">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="3bd3f-136">Assign policies to your users in Teams</span></span>](assign-policies.md)
