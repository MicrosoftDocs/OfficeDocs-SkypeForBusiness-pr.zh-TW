---
title: Lync Server 2013 萬用字元憑證支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Wildcard certificate support
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202161(v=OCS.15)
ms:contentKeyID: 48183382
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9422c3bebbb5fb32be88cfe5c41968207bbed2ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a><span data-ttu-id="edfbb-102">Lync Server 2013 中的萬用字元憑證支援</span><span class="sxs-lookup"><span data-stu-id="edfbb-102">Wildcard certificate support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="edfbb-103">_**主題上次修改日期：** 2013-03-21_</span><span class="sxs-lookup"><span data-stu-id="edfbb-103">_**Topic Last Modified:** 2013-03-21_</span></span>

<span data-ttu-id="edfbb-104">Lync Server 2013 使用憑證來提供通訊加密和伺服器身分識別驗證。</span><span class="sxs-lookup"><span data-stu-id="edfbb-104">Lync Server 2013 uses certificates to provide communications encryption and server identity authentication.</span></span> <span data-ttu-id="edfbb-105">在某些情況下（例如透過反向 proxy 的 web 發佈），強主題替換名稱（SAN）專案與提供服務之伺服器的完整功能變數名稱（FQDN）不需要。</span><span class="sxs-lookup"><span data-stu-id="edfbb-105">In some cases, such as web publishing through the reverse proxy, strong subject alternative name (SAN) entry matching to the fully qualified domain name (FQDN) of the server presenting the service is not required.</span></span> <span data-ttu-id="edfbb-106">在這些情況下，您可以使用包含萬用字元 SAN 專案的憑證（通常稱為 "萬用字元"）來降低從公用憑證授權單位申請之憑證的成本，以及減少憑證規劃程式的複雜性.</span><span class="sxs-lookup"><span data-stu-id="edfbb-106">In these cases, you can use certificates with wildcard SAN entries (commonly known as “wildcard certificates”) to reduce the cost of a certificate requested from a public certification authority and to reduce the complexity of the planning process for certificates.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="edfbb-107">若要保留整合通訊（UC）裝置（例如，辦公桌電話）的功能，您應該仔細測試已部署的憑證，以確保在您執行萬用字元憑證後裝置正常運作。</span><span class="sxs-lookup"><span data-stu-id="edfbb-107">To retain the functionality of unified communications (UC) devices (for example, desk phones), you should test the deployed certificate carefully to ensure that devices function properly after you implement a wildcard certificate.</span></span>



</div>

<span data-ttu-id="edfbb-108">在任何角色中，都不支援萬用字元專案作為 subject 名稱（也稱為「公用名」或「CN」）。</span><span class="sxs-lookup"><span data-stu-id="edfbb-108">There is no support for a wildcard entry as the subject name (also referred to as the common name or CN) for any role.</span></span> <span data-ttu-id="edfbb-109">使用 SAN 中的萬用字元專案時，支援下列伺服器角色：</span><span class="sxs-lookup"><span data-stu-id="edfbb-109">The following server roles are supported when using wildcard entries in the SAN:</span></span>

  - <span></span>  
    <span data-ttu-id="edfbb-110">**反向 proxy。**   對於簡單的 URL （達到及撥入）發行憑證，支援萬用字元 SAN 專案。</span><span class="sxs-lookup"><span data-stu-id="edfbb-110">**Reverse proxy.**   Wildcard SAN entry is supported for Simple URL (meet and dialin) publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="edfbb-111">**反向 proxy。**   LyncDiscover 發佈憑證上的 san 專案支援萬用字元 san 專案。</span><span class="sxs-lookup"><span data-stu-id="edfbb-111">**Reverse proxy.**   Wildcard SAN entry is supported for the SAN entries for LyncDiscover on the publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="edfbb-112">**導演。**   對於簡單的 url （達到及撥入），以及適用于 LyncDiscover 和 LyncDiscoverInternal 網頁元件的 SAN 專案，都支援萬用字元 san 專案。</span><span class="sxs-lookup"><span data-stu-id="edfbb-112">**Director.**   Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Director web components.</span></span>

  - <span></span>  
    <span data-ttu-id="edfbb-113">**前端伺服器（標準版）和前端池（企業版）。**</span><span class="sxs-lookup"><span data-stu-id="edfbb-113">**Front End Server (Standard Edition) and Front End pool (Enterprise Edition).**</span></span> <span data-ttu-id="edfbb-114">對於簡單的 Url （達到及撥入），以及適用于 LyncDiscover 和 LyncDiscoverInternal （在前端網頁元件中）的 SAN 專案，都支援萬用字元 SAN 專案。</span><span class="sxs-lookup"><span data-stu-id="edfbb-114">Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Front End web components.</span></span>

  - <span></span>  
    <span data-ttu-id="edfbb-115">**Exchange 整合通訊（UM）。**   在部署成獨立伺服器時，伺服器不會使用 SAN 專案。</span><span class="sxs-lookup"><span data-stu-id="edfbb-115">**Exchange Unified Messaging (UM).**   The server does not use SAN entries when deployed as a stand-alone server.</span></span>

  - <span></span>  
    <span data-ttu-id="edfbb-116">**Microsoft Exchange Server 用戶端存取伺服器。**   內部和外部用戶端支援 SAN 中的萬用字元專案。</span><span class="sxs-lookup"><span data-stu-id="edfbb-116">**Microsoft Exchange Server Client Access server.**   Wildcard entries in the SAN are supported for internal and external clients.</span></span>

  - <span></span>  
    <span data-ttu-id="edfbb-117">**Exchange 整合通訊（UM）與相同伺服器上的 Microsoft Exchange Server 用戶端存取伺服器。**   支援萬用字元 SAN 專案。</span><span class="sxs-lookup"><span data-stu-id="edfbb-117">**Exchange Unified Messaging (UM) and Microsoft Exchange Server Client Access server on same server.**   Wildcard SAN entries are supported.</span></span>

