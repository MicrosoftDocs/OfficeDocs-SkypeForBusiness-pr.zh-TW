---
title: Lync Server 2013：未受位置基礎路由支援的功能
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
ms.openlocfilehash: 967b5b7388ce60eafd46791c226bf1a3edbe0c2b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capabilities-not-supported-by-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 中未受位置基礎路由支援的功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-03-12_

以位置為基礎的路由不適用於下列類型的互動。 當 Lync 端點使用這些功能與 PSTN 端點互動時，不會強制執行位置路由。

  - PSTN 撥入會議

  - 透過回應群組撥入和撥出 PSTN 電話

  - 透過通話駐留撥打電話給寄存或檢索 PSTN 電話

  - 打入的 PSTN 通話至宣告服務

  - 透過群組通話挑選來檢索的打入 PSTN 電話

若要針對下列清單中的互動類型強制執行以位置為基礎的路由規則，您必須為會議啟用位置路由：

  - 從會議進行 PSTN 撥出

  - 從對等音訊交談升級至涉及 PSTN 端點的會議

  - 涉及 PSTN 端點的顧問式轉移

若要啟用會議的位置路由功能，請參閱[Lync Server 2013 中的會議位置路由](lync-server-2013-location-based-routing-for-conferencing.md)。

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中規劃位置基礎路由](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

