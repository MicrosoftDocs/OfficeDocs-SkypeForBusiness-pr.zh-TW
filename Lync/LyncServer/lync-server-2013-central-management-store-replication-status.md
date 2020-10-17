---
title: Lync Server 2013：中央管理存放區複寫狀態
description: Lync Server 2013：中央管理存放區複寫狀態。
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
ms.openlocfilehash: 5f1f9008a966040cf34ac0499c023f9dbe53a541
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544359"
---
# <a name="central-management-store-replication-status-in-lync-server-2013"></a>Lync Server 2013 中的中央管理存放區複寫狀態

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-01-26_

當系統管理員對 Lync Server 進行某些類型的變更時 (例如，當系統管理員建立新的語音原則或變更通訊錄服務器設定設定時) 該變更會記錄在中央管理存放區中。 接著，必須將變更複寫至所有執行 Lync Server 服務或伺服器角色的電腦。

若要複製資料，在中央管理伺服器上執行的主複製器 () 會建立已變更之設定資料的快照。 然後將此快照的複本傳送給執行 Lync Server 服務或伺服器角色的每一部電腦。 在那些電腦上，複寫代理程式會接收快照，並上傳已變更的資料。 然後，代理人會傳送主複寫器一封郵件，報告最近的複寫狀態。

Get-CsManagementStoreReplicationStatus Cmdlet 可讓您確認組織中任何 (或所有) 的 Lync Server 電腦的複寫狀態。

誰可以執行此 Cmdlet？ 根據預設，下列群組的成員有權在本機執行 Get-CsManagementStoreReplicationStatus Cmdlet： RTCUniversalUserAdmins、RTCUniversalServerAdmins。

若要傳回此 Cmdlet 所指派的所有 RBAC 角色清單 (包含您自行建立的自訂 RBAC 角色) ，請從 Windows PowerShell 提示中執行下列命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

<div>

## <a name="see-also"></a>另請參閱


[Get-CsManagementStoreReplicationStatus](https://docs.microsoft.com/powershell/module/skype/Get-CsManagementStoreReplicationStatus)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

