---
title: Lync Server 2013：設定和監控備份服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and monitoring the Backup Service
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205252(v=OCS.15)
ms:contentKeyID: 48185365
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9992f0466ceb2e01fa54cb2b2d511eeb96af755a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a>在 Lync Server 2013 中設定和監控備份服務

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

您可以使用下列 Lync Server 管理命令介面命令來設定及監視備份服務。

<div>


> [!NOTE]  
> RTCUniversalServerAdmins 群組是唯一具有執行<STRONG>CsBackupServiceStatus</STRONG>預設許可權的群組。 若要使用這個 Cmdlet，請以這個群組的成員身分登入。 或者，您可以使用<STRONG>CsBackupServiceConfiguration</STRONG> Cmdlet，將此命令的存取權授與其他群組（例如，CSAdministrator）。



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a>若要查看備份服務設定

執行下列 Cmdlet：

    Get-CsBackupServiceConfiguration

SyncInterval 的預設值是兩分鐘。

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a>設定備份服務同步處理間隔

執行下列 Cmdlet：

    Set-CsBackupServiceConfiguration -SyncInterval interval

例如，下列會將間隔設定為三分鐘。

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> 雖然您可以使用這個 Cmdlet 來變更備份服務的預設同步處理間隔，但除非是絕對必要，否則您不應該這麼做，因為同步處理間隔對備份服務效能和復原點目標（RPO）有很大的影響。



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>取得特定文件庫的備份服務狀態

執行下列 Cmdlet：

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> 備份服務同步處理狀態是從池（P1）定義 unidirectionally 到其備份池（P2）。 從 P1 到 P2 的同步處理狀態，可能與 P2 與 P1 不同。 針對 P1 到 P2，如果在 P1 中所做的所有變更都會在同步處理間隔內完全複製到 P2，則備份服務處於「穩定」狀態。 如果沒有其他變更要從 P1 同步處理到 P2，則會處於 [最終] 狀態。 這兩種狀態表示執行 Cmdlet 時備份服務的快照。 這並不表示傳回的狀態將會持續保持不變。 特別是，只有在執行 Cmdlet 之後，P1 不會產生任何變更時，才會繼續保留 [最終] 狀態。 在 P1 成為<STRONG>CsPoolfailover</STRONG>執行邏輯的一部分之後，p1 被置於唯讀模式之後，就會發生失敗情況。



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>若要取得特定資源庫之備份關聯的相關資訊

執行下列 Cmdlet：

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a>強制備份服務同步處理

執行下列 Cmdlet：

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

