---
title: Microsoft Teams 應用程式使用方式報告
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-quhur
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解如何在 Microsoft Teams 系統管理中心使用 Teams 應用程式使用方式報告。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 745761b80bd2507a31cb76cdadc015eac8e9f7fd
ms.sourcegitcommit: a4a65283e85d0c393c844dfd335df0d48e0e4105
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/11/2022
ms.locfileid: "67313925"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft Teams 應用程式使用方式報告

Microsoft Teams 系統管理中心的 Teams 應用程式使用方式報告會提供有關使用者在 Teams 中使用哪些應用程式的資訊。  

## <a name="view-the-app-usage-report"></a>檢視應用程式使用量報告

1. 在 Teams 系統管理中心的左側導覽中，選 **取 [分析&報告**  >  **[使用方式報告。](https://admin.teams.microsoft.com/analytics/reports)**

   :::image type="content" source="media/app-usage-report1.png" alt-text="[使用方式報告] 功能表項目的螢幕擷取畫面。":::

1. 在 [ **檢視報表]** 索引標籤的 [ **報表**] 底下，選取 **[應用程式使用量]**。

1. 在 **[日期範圍]** 底下，選取範圍，然後選取 [ **執行報表]**。 您可以檢視 Teams 應用程式使用方式報告，瞭解過去 7、30 或 90 天的趨勢。

   :::image type="content" source="media/app-usage-report2-trimmed.png" alt-text="[應用程式使用方式報告] 介面的螢幕擷取畫面。" lightbox="media/app-usage-report2.png":::

## <a name="interpret-the-report"></a>解讀報表

:::image type="content" alt-text="Teams 系統管理中心內含圖說文字的 Teams 應用程式使用方式報告螢幕擷取畫面。" source="media/app-usage-report5.png" lightbox="media/app-usage-report5.png":::

每個報表左上方都有一個日期，顯示建立報表的時機。 報告通常會反映應用程式開啟時的 24 小時延遲。

管理員中心提供作用中使用者和日期的圖表。 作用中使用者是指在選取的時段內至少開啟應用程式一次的使用者數目。

將游標停留在點 (4) 代表應用程式在任何日期上的使用量，以查看該應用程式在該日期的使用中使用者總數。

若要選取其他應用程式，請在右上角選取 [ **篩選** ] 圖示 (5) ，選取或輸入新準則，然後選取 [ **套用]**。

報表底部的表格 (6) 依應用程式名稱顯示作用中的使用者和團隊。

   - **應用程式名稱** 是 Teams 中所使用的應用程式的顯示名稱。
   - **作用中使用者** 是指在指定的期間內至少開啟應用程式一次的使用者數目。
   - **應用程式類型** 是「Microsoft」或「協力廠商」的靜態值。
   - **作用中團隊** 是指至少由一位團隊成員在指定的時段內開啟應用程式的團隊數目。
   - **Publisher** 是應用程式的軟體發展人員。
   - **版本** 是應用程式的軟體版本，來自應用程式開發人員。

   > [!NOTE]
   > **作用中使用者** 和 **使用中團隊** 只會針對頻道中使用的應用程式來計算。

若要新增或移除表格中的欄，請在右上角選取 [ **編輯欄** ] 圖示 (7) ，在 [ **編輯欄] 索** 引標籤上，選取新準則，然後選取 [ **套用]**。

若要將報表匯出至 CSV 檔案以進行離線分析，請選取右上角的 [匯出 **至 Excel**] 圖示， (8) ，然後在 [**狀態**] 底下的 [**下載**] 索引標籤上，選取 [**下載]**。

   :::image type="content" alt-text="[下載] 窗格的螢幕擷取畫面。" source="media/app-usage-report7.png" lightbox="media/app-usage-report7.png":::

當您在 Microsoft Excel 中檢視報表時，也會看到代表 `Id` 應用程式識別碼的資料行，通常是英數位元字串。 如果\n值 `Id` **，表示** 使用者要求刪除其資訊。

   :::image type="content" source="media/app-usage-report8.png" alt-text="已下載 Excel 報表的螢幕擷取畫面。":::

## <a name="related-articles"></a>相關文章

- [Teams 分析與報告](teams-reporting-reference.md)
