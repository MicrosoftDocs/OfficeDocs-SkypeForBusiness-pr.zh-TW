---
title: 小組的動態成員資格概觀
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解 Microsoft 團隊如何使用動態成員資格支援與 Microsoft 365 群組相關聯的小組。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dc7e3124ec3ec97e3f3643412ccb4f990ab825cc
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638402"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>小組的動態成員資格概觀

Microsoft 團隊支援使用*動態成員資格*與 microsoft 365 群組相關聯的小組。 動態成員資格可讓團隊的成員資格由一或多個在 Azure Active Directory （Azure AD）中檢查特定使用者屬性的規則所定義。 當使用者屬性變更或使用者加入並離開租使用者時，系統會自動新增或移除正確的團隊。

在動態成員資格中，您可以針對組織中的某些使用者設定小組 cohorts。 可能的案例包括：
- 醫院可以為護士、醫生和 surgeons 建立獨特的小組來廣播通訊。 如果醫院依賴 temp 員工，這一點尤為重要。
- 學校可以為特定大學中的所有教職員建立小組，包括經常變更的附屬教職員。
- 航空公司想要為每個航班建立小組（例如週二下午不停從芝加哥到亞特蘭大），而且經常變更的航班人員會視需要自動指派或移除。

使用此功能時，指定團隊的成員會根據一組特定的準則自動更新，而不是手動管理成員資格。 如果您有租使用者與管理員帳戶，只要擁有 Azure AD Premium P1 授權和團隊成員資格，就可以[由租使用者管理員指派](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)給任何使用者的 Azure ad 屬性。

Microsoft 團隊可能需要幾分鐘的時間，才能在小組的 Microsoft 365 群組中生效，以反映出動態成員資格變更。

> [!NOTE]
> - 規則可以定義誰是團隊成員，而不是團隊擁有者。
> - 請參閱 Microsoft 團隊針對團隊和頻道大小目前限制的[限制與規格](limits-specifications-teams.md)。
> - 因為成員是由動態群組規則所定義，所以擁有者將無法將使用者新增或移除為小組成員。
> -    成員將無法留下動態群組所支援的小組。


## <a name="creating-and-managing-a-microsoft-365-group-with-dynamic-membership"></a>使用動態成員資格建立及管理 Microsoft 365 群組
以租使用者管理員身分登入時，請依照[建立動態群組和檢查狀態](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)中的指示進行。 如有需要，請參閱[Azure Active Directory 中群組的動態成員資格規則](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)。

## <a name="create-a-new-team-with-your-o365-group"></a>使用您的 O365 群組建立新團隊

現在允許成員資格變更的時間生效，並以[Microsoft 團隊增強現有的 Microsoft 365 群組](enhance-office-365-groups.md)中所述，建立新的小組。

## <a name="apply-dynamic-membership-to-an-existing-team"></a>將動態成員資格套用至現有的團隊

您也可以使用現有的小組，並將其變更為擁有動態的成員資格，如在[Azure Active Directory 中將靜態群組成員資格變更為動態](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)時所述。

## <a name="changes-in-client-behavior"></a>用戶端行為的變更

針對團隊啟用動態成員資格之後，團隊用戶端就不會再允許團隊成員管理了。 [新增成員]、[編輯成員角色]、[傳送及核准加入要求] 的選項，並讓團隊保持全部隱藏。
