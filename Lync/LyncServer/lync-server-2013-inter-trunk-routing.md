---
title: Lync Server 2013：幹線間路由
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
ms.openlocfilehash: 37a9feb818f48317f9a3dddd78a70700e3f6ccfc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="inter-trunk-routing-in-lync-server-2013"></a>Lync Server 2013 中的中繼間路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-08_

Lync Server 2013 提供基本的會話管理，並支援 intertrunk 路由。 這項新功能可讓 Lync Server 提供對下游電話系統的呼叫控制功能。 Intertrunk 路由可以將 IP PBX 互連至公用的交換電話網絡（PSTN）閘道，讓來自私人分支 exchange （PBX）電話的呼叫可以路由到 PSTN，而且傳入 PSTN 呼叫可以路由到 PBX 電話。 同樣地，Lync Server 可以相互連接兩個或多個 IP PBX 系統，以便在不同 IP PBX 系統的 PBX 手機之間進行呼叫和接收。

下圖說明 Lync Server 2013，提供 PSTN 閘道與 IP PBX 之間的 interconnectivity。

![連接 PSTN 閘道/IP-PBX 圖表的 Lync Server](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "連接 PSTN 閘道/IP-PBX 圖表的 Lync Server")

下圖說明連接兩個 IP PBX 系統的 Lync Server 2013。

![交互連接 IP-PAX 系統圖表的 Lync Server](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "交互連接 IP-PAX 系統圖表的 Lync Server")

</div>

<span> </span>

</div>

</div>

</div>

