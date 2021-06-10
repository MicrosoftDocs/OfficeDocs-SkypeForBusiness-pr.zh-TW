---
title: 指派或變更使用者的緊急位置
author: cichur
ms.author: v-cichur
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
description: 在本文中，您將瞭解如何為貴組織的使用者指派或變更緊急位置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7dd986085a8c42df34d6634cbadc6e96fdfb14ca
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102979"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a><span data-ttu-id="ccc78-103">指派或變更使用者的緊急位置</span><span class="sxs-lookup"><span data-stu-id="ccc78-103">Assign or change an emergency location for a user</span></span>

<span data-ttu-id="ccc78-104">當您設定通話方案時，您必須為每個電話號碼或使用者指派緊急位置。</span><span class="sxs-lookup"><span data-stu-id="ccc78-104">When you're setting up Calling Plans, you need to assign an emergency location to each phone number or user.</span></span> <span data-ttu-id="ccc78-105">在歐盟國家/地區，當您從 Microsoft 365 或 Office 365 取得電話號碼，或將電話號碼轉接到 Microsoft 365 或 Office 365 時，緊急位置會與電話號碼相關聯。</span><span class="sxs-lookup"><span data-stu-id="ccc78-105">In European countries, the emergency location is associated with the phone number when you get it from Microsoft 365 or Office 365 or when you transfer a phone number over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="ccc78-106">在美國，緊急位置會與指派給使用者的電話號碼相關聯。</span><span class="sxs-lookup"><span data-stu-id="ccc78-106">In the United States, the emergency location is associated with the phone number when it's assigned to the user.</span></span> <span data-ttu-id="ccc78-107">如果指派給緊急位址的使用者移至新位置，可以變更緊急位址。</span><span class="sxs-lookup"><span data-stu-id="ccc78-107">The emergency address can be changed if the user that it's assigned to moves to a new location.</span></span> <span data-ttu-id="ccc78-108">有關緊急位址和位置的更多資訊，請參閱什麼是緊急位置、地點 [和通話路由？](./what-are-emergency-locations-addresses-and-call-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="ccc78-108">For more about emergency addresses and locations, see [What are emergency locations, places, and call routing?](./what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="ccc78-109">若要瞭解如何取得通話方案及其費用，請參閱Teams[授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="ccc78-109">To learn how to get a Calling Plans and how much they cost, see [Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="ccc78-110">您可以在系統管理中心指派或變更使用者的緊急Microsoft Teams，或使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="ccc78-110">You can assign or change an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="ccc78-111">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="ccc78-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="ccc78-112">在系統管理中心的左側導Microsoft Teams，按一下 **[語音** 電話  >  **號碼**。</span><span class="sxs-lookup"><span data-stu-id="ccc78-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="ccc78-113">在 [數位 **電話** 頁面上，按一下 [數位> 選項卡，選取清單中的使用者號碼，然後按一下 [**編輯**。</span><span class="sxs-lookup"><span data-stu-id="ccc78-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="ccc78-114">在編輯 **窗格** 的緊急 **位置下**，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="ccc78-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

   - <span data-ttu-id="ccc78-115">若要指派緊急位置，請搜尋並選取緊急位置。</span><span class="sxs-lookup"><span data-stu-id="ccc78-115">To assign an emergency location, search for, and select an emergency location.</span></span>

   - <span data-ttu-id="ccc78-116">若要變更已指派給使用者的緊急位置，請按一下 **[X** 以移除現有位置，然後搜尋並選取您想要指派的位置。</span><span class="sxs-lookup"><span data-stu-id="ccc78-116">To change the emergency location that's already assigned to the user, click **X** to remove the existing location, and then search for and select the location you want to assign.</span></span>

4. <span data-ttu-id="ccc78-117">根據您是否要傳送包含其電話號碼資訊的電子郵件給使用者，請關閉或開啟包含電話號碼 **資訊的電子郵件使用者**。</span><span class="sxs-lookup"><span data-stu-id="ccc78-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="ccc78-118">根據預設，這會是啟用狀態。</span><span class="sxs-lookup"><span data-stu-id="ccc78-118">By default, this is on.</span></span>

5. <span data-ttu-id="ccc78-119">按一下 **[Apply.**</span><span class="sxs-lookup"><span data-stu-id="ccc78-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="ccc78-120">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ccc78-120">Using PowerShell</span></span>

<span data-ttu-id="ccc78-121">請參閱 [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser)。</span><span class="sxs-lookup"><span data-stu-id="ccc78-121">See [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser).</span></span> 

    
## <a name="related-topics"></a><span data-ttu-id="ccc78-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="ccc78-122">Related topics</span></span>

- [<span data-ttu-id="ccc78-123">管理緊急電話</span><span class="sxs-lookup"><span data-stu-id="ccc78-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="ccc78-124">新增、變更或移除貴組織的緊急位置</span><span class="sxs-lookup"><span data-stu-id="ccc78-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="ccc78-125">新增、變更或移除貴組織緊急位置的地方</span><span class="sxs-lookup"><span data-stu-id="ccc78-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="ccc78-126">指派或變更使用者緊急位置的地方</span><span class="sxs-lookup"><span data-stu-id="ccc78-126">Assign or change a place for an emergency location for a user</span></span>](assign-change-emergency-place-user.md)
- [<span data-ttu-id="ccc78-127">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="ccc78-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="ccc78-128">緊急通話條款及條件</span><span class="sxs-lookup"><span data-stu-id="ccc78-128">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)
- [<span data-ttu-id="ccc78-129">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="ccc78-129">Teams PowerShell overview</span></span>](teams-powershell-overview.md)