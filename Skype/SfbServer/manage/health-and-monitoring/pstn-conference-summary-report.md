---
title: 商務用 Skype Server 中的 PSTN 會議摘要報告
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
description: 摘要：瞭解商務用 Skype Server 中的 PSTN 會議摘要報告。
ms.openlocfilehash: 19038b29f46e33026e3ef865226aa4d087b0a0da
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862290"
---
# <a name="pstn-conference-summary-report-in-skype-for-business-server"></a>商務用 Skype Server 中的 PSTN 會議摘要報告
 
**摘要：** 深入瞭解商務用 Skype Server 中的《 PSTN 會議摘要報告。
  
在商務用 Skype Server 中，PSTN 會議是指至少有一個參與者透過使用 PSTN (公用交換電話網路) 電話撥號進入音訊部分的任何會議。  (PSTN 電話是 "室內電話"、"蜂窩電話] 或任何其他未利用 Voice over IP 的電話。 ) 雖然在監控報告中稱為 PSTN 會議，但這些會議甚至可能更常見，稱為電話撥入式會議。
  
PSTN 會議摘要報告提供您組織中所有 PSTN 會議的相關資訊 (也就是說，所有具有至少一個撥入式使用者) 的會議。 此報告包含有關 PSTN 會議總數、參與這些會議的人員總數，以及最重要的電話撥入式使用者總數 (全部 PSTN 參與者度量) 中的相關資訊。
  
## <a name="accessing-the-pstn-conference-summary-report"></a>存取 PSTN 會議摘要報告

PSTN 會議摘要報告只可從監控報告首頁進行存取。 此報告未連結至任何其他報告。 請注意，您無法為 PSTN 會議檢索詳細的呼叫資訊，因為個別端點負責提交此資訊。 PSTN 電話不具備追蹤或送出通話詳細資訊的能力。
  
## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a>PSTN 會議摘要報告的最佳用法

若要決定所有包含撥入使用者之會議的百分比，請將 [PSTN 會議總數] 度量值與[商務用 Skype Server 中會議摘要報告](conference-summary-report.md)上找到的「會議總數」度量值進行比較。
  
如果您看不到許多 PSTN 會議，如您可能會看到，請記住組織允許撥入使用者之會議的功能，取決於已指派給使用者的會議原則：如果允許很少的使用者持有 PSTN 會議，您顯然會看到極少的 PSTN 會議。 您可以從商務用 Skype Server 管理命令介面內執行下列命令，以快速確認您 (的哪一種會議原則) 允許使用者排程 PSTN 會議：
  
```PowerShell
Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing
```

該命令將傳回類似下列的資料：
  
<pre>
Identity                                EnableDialInConferencing
--------                                ------------------------
Global                                                      True
site:Redmond                                               False
site:Dublin                                                False
Tag:RedmondDialInUsers                                      True
Tag:DublinDialInUsers                                       True
</pre>

## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集，或者以不同方法檢視傳回的資料。 例如，PSTN 會議摘要報告可讓您選擇資料的分組方式。 在此情況下，會依小時、天、周或月群組會議。
  
下表列出您可以搭配 PSTN 會議摘要報告使用的篩選器。
  
**PSTN 會議摘要報告篩選器**

|**名稱**|**描述**|
|:-----|:-----|
|**From** <br/> |時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：  <br/> 7/7/2015 1:00 PM  <br/> 如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：  <br/> 7/7/2015  <br/> 若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：  <br/> 7/3/2015  <br/> 星期永遠是從星期日開始星期六結束。  <br/> |
|**To** <br/> |時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：  <br/> 7/7/2015 1:00 PM  <br/> 如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：  <br/> 7/7/2015  <br/> 若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：  <br/> 7/3/2015  <br/> 星期永遠是從星期日開始星期六結束。  <br/> |
|**Interval** <br/> | 時間間隔。請選取下列其中一項： <br/>  每小時 (最多可以顯示 25 個小時) <br/>  每日 (最多可以顯示 31 天) <br/>  每週 (最多可以顯示 12 週) <br/>  每月 (最多可以顯示 12 個月) <br/>  若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。 例如，如果您選取 [開始日期 7/7/2015] 和 [結束2/28/2015 日期] 的 [每日間隔]，將會顯示 8/7/2015 12:00 AM 到 9/7/2015 12:00 AM (的資料，也就是有31天的資料) 總計。 <br/> |
   
## <a name="metrics"></a>度量

下表列出 PSTN 會議摘要報告中的資訊。
  
**PSTN 會議摘要報告計量**

|**名稱**|**可以排序這個項目嗎？**|**描述**|
|:-----|:-----|:-----|
|**每小時** <br/> **日常** <br/> **每週** <br/> **每月** <br/> |否  <br/> |指示所選的時間間隔。 在適用的情況下，只要按一下指定的時間間隔，即可檢視該間隔的詳細資訊。 例如，如果您使用的是每日間隔，而您按一下 [7/7/2015]，就會看到該日期的使用者註冊活動的每小時細目。  <br/> |
|**PSTN 會議總數** <br/> |否  <br/> |允許撥入存取的會議總數。  <br/> |
|**參與者總數** <br/> |否  <br/> |參與允許撥入存取之會議的人員總數。  <br/> |
|**A/V 會議總分鐘數** <br/> |否  <br/> |音訊/視訊會議的總時數。  <br/> |
|**A/V 會議參與者總分鐘數** <br/> |否  <br/> |音訊/視頻參與者的總時數。 例如，如果一個參與者在 A/V 會議中花了五分鐘，另一個參與者在同一部會議中花三分鐘的時間，則會議參與者時間的總數 A/V 會是8分鐘。  <br/> |
|**PSTN 參與者總數** <br/> |否  <br/> |撥打至允許撥入存取之會議的總使用者人數。  <br/> |
|**PSTN 參與者分鐘總數** <br/> |否  <br/> |撥號使用者所花費的會議時間總量。 例如，如果一個撥入式參與者在會議中花了五分鐘的時間，另一個參與者在同一部會議中花三分鐘的時間，則 PSTN 參與者時間總量會是8分鐘。  <br/> |
|**獨特的會議召集人** <br/> |否  <br/> |組織至少一部允許撥入存取之會議的總使用者人數。 召集過多次會議的使用者計為一個專屬召集人，就像只召集過一次會議的使用者一樣。  <br/> |
   

