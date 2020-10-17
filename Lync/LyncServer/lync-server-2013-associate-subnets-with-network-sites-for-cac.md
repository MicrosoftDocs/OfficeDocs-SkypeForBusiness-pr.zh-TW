---
title: Lync Server 2013：將子網與 CAC 的網路網站產生關聯
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for CAC
ms:assetid: a749c9b3-15f3-4e74-9f43-1507d3c2c940
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412786(v=OCS.15)
ms:contentKeyID: 48185017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fde0eb443a643371072c4c0018c05e2cd4538d0e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531600"
---
# <a name="associate-subnets-with-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="fbc08-102">在 Lync Server 2013 中將子網與 CAC 的網路網站產生關聯</span><span class="sxs-lookup"><span data-stu-id="fbc08-102">Associate subnets with network sites for CAC in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbc08-103">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="fbc08-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="fbc08-104">網路中的每個子網路都必須與特定網路網站關聯。</span><span class="sxs-lookup"><span data-stu-id="fbc08-104">Every subnet in your network must be associated with a specific network site.</span></span> <span data-ttu-id="fbc08-105">這是因為我們需要子網路資訊來判斷端點所在的網路網站。</span><span class="sxs-lookup"><span data-stu-id="fbc08-105">This is because subnet information is used to determine the network site on which an endpoint is located.</span></span> <span data-ttu-id="fbc08-106">當會話中雙方雙方的位置都已知時，通話許可控制 (CAC) 可以判斷是否有足夠的頻寬可以建立通話。</span><span class="sxs-lookup"><span data-stu-id="fbc08-106">When the locations of both parties in a session are known, call admission control (CAC) can determine if there is sufficient bandwidth to establish a call.</span></span>

<span data-ttu-id="fbc08-107">通話許可控制沒有任何將子網與網站相關聯的特殊需求。</span><span class="sxs-lookup"><span data-stu-id="fbc08-107">Call admission control does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="fbc08-108">若要在拓撲中建立子網與網站之間的關聯性，請遵循在 [Lync Server 2013 中將子網與網路網站關聯](lync-server-2013-associate-a-subnet-with-a-network-site.md)的程式。</span><span class="sxs-lookup"><span data-stu-id="fbc08-108">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span> <span data-ttu-id="fbc08-109">若要在通話許可控制的範例網路拓撲中查看網路網站 (及其各自的子網) ，請參閱規劃檔中的 [範例：在 Lync Server 2013 中收集通話許可控制需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 。</span><span class="sxs-lookup"><span data-stu-id="fbc08-109">To view the network sites (and their respective subnets) in the example network topology for call admission control, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

