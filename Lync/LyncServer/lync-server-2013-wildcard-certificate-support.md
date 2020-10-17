---
title: Lync Server 2013 萬用字元憑證支援
description: Lync Server 2013 萬用字元憑證支援。
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
ms.openlocfilehash: 46cc362eb925a86b5e90d51569db6d425ba88fa6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546109"
---
# <a name="wildcard-certificate-support-in-lync-server-2013"></a><span data-ttu-id="eef73-103">Lync Server 2013 中的萬用字元憑證支援</span><span class="sxs-lookup"><span data-stu-id="eef73-103">Wildcard certificate support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eef73-104">_**主題上次修改日期：** 2013-03-21_</span><span class="sxs-lookup"><span data-stu-id="eef73-104">_**Topic Last Modified:** 2013-03-21_</span></span>

<span data-ttu-id="eef73-105">Lync Server 2013 使用憑證來提供通訊加密和伺服器身分識別驗證。</span><span class="sxs-lookup"><span data-stu-id="eef73-105">Lync Server 2013 uses certificates to provide communications encryption and server identity authentication.</span></span> <span data-ttu-id="eef73-106">某些情況下，例如透過反向 Proxy 的 Web 發佈，不需要與代表服務之伺服器完整網域名稱 (FQDN) 相符的強式主體替代名稱 (SAN) 項目。</span><span class="sxs-lookup"><span data-stu-id="eef73-106">In some cases, such as web publishing through the reverse proxy, strong subject alternative name (SAN) entry matching to the fully qualified domain name (FQDN) of the server presenting the service is not required.</span></span> <span data-ttu-id="eef73-107">在這些情況下，您可以使用含萬用字元 SAN 項目的憑證 (一般稱為「萬用字元憑證」) 來降低從公用憑證授權單位要求憑證的成本，並能降低憑證的規劃程序複雜度。</span><span class="sxs-lookup"><span data-stu-id="eef73-107">In these cases, you can use certificates with wildcard SAN entries (commonly known as “wildcard certificates”) to reduce the cost of a certificate requested from a public certification authority and to reduce the complexity of the planning process for certificates.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="eef73-108">若要保留整合通訊 (UC) 裝置 (例如，電話機) 的功能，您應該仔細測試部署的憑證，確定實作萬用字元憑證之後，裝置的功能正常運作。</span><span class="sxs-lookup"><span data-stu-id="eef73-108">To retain the functionality of unified communications (UC) devices (for example, desk phones), you should test the deployed certificate carefully to ensure that devices function properly after you implement a wildcard certificate.</span></span>



</div>

<span data-ttu-id="eef73-p102">不支援將萬用字元項目做為任何角色的主體名稱 (又稱為一般名稱或 CN)。在 SAN 中使用萬用字元項目時，支援下列伺服器角色：</span><span class="sxs-lookup"><span data-stu-id="eef73-p102">There is no support for a wildcard entry as the subject name (also referred to as the common name or CN) for any role. The following server roles are supported when using wildcard entries in the SAN:</span></span>

  - <span></span>  
    <span data-ttu-id="eef73-111">**反向 proxy。**    萬用字元 SAN 專案支援簡單 URL (符合和撥入) 發行憑證。</span><span class="sxs-lookup"><span data-stu-id="eef73-111">**Reverse proxy.**   Wildcard SAN entry is supported for Simple URL (meet and dialin) publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="eef73-112">**反向 proxy。**    LyncDiscover 發佈憑證上的 SAN 專案支援萬用字元 SAN 專案。</span><span class="sxs-lookup"><span data-stu-id="eef73-112">**Reverse proxy.**   Wildcard SAN entry is supported for the SAN entries for LyncDiscover on the publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="eef73-113">**Director。**    在簡單的 URLs 中支援萬用字元 SAN 專案， (會在 [Director] 網頁元件中符合和撥出) 和 LyncDiscover 及 LyncDiscoverInternal 的 SAN 專案。</span><span class="sxs-lookup"><span data-stu-id="eef73-113">**Director.**   Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Director web components.</span></span>

  - <span></span>  
    <span data-ttu-id="eef73-114">**前端伺服器 (Standard Edition) 和前端集區 (Enterprise Edition) 。**</span><span class="sxs-lookup"><span data-stu-id="eef73-114">**Front End Server (Standard Edition) and Front End pool (Enterprise Edition).**</span></span> <span data-ttu-id="eef73-115">針對簡易 URLs，可支援萬用字元 SAN 專案， (在) 和撥入前端 web 元件中的 LyncDiscover 和 LyncDiscoverInternal 的 SAN 專案。</span><span class="sxs-lookup"><span data-stu-id="eef73-115">Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Front End web components.</span></span>

  - <span></span>  
    <span data-ttu-id="eef73-116">**Exchange 整合通訊 (UM) 。**    伺服器在部署為獨立伺服器時，不會使用 SAN 專案。</span><span class="sxs-lookup"><span data-stu-id="eef73-116">**Exchange Unified Messaging (UM).**   The server does not use SAN entries when deployed as a stand-alone server.</span></span>

  - <span></span>  
    <span data-ttu-id="eef73-117">**Microsoft Exchange Server Client Access Server。**    內部和外部用戶端支援 SAN 中的萬用字元專案。</span><span class="sxs-lookup"><span data-stu-id="eef73-117">**Microsoft Exchange Server Client Access server.**   Wildcard entries in the SAN are supported for internal and external clients.</span></span>

  - <span></span>  
    <span data-ttu-id="eef73-118">**Exchange 整合通訊 (UM) 與同一部伺服器上的 Microsoft Exchange Server Client Access server。**    支援萬用字元 SAN 專案。</span><span class="sxs-lookup"><span data-stu-id="eef73-118">**Exchange Unified Messaging (UM) and Microsoft Exchange Server Client Access server on same server.**   Wildcard SAN entries are supported.</span></span>

