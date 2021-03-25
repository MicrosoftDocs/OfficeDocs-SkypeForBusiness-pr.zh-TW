---
title: 指派 Teams 附加元件授權給使用者
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: 瞭解如何指派 Teams 附加元件授權給使用者，以使用音訊會議、電話系統及通話方案等功能。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 240672b125190492a036bc9dfa3f7a42070e8320
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116931"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>指派 Teams 附加元件授權給使用者

附加元件授權是特定 Teams 功能授權，例如音訊會議、電話系統及通話方案。 本文將說明如何將附加元件授權指派給個別使用者和大量大型使用者。

> [!NOTE]
> 請參閱 [Teams 附加元件授權](./microsoft-teams-add-on-licensing.md) ，以使用附加元件授權提供 Teams 功能。 您也可以根據您的方案) 找到您需要購買哪些授權以及如何購買授權 (的資訊，讓使用者能夠取得音訊會議、免付費號碼等功能，以及撥打組織外部電話號碼的功能。 決定要為使用者提供哪些功能之後，請指派授權給他們。

您可以使用 Microsoft 365 系統管理中心或 PowerShell 將授權指派給貴組織的使用者。 您必須是全域系統管理員或使用者管理系統管理員，才能管理授權。

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>指派電話系統、通話方案及通訊信用額度授權之前，您需要知道什麼

在您開始使用之前，請先檢查下列需求：

- 如果您使用的是內部部署公用交換電話網絡 (PSTN) 混合式使用者的) ，您只需要指派電話系統授權。 請勿指派通話方案授權。

- 由於 Microsoft 365 與 Microsoft Teams 之間的延遲，使用者最多可能需要 24 小時，才能在指派授權後指派通話方案。 如果使用者在 24 小時後未指派通話方案，請聯絡商務產品 [支援人員 - 系統管理協助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。

- 如果您沒有購買正確的授權數量，就會收到錯誤訊息。 如果您需要購買更多通話方案授權，請選擇購買更多方案的選項。

- 即使您的使用者獲派企業版 E5 授權，如果您想要撥打或接聽[](../what-are-communications-credits.md)PSTN 的通話，您仍然需要指派通訊信用額度授權給他們。

- 將通話方案或通訊信用額度授權指派給使用者之後，您必須取得貴組織的電話號碼，然後將這些號碼指派給使用者。 有關逐步指示，請參閱設定 [通話方案](../set-up-calling-plans.md)。

## <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 系統管理中心

使用 Microsoft 365 系統管理中心一次指派授權給個別使用者或少數使用者。 您可以在授權頁面上指派授權 (最多 20 個使用者一次) 或 **活動使用者頁面**。 您選擇的方法取決於您要管理特定使用者的產品授權，或管理特定產品的使用者授權。

有關逐步指示，請參閱指派 [授權給使用者](/microsoft-365/admin/manage/assign-licenses-to-users)。

如果您需要指派授權給大量使用者 ，例如數百或數千個使用者，請使用 Azure Active Directory ([Azure AD ](/azure/active-directory/users-groups-roles/licensing-groups-assign)) 。  

## <a name="using-powershell"></a>使用 PowerShell

使用 PowerShell 大量指派授權給使用者。  若要深入瞭解，請參閱使用 [PowerShell 將授權指派給使用者帳戶](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。

### <a name="example-script"></a>範例腳本

以下是如何使用腳本指派授權給使用者的範例。

1. 安裝適用于 IT 專業人員 RTW 的 Microsoft Online Services 登入 [小幫手的](/collaborate/connect-redirect?DownloadID=59185)64 位版本。
2. 安裝適用于 Windows PowerShell 的 Microsoft Azure Active Directory 模組：
    1. 開啟提升的 Windows PowerShell 命令提示 (以系統管理員角色執行 Windows PowerShell) 。
    2. 執行下列命令：
        ```powershell
        Install-Module MSOnline
        ```
    3. 如果系統提示您安裝 NuGet 提供者，請輸入 **Y，** 然後按 Enter。
    4. 如果系統提示您從 PSGallery 安裝模組，請輸入 **Y，** 然後按 Enter。
3. 在 Windows PowerShell 命令提示字元中，執行下列腳本來指派授權給使用者，其中您的組織名稱和要指派之授權識別碼 \<CompanyName:License> 在哪裡。 例如，litwareinc：MCOMEETADV。

    識別碼與授權好用的名稱不同。 例如，音訊會議識別碼為 MCOMEETADV。 若要深入瞭解，請參閱 [授權的產品名稱和 SKU 識別碼](#product-names-and-sku-identifiers-for-licensing)。

    ```powershell
    #Create a text file with a single column that lists the user principal names (UPNs) of users to assign licenses to. The MSOL service uses the UPN to license user accounts.
    #Example of text file:''
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
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        }
    ```

    例如，若要指派 Microsoft 365 企業版 1 和音訊會議授權，請使用腳本中的下列語法：

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    若要指派不含通話方案 (的 Microsoft Business Voice) ，請使用腳本中的下列語法：

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>授權的產品名稱和 SKU 識別碼

以下是部分產品名稱及其對應的 SKU 零件名稱清單，您可以在使用 PowerShell 管理 Teams 中的授權時做為參考。

若要深入瞭解，請參閱 [使用 PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)來查看授權和服務、 [授權](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)的產品名稱和服務方案識別碼，以及 [教育版 SKU 參考](../sku-reference-edu.md)。

| 產品名稱| SKU 零件名稱 |
|--------------|---------------|
| Microsoft Enterprise E5 (Phone System)  | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (沒有音訊會議)  | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (音訊會議)  | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 商務基本版 | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 商務標準版 | O365_BUSINESS_PREMIUM|
| Microsoft 365 商務版 | SPB|
| Microsoft Business Voice (加拿大) | BUSINESS_VOICE_MED  |
| Microsoft Business Voice (英國)  | BUSINESS_VOICE  |
| Microsoft Business Voice (美國)  | BUSINESS_VOICE_MED2  |
| Microsoft Business Voice (沒有通話方案)  | BUSINESS_VOICE_DIRECTROUTING  |
| Microsoft Business Voice (美國) 方案| BUSINESS_VOICE_DIRECTROUTING _MED |
| 音訊會議 | MCOMEETADV | 
| 使用音訊會議時， (按分鐘付費) </br>*需要設定並啟用通訊信用額度。* | MCOMEETACPEA |
| 電話系統 | MCOEV |
| 國內和國際通話方案 | MCOPSTN2 |
| 美國/ (/CA 的國內通話方案為每個使用者/月 3000 分鐘，歐盟國家/地區則為每個使用者/月 1200 分鐘)  | MCOPSTN1 |
| 國內通話方案 (每個國家/地區/月 120 分鐘)  </br>*此方案不適用於美國。* | MCOPSTN5 |
| 國內通話方案 (每個國家/地區/月 240 分鐘)  </br>*此方案不適用於美國。* | MCOPSTN6 |
| 通訊點數 | MCOPSTNPP |

## <a name="related-topics"></a>相關主題

- [Teams 附加元件授權](./microsoft-teams-add-on-licensing.md)
- [管理使用者對 Teams 的存取權](../user-access.md)
- [使用 PowerShell 查看授權和服務](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [用於授權的產品名稱和服務方案識別碼](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [教育用 SKU 參考](../sku-reference-edu.md)