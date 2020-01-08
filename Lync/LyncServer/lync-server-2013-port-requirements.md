---
title: Lync Server 2013 埠需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port requirements
ms:assetid: 9a6c1300-ef88-4181-a8f1-43cd3093962b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398798(v=OCS.15)
ms:contentKeyID: 48184886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fddb9e1ad518196b3ac2ac1d8c5d2dc0ebeac972
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-requirements-for-lync-server-2013"></a><span data-ttu-id="ebdee-102">Lync Server 2013 的埠需求</span><span class="sxs-lookup"><span data-stu-id="ebdee-102">Port requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebdee-103">_**主題上次修改日期：** 2013-03-27_</span><span class="sxs-lookup"><span data-stu-id="ebdee-103">_**Topic Last Modified:** 2013-03-27_</span></span>

<span data-ttu-id="ebdee-104">Lync Server 要求防火牆上的特定埠已開啟。</span><span class="sxs-lookup"><span data-stu-id="ebdee-104">Lync Server requires that specific ports on the firewall be open.</span></span> <span data-ttu-id="ebdee-105">此外，如果您的組織中部署了網際網路通訊協定安全性（IPsec），則必須停用傳送音訊、影片和全景影片的埠範圍所使用的 IPsec。</span><span class="sxs-lookup"><span data-stu-id="ebdee-105">Additionally, if Internet Protocol security (IPsec) is deployed in your organization, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ebdee-106">本節內容</span><span class="sxs-lookup"><span data-stu-id="ebdee-106">In This Section</span></span>

<span data-ttu-id="ebdee-107">本節包含下列主題：</span><span class="sxs-lookup"><span data-stu-id="ebdee-107">This section includes the following topics:</span></span>

  - [<span data-ttu-id="ebdee-108">Lync Server 2013 內部伺服器的埠和通訊協定</span><span class="sxs-lookup"><span data-stu-id="ebdee-108">Ports and protocols for internal servers in Lync Server 2013</span></span>](lync-server-2013-ports-and-protocols-for-internal-servers.md)

  - [<span data-ttu-id="ebdee-109">Lync Server 2013 中的 IPsec 例外狀況</span><span class="sxs-lookup"><span data-stu-id="ebdee-109">IPsec exceptions in Lync Server 2013</span></span>](lync-server-2013-ipsec-exceptions.md)

  - [<span data-ttu-id="ebdee-110">Lync Server 2013 中的連接埠摘要 - 單一合併 Edge (使用 NAT 透過私人 IP 位址)</span><span class="sxs-lookup"><span data-stu-id="ebdee-110">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="ebdee-111">Lync Server 2013 中的連接埠摘要 - 含公用 IP 位址的單一合併 Edge</span><span class="sxs-lookup"><span data-stu-id="ebdee-111">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="ebdee-112">Lync Server 2013 中的連接埠摘要 - 調整式合併 Edge (使用 NAT 透過私人 IP 位址進行 DNS 負載平衡)</span><span class="sxs-lookup"><span data-stu-id="ebdee-112">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="ebdee-113">Lync Server 2013 中的連接埠摘要 - 調整式合併 Edge (利用公用 IP 位址進行 DNS 負載平衡)</span><span class="sxs-lookup"><span data-stu-id="ebdee-113">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="ebdee-114">Lync Server 2013 中的連接埠摘要 - 調整式合併 Edge (利用硬體負載平衡器)</span><span class="sxs-lookup"><span data-stu-id="ebdee-114">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="ebdee-115">Lync Server 2013 中的連接埠摘要 - 反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="ebdee-115">Port summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-port-summary-reverse-proxy.md)

  - [<span data-ttu-id="ebdee-116">埠摘要-Lync Server 2013 中的 SIP、XMPP 同盟及公用立即訊息</span><span class="sxs-lookup"><span data-stu-id="ebdee-116">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

