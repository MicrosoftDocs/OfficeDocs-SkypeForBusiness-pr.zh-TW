---
title: Lync Server 2013：主幹間路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c1b66ea04ed72bab6d33114f52fa9fe96364b48
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="intertrunk-routing-in-lync-server-2013"></a>Lync Server 2013 中的主幹間路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-20_

Lync Server 2013 可以將 IP PBX 與公用交換式電話網絡（PSTN）閘道相互連接，讓來自 PBX 電話的呼叫可以路由到 PSTN，而且傳入的 PSTN 呼叫可以路由到專用的分支 exchange （PBX）電話。 同樣地，Lync Server 2013 可以相互連接兩個或多個 IP PBX 系統，以便在不同 IP PBX 系統的 PBX 手機之間進行呼叫和接收。

此 intertrunk 路由功能可以使用 Lync Server Management Shell Cmdlet （**設定為 new-cstrunkconfiguration**），並使用新的參數 PstnUsages 進行設定。 這個參數會指定要使用的 PSTN 使用記錄集合。 主幹使用這種 PSTN 用法來判斷路線，並據此傳送所有來電。

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

下圖說明 Lync Server 2013，提供 PSTN 閘道與 IP PBX 之間的 interconnectivity。

**Intertrunk 閘道與 IP PBX 之間的路由**

連線![pstn 閘道/IP pbx 圖的 Lync server]連接(images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "pstn 閘道/ip pbx 圖表的 lync server")

下圖說明 Lync Server 2013 互連兩個 IP PBX 系統的操作。

**在兩個 IP Pbx 之間 Intertrunk 路由**

![Lync server 互連 ip-pax 系統圖表](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "LYNC server 互連 ip-pax 系統圖表")

</div>

<span> </span>

</div>

</div>

</div>

