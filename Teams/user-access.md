---
title: 管理使用者對 Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: 瞭解如何指派或移除授權給Teams使用者，以管理使用者對Teams存取權。
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 770dcea62d6f3dc65f576a3d64a520dd4de2ecad
ms.sourcegitcommit: 950387da2a2c094b7580bcf81ae5d8b6dfba0d6b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/08/2021
ms.locfileid: "51637725"
---
# <a name="manage-user-access-to-teams"></a>管理使用者對 Teams 的存取權

您可以指派或移除Teams授權，以管理使用者層級Microsoft Teams存取權。 除了以匿名Teams加入會議之外，貴組織的每個使用者都必須擁有Teams授權，才能使用Teams。 您可以在建立Teams使用者帳戶時指派授權給新使用者，或指派給擁有現有帳戶的使用者。

根據預設，當授權方案 (例如 Microsoft 365 企業版 E3 或 Microsoft 365 商務進階版) 指派給使用者時，系統會自動指派 Teams 授權，且使用者已啟用 Teams。 您隨時都可以Teams或指派授權，為使用者停用或啟用授權。

使用從系統管理中心管理Teams訊息<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank"></a>策略，控制哪些聊天和頻道訊息功能可供 Teams。 您可以使用預設策略，或為貴組織人員建立一或多個自訂訊息策略。 若要深入瞭解，請參閱在 Teams[中管理Teams。](messaging-policies-in-teams.md)
您可以在系統Teams管理中心Microsoft 365或使用 PowerShell 管理授權。 您必須是全域系統管理員或使用者管理系統管理員，才能管理授權。

> [!NOTE]
> 我們建議您為所有使用者啟用Teams，讓團隊可以針對專案和其他動態計畫以組織方式組成。 即使您進行試驗，保持所有使用者Teams，但只將通訊目標鎖定至試驗使用者群組可能還是很有説明。

## <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365系統管理中心

Teams管理中心使用者管理介面直接管理Microsoft 365層級授權。 系統管理員可以在建立新使用者帳戶時指派授權給新使用者，或指派給擁有現有帳戶的使用者。 

> [!IMPORTANT]
> 系統管理員必須擁有全域系統管理員或使用者管理系統管理員許可權，才能管理Microsoft Teams授權。
使用 Microsoft 365管理中心，一Teams管理個別使用者或小使用者組的使用者授權。 您可以在授權Teams或活動 (頁面上管理最多20 位) **授權**。 您選擇的方法取決於您要管理特定使用者的產品授權，或管理特定產品的使用者授權。

如果您需要管理大量使用者的 Teams 授權 ，例如數百或數千個使用者，請使用[Azure Active Directory (Azure AD ](/azure/active-directory/users-groups-roles/licensing-groups-assign)Azure Active Directory (中的[PowerShell](#using-powershell)或群組授權) 。 

### <a name="assign-a-teams-license"></a>指派授權Teams授權

步驟會根據您使用授權頁面或活動 **使用者頁面****而** 不同。  有關逐步指示，請參閱指派 [授權給使用者](/microsoft-365/admin/manage/assign-licenses-to-users)。

|||
|---------|---------|
|![使用者Teams授權之螢幕擷取畫面](media/assign-teams-licenses-1.png)    | ![使用者Teams授權之螢幕擷取畫面](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>移除Teams授權

> [!IMPORTANT]
> 停用 SKU 需要大約 24 小時Teams SKU 才能生效。

當您從使用者Teams授權時，Teams使用者就會停用，而且他們不會再在應用程式啟動器Teams首頁看到任何授權。 有關詳細步驟，請參閱 [取消使用者授權](/microsoft-365/admin/manage/remove-licenses-from-users)。

|||
|---------|---------|
|![使用者Teams授權之螢幕擷取畫面](media/remove-teams-licenses-1.png)    | ![使用者Teams授權之螢幕擷取畫面](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>使用 PowerShell

使用 PowerShell 大量Teams使用者授權。 您透過 PowerShell Teams和停用其他服務方案授權的方式，來啟用和停用。 您需要服務方案識別碼Teams，如下所示：

- Microsoft Teams：TEAMS1
- Microsoft Teams： GCC： TEAMS_GOV
- Microsoft Teams DoD 的TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>大量Teams指派授權

有關詳細步驟，請參閱使用 [PowerShell 將授權指派給使用者帳戶](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。

### <a name="remove-teams-licenses-in-bulk"></a>大量Teams移除授權

有關詳細步驟，請參閱停用 [PowerShell](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) 服務存取權，以及指派使用者授權 [時停用服務存取權](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)。

#### <a name="example"></a>範例 

以下是如何使用[New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions)和[Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) Cmdlet 來停用 Teams 的範例，供擁有特定授權方案的使用者使用。 例如，請遵循下列步驟，針對Teams方案的使用者，先停用授權。 然後針對Teams使用者啟用Teams。

> [!IMPORTANT]
> [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) Cmdlet 會啟用先前停用的所有服務，除非您在自訂腳本中明確識別。 例如，如果您想要同時停用 Exchange 和 Sway，同時停用 Teams，您必須在腳本中納入此功能，否則 Exchange 和 Sway 都會針對您識別的使用者啟用。

執行下列命令以顯示貴組織中所有可用的授權方案。 若要深入瞭解，請參閱 [使用 PowerShell 來查看授權和服務](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)。


```powershell
Get-MsolAccountSku
```

執行下列命令，即貴組織的名稱，以及您先前步驟中所提取之授權計畫的 \<CompanyName:License> 識別碼。 例如，ContosoSchool：ENTERPRISEPACK_STUDENT。

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

請執行下列命令，Teams授權方案之所有使用中授權的使用者停用授權。

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a>相關主題

- [Teams附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [指派Teams附加元件授權](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [使用 PowerShell 來查看授權和服務](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [用於授權的產品名稱和服務方案識別碼](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [教育用 SKU 參考](sku-reference-edu.md)
