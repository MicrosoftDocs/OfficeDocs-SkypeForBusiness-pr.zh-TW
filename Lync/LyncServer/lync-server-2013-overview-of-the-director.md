---
title: Lync Server 2013： Director 的概覽
description: Lync Server 2013： Director 的概覽。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Director
ms:assetid: cf9919b3-e16b-47c5-be1d-2c4bc64f44ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398879(v=OCS.15)
ms:contentKeyID: 48185393
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6686534e22bab5b02a2663789298e4cf7ea582c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567629"
---
# <a name="overview-of-the-director-in-lync-server-2013"></a><span data-ttu-id="570b5-103">Lync Server 2013 中的 Director 概述</span><span class="sxs-lookup"><span data-stu-id="570b5-103">Overview of the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="570b5-104">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="570b5-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="570b5-105">Director 是一部執行 Lync Server 2013 的伺服器，可驗證使用者要求，但不會家用任何使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="570b5-105">A Director is a server running Lync Server 2013 that authenticates user requests, but does not home any user accounts.</span></span> <span data-ttu-id="570b5-106">您可以選擇在下列兩個案例中部署 Director：</span><span class="sxs-lookup"><span data-stu-id="570b5-106">You optionally can deploy a Director in the following two scenarios:</span></span>

  - <span data-ttu-id="570b5-107">如果您透過部署 Edge Server 啟用外部使用者存取，您也應該部署 Director。</span><span class="sxs-lookup"><span data-stu-id="570b5-107">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="570b5-108">在此案例中，Director 會驗證外部使用者，然後將流量傳遞給內部伺服器。</span><span class="sxs-lookup"><span data-stu-id="570b5-108">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="570b5-109">當 Director 用於驗證外部使用者時，它會從執行這些使用者驗證的開銷中免除前端集區伺服器的執行。</span><span class="sxs-lookup"><span data-stu-id="570b5-109">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="570b5-110">它也有助於將內部前端集區與惡意流量（如拒絕服務攻擊）隔離。</span><span class="sxs-lookup"><span data-stu-id="570b5-110">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="570b5-111">如果網路在這類攻擊中以不正確外部流量淹沒，這項流量會結束于 Director。</span><span class="sxs-lookup"><span data-stu-id="570b5-111">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>

  - <span data-ttu-id="570b5-112">如果您在中央網站部署多個前端集區，只要將 Director 新增至該網站，您就可以簡化驗證要求並改善效能。</span><span class="sxs-lookup"><span data-stu-id="570b5-112">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="570b5-113">在此案例中，所有要求都會先移至 Director，然後再將其路由傳送到正確的前端集區。</span><span class="sxs-lookup"><span data-stu-id="570b5-113">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

