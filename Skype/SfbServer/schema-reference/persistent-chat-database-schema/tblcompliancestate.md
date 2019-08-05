---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState 包含全池相容性狀態資訊。
ms.openlocfilehash: 1c5571d7150c3859978f8d217f0264f67ee993d5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192746"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState 包含全池相容性狀態資訊。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |Bigint, not null  <br/> |最新處理的相容性事件識別碼。  <br/> |
|activeServerID  <br/> |int, not null  <br/> |在資料庫上保留獨佔鎖的規範伺服器識別碼, 或者如果沒有, 則為-1。  <br/> |
|lockExpirationTime  <br/> |datetime2, not null  <br/> |鎖定到期時間 (如果 activeServerID 不是-1)。  <br/> |
   

