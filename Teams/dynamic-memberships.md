---
title: 小組的動態成員資格概觀
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解如何Microsoft Teams動態成員資格來支援Microsoft 365群組相關聯的團隊。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2bec8b60385185cf1e7417fb5396ef164eb585bad03d003eb174d0bb9cf30c4e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315299"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>小組的動態成員資格概觀

Microsoft Teams使用動態成員資格Microsoft 365與群組相關聯的 *團隊*。 動態成員資格可讓團隊成員資格由一或多個規則定義，這些規則會檢查 Azure AD Azure Active Directory (中的特定) 。 使用者屬性變更或使用者加入並離開租使用者時，系統會自動將使用者新增或移除至正確的團隊。

有了動態成員資格，您可以為貴組織中特定群組的使用者設定團隊。 可能的情況包括：
- 醫院可以建立不同的團隊，讓護士、醫生和醫生廣播通訊。 如果醫院仰賴臨時員工，這一點特別重要。
- 大學可以為特定學院內的所有教職員建立一個團隊，包括經常變更的教職員。
- 航空公司想要為每個航班建立一個團隊 (例如星期二下午從芝加哥到芝加哥的直達航班) 並需要自動指派或移除經常變更的乘務員。

使用這項功能時，特定小組成員會根據一組特定的準則自動更新，而不是手動管理成員資格。 若要這麼做Azure AD Premium P1租使用者系統管理員可以將授權和團隊成員資格指派給[](/azure/active-directory/users-groups-roles/groups-dynamic-membership)任何使用者的 Azure AD 屬性，只要具備租使用者和系統管理員帳戶。

Microsoft Teams可能需要幾分鐘到最多 2 小時的時間，以反映動態成員資格變更一旦在團隊的 Microsoft 365 群組中生效。

將團隊與動態群組一起使用時：

- 規則可以定義誰是團隊成員，但不能定義團隊擁有者。
- 由於成員是由動態群組規則所定義，因此擁有者無法將使用者新增或移除為小組成員。
- Teams用戶端不允許團隊的成員管理。 新增成員、編輯成員角色、傳送及核准加入要求，以及離開團隊的選項都隱藏起來。

若要建立使用動態成員資格的團隊，首先請建立動態Microsoft 365[群組，](/azure/active-directory/users-groups-roles/groups-create-rule)然後從該群組[建立團隊](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)。

您可以將現有團隊變更為動態成員資格。 請參閱[將靜態群組成員資格變更為動態Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type)資訊。

## <a name="related-topics"></a>相關主題

[Microsoft Teams 的限制和規格](limits-specifications-teams.md)

[群組的動態成員資格規則Azure Active Directory](/azure/active-directory/users-groups-roles/groups-dynamic-membership)
