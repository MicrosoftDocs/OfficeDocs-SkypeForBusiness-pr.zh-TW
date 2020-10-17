---
title: Lync Server 2013：部署行動性
description: Lync Server 2013：部署行動性。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying mobility
ms:assetid: f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690055(v=OCS.15)
ms:contentKeyID: 48185805
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf927b950f8b94884fb91224a87e196fc815fca1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545199"
---
# <a name="deploying-mobility-in-lync-server-2013"></a><span data-ttu-id="f25c7-103">在 Lync Server 2013 中部署行動性</span><span class="sxs-lookup"><span data-stu-id="f25c7-103">Deploying mobility in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f25c7-104">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="f25c7-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="f25c7-105">當您部署 Lync Server 2013 行動功能時，行動使用者可以使用支援的行動裝置進行 Lync 功能（如立即訊息 (IM) 、目前狀態及連絡人）。</span><span class="sxs-lookup"><span data-stu-id="f25c7-105">When you deploy the Lync Server 2013 mobility feature, mobile users can use supported mobile devices for Lync functionality such as instant messaging (IM), presence, and contacts.</span></span>

<span data-ttu-id="f25c7-106">如需部署行動功能之需求的詳細資訊，請參閱 [在 Lync Server 2013 中規劃行動](lync-server-2013-planning-for-mobility.md)。</span><span class="sxs-lookup"><span data-stu-id="f25c7-106">For details about requirements for deploying the mobility feature, see [Planning for mobility in Lync Server 2013](lync-server-2013-planning-for-mobility.md).</span></span>

<span data-ttu-id="f25c7-107">本節會引導您完成部署及驗證行動性和自動探索功能的步驟。</span><span class="sxs-lookup"><span data-stu-id="f25c7-107">This section guides you through the steps for deploying and verifying the mobility and automatic discovery features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f25c7-108">本章節內容</span><span class="sxs-lookup"><span data-stu-id="f25c7-108">In This Section</span></span>

  - [<span data-ttu-id="f25c7-109">在 Lync Server 2013 中建立自動探索服務的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="f25c7-109">Creating DNS records for the Autodiscover Service in Lync Server 2013</span></span>](lync-server-2013-creating-dns-records-for-the-autodiscover-service.md)

  - [<span data-ttu-id="f25c7-110">在 Lync Server 2013 中修改行動憑證</span><span class="sxs-lookup"><span data-stu-id="f25c7-110">Modifying certificates for mobility in Lync Server 2013</span></span>](lync-server-2013-modifying-certificates-for-mobility.md)

  - [<span data-ttu-id="f25c7-111">在 Lync Server 2013 中設定行動的反向 proxy</span><span class="sxs-lookup"><span data-stu-id="f25c7-111">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)

  - [<span data-ttu-id="f25c7-112">在 Lync Server 2013 中設定自動探索以進行混合式部署的行動性</span><span class="sxs-lookup"><span data-stu-id="f25c7-112">Configuring Autodiscover in Lync Server 2013 for mobility with hybrid deployments</span></span>](lync-server-2013-configuring-autodiscover-for-mobility-with-hybrid-deployments.md)

  - [<span data-ttu-id="f25c7-113">在 Lync Server 2013 中驗證行動性部署</span><span class="sxs-lookup"><span data-stu-id="f25c7-113">Verifying your mobility deployment in Lync Server 2013</span></span>](lync-server-2013-verifying-your-mobility-deployment.md)

  - [<span data-ttu-id="f25c7-114">在 Lync Server 2013 中設定推播通知</span><span class="sxs-lookup"><span data-stu-id="f25c7-114">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)

  - [<span data-ttu-id="f25c7-115">在 Lync Server 2013 中設定行動性原則</span><span class="sxs-lookup"><span data-stu-id="f25c7-115">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

