---
title: 'Lync Server 2013: Edge Server 和功能的 DNS 需求'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Edge Servers and features
ms:assetid: e3bf05c8-96fb-4dd2-acb1-f0d141c9e2ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721912(v=OCS.15)
ms:contentKeyID: 49733846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3de2c3404a581d7cabb544a89eed43d3c4572a6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-edge-servers-and-features-in-lync-server-2013"></a><span data-ttu-id="42b5e-102">Edge Server 和 Lync Server 2013 中的功能的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="42b5e-102">DNS requirements for Edge Servers and features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42b5e-103">_**上次修改主題：** 2014年-04-08_</span><span class="sxs-lookup"><span data-stu-id="42b5e-103">_**Topic Last Modified:** 2014-04-08_</span></span>

<span data-ttu-id="42b5e-104">Lync Server 2013 Edge Server、 Edge 集區] 和反向 proxy 有網域名稱系統 (DNS) 記錄的特定需求。</span><span class="sxs-lookup"><span data-stu-id="42b5e-104">Lync Server 2013 Edge Servers, Edge pools, and reverse proxies have specific requirements for Domain Name System (DNS) records.</span></span> <span data-ttu-id="42b5e-105">Lync Server 2013 中 IPv4 和 IPv6 中時，請使用，您必須規劃的主機 A 和 AAAA 記錄。</span><span class="sxs-lookup"><span data-stu-id="42b5e-105">In Lync Server 2013 when IPv4 and IPv6 are in use, you must plan for both host A and AAAA records.</span></span>

<span data-ttu-id="42b5e-106">下面所列的主題定義在部署規劃使用 DNS 記錄：</span><span class="sxs-lookup"><span data-stu-id="42b5e-106">The topics listed below define the use of DNS records for your deployment planning:</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="42b5e-107">本章節內容</span><span class="sxs-lookup"><span data-stu-id="42b5e-107">In This Section</span></span>

  - [<span data-ttu-id="42b5e-108">DNS 摘要-單一合併式 edge 與 Lync Server 2013 中使用 NAT 的私人 IP 位址</span><span class="sxs-lookup"><span data-stu-id="42b5e-108">DNS summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="42b5e-109">DNS 摘要-單一合併邊緣搭配 Lync Server 2013 中的公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="42b5e-109">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="42b5e-110">DNS 摘要-調整式合併 edge、 DNS 負載平衡與 Lync Server 2013 中使用 NAT 的私人 IP 位址</span><span class="sxs-lookup"><span data-stu-id="42b5e-110">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="42b5e-111">DNS 摘要-調整式合併 edge、 DNS 負載平衡與 Lync Server 2013 中的公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="42b5e-111">DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="42b5e-112">DNS 摘要-調整式合併邊緣搭配硬體負載平衡器在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42b5e-112">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="42b5e-113">DNS 摘要-Lync Server 2013 中的反向 proxy</span><span class="sxs-lookup"><span data-stu-id="42b5e-113">DNS summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-dns-summary-reverse-proxy.md)

  - [<span data-ttu-id="42b5e-114">DNS 摘要-SIP，XMPP 同盟和公用立即訊息在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42b5e-114">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

