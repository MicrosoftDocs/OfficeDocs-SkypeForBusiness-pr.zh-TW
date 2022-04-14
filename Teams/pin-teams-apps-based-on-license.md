---
title: 為前線員工量身打造Teams應用程式
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解為 Teams 中的第一線員工量身打造的應用程式體驗。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: b526733558570e4903d9dce43094c7ffa0f7de17
ms.sourcegitcommit: 480046a53dfb6e6cf867e1920f8fb43dda9d3774
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2022
ms.locfileid: "63774182"
---
# <a name="tailor-teams-apps-for-your-frontline-workers"></a>為前線員工量身打造Teams應用程式

> [!NOTE]
> [!INCLUDE [new-feature-coming-soon-section](includes/new-feature-coming-soon-section.md)]

## <a name="overview"></a>概觀

Teams提供一種簡單的方法，可將應用程式釘選給第一線工作人員。 這項功能會根據授權來釘選應用程式，以在Teams中提供符合他們需求的全新體驗。

透過量身打造的第一線應用程式體驗，您的第一線工作人員可在Teams取得最相關的應用程式，而不需要系統管理員採取任何動作。

## <a name="tailored-frontline-app-experience"></a>量身打造的第一線應用程式體驗

應用程式會釘選到應用程式行，也就是Teams行動用戶端底部 (iOS 和 Android) 以及Teams桌面用戶端的列。 下列應用程式會釘選給擁有 [F 授權](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)的使用者：

