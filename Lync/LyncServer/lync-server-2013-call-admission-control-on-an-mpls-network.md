---
title: Lync Server 2013：在 MPLS 網路上呼叫許可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control on an MPLS network
ms:assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398168(v=OCS.15)
ms:contentKeyID: 48183387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee138a0f61bace067db12c9df4f06338aa13ac8b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-on-an-mpls-network-with-lync-server-2013"></a>使用 Lync Server 2013 在 MPLS 網路上呼叫許可控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-22_

在多協定標籤切換（MPLS）網路中，所有網站都是以全網格連接。 也就是說，所有網站都直接連線至網際網路服務提供者的 MPLS 中樞，且每個網站都配有頻寬，可跨 WAN 連結使用到 MPLS 雲端。 沒有網路中樞或中央網站可控制 IP 路由。 下圖顯示的是以 MPLS 技術為基礎的簡單網路。

**MPLS 網路範例**

使用 MPLS 的![cac](images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "cac")

若要在 MPLS 網路中部署呼叫許可控制（CAC），您需要建立網路區域來代表 MPLS 雲端，並建立網路網站來代表每個 MPLS 附屬網站。 下圖說明如何設定網路區域和網路網站，以代表前圖中的範例 MPLS 網路。 整個頻寬限制和頻寬會話限制是依據從每個網路網站到代表 MPLS 雲端之網路區域的 WAN 連結容量而定。

**MPLS 網路的網路區域和網路網站**

使用 mpls 圖表呼叫許可(images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "控制（cac）") ![的呼叫許可控制（cac]）

</div>

<span> </span>

</div>

</div>

</div>

