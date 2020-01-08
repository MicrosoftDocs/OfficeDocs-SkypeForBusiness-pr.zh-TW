---
title: Lync Server 2013：設定增強型 9-1-1
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Enhanced 9-1-1
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398390(v=OCS.15)
ms:contentKeyID: 48184205
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0ef94e3de028f66684972fa6a3c95d4e63c35b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-enhanced-9-1-1-in-lync-server-2013"></a>在 Lync Server 2013 中設定增強型 9-1-1

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-24_

增強型9-1-1 （E9-1）是緊急通知功能，可將通話方的電話號碼與市政或街道位址進行關聯。 使用這項資訊，公用安全應答點（PSAP）可立即在 distress 中將緊急服務傳送給來電者。

若要支援 E9-1-1，Lync Server 2013 必須能夠正確地將位置與用戶端建立關聯，並確定此資訊是用來將緊急呼叫路由到最接近的 PSAP。

如需規劃 E9-1-1 部署的相關詳細資料，請參閱[Lync Server 2013 中的緊急服務規劃（E9-1-1）](lync-server-2013-planning-for-emergency-services-e9-1-1.md)。

<div>


> [!IMPORTANT]  
> Lync Server 2013 只支援在美國境內 E9-1-1。 若要部署 E9-1，您需要將 SIP 連線設定為合格的 E9-1 服務提供者，或將緊急位置識別號碼（ELIN）閘道部署到公用交換電話（PSTN）-1-1 服務提供者。 如需詳細資訊，請參閱<A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">Lync server 2013 中的增強9-1-1 （E9-1-1）和中繼伺服器</A>。 如需有關設定幹線連線的詳細資訊，請參閱<A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">在 Lync Server 2013 中使用 [媒體旁路] 設定主幹</A>。



</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中設定 E9-1-1 的語音路由](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [在 Lync Server 2013 中建立位置原則](lync-server-2013-create-location-policies.md)

  - [在 Lync Server 2013 中設定 E9-1-1 的網站資訊](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [在 Lync Server 2013 中設定位置資料庫](lync-server-2013-configure-the-location-database.md)

  - [在 Lync Server 2013 中設定高級 E9-1-1 功能](lync-server-2013-configure-advanced-e9-1-1-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

