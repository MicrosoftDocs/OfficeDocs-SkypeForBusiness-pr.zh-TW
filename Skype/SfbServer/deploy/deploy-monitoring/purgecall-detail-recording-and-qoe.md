---
title: 在商務用 Skype Server 中手動清除通話詳細資料錄製和體驗資料庫品質
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: '摘要: 瞭解如何從 CDR 和商務用 Skype Server 所用的 QoE 資料庫手動清除記錄。'
ms.openlocfilehash: ba87e05dd72e5da22cfe4e01cd68be1a9fac6242
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239874"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a>在商務用 Skype Server 中手動清除通話詳細資料錄製和體驗資料庫品質
 
**摘要:** 瞭解如何從 CDR 和商務用 Skype Server 所用的 QoE 資料庫中, 手動清除記錄。
  
CDR 與 QoE 資料庫可以手動或自動清除記錄。 清除記錄可能很重要, 因此資料不會變得陳舊, 或需要重設起始基線的報表。
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a>手動清除 CDR 及 QoE 資料庫中的記錄

系統管理員可以設定通話詳細資料錄製 (CDR) 和/或體驗品質 (QoE) 資料庫, 自動從資料庫清除舊記錄;如果已為指定的資料庫 (CDR 或 QoE) 啟用清除, 且資料庫中有超過指定時間的任何記錄, 就會發生這種情況。 例如, 每日 1:00 AM 管理員可能會設定系統, 讓 QoE 記錄超過60天, 將會從 QoE 資料庫中刪除。
  
除了自動清除之外, 兩個新的 Cmdlet &#x2014; Invoke CsCdrDatabasePurge 和 Invoke-CsQoEDatbasePurge &#x2014; 已新增至商務用 Skype Server;這些 Cmdlet 可讓系統管理員隨時手動清除 CDR 與 QoE 資料庫中的記錄。 例如, 若要從 CDR 資料庫手動清除所有超過10天的記錄, 您可以使用類似以下的命令:
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

在上述命令中, 會從 atl-sql-001.litwareinc.com 上的 [監視] 資料庫中刪除 [呼叫詳細資料記錄] 和 [超過10天的診斷資料記錄]。 (通話詳細資料記錄為使用者/會話報告。 診斷資料記錄是用戶端應用程式 (例如商務用 Skype Server) 上傳的診斷記錄。
  
如上所示, 當您執行 CsCdrDatabasePurge Cmdlet 時, 您必須同時包含 PurgeCallDetaiDataOlderThanDays 和 PurgeDiagnosticDataOlderThanDays 參數。 不過, 這些參數不需要設定為相同的值。 例如, 您可以將呼叫詳細資料記錄在10天以上的時間清除, 同時將所有的診斷資料記錄保留在資料庫中。 若要這樣做, 請將 PurgeCallDetailDataOlderThanDays 設定為 10, 並將 PurgeDiagnosticDataOlderThanDays 設定為0。 例如：
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

根據預設, 只要您執行 Invoke CsCdrDatabasePurge, 就會看到每個必須清除的資料庫資料表都有類似這個提示:
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

在實際進行資料庫清除之前, 您必須輸入 Y (是) 或 A (代表 [是])。 如果您想要取消這些確認提示, 請將下列參數新增至通話結束的 CsCdrDatabasePurge:
  
```
-Confirm:$False
```

例如：
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

如果您這樣做, 就不會顯示確認提示, 而且會立即執行資料庫清除。
  
若要清除 QoE 資料庫, 請使用 CsQoEDatabasePurge Cmdlet, 並指定要刪除的記錄的期限 (天數):
  
```
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


