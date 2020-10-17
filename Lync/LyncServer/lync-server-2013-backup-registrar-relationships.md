---
title: Lync Server 2013 備份註冊機構關係
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
ms.openlocfilehash: cd41595fed0d16327f65f4e6af39fe80c049daa4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499330"
---
# <a name="backup-registrar-relationships-in-lync-server-2013"></a><span data-ttu-id="a8fd6-102">Lync Server 2013 中的備份註冊器關聯</span><span class="sxs-lookup"><span data-stu-id="a8fd6-102">Backup Registrar relationships in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8fd6-103">_**主題上次修改日期：** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="a8fd6-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="a8fd6-104">除了提供災害復原能力之外，兩個配對的集區也可作為彼此的備份登錄器。</span><span class="sxs-lookup"><span data-stu-id="a8fd6-104">In addition to providing disaster recovery ability, two paired pools serve as the backup Registrars for each other.</span></span> <span data-ttu-id="a8fd6-105">在 Lync Server 2013 中，前端集區之間的備份註冊器關聯性永遠都是1:1 和互惠。</span><span class="sxs-lookup"><span data-stu-id="a8fd6-105">In Lync Server 2013, backup Registrar relationships between Front End pools are always 1:1 and reciprocal.</span></span> <span data-ttu-id="a8fd6-106">這表示，如果 P1 是 P2 的備份，則 P2 必須是 P1 的備份，而且兩者之中的任一個不可成為其他任何前端集區的備份。</span><span class="sxs-lookup"><span data-stu-id="a8fd6-106">This means that if P1 is the backup for P2, then P2 must be the backup for P1, and neither can be the backup for any other Front End pool.</span></span> <span data-ttu-id="a8fd6-107">這是 Lync Server 2010 所做的變更，前端集區的備份關係可能會是多達一個。</span><span class="sxs-lookup"><span data-stu-id="a8fd6-107">This is a change from Lync Server 2010, in which Front End pool backup relationships could be many to one.</span></span>

<span data-ttu-id="a8fd6-108">即使兩個前端集區之間的備份關係必須是1:1 及對稱式，每個前端集區也仍然可以是任何數目的 Survivable 分支裝置的備份註冊機構，就像在 Lync Server 2010 中一樣。</span><span class="sxs-lookup"><span data-stu-id="a8fd6-108">Even though backup relationships between two Front End pools must be 1:1 and symmetrical, each Front End pool can still also be the backup registrar for any number of Survivable Branch Appliances, just as in Lync Server 2010.</span></span>

<span data-ttu-id="a8fd6-109">請注意，Lync Server 2013 不會將嚴重損壞修復支援擴充至位於 Survivable 分支裝置的使用者。</span><span class="sxs-lookup"><span data-stu-id="a8fd6-109">Note that Lync Server 2013 does not extend disaster recovery support to users homed on a Survivable Branch Appliance.</span></span> <span data-ttu-id="a8fd6-110">如果充當 Survivable 分支裝置備份的前端集區中斷，即使在前端集區上的使用者已容錯移轉至備份前端集區之後，登入 Survivable Branch 裝置的使用者也會進入復原模式。</span><span class="sxs-lookup"><span data-stu-id="a8fd6-110">If a Front End pool that serves as the backup for a Survivable Branch Appliance goes down, users signed into the Survivable Branch Appliance fall into resiliency mode even after users homed on the Front End pool are failed over to the backup Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

