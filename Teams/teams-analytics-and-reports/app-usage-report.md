---
title: Microsoft 團隊 app 使用方式報告
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-quhur
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解如何在 Microsoft 團隊系統管理中心使用團隊 app 使用方式報告。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 91af37ed9c19a1d3e8d32cdf296cf32e90818564
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583792"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft 團隊 app 使用方式報告

Microsoft [小組] 系統管理中心中的 [小組 app 使用量] 報告，可讓您在小組中提供使用者使用哪些 app 的相關資訊。  

## <a name="view-the-app-usage-report"></a>查看應用程式使用量報告

1.  在系統管理中心的左側導覽中 <https://admin.teams.microsoft.com> ，按一下 [**分析] & 報告** \> **使用方式報告**。 在 [**查看報表**] 索引標籤的 [**報表**] 底下，選取 [ **app 使用方式**]。

     :::image type="content" source="media/app-usage-report1.png" alt-text="[使用狀況報告] 功能表項目的螢幕擷取畫面":::

2.  在 [**日期範圍**] 底下，選取一個範圍，然後按一下 [**執行報表**]。

      :::image type="content" source="media/app-usage-report2.png" alt-text="[應用程式使用量] 報告的螢幕擷取畫面":::

## <a name="interpret-the-report"></a>解讀報表

|圖說文字 |描述  |
|--------|-------------|
|**1**   |您可以針對過去7、30或90天的趨勢，查看團隊 App 使用方式報告。 |
|**2**   |每個報告都有產生報告的日期。 報告通常會反映來自開啟 app 時間的24小時延遲時間。 <br><br>![顯示日期範圍之 [應用程式使用量] 報告的螢幕擷取畫面](media/app-usage-report3.png)|
|**3**    | <ul><li>圖表上的 X 軸是特定報表的已選取日期範圍。</li><li>Y 軸是在圖表中停留在指定日期的使用者數目，這些使用者至少已開啟一次 app，而且這樣做會被視為作用中的使用者，並計入滑鼠暫留上所看到的總數。</li></ul>|
|**4**   |將游標暫留在代表指定日期應用程式使用量的點上，即可查看該應用程式在該日期的總作用中使用者的實例數。  |
|**500**   |所有 App 都將包含，但在選擇 [篩選] 圖示之後，就可以使用其他篩選器。  |
|**6**   |表格會依 App 名稱提供作用中使用者和小組的明細。<br><ul><li>[**應用程式名稱**] 是在 [團隊] 中使用之應用程式的顯示名稱。</li><li>[作用中的**使用者**] 是指在指定的時段內至少開啟過一次 app 的使用者數目。</li><li>**應用程式類型**是「Microsoft」或「協力廠商」的靜態值。</li><li>[作用中的**團隊**] 是由團隊中至少一個成員以及在指定的時段內開啟 App 的團隊數目。</li><li>**Publisher**是 app 的軟體發行者。</li><li>**版本**是應用程式的軟體版本（來自 app 發行者）。</li></ul><br>![App 使用方式報告的螢幕擷取畫面](media/app-usage-report4.png)  |
|**utf-7**  |選取 [**編輯欄**] 以新增或移除表格中的欄。<br><br>![[編輯欄] 頁面的螢幕擷取畫面](media/app-usage-report5.png)  |
|**型**  |您可以將報表匯出為 CSV 檔案，以便進行離線分析。 按一下 [**匯出至 Excel**]，然後在 [**下載**] 索引標籤上，按一下 [**下載**] 以在準備好時下載報告。<br>![[下載] 頁面的螢幕擷取畫面](media/app-usage-report7.png)  |
|**9**   |當您在 Excel 中查看報表時，您也會看到 [**識別碼**] 欄，代表 [應用程式識別碼]。 團隊識別碼通常是一個字母數位字串。 如果 [**識別碼**] 欄顯示為 * * \n * * * *，這表示使用者要求刪除其資訊。<br>![下載的 Excel 報表螢幕擷取畫面](media/app-usage-report8.png)  |

## <a name="related-topics"></a>相關主題

- [團隊分析和報告](teams-reporting-reference.md)