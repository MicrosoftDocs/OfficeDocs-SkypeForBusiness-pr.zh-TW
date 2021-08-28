---
title: 管理適用於美國政府的免費 Office 365 G1 試用版
author: SerdarSoysal
ms.author: serdars
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
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: c1208636547258524816ca77e57ddc3b83646144
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618469"
---
# <a name="manage-the-office-365-g1-trial-for-us-government"></a>管理適用於美國政府的 Office 365 G1 試用版 

自 2020 年 7 月 1 日起，我們已不再提供 Office 365 E1 試用版授權。 如果您授權使用者使用 Microsoft Teams，請參閱 [Microsoft Teams 服務描述](/office365/servicedescriptions/teams-service-description)，取得包括 Teams 的付費訂閱清單。 

使用本文中的指導方針來管理現有的 Office 365 G1 試用版授權，包括[升級為付費訂閱](#upgrade-users-from-the-office-365-g1-trial-license)。 若要深入了解，請參閱 [Microsoft 365 政府版方案](https://www.microsoft.com/microsoft-365/government/compare-office-365-government-plans) 和 [GCC 雲端中可用的 Microsoft Teams 功能](plan-for-government-gcc.md)。

請勿錯過我們的[使用 Teams 支援遠端工作者](support-remote-work-with-teams.md)的所有指導方針。

## <a name="manage-the-g1-trial"></a>管理 G1 試用版

啟用 Office 365 G1 試用版後，請為需要的任何使用者開啟授權。 若要了解做法，請參閱[管理使用者對 Teams 的存取權](user-access.md)。

一旦您為需要它的使用者開啟 G1 試用版，您就可以如同管理擁有付費授權的使用者一般，管理這些使用者。如需詳細資訊，請參閱[管理貴組織的 Teams 設定](enable-features-office-365.md)。

### <a name="upgrade-users-from-the-office-365-g1-trial-license"></a>從 Office 365 G1 試用版授權升級使用者

若要將 G1 試用版使用者升級為付費訂閱：

1.  購買包括 Teams 的訂閱。

2.  從使用者移除 Office 365 G1 試用版訂閱。

3.  指派新購買的授權。

如需詳細資訊，請參閱[適用於政府機關的 Teams](expand-teams-across-your-org/teams-for-government-landing-page.md)。

> [!NOTE]
> 如果 G1 試用版結束，且使用者未立即升級為包含 Teams 的訂閱，則不會移除使用者資料。使用者仍然存在於 Azure Active Directory 中，且 Teams 內的所有資料仍會保留。一旦將新授權指派給使用者以再次啟用 Teams 功能，所有內容仍會存在。
> 
### <a name="remove-an-office-365-g1-trial-license"></a>移除 Office 365 G1 試用版授權

  - 如果您想要透過 PowerShell 移除此授權，請參閱：[使用 Office 365 PowerShell 從使用者帳戶移除授權](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)

  - 如果您想要透過系統管理入口網站移除此授權，請參閱：[刪除組織的使用者](/microsoft-365/admin/add-users/delete-a-user)

## <a name="related-topics"></a>相關主題

[管理使用者對 Teams 的存取權](user-access.md)

[管理貴組織的 Teams 設定](enable-features-office-365.md)
