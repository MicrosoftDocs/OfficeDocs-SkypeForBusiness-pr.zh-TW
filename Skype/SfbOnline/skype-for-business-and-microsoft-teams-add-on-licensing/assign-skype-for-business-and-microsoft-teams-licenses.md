---
title: 指派商務用 Skype 授權
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Licensing
description: '瞭解如何為電話系統、音訊會議、通話方案及通訊信用額度指派商務用 Skype 授權。 '
ms.openlocfilehash: beb4fa46133aa7a09ce3d0de0a08392dbf2d2591
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106489"
---
# <a name="assign-skype-for-business-licenses"></a>指派商務用 Skype 授權

本文提供如何指派授權給使用者的秘訣，讓您使用音訊會議、電話系統及通話方案等功能。 它也提供大量指派授權腳本。

> [!IMPORTANT]
> 請參閱[商務](skype-for-business-and-microsoft-teams-add-on-licensing.md)用 Skype 附加元件授權，瞭解您需要購買哪些授權，以及如何購買授權，取決於您的 Microsoft 365 或 Office 365 方案，讓使用者取得音訊會議、免付費號碼，以及撥打公司外電話號碼的能力。


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>電話系統與通話方案：指派授權秘訣和腳本

指派音訊會議、電話系統及通話方案授權之前，您需要知道什麼

- **使用混合式使用者內部部署 PSTN 連接嗎？** 如果是這樣，您只需要指派電話 **系統** 授權。 您不應該 **指派** 通話方案。

