---
title: 在 Microsoft Teams 系統管理中心管理 Microsoft Power Platform 應用程式
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/27/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何在 Teams 系統管理中心使用 Microsoft Power Platform 來管理自訂應用程式組建的存取權。
ms.openlocfilehash: 3a81d1db3de7cf4fa82b80526ffdb206bfbe8da6
ms.sourcegitcommit: 1161cddd077056a9c1e2da99a84e35be0380b1b1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/20/2022
ms.locfileid: "68656029"
---
# <a name="manage-microsoft-power-platform-apps-in-the-teams-admin-center"></a>在 Teams 系統管理中心管理 Microsoft Power Platform 應用程式

## <a name="manage-custom-apps-created-using-microsoft-power-platform-apps"></a>管理使用 Microsoft Power Platform 應用程式建立的自訂應用程式

本文提供如何在 Microsoft Teams 系統管理中心使用 [Microsoft Power Platform](https://powerplatform.microsoft.com/) 應用程式管理自訂應用程式的概觀。 自訂應用程式是由貴組織內部的開發人員為內部使用者所建立。

> [!NOTE]
> 本文不適用於從 [應用程式] 頁面安裝或透過應用程式設定原則釘選到 Teams 的 Power Apps 應用程式或 Power Virtual Agents 應用程式。 您可以使用[應用程式權限原則](teams-app-permission-policies.md)和[應用程式設定原則](teams-app-setup-policies.md)來管理 Microsoft Store 應用程式。

[Power Apps](https://powerapps.microsoft.com) 是低程式碼或無程式碼的應用程式開發環境，組織中的應用程式建立者可以使用它來建置可連線至您商務資料的自訂應用程式。 [Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents) 是一個無程式碼的 Bot 建置環境，可讓應用程式開發人員建立功能強大的 Bot。 透過將 Microsoft Power Platform 應用程式整合至 Teams，組織可以簡化業務流程、更快速地回應不斷變更的業務需求以提升共同作業成效，並建立及共用自訂解決方案來提高工作效率。  

由您組織中的開發人員所建立的 Microsoft Power Platform 應用程式會自動新增至 Teams。 開發人員可以使用 [Power Apps 中的共用功能](/powerapps/maker/canvas-apps/share-app)和 [Power Virtual Agents 中的共用功能](/power-virtual-agents/admin-share-bots) 來控制誰可以存取他們的應用程式。

當 Microsoft Power Platform 應用程式建立或共用時，使用者可以移至 **[使用 Power Platform 建置]**，在 [應用程式] 頁面上檢視並安裝它。 (應用程式建立或共用之後可能需要幾分鐘的時間才會顯示在這裡。) 

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="[應用程式] 頁面的螢幕擷取畫面，顯示 [使用 Power Platform 建置] 中列出的 Microsoft Power Platform 應用程式。":::

如果應用程式符合下列其中一個條件，使用者會在 **[使用 Power Platform 建置]** 中看到應用程式。

|Power 應用程式 |Power Virtual Agent  |
|---------|---------|
|<ul><li>使用者已建立該應用程式。</li><li>該應用程式已直接與使用者共用。</li><li>使用者最近使用過該應用程式。 </li></ul>| <ul><li>使用者已建立 bot。</li><li>Bot 由使用者所屬團隊所擁有。 </li></ul>        |

使用者安裝 Microsoft Power Platform 應用程式的方式，與安裝任何其他 Teams 應用程式的方式相同。 請記住，使用者只能將應用程式安裝到自己有權限的内容中。 例如，使用者擁有的團隊、使用者所屬的聊天或其個人範圍。

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-teams-admin-center"></a>在 Teams 系統管理中心管理 Microsoft Power Platform 應用程式的存取權

身為系統管理員，您可以控制 Microsoft Power Platform 應用程式是否列在 Teams [應用程式] 頁面的 **[使用 Power Platform 建置]** 中。 您可以一起封鎖或允許所有在 Power Apps 建立的應用程式，或者所有在 [[管理應用程式]](manage-apps.md) 頁面的組織層級或針對使用[應用程式權限原則](teams-app-permission-policies.md)的特定使用者，在 Power Virtual Agents 建立的應用程式。

貴組織的 App Store 中的 **Shared Power Apps** 和 **Shared Power Virtual Agent Apps** 應用程式代表在該特定平台上所建立的所有應用程式。 如果您針對整個組織或特定使用者封鎖其中一個或兩個應用程式，使用者就無法在 Teams 中安裝它們。 使用者無法要求系統管理員核准以允許應用程式。

請記住，您可以控制在 Power Apps 和 Power Virtual Agents 中建立之所有應用程式的存取權，但無法允許或封鎖個別應用程式。 應用程式建立者決定誰可以從 Power Apps 和 Power Virtual Agents 中透過共用功能存取他們建立的應用程式。 如果製造商與使用者共用他們在 Power Virtual Agents 中建立的應用程式，而且您已封鎖該使用者的 **共用 Power Virtual Agents Apps**，使用者將無法在 Teams 中查看或安裝該平台的任何應用程式。

如果允許使用者從 Power Apps 或 Power Virtual Agents 存取應用程式，然後封鎖使用者，不讓使用者從其中一個或兩個平台存取應用程式，使用者仍然可以存取及使用在您封鎖應用程式之前所安裝的 Microsoft Power Platforms 應用程式。 不過，使用者無法再於 **[使用 Power Platform 建置]** 中安裝來自這些平台的任何應用程式。

> [!NOTE]
> [[管理應用程式]](manage-apps.md) 頁面上的 **[允許與自訂應用程式互動]** 全組織應用程式設定會套用至貴組織中的每個人，並規範他們是否可以與自訂應用程式互動。 全組織應用程式設定會控管所有使用者的行為，並覆寫指派給使用者的任何其他應用程式權限原則。 如果關閉此設定，貴組織中的使用者就無法安裝任何自訂應用程式，包括 Microsoft Power Platform 應用程式。 若要深入了解，請參閱 [管理全組織應用程式設定](manage-apps.md#manage-org-wide-app-settings)。

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>允許或封鎖貴組織的 Microsoft Power Platform 應用程式

根據預設，貴組織中的所有 Teams 使用者皆可使用 **共用 Power Apps** 和 **共用 Power Virtual Agent Apps**。 您可以在 Microsoft Teams 系統管理中心的 [[管理應用程式]](manage-apps.md) 頁面上封鎖或允許組織層級的應用程式。  

1. 登入 Teams 系統管理中心並存取 **Teams 應用程式**  >  **[管理應用程式](https://admin.teams.microsoft.com/policies/manage-apps)** 您必須是全域系統管理員或 Teams 服務系統管理員才能存取頁面。
1. 在應用程式清單中，執行下列其中一項。

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="顯示共用的 Microsoft Power Platform 應用程式 [管理應用程式] 頁面的螢幕擷取畫面。":::

    * 若要封鎖在 Power Apps 或 Power Virtual Agents 中為貴組織中的所有使用者建立的應用程式，請搜尋 **[共用 Power Apps** ] 或 **[共用 Power Virtual Agent Apps]**，選取該應用程式，然後選取 **[封鎖]**。
    * 若要允許在 Power Apps 或 Power Virtual Agents 中為貴組織中的所有使用者建立應用程式，請搜尋 **[共用 Power Apps]** 或 **[共用 Power Virtual Agent Apps]**，選取該應用程式，然後選取 **[允許]**。

### <a name="allow-microsoft-power-platform-apps-for-specific-users"></a>允許特定使用者使用 Microsoft Power Platform 應用程式

若要允許或封鎖貴組織中的特定使用者存取在 Power Apps 或 Power Virtual Agents 中建立的應用程式，請建立並指派一或多個自訂[應用程式權限原則](teams-app-permission-policies.md)。

例如，若要封鎖特定使用者存取在 Power Apps 中建立的應用程式，請建立應用程式許可權的自訂原則來封鎖 **共用的 Power Apps**，然後將原則指派給這些使用者。

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="已封鎖共用 Power Apps 之應用程式許可權範例自訂原則的螢幕擷取畫面。":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>使用稽核記錄調查 Microsoft Power Platform 安裝活動

您可以使用 Teams 的稽核記錄來調查使用者從 Teams [應用程式] 頁面的 **[使用 Power Platform 建置]** 　區段安裝 Microsoft Power Platform 應用程式的事件。 若要這麼做，請搜尋使用者或一組使用者的 **已安裝應用程式** Teams 事件 [稽核記錄](./audit-log-events.md) (在 **[已安裝的應用程式]** 下)。 若要尋找從 **[使用 Power Platform 建置]** 安裝的應用程式，請在指定記錄的詳細資料中尋找 **AppDistributionMode** 屬性中的 **TemplatedInstance** 值。

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="AppDistributionMode 屬性中 TemplatedInstance 值的螢幕擷取畫面。" lightbox="media/manage-power-platform-apps-audit.png":::

> [!NOTE]
> 您可以匯出 CSV 格式的稽核記錄，以便更容易篩選。

## <a name="related-articles"></a>相關文章

* [在 Power Apps 中共用畫布應用程式](/powerapps/maker/canvas-apps/share-app)
* [與其他使用者共用您的 Bot](/power-virtual-agents/admin-share-bots)
* [在 Microsoft Teams 系統管理中心管理應用程式](manage-apps.md)
* [在 Teams 中管理應用程式權限原則](teams-app-permission-policies.md)
* [透過 Teams 應用程式提交 API 發佈自訂應用程式](submit-approve-custom-apps.md)
