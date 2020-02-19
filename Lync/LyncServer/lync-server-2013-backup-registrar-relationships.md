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
ms.openlocfilehash: 07380cbea030f5c9219cef2654b4761f215988e2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-registrar-relationships-in-lync-server-2013"></a><span data-ttu-id="0187e-102">備份 Lync Server 2013 中的登錄器關聯</span><span class="sxs-lookup"><span data-stu-id="0187e-102">Backup Registrar relationships in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0187e-103">_**主題上次修改日期：** 2012年-06-28_</span><span class="sxs-lookup"><span data-stu-id="0187e-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="0187e-104">除了提供災害復原能力之外，兩個配對的集區也可作為彼此的備份登錄器。</span><span class="sxs-lookup"><span data-stu-id="0187e-104">In addition to providing disaster recovery ability, two paired pools serve as the backup Registrars for each other.</span></span> <span data-ttu-id="0187e-105">在 Lync Server 2013 中，前端集區之間的備份登錄器關聯性，而一律 1:1 逆向。</span><span class="sxs-lookup"><span data-stu-id="0187e-105">In Lync Server 2013, backup Registrar relationships between Front End pools are always 1:1 and reciprocal.</span></span> <span data-ttu-id="0187e-106">這表示，如果 P1 是 P2 的備份，則 P2 必須是 P1 的備份，而且兩者之中的任一個不可成為其他任何前端集區的備份。</span><span class="sxs-lookup"><span data-stu-id="0187e-106">This means that if P1 is the backup for P2, then P2 must be the backup for P1, and neither can be the backup for any other Front End pool.</span></span> <span data-ttu-id="0187e-107">這是從 Lync Server 2010，前端集區的備份關係可能是多對一的變更。</span><span class="sxs-lookup"><span data-stu-id="0187e-107">This is a change from Lync Server 2010, in which Front End pool backup relationships could be many to one.</span></span>

<span data-ttu-id="0187e-108">即使兩個前端集區之間的備份關係必須是 1:1，以及進行對稱式，每個前端集區仍然可以成為任何數量的 Survivable Branch Appliance，就如同 Lync Server 2010 的備份登錄器。</span><span class="sxs-lookup"><span data-stu-id="0187e-108">Even though backup relationships between two Front End pools must be 1:1 and symmetrical, each Front End pool can still also be the backup registrar for any number of Survivable Branch Appliances, just as in Lync Server 2010.</span></span>

<span data-ttu-id="0187e-109">請注意，Lync Server 2013 不會擴充災害復原支援使用者隸屬於 Survivable Branch Appliance。</span><span class="sxs-lookup"><span data-stu-id="0187e-109">Note that Lync Server 2013 does not extend disaster recovery support to users homed on a Survivable Branch Appliance.</span></span> <span data-ttu-id="0187e-110">如果前端集區中做為備份 Survivable Branch appliance 下降，使用者登入 Survivable Branch Appliance 可分為恢復能力模式即使使用者隸屬於前端集區容錯移轉至備份的前端集區。</span><span class="sxs-lookup"><span data-stu-id="0187e-110">If a Front End pool that serves as the backup for a Survivable Branch Appliance goes down, users signed into the Survivable Branch Appliance fall into resiliency mode even after users homed on the Front End pool are failed over to the backup Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

