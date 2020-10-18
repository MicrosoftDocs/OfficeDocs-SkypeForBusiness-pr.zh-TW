---
title: Lync Server 2013：新的嚴重損壞修復和高可用性功能
description: Lync Server 2013：新的嚴重損壞修復和高可用性功能。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92816f61b66d9eed76c16286aaa6c7392dca7708
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578859"
---
# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a>Lync Server 2013 中新的嚴重損壞修復和高可用性功能

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-20_

在 Lync Server 2010 中，Lync Server 2013 的主要高可用性 (HA) 模式是透過 pooling server 冗余度為基礎。 如果執行特定伺服器角色的伺服器失敗，集區中執行相同角色的其他伺服器就會接手該伺服器的負載。 這適用於前端伺服器、Edge Server、中繼伺服器和 Director。

Lync Server 2013 可讓您將位於兩個資料中心的前端集區配對，以加入新的嚴重損壞修復措施。 如果配對的集區中有一個故障，系統管理員可以將使用者從該集區容錯移轉至配對中的另一個集區，以便繼續提供服務。 這項功能不需要昂貴的網路或硬體解決方案，例如存放網路或共用磁碟。

Lync Server 2013 也新增後端伺服器高可用性。 這是選用的拓撲，您可以在其中部署前端集區的兩部後端伺服器，並為在後端伺服器上執行的所有 Lync 資料庫設定同步 SQL 鏡像。 您可以選擇是否要部署鏡像見證。

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中規劃高可用性和嚴重損壞修復](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

