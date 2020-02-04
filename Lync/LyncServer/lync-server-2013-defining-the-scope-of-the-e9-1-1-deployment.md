---
title: Lync Server 2013：定義 E9-1-1 部署的範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the scope of the E9-1-1 deployment
ms:assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425775(v=OCS.15)
ms:contentKeyID: 48183707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96f5ac1fb747a3e64be6cc84c44b390de8ce821c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a><span data-ttu-id="45489-102">在 Lync Server 2013 中定義 E9-1-1 部署的範圍</span><span class="sxs-lookup"><span data-stu-id="45489-102">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45489-103">_**主題上次修改日期：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="45489-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="45489-104">在將 Microsoft Lync Server 2013 設定為 E9-1-1 之前，您必須先規劃您的 E9-1 1 部署。</span><span class="sxs-lookup"><span data-stu-id="45489-104">Before you configure Microsoft Lync Server 2013 for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="45489-105">需要考慮的一些問題包括：</span><span class="sxs-lookup"><span data-stu-id="45489-105">Some of the questions to consider include:</span></span>

  - <span data-ttu-id="45489-106">**貴組織的原則與 E9-1-1 的法律義務為何？**</span><span class="sxs-lookup"><span data-stu-id="45489-106">**What are your organization’s policy and legal obligations with regard to E9-1-1?**</span></span>  
    <span data-ttu-id="45489-107">E9-1-1-1-1-1-1 parlance）中的 Pbx 法律需求（在 E9-1-1 中稱為多行電話系統，或 MLTS）與狀態不同。</span><span class="sxs-lookup"><span data-stu-id="45489-107">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="45489-108">您應該向法律小組諮詢，以瞭解在相關地區的 Lync Server 部署中可能適用的義務。</span><span class="sxs-lookup"><span data-stu-id="45489-108">You should consult with your legal team to understand the obligations that may apply to your deployment of Lync Server in your relevant geographies.</span></span>

<!-- end list -->

  - <span data-ttu-id="45489-109">**貴企業中需要為 E9 的哪些區域啟用-1-1？**</span><span class="sxs-lookup"><span data-stu-id="45489-109">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="45489-110">您可以為整個企業或選取的位置啟用 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="45489-110">You can enable E9-1-1 for the entire enterprise or for selected locations.</span></span> <span data-ttu-id="45489-111">例如，您可能會在不同狀態的辦公室中有不同的 E9-1 需求，或者您可能想要排除美國以外的網站</span><span class="sxs-lookup"><span data-stu-id="45489-111">For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

<!-- end list -->

  - <span data-ttu-id="45489-112">**如何將 E9-1-1 部署到分支網站？**</span><span class="sxs-lookup"><span data-stu-id="45489-112">**How will you deploy E9-1-1 to branch sites?**</span></span>  
    <span data-ttu-id="45489-113">語音復原是您在分支網站部署 E9-1-1 時，必須瞭解的重要概念。</span><span class="sxs-lookup"><span data-stu-id="45489-113">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="45489-114">如果您使用的是集中式電子 9-1-1 SIP trunks，且發生 WAN 中斷，則登入的用戶端可能無法從位置資訊服務取得位置，或無法連線到緊急服務服務提供者。</span><span class="sxs-lookup"><span data-stu-id="45489-114">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="45489-115">Lync Server 提供幾項策略，可處理分支辦公室中的語音復原，包括：具備彈性資料網路、在每個分支部署 SIP 幹線，或在中斷期間將緊急呼叫推出到本機閘道。</span><span class="sxs-lookup"><span data-stu-id="45489-115">Lync Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="45489-116">如需詳細資訊，請參閱[Lync Server 2013 中的分支網站語音復原規劃](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。</span><span class="sxs-lookup"><span data-stu-id="45489-116">For details, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<!-- end list -->

  - <span data-ttu-id="45489-117">**您是否要為在網路外部工作的使用者啟用 E9-1-1？**</span><span class="sxs-lookup"><span data-stu-id="45489-117">**Will you enable E9-1-1 for users working outside the network?**</span></span>  
    <span data-ttu-id="45489-118">自動位置採集僅適用于組織網路內部的客戶，所以您的組織必須決定是否支援在非內部部署期間從 Lync 用戶端撥打的 E9。</span><span class="sxs-lookup"><span data-stu-id="45489-118">Automatic location acquisition is available only for clients located inside the organization’s network, so your organization needs to decide whether it will support E9-1-1 calls made from Lync clients while off-premises.</span></span> <span data-ttu-id="45489-119">例如，如果使用者是在家中或從客戶的網站工作，您是否能讓他們放入緊急通話？</span><span class="sxs-lookup"><span data-stu-id="45489-119">For example, will you enable users to place emergency calls if they are working from home or from a customer site?</span></span> <span data-ttu-id="45489-120">如果用戶端位於商業網路之外，則可將用戶端設定為提示使用者輸入位置。</span><span class="sxs-lookup"><span data-stu-id="45489-120">If a client is located outside the enterprise network, the client can be configured to prompt the user for a location.</span></span> <span data-ttu-id="45489-121">不過，因為這些使用者提供的位置無法依據主要街道位址指南（MSAG） prevalidated，所以緊急服務服務提供者發送器必須在路由前確認與來電者 verbally 位置的有效性。公用安全應答點（PSAP）的呼叫。</span><span class="sxs-lookup"><span data-stu-id="45489-121">However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="45489-122">使用 VPN 連線到貴組織網路的使用者的 Lync 用戶端可以挑選內部 IP 位址資訊，但因為這些位址無法用來識別使用者的實際位置，所以必須將 VPN 子網排除在位置資訊服務。</span><span class="sxs-lookup"><span data-stu-id="45489-122">Lync clients of users who connect to your organization’s network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user’s actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="45489-123">**您想要提供緊急呼叫路由至美國以外的網站嗎？**</span><span class="sxs-lookup"><span data-stu-id="45489-123">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>  
    <span data-ttu-id="45489-124">您可能會想要提供緊急路由至您公司不是由緊急服務服務提供者所提供的區域（例如，國際位置）。</span><span class="sxs-lookup"><span data-stu-id="45489-124">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations).</span></span> <span data-ttu-id="45489-125">若要這樣做，請建立新的網站，然後將語音原則指派給參照 PSTN 使用狀況的網站，以透過本機 PSTN 閘道路由通話。</span><span class="sxs-lookup"><span data-stu-id="45489-125">To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

