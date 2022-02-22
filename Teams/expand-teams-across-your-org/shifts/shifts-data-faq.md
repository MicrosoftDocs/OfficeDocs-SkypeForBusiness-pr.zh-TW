---
title: 班次資料常見問題
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
description: 取得有關 Shifts 資料的常見問題解答，包括 Shifts 資料的儲存位置、資料保留、取回和加密。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2df5c465c9115dce47ee9e80ea649768606c338f
ms.sourcegitcommit: 10bee789272e648ea1e93d7d7c27ec645d0a8bdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/22/2022
ms.locfileid: "62918949"
---
# <a name="shifts-data-faq"></a>班次資料常見問題

本文涵蓋有關 Shifts 資料的常見問題，包括 Shifts 資料的儲存位置、資料保留、取回和加密。

## <a name="where-is-shifts-data-stored"></a>Shifts 資料儲存在哪裡？

Shifts 資料會儲存在三個地理位置 (地理位置) ：亞太地區 (亞太地區) 、歐盟 (歐盟) 或美國。 每個地理位置會將資料儲存在至少兩個 Azure 資料中心區域，以使用高可用性 (HA) 和災害復原 (DR) 。 目前，美國/北美地理位置使用美國中北部和中南部資料中心。 若要深入瞭解，請參閱[儲存Microsoft 365的位置](/microsoft-365/enterprise/o365-data-locations)。

目前，Shifts 提供澳洲、加拿大、法國、日本及英國的資料居住權。 我們正積極努力將支援範圍擴大到更多位置。

## <a name="can-i-choose-where-shifts-data-is-stored"></a>我可以選擇 Shifts 資料的儲存位置嗎？

當您第一次設定Teams，請選擇在訂閱層級設定的國家/地區。 Shifts 會遵守此選取範圍，並使用我們在 Teams 中設定的區域設定和地區。 如果我們尚未位於該區域，我們會將資料儲存在我們支援的鄰近地區。 未來，我們計畫將現有資料 ，如果儲存于鄰近地區，會遷移到在 Teams 中Teams。

## <a name="can-i-access-and-export-or-delete-a-users-personal-data-in-shifts"></a>我可以在 Shifts 中存取及匯出或刪除使用者的個人資訊嗎？

Shifts 是一般資料保護法規 (GDPR) 規範。稱為資料主體 (之人員對) 採取動作的正式要求稱為資料主體要求 (DSR) 。 您可以針對 DSR 在 Shifts 中尋找及處理個人資料。

您可以使用網頁中的內容搜尋電子檔探索工具Microsoft 365 合規性中心搜尋並匯出排程和時鐘資料Excel。 針對所有其他 Shifts 資料，您可以拍攝資料的螢幕擷取畫面。

若要深入瞭解，請參閱[Office 365 GDPR 和 CCPA](/microsoft-365/compliance/gdpr-dsr-office365)的資料主體要求。

## <a name="what-happens-to-shifts-data-if-i-turn-off-shifts-for-my-organization"></a>如果我關閉組織的 Shifts，Shifts 資料會發生什麼情況？

關閉貴組織的班次 *不會* 刪除資料。 如果您關閉 Shifts，然後再開啟 Shifts，您的 Shifts 資料仍然可以使用。

如果您刪除租使用者，保留期間結束後會刪除所有 Shifts 資料。

沒有只刪除 Shifts 資料的選項。 如果您刪除團隊，Teams保留期間結束後，會刪除與該團隊相關聯的 Shifts 排程資料。 若要深入瞭解，請參閱資料[保留、刪除和破壞Microsoft 365](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)。

## <a name="can-i-recover-a-shifts-schedule-that-was-deleted"></a>我可以復原已刪除的班次排程嗎？

如果備份刪除的Microsoft 365群組 (或已還原Teams) 排程。

根據預設，已刪除Microsoft 365群組會保留 30 天。 這 30 天期間稱為「柔刪除」，因為您仍然可以還原群組。 若要深入瞭解，請參閱[還原已刪除Microsoft 365群組](/microsoft-365/admin/create-groups/restore-deleted-group?view=o365-worldwide&tabs=admin-center)。

## <a name="can-i-use-custom-retention-policies-for-shifts-data"></a>我可以使用 Shifts 資料的自訂保留原則嗎？

