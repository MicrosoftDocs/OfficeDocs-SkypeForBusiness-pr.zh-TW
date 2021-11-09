---
title: PurgeSettings 表格
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: PurgeSettings 表包含的資訊可指定是否 (和何時會自動從 CDR 資料庫中刪除) 過期的詳細通話記錄。 請執行下列命令，請注意，也可以從商務用 Skype Server 2015 中取得清除相關資訊：
ms.openlocfilehash: 119c357ed9b0f3da456d34899c8fb9bd7007a375
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859820"
---
# <a name="purgesettings-table"></a>PurgeSettings 表格
 
PurgeSettings 表包含的資訊可指定是否 (和何時會自動從 CDR 資料庫中刪除) 過期的詳細通話記錄。 請執行下列命令，請注意，也可以從商務用 Skype Server 2015 中取得清除相關資訊：
  
```PowerShell
Get-CsCdrConfiguration
```

管理員應該將 PurgeSettings 表格視為唯讀：只有在使用 [新的-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) 或 [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) Cmdlet 時，才應進行通話詳細資料清除設定的變更。
  
此表格已引進 Microsoft Lync Server 2013。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**Id** <br/> |int  <br/> |主要  <br/> |CDR 清除設定集合的唯一識別碼。  <br/> |
|**EnablePurge** <br/> |位  <br/> ||設為 True 時 (1) 商務用 Skype Server 2015 會定期從 CDR 資料庫清除過時的記錄。 清除動作會每天在 PurgeHour 設定中指定的時間加以執行。 若設為 False (0)，就不會從資料庫自動清除記錄。 預設值為 True。  <br/> |
|**KeepCallDetailForDays** <br/> |int  <br/> ||會指定要從資料庫中清除之 CDR 記錄的保留天數)  (：如果啟用清除，則舊于此值以上的 CDR 記錄會從資料庫中移除。 預設值為 60 天。  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||指定要從資料庫中清除的錯誤報表記錄 (天數) ：若啟用清除功能，則會從資料庫中移除比此值還舊的錯誤報表記錄。 預設值為 60 天。  <br/> |
|**PurgeHour** <br/> |int  <br/> ||指定要執行資料庫清除的時間。 時間是以 24 小時制指定，0 代表午夜 (上午 12:00)，而 23 則代表下午 11:00。 請注意，您僅能指定時間的時數：允許將值設為 10 (代表上午 10:00)，但不允許設為 10:30 的 10.5 (代表上午 10:30)。 預設值為 2 (2:00 AM)。  <br/> |
