---
title: 將延伸的常設聊天室伺服器集區用於災害復原
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using a stretched Persistent Chat Server pool for disaster recovery
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205007(v=OCS.15)
ms:contentKeyID: 48184506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2d5091623e381191d23ae0c8a62835577a1f66a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a>在 Lync Server 2013 中將延伸的常設聊天室伺服器集區用於災害復原

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

持續聊天伺服器的災害復原解決方案是在延伸持續性的持久聊天伺服器池中建立。 這與 Lync Server 2010 中的大都市版網站復原類似;不過，延伸虛擬區域網路絡（VLAN）就沒有任何需求。 透過拉伸持續性聊天伺服器池，您實質上會以邏輯方式設定拓撲中的一個池，但實際上是將伺服器放在兩個不同資料中心的池中。 以相同的方式為資料庫設定 SQL Server 鏡像，並在相同的資料中心部署資料庫和鏡像。 您需要在次要資料中心中設定備份資料庫（在災害復原期間有選擇性的鏡像來提供高可用性）。 這是在災害復原期間用來進行容錯移轉的備份資料庫。

如需有關如何設定 SQL Server 鏡像以取得高可用性的詳細資料，請參閱[Lync Server 2013 中的 Sql server 鏡像](lync-server-2013-sql-server-mirroring.md)。 如需針對災難復原容錯移轉資料庫的詳細資料，請參閱[在 Lync server 2013 中設定 Sql Server 記錄傳送（針對持續聊天伺服器主要資料庫](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md)），以及[在 Lync server 2013 中的主鏡像與記錄傳送次要資料庫之間設定 Sql server 記錄傳送](lync-server-2013-set-up-log-shipping-secondary-database.md)。

</div>

<span> </span>

</div>

</div>

</div>

