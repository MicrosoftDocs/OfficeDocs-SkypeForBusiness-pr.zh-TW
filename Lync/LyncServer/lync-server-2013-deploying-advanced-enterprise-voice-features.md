---
title: Lync Server 2013：部署高級企業語音功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying advanced Enterprise Voice features
ms:assetid: 286d9c0b-9442-448f-a6e5-95b3034278fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425753(v=OCS.15)
ms:contentKeyID: 48183675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fff128d98f82745e471f39e8f172c6ddb7a8a52
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975540"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-advanced-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="0b91a-102">在 Lync Server 2013 中部署高級企業語音功能</span><span class="sxs-lookup"><span data-stu-id="0b91a-102">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b91a-103">_**主題上次修改日期：** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="0b91a-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="0b91a-104">為貴組織設定基本的企業語音功能之後，您可以根據本節中的程式，選擇部署一或多個高級企業語音功能。</span><span class="sxs-lookup"><span data-stu-id="0b91a-104">After you have configured basic Enterprise Voice functionality for your organization, you can optionally deploy one or more advanced Enterprise Voice features by following the procedures in this section.</span></span>

<span data-ttu-id="0b91a-105">如需有關高級企業語音功能的詳細資訊，請參閱[Lync Server 2013 規劃](lync-server-2013-planning.md)的下列各節：</span><span class="sxs-lookup"><span data-stu-id="0b91a-105">For details about the advanced Enterprise Voice features, see the following sections of the [Planning for Lync Server 2013](lync-server-2013-planning.md) documentation:</span></span>

  - [<span data-ttu-id="0b91a-106">在 Lync Server 2013 中規劃通話許可控制</span><span class="sxs-lookup"><span data-stu-id="0b91a-106">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="0b91a-107">在 Lync Server 2013 中規劃緊急服務 (E9-1-1)</span><span class="sxs-lookup"><span data-stu-id="0b91a-107">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="0b91a-108">在 Lync Server 2013 中規劃媒體旁路</span><span class="sxs-lookup"><span data-stu-id="0b91a-108">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

<div>

## <a name="in-this-section"></a><span data-ttu-id="0b91a-109">本節內容</span><span class="sxs-lookup"><span data-stu-id="0b91a-109">In This Section</span></span>

  - [<span data-ttu-id="0b91a-110">關於 Lync Server 2013 中的網路區域、網站和子網路</span><span class="sxs-lookup"><span data-stu-id="0b91a-110">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="0b91a-111">在 Lync Server 2013 中建立或修改網路區域</span><span class="sxs-lookup"><span data-stu-id="0b91a-111">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)

  - [<span data-ttu-id="0b91a-112">在 Lync Server 2013 中建立或修改網站</span><span class="sxs-lookup"><span data-stu-id="0b91a-112">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)

  - [<span data-ttu-id="0b91a-113">在 Lync Server 2013 中建立子網路與網路站台的關聯</span><span class="sxs-lookup"><span data-stu-id="0b91a-113">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)

  - [<span data-ttu-id="0b91a-114">在 Lync Server 2013 中設定通話許可控制</span><span class="sxs-lookup"><span data-stu-id="0b91a-114">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)

  - [<span data-ttu-id="0b91a-115">在 Lync Server 2013 中設定增強型 9-1-1</span><span class="sxs-lookup"><span data-stu-id="0b91a-115">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-enhanced-9-1-1.md)

  - [<span data-ttu-id="0b91a-116">在 Lync Server 2013 中設定媒體旁路</span><span class="sxs-lookup"><span data-stu-id="0b91a-116">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

