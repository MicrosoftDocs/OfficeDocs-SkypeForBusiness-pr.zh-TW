---
title: 管理整個 Microsoft 365 的 Teams 應用程式存取權
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: 了解如何管理整個 Microsoft 365 的 Teams 應用程式存取權。
ms.openlocfilehash: 76385d60d185fd9ad522348e4e438ac06dd4e896
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396894"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>管理整個 Microsoft 365 的 Teams 應用程式存取權

除了在 Teams 中運作的應用程式之外，應用程式開發人員還可以增強他們的 Microsoft Teams在 Outlook 中和 Office.com 上。 使用者可以在 Teams 上、Microsoft Outlook 和 Microsoft Office.com 上使用增強型應用程式。 目前，只有已設定目標發行版本中的使用者可以在 Teams、Outlook 和 Office.com 中檢視和使用這些特定應用程式。 現有的 Teams 系統管理員體驗適用於控管這些應用程式的存取權。 [訊息中心](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280) 提供有關此變更的通知。 身為 Teams 系統管理員，您可以允許特定的使用者使用增強型應用程式，或管理他們存取 Teams、Outlook 和 Office.com 中增強型應用程式的許可權。 Teams 系統管理員使用 Teams 系統管理中心來管理應用程式存取權。

若要在 Outlook 和 Office.com 中使用，增強型應用程式會繼續使用在 Teams 中授予的現有權限。 增強型 [應用程式的許可權沒有變更](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs)。

增強型應用程式如下所列：

* [Monday.com](https://teams.microsoft.com/l/app/eab2d3ce-6d6a-4415-abc4-5f40a8317b1f)
* [Mural](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d)
* [Power BI](https://teams.microsoft.com/l/app/1c4340de-2a85-40e5-8eb0-4f295368978b)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9)
* [Zoho Projects](https://teams.microsoft.com/l/app/4a39aea9-8537-4c2f-b66d-ca364eb3b80d)
* [YouTube](https://teams.microsoft.com/l/app/com.microsoft.teamspace.tab.youtube)

您可以使用下列方法控制使用者對 Teams 應用程式的存取權。 如果您是 Office Apps 系統管理員，請連絡您的全域系統管理員或 Teams 系統管理員以管理應用程式存取權。

| 管理存取權的選項 |入口網站|全域系統管理員|Teams 系統管理員|
|--|---|---|--|
| 只有目標版本中的使用者可以存取新的應用程式。 將使用者移至標準發行。 請參閱 [設定標準或目標發行選項](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) | Microsoft 365 系統管理中心 | 是 | 否 |
| 管理特定使用者對新應用程式的存取權。 請參閱 [新增自訂權限原則](teams-app-permission-policies.md#create-a-custom-app-permission-policy)，並 [將自訂原則指派給使用者](policy-assignment-overview.md)。 | Teams 系統管理中心 | 是 | 是 |
| 管理整個組織中所有使用者對新應用程式的存取權。 請參閱 [允許或封鎖應用程式](manage-apps.md#allow-and-block-apps)。 | Teams 系統管理中心 | 是 | 是 |

> [!NOTE]
> 建議您使用 [[標準發行] 選項](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) 來管理使用者存取權。 其他選項會移除使用者存取權，且使用者將無法再使用 Teams 中的現有應用程式。

> [!NOTE]
> 已在 Outlook 和 Office 中安裝相同應用程式的現有市場內增益集的使用者，將會繼續使用該應用程式。 增益集不是 Teams 應用程式，且 Teams 系統管理員無法控管存取權。

## <a name="see-also"></a>另請參閱

* [專為 Microsoft 365 設計的 Microsoft Teams 應用程式，可在預覽版中推出至 Outlook 和 Office.com](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-teams-apps-designed-for-microsoft-365-coming-in/ba-p/3269538)
* [瞭解 Microsoft 365 中的系統管理員角色](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [關於 Outlook 增益集](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [開發人員如何延伸 Teams 應用程式以在 Microsoft 365 中運作](/microsoftteams/platform/m365-apps/overview)
