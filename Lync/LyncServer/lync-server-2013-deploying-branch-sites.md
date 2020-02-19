---
title: Lync Server 2013： 部署分支站台
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
ms.openlocfilehash: c167dc4f81053d5b9dde547f2f1e6e3d9d1a0fe7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140116"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-branch-sites-in-lync-server-2013"></a>部署 Lync Server 2013 中的分支網站

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-21_

分支網站使用者在分支網站相關聯的中央網站從伺服器取得它們大部分的 Lync Server 2013 功能。 每個分支網站都恰與一個中央網站關聯。 若要與公用交換電話網路 (PSTN) 傳送通話，分支網站可能包含下列任一項：

  - PSTN 閘道，以及可能包含中繼伺服器

  - SIP 主幹

  - 現有語音基礎結構搭配專用交換機 (PBX)

  - Survivable Branch Appliance

  - Survivable Branch 伺服器

Survivable Branch Appliance 或 Survivable Branch Server 分支站台位於更有彈性廣域網路或中央站台失敗的次數超過分支網站，而這些解決方案的其中一個。 例如，在網站使用 Survivable Branch Appliance 或 Survivable Branch 伺服器部署中，使用者可以仍撥打及接聽 PSTN 通話如果網路連線至中央網站的分支站台不通。 以達到分支網站恢復的另一種方式是使用 PSTN 閘道或 SIP 主幹與分支網站的完整規模 Lync Server 部署。

如需詳細資訊需哪種分支網站部署最適合您的組織，包括先決條件和其他規劃考量，請參閱規劃文件中的[Planning for Lync Server 2013 中的 PSTN 連線能力](lync-server-2013-planning-for-pstn-connectivity.md)」 和 「 [Lync Server 2013 中的分支網站語音恢復能力的計劃](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。

<div>

## <a name="in-this-section"></a>本章節內容

  - [提供在分支網站 Lync Server 2013 中的 PSTN 連線](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [部署 Survivable Branch Appliance 或 survivable branch Server 與 Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

