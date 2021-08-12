---
title: 在 Teams - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 在本文中，您將瞭解如何規劃在 Teams 中執行Teams。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: f55183b114919048776b7fcb6f39ae6a084c29832652c32f87b97d258fb7f835
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54293070"
---
# <a name="plan-for-governance-in-teams"></a>Teams 中的控管方案

Teams提供一組豐富的工具，以執行貴組織可能需要的任何管理功能。 本文引導 IT 專業人員提出正確的問題，以判斷其管理需求，以及如何符合這些需求。 

> [!Tip] 
> 請觀看下列會話，進一步瞭解如何在 Microsoft Teams 中管理、管理和[生命週期](https://aka.ms/teams-governance)Microsoft Teams

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>群組和團隊建立、命名、分類和來賓存取

貴組織可能會要求您對團隊的命名和分類方式、來賓是否可以新增為小組成員，以及誰可以建立團隊，實行嚴格的控制措施。 您可以使用 Azure AD Azure Active Directory (和敏感度) 來設定這些區域。 

<br>

|-        |-        |-        |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |決策點|<ul><li>貴組織是否需要團隊的特定命名慣例？</li><li>團隊創作者需要將組織特定分類指派給團隊的能力嗎？</li><li>您需要根據每個團隊限制將來賓新增到團隊的能力嗎？</li><li>貴組織是否需要限制誰可以建立團隊？</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|後續步驟|<ul><li>記錄貴組織建立團隊、命名、分類和來賓存取的需求。</li><li>規劃將這些要求作為您推行計畫的一Teams一部分。</li><li>溝通併發布您的Teams，讓使用者瞭解他們預期的行為。</li></ul>|

> [!NOTE]
> 若要協助您提前規劃， [請進一步瞭解如何設定這些策略，以及需要哪些授權](/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)。
> 
> [!NOTE]
> 限制群組和團隊建立可能會降低使用者的生產力，因為許多Microsoft 365 Office 365服務需要建立群組，服務才能運作。 若要瞭解詳細資訊，請流覽至 並展開[為什麼控制誰Microsoft 365群組](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)。


#### <a name="additional-information"></a>其他資訊

在您決定需求之後，您可以使用 Azure AD 控制項來實施需求。 有關如何執行這些設定的技術指南，請參閱：

- [Azure Active Directory Cmdlet 來設定群組設定](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)

- [針對群組中的群組Microsoft 365命名Azure Active Directory](/azure/active-directory/users-groups-roles/groups-naming-policy)

- [Microsoft 365群組命名策略](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

- [使用敏感度標籤來保護網站Microsoft Teams、Microsoft 365群組SharePoint內容](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

- [群組、團隊和團隊的生命週期結束選項Yammer](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)

## <a name="group-and-team-expiration-retention-and-archiving"></a>群組和小組到期、保留和存檔

貴組織可能對於設定到期、保留和存檔團隊和團隊資料 (通道訊息和頻道檔案設定) 。 您可以設定群組到期政策，以自動管理群組的生命週期和保留原則，以視需要保留或刪除資訊，而且您可以將團隊 (設為唯讀模式) ，以保留不再使用中之團隊的時間點視圖。 請注意，已存檔的團隊會繼續採用到期原則，除非排除或續約，否則可能會刪除。

|-          |-           |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>您的組織是否需要為團隊指定到期日？</li><li>貴組織是否需要將特定的資料保留原則適用于團隊？</li><li>貴組織是否預期需要能夠將非使用中團隊存檔，才能將內容保留為唯讀狀態？</li></ul>|
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>記錄貴組織對小組到期、資料保留和存檔的需求。</li><li>規劃將這些要求作為您推行計畫的一Teams一部分。</li><li>溝通併發布您的Teams，讓使用者瞭解他們預期的行為。</li></ul>|

> [!TIP]
> 使用下表來捕獲貴組織的需求。

|功能 |詳細資料 |Azure AD Premium授權 |決策 |
|---------|---------|---------|---------|
|到期政策 |設定到期Microsoft 365管理群組的生命週期。 |P1 |待定|
|保留原則 |在安全性與合規性中心設定資料保留Teams保留&刪除資料。 **注意**：使用這項功能需要授權Microsoft 365或Office 365 企業版 E3 或更新版。 |否 |待定 |
|存檔和還原 |當團隊不再作用中，但您想要保留該團隊供參考，或日後重新啟用時，請將其存檔。 |否 |待定 |

> [!Note]
> 群組到期是Azure AD Premium功能。 若要使用這項功能，您的租使用者必須有一個訂閱，Azure AD Premium設定設定及受影響群組成員的系統管理員的訂閱和授權。

#### <a name="additional-information"></a>其他資訊

有關如何執行這些設定的技術指南，請參閱：

- [設定群組Microsoft 365到期](/azure/active-directory/users-groups-roles/groups-lifecycle)。

- [設定Teams保留原則](retention-policies.md)。

- [將小組存檔或還原](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)。

## <a name="group-and-team-membership-management"></a>群組和小組成員資格管理

對於需要快速上機和登出或使用者和來賓的團隊來說，一致管理專案成員或受限制群組是必要的。 貴組織可能也需要確認所有目前的成員都有商務理由可以組成團隊。 管理成員可能比較困難，因為團隊擁有者可以離開，而使用者通常不會在專案結束時或變更角色時自行離開群組。 管理群組成員資格，讓使用者可于需要時存取，但確保群組沒有不當存取風險的最佳方法，是透過兩個區程式：權利管理和存取審查。

[權利管理](/azure/active-directory/governance/entitlement-management-overview) 可讓您委派給專案經理等人員，以收集所需的所有資源，包括團隊成員資格，到單一套件中。 他們也可以定義誰可以提出要求：租使用者中的使用者或其他已連接組織的使用者。 專案經理會收到電子郵件中的存取要求，並核准或拒絕 MyAccess 入口網站中的要求。 系統管理員可以將存取條件設定為包含到期日或期間，除非已續約存取權，否則使用者或來賓會從團隊中移除。 系統管理員也可以設定與團隊相關聯的群組，以參與存取審查。 針對 [存取審查](/azure/active-directory/governance/access-reviews-overview)，群組擁有者會收到定期提醒，提醒他們檢查小組成員。 Access 評論包含建議，讓群組擁有者能更輕鬆地完成其一般認證程式。

|-|-|-|
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | 決策點 | 貴組織是否需要一致的程式來管理一或多個團隊的成員資格？ <br> 貴組織是否要求擁有者或成員本身定期證明他們繼續擁有一或多個團隊的成員資格？ <br> 貴組織是否需要使用者和來賓核准，要求存取資源，包括團隊、群組、SharePoint網站和應用程式？ |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| 下一個步驟？ | 記錄每個團隊或特定團隊的成員資格到期組織需求。<br>規劃貴組織如何將小組、群組、SharePoint網站和應用程式組合在存取套件中。<br>規劃哪些人員需要核准或拒絕存取要求，例如要求者主管、專案經理、連線組織的贊助者或貴組織的安全性人員。 |

> [!TIP]
> 使用下表來捕獲貴組織的需求。

| 功能 | 詳細資料 | Azure AD Premium授權 | 決策 |
|:-|:-|:-|:-|
| Access 評論 | 設定存取審查以定期重新認證特定團隊的成員資格 | P2 | 待定 |
| 權利管理 | 設定存取套件，允許使用者和來賓要求存取團隊 | P2 | 待定 |

> [!NOTE]
> 若要協助您提前規劃， [請深入瞭解他們需要哪些授權](https://azure.microsoft.com/pricing/details/active-directory/)。

### <a name="additional-information"></a>其他資訊

有關如何執行這些設定的技術指南，請參閱：

- [權利管理](/azure/active-directory/governance/entitlement-management-overview)
- [Access 評論](/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a>Teams功能管理

系統管理與生命週期管理的另一Teams是控制使用者可存取的功能的能力。 您可以管理訊息、會議及通話功能，Microsoft 365或Office 365層級或每個使用者。


|-        |-        |
|---------|---------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>貴組織是否需要限制Teams租使用者的功能？</li><li>貴組織是否需要限制Teams使用者的特定功能？</li></ul>|
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>記錄貴組織限制租使用者Teams使用者層級的功能需求。</li><li>規劃將您的特定需求作為您推行計畫的一Teams一部分。</li><li>溝通併發布您的Teams，讓使用者瞭解他們預期的行為。</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Teams功能管理焦點區域

Teams提供精細的功能，可透過策略控制訊息、會議、通話和即時活動功能等。 根據預設，不同的原則可以適用于所有使用者，也可以根據貴組織的要求，將每個使用者都適用。 

有關所有設定的詳細清單，包括如何為貴組織執行這些設定的技術指南，請參閱下列文章：

- [管理組織的 Microsoft Teams 設定](enable-features-office-365.md)
- [在轉換至新 Microsoft Teams 系統管理中心期間管理 Teams](manage-teams-skypeforbusiness-admin-center.md)
- [Microsoft Teams 中的私人頻道](private-channels.md)
- [管理 Teams 中的會議原則](meeting-policies-in-teams.md)
- [在 Teams 中管理訊息原則](messaging-policies-in-teams.md)
- [在系統管理中心管理Microsoft Teams應用程式](manage-apps.md)

此外，您可以設定頻道的仲裁，並給予特定使用者仲裁者功能，讓他們可以控制誰可以建立頻道文章並回復他們。 詳細資訊[請參閱在](manage-channel-moderation-in-teams.md)Microsoft Teams中設定及管理通道管理。

## <a name="security-and-compliance"></a>安全性與合規性

Teams以 Microsoft 365 和 Office 365 進位安全性和合規性功能為根據，支援稽核與報告、合規性內容搜尋、電子探索、法律保留和保留政策。

> [!Important]
> 如果貴組織有合規性和安全性需求，請于本文的安全性與合規性概觀一文中，查看[本主題](security-compliance-overview.md)提供Microsoft Teams。

## <a name="related-topics"></a>相關主題

[Teams 的控管快速入門](teams-adoption-governance-quick-start.md)

[Microsoft 365安全性與合規性的授權&指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->