---
title: 商務用 Skype Server 中的 P2P 摘要子報表
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
description: 摘要：瞭解商務用 Skype Server 中的 P2P 摘要子報表。
ms.openlocfilehash: 14472ee8ede0e05d56f026561dfd8884c3d6c152
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774853"
---
# <a name="p2p-summary-subreport-in-skype-for-business-server"></a>商務用 Skype Server 中的 P2P 摘要子報表
 
**摘要：** 瞭解商務用 Skype Server 中的 P2P 摘要子報表。
  
P2P 摘要子報表可提供失敗的對等通訊會話的整體觀點。
  
## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集，或者以不同方法檢視傳回的資料。 下表列出您可以搭配 P2P 摘要子報表使用的篩選器。
  
**P2P 摘要子報表篩選**

|**名稱**|**描述**|
|:-----|:-----|
|**From** <br/> |時間範圍的開始日期和時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：  <br/> 7/7/2015 1:00 PM  <br/> 如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：  <br/> 7/7/2015  <br/> 若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：  <br/> 7/3/2015  <br/> 星期永遠是從星期日開始星期六結束。  <br/> |
|**To** <br/> |時間範圍的結束日期和時間。若要按照小時檢視資料，請輸入結束日期和時間，如下所示：  <br/> 7/7/2015 1:00 PM  <br/> 如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：  <br/> 7/7/2015  <br/> 若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：  <br/> 7/3/2015  <br/> 星期永遠是從星期日開始星期六結束。  <br/> |
|**集區** <br/> |登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。您可以選取個別的集區，或是按一下 [全部] 檢視所有集區的資料。此下拉式清單會自動將資料庫內的資料填入。<br/> |
   
## <a name="metrics"></a>度量

下表列出 P2P 摘要子報表中提供的資訊。
  
**P2P 摘要子報表度量**

|**名稱**|**可以排序這個項目嗎？**|**描述**|
|:-----|:-----|:-----|
|**工作階段總數** <br/> |否  <br/> |工作階段的總數，包括成功的工作階段、失敗的工作階段 (預期失敗與未預期失敗) 以及未分類的工作階段。  <br/> |
|**失敗率** <br/> |否  <br/> |失敗的點對點工作階段百分比。  <br/> |
|**依模態的會話** <br/> |否  <br/> |依模態模式分組的會話總數 (例如立即訊息) 。  <br/> |
|**依形式區分的失敗率** <br/> |否  <br/> |依形式分類 (所群組的失敗會話總數，例如立即訊息) 。  <br/> |
   

