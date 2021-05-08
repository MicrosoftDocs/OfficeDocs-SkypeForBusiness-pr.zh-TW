---
title: 使用 Microsoft Teams 系統管理員角色來管理 Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/19/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.errorpage.needadminpermsforadmincenter.assignadminrolesarticle
- ms.teamsadmincenter.errorpage.needadminperms.assignadminrolesarticle
- ms.teamsadmincenter.signin.error.nopermissions
- ms.teamsadmincenter.directrouting.cqd
- seo-marvel-apr2020
ms.reviewer: islubin
description: 瞭解如何使用系統管理角色來指定需要不同層級存取權限的系統管理員，以管理Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: c8ede97c91254c2dfeace83302c20e310e62be12
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282339"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>使用 Microsoft Teams 系統管理員角色來管理 Teams

您可以使用 Azure Active Directory (Azure AD) ，指定需要不同層級存取權限的系統管理員來管理Microsoft Teams。 系統管理員可以管理整個Teams工作量，或者他們可以委派許可權來疑難排解通話品質問題或管理貴組織的電話需求。

## <a name="teams-roles-and-capabilities"></a>Teams角色和功能

系統提供Teams系統管理員角色：Teams、Teams通訊系統管理員、Teams通訊支援專家、Teams通訊支援工程師，以及 Teams系統管理員。 請查閱下表，瞭解每個角色可以執行哪些工作，以及系統管理員可以在系統管理中心與 PowerShell 中Microsoft Teams哪些工具。

若要追蹤，您必須是系統管理員。本文提供取得許可權的指示。

<!-- add Global admin role? -->

| 角色                                    | 可以執行這些工作                                                           | 可以存取下列工具                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Teams 系統管理員             | 管理Teams服務，以及管理及建立Microsoft 365群組。        | 系統管理中心Microsoft Teams相關的 PowerShell 控制項，包括：<ul><li> 管理會議，包括會議策略、組配置和會議橋接器。<sup>1，2</sup></li><li>管理語音，包括通話策略和電話號碼庫存和工作分派。<sup>1，3</sup></li><li>管理訊息，包括訊息策略。<sup>1，2</sup></li><li>管理所有全組織設定，包括聯盟、團隊升級和 Teams 用戶端設定。<sup>1，2</sup></li><li>管理組織中團隊及其關聯的設定，包括透過 PowerShell 支援的成員資格 (群組管理、Teams系統管理中心) 。<sup>1，2</sup></li><li>管理Teams認證的裝置，並設定及指派設定策略。<sup>1</sup></li><li>使用進一步疑難排解工具集來查看使用者設定檔頁面及疑難排解使用者通話品質問題。<sup>2</sup> </li><li>存取系統管理中心Microsoft Teams報告</li><li> 使用通話品質儀表板 (CQD) 中公開的資料，存取、監控及疑難排解租使用者的通話品質與可靠性) 通話品質不佳的使用者。 建立新的通話品質報告，並根據需要更新和移除通話品質報告。 Upload並更新 CQD 建築物資料。</li><li> [將應用程式發佈到系統管理中心中的租Microsoft Teams目錄](manage-apps.md)</li></ul> |
| Teams 通訊系統管理員      | 管理服務中的通話Teams功能。               | 管理會議，包括會議策略、組配置和會議橋接器。<sup>1，2</sup><br><br> 管理語音，包括通話策略和電話號碼庫存和工作分派。<sup>1，3</sup><br><br> 使用進一步疑難排解工具集來查看使用者設定檔頁面並疑難排解使用者通話品質問題。<sup>2</sup> <br><br> 使用通話品質儀表板 (CQD) 中公開的資料，存取、監控及疑難排解租使用者的通話品質與可靠性) 低至受到通話品質不佳影響的使用者。 建立新的通話品質報告，並根據需要更新和移除通話品質報告。 Upload並更新 CQD 建築物資料。|
| Teams 通訊支援工程師   | 使用進Teams疑難排解內部 **通訊** 問題。 | 使用進一步疑難排解工具集來查看使用者設定檔頁面及疑難排解使用者通話品質問題。<sup>2</sup> <br><br> 使用通話品質儀表板 (CQD) 中公開的資料，存取、監控及疑難排解租使用者的通話品質與可靠性) 低至受到通話品質不佳影響的使用者。 |
| Teams通訊支援專家 | 使用基本工具Teams內部通訊 **問題疑難排解**。    | 存取使用者設定檔頁面，以在通話分析中疑難排解通話。 只能查看要搜尋之特定使用者的使用者資訊。<sup>2</sup> <br><br> 使用在通話品質儀表板或 CQD (中公開的資料，存取、監控及疑難排解租使用者) 。 |
| Teams裝置系統管理員              | 管理已配置為與服務Teams裝置。                    | 管理裝置設定與更新、檢查裝置健康情況與已連接周邊裝置的狀態、設定及套用設定設定檔，以及重新開機裝置。<p>Teams系統管理員角色不提供通話品質資料或通話分析的存取權。 若要查看通話品質資料或通話分析，您必須獲得通訊Teams管理員角色。 |

<sup>1</sup> [PowerShell - Microsoft Teams (](https://www.powershellgallery.com/packages/MicrosoftTeams/)公開版本 1.1.6 或更新版本已與 商務用 Skype 連接器.) <br>
<sup>2</sup> [Microsoft Teams系統](./manage-teams-skypeforbusiness-admin-center.md)管理中心 
 <sup>3</sup> Teams系統管理員帳戶必須擁有有效的Teams授權。
<!-- <sup>3</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>4</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
有關可用於管理帳戶的管理工具Microsoft Teams，請參閱[管理Microsoft Teams。](./manage-teams-skypeforbusiness-admin-center.md)

若要進一Teams限制、規格及其他需求，請參閱適用于 Microsoft Teams[的限制Microsoft Teams。](limits-specifications-teams.md)

## <a name="assign-users-to-each-role"></a>將使用者指派給每個角色

您可以在 Azure AD 中將使用者指派給這些角色。 若要瞭解如何在 Azure AD 中指派系統管理角色給使用者，請參閱在 Azure Active Directory 中指派[使用者至系統管理員Azure Active Directory。](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)

## <a name="cmdlets-available-for-each-role"></a>每個角色可用的 Cmdlet

這些系統管理員角色的 PowerShell 工具大多都位在 Teams PowerShell 模組中，因此請注意，這些系統管理員角色可存取的一些 Cmdlet 可控制 商務用 Skype Online 也使用的共用設定。 

若要查看 Cmdlet 的完整清單：

```powershell
Get-Command -Module MicrosoftTeams
 ```

### <a name="related-topics"></a>相關主題

- [Microsoft TeamsPowerShell 概觀](teams-powershell-overview.md)
- [Microsoft TeamsPowerShell](/powershell/module/teams/?view=teams-ps)
- [在 Microsoft Teams 中指派 Teams 擁有者和成員](./assign-roles-permissions.md)