- [活動](https://support.microsoft.com/office/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56)
- [聊天](https://support.microsoft.com/office/get-started-with-chat-0b506ce2-eb6d-4fca-9668-e56980ba755e)
- [團隊](https://support.microsoft.com/office/teams-and-channels-in-microsoft-teams-c6d0e61d-a61e-44a6-a972-04f2a8fa4155)
- [無線對講機](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [工作](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)
- [班次](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
- [核准](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)

**Teams行動裝置版**

:::image type="content" source="media/tailored-teams-apps-mobile.png" alt-text="在行動裝置上量身打造的第一線應用程式體驗Teams" lightbox="media/tailored-teams-apps-mobile.png"::: 

**Teams桌面**

:::image type="content" source="media/tailored-teams-apps-desktop.png" alt-text="在桌上型電腦上量身打造的第Teams一線應用程式體驗" lightbox="media/tailored-teams-apps-desktop.png"::: 

## <a name="admin-controls"></a>系統管理控制項

> [!NOTE]
> 使用者 **釘選** 設定必須在全域 (預設) [應用程式設定原則](teams-app-setup-policies.md) 中開啟，此功能才會生效。

量身打造的第一線應用程式體驗是由Teams系統管理中心 [[管理](manage-apps.md#manage-org-wide-app-settings)應用程式] 頁面上的 [**顯示量身打造的應用程式** 全組織應用程式] 設定所控制。 如果已開啟此功能，您組織中擁有 F 授權的所有使用者都會獲得量身打造的應用程式體驗。

請記住，指派給使用者的任何自訂 [應用程式設定原則](teams-app-setup-policies.md) 優先。 這表示，如果使用者已經指派自訂應用程式設定原則給他們，使用者就會取得自訂應用程式設定原則中定義的設定。 To learn more about how the feature works with Teams app policies, including the global app setup policy, see the [Scenarios](#scenarios) section later in this article.

此功能預設為啟用。 不過，如果您不希望 Microsoft 提供量身打造的一線應用程式體驗，您可以關閉此功能。 若要關閉或開啟此功能：

1. 在Microsoft Teams系統管理中心的左側導覽畫面中，移至 **[Teams應用程式**  >  管理 **應用程式**]，然後選取 [**全組織應用程式設定]**。
2. 在 **[量身打造的應用程式]** 底下，將 **[顯示量身打造的應用程式** ] 切換為 [ **關閉** ] 或 [ **開啟]**。

    :::image type="content" source="media/tailored-teams-apps-admin-center.png" alt-text="Teams系統管理中心 [管理應用程式] 頁面上 [顯示量身打造的應用程式] 設定的螢幕擷取畫面" lightbox="media/tailored-teams-apps-admin-center.png":::

## <a name="scenarios"></a>案例

### <a name="how-does-the-tailored-frontline-app-experience-affect-my-global-app-setup-policy"></a>量身打造的第一線應用程式體驗如何影響我的全域應用程式設定原則？

瞭解量身打造的第一線應用程式體驗如何與全球應用程式設定原則搭配運作。 此表格中的案例適用于擁有 F 授權的第一線員工，以及已開啟 **[使用者釘選** ] 的全域應用程式設定原則。

|如果。。。 |然後。。。 |
|---------|---------|
|第一線工作人員具備全域應用程式設定原則，且此功能已關閉。 |第一線工作人員會取得全域應用程式設定原則中定義的應用程式。|
|第一線工作人員具備全域應用程式設定原則，且此功能已開啟。     | 第一線工作人員可獲得量身打造的第一線應用程式體驗。 全域應用程式設定原則中定義的應用程式會釘選在量身打造的應用程式下方。      |
|您更新了全域應用程式設定原則，且此功能已開啟。     |第一線工作人員會獲得量身打造的第一線應用程式體驗，而全域應用程式設定原則中定義的應用程式會釘選在量身打造的應用程式下方。         |
|第一線工作人員有全域應用程式設定原則，且已關閉 **[使用者釘選** ]。 |第一線工作人員會取得全域應用程式設定原則中定義的應用程式。|
|第一線工作人員有全域應用程式設定原則，並變更了全域應用程式設定原則，將企業營運 (LOB) 應用程式納入應用程式清單中的第二個位置。 |LOB 應用程式釘選在量身打造的應用程式下方。 如果已開啟 **使用者釘選** ，第一線工作人員可以變更應用程式順序。         |
|第一線工作人員具備全域設定原則，並變更了全域應用程式設定原則，將 Shifts 納入第一個位置。  |Shifts 釘選到第六個位置，由量身打造的一線應用程式體驗所定義。 如果已開啟 **使用者釘選** ，第一線工作人員可以變更應用程式順序。          |

### <a name="how-does-the-tailored-frontline-app-experience-work-with-other-teams-app-policies"></a>量身打造的第一線應用程式體驗如何與其他Teams應用程式原則搭配運作？

瞭解量身打造的第一線應用程式體驗如何與其他Teams應用程式原則搭配運作。

|如果。。。  |然後。。。 |
|---------|---------|
此功能已關閉。   | 第一線工作人員會將全域應用程式設定原則或自訂應用程式設定原則中定義的應用程式指派給他們。          |
|第一線工作人員有自訂應用程式設定原則，且該功能已開啟。    |第一線工作人員會在自訂應用程式設定原則中定義應用程式。          |
|針對使用者或您的組織，會封鎖量身打造的第一線應用程式體驗中的應用程式。      |量身打造的第一線應用程式體驗符合 [應用程式許可權原則](teams-app-permission-policies.md)。 如果應用程式遭到封鎖，第一線工作人員將不會看到封鎖的應用程式。           |
|已在應用程式設定原則中定義量身打造的第一線應用程式體驗中的應用程式，且該功能已開啟。 |應用程式是根據量身打造的應用程式清單所定義的順序來釘選。        |
|使用者擁有 E、A 或 G 授權，且功能已開啟。   | 使用者無法獲得量身打造的第一線應用程式體驗。 此體驗目前僅適用于擁有 F 授權的使用者。        |

> [!NOTE]
> 您無法在量身打造的一線應用程式體驗中變更應用程式或應用程式的順序。 現在，如果您想要進行變更，您可以設定自己的自訂體驗。 若要這麼做，請先關閉此功能。 然後， [建立自訂應用程式設定原則](teams-app-setup-policies.md)，並將 [它指派給使用者或群組](assign-policies-users-and-groups.md)。

## <a name="related-articles"></a>相關文章

- [在 Teams 中管理無線對講機應用程式](walkie-talkie.md)
- [在 Teams 中管理工作應用程式](manage-tasks-app.md)
- [在 Teams 中管理 Shifts 應用程式](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
- [在 Teams 中管理核准應用程式](approval-admin.md)
- [在 Teams 中管理應用程式設定原則](teams-app-setup-policies.md)
- [在 Teams 中管理應用程式權限原則](teams-app-permission-policies.md)
