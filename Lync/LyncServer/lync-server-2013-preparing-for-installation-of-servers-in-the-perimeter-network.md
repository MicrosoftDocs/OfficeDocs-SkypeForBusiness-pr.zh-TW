---
title: 準備在周邊網路中安裝伺服器
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
ms.openlocfilehash: a28fc1e77a98e2a6123537ec5c062dca5d0c6ffb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-for-installation-of-servers-in-the-perimeter-network-for-lync-server-2013"></a><span data-ttu-id="13547-102">在周邊網路中準備安裝 Lync Server 2013 的伺服器</span><span class="sxs-lookup"><span data-stu-id="13547-102">Preparing for installation of servers in the perimeter network for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13547-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="13547-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="13547-104">在您設定邊緣伺服器元件之前，必須先確定您設定的電腦符合系統需求，並完成部署 Edge 伺服器元件所需的其他必要步驟。</span><span class="sxs-lookup"><span data-stu-id="13547-104">Before you set up Edge Server components, you need to ensure that computers that you are setting up meet system requirements and complete other prerequisite steps required for deployment of Edge Server components.</span></span>

<span data-ttu-id="13547-105">開始之前，請先查看下列主題中的詳細資料，瞭解您要部署之參考體系結構的規劃檔：</span><span class="sxs-lookup"><span data-stu-id="13547-105">Before you begin, review the details in the following topics in the Planning documentation for the reference architecture that you want to deploy:</span></span>

  - [<span data-ttu-id="13547-106">Lync Server 2013 中的單一合併 Edge (利用私人 IP 位址及 NAT)</span><span class="sxs-lookup"><span data-stu-id="13547-106">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="13547-107">Lync Server 2013 中的單一合併 Edge (利用公用 IP 位址)</span><span class="sxs-lookup"><span data-stu-id="13547-107">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="13547-108">Lync Server 2013 中的調整式合併 Edge (使用 NAT 透過私人 IP 位址進行 DNS 負載平衡)</span><span class="sxs-lookup"><span data-stu-id="13547-108">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="13547-109">Lync Server 2013 中的調整式合併 Edge (透過公用 IP 位址進行 DNS 負載平衡)</span><span class="sxs-lookup"><span data-stu-id="13547-109">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="13547-110">Lync Server 2013 中含硬體負載平衡器的調整式合併 Edge</span><span class="sxs-lookup"><span data-stu-id="13547-110">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>

## <a name="in-this-section"></a><span data-ttu-id="13547-111">本節內容</span><span class="sxs-lookup"><span data-stu-id="13547-111">In This Section</span></span>

  - [<span data-ttu-id="13547-112">在 Lync Server 2013 中設定 Edge 支援的 DNS</span><span class="sxs-lookup"><span data-stu-id="13547-112">Configure DNS for edge support in Lync Server 2013</span></span>](lync-server-2013-configure-dns-for-edge-support.md)

  - [<span data-ttu-id="13547-113">在 Lync Server 2013 中設定調整式 Edge 拓撲的硬體負載平衡器</span><span class="sxs-lookup"><span data-stu-id="13547-113">Set up hardware load balancers for scaled edge topologies in Lync Server 2013</span></span>](lync-server-2013-set-up-hardware-load-balancers-for-scaled-edge-topologies.md)

  - [<span data-ttu-id="13547-114">在 Lync Server 2013 設定外部使用者存取的防火牆和連接埠</span><span class="sxs-lookup"><span data-stu-id="13547-114">Configure firewalls and ports for external user access in Lync Server 2013</span></span>](lync-server-2013-configure-firewalls-and-ports-for-external-user-access.md)

  - [<span data-ttu-id="13547-115">決定 Lync Server 2013 的外部 A/V 防火牆和連接埠需求</span><span class="sxs-lookup"><span data-stu-id="13547-115">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="13547-116">在 Lync Server 2013 中要求 Edge 元件的憑證</span><span class="sxs-lookup"><span data-stu-id="13547-116">Request certificates for edge components in Lync Server 2013</span></span>](lync-server-2013-request-certificates-for-edge-components.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

