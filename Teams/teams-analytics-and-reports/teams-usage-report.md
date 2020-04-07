---
title: Microsoft 團隊使用量報告
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
description: 瞭解如何使用 Microsoft 團隊系統管理中心中的 [團隊使用量] 報告，以取得貴組織中的小組活動的概覽。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 260b9e23219b6812427fb84fbed5ceb820c2201c
ms.sourcegitcommit: f3390e27bb63b66d1c4fb4f8afbda6b814fbbb5b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/07/2020
ms.locfileid: "43170561"
---
# <a name="microsoft-teams-usage-report"></a>Microsoft 團隊使用量報告

Microsoft 團隊系統管理中心中的 [團隊使用方式] 報告可讓您大致瞭解團隊中的使用狀況活動，包括作用中使用者和頻道的數目，讓您可以快速查看貴組織中的使用者數是使用團隊進行通訊和共同作業。 您可以查看小組的使用方式資訊，包括每個小組中的作用中使用者數與頻道、來賓和訊息。

## <a name="view-the-report"></a>查看報表

1. 在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**分析] & 報告** > **使用方式報告**。 在 [**查看報表**] 索引標籤的 [**報表**] 底下，選取 [**團隊使用方式**]。
2. 在 [**日期範圍**] 底下，選取一個範圍，然後按一下 [**執行報表**]。

    ![含標注之 [團隊系統管理中心] 的 [小組使用方式] 報告螢幕擷取畫面](../media/teams-reports-teams-usage-with-callouts.png "含標注之 [團隊系統管理中心] 的 [小組使用方式] 報告螢幕擷取畫面")

## <a name="interpret-the-report"></a>解讀報表

|圖說文字 |說明  |
|--------|-------------|
|**1**   |您可以針對過去7天或28天的趨勢，查看 [團隊使用狀況] 活動報告。 |
|**2**   |每個報告都有產生此報告的日期。 報告通常會反映來自啟用時間的24到48小時延遲時間。 |
|**3**   |<ul><li>圖表上的 X 軸是報表所選取的日期範圍。</li> <li> Y 軸是作用中專案或活動的計數。</li> </ul>將游標暫留在代表指定日期的專案或活動點上，即可查看該專案或該日期的活動實例數。|
|**4**   |您可以按一下圖例中的專案，篩選您在圖表上看到的內容。 例如，按一下 [**總**作用中的使用者]、[**團隊] & [頻道**作用中的使用者]、[作用中**通道**] 或 [**郵件**]，只會看到與每個資訊相關 變更此選取範圍不會變更表格中的資訊。 |
|**500**   |此表格提供依團隊進行的使用方式細分。 <ul><li>[**團隊名稱**] 是團隊的顯示名稱。 您可以按一下團隊名稱，移至 Microsoft 團隊系統管理中心的小組 [設定] 頁面。 </li> <li>**隱私權**指的是私人小組或公用小組。</li> <li>[作用中的**使用者**] 是團隊中在指定時段內作用中的使用者數目。</li><li>[**來賓**] 是團隊中指定時間內的來賓人數。</li> <li>[作用中**通道**] 是在指定的時間內至少有一個作用中使用者的頻道數目。</li> <li>[**張貼訊息**] 是在指定時段內，在頻道中所有投遞訊息的數目。</li> <li>[**回復訊息**] 是指在指定的時間內，頻道中所有回復訊息的數目。</li> <li>[**組織會議**數] 是使用者組織的所有排程會議數。 每個週期性會議實例會計算為一個會議。</li><li>**緊急郵件**是指在指定時間內所有緊急郵件的數目。</li> </li> </ul>請注意，如果使用者帳戶已不存在於 Azure AD 中，則使用者名稱會在資料表中顯示為 "--"。 <br><br>若要在表格中查看您想要的資訊，請務必將資料行新增至資料表。 |
|**6**   |選取 [**編輯欄**] 以新增或移除表格中的欄。|
|**utf-7**   |您可以將報表匯出為 CSV 檔案，以便進行離線分析。 按一下 [**匯出至 Excel**]，然後在 [**下載**] 索引標籤上，按一下 [**下載**] 以在準備好時下載報告。<br><br>![[下載] 索引標籤的螢幕擷取畫面，顯示已匯出的報告供下載](../media/teams-reports-export-to-csv.png)|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>相關主題

- [團隊分析和報告](teams-reporting-reference.md)
