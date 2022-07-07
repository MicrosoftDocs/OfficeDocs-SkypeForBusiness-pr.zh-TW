---
title: 指派 Teams 附加元件授權給使用者
author: SerdarSoysal
ms.author: serdars
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
description: 瞭解如何針對音訊會議、電話系統和通話方案等功能，將 Teams 附加元件授權指派給使用者。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2fca8eb5acac30210e67068f9a2b1eb8dfdce3cb
ms.sourcegitcommit: d87991ed2d3e4d70edb048378763a17ff689b710
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2022
ms.locfileid: "66682492"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>指派 Teams 附加元件授權給使用者

附加元件授權是特定 Teams 功能的授權，例如音訊會議、電話系統和通話方案。 本文說明如何將附加元件授權指派給個別使用者和大量使用者。

> [!NOTE]
> 請參閱 [Teams 附加元件授權](./microsoft-teams-add-on-licensing.md) 所提供的 Teams 功能附加元件授權。 您也可以根據您的方案，找到您需要購買哪些授權以及如何購買這些授權的相關資訊。 決定要為使用者使用哪些功能之後，請指派授權給他們。

您可以使用Microsoft 365 系統管理中心或 PowerShell 來指派授權給組織中的使用者。 您必須是全域系統管理員或使用者管理系統管理員，才能管理授權。

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>指派電話系統、通話方案和通訊點數授權之前必須知道的事項

開始之前，請檢閱下列需求：

- 如果您使用的是內部部署的公用交換電話網路 (PSTN) 使用者的連線能力，您只需要指派Teams 電話標準方案授權。 請勿指派通話方案授權。

- 將 Microsoft 通話方案指派給使用者之後，最多可能需要 24 小時，他們才會在 Teams 用戶端中看到撥號鍵台。 如果 24 小時內未顯示撥號鍵台，請檢查 [您的撥號鍵台設定](../dial-pad-configuration.md)。 如有需要，您也可以 [連絡支援服務](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。

- 如果您尚未購買正確的授權數目，您會收到錯誤訊息。 如果您需要購買更多通話方案授權，請選擇購買更多授權的選項。

- 即使您的使用者已獲指派企業版 E5 授權，您仍然需要將它們連線到 PSTN。 您有幾個[PSTN 連線選項](../pstn-connectivity.md)，包括 Microsoft Teams 通話方案、直接路由或運算子連線。

- 將通話方案或通訊點數授權指派給使用者之後，您必須為組織取得電話號碼，然後將這些號碼指派給使用者。 如需逐步指示，請參閱 [設定通話方案](../set-up-calling-plans.md)。

## <a name="using-the-microsoft-365-admin-center"></a>使用Microsoft 365 系統管理中心

使用Microsoft 365 系統管理中心一次指派授權給個別使用者或一小組使用者。

您會在 [ **授權** ] 頁面 (一次最多指派 20 個使用者) 或 [作用中 **使用者** ] 頁面 (一次最多 40 個使用者) 。 您選擇的方法取決於您要管理特定使用者的產品授權，還是管理特定產品的使用者授權。

如需逐步指示，請參閱 [指派授權給使用者](/microsoft-365/admin/manage/assign-licenses-to-users)。

如果您需要指派授權給大量使用者，例如數百或數千名使用者，請 [在 Azure Active Directory (Azure AD) ](/azure/active-directory/users-groups-roles/licensing-groups-assign)中使用 Powershell 或群組授權。

## <a name="using-powershell"></a>使用 PowerShell

使用 PowerShell 大量指派授權給使用者。 若要深入瞭解，請參閱 [使用 PowerShell 指派授權給使用者帳戶](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。

### <a name="example-script"></a>範例腳本

以下是如何使用腳本將授權指派給使用者的範例。

1. 安裝 64 位版本的 [適用于 IT 專業人員 RTW 的 Microsoft Online Services 登入小幫手](/collaborate/connect-redirect?DownloadID=59185)。
2. 安裝 Windows PowerShell 的Microsoft Azure Active Directory模組：
    1. 開啟提升許可權的Windows PowerShell命令提示字元 (以系統管理員) Windows PowerShell執行。
    2. 執行下列命令：
        ```powershell
        Install-Module MSOnline
        ```
    3. 如果系統提示您安裝 NuGet 提供者，請輸入 **Y**，然後按 Enter。
    4. 如果系統提示您從 PSGallery 安裝模組，請輸入 **Y**，然後按 Enter。
3. 在Windows PowerShell命令提示字元中，執行下列腳本以指派授權給使用者，您的組織名稱和 \<CompanyName:License> 您要指派之授權的識別碼在哪裡。 例如，litwareinc：MCOMEETADV。

    識別碼與授權的易記名稱不同。 例如，音訊會議的識別碼是 MCOMEETADV。 若要深入瞭解，請參閱 [授權用的產品名稱和 SKU 識別碼](#product-names-and-sku-identifiers-for-licensing)。

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

    例如，若要指派 Microsoft 365 企業版 E1 和音訊會議授權，請在腳本中使用下列語法：

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    若要指派具有通話方案授權的 Teams Phone，請在腳本中使用下列語法：

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOTEAMS_ESSENTIALS" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>授權用的產品名稱和 SKU 識別碼

以下是當您使用 PowerShell 管理 Teams 中的授權時，可以參照的產品名稱及其對應 SKU 元件名稱的部分清單。

若要深入瞭解，請參 [閱使用 PowerShell 檢視授權與服務](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)、 [授權的產品名稱與服務方案識別碼](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)，以及 [教育版 SKU 參考](../sku-reference-edu.md)。

| 產品名稱| SKU 元件名稱 |
|--------------|---------------|
| 使用電話系統) 的 Microsoft Enterprise E5 ( | ENTERPRISEPREMIUM |
| 不含音訊會議) 的 Microsoft Enterprise E5 ( | ENTERPRISEPREMIUM_NOPSTNCONF |
| 具備音訊會議) 的 Microsoft Enterprise E5 ( | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 商務基本版 | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 商務標準版 | O365_BUSINESS_PREMIUM|
| Microsoft 365 商務版 | SPB|
| 音訊會議 | MCOMEETADV |
| 音訊會議每分鐘付費 (在您進行時支付，) 需要設定並啟用通訊點數。* | MCOMEETACPEA |
| Teams 電話標準方案 | MCOEV |
| 含通話方案的 Teams 電話 | MCOTEAMS_ESSENTIALS |
| 國際通話方案 | MCOPSTN2 |
| 國內通話方案 (每個使用者/月 3000 分鐘的美式/PR/CA 通話方案，每個使用者為 1200 分鐘/月，針對歐盟國家/地區)  | MCOPSTN1 |
| 每個國家/地區的國內通話方案 (每個使用者每月 120 分鐘)  </br>*美國不提供此方案。* | MCOPSTN5 |
| 每個國家/地區的國內通話方案 (每個使用者每月 240 分鐘)  </br>*美國不提供此方案。* | MCOPSTN6 |
| 通訊點數 | MCOPSTNPP |

## <a name="related-content"></a>相關內容

- [Teams 附加元件授權](./microsoft-teams-add-on-licensing.md)
- [管理使用者對 Teams 的存取權](../user-access.md)
- [使用 PowerShell 檢視授權和服務](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [用於授權的產品名稱和服務方案識別碼](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [教育版 SKU 參考](../sku-reference-edu.md)
