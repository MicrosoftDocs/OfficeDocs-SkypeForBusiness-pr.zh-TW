---
title: 手動清除詳細通話記錄及經驗品質資料庫
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
ms.openlocfilehash: f14485465e44b089e5002a04d3ed5e5a392ad4d8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "41991858"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manually-purging-the-call-detail-recording-and-quality-of-experience-databases-in-lync-server-2013"></a>手動清除詳細通話記錄及 Lync Server 2013 中的經驗品質資料庫

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-07-07_

系統管理員可以設定詳細通話記錄 (CDR) 和/或經驗品質 (QoE) 資料庫會自動從資料庫; 清除舊的記錄會發生這種情況是如果清除已啟用指定的資料庫 （CDR 或 QoE），而且如果有任何已超過指定的時間量資料庫中的記錄。 例如，管理員可以設定系統在每天早上 1:00 從 QoE 資料庫中刪除超過 60 天的 QoE 記錄。

除了自動清除，兩個新的 cmdlet-Invoke-cscdrdatabasepurge 和 Invoke CsQoEDatbasePurge--已新增至 Microsoft Lync Server 2013;這些 cmdlet 可讓系統管理員可以隨時手動清除 CDR 和 QoE 資料庫的記錄。 例如，如要從 CDR 資料庫中手動清除所有超過 10 天的記錄，可使用如下的命令：

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

在上述命令中同時通話詳細記錄及診斷資料記錄較 10 天將從 atl-cs-001.litwareinc.com-sql-001.litwareinc.com 的監控資料庫中刪除。 （詳細通話記錄是使用者/工作階段的報告。 診斷資料記錄是由用戶端應用程式，例如 Lync 2013 上傳的診斷記錄。）

如上所示，執行 Invoke-CsCdrDatabasePurge Cmdlet 時，必須同時包括 PurgeCallDetaiDataOlderThanDays 及 PurgeDiagnosticDataOlderThanDays 參數。 不過，這些參數不需要設為相同的值。 例如，可以清除資料庫中超過 10 天的詳細通話記錄，但同時保留所有的診斷資料記錄。 若要這麼做，請設定為 10 和 PurgeDiagnosticDataOlderThanDays PurgeCallDetailDataOlderThanDays 設為 0。 例如：

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

依預設，每次執行 Invoke-CsCdrDatabasePurge 時，針對每個必須清除的資料庫都會出現類似以下的提示：

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

您必須輸入 Y (是) 或 A (全部皆是)，才會實際清除資料庫。如要隱藏這些確認提示，請在呼叫 Invoke-CsCdrDatabasePurge 的結尾新增下列參數：

    -Confirm:$False

例如：

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

如此做之後，確認提示就不會顯示，將立即清除資料庫。

如要清除 QoE 資料庫，則使用 Invoke-CsQoEDatabasePurge Cmdlet，並且指定要刪除之記錄的年齡 (天數)：

    Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

</div>

<span> </span>

</div>

</div>

</div>

