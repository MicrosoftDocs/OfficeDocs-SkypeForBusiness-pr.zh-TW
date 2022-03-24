---
title: 為您的Teams量身打造應用程式
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解專為前線員工量身打造的應用程式體驗，Teams。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: b526733558570e4903d9dce43094c7ffa0f7de17
ms.sourcegitcommit: b91d83739a078b175770c797c17d602eb5c83a4f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2022
ms.locfileid: "63774182"
---
# <a name="tailor-teams-apps-for-your-frontline-workers"></a>為您的Teams量身打造應用程式

> [!NOTE]
> [!INCLUDE [new-feature-coming-soon-section](includes/new-feature-coming-soon-section.md)]

## <a name="overview"></a>概觀

Teams提供一個簡單的方法，為前線員工釘上應用程式。 這項功能會根據授權將應用程式固定，為您的前線員工提供專為他們Teams的開箱即用體驗。

有了量身打造的前線應用程式體驗，您的前線員工Teams取得最相關的應用程式，而不需要系統管理員執行任何動作。

## <a name="tailored-frontline-app-experience"></a>量身打造的前線應用程式體驗

應用程式會釘到應用程式欄，即 Teams 行動用戶端 (iOS 和 Android) 底部的資料行，以及 Teams 桌面用戶端的側邊。 下列應用程式會針對擁有 [F 授權的使用者釘上](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)：

