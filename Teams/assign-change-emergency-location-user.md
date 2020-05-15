---
title: 指派或變更使用者的緊急位置
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: 在本文中，您將瞭解如何為貴組織中的使用者指派或變更緊急位置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 096e2dead1ede4f9769dafd85dfac23d6c44f399
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232474"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a><span data-ttu-id="1f5f9-103">指派或變更使用者的緊急位置</span><span class="sxs-lookup"><span data-stu-id="1f5f9-103">Assign or change an emergency location for a user</span></span>

<span data-ttu-id="1f5f9-104">當您設定通話方案時，您必須將緊急位置指派給每個電話號碼或使用者。</span><span class="sxs-lookup"><span data-stu-id="1f5f9-104">When you're setting up Calling Plans, you need to assign an emergency location to each phone number or user.</span></span> <span data-ttu-id="1f5f9-105">在歐洲國家/地區，當您從 Office 365 取得電話號碼時，或當您將電話號碼轉移到 Office 365 時，緊急位置會與電話號碼產生關聯。</span><span class="sxs-lookup"><span data-stu-id="1f5f9-105">In European countries, the emergency location is associated with the phone number when you get it from Office 365 or when you transfer a phone number over to Office 365.</span></span> <span data-ttu-id="1f5f9-106">在美國，緊急位置會與指派給使用者的電話號碼相關聯。</span><span class="sxs-lookup"><span data-stu-id="1f5f9-106">In the United States, the emergency location is associated with the phone number when it's assigned to the user.</span></span> <span data-ttu-id="1f5f9-107">如果您指派的使用者移至新的位置，就可以變更緊急位址。</span><span class="sxs-lookup"><span data-stu-id="1f5f9-107">The emergency address can be changed if the user that it's assigned to moves to a new location.</span></span> <span data-ttu-id="1f5f9-108">如需有關緊急位址和位置的詳細資訊，請參閱[管理緊急通話](what-are-emergency-locations-addresses-and-call-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="1f5f9-108">For more about emergency addresses and locations, see [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="1f5f9-109">若要瞭解如何取得通話方案和成本，請參閱[小組附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="1f5f9-109">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="1f5f9-110">您可以在 Microsoft 團隊系統管理中心或使用 PowerShell 指派或變更使用者的緊急位置。</span><span class="sxs-lookup"><span data-stu-id="1f5f9-110">You can assign or change an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="1f5f9-111">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="1f5f9-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="1f5f9-112">在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**語音**  >  **電話號碼**]。</span><span class="sxs-lookup"><span data-stu-id="1f5f9-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="1f5f9-113">在 [**電話號碼**] 頁面上，選取清單中的使用者號碼，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="1f5f9-113">On the **Phone numbers** page, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="1f5f9-114">在 [**編輯**] 窗格的 [**緊急位置**] 底下，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="1f5f9-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

   - <span data-ttu-id="1f5f9-115">若要指派緊急位置，請搜尋並選取緊急位置。</span><span class="sxs-lookup"><span data-stu-id="1f5f9-115">To assign an emergency location, search for, and select an emergency location.</span></span>

   - <span data-ttu-id="1f5f9-116">若要變更已指派給使用者的緊急位置，請按一下 [ **X** ] 以移除現有的位置，然後搜尋並選取您要指派的位置。</span><span class="sxs-lookup"><span data-stu-id="1f5f9-116">To change the emergency location that's already assigned to the user, click **X** to remove the existing location, and then search for and select the location you want to assign.</span></span>

4. <span data-ttu-id="1f5f9-117">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1f5f9-117">Click **Save**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="1f5f9-118">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f5f9-118">Using PowerShell</span></span>

<span data-ttu-id="1f5f9-119">請參閱[設定 CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser)。</span><span class="sxs-lookup"><span data-stu-id="1f5f9-119">See [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser).</span></span> 

    
## <a name="related-topics"></a><span data-ttu-id="1f5f9-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="1f5f9-120">Related topics</span></span>

- [<span data-ttu-id="1f5f9-121">管理緊急通話</span><span class="sxs-lookup"><span data-stu-id="1f5f9-121">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="1f5f9-122">新增、變更或移除貴組織的緊急位置</span><span class="sxs-lookup"><span data-stu-id="1f5f9-122">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="1f5f9-123">新增、變更或移除貴組織緊急位置的地方</span><span class="sxs-lookup"><span data-stu-id="1f5f9-123">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="1f5f9-124">指派或變更使用者緊急位置的地方</span><span class="sxs-lookup"><span data-stu-id="1f5f9-124">Assign or change a place for an emergency location for a user</span></span>](assign-change-emergency-place-user.md)
- [<span data-ttu-id="1f5f9-125">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="1f5f9-125">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="1f5f9-126">緊急通話條款及條件</span><span class="sxs-lookup"><span data-stu-id="1f5f9-126">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
- [<span data-ttu-id="1f5f9-127">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="1f5f9-127">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