<span data-ttu-id="edfbb-118">在本主題中未解決的伺服器角色：</span><span class="sxs-lookup"><span data-stu-id="edfbb-118">Server roles that are not addressed in this topic:</span></span>

  - <span data-ttu-id="edfbb-119">內部伺服器角色（包括但不限於中繼伺服器、封存及監視伺服器、Survivable 分支裝置或 Survivable 分支伺服器）</span><span class="sxs-lookup"><span data-stu-id="edfbb-119">Internal server roles (including, but not limited to the Mediation Server, Archiving and Monitoring Server, Survivable Branch Appliance, or Survivable Branch Server)</span></span>

  - <span data-ttu-id="edfbb-120">外部邊緣伺服器介面</span><span class="sxs-lookup"><span data-stu-id="edfbb-120">External Edge Server interfaces</span></span>

  - <span data-ttu-id="edfbb-121">內部邊緣伺服器</span><span class="sxs-lookup"><span data-stu-id="edfbb-121">Internal Edge Server</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="edfbb-122">針對內部邊緣伺服器介面，您可以將萬用字元專案指派給 SAN，而且受支援。</span><span class="sxs-lookup"><span data-stu-id="edfbb-122">For the internal Edge Server interface, a wildcard entry can be assigned to the SAN, and is supported.</span></span> <span data-ttu-id="edfbb-123">不會查詢內部邊緣伺服器上的 SAN，且萬用字元 SAN 專案的值有限。</span><span class="sxs-lookup"><span data-stu-id="edfbb-123">The SAN on the internal Edge Server is not queried, and a wildcard SAN entry is of limited value.</span></span>

    
    </div>

<span data-ttu-id="edfbb-124">如需憑證設定的詳細資料，包括在憑證中使用萬用字元，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="edfbb-124">For details about certificate configurations, including the use of wildcards in certificates, see the following topics:</span></span>

  - [<span data-ttu-id="edfbb-125">Lync Server 2013 中內部伺服器的憑證需求</span><span class="sxs-lookup"><span data-stu-id="edfbb-125">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="edfbb-126">Lync Server 2013 中的外部使用者存取的憑證需求</span><span class="sxs-lookup"><span data-stu-id="edfbb-126">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="edfbb-127">Lync Server 2013 中的憑證摘要 - DNS 與 HLB 負載平衡</span><span class="sxs-lookup"><span data-stu-id="edfbb-127">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="edfbb-128">Lync Server 2013 中的憑證摘要 - 單一 Director</span><span class="sxs-lookup"><span data-stu-id="edfbb-128">Certificate summary - Single Director in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-director.md)

  - [<span data-ttu-id="edfbb-129">Lync Server 2013 中的憑證摘要 - 調整式 Director 集區 (硬體負載平衡器)</span><span class="sxs-lookup"><span data-stu-id="edfbb-129">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="edfbb-130">Lync Server 2013 中的憑證摘要 - 反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="edfbb-130">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="edfbb-131">整合內部部署 Unified Messaging 和 Lync Server 2013 的指導方針</span><span class="sxs-lookup"><span data-stu-id="edfbb-131">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

<span data-ttu-id="edfbb-132">如需針對 Exchange 設定憑證的詳細資料，包括萬用字元的使用，請參閱 Exchange 2013 產品檔。</span><span class="sxs-lookup"><span data-stu-id="edfbb-132">For details about configuring certificates for Exchange, including the use of wildcards, see the Exchange 2013 product documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

