---
title: 使用 Microsoft 團隊管理員角色管理團隊
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/19/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1keywords:
- ms.teamsadmincenter.errorpage.needadminpermsforadmincenter.assignadminrolesarticle
- ms.teamsadmincenter.errorpage.needadminperms.assignadminrolesarticle
- ms.teamsadmincenter.signin.error.nopermissions
- ms.teamsadmincenter.directrouting.cqd
ms.reviewer: islubin
description: 瞭解如何使用不同的管理角色來管理團隊。
appliesto:
- Microsoft Teams
ms.openlocfilehash: b0bc064e6f01b215f4af53a3e7cb51f2b529cd4a
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483877"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>使用 Microsoft 團隊管理員角色管理團隊

使用 Azure Active Directory (Azure AD), 您可以指定管理員需要不同層級的存取權來管理 Microsoft 團隊。 系統管理員可以管理整個小組的工作負荷, 或者他們可以擁有委派許可權, 以解決通話品質問題或管理組織的電話需求。 

## <a name="teams-roles-and-capabilities"></a>小組角色和功能

共有四個團隊管理員角色可供使用: 團隊服務管理員、團隊溝通系統管理員、團隊溝通支援專家, 以及團隊溝通支援工程師。 請參閱下表, 瞭解每個角色可以執行的動作, 以及系統管理員可在 Microsoft 團隊系統管理中心和 PowerShell 中使用哪些工具。



<!-- add Global admin role? -->

| 角色 | 可以執行這些工作 | 可以存取下列工具 |
|----- | ------------------ | ------------------------------ |
| 團隊服務管理員 | 管理團隊服務, 以及管理和建立 Office 365 群組 | Microsoft 團隊系統管理中心及相關聯的 PowerShell 控制項中的所有專案, 包括:<ul><li> 管理會議, 包括會議原則、設定及會議橋。<sup>1、3</sup></li><li>管理語音, 包括通話原則和電話號碼庫存與作業。<sup>1</sup></li><li>管理訊息, 包括訊息原則。<sup>1、3</sup></li><li>管理所有組織範圍的設定, 包括同盟、團隊升級及團隊用戶端設定。<sup>1, 3</sup></li><li>管理組織中的團隊及其相關設定, 包括成員資格 (透過 PowerShell 支援的群組管理、團隊系統管理中心的小組管理)。<sup>23</sup></li><li>使用高級疑難排解工具組來查看使用者設定檔頁面, 並疑難排解使用者通話品質問題。<sup>3</sup> </li><li> 使用在通話品質儀表板 (CQD) 中公開的資料來存取、監控及解答租使用者的通話品質與可靠性, 並將這些資料暴露在因通話品質不佳的影響。 視需要建立新報表、更新及移除報表。 上傳並更新 CQD 建立資料。</li><li> [從團隊用戶端將 app 發佈至租使用者應用程式目錄](https://docs.microsoft.com/microsoftteams/tenant-apps-catalog-teams)</li></ul> |
| 團隊溝通系統管理員 | 管理小組服務中的通話和會議功能。 | 管理會議, 包括會議原則、設定及會議橋。<sup>1、3</sup><br><br> 管理語音, 包括通話原則和電話號碼庫存與作業。<sup>1</sup><br><br> 使用高級疑難排解工具組來查看使用者設定檔頁面, 並疑難排解使用者通話品質問題。<sup>3</sup> <br><br> 使用在通話品質儀表板 (CQD) 中公開的資料, 向受到不良通話品質影響的使用者進行存取、監控及疑難排解租使用者的通話品質與可靠性。 視需要建立新報表、更新及移除報表。 上傳並更新 CQD 建立資料。|
| 團隊溝通支援工程師 | 使用 [**高級**工具] 來疑難排解團隊中的通訊問題。 | 使用高級疑難排解工具組來查看使用者設定檔頁面, 並疑難排解使用者通話品質問題。<sup>3</sup> <br><br> 使用在通話品質儀表板 (CQD) 中公開的資料, 向受到不良通話品質影響的使用者進行存取、監控及疑難排解租使用者的通話品質與可靠性。 |
| 團隊溝通支援專家 | 使用**基本**工具來疑難排解團隊中的通訊問題。| Access 使用者設定檔頁面, 可讓您在通話分析中排除通話的問題。 只能針對搜尋的特定使用者查看使用者資訊。<sup>3</sup> <br><br> 使用在通話品質儀表板 (CQD) 中公開的資料, 存取、監控並解答租使用者的通話品質與可靠性問題。  

<sup>1</sup> [PowerShell-商務用 Skype 模組](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
<sup>2</sup> [PowerShell-Microsoft 團隊模組](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3</sup> [Microsoft 團隊系統管理中心](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>4</sup> Azure Active Directory admin center <<note that these are going to come later because they’re related to O365 Group management>> 
<sup>5</sup> Microsoft 365 Admin Center <<note that these are going to come later because they’re related to O365 Group management>> 
-->
如需管理 Microsoft 團隊可用之系統管理工具的詳細資訊, 請參閱[管理 Microsoft 團隊](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)。

如需適用于團隊之限制、規格及其他需求的詳細資訊, 請參閱[Microsoft 團隊的限制與規格](limits-specifications-teams.md)。

## <a name="assign-users-to-each-role"></a>將使用者指派給每個角色

您可以將使用者指派給 Azure AD 中的這些角色。 若要瞭解如何將系統管理角色指派給 Azure AD 中的使用者, 請參閱[將使用者指派給 Azure Active Directory 中的系統管理員角色](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。

## <a name="cmdlets-available-for-each-role"></a>每個角色可用的 Cmdlet

在商務用 Skype PowerShell 模組中, 這些系統管理員角色的大部分 PowerShell 工具都很重要, 請務必注意, 這些系統管理員角色的一些 Cmdlet 都有權控制共用設定, 也適用于商務用 Skype Online。 商務用 Skype 系統管理員角色也可以存取商務用 Skype PowerShell 模組中的所有 Cmdlet。

若要在商務用 Skype PowerShell 模組中查看指定角色目前可用的 Cmdlet 完整清單, 請依照下列步驟進行:

1. 指派該角色給使用者 (並確定該使用者沒有其他角色)。
2. 連接到商務用 Skype PowerShell 模組:<br>
   是. $session = new-csonlinesession<br>
   乙. 匯入-pssession $session<br>
   c-clip. 使用 [**取得模組**] 識別匯入會話的名稱 (它將是隨機產生的名稱)。<br>
3. 使用上方的 [**取得命令模組** <*名稱*]> 來找出所有可用的 Cmdlet

### <a name="related-topics"></a>相關主題

- [Microsoft 團隊 PowerShell 概覽](teams-powershell-overview.md)
- [Microsoft 團隊 PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
- [在 Microsoft 團隊中指派小組擁有者和成員](https://docs.microsoft.com/microsoftteams/assign-roles-permissions)

