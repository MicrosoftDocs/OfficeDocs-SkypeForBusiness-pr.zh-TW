---
title: 手動清除通話詳細資料錄製及體驗資料庫品質
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manually purging the call detail recording and Quality of Experience databases
ms:assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204812(v=OCS.15)
ms:contentKeyID: 48183859
ms.date: 07/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 979f05441bfb62c8b79c604127e23fe7b7b4909f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977035"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manually-purging-the-call-detail-recording-and-quality-of-experience-databases-in-lync-server-2013"></a><span data-ttu-id="4ccf4-102">在 Lync Server 2013 中手動清除通話詳細資料錄製和體驗的品質資料庫</span><span class="sxs-lookup"><span data-stu-id="4ccf4-102">Manually purging the call detail recording and Quality of Experience databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ccf4-103">_**主題上次修改日期：** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="4ccf4-103">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="4ccf4-104">系統管理員可以設定通話詳細資料錄製（CDR）和/或體驗品質（QoE）資料庫，自動從資料庫清除舊記錄;如果已為指定的資料庫（CDR 或 QoE）啟用清除，且資料庫中有超過指定時間的任何記錄，就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="4ccf4-104">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time.</span></span> <span data-ttu-id="4ccf4-105">例如，每日 1:00 AM 管理員可能會設定系統，讓 QoE 記錄超過60天，將會從 QoE 資料庫中刪除。</span><span class="sxs-lookup"><span data-stu-id="4ccf4-105">For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>

<span data-ttu-id="4ccf4-106">除了自動清除外，還將兩個新的 Cmdlet （CsCdrDatabasePurge 和 Invoke-CsQoEDatbasePurge）新增至 Microsoft Lync Server 2013;這些 Cmdlet 可讓系統管理員隨時手動清除 CDR 與 QoE 資料庫中的記錄。</span><span class="sxs-lookup"><span data-stu-id="4ccf4-106">In addition to that automatic purging, two new cmdlets -- Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge -- have been added to Microsoft Lync Server 2013; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="4ccf4-107">例如，若要從 CDR 資料庫手動清除所有超過10天的記錄，您可以使用類似以下的命令：</span><span class="sxs-lookup"><span data-stu-id="4ccf4-107">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

<span data-ttu-id="4ccf4-108">在上述命令中，會從 atl-sql-001.litwareinc.com 上的 [監視] 資料庫中刪除 [呼叫詳細資料記錄] 和 [超過10天的診斷資料記錄]。</span><span class="sxs-lookup"><span data-stu-id="4ccf4-108">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="4ccf4-109">（通話詳細資料記錄為使用者/會話報告。</span><span class="sxs-lookup"><span data-stu-id="4ccf4-109">(Call detail records are user/session reports.</span></span> <span data-ttu-id="4ccf4-110">診斷資料記錄是用戶端應用程式（例如 Lync 2013）上傳的診斷記錄。</span><span class="sxs-lookup"><span data-stu-id="4ccf4-110">Diagnostic data records are diagnostic logs uploaded by client applications such as Lync 2013.)</span></span>

<span data-ttu-id="4ccf4-111">如上所示，當您執行 CsCdrDatabasePurge Cmdlet 時，您必須同時包含 PurgeCallDetaiDataOlderThanDays 和 PurgeDiagnosticDataOlderThanDays 參數。</span><span class="sxs-lookup"><span data-stu-id="4ccf4-111">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="4ccf4-112">不過，這些參數不需要設定為相同的值。</span><span class="sxs-lookup"><span data-stu-id="4ccf4-112">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="4ccf4-113">例如，您可以將呼叫詳細資料記錄在10天以上的時間清除，同時將所有的診斷資料記錄保留在資料庫中。</span><span class="sxs-lookup"><span data-stu-id="4ccf4-113">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="4ccf4-114">若要這樣做，請將 PurgeCallDetailDataOlderThanDays 設定為10，並將 PurgeDiagnosticDataOlderThanDays 設定為0。</span><span class="sxs-lookup"><span data-stu-id="4ccf4-114">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="4ccf4-115">例如：</span><span class="sxs-lookup"><span data-stu-id="4ccf4-115">For example:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

<span data-ttu-id="4ccf4-116">根據預設，只要您執行 Invoke CsCdrDatabasePurge，就會看到每個必須清除的資料庫資料表都有類似這個提示：</span><span class="sxs-lookup"><span data-stu-id="4ccf4-116">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

<span data-ttu-id="4ccf4-117">在實際進行資料庫清除之前，您必須輸入 Y （是）或 A （代表 [是]）。</span><span class="sxs-lookup"><span data-stu-id="4ccf4-117">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place.</span></span> <span data-ttu-id="4ccf4-118">如果您想要取消這些確認提示，請將下列參數新增至通話結束的 CsCdrDatabasePurge：</span><span class="sxs-lookup"><span data-stu-id="4ccf4-118">If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>

    -Confirm:$False

<span data-ttu-id="4ccf4-119">例如：</span><span class="sxs-lookup"><span data-stu-id="4ccf4-119">For example:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

<span data-ttu-id="4ccf4-120">如果您這樣做，就不會顯示確認提示，而且會立即執行資料庫清除。</span><span class="sxs-lookup"><span data-stu-id="4ccf4-120">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>

<span data-ttu-id="4ccf4-121">若要清除 QoE 資料庫，請使用 CsQoEDatabasePurge Cmdlet，並指定要刪除的記錄的期限（天數）：</span><span class="sxs-lookup"><span data-stu-id="4ccf4-121">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>

    Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

</div>

<span> </span>

</div>

</div>

</div>

