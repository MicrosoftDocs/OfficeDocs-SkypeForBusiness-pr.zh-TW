---
title: Microsoft 團隊使用者活動報告
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解如何使用 Microsoft 團隊系統管理中心的 [小組使用者活動] 報告，查看貴組織中的使用者使用團隊的方式。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9516c7ed39a56e09bb714f58e988dc46b41ec9e2
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2020
ms.locfileid: "43903868"
---
# <a name="microsoft-teams-user-activity-report"></a>Microsoft 團隊使用者活動報告

[團隊使用者活動] 報告可讓您深入瞭解貴組織中的使用者在團隊中執行的活動類型。 例如，您可以查看有多少使用者透過1:1 通話進行通訊，以及多少使用者透過通道訊息通訊，以及有多少使用者參與私人聊天訊息。

## <a name="view-the-user-activity-report"></a>查看使用者活動報告

1. 在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**分析] & 報告** > **使用方式報告**。 在 [**查看報表**] 索引標籤的 [**報表**] 底下，選取 [**團隊使用者活動**]。
2. 在 [**日期範圍**] 底下，選取一個範圍，然後按一下 [**執行報表**]。

    ![[團隊系統管理中心] 的 [小組] 使用者活動報告的螢幕擷取畫面（含標注）](../media/teams-reports-user-activity-with-callouts.png "[團隊系統管理中心] 的 [小組] 使用者活動報告的螢幕擷取畫面（含標注）")

## <a name="interpret-the-report"></a>解讀報表

|圖說文字 |說明  |
|--------|-------------|
|**1**   |您可以針對過去7天、28或90天的趨勢，查看團隊使用者活動報告。 |
|**2**   |每個報告都有產生此報告的日期。 報告通常會反映來自啟用時間的24到48小時延遲時間。 |
|**3**   |<ul><li>圖表上的 X 軸是特定報表的已選取日期範圍。 </li><li>Y 軸是參與活動的使用者數目。</li></ul>將游標暫留在代表指定日期的活動點上，即可查看該活動在該指定日期的實例數。 |
|**4**   |您可以按一下圖例中的專案，篩選您在圖表上看到的內容。 例如，按一下 [ **1:1 通話**]、[**頻道訊息**] 或 [**聊天訊息**]，只查看與每一個相關的資訊。 變更選取範圍不會變更表格中的資訊。 |
|**500**   |此表格提供使用者的使用方式細分。   <ul><li>[**顯示名稱**] 是使用者的顯示名稱。 您可以按一下顯示名稱，移至 Microsoft 團隊系統管理中心的 [使用者設定] 頁面。</li><li>[ **1:1 通話**] 是使用者在指定期間內參與的1:1 通話數目。</li><li>[**頻道訊息**] 是使用者在特定的時段內，在小組聊天中張貼的唯一訊息數目。</li><li>[**回復訊息**] 是使用者在特定期間內于團隊頻道中張貼的唯一回復訊息數。</li> <li>[**張貼訊息**] 是在指定期間內，使用者在團隊頻道中張貼的唯一張貼訊息數目。</li><li>[**組織會議**數] 是使用者在指定的時段內組織的排程會議數量。</li><li>[**會議參與**] 是使用者在特定的時段內參與的排程會議數。</li><li>[**交談訊息**] 是使用者在特定的時段內，在私人聊天中張貼的唯一訊息數目。</li><li>**緊急郵件**是指使用者在指定的時段內，在聊天中張貼的緊急訊息數目。</li><li>[**群組通話**] 是使用者在特定的時段內參與的群組呼叫數目。</li><li>[**音訊時間**] 是使用者在指定的時段內參與的總音訊時間。</li><li>[**視頻時間**] 是使用者在特定的時段內參與的視頻總時間。</li><li>[**螢幕共用時間**] 是使用者在指定的時段內參與的螢幕共用時間總計。</li>  <li>[**上一個活動**] 是使用者參與團隊活動的最後一個日期（UTC）。</li> </ul>請注意，如果使用者帳戶已不存在於 Azure AD 中，則使用者名稱會在資料表中顯示為 "--"。 <br><br>若要在表格中查看您想要的資訊，請務必將資料行新增至資料表。
|**6**   |選取 [**編輯欄**] 以新增或移除表格中的欄。 |
|**utf-7**   |您可以將報表匯出為 CSV 檔案，以便進行離線分析。 按一下 [**匯出至 Excel**]，然後在 [**下載**] 索引標籤上，按一下 [**下載**] 以在準備好時下載報告。<br><br>![[下載] 索引標籤的螢幕擷取畫面，顯示已匯出的報告供下載](../media/teams-reports-export-to-csv.png) <br>當您在 Excel 中查看報表時，您也會看到 [**識別碼**] 欄，代表 [團隊識別碼]。 團隊識別碼通常是一個字母數位字串。 如果 [**識別碼**] 欄顯示為 [ **\n**]，表示使用者要求刪除其資訊。 ||

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>相關主題

- [團隊分析和報告](teams-reporting-reference.md)
