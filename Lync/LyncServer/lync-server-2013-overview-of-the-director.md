---
title: Director 的 Lync Server 2013： 概觀
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
ms.openlocfilehash: 2ac09f5ca7ed67b078b3d5313982cff4af38e835
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140056"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-director-in-lync-server-2013"></a><span data-ttu-id="b526e-102">Lync Server 2013 中 Director 概觀</span><span class="sxs-lookup"><span data-stu-id="b526e-102">Overview of the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b526e-103">_**主題上次修改日期：** 2012年-09-08_</span><span class="sxs-lookup"><span data-stu-id="b526e-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="b526e-104">Director 是執行 Lync Server 2013 的驗證使用者要求，但不會主控任何使用者帳戶的伺服器。</span><span class="sxs-lookup"><span data-stu-id="b526e-104">A Director is a server running Lync Server 2013 that authenticates user requests, but does not home any user accounts.</span></span> <span data-ttu-id="b526e-105">（選用） 可以部署 Director 下列兩種案例：</span><span class="sxs-lookup"><span data-stu-id="b526e-105">You optionally can deploy a Director in the following two scenarios:</span></span>

  - <span data-ttu-id="b526e-106">如果您藉由部署 Edge Server 啟用外部使用者存取，您也應該部署 Director。</span><span class="sxs-lookup"><span data-stu-id="b526e-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="b526e-107">在此案例中，Director 驗證外部使用者，並接著將傳遞它們登入內部伺服器的流量。</span><span class="sxs-lookup"><span data-stu-id="b526e-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="b526e-108">Director 來驗證外部使用者使用時，它會減輕前端集區伺服器執行驗證這些使用者的額外負荷。</span><span class="sxs-lookup"><span data-stu-id="b526e-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="b526e-109">它也可協助將內部前端集區隔離惡意流量，例如拒絕服務攻擊。</span><span class="sxs-lookup"><span data-stu-id="b526e-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="b526e-110">無效的外部流量，在這類攻擊大量湧入網路時，此流量結束 Director。</span><span class="sxs-lookup"><span data-stu-id="b526e-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>

  - <span data-ttu-id="b526e-111">如果您將部署在中央網站的多個前端集區，藉由將 Director 新增至該網站可以簡化驗證要求，並改善效能。</span><span class="sxs-lookup"><span data-stu-id="b526e-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="b526e-112">在此案例中，所有要求都前往第一個 Director，然後將它們路由傳送至正確的前端集區。</span><span class="sxs-lookup"><span data-stu-id="b526e-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

