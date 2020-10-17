---
title: Lync Server 2013： Location-Based 路由不支援的功能
description: Lync Server 2013：不支援 Location-Based 路由的功能。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capabilities not supported by Location-Based Routing
ms:assetid: c3d54953-a7d6-4465-a6c3-ae411b2d8ea9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994071(v=OCS.15)
ms:contentKeyID: 51803982
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf9cd03a8cbdd50e136605c4f172598b2ad3f523
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565159"
---
# <a name="capabilities-not-supported-by-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 中 Location-Based 路由不支援的功能

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-03-12_

Location-Based 路由不適用於下列類型的互動。 當 Lync 端點使用這些功能與 PSTN 端點互動時，不會強制執行 Location-Based 路由。

  - PSTN 電話撥入式會議

  - 透過回應群組的呼入和呼出 PSTN 通話

  - 透過通話駐留通話駐留或檢索 PSTN 通話

  - 對宣告服務的打入 PSTN 通話

  - 透過群組呼叫收取的打入的 PSTN 通話

若要對下列清單中的互動類型執行 Location-Based 路由規則，您必須為會議啟用 Location-Based 路由：

  - 來自會議的 PSTN 撥出

  - 從對等音訊交談上報至涉及 PSTN 端點的會議

  - 涉及 PSTN 端點的諮詢轉移

若要啟用會議的 Location-Based 路由，請參閱 [Lync Server 2013 中的會議位置基礎路由](lync-server-2013-location-based-routing-for-conferencing.md)。

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中規劃 Location-Based 路由](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

