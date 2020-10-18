---
title: Lync Server 2013：混合式部署的概述
description: Lync Server 2013：混合式部署的概述。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of hybrid deployments
ms:assetid: f6610f2f-c804-4f36-81fc-7aa3297bb4a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205386(v=OCS.15)
ms:contentKeyID: 48185845
ms.date: 05/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98fce595614484fdc56fe84d5ad6076c9becc4e8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577389"
---
# <a name="overview-of-lync-server-2013-hybrid-deployments"></a><span data-ttu-id="32abc-103">Lync Server 2013 混合式部署的概述</span><span class="sxs-lookup"><span data-stu-id="32abc-103">Overview of Lync Server 2013 hybrid deployments</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32abc-104">_**主題上次修改日期：** 2016-05-25_</span><span class="sxs-lookup"><span data-stu-id="32abc-104">_**Topic Last Modified:** 2016-05-25_</span></span>

<span data-ttu-id="32abc-105">Lync Server 混合式部署是一種部署方式，使用者可以使用 Lync Server 內部部署和 Microsoft Lync Online，分割網域的使用者（例如 contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="32abc-105">A Lync Server hybrid deployment is a deployment where users of a domain, such as contoso.com, are split between using Lync Server on-premises and Microsoft Lync Online.</span></span> <span data-ttu-id="32abc-106">有些網域使用者位於內部部署的 Lync 伺服器上，有些使用者則位於商務用 Skype Online 中。</span><span class="sxs-lookup"><span data-stu-id="32abc-106">Some of the domain users are homed on the on-premises Lync Server, and some users are homed in Skype for Business Online.</span></span>

<span data-ttu-id="32abc-107">您可以使用商務用 Skype Online 設定混合式的內部部署 Lync 部署，並使用 Active Directory 同步處理，以保持內部部署和線上使用者同步。</span><span class="sxs-lookup"><span data-stu-id="32abc-107">You can configure your on-premises Lync deployment for hybrid with Skype for Business Online and use Active Directory Synchronization to keep your on-premises and online users synchronized.</span></span> <span data-ttu-id="32abc-108">您也可以設定混合式部署，以與內部部署 Exchange 和 SharePoint 整合，或是使用 Microsoft 365 和 Office 365 應用程式（包括 Exchange Online 和 SharePoint 線上）進行整合。</span><span class="sxs-lookup"><span data-stu-id="32abc-108">You can also configure hybrid deployments for integration with on-premises Exchange and SharePoint, or with Microsoft 365 and Office 365 applications, including Exchange Online and SharePoint Online.</span></span>

<span data-ttu-id="32abc-109">本節會引導您部署 Lync Server 混合部署所需的應用程式，然後設定您的部署，以管理 Lync Server 內部部署和商務用 Skype Online 之間的使用者。</span><span class="sxs-lookup"><span data-stu-id="32abc-109">This section guides you through deploying the applications required for a Lync Server hybrid deployment, and then configuring your deployment to manage users between Lync Server on-premises and Skype for Business Online.</span></span>

<span data-ttu-id="32abc-110">如需使用商務用 Skype Online 為混合式設定內部部署 Lync Server 部署的詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="32abc-110">For information about configuring your on-premises Lync Server deployment for hybrid with Skype for Business Online see the following topics:</span></span>

  - [<span data-ttu-id="32abc-111">規劃 Lync Server 2013 混合式部署</span><span class="sxs-lookup"><span data-stu-id="32abc-111">Planning for Lync Server 2013 hybrid deployments</span></span>](lync-server-2013-planning-for-hybrid-deployments.md)

  - [<span data-ttu-id="32abc-112">設定 Lync Server 2013 混合式部署</span><span class="sxs-lookup"><span data-stu-id="32abc-112">Configuring Lync Server 2013 hybrid deployments</span></span>](lync-server-2013-configuring-hybrid-deployments.md)

<span data-ttu-id="32abc-113">如需商務用 Skype Online 的詳細資訊，請參閱 [Lync online](https://go.microsoft.com/fwlink/p/?linkid=282396)。</span><span class="sxs-lookup"><span data-stu-id="32abc-113">For more information about Skype for Business Online, see [Lync Online](https://go.microsoft.com/fwlink/p/?linkid=282396).</span></span>

</div>

<span> </span>

</div>

</div>

</div>
