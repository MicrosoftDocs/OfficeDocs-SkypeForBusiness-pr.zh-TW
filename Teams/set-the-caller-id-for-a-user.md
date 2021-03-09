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
description: 瞭解 Microsoft 365 和 Office 365 預設本機號碼 (使用者指派的電話號碼) 也稱為電話線路識別碼。 您可以變更或封鎖使用者的本機號碼。
ms.openlocfilehash: 1cc6221c0f4ca1642cc9422ed81e0e07ae1bfc91
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569415"
---
# <a name="set-the-caller-id-for-a-user"></a>設定使用者的來電顯示
Microsoft 365 和 Office 365 的電話系統提供預設本機號碼，即使用者指派的電話號碼。 您可以變更或封鎖本機號碼 (呼叫行識別碼) 使用者。 您可以進一步瞭解如何在組織中使用本機號碼，方法為了解如何在組織中使用來電 [顯示](how-can-caller-id-be-used-in-your-organization.md)。
  
> [!TIP]
> 您目前無法封鎖商務用 Skype Online 中的來電。 
  
您可以變更一些設定：
  
> [!NOTE]
> 這 **適用于** 使用 Lync 或商務用 Skype Server 的內部部署組織。
  
- **變更他們的撥出本機號碼** 您可以使用另一個電話號碼取代使用者的本機號碼功能 ，預設為使用者的電話號碼。 例如，您可以變更使用者的本機號碼，從他們的電話號碼變更為公司的主要電話號碼，或將使用者的電話線路識別碼從電話號碼變更為法務部門的主要電話號碼。 您可以將通話識別碼號碼變更為 **任何線上服務** 號碼 (或免付費電話號碼) 。
    
    > [!NOTE]
    > 如果您想要使用服務參數，您必須指定有效的服務編號。
  
- **封鎖他們的外發本機號碼** 您可以封鎖撥出的本機號碼，防止在使用者的外寄 PSTN 通話中送出。 這麼做會禁止對方的電話號碼顯示在受話者手機上。
    
- **封鎖本機號碼** 您可以封鎖使用者無法接收任何 PSTN 來電的本機號碼。
    
> [!IMPORTANT]
> 緊急電話一定會將使用者的電話號碼 (本機號碼) 。 
  
根據預設，這些本機號碼設定全部 **為關閉**。 這表示當使用者撥打 PSTN 電話時，可以看到商務用 Skype Online 使用者的電話號碼。
  
若要深入瞭解這些設定，以及如何使用這些設定，請前往組織中如何使用來電 [顯示](how-can-caller-id-be-used-in-your-organization.md)。
  
## <a name="set-your-caller-id-policy-settings"></a>設定您的本機號碼政策設定

> [!NOTE]
> 針對商務用 Skype Online 中所有的本機號碼設定，您必須使用 Windows PowerShell，而且無法使用商務用 **Skype 系統管理中心**。  
  
### <a name="start-powershell"></a>啟動 PowerShell

- 開啟 Windows PowerShell 命令提示程式，然後執行下列命令：

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a>查看貴組織的所有本機號碼政策設定

- 若要在組織中查看所有本機號碼政策設定，請執行：

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  查看 [Get-CsCallingLineIdentity 的更多範例和詳細資料](https://technet.microsoft.com/library/mt793856.aspx)。
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a>為貴組織建立新的本機號碼政策


- 若要建立將本機號碼設定為匿名的新本機號碼政策，請執行：
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > 在所有案例中，「服務編號」欄位不應包含初始 「+」。

  查看 [New-CsCallingLineIdentity 的更多範例和詳細資料](https://technet.microsoft.com/library/mt793855.aspx)。
    
- 若要將您建立的新原則適用于 Amos Marble，請執行：
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  在 [Grant-CsCallingLineIdentity Cmdlet](https://technet.microsoft.com/library/mt793857.aspx) 上查看更多。
    
如果您已經建立原則，您可以使用 [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) Cmdlet 對現有原則進行變更，然後使用 [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) Cmdlet 將設定套用至您的使用者。
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a>設定讓本機號碼被封鎖

- 若要封鎖本機號碼，請執行：
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  查看 [Set-CsCallingLineIdentity 的更多範例和詳細資料](https://technet.microsoft.com/library/mt793854.aspx)。
    
- 若要將您建立原則設定適用于貴組織的使用者，請執行：
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    在 [Grant-CsCallingLineIdentity Cmdlet](https://technet.microsoft.com/library/mt793857.aspx) 上查看更多。
    
### <a name="remove-a-caller-id-policy"></a>移除本機號碼政策

若要從組織移除一個策略，請執行：
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
若要從使用者移除策略，請執行：
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>想要進一瞭解更多 Windows PowerShell 嗎？

- Windows PowerShell 就是管理使用者，以及允許或禁止使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單點系統管理來管理 Microsoft 365 或 Office 365 和商務用 Skype Online，當您有多個任務作作時，可以簡化您的日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [為何要使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的六個原因](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell 在速度、簡易性和生產力方面有許多優點，比只使用 Microsoft 365 系統管理中心有許多優點，例如當您一次為許多使用者進行設定變更時。 在下列主題中瞭解這些優點：
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 執行一般商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a>相關主題
[移轉電話號碼的常見問題](/microsoftteams/transferring-phone-numbers-common-questions)

[用於通話方案的電話號碼類型](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)

[深入了解通話線路識別碼和來電方名稱](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[緊急通話條款及條件](/microsoftteams/emergency-calling-terms-and-conditions)

[商務用 Skype Online：緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
 
