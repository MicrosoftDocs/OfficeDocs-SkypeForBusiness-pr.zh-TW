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
f1keywords: None
ms.custom:
- Licensing
description: '瞭解如何為手機系統、音訊會議、通話方案和通訊點數指派商務用 Skype 授權。 '
ms.openlocfilehash: 997cffce5b98ed992371a0f43e701b2efc1ae128
ms.sourcegitcommit: 6d5f09acdcdc8d5a36f7ac785349209e7496f17d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/07/2019
ms.locfileid: "37642249"
---
# <a name="assign-skype-for-business-licenses"></a>指派商務用 Skype 授權

本文提供有關指派授權給使用者的秘訣，例如音訊會議、電話系統和通話方案等功能。 它也提供大量指派授權的腳本。

> [!IMPORTANT]
> 請參閱[商務用 Skype 附加元件授權](skype-for-business-and-microsoft-teams-add-on-licensing.md)，以取得您需要購買哪些授權，以及**如何購買**它們（視您的 Office 365 方案而定），讓使用者取得音訊會議、免付費電話號碼，以及撥打電話號碼以外的功能您的公司。


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>電話系統與通話方案：指派授權的秘訣與腳本

指派音訊會議、電話系統和通話方案授權前需要注意的事項

- **針對混合式使用者使用內部部署 PSTN 連線能力？** 如果是這樣，您只需要指派**電話系統**授權即可。 您**不**應該指派通話方案。

- **指派授權之後的延遲**：由於 Office 365 與商務用 Skype Online 之間的延遲，在指派授權之後，可能需要長達24小時才能獲指派通話方案。 如果在24小時之後，使用者並未獲指派通話方案，請[與商務用支援人員聯繫，以取得系統管理協助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。

- **錯誤訊息**：如果您尚未購買正確數量的授權，您會收到錯誤訊息。 如果您需要購買更多通話方案授權，請選擇 [**購買更多**]。
    
- **後續步驟**：將通話方案授權指派給使用者之後，您將需要取得貴組織的電話號碼，然後將這些號碼指派給組織中的人員。 如需逐步指示，請參閱[設定通話方案](/microsoftteams/set-up-calling-plans)。
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>如何將電話系統和通話方案授權指派給一個使用者

這些步驟與指派 Office 365 授權是一樣的。 請參閱[指派或移除商務用 Office 365 的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>如何大量指派電話系統和通話方案授權

1. 安裝**適用于 IT 專業人員的 Microsoft Online Services 登入**小幫手 RTW。 沒有安裝該模組嗎？ 請參閱[適用于 IT 專業人員的 Microsoft Online Services 登入](https://go.microsoft.com/fwlink/?LinkId=625123)小幫手 RTW 以下載它。

2. 安裝**Windows Azure Active Directory 模組。** 沒有安裝該模組嗎？ 如需下載指示與 Cmdlet 語法，請參閱[使用 Windows PowerShell 管理 AZURE AD](https://go.microsoft.com/fwlink/p/?LinkId=320628) 。

3. 安裝模組後，請使用 Windows PowerShell 命令提示字元及下列語法，將授權指派給您的使用者：

   這個範例會指派**企業版 E3 授權**，以及**手機系統**和**國內通話方案**授權。

   腳本中的授權或產品名稱的名稱會以斜體文字列出（請參閱在這個範例之後，請參閱**電話系統和通話方案產品名稱或 sku 用於腳本**）。

   ```
   #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>用於腳本的電話系統和通話方案產品名稱或 Sku

|**產品名稱**|**SKU 元件名稱**|
|:-----|:-----|
|企業版 E5 （含電話系統）  <br/> |ENTERPRISEPREMIUM  <br/> |
|企業版 E3  <br/> |ENTERPRISEPACK  <br/> |
|企業版 E1  <br/> |STANDARDPACK  <br/> |
|商務用 Skype Online 獨立方案2  <br/> |MCOSTANDARD  <br/> |
|電話系統  <br/> |MCOEV  <br/> |
|國際通話方案  <br/> |MCOPSTN2  <br/> |
|國內通話方案（3000美元/1200 分歐盟方案）  <br/> |MCOPSTN1  <br/> |
|國內通話方案（120最小通話方案）  <br/> |MCOPSTN5  <br/> |
|國內通話方案（240最小通話方案）  <br/> |MCOPSTN6  <br/> |
|通訊點數  <br/> |MCOPSTNC  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>音訊會議：指派授權的秘訣與腳本

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>指派音訊會議授權前需要注意的事項

- **協力廠商音訊會議提供者**：如果某人已設定為使用協力廠商音訊會議提供者，當您指派**音訊會議**授權時，系統會將其變更為使用 Microsoft 作為音訊會議服務. 您可以將它們變更回協力廠商提供者。

- 後續步驟：指派**音訊會議**授權之後，您需要指派音訊會議提供者。 請參閱 [將 Microsoft 指派為音訊會議提供者]。

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>如何將音訊會議授權指派給一名使用者

這些步驟與指派 Office 365 授權是一樣的。 請參閱[指派或移除商務用 Office 365 的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>如何大量指派音訊會議授權

1. 下載並安裝[適用于 IT 專業人員的 Microsoft Online Services 登入](https://go.microsoft.com/fwlink/?LinkId=625123)小幫手 RTW。

2. 下載並安裝**Windows Azure Active Directory 模組。** 如需下載指示與 Cmdlet 語法，請參閱[使用 Windows PowerShell 管理 AZURE AD](https://go.microsoft.com/fwlink/p/?LinkId=320628) 。

    安裝模組後，請使用 Windows PowerShell 命令提示字元及下列語法，將授權指派給您的使用者：

    腳本中授權或產品名稱的名稱會以斜體文字列出。 請參閱[音訊會議產品名稱或 sku，以供](assign-skype-for-business-and-microsoft-teams-licenses.md#sku)所有產品名稱的腳本使用。

    這個範例會指派企業版 E3 授權以及音訊會議授權。

```
#Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>用於腳本的音訊會議產品名稱或 Sku
<a name="sku"> </a>

|**產品名稱**|**SKU 元件名稱**|
|:-----|:-----|
|音訊會議  <br/> |MCOMEETADV  <br/> |
|商務用 Skype Online 獨立方案2  <br/> |MCOSTANDARD  <br/> |
|企業版 E1  <br/> |STANDARDPACK  <br/> |
|企業版 E3  <br/> |ENTERPRISEPACK  <br/> |
|企業版 E5 （不含音訊會議）  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|企業版 E5 （含音訊會議）  <br/> |ENTERPRISEPREMIUM  <br/> |

## <a name="communications-credits"></a>通訊點數

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>指派通訊點數授權前需要注意的事項

- **企業版 E5 客戶**：即使您的使用者已獲指派企業版 e5 授權，我們仍建議您指派其**通訊信用額度**授權。
    
- **後續步驟**：在您指派這些授權之後，您必須取得貴組織的電話號碼，然後將這些號碼指派給貴組織中的人員。 如需逐步指示，請參閱[設定通話方案](/microsoftteams/set-up-calling-plans)。
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>如何指派通訊點數授權給一名使用者

這些步驟與指派 Office 365 授權是一樣的。 請參閱[指派或移除商務用 Office 365 的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>如何大量指派通訊點數授權

請參閱指派**音訊會議**授權的範例腳本。 使用指派**通訊點數**授權的資訊來更新它。

## <a name="related-topics"></a>相關主題
  
[設定通話方案](/microsoftteams/set-up-calling-plans)
  
[新增基金及管理通訊點數](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
