---
title: PurgeSettings 資料表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: 'PurgeSettings 資料表包含的資訊可指定是否會自動從 CDR 資料庫中刪除過時的呼叫詳細資料記錄。 請注意, 您也可以透過執行下列命令, 在商務用 Skype Server 2015 中取得清除相關資訊:'
ms.openlocfilehash: 6aac92555dda6875f23a177bb09384f453369846
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192811"
---
# <a name="purgesettings-table"></a>PurgeSettings 資料表
 
PurgeSettings 資料表包含的資訊可指定是否會自動從 CDR 資料庫中刪除過時的呼叫詳細資料記錄。 請注意, 您也可以透過執行下列命令, 在商務用 Skype Server 2015 中取得清除相關資訊:
  
```
Get-CsCdrConfiguration
```

系統管理員應該將 PurgeSettings 資料表視為唯讀: 只有使用[新的-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)或[Set CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) Cmdlet, 才能對通話詳細資料清除設定進行變更。
  
此表格是在 Microsoft Lync Server 2013 中推出。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**標識號** <br/> |int  <br/> |首選  <br/> |CDR 清除設定集合的唯一識別碼。  <br/> |
|**EnablePurge** <br/> |稍微  <br/> ||當設定為 True (1) 商務用 Skype Server 2015 時, 會定期從 CDR 資料庫清除過時的記錄。 [清除] 會在每天的 PurgeHour 設定所指定的聖多美上進行。 如果設定為 False (0), 則不會自動從資料庫清除記錄。 預設值為 True。  <br/> |
|**KeepCallDetailForDays** <br/> |int  <br/> ||指定將從資料庫清除的 CDR 記錄 (天數) 的存留期: 如果已啟用清除, 則早于此值的 CDR 記錄將會從資料庫中移除。 預設值為60天。  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||指定將從資料庫清除的錯誤報表記錄 (天數) 的存留期: 如果已啟用清除, 則超過此值的錯誤報表記錄將會從資料庫中移除。 預設值為60天。  <br/> |
|**PurgeHour** <br/> |int  <br/> ||指定要在進行資料庫清除時的當地時間。 時間是以 24 小時制指定，0 代表午夜 (12:00 AM)，而 23 則代表 11:00 PM。 請注意, 您只能指定一天中的小時數: 值為 10 (表示 10:00 AM), 但不允許值為 10:30 of 10.5 (表示 10:30 AM)。 預設值為 2 (2:00 AM)。  <br/> |
   

