---
title: Lync Server 2013：規劃自動探索
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6416e2ed817dc3cc03a0ec516175c92623bb31b3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497870"
---
# <a name="planning-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="b702f-102">在 Lync Server 2013 中規劃自動探索</span><span class="sxs-lookup"><span data-stu-id="b702f-102">Planning for Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b702f-103">_**主題上次修改日期：** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="b702f-103">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="b702f-104">Lync server 2010：11月2011的累計更新中已引進 Lync Server 的自動探索。</span><span class="sxs-lookup"><span data-stu-id="b702f-104">Autodiscover was introduced for Lync Server in the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="b702f-105">這項初始的自動探索執行的主要目的是提供一種方法，讓 Lync Mobile 能夠找出行動服務 (Mcx) 。</span><span class="sxs-lookup"><span data-stu-id="b702f-105">The primary purpose for this initial implementation of Autodiscover was to provide a means for Lync Mobile to locate the Mobility service (Mcx).</span></span> <span data-ttu-id="b702f-106">Lync Server 2013 中的自動探索服務現在是所有用戶端用來尋找伺服器和使用者服務的服務。</span><span class="sxs-lookup"><span data-stu-id="b702f-106">The Autodiscover service in Lync Server 2013 is now a service used by all clients to locate server and user services.</span></span> <span data-ttu-id="b702f-107">Microsoft Lync Server 2013 自動探索服務會在 Director 和前端伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="b702f-107">The Microsoft Lync Server 2013 Autodiscover service runs on Directors and Front End Servers.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="b702f-108">如需更多對自動探索的技術瞭解，以及與用戶端進行通訊的相關資訊，請參閱 <A href="lync-server-2013-understanding-autodiscover.md">瞭解 Lync Server 2013 中的自動</A>探索。</span><span class="sxs-lookup"><span data-stu-id="b702f-108">For a more technical understanding of Autodiscover and what is communicated to clients, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="b702f-109">行動性仍然是不同的案例，行動服務仍然需要一些特殊的規劃。</span><span class="sxs-lookup"><span data-stu-id="b702f-109">Mobility is still a distinct scenario and the Mobility services still require some special planning.</span></span> <span data-ttu-id="b702f-110">如需其他詳細資料，請參閱 <A href="lync-server-2013-planning-for-mobility.md">在 Lync Server 2013 中規劃行動</A>。</span><span class="sxs-lookup"><span data-stu-id="b702f-110">For additional details, see <A href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="b702f-111">在 Lync Server 2010 中引入「自動探索」時，必須採取一些威脅，才可實施對現有伺服器部署有可能的憑證變更所需的服務。</span><span class="sxs-lookup"><span data-stu-id="b702f-111">When Autodiscover was introduced in Lync Server 2010, there were compromises that needed to be made in order to implement a service that required potential certificate changes to existing server deployments.</span></span> <span data-ttu-id="b702f-112">自動探索可用於 HTTPS 的埠 TCP 443，或透過埠 TCP 80 進行 HTTP。</span><span class="sxs-lookup"><span data-stu-id="b702f-112">Autodiscover could be used over port TCP 443 for HTTPS or over port TCP 80 for HTTP.</span></span> <span data-ttu-id="b702f-113">若決定使用 HTTPS，應重新產生反向 proxy、Director 和前端伺服器上的憑證，以容納必要的 `lyncdiscover.<domain>` 和 `lyncdiscoverinternal.<domain>` DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="b702f-113">If the decision was made to use HTTPS, certificates on reverse proxies, Directors, and Front End Servers needed to be reissued in order to accommodate the required `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` DNS records.</span></span> <span data-ttu-id="b702f-114">如果決策使用的是 HTTP，使用 DNS CNAME (或別名) 記錄來使用憑證上的現有名稱，便可避免重新發起憑證。</span><span class="sxs-lookup"><span data-stu-id="b702f-114">If the decision was to use HTTP, the reissue of certificates could be avoided by using DNS CNAME (or alias) records to use existing names on the certificates.</span></span> <span data-ttu-id="b702f-115">使用 HTTP 是指未加密初始通訊。</span><span class="sxs-lookup"><span data-stu-id="b702f-115">Using HTTP did mean that the initial communications were unencrypted.</span></span>

<span data-ttu-id="b702f-116">因為 Lync Server 2013 針對所有用戶端使用自動探索，所以主要案例是以獨佔方式使用 HTTPS，並使用 lyncdiscover 建立憑證。\<domain\></span><span class="sxs-lookup"><span data-stu-id="b702f-116">Because Lync Server 2013 uses Autodiscover for all clients, the main scenario is to use HTTPS exclusively and to create certificates with lyncdiscover.\<domain\></span></span> <span data-ttu-id="b702f-117">反向 proxy、Director 及前端伺服器設定的一部分。</span><span class="sxs-lookup"><span data-stu-id="b702f-117">as part of the configuration of reverse proxies, Directors and Front End Servers.</span></span> <span data-ttu-id="b702f-118">若要將自動探索從 Lync Server 2010 實施升級的部署，您可能想要使用 HTTP 來避免重新發起憑證。</span><span class="sxs-lookup"><span data-stu-id="b702f-118">If you are implementing Autodiscover into an upgraded deployment from Lync Server 2010, you may want to use HTTP to avoid reissuing certificates.</span></span> <span data-ttu-id="b702f-119">下列各節提供兩種案例的指導方針。</span><span class="sxs-lookup"><span data-stu-id="b702f-119">Guidance for both scenarios is provided in the following sections.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b702f-120">外部 web 服務發行規則所使用之憑證上的主體替代名稱清單必須包含<EM>lyncdiscover。 &lt;組織 &gt; </EM>內每個 SIP 網域的 microsoft.rtc.management.xds.sipdomain 專案。</span><span class="sxs-lookup"><span data-stu-id="b702f-120">The subject alternative name list on certificates used by the external web services publishing rule must contain a <EM>lyncdiscover.&lt;sipdomain&gt;</EM> entry for each SIP domain within your organization.</span></span> <span data-ttu-id="b702f-121">如需 Director、前端伺服器及反向 proxy 所需的主體替代名稱專案的詳細資訊，請參閱 <A href="lync-server-2013-certificate-summary-autodiscover.md">Lync Server 2013 中的憑證摘要-自動</A>探索。</span><span class="sxs-lookup"><span data-stu-id="b702f-121">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see <A href="lync-server-2013-certificate-summary-autodiscover.md">Certificate summary - Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b702f-122">本章節內容</span><span class="sxs-lookup"><span data-stu-id="b702f-122">In This Section</span></span>

  - [<span data-ttu-id="b702f-123">Lync Server 2013 中的憑證摘要-自動探索</span><span class="sxs-lookup"><span data-stu-id="b702f-123">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)

  - [<span data-ttu-id="b702f-124">Lync Server 2013 中的埠摘要-自動探索</span><span class="sxs-lookup"><span data-stu-id="b702f-124">Port summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-port-summary-autodiscover.md)

  - [<span data-ttu-id="b702f-125">Lync Server 2013 中的 DNS 摘要-自動探索</span><span class="sxs-lookup"><span data-stu-id="b702f-125">DNS summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-dns-summary-autodiscover.md)

  - [<span data-ttu-id="b702f-126">Lync Server 2013 中的混合式和分割網域自動探索</span><span class="sxs-lookup"><span data-stu-id="b702f-126">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

