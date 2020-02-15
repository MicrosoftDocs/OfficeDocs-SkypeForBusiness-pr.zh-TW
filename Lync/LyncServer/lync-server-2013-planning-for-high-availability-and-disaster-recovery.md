---
title: Lync Server 2013： 規劃高可用性和災害復原
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
ms.openlocfilehash: 38a41585da7cb247dc955b3f4e18ee4812ef5a2a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a>規劃 Lync Server 2013 中的高可用性和災害復原

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-10-31_

Lync Server 2010，如同在 Lync Server 2013 中的多數伺服器角色的主要高可用性配置根據經由共用伺服器備援。 如果執行特定伺服器角色的伺服器失敗，集區中執行相同角色的其他伺服器就會接手該伺服器的負載。 這適用於前端伺服器、Edge Server、中繼伺服器和 Director。

Lync Server 2013 會將新的前端集區的災害復原措施新增到兩個資料中心提供的服務接續萬一有一整個集區或網站移往下引入一部伺服器的地理位置不同。

Lync Server 2013 也增強後端伺服器高可用性，可支援後端資料庫的同步 SQL 鏡像。

本節說明這些主要高可用性和災害復原功能，另外也會說明您可以針對其他伺服器角色的高可用性和災害復原採取哪些步驟。

<div>

## <a name="in-this-section"></a>本節內容

  - [Lync Server 2013 中的結束集區嚴重損壞修復的前端](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [Lync Server 2013 中的 edge Server 災害復原](lync-server-2013-edge-server-disaster-recovery.md)

  - [規劃 Lync Server 2013 中的企業語音恢復能力](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [Lync Server 2013 的災害復原的通話管理功能](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [針對 Lync Server 2013 中的高可用性和災害復原設定常設聊天室伺服器](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Lync Server 2010 都會網站恢復](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

