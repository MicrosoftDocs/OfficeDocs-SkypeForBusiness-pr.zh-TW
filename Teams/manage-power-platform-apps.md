---
title: 在 Microsoft [團隊管理中心] 中管理 Power Platform 應用程式
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: joglocke
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊系統管理中心中管理 Power Platform app 的存取權。
ms.openlocfilehash: a380a7d8803fc32393f5c99c576cb304e563c296
ms.sourcegitcommit: 96febfae562d604d9affc60028975881f5d6fb7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/20/2020
ms.locfileid: "48599548"
---
# <a name="manage-power-platform-apps-in-the-microsoft-teams-admin-center"></a>在 Microsoft [團隊管理中心] 中管理 Power Platform 應用程式

## <a name="power-platform-apps-in-teams"></a>團隊中的 Power Platform 應用程式

本文將說明如何管理新增至 Microsoft 團隊系統管理中心之小組的 [Power Platform](https://powerplatform.microsoft.com/) app。

[Power app](https://powerapps.microsoft.com) 是低代碼/無代碼應用程式開發環境，貴組織中的開發人員可以使用它來建立連線至您的商務資料的自訂應用程式。 [Power Virtual agent](https://docs.microsoft.com/power-virtual-agents/fundamentals-what-is-power-virtual-agents) 是一種無需開發人員用來建立功能強大的機器人的無程式碼 bot 組建環境。 透過將 Power Platform app 整合成小組，組織可以簡化業務流程、回應不斷變化的業務需求，以促進更大的共同作業，並建立及共用自訂解決方案以提高生產力。  

貴組織中由系統製造商所建立的 Power Platform app 會自動新增至團隊。 使用 power Apps 中的 [共用功能](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) 和 [power Virtual agent 中的共用功能](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)，員工可以控制誰可以存取其應用程式。 

當 Power Platform 應用程式建立或共用時，使用者可以在 [應用程式] 頁面上，透過您的同事建立**的*組織名稱*** 來查看並安裝  >  ** **。  (可能需要幾分鐘的時間，才會在應用程式建立或共用之後，才會顯示應用程式。 ) 

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="[應用程式] 頁面的螢幕擷取畫面，顯示由您的同事建立的 Power Platform app":::

如果應用程式符合下列其中一個條件，使用者就會看到 **由您同事建立** 的 Power Platform 應用程式。

|Power App |Power Virtual Agent  |
|---------|---------|
|<ul><li>使用者建立應用程式。</li><li>App 是直接與使用者共用。</li><li>使用者最近使用過應用程式。 </li></ul>| <ul><li>使用者建立了 bot。</li><li>Bot 是由使用者所屬的小組所擁有。 </li></ul>        |

使用者以安裝任何其他團隊 app 的方式，安裝 Power Platform 應用程式。 請記住，使用者只能將 app 安裝至他們擁有許可權的內容，例如，擁有者擁有的小組、其所屬的聊天或其個人範圍。

## <a name="manage-access-to-power-platform-apps-in-the-microsoft-teams-admin-center"></a>管理 Microsoft 團隊系統管理中心的 Power Platform 應用程式存取權

身為系統管理員，您可以控制 **由您的同事** 在團隊中的 [應用程式] 頁面上所建立的 Power Platform app。 您可以在 [ [管理應用程式](manage-apps.md) ] 頁面上的 [管理 app] 頁面上，或針對特定使用者使用 [app 許可權原則](teams-app-permission-policies.md)，綜合封鎖或允許在 power Virtual agent 中建立的所有 app。

貴組織 app store 中的 [ **共用電源 app** ] 和 [ **共用電源虛擬代理** ] 應用程式代表在該特定平臺上建立的所有 app。 如果您在組織階層或針對特定使用者封鎖其中一個或兩個應用程式，這些使用者就無法看到 **由您的同事建立** 的那些平臺中的任何應用程式，而且無法在小組中安裝它們。  

請記住，您可以控制對 Power App 和 Power Virtual Agent 中所建立之所有 app 的存取，但您無法允許或封鎖個別的應用程式。 在 Power App 和 Power Virtual Agent 中，您可以透過共用功能來決定誰可以存取他們所建立的應用程式。 如果您的 maker 是與使用者在 Power Virtual Agent 中建立的應用程式，而且您已封鎖該使用者的 **共用 Power Virtual Agent 應用** 程式，則使用者將無法在團隊中看到或安裝該平臺中的任何應用程式。

如果允許使用者從 Power Apps 或 Power Virtual Agent 存取應用程式，然後封鎖使用者從這兩個平臺的其中一個或兩個都存取應用程式，使用者仍然可以存取及使用其在您封鎖 app 或應用程式之前所安裝的 Power 平臺應用程式。 不過，使用者不能再看到或安裝來自 **您同事所建**之平臺的任何應用程式。

> [!NOTE]
> [[管理應用程式](manage-apps.md)] 頁面上的 [**允許與自訂應用程式互動] 與**[管理 app] 頁面上的 [全式應用程式] 設定適用于組織中的所有人，並可控制他們是否 全組織式應用程式設定會控制所有使用者的行為，並覆寫指派給使用者的任何其他應用程式許可權原則。 根據預設，此設定為開啟狀態。 如果關閉此設定，貴組織中的使用者將無法看到或安裝任何自訂應用程式，包括 Power Platform app。 若要深入瞭解，請參閱 [管理整個組織內的應用程式設定](manage-apps.md#manage-org-wide-app-settings)。

### <a name="allow-or-block-power-platform-apps-for-your-organization"></a>允許或封鎖貴組織的 Power Platform 應用程式

根據預設，您組織中的所有團隊使用者都可以使用 **共用的 Power app** 和 **共用的 Power Virtual Agent app** 。 您可以在 Microsoft 團隊系統管理中心的 [ [管理應用程式](manage-apps.md) ] 頁面上，在組織階層封鎖或允許。  

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **管理應用程式**]。 您必須是全域系統管理員或團隊服務系統管理員，才能存取該頁面。
2. 在應用程式清單中，執行下列其中一項操作。

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="[管理應用程式] 頁面的螢幕擷取畫面，顯示共用的 Power Platform 應用程式":::

    - 若要封鎖貴組織中所有使用者在 Power App 或 Power Virtual Agent 中建立的應用程式，請搜尋 **共用的 Power app** 或 **共用的 Power Virtual agent 應用程式**，選取它，然後按一下 [ **封鎖**]。
    - 若要允許貴組織中所有使用者在 Power App 或 Power Virtual Agent 中建立的應用程式，請搜尋 **共用的 Power app** 或 **共用的 Power Virtual agent 應用程式**，選取它，然後按一下 [ **允許**]。

### <a name="allow-or-block-power-platform-apps-for-specific-users"></a>針對特定使用者允許或封鎖 Power Platform 應用程式

若要允許或封鎖貴組織中的特定使用者存取在 Power App 或 Power Virtual Agent 中建立的應用程式，請建立並指派一或多個自訂 [應用程式許可權原則](teams-app-permission-policies.md)。 

例如，若要封鎖特定使用者存取在 Power 應用程式中建立的應用程式，請建立自訂應用程式許可權原則來封鎖 **共用的 Power 應用程式**，然後將原則指派給這些使用者。

:::image type="content" source="media/manage-power-platform-apps-app-permissions-policy.png" alt-text="已封鎖共用電源 app 之範例自訂應用程式許可權原則的螢幕擷取畫面":::

### <a name="use-audit-logs-to-investigate-power-platform-installation-activity"></a>使用審核記錄來調查 Power Platform 的安裝活動

您可以使用小組的審核記錄來調查使用者從 [小組] 中的 [應用程式] 頁面上的 [ **由您的同事建立** 的 Power Platform app] 區段中，的事件。 若要這樣做，請在**AppInstalled**作業) 的 [**已安裝的應用程式**小組] (事件中，搜尋特定使用者或一組使用者的 [[審核記錄](https://docs.microsoft.com/microsoftteams/audit-log-events)]。 若要尋找從 [**由您的同事建立**的應用程式] 區段中安裝的 app，請在指定記錄的詳細資料中，尋找**AppDistributionMode**屬性底下的**TemplatedInstance**值。 

> [!NOTE]
> 您可以將審核記錄匯出為 CSV 格式，以便更輕鬆地進行篩選。

## <a name="related-topics"></a>相關主題

- [在 Power 應用程式中共用畫布 app](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app)
- [與其他使用者共用您的機器人](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)
- [在 Microsoft 團隊系統管理中心中管理應用程式](manage-apps.md)
- [在 Teams 中管理應用程式權限原則](teams-app-permission-policies.md)
- [發佈透過團隊 App 提交 API 提交的自訂應用程式](submit-approve-custom-apps.md)
