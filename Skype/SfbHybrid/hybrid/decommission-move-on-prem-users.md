---
title: 將使用者和端點移至雲端
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 在解除委任商務用 Skype 內部部署環境之前，移動使用者和端點。
ms.openlocfilehash: 130f276d07dd33be33d3c038c2ead20c7a887e6b
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593888"
---
# <a name="move-required-users-and-endpoints-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="6b97b-103">在解除委任內部部署環境之前，移動必要的使用者和端點</span><span class="sxs-lookup"><span data-stu-id="6b97b-103">Move required users and endpoints before decommissioning your on-premises environment</span></span>

<span data-ttu-id="6b97b-104">本文說明如何在解除委任您的內部部署商務用 Skype 環境之前，將所需的使用者和應用程式端點移至 Microsoft 雲端。</span><span class="sxs-lookup"><span data-stu-id="6b97b-104">This article describes how to move required users and application endpoints to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="6b97b-105">這是解除委任內部部署環境之下列步驟的步驟1：</span><span class="sxs-lookup"><span data-stu-id="6b97b-105">This is step 1 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="6b97b-106">**步驟1。將所有需要的使用者和應用程式端點從內部部署移至線上。**</span><span class="sxs-lookup"><span data-stu-id="6b97b-106">**Step 1. Move all required users and application endpoints from on-premises to online.**</span></span> <span data-ttu-id="6b97b-107"> (本文。 ) </span><span class="sxs-lookup"><span data-stu-id="6b97b-107">(This article.)</span></span>

- <span data-ttu-id="6b97b-108">步驟 2.</span><span class="sxs-lookup"><span data-stu-id="6b97b-108">Step 2.</span></span> <span data-ttu-id="6b97b-109">[停用您的混合](cloud-consolidation-disabling-hybrid.md)式設定。</span><span class="sxs-lookup"><span data-stu-id="6b97b-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="6b97b-110">步驟 3.</span><span class="sxs-lookup"><span data-stu-id="6b97b-110">Step 3.</span></span> <span data-ttu-id="6b97b-111">[移除您的內部部署商務用 Skype 部署](decommission-remove-on-prem.md)。</span><span class="sxs-lookup"><span data-stu-id="6b97b-111">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="6b97b-112">將所有必要使用者從內部部署移至雲端</span><span class="sxs-lookup"><span data-stu-id="6b97b-112">Move all required users from on-premises to the cloud</span></span>

