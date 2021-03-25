---
title: 設定使用者的來電顯示
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: 瞭解 Microsoft 365 和 Office 365 預設本機號碼 (使用者指派的電話號碼) 也稱為電話線識別碼。 您可以變更或封鎖使用者的本機號碼。
ms.openlocfilehash: 41883e00955cf5f39f4420fb10ead1be2e131a77
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117151"
---
# <a name="set-the-caller-id-for-a-user"></a>設定使用者的來電顯示
Microsoft 365 和 Office 365 中的電話系統提供預設本機號碼，即使用者指派的電話號碼。 您可以變更或封鎖本機號碼 (呼叫線識別碼) 使用者。 您可以進一步瞭解如何在組織中使用本機號碼，方法為 [：如何在](how-can-caller-id-be-used-in-your-organization.md)貴組織中使用本機號碼。
  
> [!TIP]
> 您目前無法封鎖商務用 Skype Online 中的來電。 
  
您可以變更一些設定：
  
> [!NOTE]
> 這 **不適用於** 使用 Lync 或商務用 Skype Server 的內部部署組織。
  
- **變更他們的外發本機號碼** 您可以將使用者的本機號碼取代為另一個電話號碼，預設為使用者的電話號碼。 例如，您可以變更使用者的本機號碼，將使用者的電話號碼變更為公司的主要電話號碼，或將使用者的電話線識別碼從電話號碼變更為法務部門的主要電話號碼。 您可以將通話 ID 號碼變更為 **任何線上服務** 號碼 (或免付費) 。
    
    > [!NOTE]
    > 如果您想要使用 Service  _參數，_ 您必須指定有效的服務號碼。
  
- **封鎖他們的外發本機號碼** 您可以封鎖外寄本機號碼，防止在使用者的外寄 PSTN 通話中送出。 這麼做會封鎖他們的電話號碼，不會顯示在被通話者的電話上。
    
- **封鎖本機號碼** 您可以封鎖使用者接收任何傳入 PSTN 通話的本機號碼。
    
> [!IMPORTANT]
> 緊急電話一定會將使用者的電話號碼 (來電) 。 
  
根據預設，所有這些本機號碼設定 **都已關閉**。 這表示當使用者撥打 PSTN 電話時，可以看到商務用 Skype Online 使用者的電話號碼。
  
若要深入瞭解這些設定，以及如何使用這些設定，請前往如何在貴組織中 [使用本機號碼](how-can-caller-id-be-used-in-your-organization.md)。
  
## <a name="set-your-caller-id-policy-settings"></a>設定本機號碼策略設定

> [!NOTE]
> 針對商務用 Skype Online 中所有的本機號碼設定，您必須使用 Windows PowerShell，而且您不得使用 **商務用 Skype 系統管理中心**。  
  
### <a name="start-powershell"></a>啟動 PowerShell

- 開啟 Windows PowerShell 命令提示符，然後執行下列命令：

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a>查看貴組織中所有的本機號碼策略設定

- 若要在貴組織中查看所有本機號碼策略設定，請執行：

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  請參閱 [Get-CsCallingLineIdentity 的更多範例和詳細資料](/powershell/module/skype/Get-CsCallingLineIdentity)。
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a>為貴組織建立新的本機號碼策略


- 若要建立將本機號碼設定為匿名的新本機號碼策略，請執行：
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > 在所有的情況下，「服務編號」欄位不應包含初始的「+」。

  請參閱 [New-CsCallingLineIdentity 的更多範例和詳細資料](/powershell/module/skype/New-CsCallingLineIdentity)。
    
- 若要將您建立的新原則適用于 Amos Marble，請執行：
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  請參閱 [Grant-CsCallingLineIdentity Cmdlet](/powershell/module/skype/Grant-CsCallingLineIdentity) 上的更多資訊。
    
如果您已經建立原則，您可以使用 [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) Cmdlet 對現有原則進行變更，然後使用 [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) Cmdlet 將設定套用給使用者。
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a>設定以封鎖本機號碼

- 若要封鎖本機號碼，請執行：
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  請參閱 [Set-CsCallingLineIdentity 的更多範例和詳細資料](/powershell/module/skype/Set-CsCallingLineIdentity)。
    
- 若要將您建立的策略設定適用于貴組織的使用者，請執行：
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    請參閱 [Grant-CsCallingLineIdentity Cmdlet](/powershell/module/skype/Grant-CsCallingLineIdentity) 上的更多資訊。
    
### <a name="remove-a-caller-id-policy"></a>移除本機號碼策略

若要從貴組織移除策略，請執行：
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
若要從使用者移除策略，請執行：
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>想要進一瞭解 Windows PowerShell 嗎？

- Windows PowerShell 就是管理使用者，以及允許或不允許使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365 和商務用 Skype Online，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [Windows PowerShell 與 Lync Online 的簡介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [您可能會想要使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的六個原因](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell 比使用 Microsoft 365 系統管理中心在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。 請從下列主題瞭解這些優點：
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [使用 Windows PowerShell 執行常見的商務用 Skype Online 管理工作](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  
 ## <a name="related-topics"></a>相關主題
[移轉電話號碼的常見問題](./phone-number-calling-plans/port-order-overview.md)

[用於通話方案的各種電話號碼](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)

[深入了解通話線路識別碼和來電方名稱](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[緊急通話條款及條件](./emergency-calling-terms-and-conditions.md)

[商務用 Skype Online：緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
