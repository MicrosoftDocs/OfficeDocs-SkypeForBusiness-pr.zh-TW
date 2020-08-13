---
title: 驗證內部伺服器和 Edge Server 之間的連線能力
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity between internal servers and Edge Servers
ms:assetid: 219f706e-2b8a-46c5-b394-c384240eef50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398292(v=OCS.15)
ms:contentKeyID: 48183602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bd749aea86f610cee2671648e4e2ce1486cfba5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-between-internal-servers-and-edge-servers-in-lync-server-2013"></a>驗證 Lync Server 2013 中內部伺服器和 Edge Server 之間的連線能力

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

在 Lync Server 2013 中，可使用個別驗證嚮導，以協助驗證 Edge Server 與內部伺服器之間的連線能力。 在 [Lync Server 2013] 中，當您安裝 Edge Server 時，會自動進行連線驗證。

您可以在中央管理存放區 (所在的內部電腦上執行 Windows PowerShell **Get-CsManagementStoreReplicationStatus** Cmdlet，以驗證設定資訊的複寫，也可以在已安裝任何已加入網域的電腦上，執行 ( # A0) 之 Lync Server 2013 核心元件的任何已加入網域的電腦。 初始結果可能會指出複寫的狀態為 "False"，而非 "True"。 若是如此，請執行 **Invoke-CsManagementStoreReplication** Cmdlet、等候複寫完成，然後再次執行 **Get-CsManagementStoreReplicationStatus**。

您可以單獨驗證外部使用者連線，包括使用 Office Communications Server 遠端連線分析程式來驗證遠端使用者連線。 如需詳細資訊，請參閱[在 Lync Server 2013 中驗證外部使用者的連線能力](lync-server-2013-verify-connectivity-for-external-users.md)。

</div>

<span> </span>

</div>

</div>

</div>

