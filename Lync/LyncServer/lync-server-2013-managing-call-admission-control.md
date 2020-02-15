---
title: Lync Server 2013： 管理通話許可控制
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
ms.openlocfilehash: ccb92b69c16f6dd45eedb584f0f63294dcbea4c0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037131"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="c9f22-102">管理 Lync Server 2013 中的通話許可控制</span><span class="sxs-lookup"><span data-stu-id="c9f22-102">Managing call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9f22-103">_**主題上次修改日期：** 2012年-11-01_</span><span class="sxs-lookup"><span data-stu-id="c9f22-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c9f22-104">通話許可控制服務 (CAC) 會根據可用的網路頻寬，判斷是否允許建立即時通訊工作階段 (如語音或視訊通話)。</span><span class="sxs-lookup"><span data-stu-id="c9f22-104">Call admission control (CAC) determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="c9f22-105">使用下列程序來管理 Lync Server 2013 環境的不同 CAC 功能。</span><span class="sxs-lookup"><span data-stu-id="c9f22-105">Use the following procedures to manage different CAC features for your Lync Server 2013 environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c9f22-106">本章節內容</span><span class="sxs-lookup"><span data-stu-id="c9f22-106">In This Section</span></span>

  - [<span data-ttu-id="c9f22-107">啟用 Lync Server 2013 中的通話許可控制</span><span class="sxs-lookup"><span data-stu-id="c9f22-107">Enabling call admission control in Lync Server 2013</span></span>](lync-server-2013-enabling-call-admission-control.md)

  - [<span data-ttu-id="c9f22-108">管理 Lync Server 2013 中的網路頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="c9f22-108">Managing network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-managing-network-bandwidth-policy-profiles.md)

  - [<span data-ttu-id="c9f22-109">Lync Server 2013 中的網路地區</span><span class="sxs-lookup"><span data-stu-id="c9f22-109">Network regions in Lync Server 2013</span></span>](lync-server-2013-network-regions.md)

  - [<span data-ttu-id="c9f22-110">Lync Server 2013 中的網路地區路由</span><span class="sxs-lookup"><span data-stu-id="c9f22-110">Network region routes in Lync Server 2013</span></span>](lync-server-2013-network-region-routes.md)

  - [<span data-ttu-id="c9f22-111">Lync Server 2013 中網站的通話許可控制</span><span class="sxs-lookup"><span data-stu-id="c9f22-111">Call admission control for sites in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-for-sites.md)

  - [<span data-ttu-id="c9f22-112">啟用和停用媒體旁路 Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="c9f22-112">Enabling and disabling media bypass in Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-media-bypass.md)

  - [<span data-ttu-id="c9f22-113">Lync Server 2013 中的連結網路地區</span><span class="sxs-lookup"><span data-stu-id="c9f22-113">Linking network regions in Lync Server 2013</span></span>](lync-server-2013-linking-network-regions.md)

  - [<span data-ttu-id="c9f22-114">管理 Lync Server 2013 中的子網路</span><span class="sxs-lookup"><span data-stu-id="c9f22-114">Managing network subnets in Lync Server 2013</span></span>](lync-server-2013-managing-network-subnets.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c9f22-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c9f22-115">See Also</span></span>


[<span data-ttu-id="c9f22-116">Lync Server 2013 中的通話許可控制的概觀</span><span class="sxs-lookup"><span data-stu-id="c9f22-116">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

