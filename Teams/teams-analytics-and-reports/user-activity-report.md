---
title: Microsoft Teams 使用者活動報告
author: cichur
ms.author: v-cichur
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
description: 瞭解如何在 Microsoft Teams 系統管理中心使用 Teams 使用者活動報告，以查看貴組織的使用者如何使用 Teams。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f02d2f8751b8059f435164158d5c97fb6766a286
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196909"
---
# <a name="microsoft-teams-user-activity-report"></a>Microsoft Teams 使用者活動報告

Teams 使用者活動報告提供貴組織使用者在 Teams 中執行之活動類型的深入資訊。 您可以透過 1：1 和群組通話未排 (，查看有多少使用者透過未排) 。 查看 Teams 使用者已組織多少場會議，以及 Teams 使用者參與的會議。 查看有關螢幕、視訊和音訊通話分鐘數的詳細資訊，以及聊天通訊統計資料，例如有多少使用者回復和張貼頻道訊息，以及有多少使用者參與 1：1 或群組聊天訊息。

## <a name="view-the-user-activity-report"></a>查看使用者活動報告

您必須是 Teams 服務系統管理員才能進行這些變更。 請參閱 [使用 Teams 系統管理員角色來管理 Teams，](https://docs.microsoft.com/microsoftteams/using-admin-roles) 以閱讀取得系統管理員角色和許可權。

1. 在 Microsoft Teams 系統管理中心的左側流覽中，選取分析 **&報告**  >  **使用方式報告**。 在視圖 **報表的選項卡** 上，選取 **報表** 下的 **Teams 使用者活動**。
2. 在 **日期範圍** 下，選取範圍，然後選取執行 **報表**。

    ![Teams 系統管理中心中 Teams 使用者活動報告與圖說圖的螢幕擷取畫面](../media/teams-reports-user-activity-with-callouts.png "Teams 系統管理中心中 Teams 使用者活動報告與圖說圖的螢幕擷取畫面")

## <a name="interpret-the-report"></a>解讀報表

|標注 |說明  |
|--------|-------------|
|**1**   |您可以針對過去 7 天、30 天或 90 天的趨勢來查看 Teams 使用者活動報告。 |
|**2**   |每個報表都有產生此報表的日期。 報告通常會反映出啟用時間有 24 小時的延遲。 |
|**3**   |圖表中的時間序列資料點會顯示在租使用者匯總的不同使用計量。 |
|**4**   |表格式資料代表每個使用者匯總的不同使用計量。 |
|**5**   |<ul><li>圖表上的 X 軸是報表的選取日期範圍。</li> <li> Y 軸是活動專案或活動的計數。</li> </ul>將游標停留在代表某個日期之專案或活動的點上，以查看該專案或該日期的活動實例數目。|
|**6**   | 以租使用者層級以圖形表示的每個度量。 選取圖例中的專案，以篩選圖表上顯示的專案。 選取 **頻道訊息**、 **回復訊息**、  **聊天訊息** 或 **已組織會議** ，以查看每個訊息的相關資訊。 變更此選取範圍不會變更表格中的資訊。 |
|**7**   |表格提供使用者使用方式的明細。   <ul><li>**顯示名稱** 是使用者的顯示名稱。 選取顯示名稱，以前往 Microsoft Teams 系統管理中心的使用者詳細資料頁面。</li><li>**頻道訊息** 是使用者在指定的時段內，在團隊頻道中張貼的唯一訊息數目。</li><li>**回復訊息** 是使用者在指定的時段內，在小組頻道中張貼的唯一回復訊息數目。</li> <li>**張貼訊息** 是使用者在指定的時段內，在小組頻道中張貼的唯一貼文訊息數目。</li><li>**聊天訊息** 是使用者在指定的時段內于私人聊天中張貼的唯一訊息數目。</li><li>**緊急訊息** 是使用者在指定的時段內于聊天中張貼的緊急訊息數目。</li><li>**組織的會議** 總數是使用者于指定時段內組織的一次性排程、週期性、非計畫 <em></em>及未分類會議的總和。</li><li>**排定一次的會議** 是使用者在指定的時段內組織的一次排程會議數目。</li><li>**排定的週期性** 會議是使用者在指定的時段內組織的週期性會議數目。</li><li>**組織的會議是** 使用者在指定的時段內組織非計畫會議的數量。</li><li>**參與的會議** 總數是使用者在指定的時段內參與的一次性排程、週期性、非計畫及未分類 <em></em>會議的總和。</li><li>**已排程一次** 的會議是使用者在指定的時段內參與的一次排程會議數目。</li><li>**參與的會議排定週期性** 是使用者在指定的時段內參與的週期性會議數目。</li><li>**參與的會議 adhoc** 是使用者在指定的時段內參與的未計畫會議數目。</li><li>**1：1** 通話是使用者在指定的時段內參與的 1 對 1 通話數。</li><li>**音訊時間** 是使用者在 (參與) 分鐘的總音訊時間。</li><li>**影片時間** 是使用者在 () 參與的視視時間總分鐘數。</li><li>**螢幕畫面分享** 時間是使用者 (參與) 分鐘的總螢幕分享時間。</li>  <li>**上次活動** 是使用者 (Utc) 的最後一個日期。</li><li>**其他活動** 會追蹤使用者被視為使用中時間，但聊天訊息、1 對 1 通話、頻道訊息、總會議和已組織會議的值為零。 例如，當使用者開啟頻道訊息貼文但無法回復時，或當使用者收到私人訊息並讀取該私人訊息，但無法回應該訊息時，即會執行這些動作。</li> <li>**未分類的會議** 是無法分類為排程、週期性或非計畫的會議。 這些號碼簡短，而且大多無法識別，因為遙測資訊遭到竄改</li> </ul>**群組通話** 已由會議 **組織 adhoc 和** Meetings 參與 **adhoc 取代**。 這兩個值的總和等於 Group 呼叫 **所測量的值**。
|**8**   |選取 **編輯欄** 以新增或移除表格中的欄。 |
|**9**   |將報表匯出為 CSV 檔案，進行離線分析。 選取 **匯出至 Excel，** 然後選取 **下載** Tab，選取下載以在報表準備就緒時下載報表。<br><br>![顯示要下載之匯出報表的下載視窗螢幕擷取畫面](../media/teams-reports-export-to-csv.png) <br>當您在 Excel 中查看報表時，也會看到代表使用者識別碼的 **識別碼** 欄。 使用者識別碼通常是 Alphanumer 字串。 ||

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>相關主題

- [Teams 分析和報告](teams-reporting-reference.md)
