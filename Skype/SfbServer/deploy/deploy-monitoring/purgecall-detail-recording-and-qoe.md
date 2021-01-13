---
title: 在商務用 Skype Server 中手動清除詳細通話記錄與經驗品質資料庫
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: 摘要：瞭解如何從 CDR 和商務用 Skype Server 所使用的 QoE 資料庫，手動清除記錄。
ms.openlocfilehash: 2d36af2d06b6d6951e436ea456d4036478278600
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802143"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a>在商務用 Skype Server 中手動清除詳細通話記錄與經驗品質資料庫
 
**摘要：** 瞭解如何從 CDR 和商務用 Skype Server 所使用的 QoE 資料庫，手動清除記錄。
  
CDR 和 QoE 資料庫可以手動或自動清除記錄。 清除記錄可能很重要，所以資料不會變得陳舊，也不需要重設起始基準的報表。
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a>手動清除 CDR 和 QoE 資料庫中的記錄

管理員可以設定詳細通話記錄 (CDR) 和/或經驗品質 (QoE) 資料庫自動清除資料庫中的舊記錄;如果已對指定的資料庫 (CDR 或 QoE) 中已啟用清除，而且如果資料庫中的任何記錄的長度超過指定的時間，便會發生這種情況。 例如，管理員可以設定系統在每天早上 1:00 從 QoE 資料庫中刪除超過 60 天的 QoE 記錄。
  
除了自動清除之外，還會將兩個新 Cmdlet &#x2014; Invoke-CsCdrDatabasePurge 和 Invoke-CsQoEDatbasePurge &#x2014; 新增至商務用 Skype Server;這些 Cmdlet 可讓系統管理員在任何時間從 CDR 和 QoE 資料庫手動清除記錄。 例如，如要從 CDR 資料庫中手動清除所有超過 10 天的記錄，可使用如下的命令：
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

在上述命令中，會從 atl-sql-001.litwareinc.com 上的監視資料庫刪除詳細通話記錄及超過10天的診斷資料記錄。  (詳細通話記錄是使用者/會話報告。 診斷資料記錄是用戶端應用程式（例如商務用 Skype Server）上傳的診斷記錄。 ) 
  
如上所示，執行 Invoke-CsCdrDatabasePurge Cmdlet 時，必須同時包括 PurgeCallDetaiDataOlderThanDays 及 PurgeDiagnosticDataOlderThanDays 參數。 不過，這些參數不需要設為相同的值。 例如，可以清除資料庫中超過 10 天的詳細通話記錄，但同時保留所有的診斷資料記錄。 若要這麼做，請將 PurgeCallDetailDataOlderThanDays 設定為10，並將 PurgeDiagnosticDataOlderThanDays 設定為0。 例如：
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

依預設，每次執行 Invoke-CsCdrDatabasePurge 時，針對每個必須清除的資料庫都會出現類似以下的提示：
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

您必須輸入 Y (是) 或 A (全部皆是)，才會實際清除資料庫。如要隱藏這些確認提示，請在呼叫 Invoke-CsCdrDatabasePurge 的結尾新增下列參數：
  
```powershell
-Confirm:$False
```

例如：
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

如此做之後，確認提示就不會顯示，將立即清除資料庫。
  
如要清除 QoE 資料庫，則使用 Invoke-CsQoEDatabasePurge Cmdlet，並且指定要刪除之記錄的年齡 (天數)：
  
```powershell
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


