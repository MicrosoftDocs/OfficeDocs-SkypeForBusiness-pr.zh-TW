---
title: Microsoft 團隊即時事件使用量報告
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 瞭解如何使用 Microsoft 團隊系統管理中心中的 [團隊即時事件使用量] 報告，以取得貴組織中的小組即時事件活動的概覽。
appliesto:
- Microsoft Teams
ms.openlocfilehash: ad0ecd27df1f7bccd9a451f2581d55e5c335b1e0
ms.sourcegitcommit: f1c4255b52576c602d528c580941404eb547bc78
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/24/2019
ms.locfileid: "37131611"
---
# <a name="microsoft-teams-live-event-usage-report"></a>Microsoft 團隊即時事件使用量報告

Microsoft 團隊系統管理中心的 [小組即時事件使用量] 報告會顯示您組織中的即時事件的活動概覽。 您可以查看使用方式資訊，包括事件狀態、開始時間、視圖，以及每個事件的生產類型。 您可以深入瞭解使用狀況趨勢，並查看貴組織的排程、提出及產生即時事件。

## <a name="view-the-report"></a>查看報表

1. 在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**分析] & 報告** > **使用方式報告**。 在 [**查看報表**] 索引標籤的 [**報表**] 底下，選取 [**團隊即時事件使用量**]。
2. 在 [**日期範圍**] 底下，選取預先定義的範圍或設定自訂範圍。 您可以將範圍設定為在目前日期之前或之後的六個月內顯示資料。
3. 可選在 [**召集人**] 底下，您可以選擇只顯示由特定使用者組織的即時事件。
4. 按一下 [**執行報表**]。  

    ![[小組管理中心] 中的 [小組即時事件使用量] 報告螢幕擷取畫面（含標注]）(../media/teams-live-event-usage-report-with-callouts.png "[小組管理中心] 中的 [小組即時事件使用量] 報告螢幕擷取畫面（含標注")）

## <a name="interpret-the-report"></a>解讀報表

|圖說文字 |說明  |
|--------|-------------|
|**sr-1**   |您可以在過去7天、28天或您所設定的自訂日期範圍中，查看 [團隊即時事件] 報表的趨勢。 |
|**pplx-2**   |每個報告都有產生的日期。 當頁面重新整理時，報告會反映接近的即時活動。 |
|**3**   |<ul><li>圖表上的 X 軸是報表所選取的日期範圍。</li> <li> Y 軸是總計的視圖數。</li> </ul>將游標停留在指定日期上的點上，即可查看該日期上所有即時事件的視圖數。|
|**4**   |下表提供每個即時事件的細目分類。 <ul><li>**事件**是即時事件的顯示名稱。 按一下事件名稱，取得事件的[詳細資料](#view-event-details)。 </li> <li>[**開始時間**] 指的是事件的開始日期和時間。</li> <li>**事件狀態**顯示事件是否已發生。  </li><li>[**召集人**] 是事件召集人的名稱。</li> <li>**演示**者是事件簡報者的名稱。</li><li>**發生器**是事件發生器的名稱。</li><li>[**視圖**] 是唯一的視圖數。</li><li>[**錄製**] 會顯示 [錄製] 設定為 [開啟] 或 [關閉]。</li><li>[**生產類型**] 會顯示事件是在團隊中產生，還是由外部應用程式或裝置產生。</li></li> </ul>請注意，如果使用者帳戶已不存在於 Azure AD 中，則使用者名稱會在資料表中顯示為 "--"。 <br><br>若要在表格中查看您想要的資訊，請務必將資料行新增至資料表。 |
|**500**   |選取 [**編輯欄**] 以新增或移除表格中的欄。|

## <a name="view-event-details"></a>查看事件詳細資料

[即時事件詳細資料] 頁面提供即時事件的詳細資料摘要，並列出與事件相關聯的所有檔案，包括記錄及錄製。 按一下檔案名以查看或下載檔案。

![顯示即時事件詳細資料的螢幕擷取畫面](../media/teams-live-event-usage-report-event-detail.png)

如果您的組織已啟用[Hive](https://www.hivestreaming.com/partners/integration-partners/microsoft/) ECDN 或[Kollective](https://kollective.com) eCDN，您可以按一下 [合作夥伴報告] 連結來取得其他出席者分析。

## <a name="related-topics"></a>相關主題

- [團隊分析和報告](teams-reporting-reference.md)
- [什麼是團隊即時活動？](../teams-live-events/what-are-teams-live-events.md)