<span data-ttu-id="eef73-119">本主題中未介紹的伺服器角色：</span><span class="sxs-lookup"><span data-stu-id="eef73-119">Server roles that are not addressed in this topic:</span></span>

  - <span data-ttu-id="eef73-120">內部伺服器角色 (包括（但不限於）轉送伺服器、封存和監控伺服器、Survivable 分支裝置或 Survivable Branch 伺服器) </span><span class="sxs-lookup"><span data-stu-id="eef73-120">Internal server roles (including, but not limited to the Mediation Server, Archiving and Monitoring Server, Survivable Branch Appliance, or Survivable Branch Server)</span></span>

  - <span data-ttu-id="eef73-121">外部 Edge Server 介面</span><span class="sxs-lookup"><span data-stu-id="eef73-121">External Edge Server interfaces</span></span>

  - <span data-ttu-id="eef73-122">內部 Edge Server</span><span class="sxs-lookup"><span data-stu-id="eef73-122">Internal Edge Server</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eef73-123">針對內部 Edge Server 介面，可以將萬用字元專案指派給 SAN，而且支援此專案。</span><span class="sxs-lookup"><span data-stu-id="eef73-123">For the internal Edge Server interface, a wildcard entry can be assigned to the SAN, and is supported.</span></span> <span data-ttu-id="eef73-124">不會查詢內部 Edge Server 上的 SAN，而且萬用字元 SAN 專案的值有限。</span><span class="sxs-lookup"><span data-stu-id="eef73-124">The SAN on the internal Edge Server is not queried, and a wildcard SAN entry is of limited value.</span></span>

    
    </div>

<span data-ttu-id="eef73-125">如需憑證設定的詳細資料，包括憑證中的萬用字元使用，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="eef73-125">For details about certificate configurations, including the use of wildcards in certificates, see the following topics:</span></span>

  - [<span data-ttu-id="eef73-126">Lync Server 2013 中內部伺服器的憑證需求</span><span class="sxs-lookup"><span data-stu-id="eef73-126">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="eef73-127">Lync Server 2013 中外部使用者存取的憑證需求</span><span class="sxs-lookup"><span data-stu-id="eef73-127">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="eef73-128">Lync Server 2013 的憑證摘要-DNS 與 HLB 負載平衡</span><span class="sxs-lookup"><span data-stu-id="eef73-128">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="eef73-129">Lync Server 2013 中的憑證摘要-單一 Director</span><span class="sxs-lookup"><span data-stu-id="eef73-129">Certificate summary - Single Director in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-director.md)

  - [<span data-ttu-id="eef73-130">Lync Server 2013 中的憑證摘要-調整式 Director 集區（硬體負載平衡器）</span><span class="sxs-lookup"><span data-stu-id="eef73-130">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="eef73-131">Lync Server 2013 的憑證摘要-反向 proxy</span><span class="sxs-lookup"><span data-stu-id="eef73-131">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="eef73-132">整合內部部署整合通訊和 Lync Server 2013 的指導方針</span><span class="sxs-lookup"><span data-stu-id="eef73-132">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

<span data-ttu-id="eef73-133">如需有關為 Exchange 設定憑證的詳細資訊，包括使用萬用字元，請參閱 Exchange 2013 產品檔。</span><span class="sxs-lookup"><span data-stu-id="eef73-133">For details about configuring certificates for Exchange, including the use of wildcards, see the Exchange 2013 product documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

