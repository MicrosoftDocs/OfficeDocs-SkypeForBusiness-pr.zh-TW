---
title: 在系統管理中心管理 microsoft Power Platform 應用程式Microsoft Teams管理中心
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
description: 瞭解如何在系統管理中心管理 Microsoft Power Platform 內建的自訂Microsoft Teams存取權。
ms.openlocfilehash: c093d432faa8d4977f4d931ac948a35dc6fe6509
ms.sourcegitcommit: c7b95254dec4420ba0a697fd49d11b448364c919
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2022
ms.locfileid: "63442669"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>在系統管理中心管理 microsoft Power Platform 應用程式Microsoft Teams管理中心

## <a name="microsoft-power-platform-apps-in-teams"></a>Microsoft Power Platform 應用程式Teams

本文提供如何在系統管理中心管理[Microsoft Power Platform](https://powerplatform.microsoft.com/)應用程式Microsoft Teams概觀。

> [!NOTE]
> 本文適用于由貴組織製作人使用或Power Apps建立Power Virtual Agents。 這些自訂應用程式會自動新Teams。 本文不適用於從應用程式頁面Power Apps或Power Virtual Agents透過應用程式設定原則釘Teams的 App 或應用程式。 您可以使用應用程式權限原則和應用程式設定政策，像管理應用程式頁面上任何其他[](manage-apps.md)應用程式一樣管理[這些應用程式](teams-app-setup-policies.md)。[ ](teams-app-permission-policies.md)

[Power Apps](https://powerapps.microsoft.com)是低程式碼/無代碼的應用程式開發環境，貴組織的製造商可以使用這個環境來建立可連接到您商務資料的自訂應用程式。 [Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents)無程式碼的 Bot 建立環境，讓製造商建立功能強大的 Bot。 將 Microsoft Power Platform 應用程式整合至 Teams 後，組織可以簡化商務程式、更快速地回應變更的業務需求，以推動更大的共同作業，以及建立及共用自訂解決方案，以提升生產力。  

由貴組織中製造商所建立之 Microsoft Power Platform 應用程式會自動新Teams。 製作人可以使用應用程式中的共用功能以及 Power Apps 中的共用[](/powerapps/maker/canvas-apps/share-app)功能來控制[誰可以存取其Power Virtual Agents](/power-virtual-agents/admin-share-bots)。

建立或共用 Microsoft Power Platform ****  >  App 時，使用者可以在同事為貴組織建立名稱建立時，在應用程式頁面上查看 **並安裝。**  (建立或共用應用程式後，可能需要幾分鐘的時間，應用程式才能在這裡顯示。) 

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="應用程式頁面的螢幕擷取畫面，顯示同事在建立中所列的 Microsoft Power Platform 應用程式":::

如果應用程式符合下列其中一個條件，使用者會看到同事在內建的應用程式。

|Power 應用程式 |Power Virtual Agents  |
|---------|---------|
|<ul><li>使用者建立了應用程式。</li><li>應用程式已直接與使用者共用。</li><li>使用者最近使用的應用程式。 </li></ul>| <ul><li>使用者建立了 Bot。</li><li>Bot 是由使用者所屬團隊所擁有。 </li></ul>        |

使用者安裝 Microsoft Power Platform App 的方式，與安裝任何其他應用程式Teams相同。 請記住，使用者只能將應用程式安裝至他們有權使用的背景，例如他們擁有的團隊、他們屬於的聊天，或是他們的個人範圍。

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>在系統管理中心管理 Microsoft Power Platform Microsoft Teams存取權

做為系統管理員，您可以控制 Microsoft Power Platform 應用程式是否列在您同事在 Teams 中的應用程式頁面上的建Teams。 您可以共同封鎖或允許在 Power Apps 中建立的所有應用程式，或是在組織層級上Power Virtual Agents或針對使用應用程式權限原則的特定使用者所建立[](manage-apps.md)的所有[應用程式。](teams-app-permission-policies.md)

貴 **Power Apps** 市中的共用 Power **Virtual Agent App** 應用程式代表該特定平臺上建立的所有應用程式。 如果您在組織層級或針對特定使用者封鎖一或兩個這些應用程式，這些使用者無法從同事建集的這些平臺看到任何應用程式，而且無法將它們安裝在 Teams。  

請記住，您可以控制對在 Power Apps 和 Power Virtual Agents 中建立的所有 app 的存取權，但無法允許或封鎖個別的應用程式。 製作人會決定誰可以透過共用功能從 Power Apps Power Virtual Agents。 如果製造商與使用者在 Power Virtual Agents 中建立的應用程式共用，而您封鎖該使用者的共用 **Power Virtual Agents** App，使用者將無法在 Teams 中查看或安裝該平臺的任何應用程式。

如果使用者允許從 Power Apps 或 Power Virtual Agents 存取應用程式，而您接著封鎖使用者從其中一個或兩個平臺存取應用程式，則在您封鎖 App 或 App 之前，使用者仍可存取並使用他們安裝的 Microsoft Power 平臺應用程式。 不過，使用者無法再看到或安裝同事在內建平臺 **的任何應用程式**。

> [!NOTE]
> 在 **管理應用程式頁面上** 的允許與自訂應用程式進行互動的組織應用程式 [](manage-apps.md)設定適用于貴組織中的每個人，並規範他們是否能與自訂應用程式互動。 全組織應用程式設定會控管所有使用者的行為，並覆寫指派給使用者的任何其他應用程式權限原則。 此設定預設會開啟。 如果關閉此設定，貴組織的使用者就看不到或安裝任何自訂應用程式，包括 Microsoft Power Platform App。 若要深入瞭解，請參閱 [管理全組織的應用程式設定](manage-apps.md#manage-org-wide-app-settings)。

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>允許或封鎖貴組織的 Microsoft Power Platform 應用程式

根據預設，**貴Power Apps** 所有使用者都Teams共用和共用 **Power 虛擬** 代理應用程式。 您可以在系統管理中心的管理應用程式頁面上，在組織層級封鎖[](manage-apps.md)或允許Microsoft Teams應用程式。  

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **Teams 應用程式** > **管理應用程式**。 您必須是全域系統管理員或Teams系統管理員才能存取頁面。
2. 在應用程式清單中，執行下列其中一項操作。

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="管理應用程式頁面的螢幕擷取畫面，顯示共用的 Microsoft Power Platform 應用程式":::

    - 若要封鎖在 Power Apps 或 Power Virtual Agents 中為貴組織所有使用者建立的應用程式，請搜尋 [共用 **Power Apps 或** **[共用 Power 虛擬** 代理程式應用程式>，選取它，然後按一下 [**封鎖**。
    - 若要允許在 Power Apps 或 Power Virtual Agents 中為貴組織所有使用者建立的應用程式，請搜尋 [共用 **Power Apps 或** **[共用 Power Virtual Agent Apps**>，選取它，然後按一下 [**允許**。

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>允許或封鎖特定使用者的 Microsoft Power Platform 應用程式

若要允許或封鎖貴組織中特定使用者存取在 Power Apps 或 Power Virtual Agents 中建立的應用程式，請建立並指派一或多個自訂[應用程式權限原則](teams-app-permission-policies.md)。

例如，若要封鎖特定使用者存取在 Power Apps 中建立的應用程式，請建立自訂應用程式權限原則來封鎖共用Power Apps，然後將該策略指派給這些使用者。

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="已封鎖共用帳戶的自訂應用程式許可權Power Apps的螢幕擷取畫面。":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>使用稽核記錄來調查 Microsoft Power Platform 安裝活動

您可以使用稽核記錄Teams，調查使用者從 Teams 中應用程式頁面的 "由同事建立」 區段安裝 Microsoft  Power Platform 應用程式的事件。 若要 [這麼做，請](./audit-log-events.md)針對使用者或一組Teams 在 **App 安裝** (中搜尋已安裝的應用程式) 事件記錄。 若要尋找同事從 **建** 置安裝的應用程式，請尋找特定記錄詳細資料 **中 AppDistributionMode 屬性中的 TemplatedInstance** 值。****

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="AppDistributionMode 屬性中 TemplatedInstance 值的螢幕擷取畫面。":::

> [!NOTE]
> 您可以匯出 CSV 格式的稽核記錄，以便更容易篩選。

## <a name="related-topics"></a>相關主題

- [在應用程式中共用畫布Power Apps](/powerapps/maker/canvas-apps/share-app)
- [與其他使用者共用您的 Bot](/power-virtual-agents/admin-share-bots)
- [在系統管理中心Microsoft Teams應用程式](manage-apps.md)
- [在 Teams 中管理應用程式權限原則](teams-app-permission-policies.md)
- [發佈透過應用程式提交 API Teams提交的自訂應用程式](submit-approve-custom-apps.md)
