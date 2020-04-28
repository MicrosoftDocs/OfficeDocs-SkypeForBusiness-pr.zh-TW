---
title: 指派 Teams 授權
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: 瞭解如何指派音訊會議、電話系統和通話方案等功能的授權。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 55d85aae6540c6b5888be848ad08d686bd0da2b1
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905065"
---
# <a name="assign-microsoft-teams-licenses"></a>指派 Microsoft 團隊授權

您可以將授權指派給使用者，以取得音訊會議、電話系統和通話方案等功能。 本文說明如何大量為個別使用者新增這些授權。 

> [!IMPORTANT]
> 請參閱[Microsoft 團隊附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)，以取得您需要購買哪些授權，以及如何購買它們（視您的 Office 365 方案而定），讓使用者可以取得音訊會議、免付費電話號碼，以及撥打電話給企業外部的電話號碼。

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>電話系統與通話方案：指派授權的秘訣與腳本

以下是在指派音訊會議、電話系統和通話方案授權前，您需要知道的事項。

- **針對混合式使用者使用內部部署 PSTN 連線能力？** 如果是這樣，您只需要指派電話系統授權即可。 您不應該指派通話方案。

- **指派授權之後的延遲**：由於 Office 365 與 Microsoft 團隊之間的延遲，在指派授權之後，可能需要長達24小時才能指派通話方案。 如果在24小時之後，使用者並未獲指派通話方案，請[與商務用支援人員聯繫，以取得系統管理協助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。

- **錯誤訊息**：如果您尚未購買正確數量的授權，您會收到錯誤訊息。 如果您需要購買更多通話方案授權，請選擇 [**購買更多**]。

- **後續步驟**：將通話方案授權指派給使用者之後，您將需要取得貴組織的電話號碼，然後將這些號碼指派給組織中的人員。 如需逐步指示，請參閱[設定通話方案](set-up-calling-plans.md)。

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a>指派電話系統和通話方案授權給一名使用者

這些步驟與指派 Office 365 授權是一樣的。 請參閱[指派或移除商務用 Office 365 的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a>大量指派電話系統和通話方案授權

1. 安裝適用于 IT 專業人員的 Microsoft Online Services 登入小幫手 RTW。 沒有安裝該模組嗎？ 請參閱[適用于 IT 專業人員的 Microsoft Online Services 登入](https://go.microsoft.com/fwlink/?LinkId=625123)小幫手 RTW 以下載它。

2. 安裝 Windows Azure Active Directory 模組。 沒有安裝該模組嗎？ 如需下載指示與 Cmdlet 語法，請參閱[使用 Windows PowerShell 管理 AZURE AD](https://go.microsoft.com/fwlink/p/?LinkId=320628) 。

3. 安裝模組後，請使用 Windows PowerShell 命令提示字元及下列語法，將授權指派給您的使用者：

這個範例會指派企業版 E3 授權，以及手機系統和國內通話方案授權。

腳本中的授權或產品名稱的名稱會以斜體列出（請參閱在此範例之後，請參閱[電話系統和通話方案產品名稱或 sku 用於腳本](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting)）。

```powershell
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

## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>用於腳本的電話系統和通話方案產品名稱或 Sku

| 產品名稱 | SKU 元件名稱 |
|--------------|---------------|
| 企業版 E5 （含電話系統） | ENTERPRISEPREMIUM |
| 企業版 E3 | ENTERPRISEPACK | 
| 企業版 E1 | STANDARDPACK | 
| 電話系統 | MCOEV |
| 國內 & 國際通話方案 | MCOPSTN2 |
| 國內通話方案（每個使用者/每個月的每個使用者/每個月的每個月的3000分鐘1200，歐盟國家/地區的每個使用者/月份） | MCOPSTN1 |
| 國內通話方案（每個國家/地區每個使用者/月的120分鐘） </br>*注意：此方案不適用於我們*。 | MCOPSTN5 |
| 國內通話方案（每個國家/地區每個使用者/月的240分鐘） </br>*注意：此方案不適用於我們*。 | MCOPSTN6 |
| 通訊點數 | MCOPSTNPP | 

## <a name="assign-an-audio-conferencing-license-to-one-user"></a>將音訊會議授權指派給一名使用者

這些步驟與指派 Office 365 授權是一樣的。 請參閱[指派或移除商務用 Office 365 的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

## <a name="assign-audio-conferencing-licenses-in-bulk"></a>大量指派音訊會議授權

1. 下載並安裝[適用于 IT 專業人員的 Microsoft Online Services 登入](https://go.microsoft.com/fwlink/?LinkId=625123)小幫手 RTW。

2. 下載並安裝 Windows Azure Active Directory 模組。 如需下載指示與 Cmdlet 語法，請參閱[使用 Windows PowerShell 管理 AZURE AD](https://go.microsoft.com/fwlink/p/?LinkId=320628) 。

安裝模組後，請使用 Windows PowerShell 命令提示字元及下列語法，將授權指派給您的使用者：

腳本中授權或產品名稱的名稱會以斜體列出。 請參閱[音訊會議產品名稱或 sku，以供](#audio-conferencing-product-names-or-skus-used-for-scripting)所有產品名稱的腳本使用。

這個範例會指派企業版 E3 授權以及音訊會議授權。

```powershell
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

## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>用於腳本的音訊會議產品名稱或 SKU

| 產品名稱 | SKU 元件名稱 |
|--------------|---------------|
| 音訊會議（訂閱） | MCOMEETADV | 
| 每分鐘付費語音會議（隨您的付費）</br>*注意：需要設定並啟用通訊點數*。 |    MCOMEETACPEA |
| 企業版 E1 | STANDARDPACK | 
| 企業版 E3 | ENTERPRISEPACK |
| 企業版 E5 （不含音訊會議） |     ENTERPRISEPREMIUM_NOPSTNCONF |
| 企業版 E5 （含音訊會議） | ENTERPRISEPREMIUM |

##  <a name="communications-credits"></a>通訊點數

以下是在指派通訊信用權前，您需要知道的事項。

- **企業版 E5 客戶**：即使您的使用者已獲指派企業版 e5 授權，我們仍建議您指派其通訊信用額度授權。

- **後續步驟**：在您指派這些授權之後，您必須取得貴組織的電話號碼，然後將這些號碼指派給貴組織中的人員。 如需逐步指示，請參閱[設定通話方案](set-up-calling-plans.md)。

## <a name="assign-a-communications-credits-license-to-one-user"></a>指派通訊點數授權給一名使用者

這些步驟與指派 Office 365 授權是一樣的。 請參閱[指派或移除商務用 Office 365 的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

## <a name="assign-communications-credits-licenses-in-bulk"></a>大量指派通訊點數授權

請參閱指派音訊會議授權的範例腳本。 使用指派通訊點數授權的資訊來更新它。

## <a name="related-topics"></a>相關主題

[設定通話方案](set-up-calling-plans.md)
</br>
[加值和管理通訊點數](add-funds-and-manage-communications-credits.md)
