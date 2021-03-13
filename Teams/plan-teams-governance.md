---
title: 在 Teams 中規劃管理 - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 本文將瞭解如何在 Teams 中規劃如何執行管理功能。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 38e51b85e7ecf8efc61c6ca78ca16e4366372885
ms.sourcegitcommit: da2a70a9b5e05d0fd7ecc150b451f5805667514c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2021
ms.locfileid: "50756229"
---
# <a name="plan-for-governance-in-teams"></a>Teams 中的控管方案

Teams 提供豐富的工具，可實施貴組織可能需要的任何管理功能。 本文會引導 IT 專業人員提出正確的問題，以判斷其監管需求，以及如何符合這些需求。 

> [!Tip] 
> 觀看下列會話以深入瞭解 Microsoft Teams 中的管理[：Microsoft Teams](https://aka.ms/teams-governance)中的管理、管理和生命週期

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>群組和團隊建立、命名、分類和來賓存取

您的組織可能會要求您對團隊的命名與分類方式、來賓是否可以新增為團隊成員，以及誰可以建立團隊，進行嚴格控制。 您可以使用 Azure Active Directory 和 Azure AD (和敏感度) 設定這些區域。 

<br>

|-        |-        |-        |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |決策點|<ul><li>您的組織是否需要團隊的特定命名慣例？</li><li>團隊創作者需要將組織特定的分類指派給團隊嗎？</li><li>您需要根據每個團隊限制將來賓新增到團隊的能力嗎？</li><li>您的組織是否需要限制誰可以建立團隊？</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|後續步驟|<ul><li>記錄貴組織建立團隊、命名、分類和來賓存取的需求。</li><li>規劃在 Teams 推出時執行這些需求。</li><li>溝通併發布您的政策，讓 Teams 使用者瞭解他們預期的行為。</li></ul>|

> [!NOTE]
> 若要協助您提前規劃， [請深入瞭解如何設定這些策略，以及需要哪些授權](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)。
> 
> [!NOTE]
> 限制群組和團隊建立可能會降低使用者的生產力，因為許多 Microsoft 365 和 Office 365 服務都需要建立群組，才能讓服務運作。 有關其他資訊，請流覽至並展開 [為什麼控制建立 Microsoft 365 群組的人](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)。


#### <a name="additional-information"></a>其他資訊

決定需求之後，您可以使用 Azure AD 控制項來將其實施。 有關如何執行這些設定的技術指引，請參閱：

- [用於設定群組設定之 Azure Active Directory Cmdlet](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)

- [在 Azure Active Directory 中針對 Microsoft 365 群組強制執行命名策略](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)

- [Microsoft 365 群組命名政策](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

- [使用敏感度標籤來保護 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站中的內容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

- [群組、團隊和 Yammer 的生命週期結束選項](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)

## <a name="group-and-team-expiration-retention-and-archiving"></a>群組和團隊到期、保留和存檔

貴組織可能對於設定到期、保留和存檔團隊和團隊資料、頻道訊息和頻道檔案 (設定額外) 。 您可以設定群組到期政策，以自動管理群組的生命週期和保留原則，以視需要保留或刪除資訊，也可以將團隊 (設為唯讀模式) ，以保留不再使用中團隊的時間點模式。 請注意，已存檔的團隊會繼續使用到期原則，除非已排除或續約，否則可能會被刪除。

|-          |-           |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>您的組織是否需要指定團隊的到期日？</li><li>您的組織是否需要將特定的資料保留原則適用于團隊？</li><li>您的組織預期需要能夠將非使用中的團隊存檔，才能將內容保留為唯讀狀態嗎？</li></ul>|
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>記錄貴組織對於團隊到期日、資料保留和存檔的需求。</li><li>規劃在 Teams 推出時執行這些需求。</li><li>溝通併發布您的政策，讓 Teams 使用者瞭解他們預期的行為。</li></ul>|

> [!TIP]
> 使用下表來記錄貴組織的需求。

|功能 |詳細資料 |需要 Azure AD Premium 授權 |決策 |
|---------|---------|---------|---------|
|到期政策 |設定到期政策來管理 Microsoft 365 群組的生命週期。 |P1 |待定|
|保留政策 |在安全性與合規性中心設定 Teams 的保留&資料。 **注意**：使用此功能需要 Microsoft 365 或 Office 365 企業版 E3 或更新版的授權。 |否 |待定 |
|存檔和還原 |當團隊不再作用中，但您想要保留該團隊供參考或日後重新啟用時，請將其存檔。 |否 |待定 |

> [!Note]
> 群組到期是 Azure AD Premium 功能。 若要使用此功能，您的租使用者必須擁有 Azure AD Premium 的訂閱，以及設定及受影響群組成員的系統管理員授權。

#### <a name="additional-information"></a>其他資訊

有關如何執行這些設定的技術指引，請參閱：

- [設定 Microsoft 365 群組到期](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)。

- [設定 Teams 保留政策](retention-policies.md)。

- [存檔或還原團隊](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)。

## <a name="group-and-team-membership-management"></a>群組和小組成員資格管理

對於需要快速上機和登出的團隊，或使用者和來賓，需要一致地管理專案成員或受限制的群組。 您的組織可能也需要確認目前所有成員都有業務理由可以組成團隊。 管理成員可能比較困難，因為團隊擁有者可以離開，而使用者通常不會在專案結束時或變更角色時自行離開群組。 管理群組成員資格，讓使用者可于需要時取得存取權，但確保群組沒有不當存取的風險，最好的方式就是透過兩個區程式：權利管理和存取審查。

[權益管理](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) 可讓您委派給專案經理等人員，以收集所有所需的資源，包括團隊成員資格，並整合成單一套件。 他們也可以定義誰可以提出要求：租使用者中的使用者或其他已連接的組織。 專案經理將會收到電子郵件中的存取要求，並核准或拒絕 MyAccess 入口網站中的要求。 除非續約存取，否則系統管理員可以設定存取的條件，以包含使用者或來賓從團隊中移除的到期日或期間。 系統管理員也可以設定與團隊相關聯的群組，以參與存取審查。 針對 [存取權審查](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)，群組擁有者會收到定期提醒，以評論團隊成員。 Access 評論包含建議，讓群組擁有者能更輕鬆地完成一般證明程式。

|-|-|-|
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | 決策點 | 您的組織是否需要一致的程式來管理一或多個團隊的成員資格？ <br> 貴組織是否需要擁有者或成員本身，以證明他們定期擁有一或多個團隊的成員資格？ <br> 您的組織是否需要核准使用者和來賓，以要求存取團隊、群組、SharePoint 網站和應用程式等資源？ |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| 下一個步驟？ | 記錄您組織對於每個團隊或特定團隊的成員資格到期需求。<br>規劃貴組織如何將小組、群組、SharePoint 網站和應用程式組合在存取套件中。<br>規劃哪些人員需要核准或拒絕存取要求，例如要求人的主管、專案經理、關係企業贊助商或貴組織的安全性人員。 |

> [!TIP]
> 使用下表來記錄貴組織的需求。

| 功能 | 詳細資料 | 需要 Azure AD Premium 授權 | 決策 |
|:-|:-|:-|:-|
| Access 評論 | 設定存取權審查，以定期重新認證特定團隊的成員資格 | P2 | 待定 |
| 權利管理 | 設定存取套件，讓使用者和來賓要求存取團隊 | P2 | 待定 |

> [!NOTE]
> 若要協助您提前規劃， [請深入瞭解他們需要哪些授權](https://azure.microsoft.com/pricing/details/active-directory/)。

### <a name="additional-information"></a>其他資訊

有關如何執行這些設定的技術指引，請參閱：

- [權利管理](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)
- [Access 評論](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a>Teams 功能管理

Teams 的控管與生命週期管理的另一項重要層面，是能夠控制使用者可存取的功能。 您可以在 Microsoft 365 或 Office 365 組織層級或每個使用者管理訊息、會議及通話功能。


|-        |-        |
|---------|---------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>您的組織是否需要限制整個租使用者 Teams 的功能？</li><li>您的組織是否需要限制特定使用者的 Teams 功能？</li></ul>|
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>記錄貴組織在租使用者和使用者層級限制 Teams 功能的需求。</li><li>在 Teams 推出時規劃如何執行您的特定需求。</li><li>溝通併發布您的政策，讓 Teams 使用者瞭解他們預期的行為。</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Teams 功能管理焦點區域

Teams 透過政策提供精細的功能，可控制傳訊、會議、通話和即時活動功能等。 根據預設，或貴組織可要求將不同的原則適用于所有使用者或每個使用者。 

若要瞭解所有設定的詳細清單，包括如何為貴組織執行這些設定的技術指引，請參閱下列文章：

- [管理組織的 Microsoft Teams 設定](enable-features-office-365.md)
- [在轉換至新 Microsoft Teams 系統管理中心期間管理 Teams](manage-teams-skypeforbusiness-admin-center.md)
- [Microsoft Teams 中的私人頻道](private-channels.md)
- [管理 Teams 中的會議原則](meeting-policies-in-teams.md)
- [管理 Teams 中的訊息傳遞原則](messaging-policies-in-teams.md)
- [在 Microsoft Teams 系統管理中心管理您的應用程式](manage-apps.md)

此外，您可以設定頻道仲裁，並給予仲裁者功能給特定使用者，讓他們可以控制誰可以建立頻道文章並回復他們。 請參閱在 Microsoft Teams 中設定及 [管理頻道的審核，](manage-channel-moderation-in-teams.md) 以瞭解更多資訊。

## <a name="security-and-compliance"></a>安全性與合規性

Teams 建立在 Microsoft 365 和 Office 365 進位的安全性與合規性功能上，支援稽核與報告、合規性內容搜尋、電子探索、法務保留和保留政策。

> [!Important]
> 如果貴組織有合規性和安全性需求，請查閱 Microsoft Teams 中安全性與合規性概觀一文提供之本主題 [的深入內容](security-compliance-overview.md)。

## <a name="related-topics"></a>相關主題

[Teams 的控管快速入門](teams-adoption-governance-quick-start.md) (英文)

[Microsoft 365 安全性與合規性&指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
