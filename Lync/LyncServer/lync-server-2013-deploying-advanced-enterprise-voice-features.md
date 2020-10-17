---
title: Lync Server 2013：部署 advanced Enterprise Voice 功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying advanced Enterprise Voice features
ms:assetid: 286d9c0b-9442-448f-a6e5-95b3034278fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425753(v=OCS.15)
ms:contentKeyID: 48183675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7172a80342e88e6f58d233ee3a69abfd813196c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531330"
---
# <a name="deploying-advanced-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="e9334-102">在 Lync Server 2013 中部署高級 Enterprise Voice 功能</span><span class="sxs-lookup"><span data-stu-id="e9334-102">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9334-103">_**主題上次修改日期：** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="e9334-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="e9334-104">為您的組織設定基本的 Enterprise Voice 功能後，您可以選擇性地執行本節中的程序，以部署一或多項進階 Enterprise Voice 功能。</span><span class="sxs-lookup"><span data-stu-id="e9334-104">After you have configured basic Enterprise Voice functionality for your organization, you can optionally deploy one or more advanced Enterprise Voice features by following the procedures in this section.</span></span>

<span data-ttu-id="e9334-105">如需有關高級 Enterprise Voice 功能的詳細資訊，請參閱 [規劃 Lync Server 2013](lync-server-2013-planning.md) 檔的下列各節：</span><span class="sxs-lookup"><span data-stu-id="e9334-105">For details about the advanced Enterprise Voice features, see the following sections of the [Planning for Lync Server 2013](lync-server-2013-planning.md) documentation:</span></span>

  - [<span data-ttu-id="e9334-106">在 Lync Server 2013 中規劃通話許可控制</span><span class="sxs-lookup"><span data-stu-id="e9334-106">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="e9334-107">在 Lync Server 2013 中規劃緊急服務 (E9-1-1) </span><span class="sxs-lookup"><span data-stu-id="e9334-107">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="e9334-108">在 Lync Server 2013 中規劃媒體旁路</span><span class="sxs-lookup"><span data-stu-id="e9334-108">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

<div>

## <a name="in-this-section"></a><span data-ttu-id="e9334-109">本章節內容</span><span class="sxs-lookup"><span data-stu-id="e9334-109">In This Section</span></span>

  - [<span data-ttu-id="e9334-110">關於 Lync Server 2013 中的網路地區、網站和子網</span><span class="sxs-lookup"><span data-stu-id="e9334-110">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="e9334-111">在 Lync Server 2013 中建立或修改網路地區</span><span class="sxs-lookup"><span data-stu-id="e9334-111">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)

  - [<span data-ttu-id="e9334-112">在 Lync Server 2013 中建立或修改網路網站</span><span class="sxs-lookup"><span data-stu-id="e9334-112">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)

  - [<span data-ttu-id="e9334-113">在 Lync Server 2013 中建立子網與網路網站的關聯</span><span class="sxs-lookup"><span data-stu-id="e9334-113">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)

  - [<span data-ttu-id="e9334-114">在 Lync Server 2013 中設定通話許可控制</span><span class="sxs-lookup"><span data-stu-id="e9334-114">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)

  - [<span data-ttu-id="e9334-115">在 Lync Server 2013 中設定增強型9-1-1</span><span class="sxs-lookup"><span data-stu-id="e9334-115">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-enhanced-9-1-1.md)

  - [<span data-ttu-id="e9334-116">在 Lync Server 2013 中設定媒體旁路</span><span class="sxs-lookup"><span data-stu-id="e9334-116">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

