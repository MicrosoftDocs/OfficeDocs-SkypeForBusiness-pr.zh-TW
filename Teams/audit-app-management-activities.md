---
title: 搜尋應用程式管理事件的稽核記錄
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 12/02/2022
ms.collection:
- M365-collaboration
search.appverid: MET150
f1keywords: ''
description: 了解如何稽核貴組織中使用者和系統管理員的 Teams 應用程式活動。
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 9114bae9fa24a546aec2629f1f347af193b10fd5
ms.sourcegitcommit: 339a35e461c84ee309ade1a53299ba12231df7a3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/29/2022
ms.locfileid: "69677503"
---
# <a name="search-audit-logs-for-app-management-activities-and-events"></a>搜尋應用程式管理活動和事件的稽核記錄

Microsoft 365 中的 Microsoft Purview 稽核 (標準版) 可讓您按使用者和系統管理員搜尋在各種 Microsoft 365 服務中執行之活動的稽核記錄。

在搜尋稽核記錄之前，請確定您完成下列必要條件：

* [取得組織的訂閱和使用者授權](/microsoft-365/compliance/set-up-basic-audit)。
* [在 Microsoft Purview 合規性入口網站中開啟稽核功能](/microsoft-365/compliance/turn-audit-log-search-on-or-off)。
* [指派搜尋稽核記錄的權限](/microsoft-365/compliance/set-up-basic-audit)。

## <a name="search-the-audit-logs-for-app-events-in-teams"></a>搜尋 Teams 中應用程式事件的稽核記錄

Teams 中應用程式事件的稽核記錄可協助您調查系統管理員與應用程式管理相關的特定動作。 雖然您可以搜尋記錄檔以尋找各種動作，但下表列出一些記錄的動作。

| Teams 應用程式動作 | 入口網站中的活動名稱 | 描述  |
|-------|-------|:-------|
| **已安裝的應用程式**                 | `AppInstalled`               | 應用程式隨即安裝或新增至 Teams 用戶端。 |
| **已升級應用程式**                  | `AppUpgraded`                | 應用程式已升級至目錄中的最新版本。 |
| **已解除安裝的應用程式**               | `AppUninstalled`             | 應用程式已從 Teams 用戶端卸載或移除。                                   |
| **已發佈的應用程式**                 | `AppPublishedToCatalog`      | 應用程式已新增至目錄。                          |
| **已更新的應用程式**                   | `AppUpdatedInCatalog`        | 目錄中已更新應用程式。                        |
| **已刪除應用程式**                   | `AppDeletedFromCatalog`      | 已從目錄中刪除應用程式。                      |
| **已刪除所有組織應用程式** | `DeletedAllOrganizationApps` | 已從目錄中刪除所有組織應用程式。          |

<!--- organization apps = custom or 3p --->

如需已稽核的完整 Teams 活動清單，請參閱 [Teams 活動](audit-log-events.md#teams-activities) 和 [Teams 活動中的班次](audit-log-events.md#shifts-in-teams-activities)。

> [!NOTE]
> 當這些活動在 Teams 和標準頻道中完成時，也會記錄來自私人頻道的應用程式事件。

若要搜尋 Teams 應用程式活動的稽核記錄，請遵循下列步驟：

1. 登入 Microsoft Purview 合規性入口網站，然後移至 **解決方案** > **[稽核](https://compliance.microsoft.com/auditlogsearch)**。
1. 在 [ **稽核** ] 頁面上，視需要更新下欄欄位：

   * **日期和時間範圍**：選取您要檢查稽核記錄之時段的開始和結束日期。
   * **活動**：輸入 Microsoft Teams 活動。 從清單中，選取一或多個應用程式活動。 若要快速尋找 Teams 活動，您可以在 **[活動]** 搜尋欄位中搜尋字詞 `Teams activities`。
   * **檔案、資料夾或網站**：輸入檔案名稱、URL 或其中一部分。
   * **使用者**：新增您想要搜尋其稽核記錄的使用者。

1. 選取 **[搜尋]**。

   :::image type="content" source="media/compliance-search-teams-activities-trimmed.png" alt-text="在 Microsoft Purview 合規性入口網站中搜尋 Teams 活動以稽核 Teams 事件。" lightbox="media/compliance-search-teams-activities.png":::

您可以將搜尋的稽核記錄匯出為 CSV 檔案。 如需詳細資訊，請參閱 [匯出、設定及檢視稽核記錄](/microsoft-365/compliance/export-view-audit-log-records)。

> [!NOTE]
> 當上述其中一項活動是由使用者或系統管理員執行時，Teams 會產生並儲存稽核記錄。 在稽核 (標準版) 中，記錄都會保留 90 天，這意味著您可以搜尋過去三個月內發生的活動。

> [!TIP]
> 身為系統管理員，如果您想要建立每個使用者的報告，以瞭解使用者是否已封鎖或將 Bot 設為靜音，請參閱 [瞭解誰已封鎖、靜音或卸載 Bot](/microsoftteams/platform/bots/how-to/conversations/send-proactive-messages?#understand-who-blocked-muted-or-uninstalled-a-bot)。

## <a name="related-articles"></a>相關文章

* [使用稽核記錄來調查Microsoft Power Platform 安裝活動](manage-power-platform-apps.md#use-audit-logs-to-check-microsoft-power-platform-installation-activity)。
* [在合規性入口網站中搜尋稽核記錄](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)。
* [Microsoft Purview 稽核進階版概觀](/microsoft-365/compliance/advanced-audit)。
* [開啟或關閉稽核](/microsoft-365/compliance/turn-audit-log-search-on-or-off)。
