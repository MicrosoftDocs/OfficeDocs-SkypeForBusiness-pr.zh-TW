---
title: Lync Server 2013：高可用性和嚴重損壞修復支援
description: Lync Server 2013：高可用性和嚴重損壞修復支援。
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
ms.openlocfilehash: a8113c6b54cbb55e8149f8d6dd1b53ccbdc9436d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552789"
---
# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a>Lync Server 2013 的高可用性和嚴重損壞修復支援

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-25_

Lync Server 2013 透過 pooling 透過伺服器的冗余度，提供高可用性。 如果執行特定伺服器角色的伺服器失敗，集區中執行相同角色的其他伺服器就會接手該伺服器的負載。 這適用於前端伺服器、Edge Server、中繼伺服器和 Director。 如需伺服器角色的詳細資訊，請參閱 [Lync server 2013 中的伺服器角色](lync-server-2013-server-roles.md)。

Lync Server 2013 也會啟用集區配對，以提供嚴重損壞修復措施。 如果您部署這個拓樸，將會指定前端集區配對，每一對中各個集區都位在不同的資料中心，並且在不同的地理區。 如果一個集區或網站故障，您可以重新導向該集區的使用者，以使用該配對中另一個集區，讓服務中斷時間降至最低。

Lync Server 2013 也支援後端伺服器高可用性。 這是選用的拓撲，您可以在其中部署前端集區的兩部後端伺服器，並為在後端伺服器上執行的所有 Lync 資料庫設定同步 SQL Server 鏡像。

如需有關集區配對及後端伺服器鏡像的詳細資訊，請參閱 [在 Lync Server 2013 中規劃高可用性和嚴重損壞修復](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的伺服器角色](lync-server-2013-server-roles.md)  
[在 Lync Server 2013 中規劃高可用性和嚴重損壞修復](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

