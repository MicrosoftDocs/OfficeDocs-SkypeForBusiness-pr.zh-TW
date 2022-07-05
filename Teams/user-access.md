---
title: 管理使用者對 Microsoft Teams 的存取權
manager: SerdarSoysal
ms.author: mikeplum
author: MikePlumleyMSFT
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: 瞭解如何指派或移除 Teams 授權給貴組織中的使用者，以管理使用者對 Teams 的存取權。
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8e78d5905eaed7d9302ffdbf071c3dcf93f00fea
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/05/2022
ms.locfileid: "66616259"
---
# <a name="manage-user-access-to-teams"></a>管理使用者對 Teams 的存取權

您可以指派或移除 Microsoft Teams 產品授權，以在使用者層級管理 Teams 的存取權。 除了以匿名方式加入 Teams 會議之外，貴組織中的每個使用者都必須擁有 Teams 授權，才能使用 Teams。 您可以在建立新的使用者帳戶時指派 Teams 授權給新使用者，或指派給擁有現有帳戶的使用者。

根據預設，當授權方案 (例如Microsoft 365 企業版 E3 或 Microsoft 365 商務進階版) 指派給使用者時，系統會自動指派 Teams 授權，並啟用 Teams 的使用者。 您可以隨時移除或指派授權，停用或啟用使用者的 Teams。

使用從<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams 管理員中心</a>管理的訊息原則，以控制 Teams 中使用者可使用的聊天和頻道訊息功能。 您可以使用預設原則，或為組織中的人員建立一或多個自訂訊息原則。 若要深入瞭解，請閱讀 [管理 Teams 中的訊息原則](messaging-policies-in-teams.md)。
您可以在 Microsoft 365 系統管理中心 或使用 PowerShell 管理 Teams 授權。 您必須是全域系統管理員或使用者管理系統管理員，才能管理授權。

> [!NOTE]
> 我們建議您為所有使用者啟用 Teams，以便針對專案和其他動態計畫以組織方式形成團隊。 即使您正在執行試驗，讓所有使用者都能使用 Teams，但只對試驗群組的使用者進行目標通訊可能仍然很有説明。

## <a name="using-the-microsoft-365-admin-center"></a>使用Microsoft 365 系統管理中心

Teams 使用者層級授權會直接透過使用者管理介面Microsoft 365 系統管理中心管理。 系統管理員可以在新使用者帳戶建立時指派授權給新使用者，或指派給擁有現有帳戶的使用者。 

> [!IMPORTANT]
> 管理員必須具備全域系統管理員或使用者管理系統管理員許可權，才能管理 Microsoft Teams 授權。
使用Microsoft 365 系統管理中心一次管理個別使用者或一小組使用者的 Teams 授權。 您可以在 [授權] 頁面 () 或作用中使用者頁面管理最多 20 個 **使用者** 的 Teams **授權**。 您選擇的方法取決於您要管理特定使用者的產品授權，還是管理特定產品的使用者授權。

如果您需要管理大量使用者的 Teams 授權，例如數百或數千名使用者，請使用 Azure Active [Directory 中的 PowerShell](#using-powershell) 或 [群組授權， (Azure AD) ](/azure/active-directory/users-groups-roles/licensing-groups-assign)。 

### <a name="assign-a-teams-license"></a>指派 Teams 授權

步驟會根據您使用的是 **[授權** ] 頁面或 [作用中 **使用者** ] 頁面而有所不同。  如需逐步指示，請參閱 [指派授權給使用者](/microsoft-365/admin/manage/assign-licenses-to-users)。

|&nbsp;|&nbsp;|
|---------|---------|
|![使用者已啟用 Teams 授權的螢幕擷取畫面 1。](media/assign-teams-licenses-1.png)    | ![使用者已啟用 Teams 授權的螢幕擷取畫面 2](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>移除 Teams 授權

> [!IMPORTANT]
> 停用 Teams SKU 大約需要 24 小時才會生效。

當您移除使用者的 Teams 授權時，該使用者的 Teams 會停用，他們不會再于應用程式啟動器或首頁中看到 Teams。 如需詳細步驟，請參閱 [取消指派使用者的授權](/microsoft-365/admin/manage/remove-licenses-from-users)。

|&nbsp;|&nbsp;|
|---------|---------|
|![使用者已停用 Teams 授權的螢幕擷取畫面 1。](media/remove-teams-licenses-1.png)    | ![使用者已停用 Teams 授權的螢幕擷取畫面 2](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>使用 PowerShell

使用 PowerShell 大量管理使用者的 Teams 授權。 您透過 PowerShell 啟用和停用 Teams 的方式，與啟用任何其他服務方案授權的方式相同。 您需要 Teams 服務方案的識別碼，如下所示：

- Microsoft Teams：TEAMS1
- Microsoft Teams for GCC：TEAMS_GOV
- Microsoft Teams for DoD：TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>大量指派 Teams 授權

如需詳細步驟，請參閱 [使用 PowerShell 指派授權給使用者帳戶](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。

### <a name="remove-teams-licenses-in-bulk"></a>大量移除 Teams 授權

如需詳細步驟，請參閱 [使用 PowerShell 停用服務存取](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) 和在 [指派使用者授權時停用服務存取權](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)。

#### <a name="example"></a>範例 

下列範例說明如何針對擁有特定授權方案的使用者，使用 [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) 和 [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) Cmdlet 來停用 Teams。 例如，請遵循下列步驟，首先針對擁有特定授權方案的所有使用者停用 Teams。 然後為每個應該有權存取 Teams 的個別使用者啟用 Teams。

> [!IMPORTANT]
> [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) Cmdlet 會啟用先前停用的所有服務，除非您在自訂腳本中明確指出。 例如，如果您想要讓 Exchange 和 Sway 同時停用 Teams，則必須在腳本中包含此功能，否則 Exchange 和 Sway 將會針對您識別的使用者啟用。

執行下列命令以顯示貴組織中所有可用的授權方案。 若要深入瞭解，請參 [閱使用 PowerShell 檢視授權和服務](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)。


```powershell
Get-MsolAccountSku
```

執行下列命令，您在先前 \<CompanyName:License> 步驟中擷取的組織名稱和授權方案識別碼在哪裡。 例如，ContosoSchool：ENTERPRISEPACK_STUDENT。

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

執行下列命令，針對擁有授權方案有效授權的所有使用者停用 Teams。

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a>相關主題

- [Teams 附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [指派 Teams 附加元件授權](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [使用 PowerShell 檢視授權和服務](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [用於授權的產品名稱和服務方案識別碼](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [教育版 SKU 參考](sku-reference-edu.md)
