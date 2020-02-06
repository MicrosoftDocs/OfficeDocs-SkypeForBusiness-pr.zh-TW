---
title: 在商務用 Skype Server 中手動清除通話詳細資料錄製和體驗資料庫品質
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: 摘要：瞭解如何從 CDR 和商務用 Skype Server 所用的 QoE 資料庫手動清除記錄。
ms.openlocfilehash: c5d0eb31ad00d0e8636f5c151240c54df7320bbc
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41787693"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a><span data-ttu-id="1ff54-103">在商務用 Skype Server 中手動清除通話詳細資料錄製和體驗資料庫品質</span><span class="sxs-lookup"><span data-stu-id="1ff54-103">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>
 
<span data-ttu-id="1ff54-104">**摘要：** 瞭解如何從 CDR 和商務用 Skype Server 所用的 QoE 資料庫中，手動清除記錄。</span><span class="sxs-lookup"><span data-stu-id="1ff54-104">**Summary:** Learn how to manually purge records from the CDR and the QoE databases used by Skype for Business Server.</span></span>
  
<span data-ttu-id="1ff54-105">CDR 與 QoE 資料庫可以手動或自動清除記錄。</span><span class="sxs-lookup"><span data-stu-id="1ff54-105">The CDR and QoE databases can be manually or automatically purged of records.</span></span> <span data-ttu-id="1ff54-106">清除記錄可能很重要，因此資料不會變得陳舊，或需要重設起始基線的報表。</span><span class="sxs-lookup"><span data-stu-id="1ff54-106">Purging records can be important so that data doesn't become stale or when needing to reset reports from a starting baseline.</span></span>
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a><span data-ttu-id="1ff54-107">手動清除 CDR 及 QoE 資料庫中的記錄</span><span class="sxs-lookup"><span data-stu-id="1ff54-107">Manually purge records from CDR and QoE databases</span></span>

<span data-ttu-id="1ff54-108">系統管理員可以設定通話詳細資料錄製（CDR）和/或體驗品質（QoE）資料庫，自動從資料庫清除舊記錄;如果已為指定的資料庫（CDR 或 QoE）啟用清除，且資料庫中有超過指定時間的任何記錄，就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="1ff54-108">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time.</span></span> <span data-ttu-id="1ff54-109">例如，每日 1:00 AM 管理員可能會設定系統，讓 QoE 記錄超過60天，將會從 QoE 資料庫中刪除。</span><span class="sxs-lookup"><span data-stu-id="1ff54-109">For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>
  
<span data-ttu-id="1ff54-110">除了自動清除之外，兩個新的 Cmdlet &#x2014; Invoke CsCdrDatabasePurge 和 Invoke-CsQoEDatbasePurge &#x2014; 已新增至商務用 Skype Server;這些 Cmdlet 可讓系統管理員隨時手動清除 CDR 與 QoE 資料庫中的記錄。</span><span class="sxs-lookup"><span data-stu-id="1ff54-110">In addition to that automatic purging, two new cmdlets &#x2014; Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge &#x2014; have been added to Skype for Business Server; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="1ff54-111">例如，若要從 CDR 資料庫手動清除所有超過10天的記錄，您可以使用類似以下的命令：</span><span class="sxs-lookup"><span data-stu-id="1ff54-111">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

<span data-ttu-id="1ff54-112">在上述命令中，會從 atl-sql-001.litwareinc.com 上的 [監視] 資料庫中刪除 [呼叫詳細資料記錄] 和 [超過10天的診斷資料記錄]。</span><span class="sxs-lookup"><span data-stu-id="1ff54-112">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="1ff54-113">（通話詳細資料記錄為使用者/會話報告。</span><span class="sxs-lookup"><span data-stu-id="1ff54-113">(Call detail records are user/session reports.</span></span> <span data-ttu-id="1ff54-114">診斷資料記錄是用戶端應用程式（例如商務用 Skype Server）上傳的診斷記錄。</span><span class="sxs-lookup"><span data-stu-id="1ff54-114">Diagnostic data records are diagnostic logs uploaded by client applications such as Skype for Business Server.)</span></span>
  
<span data-ttu-id="1ff54-115">如上所示，當您執行 CsCdrDatabasePurge Cmdlet 時，您必須同時包含 PurgeCallDetaiDataOlderThanDays 和 PurgeDiagnosticDataOlderThanDays 參數。</span><span class="sxs-lookup"><span data-stu-id="1ff54-115">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="1ff54-116">不過，這些參數不需要設定為相同的值。</span><span class="sxs-lookup"><span data-stu-id="1ff54-116">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="1ff54-117">例如，您可以將呼叫詳細資料記錄在10天以上的時間清除，同時將所有的診斷資料記錄保留在資料庫中。</span><span class="sxs-lookup"><span data-stu-id="1ff54-117">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="1ff54-118">若要這樣做，請將 PurgeCallDetailDataOlderThanDays 設定為10，並將 PurgeDiagnosticDataOlderThanDays 設定為0。</span><span class="sxs-lookup"><span data-stu-id="1ff54-118">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="1ff54-119">例如：</span><span class="sxs-lookup"><span data-stu-id="1ff54-119">For example:</span></span>
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

<span data-ttu-id="1ff54-120">根據預設，只要您執行 Invoke CsCdrDatabasePurge，就會看到每個必須清除的資料庫資料表都有類似這個提示：</span><span class="sxs-lookup"><span data-stu-id="1ff54-120">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

<span data-ttu-id="1ff54-121">在實際進行資料庫清除之前，您必須輸入 Y （是）或 A （代表 [是]）。</span><span class="sxs-lookup"><span data-stu-id="1ff54-121">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place.</span></span> <span data-ttu-id="1ff54-122">如果您想要取消這些確認提示，請將下列參數新增至通話結束的 CsCdrDatabasePurge：</span><span class="sxs-lookup"><span data-stu-id="1ff54-122">If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>
  
```powershell
-Confirm:$False
```

<span data-ttu-id="1ff54-123">例如：</span><span class="sxs-lookup"><span data-stu-id="1ff54-123">For example:</span></span>
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

<span data-ttu-id="1ff54-124">如果您這樣做，就不會顯示確認提示，而且會立即執行資料庫清除。</span><span class="sxs-lookup"><span data-stu-id="1ff54-124">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>
  
<span data-ttu-id="1ff54-125">若要清除 QoE 資料庫，請使用 CsQoEDatabasePurge Cmdlet，並指定要刪除的記錄的期限（天數）：</span><span class="sxs-lookup"><span data-stu-id="1ff54-125">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>
  
```powershell
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


