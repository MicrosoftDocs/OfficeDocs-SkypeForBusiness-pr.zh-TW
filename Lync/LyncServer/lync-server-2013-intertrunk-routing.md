---
title: Lync Server 2013：主幹間路由
description: Lync Server 2013：主幹間路由傳送。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30c838ee94a2df0807195c172d7e2a3a393523af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553139"
---
# <a name="intertrunk-routing-in-lync-server-2013"></a>Lync Server 2013 中的主幹間路由

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-20_

Lync Server 2013 可將 IP-PBX 互連至公用交換電話網路 (PSTN) 閘道，以便從 PBX 電話將通話路由傳送至 PSTN，然後將傳入 PSTN 通話路由傳送至專用交換機 (PBX) phone。 同樣地，Lync Server 2013 可以互連兩個或多個 IP-PBX 系統，這樣通話便可在不同 IP-PBX 系統的 PBX 電話間撥打及接收。

您可以使用 Lync Server 管理命令介面 Cmdlet **Set-CsTrunkConfiguration**，使用新參數 PstnUsages 來設定此主幹間路由功能。 此參數會指定要使用的 PSTN 使用方式記錄集合。 主幹使用此 PSTN 使用方式判斷路由，並據此路由傳送所有來電。

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

下圖說明 Lync Server 2013 在 PSTN 閘道和 IP-PBX 之間提供 interconnectivity。

**閘道和 IP PBX 間的主幹間路由**

![連接 PSTN 閘道/IP-PBX 圖表的 Lync Server](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "連接 PSTN 閘道/IP-PBX 圖表的 Lync Server")

下圖說明 Lync Server 2013 互連兩個 IP-PBX 系統的互連。

**主幹間兩個 IP PBXs 之間的路由**

![Lync Server 互連 IP-PAX 系統圖表](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server 互連 IP-PAX 系統圖表")

</div>

<span> </span>

</div>

</div>

</div>

