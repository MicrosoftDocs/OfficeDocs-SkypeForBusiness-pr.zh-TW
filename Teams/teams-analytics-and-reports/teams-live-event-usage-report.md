---
title: Microsoft Teams活動使用方式報告
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
  - M365-collaboration
description: 瞭解如何使用 Teams 系統管理中心Microsoft Teams即時活動使用方式報告，以取得Teams即時活動活動的概觀。
appliesto:
  - Microsoft Teams
ms.custom: seo-marvel-apr2020
---
# <a name="microsoft-teams-live-event-usage-report"></a>Microsoft Teams活動使用方式報告

系統Teams系統管理中心Microsoft Teams即時活動使用方式報告，顯示貴組織中即時活動的活動概觀。 您可以針對每個事件查看使用方式資訊，包括事件狀態、開始時間、視圖及生產類型。 您可以深入瞭解使用趨勢，並查看貴組織中誰排程、進行展示，以及製作即時活動。

## <a name="view-the-live-event-usage-report"></a>查看即時活動使用方式報告

1. 在系統管理中心的左側導Microsoft Teams，按一下 [分析&**報表**  >  **。** On the **View reports** tab, under **Report**, select **Teams live event usage**.
2. 在 **日期範圍** 下，選取預先定義的範圍或設定自訂範圍。 您可以將範圍設定為最多顯示一年、六個月之前和目前日期之後的資料。
3.  (選) 在召集人下，您可以選擇只顯示由特定使用者組織的即時活動。
4. 按一下 **[執行報表**。  

   :::image type="content" alt-text="系統管理中心Teams活動使用方式報表的螢幕擷取畫面Teams圖說文字。" source="../media/teams-live-event-usage-report-with-callouts.png" lightbox="../media/teams-live-event-usage-report-with-callouts.png":::

## <a name="interpret-the-report"></a>解譯報表

|標注 |描述  |
|--------|-------------|
|**1**   |您可以Teams即時活動報告，查看過去 7 天、28 天的趨勢，或您設定自訂的日期範圍。 |
|**2**   |每個報表都有產生日期。 當頁面重新更新時，報表會反映接近即時的活動。 |
|**3**   |<ul><li>圖表上的 X 軸是報表的選取日期範圍。</li> <li> Y 軸是總的視圖計數。</li> </ul>將游標停留在給定日期的點上方，以查看該日期所有即時事件的觀看次數。|
|**4**   |表格會提供每個即時活動的明細。 <ul><li>**事件** 是即時事件的顯示名稱。 按一下事件名稱 [以取得活動](#view-event-details) 的詳細資訊。 </li> <li>**開始時間** 是指事件的開始日期和時間。</li> <li>**事件狀態** 會顯示事件是否已發生。  </li><li>**召集人** 是活動召集人的名稱。</li> <li>**演示** 者是活動簡報者的名稱。</li><li>**製作** 人是活動製作人的名稱。</li><li>**視圖** 是活動完成之後的唯一視圖數目。</li><li>**錄製** 會顯示錄製設定是已啟用或關閉。</li><li>**生產類型** 會顯示事件是以 Teams或外部應用程式或裝置產生。</li></li> </ul>請注意，如果使用者帳戶不再存在於 Azure AD，使用者名稱會顯示為 「--」于表格中。 <br><br>若要在表格中查看您想要的資訊，請務必新增欄至資料表。 |
|**5**   |選取 **編輯欄** 以新增或移除表格中的欄。|

## <a name="notes"></a>注釋
我們最多會顯示 100 個符合目前報告準則的即時活動。 若要查看更多即時活動，請應用日期篩選來縮減清單大小。

匿名簡報者不會包含在報告中。

任何觀看活動或活動視需要錄製的人，將不會包含在查看計數中。 

## <a name="view-event-details"></a>查看活動詳細資料

即時活動詳細資料頁面提供即時活動詳細資料摘要，並列出與活動相關的所有檔案，包括文字記錄與錄製。 按一下檔案名以查看或下載檔案。

:::image type="content" alt-text="顯示即時活動詳細資料之螢幕擷取畫面。" source="../media/teams-live-event-usage-report-event-detail.png" lightbox="../media/teams-live-event-usage-report-event-detail.png":::

如果貴組織已啟用 [Hive](https://www.hivestreaming.com/partners/integration-partners/microsoft/) eCDN 或 [Kollective](https://kollective.com) eCDN，您可以按一下合作夥伴報告連結，取得其他出席者分析。

## <a name="related-topics"></a>相關主題

- [Teams 分析與報告](teams-reporting-reference.md)
- [什麼是 Teams 即時活動？](../teams-live-events/what-are-teams-live-events.md)
