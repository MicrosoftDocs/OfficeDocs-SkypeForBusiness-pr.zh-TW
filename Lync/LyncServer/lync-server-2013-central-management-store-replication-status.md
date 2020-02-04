---
title: Lync Server 2013：一般管理存放區覆寫狀態
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central management store replication status
ms:assetid: f514f88d-986b-4e45-b79b-e04a7616c1fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720926(v=OCS.15)
ms:contentKeyID: 63969663
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4212e8616916f6a2a256530a7a0b74c9811f166d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736853"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="central-management-store-replication-status-in-lync-server-2013"></a>Lync Server 2013 中的一般管理存放區覆寫狀態

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-01-26_

當系統管理員將某種類型變更為 Lync Server 時（例如，當系統管理員建立新的語音原則，或變更 [通訊錄服務器] 配置設定）時，這些變更會記錄在中央管理儲存區中。 接著，必須將變更複製到所有執行 Lync Server 服務或伺服器角色的電腦上。

若要複製資料，主要複製器（在中央管理伺服器上執行）會建立變更之設定資料的快照。 然後，會將此快照的複本傳送給執行 Lync Server 服務或伺服器角色的每個電腦。 在這些電腦上，複製代理程式會接收快照，並上傳已變更的資料。 然後，agent 就會傳送一封郵件的主複製器，報告最新的複製狀態。

CsManagementStoreReplicationStatus Cmdlet 可讓您確認貴組織中所有（或所有） Lync Server 電腦的複製狀態。

誰可以執行這個 Cmdlet？ 根據預設，下列群組的成員有權在本機執行 CsManagementStoreReplicationStatus Cmdlet： RTCUniversalUserAdmins、RTCUniversalServerAdmins。

若要傳回這個 Cmdlet 所指派的所有 RBAC 角色清單（包括您自行建立的任何自訂 RBAC 角色），請在 Windows PowerShell 提示中執行下列命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

<div>

## <a name="see-also"></a>請參閱


[CsManagementStoreReplicationStatus](https://docs.microsoft.com/powershell/module/skype/Get-CsManagementStoreReplicationStatus)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

