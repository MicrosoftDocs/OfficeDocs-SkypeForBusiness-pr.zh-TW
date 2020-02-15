---
title: Lync Server 2013： 中央管理存放區複寫狀態
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
ms.openlocfilehash: d7d411733712cf274760a45cd4e315b4f02a66e0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="central-management-store-replication-status-in-lync-server-2013"></a>Lync Server 2013 中的中央管理存放區複寫狀態

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015年-01-26_

當系統管理員進行變更的某種類型的 Lync Server （例如，當系統管理員會建立新的語音原則或變更的 Address Book Server 組態設定時） 會記錄該變更中央管理存放區中。 接著，變更然後必須複寫到所有執行 Lync Server 服務或伺服器角色的電腦。

若要將資料複寫，（中央管理伺服器上執行） 主要複寫器會建立已變更的組態資料的快照集。 此快照集的複本再傳送至每個執行 Lync Server 服務或伺服器角色的電腦。 在這些電腦上的複寫代理程式接收快照集，並將已變更的資料上傳。 代理程式接著會傳送主要複寫器郵件，報告的最新的複寫狀態。

Get-csmanagementstorereplicationstatus cmdlet 可讓您確認任何 （或所有） 在組織中的 Lync Server 電腦的複寫狀態。

誰可以執行此指令程式？ 根據預設，下列群組的成員會獲授權在本機上執行 Get-csmanagementstorereplicationstatus cmdlet: RTCUniversalUserAdmins、 RTCUniversalServerAdmins。

若要傳回所有 （包括您自行建立的任何自訂 RBAC 角色） 已指派此 cmdlet 的 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

<div>

## <a name="see-also"></a>另請參閱


[Get-csmanagementstorereplicationstatus](https://docs.microsoft.com/powershell/module/skype/Get-CsManagementStoreReplicationStatus)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

