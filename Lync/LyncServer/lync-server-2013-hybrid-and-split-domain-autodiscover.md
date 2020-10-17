---
title: Lync Server 2013：混合式和分割網域自動探索
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
ms.openlocfilehash: 0340e1226d3fb7abc475769892f0cd675c838c89
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528160"
---
# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a><span data-ttu-id="9c78b-102">Lync Server 2013 中的混合式和分割網域自動探索</span><span class="sxs-lookup"><span data-stu-id="9c78b-102">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c78b-103">_**主題上次修改日期：** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="9c78b-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="9c78b-104">共用 SIP 位址空間（也稱為 *分割網域* 部署或 *混合* 式部署）是一種設定，可讓使用者在內部部署部署和線上環境中部署。</span><span class="sxs-lookup"><span data-stu-id="9c78b-104">A shared SIP address space, also known as a *split-domain* deployment, or a *hybrid* deployment, is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="9c78b-105">想要的結果是讓使用者不論其主伺服器位於何處 (內部部署或線上) ，登入部署並重新導向至其主伺服器位置。</span><span class="sxs-lookup"><span data-stu-id="9c78b-105">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="9c78b-106">為了達到此目的，Lync Server 2013 的自動探索功能是用來將線上使用者重新導向至線上拓撲。</span><span class="sxs-lookup"><span data-stu-id="9c78b-106">To accomplish this, the Autodiscover feature of Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="9c78b-107">您可以使用 Lync Server 管理命令介面、 **Get-CsHostingProvider** Cmdlet 和 get-cshostingprovider 指令程式， **設定** 自動探索統一資源定位器 (URL) 。</span><span class="sxs-lookup"><span data-stu-id="9c78b-107">You can do this by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell, the **Get-CsHostingProvider** cmdlet, and the **Set-CsHostingProvider** cmdlet.</span></span>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="9c78b-108">分割網域部署的行動性</span><span class="sxs-lookup"><span data-stu-id="9c78b-108">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="9c78b-109">您需要收集和記錄下列部署的屬性：</span><span class="sxs-lookup"><span data-stu-id="9c78b-109">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="9c78b-110">從 Lync Server 管理命令介面中，輸入</span><span class="sxs-lookup"><span data-stu-id="9c78b-110">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="9c78b-111">在結果中尋找具有 **ProxyFQDN** 屬性的線上提供者。</span><span class="sxs-lookup"><span data-stu-id="9c78b-111">In the results, find the online provider with the attribute **ProxyFQDN**.</span></span> <span data-ttu-id="9c78b-112">例如，sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="9c78b-112">For example, sipfed.online.lync.com.</span></span>

  - <span data-ttu-id="9c78b-113">記錄 ProxyFQDN 的值。</span><span class="sxs-lookup"><span data-stu-id="9c78b-113">Record the value of the ProxyFQDN.</span></span>

  - <span data-ttu-id="9c78b-114">在內部部署的 Lync Server 控制台中啟用同盟，允許與線上提供者同盟。</span><span class="sxs-lookup"><span data-stu-id="9c78b-114">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider.</span></span>

  - <span data-ttu-id="9c78b-115">為線上提供者啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="9c78b-115">Enable federation for the online provider.</span></span> <span data-ttu-id="9c78b-116">根據預設，所有的線上使用者都會啟用網域同盟，而且可以與所有網域通訊。</span><span class="sxs-lookup"><span data-stu-id="9c78b-116">By default, all online users are enabled for domain federation and can communicate with all domains.</span></span>

  - <span data-ttu-id="9c78b-117">如果您會定義封鎖和允許的網域，請決定您要明確允許或明確封鎖的網域。</span><span class="sxs-lookup"><span data-stu-id="9c78b-117">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block.</span></span>

  - <span data-ttu-id="9c78b-118">若要使用線上同盟，您必須規劃防火牆例外狀況、憑證和 DNS 主機 (A 或 AAAA （如果使用 IPv6) 記錄）。</span><span class="sxs-lookup"><span data-stu-id="9c78b-118">For online federation, you must plan for firewall exceptions, certificates, and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="9c78b-119">此外，您必須設定同盟原則。</span><span class="sxs-lookup"><span data-stu-id="9c78b-119">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="9c78b-120">如需詳細資訊，請參閱 [規劃 Lync Server 2013 和 Office 通訊伺服器同盟](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="9c78b-120">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

