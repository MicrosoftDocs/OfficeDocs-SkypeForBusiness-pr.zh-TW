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
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState 包含集區範圍的相容性狀態資訊。
ms.openlocfilehash: c9027068550b4320e1e7d170ee23b6cb6e060d6162583132f927c720c09d6ebe
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315419"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState 包含集區範圍的相容性狀態資訊。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint，非 null  <br/> |最新處理的相容性事件的識別碼。  <br/> |
|activeServerID  <br/> |int，非 null  <br/> |在資料庫上保留獨佔鎖定之規範伺服器的識別碼，如果沒有，則為-1。  <br/> |
|lockExpirationTime  <br/> |datetime2，非 null  <br/> |如果 activeServerID 不是-1) ，則鎖定到期時間 (。  <br/> |
   

