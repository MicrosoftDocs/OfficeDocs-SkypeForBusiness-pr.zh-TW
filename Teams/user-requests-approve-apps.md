---
title: 使用者要求系統管理員允許應用程式
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.collection:
- M365-collaboration
- m365-frontline
ms.reviewer: mhayrapetyan
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: 瞭解如何管理和設定使用者要求，以允許組織中封鎖的應用程式。
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: c47578184aa97f9c6cc366e186c1590ef1e3fba4
ms.sourcegitcommit: ebffec34c050421dc8d09a16907644657ce323f4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/09/2022
ms.locfileid: "67637307"
---
# <a name="manage-user-requests-to-allow-apps-that-are-blocked-by-admins"></a>管理使用者要求以允許系統管理員封鎖的應用程式

您在組織中封鎖的應用程式可能會降低使用者生產力和共同作業。 可在 Teams 市集中取得但組織中封鎖的應用程式無法被使用者使用。 不過，若要掌握資訊，使用者可以檢視封鎖的應用程式、檢視應用程式的資訊，以及它伺服器的使用案例。 在您選擇允許該應用程式之後，使用者可以要求系統管理員核准，讓他們可以在 Teams 中使用這些應用程式。

這項功能可提供有關貴組織內應用程式需求的訊號。 您可以輕鬆檢視應用程式要求的匯總數量，並針對要考慮在貴組織中允許哪些應用程式做出明智的決策。

您保留使用者允許或封鎖之應用程式的完整控制權。 如果您選擇允許應用程式，用來管理應用程式的控制項和 UI 會保持不變。

* 預設選項會在 Teams 系統管理中心傳送使用者要求，您可以在此 [檢視使用者要求並允許要求的應用程式](#view-user-requests-and-allow-the-requested-apps)。

   :::image type="content" source="media/user-request-blocked-apps.png" alt-text="顯示要求系統管理員核准封鎖應用程式選項的螢幕擷取畫面。":::

* 自訂可讓您將使用者重新導向至自訂應用程式要求方法，藉此設定 [使用者體驗](#modify-the-default-setting-to-receive-end-user-requests-to-allow-an-app) 。 您可以提供自訂文字簡訊通知使用者，並將使用者導向貴組織的內部 URL，以收集允許應用程式的要求。

   :::image type="content" source="media/user-request-blocked-apps-redirected.png" alt-text="螢幕擷取畫面顯示當系統管理員將允許應用程式要求 URL 重新導向至自訂 URL 時，市集中應用程式的使用者體驗。":::

## <a name="modify-the-default-setting-to-receive-end-user-requests-to-allow-an-app"></a>修改預設設定以接收使用者要求以允許應用程式

若要設定自訂訊息，並將使用者重新導向至組織專屬的 URL 以要求應用程式核准，請依照下列步驟進行：

1. 登入 Teams 系統管理中心並存取 **Teams 應用程式**  >  **[[管理應用程式]](https://admin.teams.microsoft.com/policies/manage-apps)** 頁面。

1. 選取 [全組織應用程式設定]。

1. 若要在 Teams 用戶端存放區中顯示自訂訊息或指示，請在使用者要求設定中提供簡訊。

1. 若要提供組織專屬的 URL 來收集使用者要求，請執行下列動作：

   1. 將 [將要求重新導向至外部工具] 選項變更為 [開啟]。
   1. 提供您的組織專屬自訂 URL。

      :::image type="content" source="media/user-request-config-org-wide-setting.png" alt-text="螢幕擷取畫面，以切換使用者要求的 URL 自訂，以解除封鎖整個組織設定 UI 中的應用程式。":::

1. 選取 [儲存 **]**。

## <a name="view-user-requests-and-allow-the-requested-apps"></a>檢視使用者要求並允許要求的應用程式

以預設方法收到的使用者要求會顯示在 Teams 系統管理中心。 您可以輕鬆檢視和管理要求。 我們強烈建議定期對終端使用者要求進行分級檢查。 若要檢視和允許應用程式，請遵循下列步驟：

1. 登入 Teams 系統管理中心並存取 **Teams 應用程式**  >  **[[管理應用程式]](https://admin.teams.microsoft.com/policies/manage-apps)** 頁面。

1. 選擇顯示 [ **使用者要求]** 欄。 您也可以排序欄。

   :::image type="content" source="media/user-requests-tac.png" alt-text="螢幕擷取畫面顯示 Teams 系統管理中心中使用者要求的欄，而且可以排序。" lightbox="media/user-requests-tac-expanded.png":::

1. 若要開啟您要允許的應用程式詳細資料頁面，請選取應用程式的名稱。

1. 選 **取 [管理要求]**。

   :::image type="content" source="media/apps-manage-user-requests.png" alt-text="顯示應用程式詳細資料頁面上 [管理要求] 選項的螢幕擷取畫面。" lightbox="media/apps-manage-user-requests-expanded.png":::

1. 依照快顯對話方塊中顯示的下列一或多個步驟進行。 核准應用程式的步驟會根據用來封鎖它的方法而有所不同。

   * 如果應用程式使用許可權原則遭到封鎖， [請修改許可權原則](teams-app-permission-policies.md)。
   * 如果已封鎖所有使用者的應用程式，[請允許該應用程式](manage-apps.md#allow-and-block-apps)。
   * 如果所有使用者都已封鎖所有應用程式，請 [修改整個組織的設定](manage-apps.md#manage-org-wide-app-settings)。

1. 或者，若要切換到您組織特定 URL 的自訂設定，請在 [管理使用者要求] 對話方塊中選取 [設定使用者要求] 連結。 它會開啟全組織應用程式設定窗格，您可以在其中 [設定使用者要求體驗](#modify-the-default-setting-to-receive-end-user-requests-to-allow-an-app)。

如果您在 Teams 系統管理中心收到要求後允許應用程式，則 Teams 不會通知使用者已處理他們的要求。 使用者可以在 Teams 市集中檢查應用程式，以檢查是否允許該應用程式。 允許後，使用者就可以使用 [新增應用程式] 選項。 如果您在透過組織特定的方法收到要求後允許應用程式，則會套用您為使用者提供狀態更新的內部機制。

若要將應用程式要求數重設為零，請關閉要求。 只允許應用程式不會將其要求重設為零。

## <a name="dismiss-user-requests"></a>關閉使用者要求

若要關閉允許應用程式的要求，請遵循下列步驟：

1. 選取您要關閉使用者要求的應用程式名稱。
1. 選取 **[管理要求]**，然後選取 **[解除對話方塊上的所有要求]**。

   :::image type="content" source="media/dismiss-user-requests-apps.png" alt-text="系統管理員可以透過允許應用程式核准使用者要求，也可以解除要求且不執行任何動作。":::

如果您關閉要求，並不會通知使用者已處理他們的要求。 當您關閉允許應用程式的要求時，系統管理中心內的要求會重設為零。 此外，在您關閉要求數小時之後，使用者可以再次要求允許相同的應用程式。

## <a name="related-article"></a>相關文章

* [如何管理協力廠商應用程式的概觀](manage-apps.md)。
