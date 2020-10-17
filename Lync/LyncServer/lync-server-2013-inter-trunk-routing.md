---
title: Lync Server 2013：主幹間路由
description: Lync Server 2013：主幹間路由。
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
ms.openlocfilehash: 7e023956f28183423c04e94948acdec0df2c1284
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543969"
---
# <a name="inter-trunk-routing-in-lync-server-2013"></a>Lync Server 2013 中的主幹間路由

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-08_

Lync Server 2013 提供基本的會話管理，其支援主幹間路由。 這項新功能可讓 Lync Server 向下游電話語音系統提供呼叫控制功能。 主幹間路由可將 IP-PBX 互連至公用交換電話網路 (PSTN) 閘道，使來自私營分公司 exchange (PBX) phone 的呼叫可以路由傳送至 PSTN，而且傳入 PSTN 通話可以路由傳送至 PBX 電話。 同樣地，Lync Server 可以互連兩個或多個 IP-PBX 系統，這樣通話便可在不同 IP-PBX 系統的 PBX 電話之間進行和接收。

下圖說明 Lync Server 2013 在 PSTN 閘道和 IP-PBX 之間提供 interconnectivity。

![連接 PSTN 閘道/IP-PBX 圖表的 Lync Server](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "連接 PSTN 閘道/IP-PBX 圖表的 Lync Server")

下圖說明連接兩個 IP-PBX 系統的 Lync Server 2013。

![Lync Server 互連 IP-PAX 系統圖表](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server 互連 IP-PAX 系統圖表")

</div>

<span> </span>

</div>

</div>

</div>

