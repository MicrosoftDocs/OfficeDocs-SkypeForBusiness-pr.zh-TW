---
title: 在小組中規劃管理-Microsoft 團隊
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/10/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 在本文中，您將瞭解如何規劃在團隊中實施系統管理功能。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a196dfee988a41a5d8145d9b6256d1df6e714133
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905825"
---
# <a name="plan-for-governance-in-teams"></a>Teams 中的控管方案

團隊會提供一組豐富的工具來實施貴組織可能需要的任何管轄功能。 本文將指導 IT 專業人員提出正確的問題，以決定其管理需求，以及如何滿足他們的需求。 

> [!Tip] 
> 請觀看下列會話，深入瞭解 Microsoft 團隊中的管轄：[管理、管理與生命週期](https://aka.ms/teams-governance)

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>群組和小組建立、命名、分類和來賓存取

您的組織可能會要求您在小組命名及分類的方式上執行嚴格的控制，您可以將來賓新增為小組成員，以及誰可以建立團隊。 您可以使用 Azure Active Directory （Azure AD）來設定這些區域中的每一個。 

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |決策點|<ul><li>貴組織是否需要適用于團隊的特定命名慣例？</li><li>小組創作者是否需要能夠將組織特定分類指派給團隊？</li><li>您是否需要限制將來賓新增到小組的人員的能力？</li><li>貴組織是否需要限制誰可以建立團隊？</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|後續步驟|<ul><li>記錄貴組織建立、命名、分類和來賓存取的需求。</li><li>規劃將這些需求作為小組推出的一部分來執行。</li><li>溝通及發佈您的原則，以告知小組使用者他們可以預期的行為。</li></ul>|

> [!TIP]
> 使用下表來捕獲貴組織的需求。

|功能 |詳細資料 |Azure AD Premium <br> 需要授權 |決議 |
|---------|---------|---------|---------|
|團隊命名原則 | 使用以前置詞為基礎的自訂封鎖字。 |P1 |TBD |
|小組分類 |指派分類給小組。 |P1 |TBD |
|小組來賓存取 |允許或禁止將來賓新增至小組。 |否 |TBD |
|小組建立 |將小組建立限制為管理員。 |否 |TBD|
|小組建立 |將小組建立限制為安全群組成員。 |P1 |TBD|

> [!NOTE]
> 若要協助您預先規劃，請[進一步瞭解如何設定這些原則以及他們所需的授權](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)。
> 
> [!NOTE]
> 限制群組和小組建立會降低使用者的生產力，因為許多 Office 365 服務都需要建立群組才能正常運作。 如需其他資訊，請流覽並展開[控制誰能建立 Microsoft 365 群組的原因](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)。


#### <a name="additional-information"></a>其他資訊

在您決定需求之後，您可以使用 Azure AD 控制項來實現它們。 如需如何實現這些設定的技術指導方針，請參閱：

- [Azure Active Directory Cmdlet，用於設定群組設定](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)。

- [在 Azure Active Directory 中強制執行 Microsoft 365 群組的命名原則](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)。

- [Microsoft 365 群組命名原則](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。


## <a name="group-and-team-expiration-retention-and-archiving"></a>群組和小組到期、保留及封存

您的組織可能對設定到期、保留及封存團隊與團隊資料（頻道訊息和頻道檔案）的需求有額外需求。 您可以設定群組過期原則，以自動管理群組和保留原則的生命週期，以根據需要保留或刪除資訊，而且您可以將團隊封存（將其設為唯讀模式），以保留不在使用中的小組的時間點視圖。

|           |            |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>貴組織是否需要指定團隊的到期日？</li><li>貴組織是否需要將特定的資料保留原則套用至團隊？</li><li>貴組織是否希望能夠封存不活躍的小組，以保持內容處於唯讀狀態？</li></ul>|
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>記錄貴組織的小組到期、資料保留及封存需求。</li><li>規劃將這些需求作為您團隊推出的一部分來執行。</li><li>溝通及發佈您的原則，以告知小組使用者他們可以預期的行為。</li></ul>|

> [!TIP]
> 使用下表來捕獲貴組織的需求。

|功能 |詳細資料 |需要 Azure AD Premium 授權 |決議 |
|---------|---------|---------|---------|
|過期原則 |設定過期原則，管理 Microsoft 365 群組的週期。 |P1 |TBD|
|保留原則 |在安全性 & 合規性中心設定小組的保留原則，以保留或刪除特定時段內的資料。 **注意**：使用這項功能需要授權 Office 365 Enterprise E3 或更新版本。 |否 |TBD |
|封存和還原 |當小組已不在使用中，但您想要保留以供參考或在將來重新啟用時，請封存團隊。 |否 |TBD |

> [!Note]
> [群組到期] 是 Azure AD Premium 功能。 若要使用此功能，您的租使用者必須具備 Azure AD Premium 的訂閱，以及設定受影響群組之成員之系統管理員的授權。

#### <a name="additional-information"></a>其他資訊

如需如何實現這些設定的技術指導方針，請參閱：

- [設定 Microsoft 365 群組到期](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)日。

- [設定小組保留原則](retention-policies.md)。

- 封存[或還原團隊](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)。


## <a name="teams-feature-management"></a>團隊功能管理

小組管理與生命週期管理的另一個重要方面，就是控制您的使用者可以存取哪些功能的功能。 您可以在 Office 365 的組織層級或每位使用者，管理訊息、會議和通話功能。 


|         |         |
|---------|---------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>貴組織是否需要限制您整個租使用者的小組功能？</li><li>貴組織是否需要限制特定使用者的小組功能？</li></ul>|
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>在租使用者層級中記錄您組織限制小組功能的需求。</li><li>規劃將您的特定需求作為小組推出的一部分來實現。</li><li>溝通及發佈您的原則，以告知小組使用者他們可以預期的行為。</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>團隊功能管理焦點區域

團隊可透過原則提供精確的功能，以控制訊息、會議、通話及即時事件功能等等。 根據貴組織的需求，預設或每位使用者都可以套用不同的原則。 

如需所有設定的詳細清單，包括如何針對您的組織實施相關的技術指導方針，請參閱下列文章：

- [管理組織的 Microsoft Teams 設定](enable-features-office-365.md)
- [在轉換至新 Microsoft Teams 系統管理中心期間管理 Teams](manage-teams-skypeforbusiness-admin-center.md)
- [在團隊中管理會議原則](meeting-policies-in-teams.md)
- [管理小組中的訊息傳遞原則](messaging-policies-in-teams.md)

此外，您可以為頻道設定裁決，並向特定使用者提供仲裁者的功能，讓他們能夠控制誰可以建立頻道發佈及回復。 如需詳細資訊，請參閱[在 Microsoft 團隊中設定和管理 [頻道裁決](manage-channel-moderation-in-teams.md)]。

## <a name="security-and-compliance"></a>安全性與合規性

團隊是以 Office 365 的高級安全性與合規性功能為基礎，並支援審計與報告、合規性內容搜尋、電子探索、法律封存及保留原則。 

> [!Important]
> 如果您的組織具備合規性與安全性需求，請參閱在[Microsoft 團隊中的安全性與合規性一](security-compliance-overview.md)文中所提供的深入閱讀本主題的內容。

## <a name="related-topics"></a>相關主題

[Teams 的控管快速入門](teams-adoption-governance-quick-start.md) (英文)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
