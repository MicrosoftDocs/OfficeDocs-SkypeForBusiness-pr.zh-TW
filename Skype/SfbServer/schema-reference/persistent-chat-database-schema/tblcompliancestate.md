---
title: tblComplianceState
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState 包含集區範圍的相容性狀態資訊。
ms.openlocfilehash: 627632625e5898557d650009974fe709ff00e35d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398637"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState 包含集區範圍的相容性狀態資訊。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint，非 null  <br/> |最新處理的相容性事件的識別碼。  <br/> |
|activeServerID  <br/> |int，非 null  <br/> |在資料庫上保留獨佔鎖定之規範伺服器的識別碼，如果沒有，則為-1。  <br/> |
|lockExpirationTime  <br/> |datetime2，非 null  <br/> |如果 activeServerID 不是-1) ，則鎖定到期時間 (。  <br/> |
   

