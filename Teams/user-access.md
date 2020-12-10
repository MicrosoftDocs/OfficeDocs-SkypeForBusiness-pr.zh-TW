---
title: 管理使用者對 Microsoft 團隊的存取權
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: 瞭解如何指派或移除團隊授權給組織中的使用者，以管理使用者對團隊的存取權。
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9d370bec6eb8a3319427c934593016f2b85d6c26
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611457"
---
# <a name="manage-user-access-to-teams"></a>管理使用者對 Teams 的存取權

您可以指派或移除 Microsoft 團隊產品授權，在使用者層級管理團隊的存取權。 除了以匿名方式加入團隊會議之外，貴組織中的每位使用者都必須擁有團隊授權，才能使用團隊。 您可以在建立新的使用者帳戶時指派團隊授權給新使用者，或是使用現有帳戶指派給使用者。

根據預設，當授權方案 (：例如，Microsoft 365 企業版 E3 或 Microsoft 365 Business Premium) 指派給使用者時，系統會自動指派團隊授權，並為團隊啟用使用者。 您可以隨時移除或指派授權，來停用或啟用使用者的團隊。

使用來自 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">團隊系統管理中心</a>管理的訊息原則，以控制可供團隊使用者使用的聊天和通道訊息功能。 您可以針對組織中的人員，使用預設原則或建立一或多個自訂的訊息策略。 若要深入瞭解，請參閱 [管理團隊中的訊息傳遞原則](messaging-policies-in-teams.md)。
您可以在 Microsoft 365 系統管理中心或使用 PowerShell 管理團隊授權。 您必須是全域系統管理員或使用者管理系統管理員，才能管理授權。

> [!NOTE]
> 我們建議您為所有使用者啟用團隊，讓團隊可以針對專案和其他動態方案進行 organically。 即使您執行的是試用版，仍可將團隊保持為所有使用者使用，但只有目標是與使用者的試驗群組進行通訊。

## <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 系統管理中心

團隊使用者層級授權是透過 Microsoft 365 系統管理中心使用者管理介面直接管理。 系統管理員可以在建立新的使用者帳戶時指派授權給新的使用者，或指派給現有帳戶的使用者。 

> [!IMPORTANT]
> 系統管理員必須具備全域系統管理員或使用者管理管理員的許可權，才能管理 Microsoft 團隊授權。
使用 Microsoft 365 系統管理中心，分別管理個別使用者或一組小組使用者的小組授權。 您可以在 [ **授權** ] 頁面上管理多達20個使用者，同時) 或 [作用中 **使用者** ] 頁面上的 [團隊授權] (。 您選擇的方法取決於您是否要管理特定使用者的產品授權，或管理特定產品的使用者授權。

如果您需要管理大量使用者（例如幾百或數千位使用者）的團隊授權，請[在 Azure Active Directory 中使用 PowerShell 或群組式授權 (AZURE AD) ](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)。 [](#using-powershell) 

### <a name="assign-a-teams-license"></a>指派團隊授權

這些步驟會根據您使用的是 [ **授權** ] 頁面或 [作用中 **使用者** ] 頁面而有所不同。  如需逐步指示，請參閱 [指派授權給使用者](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。

|||
|---------|---------|
|![已針對使用者啟用之團隊授權的螢幕擷取畫面](media/assign-teams-licenses-1.png)    | ![已針對使用者啟用之團隊授權的螢幕擷取畫面](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>移除團隊授權

當您移除使用者的小組授權時，系統會停用該使用者的小組，且不會再在應用程式啟動器或首頁中看到小組。 如需詳細步驟，請參閱 [取消指派給使用者的授權](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users)。

|||
|---------|---------|
|![使用者已停用之小組授權的螢幕擷取畫面](media/remove-teams-licenses-1.png)    | ![使用者已停用之小組授權的螢幕擷取畫面](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>使用 PowerShell

使用 PowerShell 管理大量使用者的團隊授權。 您可以透過 PowerShell 啟用和停用團隊，就像在任何其他服務方案授權中一樣。 您需要團隊服務方案的識別碼，如下所示：

- Microsoft 團隊： TEAMS1
- 適用于 GCC 的 Microsoft 團隊： TEAMS_GOV
- 適用于 DoD 的 Microsoft 團隊： TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>大量指派團隊授權

如需詳細步驟，請參閱 [使用 PowerShell 指派授權給使用者帳戶](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。

### <a name="remove-teams-licenses-in-bulk"></a>大量移除團隊授權

如需詳細步驟，請參閱 [使用 PowerShell 停用服務的存取權](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) ，以及 [在指派使用者授權時停用服務的存取權](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)。

#### <a name="example"></a>範例 

以下是如何使用 [新的 MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) 和 [MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) Cmdlet 來針對擁有特定授權方案的使用者停用團隊的範例。 例如，請依照下列步驟，先針對所有擁有特定授權方案的使用者停用團隊。 然後針對應該有權存取團隊的每位使用者，分別啟用團隊。

> [!IMPORTANT]
> [新的 MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) Cmdlet 會啟用先前已停用的所有服務，除非您在自訂腳本中明確標示。 例如，如果您想要停用 Exchange 和 Sway 同時又停用小組，您必須在腳本中包含這項功能，否則您所識別的使用者將會啟用 Exchange 和 Sway。

執行下列命令，以顯示貴組織中所有可用的授權方案。 若要深入瞭解，請參閱 [使用 PowerShell 來查看授權及服務](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)。


```powershell
Get-MsolAccountSku
```

執行下列命令，其中 \<CompanyName:License> 是您的組織名稱，以及您在先前步驟中檢索之授權方案的識別碼。 例如，ContosoSchool： ENTERPRISEPACK_STUDENT。

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

執行下列命令，以針對所有擁有授權方案有效授權的使用者停用團隊。

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="manage-teams-at-the-organization-level"></a>在組織層級管理團隊

[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

## <a name="related-topics"></a>相關主題

- [團隊附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [指派團隊附加元件授權](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [使用 PowerShell 來查看授權與服務](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [用於授權的產品名稱和服務方案識別碼](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [教育版 SKU 參考](sku-reference-edu.md)
