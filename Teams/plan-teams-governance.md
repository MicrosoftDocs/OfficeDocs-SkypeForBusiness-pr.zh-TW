---
title: 在小組中規劃管理-Microsoft 團隊
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.openlocfilehash: ea48b4df3313784cf129cf483aebac341917cb21
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656354"
---
# <a name="plan-for-governance-in-teams"></a>Teams 中的控管方案

團隊會提供一組豐富的工具來實施貴組織可能需要的任何管轄功能。 本文將指導 IT 專業人員提出正確的問題，以決定其管理需求，以及如何滿足他們的需求。 

> [!Tip] 
> 請觀看下列會話，深入瞭解 Microsoft 團隊中的管轄：[管理、管理與生命週期](https://aka.ms/teams-governance)

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>群組和小組建立、命名、分類和來賓存取

您的組織可能會要求您在小組命名及分類的方式上執行嚴格的控制，您可以將來賓新增為小組成員，以及誰可以建立團隊。 您可以使用 Azure Active Directory (Azure AD) 來設定這些區域。 

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
> 限制群組和小組建立可能會降低使用者的生產力，因為許多 Microsoft 365 和 Office 365 服務都需要建立群組才能正常運作。 如需其他資訊，請流覽並展開[控制誰能建立 Microsoft 365 群組的原因](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)。


#### <a name="additional-information"></a>其他資訊

在您決定需求之後，您可以使用 Azure AD 控制項來實現它們。 如需如何實現這些設定的技術指導方針，請參閱：

- [Azure Active Directory Cmdlet，用於設定群組設定](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)。

- [在 Azure Active Directory 中強制執行 Microsoft 365 群組的命名原則](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)。

- [Microsoft 365 群組命名原則](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。


## <a name="group-and-team-expiration-retention-and-archiving"></a>群組和小組到期、保留及封存

您的組織可能對設定到期、保留及封存團隊及小組資料 (通道訊息及) 通道檔案的其他需求。 您可以設定群組過期原則來自動管理群組和保留原則的生命週期，以根據需要保留或刪除資訊，而且您可以將團隊封存 (將其設為唯讀模式) ，以保留不在使用中的小組的時間點視圖。

|           |            |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>貴組織是否需要指定團隊的到期日？</li><li>貴組織是否需要將特定的資料保留原則套用至團隊？</li><li>貴組織是否希望能夠封存不活躍的小組，以保持內容處於唯讀狀態？</li></ul>|
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>記錄貴組織的小組到期、資料保留及封存需求。</li><li>規劃將這些需求作為您團隊推出的一部分來執行。</li><li>溝通及發佈您的原則，以告知小組使用者他們可以預期的行為。</li></ul>|

> [!TIP]
> 使用下表來捕獲貴組織的需求。

|功能 |詳細資料 |需要 Azure AD Premium 授權 |決議 |
|---------|---------|---------|---------|
|過期原則 |設定過期原則，管理 Microsoft 365 群組的週期。 |P1 |TBD|
|保留原則 |在安全性 & 合規性中心設定小組的保留原則，以保留或刪除特定時段內的資料。 **注意**：使用這項功能需要授權 Microsoft 365 或 Office 365 Enterprise E3 或更新版本。 |否 |TBD |
|封存和還原 |當小組已不在使用中，但您想要保留以供參考或在將來重新啟用時，請封存團隊。 |否 |TBD |

> [!Note]
> [群組到期] 是 Azure AD Premium 功能。 若要使用此功能，您的租使用者必須具備 Azure AD Premium 的訂閱，以及設定受影響群組之成員之系統管理員的授權。

#### <a name="additional-information"></a>其他資訊

如需如何實現這些設定的技術指導方針，請參閱：

- [設定 Microsoft 365 群組到期](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)日。

- [設定小組保留原則](retention-policies.md)。

- 封存[或還原團隊](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)。

## <a name="group-and-team-membership-management"></a>群組和小組成員資格管理

在需要快速加入和脫離或使用者和來賓的小組中，始終如一地管理以專案為基礎的成員或受限制的群組是必要的。 貴組織也可能需要確保所有目前成員都能在小組中進行業務調整。 管理成員可能很困難，因為小組擁有者可以離開，而且使用者通常不會在專案結束或變更角色時離開群組本身。 管理群組成員資格的最佳方式，可讓使用者在需要時取得存取權，但確定群組沒有不當存取的風險是透過兩個地區流程： [權利管理與存取權審查]。

[[權利管理](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)] 可讓您委派給某個人（例如專案經理），以便將所需的所有資源（包括團隊成員資格）收集到單一套件中。 他們也可以定義誰可以發出要求：您租使用者中的使用者或來自其他已連接的組織。 專案經理將會在其電子郵件中收到存取要求，並在 MyAccess 入口網站中核准或拒絕要求。 系統管理員可以設定 access 的條件，以包含到期日或期間（除非 access 已更新），否則將會從團隊中移除使用者或來賓。 系統管理員也可以設定與團隊相關聯的群組，以參與 access 評論。 針對[access 評論](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)，群組擁有者會收到定期提醒，以查看小組成員。 Access 評論包括建議，讓群組擁有者能更輕鬆地完成標準認證程式。

||||
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | 決策點 | 貴組織需要一致的程式來管理一或多位團隊的成員資格嗎？ <br> 貴組織是否需要擁有者或成員本身，以定期向一或多個小組的持續成員資格進行調整？ <br> 您的組織是否需要核准使用者和來賓要求對資源的存取權，包括團隊、群組、SharePoint 網站和應用程式？ |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| 後續步驟？ | 針對每個小組或特定小組，為成員資格到期記錄您的組織需求。<br>規劃貴組織可以如何將團隊、群組、SharePoint 網站和應用程式捆綁到 access 套件中。<br>規劃哪些人（例如要求者的管理員）、專案經理、連線組織的主辦人或貴組織中的安全專員，都必須核准或拒絕存取要求。 |

> [!TIP]
> 使用下表來捕獲貴組織的需求。

| 功能 | 詳細資料 | 需要 Azure AD Premium 授權 | 決議 |
|:-|:-|:-|:-|
| Access 評論 | 設定存取權審查，以定期 recertify 特定團隊的成員資格 | 又 | TBD |
| 權利管理 | 設定存取套件，讓使用者與客人要求對團隊進行存取權 | 又 | TBD |

> [!NOTE]
> 若要協助您預先規劃，請[進一步瞭解他們所需的授權](https://azure.microsoft.com/pricing/details/active-directory/)。

### <a name="additional-information"></a>其他資訊

如需如何實現這些設定的技術指導方針，請參閱：

- [權利管理](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)
- [Access 評論](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a>團隊功能管理

小組管理與生命週期管理的另一個重要方面，就是控制您的使用者可以存取哪些功能的功能。 您可以在 Microsoft 365 或 Office 365 組織層級或每位使用者，管理訊息、會議和通話功能。


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

團隊是以 Microsoft 365 和 Office 365 的高級安全性與合規性功能為基礎，並支援審核與報告、合規性內容搜尋、電子探索、法律封存及保留原則。

> [!Important]
> 如果您的組織具備合規性與安全性需求，請參閱在[Microsoft 團隊中的安全性與合規性一](security-compliance-overview.md)文中所提供的深入閱讀本主題的內容。

## <a name="related-topics"></a>相關主題

[Teams 的控管快速入門](teams-adoption-governance-quick-start.md) (英文)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
