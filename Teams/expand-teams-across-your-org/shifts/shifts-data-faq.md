---
title: Shifts 資料常見問題
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: 取得有關 Shifts 資料的常見問題解答，包括班次資料的儲存位置、資料保留、擷取和加密。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f05ba56086a9c9dd3cbad046c1cfad34733ee2ee
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268188"
---
# <a name="shifts-data-faq"></a>Shifts 資料常見問題

本文涵蓋有關 Shifts 資料的常見問題，包括班次資料的儲存位置、資料保留、擷取和加密。

## <a name="where-is-shifts-data-stored"></a>Shifts 資料儲存在哪裡？

Shifts 資料會儲存在三個地理位置 () 的其中一個：亞太地區 (APAC) 、歐盟 (歐盟) 或美國。 每個地理位置至少會將資料儲存在兩個 Azure 資料中心區域，以用於高可用性 (HA) 和災害復原 (DR) 。 目前，美國/北美洲使用中南部美國的資料中心。 若要深入瞭解，請參閱 [Microsoft 365 客戶資料的儲存位置](/microsoft-365/enterprise/o365-data-locations)。

目前，Shifts 提供澳洲、加拿大、法國、日本和英國的資料居住地。 我們正積極努力將支援擴充到更多位置。

## <a name="can-i-choose-where-shifts-data-is-stored"></a>我可以選擇儲存 Shifts 資料的位置嗎？

第一次設定 Teams 時，您會選擇訂閱等級所設定的國家或地區。 如果我們支援該地區，Shifts 會遵守此選取範圍，並使用 Teams 中設定的地區和地區。 如果我們還不在該區域，我們會將資料儲存在我們支援的鄰近地區。 在未來，我們計畫將現有資料，如果儲存在鄰近地區，移轉到 Teams 中布建的地區。

## <a name="can-i-access-and-export-or-delete-a-users-personal-data-in-shifts"></a>我可以在 Shifts 中存取及匯出或刪除使用者的個人資料嗎？

Shifts 是一般資料保護規定， (GDPR) 規範。  (稱為資料主體) 對其個人資料採取動作的正式要求稱為資料主體要求 (DSR) 。 您可以在 Shifts 中尋找及處理個人資料，以回應 DSR。

您可以在Microsoft Purview 合規性入口網站中使用內容搜尋電子檔探索工具，搜尋排程和時鐘資料並匯出至 Excel。 針對所有其他 Shifts 資料，您可以擷取資料的螢幕擷取畫面。

若要深入瞭解，[請參閱Office 365 GDPR 和 CCPA 的資料主體要求](/microsoft-365/compliance/gdpr-dsr-office365)。

## <a name="what-happens-to-shifts-data-if-i-turn-off-shifts-for-my-organization"></a>如果我關閉組織的 Shifts，Shifts 資料會發生什麼情況？

關閉貴組織中的班次 *並不會* 刪除資料。 如果您關閉 Shifts，然後再開啟 Shifts，您的 Shifts 資料仍然可以使用。

如果您刪除租使用者，所有 Shifts 資料都會在保留期間結束後刪除。

沒有只刪除 Shifts 資料的選項。 如果您在 Teams 中刪除團隊，則會在保留期間結束後刪除與該團隊相關聯的班次排程資料。 若要深入瞭解，請參閱 [Microsoft 365 中的資料保留、刪除和破壞](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)。

## <a name="can-i-recover-a-shifts-schedule-that-was-deleted"></a>我可以復原已刪除的班次排程嗎？

如果支援排程的 Microsoft 365 群組 (或 Teams) 中的團隊已還原，您可以復原已刪除的排程。

根據預設，已刪除的 Microsoft 365 群組會保留 30 天。 此 30 天期間稱為「虛刪除」，因為您仍然可以還原群組。 若要深入瞭解，請參閱 [還原已刪除的 Microsoft 365 群組](/microsoft-365/admin/create-groups/restore-deleted-group?tabs=admin-center)。

## <a name="can-i-use-custom-retention-policies-for-shifts-data"></a>我可以針對 Shifts 資料使用自訂保留原則嗎？

