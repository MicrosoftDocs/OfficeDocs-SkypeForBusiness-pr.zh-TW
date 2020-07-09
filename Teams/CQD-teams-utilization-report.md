---
title: 在 Power BI 中使用 CQD 資料來查看 Microsoft 團隊利用率
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: 使用 [團隊資料使用量 Power BI 報表] 存取 Microsoft 團隊通話品質儀表板（CQD）資料，以追蹤貴組織中的 Microsoft 團隊使用量。
ms.openlocfilehash: bd1a95a683da881a78acb5d4849bba0ac55f4898
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085579"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a>在 Power BI 中使用 CQD 資料來查看 Microsoft 團隊利用率

我們新增了2020年3月的新功能，我們已將 [團隊利用率] 報告新增至可下載[的 POWER BI 查詢範本以供 CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)使用。 

這個新的「團隊利用率」報告可讓您透過存取團隊通話品質儀表板（CQD）資料，來查看您的使用者使用 Microsoft 團隊的方式（以及多少）。 這些報告是要成為集中位置，管理員與企業領導人都可以快速移至此資料。

[團隊利用率 Power BI] 報表包含兩個主要的報表： [**[通話計數摘要](#call-count-summary-report)**] 和 [**[音訊分鐘摘要](#audio-minutes-summary-report)**]。 [每日使用量](#daily-usage)、[地區音訊詳細資料](#regional-audio-details)、[會議詳細資料](#conference-details)和[使用者清單](#user-list)報告在使用者利用 [向下切入] 報告（如下所述）中時，就會開始播放。

> [!NOTE]
> 必須填入建立和子網資料，才能提供區域和網路篩選功能。

## <a name="call-count-summary-report"></a>[通話計數摘要] 報告

主頁面（[通話計數摘要]）會立即提供最近30和90天的音訊、影片和螢幕共用會話數目，如章節標題中所述。 最初顯示的資料是針對組織而言，您可以使用頁面左側的 [交叉分析篩選器] 下拉式清單選項加以篩選。

![螢幕擷取畫面：團隊利用率報告](media/CQD-teams-utilization-report1.png)

1. 在交叉分析篩選器下拉式清單的右側，依媒體類型進行的呼叫數量會在過去30天內細分為內部/外部視圖。 我們可以透過上述螢幕擷取畫面來查看更多來自外部組織位置的呼叫，從而讓您考慮目前的全域環境。
  ![螢幕擷取畫面：團隊利用率報告](media/CQD-teams-utilization-report2.png)

1. 在 [媒體類型計數] 方塊的右邊，我們有 [每月通話計數依據媒體類型]，最後90天。 每個資料行和媒體類型都可以進行懸停，以顯示前一月或目前月份的計數，以提供使用趨勢資訊。
  ![螢幕擷取畫面：團隊利用率報告](media/CQD-teams-utilization-report3.png)
 

1. 中間圖形的運作方式就是90天的圖表，但它提供過去30天的每日使用狀況視圖，並允許使用者以滑鼠右鍵按一下，並向下切入特定日期的詳細資料。
  ![螢幕擷取畫面：團隊利用率報告](media/CQD-teams-utilization-report4.png)

在頁面左下方，您會發現一個表格，提供過去一年每個媒體類型的總計值。 
    ![螢幕擷取畫面：團隊利用率報告 ](media/CQD-teams-utilization-report5.png) ![ 螢幕擷取畫面：團隊利用率報告](media/CQD-teams-utilization-report6.png)   

在表格右側，橫條圖會顯示過去30天內最常使用（通話/串流）的用戶端。
   ![螢幕擷取畫面：團隊利用率報告](media/CQD-teams-utilization-report7.png)

此頁面的最後一組圖表會分別顯示每個媒體類型，以及顯示會議與 P2P 使用方式的細目分類。 下表顯示與 P2P 相比，有明顯較高的會議使用量。
  ![螢幕擷取畫面：團隊利用率報告](media/CQD-teams-utilization-report8.png)

## <a name="audio-minutes-summary-report"></a>音訊分鐘摘要報告

在 [音訊分鐘使用方式] 報告中，會透過幾種不同的視圖提供總分鐘使用量。 

我們會在交叉分析篩選器旁顯示三十天的使用方式摘要，輕鬆地使用文字方塊。 [最大值] 會顯示三十天的總計，並在其下方加上內部和外部細目。

![螢幕擷取畫面：團隊利用率報告](media/CQD-teams-utilization-report9.png)

右上方橫條圖提供會議音訊使用量的 yearlong。 將游標暫留在月份上以顯示會議音訊分鐘數。

若要在 P2P 與會議音訊中顯示差異，左下角圖表會取得過去一年的所有音訊，並在這兩種類型之間分割。

![螢幕擷取畫面：團隊利用率報告](media/CQD-teams-utilization-report10.png)

[音訊分鐘] 頁面的最後一個圖表會顯示全域地圖疊加上的音訊分鐘使用量。 只有在建立和子網資料上傳到租使用者時，才能使用此圖表。 在地圖上重迭的圓形圖可以深化到其中，進而提供區域音訊使用量。

![螢幕擷取畫面：團隊利用率報告](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a>鑽取功能

如先前所述，使用者可以深入探索每日和地區使用方式報告。

### <a name="daily-usage"></a>每日使用量

每日使用方式報告可讓系統管理員透過一天的時間來識別高峰期消耗量。 除了用法之外，我們還能捕獲該日的整體使用者觀點和意見反應。

![螢幕擷取畫面：團隊利用率報告](media/CQD-teams-utilization-report12.png)

[每日使用方式] 報告會顯示所選日期的音訊、影片和螢幕共用的數目，並增加內部和外部連線性的功能。 會議和對等細目細目分類是直接位於 [您的 [一份] [總] 方塊的右側。 報表的右上角提供一份清單，其中包含其相關聯的識別碼以及當天的參與者。 您也可以在會議清單中進一步向下流覽至 [會議詳細資料] 報告。 取代圖形

![螢幕擷取畫面：團隊利用率報告](media/CQD-teams-utilization-report13.png)

[中央區域] 中的 [橫條圖] 可讓使用者透過一天的時間來識別高峰期消耗量。 使用者可向下切入圖中所代表的小時，這將會在每小時顯示一份使用者清單報告。

在 [橫條圖] 的右側，使用者的意見反應會以視覺格式呈現。 在使用者觀點可以是主觀的情況下，它會提供可用於識別潛在問題的洞察力。

下表提供一系列的度量單位。 較差的百分比以及失敗率可提供具有潛在改善區域的系統管理員。 您也可以個別選取每個小時，如下所示。

這個資料可用來找出在高峰期內遇到問題的區域。


按一下該日期的欄，即可顯示該小時的度量單位。
![螢幕擷取畫面：團隊利用率報告](media/CQD-teams-utilization-report14.png)
  
  1.  圖表下方的表格會顯示該小時的度量單位。 這可以依據任何欄標題來排序;不過，我們很樂意找出有問題的區域。  
    ![螢幕擷取畫面：團隊利用率報告](media/CQD-teams-utilization-report15.png)
    
  2.  我們在此期間看到 IND 區域在會議中遇到較差的視頻效能。 接著，您可以使用 CQD QER Microsoft 報表來縮小有問題的位置，因為已識別出區域和時間範圍。

### <a name="conference-details"></a>會議詳細資料

[會議詳細資料] 報告可提供從出席者清單到在會話期間使用的媒體類型等其他會議的深入見解。

以滑鼠右鍵按一下會議的 [會議 ID] 圖表中的參與者列，以深入瞭解會議詳細資料。

![螢幕擷取畫面：團隊利用率報告](media/CQD-teams-utilization-report24.png)

![螢幕擷取畫面：團隊利用率報告](media/CQD-teams-utilization-report25.png)
  

我們可以在會議中看到參與者，並將所有相關資訊移至 [資料包遺失] 和 [抖動]，協助您在底部表格中進行可能的疑難排解工作。

![螢幕擷取畫面：團隊利用率報告](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a>地區音訊詳細資料

[地區音訊詳細資料] 向下切入特別顯示所選區域的音訊分鐘使用量。 擁有 CQD 存取權的使用者可以查看所選區域內 P2P 與會議音訊的使用方式趨勢。

1.  在 [通話計數摘要] 頁面上，透過資料表以特定區域為依據。
  ![螢幕擷取畫面：團隊利用率報告](media/CQD-teams-utilization-report16.png)

2.  選取需要其他區域資訊的那一列。
  ![螢幕擷取畫面：團隊利用率報告](media/CQD-teams-utilization-report17.png)

3.  資料趨勢會顯示在內部網路上所使用的大量分鐘數，以及會議最超越 P2P 的使用方式。
  ![螢幕擷取畫面：團隊利用率報告](media/CQD-teams-utilization-report18.png)

地區音訊趨勢可以用來顯示使用者如何受到世界各地的影響。 具體來說，我們會預期您會看到 EMEA 與 APAC 區域的外部使用方式，讓人員能在遠端作業時增加。


### <a name="user-list"></a>使用者清單

使用者清單 [向下切入] 會根據預期，提供查看報表之人員所選取之特定小時的使用者特定資訊。 您可以透過 [每日使用量] 報告上的 [每小時趨勢] 圖形中的向下切入來存取使用者清單報告。 以滑鼠右鍵按一下需要額外資訊，然後選取 [鑽取] 和 [使用者清單]，如下所示。

![螢幕擷取畫面：團隊利用率報告](media/CQD-teams-utilization-report19.png)

[使用者清單] 報表會透過頁面頂端中心的環圈圖顯示內部/外部連線性。 我們可以在下方影像中看到有大量參與公司網路外部的人員。

圖表右上角顯示在該小時內每個使用者所做的通話次數。

![螢幕擷取畫面：團隊利用率報告](media/CQD-teams-utilization-report20.png)

下表提供每位使用者在該時間內參與之會話的詳細資訊。 [失敗類型] 欄可用於判斷導致呼叫下降的原因。 [捕獲] 和 [轉譯裝置] 欄可用於識別為什麼來電報告品質不佳的原因。


## <a name="related-topics"></a>相關主題

[通話品質儀表板中提供的維度和量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通話品質儀表板中的資料流分類](stream-classification-in-call-quality-dashboard.md)

[設定商務用 Skype 通話分析](set-up-call-analytics.md)

[使用通話分析來疑難排解不良通話品質](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通話分析和通話品質儀表板](difference-between-call-analytics-and-call-quality-dashboard.md)

[Teams 疑難排解](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
 