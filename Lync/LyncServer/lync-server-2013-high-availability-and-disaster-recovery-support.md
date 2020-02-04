---
title: Lync Server 2013：高可用性和災害復原支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: High availability and disaster recovery support
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204866(v=OCS.15)
ms:contentKeyID: 48184053
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b73f6605f2fff063858a0180d61a306f7dd2d746
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a>Lync Server 2013 中的高可用性和災害復原支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-25_

Lync Server 2013 透過 [彙集]，透過伺服器冗余提供高可用性。 如果執行特定伺服器角色的伺服器失敗，則池中執行相同角色的其他伺服器會載入該伺服器。 這適用于前端伺服器、邊緣伺服器、轉送伺服器和控制器。 如需伺服器角色的詳細資料，請參閱[Lync server 2013 中的伺服器角色](lync-server-2013-server-roles.md)。

Lync Server 2013 也會透過啟用池配對來提供災害復原措施。 如果您部署這個拓朴，您將會指定一組前端池，其中每個池都位於另一個資料中心，且位於不同的地理區域中。 如果有一個池或網站停機，您可以重新導向該池的使用者，以使用該集中的其他池，並最少中斷服務。

Lync Server 2013 也支援後端伺服器高可用性。 這是一種選用拓朴，您可以在其中部署前端池的兩個後端伺服器，並針對在後端伺服器上執行的所有 Lync 資料庫，設定同步處理的 SQL Server 鏡像。

如需有關池配對與後端伺服器鏡像的詳細資料，請參閱[在 Lync Server 2013 中規劃高可用性和災害復原](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的伺服器角色](lync-server-2013-server-roles.md)  
[在 Lync Server 2013 中規劃高可用性和災害復原](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

