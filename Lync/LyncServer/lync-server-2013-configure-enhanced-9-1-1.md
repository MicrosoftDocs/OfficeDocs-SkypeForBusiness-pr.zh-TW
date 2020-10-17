---
title: Lync Server 2013：設定增強型9-1-1
description: Lync Server 2013：設定增強型9-1-1。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Enhanced 9-1-1
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398390(v=OCS.15)
ms:contentKeyID: 48184205
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc7a2a9ed10e7f29f53a4dfff6dff926ded18d38
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553329"
---
# <a name="configure-enhanced-9-1-1-in-lync-server-2013"></a>在 Lync Server 2013 中設定增強型9-1-1

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-24_

增強型 9-1-1 (E9-1-1) 是緊急通知功能，會讓來電者的電話號碼與市街地址產生關聯。使用這項資訊，公共安全勤務中心 (PSAP) 可以立即派遣緊急服務人員到需要幫助的來電者所在處。

若要支援 E9-1-1，Lync Server 2013 必須能夠正確地將位置與用戶端產生關聯，並確定此資訊是用來將緊急通話路由傳送至最近的 PSAP。

如需規劃 E9-1-1 部署的詳細資訊，請參閱 [E9-1-1) In Lync Server 2013 中的 [規劃緊急 (服務](lync-server-2013-planning-for-emergency-services-e9-1-1.md)]。

<div>


> [!IMPORTANT]  
> Lync Server 2013 只支援美國境內的 E9-1-1。 若要部署 E9-1-1，您必須設定與合格的 E9-1-1 服務提供者的 SIP 連線，或者將緊急位置識別號碼 (ELIN) 閘道部署至以公用交換電話網路 (PSTN) 為基礎的 E9-1-1 服務提供者。 如需詳細資訊，請參閱 <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">E9-1-1) 和轉送伺服器（Lync server 2013）中的增強 9-1-1 (</A>。 如需設定主幹連線的詳細資訊，請參閱 <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">在 Lync Server 2013 中使用媒體旁路設定主幹</A>。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中設定 E9-1-1 語音路由](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [在 Lync Server 2013 中建立位置原則](lync-server-2013-create-location-policies.md)

  - [在 Lync Server 2013 中設定 E9-1-1 的網站資訊](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [在 Lync Server 2013 中設定位置資料庫](lync-server-2013-configure-the-location-database.md)

  - [在 Lync Server 2013 中設定 advanced E9-1-1 功能](lync-server-2013-configure-advanced-e9-1-1-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

