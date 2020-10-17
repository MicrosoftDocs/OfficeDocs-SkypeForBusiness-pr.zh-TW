---
title: 手動清除詳細通話記錄與經驗品質資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manually purging the call detail recording and Quality of Experience databases
ms:assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204812(v=OCS.15)
ms:contentKeyID: 48183859
ms.date: 07/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b34b3a0dd79651ef288740243313d58482959e4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524780"
---
# <a name="manually-purging-the-call-detail-recording-and-quality-of-experience-databases-in-lync-server-2013"></a><span data-ttu-id="9e170-102">在 Lync Server 2013 中手動清除詳細通話記錄與經驗品質資料庫</span><span class="sxs-lookup"><span data-stu-id="9e170-102">Manually purging the call detail recording and Quality of Experience databases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e170-103">_**主題上次修改日期：** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="9e170-103">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="9e170-104">管理員可以設定詳細通話記錄 (CDR) 和/或經驗品質 (QoE) 資料庫自動清除資料庫中的舊記錄;如果已對指定的資料庫 (CDR 或 QoE) 中已啟用清除，而且如果資料庫中的任何記錄的長度超過指定的時間，便會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="9e170-104">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time.</span></span> <span data-ttu-id="9e170-105">例如，管理員可以設定系統在每天早上 1:00 從 QoE 資料庫中刪除超過 60 天的 QoE 記錄。</span><span class="sxs-lookup"><span data-stu-id="9e170-105">For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>

<span data-ttu-id="9e170-106">除了自動清除之外，還會將兩個新的 Cmdlet （Invoke-CsCdrDatabasePurge 和 Invoke-CsQoEDatbasePurge）新增至 Microsoft Lync Server 2013;這些 Cmdlet 可讓系統管理員在任何時間從 CDR 和 QoE 資料庫手動清除記錄。</span><span class="sxs-lookup"><span data-stu-id="9e170-106">In addition to that automatic purging, two new cmdlets -- Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge -- have been added to Microsoft Lync Server 2013; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="9e170-107">例如，如要從 CDR 資料庫中手動清除所有超過 10 天的記錄，可使用如下的命令：</span><span class="sxs-lookup"><span data-stu-id="9e170-107">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

<span data-ttu-id="9e170-108">在上述命令中，會從 atl-sql-001.litwareinc.com 上的監視資料庫刪除詳細通話記錄及超過10天的診斷資料記錄。</span><span class="sxs-lookup"><span data-stu-id="9e170-108">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="9e170-109"> (詳細通話記錄是使用者/會話報告。</span><span class="sxs-lookup"><span data-stu-id="9e170-109">(Call detail records are user/session reports.</span></span> <span data-ttu-id="9e170-110">診斷資料記錄是用戶端應用程式（如 Lync 2013）上傳的診斷記錄。 ) </span><span class="sxs-lookup"><span data-stu-id="9e170-110">Diagnostic data records are diagnostic logs uploaded by client applications such as Lync 2013.)</span></span>

<span data-ttu-id="9e170-111">如上所示，執行 Invoke-CsCdrDatabasePurge Cmdlet 時，必須同時包括 PurgeCallDetaiDataOlderThanDays 及 PurgeDiagnosticDataOlderThanDays 參數。</span><span class="sxs-lookup"><span data-stu-id="9e170-111">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="9e170-112">不過，這些參數不需要設為相同的值。</span><span class="sxs-lookup"><span data-stu-id="9e170-112">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="9e170-113">例如，可以清除資料庫中超過 10 天的詳細通話記錄，但同時保留所有的診斷資料記錄。</span><span class="sxs-lookup"><span data-stu-id="9e170-113">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="9e170-114">若要這麼做，請將 PurgeCallDetailDataOlderThanDays 設定為10，並將 PurgeDiagnosticDataOlderThanDays 設定為0。</span><span class="sxs-lookup"><span data-stu-id="9e170-114">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="9e170-115">例如：</span><span class="sxs-lookup"><span data-stu-id="9e170-115">For example:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

<span data-ttu-id="9e170-116">依預設，每次執行 Invoke-CsCdrDatabasePurge 時，針對每個必須清除的資料庫都會出現類似以下的提示：</span><span class="sxs-lookup"><span data-stu-id="9e170-116">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

<span data-ttu-id="9e170-p105">您必須輸入 Y (是) 或 A (全部皆是)，才會實際清除資料庫。如要隱藏這些確認提示，請在呼叫 Invoke-CsCdrDatabasePurge 的結尾新增下列參數：</span><span class="sxs-lookup"><span data-stu-id="9e170-p105">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place. If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>

    -Confirm:$False

<span data-ttu-id="9e170-119">例如：</span><span class="sxs-lookup"><span data-stu-id="9e170-119">For example:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

<span data-ttu-id="9e170-120">如此做之後，確認提示就不會顯示，將立即清除資料庫。</span><span class="sxs-lookup"><span data-stu-id="9e170-120">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>

<span data-ttu-id="9e170-121">如要清除 QoE 資料庫，則使用 Invoke-CsQoEDatabasePurge Cmdlet，並且指定要刪除之記錄的年齡 (天數)：</span><span class="sxs-lookup"><span data-stu-id="9e170-121">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>

    Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

</div>

<span> </span>

</div>

</div>

</div>

