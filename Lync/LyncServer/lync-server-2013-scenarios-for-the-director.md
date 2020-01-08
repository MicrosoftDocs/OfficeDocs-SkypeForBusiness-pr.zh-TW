---
title: Lync Server 2013：Director 案例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scenarios for the Director
ms:assetid: d2cf384a-0860-4779-80ce-cba2543be322
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398908(v=OCS.15)
ms:contentKeyID: 48185419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eba35647e8ecc0cfa59d5c7c6b5c32b07bedf95e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977877"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-the-director-in-lync-server-2013"></a><span data-ttu-id="1578f-102">Lync Server 2013 中的 Director 案例</span><span class="sxs-lookup"><span data-stu-id="1578f-102">Scenarios for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1578f-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="1578f-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="1578f-104">Director 是執行 Microsoft Lync Server 2013 通訊軟體的伺服器，可驗證使用者要求，但不會家用任何使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="1578f-104">A Director is a server running Microsoft Lync Server 2013 communications software that can authenticate user requests, but does not home any user accounts.</span></span> <span data-ttu-id="1578f-105">控制器也會託管與前端伺服器類似的 web 服務，並會驗證 web 票證要求並提供其他服務。</span><span class="sxs-lookup"><span data-stu-id="1578f-105">The Director also hosts web services similar to the Front End Server and will authenticate web ticket requests and provide other services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1578f-106">如果您要部署控制器，您必須透過反向 proxy 以及前端伺服器的 web 服務，在外部發佈控制器 web 服務。</span><span class="sxs-lookup"><span data-stu-id="1578f-106">If you deploy Directors, you must publish the Director web services externally through the reverse proxy as well as the web services of the Front End Server.</span></span> <span data-ttu-id="1578f-107">下列主題說明可能的控制器拓撲的規劃程式。</span><span class="sxs-lookup"><span data-stu-id="1578f-107">The topics following describe the planning process for the possible Director topologies.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1578f-108">本節內容</span><span class="sxs-lookup"><span data-stu-id="1578f-108">In This Section</span></span>

  - [<span data-ttu-id="1578f-109">Lync Server 2013 中的 Director 概觀</span><span class="sxs-lookup"><span data-stu-id="1578f-109">Overview of the Director in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-director.md)

  - [<span data-ttu-id="1578f-110">Lync Server 2013 中 Director 的必要元件</span><span class="sxs-lookup"><span data-stu-id="1578f-110">Components required for the Director in Lync Server 2013</span></span>](lync-server-2013-components-required-for-the-director.md)

  - [<span data-ttu-id="1578f-111">Lync Server 2013 中 Director 的軟硬體需求</span><span class="sxs-lookup"><span data-stu-id="1578f-111">Hardware and software requirements for the Director in Lync Server 2013</span></span>](lync-server-2013-hardware-and-software-requirements-for-the-director.md)

  - [<span data-ttu-id="1578f-112">Lync Server 2013 中的單一 Director</span><span class="sxs-lookup"><span data-stu-id="1578f-112">Single Director in Lync Server 2013</span></span>](lync-server-2013-single-director.md)

  - [<span data-ttu-id="1578f-113">Lync Server 2013 中的調整式 Director 集區</span><span class="sxs-lookup"><span data-stu-id="1578f-113">Scaled Director pool in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1578f-114">請參閱</span><span class="sxs-lookup"><span data-stu-id="1578f-114">See Also</span></span>


[<span data-ttu-id="1578f-115">Lync Server 2013 中支援的拓撲</span><span class="sxs-lookup"><span data-stu-id="1578f-115">Supported topologies in Lync Server 2013</span></span>](lync-server-2013-supported-topologies.md)  
[<span data-ttu-id="1578f-116">Lync Server 2013 的伺服器硬體平台</span><span class="sxs-lookup"><span data-stu-id="1578f-116">Server hardware platforms for Lync Server 2013</span></span>](lync-server-2013-server-hardware-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

