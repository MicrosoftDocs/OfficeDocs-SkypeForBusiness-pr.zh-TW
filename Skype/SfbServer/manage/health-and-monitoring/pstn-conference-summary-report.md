---
title: 商務用 Skype Server 中的 PSTN 會議摘要報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
description: '摘要: 瞭解商務用 Skype Server 中的 PSTN 會議摘要報告。'
ms.openlocfilehash: 8b8b108243e257c414e9d6bb101e69fc9701d82e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188725"
---
# <a name="pstn-conference-summary-report-in-skype-for-business-server"></a>商務用 Skype Server 中的 PSTN 會議摘要報告
 
**摘要:** 瞭解商務用 Skype Server 中的 PSTN 會議摘要報告。
  
在商務用 Skype Server 中, PSTN 會議是一個會議, 其中至少有一個參與者使用 PSTN (公開交換電話網絡) 電話撥入音訊部分。 (PSTN 手機是「有線電話、」手機或任何其他不使用語音 over IP 的電話)。雖然在監視報告中稱為 PSTN 會議, 但這些會議可能更常見, 也稱為撥入式會議。
  
PSTN 會議摘要報告提供貴組織中所有 PSTN 會議的相關資訊 (也就是至少有一個撥入使用者的所有會議)。 此報告包含有關 PSTN 會議總數、參與這些會議的人數總數, 以及最重要的電話撥入使用者總數 (總 PSTN 參與者統計值) 的相關資訊。
  
## <a name="accessing-the-pstn-conference-summary-report"></a>存取 PSTN 會議摘要報告

PSTN 會議摘要報告只能從 [監控報告] 首頁進行存取。 此報告未連結至任何其他報表。 請注意, 您無法取得 PSTN 會議的詳細呼叫資訊, 因為個別端點負責提交此資訊。 PSTN 手機無法追蹤或提交通話詳細資訊。
  
## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a>充分利用 PSTN 會議摘要報告

若要判斷包含撥入使用者的所有會議的百分比, 請比較 PSTN 會議總量與[商務用 Skype Server 的 [會議摘要] 報告中](conference-summary-report.md)的 [總會議] 度量值。
  
如果您沒有看到許多您可能會看到的 PSTN 會議, 請記住, 組織允許撥入使用者的會議的能力取決於已指派給使用者的會議原則: 您的使用者數只有幾個使用者可以保留 PSTN-ZA&PLATFORM 會議您顯然會看到很少的 PSTN 會議。 您可以從商務用 Skype Server Management Shell 中執行下列命令, 以快速確認您的會議原則 (如果有的話), 允許使用者排程 PSTN 會議:
  
```
Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing
```

這樣會傳回如下所示的資料:
  
<pre>
Identity                                EnableDialInConferencing
--------                                ------------------------
Global                                                      True
site:Redmond                                               False
site:Dublin                                                False
Tag:RedmondDialInUsers                                      True
Tag:DublinDialInUsers                                       True
</pre>

## <a name="filters"></a>濾鏡

篩選提供一種方式, 可讓您傳回更精細設定目標的資料集, 或以不同的方式來查看傳回的資料。 例如, PSTN 會議摘要報告可讓您選擇資料的分組方式。 在這種情況下, 會議會依小時、日、周或月進行分組。
  
下表列出您可搭配 PSTN 會議摘要報告使用的篩選準則。
  
**PSTN 會議摘要報告篩選器**

|**名稱**|**說明**|
|:-----|:-----|
|**從** <br/> |時間範圍的開始日期/時間。 若要依時間查看資料, 請輸入 [開始日期] 和 [時間], 如下所示:  <br/> 7/7/2015 1:00 PM  <br/> 如果您沒有輸入開始時間, 報告會在指定日期自動于12:00 點開始。 若要依天查看資料, 只需輸入日期:  <br/> 7/7/2015  <br/> 若要依周或依月查看, 請在您要查看的周或月份中, 輸入您要查看的日期 (不需要輸入周或月的第一天):  <br/> 7/3/2015  <br/> 周數總是從星期日到星期六執行。  <br/> |
|**自** <br/> |時間範圍的結束日期/時間。 若要依時間查看資料, 請輸入 [結束日期] 和 [時間], 如下所示:  <br/> 7/7/2015 1:00 PM  <br/> 如果您沒有輸入結束時間, 報告會在指定日期自動結束于12:00。 若要依天查看資料, 只需輸入日期:  <br/> 7/7/2015  <br/> 若要依周或依月查看, 請在您要查看的周或月份中, 輸入您要查看的日期 (不需要輸入周或月的第一天):  <br/> 7/3/2015  <br/> 周數總是從星期日到星期六執行。  <br/> |
|**Interval** <br/> | 時間間隔。 選取下列其中一項: <br/>  每小時 (最多可顯示25小時) <br/>  每天 (最多可以顯示31天) <br/>  每週 (最多可以顯示12周) <br/>  每月 (最多可以顯示12個月) <br/>  如果 [開始] 和 [結束] 日期超過所選間隔所允許的最大值數, 則會顯示值的數目上限 (從開始日期開始)。 例如, 如果您選取 [開始日期 7/7/2015] 和 [結束日期] 2/28/2015 的 [日間隔], 則會顯示 8/7/2015 12:00 AM 至 9/7/2015 12:00 AM (也就是31天內的資料) 的資料。 <br/> |
   
## <a name="metrics"></a>指標

下表列出 PSTN 會議摘要報告中的資訊。
  
**PSTN 會議摘要報告度量單位**

|**名稱**|**您可以針對此專案進行排序嗎？**|**說明**|
|:-----|:-----|:-----|
|**工資** <br/> **日常** <br/> **周更新** <br/> **次** <br/> |不  <br/> |指出選取的時間間隔。 在適當的地方, 您可以按一下指定的時間間隔, 以查看該間隔的詳細資訊。 例如, 如果您使用的是每日間隔, 而您按一下 [7/7/2015], 就會看到該日期的使用者註冊活動的每小時細目。  <br/> |
|**PSTN 會議總數** <br/> |不  <br/> |允許撥入存取的會議總數。  <br/> |
|**參與者總數** <br/> |不  <br/> |參與允許撥入存取之會議的人員總數。  <br/> |
|**A/V 會議紀要總計** <br/> |不  <br/> |音訊/視訊會議的總時間。  <br/> |
|**A/V 會議參與者紀要總計** <br/> |不  <br/> |音訊/視覺參與者的總時間。 例如, 如果一個參與者在 A/V 會議中花費了五分鐘, 而另一個參與者在同一筆會議中花費了三分鐘, 則總的 A/V 會議參與者時間會是八分鐘。  <br/> |
|**PSTN 參與者總數** <br/> |不  <br/> |撥入會議且允許撥入存取的使用者總數。  <br/> |
|**PSTN 參與者通話總分鐘數** <br/> |不  <br/> |撥入使用者所花費的會議時間總量。 例如, 如果一個撥入參與者在會議中花了五分鐘的時間, 而另一個參與者在同一個會議中花費了三分鐘, 則 PSTN 參與者時間總會是八分鐘。  <br/> |
|**唯一的會議召集人** <br/> |不  <br/> |組織至少有一部允許撥入存取的會議的使用者總數。 組織多個會議的使用者會算作一個唯一的召集人, 就像只組織單一會議的使用者。  <br/> |
   

