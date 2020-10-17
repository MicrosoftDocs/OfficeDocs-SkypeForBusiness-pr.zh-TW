---
title: Lync Server 2013：管理通話許可控制
description: Lync Server 2013：管理通話許可控制。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing call admission control
ms:assetid: b0bd4783-6f47-408d-b010-2e30f9bc1770
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721851(v=OCS.15)
ms:contentKeyID: 49733784
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a1c01bff6d1dce48dea314b6704cc0f5ff7d6b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549459"
---
# <a name="managing-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="da2be-103">在 Lync Server 2013 中管理通話許可控制</span><span class="sxs-lookup"><span data-stu-id="da2be-103">Managing call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da2be-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="da2be-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="da2be-105">通話許可控制服務 (CAC) 會根據可用的網路頻寬，判斷是否允許建立即時通訊工作階段 (如語音或視訊通話)。</span><span class="sxs-lookup"><span data-stu-id="da2be-105">Call admission control (CAC) determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="da2be-106">使用下列程式可管理 Lync Server 2013 環境的不同 CAC 功能。</span><span class="sxs-lookup"><span data-stu-id="da2be-106">Use the following procedures to manage different CAC features for your Lync Server 2013 environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="da2be-107">本章節內容</span><span class="sxs-lookup"><span data-stu-id="da2be-107">In This Section</span></span>

  - [<span data-ttu-id="da2be-108">在 Lync Server 2013 中啟用通話許可控制</span><span class="sxs-lookup"><span data-stu-id="da2be-108">Enabling call admission control in Lync Server 2013</span></span>](lync-server-2013-enabling-call-admission-control.md)

  - [<span data-ttu-id="da2be-109">在 Lync Server 2013 中管理網路頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="da2be-109">Managing network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-managing-network-bandwidth-policy-profiles.md)

  - [<span data-ttu-id="da2be-110">Lync Server 2013 中的網路地區</span><span class="sxs-lookup"><span data-stu-id="da2be-110">Network regions in Lync Server 2013</span></span>](lync-server-2013-network-regions.md)

  - [<span data-ttu-id="da2be-111">Lync Server 2013 中的網路地區路由</span><span class="sxs-lookup"><span data-stu-id="da2be-111">Network region routes in Lync Server 2013</span></span>](lync-server-2013-network-region-routes.md)

  - [<span data-ttu-id="da2be-112">Lync Server 2013 中網站的通話許可控制</span><span class="sxs-lookup"><span data-stu-id="da2be-112">Call admission control for sites in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-for-sites.md)

  - [<span data-ttu-id="da2be-113">在 Lync Server 2013 中啟用和停用媒體旁路</span><span class="sxs-lookup"><span data-stu-id="da2be-113">Enabling and disabling media bypass in Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-media-bypass.md)

  - [<span data-ttu-id="da2be-114">在 Lync Server 2013 中連結網路地區</span><span class="sxs-lookup"><span data-stu-id="da2be-114">Linking network regions in Lync Server 2013</span></span>](lync-server-2013-linking-network-regions.md)

  - [<span data-ttu-id="da2be-115">在 Lync Server 2013 中管理網路子網</span><span class="sxs-lookup"><span data-stu-id="da2be-115">Managing network subnets in Lync Server 2013</span></span>](lync-server-2013-managing-network-subnets.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="da2be-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="da2be-116">See Also</span></span>


[<span data-ttu-id="da2be-117">Lync Server 2013 中的通話許可控制概覽</span><span class="sxs-lookup"><span data-stu-id="da2be-117">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

