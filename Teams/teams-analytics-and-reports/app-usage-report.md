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
ms.openlocfilehash: 7679652f0cb93e445e72af80307803b1e3197992
ms.sourcegitcommit: b57e19e20900ff02f3196c811bf1dd1acd149c79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2021
ms.locfileid: "60596210"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft Teams應用程式使用方式報告

Teams系統管理中心中的 Microsoft Teams應用程式使用方式報告會提供使用者在 Teams 中使用哪些應用程式的資訊。  

## <a name="view-the-app-usage-report"></a>查看應用程式使用方式報告

1. 在系統管理中心的左側流覽中，按一下 [分析& <https://admin.teams.microsoft.com> **報告**  >  **使用方式報告**。<br><br>![使用方式報告功能表項目的螢幕擷取畫面。](media/app-usage-report1.png "使用方式報告功能表項目的螢幕擷取畫面。")
2. On the **View reports** tab, under **Report**, select **Apps Usage**.

3. 在 **[日期範圍**」 下，選取範圍，然後按一下 [ **執行報表**> 。 您可以Teams應用程式使用方式報告，查看過去 7、30 或 90 天內的趨勢。<br><br>![應用程式使用方式報表的螢幕擷取畫面。](media/app-usage-report2.png "應用程式使用方式報表的螢幕擷取畫面。")


## <a name="interpret-the-report"></a>解譯報表

:::image type="content" alt-text="螢幕擷取畫面顯示 Teams系統管理中心內具有圖說Teams應用程式使用方式報告。" source="media/app-usage-report5.png" lightbox="media/app-usage-report5.png":::

1. 每個報表的左上角都有一個日期，顯示報表的建立時間。 報表通常會反映從應用程式開啟起 24 小時的延遲。

2. 圖表上的 Y 軸是將游標停留在圖表上所選取日期的使用者數目，因為已開啟應用程式至少一次，因此被視為使用中使用者。

3. 圖表上的 X 軸是您為報表選取的日期範圍。

4. 將游標停留在代表應用程式在任何日期使用量的點上，以查看該日期該 App 的使用中使用者總數。

5. 若要選取其他應用程式，請按一下右上角的 [篩選圖示，選取或輸入新準則，然後按一下 **[Apply.**

6. 報表底部的表格會以應用程式名稱顯示使用中使用者和團隊。

   - **應用程式名稱** 是應用程式在 Teams 中使用的顯示Teams。
   - **使用中** 使用者是在指定的時段內至少開啟應用程式一次的使用者數目。
   - **應用程式類型** 是「Microsoft」或「協力廠商」的靜態值。
   - **使用中** 團隊是團隊中至少有一個成員開啟 App 的團隊數目，以及指定時段內開啟應用程式的團隊數目。
   - **Publisher** 應用程式的軟體發行者。
   - **版本** 是應用程式發行者所提供之應用程式的軟體版本。

   > [!NOTE]
   > **活動使用者****和使用中團隊** 只會針對頻道中使用的應用程式進行計算。

7. 若要新增或移除表格中的欄，請按一下右上角的 [編輯欄圖示，在 [編輯欄索引行索引鍵中，選取新準則，然後按一下 **[Apply.**

8. 若要將報表匯出至 CSV 檔案進行離線分析，請選取右上角的 [匯出至 Excel 圖示，然後在 [狀態> 下的[下載 **Excel** 上，按一下 [**下載**。

   :::image type="content" alt-text="下載窗格的螢幕擷取畫面。" source="media/app-usage-report7.png" lightbox="media/app-usage-report7.png":::

9. 當您在 Excel中查看報表時，您也會看到一個 Id欄，代表應用程式識別碼，通常是字母數位字串。 如果 **識別碼****\n，** 這表示使用者要求刪除他們的資訊。

   ![下載的報表Excel螢幕擷取畫面。](media/app-usage-report8.png "下載的報表Excel螢幕擷取畫面。")

## <a name="related-topics"></a>相關主題

- [Teams 分析與報告](teams-reporting-reference.md)
