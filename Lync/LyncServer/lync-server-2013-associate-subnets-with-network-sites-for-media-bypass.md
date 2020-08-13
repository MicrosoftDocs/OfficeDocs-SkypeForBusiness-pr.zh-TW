---
title: Lync Server 2013：將子網與媒體旁路的網路網站產生關聯
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for media bypass
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398401(v=OCS.15)
ms:contentKeyID: 48184244
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5565be047443ebb0bf84358a592dc0b1f9314c8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="4eb4d-102">在 Lync Server 2013 中將子網與媒體旁路的網站建立關聯</span><span class="sxs-lookup"><span data-stu-id="4eb4d-102">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4eb4d-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="4eb4d-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4eb4d-104">本主題假定您已經設定好媒體旁路全域設定，以及媒體旁路的網路區域與網路網站。</span><span class="sxs-lookup"><span data-stu-id="4eb4d-104">This topic assumes that you have configured media bypass global settings and that you have configured network region and network sites for media bypass.</span></span>



</div>

<span data-ttu-id="4eb4d-p101">網路中的每個子網路都必須與特定網路網站關聯。這是因為我們需要子網路資訊來判斷端點所在的網路網站。一旦知道工作階段中的雙方位置，媒體旁路就能判斷出要將媒體傳送到何處以便處理。</span><span class="sxs-lookup"><span data-stu-id="4eb4d-p101">Every subnet in your network must be associated with a specific network site. This is because subnet information is used to determine the network site on which an endpoint is located. When the locations of both parties in a session are known, media bypass can determine where to send media for processing.</span></span>

<span data-ttu-id="4eb4d-108">媒體旁路不需要任何特殊需求，就能將子網路與網路網站進行關聯。</span><span class="sxs-lookup"><span data-stu-id="4eb4d-108">Media bypass does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="4eb4d-109">若要在拓撲中建立子網與網站之間的關聯性，請遵循在[Lync Server 2013 中將子網與網路網站關聯](lync-server-2013-associate-a-subnet-with-a-network-site.md)的程式。</span><span class="sxs-lookup"><span data-stu-id="4eb4d-109">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a><span data-ttu-id="4eb4d-110">後續步驟：建立頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="4eb4d-110">Next Steps: Create Bandwidth Policy Profiles</span></span>

<span data-ttu-id="4eb4d-p103">當您為媒體旁路需要將子網路與網站關聯之後，必須建立一個或多個頻寬原則設定檔，以將子網路分割為具有良好連線能力與不具備良好連線能力的子網路，以因應媒體旁路所需。當網路地區內的所有子網路與沒有頻寬限制的網站關聯時，將提供良好的連線能力，因此這些子網路可以使用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="4eb4d-p103">After you associate subnets with network sites for media bypass, you must create one or more bandwidth policy profiles that will partition subnets into those with good connectivity and those without, for the purposes of media bypass. All subnets within a network region with network sites that do not have bandwidth constraints have good connectivity, and, therefore, those subnets can use media bypass.</span></span>

<span data-ttu-id="4eb4d-113">如需設定頻寬原則設定檔的程式，請參閱[在 Lync Server 2013 中建立頻寬原則設定檔](lync-server-2013-create-bandwidth-policy-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="4eb4d-113">For procedures to configure bandwidth policy profiles, see [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

