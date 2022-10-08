---
title: 使用應用程式自訂來為貴組織的需求標上應用程式的商標
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/20/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解如何變更應用程式的中繼資料和外觀，以重新命名應用程式，以便在貴組織中更有效地採用應用程式。
ms.openlocfilehash: 7e2fe4545858980e3fc9d9784aea7b44256d52db
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377471"
---
# <a name="use-app-customization-to-update-branding-of-apps-in-your-organizations-teams-store"></a>使用應用程式自訂來更新貴組織 Teams 市集中應用程式的商標

Microsoft Teams 系統管理員可以修改某些 Teams 應用程式的外觀，為組織使用者提供個人化的品牌體驗。 這類修改可以增強使用者的 Teams 市集體驗，並協助遵守組織的品牌。 例如，系統管理員可以修改應用程式的描述和圖示。 自訂可讓使用者輕鬆識別應用程式為內部工具、瞭解其組織特定的使用案例，以及自信地使用它。 系統管理員透過變更應用程式的一些中繼資料或屬性來進行這些更新。 變更僅適用于其組織內。 這項功能稱為應用程式自訂。

只有當應用程式開發人員允許自訂應用程式時，系統管理員才能自訂應用程式。 雖然 Teams 提供自訂下列屬性的選項，但應用程式開發人員會控制哪些屬性可以由任何系統管理員實際自訂。

* 簡短名稱
* 簡短描述
* 完整描述
* 隱私權原則 URL
* 網站 URL
* 使用規定 URL
* 應用程式圖示
* 圖示的大綱色彩
* 強調色

如需每個屬性的詳細資訊，請參閱 Teams 開發人員檔中的 [Teams 資訊清單架構](/microsoftteams/platform/resources/schema/manifest-schema) 。

> [!NOTE]
> 您必須擁有 Teams 用戶端授權，才能自訂應用程式資訊。

## <a name="verify-if-an-app-is-customizable"></a>確認應用程式是否可自訂

所有應用程式都無法自訂。 如果應用程式開發人員允許自訂其應用程式，則只有這樣您才能修改應用程式的外觀。 若要確認您選擇的應用程式是否可自訂，請遵循下列步驟：

