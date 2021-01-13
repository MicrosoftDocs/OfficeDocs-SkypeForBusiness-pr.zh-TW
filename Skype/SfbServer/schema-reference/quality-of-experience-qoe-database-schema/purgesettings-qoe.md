---
title: 'PurgeSettings table (QoE) '
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
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: PurgeSettings 資料表包含指定在經驗品質記錄過期時，會自動從 QoE 資料庫加以刪除的資訊。 請注意，您也可以透過執行下列命令，在商務用 Skype Server 管理命令介面中取得清除相關資訊：
ms.openlocfilehash: eef723298b04aecf633368d767623488a53ac6ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815803"
---
# <a name="purgesettings-table-qoe"></a>PurgeSettings table (QoE) 
 
PurgeSettings 資料表包含指定在經驗品質記錄過期時，會自動從 QoE 資料庫加以刪除的資訊。 請注意，您也可以透過執行下列命令，在商務用 Skype Server 管理命令介面中取得清除相關資訊：
  
```PowerShell
Get-CsQoEConfiguration
```

此表格已引進 Microsoft Lync Server 2013。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**識別碼** <br/> |int  <br/> |主要  <br/> |QoE 清除設定集的唯一識別碼。  <br/> |
|**EnablePurge** <br/> |位  <br/> ||設為 True 時 (1) Microsoft Lync Server 2013 會定期從 QoE 資料庫中清除過時的記錄。 清除動作會每天在 PurgeHour 設定中指定的時間加以執行。 若設為 False (0)，就不會從資料庫自動清除記錄。 預設值為 True。  <br/> |
|**KeepQoEDataForDays** <br/> |int  <br/> ||指定要從資料庫清除之 QoE 記錄的存留期 (以天數為單位)：若啟用清除，就會從資料庫移除舊於此值的 QoE。預設值為 60 天。  <br/> |
|**PurgeHour** <br/> |int  <br/> ||指定要執行資料庫清除的時間。時間是以 24 小時制指定，0 代表午夜 (上午 12:00)，而 23 則代表下午 11:00。請注意，您僅能指定時間的時數：允許將值設為 10 (代表上午 10:00)，但不允許設為 10:30 的 10.5 (代表上午 10:30)。預設值為 1 (上午 1:00)。指定要執行資料庫清除的時間。時間是以 24 小時制指定，0 代表午夜 (上午 12:00)，而 23 則代表下午 11:00。請注意，您僅能指定時間的時數：允許將值設為 10 (代表上午 10:00)，但不允許設為 10:30 的 10.5 (代表上午 10:30)。預設值為 1 (上午 1:00)。  <br/> |
   

