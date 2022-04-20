---
title: 在 Microsoft Teams 系統管理中心管理 Microsoft Power Platform 應用程式
author: guptaashish
ms.author: guptaashish
manager: prkosh
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
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解如何管理Microsoft Teams系統管理中心內建于 Microsoft Power Platform 的自訂應用程式存取權。
ms.openlocfilehash: c093d432faa8d4977f4d931ac948a35dc6fe6509
ms.sourcegitcommit: bf0071417188b33fc23e2a420187da5024d4bd40
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2022
ms.locfileid: "63442669"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 系統管理中心管理 Microsoft Power Platform 應用程式

## <a name="microsoft-power-platform-apps-in-teams"></a>Teams 中的 Microsoft Power Platform 應用程式

本文提供如何在 Microsoft Teams 系統管理中心管理[Microsoft Power Platform](https://powerplatform.microsoft.com/)應用程式的概觀。

> [!NOTE]
> 本文適用于由貴組織製作者使用Power Apps或Power Virtual Agents建立的自訂應用程式。 這些自訂應用程式會自動新增至Teams。 本文不適用於從 [應用程式] 頁面安裝或透過應用程式設定原則釘選到Teams的Power Apps應用程式或Power Virtual Agents應用程式。 您可以使用[應用程式許可權](teams-app-permission-policies.md)原則和[應用程式設定](teams-app-setup-policies.md)原則，像在 [[管理應用程式](manage-apps.md)] 頁面上管理任何其他應用程式一樣管理這些應用程式。

[Power Apps](https://powerapps.microsoft.com)是低程式碼/無程式碼的應用程式開發環境，組織中的製作者可以使用它來建置可連線至您商務資料的自訂應用程式。 [Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents)是一個無程式碼的 Bot 建立環境，供製作者建立功能強大的 Bot。 隨著 Microsoft Power Platform 應用程式整合至Teams，組織可以簡化商務程式、更快速地回應變更的商務需求，以促進更多共同作業，以及建立和共用自訂解決方案以提高生產力。  

由您組織中的製造商所建立的 Microsoft Power Platform 應用程式會自動新增至Teams。 製作者可以使用 Power Apps[中的共用功能和 Power Virtual Agents 中的共用功能](/powerapps/maker/canvas-apps/share-app)來控制誰可以存取[](/power-virtual-agents/admin-share-bots)他們的應用程式。

當 Microsoft Power Platform 應用程式建立或共用時，使用者可以在 [應用程式] 頁面上檢視並安裝它，方法是移至 **同事****為 *您的組織* 建立的 [**  >  專屬名稱]。  (應用程式建立或共用之後可能需要幾分鐘的時間，應用程式才會顯示在這裡。) 

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="[應用程式] 頁面的螢幕擷取畫面，顯示同事內建的 Microsoft Power Platform 應用程式":::

如果應用程式符合下列其中一個條件，使用者會看到 **同事內建** 的應用程式。

|Power 應用程式 |Power Virtual Agents  |
|---------|---------|
|<ul><li>使用者已建立應用程式。</li><li>應用程式已直接與使用者共用。</li><li>使用者最近使用過此應用程式。 </li></ul>| <ul><li>使用者已建立 Bot。</li><li>Bot 由使用者所屬的團隊所擁有。 </li></ul>        |

使用者安裝 Microsoft Power Platform 應用程式的方式，與安裝任何其他Teams應用程式的方式相同。 請記住，使用者只能將應用程式安裝到他們擁有許可權的上下文，例如，他們擁有的團隊、屬於其一部分的聊天，或是其個人範圍。

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>管理Microsoft Teams系統管理中心的 Microsoft Power Platform 應用程式存取權

身為系統管理員，您可以控制您的同事是否在 Teams 的 [應用程式] 頁面上，將 Microsoft Power Platform 應用程式列在 [**內建**] 中。 您可以在 [[管理](manage-apps.md)應用程式] 頁面上，或針對使用應用程式許可權原則的特定使用者，共同封鎖或允許在 Power Virtual Agents Power Apps或以組織層級以組織層級建立的所有[應用程式](teams-app-permission-policies.md)。

貴組織應用程式市集中的 **共用Power Apps** 和 **共用 Power Virtual Agent Apps 應用程式** 代表在該特定平臺上建立的所有應用程式。 如果您在組織層級或針對特定使用者封鎖其中一個或兩個應用程式，這些使用者就無法在 **您的同事建立** 的這些平臺中看到任何應用程式，也無法在Teams中安裝它們。  

請記住，您可以控制存取在 Power Apps 和 Power Virtual Agents 中建立的所有應用程式，但您無法允許或封鎖個別應用程式。 製作者決定誰可以從Power Apps和Power Virtual Agents內透過共用功能存取他們建立的應用程式。 如果製作程式與使用者共用他們在 Power Virtual Agents 中建立的應用程式，而且您已封鎖該使用者的 **共用Power Virtual Agents應用程式**，使用者將無法在 Teams 中查看或安裝該平臺中的任何應用程式。

如果允許使用者從Power Apps或Power Virtual Agents存取應用程式，然後封鎖使用者存取來自一或兩個這些平臺的應用程式，使用者仍然可以存取和使用在您封鎖應用程式之前所安裝的 Microsoft Power 平臺應用程式。 不過，使用者再也無法看到或安裝 **同事所建置** 這些平臺中的任何應用程式。

> [!NOTE]
> [[管理](manage-apps.md)應用程式] 頁面上的 [**允許與自訂應用程式** 互動] 應用程式設定會套用至貴組織中的每個人，並規範他們是否可以與自訂應用程式互動。 全組織應用程式設定會控管所有使用者的行為，並覆寫指派給使用者的任何其他應用程式權限原則。 此設定預設會開啟。 如果關閉此設定，您組織中的使用者就無法看到或安裝任何自訂應用程式，包括 Microsoft Power Platform 應用程式。 若要深入瞭解，請參閱 [管理整個組織的應用程式設定](manage-apps.md#manage-org-wide-app-settings)。

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>允許或封鎖貴組織的 Microsoft Power Platform 應用程式

根據預設，貴組織中的所有 **Teams** 使用者皆可使用共用Power Apps和 **共用 Power Virtual Agent Apps**。 您可以在系統管理中心的 [[管理應用程式](manage-apps.md)] Microsoft Teams 頁面上，于組織層級封鎖或允許它們。  

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **Teams 應用程式** > **管理應用程式**。 您必須是全域系統管理員或Teams服務系統管理員才能存取頁面。
2. 在應用程式清單中，執行下列其中一項操作。

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="[管理應用程式] 頁面的螢幕擷取畫面，顯示共用的 Microsoft Power Platform 應用程式":::

    - 若要封鎖在Power Apps或Power Virtual Agents中為貴組織中的所有使用者建立的應用程式，請搜尋 [**共用Power Apps**] 或 [**共用 Power Virtual Agent Apps**]，選取它，然後按一下 [**封鎖]**。
    - 若要允許在Power Apps或Power Virtual Agents中為貴組織中的所有使用者建立應用程式，請搜尋 **[共用Power Apps**] 或 [**共用 Power Virtual Agent Apps**]，選取它，然後按一下 [**允許]**。

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>允許或封鎖特定使用者的 Microsoft Power Platform 應用程式

若要允許或封鎖貴組織中的特定使用者存取以Power Apps或Power Virtual Agents建立的應用程式，請建立並指派一或多個自訂[應用程式許可權原則](teams-app-permission-policies.md)。

例如，若要封鎖特定使用者存取在 Power Apps 中建立的應用程式，請建立自訂應用程式許可權原則來封鎖 **共用Power Apps**，然後將原則指派給這些使用者。

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="已封鎖 [共用Power Apps的自訂應用程式許可權原則範例螢幕擷取畫面。":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>使用稽核記錄調查 Microsoft Power Platform 安裝活動

您可以使用Teams的稽核記錄來調查使用者從 Teams 中 [應用程式] 頁面的同事 **所建置** 區段安裝 Microsoft Power Platform 應用程式的事件。 若要這麼做，請搜尋 [已安裝的 **應用程式**] Teams事件的 [稽核記錄](./audit-log-events.md) (在 **[已安裝的應用程式**] 作業) 底下，搜尋使用者或一組使用者。 若要尋找 **由同事所建置的** 應用程式，請在指定記錄的詳細資料中尋找 **AppDistributionMode** 屬性中的 **TemplatedInstance** 值。

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="AppDistributionMode 屬性中 TemplatedInstance 值的螢幕擷取畫面。":::

> [!NOTE]
> 您可以匯出 CSV 格式的稽核記錄，以便更容易篩選。

## <a name="related-topics"></a>相關主題

- [在 Power Apps 中共用畫布應用程式](/powerapps/maker/canvas-apps/share-app)
- [與其他使用者共用您的 Bot](/power-virtual-agents/admin-share-bots)
- [在Microsoft Teams系統管理中心管理應用程式](manage-apps.md)
- [在 Teams 中管理應用程式權限原則](teams-app-permission-policies.md)
- [發佈透過 Teams 應用程式提交 API 提交的自訂應用程式](submit-approve-custom-apps.md)
