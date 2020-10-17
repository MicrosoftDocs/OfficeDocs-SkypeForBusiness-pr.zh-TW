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
ms.openlocfilehash: 27d280580f4d9cae1f6240b554be760d1689daa3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504480"
---
# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a><span data-ttu-id="bb0b5-102">在 Lync Server 2013 中定義 E9-1-1 部署的範圍</span><span class="sxs-lookup"><span data-stu-id="bb0b5-102">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb0b5-103">_**主題上次修改日期：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="bb0b5-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="bb0b5-104">將 Microsoft Lync Server 2013 設定為 E9-1-1 之前，您必須規劃 E9-1-1 部署。</span><span class="sxs-lookup"><span data-stu-id="bb0b5-104">Before you configure Microsoft Lync Server 2013 for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="bb0b5-105">應考量的問題包括：</span><span class="sxs-lookup"><span data-stu-id="bb0b5-105">Some of the questions to consider include:</span></span>

  - <span data-ttu-id="bb0b5-106">**您組織對於 E9-1-1 的原則及法律義務為何？**</span><span class="sxs-lookup"><span data-stu-id="bb0b5-106">**What are your organization’s policy and legal obligations with regard to E9-1-1?**</span></span>  
    <span data-ttu-id="bb0b5-107">E9-1-1 對於 PBX (以 E9-1-1 的說法稱為多線電話系統，或 MLTS) 的法律要求會因為各州而有所不同。</span><span class="sxs-lookup"><span data-stu-id="bb0b5-107">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="bb0b5-108">您應該向法律小組請教，以瞭解可能對您的相關地理區域中的 Lync Server 部署所套用的義務。</span><span class="sxs-lookup"><span data-stu-id="bb0b5-108">You should consult with your legal team to understand the obligations that may apply to your deployment of Lync Server in your relevant geographies.</span></span>

<!-- end list -->

  - <span data-ttu-id="bb0b5-109">**您的企業中有哪些領域需要啟用 E9-1-1？**</span><span class="sxs-lookup"><span data-stu-id="bb0b5-109">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="bb0b5-p103">您可以為整個企業或為選取的位置啟用 E9-1-1。例如，對於位於不同州的辦公室，您可能有不同的 E9-1-1 需求，或者您可能想要排除美國境外的網站。</span><span class="sxs-lookup"><span data-stu-id="bb0b5-p103">You can enable E9-1-1 for the entire enterprise or for selected locations. For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

<!-- end list -->

  - <span data-ttu-id="bb0b5-112">**您要如何將 E9-1-1 部署至分支網站？**</span><span class="sxs-lookup"><span data-stu-id="bb0b5-112">**How will you deploy E9-1-1 to branch sites?**</span></span>  
    <span data-ttu-id="bb0b5-113">在分支網站部署 E9-1-1 時，語音恢復能力是必須要了解的重要概念。</span><span class="sxs-lookup"><span data-stu-id="bb0b5-113">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="bb0b5-114">如果您已集中式電子 9-1-1 SIP 主幹，且發生 WAN 中斷，則登入的用戶端可能無法從位置資訊服務取得位置，或無法連線至緊急服務服務提供者。</span><span class="sxs-lookup"><span data-stu-id="bb0b5-114">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="bb0b5-115">Lync Server 提供數個策略，用來處理分支辦公室中的語音彈性，包括：具有可恢復的資料網路、在每個分支部署 SIP 主幹，或在中斷期間將緊急呼叫推出至本機閘道。</span><span class="sxs-lookup"><span data-stu-id="bb0b5-115">Lync Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="bb0b5-116">如需詳細資訊，請參閱 [在 Lync Server 2013 中規劃分支網站語音恢復功能](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。</span><span class="sxs-lookup"><span data-stu-id="bb0b5-116">For details, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<!-- end list -->

  - <span data-ttu-id="bb0b5-117">**您是否會為在網路以外工作的使用者啟用 E9-1-1？**</span><span class="sxs-lookup"><span data-stu-id="bb0b5-117">**Will you enable E9-1-1 for users working outside the network?**</span></span>  
    <span data-ttu-id="bb0b5-p105">自動取得位置僅適用於位於組織網路內部的用戶端，因此您的組織必須決定是否要支援來自外部部署 Lync 用戶端發出的 E9-1-1 電話。例如，若使用者是在家裡工作，或是在客戶網站上，您是否要允許該使用者撥打緊急通話？若用戶端位於企業網路之外，可設定用戶端提示使用者告知其位置。不過根據主要街道地址指南 (MSAG)，這些使用者提供的位置無法預先加以驗證，緊急服務的服務提供者發送方需要以口頭與來電者確定此位置的有效性，才能將電話路由至公共安全勤務中心 (PSAP)。</span><span class="sxs-lookup"><span data-stu-id="bb0b5-p105">Automatic location acquisition is available only for clients located inside the organization’s network, so your organization needs to decide whether it will support E9-1-1 calls made from Lync clients while off-premises. For example, will you enable users to place emergency calls if they are working from home or from a customer site? If a client is located outside the enterprise network, the client can be configured to prompt the user for a location. However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bb0b5-122">使用 VPN 連線到貴組織網路之使用者的 Lync 用戶端可以挑選內部 IP 位址資訊，但因為這些位址不能用來識別使用者的實際位置，所以從位置資訊服務排除 VPN 子網是必要的。</span><span class="sxs-lookup"><span data-stu-id="bb0b5-122">Lync clients of users who connect to your organization’s network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user’s actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="bb0b5-123">**您是否要提供路由至美國以外網站的緊急電話？**</span><span class="sxs-lookup"><span data-stu-id="bb0b5-123">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>  
    <span data-ttu-id="bb0b5-p106">您可以為公司中不受緊急服務的服務提供者所涵蓋的區域 (例如駐外地點) 提供緊急路由。若要這麼做，請建立新網站，然後為其指派語音原則，並讓此語音原則參照透過本機 PSTN 閘道路由電話的 PSTN 使用方式。</span><span class="sxs-lookup"><span data-stu-id="bb0b5-p106">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations). To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