1. 登入 Teams 系統管理中心並存取 **Teams 應用程式**  >  **[管理應用程式](https://admin.teams.microsoft.com/policies/manage-apps)**。

1. 或者，如果看不到 **[可自訂]** 欄，請選取 [編輯欄] :::image type="icon" source="media/settings-icon-16px.svg"::: ，然後將 **[可自訂** ] 選項切換為 [ **開啟]**。

1. 使用應用程式名稱搜尋您要自訂的應用程式。 確認應用程式開發人員是否允許自訂應用程式，請在 **[可自訂]** 欄中確認。

   :::image type="content" source="media/customizable-apps-in-tac.png" alt-text="螢幕擷取畫面顯示系統管理中心的可自訂欄，可協助您確認應用程式是否可自訂。":::

若要找出 Teams 市集中所有可自訂的應用程式，請排序 **[可自訂]** 欄。

## <a name="customize-an-app"></a>自訂應用程式

若要變更貴組織 Teams 市集中應用程式的外觀與風格，請遵循下列步驟：

1. 登入 Teams 系統管理中心並存取 **Teams 應用程式**  >  **[管理應用程式](https://admin.teams.microsoft.com/policies/manage-apps)**。

1. 使用應用程式名稱搜尋您要自訂的應用程式 [，並確保可以自訂](#verify-if-an-app-is-customizable)應用程式。

1. 若要開啟 UI 以自訂個別的元資料欄位，請遵循下列其中一個步驟：

   * 選取應用程式的列，然後在 [管理應用程式] 頁面的工具列中選取 [ **自訂** :::image type="icon" source="media/edit-pen-icon.png"::: ]。

   * 選取應用程式名稱以開啟應用程式詳細資料頁面，然後選取 [**可自訂] 底** 下的編輯圖示 :::image type="icon" source="media/edit-pen-icon.png"::: 。

   * 選取應用程式名稱以開啟應用程式詳細資料頁面，然後選取 **[自訂動作**  >  **]**。

     :::image type="content" source="media/customize-action-menu.png" alt-text="螢幕擷取畫面顯示可開啟 [動作] 功能表，然後從應用程式詳細資料頁面選取 [自訂] 選項來自訂應用程式的選項。" lightbox="media/customize-action-menu-expanded.png":::

1. 自訂一或多個可用欄位。 只有這些元資料欄位會顯示，而且可自訂應用程式開發人員允許的功能。 如需部分欄位的限制，請參閱 [可自訂欄位的考慮與限制](#considerations-and-limitations-of-app-customization)。

   :::image type="content" source="media/customize-settings.png" alt-text="螢幕擷取畫面會顯示自訂使用者介面上的名稱和描述。":::

1. 自訂應用程式之後，選取 **[套用]**。 若要驗證您所做的變更，請參閱 [預覽應用程式詳細資料](#preview-app-customizations)。 若要復原變更，請參閱 [將應用程式詳細資料重設為預設值](#reset-app-details-to-default-values)。

1. 選 **取 [發佈** ] 以將自訂的應用程式發佈到貴組織的市集。

此應用程式會列在 [ **管理應用程式** ] 頁面以及 Teams 市集和用戶端 (中，可透過網頁、行動裝置或桌面用戶端) 取得更新的詳細資料。 修改可能需要幾個小時才會顯示。

## <a name="preview-app-customizations"></a>預覽應用程式自訂

若要在儲存自訂專案後檢視變更，請檢視應用程式詳細資料頁面。

1. 登入 Teams 系統管理中心並存取 **Teams 應用程式**  >  **[管理應用程式](https://admin.teams.microsoft.com/policies/manage-apps)**。

1. 若要開啟應用程式詳細資料頁面，請選取應用程式名稱。

1. 檢視應用程式詳細資料，包括發行者簡短名稱欄位中的原始應用程式 **名稱**。 只有當您變更了應用程式的簡短名稱時，才會顯示欄位。

   :::image type="content" source="media/original-app-version.png" alt-text="螢幕擷取畫面顯示已修改的應用程式簡短名稱。":::

幾個小時後，您的 Teams 使用者就可以在他們的用戶端 (網頁、行動裝置和桌上型電腦) 的 Teams 市集中看到自訂應用程式。

   :::image type="content" source="media/contoso-app.png" alt-text="螢幕擷取畫面顯示 Teams 用戶端中自訂的應用程式。":::

## <a name="considerations-and-limitations-of-app-customization"></a>應用程式自訂的考慮與限制

請考慮下列應用程式自訂功能的詳細資料：

* 您只能自訂 [協力廠商應用程式](deploy-apps-microsoft-teams-landing-page.md#third-party-apps-validated-by-microsoft) ，不能 [自訂應用程式](deploy-apps-microsoft-teams-landing-page.md#custom-apps)。

* 您無法在政府社群雲端高 (GCCH) 和美國商務部 (DoD) 環境中自訂任何應用程式。

* 只有在應用程式開發人員允許時，才能自訂應用程式。

* 任何應用程式的修改只能在貴組織內使用。

* 您只有一個版本的應用程式，因為自訂應用程式詳細資料並不會建立應用程式的複本。

* 當您自訂應用程式以及與應用程式相關的任何描述時，請確定您遵循應用程式開發人員在其檔或使用條款中提供的指導方針。 使用任何協力廠商影像時，請遵守著作權法。

* 管理員提供的自訂資料會儲存在最近的資料儲存區域。

* 您有責任確保使用規定或隱私權原則的連結有效。

* 如果應用程式開發人員不再允許自訂欄位，應用程式詳細資料頁面上會出現一則訊息，通知系統管理員有關該欄位的資訊。 對欄位所做的任何變更都會還原為原始值。

* 建議您先在 Teams 測試租用戶中測試應用程式自訂變更，然後才在生產環境中進行這些變更。 若要取得測試租使用者，請依照 [建立測試租使用者](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant)的指示進行。

* 更新最多需要 24 小時，才能在用戶端中顯示所有使用者和系統管理員帳戶。

* 若要讓現有的應用程式可以自訂，開發人員可以在 Teams 市集中提供應用程式的新版本。

* 應用程式 [使用方式報告](teams-analytics-and-reports/app-usage-report.md) 會顯示發行者所提供的應用程式原始名稱，即使使用者已使用自訂的應用程式。

* Microsoft Graph 權限同意對話方塊會顯示發行者所提供的應用程式原始名稱。 它可協助您正確識別應用程式，同時提供其權限。

* 自訂應用程式並不會變更任何應用程式功能。

部分可自訂欄位的限制如下：

| 可自訂的欄位 | 考慮 |
|:---|:---|
| 任何 URL 欄位 | 確定使用 `https` 有效且安全的 URL。 |
| 簡短描述 | 簡短描述不得超過 80 個字元。 請勿重複完整描述中的內容。 |
| 圖示 | PNG 格式的透明外框圖示解析度為 32x32 圖元。 |
| 色彩圖示 | PNG 格式的全色圖示解析度為 192x192 圖元。 |
| 強調色 | 色彩必須符合您的圖示背景。 |

## <a name="troubleshoot-app-customization"></a>應用程式自訂疑難排解

| 錯誤與問題 | 可能的修正或瞭解問題 |
| --- | --- |
| 我的更新不適用於我的使用者。 | 請等候幾個小時，讓變更散播。 |
| 我無法自訂應用程式。 | 交互檢查應用程式是否 [可自訂](#verify-if-an-app-is-customizable)。|
| 我開始自訂應用程式，但無法儲存或套用我的變更。 | 遵守欄位的限制。 尋找 UI 上的錯誤以及 [應用程式自訂的限制](#considerations-and-limitations-of-app-customization) |
| 管理無法正確載入的應用程式頁面。 應用程式清單不會顯示。 | 管理員使用的帳戶必須已指派 Teams 授權。 |

<!--- Check ICM for error string. --->

## <a name="reset-app-details-to-default-values"></a>將應用程式詳細資料重設為預設值

您可以將應用程式詳細資料重設為應用程式開發人員提供的原始值。 此選項僅適用於您自訂的應用程式。

1. 在 Teams 系統管理中心，存取 **Teams 應用程式** > **[管理應用程式](https://admin.teams.microsoft.com/policies/manage-apps)**。

1. 若要開啟應用程式詳細資料頁面，請選取應用程式名稱。

1. 從 [ **動作]** 功能表中，選取 [ **重設為預設值]**。

   :::image type="content" source="media/reset-app-customization.png" alt-text="螢幕擷取畫面顯示自訂應用程式的重設為預設選項。":::

## <a name="related-articles"></a>相關文章

* [打造貴組織的應用程式市集](customize-your-app-store.md)
* [重新命名您的應用程式社群文章](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
