---
title: 小組的動態成員資格概觀
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解 Microsoft Teams 如何使用動態成員資格來支援與 Microsoft 365 群組相關聯的團隊。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ff6a71978873d723f39a534f876696a0def2f756
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562572"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>小組的動態成員資格概觀

Microsoft Teams 使用 *動態成員資格* 支援與 Microsoft 365 群組相關聯的團隊。 動態成員資格可讓團隊的成員資格由一或多個規則定義，該規則會檢查 Azure Active Directory (Azure AD) 中的特定使用者屬性。 當使用者屬性變更或使用者加入並離開租使用者時，使用者會自動新增或移除到正確的團隊。

有了動態成員資格，您可以為組織中的特定使用者群組設定團隊。 可能的案例包括：
- 醫院可以為護士、醫生和醫師建立不同的團隊，以廣播通訊。 如果醫院仰賴臨時員工，這就特別重要。
- 大學可以為特定大學內的所有教職員建立團隊，包括經常變更的教職員。
- 航空公司想要為每一個班機建立一個團隊， (像是從芝加哥到芝加哥的星期二下午不間停) ，並視需要自動指派或移除經常變更的正式發行前小眾測試人員。

使用此功能時，指定小組的成員會根據一組特定準則自動更新，而不是手動管理成員資格。 這麼做需要Azure AD Premium P1只要您有租使用者和系統管理員帳戶，[租使用者系統管理員就可以指派](/azure/active-directory/users-groups-roles/groups-dynamic-membership)授權和小組成員資格給任何使用者的 Azure AD 屬性。

Microsoft Teams 在團隊的 Microsoft 365 群組中生效後，可能需要幾分鐘到最多 2 小時的時間來反映動態成員資格變更。

在動態群組中使用團隊時：

- 規則可以定義誰是團隊成員，但不能定義誰是團隊擁有者。
- 擁有者將無法將使用者新增或移除為團隊成員，因為成員是由動態群組規則定義。
- Teams 用戶端不允許團隊的成員管理。 新增成員、編輯成員角色、傳送及核准加入要求，以及讓團隊保持隱藏的選項。

若要建立使用動態成員資格的團隊，請先 [建立動態的 Microsoft 365 群組](/azure/active-directory/users-groups-roles/groups-create-rule) ，然後 [從該群組建立團隊](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)。

您可以將現有團隊變更為動態成員資格。 如需詳細資訊，請參閱 [在 Azure Active Directory 中將靜態群組成員資格變更為動態](/azure/active-directory/users-groups-roles/groups-change-type) 。

## <a name="related-topics"></a>相關主題

[Microsoft Teams 的限制和規格](limits-specifications-teams.md)

[Azure Active Directory 中群組的動態成員資格規則](/azure/active-directory/users-groups-roles/groups-dynamic-membership)
