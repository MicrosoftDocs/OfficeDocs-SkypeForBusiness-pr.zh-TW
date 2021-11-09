---
title: 商務用 Skype Server 2015 中的 IMReportSummary 表格
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: IMReportSummaryTable 會提供組織中保留之立即訊息工作階段的整體報告。 此表格已引進 Microsoft Lync Server 2013。
ms.openlocfilehash: 438b6f7e7093cba3e7f2c1d0b9a82a592128b86c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845016"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 IMReportSummary 表格
 
IMReportSummaryTable 會提供組織中保留之立即訊息工作階段的整體報告。 此表格已引進 Microsoft Lync Server 2013。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |datetime  <br/> |主要  <br/> |立即訊息工作階段開始的日期及時間。  <br/> |
|**TimePeriod** <br/> |char (1)   <br/> |主要  <br/> ||
|**PoolFQDN** <br/> |Nvarchar (257)   <br/> |主要  <br/> |裝載此工作階段之集區的完整網域名稱。  <br/> |
|**AuthType** <br/> |int  <br/> |主要  <br/> |電話的優先順序 (例如，緊急或非緊急)。 優先順序資訊會儲存在[商務用 Skype Server 2015 的 CallPriorities 表格](callpriorities.md)中。  <br/> |
|**SessionCount** <br/> |Bigint  <br/> |||
|**MsgCount** <br/> |Bigint  <br/> ||工作階段期間交換的立即訊息總數。  <br/> |
   

