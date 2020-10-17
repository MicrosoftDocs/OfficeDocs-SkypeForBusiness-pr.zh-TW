---
title: 使用延伸的持久聊天伺服器集區進行嚴重損壞修復
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
ms.openlocfilehash: 1c09231abfae7bbcc32083d7db72d8a4be79ecff
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535920"
---
# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a>在 Lync Server 2013 中使用延伸的持久聊天伺服器集區進行嚴重損壞修復

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

Persistent Chat Server 的嚴重損壞復原解決方案是在延伸的持久聊天伺服器集區上建立。 這與 Lync Server 2010 中的大都市網站恢復功能類似;不過，不需要延伸虛擬區域網路絡 (VLAN) 。 透過拉伸 Persistent Chat Server 集區，您基本上會以邏輯方式設定拓撲中的一個集區，但實際將伺服器集放在兩個不同資料中心的集區中。 以相同的方式設定資料庫的 SQL Server 鏡像，並在相同的資料中心部署資料庫和鏡像。 您必須在次要資料中心設定備份資料庫 (包含於災害復原期間提供高可用性的選用鏡像)。 此為在災害復原期間用於容錯移轉的備份資料庫。

如需如何設定 SQL Server 鏡像以取得高可用性的詳細資訊，請參閱 [Lync server 2013 中的 SQL server 鏡像](lync-server-2013-sql-server-mirroring.md)。 如需容錯移轉資料庫容錯移轉的相關詳細資訊，請參閱2013在 lync server 2013 中 [為 Persistent Chat server 主資料庫設定 Sql Server 記錄傳送](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) ，並 [設定主要鏡像與記錄傳送次要資料庫之間的 Sql server 記錄傳送](lync-server-2013-set-up-log-shipping-secondary-database.md)。

</div>

<span> </span>

</div>

</div>

</div>

