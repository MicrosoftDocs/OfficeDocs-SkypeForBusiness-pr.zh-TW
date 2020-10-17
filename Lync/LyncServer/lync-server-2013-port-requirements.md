---
title: Lync Server 2013 埠需求
description: Lync Server 2013 埠需求。
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
ms.openlocfilehash: ba7ae9a1ee098f55c61ae476f12c3b856c69f90e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543159"
---
# <a name="port-requirements-for-lync-server-2013"></a><span data-ttu-id="88067-103">Lync Server 2013 的埠需求</span><span class="sxs-lookup"><span data-stu-id="88067-103">Port requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88067-104">_**主題上次修改日期：** 2013-03-27_</span><span class="sxs-lookup"><span data-stu-id="88067-104">_**Topic Last Modified:** 2013-03-27_</span></span>

<span data-ttu-id="88067-105">Lync Server 要求開啟防火牆上的特定埠。</span><span class="sxs-lookup"><span data-stu-id="88067-105">Lync Server requires that specific ports on the firewall be open.</span></span> <span data-ttu-id="88067-106">此外，如果您的組織中已部署網際網路通訊協定安全性 (IPsec) ，IPsec 必須透過用於傳遞音訊、影片及全景影片的埠範圍加以停用。</span><span class="sxs-lookup"><span data-stu-id="88067-106">Additionally, if Internet Protocol security (IPsec) is deployed in your organization, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="88067-107">本章節內容</span><span class="sxs-lookup"><span data-stu-id="88067-107">In This Section</span></span>

<span data-ttu-id="88067-108">本節包含下列主題：</span><span class="sxs-lookup"><span data-stu-id="88067-108">This section includes the following topics:</span></span>

  - [<span data-ttu-id="88067-109">Lync Server 2013 中內部伺服器的埠與通訊協定</span><span class="sxs-lookup"><span data-stu-id="88067-109">Ports and protocols for internal servers in Lync Server 2013</span></span>](lync-server-2013-ports-and-protocols-for-internal-servers.md)

  - [<span data-ttu-id="88067-110">Lync Server 2013 中的 IPsec 例外狀況</span><span class="sxs-lookup"><span data-stu-id="88067-110">IPsec exceptions in Lync Server 2013</span></span>](lync-server-2013-ipsec-exceptions.md)

  - [<span data-ttu-id="88067-111">Lync Server 2013 中的埠摘要-單一合併 edge （使用 NAT 透過私人 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="88067-111">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="88067-112">Lync Server 2013 中的埠摘要-含公用 IP 位址的單一合併 edge</span><span class="sxs-lookup"><span data-stu-id="88067-112">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="88067-113">在 Lync Server 2013 中，埠摘要-調整式合併 edge （使用 NAT 透過私人 IP 位址進行 DNS 負載平衡）</span><span class="sxs-lookup"><span data-stu-id="88067-113">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="88067-114">Lync Server 2013 中的埠摘要-調整式合併 edge （透過公用 IP 位址進行 DNS 負載平衡）</span><span class="sxs-lookup"><span data-stu-id="88067-114">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="88067-115">Lync Server 2013 中的埠摘要-調整式合併 edge （使用硬體負載平衡器）</span><span class="sxs-lookup"><span data-stu-id="88067-115">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="88067-116">Lync Server 2013 中的埠摘要-反向 proxy</span><span class="sxs-lookup"><span data-stu-id="88067-116">Port summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-port-summary-reverse-proxy.md)

  - [<span data-ttu-id="88067-117">Lync Server 2013 中的埠摘要-SIP、XMPP 同盟和公用立即訊息</span><span class="sxs-lookup"><span data-stu-id="88067-117">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

