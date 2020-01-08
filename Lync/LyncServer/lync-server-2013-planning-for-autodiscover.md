---
title: Lync Server 2013：規劃自動探索
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a1d0ce7a775bc73c5f3afa10d1f9c148395b0eb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977734"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="559ac-102">規劃 Lync Server 2013 中的自動探索</span><span class="sxs-lookup"><span data-stu-id="559ac-102">Planning for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="559ac-103">_**主題上次修改日期：** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="559ac-103">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="559ac-104">在 Lync server 2010 （2011年11月）累計更新中，會針對 Lync Server 推出自動探索功能。</span><span class="sxs-lookup"><span data-stu-id="559ac-104">Autodiscover was introduced for Lync Server in the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="559ac-105">此初始的自動探索實現的主要用途是提供 Lync Mobile 的一種方法來找出行動服務（Mcx）。</span><span class="sxs-lookup"><span data-stu-id="559ac-105">The primary purpose for this initial implementation of Autodiscover was to provide a means for Lync Mobile to locate the Mobility service (Mcx).</span></span> <span data-ttu-id="559ac-106">Lync Server 2013 中的自動探索服務現已成為所有用戶端用來尋找伺服器和使用者服務的服務。</span><span class="sxs-lookup"><span data-stu-id="559ac-106">The Autodiscover service in Lync Server 2013 is now a service used by all clients to locate server and user services.</span></span> <span data-ttu-id="559ac-107">Microsoft Lync Server 2013 自動探索服務會在控制器和前端伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="559ac-107">The Microsoft Lync Server 2013 Autodiscover service runs on Directors and Front End Servers.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="559ac-108">如需深入瞭解自動探索以及傳送給用戶端的內容，請參閱<A href="lync-server-2013-understanding-autodiscover.md">瞭解 Lync Server 2013 中的自動</A>探索。</span><span class="sxs-lookup"><span data-stu-id="559ac-108">For a more technical understanding of Autodiscover and what is communicated to clients, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="559ac-109">行動性仍是一個獨特的案例，行動服務仍需要一些特殊規劃。</span><span class="sxs-lookup"><span data-stu-id="559ac-109">Mobility is still a distinct scenario and the Mobility services still require some special planning.</span></span> <span data-ttu-id="559ac-110">如需其他詳細資料，請參閱<A href="lync-server-2013-planning-for-mobility.md">在 Lync Server 2013 中規劃行動</A>。</span><span class="sxs-lookup"><span data-stu-id="559ac-110">For additional details, see <A href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="559ac-111">當 [Lync Server 2010] 中推出 [自動探索] 時，需要進行一些折衷，才能實現需要對現有伺服器部署有潛在證書變更的服務。</span><span class="sxs-lookup"><span data-stu-id="559ac-111">When Autodiscover was introduced in Lync Server 2010, there were compromises that needed to be made in order to implement a service that required potential certificate changes to existing server deployments.</span></span> <span data-ttu-id="559ac-112">自動探索可用於 HTTPS 的埠 TCP 443，或經由埠 TCP 80 （針對 HTTP）使用。</span><span class="sxs-lookup"><span data-stu-id="559ac-112">Autodiscover could be used over port TCP 443 for HTTPS or over port TCP 80 for HTTP.</span></span> <span data-ttu-id="559ac-113">如果決定使用 HTTPS，必須重新頒發反向代理、控制器和前端伺服器上的憑證，才能容納必要`lyncdiscover.<domain>`的`lyncdiscoverinternal.<domain>` DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="559ac-113">If the decision was made to use HTTPS, certificates on reverse proxies, Directors, and Front End Servers needed to be reissued in order to accommodate the required `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` DNS records.</span></span> <span data-ttu-id="559ac-114">如果決定要使用 HTTP，您可以使用 DNS CNAME （或別名）記錄來避免重新頒發憑證，以使用憑證上現有的名稱。</span><span class="sxs-lookup"><span data-stu-id="559ac-114">If the decision was to use HTTP, the reissue of certificates could be avoided by using DNS CNAME (or alias) records to use existing names on the certificates.</span></span> <span data-ttu-id="559ac-115">使用 HTTP 是指未加密初始通訊。</span><span class="sxs-lookup"><span data-stu-id="559ac-115">Using HTTP did mean that the initial communications were unencrypted.</span></span>

<span data-ttu-id="559ac-116">由於 Lync Server 2013 使用所有用戶端的自動探索功能，因此主要案例是使用 HTTPS，並以 lyncdiscover 建立證書。\<[\>網域] 做為反向代理、控制器和前端伺服器的設定的一部分。</span><span class="sxs-lookup"><span data-stu-id="559ac-116">Because Lync Server 2013 uses Autodiscover for all clients, the main scenario is to use HTTPS exclusively and to create certificates with lyncdiscover.\<domain\> as part of the configuration of reverse proxies, Directors and Front End Servers.</span></span> <span data-ttu-id="559ac-117">如果您要從 Lync Server 2010 將自動探索實現到升級後的部署，您可能會想要使用 HTTP 來避免重新頒發憑證。</span><span class="sxs-lookup"><span data-stu-id="559ac-117">If you are implementing Autodiscover into an upgraded deployment from Lync Server 2010, you may want to use HTTP to avoid reissuing certificates.</span></span> <span data-ttu-id="559ac-118">下列各節提供這兩個案例的指導方針。</span><span class="sxs-lookup"><span data-stu-id="559ac-118">Guidance for both scenarios is provided in the following sections.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="559ac-119">外部 web 服務發佈規則所使用的憑證上的 [subject 替換名稱] 清單必須包含<EM>lyncdiscover&lt; 。針對&gt; </EM>貴組織內的每個 SIP 網域 sipdomain 專案。</span><span class="sxs-lookup"><span data-stu-id="559ac-119">The subject alternative name list on certificates used by the external web services publishing rule must contain a <EM>lyncdiscover.&lt;sipdomain&gt;</EM> entry for each SIP domain within your organization.</span></span> <span data-ttu-id="559ac-120">如需董事、前端伺服器及反向 proxy 所需的主題替換名稱專案的詳細資料，請參閱<A href="lync-server-2013-certificate-summary-autodiscover.md">在 Lync Server 2013 中</A>的 [自動探索]。</span><span class="sxs-lookup"><span data-stu-id="559ac-120">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see <A href="lync-server-2013-certificate-summary-autodiscover.md">Certificate summary - Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="559ac-121">本節內容</span><span class="sxs-lookup"><span data-stu-id="559ac-121">In This Section</span></span>

  - [<span data-ttu-id="559ac-122">憑證摘要-Lync Server 2013 中的自動探索</span><span class="sxs-lookup"><span data-stu-id="559ac-122">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)

  - [<span data-ttu-id="559ac-123">埠摘要-Lync Server 2013 中的自動探索</span><span class="sxs-lookup"><span data-stu-id="559ac-123">Port summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-port-summary-autodiscover.md)

  - [<span data-ttu-id="559ac-124">DNS 摘要-Lync Server 2013 中的自動探索</span><span class="sxs-lookup"><span data-stu-id="559ac-124">DNS summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-dns-summary-autodiscover.md)

  - [<span data-ttu-id="559ac-125">Lync Server 2013 中的混合式和剝離網域自動探索</span><span class="sxs-lookup"><span data-stu-id="559ac-125">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

