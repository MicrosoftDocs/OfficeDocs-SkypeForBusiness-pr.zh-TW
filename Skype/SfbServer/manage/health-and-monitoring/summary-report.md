---
title: 商務用 Skype Server 中的通話診斷摘要報告
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9091de56-13e6-440e-9353-f57c10c906fe
description: 摘要：瞭解商務用 Skype Server 中所用的通話診斷摘要報告。
ms.openlocfilehash: 76907a319f5e4d828829daf7bc0564a964eb7633
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397697"
---
# <a name="call-diagnostic-summary-report-in-skype-for-business-server"></a>商務用 Skype Server 中的通話診斷摘要報告
 
**總結：** 深入瞭解商務用 Skype Server 所使用的通話診斷摘要報告。
  
通話診斷摘要報告提供失敗的對等和會議會話的整體外觀。 報告顯示這兩種類型的會話的整體失敗率，並以會話形式的形式進一步打破失敗資訊：
  
- 立即訊息
    
- 應用程式共用
    
- 檔案傳輸
    
- 音訊
    
- 影片
    
## <a name="accessing-the-call-diagnostic-summary-report"></a>存取通話診斷摘要報告

通話診斷摘要報告可從監控報告的首頁進行存取。 在 [通話診斷摘要報告] 中，您可以按一下報告之 [Peer-to-Peer 會話摘要] 區段下的 [失敗率]，[以存取商務用 Skype Server 中的 Peer-to-Peer 活動診斷報告](peer-to-peer-activity-diagnostic-report.md)。 您也可以按一下下列任一會議計量，[以在商務用 Skype Server 中存取會議診斷報告](conference-diagnostic-report.md)：
  
- 整體工作階段失敗率
    
- 焦點失敗率
    
- MCU 失敗率
    
## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a>通話診斷摘要報告的最佳用法

通話診斷摘要報告包含的圖形會比較商務用 Skype Server 中所使用之各種形式的失敗率。 這些圖形中的資料行實際上是 hotlinks 的;例如，如果您按一下點對點工作階段的 [立即訊息] 欄，您會[在商務用 Skype Server 中深入瞭解 Peer-to-Peer 活動診斷報告](peer-to-peer-activity-diagnostic-report.md)的實例，該報告提供 [通話診斷摘要報告] 中所包含之所有立即訊息會話的其他詳細資料。
  
## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。 例如，[通話診斷摘要] 報告可讓您篩選諸如會話中所使用的註冊區集區或 Edge Server 等事項。 您也可以選擇資料的分組方式。 在這種情況下，通話會按照小時、日、星期或月而加以分組。
  
下表列出您可以搭配通話診斷摘要報告使用的篩選器。
  
**通話診斷摘要報告篩選器**

|**名稱**|**描述**|
|:-----|:-----|
|**From** <br/> |時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：  <br/> 7/7/2015 1:00 PM  <br/> 如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：  <br/> 7/7/2015  <br/> 若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：  <br/> 7/3/2015  <br/> 星期永遠是從星期日開始星期六結束。  <br/> |
|**To** <br/> |時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：  <br/> 7/7/2015 1:00 PM  <br/> 如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：  <br/> 7/7/2015  <br/> 若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：  <br/> 7/3/2015  <br/> 星期永遠是從星期日開始星期六結束。  <br/> |
|**Interval** <br/> | 時間間隔。請選取下列其中一項： <br/>  每小時 (最多可以顯示 25 個小時) <br/>  每日 (最多可以顯示 31 天) <br/>  每週 (最多可以顯示 12 週) <br/>  每月 (最多可以顯示 12 個月) <br/>  若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。 例如，如果您選取 [開始日期 7/7/2015] 和 [結束2/28/2015 日期] 的 [每日間隔]，將會顯示 8/7/2015 12:00 AM 到 9/7/2015 12:00 AM (的資料，也就是有31天的資料) 總計。 <br/> |
|**集區** <br/> |登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。您可以選取個別的集區，或是按一下 [全部] 檢視所有集區的資料。此下拉式清單會自動將資料庫內的資料填入。<br/> |
   
## <a name="metrics-for-peer-to-peer-sessions"></a>Peer-to-Peer 會話的計量

下表列出點對點工作階段的通話診斷摘要報告所提供的資訊 (也就是說，只涉及兩位參與者) 。
  
**Peer-to-Peer 會話的計量**

|**名稱**|**可以排序這個項目嗎？**|**描述**|
|:-----|:-----|:-----|
|**工作階段總數** <br/> |否  <br/> |進行中的點對點工作階段總數。  <br/> |
|**失敗率** <br/> |否  <br/> |失敗的點對點工作階段百分比。 當您按一下此專案時，報告會顯示 Peer-to-Peer 活動診斷報告，其中會顯示失敗的點對點工作階段詳細資訊。  <br/> |
   
## <a name="metrics-for-conferencing-sessions"></a>會議會話的計量

下表列出會議會話的通話診斷報告中所提供的資訊 (也就是說，涉及三個或更多參與者) 的會話。
  
**會議會話的計量**

|**名稱**|**可以排序這個項目嗎？**|**描述**|
|:-----|:-----|:-----|
|**會議總數** <br/> |否  <br/> |已執行的會議總數。  <br/> |
|**會議工作階段總數** <br/> |否  <br/> |已執行的會議會話總數。  <br/> |
|**整體工作階段失敗率** <br/> |否  <br/> |失敗之會議會話總數所占的百分比。  <br/> |
|**焦點工作階段** <br/> |否  <br/> |失敗的專注型會議會話總數。  <br/> |
|**焦點失敗率** <br/> |否  <br/> |失敗之專注于會議會話的百分比。  <br/> |
|**MCU 會話** <br/> |否  <br/> |會議服務器型 (的總數（以前稱為 Multipoint Control Unit 或 MCU) 會議失敗）。  <br/> |
|**MCU 失敗率** <br/> |否  <br/> |會議服務器型 (（以前稱為 Multipoint Control Unit 或 MCU) 會議失敗）的百分比。  <br/> |
   

