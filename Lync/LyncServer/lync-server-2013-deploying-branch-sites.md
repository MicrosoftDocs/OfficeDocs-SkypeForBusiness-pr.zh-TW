---
title: Lync Server 2013：部署分支網站
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
ms.openlocfilehash: facfda5d1d7ce67ea08f71cbfb943792eeced7a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-branch-sites-in-lync-server-2013"></a>在 Lync Server 2013 中部署分支網站

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

分支網站使用者在分支網站所關聯的中央網站上，從伺服器取得最大部分的 Lync Server 2013 功能。 每個分支網站都只與一個中央網站相關聯。 若要提供與公眾交換電話網絡（PSTN）的呼叫和來源，分支網站可能會包含下列任何一項：

  - PSTN 閘道和可能是 Meditation 伺服器

  - SIP 主幹

  - 具有私人分支 exchange （PBX）的現有語音結構

  - Survivable 分支裝置

  - Survivable 分支伺服器

使用 Survivable 分支裝置或 Survivable 分支伺服器的分支網站，比不含下列其中一種解決方案的分支網站的廣域網路或中央網站故障更具彈性。 例如，在已部署 Survivable 分支裝置或 Survivable 分支伺服器的網站中，如果將分支網站連線到中央網站的網路，使用者仍然可以撥打和接聽 PSTN 通話。 若要實現分支網站復原，另一種方式是在分支網站上使用 PSTN 閘道或 SIP 幹線進行完整的 Lync 伺服器部署。

如需有關哪個分支網站部署適合您組織的詳細資料（包括先決條件及其他規劃考慮），請參閱規劃檔中的 lync server [2013 規劃](lync-server-2013-planning-for-pstn-connectivity.md)，以及在[lync Server 2013 中規劃分支網站語音復原](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。

<div>

## <a name="in-this-section"></a>本節內容

  - [使用 Lync Server 2013 在分支網站提供 PSTN 連線](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [使用 Lync Server 2013 部署 Survivable Branch Appliance 或 Survivable Branch Server](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

