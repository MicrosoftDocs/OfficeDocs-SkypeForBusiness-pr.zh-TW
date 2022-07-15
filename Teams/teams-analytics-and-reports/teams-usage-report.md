---
title: Microsoft Teams 使用方式報告
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kojika
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解如何使用 Microsoft Teams 系統管理中心的 Teams 使用方式報告，以取得貴組織中 Teams 活動的概觀。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3770d3e45e75808d8dc92e139c1886f6623df922
ms.sourcegitcommit: 4c4f2f220832cae3efb3f6f3c74795300d661295
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2022
ms.locfileid: "66825537"
---
# <a name="microsoft-teams-usage-report"></a>Microsoft Teams 使用方式報告

Microsoft Teams 系統管理中心的 Teams 使用方式報告可讓您概略瞭解 Teams 中的使用方式活動，包括使用中的使用者數目和頻道，讓您可以快速查看組織中有多少使用者正在使用 Teams 進行通訊和共同作業。 您可以檢視團隊的使用資訊，包括每個團隊中的使用中使用者和頻道、來賓和訊息數目。

## <a name="view-the-usage-report"></a>檢視使用方式報告

1. 在 Microsoft Teams 系統管理中心的左側導覽中，按一下 **[分析&報告**  >  **使用方式報告。** 在 [ **檢視報表]** 索引標籤的 [ **報表**] 底下，選 **取 [Teams 使用量]**。
2. 在 **[日期範圍]** 底下，選取範圍，然後按一下 [ **執行報表]**。

    ![Teams 系統管理中心內含圖說文字的 Teams 使用方式報告螢幕擷取畫面。](../media/teams-reports-teams-usage-with-callouts1.png "Teams 系統管理中心內含圖說文字的 Teams 使用方式報告螢幕擷取畫面")

## <a name="interpret-the-report"></a>解讀報表

|標注 |描述  |
|--------|-------------|
|**1**   |您可以檢視 Teams 使用方式活動報告，以查看過去 7 天、30 或 90 天的趨勢。 |
|**2**   |每份報告都有產生此報告的日期。 報告通常會反映啟用時間的 24 到 48 小時延遲。 |
|**3**   |<ul><li>圖表上的 X 軸是報表的選取日期範圍。</li> <li> Y 軸是活動專案或活動的計數。</li> </ul>將游標停留在指定日期上代表專案或活動的點上，以查看該專案或活動在指定日期上的實例數目。|
|**4**   |您可以按一下圖例中的專案，篩選圖表上顯示的內容。 例如，按一下 [  **作用中使用者總數]**、 **[Teams &通道** 作用中使用者]、[  **作用中頻道**] 或 [ **訊息** ]，只查看每個頻道的相關資訊。 變更此選取範圍並不會變更表格中的資訊。 |
|**5**   |表格提供您依小組使用的明細。 <ul><li>**團隊名稱** 是團隊的顯示名稱。 您可以按一下團隊名稱，移至 Microsoft Teams 系統管理中心的團隊設定頁面。 </li> <li>**隱私** 權是指團隊是私人團隊還是公開團隊。</li> <li>**作用中使用者** 是指小組在指定的時段內作用中使用者數目。</li><li>**來賓** 是團隊在指定期間內的來賓數目。</li> <li>**作用中頻道** 是指在指定的時段內至少有一個作用中使用者的頻道數目。</li> <li>**「張貼訊息** 」是頻道中指定時段內所有張貼訊息的數目。</li> <li>**回復訊息** 是頻道中指定期間內所有回復訊息的數目。</li> <li>**召集的會議** 是指使用者在指定的時段內召集的已排程和臨時會議數目。 </li><li>**緊急訊息** 是指指定期間內所有緊急郵件的數目。</li><li>**圖釋** 是指定期間內所有訊息的回應數目。</li><li>**提及** 是指在指定的時段內，郵件中使用的所有提及數目。</li><li>**頻道訊息** 是指團隊使用者在指定的時段內，在團隊聊天中張貼的唯一訊息數目。</li> </li> </ul>請注意，如果團隊不存在，該名稱會在資料表中顯示為 「--」。 <br><br>若要在資料表中查看您要的資訊，請務必將欄新增至資料表。 |
|**6**   |選取 **[編輯欄]** 以新增或移除表格中的欄。|
|**7**   |您可以將報表匯出為 CSV 檔案以進行離線分析。 按一下 **[匯出至 Excel**]，然後在 [ **下載] 索引卷** 標上，按一下 [ **下載** ] 以在報表準備就緒時下載報表。<br><br>![顯示要下載之匯出報表的 [下載] 索引標籤螢幕擷取畫面。](../media/teams-reports-export-to-csv.png)|
|**8** |圖表中的時間序列資料點顯示在租使用者匯總的不同使用量計量|
|**9** |表格式資料表示每個小組匯總的不同使用量計量|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>相關主題

- [Teams 分析與報告](teams-reporting-reference.md)
