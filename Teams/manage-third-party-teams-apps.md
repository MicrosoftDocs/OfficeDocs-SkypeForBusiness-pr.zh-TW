---
title: 管理整個 Microsoft 365 的 Teams 應用程式存取權
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 10/24/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: 了解如何管理整個 Microsoft 365 的 Teams 應用程式存取權。
ms.openlocfilehash: ae11a72324bb4382012c751150a254773c9145b7
ms.sourcegitcommit: c627bd1df17aefdc353bc4da6db169dfe169031e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2022
ms.locfileid: "68680554"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>管理整個 Microsoft 365 的 Teams 應用程式存取權

除了在 Teams 中運作的應用程式之外，應用程式開發人員還可以增強他們的 Microsoft Teams在 Outlook 中和 Office.com 上。 使用者可以在 Teams 上、Microsoft Outlook 和 Microsoft Office.com 上使用增強型應用程式。 目前，只有 [已設定目標發行](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) 版中的使用者可以在 Teams、Outlook 和 Office.com 中檢視和使用這些特定應用程式。 [訊息中心](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280) 提供有關此變更的通知。

## <a name="manage-the-enhanced-apps-access-microsoft-365"></a>管理增強型應用程式存取 Microsoft 365

現有的 Teams 系統管理員體驗適用於控管這些應用程式的存取權。 Teams 系統管理員使用 Teams 系統管理中心來管理應用程式存取權。 身為 Teams 系統管理員，您可以允許特定的使用者使用增強型應用程式，或管理他們存取 Teams、Outlook 和 Office.com 中增強型應用程式的許可權。

若要在 Outlook 和 Office.com 中使用，增強型應用程式會繼續使用在 Teams 中授予的現有權限。 增強型應用程式的許可權沒有變更。 已在 Outlook 和 Office 中安裝相同應用程式現有市場內增益集的使用者，將會繼續使用該應用程式。 增益集不是 Teams 應用程式，且 Teams 系統管理員無法控制存取權。

Office 應用程式系統管理員可以連絡全域系統管理員或 Teams 系統管理員，以管理增強型應用程式的存取權。 如需詳細資訊，請參閱 [Microsoft 365 中的系統管理員角色](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)。

您可以使用下列方法控制使用者存取。

| 管理存取權的選項 |入口網站|全域系統管理員|Teams 系統管理員|
|--|---|---|--|
| 只有目標版本中的使用者可以存取新的應用程式。 將使用者移至標準發行。 請參閱 [設定標準或目標發行選項](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) | Microsoft 365 系統管理中心 | 是 | 否 |
| 管理特定使用者對新應用程式的存取權。 請參閱 [新增自訂權限原則](teams-app-permission-policies.md#create-an-app-permission-policy)，並 [將自訂原則指派給使用者](policy-assignment-overview.md)。 | Teams 系統管理中心 | 是 | 是 |
| 管理整個組織中所有使用者對新應用程式的存取權。 請參閱 [允許或封鎖應用程式](manage-apps.md#allow-and-block-apps)。 | Teams 系統管理中心 | 是 | 是 |

> [!NOTE]
> 建議您使用 [[標準發行] 選項](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) 來管理使用者存取權。 其他選項會移除使用者存取權，且使用者將無法再使用 Teams 中的現有應用程式。

## <a name="list-of-enhanced-apps"></a>增強型應用程式清單

增強型應用程式清單如下：

* [Adobe Acrobat Sign](https://teams.microsoft.com/l/app/0f56a9d1-f502-40f9-a9e8-816d7adbb68b?source=app-details-dialog)
* [較大的大腦 eLearning](https://teams.microsoft.com/l/app/12345514-afee-abcd-acde-c5b34109abcd?source=app-details-dialog)
* [Bookings](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=app-details-dialog)
* [e2e-assure](https://teams.microsoft.com/l/app/8bdf3437-e038-4a93-abdc-00461630f6c3?source=app-details-dialog)
* [ESi-Tik](https://teams.microsoft.com/l/app/fe9627db-f23e-42b1-b454-d4d1ca5af33e?source=app-details-dialog)
* [鏡頭](https://teams.microsoft.com/l/app/cfaeb687-adc7-4e36-a847-39bb35bfb631?source=app-details-dialog)
* [Monday.com](https://teams.microsoft.com/l/app/eab2d3ce-6d6a-4415-abc4-5f40a8317b1f)
* [Mural](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d)
* [我的圖戳](https://teams.microsoft.com/l/app/46fae4d0-faf5-11e9-80f3-53ad33b77bce?source=app-details-dialog)
* [PDF 工具](https://teams.microsoft.com/l/app/ca4b5141-5c46-47bc-a05e-2733d9bd69aa?source=app-details-dialog)
* [Power BI](https://teams.microsoft.com/l/app/1c4340de-2a85-40e5-8eb0-4f295368978b)
* [Priority Matrix](https://teams.microsoft.com/l/app/5be2b320-a5b7-4221-893c-dee506e4e365?source=app-details-dialog)
* [Jira 的 Smart Connect](https://teams.microsoft.com/l/app/6402de97-ce33-4386-bf28-b37e9e139c09?source=app-details-dialog)
* [即將排程](https://teams.microsoft.com/l/app/bf280b0d-b87d-4158-9f2a-70b63674cd27?source=app-details-dialog)
* [簡化](https://teams.microsoft.com/l/app/aa6e7fb6-34ac-4947-9c13-3565c66e368b?source=app-details-dialog)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9)
* [轉錄小幫手 TNA2](https://teams.microsoft.com/l/app/32c31ccd-b878-470e-9259-98c079ae5528?source=app-details-dialog)
* [Umb 並](https://teams.microsoft.com/l/app/23fc1de6-dda0-4043-9ebb-a555e845843d?source=app-details-dialog)
* [瓦爾多](https://teams.microsoft.com/l/app/1d041f16-ab49-4627-bfda-6b60ad2cab6a?source=app-details-dialog)
* [YouTube](https://teams.microsoft.com/l/app/com.microsoft.teamspace.tab.youtube)
* [Zoho Projects](https://teams.microsoft.com/l/app/4a39aea9-8537-4c2f-b66d-ca364eb3b80d)

## <a name="related-articles"></a>相關文章

* [專為 Microsoft 365 設計的 Microsoft Teams 應用程式，可在預覽版中推出至 Outlook 和 Office.com](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-teams-apps-designed-for-microsoft-365-coming-in/ba-p/3269538)
* [瞭解 Microsoft 365 中的系統管理員角色](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [關於 Outlook 增益集](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [開發人員如何延伸 Teams 應用程式以在 Microsoft 365 中運作](/microsoftteams/platform/m365-apps/overview)
