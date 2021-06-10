---
title: 使用 CQD Microsoft Teams在 Power BI中查看使用方式
ms.author: serdars
author: SerdarSoysal
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
description: 使用 Teams使用方式Power BI報表Microsoft Teams通話品質儀表板 (CQD) ，以追蹤Microsoft Teams使用方式。
ms.openlocfilehash: 719f02ce7a5cd36e96ed7fd563c259c6e77764fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095037"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a>使用 CQD Microsoft Teams在 Power BI中查看使用方式

新增于 2020 年 3 月，我們已新增 Teams 使用方式報表至可下載的[CQD Power BI查詢範本](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。 

這個新Teams使用方式報告可讓您存取 Teams 通話品質儀表板 (CQD) 資料，來瞭解 (以及您的) 使用者使用 Microsoft Teams 量。 這些報告是一個集中式位置，系統管理員和商務領導者都可以快速前往此資料。

使用Teams報告Power BI兩個主要報告：通話 **[計數摘要](#call-count-summary-report)** 和 **[音訊分鐘摘要](#audio-minutes-summary-report)**。 當使用者[利用](#daily-usage)[下列描述所述](#regional-audio-details)之向下切[](#conference-details)入報表時[](#user-list)，會使用每日使用量、地區音訊詳細資料、會議詳細資料及使用者清單報告。

> [!NOTE]
> 必須填上建築物和子網資料，以提供地區和網路篩選功能。

## <a name="call-count-summary-report"></a>通話計數摘要報表

通話 (摘要) 首頁會如章節標題所述，立即提供過去 30 天和 90 天內的音訊、視視和螢幕共用會話數目。 最初顯示的資料適用于整個組織，而且可以使用頁面左側的分析篩選器下拉式選項進行篩選。

![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report1.png)

1. 在分析分析片下拉式下拉清單的右側，媒體類型的通話數會細分為過去 30 天內的內部/外部視圖。 我們可以透過上述螢幕擷取畫面，看到組織外部位置發生更多通話，考慮到目前的全域環境，這很合理。
  ![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report2.png)

1. 在媒體類型計數方塊的右側，我們有過去 90 天的按媒體類型計算每月通話計數。 每一欄和媒體類型都可以停留在上方，以顯示前一個月或目前月份至今的計數，並提供使用趨勢資訊。
  ![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report3.png)
 

1. 中間圖形的作用與 90 天圖形一樣，不過它提供過去 30 天的每日使用量視圖，並允許使用者以滑鼠右鍵按一下並向下向下切入特定日期的詳細資訊。
  ![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report4.png)

在頁面左下區段，您可以找到一個表格，提供過去一年每種媒體類型的總計值。 
    ![螢幕擷取畫面：Teams使用方式報告 ](media/CQD-teams-utilization-report5.png) ![ 螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report6.png)   

在表格右側，橫條圖會顯示過去 30 天內 (通話/) 流的用戶端。
   ![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report7.png)

此頁面的最後一組圖表會個別顯示每一種媒體類型，以及顯示會議與 P2P 使用方式的明細。 下列圖表顯示，與 P2P 相比，會議使用量大幅增加。
  ![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report8.png)

## <a name="audio-minutes-summary-report"></a>音訊分鐘摘要報告

在音訊分鐘使用量報告中，總分鐘使用量會透過幾個不同的視圖提供。 

我們有三十天的使用量摘要顯示在分析分析器旁邊，因為很容易使用文字方塊。 頂端數位會顯示三十天總計，其內部和外部明細低於該數位。

![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report9.png)

右上方的橫條圖提供會議音訊使用量的一年模式。 將游標停留在月份上以顯示會議音訊分鐘數。

若要顯示 P2P 和會議音訊的差異，左下角圖表會採用過去一年的所有音訊，並分為兩種類型。

![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report10.png)

音訊分鐘數頁面的最後一個圖表會顯示全域地圖覆本上的音訊分鐘使用量。 只有當建築物和子網資料上傳至租使用者時，此圖表才能使用。 您可以向下切入地圖上的圓形圖覆面，提供地區音訊使用量。

![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a>深入分析功能

如先前所指出，使用者可以深入查看每日和區域使用方式報告。

### <a name="daily-usage"></a>每日使用量

每日使用量報告可讓系統管理員識別一天中的尖峰消費期間。 除了使用方式之外，我們也能夠收集當天的整體使用者情緒和意見。

![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report12.png)

每日使用量報告會顯示所選日的音訊、視音訊和螢幕畫面共用數量，並新增了區分內部和外部連接的能力。 會議與對等分解位於模式總計方塊的右方。 報表的右上方會提供一份會議清單，包含其相關聯的 ID 和當天的參與者。 會議清單也提供另一個向下切入至會議詳細資料包表。 取代圖形

![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report13.png)

中央區域中的橫條圖可讓使用者識別一天中的尖峰消費期間。 使用者可以向下向下切入圖形上代表的小時，該小時會呈現使用者清單報表。

在橫條圖右側，使用者意見回饋會以視覺格式呈現。 雖然使用者情緒可能有些不一樣，但它提供深入見解，可用來識別潛在問題。

底端表格提供一天的度量範圍。 不佳的百分比與失敗率可以為系統管理員提供潛在的改進領域。 每小時也可以個別選取，如下所示。

此資料可用來識別在尖峰消費期間發生問題的區域。


按一下該天的欄以顯示該小時的度量。
![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report14.png)
  
  1.  圖表下方的表格會顯示該小時的度量單位。 這可排序任何欄標題;不過，我們有興趣尋找有問題的區域。  
    ![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report15.png)
    
  2.  我們看到 IND 區域在這段期間，在會議中遇到不佳的視像效果。 接著，當已識別地區與時間範圍時，CQD QER Microsoft 報告可用來縮小有問題的位置。

### <a name="conference-details"></a>會議詳細資料

會議詳細資料包告提供會議的其他深入資訊，從出席者清單到會話期間使用的媒體類型。

以滑鼠右鍵按一下 [每日使用狀況」 頁面上會議 ID 圖表中的參與者欄，以向下向下切入會議詳細資料。

![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report24.png)

![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report25.png)
  

我們可以查看會議參與者，以及所有相關資訊，包括封包遺失和抖動，以協助下表中的潛在疑難排解工作。

![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a>地區音訊詳細資料

地區音訊詳細資料向下向下縮小，專門顯示所選區域的音訊分鐘使用量。 具有 CQD 存取權的使用者可以看到所選地區內 P2P 和會議音訊的使用趨勢。

1.  在呼叫計數摘要頁面上，在表格中以特定區域方式向下切入。
  ![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report16.png)

2.  選取包含區域的其他資訊列。
  ![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report17.png)

3.  資料趨勢顯示內部網路上使用大量分鐘數，而會議遠超過 P2P 使用。
  ![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report18.png)

地區音訊趨勢可用來顯示使用者受到外部影響的影響。 具體來說，目前我們預期 EMEA 和 APAC 地區的外部使用量會增加，因為有人要求遠端工作。


### <a name="user-list"></a>使用者清單

使用者清單向下切入會如預期提供檢視報表之人員所選取之特定時間的使用者特定資訊。 使用者清單報表可在每日使用量報表的每小時趨勢圖形中向下向下切入來訪問。 以滑鼠右鍵按一下需要額外資訊的時間，然後選取 [鑽取及使用者清單>，如下所示。

![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report19.png)

使用者清單報表會透過頁面頂端中心的環圈圖顯示內部/外部連接。 如下圖所示，在公司網路外部有大量參與。

圖形的右上方顯示每個使用者在一小時內的通話次數。

![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report20.png)

底部表格提供每個使用者在這一小時參與會話的詳細資訊。 在判斷導致通話下拉的原因時，失敗類型欄很有用。 在識別通話品質不佳的原因時，捕獲和呈現裝置欄非常實用。


## <a name="related-topics"></a>相關主題

[通話品質儀表板中提供的維度和量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通話品質儀表板中的資料流分類](stream-classification-in-call-quality-dashboard.md)

[設定商務用 Skype 通話分析](set-up-call-analytics.md)

[使用通話分析來疑難排解不良通話品質](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通話分析和通話品質儀表板](./monitor-call-quality-qos.md)

[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)