目前，Shifts 不支援自訂保留原則。

若要深入瞭解 Teams 中的保留原則，請參閱 [瞭解 Teams 的保留](/microsoft-365/compliance/retention-policies-teams) 以及 [管理 Teams 的保留原則](../../retention-policies.md)。

## <a name="can-i-retrieve-shifts-data-for-a-user-whose-license-was-revoked"></a>我可以擷取已撤銷授權之使用者的 Shifts 資料嗎？

今天，我們無法為已撤銷授權的使用者提供擷取資料的功能。 我們正在努力開發這項功能。

## <a name="what-type-of-encryption-does-shifts-use-for-data-at-rest-and-in-transit"></a>Shifts 在休憩和傳輸中的資料使用何種類型的加密？

Shifts 資料會由 Azure 大體 DB 和 Azure 儲存空間加密。 若要深入瞭解，請參閱 [休息時的 Azure 資料加密](/azure/security/fundamentals/encryption-atrest) 和 [Azure 共同作業 DB 中的資料加密](/azure/cosmos-db/database-encryption-at-rest)。

Shifts 遵循 Microsoft 365 在傳輸中加密資料的指導方針。 若要深入瞭解，請參閱資料傳輸 [中的加密](/compliance/assurance/assurance-encryption-in-transit)。

待用和傳輸中資料的 Shift 加密會每年由 SOC2 合規性稽核進行驗證。

## <a name="can-i-access-immutable-copies-of-shifts-data"></a>我可以存取無法停用的 Shifts 資料複本嗎？

我們不會儲存無法停用的 Shifts 資料複本。 例如，主管可以變更排程，例如新增附注、變更班次時間、指派工作等。

## <a name="can-shifts-data-be-edited"></a>可以編輯 Shifts 資料嗎？

班次的某些層面無法變更，某些方面可以變更。 例如，您可以編輯筆記和色彩等班次詳細資料，類似在 Shifts 應用程式中變更的方式。 除非撤銷要求，否則無法編輯 Shift 要求。

若要查看哪些欄位已變更，您可以搜尋 Microsoft 365 稽核記錄中的 Shifts 事件。 若要深入瞭解 Microsoft 365 稽核記錄中針對 Shifts 活動所記錄的事件，請參閱 [Teams 活動中的班次](../../audit-log-events.md#shifts-in-teams-activities)。

## <a name="my-organization-uses-a-workforce-management-system-for-scheduling-can-we-integrate-with-and-access-shifts-data"></a>我的組織使用人力管理系統來排程。 我們可以與 Shifts 資料整合及存取嗎？

Shifts Graph API 可讓您將 Shifts 資料與外部員工管理 (WFM) 系統整合。 若要深入瞭解，請參閱 [Shifts Graph API](/graph/api/resources/shift)。

我們也提供受管理的 Shifts 連接器和開放原始的 Shifts 連接器。 透過這些連接器，您可以直接將WFM系統與 Shifts 整合。 若要深入瞭解 Shifts 連接器和支援WFM系統，請參閱[Shifts 連接器](shifts-connectors.md)。

## <a name="can-shifts-data-be-deleted-permanently-after-a-specified-period-of-time"></a>Shifts 資料可以在指定的一段時間後永久刪除嗎？

今天，我們完全不會刪除您的 Shifts 資料。 使用 [Shifts Graph API](/graph/api/resources/shift)，您可以 [使用 Power Apps 建立應用程式](/powerapps/maker/) ，將資料保留一段指定的時間。 不過，我們不以原生方式支援此功能。

## <a name="can-shifts-data-be-moved-in-a-tenant-to-tenant-migration"></a>Shifts 資料可以在租使用者對租使用者移轉中移動嗎？

根據特定要求，您可以將班次資料從一個租使用者移轉到另一個租使用者。 請記住，不支援租使用者對租使用者移轉，但可以提出為客戶要求。

## <a name="related-articles"></a>相關文章

- [Teams 中的 Shifts](../shifts-for-teams-landing-page.md)
- [管理 Shifts 應用程式](manage-the-shifts-app-for-your-organization-in-teams.md)
