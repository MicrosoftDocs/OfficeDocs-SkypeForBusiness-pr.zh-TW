---
title: Lync Server 2013 的連接埠需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port requirements
ms:assetid: 9a6c1300-ef88-4181-a8f1-43cd3093962b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398798(v=OCS.15)
ms:contentKeyID: 48184886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4ac38534f7d52aca3df9c24cac10be10dee5be6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-requirements-for-lync-server-2013"></a><span data-ttu-id="8bebc-102">Lync Server 2013 的連接埠需求</span><span class="sxs-lookup"><span data-stu-id="8bebc-102">Port requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bebc-103">_**上次修改主題：** 2013 年 03 月 27 日_</span><span class="sxs-lookup"><span data-stu-id="8bebc-103">_**Topic Last Modified:** 2013-03-27_</span></span>

<span data-ttu-id="8bebc-104">Lync Server 必須開啟防火牆上的特定連接埠。</span><span class="sxs-lookup"><span data-stu-id="8bebc-104">Lync Server requires that specific ports on the firewall be open.</span></span> <span data-ttu-id="8bebc-105">此外，如果您組織中部署網際網路通訊協定安全性 (IPsec)，IPsec 必須停用透過用於傳遞的音訊、 視訊和 panorama 視訊的連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="8bebc-105">Additionally, if Internet Protocol security (IPsec) is deployed in your organization, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8bebc-106">本章節內容</span><span class="sxs-lookup"><span data-stu-id="8bebc-106">In This Section</span></span>

<span data-ttu-id="8bebc-107">本節包含下列主題：</span><span class="sxs-lookup"><span data-stu-id="8bebc-107">This section includes the following topics:</span></span>

  - [<span data-ttu-id="8bebc-108">連接埠和通訊協定適用於 Lync Server 2013 中的內部伺服器</span><span class="sxs-lookup"><span data-stu-id="8bebc-108">Ports and protocols for internal servers in Lync Server 2013</span></span>](lync-server-2013-ports-and-protocols-for-internal-servers.md)

  - [<span data-ttu-id="8bebc-109">Lync Server 2013 中的 IPsec 例外</span><span class="sxs-lookup"><span data-stu-id="8bebc-109">IPsec exceptions in Lync Server 2013</span></span>](lync-server-2013-ipsec-exceptions.md)

  - [<span data-ttu-id="8bebc-110">連接埠摘要-單一合併式 edge 與 Lync Server 2013 中使用 NAT 的私人 IP 位址</span><span class="sxs-lookup"><span data-stu-id="8bebc-110">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="8bebc-111">連接埠摘要-單一合併邊緣搭配 Lync Server 2013 中的公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="8bebc-111">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="8bebc-112">連接埠摘要-調整式合併 edge、 DNS 負載平衡與 Lync Server 2013 中使用 NAT 的私人 IP 位址</span><span class="sxs-lookup"><span data-stu-id="8bebc-112">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="8bebc-113">連接埠摘要-調整式合併 edge、 DNS 負載平衡與 Lync Server 2013 中的公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="8bebc-113">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="8bebc-114">連接埠摘要-調整式合併邊緣搭配硬體負載平衡器在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bebc-114">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="8bebc-115">連接埠摘要-Lync Server 2013 中的反向 proxy</span><span class="sxs-lookup"><span data-stu-id="8bebc-115">Port summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-port-summary-reverse-proxy.md)

  - [<span data-ttu-id="8bebc-116">連接埠摘要-SIP，XMPP 同盟和公用立即訊息在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bebc-116">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

