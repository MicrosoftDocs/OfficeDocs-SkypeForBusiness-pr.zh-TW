---
title: Lync Server 2013：設定外部使用者存取的防火牆和埠
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure firewalls and ports for external user access
ms:assetid: cacb3832-f8db-4009-bfcf-6f5c15c236ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398848(v=OCS.15)
ms:contentKeyID: 48185430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8f8ac768256a45e908905e3eed1c0fc343b6da9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213129"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-firewalls-and-ports-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="9319d-102">在 Lync Server 2013 中設定外部使用者存取的防火牆和埠</span><span class="sxs-lookup"><span data-stu-id="9319d-102">Configure firewalls and ports for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9319d-103">_**主題上次修改日期：** 2012-05-21_</span><span class="sxs-lookup"><span data-stu-id="9319d-103">_**Topic Last Modified:** 2012-05-21_</span></span>

<span data-ttu-id="9319d-104">若要設定防火牆及埠，您需要針對不使用 DNS 負載平衡) 的縮放部署，針對 Edge Server、反向 proxy 伺服器及可能的硬體負載 (平衡器進行設定。</span><span class="sxs-lookup"><span data-stu-id="9319d-104">To configure firewalls and ports, you need to configure them for Edge Servers, reverse proxy servers, and possibly hardware load balancers (for a scaled deployment that does not use DNS load balancing).</span></span> <span data-ttu-id="9319d-105">本節提供所有 Edge Server 元件的防火牆和埠需求，以及 Edge server 之防火牆埠的設定相關資訊。</span><span class="sxs-lookup"><span data-stu-id="9319d-105">This section provides information about firewall and port requirements for all Edge Server components and the configuration of firewall ports for Edge Servers.</span></span> <span data-ttu-id="9319d-106">如需設定反向 proxy 伺服器埠的詳細資訊，請參閱[設定 Lync Server 2013 的反向 proxy 伺服器](lync-server-2013-setting-up-reverse-proxy-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="9319d-106">For details about configuring ports for reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md).</span></span> <span data-ttu-id="9319d-107">如果您部署的是調整式 edge 拓撲，而且使用硬體負載平衡，而不是使用 DNS 負載平衡，請參閱規劃檔中的[調整式合併 edge （Lync Server 2013 中的硬體負載](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)平衡器），以取得設定硬體負載平衡器埠的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="9319d-107">If you are deploying a scaled edge topology and are using hardware load balancing instead of DNS load balancing, see [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md) in the Planning documentation for details about configuring ports for hardware load balancers.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="9319d-108">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9319d-108">See Also</span></span>


[<span data-ttu-id="9319d-109">決定 Lync Server 2013 的外部 A/V 防火牆和埠需求</span><span class="sxs-lookup"><span data-stu-id="9319d-109">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

