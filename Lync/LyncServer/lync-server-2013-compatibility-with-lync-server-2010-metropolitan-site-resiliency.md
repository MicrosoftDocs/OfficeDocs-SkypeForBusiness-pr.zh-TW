---
title: Lync Server 2013 與 Lync Server 2010 大都市網站恢復的相容性
description: Lync Server 2013 與 Lync Server 2010 大都市網站恢復的相容性。
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
ms.openlocfilehash: ec72f261ac593b24bad13dcd400f495ba7ba0722
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576929"
---
# <a name="lync-server-2010-metropolitan-site-resiliency"></a>Lync Server 2010 大都市網站恢復功能

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-03-19_

Lync 2013 Server 2010 不支援 Lync Server 支援的大都市網站恢復解決方案。 這個解決方案會將單一前端集區橫跨同一都會區中的兩個資料中心。

大都市網站恢復解決方案旨在從整個資料中心遺失時復原。 當您跨越兩個資料中心的集區時，您通常會在一個資料中心中放置一半的前端，另一個則是第二個資料中心的一半。 如果您遺失整個資料中心，您已遺失一半的前端伺服器。 這可能會導致 Lync Server 2013 中的前端集區的新分散式系統模型發生問題。 如需詳細資訊，請參閱 [Lync Server 2013 中的前端伺服器、立即訊息及顯示狀態的拓撲和元件](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。

</div>

<span> </span>

</div>

</div>

</div>

