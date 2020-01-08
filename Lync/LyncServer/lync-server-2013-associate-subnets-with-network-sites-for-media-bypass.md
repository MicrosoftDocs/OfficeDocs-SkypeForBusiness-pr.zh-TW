---
title: Lync Server 2013：將子網與網路網站建立關聯，以進行媒體旁路
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Associate subnets with network sites for media bypass
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398401(v=OCS.15)
ms:contentKeyID: 48184244
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c0f2d6461264ff8b54609e280c59986e1a923c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40973969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="ab4ea-102">在 Lync Server 2013 中將子網與網路網站進行媒體旁路</span><span class="sxs-lookup"><span data-stu-id="ab4ea-102">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab4ea-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="ab4ea-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ab4ea-104">本主題假設您已設定媒體旁路全域設定，且已設定媒體旁路的網路區域和網路網站。</span><span class="sxs-lookup"><span data-stu-id="ab4ea-104">This topic assumes that you have configured media bypass global settings and that you have configured network region and network sites for media bypass.</span></span>



</div>

<span data-ttu-id="ab4ea-105">您網路中的每個子網都必須與特定的網路網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="ab4ea-105">Every subnet in your network must be associated with a specific network site.</span></span> <span data-ttu-id="ab4ea-106">這是因為子網資訊是用來判斷端點所在的網路網站。</span><span class="sxs-lookup"><span data-stu-id="ab4ea-106">This is because subnet information is used to determine the network site on which an endpoint is located.</span></span> <span data-ttu-id="ab4ea-107">當會話中雙方的位置都已知時，媒體旁路可以決定傳送媒體以進行處理的位置。</span><span class="sxs-lookup"><span data-stu-id="ab4ea-107">When the locations of both parties in a session are known, media bypass can determine where to send media for processing.</span></span>

<span data-ttu-id="ab4ea-108">媒體旁路不需要將子網與網路網站建立關聯的任何特殊需求。</span><span class="sxs-lookup"><span data-stu-id="ab4ea-108">Media bypass does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="ab4ea-109">若要在您的拓撲中的子網和網路網站之間建立關聯，請遵循在[Lync Server 2013 中將子網與網路網站建立](lync-server-2013-associate-a-subnet-with-a-network-site.md)關聯的程式。</span><span class="sxs-lookup"><span data-stu-id="ab4ea-109">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a><span data-ttu-id="ab4ea-110">後續步驟：建立頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="ab4ea-110">Next Steps: Create Bandwidth Policy Profiles</span></span>

<span data-ttu-id="ab4ea-111">當您將子網與網路網站進行媒體旁路的關聯之後，您必須建立一個或多個頻寬原則設定檔，將子網分割成具有良好連線性的子網，而不需要使用，就是為了媒體略過。</span><span class="sxs-lookup"><span data-stu-id="ab4ea-111">After you associate subnets with network sites for media bypass, you must create one or more bandwidth policy profiles that will partition subnets into those with good connectivity and those without, for the purposes of media bypass.</span></span> <span data-ttu-id="ab4ea-112">網路區域中的所有子網都有一個沒有頻寬限制的網路網站具有良好的連線性，因此，這些子網可以使用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="ab4ea-112">All subnets within a network region with network sites that do not have bandwidth constraints have good connectivity, and, therefore, those subnets can use media bypass.</span></span>

<span data-ttu-id="ab4ea-113">如需設定頻寬原則設定檔的程式，請參閱[在 Lync Server 2013 中建立頻寬原則設定檔](lync-server-2013-create-bandwidth-policy-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="ab4ea-113">For procedures to configure bandwidth policy profiles, see [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

