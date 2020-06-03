---
title: 工作階段詳細資報告
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: e62ac09f-dfdc-4306-8e06-31349a3b27f0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
description: '[報告] 儀表板會顯示您組織中 Microsoft 365 或 Office 365 產品的活動概覽。 它可讓您深入瞭解個別的產品層級報告，讓您更精確地瞭解每個產品內的活動。'
ms.openlocfilehash: 951f93aabe66bdb7e6b92f9b2c6cf1627e7e1a10
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/02/2020
ms.locfileid: "44205504"
---
# <a name="session-details-report"></a>工作階段詳細資報告

[**報告**] 儀表板會顯示您組織中 Microsoft 365 或 Office 365 產品的活動概覽。 它可讓您深入瞭解個別的產品層級報告，讓您更精確地瞭解每個產品內的活動。 例如，您可以使用商務用**Skype 的 [會話詳細資料**] 報告，查看個別使用者的通話體驗的詳細資料。
  
查看[報表概覽](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)以取得更多可用報表。
  
此報告以及其他商務用 Skype 報告可提供活動的詳細資料，包括您組織內的會話詳細資料。 當您調查、規劃及針對貴組織進行其他業務決策，以及設定[通訊點數](/microsoftteams/what-are-communications-credits)時，這些詳細資料非常有用。
  
> [!NOTE]
> 當您以系統管理員身分登入 Microsoft 365 系統管理中心時，您可以看到所有商務用 Skype 報告。 
  
## <a name="how-to-get-to-the-skype-for-business-session-details-report"></a>如何取得商務用 Skype 會話詳細資料包表

1. 移至系統管理中心 >**報表**
    
2. 從左側功能表選取 [**報告**]，然後按一下 [**使用量**]。
    
3. 在 [**選取報告**] 下的清單中，按一下 [**商務用 Skype 會話詳細資料**]。
    
    > [!TIP]
    > 如果您沒有看到此報告，請移至**商務用 Skype 系統管理中心**  >  **報告**  >  **會話詳細資料**。 
  
    > [!IMPORTANT]
    > 視您擁有的 Microsoft 365 或 Office 365 訂閱而定，您可能不會看到這裡顯示的所有產品和報表。 
  
## <a name="interpret-the-skype-for-business-session-details-report"></a>解讀商務用 Skype 會話詳細資料包表

您可以查看每個顯示的欄，以取得使用者的商務用 Skype 會話詳細資料。
  
這就是報表看起來的樣子。
  
![商務用 Skype 會話詳細資料包告儀表板。](../images/3d87ab39-6eaa-46b5-b5f9-7f54dc987ae0.png)
  
***
![數位1](../images/sfbcallout1.png)<br/>[**依別名搜尋使用者**] 可讓您搜尋單一使用者，並顯示下表中的所有使用者會話詳細資料。 
***
![數位2](../images/sfbcallout2.png)<br/>[**從日期時間輸入**] 可讓您放入開始日期。 您可以使用行事歷來選取日期，或手動輸入日期。 必須填入此欄位。
***
![數位3](../images/sfbcallout3.png)<br/>[**輸入至日期時間**] 可讓您放入結束日期。 您可以使用行事歷來選取日期，或手動輸入日期。 如果未設定結束日期，則預設值為從開始日期起的30天。
***
![數位4](../images/sfbcallout4.png)<br/>下表顯示每個使用者的所有會話詳細資料明細。 這會顯示已指派商務用 Skype 及其會話資訊的所有使用者。 您可以在資料表中新增/移除資料行。 <br/><br/>該表在每個會話中都具有下列資料行：
*    **對話方塊識別碼**是 SIP 會話唯一識別碼的識別碼。
*    **媒體類型描述**說明會話是會議通話或 P2P 會話，以及所使用的媒體類型（音訊/視頻/應用程式共用）。
*    [**開始時間**] 是會話開始的時間。
*    [**結束時間**] 是會話結束的時間。
*    **FROM uri**是啟動會話的使用者或服務的 uri。 如果使用者從 PSTN 電話啟動會話，可能會是空白的。
*    **TO uri**是會話初始的目標使用者或服務的 uri。 在會議的情況中，這是召集人的 URI。 如果會話的目標是 PSTN 電話號碼，可能會是空白的。
*    **從用戶端版本**告訴您啟動會話之使用者或服務所使用之用戶端的使用者代理程式和版本。
*    在**用戶端版本**中，告訴您使用者或服務的使用者代理程式和版本，該使用者或服務是會話啟動的目標。
*    如果會話是電話會議，**會議 url**就是會議的 SIP url。 同一個會議通話中的所有使用者都將擁有相同的會議 URL。 
*    [**從電話號碼**] 是指會話目標的電話號碼（如果適用的話）。 電話號碼的最後一個數位可能會以 ' x」取代，以保護使用者隱私權。
*    [**電話號碼**] 是指會話目標的電話號碼（如果適用的話）。 電話號碼的最後一個數位可能會以 ' x」取代，以保護使用者隱私權。
*    [**從端點識別碼**] 是 [來自于] 使用者所使用端點的唯一 GUID。 用來識別使用者是否要從同一個端點傳達多個會話。 如果使用者使用 PSTN 手機或從服務啟動會話，可能會是空白的。
*    [ **To Endpoint Id** ] 是使用者所使用端點的唯一 GUID。 用來識別使用者是否要從同一個端點傳達多個會話。 如果使用者使用的是 PSTN 電話，或者會話是從服務啟動，或無法建立會話，可能會是空白的。
*    會議**實例**是使用會議 URL 的會議實例的唯一 GUID。 週期性會議將會有相同的會議 URL，但是會議的每個實例都會有差異會議實例。
*    **代表 uri**是指代表其建立會話之 DELEGATOR 的 uri。 <br/> [**由 URI 參照**] 是指參照會話的使用者 uri。
*    **回應代碼**是建立會話的 SIP 回應代碼，用來指出會話是否已順利建立。

