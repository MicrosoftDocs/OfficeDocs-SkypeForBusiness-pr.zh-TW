---
title: 商務用 Skype Server 中的會議摘要子報告
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
ms.assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
description: 摘要：瞭解商務用 Skype Server 中的會議摘要子報表。
ms.openlocfilehash: 6c2161287b3446d5b7cba28e984ad50cd3a136e9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60838625"
---
# <a name="conference-summary-subreport-in-skype-for-business-server"></a>商務用 Skype Server 中的會議摘要子報告
 
**摘要：** 深入瞭解商務用 Skype Server 中的會議摘要子報表。
  
會議摘要子報告提供了失敗會議工作階段的整體檢視。這些失敗的工作階段可藉由工作階段類型加以細分為：焦點工作階段及 MCU 工作階段。
  
## <a name="filters"></a>篩選

篩選器可供您用於傳回更加精確的一組資料，或是使用其他方式檢視傳回的資料。下表列出可搭配會議摘要子報告使用的篩選器。
  
**會議摘要子報告篩選器**

|**名稱**|**描述**|
|:-----|:-----|
|**From** <br/> |時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：  <br/> 7/7/2015 1:00 PM  <br/> 如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：  <br/> 7/7/2015  <br/> 若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：  <br/> 7/3/2015  <br/> 星期永遠是從星期日開始星期六結束。  <br/> |
|**To** <br/> |時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：  <br/> 7/7/2015 1:00 PM  <br/> 如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：  <br/> 7/7/2015  <br/> 若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：  <br/> 7/3/2015  <br/> 星期永遠是從星期日開始星期六結束。  <br/> |
|**集區** <br/> |登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。您可以選取個別的集區，或是按一下 [全部] 檢視所有集區的資料。此下拉式清單會自動將資料庫內的資料填入。<br/> |
   
## <a name="metrics"></a>度量

下表列出會議摘要子報告中提供的資訊。
  
**會議摘要子報告計量**

|**名稱**|**可以排序這個項目嗎？**|**描述**|
|:-----|:-----|:-----|
|**會議總數** <br/> |否  <br/> |保留的會議總數。  <br/> |
|**會議工作階段總數** <br/> |否  <br/> |會議工作階段總數。單一會議可能會有多個工作階段；例如，會議可能包含焦點工作階段及 MCU 工作階段。  <br/> |
|**整體工作階段失敗率** <br/> |否  <br/> |所有失敗工作階段的百分比。  <br/> |
|**焦點工作階段** <br/> |否  <br/> |焦點工作階段總數。  <br/> |
|**焦點失敗率** <br/> |否  <br/> |失敗之焦點工作階段的百分比。  <br/> |
|MCU 工作階段  <br/> |否  <br/> |MCU 工作階段總數。  <br/> |
|**MCU 失敗率** <br/> |否  <br/> |失敗之 MCU 工作階段的百分比。  <br/> |
|**依形式區分的 MCU 工作階段** <br/> |否  <br/> |依形式分組 (例如，IM 會議) 的 MCU 工作階段總數。  <br/> |
|**依形式區分的失敗率** <br/> |否  <br/> |依形式分組 (例如，IM 會議) 的 MCU 工作階段百分比。  <br/> |
   

