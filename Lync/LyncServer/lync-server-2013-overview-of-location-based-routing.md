---
title: Lync Server 2013： Location-Based 路由的概述
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
ms.openlocfilehash: 48fee2b9db45519ff4773b4dfe47b33745e5fb10
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520960"
---
# <a name="overview-of-location-based-routing-in-lync-server-2013"></a>在 Lync Server 2013 中 Location-Based 路由的概覽

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

Location-Based 路由引進一組新的規則，可修改國內和國際 PSTN 通話的路由，以避免收費旁路。 Location-Based 路由可讓您靈活地將這些規則的範圍設定為特定區域、特定閘道或特定使用者集。

下列案例說明 Location-Based 路由可強制執行的主要限制類型：

  - 出局通話– Location-Based 路由可強制撥出呼叫至位於與來電者防止 PSTN 長途電話旁路之 PSTN 閘道的外撥，這可防止呼叫來自位於其他地區之 PSTN 閘道的外送。

  - 進入通話– Location-Based 路由可在撥入電話所在的 PSTN 閘道與呼叫的 Lync 使用者不在相同地區時，防止傳入 PSTN 來電撥打 Lync 端點。

  - 未知地區– Location-Based 路由會限制位於未決定位置之使用者傳入和傳出 PSTN 來電 (亦即從網際網路連線或位於未知地區) 的遠端使用者。

  - 國際地區–如果找不到使用者位置的閘道，Location-Based 路由會透過國際 PSTN 閘道來傳送撥出電話。

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中規劃 Location-Based 路由](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

