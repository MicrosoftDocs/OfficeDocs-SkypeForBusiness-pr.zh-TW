---
title: 商務用 Skype Server 2015 中的 IMReportSummary 表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: IMReportSummaryTable 會提供組織中保留之立即訊息工作階段的整體報告。 此表格已引進 Microsoft Lync Server 2013。
ms.openlocfilehash: 204aeb21037f69eb34c2e12ee642d2ed6495111f8ae68d8c8f3786eb49a957fa
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341718"
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
   

