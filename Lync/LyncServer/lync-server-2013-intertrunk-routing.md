---
title: Lync Server 2013： 主幹間路由
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
ms.openlocfilehash: ce206c0f20dc00c6abc1304db8c1f933cbefdbca
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145261"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="intertrunk-routing-in-lync-server-2013"></a>Lync Server 2013 中的主幹相互路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-20 個_

Lync Server 2013 可以相互連線至公用交換的電話網路 (PSTN) 閘道 IP PBX，以便從 PBX 電話的通話路由至 PSTN，以及傳入 PSTN 通話路由至專用交換機 (pbx) 電話。 同樣地，Lync Server 2013 可以 interconnect 兩個或多個 IP-PBX 系統，以便可以放置和 PBX 電話從不同的 IP PBX 系統之間接收來電。

此主幹間路由功能可以設定 Lync Server 管理命令介面指令程式， **Set-cstrunkconfiguration**，使用新的參數，PstnUsages。 此參數會指定要使用的 PSTN 使用方式記錄的集合。 主幹使用此 PSTN 使用方式，來判定路由，並據此路由傳送所有來電。

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

下圖說明提供互連功能 PSTN 閘道與 IP-PBX 間的 Lync Server 2013。

**閘道和 IP PBX 之間的主幹相互路由**

![Lync Server 連線 PSTN 閘道/IP-PBX 圖表](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server 連線 PSTN 閘道/IP-PBX 圖表")

下圖說明交互連接兩個 IP-PBX 系統的 Lync Server 2013。

**兩個 IP Pbx 之間的主幹相互路由**

![Lync Server 交互連接 IP PAX 系統圖表](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server 交互連接 IP PAX 系統圖表")

</div>

<span> </span>

</div>

</div>

</div>

