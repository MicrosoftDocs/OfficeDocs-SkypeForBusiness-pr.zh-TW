---
title: Lync Server 2013：規劃前端集區配對
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Front End pool pairing
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205293(v=OCS.15)
ms:contentKeyID: 48185508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0445a6d952ba7311b8f6b5435c16d9e91de587f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982675"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a>在 Lync Server 2013 中規劃前端集區配對

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

針對 Lync Server 2013 中最佳的災害復原能力，請跨兩個地理位置分散的網站，部署前端池的對。 每個網站都包含與另一個網站中相對應的前端池配對的前端池。 這兩個網站都是作用中的，而 Lync Server 備份服務提供即時資料複製來保持池同步處理。 備份服務是 Lync Server 2013 中的新功能，可用於支援災害復原方案。 當您將池與另一個前端池配對時，它會安裝在前端池。

如果一個網站中的 [池] 失敗，您可以將該池的使用者容錯移轉至其他網站的 [池]，然後在這兩個池中的所有使用者提供服務。 針對容量規劃目的，每個池都應該設計為在發生災難事件時，處理兩個彙集中所有使用者的工作量。

<div>

## <a name="in-this-section"></a>本節內容

  - [支援 Lync Server 2013 的池配對選項和最佳做法](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [Lync Server 2013 中的備份登錄器關聯](lync-server-2013-backup-registrar-relationships.md)

  - [Lync Server 2013 中的集區容錯回復與集區容錯移轉的復原時間](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [Lync Server 2013 中的中央管理存放區容錯移轉](lync-server-2013-central-management-store-failover.md)

  - [Lync Server 2013 中前端集區配對資料安全性](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

