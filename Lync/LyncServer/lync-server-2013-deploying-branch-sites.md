---
title: Lync Server 2013：部署分支網站
description: Lync Server 2013：部署分支網站。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d653e3f06de832693d97bfb229f122a67c28640e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552639"
---
# <a name="deploying-branch-sites-in-lync-server-2013"></a>在 Lync Server 2013 中部署分支網站

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

分支網站使用者在分支網站相關聯的中央網站上，從該伺服器取得大多數的 Lync Server 2013 功能。 每個分支網站都恰與一個中央網站關聯。 若要與公用交換電話網路 (PSTN) 傳送通話，分支網站可能包含下列任一項：

  - PSTN 閘道，以及可能包含中繼伺服器

  - SIP 主幹

  - 現有語音基礎結構搭配專用交換機 (PBX)

  - Survivable 分支裝置

  - Survivable 分支伺服器

使用 Survivable 分支裝置或 Survivable Branch 伺服器的分支網站，在廣域網路絡或中央網站發生故障的情況下，會比沒有這些解決方案的分支網站更具彈性。 例如，在已部署 Survivable 分支裝置或 Survivable Branch 伺服器的網站中，如果將分支網站連接到中央網站時，使用者仍可撥打和接收 PSTN 通話。 若要達到分支網站恢復能力，另一種方式是使用 PSTN 閘道，或在分支網站使用具有完整層級 Lync Server 部署的 SIP 主幹。

如需有關貴組織正確分支網站部署的詳細資訊，包括必要條件和其他規劃考慮，請參閱規劃檔中的規劃 lync server [2013 中的 PSTN](lync-server-2013-planning-for-pstn-connectivity.md) 連線和 [規劃分支網站語音2013彈性](lync-server-2013-planning-for-branch-site-voice-resiliency.md) 。

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 的分支網站提供 PSTN 連線能力](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [使用 Lync Server 2013 部署 Survivable 分支裝置或伺服器](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

