---
title: Microsoft Teams應用程式使用方式報告
author: SerdarSoysal
ms.author: serdars
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
description: 瞭解如何在系統管理中心Teams應用程式使用方式Microsoft Teams報告。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f58634bea7a2846e35ddc4dbc8da0be13396e616
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/01/2021
ms.locfileid: "60046009"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft Teams應用程式使用方式報告

系統Teams系統管理中心Microsoft Teams應用程式使用方式報告會提供使用者在應用程式中使用哪些應用程式Teams。  

## <a name="view-the-app-usage-report"></a>查看應用程式使用方式報告

1.  在系統管理中心的左側流覽中，按一下 [分析& <https://admin.teams.microsoft.com> **報告** \> **使用方式報告**。 On the **View reports** tab, under **Report**, select **Apps Usage**.

     :::image type="content" source="media/app-usage-report1.png" alt-text="使用方式報告功能表項目的螢幕擷取畫面。":::

2.  在 **[日期範圍**」 下，選取範圍，然後按一下 [ **執行報表**> 。

      :::image type="content" source="media/app-usage-report2.png" alt-text="應用程式使用方式報表的螢幕擷取畫面。":::

## <a name="interpret-the-report"></a>解譯報表

|標注 |描述  |
|--------|-------------|
|**1**   |您可以Teams應用程式使用方式報告，查看過去 7、30 或 90 天內的趨勢。 |
|**2**   |每個報表都有產生報表的日期。 報告通常會反映從應用程式開啟起 24 小時的延遲。 <br><br>![顯示日期範圍之應用程式使用量報表的螢幕擷取畫面。](media/app-usage-report3.png)|
|**3**    | <ul><li>圖表上的 X 軸是特定報表的選取日期範圍。</li><li>Y 軸是將游標暫停在圖表中的一天、這些使用者已開啟應用程式至少一次的使用者數目，如此一來，就被視為使用中使用者，並累算到滑鼠游標暫停時所看到的總數。</li></ul>|
|**4**   |將游標停留在代表給定日期之應用程式使用量的點上，以查看該 App 在給定日期的總使用中使用者數目。  |
|**5**   |所有應用程式都會包含在內，但選擇篩選圖示，即可使用其他篩選。  |
|**6**   |資料表會提供使用中使用者和團隊的 App 名稱明細。<br><ul><li>**應用程式名稱** 是應用程式在 Teams 中使用的顯示Teams。</li><li>**使用中** 使用者是在指定的時段內至少開啟應用程式一次的使用者數目。</li><li>**應用程式類型** 是「Microsoft」或「協力廠商」的靜態值。</li><li>**使用中** 團隊是團隊中至少有一個成員在指定的時段內開啟 App 的團隊數目。</li><li>**Publisher** 應用程式的軟體發行者。</li><li>**版本** 是應用程式發行者所提供之應用程式的軟體版本。</li></ul><b> 注意：</b> 目前，僅針對頻道中使用的應用程式計算 'Active 使用者'和 'Active teams'。     
<br>![應用程式使用方式報表的螢幕擷取畫面。](media/app-usage-report4.png)|
|**7**  |選取 **編輯欄** 以新增或移除表格中的欄。<br><br>![編輯欄頁面的螢幕擷取畫面。](media/app-usage-report5.png)  |
|**8**  |您可以將報表匯出至 CSV 檔案，進行離線分析。 按一下 **[匯出Excel，** 然後在 [下載>選項卡上，按一下[下載以在報表準備就緒時下載報表。<br>![下載頁面的螢幕擷取畫面。](media/app-usage-report7.png)  |
|**9**   |當您在 Excel中查看報表時，您也會看到代表應用程式識別碼的 **識別碼** 欄。 團隊識別碼通常是一個數位字串。 如果 **識別碼欄** 顯示為 **\n***，這表示使用者要求刪除其資訊。<br>![下載的報表Excel螢幕擷取畫面。](media/app-usage-report8.png)  |

## <a name="related-topics"></a>相關主題

- [Teams 分析與報告](teams-reporting-reference.md)