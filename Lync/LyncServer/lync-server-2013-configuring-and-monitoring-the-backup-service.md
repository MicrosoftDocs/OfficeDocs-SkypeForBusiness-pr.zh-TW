---
title: Lync Server 2013：設定及監視備份服務
description: Lync Server 2013：設定及監視備份服務。
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
ms.openlocfilehash: 35302aeb430e8591babd88969d4c5c158c1ac0bf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574639"
---
# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a>在 Lync Server 2013 中設定及監視備份服務

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

您可以使用下列 Lync Server 管理命令介面命令來設定及監視備份服務。

<div>


> [!NOTE]  
> 根據預設，RTCUniversalServerAdmins 群組是具有執行 <STRONG>Get-CsBackupServiceStatus</STRONG> 許可權的唯一群組。 若要使用此 Cmdlet，請以此群組的成員身分登入。 或者，您可以將此命令的存取權授與其他群組 (例如，使用 <STRONG>Set-CsBackupServiceConfiguration</STRONG> 指令程式 CSAdministrator) 。



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

例如，下列會將間隔設定為3分鐘。

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> 雖然您可以使用此 Cmdlet 變更備份服務的預設同步處理間隔，但除非完全必要，否則不應這麼做，因為同步處理間隔對備份服務效能具有極大的影響，而且復原點目標 (RPO) 。



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>取得特定集區的備份服務狀態

執行下列 Cmdlet：

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> 備份服務同步處理狀態是從 (P1) 集區 unidirectionally 至其備份組區 (P2) 所定義。 從 P1 到 P2 的同步處理狀態可能不同于從 P2 到 P1 的狀態。 若為 P1，當 P1 中所做的所有變更都會在同步處理間隔內完全複寫至 P2 時，備份服務處於「穩定」狀態。 如果沒有其他要從 P1 同步處理的變更，則為 "final" 狀態。 這兩種狀態都會指出執行 Cmdlet 時備份服務的快照。 這並不表示傳回的狀態會在此後保留。 特別是，當執行 Cmdlet 後，如果 P1 不會產生任何變更，則 "final" 狀態會繼續保留。 當 p1 成為 <STRONG>CsPoolfailover</STRONG> 執行邏輯的一部分時，p1 被置於唯讀模式後，就會發生失敗的情況。



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>若要取得特定集區之備份關係的相關資訊

執行下列 Cmdlet：

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a>強制執行備份服務同步處理

執行下列 Cmdlet：

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

