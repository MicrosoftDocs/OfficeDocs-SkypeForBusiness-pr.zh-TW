---
title: 修改貴組織Teams市集中應用程式的外觀
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams 中自訂應用程式。
ms.openlocfilehash: 3f8a8a3c1922de230573628926a1aff2eee6ee06
ms.sourcegitcommit: e38dc23e3968f55625e90c8883884045f80d22ee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2022
ms.locfileid: "66124368"
---
# <a name="customize-appearance-of-apps-in-your-organizations-teams-store"></a>自訂貴組織Teams市集中應用程式的外觀

Microsoft Teams可讓系統管理員自訂Teams應用程式，以增強店面體驗並遵守組織品牌。 應用程式開發人員可以允許Teams系統管理員自訂其應用程式。接著，您可以在系統管理中心的 [管理應用程式] Teams 頁面中，根據組織需求更新應用程式屬性。 您可以自訂的詳細資料包括：

* 簡短名稱
* 簡短描述
* 完整描述
* 隱私權原則 URL
* 網站 URL
* 使用規定 URL
* 應用程式圖示
* 圖示的外框色彩
* 輔色

如需應用程式各種元資料欄位的相關資訊，請參閱開發人員檔中的[Teams資訊清單架構](/microsoftteams/platform/resources/schema/manifest-schema)。

> [!NOTE]
> 您無法自訂任何組織中的側載應用程式。 您無法在 政府社群雲端 High (GCCH) 或美國商務部 (DoD) 雲中自訂任何應用程式。

## <a name="customize-details-of-an-app"></a>自訂應用程式的詳細資料

若要自訂應用程式，請完成下列步驟：

1. 登入 Teams 系統管理中心。

1. 展開 **Teams應用程式**，然後選取 **[[管理應用程式]](https://admin.teams.microsoft.com/policies/manage-apps)**。

1. 檢查應用程式清單的 **[可自訂** ] 欄，並依可自訂的應用程式排序。

   ![系統管理中心的自訂欄可協助您查看可自訂的應用程式。](media/customizable-apps-in-tac.png)

   存取自訂功能有三個進入點：

   * 選取您要自訂之應用程式旁邊的，然後選取 [ **自訂]**。

     ![自訂選取範圍選項 1.](media/select-app-to-customize1.png)

   * 選取應用程式名稱，然後選取 [ **可自訂**] 中的編輯圖示。

     ![自訂選取範圍選項 2。](media/communities-microsoft.png)

   * 選取應用程式名稱，按一下 [動作 **] 上的****溢位功能表** 暫留，然後選取 [自訂]。

     ![自訂選取範圍選項 3.](media/customize-action-menu.png)

1. 展開 [ **詳細資料]** 區段並自訂下列一或多個欄位。 可由開發人員指定為可自訂的欄位會顯示。

    * 簡短名稱
    * 簡短描述
    * 完整描述
    * 網站
    * 隱私權原則 URL
    * 使用規定 URL

   ![自訂設定。](media/customize-settings.png)

1. 展開 **[圖示]** 區段。

1. Upload圖示。 使用 PNG 格式的圖示 (192 x 192) 圖元。

1. 選擇圖示外框色彩。 使用 PNG 格式的透明外框 (32x32) 圖元。

1. 選取符合圖示的應用程式輔色。

   ![自訂圖示面板色彩選項。](media/customize-app-colors.png)

1. 自訂應用程式之後，選取 [ **套用]**。

1. 選 **取 [發佈** ] 以發佈自訂的應用程式。

   自訂應用程式現在會列在 [ **管理應用程式** ] 頁面中。 您只有一個版本的應用程式，因為自訂應用程式功能並不會建立應用程式的複本。

現在您的Teams使用者可以在用戶端中看到自訂的應用程式。

   ![Teams用戶端中的自訂應用程式。](media/contoso-app.png)

請注意自訂應用程式的下列詳細資料：

* 當您自訂應用程式，以及任何與應用程式相關的描述時，如果應用程式發行者在其檔或使用條款中提供，請確定您遵循任何自訂指導方針。 對於您可能使用的任何協力廠商影像，您也必須尊重他人的權利。

* 管理員提供的自訂資料會儲存在最接近的地區。

* 您必須負責確保使用規定或隱私權原則的連結有效。

* 如果應用程式發行者不再允許可自訂欄位，應用程式詳細資料頁面上會出現一則訊息，通知系統管理員有關無法再自訂的欄位。 對該欄位所做的所有變更將會還原為原始值。

* 建議您先在Teams測試租使用者中測試應用程式自訂變更，然後再在您的生產環境中進行這些變更。

* 商標變更最多可能需要 24 小時，才能傳播到所有使用者。

* 開發人員可以提供應用程式的新版本，讓應用程式可以自訂。 您上傳新版本，並移除舊版的應用程式。 如果您已自訂併發布應用程式，使用應用程式自訂功能自訂的新應用程式將不會取代目前的應用程式。

* [應用程式使用方式報告](teams-analytics-and-reports/app-usage-report.md)會顯示發行者所提供的應用程式原始名稱。

* [Microsoft Graph許可權同意] 對話方塊會顯示發行者所提供的應用程式原始名稱。 它可協助您在提供許可權時準確識別應用程式。

## <a name="review-app-details"></a>檢閱應用程式詳細資料

您可能會想要查看應用程式詳細資料以檢閱資訊。

1. 登入 Teams 系統管理中心。

1. 展開 **Teams應用程式**，然後選取 **[[管理應用程式]](https://admin.teams.microsoft.com/policies/manage-apps)**。

1. 選取應用程式名稱。

1. 檢視應用程式詳細資料，包括原始應用程式名稱 **發行者提供的簡短名稱**。

   ![自訂圖示面板應用程式名稱。](media/original-app-version.png)

   只有當您變更了應用程式的簡短名稱時，才會顯示 **發行** 者的簡短名稱欄位。

## <a name="reset-app-details-to-default-values"></a>將應用程式詳細資料重設為預設值

您可以將應用程式詳細資料重設為應用程式開發人員提供的原始值。 此選項僅適用于您自訂的應用程式。

1. 在Teams系統管理中心，存取 **Teams應用程式**  >  **[管理應用程式。](https://admin.teams.microsoft.com/policies/manage-apps)**

1. 選取應用程式名稱。

1. 從 [動作] 功能表選取 [**重設為預設****值**]。

   ![選取 [重設] 以醒目提示預設值。](media/select-reset.png)

## <a name="related-article"></a>相關文章

* [管理應用程式](manage-apps.md)
* [自訂群組織的 App Store](customize-your-app-store.md)
* [重新命名您的應用程式](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
