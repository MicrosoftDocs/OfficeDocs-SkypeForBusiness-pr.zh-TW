---
title: 使用者要求系統管理員
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
ms.openlocfilehash: 62d34aae25ef1ebff585ea430aeb3db20856669a
ms.sourcegitcommit: 9de6b0b03f433e71fe239d292387eed33c11b531
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/13/2022
ms.locfileid: "67657323"
---
# <a name="manage-user-requests"></a>管理使用者要求

貴組織中封鎖的應用程式可能會影響使用者生產力和共同作業。 使用者無法使用封鎖的應用程式，但可以在 Teams 市集中檢視這類應用程式及其資訊，並要求系統管理員核准。 評估要求之後，您可以選擇允許應用程式或關閉要求。

這項功能可提供有關貴組織內應用程式需求的訊號。 您可以輕鬆檢視每個要求應用程式的要求匯總數量。 它可協助您針對要評估允許的應用程式做出明智的決策。

您保留使用者允許或封鎖之應用程式的完整控制權。 如果您選擇允許應用程式，用來管理應用程式的控制項和 UI 會保持不變。

* 預設選項會將使用者要求傳送到 Teams 系統管理中心，您可以在此 [檢視使用者要求並允許要求的應用程式](#view-user-requests-in-teams-admin-center)。

   :::image type="content" source="media/user-request-blocked-apps.png" alt-text="顯示要求系統管理員核准封鎖應用程式選項的螢幕擷取畫面。":::

* 自訂可讓您設定最適合貴組織的 [使用者體驗](#modify-the-default-setting-to-receive-end-user-requests) 。 您可以提供說明或 Teams App 市集中顯示的自訂訊息，要求核准選項會將使用者導向組織特定的 URL 以收集其要求。

   :::image type="content" source="media/user-request-blocked-apps-redirected.png" alt-text="螢幕擷取畫面顯示當系統管理員將允許應用程式要求 URL 重新導向至組織特定 URL 時，市集中應用程式的使用者體驗。":::

## <a name="view-user-requests-in-teams-admin-center"></a>在 Teams 系統管理中心檢視使用者要求

以預設方法收到的使用者要求會顯示在 Teams 系統管理中心。 您可以輕鬆檢視和管理要求。 我們建議定期分級以檢查使用者要求。 若要檢視和允許應用程式，請遵循下列步驟：

1. 登入 Teams 系統管理中心，然後移至 **Teams 應用程式**  >  [**管理應用程式**](https://admin.teams.microsoft.com/policies/manage-apps)。

1. 選擇顯示 [ **使用者要求]** 欄。 您也可以排序欄。

   :::image type="content" source="media/user-requests-tac.png" alt-text="螢幕擷取畫面顯示 Teams 系統管理中心中使用者要求的欄，而且可以排序。" lightbox="media/user-requests-tac-expanded.png":::

1. 若要開啟您要允許的應用程式詳細資料頁面，請選取應用程式的名稱。

1. 選 **取 [管理要求]**。

   :::image type="content" source="media/apps-manage-user-requests.png" alt-text="顯示應用程式詳細資料頁面上 [管理要求] 選項的螢幕擷取畫面。" lightbox="media/apps-manage-user-requests-expanded.png":::

1. 依照快顯對話方塊中顯示的下列一或多個步驟進行。 核准應用程式的步驟會根據用來封鎖它的方法而有所不同。

   * 如果應用程式使用許可權原則遭到封鎖， [請修改許可權原則](teams-app-permission-policies.md)。
   * 如果已封鎖所有使用者的應用程式，[請允許該應用程式](manage-apps.md#allow-and-block-apps)。
   * 如果所有使用者都已封鎖所有應用程式，請 [修改整個組織的設定](manage-apps.md#manage-org-wide-app-settings)。

使用者可以在 Teams 市集中檢視應用程式的 **[新增** ] 選項，以檢查是否允許該應用程式。 當您在 Teams 系統管理中心收到要求後允許應用程式，則 Teams 不會通知使用者已處理他們的要求。 當您允許應用程式時，要求計數器不會重設為零。

## <a name="modify-the-default-setting-to-receive-end-user-requests"></a>修改預設設定以接收使用者要求

Teams 會提供預設訊息，讓使用者要求應用程式核准。 您可以修改預設設定，以新增含有指示、組織特定 URL 或兩者兼具的自訂郵件。 這些修改會顯示在 Teams 市集中的每個應用程式。

若要設定自訂訊息，並將使用者重新導向至組織專屬的 URL，請遵循下列步驟：

1. 登入 Teams 系統管理中心，然後移至 **Teams 應用程式**  >  [**管理應用程式**](https://admin.teams.microsoft.com/policies/manage-apps)。

1. 在右上角，選取 **[全組織應用程式設定]**。

1. 若要在 Teams 市集中顯示自訂訊息或指示，請在 [ **使用者要求** 設定] 下的文字欄位中輸入文字簡訊。

1. 若要提供組織專屬的 URL 來收集使用者要求，請遵循下列步驟：

   1. 開啟 [ **重新導向外部連結要求]** 切換開關。
   1. 提供您的組織專屬 URL。

      :::image type="content" source="media/user-request-config-org-wide-setting.png" alt-text="螢幕擷取畫面，以切換使用者要求的 URL 自訂，以解除封鎖整個組織設定 UI 中的應用程式。":::

1. 選取 [儲存 **]**。

評估並允許要求之應用程式的方法保持不變。

## <a name="dismiss-user-requests"></a>關閉使用者要求

若要關閉允許應用程式的要求，請遵循下列步驟：

1. 選取您要關閉使用者要求的應用程式名稱。
1. 選 **取 [管理要求]**。
1. 在 [管理使用者要求] 對話方塊中，選 **取 [關閉所有要求]**。

   :::image type="content" source="media/dismiss-user-requests-apps.png" alt-text="系統管理員可以透過允許應用程式核准使用者要求，也可以解除要求且不執行任何動作。":::

如果您關閉要求，並不會通知使用者已處理他們的要求。 當您關閉允許應用程式的要求時，系統管理中心內的要求會重設為零。 此外，在幾小時關閉要求之後，使用者可以再次要求允許相同的應用程式。

## <a name="related-article"></a>相關文章

* [如何管理協力廠商應用程式的概觀](manage-apps.md)。
