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
description: 瞭解 Microsoft 365 和 Office 365 預設本機號碼 (使用者指派的電話號碼) ，也稱為呼叫線路 ID。 您可以變更或封鎖使用者的本機號碼。
ms.openlocfilehash: ff8355b9435d0a21c032ee90b442884c0319221c
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814322"
---
# <a name="set-the-caller-id-for-a-user"></a>設定使用者的來電顯示
Microsoft 365 和 Office 365 中的電話系統提供使用者指派電話號碼的預設本機號碼。 您可以變更或封鎖本機號碼 (也稱為使用者的通話行識別碼) 。 若要深入瞭解如何在 [您的組織](how-can-caller-id-be-used-in-your-organization.md)中使用本機號碼，請參閱如何在貴組織中使用本機號碼。
  
> [!TIP]
> 您無法在商務用 Skype Online 中封鎖目前的來電。 
  
您可以變更以下設定：
  
> [!NOTE]
> 這 **不適** 用於使用 Lync 或商務用 Skype Server 的內部部署組織。
  
- **變更其外寄來電** 顯示您可以取代使用者的本機號碼，預設為其電話號碼，也就是其他電話號碼。 例如，您可以將使用者的本機號碼，從其電話號碼變更為公司的主要電話號碼，或將使用者的電話撥打電話號碼從他們的電話號碼變更為法律部門的主要電話號碼。 您可以將通話 ID 號碼變更為任何線上 **服務** 號碼 (付費或免費付費) 。
    
    > [!NOTE]
    > 如果您想要使用  _服務_ 參數，您必須指定有效的服務號碼。
  
- **封鎖其輸出來電者識別碼** 您可以封鎖外寄本機號碼，不會在使用者的出局 PSTN 通話中傳送出去。 這樣做會封鎖電話號碼無法在通話者的電話上顯示。
    
- **封鎖來電者識別碼** 您可以封鎖使用者在任何打入的 PSTN 電話上接收本機號碼的號碼。
    
> [!IMPORTANT]
> 緊急通話總是會將使用者的電話號碼傳送 (本機號碼) 。 
  
根據預設，所有的本機號碼設定都是 **關閉**的。 這表示當使用者撥打電話給 PSTN 手機時，可以看到商務用 Skype Online 使用者的電話號碼。
  
若要深入瞭解這些設定，以及如何使用這些設定，請移至 [如何在您的組織中使用來電](how-can-caller-id-be-used-in-your-organization.md)顯示。
  
## <a name="set-your-caller-id-policy-settings"></a>設定您的本機號碼原則設定

> [!NOTE]
> 針對商務用 Skype Online 中的所有本機號碼設定，您必須使用 Windows PowerShell，而且您 **無法使用商務用** **Skype 系統管理中心**。 
  
### <a name="verify-and-start-windows-powershell"></a>驗證並啟動 Windows PowerShell

- **檢查您執行的是 Windows PowerShell 版本3.0 或更高版本**
    
1. 若要確認您執行的是版本3.0 或更高版本： [**開始] 功能表**  >  **Windows PowerShell**。
    
2. 在**Windows PowerShell**視窗中輸入 [_取得主機_]，以檢查版本。
    
3. 如果您沒有版本3.0 或更高版本，您需要下載並安裝 Windows PowerShell 更新。 請參閱 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) ，以下載並更新 Windows PowerShell 至版本4.0。 出現提示時，請重新開機電腦。
    
4. 您也需要安裝適用于商務用 Skype Online 的 Windows PowerShell 模組，這可讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組只受64位電腦支援，可從 [適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。 如果出現提示，請重新開機電腦。
    
    如果您需要進一步瞭解，請參閱 [在單一 Windows PowerShell 視窗中連線至所有 Microsoft 365 或 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx)。
    
- **啟動 Windows PowerShell 會話**
    
1. 從 [**開始] 功能表**中的 [  >  **Windows PowerShell**]。
    
2. 在 **Windows PowerShell** 視窗中，執行下列動作以連線至您的 Microsoft 365 或 Office 365：
    
   > [!NOTE]
   >
   > 商務用 Skype Online 連接器目前是最新團隊 PowerShell 模組的一部分。
   > 如果您使用的是最新的 [團隊 PowerShell 公開發行](https://www.powershellgallery.com/packages/MicrosoftTeams/)，就不需要安裝商務用 Skype Online 連接器。
   ```PowerShell
    Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

如果您需要啟動 Windows PowerShell 的詳細資訊，請參閱 [在單一 Windows powershell 視窗中連線至所有 Microsoft 365 或 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx) ，或 [設定您的 windows powershell 電腦](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a>查看貴組織中的所有本機號碼原則設定

- 若要查看貴組織中所有本機號碼原則設定，請執行：

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  如需 [CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx)的詳細資訊，請參閱更多範例和詳細資料。
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a>為您的組織建立新的本機號碼原則


- 若要建立將本機號碼設定為 anonymous 的新本機號碼原則，請執行：
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > 在任何情況下，「服務編號」欄位不應該包含初始 "+"。

  如需 [新的 CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx)，請參閱更多範例和詳細資料。
    
- 若要將您建立的新原則套用至 Amos 大理石，請執行：
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  如需 [CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) Cmdlet 的詳細資訊，請參閱。
    
如果您已建立原則，您可以使用 [CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) Cmdlet 來變更現有的原則，然後使用 [授與 CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) Cmdlet 將設定套用到您的使用者。
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a>將它設定為會封鎖本機號碼來電

- 若要封鎖來電呼叫者識別碼，請執行：
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  如需 [設定 CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx)的更多範例和詳細資料，請參閱。
    
- 若要將您建立的原則設定套用至貴組織中的使用者，請執行：
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    如需 [CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) Cmdlet 的詳細資訊，請參閱。
    
### <a name="remove-a-caller-id-policy"></a>移除本機號碼原則

若要移除貴組織的原則，請執行：
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
若要移除使用者的原則，請執行：
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>想要深入瞭解 Windows PowerShell 嗎？

- Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。 在 Windows PowerShell 中，您可以使用單一管理點管理 Microsoft 365 或 Office 365 及商務用 Skype Online，當您有多個工作需要執行時，可簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [您可能會想要使用 Windows PowerShell 來管理 Microsoft 365 或 Office 365 的六個原因](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell 在速度、簡潔性和生產率上都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者設定變更時。 請參閱下列主題，瞭解這些優點：
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a>相關主題
[移轉電話號碼的常見問題](/microsoftteams/transferring-phone-numbers-common-questions)

[通話方案所用的不同類型的電話號碼](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)

[深入了解通話線路識別碼和來電方名稱](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[緊急通話條款及條件](/microsoftteams/emergency-calling-terms-and-conditions)

[商務用 Skype Online：緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
 
