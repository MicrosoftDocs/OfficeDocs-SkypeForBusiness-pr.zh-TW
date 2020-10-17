---
title: Lync Server 2013： IP 和網路通訊協定支援
description: Lync Server 2013： IP 和網路通訊協定支援。
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
ms.openlocfilehash: dbd8022dd7197524334e0c70ea0ad875a30446de
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553119"
---
# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a><span data-ttu-id="e0e33-103">Lync Server 2013 中的 IP 和網路通訊協定支援</span><span class="sxs-lookup"><span data-stu-id="e0e33-103">IP and networking protocol support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0e33-104">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="e0e33-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="e0e33-105">Lync Server 2013 支援下列 IP 和網路通訊協定：</span><span class="sxs-lookup"><span data-stu-id="e0e33-105">Lync Server 2013 supports the following IP and networking protocols:</span></span>

  - <span data-ttu-id="e0e33-106">**IP 通訊協定。**    Lync Server 2013 支援伺服器網路的 IP 版本 4 (IPv4) 或 IP 版本 6 (IPv6) 。</span><span class="sxs-lookup"><span data-stu-id="e0e33-106">**IP Protocols.**   Lync Server 2013 supports either IP version 4 (IPv4) or IP version 6 (IPv6) for the server network.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e0e33-107">在啟用雙重 IP 堆疊的網路中，Lync Server 2013 可以運作。</span><span class="sxs-lookup"><span data-stu-id="e0e33-107">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

    
    </div>

  - <span data-ttu-id="e0e33-108">**SIP 傳輸通訊協定。**    一般情況下，SIP 至少可以使用三種傳輸類型：使用者資料包協定 (UDP) 、傳輸控制通訊協定 (TCP) 及傳輸層安全性 (TLS) 。</span><span class="sxs-lookup"><span data-stu-id="e0e33-108">**SIP Transport Protocols.**   Generically, SIP can use at least three transport types: User Datagram Protocol (UDP), Transmission Control Protocol (TCP), and Transport Layer Security (TLS).</span></span> <span data-ttu-id="e0e33-109">在預設的 SIP 傳輸設定中，TLS 會透過 TCP 執行。</span><span class="sxs-lookup"><span data-stu-id="e0e33-109">In the default SIP transport configuration, TLS runs over TCP.</span></span> <span data-ttu-id="e0e33-110">TLS 是在 Lync Server 2013 網路內使用。</span><span class="sxs-lookup"><span data-stu-id="e0e33-110">TLS is used within the Lync Server 2013 network.</span></span> <span data-ttu-id="e0e33-111">在網路的 edge 中，Lync Server 2013 可以透過 TCP 進行交互操作。</span><span class="sxs-lookup"><span data-stu-id="e0e33-111">At the edge of the network, Lync Server 2013 can interoperate over TCP.</span></span> <span data-ttu-id="e0e33-112">Lync Server 2013 不支援 SIP 傳輸的 UDP，因為它不符合企業通訊安全性、可靠性和擴充性的最低標準。</span><span class="sxs-lookup"><span data-stu-id="e0e33-112">Lync Server 2013 does not support UDP for SIP transport because it doesn’t meet the minimum standards for enterprise communications security, reliability, and scalability.</span></span> <span data-ttu-id="e0e33-113">如需詳細資訊，請參閱 NextHop 的博客文章：「UDP （或不是 UDP）」，這是問題的「at」 [https://go.microsoft.com/fwlink/p/?linkId=185369](https://go.microsoft.com/fwlink/p/?linkid=185369) 。</span><span class="sxs-lookup"><span data-stu-id="e0e33-113">For details, see the NextHop blog article, "To UDP, or not to UDP, that is the question," at [https://go.microsoft.com/fwlink/p/?linkId=185369](https://go.microsoft.com/fwlink/p/?linkid=185369).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e0e33-114">每個網誌的內容及其 URL 如有變更，恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="e0e33-114">The content of each blog and its URL are subject to change without notice.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

