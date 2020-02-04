---
title: Lync Server 2013：評估語音使用方式和流量
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Estimating voice usage and traffic
ms:assetid: 621b08fb-f894-4d91-ac38-e443401b098b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398439(v=OCS.15)
ms:contentKeyID: 48184332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06093893c5de9a08322e1577fbbbe6779d4209cc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="estimating-voice-usage-and-traffic-for-lync-server-2013"></a>針對 Lync Server 2013 評估語音使用方式和流量

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-08-07_

Microsoft Lync Server 2013、規劃工具會使用下列度量來估計每個網站的使用者流量，以及支援該流量所需的埠數。

  - <span></span>  
    對於**輕型流量**（每個使用者每小時一個 PSTN 通話），請在每個埠上見15個使用者。

  - <span></span>  
    針對**中型交通**（每位使用者每小時2個 PSTN 通話），圖10每個埠的使用者數。

  - <span></span>  
    對於**大量流量**（3個或更多每個使用者每小時的 PSTN 通話），請依圖5每個埠的使用者。

接下來的埠數會決定要使用的中繼伺服器和閘道數目。 大多陣列織考慮將範圍從2個埠部署到最多960個埠的公用交換電話網絡（PSTN）閘道。 （甚至是更大的閘道，但主要是由電話服務提供者使用。）

例如，有10000使用者和中型交通的組織需要1000埠。 所需的閘道數目會等於由閘道總容量決定所需的埠總數。

</div>

<span> </span>

</div>

</div>

</div>

