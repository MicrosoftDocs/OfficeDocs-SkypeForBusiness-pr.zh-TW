---
title: 將混合應用程式端點移至雲端
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
description: 在解除委任商務用 Skype 內部部署環境之前，請先移動 hyrid 應用程式端點。
ms.openlocfilehash: 959a3ed47993f431636fe3c99b8502cf9aa634fe
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684380"
---
# <a name="move-hybrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="0c782-103">在解除委任內部部署環境之前，移動混合應用程式端點</span><span class="sxs-lookup"><span data-stu-id="0c782-103">Move hybrid application endpoints before decommissioning your on-premises environment</span></span>

<span data-ttu-id="0c782-104">本文說明如何在解除您的內部部署商務用 Skype 環境之前，將所需的混合應用程式端點移至 Microsoft 雲端。</span><span class="sxs-lookup"><span data-stu-id="0c782-104">This article describes how to move required hybrid application endpoints to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="0c782-105">這是將您的內部部署環境解除委任之下列步驟的步驟3：</span><span class="sxs-lookup"><span data-stu-id="0c782-105">This is step 3 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="0c782-106">步驟 1.</span><span class="sxs-lookup"><span data-stu-id="0c782-106">Step 1.</span></span> [<span data-ttu-id="0c782-107">將所有必要使用者從內部部署移至線上</span><span class="sxs-lookup"><span data-stu-id="0c782-107">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- <span data-ttu-id="0c782-108">步驟 2.</span><span class="sxs-lookup"><span data-stu-id="0c782-108">Step 2.</span></span> <span data-ttu-id="0c782-109">[停用您的混合](cloud-consolidation-disabling-hybrid.md)式設定。</span><span class="sxs-lookup"><span data-stu-id="0c782-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="0c782-110">**步驟3。將混合應用程式端點從內部部署移至線上。**</span><span class="sxs-lookup"><span data-stu-id="0c782-110">**Step 3. Move hybrid application endpoints from on-premises to online.**</span></span> <span data-ttu-id="0c782-111"> (本文) </span><span class="sxs-lookup"><span data-stu-id="0c782-111">(This article)</span></span>

- <span data-ttu-id="0c782-112">步驟 4.</span><span class="sxs-lookup"><span data-stu-id="0c782-112">Step 4.</span></span> <span data-ttu-id="0c782-113">[移除您的內部部署商務用 Skype 部署](decommission-remove-on-prem.md)。</span><span class="sxs-lookup"><span data-stu-id="0c782-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a><span data-ttu-id="0c782-114">將所有需要的混合應用程式端點從內部部署移至線上</span><span class="sxs-lookup"><span data-stu-id="0c782-114">Move all required hybrid application endpoints from on-premises to online</span></span>

<span data-ttu-id="0c782-115">在您可以將這些端點移至線上之前，您必須確定已更新 DNS 記錄，以指向端點所使用之所有 sip 網域的 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="0c782-115">Before you can move these endpoints to online, you must ensure you have updated DNS records to point to Microsoft 365 for all sip domains used by the endpoints.</span></span> <span data-ttu-id="0c782-116">如果 DNS 記錄指向內部部署，便無法建立線上資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="0c782-116">It is not possible to create online Resource Accounts if DNS records point to on-premises.</span></span> <span data-ttu-id="0c782-117">如需詳細資訊，請參閱 [停用混合](cloud-consolidation-disabling-hybrid.md)式設定。</span><span class="sxs-lookup"><span data-stu-id="0c782-117">For more information, see [Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

1. <span data-ttu-id="0c782-118">執行下列內部部署商務用 Skype Server PowerShell 命令，以取得及匯出內部部署混合應用程式端點設定：</span><span class="sxs-lookup"><span data-stu-id="0c782-118">Retrieve and export on-premises hybrid application endpoint settings by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. <span data-ttu-id="0c782-119">在 Microsoft 365 中建立並授權新的[資源帳戶](/microsoftteams/manage-resource-accounts)，以取代現有的內部部署混合應用程式端點。</span><span class="sxs-lookup"><span data-stu-id="0c782-119">Create and license new [Resource Accounts](/microsoftteams/manage-resource-accounts) in Microsoft 365 to replace the existing on-premises hybrid application endpoints.</span></span>

3. <span data-ttu-id="0c782-120">將新的資源帳戶與現有的混合式應用程式端點產生關聯。</span><span class="sxs-lookup"><span data-stu-id="0c782-120">Associate the new Resource Accounts with the existing hybrid application endpoints.</span></span>

4. <span data-ttu-id="0c782-121">執行下列內部部署商務用 Skype Server PowerShell 命令，以移除內部部署混合應用程式端點中所定義的電話號碼：</span><span class="sxs-lookup"><span data-stu-id="0c782-121">Remove phone numbers defined in the on-premises hybrid application endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. <span data-ttu-id="0c782-122">因為這些帳戶的電話號碼可能是在 Microsoft 365 而非內部部署中管理，所以請在商務用 Skype 線上中執行下列命令 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0c782-122">Because it's possible that phone numbers for these accounts were managed in Microsoft 365 instead of on-premises, run the following command in Skype for Business Online PowerShell:</span></span>

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

6. <span data-ttu-id="0c782-123">將電話號碼指派給在步驟2中建立的新資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="0c782-123">Assign phone numbers to the new Resource Accounts created in Step 2.</span></span> <span data-ttu-id="0c782-124">如需如何將電話號碼指派給資源帳戶的詳細資訊，請參閱下列文章： [指派服務號碼](/microsoftteams/manage-resource-accounts#assign-a-service-number)。</span><span class="sxs-lookup"><span data-stu-id="0c782-124">For more information about how to assign a phone number to a resource account, see the following article: [Assign a service number](/microsoftteams/manage-resource-accounts#assign-a-service-number).</span></span>

7. <span data-ttu-id="0c782-125">執行下列內部部署商務用 Skype Server PowerShell 命令，以刪除內部部署端點：</span><span class="sxs-lookup"><span data-stu-id="0c782-125">Delete the on-premises endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
<span data-ttu-id="0c782-126">您現在已準備好[移除內部部署商務用 Skype 部署](decommission-remove-on-prem.md)。</span><span class="sxs-lookup"><span data-stu-id="0c782-126">You are now ready to [remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0c782-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0c782-127">See also</span></span>

- [<span data-ttu-id="0c782-128">解除您的內部部署商務用 Skype 環境</span><span class="sxs-lookup"><span data-stu-id="0c782-128">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="0c782-129">將所有必要使用者從內部部署移至線上</span><span class="sxs-lookup"><span data-stu-id="0c782-129">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="0c782-130">停用混合式設定</span><span class="sxs-lookup"><span data-stu-id="0c782-130">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="0c782-131">移除您的內部部署商務用 Skype 部署</span><span class="sxs-lookup"><span data-stu-id="0c782-131">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




