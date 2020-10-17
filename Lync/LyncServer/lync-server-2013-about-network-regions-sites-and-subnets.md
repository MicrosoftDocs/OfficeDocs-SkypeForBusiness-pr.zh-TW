---
title: Lync Server 2013：關於網路地區、網站及子網
description: Lync Server 2013：關於網路地區、網站及子網。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: About network regions, sites, and subnets
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48184335
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3c7f660f3c72003527e0721c3f9702865e9b9b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568929"
---
# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="0d2f5-103">關於 Lync Server 2013 中的網路地區、網站和子網</span><span class="sxs-lookup"><span data-stu-id="0d2f5-103">About network regions, sites, and subnets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d2f5-104">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="0d2f5-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="0d2f5-p101">本節所說明的進階 Enterprise Voice 功能共用網路地區、網站及子網路的特定設定需求。例如，這三個進階功能都需要拓撲中的每個子網路與特定 *「網站」* 相關聯，而且每個網站都必須與 *「網路地區」* 相關聯。</span><span class="sxs-lookup"><span data-stu-id="0d2f5-p101">The advanced Enterprise Voice features described in this section share certain configuration requirements for network regions, network sites, and subnets. For example, all three advanced features require that each subnet in your topology be associated with a specific *network site*, and each network site must be associated with a *network region*.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0d2f5-107">在您開始進行通話許可控制、E9-1-1 或媒體旁路的網路設定之前，請確定您已在規劃檔中的「 <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013</A> 」主題中查看有關網路設定的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="0d2f5-107">Before you begin network configuration for call admission control, E9-1-1, or media bypass, make sure that you reviewed additional information about network settings in the <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A> topic in the Planning documentation.</span></span> <span data-ttu-id="0d2f5-108">如需主要關於通話許可控制之網路設定的詳細資訊，請參閱規劃檔中的在 <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013 中定義通話許可控制的需求</A> 。</span><span class="sxs-lookup"><span data-stu-id="0d2f5-108">For details about network configuration primarily about call admission control, also see <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<span data-ttu-id="0d2f5-109">通話許可控制及 E9-1-1 具有其他的網站設定需求：</span><span class="sxs-lookup"><span data-stu-id="0d2f5-109">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>

  - <span data-ttu-id="0d2f5-110">通話許可控制需要指定透過 WAN 頻寬限制所限制之每個網站的 *「頻寬原則設定檔」*。</span><span class="sxs-lookup"><span data-stu-id="0d2f5-110">Call admission control requires that a *bandwidth policy profile* be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="0d2f5-111">如果您打算部署通話許可控制，您必須先 [在 Lync Server 2013 中建立頻寬原則設定檔](lync-server-2013-create-bandwidth-policy-profiles.md) ，再設定網路網站。</span><span class="sxs-lookup"><span data-stu-id="0d2f5-111">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>

  - <span data-ttu-id="0d2f5-112">E9-1-1 需要指定每個網站的 *「位置原則」*。</span><span class="sxs-lookup"><span data-stu-id="0d2f5-112">E9-1-1 requires that a *location policy* be specified for each site.</span></span> <span data-ttu-id="0d2f5-113">如果您打算部署 E9-1-1，您必須先 [在 Lync Server 2013 中建立位置原則](lync-server-2013-create-location-policies.md) ，再設定網站。</span><span class="sxs-lookup"><span data-stu-id="0d2f5-113">If you plan to deploy E9-1-1, you must [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) before you configure your network sites.</span></span>

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a><span data-ttu-id="0d2f5-114">建立或修改網路地區、網站及子網路</span><span class="sxs-lookup"><span data-stu-id="0d2f5-114">Create or Modify Network Regions, Network Sites, and Subnets</span></span>

<span data-ttu-id="0d2f5-p105">下列主題提供網路地區及網站的建立或修改步驟，以及將子網路與網站相關聯的步驟。這些不是任何特定進階 Enterprise Voice 功能特有的主題。</span><span class="sxs-lookup"><span data-stu-id="0d2f5-p105">The following topics provide steps to create or modify network regions and network sites, and to associate subnets with network sites. These topics are not specific to any particular advanced Enterprise Voice feature.</span></span>

  - [<span data-ttu-id="0d2f5-117">在 Lync Server 2013 中建立或修改網路地區</span><span class="sxs-lookup"><span data-stu-id="0d2f5-117">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)

  - [<span data-ttu-id="0d2f5-118">在 Lync Server 2013 中建立或修改網路網站</span><span class="sxs-lookup"><span data-stu-id="0d2f5-118">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)

  - [<span data-ttu-id="0d2f5-119">在 Lync Server 2013 中建立子網與網路網站的關聯</span><span class="sxs-lookup"><span data-stu-id="0d2f5-119">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

