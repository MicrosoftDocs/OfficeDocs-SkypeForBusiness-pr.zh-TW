---
title: Microsoft Teams App 使用方式報告
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
description: 瞭解如何在 Microsoft Teams 系統管理中心使用 Teams App 使用方式報告。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 29e51e91cdc42000350a48dd0d83225e7791aea6
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460593"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft Teams App 使用方式報告

Microsoft Teams 系統管理中心的 Teams 應用程式使用方式報告會提供使用者在 Teams 中使用哪些應用程式的資訊。  

## <a name="view-the-app-usage-report"></a>查看應用程式使用量報告

1.  在系統管理中心的左側流覽位置，按一下 <https://admin.teams.microsoft.com> **[分析&報告** \> **使用方式報告**。 在顯示 **報表的顯示** 方式中 **，選取在** 報表下的 **應用程式使用量**。

     :::image type="content" source="media/app-usage-report1.png" alt-text="使用方式報告功能表項目的螢幕擷取畫面":::

2.  在 **[日期範圍** 中，選取範圍，然後按一下 [ **執行報表**。

      :::image type="content" source="media/app-usage-report2.png" alt-text="應用程式使用量報告的螢幕擷取畫面":::

## <a name="interpret-the-report"></a>解讀報表

|標注 |說明  |
|--------|-------------|
|**1**   |您可以針對過去 7、30 或 90 天內的趨勢來查看 Teams 應用程式使用量報告。 |
|**2**   |每個報表都有產生報表的日期。 報告通常會反映出從應用程式開啟起 24 小時的延遲。 <br><br>![顯示日期範圍之應用程式使用量報表的螢幕擷取畫面](media/app-usage-report3.png)|
|**3**    | <ul><li>圖表上的 X 軸是特定報表的選取日期範圍。</li><li>Y 軸是將游標暫停于圖表中之日期的使用者數目，這些使用者已開啟應用程式至少一次，如此一來，就視為使用中使用者，並計入滑鼠暫停時看到的總數量。</li></ul>|
|**4**   |將游標停留在代表給定日期之應用程式使用量的點上，以查看該 App 在該日期的總使用中使用者數目。  |
|**5**   |所有應用程式都會包含在內，但選擇篩選圖示，即可使用其他篩選。  |
|**6**   |表格提供使用中使用者和團隊的 App 名稱明細。<br><ul><li>**應用程式名稱** 是 Teams 中所使用的應用程式的顯示名稱。</li><li>**使用中** 使用者是在指定的時段內至少開啟應用程式一次的使用者數目。</li><li>**應用程式類型** 是「Microsoft」或「協力廠商」的靜態值。</li><li>**使用中的** 團隊是團隊中至少有一個成員在指定的時段內開啟應用程式的團隊數目。</li><li>**Publisher** 是 App 的軟體發行者。</li><li>**版本** 是應用程式發行者所提供 App 的軟體版本。</li></ul><b> 注意：</b> 目前，只有頻道中使用的應用程式會計算使用中使用者和使用中團隊。     

<br>![應用程式使用量報表的 ](media/app-usage-report4.png)  螢幕擷取畫面 **| |7 |**  選取 **編輯欄** 以新增或移除表格中的欄。<br><br>![編輯欄頁面的 ](media/app-usage-report5.png)  螢幕擷取畫面 **| |8 |**  您可以將報表匯出為 CSV 檔案，進行離線分析。 按一下 **[匯出至 Excel，** 再按一下 [下載資料標籤上，下載時下載報表已就緒。<br>![下載頁面的螢幕擷取畫面| | ](media/app-usage-report7.png) **9 |**   當您在 Excel 中查看報表時，也會看到代表應用程式識別碼的 **識別碼** 欄。 團隊識別碼通常是一個 Alphanumer 字串。 如果 **識別碼** 欄顯示為 **\n*{，這表示使用者要求刪除其資訊。<br>![下載的 Excel 報表螢幕擷取畫面](media/app-usage-report8.png)  |

## <a name="related-topics"></a>相關主題

- [Teams 分析和報告](teams-reporting-reference.md)