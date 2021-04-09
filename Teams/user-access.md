---
title: 管理 Microsoft Teams 的使用者存取權
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
description: 瞭解如何指派或移除 Teams 授權給貴組織的使用者來管理 Teams 的使用者存取權。
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

您可以指派或移除 Microsoft Teams 產品授權，以管理使用者層級的 Teams 存取權。 除了匿名加入 Teams 會議之外，貴組織的每個使用者都必須擁有 Teams 授權，才能使用 Teams。 您可以在建立新使用者帳戶時指派 Teams 授權給新使用者，或指派給擁有現有帳戶的使用者。

根據預設，當授權方案 (例如 Microsoft 365 企業版 E3 或 Microsoft 365 商務進級版) 指派給使用者時，系統會自動指派 Teams 授權，且該使用者已啟用 Teams。 您隨時都可以移除或指派授權，為使用者停用或啟用 Teams。

使用從 Teams 系統管理中心管理的訊息策略，控制 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">哪些</a>聊天和頻道傳訊功能可供 Teams 中的使用者使用。 您可以使用預設策略，或為貴組織人員建立一或多個自訂訊息策略。 若要深入瞭解，請參閱 [在 Teams 中管理訊息策略](messaging-policies-in-teams.md)。
您可以在 Microsoft 365 系統管理中心或使用 PowerShell 管理 Teams 授權。 您必須是全域系統管理員或使用者管理系統管理員，才能管理授權。

> [!NOTE]
> 我們建議您為所有使用者啟用 Teams，以便針對專案和其他動態計畫，以組織方式組成團隊。 即使您進行試驗，讓所有使用者都保持 Teams 啟用可能仍然有説明，但只會將通訊目標鎖定至試驗使用者群組。

## <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 系統管理中心

Teams 使用者層級授權會透過 Microsoft 365 系統管理中心使用者管理介面直接管理。 系統管理員可以在建立新使用者帳戶時指派授權給新使用者，或指派給擁有現有帳戶的使用者。 

> [!IMPORTANT]
> 系統管理員必須擁有全域系統管理員或使用者管理系統管理員許可權，才能管理 Microsoft Teams 授權。
使用 Microsoft 365 系統管理中心一次管理個別使用者或少數使用者的 Teams 授權。 您可以在授權頁面或 (管理Teams 授權) 最多 20 **個使用者。** 您選擇的方法取決於您要管理特定使用者的產品授權，或管理特定產品的使用者授權。

如果您需要管理大量使用者的 Teams 授權 ，例如數百或數千個使用者，請使用[Azure Active Directory ](/azure/active-directory/users-groups-roles/licensing-groups-assign) (Azure AD) 中的[PowerShell](#using-powershell)或群組授權。 

### <a name="assign-a-teams-license"></a>指派 Teams 授權

步驟會根據您使用授權頁面或活動 **使用者頁面****而** 不同。  有關逐步指示，請參閱指派 [授權給使用者](/microsoft-365/admin/manage/assign-licenses-to-users)。

|||
|---------|---------|
|![使用者已啟用 Teams 授權之螢幕擷取畫面](media/assign-teams-licenses-1.png)    | ![使用者已啟用 Teams 授權之螢幕擷取畫面](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>移除 Teams 授權

> [!IMPORTANT]
> 停用 Teams SKU 需要大約 24 小時才能生效。

當您從使用者移除 Teams 授權時，該使用者的 Teams 會停用，而且他們不會再在應用程式啟動器或首頁中看到 Teams。 有關詳細步驟，請參閱 [取消使用者授權](/microsoft-365/admin/manage/remove-licenses-from-users)。

|||
|---------|---------|
|![已停用使用者的 Teams 授權螢幕擷取畫面](media/remove-teams-licenses-1.png)    | ![已停用使用者的 Teams 授權螢幕擷取畫面](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>使用 PowerShell

使用 PowerShell 大量管理使用者的 Teams 授權。 您透過 PowerShell 啟用和停用 Teams 的方式，與任何其他服務方案授權相同。 您需要 Teams 服務方案識別碼，如下所示：

- Microsoft Teams：TEAMS1
- GCC 的 Microsoft Teams：TEAMS_GOV
- Microsoft Teams for DoD：TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>大量指派 Teams 授權

有關詳細步驟，請參閱使用 [PowerShell 將授權指派給使用者帳戶](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。

### <a name="remove-teams-licenses-in-bulk"></a>大量移除 Teams 授權

有關詳細步驟，請參閱停用 [PowerShell](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) 服務存取權，以及指派使用者授權 [時停用服務存取權](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)。

#### <a name="example"></a>範例 

以下是如何使用 [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) 和 [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) Cmdlet 來停用 Teams 的範例，供擁有特定授權方案的使用者使用。 例如，請遵循下列步驟，針對擁有特定授權計畫的所有使用者，先停用 Teams。 然後針對應具有 Teams 存取權的每個個別使用者啟用 Teams。

> [!IMPORTANT]
> [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) Cmdlet 會啟用先前停用的所有服務，除非您在自訂腳本中明確識別。 例如，如果您想要同時停用 Exchange 和 Sway，同時停用 Teams，您必須在腳本中納入此功能，否則將針對您識別的使用者啟用 Exchange 和 Sway。

執行下列命令以顯示貴組織中所有可用的授權方案。 若要深入瞭解，請參閱 [使用 PowerShell 來查看授權和服務](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)。


```powershell
Get-MsolAccountSku
```

執行下列命令，即貴組織的名稱，以及您先前步驟所提取之授權計畫的 \<CompanyName:License> 識別碼。 例如，ContosoSchool：ENTERPRISEPACK_STUDENT。

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

請執行下列命令，針對擁有授權方案有效授權之所有使用者停用 Teams。

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a>相關主題

- [Teams 附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [指派 Teams 附加元件授權](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [使用 PowerShell 查看授權和服務](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [用於授權的產品名稱和服務方案識別碼](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [教育用 SKU 參考](sku-reference-edu.md)
