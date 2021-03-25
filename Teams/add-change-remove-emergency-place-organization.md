---
title: 新增、變更、移除緊急位置的位置
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
description: 瞭解如何在 Microsoft Teams 系統管理中心為貴組織新增、變更或移除緊急位置的位置。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 50343fbd1d16694e46afafe53114f2dde4b7b150
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121501"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a><span data-ttu-id="73efd-103">新增、變更或移除貴組織緊急位置的地方</span><span class="sxs-lookup"><span data-stu-id="73efd-103">Add, change, or remove a place for an emergency location in your organization</span></span>

<span data-ttu-id="73efd-104">根據貴組織實體位置的數量，您可以新增建築物、樓層和辦公室的位置，以建立更具體的緊急位置。</span><span class="sxs-lookup"><span data-stu-id="73efd-104">Depending on the number of physical locations in your organization, you can add places for buildings, floors, and offices to create a more specific emergency location.</span></span> <span data-ttu-id="73efd-105">請參閱 [管理緊急電話](what-are-emergency-locations-addresses-and-call-routing.md) 以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="73efd-105">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) for more information.</span></span>
  
<span data-ttu-id="73efd-106">若要瞭解如何取得通話方案及其費用，請參閱 [Teams 附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="73efd-106">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="73efd-107">您可以在 Microsoft Teams 系統管理中心或使用 PowerShell 管理組織的緊急位置。</span><span class="sxs-lookup"><span data-stu-id="73efd-107">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-a-place-to-an-emergency-location"></a><span data-ttu-id="73efd-108">新增位置至緊急位置</span><span class="sxs-lookup"><span data-stu-id="73efd-108">Add a place to an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="73efd-109">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="73efd-109">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="73efd-110">在 Microsoft Teams 系統管理中心的左側流覽中，按一下 **[位置**  >  **緊急位址**> 。</span><span class="sxs-lookup"><span data-stu-id="73efd-110">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="73efd-111">在清單中，按一下要新增位置的位置名稱。</span><span class="sxs-lookup"><span data-stu-id="73efd-111">In the list, click the name of the location for which you want to add a place.</span></span>
3. <span data-ttu-id="73efd-112">在 [ **位置」** 選項卡上，按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="73efd-112">On the **Places** tab, click **Add**.</span></span>
4. <span data-ttu-id="73efd-113">輸入地點名稱，然後按一下 **[Apply.**</span><span class="sxs-lookup"><span data-stu-id="73efd-113">Enter a place name, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="73efd-114">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="73efd-114">Using PowerShell</span></span>

<span data-ttu-id="73efd-115">請參閱 [New-CsOnlineLisLocation](/powershell/module/skype/new-csonlinelislocation)。</span><span class="sxs-lookup"><span data-stu-id="73efd-115">See [New-CsOnlineLisLocation](/powershell/module/skype/new-csonlinelislocation).</span></span>
    
## <a name="change-a-place-for-an-emergency-location"></a><span data-ttu-id="73efd-116">變更緊急位置的位置</span><span class="sxs-lookup"><span data-stu-id="73efd-116">Change a place for an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="73efd-117">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="73efd-117">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="73efd-118">在 Microsoft Teams 系統管理中心的左側流覽中，按一下 **[位置**  >  **緊急位址**> 。</span><span class="sxs-lookup"><span data-stu-id="73efd-118">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="73efd-119">在清單中，按一下要變更位置的位置名稱。</span><span class="sxs-lookup"><span data-stu-id="73efd-119">In the list, click the name of the location for which you want to change a place.</span></span>
3. <span data-ttu-id="73efd-120">在 [ **位置」** 選項卡上，選取您想要變更的位置，然後按一下 [ **編輯**。</span><span class="sxs-lookup"><span data-stu-id="73efd-120">On the **Places** tab, select the place you want to change, and then click **Edit**.</span></span>
4. <span data-ttu-id="73efd-121">更新位置資訊，然後按一下 **[Apply.**</span><span class="sxs-lookup"><span data-stu-id="73efd-121">Update the place information, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="73efd-122">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="73efd-122">Using PowerShell</span></span>

<span data-ttu-id="73efd-123">請參閱 [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation)。</span><span class="sxs-lookup"><span data-stu-id="73efd-123">See [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="remove-a-place-from-an-emergency-location"></a><span data-ttu-id="73efd-124">從緊急位置移除位置</span><span class="sxs-lookup"><span data-stu-id="73efd-124">Remove a place from an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="73efd-125">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="73efd-125">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="73efd-126">在 Microsoft Teams 系統管理中心的左側流覽中，按一下 **[位置**  >  **緊急位址**> 。</span><span class="sxs-lookup"><span data-stu-id="73efd-126">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="73efd-127">在清單中，按一下要移除位置的位置名稱。</span><span class="sxs-lookup"><span data-stu-id="73efd-127">In the list, click the name of the location for which you want to remove a place.</span></span>
3. <span data-ttu-id="73efd-128">在 [ **位置」** 選項卡上，選取您想要移除的位置，然後按一下 [ **刪除**。</span><span class="sxs-lookup"><span data-stu-id="73efd-128">On the **Places** tab, select the place you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="73efd-129">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="73efd-129">Using PowerShell</span></span>

<span data-ttu-id="73efd-130">請參閱 [Remove-CsOnlineLisLocation](/powershell/module/skype/remove-csonlinelislocation)。</span><span class="sxs-lookup"><span data-stu-id="73efd-130">See [Remove-CsOnlineLisLocation](/powershell/module/skype/remove-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="73efd-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="73efd-131">Related topics</span></span>

- [<span data-ttu-id="73efd-132">新增、變更或移除貴組織緊急位置的地方</span><span class="sxs-lookup"><span data-stu-id="73efd-132">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="73efd-133">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="73efd-133">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="73efd-134">緊急通話條款及條件</span><span class="sxs-lookup"><span data-stu-id="73efd-134">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)