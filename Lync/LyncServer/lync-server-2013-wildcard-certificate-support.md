---
title: Lync Server 2013 萬用字元憑證支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Wildcard certificate support
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202161(v=OCS.15)
ms:contentKeyID: 48183382
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18b1313432cac09f03cd414b90d9a068f271edef
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a><span data-ttu-id="c5863-102">Lync Server 2013 中的萬用字元憑證支援</span><span class="sxs-lookup"><span data-stu-id="c5863-102">Wildcard certificate support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5863-103">_**上次修改主題：** 2013年-03-21_</span><span class="sxs-lookup"><span data-stu-id="c5863-103">_**Topic Last Modified:** 2013-03-21_</span></span>

<span data-ttu-id="c5863-104">Lync Server 2013 使用憑證來提供通訊加密] 及 [server 身分識別驗證。</span><span class="sxs-lookup"><span data-stu-id="c5863-104">Lync Server 2013 uses certificates to provide communications encryption and server identity authentication.</span></span> <span data-ttu-id="c5863-105">某些情況下，例如透過反向 Proxy 的 Web 發佈，不需要與代表服務之伺服器完整網域名稱 (FQDN) 相符的強式主體替代名稱 (SAN) 項目。</span><span class="sxs-lookup"><span data-stu-id="c5863-105">In some cases, such as web publishing through the reverse proxy, strong subject alternative name (SAN) entry matching to the fully qualified domain name (FQDN) of the server presenting the service is not required.</span></span> <span data-ttu-id="c5863-106">在這些情況下，您可以使用含萬用字元 SAN 項目的憑證 (一般稱為「萬用字元憑證」) 來降低從公用憑證授權單位要求憑證的成本，並能降低憑證的規劃程序複雜度。</span><span class="sxs-lookup"><span data-stu-id="c5863-106">In these cases, you can use certificates with wildcard SAN entries (commonly known as “wildcard certificates”) to reduce the cost of a certificate requested from a public certification authority and to reduce the complexity of the planning process for certificates.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="c5863-107">若要保留整合通訊 (UC) 裝置 (例如，電話機) 的功能，您應該仔細測試部署的憑證，確定實作萬用字元憑證之後，裝置的功能正常運作。</span><span class="sxs-lookup"><span data-stu-id="c5863-107">To retain the functionality of unified communications (UC) devices (for example, desk phones), you should test the deployed certificate carefully to ensure that devices function properly after you implement a wildcard certificate.</span></span>



</div>

<span data-ttu-id="c5863-p102">不支援將萬用字元項目做為任何角色的主體名稱 (又稱為一般名稱或 CN)。在 SAN 中使用萬用字元項目時，支援下列伺服器角色：</span><span class="sxs-lookup"><span data-stu-id="c5863-p102">There is no support for a wildcard entry as the subject name (also referred to as the common name or CN) for any role. The following server roles are supported when using wildcard entries in the SAN:</span></span>

  - <span></span>  
    <span data-ttu-id="c5863-110">**反向 proxy。**   簡單 URL （meet 和 dialin） 發行的憑證可支援萬用字元 SAN 項目。</span><span class="sxs-lookup"><span data-stu-id="c5863-110">**Reverse proxy.**   Wildcard SAN entry is supported for Simple URL (meet and dialin) publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="c5863-111">**反向 proxy。**   萬用字元 SAN 項目都支援 SAN 項目中的 LyncDiscover 發行的憑證。</span><span class="sxs-lookup"><span data-stu-id="c5863-111">**Reverse proxy.**   Wildcard SAN entry is supported for the SAN entries for LyncDiscover on the publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="c5863-112">**Director。**   萬用字元 SAN 項目支援簡單 Url （meet 和 dialin） 和 SAN 項目 LyncDiscover 和 LyncDiscoverInternal Director web 元件。</span><span class="sxs-lookup"><span data-stu-id="c5863-112">**Director.**   Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Director web components.</span></span>

  - <span></span>  
    <span data-ttu-id="c5863-113">**前端伺服器 (Standard Edition) 及前端集區 (Enterprise Edition)。**</span><span class="sxs-lookup"><span data-stu-id="c5863-113">**Front End Server (Standard Edition) and Front End pool (Enterprise Edition).**</span></span> <span data-ttu-id="c5863-114">萬用字元 SAN 項目支援簡單 url （meet 和 dialin），和 SAN 項目 LyncDiscover 和 LyncDiscoverInternal 前方結束 web 元件。</span><span class="sxs-lookup"><span data-stu-id="c5863-114">Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Front End web components.</span></span>

  - <span></span>  
    <span data-ttu-id="c5863-115">**Exchange 整合通訊 (UM)。**   伺服器不會使用 SAN 項目部署為獨立伺服器時。</span><span class="sxs-lookup"><span data-stu-id="c5863-115">**Exchange Unified Messaging (UM).**   The server does not use SAN entries when deployed as a stand-alone server.</span></span>

  - <span></span>  
    <span data-ttu-id="c5863-116">**Microsoft Exchange Server 用戶端存取伺服器。**   內部和外部用戶端支援在 SAN 中的萬用字元項目。</span><span class="sxs-lookup"><span data-stu-id="c5863-116">**Microsoft Exchange Server Client Access server.**   Wildcard entries in the SAN are supported for internal and external clients.</span></span>

  - <span></span>  
    <span data-ttu-id="c5863-117">**在同一部伺服器上的 Exchange 整合通訊 (UM) 及 Microsoft Exchange Server 用戶端存取伺服器。**   支援萬用字元 SAN 項目。</span><span class="sxs-lookup"><span data-stu-id="c5863-117">**Exchange Unified Messaging (UM) and Microsoft Exchange Server Client Access server on same server.**   Wildcard SAN entries are supported.</span></span>

<span data-ttu-id="c5863-118">本主題中未介紹的伺服器角色：</span><span class="sxs-lookup"><span data-stu-id="c5863-118">Server roles that are not addressed in this topic:</span></span>

  - <span data-ttu-id="c5863-119">內部伺服器角色 （包括，但不是限於中繼伺服器、 封存和監控伺服器、 Survivable Branch Appliance 或 Survivable Branch 伺服器）</span><span class="sxs-lookup"><span data-stu-id="c5863-119">Internal server roles (including, but not limited to the Mediation Server, Archiving and Monitoring Server, Survivable Branch Appliance, or Survivable Branch Server)</span></span>

  - <span data-ttu-id="c5863-120">外部 Edge Server 介面</span><span class="sxs-lookup"><span data-stu-id="c5863-120">External Edge Server interfaces</span></span>

  - <span data-ttu-id="c5863-121">內部 Edge Server</span><span class="sxs-lookup"><span data-stu-id="c5863-121">Internal Edge Server</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c5863-122">內部的 Edge Server 介面的萬用字元項目可以指派給 SAN (英文），並支援。</span><span class="sxs-lookup"><span data-stu-id="c5863-122">For the internal Edge Server interface, a wildcard entry can be assigned to the SAN, and is supported.</span></span> <span data-ttu-id="c5863-123">SAN (英文） 內部 Edge Server 上不在查詢中，而且萬用字元 SAN 項目時限制的值。</span><span class="sxs-lookup"><span data-stu-id="c5863-123">The SAN on the internal Edge Server is not queried, and a wildcard SAN entry is of limited value.</span></span>

    
    </div>

<span data-ttu-id="c5863-124">如需詳細資訊的憑證組態，包括萬用字元的使用中的憑證，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="c5863-124">For details about certificate configurations, including the use of wildcards in certificates, see the following topics:</span></span>

  - [<span data-ttu-id="c5863-125">適用於 Lync Server 2013 中的內部伺服器的憑證需求</span><span class="sxs-lookup"><span data-stu-id="c5863-125">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="c5863-126">Lync Server 2013 中的外部使用者存取的憑證需求</span><span class="sxs-lookup"><span data-stu-id="c5863-126">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="c5863-127">憑證摘要-DNS 與 HLB 負載平衡 Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="c5863-127">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="c5863-128">憑證摘要-Lync Server 2013 中的單一 Director</span><span class="sxs-lookup"><span data-stu-id="c5863-128">Certificate summary - Single Director in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-director.md)

  - [<span data-ttu-id="c5863-129">憑證摘要-調整式 Director 集區、 Lync Server 2013 中的硬體負載平衡器</span><span class="sxs-lookup"><span data-stu-id="c5863-129">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="c5863-130">憑證摘要-Lync Server 2013 中的反向 proxy</span><span class="sxs-lookup"><span data-stu-id="c5863-130">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="c5863-131">指導方針整合內部 Unified Messaging 和 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5863-131">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

<span data-ttu-id="c5863-132">如需設定 Exchange，包括萬用字元，請使用憑證的詳細資訊請參閱 < Exchange 2013 產品的說明文件。</span><span class="sxs-lookup"><span data-stu-id="c5863-132">For details about configuring certificates for Exchange, including the use of wildcards, see the Exchange 2013 product documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

