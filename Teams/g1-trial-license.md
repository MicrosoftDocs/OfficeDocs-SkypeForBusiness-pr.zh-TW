---
title: 管理適用於美國政府的免費 Office 365 G1 試用版
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
audience: Admin
ms.reviewer: aarimm
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: high
description: 適用於美國政府，如果您沒有 Microsoft Teams 且急需使用它，針對因應 COVID-19 (冠狀病毒) 爆發而需要從遠端工作或在家工作 (WFH) 的使用者而推出的 Office 365 G1 試用版。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d45869d015dc5486d3971bff5795cb0cc791dd5c
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377321"
---
# <a name="manage-the-office-365-g1-trial-for-us-government"></a>管理適用於美國政府的 Office 365 G1 試用版 

自 2020 年 7 月 1 日起，我們已不再提供 Office 365 E1 試用版授權。 如果您授權使用者使用 Microsoft Teams，請參閱 [Microsoft Teams 服務描述](/office365/servicedescriptions/teams-service-description)，取得包括 Teams 的付費訂閱清單。 

使用本文中的指導方針來管理現有的 Office 365 G1 試用版授權，包括[升級為付費訂閱](#upgrade-users-from-the-office-365-g1-trial-license)。 若要深入了解，請參閱 [Microsoft 365 政府版方案](https://www.microsoft.com/microsoft-365/government/compare-office-365-government-plans) 和 [GCC 雲端中可用的 Microsoft Teams 功能](plan-for-government-gcc.md)。

請勿錯過我們的[使用 Teams 支援遠端工作者](support-remote-work-with-teams.md)的所有指導方針。

## <a name="manage-the-g1-trial"></a>管理 G1 試用版

啟用 Office 365 G1 試用版後，請為需要的任何使用者開啟授權。 若要了解做法，請參閱[管理使用者對 Teams 的存取權](user-access.md)。

Once you've turned on the G1 Trial for the users who need it, you'll manage these users just like you manage users who have a paid license. For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).

### <a name="upgrade-users-from-the-office-365-g1-trial-license"></a>從 Office 365 G1 試用版授權升級使用者

若要將 G1 試用版使用者升級為付費訂閱：

1.  購買包括 Teams 的訂閱。

2.  從使用者移除 Office 365 G1 試用版訂閱。

3.  指派新購買的授權。

如需詳細資訊，請參閱[適用於政府機關的 Teams](expand-teams-across-your-org/teams-for-government-landing-page.md)。

> [!NOTE]
> If the G1 Trial license ends and a user is not immediately upgraded to a subscription that includes Teams, the user data is not removed. The user still exists in Azure Active Directory and all data within Teams still remains. Once a new license is assigned to the user to enable Teams functionality again, all content will still exist.
> 
### <a name="remove-an-office-365-g1-trial-license"></a>移除 Office 365 G1 試用版授權

  - 如果您想要透過 PowerShell 移除此授權，請參閱：[使用 Office 365 PowerShell 從使用者帳戶移除授權](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)

  - 如果您想要透過系統管理入口網站移除此授權，請參閱：[從貴組織刪除使用者](/microsoft-365/admin/add-users/delete-a-user)

## <a name="related-topics"></a>相關主題

[管理使用者對 Teams 的存取權](user-access.md)

[管理組織的 Teams 設定](enable-features-office-365.md)
