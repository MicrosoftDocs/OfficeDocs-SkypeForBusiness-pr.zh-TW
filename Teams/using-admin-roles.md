---
title: 使用 Microsoft Teams 系統管理員角色管理 Teams
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
description: 瞭解如何使用系統管理角色來指定需要不同層級存取權才能管理 Teams 的系統管理員。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 201cc1d73166825d729b4581d183ea58cfda64af
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093733"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>使用 Microsoft Teams 系統管理員角色管理 Teams

使用 Azure Active Directory (Azure AD) ，您可以指定需要不同層級存取權限的系統管理員來管理 Microsoft Teams。 系統管理員可以管理整個 Teams 工作負載，或者可以委派許可權來疑難排解通話品質問題或管理貴組織的電話需求。

## <a name="teams-roles-and-capabilities"></a>Teams 角色和功能

有幾個 Teams 系統管理員角色可供使用：Teams 服務系統管理員、Teams 通訊系統管理員、Teams 通訊支援專家、Teams 通訊支援工程師和 Teams 裝置系統管理員。 請查閱下表，瞭解每個角色可以執行哪些工作，以及系統管理員可在 Microsoft Teams 系統管理中心和 PowerShell 中使用哪些工具。

若要追蹤，您必須是系統管理員。本文提供取得許可權的指示。

<!-- add Global admin role? -->

| 角色                                    | 可以執行這些工作                                                           | 可以存取下列工具                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Teams 服務管理員             | 管理 Teams 服務，以及管理及建立 Microsoft 365 群組。        | Microsoft Teams 系統管理中心和相關 PowerShell 控制項的所有專案，包括：<ul><li> 管理會議，包括會議策略、組配置和會議橋接器。<sup>1，2</sup></li><li>管理語音，包括通話策略和電話號碼庫存和工作分派。<sup>1</sup></li><li>管理訊息，包括訊息策略。<sup>1，2</sup></li><li>管理所有全組織設定，包括聯盟、團隊升級和 Teams 用戶端設定。<sup>1，2</sup></li><li>管理組織中團隊及其關聯的設定，包括透過 PowerShell 支援的成員資格 (群組管理、Teams 系統管理中心中的團隊管理) 。<sup>1，2</sup></li><li>管理 Teams 認證的裝置，並設定及指派設定策略。<sup>1</sup></li><li>使用進一步疑難排解工具集來查看使用者設定檔頁面及疑難排解使用者通話品質問題。<sup>2</sup> </li><li>存取 Microsoft Teams 系統管理中心的所有報告</li><li> 使用通話品質儀表板 (CQD) 中公開的資料，存取、監控及疑難排解租使用者的通話品質與可靠性) 通話品質不佳影響的使用者。 建立新的通話品質報告，並根據需要更新和移除通話品質報告。 上傳及更新 CQD 建築物資料。</li><li> [在 Microsoft Teams 系統管理中心將應用程式發佈至租使用者應用程式目錄](manage-apps.md)</li></ul> |
| Teams 通訊系統管理員      | 在 Teams 服務中管理通話和會議功能。               | 管理會議，包括會議策略、組配置和會議橋接器。<sup>1，2</sup><br><br> 管理語音，包括通話策略和電話號碼庫存和工作分派。<sup>1</sup><br><br> 使用進一步疑難排解工具集來查看使用者設定檔頁面並疑難排解使用者通話品質問題。<sup>2</sup> <br><br> 使用通話品質儀表板 (CQD) 中公開的資料，存取、監控及疑難排解租使用者的通話品質與可靠性) 低至受到通話品質不佳影響的使用者。 建立新的通話品質報告，並根據需要更新和移除通話品質報告。 上傳及更新 CQD 建築物資料。|
| Teams 通訊支援工程師   | 使用進位工具疑難排解 Teams **中的通訊** 問題。 | 使用進一步疑難排解工具集來查看使用者設定檔頁面及疑難排解使用者通話品質問題。<sup>2</sup> <br><br> 使用通話品質儀表板 (CQD) 中公開的資料，存取、監控及疑難排解租使用者的通話品質與可靠性) 低至受到通話品質不佳影響的使用者。 |
| Teams Communications 支援專員 | 使用基本工具疑難排解 Teams **中的通訊** 問題。    | 存取使用者設定檔頁面，以在通話分析中疑難排解通話。 只能查看要搜尋之特定使用者的使用者資訊。<sup>2</sup> <br><br> 使用在通話品質儀表板或 CQD (中公開的資料，存取、監控及疑難排解租使用者) 。 |
| Teams 裝置系統管理員              | 管理已針對 Teams 服務所配置的裝置。                    | 管理裝置設定和更新、審查已連接之周邊的裝置健康情況與狀態、設定及套用設定設定檔，以及重新開機裝置。<p>Teams 裝置系統管理員角色不提供通話品質資料或通話分析的存取權。 若要查看通話品質資料或通話分析，您必須指派 Teams Communications 系統管理員角色。 |

<sup>1</sup> [PowerShell - Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/) 模組 (公開發行 1.1.6 或更新版本已與商務用 Skype Online Connector.) <br>
<sup>2</sup> [Microsoft Teams 系統管理中心](./manage-teams-skypeforbusiness-admin-center.md)
<!-- <sup>3</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>4</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
有關可用於管理 Microsoft Teams 的管理工具詳細資訊，請參閱 [管理 Microsoft Teams](./manage-teams-skypeforbusiness-admin-center.md)。

有關適用于 Teams 的限制、規格及其他需求詳細資訊，請參閱 Microsoft Teams 的限制 [和規格](limits-specifications-teams.md)。

## <a name="assign-users-to-each-role"></a>將使用者指派給每個角色

您可以在 Azure AD 中將使用者指派給這些角色。 若要瞭解如何在 Azure AD 中指派系統管理角色給使用者，請參閱在 Azure Active Directory 中指派使用者 [至系統管理員角色](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。

## <a name="cmdlets-available-for-each-role"></a>每個角色可用的 Cmdlet

這些系統管理員角色的 PowerShell 工具大多都採用 Teams PowerShell 模組，而且請注意，這些系統管理員角色可存取的一些 Cmdlet 可控制也用於商務用 Skype Online 的共用設定。 

若要查看 Cmdlet 的完整清單：

```powershell
Get-Command -Module MicrosoftTeams
 ```

### <a name="related-topics"></a>相關主題

- [Microsoft Teams PowerShell 概觀](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps)
- [在 Microsoft Teams 中指派 Teams 擁有者和成員](./assign-roles-permissions.md)