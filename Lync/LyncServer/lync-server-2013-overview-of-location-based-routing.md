---
title: 'Lync Server 2013: Overview of 依位置路由'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1b563f28fac5eef836262138c2b0713f7b273e0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-in-lync-server-2013"></a>Overview of Lync Server 2013 中依位置路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-21_

位置型路由引進了一組新的規則，修改可防止通話費略過的國內和國際 PSTN 通話路由傳送。 位置型路由提供的彈性來範圍至特定的區域，這些規則特定閘道或特定的使用者只有一組。

下列案例說明的限制位置型路由可以強制執行的主要類型：

  - 輸出通話 – 位置型路由可以強制執行輸出從位於同一個區域設為來電者為防止 PSTN 通話費略過，以防止透過 PSTN 閘道位於不同的地區，做為輸出呼叫 PSTN 閘道的撥出電話來電者。

  - 輸入呼叫 – 位置型路由可以防止響鈴 Lync 端點傳入 PSTN 通話如果路由內送呼叫的 PSTN 閘道並非位於受話 Lync 使用者的相同區域。

  - 未知的區域 – 位置型路由限制傳入和傳出 PSTN 通話到及傳送自位於未定位置 （亦即遠端使用者從網際網路連接或位於未知的地區） 的使用者。

  - 國際區域 – 強制執行位置型的路由，路由傳送撥出電話通過國際 PSTN 閘道，如果找不到本機閘道到使用者的位置。

<div>

## <a name="see-also"></a>另請參閱


[規劃 Lync Server 2013 中依位置路由](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

