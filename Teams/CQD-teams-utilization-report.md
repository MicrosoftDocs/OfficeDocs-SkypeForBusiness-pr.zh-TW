---
title: 使用 CQD 資料檢視 Power BI 中的 Microsoft Teams 使用率
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
description: 使用 Teams 使用 Power BI 報告存取 Microsoft Teams 通話品質儀表板 (CQD) 資料來追蹤貴組織中的 Microsoft Teams 使用量。
ms.openlocfilehash: bd579fa3f57c6e3b50a363eb77523f577c750efb
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270688"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a>使用 CQD 資料檢視 Power BI 中的 Microsoft Teams 使用率

Teams 使用方式報告是作為適用于 [CQD 的可下載 Power BI 查詢範本](https://www.microsoft.com/download/details.aspx?id=102291)的一部分提供。 

此報告可讓您存取 Teams 通話品質儀表板 (CQD) 資料，以查看使用者使用 Microsoft Teams 的 (程度，以及使用者使用 Microsoft Teams 的) 程度。 這些報告是一個集中式位置，系統管理員和商務主管都可以快速移至此資料。 請注意，由於 [通話品質遙測的性質，我們建議不要將此資料依賴于具體數位](CQD-frequently-asked-questions.md#im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that)。

Teams 使用量 Power BI 報表包含兩個主要報告： **[通話計數摘要](#call-count-summary-report)** 和 **[音訊通話分鐘數摘要](#audio-minutes-summary-report)**。 當使用者利用下列描述所述的向下切入報告時， [[每日使用量](#daily-usage)]、 [[地區音訊詳細](#regional-audio-details)資料]、[ [會議詳細](#conference-details) 資料] 和 [ [使用者清單](#user-list) ] 報告就會生效。

> [!NOTE]
> 必須填入建築物和子網路資料，以提供地區和網路篩選功能。

## <a name="call-count-summary-report"></a>通話計數摘要報表

 (通話計數摘要) 主頁面會立即提供過去 30 天和 90 天內的音訊、視訊和螢幕共用會話數目，如章節標題中所述。 最初顯示的資料適用于整個組織，而且可以使用頁面左側的交叉分析篩選器下拉式選項進行篩選。

![螢幕擷取畫面：Teams 使用方式報告。](media/CQD-teams-utilization-report1.png)

1. 交叉分析篩選器下拉式清單右側的媒體類型通話數，在過去三十天內會細分為內部/外部檢視。 我們可以透過上述螢幕擷取畫面，看到組織外部有更多呼叫正在進行，這在考慮目前的全球環境時非常有意義。
  ![螢幕擷取畫面：Teams 使用方式報告。](media/CQD-teams-utilization-report2.png)

1. 在媒體類型計數方塊的右側，我們有過去 90 天按媒體類型計算的每月通話數。 您可以將每個欄和媒體類型暫留以顯示上個月或目前月份的計數，並提供使用趨勢資訊。
  ![螢幕擷取畫面：Teams 使用方式報告。](media/CQD-teams-utilization-report3.png)
 

1. 中間圖形的運作方式與 90 天圖表相同，不過它提供了過去 30 天的每日使用狀況檢視，並可讓使用者以滑鼠右鍵按一下並向下切入特定日期的詳細資料。
  ![螢幕擷取畫面：Teams 使用方式報告。](media/CQD-teams-utilization-report4.png)

在頁面的左下方區段，您會發現一個表格，提供過去一年中各媒體類型的總計值。 
    ![螢幕擷取畫面：Teams 使用方式報告。](media/CQD-teams-utilization-report5.png)
    ![螢幕擷取畫面：Teams 使用方式報告。](media/CQD-teams-utilization-report6.png)   

在表格右側，橫條圖會顯示用戶端在過去 30 天內) 使用最多 ( (通話/串流。
   ![螢幕擷取畫面：Teams 使用方式報告。](media/CQD-teams-utilization-report7.png)

本頁的最後一組圖表會個別顯示每種媒體類型，並顯示會議和 P2P 使用狀況的明細。 下圖顯示與 P2P 相比，會議使用量大幅增加。
  ![螢幕擷取畫面：Teams 使用方式報告。](media/CQD-teams-utilization-report8.png)

## <a name="audio-minutes-summary-report"></a>音訊分鐘數摘要報表

在 [音訊分鐘數使用量] 報告中，總分鐘數使用量是透過幾個不同的檢視提供。 

我們已在交叉分析篩選器旁顯示三十天的使用摘要，以方便使用文字方塊。 頂端數字顯示 30 天總計，下方為內部和外部明細。

![螢幕擷取畫面：Teams 使用方式報告。](media/CQD-teams-utilization-report9.png)

右上角的橫條圖提供長達一年的會議音訊使用狀況檢視。 將游標停留在月份上以顯示會議音訊分鐘數。

若要顯示 P2P 與會議音訊的差異，左下角的圖表會擁取過去一年的所有音訊，並在這兩種類型之間中斷分隔。

![螢幕擷取畫面：Teams 使用方式報告。](media/CQD-teams-utilization-report10.png)

[音訊分鐘數] 頁面的最後一個圖表顯示全域地圖重迭的音訊分鐘數使用量。 只有在建築物和子網資料上傳到租使用者時，此圖表才能運作。 地圖上的圓形圖重迭可以切入，後續提供地區音訊使用量。

![螢幕擷取畫面：Teams 使用方式報告。](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a>切入功能

如先前所述，使用者可以深入瞭解每日及地區使用方式報告。

### <a name="daily-usage"></a>每日使用量

[每日使用量] 報告可讓系統管理員識別一整天的尖峰消費期間。 除了使用方式之外，我們也可以擷取當天的整體使用者情緒和意見反應。

![螢幕擷取畫面：Teams 使用方式報告。](media/CQD-teams-utilization-report12.png)

[每日使用方式] 報告會顯示所選日期的音訊、視訊和螢幕共用數目，並新增辨別內部和外部連線能力的能力。 [會議] 和 [對等對等] 明細位於 [形式總計] 方塊的直接右側。 報告右上角提供含有其相關識別碼的會議清單，以及當天的參與者。 會議清單也會提供會議詳細資料包告的其他向下切入。 REPLACE 圖形

![螢幕擷取畫面：Teams 使用方式報告。](media/CQD-teams-utilization-report13.png)

中心區域中的橫條圖可讓使用者識別一整天的尖峰消費期間。 使用者可以向下切入圖表上顯示的小時，以顯示該小時的 [使用者清單] 報告。

在橫條圖右側，會以視覺格式呈現 [使用者意見反應]。 雖然使用者情緒可以是主旨，但卻能提供可用來找出潛在問題的深入解析。

下表提供當天的計量範圍。 不佳的百分比以及失敗率可以為系統管理員提供潛在的改善領域。 您也可以個別選取每小時，如下所示。

此資料可用來識別在尖峰使用時間發生問題的地區。


按一下當天的欄，即可顯示該小時的計量。
![螢幕擷取畫面：Teams 使用方式報告。](media/CQD-teams-utilization-report14.png)
  
  1.  圖表下方的表格會顯示該小時的計量。 這可以由任何欄標題排序;不過，我們很樂意尋找有問題的領域。  
    ![螢幕擷取畫面：Teams 使用方式報告。](media/CQD-teams-utilization-report15.png)
    
  2.  我們發現 IND 區域在這段期間的會議中發生視訊效能不佳的問題。 之後，CQD QER Microsoft 報告可用來縮小有問題的位置範圍，因為已識別出地區和時間範圍。

### <a name="conference-details"></a>會議詳細資料

會議詳細資料包告提供會議的其他深入解析，從出席者清單到會話期間使用的媒體類型。

以滑鼠右鍵按一下會議[每日使用量] 頁面上會議 ID 圖表中的參與者列，向下切入會議詳細資料。

![螢幕擷取畫面：Teams 使用方式報告。](media/CQD-teams-utilization-report24.png)

![螢幕擷取畫面：Teams 使用方式報告。](media/CQD-teams-utilization-report25.png)
  

我們可以看到會議中的參與者，以及所有相關資訊，以致于封包遺失和抖動，以協助在底部表格中進行可能的疑難排解工作。

![螢幕擷取畫面：Teams 使用方式報告。](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a>地區音訊詳細資料

向下切入的區域音訊詳細資料會特別顯示所選區域的音訊分鐘數使用量。 具有 CQD 存取權的使用者可以在所選區域內看到 P2P 和會議音訊的使用趨勢。

1.  在 [通話計數摘要] 頁面上，透過表格切入至特定區域。
  ![螢幕擷取畫面：Teams 使用方式報告。](media/CQD-teams-utilization-report16.png)

2.  選取含有需要額外資訊之區域的資料列。
  ![螢幕擷取畫面：Teams 使用方式報告。](media/CQD-teams-utilization-report17.png)

3.  資料趨勢顯示在內部網路上使用大量分鐘數，而會議的使用量遠超過 P2P 使用量。
  ![螢幕擷取畫面：Teams 使用方式報告。](media/CQD-teams-utilization-report18.png)

地區音訊趨勢可用來顯示使用者如何受到全球外部影響的影響。 具體來說，目前我們預期會看到 EMEA 和 APAC 地區的外部使用量增加，因此系統會要求人員進行遠端工作。


### <a name="user-list"></a>使用者清單

向下切入的 [使用者清單] 會如預期般提供使用者特定時間的特定資訊，供檢視報告的人員選取。 使用者清單報表可透過每日使用量報表的 [每小時趨勢] 圖表向下切入來存取。 以滑鼠右鍵按一下所需的小時額外資訊，然後選取 [切入] 和 [使用者清單]，如下所示。

![螢幕擷取畫面：Teams 使用方式報告。](media/CQD-teams-utilization-report19.png)

[使用者清單] 報告會透過頁面頂端中央的環圈圖顯示內部/外部連線能力。 我們可以在下圖中看到公司網路外部有大量參與。

圖表右上角顯示每位使用者在該小時內撥打的通話數目。

![螢幕擷取畫面：Teams 使用方式報告。](media/CQD-teams-utilization-report20.png)

下錶針對每位使用者在該小時內參與的會話提供詳細資訊。 [失敗類型] 欄在判斷導致呼叫中斷的原因時很有用。 擷取和轉譯裝置欄很適合用於識別為何有人回報通話品質不佳。


## <a name="related-topics"></a>相關主題

[通話品質儀表板中提供的維度和量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通話品質儀表板中的資料流分類](stream-classification-in-call-quality-dashboard.md)

[設定商務用 Skype 通話分析](set-up-call-analytics.md)

[使用通話分析來疑難排解不良通話品質](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通話分析和通話品質儀表板](./monitor-call-quality-qos.md)

[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)
