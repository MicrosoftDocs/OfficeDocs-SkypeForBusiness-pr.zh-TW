---
title: 驗證內部伺服器和 Edge Server 之間的連線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify connectivity between internal servers and Edge Servers
ms:assetid: 219f706e-2b8a-46c5-b394-c384240eef50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398292(v=OCS.15)
ms:contentKeyID: 48183602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e3868462036312be97484e41c69b51ae022b57c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975119"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-between-internal-servers-and-edge-servers-in-lync-server-2013"></a>在 Lync Server 2013 中驗證內部伺服器和 Edge Server 之間的連線

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

在 Lync Server 2013 中，有一個單獨的驗證嚮導可用來協助驗證邊緣伺服器與內部伺服器之間的連線性。 在 Lync Server 2013 中，連線驗證是在您安裝 Edge 伺服器時自動完成。

您可以在中央管理儲存所在的內部電腦（或已加入任何已安裝 Lync Server 2013 核心元件（OcsCore .msi）的電腦上，執行 Windows PowerShell **CsManagementStoreReplicationStatus** Cmdlet，以驗證將配置資訊複製到 edge。 初始結果可能會指出狀態為「False」，而不是「True」以進行複製。 如果是，請執行**CsManagementStoreReplication** Cmdlet，並允許複製完成時間，然後再次執行**CsManagementStoreReplicationStatus** 。

您可以分別驗證外部使用者連線，包括使用 Office 通訊伺服器遠端連線分析程式來驗證遠端使用者的連線性。 如需詳細資訊，請參閱[在 Lync Server 2013 中驗證外部使用者的連線能力](lync-server-2013-verify-connectivity-for-external-users.md)。

</div>

<span> </span>

</div>

</div>

</div>

