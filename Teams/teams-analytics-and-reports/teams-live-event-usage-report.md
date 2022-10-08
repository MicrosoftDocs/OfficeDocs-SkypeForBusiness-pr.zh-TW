---
title: Microsoft Teams 即時活動使用方式報告
author: CarolynRowe
ms.author: crowe
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
description: 瞭解如何使用 Microsoft Teams 系統管理中心的 Teams 即時活動使用方式報告，以取得貴組織中 Teams 即時活動活動的概觀。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1a7f571610c49da16735cf66f65f725901fce56d
ms.sourcegitcommit: b2692b3f6c60d8df5ba0677c68ff9c90a75a0d72
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2022
ms.locfileid: "68033811"
---
# <a name="microsoft-teams-live-event-usage-report"></a>Microsoft Teams 即時活動使用方式報告

Microsoft Teams 系統管理中心的 Teams 即時活動使用方式報告會顯示貴組織中所舉辦即時活動的活動概觀。 您可以檢視每個事件的使用狀況資訊，包括事件狀態、開始時間、檢視和生產類型。 您可以深入瞭解使用趨勢，並查看組織中的人員排程、展示和產生即時活動。

## <a name="view-the-live-event-usage-report"></a>檢視即時事件使用方式報告

1. 在 Microsoft Teams 系統管理中心的左側導覽中，按一下 **[分析&報告**  >  **使用方式報告。** 在 [ **檢視報表] 索** 引標籤的 [ **報告**] 底下，選 **取 [Teams 即時活動使用量]**。
2. 在 **[日期範圍]** 底下，選取預先定義的範圍或設定自訂範圍。 您可以設定範圍，在目前日期前後六個月內顯示最多一年的資料。
3.  (選擇性) 在 [召集人 **] 底下**，您可以選擇只顯示由特定使用者組織的即時活動。
4. 按一下 **[執行報表]**。  

   :::image type="content" alt-text="Teams 系統管理中心內含圖說文字的 Teams 即時活動使用方式報告螢幕擷取畫面。" source="../media/teams-live-event-usage-report-with-callouts.png" lightbox="../media/teams-live-event-usage-report-with-callouts.png":::

## <a name="interpret-the-report"></a>解讀報表

|標注 |描述  |
|--------|-------------|
|**1**   |您可以檢視 Teams 即時活動報告，以查看過去 7 天、28 天的趨勢，或您設定的自訂日期範圍。 |
|**2**   |每個報告都有產生報告的日期。 當頁面重新整理時，報告會反映接近即時的活動。 |
|**3**   |<ul><li>圖表上的 X 軸是報表的選取日期範圍。</li> <li> Y 軸是總檢視計數。</li> </ul>將游標停留在指定日期的點上，以查看該日期所有即時活動的檢視次數。|
|**4**   |表格會提供每個即時事件的明細。 <ul><li>**事件** 是即時活動的顯示名稱。 按一下活動名稱以 [取得活動的詳細](#view-event-details) 資料。 </li> <li>**[開始時間** ] 是指活動的開始日期和時間。</li> <li>**事件狀態** 會顯示事件是否已發生。  </li><li>**召集** 人是活動召集人的名稱。</li> <li>**簡報者** 是活動簡報者的名稱。</li><li>**製作人** 是活動製作人的名稱。</li><li>**[檢視** ] 是事件完成後的唯一檢視數目。</li><li>**錄製** 會顯示錄製設定是開啟還是關閉。</li><li>**生產類型** 會顯示事件是否由 Teams 或外部應用程式或裝置產生。</li></li> </ul>請注意，如果 Azure AD 中不再存在使用者帳戶，則使用者名稱會在資料表中顯示為 「--」。 <br><br>若要在資料表中查看您要的資訊，請務必將欄新增至資料表。 |
|**5**   |選取 **[編輯欄]** 以新增或移除表格中的欄。|

## <a name="notes"></a>注釋
我們最多會顯示 100 個符合目前報告準則的即時活動。 若要查看更多即時活動，請套用日期篩選以縮減清單大小。

匿名簡報者不會包含在報告中。

任何依需求觀看活動或活動的錄製內容，都不會包含在檢視計數中。 

## <a name="view-event-details"></a>檢視活動詳細資料

即時活動詳細資料頁面會提供即時活動的詳細資料摘要，並列出與活動相關聯的所有檔案，包括文字記錄和錄製。 按一下檔案名以檢視或下載檔案。

:::image type="content" alt-text="顯示即時活動的詳細資料的螢幕擷取畫面。" source="../media/teams-live-event-usage-report-event-detail.png" lightbox="../media/teams-live-event-usage-report-event-detail.png":::

如果貴組織已啟用 [Hive](https://www.hivestreaming.com/partners/integration-partners/microsoft/) eCDN 或 [Kollective](https://kollective.com) eCDN，您可以按一下合作夥伴報告連結，以取得其他出席者分析資料。

## <a name="related-topics"></a>相關主題

- [Teams 分析與報告](teams-reporting-reference.md)
- [什麼是 Teams 即時活動？](../teams-live-events/what-are-teams-live-events.md)
