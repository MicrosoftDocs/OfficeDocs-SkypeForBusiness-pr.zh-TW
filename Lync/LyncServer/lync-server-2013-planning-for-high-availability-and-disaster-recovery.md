---
title: Lync Server 2013：規劃高可用性和嚴重損壞修復
description: Lync Server 2013：規劃高可用性和嚴重損壞修復。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for high availability and disaster recovery
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48183497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bb5f430201c48738421c4fbe72151ca58173898
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571839"
---
# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a>在 Lync Server 2013 中規劃高可用性和嚴重損壞修復

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-31_

就像在 Lync Server 2010 中，Lync Server 2013 中的大部分伺服器角色的主要高可用性架構，都是透過 pooling server 冗余度為基礎。 如果執行特定伺服器角色的伺服器失敗，集區中執行相同角色的其他伺服器就會接手該伺服器的負載。 這適用於前端伺服器、Edge Server、中繼伺服器和 Director。

Lync Server 2013 新增前端集區的新的嚴重損壞修復方法，方法是將伺服器的地理 dispersement 引入兩個資料中心，以在整個集區或網站中斷時，提供服務的連續執行。

Lync Server 2013 也可支援後端資料庫的同步 SQL 鏡像，增強後端伺服器的高可用性。

本節說明這些主要高可用性和災害復原功能，另外也會說明您可以針對其他伺服器角色的高可用性和災害復原採取哪些步驟。

<div>

## <a name="in-this-section"></a>本節內容

  - [Lync Server 2013 中的前端集區嚴重損壞修復](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [Lync Server 2013 中的 Edge Server 災難性修復](lync-server-2013-edge-server-disaster-recovery.md)

  - [在 Lync Server 2013 中規劃 Enterprise Voice 韌性](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [Lync Server 2013 中的「災難修復」的通話管理功能](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [在 Lync Server 2013 中設定持久聊天伺服器以取得高可用性和嚴重損壞修復](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Lync Server 2010 大都市網站恢復功能](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

