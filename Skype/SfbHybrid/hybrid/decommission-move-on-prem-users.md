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
# <a name="move-required-users-and-endpoints-before-decommissioning-your-on-premises-environment"></a>在解除委任內部部署環境之前，移動必要的使用者和端點

本文說明如何在解除委任您的內部部署商務用 Skype 環境之前，將所需的使用者和應用程式端點移至 Microsoft 雲端。 這是解除委任內部部署環境之下列步驟的步驟1：

- **步驟1。將所有需要的使用者和應用程式端點從內部部署移至線上。**  (本文。 ) 

- 步驟 2. [停用您的混合](cloud-consolidation-disabling-hybrid.md)式設定。

- 步驟 3. [移除您的內部部署商務用 Skype 部署](decommission-remove-on-prem.md)。


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a>將所有必要使用者從內部部署移至雲端

完成遷移之後，您將繼續使用的任何使用者，必須先從內部部署移至雲端。 您可以使用內部部署系統管理工具移動使用者。 如需詳細資訊，請參閱 [在內部部署與雲端之間移動使用者](move-users-between-on-premises-and-cloud.md)。

雖然具有內部部署商務用 Skype 伺服器帳戶的使用者可以使用小組，但這些使用者卻沒有小組的完整功能。 無論是線上或內部部署) ，這些使用者都無法與其他任何使用商務用 Skype 的使用者進行交互操作或同盟 (。 這些使用者也不能在其團隊用戶端接收 PSTN 通話。 因此，您必須將這些使用者移至線上。 此步驟也可確保在商務用 Skype Server 中建立的任何連絡人或會議都會遷移至小組。

若要檢查內部部署中是否還有任何其他使用者，請在 [商務用 Skype Server PowerShell] 視窗中執行下列 Cmdlet。

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

若傳回任何使用者，請複查輸出以判斷是否必須將任何帳戶移至雲端，並針對任何這類使用者執行[下列步驟。](move-users-between-on-premises-and-cloud.md) 針對不再需要的使用者帳戶，請執行下列商務用 Skype Server PowerShell Cmdlet：

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> 執行 Disable-CsUser 會移除所有符合篩選準則之使用者的所有商務用 Skype 屬性。 繼續之前，請先確認這些帳戶已不再需要繼續進行。

## <a name="move-on-premises-hybrid-application-endpoints-to-microsoft-365"></a>將內部部署混合應用程式端點移至 Microsoft 365

1. 執行下列內部部署商務用 Skype Server PowerShell 命令，以取得及匯出內部部署混合應用程式端點設定：

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. 在 Microsoft 365 中建立並授權新的 [資源帳戶](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) ，以取代現有的內部部署混合應用程式端點。

3. 將新的資源帳戶與現有的混合式應用程式端點產生關聯。

4. 執行下列內部部署商務用 Skype Server PowerShell 命令，以移除內部部署混合應用程式端點中所定義的電話號碼：

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. 因為這些帳戶的電話號碼可能是在 Microsoft 365 而非內部部署中管理，所以請在商務用 Skype Online 中執行下列命令 PowerShell:

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

6. 將電話號碼指派給在步驟2中建立的新資源帳戶。 如需如何將電話號碼指派給資源帳戶的詳細資訊，請參閱下列文章： [指派服務號碼](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number)。

7. 執行下列內部部署商務用 Skype Server PowerShell 命令，以刪除內部部署端點：

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
您現在已準備好 [停用混合](cloud-consolidation-disabling-hybrid.md)式設定。

## <a name="see-also"></a>另請參閱

- [解除委任您的內部部署商務用 Skype 環境](decommission-on-prem-overview.md)

- [停用混合式設定](cloud-consolidation-disabling-hybrid.md)

- [移除您的內部部署商務用 Skype 部署](decommission-remove-on-prem.md)




