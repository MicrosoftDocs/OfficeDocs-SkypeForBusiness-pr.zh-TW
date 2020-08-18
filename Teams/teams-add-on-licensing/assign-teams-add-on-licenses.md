---
title: 指派團隊附加元件授權給使用者
author: LanaChin
ms.author: v-lanac
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
description: 瞭解如何將團隊附加元件授權指派給使用者，以取得音訊會議、電話系統和通話方案等功能。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5dd09ae11104aa0297a12417d4c267edfc17cf3f
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788737"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>指派團隊附加元件授權給使用者

附加元件授權是特定團隊功能（例如音訊會議、電話系統和通話方案）的授權。 本文說明如何將附加元件授權指派給個別使用者，以及大量使用者。

> [!NOTE]
> 請參閱 [小組附加元件授權](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) ，瞭解適用于附加元件授權的小組功能。 您也可以找到您需要購買哪些授權，以及如何購買這些授權的相關資訊 (取決於您的方案) ，讓使用者可以取得音訊會議、免付費電話號碼，以及撥打貴組織以外的電話號碼的功能。 在您決定要為使用者提供哪些功能之後，請將授權指派給他們。

您可以使用 Microsoft 365 系統管理中心或 PowerShell，指派授權給貴組織中的使用者。 您必須是全域系統管理員或使用者管理系統管理員，才能管理授權。

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>指派電話系統、通話方案和通訊信用授權前需要注意的事項

在您開始之前，請先檢查下列專案：

- 如果您使用的是內部部署的公用交換電話網絡 (PSTN) 連線至混合式使用者，您只需要指派電話系統授權。 請勿指派通話方案授權。

- 由於 Microsoft 365 與 Microsoft 團隊之間的延遲，在指派授權之後，可能需要長達24小時的時間指派通話方案。 如果使用者在24小時後未獲指派通話方案， [請聯絡商務產品支援-系統管理協助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。

- 如果您還沒有購買正確數量的授權，您會收到錯誤訊息。 如果您需要購買更多通話方案授權，請選擇購買更多的選項。

- 即使您的使用者已獲指派企業版 E5 授權，但如果他們想要從 PSTN 撥打或接聽電話，仍需將 [通訊信用](../what-are-communications-credits.md) 權指派給他們。

- 在您將通話方案或通訊信用授權指派給使用者之後，您必須取得貴組織的電話號碼，然後將這些號碼指派給使用者。 如需逐步指示，請參閱 [設定通話方案](../set-up-calling-plans.md)。

## <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 系統管理中心

使用 Microsoft 365 系統管理中心，一次將授權指派給個別的使用者或一組小的使用者。 您可以在 [ **授權** ] 頁面上指派授權， (一次最多20個使用者) 或 [作用中的 **使用者** ] 頁面。 您選擇的方法取決於您是否要管理特定使用者的產品授權，或管理特定產品的使用者授權。

如需逐步指示，請參閱 [指派授權給使用者](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。

如果您需要指派大量使用者（例如幾百或數千個使用者）的授權，請 [在 Azure Active Directory 中使用 Powershell 或群組式授權 (AZURE AD) ](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)。  

## <a name="using-powershell"></a>使用 PowerShell

使用 PowerShell 來大量指派授權給使用者。  若要深入瞭解，請參閱 [使用 PowerShell 指派授權給使用者帳戶](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。

### <a name="example-script"></a>範例腳本

以下範例說明如何使用腳本來指派授權給您的使用者。

1. 安裝 [適用于 IT 專業人員](https://go.microsoft.com/fwlink/p/?LinkId=286152)的64位版本的 Microsoft Online Services 登入小幫手 RTW。
2. 安裝適用于 Windows PowerShell 的 Microsoft Azure Active Directory 模組：
    1. 開啟提升許可權的 Windows PowerShell 命令提示字元 (以系統管理員身分執行 Windows PowerShell) 。
    2. 執行下列命令：
        ```powershell
        Install-Module MSOnline
        ```
    3. 如果系統提示您安裝 NuGet 提供者，請輸入 **Y**，然後按 enter。
    4. 如果系統提示您從 PSGallery 安裝模組，請輸入 **Y**，然後按 enter。
3. 在 Windows PowerShell 命令提示字元中，執行下列腳本來指派授權給您的使用者，其中 \<CompanyName:License> 是您的組織名稱，以及您要指派之授權的識別碼。 例如，litwareinc： MCOMEETADV。

    識別碼與授權的易記名稱不同。 例如，音訊會議的識別碼是 MCOMEETADV。 若要深入瞭解，請參閱 [授權的產品名稱和 SKU 識別碼](#product-names-and-sku-identifiers-for-licensing)。

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

    例如，若要指派 Microsoft 365 企業版1和音訊會議授權，請在腳本中使用下列語法：

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    若要將 Microsoft 商務語音 (指派給不需通話方案) 授權，請在腳本中使用下列語法：

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>授權的產品名稱和 SKU 識別碼

以下是產品名稱的部分清單及其對應的 SKU 元件名稱，當您使用 PowerShell 管理團隊中的授權時，您可以使用這些名稱作為參考。

若要深入瞭解，請參閱 [使用 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)、 [產品名稱和服務方案識別碼來查看授權及服務，以取得授權](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)及 [教育 SKU 參考](../sku-reference-edu.md)。

| 產品名稱| SKU 元件名稱 |
|--------------|---------------|
| Microsoft 企業版 E5 (與電話系統)  | ENTERPRISEPREMIUM |
| 沒有音訊會議的 Microsoft 企業版 E5 ()  | ENTERPRISEPREMIUM_NOPSTNCONF |
| 使用音訊會議的 Microsoft 企業版 E5 ()  | ENTERPRISEPREMIUM |
| Microsoft 企業版 E3 | ENTERPRISEPACK |
| Microsoft 企業版 E1 | STANDARDPACK |
| Microsoft 365 商務基本版 | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 商務標準版 | O365_BUSINESS_PREMIUM|
| Microsoft 365 商務版 | SPB|
| Microsoft 商務語音 (加拿大) | BUSINESS_VOICE_MED  |
| Microsoft 商務語音 (英國)  | BUSINESS_VOICE  |
| Microsoft 商務語音 (美國)  | BUSINESS_VOICE_MED2  |
| 不需通話方案的 Microsoft 商務語音 ()  | BUSINESS_VOICE_DIRECTROUTING  |
| Microsoft 商務語音 (不需美國電話方案) | BUSINESS_VOICE_DIRECTROUTING _MED |
| 音訊會議 | MCOMEETADV | 
| 語音會議每分鐘付款 (按您的方式付費) </br>*需要設定並啟用通訊信用額度。* | MCOMEETACPEA |
| 電話系統 | MCOEV |
| 國內和國際通話方案 | MCOPSTN2 |
| 國內通話方案在每個使用者/每個月) 1200 的每個使用者/每個月份撥打3000分鐘 ( | MCOPSTN1 |
| 國內通話方案針對每個國家/地區的每個使用者/月份 (120 分鐘)  </br>*美國未提供此方案。* | MCOPSTN5 |
| 國內通話方案針對每個國家/地區的每個使用者/月份 (240 分鐘)  </br>*美國未提供此方案。* | MCOPSTN6 |
| 通訊點數 | MCOPSTNPP |

## <a name="related-topics"></a>相關主題

- [Teams 附加元件授權](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
- [管理使用者對 Teams 的存取權](../user-access.md)
- [使用 PowerShell 來查看授權與服務](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [用於授權的產品名稱和服務方案識別碼](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [教育版 SKU 參考](../sku-reference-edu.md)