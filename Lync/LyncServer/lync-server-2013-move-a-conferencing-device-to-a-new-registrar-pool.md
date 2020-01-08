---
title: Lync Server 2013：將會議裝置移至新的註冊機構池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move a conferencing device to a new Registrar pool
ms:assetid: 26e02ca3-e881-4f90-8bf0-b13649108100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994025(v=OCS.15)
ms:contentKeyID: 51803934
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7cf8b9e9fefc8dee60392a122d127e87d011446
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-conferencing-device-to-a-new-registrar-pool-in-lync-server-2013"></a>在 Lync Server 2013 中將會議裝置移至新的註冊機構池

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-20_

使用**CsMeetingRoom** Cmdlet，將會議裝置從一個註冊機構池移至另一個。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。

<div>


> [!NOTE]  
> 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。



</div>

<div>


<div>

## <a name="moving-a-conferencing-device-to-a-new-registrar-pool"></a>將會議裝置移至新的註冊機構池

  - 若要移動會議裝置，您必須指定要移動的聊天室身分識別，然後將目標參數設定為裝置將會移至的註冊機構池的完整功能變數名稱（FQDN）。 例如：
    
        Move-CsMeetingRoom -Target "atl-cs-001.litwareinc.com" -Identity "Room 14"

</div>

如需詳細資訊，請參閱[移動流覽 CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Move-CsMeetingRoom) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

