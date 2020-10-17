---
title: 準備在周邊網路中安裝伺服器
description: 準備在周邊網路中安裝伺服器。
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
ms.openlocfilehash: 5689d7990cc1ddf91ad6487d8abed08f40cd3db5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549919"
---
# <a name="preparing-for-installation-of-servers-in-the-perimeter-network-for-lync-server-2013"></a><span data-ttu-id="f6d64-103">準備 Lync Server 2013 周邊網路中的伺服器安裝</span><span class="sxs-lookup"><span data-stu-id="f6d64-103">Preparing for installation of servers in the perimeter network for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6d64-104">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="f6d64-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="f6d64-105">在您安裝 Edge Server 元件之前，請先確定要安裝的電腦符合系統需求，並完成其他 Edge Server 元件部署的先決步驟。</span><span class="sxs-lookup"><span data-stu-id="f6d64-105">Before you set up Edge Server components, you need to ensure that computers that you are setting up meet system requirements and complete other prerequisite steps required for deployment of Edge Server components.</span></span>

<span data-ttu-id="f6d64-106">在您開始之前，請詳閱規劃文件中的下列主題，並查看想要部署的參考架構：</span><span class="sxs-lookup"><span data-stu-id="f6d64-106">Before you begin, review the details in the following topics in the Planning documentation for the reference architecture that you want to deploy:</span></span>

  - [<span data-ttu-id="f6d64-107">Lync Server 2013 中的單一合併 edge （利用私人 IP 位址及 NAT）</span><span class="sxs-lookup"><span data-stu-id="f6d64-107">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="f6d64-108">Lync Server 2013 中的單一合併 edge （使用公用 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="f6d64-108">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="f6d64-109">Lync Server 2013 中的調整式合併 edge （使用 NAT 透過私人 IP 位址進行 DNS 負載平衡）</span><span class="sxs-lookup"><span data-stu-id="f6d64-109">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="f6d64-110">Lync Server 2013 中的調整式合併 edge （透過公用 IP 位址進行 DNS 負載平衡）</span><span class="sxs-lookup"><span data-stu-id="f6d64-110">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="f6d64-111">Lync Server 2013 中的調整式合併 edge （搭配硬體負載平衡器）</span><span class="sxs-lookup"><span data-stu-id="f6d64-111">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>

## <a name="in-this-section"></a><span data-ttu-id="f6d64-112">本章節內容</span><span class="sxs-lookup"><span data-stu-id="f6d64-112">In This Section</span></span>

  - [<span data-ttu-id="f6d64-113">在 Lync Server 2013 中設定 edge 支援的 DNS</span><span class="sxs-lookup"><span data-stu-id="f6d64-113">Configure DNS for edge support in Lync Server 2013</span></span>](lync-server-2013-configure-dns-for-edge-support.md)

  - [<span data-ttu-id="f6d64-114">在 Lync Server 2013 中設定調整式 edge 拓撲的硬體負載平衡器</span><span class="sxs-lookup"><span data-stu-id="f6d64-114">Set up hardware load balancers for scaled edge topologies in Lync Server 2013</span></span>](lync-server-2013-set-up-hardware-load-balancers-for-scaled-edge-topologies.md)

  - [<span data-ttu-id="f6d64-115">在 Lync Server 2013 中設定外部使用者存取的防火牆和埠</span><span class="sxs-lookup"><span data-stu-id="f6d64-115">Configure firewalls and ports for external user access in Lync Server 2013</span></span>](lync-server-2013-configure-firewalls-and-ports-for-external-user-access.md)

  - [<span data-ttu-id="f6d64-116">決定 Lync Server 2013 的外部 A/V 防火牆和埠需求</span><span class="sxs-lookup"><span data-stu-id="f6d64-116">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="f6d64-117">在 Lync Server 2013 中要求 edge 元件的憑證</span><span class="sxs-lookup"><span data-stu-id="f6d64-117">Request certificates for edge components in Lync Server 2013</span></span>](lync-server-2013-request-certificates-for-edge-components.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

