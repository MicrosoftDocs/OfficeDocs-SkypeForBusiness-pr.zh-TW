---
title: Lync Server 2013：反向 Proxy 案例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for reverse proxy
ms:assetid: 13108f59-a660-4ff1-8404-079d1cb646f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204691(v=OCS.15)
ms:contentKeyID: 48183468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82e1dffa55d6af8d131d3a94710c76277cfa75d9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="1c5e5-102">Lync Server 2013 中的反向 Proxy 案例</span><span class="sxs-lookup"><span data-stu-id="1c5e5-102">Scenarios for reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c5e5-103">_**主題上次修改日期：** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="1c5e5-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="1c5e5-104">Lync Server 2013 需要使用反向代理，提供對服務和資源（例如會議和撥入式簡易 Url、通訊錄、會議內容、通訊群組清單展開、行動服務等）的存取權。</span><span class="sxs-lookup"><span data-stu-id="1c5e5-104">Reverse proxies are required in Lync Server 2013 for providing access to services and resources such as the meeting and dial-in Simple URLs, address book, meeting content, distribution list expansion, mobility services, and others.</span></span> <span data-ttu-id="1c5e5-105">Lync Server 2013 中的典型反向 proxy 案例是允許外部用戶端（例如桌面用戶端或 Lync Web App 用戶端）存取控制器或前端伺服器外部 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="1c5e5-105">The typical reverse proxy scenario in Lync Server 2013 is to allow external clients (for example, the desktop client or Lync Web App client) access to the Director or Front End Server external Web Services.</span></span>

<span data-ttu-id="1c5e5-106">**反向 proxy 與外部 web 服務**</span><span class="sxs-lookup"><span data-stu-id="1c5e5-106">**Reverse proxy and external web services**</span></span>

<span data-ttu-id="1c5e5-107">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="1c5e5-107">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>

<span data-ttu-id="1c5e5-108">在規劃階段，您可以在 Lync Server 2013 部署中定義反向 proxy 的需求。</span><span class="sxs-lookup"><span data-stu-id="1c5e5-108">During the planning phase, you define the requirements for the reverse proxy in a Lync Server 2013 deployment.</span></span> <span data-ttu-id="1c5e5-109">反向 proxy 可讓您存取下列外部用戶端的功能：</span><span class="sxs-lookup"><span data-stu-id="1c5e5-109">The reverse proxy enables access to features for the following external clients:</span></span>

  - <span data-ttu-id="1c5e5-110">Microsoft Lync 2013 桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="1c5e5-110">Microsoft Lync 2013 desktop client</span></span>

  - <span data-ttu-id="1c5e5-111">Microsoft Lync Web App</span><span class="sxs-lookup"><span data-stu-id="1c5e5-111">Microsoft Lync Web App</span></span>

  - <span data-ttu-id="1c5e5-112">Microsoft Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="1c5e5-112">Microsoft Lync Mobile</span></span>

  - <span data-ttu-id="1c5e5-113">Lync Windows Store 應用程式</span><span class="sxs-lookup"><span data-stu-id="1c5e5-113">Lync Windows Store app</span></span>

<span data-ttu-id="1c5e5-114">規劃 Lync Server 2013 部署時，您會將 Lync Server 2013 的實際需求對應到反向 proxy 的功能。</span><span class="sxs-lookup"><span data-stu-id="1c5e5-114">When planning your Lync Server 2013 deployment, you map the actual requirements for Lync Server 2013 to the reverse proxy features.</span></span>

1.  <span data-ttu-id="1c5e5-115">外部用戶端會連線到埠 TCP 443 上的反向 proxy，並將使用安全通訊端層（SSL）或傳輸層安全性（TLS）。</span><span class="sxs-lookup"><span data-stu-id="1c5e5-115">External clients will connect to the reverse proxy on port TCP 443 and will use secure socket layer (SSL) or transport layer security (TLS).</span></span> <span data-ttu-id="1c5e5-116">Microsoft Lync Mobile 用戶端可以在埠 TCP 80 上連線，但只會在執行 Lync 探索服務的初始連線時，且系統管理員已設定正確的網域名稱系統（DNS） CNAME （或別名）記錄，並接受此通訊不會加密。</span><span class="sxs-lookup"><span data-stu-id="1c5e5-116">Microsoft Lync Mobile clients can connect on port TCP 80, but only when performing the initial connection to the Lync discover services and the administrator has configured the proper domain name system (DNS) CNAME (or alias) records, and accepts that this communication will not be encrypted.</span></span>