- 指派授權後的延遲：由於 Microsoft 365 或 Office 365 與商務用 Skype Online 之間的延遲，指派授權後，使用者最多可能需要 24 小時才能獲得通話方案。 如果 24 小時後未指派使用者通話方案，請聯絡商務產品 [支援人員 - 系統管理協助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。

- **錯誤訊息**：如果您沒有購買正確的授權數量，就會收到錯誤訊息。 如果您需要購買更多通話方案授權，請選擇 購買 **更多**。
    
- **下一** 個步驟：將通話方案授權指派給使用者之後，您必須取得貴組織的電話號碼，然後將這些號碼指派給貴組織的人。 有關逐步指示，請參閱 [設定通話方案](/microsoftteams/set-up-calling-plans)。
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>如何將電話系統與通話方案授權指派給一個使用者

這些步驟與指派 Microsoft 365 或 Office 365 授權相同。 請參閱 [指派或移除商務用 Microsoft 365 授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>如何大量指派電話系統與通話方案授權

1. 安裝 **MICROSOFT Online Services Sign-In IT 專業人員 RTW 小幫手**。 沒有安裝模組嗎？ 請參閱 [Microsoft Online Services Sign-In IT 專業人員 RTW](https://go.microsoft.com/fwlink/?LinkId=625123) 小幫手來下載。

2. 安裝 **Windows Azure Active Directory 模組。** 沒有安裝模組嗎？ 請參閱 [使用 Windows PowerShell 管理 Azure AD，](/previous-versions/azure/jj151815(v=azure.100)) 以參閱下載指示和 Cmdlet 語法。

3. 安裝模組之後，請使用 Windows PowerShell 命令提示和下列語法來指派授權給使用者：

   此範例會指派 **企業版 E3 授權** ，以及電話 **系統** 與 **國內通話方案** 授權。

   腳本中的授權或產品名稱名稱會以斜體文字列出 (請參閱範例) 之後用於腳本的電話系統與通話方案產品名稱或 **SKus。**

   ```powershell
   #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.

   #Example of text file:
   #user1@domain.com
   #user2@domain.com

   #Import Module
   ipmo MSOnline
   #Authenticate to MSOLservice.
   Connect-MSOLService
   #File prompt to select the userlist txt file.
   [System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
   $OFD = New-Object System.Windows.Forms.OpenFileDialog
   $OFD.filter = "text files (*.*)| *.txt"
   $OFD.ShowDialog() | Out-Null
   $OFD.filename
   If ($OFD.filename -eq '')
   {
    Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
   }
   #Create a variable of all users.
   $users = Get-Content $OFD.filename
   #License each user in the $users variable.
   #Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and
   International Calling.
   for each ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
    }
   ```
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>電話系統與通話方案產品名稱或用於腳本的 SKUs

|**產品名稱**|**SKU 零件名稱**|
|:-----|:-----|
|企業版 E5 (電話系統)   <br/> |ENTERPRISEPREMIUM  <br/> |
|企業版 E3  <br/> |ENTERPRISEPACK  <br/> |
|企業版 E1  <br/> |STANDARDPACK  <br/> |
|商務用 Skype Online 獨立方案 2  <br/> |MCOSTANDARD  <br/> |
|電話系統  <br/> |MCOEV  <br/> |
|國際通話方案  <br/> |MCOPSTN2  <br/> |
|國內通話方案 (3000 分鐘美國 / 1200 分鐘的歐盟方案)   <br/> |MCOPSTN1  <br/> |
|國內通話方案 (120 分鐘的通話方案)   <br/> |MCOPSTN5  <br/> |
|國內通話方案 (240 分鐘的通話方案)   <br/> |MCOPSTN6  <br/> |
|通訊點數  <br/> |MCOPSTNC  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>音訊會議：指派授權秘訣和腳本

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>指派音訊會議授權之前，您需要知道什麼

- 協力廠商音訊會議提供者：如果有人已設定使用協力廠商音訊會議提供者，當您指派音訊會議授權給他們時，他們將會變更為使用 Microsoft 作為音訊會議提供者。 您可以將它們變更回協力廠商提供者。

- 下一個步驟：指派 **音訊會議授權** 之後，您需要指派音訊會議提供者。 請參閱 [將 Microsoft 指派為音訊會議提供者]。

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>如何將音訊會議授權指派給一個使用者

這些步驟與指派 Microsoft 365 或 Office 365 授權相同。 請參閱 [指派或移除商務用 Microsoft 365 授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>如何大量指派音訊會議授權

1. 下載並安裝 [Microsoft Online Services Sign-In IT 專業人員 RTW 小幫手](https://go.microsoft.com/fwlink/?LinkId=625123)。

2. 下載並安裝 **Windows Azure Active Directory 模組。** 請參閱[使用 Windows PowerShell 管理 Azure AD，](/previous-versions/azure/jj151815(v=azure.100)) 以參閱下載指示和 Cmdlet 語法。

    安裝模組之後，請使用 Windows PowerShell 命令提示和下列語法來指派授權給使用者：

    腳本中的授權或產品名稱名稱會以斜體文字列出。 請參閱 [音訊會議產品名稱或用於](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) 所有產品名稱之腳本的 SKUs。

    此範例會指派企業版 E3 授權以及音訊會議授權。

    ```powershell
    #Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.
    #Example of text file:
    #user1@domain.com
    #user2@domain.com

    #Import Module
    ipmo MSOnline

    #Authenticate to MSOLservice
    Connect-MSOLService
    #File prompt to select the userlist txt file
    [System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
      $OFD = New-Object System.Windows.Forms.OpenFileDialog
      $OFD.filter = "text files (*.*)| *.txt"
      $OFD.ShowDialog() | Out-Null
      $OFD.filename

    If ($OFD.filename -eq '')
    {
    Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
    }

    #Create a variable of all users
    $users = Get-Content $OFD.filename

    #License each user in the $users variable
    foreach ($user in $users)
        {
        Write-host "Assigning License: $user"
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOMEETADV " -ErrorAction SilentlyContinue
        }
    ```

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>音訊會議產品名稱或用於腳本的 SKUs
<a name="sku"> </a>

|**產品名稱**|**SKU 零件名稱**|
|:-----|:-----|
|音訊會議  <br/> |MCOMEETADV  <br/> |
|商務用 Skype Online 獨立方案 2  <br/> |MCOSTANDARD  <br/> |
|企業版 E1  <br/> |STANDARDPACK  <br/> |
|企業版 E3  <br/> |ENTERPRISEPACK  <br/> |
|企業版 E5 (沒有音訊會議)   <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|企業版 E5 (音訊會議)   <br/> |ENTERPRISEPREMIUM  <br/> |

## <a name="communications-credits"></a>通訊點數

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>指派通訊信用額度授權之前，您需要知道什麼

- **企業版 E5 客戶**：即使您的使用者已指派企業版 E5 授權，我們還是建議您指派通訊 **信用額度** 授權給他們。
    
- **下一** 個步驟：指派這些授權之後，您必須取得貴組織的電話號碼，然後將這些號碼指派給貴組織的人。 有關逐步指示，請參閱 [設定通話方案](/microsoftteams/set-up-calling-plans)。
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>如何將通訊信用額度授權指派給一個使用者

這些步驟與指派 Microsoft 365 或 Office 365 授權相同。 請參閱 [指派或移除商務用 Microsoft 365 授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>如何大量指派通訊信用額度授權

查看指派音訊會議授權範例 **腳本** 。 使用指派通訊信用額度授權的資訊 **進行更新** 。

## <a name="related-topics"></a>相關主題
  
[設定通話方案](/microsoftteams/set-up-calling-plans)
  
[加值和管理通訊點數](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
