---
title: 將混合應用程式端點遷移至雲端
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
description: 在解除委任商務用 Skype 內部部署環境之前，請先遷移 hyrid 應用程式端點。
ms.openlocfilehash: ee437f7f6c35ee67168c81e8e8ad440b1b0ba824
ms.sourcegitcommit: 3f1635d1915561798ea764c3e33d7db55f7e49da
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/23/2021
ms.locfileid: "53574238"
---
# <a name="migrate-hybrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a>在解除委任內部部署環境之前遷移混合應用程式端點

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

本文說明如何在解除您的內部部署商務用 Skype 環境之前，將所需的混合應用程式端點移至 Microsoft 雲端。 這是將您的內部部署環境解除委任之下列步驟的步驟3：

- 步驟 1。 [將所有必要使用者從內部部署移至線上](decommission-move-on-prem-users.md)

- 步驟 2. [停用您的混合](cloud-consolidation-disabling-hybrid.md)式設定。

- **步驟3。從內部部署向線上遷移混合應用程式端點。**  (本文) 

- 步驟 4： [移除您的內部部署商務用 Skype 部署](decommission-remove-on-prem.md)。


## <a name="migrate-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a>將所有需要的混合應用程式端點從內部部署遷移至線上

在您可以將這些端點移至線上之前，您必須確定已更新 DNS 記錄，以指向端點所使用之所有 sip 網域的 Microsoft 365。 請注意，一旦您將 DNS 更新為指向 Microsoft 365，只要您完成此步驟，就無法再發現任何現有的混合應用程式端點。 由於此步驟 (建立線上資源) 帳戶，因此如果 DNS 記錄指向內部部署，您應該規劃在相同維護視窗中執行步驟2和3。 如需詳細資訊，請參閱 [停用混合](cloud-consolidation-disabling-hybrid.md)式設定。

1. 執行下列內部部署商務用 Skype Server PowerShell 命令，以取得及匯出內部部署混合應用程式端點設定：

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. 在 Microsoft 365 中建立並授權新的[資源帳戶](/microsoftteams/manage-resource-accounts)，以取代現有的內部部署混合應用程式端點。

3. 將新的資源帳戶與現有的混合式應用程式端點產生關聯。

4. 執行下列內部部署商務用 Skype Server PowerShell 命令，以移除內部部署混合應用程式端點中所定義的電話號碼：

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. 因為這些帳戶的電話號碼可能是在 Microsoft 365 而非內部部署中管理，所以請在 Teams 中執行下列命令 PowerShell:

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

6. 將電話號碼指派給在步驟2中建立的新資源帳戶。 如需如何將電話號碼指派給資源帳戶的詳細資訊，請參閱下列文章： [指派服務號碼](/microsoftteams/manage-resource-accounts#assign-a-service-number)。

7. 執行下列內部部署商務用 Skype Server PowerShell 命令，以刪除內部部署端點：

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
您現在已準備好[移除內部部署商務用 Skype 部署](decommission-remove-on-prem.md)。

## <a name="see-also"></a>另請參閱

- [解除您的內部部署商務用 Skype 環境](decommission-on-prem-overview.md)

- [將所有必要使用者從內部部署移至線上](decommission-move-on-prem-users.md)

- [停用混合式設定](cloud-consolidation-disabling-hybrid.md)

- [移除您的內部部署商務用 Skype 部署](decommission-remove-on-prem.md)




