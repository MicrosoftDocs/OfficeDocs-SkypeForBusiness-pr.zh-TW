---
title: Lync Server 2013： Edge 伺服器與功能的 DNS 需求
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
ms.openlocfilehash: 9e9f0cb2eb68ed29984811f1c42a97dab4693a2f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-edge-servers-and-features-in-lync-server-2013"></a><span data-ttu-id="c0250-102">Lync Server 2013 中 Edge 伺服器與功能的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="c0250-102">DNS requirements for Edge Servers and features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0250-103">_**主題上次修改日期：** 2014-04-08_</span><span class="sxs-lookup"><span data-stu-id="c0250-103">_**Topic Last Modified:** 2014-04-08_</span></span>

<span data-ttu-id="c0250-104">Lync Server 2013 Edge 伺服器、邊緣池及反向代理程式都有對網域名稱系統（DNS）記錄的特定需求。</span><span class="sxs-lookup"><span data-stu-id="c0250-104">Lync Server 2013 Edge Servers, Edge pools, and reverse proxies have specific requirements for Domain Name System (DNS) records.</span></span> <span data-ttu-id="c0250-105">在 Lync Server 2013 中，當您使用 IPv4 與 IPv6 時，您必須規劃主機 A 和 AAAA 記錄。</span><span class="sxs-lookup"><span data-stu-id="c0250-105">In Lync Server 2013 when IPv4 and IPv6 are in use, you must plan for both host A and AAAA records.</span></span>

<span data-ttu-id="c0250-106">下列主題定義您的部署規劃的 DNS 記錄的使用方式：</span><span class="sxs-lookup"><span data-stu-id="c0250-106">The topics listed below define the use of DNS records for your deployment planning:</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c0250-107">本節內容</span><span class="sxs-lookup"><span data-stu-id="c0250-107">In This Section</span></span>

  - [<span data-ttu-id="c0250-108">Lync Server 2013 中的 DNS 摘要 - 單一合併 Edge (使用 NAT 透過私人 IP 位址)</span><span class="sxs-lookup"><span data-stu-id="c0250-108">DNS summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="c0250-109">Lync Server 2013 中的 DNS 摘要 - 單一合併 Edge (利用公用 IP 位址)</span><span class="sxs-lookup"><span data-stu-id="c0250-109">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="c0250-110">Lync Server 2013 中的 DNS 摘要 - 調整式合併 Edge (使用 NAT 透過私人 IP 位址進行 DNS 負載平衡)</span><span class="sxs-lookup"><span data-stu-id="c0250-110">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="c0250-111">Lync Server 2013 中的 DNS 摘要 - 調整式合併 Edge (透過公用 IP 位址進行 DNS 負載平衡)</span><span class="sxs-lookup"><span data-stu-id="c0250-111">DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="c0250-112">Lync Server 2013 中的 DNS 摘要 - 調整式合併 Edge (利用硬體負載平衡器)</span><span class="sxs-lookup"><span data-stu-id="c0250-112">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="c0250-113">Lync Server 2013 中的 DNS 摘要 - 反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="c0250-113">DNS summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-dns-summary-reverse-proxy.md)

  - [<span data-ttu-id="c0250-114">DNS 摘要-Lync Server 2013 中的 SIP、XMPP 同盟及公用立即訊息</span><span class="sxs-lookup"><span data-stu-id="c0250-114">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

