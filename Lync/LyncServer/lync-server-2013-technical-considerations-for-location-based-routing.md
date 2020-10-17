---
title: Lync Server 2013： Location-Based 路由的技術考慮
description: Lync Server 2013： Location-Based 路由的技術考慮。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical considerations for Location-Based Routing
ms:assetid: 2e2a9199-7c6f-48d3-9adb-3873fc4f8c4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994027(v=OCS.15)
ms:contentKeyID: 51803936
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54a025af81ab148ad41f95d0a8cf4f900beb7e00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568049"
---
# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a>在 Lync Server 2013 中 Location-Based 路由的技術考慮

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-09_

規劃 Location-Based 路由時，您應該考慮對下列案例的影響。

<div>

## <a name="disaster-recovery"></a>嚴重損壞修復

在從主要集區容錯移轉至備份組區，以及將一般作業還原至主要集區時，Location-Based 路由會在發生災難和復原程式期間的任何時間保持強制執行。

</div>

<div>

## <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

設定 Location-Based 路由會影響部署 Survivable 分支裝置相關聯之閘道的規劃。 與您的 SBA 關聯的閘道，必須位於與 Survivable Branch 裝置相同的網路網站中;否則，位於 Survivable Branch 裝置的使用者將不會在設定 Location-Based 路由的情況下，撥打撥出電話。 當您的 Survivable 分支裝置與中央網站之間的 WAN 連線已停機時，Location-Based 路由限制仍會執行。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中規劃 Location-Based 路由](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