2.  <span data-ttu-id="1c5e5-117">Lync Server 2013 外部 web 服務（在前端伺服器和/或控制器上部署）預期從埠 TCP 4443 上的反向 proxy 進行連線，而且預期該連線將是 SSL/TLS。</span><span class="sxs-lookup"><span data-stu-id="1c5e5-117">Lync Server 2013 external web services (deployed on the Front End Server and/or the Director) expect a connection from a reverse proxy on port TCP 4443, and it expects that the connection will be SSL/TLS.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1c5e5-118">針對外部 web 服務建議的預設偵聽埠是 HTTP 流量的 TCP 8080，以及 HTTPS 流量的 TCP 4443。</span><span class="sxs-lookup"><span data-stu-id="1c5e5-118">The suggested default listening ports for the external web services are TCP 8080 for HTTP traffic, and TCP 4443 for HTTPS traffic.</span></span> <span data-ttu-id="1c5e5-119">[拓撲建立器] 提供可覆寫預設值並定義您自己的外部 web 服務偵聽埠的機會。</span><span class="sxs-lookup"><span data-stu-id="1c5e5-119">Topology Builder provides an opportunity to override the defaults and define your own listening ports for the external web services.</span></span> <span data-ttu-id="1c5e5-120">請務必注意，反向 proxy 會與外部 web 服務進行通訊，而外部用戶端則與反向 proxy 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="1c5e5-120">It’s important to note that the reverse proxy communicates with the external web services, and the external clients communicate with the reverse proxy.</span></span> <span data-ttu-id="1c5e5-121">外部用戶端與埠 TCP 443 上的反向 proxy 通訊，但您可以重新定義反向 proxy 與外部 web 服務通訊的埠。</span><span class="sxs-lookup"><span data-stu-id="1c5e5-121">The external client communicates with the reverse proxy on port TCP 443, but you can redefine what port the reverse proxy communicates with the external web services on.</span></span> <span data-ttu-id="1c5e5-122">拓撲 Builder 中的選項可覆寫 web 服務的預設偵聽埠，可讓您解決基礎結構中可能會發生的偵聽埠衝突。</span><span class="sxs-lookup"><span data-stu-id="1c5e5-122">The options in Topology Builder to override the default listening ports for the web services allows you to resolve listening port conflicts that may arise in your infrastructure.</span></span>

    
    </div>

3.  <span data-ttu-id="1c5e5-123">Lync Server 2013 外部 web 服務需要來自用戶端的未修改主機標頭，以找出用戶端嘗試使用的服務和 web 伺服器目錄。</span><span class="sxs-lookup"><span data-stu-id="1c5e5-123">Lync Server 2013 external web services expect an unmodified Host Header from the client to identify what service and web server directory the client is attempting to use.</span></span> <span data-ttu-id="1c5e5-124">要求應看起來像是來自反向 proxy</span><span class="sxs-lookup"><span data-stu-id="1c5e5-124">Requests should appear as if they came from the reverse proxy</span></span>

