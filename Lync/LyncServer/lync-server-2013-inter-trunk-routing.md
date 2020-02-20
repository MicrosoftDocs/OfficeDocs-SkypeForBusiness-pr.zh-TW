---
title: Lync Server 2013： 主幹間路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Inter-trunk routing
ms:assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721940(v=OCS.15)
ms:contentKeyID: 49733877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b73e4b7588c7f267a5fe4abc2db48661755dea03
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="inter-trunk-routing-in-lync-server-2013"></a>Lync Server 2013 中的主幹間路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-08_

Lync Server 2013 提供透過支援的主幹相互路由功能的基本工作階段管理。 這項新功能可讓 Lync 伺服器，以提供呼叫控制功能下游電話語音系統。 主幹間路由可以 interconnect 至公用交換的電話網路 (PSTN) 閘道 IP PBX，以便從專用交換機 (pbx) 電話的通話路由至 PSTN，以及傳入 PSTN 通話可以路由傳送至 PBX 的電話。 同樣地，Lync Server 可以 interconnect 兩個或多個 IP-PBX 系統，以便可以放置和 PBX 電話從不同的 IP PBX 系統之間接收來電。

下圖說明提供互連功能 PSTN 閘道與 IP-PBX 間的 Lync Server 2013。

![Lync Server 連線 PSTN 閘道/IP-PBX 圖表](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server 連線 PSTN 閘道/IP-PBX 圖表")

下圖說明連接兩個 IP-PBX 系統的 Lync Server 2013。

![Lync Server 交互連接 IP PAX 系統圖表](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server 交互連接 IP PAX 系統圖表")

</div>

<span> </span>

</div>

</div>

</div>

