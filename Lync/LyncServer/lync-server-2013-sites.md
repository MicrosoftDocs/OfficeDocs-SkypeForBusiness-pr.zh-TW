---
title: Lync Server 2013 網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1843ac4256e71723abf59fa272155ced2010e72
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-sites-for-lync-server-2013"></a>Lync Server 2013 的 Lync Server 網站

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-16_

在 Lync Server 中，您會在網路上定義包含 Lync Server 元件的*網站*。 網站是一組由高速、低延遲網路連接的電腦，例如單一局域網（LAN），或由高速光纖光纖網路連接的兩個網路。 請注意，Lync Server 網站是來自 Active Directory 網域服務網站和 Microsoft Exchange Server 網站的個別概念。 您的 Lync Server 網站不需要與 Active Directory 網站相對應。

<div>

## <a name="site-types"></a>網站類型

每個網站都是*中央網站*，其中包含至少一個前端池或標準版伺服器，或*分支網站*。 每個分支網站都只會與一個中心網站建立關聯，而分支網站上的使用者就能從關聯的中央網站從伺服器取得大多數的 Lync Server 功能。

每個分支網站都包含下列其中一項：

  - *Survivable 分支裝置（SBA）* 是一種工業標準刀片伺服器，其中包含 Lync Server 註冊機構，以及在 Windows server 上執行的中繼伺服器。 Survivable 分支裝置也包含公用的交換電話網絡（PSTN）閘道。 Survivable 分支裝置專為25與1000使用者之間的分支網站而設計。

  - *Survivable 分支伺服器（SBS）* 是一種執行 Windows Server 且符合指定硬體需求的伺服器，且已在其中安裝 Lync Server 註冊機構和轉送伺服器軟體。 它必須連線至 PSTN 閘道或 SIP 幹線給電話服務提供者。 Survivable 分支伺服器是針對1000與5000使用者之間的分支網站而設計。

  - PSTN 閘道，也可以選擇使用*中繼伺服器*。 如需此與其他伺服器角色的詳細資料，請參閱[Lync server 2013 中的伺服器角色](lync-server-2013-server-roles.md)。

有彈性廣域網路（WAN）連結至中心網站的分支機搆可以使用第三個選項： PSTN 閘道，以及其他中繼伺服器。 具有較低彈性連結的分支機搆網站應該使用 Survivable 分支裝置或 Survivable 分支伺服器，這會提供廣域網路絡故障的復原時間。 例如，在已部署 Survivable 分支裝置或 Survivable 分支伺服器的網站中，如果將分支網站連接至中心網站的 WAN，使用者仍然可以撥打及接聽企業語音通話。 如需 Survivable 分支裝置的詳細資料，請 Survivable [分支伺服器] 和 [復原]，請參閱規劃檔中的[Lync server 2013 規劃企業語音復原](lync-server-2013-planning-for-enterprise-voice-resiliency.md)。

</div>

<div>

## <a name="site-topologies"></a>網站拓撲

您的部署必須包含至少一個中央網站，而且可以包含零到多個分支網站。 每個分支網站都隸屬于一個中心網站。 中央網站將 Lync Server services 提供給分支網站，而該網站不是在本機主機（例如目前狀態與會議）中託管。

如果您有多個網站，您可以將前端池放在不同的網站，以啟用災害復原能力。 如需詳細資訊，請參閱[Lync Server 2013 中的高可用性與災害復原支援](lync-server-2013-high-availability-and-disaster-recovery-support.md)。

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的伺服器角色](lync-server-2013-server-roles.md)  
[Lync Server 2013 中的高可用性和災害復原支援](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[在 Lync Server 2013 中規劃企業語音復原](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

