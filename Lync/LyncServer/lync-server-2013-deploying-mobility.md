---
title: Lync Server 2013：部署行動性
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
ms.openlocfilehash: 0d93f01d93e1903e1db1bd3f3663ac7cb4c5a1ce
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-mobility-in-lync-server-2013"></a><span data-ttu-id="ef5a5-102">在 Lync Server 2013 中部署行動性</span><span class="sxs-lookup"><span data-stu-id="ef5a5-102">Deploying mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef5a5-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="ef5a5-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="ef5a5-104">當您部署 Lync Server 2013 行動功能時，行動使用者可以使用支援的行動裝置進行 Lync 功能（如立即訊息 (IM) 、目前狀態及連絡人）。</span><span class="sxs-lookup"><span data-stu-id="ef5a5-104">When you deploy the Lync Server 2013 mobility feature, mobile users can use supported mobile devices for Lync functionality such as instant messaging (IM), presence, and contacts.</span></span>

<span data-ttu-id="ef5a5-105">如需部署行動功能之需求的詳細資訊，請參閱[在 Lync Server 2013 中規劃行動](lync-server-2013-planning-for-mobility.md)。</span><span class="sxs-lookup"><span data-stu-id="ef5a5-105">For details about requirements for deploying the mobility feature, see [Planning for mobility in Lync Server 2013](lync-server-2013-planning-for-mobility.md).</span></span>

<span data-ttu-id="ef5a5-106">本節會引導您完成部署及驗證行動性和自動探索功能的步驟。</span><span class="sxs-lookup"><span data-stu-id="ef5a5-106">This section guides you through the steps for deploying and verifying the mobility and automatic discovery features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ef5a5-107">本章節內容</span><span class="sxs-lookup"><span data-stu-id="ef5a5-107">In This Section</span></span>

  - [<span data-ttu-id="ef5a5-108">在 Lync Server 2013 中建立自動探索服務的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="ef5a5-108">Creating DNS records for the Autodiscover Service in Lync Server 2013</span></span>](lync-server-2013-creating-dns-records-for-the-autodiscover-service.md)

  - [<span data-ttu-id="ef5a5-109">在 Lync Server 2013 中修改行動憑證</span><span class="sxs-lookup"><span data-stu-id="ef5a5-109">Modifying certificates for mobility in Lync Server 2013</span></span>](lync-server-2013-modifying-certificates-for-mobility.md)

  - [<span data-ttu-id="ef5a5-110">在 Lync Server 2013 中設定行動的反向 proxy</span><span class="sxs-lookup"><span data-stu-id="ef5a5-110">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)

  - [<span data-ttu-id="ef5a5-111">在 Lync Server 2013 中設定自動探索以進行混合式部署的行動性</span><span class="sxs-lookup"><span data-stu-id="ef5a5-111">Configuring Autodiscover in Lync Server 2013 for mobility with hybrid deployments</span></span>](lync-server-2013-configuring-autodiscover-for-mobility-with-hybrid-deployments.md)

  - [<span data-ttu-id="ef5a5-112">在 Lync Server 2013 中驗證行動性部署</span><span class="sxs-lookup"><span data-stu-id="ef5a5-112">Verifying your mobility deployment in Lync Server 2013</span></span>](lync-server-2013-verifying-your-mobility-deployment.md)

  - [<span data-ttu-id="ef5a5-113">在 Lync Server 2013 中設定推播通知</span><span class="sxs-lookup"><span data-stu-id="ef5a5-113">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)

  - [<span data-ttu-id="ef5a5-114">在 Lync Server 2013 中設定行動性原則</span><span class="sxs-lookup"><span data-stu-id="ef5a5-114">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

