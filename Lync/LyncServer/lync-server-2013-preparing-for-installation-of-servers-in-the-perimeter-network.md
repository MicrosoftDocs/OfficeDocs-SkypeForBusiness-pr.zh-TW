---
title: 準備安裝在周邊網路中的伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing for installation of servers in the perimeter network
ms:assetid: 5e6c457a-f964-4ef7-a709-97abda9c673a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398416(v=OCS.15)
ms:contentKeyID: 48184292
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31c0cbd7355b5ac51908a9a7eba2ae0e6b6680ed
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139124"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-for-installation-of-servers-in-the-perimeter-network-for-lync-server-2013"></a><span data-ttu-id="7503d-102">準備安裝 Lync Server 2013 的周邊網路中的伺服器</span><span class="sxs-lookup"><span data-stu-id="7503d-102">Preparing for installation of servers in the perimeter network for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7503d-103">_**主題上次修改日期：** 2012年-09-08_</span><span class="sxs-lookup"><span data-stu-id="7503d-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="7503d-104">在您安裝 Edge Server 元件之前，請先確定要安裝的電腦符合系統需求，並完成其他 Edge Server 元件部署的先決步驟。</span><span class="sxs-lookup"><span data-stu-id="7503d-104">Before you set up Edge Server components, you need to ensure that computers that you are setting up meet system requirements and complete other prerequisite steps required for deployment of Edge Server components.</span></span>

<span data-ttu-id="7503d-105">在您開始之前，請詳閱規劃文件中的下列主題，並查看想要部署的參考架構：</span><span class="sxs-lookup"><span data-stu-id="7503d-105">Before you begin, review the details in the following topics in the Planning documentation for the reference architecture that you want to deploy:</span></span>

  - [<span data-ttu-id="7503d-106">私人 IP 位址及 NAT Lync Server 2013 中的單一合併的 edge</span><span class="sxs-lookup"><span data-stu-id="7503d-106">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="7503d-107">與 Lync Server 2013 中的公用 IP 位址的單一合併的 edge</span><span class="sxs-lookup"><span data-stu-id="7503d-107">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="7503d-108">調整式合併的 edge、 DNS 負載平衡與 Lync Server 2013 中使用 NAT 的私人 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7503d-108">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="7503d-109">調整式合併的 edge、 DNS 負載平衡與 Lync Server 2013 中的公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7503d-109">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="7503d-110">Lync Server 2013 中調整式合併的邊緣搭配硬體負載平衡器</span><span class="sxs-lookup"><span data-stu-id="7503d-110">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>

## <a name="in-this-section"></a><span data-ttu-id="7503d-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="7503d-111">In This Section</span></span>

  - [<span data-ttu-id="7503d-112">設定 Lync Server 2013 中的 edge 支援的 DNS</span><span class="sxs-lookup"><span data-stu-id="7503d-112">Configure DNS for edge support in Lync Server 2013</span></span>](lync-server-2013-configure-dns-for-edge-support.md)

  - [<span data-ttu-id="7503d-113">設定 Lync Server 2013 中的調整式的 edge 拓撲的硬體負載平衡器</span><span class="sxs-lookup"><span data-stu-id="7503d-113">Set up hardware load balancers for scaled edge topologies in Lync Server 2013</span></span>](lync-server-2013-set-up-hardware-load-balancers-for-scaled-edge-topologies.md)

  - [<span data-ttu-id="7503d-114">在 Lync Server 2013 中設定防火牆和連接埠的外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="7503d-114">Configure firewalls and ports for external user access in Lync Server 2013</span></span>](lync-server-2013-configure-firewalls-and-ports-for-external-user-access.md)

  - [<span data-ttu-id="7503d-115">決定外部 A / V 防火牆和連接埠需求 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7503d-115">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="7503d-116">適用於 Lync Server 2013 中的 edge 元件的要求憑證</span><span class="sxs-lookup"><span data-stu-id="7503d-116">Request certificates for edge components in Lync Server 2013</span></span>](lync-server-2013-request-certificates-for-edge-components.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

