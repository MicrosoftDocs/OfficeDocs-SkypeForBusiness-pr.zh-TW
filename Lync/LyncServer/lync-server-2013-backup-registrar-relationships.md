---
title: Lync Server 2013 備份登錄器關聯
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup Registrar relationships
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205033(v=OCS.15)
ms:contentKeyID: 48184631
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ac47dcda07d7c0ca368cc572ccfafe2c6c95b2f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-registrar-relationships-in-lync-server-2013"></a>備份 Lync Server 2013 中的登錄器關聯

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-06-28_

除了提供災害復原能力之外，兩個配對的集區也可作為彼此的備份登錄器。 在 Lync Server 2013 中，前端集區之間的備份登錄器關聯性，而一律 1:1 逆向。 這表示，如果 P1 是 P2 的備份，則 P2 必須是 P1 的備份，而且兩者之中的任一個不可成為其他任何前端集區的備份。 這是從 Lync Server 2010，前端集區的備份關係可能是多對一的變更。

即使兩個前端集區之間的備份關係必須是 1:1，以及進行對稱式，每個前端集區仍然可以成為任何數量的 Survivable Branch Appliance，就如同 Lync Server 2010 的備份登錄器。

請注意，Lync Server 2013 不會擴充災害復原支援使用者隸屬於 Survivable Branch Appliance。 如果前端集區中做為備份 Survivable Branch appliance 下降，使用者登入 Survivable Branch Appliance 可分為恢復能力模式即使使用者隸屬於前端集區容錯移轉至備份的前端集區。

</div>

<span> </span>

</div>

</div>

</div>

