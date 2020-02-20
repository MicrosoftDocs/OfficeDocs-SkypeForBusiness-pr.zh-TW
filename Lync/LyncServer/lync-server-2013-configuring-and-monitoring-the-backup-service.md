---
title: Lync Server 2013： 設定和監控備份服務
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
ms.openlocfilehash: 65fbbf4db9e15eac2d29fcde6bd126355c794a95
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a>設定和監控 Lync Server 2013 中備份服務

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-01_

您可以使用下列的 Lync Server 管理命令介面命令來設定和監控備份服務。

<div>


> [!NOTE]  
> 以 RTCUniversalServerAdmins 群組是具有執行<STRONG>Get-csbackupservicestatus</STRONG>預設權限的唯一群組。 若要使用此指令程式，此群組的成員身分登入。 或者，您可以存取權授與此命令 (例如，CSAdministrator) 的其他群組使用<STRONG>Set-csbackupserviceconfiguration</STRONG> cmdlet。



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a>若要查看備份服務組態

執行下列 Cmdlet：

    Get-CsBackupServiceConfiguration

SyncInterval 的預設值為 2 分鐘。

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a>若要設定的備份服務同步處理間隔

執行下列 Cmdlet：

    Set-CsBackupServiceConfiguration -SyncInterval interval

例如，下列設定的間隔為 3 分鐘。

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> 雖然您可以使用此 cmdlet 變更備份服務的預設同步間隔，您不應執行因此若非絕對必要，因為同步間隔具有極大影響備份服務的效能和復原點目標 (RPO)。



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>若要取得特定集區的備份服務狀態

執行下列 Cmdlet：

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> 備份服務同步處理的狀態定義 unidirectionally 從集區 (P1) 至其備份集區 (P2)。 可以不同於另一條從 P2 到 P1 P2 從 P1 同步處理狀態。 P1 至 P2，備份服務處於 「 穩定 」 狀態如果所有 P1 所做的變更會完全透過都複寫至 P2 內的同步處理間隔。 它是在 「 最終 」 狀態有必須從 P1 同步處理至 P2 沒有更多的變更。 這兩種狀態指出備份服務的快照集在執行指令程式時的時間。 並不表示傳回的狀態會保持為先。 特別是，「 最終 」 狀態會繼續保留如果 P1 不會產生任何變更之後執行指令程式。 這是在容錯 P1 移轉，至 P2 P1 一部分<STRONG>Invoke-cspoolfailover</STRONG>執行邏輯放入唯讀模式之後的情況下，則為 true。



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>若要取得特定集區的備份關係的相關資訊

執行下列 Cmdlet：

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a>若要強制備份服務同步處理

執行下列 Cmdlet：

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

