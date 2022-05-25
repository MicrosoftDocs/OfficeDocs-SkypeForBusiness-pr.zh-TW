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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Licensing
description: '瞭解如何指派商務用 Skype電話系統、音訊會議、通話方案和通訊點數的授權。 '
ms.openlocfilehash: 6917b3d47f29c10bea8b7695cfa69ace60609393
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671819"
---
# <a name="assign-skype-for-business-licenses"></a>指派商務用 Skype 授權

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

本文提供有關指派授權給使用者的相關秘訣，例如音訊會議、電話系統和通話方案等功能。 它也提供大量指派授權的腳本。

> [!IMPORTANT]
> 如需您需要購買哪些授權以及 **購買方式** 的相關資訊，請參閱 [商務用 Skype附加](skype-for-business-and-microsoft-teams-add-on-licensing.md)元件授權，這些資訊會根據您的Microsoft 365或Office 365方案而定，讓使用者取得音訊會議、免付費電話號碼，以及撥打公司外部電話號碼的能力。


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>電話系統和通話方案：指派授權的提示和腳本

指派音訊會議、電話系統和通話方案授權之前必須知道的事項

- **使用混合式使用者的內部部署 PSTN 連線嗎？** 若是如此，您只需要指派 **電話系統** 授權。 您 **不應該指** 派通話方案。

- **指派授權後的延遲**：由於Microsoft 365或Office 365與 商務用 Skype Online 之間的延遲，在您指派授權之後，使用者最多可能需要 24 小時才能獲得指派通話方案。 如果 24 小時之後使用者未獲指派通話方案，請[連絡商務產品的支援人員 - 管理員說明]](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。

- **錯誤訊息**：如果您尚未購買正確的授權數目，您會收到錯誤訊息。 如果您需要購買更多通話方案授權，請選擇 [ **購買更多]**。
    
- **後續步驟**：將通話方案授權指派給使用者之後，您必須為組織取得電話號碼，然後將這些號碼指派給組織中的人員。 如需逐步指示，請參閱 [設定通話方案](/microsoftteams/set-up-calling-plans)。
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>如何指派電話系統和通話方案授權給一個使用者

這些步驟與指派Microsoft 365或Office 365授權相同。 請參閱[指派或移除商務用 Microsoft 365 的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>如何大量指派電話系統和通話方案授權

1. 安裝 **適用于 IT 專業人員 RTW 的 Microsoft Online Services Sign-In小幫手**。 沒有安裝模組嗎？ 請參閱 [Microsoft Online Services Sign-In IT 專業人員小幫手 RTW](https://go.microsoft.com/fwlink/?LinkId=625123) 以下載。

2. 安裝 **Windows Azure Active Directory模組。** 沒有安裝模組嗎？ 如需下載指示和 Cmdlet 語法，請參閱[使用 Windows PowerShell 管理 Azure AD](/previous-versions/azure/jj151815(v=azure.100))。

3. 安裝模組之後，請使用Windows PowerShell命令提示字元和下列語法，將授權指派給使用者：

   此範例會指派 **Enterprise E3 授權** 以及 **電話系統** 和 **國內通話方案** 授權。

   腳本中的授權名稱或產品名稱會列在斜體文字中 (在範例) 之後，查看 **用於腳本的電話系統和通話方案產品名稱或 SKU**。

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>用於腳本的電話系統和通話方案產品名稱或 SKU

|**產品名稱**|**SKU 元件名稱**|
|:-----|:-----|
|Enterprise E5 (與 電話系統)   <br/> |ENTERPRISEPREMIUM  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|商務用 Skype Online 獨立方案 2  <br/> |MCOSTANDARD  <br/> |
|電話系統  <br/> |MCOEV  <br/> |
|國際通話方案  <br/> |MCOPSTN2  <br/> |
|國內通話方案 (3000 分鐘/1200 分鐘歐盟方案)   <br/> |MCOPSTN1  <br/> |
|國內通話方案 (120 分鐘通話方案)   <br/> |MCOPSTN5  <br/> |
|國內通話方案 (240 分鐘通話方案)   <br/> |MCOPSTN6  <br/> |
|通訊點數  <br/> |MCOPSTNC  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>音訊會議：指派授權的提示和腳本

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>指派音訊會議授權之前必須知道的事項

- **協力廠商音訊會議提供者**：如果有人已設定使用協力廠商音訊會議提供者，當您指派 **音訊會議** 授權給他們時，他們會被變更為使用 Microsoft 做為音訊會議提供者。 您可以將其變更回協力廠商提供者。

- 後續步驟：指派 **音訊會議** 授權之後，您需要指派音訊會議提供者。 請參閱 [指派 Microsoft 作為音訊會議提供者]。

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>如何指派音訊會議授權給一個使用者

這些步驟與指派Microsoft 365或Office 365授權相同。 請參閱[指派或移除商務用 Microsoft 365 的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>如何大量指派音訊會議授權

1. 下載並安裝 [Microsoft Online Services Sign-In適用于 IT 專業人員的助理 RTW](https://go.microsoft.com/fwlink/?LinkId=625123)。

2. 下載並安裝 **Windows Azure Active Directory模組。** 如需下載指示和 Cmdlet 語法，請參閱[使用 Windows PowerShell 管理 Azure AD](/previous-versions/azure/jj151815(v=azure.100))。

   安裝模組之後，請使用Windows PowerShell命令提示字元和下列語法，將授權指派給使用者：

   腳本中的授權名稱或產品名稱會以斜體文字列出。 請[參閱音訊會議用於腳本處理所有產品名稱的產品名稱或 SKU](assign-skype-for-business-and-microsoft-teams-licenses.md#sku)。

   此範例會指派 Enterprise E3 授權以及音訊會議授權。

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>音訊會議用於腳本的產品名稱或 SKU
<a name="sku"> </a>

|**產品名稱**|**SKU 元件名稱**|
|:-----|:-----|
|音訊會議  <br/> |MCOMEETADV  <br/> |
|商務用 Skype Online 獨立方案 2  <br/> |MCOSTANDARD  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E5 (而不需音訊會議)   <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|Enterprise具有 音訊會議) 的 E5 (  <br/> |ENTERPRISEPREMIUM  <br/> |

## <a name="communications-credits"></a>通訊點數

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>指派通訊點數授權之前必須知道的事項

- **Enterprise E5 客戶**：即使您的使用者獲指派 Enterprise E5 授權，我們仍建議您指派 **通訊點數** 授權給他們。
    
- **後續步驟**：指派這些授權之後，您必須為組織取得電話號碼，然後將這些號碼指派給組織中的人員。 如需逐步指示，請參閱 [設定通話方案](/microsoftteams/set-up-calling-plans)。
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>如何指派通訊點數授權給一個使用者

這些步驟與指派Microsoft 365或Office 365授權相同。 請參閱[指派或移除商務用 Microsoft 365 的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>如何大量指派通訊點數授權

請參閱指派 **音訊會議** 授權的範例腳本。 使用指派 **通訊點數** 授權的資訊來更新。

## <a name="related-topics"></a>相關主題
  
[設定通話方案](/microsoftteams/set-up-calling-plans)
  
[加值和管理通訊點數](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
