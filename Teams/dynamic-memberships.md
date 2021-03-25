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
description: 瞭解 Microsoft Teams 如何使用動態成員資格支援與 Microsoft 365 群組相關聯的團隊。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a76600e8ca0a92b2d46e99bc26a857c969bd07e7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120765"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>小組的動態成員資格概觀

Microsoft Teams 支援使用動態成員資格與 Microsoft 365 群組 *相關聯的團隊*。 動態成員資格可讓團隊的成員資格由一或多個規則定義，這些規則會檢查 Azure Active Directory (Azure AD) 。 使用者屬性變更或使用者加入並離開租使用者時，系統會自動將使用者新增或移除至正確的團隊。

有了動態成員資格，您可以為貴組織中特定群組的使用者設定團隊。 可能的情況包括：
- 醫院可以建立不同的團隊，讓護士、醫生和醫生廣播通訊。 如果醫院仰賴臨時員工，這一點特別重要。
- 大學可以針對特定學院內的所有教職員建立一個團隊，包括經常變更的教職員。
- 航空公司想要為每個航班建立一個團隊 (例如星期二下午從芝加哥到芝加哥的直達航班) 並需要自動指派或移除經常變更的乘務員。

使用這項功能時，特定小組成員會根據一組特定的準則自動更新，而不是手動管理成員資格。 這麼做需要 Azure AD Premium P1 授權，[](/azure/active-directory/users-groups-roles/groups-dynamic-membership)而且只要擁有租使用者和系統管理員帳戶，租使用者系統管理員就可以將小組成員資格指派給任何使用者的 Azure AD 屬性。

Microsoft Teams 可能需要幾分鐘到最多 2 小時，以反映動態成員資格變更一旦在小組的 Microsoft 365 群組中生效。

> [!NOTE]
> - 規則可以定義誰是團隊成員，但不能定義團隊擁有者。
> - 請參閱 [Microsoft Teams 的上限](limits-specifications-teams.md) 和規格，瞭解目前團隊和頻道大小的限制。
> - 由於成員是由動態群組規則所定義，因此擁有者無法將使用者新增或移除為小組成員。
> -    成員將無法離開由動態群組支援的團隊。

## <a name="creating-and-managing-a-microsoft-365-group-with-dynamic-membership"></a>建立及管理具有動態成員資格的 Microsoft 365 群組

以租使用者系統管理員登入時，請遵循建立動態群組中的指示， [並檢查狀態](/azure/active-directory/users-groups-roles/groups-create-rule)。 如果需要，請參閱 [Azure Active Directory 中群組的動態成員資格規則](/azure/active-directory/users-groups-roles/groups-dynamic-membership)。

## <a name="create-a-new-team-with-your-microsoft-365-group"></a>使用 Microsoft 365 群組建立新團隊

現在，允許成員資格變更生效，並建立新團隊，如從現有群組建立團隊 [中所述](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)。

## <a name="apply-dynamic-membership-to-an-existing-team"></a>將動態成員資格適用于現有團隊

您也可以使用現有的團隊，並變更為動態成員資格，如在 [Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type)中將靜態群組成員資格變更為動態中所述。

## <a name="changes-in-client-behavior"></a>用戶端行為變更

為團隊啟用動態成員資格後，Teams 用戶端將不再允許團隊的成員管理。 新增成員、編輯成員角色、傳送及核准加入要求，以及離開團隊的選項都隱藏起來。