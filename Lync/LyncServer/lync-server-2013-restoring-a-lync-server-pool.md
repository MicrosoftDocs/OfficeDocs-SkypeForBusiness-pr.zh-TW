---
title: Lync Server 2013：還原 Lync Server 池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Lync Server pool
ms:assetid: 6fe80fb3-38ad-4931-a07b-1763b61aa448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202176(v=OCS.15)
ms:contentKeyID: 51541488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f43cbe049fdedc2f0b4d31eecc4a0506a4a62201
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-lync-server-pool-in-lync-server-2013"></a><span data-ttu-id="1a6f4-102">在 Lync Server 2013 中還原 Lync Server 文件庫</span><span class="sxs-lookup"><span data-stu-id="1a6f4-102">Restoring a Lync Server pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a6f4-103">_**主題上次修改日期：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="1a6f4-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="1a6f4-104">您的 Lync Server 部署可能會包含下列任何一種類型的 pool：</span><span class="sxs-lookup"><span data-stu-id="1a6f4-104">Your Lync Server deployment may include any of the following types of pools:</span></span>

  - <span data-ttu-id="1a6f4-105">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="1a6f4-105">Front End Server</span></span>

  - <span data-ttu-id="1a6f4-106">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="1a6f4-106">Mediation Server</span></span>

  - <span data-ttu-id="1a6f4-107">常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="1a6f4-107">Persistent Chat Server</span></span>

  - <span data-ttu-id="1a6f4-108">Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="1a6f4-108">Edge Server</span></span>

<span data-ttu-id="1a6f4-109">如果整個池遇到中斷，請針對池中的每個成員伺服器，按照這些程式執行。</span><span class="sxs-lookup"><span data-stu-id="1a6f4-109">If an entire pool experiences an outage, follow these procedures for each member server in the pool.</span></span>

  - <span data-ttu-id="1a6f4-110">如果是前端池，請先還原後端伺服器，然後還原每個前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="1a6f4-110">For a Front End pool, restore the Back End Server first, and then restore each Front End Server.</span></span> <span data-ttu-id="1a6f4-111">如需詳細資訊，請參閱[在 Lync server 2013 中還原企業版後端伺服器](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)，並[在 lync Server 2013 中還原企業版成員伺服器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。</span><span class="sxs-lookup"><span data-stu-id="1a6f4-111">For details, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) and [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

  - <span data-ttu-id="1a6f4-112">針對所有其他類型的 pool，請還原每個成員伺服器。</span><span class="sxs-lookup"><span data-stu-id="1a6f4-112">For all other types of pools, restore each member server.</span></span> <span data-ttu-id="1a6f4-113">如需詳細資訊，請參閱[在 Lync server 2013 中還原企業版成員伺服器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。</span><span class="sxs-lookup"><span data-stu-id="1a6f4-113">For details, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

