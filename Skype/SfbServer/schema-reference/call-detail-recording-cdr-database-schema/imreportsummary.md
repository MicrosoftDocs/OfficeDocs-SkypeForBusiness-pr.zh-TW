---
title: 商務用 Skype Server 2015 中的 IMReportSummary 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: IMReportSummaryTable 會提供組織中的立即訊息會話的整體報告。 此表格是在 Microsoft Lync Server 2013 中推出。
ms.openlocfilehash: 647b8dc3e48e56d126a65f524de90954b7aeca8f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192844"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 IMReportSummary 表格
 
IMReportSummaryTable 會提供組織中的立即訊息會話的整體報告。 此表格是在 Microsoft Lync Server 2013 中推出。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**開始** <br/> |datetime  <br/> |首選  <br/> |立即訊息會話開始的日期和時間。  <br/> |
|**TimePeriod** <br/> |char (1)  <br/> |首選  <br/> ||
|**PoolFQDN** <br/> |Nvarchar (257)  <br/> |首選  <br/> |主持會話之池的完整功能變數名稱。  <br/> |
|**AuthType** <br/> |int  <br/> |首選  <br/> |通話的優先順序 (例如, 緊急或非緊急)。 優先順序資訊會儲存在[商務用 Skype Server 2015 的 CallPriorities 表格](callpriorities.md)中。  <br/> |
|**SessionCount** <br/> |Bigint  <br/> |||
|**MsgCount** <br/> |Bigint  <br/> ||會話期間交換的立即訊息總數。  <br/> |
   