4.  <span data-ttu-id="1c5e5-125">外部 web 服務使用已定義的 web 伺服器虛擬目錄（vDir），提供提供給用戶端的服務。</span><span class="sxs-lookup"><span data-stu-id="1c5e5-125">The external web services use defined web server virtual directories (vDir) that provide the services offered to clients.</span></span> <span data-ttu-id="1c5e5-126">特定的外部可識別 web 服務包括：</span><span class="sxs-lookup"><span data-stu-id="1c5e5-126">Specific externally identifiable web services are:</span></span>
    
      - <span data-ttu-id="1c5e5-127">針對網路會議會議的 [會議] vDir</span><span class="sxs-lookup"><span data-stu-id="1c5e5-127">The “Meet” vDir for web conference meetings</span></span>
    
      - <span data-ttu-id="1c5e5-128">電話撥打電話給手機存取和電話會議的 vDir</span><span class="sxs-lookup"><span data-stu-id="1c5e5-128">The “Dialin” vDir for phone access and phone conferencing</span></span>
    
      - <span data-ttu-id="1c5e5-129">Lync Windows Store app、Lync Mobile 和桌面用戶端 Lync 2013 的 [自動探索] vDir。</span><span class="sxs-lookup"><span data-stu-id="1c5e5-129">The “Autodiscover” vDir for Lync Windows Store app, Lync Mobile, and the desktop client Lync 2013.</span></span> <span data-ttu-id="1c5e5-130">在 Lync Server 2013 中的自動探索是由 DNS 名稱 "lyncdiscover" 所知道</span><span class="sxs-lookup"><span data-stu-id="1c5e5-130">Autodiscover in Lync Server 2013 is known by the DNS name “lyncdiscover”</span></span>
    
      - <span data-ttu-id="1c5e5-131">未定義的服務會透過直接呼叫外部 web 服務的方式，由外部用戶端存取。</span><span class="sxs-lookup"><span data-stu-id="1c5e5-131">Services not defined are accessed by the external client by direct calls to the external web services.</span></span> <span data-ttu-id="1c5e5-132">例如，通訊群組延伸（DLX）和通訊錄服務（ABS）都是透過直接呼叫外部 web 服務和相關聯的 vDirs 來存取。</span><span class="sxs-lookup"><span data-stu-id="1c5e5-132">For example, distribution group expansion (DLX) and the address book service (ABS) are accessed by direct calls to the external web services and associated vDirs.</span></span> <span data-ttu-id="1c5e5-133">用戶端知道 vDir 的實際路徑，並根據此資訊構造統一式記錄定位器（URL）。</span><span class="sxs-lookup"><span data-stu-id="1c5e5-133">The client knows the actual path to the vDir and constructs a uniform record locator (URL) based on this information.</span></span> <span data-ttu-id="1c5e5-134">用戶端會使用類似以下的 URL 來存取通訊錄服務`https://externalweb.contoso.com/abs/handler`</span><span class="sxs-lookup"><span data-stu-id="1c5e5-134">The client would access the address book service using a URL similar to `https://externalweb.contoso.com/abs/handler`</span></span>
    
      - <span data-ttu-id="1c5e5-135">當會議已定義並設定為 Lync Server 拓撲的一部分時，為 Office Web Apps 伺服器</span><span class="sxs-lookup"><span data-stu-id="1c5e5-135">The Office Web Apps Server when conferencing is defined and configured as part of the Lync Server topology</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1c5e5-136">Office Web Apps 伺服器是一個獨立的角色服務器，且未設定為外部 Web 服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="1c5e5-136">The Office Web Apps Server is a separate role server and is not configured as part of the external web services.</span></span> <span data-ttu-id="1c5e5-137">此伺服器會另行發佈，以供用戶端存取。</span><span class="sxs-lookup"><span data-stu-id="1c5e5-137">This server is separately published for client access.</span></span>

        
        </div>

5.  <span data-ttu-id="1c5e5-138">針對每個服務定義 SSL 橋接。</span><span class="sxs-lookup"><span data-stu-id="1c5e5-138">Define SSL bridging for each service.</span></span> <span data-ttu-id="1c5e5-139">外部埠 TCP 443 對應至 TCP 4443 的外部 web 服務埠。</span><span class="sxs-lookup"><span data-stu-id="1c5e5-139">The external port TCP 443 is mapped to the external web services port of TCP 4443.</span></span> <span data-ttu-id="1c5e5-140">針對未加密的 HTTP，埠 TCP 80 對應至外部 web 服務埠 TCP 8080</span><span class="sxs-lookup"><span data-stu-id="1c5e5-140">For unencrypted HTTP, port TCP 80 is mapped to the external web services port TCP 8080</span></span>

6.  <span data-ttu-id="1c5e5-141">規劃反向 proxy 監聽器以發佈 web 伺服器資源</span><span class="sxs-lookup"><span data-stu-id="1c5e5-141">Plan for reverse proxy listeners to publish web server resources</span></span>

7.  <span data-ttu-id="1c5e5-142">根據將提供的服務，要求並設定反向 proxy 的憑證。</span><span class="sxs-lookup"><span data-stu-id="1c5e5-142">Request and configure the certificate for the reverse proxy based on the services that will be offered.</span></span> <span data-ttu-id="1c5e5-143">如果使用正確的消費者替換名稱進行設定，則此憑證可以由反向 proxy 伺服器上所有已設定的偵聽程式共用</span><span class="sxs-lookup"><span data-stu-id="1c5e5-143">If configured with the correct subject alternative names, this certificate can be shared by all configured listeners on the reverse proxy server</span></span>

<span data-ttu-id="1c5e5-144">可用來規劃反向 proxy 部署的資源：</span><span class="sxs-lookup"><span data-stu-id="1c5e5-144">Resources available for planning your reverse proxy deployment:</span></span>

  - [<span data-ttu-id="1c5e5-145">Lync Server 2013 中的資料收集</span><span class="sxs-lookup"><span data-stu-id="1c5e5-145">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="1c5e5-146">Lync Server 2013 中的憑證摘要 - 反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="1c5e5-146">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="1c5e5-147">Lync Server 2013 中的連接埠摘要 - 反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="1c5e5-147">Port summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-port-summary-reverse-proxy.md)

  - [<span data-ttu-id="1c5e5-148">Lync Server 2013 中的 DNS 摘要 - 反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="1c5e5-148">DNS summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