- [活動](https://support.microsoft.com/office/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56)
- [聊天](https://support.microsoft.com/office/get-started-with-chat-0b506ce2-eb6d-4fca-9668-e56980ba755e)
- [團隊](https://support.microsoft.com/office/teams-and-channels-in-microsoft-teams-c6d0e61d-a61e-44a6-a972-04f2a8fa4155)
- [無線對講機](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [工作](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)
- [班次](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
- [核准](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)

**Teams行動版**

:::image type="content" source="media/tailored-teams-apps-mobile.png" alt-text="在行動版上量Teams應用程式體驗" lightbox="media/tailored-teams-apps-mobile.png"::: 

**Teams桌面**

:::image type="content" source="media/tailored-teams-apps-desktop.png" alt-text="在桌上出版上量身打造Teams應用程式體驗" lightbox="media/tailored-teams-apps-desktop.png"::: 

## <a name="admin-controls"></a>系統管理控制項

> [!NOTE]
> 您必須 **在全組織 (** 應用程式設定) 中開啟使用者釘點設定，此功能生效。[](teams-app-setup-policies.md)

量身打造的前線應用程式體驗是由系統管理中心的管理應用程式頁面上的顯示量身訂做的應用程式全[](manage-apps.md#manage-org-wide-app-settings)組織應用程式設定所控制Teams控制。 如果此功能已啟用，貴組織中所有擁有 F 授權的使用者都會獲得量身打造的應用程式體驗。

請記住，指派給使用者的任何自訂 [應用程式](teams-app-setup-policies.md) 設定策略優先。 這表示如果使用者已指派自訂應用程式設定策略給他們，使用者就會獲得自訂應用程式設定策略中定義的設定。 若要深入瞭解此功能如何與應用程式Teams ，包括全域應用程式設定政策一起運作，請參閱本文稍後的 一[](#scenarios)節。

此功能預設為啟用。 不過，如果您不希望 Microsoft 提供量身打造的前線應用程式體驗，您可以關閉此功能。 若要關閉或開啟此功能：

1. 在系統管理中心的左側導Microsoft Teams，請Teams **應用程式**  >  **管理應用程式**，然後選取整個 **組織的應用程式設定**。
2. 在 **自訂應用程式下**，將顯示 **量身** 訂做的應用程式切換為 **關閉** 或 **開啟**。

    :::image type="content" source="media/tailored-teams-apps-admin-center.png" alt-text="系統管理中心的管理應用程式頁面上顯示量身訂做的應用程式Teams螢幕擷取畫面" lightbox="media/tailored-teams-apps-admin-center.png":::

## <a name="scenarios"></a>案例

### <a name="how-does-the-tailored-frontline-app-experience-affect-my-global-app-setup-policy"></a>量身打造的前線應用程式體驗如何影響我的全域應用程式設定政策？

瞭解量身打造的前線應用程式體驗如何與全域應用程式設定政策共同運作。 此表格中的情境適用于擁有 F 授權和全域應用程式設定原則的前線員工，且使用者釘點功能已開啟。

|如果。。。 |然後。。。 |
|---------|---------|
|前線工作人員有全域應用程式設定政策，且此功能已關閉。 |前線工作人員會獲得全域應用程式設定政策中定義的應用程式。|
|前線工作人員具有全域應用程式設定政策，且此功能已啟用。     | 前線工作人員會獲得量身打造的前線應用程式體驗。 全域應用程式設定政策中定義的應用程式會釘在量身訂做的應用程式下方。      |
|您更新全域應用程式設定策略，且此功能已啟動。     |前線工作人員會獲得量身打造的前線應用程式體驗，而全域應用程式設定政策中定義的應用程式會釘在量身訂做的應用程式下方。         |
|前線工作人員具有全域應用程式設定策略，且使用者 **釘點** 已關閉。 |前線工作人員會獲得全域應用程式設定政策中定義的應用程式。|
|前線員工具有全域應用程式設定策略，而全域應用程式設定策略會變更為在應用程式清單中的第二個位置包含企業 (LOB) 應用程式。 |LOB 應用程式會釘在量身訂做的應用程式下方。 如果使用者釘點已啟動，前線工作人員可以 **變更** 應用程式順序。         |
|前線員工具有全域設定策略，而全域應用程式設定策略會變更為將 Shifts 納入第一個位置。  |班次會釘到第六個位置，這是由量身打造的前線應用程式體驗所定義。 如果使用者釘點已啟動，前線工作人員可以 **變更** 應用程式順序。          |

### <a name="how-does-the-tailored-frontline-app-experience-work-with-other-teams-app-policies"></a>量身打造的前線應用程式體驗如何與其他應用程式Teams一起？

瞭解量身打造的前線應用程式體驗如何與其他應用程式Teams一起運作。

|如果。。。  |然後。。。 |
|---------|---------|
此功能已關閉。   | 前線工作人員會獲得在全域應用程式設定政策或指派給他們的自訂應用程式設定政策中定義的 App。          |
|前線工作人員有自訂應用程式設定政策，且此功能已啟用。    |前線工作人員會獲得自訂應用程式設定政策中定義的應用程式。          |
|針對使用者或貴組織所量身打造的前線應用程式體驗中的應用程式會封鎖。      |量身打造的前線應用程式體驗會遵守 [應用程式許可權政策](teams-app-permission-policies.md)。 如果應用程式被封鎖，前線工作人員不會看到封鎖的應用程式。           |
|自訂前線應用程式體驗中的應用程式已在應用程式設定政策中定義，且此功能已啟動。 |根據量身訂做的應用程式清單所定義的順序來釘定應用程式。        |
|使用者擁有 E、A 或 G 授權，且此功能已啟用。   | 使用者無法取得量身打造的前線應用程式體驗。 目前，體驗僅適用于擁有 F 授權的使用者。        |

> [!NOTE]
> 在量身打造的前線應用程式體驗中，您無法變更 App 或應用程式的順序。 目前，如果您想要進行變更，您可以設定自己的自訂體驗。 若要這麼做，請先關閉此功能。 接著， [建立自訂應用程式設定策略](teams-app-setup-policies.md)， [並將其指派給使用者或群組](assign-policies-users-and-groups.md)。

## <a name="related-articles"></a>相關文章

- [在應用程式中管理對講Teams](walkie-talkie.md)
- [在應用程式中管理工作Teams](manage-tasks-app.md)
- [在應用程式中管理 Shifts Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
- [在應用程式中管理核准Teams](approval-admin.md)
- [在 Teams 中管理應用程式設定原則](teams-app-setup-policies.md)
- [在 Teams 中管理應用程式權限原則](teams-app-permission-policies.md)
