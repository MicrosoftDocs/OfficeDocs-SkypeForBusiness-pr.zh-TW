---
title: Lync Server 2013：設定外部使用者存取的防火牆和連接埠
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure firewalls and ports for external user access
ms:assetid: cacb3832-f8db-4009-bfcf-6f5c15c236ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398848(v=OCS.15)
ms:contentKeyID: 48185430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 142488d35c3d5afa988be11baa688849065df066
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982521"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-firewalls-and-ports-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="ddb9d-102">在 Lync Server 2013 設定外部使用者存取的防火牆和連接埠</span><span class="sxs-lookup"><span data-stu-id="ddb9d-102">Configure firewalls and ports for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ddb9d-103">_**主題上次修改日期：** 2012-05-21_</span><span class="sxs-lookup"><span data-stu-id="ddb9d-103">_**Topic Last Modified:** 2012-05-21_</span></span>

<span data-ttu-id="ddb9d-104">若要設定防火牆和埠，您必須針對 Edge 伺服器、反向 proxy 伺服器以及可能的硬體負載平衡器（針對不使用 DNS 負載平衡的縮放部署）來設定它們。</span><span class="sxs-lookup"><span data-stu-id="ddb9d-104">To configure firewalls and ports, you need to configure them for Edge Servers, reverse proxy servers, and possibly hardware load balancers (for a scaled deployment that does not use DNS load balancing).</span></span> <span data-ttu-id="ddb9d-105">本節提供所有邊緣伺服器元件的防火牆和埠需求，以及邊緣伺服器的防火牆埠設定的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ddb9d-105">This section provides information about firewall and port requirements for all Edge Server components and the configuration of firewall ports for Edge Servers.</span></span> <span data-ttu-id="ddb9d-106">如需有關設定反向 proxy 伺服器埠的詳細資料，請參閱[設定 Lync Server 2013 的反向 proxy 伺服器](lync-server-2013-setting-up-reverse-proxy-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="ddb9d-106">For details about configuring ports for reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md).</span></span> <span data-ttu-id="ddb9d-107">如果您要部署經過比例調整的邊緣拓撲，且使用的是硬體負載平衡（而非 DNS 負載平衡），請參閱在規劃檔中[使用硬體2013負載平衡器調整合並邊緣](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)，以取得有關為硬體負載平衡器設定埠的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ddb9d-107">If you are deploying a scaled edge topology and are using hardware load balancing instead of DNS load balancing, see [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md) in the Planning documentation for details about configuring ports for hardware load balancers.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="ddb9d-108">請參閱</span><span class="sxs-lookup"><span data-stu-id="ddb9d-108">See Also</span></span>


[<span data-ttu-id="ddb9d-109">決定 Lync Server 2013 的外部 A/V 防火牆和連接埠需求</span><span class="sxs-lookup"><span data-stu-id="ddb9d-109">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