目前，Shifts 不支援自訂保留政策。

若要深入瞭解 Teams 中的保留Teams，請參閱瞭解保留[Teams管理保留](/microsoft-365/compliance/retention-policies-teams)[Teams。](../../retention-policies.md)

## <a name="can-i-retrieve-shifts-data-for-a-user-whose-license-was-revoked"></a>我可以為授權被撤銷的使用者取回 Shifts 資料嗎？

今天，我們並不提供為授權被撤銷的使用者取回資料的能力。 這項功能是我們正在努力進行的工作。

## <a name="is-shifts-supported-in-government-cloud-community-gcc-environments"></a>政府雲端環境是否支援 Shift Community (GCC) ？

班次適用于GCC，但不適用於高GCC DoD 環境。

## <a name="what-type-of-encryption-does-shifts-use-for-data-at-rest-and-in-transit"></a>Shifts 會針對靜態和傳輸中的資料使用哪種加密類型？

班次資料會由 Azure Cosmos DB 和 Azure 儲存體。 若要深入瞭解，請參閱[靜態 Azure 資料加密](/azure/security/fundamentals/encryption-atrest)和[Azure 資料](/azure/cosmos-db/database-encryption-at-rest)加密Cosmos DB。

班次遵循Microsoft 365傳輸中資料加密的準則。 若要深入瞭解，請參閱 [傳輸資料加密](/compliance/assurance/assurance-encryption-in-transit)。

SOC2 合規性稽核每年會驗證靜態和傳輸中資料的班次加密。

## <a name="can-i-access-immutable-copies-of-shifts-data"></a>我可以存取 Shifts 資料的不可變複本嗎？

我們不會儲存 Shifts 資料的不可變複本。 例如，主管可以變更排程，例如新增筆記、變更班次時間、指派工作等等。

## <a name="can-shifts-data-be-edited"></a>可以編輯 Shifts 資料嗎？

有些班次的某些層面無法變更，某些方面可以變更。 例如，您可以編輯筆記和色彩等班次詳細資料，就像在 Shifts 應用程式中變更這些詳細資料的方式一樣。 除非要求已撤銷，否則無法編輯班次要求。

若要查看哪些欄位已變更，您可以搜尋 Microsoft 365記錄中的 Shifts 事件。 若要深入瞭解在稽核記錄中記錄 Shifts 活動的事件，請參閱Microsoft 365活動中的班次Teams[活動](../../audit-log-events.md#shifts-in-teams-activities)。

## <a name="my-organization-uses-a-workforce-management-system-for-scheduling-can-we-integrate-with-and-access-shifts-data"></a>我的組織使用人力管理系統進行排程。 我們可以與 Shifts 資料整合並存取嗎？

班次Graph API 讓您將 Shifts 資料與外部員工管理整合在 WFM (系統中) 整合。 若要深入瞭解，請參閱[移轉Graph API](/graph/api/resources/shift)。

我們也提供受管理的 Shifts 連接器和開放來源 Shifts 連接器。 使用這些連接器，您可以直接將 WFM 系統與 Shifts 整合。 若要深入瞭解 Shifts 連接器和支援的 WFM 系統，請參閱 [Shifts 連接器](shifts-connectors.md)。

## <a name="can-shifts-data-be-deleted-permanently-after-a-specified-period-of-time"></a>Shifts 資料可以在指定的一段時間之後永久刪除嗎？

今天，我們不會刪除您的 Shifts 資料。 使用[Shifts Graph API](/graph/api/resources/shift)，使用 Power Apps 建立應用程式，以將資料保留[](/powerapps/maker/)指定的一段時間。 不過，我們不支援此原生功能。

## <a name="can-shifts-data-be-moved-in-a-tenant-to-tenant-migration"></a>Shifts 資料可以在租使用者對租使用者移轉中移動嗎？

班次資料可視特定要求從一個租使用者移轉到另一個租使用者。 請記住，租使用者對租使用者移移不受開箱即用支援，但可以提出為客戶要求。

## <a name="related-articles"></a>相關文章

- [Teams 中的 Shifts](../shifts-for-teams-landing-page.md)
- [管理 Shifts 應用程式](manage-the-shifts-app-for-your-organization-in-teams.md)
