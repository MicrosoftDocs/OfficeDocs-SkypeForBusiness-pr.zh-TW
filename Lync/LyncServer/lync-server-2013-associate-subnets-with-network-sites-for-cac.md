---
title: Lync Server 2013： 將子網路與網站的關聯的 CAC
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
ms.openlocfilehash: f325554d644282953d89fc46c183eed3756d2a07
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="7d9ea-102">將子網路與網站關聯的 Lync Server 2013 中的 CAC</span><span class="sxs-lookup"><span data-stu-id="7d9ea-102">Associate subnets with network sites for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d9ea-103">_**主題上次修改日期：** 2012年-10-20 個_</span><span class="sxs-lookup"><span data-stu-id="7d9ea-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="7d9ea-104">網路中的每個子網路都必須與特定網路網站關聯。</span><span class="sxs-lookup"><span data-stu-id="7d9ea-104">Every subnet in your network must be associated with a specific network site.</span></span> <span data-ttu-id="7d9ea-105">這是因為我們需要子網路資訊來判斷端點所在的網路網站。</span><span class="sxs-lookup"><span data-stu-id="7d9ea-105">This is because subnet information is used to determine the network site on which an endpoint is located.</span></span> <span data-ttu-id="7d9ea-106">時已知的工作階段中雙方的位置，通話許可控制 (CAC) 可以判斷是否有足夠的頻寬，若要建立通話。</span><span class="sxs-lookup"><span data-stu-id="7d9ea-106">When the locations of both parties in a session are known, call admission control (CAC) can determine if there is sufficient bandwidth to establish a call.</span></span>

<span data-ttu-id="7d9ea-107">通話許可控制並沒有任何特殊需求將子網路與網路網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="7d9ea-107">Call admission control does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="7d9ea-108">若要在您的拓樸中建立子網路與網路網站之間的關聯，請遵循中[建立關聯的子網路與網路網站在 Lync Server 2013 中](lync-server-2013-associate-a-subnet-with-a-network-site.md)的程序。</span><span class="sxs-lookup"><span data-stu-id="7d9ea-108">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span> <span data-ttu-id="7d9ea-109">若要檢視網路網站 （和其各自的子網路） 中的通話許可控制範例網路拓撲，請參閱[範例： 收集您的 Lync Server 2013 中的通話許可控制需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)中規劃文件。</span><span class="sxs-lookup"><span data-stu-id="7d9ea-109">To view the network sites (and their respective subnets) in the example network topology for call admission control, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

