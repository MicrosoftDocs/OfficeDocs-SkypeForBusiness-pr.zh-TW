---
title: 管理跨Teams應用程式Microsoft 365
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
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 管理跨 Teams 應用程式Microsoft 365。
ms.openlocfilehash: 981dd4a36cad46085aa7e620ea893f5b62bbaa96
ms.sourcegitcommit: 9e868a155bcd20dd5dafdedcff091ff77ca7398b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2022
ms.locfileid: "64584318"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>管理跨Teams應用程式Microsoft 365

應用程式開發人員可以更新Microsoft Teams應用程式，以在 Outlook 和 Office.com 上工作，以及使用 Teams。 使用者可以在更新之後，在 Teams、Microsoft Outlook Microsoft Office.com 使用更新的應用程式。 目前，只有目標發行中的使用者才能在 Teams、Outlook 和 Office.com 中查看及使用這些特定應用程式。 現有的系統Teams管理體驗適用于管理這些應用程式的存取權。 訊息中心提供此變更 [的通知](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280)。 做為Teams系統管理員，您可以允許特定使用者使用更新的應用程式，或在 Teams、Outlook 和 Office.com 管理其更新應用程式的存取權。 Teams系統管理員使用 Teams系統管理中心來管理應用程式存取權。

若要在 Outlook Office.com 中使用，更新的應用程式會繼續使用在 Teams 中授予的現有Teams。 更新 [的應用程式許可權沒有變更](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs)。

您可以使用下列方法控制使用者對Teams應用程式的存取權。 如果您是應用程式系統管理員Office，請與您的全域系統管理員Teams系統管理員，以管理應用程式存取權。

| 管理存取的選項 |門戶|全域系統管理員|Teams系統管理員|
|--|---|---|--|
| 只有目標發行中的使用者才能存取新應用程式。 將使用者移至標準版本。 請參閱 [設定標準或目標發行選項](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) | Microsoft 365 系統管理中心 | 是 | 否 |
| 管理特定使用者新應用程式的存取權。 請參閱 [新增自訂權限原則](teams-app-permission-policies.md#create-a-custom-app-permission-policy) ， [並將自訂策略指派給使用者](policy-assignment-overview.md)。 | Teams系統管理中心 | 是 | 是 |
| 管理貴組織所有使用者新應用程式的存取權。 請參閱 [允許或封鎖應用程式](manage-apps.md#allow-and-block-apps)。 | Teams系統管理中心 | 是 | 是 |

> [!NOTE]
> 我們建議您使用 [標準發行選項](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) 來管理使用者存取權。 其他選項會移除使用者存取權，他們將無法在 Teams。

> [!NOTE]
> 在 Outlook 和 Office 中已安裝相同應用程式的現有市內附加元件的使用者會繼續使用該 App。 這些附加元件不會Teams，Teams系統管理員無法管理存取權。

以下是可跨曲面工作的更新應用程式Microsoft 365清單：

* [壁畫](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d?source=app-details-dialog)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9?source=app-details-dialog)

## <a name="see-also"></a>另請參閱

* [瞭解系統管理角色Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [關於Outlook附加元件](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [開發人員如何將應用程式Teams跨應用程式Microsoft 365](/microsoftteams/platform/m365-apps/overview)
