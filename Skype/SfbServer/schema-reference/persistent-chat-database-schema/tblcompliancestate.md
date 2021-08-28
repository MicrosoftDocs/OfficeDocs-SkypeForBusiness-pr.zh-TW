---
title: tblComplianceState
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
ms.localizationpriority: medium
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState 包含集區範圍的相容性狀態資訊。
ms.openlocfilehash: c96f43c27179d5dd933aeba7f1483be3e1f7ee7e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580397"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState 包含集區範圍的相容性狀態資訊。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint，非 null  <br/> |最新處理的相容性事件的識別碼。  <br/> |
|activeServerID  <br/> |int，非 null  <br/> |在資料庫上保留獨佔鎖定之規範伺服器的識別碼，如果沒有，則為-1。  <br/> |
|lockExpirationTime  <br/> |datetime2，非 null  <br/> |如果 activeServerID 不是-1) ，則鎖定到期時間 (。  <br/> |
   

