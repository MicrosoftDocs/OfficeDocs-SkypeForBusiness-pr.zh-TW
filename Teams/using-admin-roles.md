---
title: 使用 Microsoft Teams 系統管理員角色來管理 Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: 瞭解如何使用系統管理角色來指定需要不同層級存取權限的系統管理員來管理 Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 17a8f6e9475355a5ee0f8960294bf3589d228ed1
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615449"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>使用 Microsoft Teams 系統管理員角色來管理 Teams

使用 Azure Active Directory (Azure AD) ，您可以指定需要不同層級存取才能管理 Microsoft Teams 的系統管理員。 系統管理員可以管理整個 Teams 工作負載，也可以擁有針對通話品質問題進行疑難排解或管理貴組織電話語音需求的委派許可權。

## <a name="teams-roles-and-capabilities"></a>Teams 角色和功能

有數個 Teams 系統管理員角色可供使用：Teams 系統管理員、Teams 通訊系統管理員、Teams 通訊支援專家、Teams 通訊支援工程師，以及 Teams 裝置系統管理員。 請檢閱下表，瞭解每個角色可以做什麼，以及系統管理員可以在 Microsoft Teams 系統管理中心和 PowerShell 中使用哪些工具。

> [!NOTE]
> 商務用 Skype Online 系統管理員可以透過 PowerShell 同時管理 **Teams** 和 **商務用 Skype Online** 應用程式原則。

若要追蹤，您必須是系統管理員。取得許可權的指示請參閱本文。

<!-- add Global admin role? -->

| 角色                                    | 可以執行這些工作                                                           | 可以存取下列工具                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Teams 系統管理員             | 管理 Teams 服務，以及管理和建立Microsoft 365 群組。        | Microsoft Teams 系統管理中心內的所有專案以及相關聯的 PowerShell 控制項，包括：<ul><li> 管理會議，包括會議原則、設定和會議橋接器。<sup>1，2</sup></li><li>管理語音，包括通話原則和電話號碼庫存和指派。<sup>1，3</sup></li><li>管理訊息中心，包括訊息原則。<sup>1，2</sup></li><li>管理全組織設定，包括同盟、團隊升級和團隊用戶端設定。<sup>1，2</sup></li><li>管理組織中的團隊及其相關設定，包括透過 PowerShell 支援的成員資格 (群組管理、Teams 系統管理中心的團隊管理) 。<sup>1，2</sup></li><li>管理 Teams 認證的裝置，並設定和指派組態原則。<sup>1</sup></li><li>使用進階疑難排解工具組，檢視使用者設定檔頁面並疑難排解使用者通話品質問題。<sup>2</sup> </li><li>存取 Microsoft Teams 系統管理中心的所有報告</li><li> 使用 [通話品質儀表板] (CQD 中所公開的資料，存取、監視及疑難排解租使用者的通話品質及可靠性，) 降低到受通話品質不佳影響的使用者。 視需要建立新的通話品質報告、更新和移除通話品質報告。 上傳和更新 CQD 建築物資料。</li><li> [在 Microsoft Teams 系統管理中心將應用程式發佈到租使用者應用程式目錄](manage-apps.md)</li></ul> |
| Teams 通訊系統管理員      | 管理 Teams 服務中的通話和會議功能。               | 管理會議，包括會議原則、設定和會議橋接器。<sup>1，2</sup><br><br> 管理語音，包括通話原則和電話號碼庫存和指派。<sup>1，3</sup><br><br> 使用進階疑難排解工具組來檢視使用者設定檔頁面，並疑難排解使用者通話品質問題。<sup>2</sup> <br><br> 使用 [通話品質儀表板] (CQD 中所公開的資料，存取、監視及疑難排解租使用者的通話品質和可靠性，) 降低到受通話品質不佳影響的使用者。 視需要建立新的通話品質報告、更新和移除通話品質報告。 上傳和更新 CQD 建築物資料。|
| Teams 通訊支援工程師   | 使用 **進** 階工具疑難排解 Teams 內的通訊問題。 | 使用進階疑難排解工具組，檢視使用者設定檔頁面並疑難排解使用者通話品質問題。<sup>2</sup> <br><br> 使用 [通話品質儀表板] (CQD 中所公開的資料，存取、監視及疑難排解租使用者的通話品質和可靠性，) 降低到受通話品質不佳影響的使用者。 |
| Teams 通訊支援專家 | 使用 **基本** 工具疑難排解 Teams 內的通訊問題。    | 在 Call Analytics 中針對通話進行疑難排解的存取使用者設定檔頁面。 只能檢視搜尋特定使用者的使用者資訊。<sup>2</sup> <br><br> 使用 [通話品質儀表板] (CQD) 中公開的資料，存取、監視及疑難排解租使用者的通話品質和可靠性。 |
| Teams 裝置系統管理員              | 管理設定為搭配 Teams 服務使用的裝置。                    | 管理裝置設定和更新、檢閱連接周邊裝置的裝置健康情況和狀態、設定和套用組態設定檔，以及重新開機裝置。<p>Teams 裝置系統管理員角色不提供通話品質資料或通話分析的存取權。 若要檢視通話品質資料或通話分析，您必須獲派 Teams Communications 系統管理員角色。 |

<sup>1</sup> [PowerShell - Microsoft Teams 模組](https://www.powershellgallery.com/packages/MicrosoftTeams/) (公開發行 1.1.6 或更新版本已與 商務用 Skype Online Connector.) 整合<br>
<sup>2</sup> [Microsoft Teams 系統管理中心](./manage-teams-skypeforbusiness-admin-center.md) 
 <sup>3</sup> Teams 系統管理員帳戶必須具備有效的 Teams 授權。
<!-- <sup>3</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>4</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
如需有關可用來管理 Microsoft Teams 的系統管理工具的詳細資訊，請參閱 [管理 Microsoft Teams](./manage-teams-skypeforbusiness-admin-center.md)。

如需適用于 Teams 的限制、規格及其他需求的詳細資訊，請參閱 [Microsoft Teams 的限制和規格](limits-specifications-teams.md)。

## <a name="assign-users-to-each-role"></a>指派使用者給每個角色

您可以在 Azure AD 中指派使用者擔任這些角色。 若要瞭解如何在 Azure AD 中指派系統管理角色給使用者，請參閱 [在 Azure Active Directory 中指派使用者給系統管理員角色](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。

## <a name="cmdlets-available-for-each-role"></a>每個角色都可使用 Cmdlet

這些系統管理員角色的大部分 PowerShell 工具都存在於 Teams PowerShell 模組中，請務必注意，這些系統管理員角色可存取某些 Cmdlet，以控制也用於 商務用 Skype Online 的共用設定。 

若要檢視 Cmdlet 的完整清單：

```powershell
Get-Command -Module MicrosoftTeams
 ```

### <a name="related-articles"></a>相關文章

- [Microsoft Teams PowerShell 概觀](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](/powershell/module/teams/)
- [在 Microsoft Teams 中指派 Teams 擁有者和成員](./assign-roles-permissions.md)