<span data-ttu-id="6b97b-113">完成遷移之後，您將繼續使用的任何使用者，必須先從內部部署移至雲端。</span><span class="sxs-lookup"><span data-stu-id="6b97b-113">Any users that you will continue to use after completing the migration must first be moved from on-premises to the cloud.</span></span> <span data-ttu-id="6b97b-114">您可以使用內部部署系統管理工具移動使用者。</span><span class="sxs-lookup"><span data-stu-id="6b97b-114">You move users by using the on-premises administration tools.</span></span> <span data-ttu-id="6b97b-115">如需詳細資訊，請參閱 [在內部部署與雲端之間移動使用者](move-users-between-on-premises-and-cloud.md)。</span><span class="sxs-lookup"><span data-stu-id="6b97b-115">For details, see [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span></span>

<span data-ttu-id="6b97b-116">雖然具有內部部署商務用 Skype 伺服器帳戶的使用者可以使用小組，但這些使用者卻沒有小組的完整功能。</span><span class="sxs-lookup"><span data-stu-id="6b97b-116">Although it is possible for users with on-premises Skype for Business Server accounts to use Teams, these users do not have the full functionality of Teams.</span></span> <span data-ttu-id="6b97b-117">無論是線上或內部部署) ，這些使用者都無法與其他任何使用商務用 Skype 的使用者進行交互操作或同盟 (。</span><span class="sxs-lookup"><span data-stu-id="6b97b-117">These users cannot interoperate or federate with any other user still using Skype for Business (whether online or on-premises).</span></span> <span data-ttu-id="6b97b-118">這些使用者也不能在其團隊用戶端接收 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="6b97b-118">Nor can these users receive PSTN calls in their Teams client.</span></span> <span data-ttu-id="6b97b-119">因此，您必須將這些使用者移至線上。</span><span class="sxs-lookup"><span data-stu-id="6b97b-119">Therefore, you must move these users to online.</span></span> <span data-ttu-id="6b97b-120">此步驟也可確保在商務用 Skype Server 中建立的任何連絡人或會議都會遷移至小組。</span><span class="sxs-lookup"><span data-stu-id="6b97b-120">This step also ensures any contacts or meetings created in Skype for Business Server are migrated to Teams.</span></span>

<span data-ttu-id="6b97b-121">若要檢查內部部署中是否還有任何其他使用者，請在 [商務用 Skype Server PowerShell] 視窗中執行下列 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6b97b-121">To check if there are any remaining users in your on-premises deployment, run the following cmdlet in a Skype for Business Server PowerShell window.</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

<span data-ttu-id="6b97b-122">若傳回任何使用者，請複查輸出以判斷是否必須將任何帳戶移至雲端，並針對任何這類使用者執行[下列步驟。](move-users-between-on-premises-and-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="6b97b-122">If any users are returned, review the output to determine if any accounts must be moved to the cloud, and, for any such users, follow the steps [here](move-users-between-on-premises-and-cloud.md).</span></span> <span data-ttu-id="6b97b-123">針對不再需要的使用者帳戶，請執行下列商務用 Skype Server PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="6b97b-123">For user accounts that are no longer needed, run the following Skype for Business Server PowerShell cmdlet:</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> <span data-ttu-id="6b97b-124">執行 Disable-CsUser 會移除所有符合篩選準則之使用者的所有商務用 Skype 屬性。</span><span class="sxs-lookup"><span data-stu-id="6b97b-124">Running Disable-CsUser will remove all Skype for Business attributes for all users meeting the filter criteria.</span></span> <span data-ttu-id="6b97b-125">繼續之前，請先確認這些帳戶已不再需要繼續進行。</span><span class="sxs-lookup"><span data-stu-id="6b97b-125">Before proceeding, confirm that these accounts are no longer needed going forward.</span></span>

## <a name="move-on-premises-hybrid-application-endpoints-to-microsoft-365"></a><span data-ttu-id="6b97b-126">將內部部署混合應用程式端點移至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6b97b-126">Move on-premises hybrid application endpoints to Microsoft 365</span></span>

1. <span data-ttu-id="6b97b-127">執行下列內部部署商務用 Skype Server PowerShell 命令，以取得及匯出內部部署混合應用程式端點設定：</span><span class="sxs-lookup"><span data-stu-id="6b97b-127">Retrieve and export on-premises hybrid application endpoint settings by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. <span data-ttu-id="6b97b-128">在 Microsoft 365 中建立並授權新的 [資源帳戶](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) ，以取代現有的內部部署混合應用程式端點。</span><span class="sxs-lookup"><span data-stu-id="6b97b-128">Create and license new [Resource Accounts](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) in Microsoft 365 to replace the existing on-premises hybrid application endpoints.</span></span>

3. <span data-ttu-id="6b97b-129">將新的資源帳戶與現有的混合式應用程式端點產生關聯。</span><span class="sxs-lookup"><span data-stu-id="6b97b-129">Associate the new Resource Accounts with the existing hybrid application endpoints.</span></span>

4. <span data-ttu-id="6b97b-130">執行下列內部部署商務用 Skype Server PowerShell 命令，以移除內部部署混合應用程式端點中所定義的電話號碼：</span><span class="sxs-lookup"><span data-stu-id="6b97b-130">Remove phone numbers defined in the on-premises hybrid application endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. <span data-ttu-id="6b97b-131">因為這些帳戶的電話號碼可能是在 Microsoft 365 而非內部部署中管理，所以請在商務用 Skype Online 中執行下列命令 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6b97b-131">Because it's possible that phone numbers for these accounts were managed in Microsoft 365 instead of on-premises, run the following command in Skype for Business Online PowerShell:</span></span>

   ```PowerShell
   $endpoints = import-csv "c:\backup\HybridEndpoints.csv"
   foreach ($endpoint in $endpoints)
   {
   if($endpoint.LineUri)
       {
           $upn = $endpoint.SipAddress.Replace("sip:","")
           $ra=Get-CsOnlineApplicationInstance | where UserPrincipalName -eq $upn 
           Set-CsOnlineApplicationInstance -Identity $ra.Objectid -OnpremPhoneNumber ""
       }
   }
   ```

6. <span data-ttu-id="6b97b-132">將電話號碼指派給在步驟2中建立的新資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="6b97b-132">Assign phone numbers to the new Resource Accounts created in Step 2.</span></span> <span data-ttu-id="6b97b-133">如需如何將電話號碼指派給資源帳戶的詳細資訊，請參閱下列文章： [指派服務號碼](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number)。</span><span class="sxs-lookup"><span data-stu-id="6b97b-133">For more information about how to assign a phone number to a resource account, see the following article: [Assign a service number](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number).</span></span>

7. <span data-ttu-id="6b97b-134">執行下列內部部署商務用 Skype Server PowerShell 命令，以刪除內部部署端點：</span><span class="sxs-lookup"><span data-stu-id="6b97b-134">Delete the on-premises endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
<span data-ttu-id="6b97b-135">您現在已準備好 [停用混合](cloud-consolidation-disabling-hybrid.md)式設定。</span><span class="sxs-lookup"><span data-stu-id="6b97b-135">You are now ready to [disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6b97b-136">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6b97b-136">See also</span></span>

- [<span data-ttu-id="6b97b-137">解除委任您的內部部署商務用 Skype 環境</span><span class="sxs-lookup"><span data-stu-id="6b97b-137">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="6b97b-138">停用混合式設定</span><span class="sxs-lookup"><span data-stu-id="6b97b-138">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="6b97b-139">移除您的內部部署商務用 Skype 部署</span><span class="sxs-lookup"><span data-stu-id="6b97b-139">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




