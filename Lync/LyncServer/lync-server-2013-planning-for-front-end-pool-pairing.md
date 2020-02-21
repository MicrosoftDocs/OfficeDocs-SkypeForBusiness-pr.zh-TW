---
title: Lync Server 2013： 規劃前端集區配對
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Front End pool pairing
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205293(v=OCS.15)
ms:contentKeyID: 48185508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10d45434bf34cc5e7e158039851e8a7fb2cbd6e1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a>前端集區配對 Lync Server 2013 中規劃

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-28_

對於在 Lync Server 2013 最佳嚴重損壞修復能力，部署配對前端集區的跨兩個地理位置分散的站台。 每個網站包含與其他站台中的對應前端集區配對前端集區。 這兩個網站都在使用中，與 Lync Server 備份服務提供即時資料複寫到保持同步處理的集區。 備份服務是在設計為支援的災害復原解決方案的 Lync Server 2013 中的新功能。 配對與另一個前端集區的集區時，它會安裝在前端集區。

如果一個站台中的集區失敗，您可以容錯移轉至其他站台中，然後在兩個集區中的所有使用者提供服務的集區將使用者從該集區。 為了進行容量規劃，每個集區應被設計來處理發生嚴重損壞兩個集區中的所有使用者的工作負載。

<div>

## <a name="in-this-section"></a>本章節內容

  - [支援的集區配對選項和 Lync Server 2013 的最佳做法](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [備份 Lync Server 2013 中的登錄器關聯](lync-server-2013-backup-registrar-relationships.md)

  - [集區容錯移轉和集區容錯回復 Lync Server 2013 中的復原時間](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [Lync Server 2013 中的中央管理存放區容錯移轉](lync-server-2013-central-management-store-failover.md)

  - [前端配對 Lync Server 2013 中的資料安全性集區](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

