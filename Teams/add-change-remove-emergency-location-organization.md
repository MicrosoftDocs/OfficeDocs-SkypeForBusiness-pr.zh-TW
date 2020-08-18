---
title: 新增、變更、移除緊急位置
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
description: '瞭解如何在 Microsoft 團隊系統管理中心新增、變更或移除您組織的緊急位置。 '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 762246630d245acf92c16aff8df2c9392a307b07
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788567"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a><span data-ttu-id="16221-103">新增、變更或移除貴組織的緊急位置</span><span class="sxs-lookup"><span data-stu-id="16221-103">Add, change, or remove an emergency location for your organization</span></span>

<span data-ttu-id="16221-104">緊急位置必須與電話號碼相關聯，但在這種情況下，可能會因國家/地區而異。</span><span class="sxs-lookup"><span data-stu-id="16221-104">An emergency location must be associated with a phone number, but when this happens can vary between countries and regions.</span></span> <span data-ttu-id="16221-105">例如，在美國，當您將電話號碼指派給使用者時，您必須建立緊急位置。</span><span class="sxs-lookup"><span data-stu-id="16221-105">For example, in the United States, you need to associate an emergency location when you assign the phone number to the user.</span></span> <span data-ttu-id="16221-106">在英國，當您從 Microsoft 365 或 Office 365 取得電話號碼或從目前的服務提供者轉接電話號碼時，您必須將緊急位置與電話號碼產生關聯。</span><span class="sxs-lookup"><span data-stu-id="16221-106">In the United Kingdom, you need to associate an emergency location to the phone number when you get the phone numbers from Microsoft 365 or Office 365 or transfer phone numbers from your current service provider.</span></span>

<span data-ttu-id="16221-107">無論您所在的國家或地區為何，您都可以將位置或位置新增到緊急位置，並移除緊急位置。</span><span class="sxs-lookup"><span data-stu-id="16221-107">No matter which country or region you are in, you can add a place or places to an emergency location and remove an emergency location.</span></span> <span data-ttu-id="16221-108">視貴組織中的物理位置數量而定，您可以為建築物、地面與辦公室建立位置。</span><span class="sxs-lookup"><span data-stu-id="16221-108">Depending on the number of physical locations in your organization, you can create places for buildings, floors, and offices.</span></span> <span data-ttu-id="16221-109">請參閱 [管理緊急通話](what-are-emergency-locations-addresses-and-call-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="16221-109">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="16221-110">若要瞭解如何取得通話方案和成本，請參閱 [小組附加元件授權](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)。</span><span class="sxs-lookup"><span data-stu-id="16221-110">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>

<span data-ttu-id="16221-111">您可以在 Microsoft 團隊系統管理中心或使用 PowerShell 管理您組織的緊急位置。</span><span class="sxs-lookup"><span data-stu-id="16221-111">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-an-emergency-location"></a><span data-ttu-id="16221-112">新增緊急位置</span><span class="sxs-lookup"><span data-stu-id="16221-112">Add an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="16221-113">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="16221-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="16221-114">在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**地點**  >  **緊急位址**]。</span><span class="sxs-lookup"><span data-stu-id="16221-114">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="16221-115">按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="16221-115">Click **Add**.</span></span>
3. <span data-ttu-id="16221-116">輸入位置的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="16221-116">Enter a name and description for the location.</span></span>
4. <span data-ttu-id="16221-117">選取國家或地區，然後輸入位址。</span><span class="sxs-lookup"><span data-stu-id="16221-117">Select the country or region, and then enter the address.</span></span>

   > [!NOTE]
   > <span data-ttu-id="16221-118">在比利時、法國、德國、愛爾蘭、荷蘭及西班牙，若要在 Microsoft 365 或 Office 365 中成功啟用電話號碼，請務必瞭解，在緊急位置（用來取得號碼）中設定的位址必須符合電話號碼的區功能變數代碼。</span><span class="sxs-lookup"><span data-stu-id="16221-118">In Belgium, France, Germany, Ireland, Netherlands, and Spain, it's important to understand that to successfully activate a phone number in Microsoft 365 or Office 365, the address set up in the emergency location, which is used to acquire the number, must match the phone number's area code.</span></span>

5. <span data-ttu-id="16221-119">如果找不到位址，而您想要手動編輯位址，請開啟 **[手動編輯位址**]。</span><span class="sxs-lookup"><span data-stu-id="16221-119">If the address isn't found and you want to manually edit the address, turn on **Edit the address manually**.</span></span>
6. <span data-ttu-id="16221-120">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="16221-120">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="16221-121">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="16221-121">Using PowerShell</span></span>

<span data-ttu-id="16221-122">請參閱 [新-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress)。</span><span class="sxs-lookup"><span data-stu-id="16221-122">See [New-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress).</span></span>
    
## <a name="change-an-emergency-location"></a><span data-ttu-id="16221-123">變更緊急位置</span><span class="sxs-lookup"><span data-stu-id="16221-123">Change an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="16221-124">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="16221-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="16221-125">在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**地點**  >  **緊急位址**]。</span><span class="sxs-lookup"><span data-stu-id="16221-125">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="16221-126">在清單中，選取您要變更的位置，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="16221-126">In the list, select the location that you want to change, and then click **Edit**.</span></span>
3. <span data-ttu-id="16221-127">進行您想要的變更。</span><span class="sxs-lookup"><span data-stu-id="16221-127">Make the changes you want.</span></span>
4. <span data-ttu-id="16221-128">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="16221-128">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="16221-129">只有在位址未驗證時，才能變更位置的位址資訊。</span><span class="sxs-lookup"><span data-stu-id="16221-129">You can change the address information for a location only if the address isn't validated.</span></span> <span data-ttu-id="16221-130">如果位址已經過驗證，且您需要變更位址，請刪除該位置，然後使用正確的位址建立新位置。</span><span class="sxs-lookup"><span data-stu-id="16221-130">If the address is already validated, and you need to change the address, delete the location, and then create a new location with the correct address.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="16221-131">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="16221-131">Using PowerShell</span></span>

<span data-ttu-id="16221-132">請參閱 [設定 CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress)。</span><span class="sxs-lookup"><span data-stu-id="16221-132">See [Set-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress).</span></span>
    
## <a name="remove-an-emergency-location"></a><span data-ttu-id="16221-133">移除緊急位置</span><span class="sxs-lookup"><span data-stu-id="16221-133">Remove an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="16221-134">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="16221-134">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="16221-135">在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**地點**  >  **緊急位址**]。</span><span class="sxs-lookup"><span data-stu-id="16221-135">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="16221-136">在清單中，選取您要移除的位置，然後按一下 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="16221-136">In the list, select the location that you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="16221-137">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="16221-137">Using PowerShell</span></span>

<span data-ttu-id="16221-138">請參閱 [移除-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress)。</span><span class="sxs-lookup"><span data-stu-id="16221-138">See [Remove-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="16221-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="16221-139">Related topics</span></span>

- [<span data-ttu-id="16221-140">管理緊急通話</span><span class="sxs-lookup"><span data-stu-id="16221-140">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="16221-141">新增、變更或移除貴組織緊急位置的地方</span><span class="sxs-lookup"><span data-stu-id="16221-141">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="16221-142">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="16221-142">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="16221-143">緊急通話條款及條件</span><span class="sxs-lookup"><span data-stu-id="16221-143">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