針對每個會話，有一個子資料工作表，其中包含不同的資料，視情況而定。 下列清單列出 [寄件者] 和 [寄件者] 的子資料工作表中提供的索引標籤。
*    [會話] 索引標籤會顯示電腦與作業系統的相關資料。
*    [MEDIALINES] 索引標籤會顯示網路連通性資訊和裝置資訊。
*    [AUDIOSTREAMS] 索引標籤會顯示有關會話中所涉及之音訊資料流程的網路效能資料。
*    [AUDIOCLIENTEVENTS] 索引標籤會顯示影響音訊體驗的用戶端檢測問題的相關資料。
*    [AUDIOSIGNALS] 索引標籤會顯示有關會話之音訊信號處理的資料。
*    [APPSHARINGSTREAMS] 索引標籤會顯示會話中所涉及之應用程式共用或桌面共用資料流程的網路效能資料。
*    [VIDEOCLIENTEVENTS] 索引標籤會顯示用戶端檢測到影響影片體驗的問題資料。
*    [VIDEOSTREAMS] 索引標籤會顯示有關會話中所涉及之影片資料流程的網路效能資料。
*    [TRACEROUTES] 索引標籤會顯示在會話期間透過 traceroute 收集的網路躍點數。 在會話中使用的實際媒體路徑可能會有所不同，而且只有在會話中有音訊時，才能使用此資料。
*    [FEEDBACKREPORTS] 索引標籤會顯示會話中使用者所提供的任何通話問卷資料終點。
***
![數位5](../images/sfbcallout5.png)<br/>按一下以將欄拖曳至依據特定欄進行分組，如果您想要建立一個將一或多個欄中的所有資料組成群組的視圖 **，請在這裡拖曳欄標題**。 
***
![數位6](../images/sfbcallout6.png)<br/>您也可以按一下或敲擊 [**匯出至 excel** ] 按鈕，將報告資料匯出至 Excel .csv 檔案。 <br/><br/> 這會匯出所有使用者的資料，並可讓您進行簡單的排序與篩選，以進行進一步分析。 如果您的使用者少於2000，您可以在報表本身的資料表中排序和篩選。 如果您有超過2000的使用者，若要篩選和排序，您必須匯出資料。  
   
## <a name="want-to-see-other-skype-for-business-reports"></a>想要查看其他商務用 Skype 報表嗎？

- [商務用 Skype 活動報告](activity-report.md)您可以查看使用者使用對等、組織的方式，以及參與會議會話的數量。
    
- [商務用 Skype 裝置使用方式報告](device-usage-report.md)您可以查看裝置，包括已安裝商務用 Skype 應用程式的 Windows 作業系統和行動裝置，以及用於 IM 和會議的行動裝置。
    
- [商務用 Skype 會議召集人活動報告](conference-organizer-activity-report.md)您可以查看您的使用者使用 IM、音訊/視頻、應用程式共用、Web、撥入/取出-協力廠商以及撥入/登出-Microsoft 來組織會議的數量。
    
- [商務用 Skype 會議參與者活動報告](conference-participant-activity-report.md)您可以查看有多少 IM、音訊/視頻、應用程式共用、網頁和撥入/撥出會議會議都在參與。
    
- [商務用 Skype 對等活動報告](peer-to-peer-activity-report.md)您可以查看您的使用者使用 IM、音訊/視頻、應用程式共用和傳送檔案的數量。
    
- [商務用 SKYPE PSTN 使用方式報告](pstn-usage-report.md)您可以在輸入/撥出通話中看到所花費的分鐘數，以及這些通話的成本。

- [商務用 Skype 使用者封鎖報告](users-blocked-report.md)您可以看到貴組織中已封鎖進行 PSTN 通話的使用者。

- [商務用 SKYPE PSTN 分鐘池報告](pstn-minute-pools-report.md)您可以查看貴組織內的當月所消耗的分鐘數。
    
## <a name="related-topics"></a>相關主題
[系統管理中心的活動報告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 