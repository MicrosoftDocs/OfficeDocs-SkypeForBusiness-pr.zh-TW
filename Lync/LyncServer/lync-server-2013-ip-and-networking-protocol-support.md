---
title: 'Lync Server 2013: IP 和網路通訊協定支援'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP and networking protocol support
ms:assetid: b0cffb10-3478-445c-89c7-8cb8b5027424
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412848(v=OCS.15)
ms:contentKeyID: 48185128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d413c53f8f6600170cf7ec7bfdcca8b052101eca
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a><span data-ttu-id="5018c-102">Lync Server 2013 中的 IP 和網路通訊協定支援</span><span class="sxs-lookup"><span data-stu-id="5018c-102">IP and networking protocol support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5018c-103">_**主題上次修改日期：** 2012年-09-21_</span><span class="sxs-lookup"><span data-stu-id="5018c-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="5018c-104">Lync Server 2013 支援下列 IP 和網路通訊協定：</span><span class="sxs-lookup"><span data-stu-id="5018c-104">Lync Server 2013 supports the following IP and networking protocols:</span></span>

  - <span data-ttu-id="5018c-105">**IP 通訊協定。**   Lync Server 2013 的伺服器網路支援 IP 版本 4 (IPv4) 或 IP 版本 6 (IPv6)。</span><span class="sxs-lookup"><span data-stu-id="5018c-105">**IP Protocols.**   Lync Server 2013 supports either IP version 4 (IPv4) or IP version 6 (IPv6) for the server network.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5018c-106">Lync Server 2013 可以在啟用雙重 IP 堆疊的網路中運作。</span><span class="sxs-lookup"><span data-stu-id="5018c-106">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

    
    </div>

  - <span data-ttu-id="5018c-107">**SIP 傳輸通訊協定。**   SIP 代，可以使用，至少有三種傳輸類型： 使用者資料包通訊協定 (UDP)、 傳輸控制通訊協定 (TCP) 和傳輸層安全性 (TLS)。</span><span class="sxs-lookup"><span data-stu-id="5018c-107">**SIP Transport Protocols.**   Generically, SIP can use at least three transport types: User Datagram Protocol (UDP), Transmission Control Protocol (TCP), and Transport Layer Security (TLS).</span></span> <span data-ttu-id="5018c-108">在 [預設 SIP 傳輸組態中，TLS 執行 over TCP。</span><span class="sxs-lookup"><span data-stu-id="5018c-108">In the default SIP transport configuration, TLS runs over TCP.</span></span> <span data-ttu-id="5018c-109">TLS 用在 Lync Server 2013 網路內。</span><span class="sxs-lookup"><span data-stu-id="5018c-109">TLS is used within the Lync Server 2013 network.</span></span> <span data-ttu-id="5018c-110">在網路邊緣，Lync Server 2013 可以透過 TCP 交互操作。</span><span class="sxs-lookup"><span data-stu-id="5018c-110">At the edge of the network, Lync Server 2013 can interoperate over TCP.</span></span> <span data-ttu-id="5018c-111">Lync Server 2013 不支援 UDP SIP 傳輸因為它不符合企業通訊安全性、 可靠性與延展性的下限標準。</span><span class="sxs-lookup"><span data-stu-id="5018c-111">Lync Server 2013 does not support UDP for SIP transport because it doesn’t meet the minimum standards for enterprise communications security, reliability, and scalability.</span></span> <span data-ttu-id="5018c-112">如需詳細資訊，請參閱 NextHop 部落格文章，「 UDP，或不 UDP，是問題，" [https://go.microsoft.com/fwlink/p/?linkId=185369](https://go.microsoft.com/fwlink/p/?linkid=185369)。</span><span class="sxs-lookup"><span data-stu-id="5018c-112">For details, see the NextHop blog article, "To UDP, or not to UDP, that is the question," at [https://go.microsoft.com/fwlink/p/?linkId=185369](https://go.microsoft.com/fwlink/p/?linkid=185369).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5018c-113">每個網誌的內容及其 URL 如有變更，恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="5018c-113">The content of each blog and its URL are subject to change without notice.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

