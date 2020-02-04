---
title: Lync Server 2013：混合式和分割網域-自動探索
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hybrid and split-domain - Autodiscover
ms:assetid: c855bcc5-b656-4d2d-92d6-f016f2797d3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945652(v=OCS.15)
ms:contentKeyID: 51541520
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce38bba4717e3340e7eacf33ce67fc357d208b83
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a><span data-ttu-id="b6353-102">Lync Server 2013 中的混合式和剝離網域自動探索</span><span class="sxs-lookup"><span data-stu-id="b6353-102">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6353-103">_**主題上次修改日期：** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="b6353-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="b6353-104">共用的 SIP 位址空間（又稱為*分割網域*部署）或*混合*式部署，是在內部部署和線上環境中部署使用者的配置。</span><span class="sxs-lookup"><span data-stu-id="b6353-104">A shared SIP address space, also known as a *split-domain* deployment, or a *hybrid* deployment, is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="b6353-105">您想要的結果是讓使用者無論其主伺服器位於何處（內部部署或線上），都能登入部署，並重新導向到他們的主伺服器位置。</span><span class="sxs-lookup"><span data-stu-id="b6353-105">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="b6353-106">若要完成此作業，Lync Server 2013 的自動探索功能是用來重新導向線上使用者與線上拓撲。</span><span class="sxs-lookup"><span data-stu-id="b6353-106">To accomplish this, the Autodiscover feature of Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="b6353-107">您可以透過使用 Lync Server 管理命令介面、 **CsHostingProvider** Cmdlet 和**CsHostingProvider** Cmdlet 來設定自動探索統一資源定位器（URL）來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="b6353-107">You can do this by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell, the **Get-CsHostingProvider** cmdlet, and the **Set-CsHostingProvider** cmdlet.</span></span>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="b6353-108">分割網域部署的行動性</span><span class="sxs-lookup"><span data-stu-id="b6353-108">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="b6353-109">您將需要收集並錄製下列已部署的屬性：</span><span class="sxs-lookup"><span data-stu-id="b6353-109">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="b6353-110">從 Lync Server 管理命令介面輸入</span><span class="sxs-lookup"><span data-stu-id="b6353-110">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="b6353-111">在結果中，尋找具有屬性**ProxyFQDN**的線上提供者。</span><span class="sxs-lookup"><span data-stu-id="b6353-111">In the results, find the online provider with the attribute **ProxyFQDN**.</span></span> <span data-ttu-id="b6353-112">例如，sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="b6353-112">For example, sipfed.online.lync.com.</span></span>

  - <span data-ttu-id="b6353-113">記錄 ProxyFQDN 的值。</span><span class="sxs-lookup"><span data-stu-id="b6353-113">Record the value of the ProxyFQDN.</span></span>

  - <span data-ttu-id="b6353-114">在內部部署的 Lync Server [控制台] 中啟用同盟，允許與線上提供者進行同盟。</span><span class="sxs-lookup"><span data-stu-id="b6353-114">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider.</span></span>

  - <span data-ttu-id="b6353-115">針對線上提供者啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="b6353-115">Enable federation for the online provider.</span></span> <span data-ttu-id="b6353-116">根據預設，所有的線上使用者都會啟用網域聯盟，而且可以與所有網域進行通訊。</span><span class="sxs-lookup"><span data-stu-id="b6353-116">By default, all online users are enabled for domain federation and can communicate with all domains.</span></span>

  - <span data-ttu-id="b6353-117">如果您要定義封鎖和允許的網域，請判斷您將明確允許或明確封鎖的網域。</span><span class="sxs-lookup"><span data-stu-id="b6353-117">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block.</span></span>

  - <span data-ttu-id="b6353-118">針對線上同盟，您必須規劃防火牆例外狀況、憑證和 DNS 主機（如果使用 IPv6，則為 A 或 AAAA）。</span><span class="sxs-lookup"><span data-stu-id="b6353-118">For online federation, you must plan for firewall exceptions, certificates, and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="b6353-119">此外，您必須設定同盟原則。</span><span class="sxs-lookup"><span data-stu-id="b6353-119">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="b6353-120">如需詳細資訊，請參閱[規劃 Lync Server 2013 和 Office 通訊伺服器同盟](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="b6353-120">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

