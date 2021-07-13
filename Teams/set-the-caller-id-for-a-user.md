---
title: 設定使用者的來電顯示
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: 瞭解使用者Microsoft 365號碼Office 365使用者 (號碼的預設本機號碼) 電話線識別碼。 您可以變更或封鎖使用者的本機號碼。
ms.openlocfilehash: 2e94dde2c3271e2b31e4c679c5e020c121d28c25
ms.sourcegitcommit: 41e2e97b5856e727e42ebf5bfebceede9af56481
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53388648"
---
# <a name="set-the-caller-id-for-a-user"></a>設定使用者的來電顯示

電話系統中Microsoft 365提供預設本機號碼，即使用者指派的電話號碼。 您可以變更或封鎖本機號碼 (呼叫線識別碼) 使用者。 您可以進一步瞭解如何在組織中使用本機號碼，方法為 [：如何在](how-can-caller-id-be-used-in-your-organization.md)貴組織中使用本機號碼。
  
根據預設，下列本機號碼設定 **會關閉**。 這表示Teams撥打 PSTN 電話時，可以看到該使用者的電話號碼。 您可以變更這些設定，如下所示：
  
- **外發本機號碼** 您可以將使用者的本機號碼取代為另一個電話號碼，預設為使用者的電話號碼。 例如，您可以變更使用者的本機號碼，從他們的電話號碼變更為公司的主要電話號碼，或變更為法務部門的主要電話號碼。 此外，您可以將通話識別碼設為任何線上服務號碼 (付費或免付費) ，或透過指派給自動總機或通話佇列使用的資源帳戶的直接路由，將內部部署電話號碼設定為內部部署電話號碼。
    
  > [!NOTE]
  > 如果您想要使用 Service *參數，* 您必須指定有效的服務號碼。
  > 如果下拉式中看不到 PowerShell 模組 2.3.1 或更高版本，您必須在 Teams PowerShell 模組 2.3.1 或稍後使用 PowerShell Cmdlet New-CsCallingLineIdentity 或 Set-CsCallingLineIdentity。
  
- **封鎖外發本機號碼。** 您可以封鎖外寄本機號碼，防止在使用者的外寄 PSTN 通話中送出。 這麼做會封鎖他們的電話號碼，不會顯示在被通話者的電話上。
    
- **封鎖本機號碼。** 您可以在任何傳入的 PSTN 通話中封鎖使用者接收本機號碼。

- **將通話方名稱設定 (CNAM) 。** 針對您的Microsoft Teams，您可以在外寄 PSTN 通話上傳送 CNAM。
    
> [!IMPORTANT]
> 緊急電話會一直將使用者的電話號碼 (來電) 。 
  

  
若要深入瞭解這些設定，以及如何使用這些設定，請參閱如何在貴組織中 [使用本機號碼](how-can-caller-id-be-used-in-your-organization.md)。
  
## <a name="set-your-caller-id-policy-settings"></a>設定本機號碼策略設定

> [!NOTE]
> 若要將本機號碼設為資源帳戶電話號碼，並設定通話方名稱，請使用 Teams PowerShell 模組 2.3.1 或更高版本中的 PowerShell Cmdlet New-CsCallingLineIdentity 或 Set-CsCallingLineIdentity。  (系統管理中心目前Microsoft Teams這些選項)  

開啟 Windows PowerShell命令提示符，然後執行下列命令：

```PowerShell
# When using Teams PowerShell Module

Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
``` 

### <a name="view-create-and-apply-policy-settings"></a>查看、建立及適用原則設定

1. 若要查看貴組織中所有的本機號碼策略設定，請執行：

     ```PowerShell
     Get-CsCallingLineIdentity |fl
     ```
   詳細資訊，請參閱 [Get-CsCallingLineIdentity](/powershell/module/skype/Get-CsCallingLineIdentity)。
    
2. 若要為貴組織建立新的本機號碼策略，請使用 New-CsCallingIdentity Cmdlet：
    
     ```PowerShell
     New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
     ```
    在所有的情況下，「服務編號」欄位不應包含初始的「+」。

   詳細資訊，請參閱 [New-CsCallingLineIdentity](/powershell/module/skype/New-CsCallingLineIdentity)。
    
3. 使用 Cmdlet 來Grant-CsCallingIdentity原則。 例如，下列範例將新原則適用于使用者 Amos Marble。
    
     ```PowerShell
     Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
     ```
   詳細資訊，請參閱 [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) Cmdlet。
    

4. 如果您想要封鎖本機號碼，請執行：
    
   ```PowerShell
   Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true
   ``` 

   詳細資訊，請參閱 [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity)。
    
5. 若要將您建立的策略設定適用于貴組織的使用者，請執行：
    
   ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
   ```
   詳細資訊，請參閱 [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity)。

6. 若要建立新的本機號碼規則，將本機號碼設定為指定資源帳戶的電話號碼，然後將通話方名稱設定為 Contoso：

   ```PowerShell
   $ObjId = (Get-CsOnlineApplicationInstance -Identity dkcq@contoso.com).ObjectId
   New-CsCallingLineIdentity  -Identity DKCQ -CallingIDSubstitute Resource -EnableUserOverride $false -ResourceAccount $ObjId -CompanyName "Contoso"
   ```

如果您已經建立原則，您可以使用 [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) Cmdlet 對現有原則進行變更，然後使用 [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) Cmdlet 將設定套用給使用者。
    
### <a name="remove-a-policy-setting"></a>移除策略設定

若要從貴組織移除策略，請執行：
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
若要從使用者移除策略，請執行：
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>想要進一Windows PowerShell？

Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。 有了Windows PowerShell，您可以使用單一Microsoft 365管理點來管理您的工作，以簡化您的日常工作。 若要開始使用Windows PowerShell，請參閱以下主題：
    
- [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [您可能會想要使用 Windows PowerShell 管理Microsoft 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell相比于僅使用 Microsoft 365 系統管理中心，在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。 請從下列主題瞭解這些優點：
    
- [使用 Microsoft 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- [使用 Windows PowerShell 管理 商務用 Skype Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [使用Windows PowerShell執行線上商務用 Skype管理工作](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  
 ## <a name="related-topics"></a>相關主題
[移轉電話號碼的常見問題](./phone-number-calling-plans/port-order-overview.md)

[用於通話方案的各種電話號碼](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)

[深入了解通話線路識別碼和來電方名稱](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[緊急通話條款及條件](./emergency-calling-terms-and-conditions.md)

[商務用 Skype線上：緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
