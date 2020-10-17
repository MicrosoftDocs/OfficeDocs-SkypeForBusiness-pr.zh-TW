---
title: Lync Server 2013：規劃前端集區配對
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
ms.openlocfilehash: 484a19b890602ea338f5e98a126a13582ce7e931
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522190"
---
# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a>在 Lync Server 2013 中規劃前端集區配對

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

為了獲得 Lync Server 2013 中最佳的嚴重損壞復原能力，請將前端集區配對部署到兩個地理位置分散的網站。 每個網站都包含與另一個網站中對應的前端集區成對的前端集區。 這兩個網站都使用中，而 Lync Server 備份服務會提供即時資料複寫，以保持集區同步。 備份服務是 Lync Server 2013 中的新功能，其設計目的是用來支援嚴重損壞修復解決方案。 當您將集區與另一個前端集區配對時，它會安裝在前端集區上。

如果某個網站中的集區失敗，您可以將該集區中的使用者容錯移轉至其他網站的集區，然後再為這兩個集區中的所有使用者提供服務。 為了進行容量規劃，每個集區都應該設計為在發生嚴重損壞時處理兩個集區中所有使用者的工作負載。

<div>

## <a name="in-this-section"></a>本章節內容

  - [支援 Lync Server 2013 的集區配對選項及最佳作法](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [Lync Server 2013 中的備份註冊器關聯](lync-server-2013-backup-registrar-relationships.md)

  - [Lync Server 2013 的集區容錯移轉及集區回復器恢復時間](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [Lync Server 2013 中的中央管理存放區容錯移轉](lync-server-2013-central-management-store-failover.md)

  - [Lync Server 2013 中的前端集區配對資料安全性](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

