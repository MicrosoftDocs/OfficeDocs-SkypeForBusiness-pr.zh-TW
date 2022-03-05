---
title: 根據授權Teams自訂您的應用程式
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何根據授權Teams為貴組織的使用者釘上應用程式。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 34614a6c1b45ea9660552b77b7c91d87e5c30d5f
ms.sourcegitcommit: 2d4dab7a6436e53db9475d67695504753896ca86
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2022
ms.locfileid: "63065241"
---
# <a name="tailor-your-teams-apps-based-on-license"></a>根據授權Teams自訂您的應用程式

> [!NOTE]
> [!INCLUDE [new-feature-coming-soon-section](includes/new-feature-coming-soon-section.md)]

> [!NOTE]
> 目前，此功能適用于 F 授權。 因此，本文著重于前線員工的體驗。 未來將會支援其他授權類型。

## <a name="overview"></a>概觀

Teams提供一種根據授權釘上應用程式的方法。 當使用者在啟用量身Teams時，使用者就會獲得根據授權量身打造的應用程式體驗。

這項功能可讓使用者在 Teams中擁有最相關的應用程式，而不需要系統管理員執行任何動作。

## <a name="tailored-app-experience"></a>量身打造的應用程式體驗

應用程式會釘釘到應用程式欄，即 Teams 桌面用戶端側邊以及 Teams 行動用戶端 (iOS 和 Android) 底部的) 。

已針對擁有 F 授權的使用者釘上的應用程式：

- [活動](https://support.microsoft.com/office/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56)
- [聊天](https://support.microsoft.com/office/get-started-with-chat-0b506ce2-eb6d-4fca-9668-e56980ba755e)
- [團隊](https://support.microsoft.com/office/teams-and-channels-in-microsoft-teams-c6d0e61d-a61e-44a6-a972-04f2a8fa4155)
- [無線對講機](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [工作](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)
- [班次](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
- [核准](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)

## <a name="admin-controls"></a>系統管理控制項

> [!NOTE]
> 使用者釘點必須在全域 (全組織的預設) [App](teams-app-setup-policies.md) 設定政策中開啟，此功能生效。

量身打造的應用程式體驗功能是由系統管理中心的管理應用程式頁面上的根據授權組織整個應用程式設定來顯示量身[](manage-apps.md#manage-org-wide-app-settings)訂做的應用程式Teams控制。 如果此功能已啟用，貴組織中所有擁有 F 授權的使用者都會獲得量身打造的應用程式體驗。

請記住，指派給使用者的任何自訂應用程式設定策略優先。 這表示如果使用者已指派自訂應用程式設定策略給他們，使用者就會獲得自訂應用程式設定策略中定義的設定。 若要深入瞭解此功能如何與組織中已申請的現有應用程式設定原則一起運作，請參閱本文的 一節[](#scenarios)。

此功能預設為啟用。 不過，如果您不希望 Microsoft 提供量身打造的應用程式體驗，您可以關閉此功能。 若要關閉或開啟此功能：

1. 在系統管理中心的左側導Microsoft Teams，請Teams **應用程式**  >  **管理應用程式**，然後選取整個 **組織的應用程式設定**。
2. 在 **自訂應用程式下**，**將根據授權** 顯示量身訂做的應用程式切換為 **關閉或****開啟**。

## <a name="scenarios"></a>案例

使用此表格中的資訊來瞭解量身訂做的應用程式體驗在各種情況下如何運作，包括當您已採用現有的應用程式設定原則時。

|如果。。。  |然後。。。 |
|---------|---------|
|使用者具有全域應用程式設定策略，且此功能已啟用。     | 使用者會獲得量身打造的應用程式體驗。 在全域應用程式設定策略中定義的 App 仍然會釘上，並進一步顯示在已釘住的應用程式清單中。      |
|使用者有自訂應用程式設定策略，且此功能已啟動。    |使用者會獲得自訂應用程式設定策略中定義的設定。          |
|此功能已啟動，而且您更新全域應用程式設定策略。     |使用者會根據他們的授權獲得量身打造的應用程式體驗。 在全域應用程式設定策略中定義的 App 仍然會釘上，並進一步顯示在已釘住的應用程式清單中。          |
|此功能已關閉。   | 使用者會獲得在全域應用程式設定策略或指派給他們的自訂應用程式設定政策中定義的體驗。          |
|使用者擁有 E、A 或 G 授權，且此功能已啟用。   | 使用者無法取得量身打造的應用程式體驗。 目前，量身打造的應用程式體驗僅適用于擁有 F 授權的使用者。        |
|自訂應用程式體驗中的應用程式會針對使用者或貴組織封鎖。      |量身打造的應用程式體驗會遵守應用程式許可權政策。 如果應用程式被封鎖，使用者不會看到封鎖的應用程式。           |
|自訂應用程式體驗中的應用程式已在應用程式設定策略中定義，且此功能已啟動。 |根據量身訂做的應用程式體驗所定義的順序來釘定應用程式。        |

> [!NOTE]
> 在量身打造的應用程式體驗中，您無法變更 App 或應用程式的順序。 目前，如果您想要進行變更，您可以設定自己的自訂體驗。 若要這麼做，請先關閉此功能。 接著， [建立自訂應用程式設定策略](teams-app-setup-policies.md)， [並將其指派給使用者或群組](assign-policies-users-and-groups.md)。

## <a name="related-articles"></a>相關文章

- [在應用程式中管理對講Teams](walkie-talkie.md)
- [在應用程式中管理工作Teams](manage-tasks-app.md)
- [在應用程式中管理 Shifts Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
- [在應用程式中管理核准Teams](approval-admin.md)
- [在 Teams 中管理應用程式設定原則](teams-app-setup-policies.md)
- [在 Teams 中管理應用程式權限原則](teams-app-permission-policies.md)
