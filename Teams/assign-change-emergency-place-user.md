---
title: 指派、變更使用者緊急位置的位置
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
description: 在本文中，您將瞭解如何為貴組織中的使用者指派或變更緊急位置的位置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 385855c456d3a4e5c2de53fb2605e4d5d30d84a4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809523"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a><span data-ttu-id="24ccc-103">為使用者指派或變更緊急位置的位置</span><span class="sxs-lookup"><span data-stu-id="24ccc-103">Assign or change the place for an emergency location for a user</span></span>

<span data-ttu-id="24ccc-104">當您將電話號碼指派給使用者時，每個活躍的電話號碼都必須有相關聯的緊急位置。</span><span class="sxs-lookup"><span data-stu-id="24ccc-104">Each active phone number must have an associated emergency location when you assign the phone number to a user.</span></span> <span data-ttu-id="24ccc-105"> (當您在 Office 365 中取得電話號碼或傳送電話號碼時，就會建立關聯的位址。 ) 當您將數位與緊急位置建立關聯時，您也可以新增位置，以便在物理位置中提供更精確的位置。</span><span class="sxs-lookup"><span data-stu-id="24ccc-105">(You associate the address when you get a phone number in Office 365 or when you transfer a phone number.) When you associate the number with an emergency location, you can also add a place to provide a more exact location within a physical location.</span></span> <span data-ttu-id="24ccc-106">位置可以是地面、建築物翼或使用者所在的辦公室號碼。</span><span class="sxs-lookup"><span data-stu-id="24ccc-106">A place can be the floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="24ccc-107">您可以在指定的緊急位置有不限數量的位置，而且如果使用者移至不同的 office 或組建，就可以變更位置。</span><span class="sxs-lookup"><span data-stu-id="24ccc-107">You can have an unlimited number of places for a given emergency location, and you can change the place if the user moves to a different office or building.</span></span> <span data-ttu-id="24ccc-108">例如，如果使用者從 floor 34 移至地面35。</span><span class="sxs-lookup"><span data-stu-id="24ccc-108">For example, if the user moves from floor 34 to floor 35.</span></span>
  
<span data-ttu-id="24ccc-109">若要瞭解如何取得通話方案和成本，請參閱 [小組附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="24ccc-109">To learn how to get Calling Plans and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="24ccc-110">您可以在 Microsoft 團隊系統管理中心或使用 PowerShell 中為使用者指派或變更緊急位置的位置。</span><span class="sxs-lookup"><span data-stu-id="24ccc-110">You can assign or change the place for an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="24ccc-111">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="24ccc-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="24ccc-112">在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**語音**  >  **電話號碼**]。</span><span class="sxs-lookup"><span data-stu-id="24ccc-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="24ccc-113">在 [ **電話號碼** ] 頁面上，按一下 [ **數位** ] 索引標籤，選取清單中的使用者編號，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="24ccc-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="24ccc-114">在 [ **編輯** ] 窗格的 [ **緊急位置**] 底下，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="24ccc-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

    - <span data-ttu-id="24ccc-115">若要指派位置，請搜尋位置或位置，然後選取搜尋結果中的位置。</span><span class="sxs-lookup"><span data-stu-id="24ccc-115">To assign a place, search for the location or place, and then select the place in the search results.</span></span>

    - <span data-ttu-id="24ccc-116">若要變更已指派給使用者的位置，請按一下 [ **X** ] 以移除現有的位置和位置，然後按一下 [搜尋]，然後選取您要指派的位置。</span><span class="sxs-lookup"><span data-stu-id="24ccc-116">To change the place that's already assigned to the user, click **X** to remove the existing location and place, search for and then select the place you want to assign.</span></span>

4. <span data-ttu-id="24ccc-117">視您是否想要傳送電子郵件給使用者的電話號碼資訊而定，請關閉或開啟 **含有電話號碼資訊的電子郵件使用者**。</span><span class="sxs-lookup"><span data-stu-id="24ccc-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="24ccc-118">根據預設，這是開啟的。</span><span class="sxs-lookup"><span data-stu-id="24ccc-118">By default, this is on.</span></span>

5. <span data-ttu-id="24ccc-119">按一下 **[** 套用]。</span><span class="sxs-lookup"><span data-stu-id="24ccc-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="24ccc-120">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="24ccc-120">Using PowerShell</span></span>

<span data-ttu-id="24ccc-121">請參閱 [設定 CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)。</span><span class="sxs-lookup"><span data-stu-id="24ccc-121">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="24ccc-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="24ccc-122">Related topics</span></span>

- [<span data-ttu-id="24ccc-123">管理緊急通話</span><span class="sxs-lookup"><span data-stu-id="24ccc-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="24ccc-124">新增、變更或移除貴組織的緊急位置</span><span class="sxs-lookup"><span data-stu-id="24ccc-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="24ccc-125">新增、變更或移除貴組織緊急位置的地方</span><span class="sxs-lookup"><span data-stu-id="24ccc-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="24ccc-126">指派或變更使用者的緊急位置</span><span class="sxs-lookup"><span data-stu-id="24ccc-126">Assign or change an emergency location for a user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="24ccc-127">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="24ccc-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="24ccc-128">緊急通話條款及條件</span><span class="sxs-lookup"><span data-stu-id="24ccc-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
