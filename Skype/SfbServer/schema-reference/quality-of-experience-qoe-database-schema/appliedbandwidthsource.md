---
title: AppliedBandwidthSource 表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: AppliedBandwidthSource 表格是一種支援資料表，其中的每一項記錄都代表一種來源。
ms.openlocfilehash: 2daa4d35d11c000503fa83c79963df14886f50cd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58633467"
---
# <a name="appliedbandwidthsource-table"></a>AppliedBandwidthSource 表格
 
AppliedBandwidthSource 表格是一種支援資料表，其中的每一項記錄都代表一種來源。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |主要  <br/> |用於識別來源的唯一號碼。  <br/> |
|**AppliedBandwidthSource** <br/> |Varchar (256)   <br/> |Unique  <br/> |這是所採用的頻寬容量來源。 它說明頻寬限制來自 (，例如「原則伺服器」、「輪流伺服器」或「模態」 ) 。  <br/> |
   

