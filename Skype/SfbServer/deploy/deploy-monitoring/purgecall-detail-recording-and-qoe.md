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
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a><span data-ttu-id="02a36-103">在商務用 Skype Server 中手動清除詳細通話記錄與經驗品質資料庫</span><span class="sxs-lookup"><span data-stu-id="02a36-103">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>
 
<span data-ttu-id="02a36-104">**摘要：** 瞭解如何從 CDR 和商務用 Skype Server 所使用的 QoE 資料庫，手動清除記錄。</span><span class="sxs-lookup"><span data-stu-id="02a36-104">**Summary:** Learn how to manually purge records from the CDR and the QoE databases used by Skype for Business Server.</span></span>
  
<span data-ttu-id="02a36-105">CDR 和 QoE 資料庫可以手動或自動清除記錄。</span><span class="sxs-lookup"><span data-stu-id="02a36-105">The CDR and QoE databases can be manually or automatically purged of records.</span></span> <span data-ttu-id="02a36-106">清除記錄可能很重要，所以資料不會變得陳舊，也不需要重設起始基準的報表。</span><span class="sxs-lookup"><span data-stu-id="02a36-106">Purging records can be important so that data doesn't become stale or when needing to reset reports from a starting baseline.</span></span>
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a><span data-ttu-id="02a36-107">手動清除 CDR 和 QoE 資料庫中的記錄</span><span class="sxs-lookup"><span data-stu-id="02a36-107">Manually purge records from CDR and QoE databases</span></span>

<span data-ttu-id="02a36-108">管理員可以設定詳細通話記錄 (CDR) 和/或經驗品質 (QoE) 資料庫自動清除資料庫中的舊記錄;如果已對指定的資料庫 (CDR 或 QoE) 中已啟用清除，而且如果資料庫中的任何記錄的長度超過指定的時間，便會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="02a36-108">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time.</span></span> <span data-ttu-id="02a36-109">例如，管理員可以設定系統在每天早上 1:00 從 QoE 資料庫中刪除超過 60 天的 QoE 記錄。</span><span class="sxs-lookup"><span data-stu-id="02a36-109">For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>
  
<span data-ttu-id="02a36-110">除了自動清除之外，還會將兩個新 Cmdlet &#x2014; Invoke-CsCdrDatabasePurge 和 Invoke-CsQoEDatbasePurge &#x2014; 新增至商務用 Skype Server;這些 Cmdlet 可讓系統管理員在任何時間從 CDR 和 QoE 資料庫手動清除記錄。</span><span class="sxs-lookup"><span data-stu-id="02a36-110">In addition to that automatic purging, two new cmdlets &#x2014; Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge &#x2014; have been added to Skype for Business Server; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="02a36-111">例如，如要從 CDR 資料庫中手動清除所有超過 10 天的記錄，可使用如下的命令：</span><span class="sxs-lookup"><span data-stu-id="02a36-111">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

<span data-ttu-id="02a36-112">在上述命令中，會從 atl-sql-001.litwareinc.com 上的監視資料庫刪除詳細通話記錄及超過10天的診斷資料記錄。</span><span class="sxs-lookup"><span data-stu-id="02a36-112">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="02a36-113"> (詳細通話記錄是使用者/會話報告。</span><span class="sxs-lookup"><span data-stu-id="02a36-113">(Call detail records are user/session reports.</span></span> <span data-ttu-id="02a36-114">診斷資料記錄是用戶端應用程式（例如商務用 Skype Server）上傳的診斷記錄。 ) </span><span class="sxs-lookup"><span data-stu-id="02a36-114">Diagnostic data records are diagnostic logs uploaded by client applications such as Skype for Business Server.)</span></span>
  
<span data-ttu-id="02a36-115">如上所示，執行 Invoke-CsCdrDatabasePurge Cmdlet 時，必須同時包括 PurgeCallDetaiDataOlderThanDays 及 PurgeDiagnosticDataOlderThanDays 參數。</span><span class="sxs-lookup"><span data-stu-id="02a36-115">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="02a36-116">不過，這些參數不需要設為相同的值。</span><span class="sxs-lookup"><span data-stu-id="02a36-116">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="02a36-117">例如，可以清除資料庫中超過 10 天的詳細通話記錄，但同時保留所有的診斷資料記錄。</span><span class="sxs-lookup"><span data-stu-id="02a36-117">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="02a36-118">若要這麼做，請將 PurgeCallDetailDataOlderThanDays 設定為10，並將 PurgeDiagnosticDataOlderThanDays 設定為0。</span><span class="sxs-lookup"><span data-stu-id="02a36-118">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="02a36-119">例如：</span><span class="sxs-lookup"><span data-stu-id="02a36-119">For example:</span></span>
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

<span data-ttu-id="02a36-120">依預設，每次執行 Invoke-CsCdrDatabasePurge 時，針對每個必須清除的資料庫都會出現類似以下的提示：</span><span class="sxs-lookup"><span data-stu-id="02a36-120">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

<span data-ttu-id="02a36-p106">您必須輸入 Y (是) 或 A (全部皆是)，才會實際清除資料庫。如要隱藏這些確認提示，請在呼叫 Invoke-CsCdrDatabasePurge 的結尾新增下列參數：</span><span class="sxs-lookup"><span data-stu-id="02a36-p106">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place. If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>
  
```powershell
-Confirm:$False
```

<span data-ttu-id="02a36-123">例如：</span><span class="sxs-lookup"><span data-stu-id="02a36-123">For example:</span></span>
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

<span data-ttu-id="02a36-124">如此做之後，確認提示就不會顯示，將立即清除資料庫。</span><span class="sxs-lookup"><span data-stu-id="02a36-124">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>
  
<span data-ttu-id="02a36-125">如要清除 QoE 資料庫，則使用 Invoke-CsQoEDatabasePurge Cmdlet，並且指定要刪除之記錄的年齡 (天數)：</span><span class="sxs-lookup"><span data-stu-id="02a36-125">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>
  
```powershell
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


