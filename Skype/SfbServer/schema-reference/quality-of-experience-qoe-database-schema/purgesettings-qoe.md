---
title: PurgeSettings table （QoE）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: PurgeSettings 資料表包含的資訊會指定是否（以及時間）系統會自動將過時的體驗記錄品質從 QoE 資料庫中刪除。 請注意，您也可以透過執行下列命令，在商務用 Skype Server Management 命令介面內取得清除相關資訊：
ms.openlocfilehash: dab1b2ffeab5882d0e459d7957b2817e780fc3a4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807330"
---
# <a name="purgesettings-table-qoe"></a>PurgeSettings table （QoE）
 
PurgeSettings 資料表包含的資訊會指定是否（以及時間）系統會自動將過時的體驗記錄品質從 QoE 資料庫中刪除。 請注意，您也可以透過執行下列命令，在商務用 Skype Server Management 命令介面內取得清除相關資訊：
  
```PowerShell
Get-CsQoEConfiguration
```

此表格是在 Microsoft Lync Server 2013 中推出。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**標識號** <br/> |int  <br/> |首選  <br/> |QoE 清除設定集合的唯一識別碼。  <br/> |
|**EnablePurge** <br/> |稍微  <br/> ||當設定為 True （1）時，Microsoft Lync Server 2013 會定期從 QoE 資料庫清除過時的記錄。 [清除] 會在每天的 PurgeHour 設定所指定的聖多美上進行。 如果設定為 False （0），則不會自動從資料庫清除記錄。 預設值為 True。  <br/> |
|**KeepQoEDataForDays** <br/> |int  <br/> ||指定將從資料庫清除的 QoE 記錄（天）期限：如果已啟用清除，則會從資料庫中移除超過此值的 QoE 記錄。 預設值為60天。  <br/> |
|**PurgeHour** <br/> |int  <br/> ||指定要在進行資料庫清除時的當地時間。 時間是以 24 小時制指定，0 代表午夜 (12:00 AM)，而 23 則代表 11:00 PM。 請注意，您只能指定一天中的小時數：值為10（表示 10:00 AM），但不允許值為 10:30 of 10.5 （表示 10:30 AM）。 預設值為1（1:00 AM）。 指定要在進行資料庫清除時的當地時間。 時間是以 24 小時制指定，0 代表午夜 (12:00 AM)，而 23 則代表 11:00 PM。 請注意，您只能指定一天中的小時數：值為10（表示 10:00 AM），但不允許值為 10:30 of 10.5 （表示 10:30 AM）。 預設值為1（1:00 AM）。  <br/> |
   

