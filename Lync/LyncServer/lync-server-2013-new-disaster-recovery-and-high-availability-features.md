---
title: Lync Server 2013：新的災害復原和高可用性功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e93e2265d401c6dca16f5c00c339fbdc893aba0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a>Lync Server 2013 中新的災害復原和高可用性功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-20_

就像在 Lync Server 2010 中，Lync Server 2013 的主要高可用性（HA）配置是透過「池」以伺服器冗余為基礎。 如果執行特定伺服器角色的伺服器失敗，則池中執行相同角色的其他伺服器會載入該伺服器。 這適用于前端伺服器、邊緣伺服器、轉送伺服器和控制器。

Lync Server 2013 可讓您對位於兩個資料中心的前端池進行配對，以新增災害復原量值。 如果其中一個配對的池向下，系統管理員可以將該池中的使用者容錯移轉至該組中的另一個池，以提供服務的延續。 此功能不需要昂貴的網路或硬體解決方案（例如儲存網路或共用磁片）。

Lync Server 2013 也會新增後端伺服器高可用性。 這是一種選用拓朴，您可以在其中部署前端池的兩個後端伺服器，並針對在後端伺服器上執行的所有 Lync 資料庫，設定同步處理的 SQL 鏡像。 您可以選擇是否要為鏡像部署見證。

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中規劃高可用性和災害復原](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

