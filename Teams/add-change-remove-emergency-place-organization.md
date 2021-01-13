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
description: 瞭解如何在 Microsoft 團隊系統管理中心新增、變更或移除您組織緊急位置的位置。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d390113b30558b94fadab695731b8c08b4c01ace
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806273"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a><span data-ttu-id="4c7e7-103">新增、變更或移除貴組織緊急位置的地方</span><span class="sxs-lookup"><span data-stu-id="4c7e7-103">Add, change, or remove a place for an emergency location in your organization</span></span>

<span data-ttu-id="4c7e7-104">視貴組織中的物理位置數量而定，您可以新增建築物、地面和辦事處的位置，以建立更明確的緊急位置。</span><span class="sxs-lookup"><span data-stu-id="4c7e7-104">Depending on the number of physical locations in your organization, you can add places for buildings, floors, and offices to create a more specific emergency location.</span></span> <span data-ttu-id="4c7e7-105">如需詳細資訊，請參閱 [管理緊急通話](what-are-emergency-locations-addresses-and-call-routing.md) 。</span><span class="sxs-lookup"><span data-stu-id="4c7e7-105">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) for more information.</span></span>
  
<span data-ttu-id="4c7e7-106">若要瞭解如何取得通話方案和成本，請參閱 [小組附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="4c7e7-106">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="4c7e7-107">您可以在 Microsoft 團隊系統管理中心或使用 PowerShell 管理您組織的緊急位置。</span><span class="sxs-lookup"><span data-stu-id="4c7e7-107">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-a-place-to-an-emergency-location"></a><span data-ttu-id="4c7e7-108">在緊急位置加入地點</span><span class="sxs-lookup"><span data-stu-id="4c7e7-108">Add a place to an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="4c7e7-109">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="4c7e7-109">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="4c7e7-110">在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**地點**  >  **緊急位址**]。</span><span class="sxs-lookup"><span data-stu-id="4c7e7-110">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="4c7e7-111">在清單中，按一下您要新增位置的位置名稱。</span><span class="sxs-lookup"><span data-stu-id="4c7e7-111">In the list, click the name of the location for which you want to add a place.</span></span>
3. <span data-ttu-id="4c7e7-112">按一下 [ **位置** ] 索引標籤上的 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="4c7e7-112">On the **Places** tab, click **Add**.</span></span>
4. <span data-ttu-id="4c7e7-113">輸入地點名稱， **然後按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="4c7e7-113">Enter a place name, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="4c7e7-114">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c7e7-114">Using PowerShell</span></span>

<span data-ttu-id="4c7e7-115">請參閱 [新-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation)。</span><span class="sxs-lookup"><span data-stu-id="4c7e7-115">See [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).</span></span>
    
## <a name="change-a-place-for-an-emergency-location"></a><span data-ttu-id="4c7e7-116">變更緊急位置的位置</span><span class="sxs-lookup"><span data-stu-id="4c7e7-116">Change a place for an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="4c7e7-117">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="4c7e7-117">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="4c7e7-118">在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**地點**  >  **緊急位址**]。</span><span class="sxs-lookup"><span data-stu-id="4c7e7-118">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="4c7e7-119">在清單中，按一下您要變更位置的位置名稱。</span><span class="sxs-lookup"><span data-stu-id="4c7e7-119">In the list, click the name of the location for which you want to change a place.</span></span>
3. <span data-ttu-id="4c7e7-120">在 [ **位置** ] 索引標籤上，選取您要變更的位置，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="4c7e7-120">On the **Places** tab, select the place you want to change, and then click **Edit**.</span></span>
4. <span data-ttu-id="4c7e7-121">更新 [位置資訊]， **然後按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="4c7e7-121">Update the place information, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="4c7e7-122">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c7e7-122">Using PowerShell</span></span>

<span data-ttu-id="4c7e7-123">請參閱 [設定 CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)。</span><span class="sxs-lookup"><span data-stu-id="4c7e7-123">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="remove-a-place-from-an-emergency-location"></a><span data-ttu-id="4c7e7-124">從緊急位置移除位置</span><span class="sxs-lookup"><span data-stu-id="4c7e7-124">Remove a place from an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="4c7e7-125">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="4c7e7-125">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="4c7e7-126">在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**地點**  >  **緊急位址**]。</span><span class="sxs-lookup"><span data-stu-id="4c7e7-126">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="4c7e7-127">在清單中，按一下您要移除位置的位置名稱。</span><span class="sxs-lookup"><span data-stu-id="4c7e7-127">In the list, click the name of the location for which you want to remove a place.</span></span>
3. <span data-ttu-id="4c7e7-128">在 [ **位置** ] 索引標籤上，選取您要移除的位置，然後按一下 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="4c7e7-128">On the **Places** tab, select the place you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="4c7e7-129">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c7e7-129">Using PowerShell</span></span>

<span data-ttu-id="4c7e7-130">請參閱 [移除-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation)。</span><span class="sxs-lookup"><span data-stu-id="4c7e7-130">See [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="4c7e7-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="4c7e7-131">Related topics</span></span>

- [<span data-ttu-id="4c7e7-132">新增、變更或移除貴組織緊急位置的地方</span><span class="sxs-lookup"><span data-stu-id="4c7e7-132">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="4c7e7-133">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="4c7e7-133">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="4c7e7-134">緊急通話條款及條件</span><span class="sxs-lookup"><span data-stu-id="4c7e7-134">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
