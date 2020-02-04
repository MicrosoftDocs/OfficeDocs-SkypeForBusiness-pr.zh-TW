---
title: Lync Server 2013：IP 和網路通訊協定支援
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
ms.openlocfilehash: 285ed0d383b09276979ad6e29c390e2fc22a1caf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a><span data-ttu-id="47085-102">Lync Server 2013 中的 IP 和網路通訊協定支援</span><span class="sxs-lookup"><span data-stu-id="47085-102">IP and networking protocol support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47085-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="47085-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="47085-104">Lync Server 2013 支援下列 IP 和網路通訊協定：</span><span class="sxs-lookup"><span data-stu-id="47085-104">Lync Server 2013 supports the following IP and networking protocols:</span></span>

  - <span data-ttu-id="47085-105">**IP 通訊協定。**   Lync server 2013 支援伺服器網路的 ip 版本4（IPv4）或 ip 版本6（IPv6）。</span><span class="sxs-lookup"><span data-stu-id="47085-105">**IP Protocols.**   Lync Server 2013 supports either IP version 4 (IPv4) or IP version 6 (IPv6) for the server network.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="47085-106">在啟用雙 IP 堆疊的網路中，Lync Server 2013 可以正常運作。</span><span class="sxs-lookup"><span data-stu-id="47085-106">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

    
    </div>

  - <span data-ttu-id="47085-107">**SIP 傳輸通訊協定。**   一般情況下，SIP 最少可以使用三種傳輸類型：使用者資料包協定（UDP）、傳輸控制通訊協定（TCP），以及傳輸層安全性（TLS）。</span><span class="sxs-lookup"><span data-stu-id="47085-107">**SIP Transport Protocols.**   Generically, SIP can use at least three transport types: User Datagram Protocol (UDP), Transmission Control Protocol (TCP), and Transport Layer Security (TLS).</span></span> <span data-ttu-id="47085-108">在預設 SIP 傳輸配置中，TLS 會在 TCP 上執行。</span><span class="sxs-lookup"><span data-stu-id="47085-108">In the default SIP transport configuration, TLS runs over TCP.</span></span> <span data-ttu-id="47085-109">TLS 是在 Lync Server 2013 網路中使用。</span><span class="sxs-lookup"><span data-stu-id="47085-109">TLS is used within the Lync Server 2013 network.</span></span> <span data-ttu-id="47085-110">在網路邊緣，Lync Server 2013 可以在 TCP 上進行交互操作。</span><span class="sxs-lookup"><span data-stu-id="47085-110">At the edge of the network, Lync Server 2013 can interoperate over TCP.</span></span> <span data-ttu-id="47085-111">Lync Server 2013 不支援 SIP 傳輸的 UDP，因為它不符合企業通訊安全性、可靠性及可伸縮性的最低標準。</span><span class="sxs-lookup"><span data-stu-id="47085-111">Lync Server 2013 does not support UDP for SIP transport because it doesn’t meet the minimum standards for enterprise communications security, reliability, and scalability.</span></span> <span data-ttu-id="47085-112">如需詳細資訊，請參閱 NextHop 博客文章、「UDP （或不是 UDP），也就是 "at [http://go.microsoft.com/fwlink/p/?linkId=185369](http://go.microsoft.com/fwlink/p/?linkid=185369)" 問題。</span><span class="sxs-lookup"><span data-stu-id="47085-112">For details, see the NextHop blog article, "To UDP, or not to UDP, that is the question," at [http://go.microsoft.com/fwlink/p/?linkId=185369](http://go.microsoft.com/fwlink/p/?linkid=185369).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="47085-113">每個博客及其 URL 的內容可能會變更，恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="47085-113">The content of each blog and its URL are subject to change without notice.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

