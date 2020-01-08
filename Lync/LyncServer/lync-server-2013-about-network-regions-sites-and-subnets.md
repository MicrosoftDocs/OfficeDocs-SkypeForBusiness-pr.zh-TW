---
title: Lync Server 2013：關於網路區域、網站和子網路
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: About network regions, sites, and subnets
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48184335
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef6601a0baafd1226f4e283d62a8cbdb410064ff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="e946f-102">關於 Lync Server 2013 中的網路區域、網站和子網路</span><span class="sxs-lookup"><span data-stu-id="e946f-102">About network regions, sites, and subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e946f-103">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="e946f-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="e946f-104">此區段中所述的 [高級企業語音功能] 共用網路區域、網路網站和子網的特定設定需求。</span><span class="sxs-lookup"><span data-stu-id="e946f-104">The advanced Enterprise Voice features described in this section share certain configuration requirements for network regions, network sites, and subnets.</span></span> <span data-ttu-id="e946f-105">例如，三個高級功能都要求拓撲中的每個子網都與特定的*網路網站*相關聯，且每個網路網站都必須與一個*網路區域*建立關聯。</span><span class="sxs-lookup"><span data-stu-id="e946f-105">For example, all three advanced features require that each subnet in your topology be associated with a specific *network site*, and each network site must be associated with a *network region*.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e946f-106">在您開始進行呼叫許可控制、E9-1 或媒體旁路的網路設定之前，請務必在規劃檔中查看<A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013</A>主題中的 [網路設定] 中的 [網路設定] 中的其他相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e946f-106">Before you begin network configuration for call admission control, E9-1-1, or media bypass, make sure that you reviewed additional information about network settings in the <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A> topic in the Planning documentation.</span></span> <span data-ttu-id="e946f-107">如需有關網路設定的詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013 中的通話許可控制需求</A>。</span><span class="sxs-lookup"><span data-stu-id="e946f-107">For details about network configuration primarily about call admission control, also see <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<span data-ttu-id="e946f-108">[通話許可控制] 和 [E9-1-1] 有網路網站的其他配置需求：</span><span class="sxs-lookup"><span data-stu-id="e946f-108">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>

  - <span data-ttu-id="e946f-109">呼叫許可控制要求為受 WAN 頻寬限制所限制的每個網站指定*頻寬原則設定檔*。</span><span class="sxs-lookup"><span data-stu-id="e946f-109">Call admission control requires that a *bandwidth policy profile* be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="e946f-110">如果您打算部署通話許可控制，您必須先[在 Lync Server 2013 中建立頻寬原則設定檔](lync-server-2013-create-bandwidth-policy-profiles.md)，然後才能設定您的網路網站。</span><span class="sxs-lookup"><span data-stu-id="e946f-110">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>

  - <span data-ttu-id="e946f-111">E9-1-1-1 需要為每個網站指定*位置原則*。</span><span class="sxs-lookup"><span data-stu-id="e946f-111">E9-1-1 requires that a *location policy* be specified for each site.</span></span> <span data-ttu-id="e946f-112">如果您打算部署 E9-1-1，您必須先[在 Lync Server 2013 中建立位置原則](lync-server-2013-create-location-policies.md)，才能設定您的網路網站。</span><span class="sxs-lookup"><span data-stu-id="e946f-112">If you plan to deploy E9-1-1, you must [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) before you configure your network sites.</span></span>

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a><span data-ttu-id="e946f-113">建立或修改網路區域、網路網站和子網</span><span class="sxs-lookup"><span data-stu-id="e946f-113">Create or Modify Network Regions, Network Sites, and Subnets</span></span>

<span data-ttu-id="e946f-114">下列主題提供建立或修改網路區域和網路網站的步驟，以及將子網與網路網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="e946f-114">The following topics provide steps to create or modify network regions and network sites, and to associate subnets with network sites.</span></span> <span data-ttu-id="e946f-115">這些主題不是任何特定的高級企業語音功能所特有。</span><span class="sxs-lookup"><span data-stu-id="e946f-115">These topics are not specific to any particular advanced Enterprise Voice feature.</span></span>

  - [<span data-ttu-id="e946f-116">在 Lync Server 2013 中建立或修改網路區域</span><span class="sxs-lookup"><span data-stu-id="e946f-116">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)

  - [<span data-ttu-id="e946f-117">在 Lync Server 2013 中建立或修改網站</span><span class="sxs-lookup"><span data-stu-id="e946f-117">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)

  - [<span data-ttu-id="e946f-118">在 Lync Server 2013 中建立子網路與網路站台的關聯</span><span class="sxs-lookup"><span data-stu-id="e946f-118">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

