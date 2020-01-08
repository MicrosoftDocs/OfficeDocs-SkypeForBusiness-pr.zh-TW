---
title: Lync Server 2013：規劃高可用性和災害復原
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for high availability and disaster recovery
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48183497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 092e59813f76690233a950cd8ce914df47146d37
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a>在 Lync Server 2013 中規劃高可用性和災害復原

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-31_

就像在 Lync Server 2010 中，Lync Server 2013 中大多數伺服器角色的主要高可用性配置都是透過「池」以伺服器冗余為基礎。 如果執行特定伺服器角色的伺服器失敗，則池中執行相同角色的其他伺服器會載入該伺服器。 這適用于前端伺服器、邊緣伺服器、轉送伺服器和控制器。

Lync Server 2013 會將您的伺服器地理位置 dispersement 引入兩個資料中心，以提供服務的新災害復原方法，以在整個池或網站向下移動。

Lync Server 2013 也會針對後端資料庫支援同步 SQL 鏡像，改善後端伺服器的高可用性。

本節說明這些主要的高可用性和災難復原功能，同時也說明您可以針對其他伺服器角色採取的高可用性和災難復原步驟。

<div>

## <a name="in-this-section"></a>本節內容

  - [Lync Server 2013 中的前端集區災害復原](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [Lync Server 2013 中的 Edge Server 災害復原](lync-server-2013-edge-server-disaster-recovery.md)

  - [在 Lync Server 2013 中規劃企業語音復原](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [Lync Server 2013 中的災害復原通話管理功能](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [在 Lync Server 2013 中針對高可用性和災害復原設定常設聊天室伺服器](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Lync Server 2010 都會區網站復原](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

