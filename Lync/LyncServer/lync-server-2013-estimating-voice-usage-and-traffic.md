---
title: Lync Server 2013： 評估語音使用方式和流量
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
ms.openlocfilehash: 7723a67b4cefb75218f01dde3603a100b54d40b8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42131396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="estimating-voice-usage-and-traffic-for-lync-server-2013"></a>評估語音使用方式和 Lync Server 2013 的流量

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-08-07_

Microsoft Lync Server 2013、 規劃工具可用於下列計量評估的使用者流量，每個網站，以及支援該流量所需的連接埠數目。

  - <span></span>  
    針對**輕型流量** (每位使用者每小時一個 PSTN 通話)，估計每個連接埠 15 位使用者。

  - <span></span>  
    針對**中型流量** (每位使用者每小時兩個 PSTN 通話)，估計每個連接埠 10 位使用者。

  - <span></span>  
    針對**重型流量** (每位使用者每小時三個以上的 PSTN 通話)，估計每個連接埠 5 位使用者。

連接埠的數量接著會決定中繼伺服器和閘道所需的數目。 大多數的組織請考慮部署多達 960 連接埠大小 2 的連接埠範圍公用交換的電話網路 (PSTN) 閘道。 （有更大的閘道器，但這些可用主要是藉由電話語音服務提供者）。

例如，有 10,000 位使用者及中型流量的組織需要 1000 個連接埠。需要的閘道數目會等於閘道總容量所決定的必要連接埠總數。

</div>

<span> </span>

</div>

</div>

</div>

