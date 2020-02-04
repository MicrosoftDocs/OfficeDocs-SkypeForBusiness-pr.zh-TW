---
title: 與 Lync Server 2010 都會區網站復原的 Lync Server 2013 相容性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2010 metropolitan site resiliency
ms:assetid: 18673ff6-b664-4a57-a89b-cbda8b129e6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204715(v=OCS.15)
ms:contentKeyID: 48183526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 395ec568ebafea5c7a06e19340ff5ad10158ffb3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2010-metropolitan-site-resiliency"></a>Lync Server 2010 都會區網站復原

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-03-19_

Lync Server 2013 不支援 Lync Server 2010 支援的大都市網站復原方案。 這個方案涉及跨同一大都市區域中的兩個資料中心跨越單一前端池。

大都市網站復原解決方案的設計目的是要從整個資料中心遺失時復原。 當您跨兩個資料中心跨越您的池時，通常會將半端放在一個資料中心，而另一個資料中心則是第二個資料中心。 如果您遺失整個資料中心，就會遺失一半的前端伺服器。 在 Lync Server 2013 中，這可能會導致新分散式系統模型的新分散式系統模型發生問題。 如需詳細資訊，請參閱[Lync Server 2013 中前端伺服器、立即訊息和目前狀態的拓撲與元件](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。

</div>

<span> </span>

</div>

</div>

</div>

