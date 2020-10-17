---
title: Lync Server 2013：反向 proxy 案例
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
ms.openlocfilehash: 767df1e427cd29e9437b4bd04d2859b382b48267
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510830"
---
# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="c31f2-102">Lync Server 2013 中的反向 proxy 案例</span><span class="sxs-lookup"><span data-stu-id="c31f2-102">Scenarios for reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c31f2-103">_**主題上次修改日期：** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="c31f2-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="c31f2-104">Lync Server 2013 需要反向 proxy，以提供對服務和資源的存取，例如會議和電話撥入式的簡易 URLs、通訊錄、會議內容、通訊群組清單展開、行動服務等等。</span><span class="sxs-lookup"><span data-stu-id="c31f2-104">Reverse proxies are required in Lync Server 2013 for providing access to services and resources such as the meeting and dial-in Simple URLs, address book, meeting content, distribution list expansion, mobility services, and others.</span></span> <span data-ttu-id="c31f2-105">Lync Server 2013 中的一般反向 proxy 案例是允許外部用戶端 (例如，桌面用戶端或 Lync Web App 用戶端) 存取 Director 或前端伺服器的外部 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="c31f2-105">The typical reverse proxy scenario in Lync Server 2013 is to allow external clients (for example, the desktop client or Lync Web App client) access to the Director or Front End Server external Web Services.</span></span>

<span data-ttu-id="c31f2-106">**反向 proxy 和外部 web 服務**</span><span class="sxs-lookup"><span data-stu-id="c31f2-106">**Reverse proxy and external web services**</span></span>

<span data-ttu-id="c31f2-107">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="c31f2-107">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>

<span data-ttu-id="c31f2-108">在規劃階段期間，您可以在 Lync Server 2013 部署中定義反向 proxy 的需求。</span><span class="sxs-lookup"><span data-stu-id="c31f2-108">During the planning phase, you define the requirements for the reverse proxy in a Lync Server 2013 deployment.</span></span> <span data-ttu-id="c31f2-109">反向 proxy 啟用下列外部用戶端的功能存取：</span><span class="sxs-lookup"><span data-stu-id="c31f2-109">The reverse proxy enables access to features for the following external clients:</span></span>

  - <span data-ttu-id="c31f2-110">Microsoft Lync 2013 桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="c31f2-110">Microsoft Lync 2013 desktop client</span></span>

  - <span data-ttu-id="c31f2-111">Microsoft Lync Web App</span><span class="sxs-lookup"><span data-stu-id="c31f2-111">Microsoft Lync Web App</span></span>

  - <span data-ttu-id="c31f2-112">Microsoft Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="c31f2-112">Microsoft Lync Mobile</span></span>

  - <span data-ttu-id="c31f2-113">Lync Windows Store 應用程式</span><span class="sxs-lookup"><span data-stu-id="c31f2-113">Lync Windows Store app</span></span>

<span data-ttu-id="c31f2-114">規劃 Lync Server 2013 部署時，會將 Lync Server 2013 的實際需求對應至反向 proxy 功能。</span><span class="sxs-lookup"><span data-stu-id="c31f2-114">When planning your Lync Server 2013 deployment, you map the actual requirements for Lync Server 2013 to the reverse proxy features.</span></span>

1.  <span data-ttu-id="c31f2-115">外部用戶端會連接到埠 TCP 443 上的反向 proxy，並使用安全通訊端層 (SSL) 或傳輸層安全性 (TLS) 。</span><span class="sxs-lookup"><span data-stu-id="c31f2-115">External clients will connect to the reverse proxy on port TCP 443 and will use secure socket layer (SSL) or transport layer security (TLS).</span></span> <span data-ttu-id="c31f2-116">Microsoft Lync Mobile 用戶端可以在埠 TCP 80 上進行連線，但只有在執行 Lync 探索服務的初始連線時，系統會將正確的網域名稱系統設定 (DNS) CNAME (或別名) 記錄，並接受此通訊不會加密。</span><span class="sxs-lookup"><span data-stu-id="c31f2-116">Microsoft Lync Mobile clients can connect on port TCP 80, but only when performing the initial connection to the Lync discover services and the administrator has configured the proper domain name system (DNS) CNAME (or alias) records, and accepts that this communication will not be encrypted.</span></span>

2.  <span data-ttu-id="c31f2-117">Lync Server 2013 在前端伺服器及（或） Director) 上部署的外部 web 服務 (會期望從埠 TCP 4443 上的反向 proxy 進行連線，並且預期會 SSL/TLS 該連線。</span><span class="sxs-lookup"><span data-stu-id="c31f2-117">Lync Server 2013 external web services (deployed on the Front End Server and/or the Director) expect a connection from a reverse proxy on port TCP 4443, and it expects that the connection will be SSL/TLS.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c31f2-118">建議的外部 web 服務預設收聽埠為 TCP 8080，用於 HTTP 流量，TCP 4443 用於 HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="c31f2-118">The suggested default listening ports for the external web services are TCP 8080 for HTTP traffic, and TCP 4443 for HTTPS traffic.</span></span> <span data-ttu-id="c31f2-119">拓撲產生器提供的機會可以覆寫預設值，並定義您自己的外部 web 服務偵聽埠。</span><span class="sxs-lookup"><span data-stu-id="c31f2-119">Topology Builder provides an opportunity to override the defaults and define your own listening ports for the external web services.</span></span> <span data-ttu-id="c31f2-120">請務必注意，反向 proxy 會與外部 web 服務進行通訊，而外部用戶端則會與反向 proxy 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="c31f2-120">It’s important to note that the reverse proxy communicates with the external web services, and the external clients communicate with the reverse proxy.</span></span> <span data-ttu-id="c31f2-121">外部用戶端與埠 TCP 443 上的反向 proxy 進行通訊，但您可以重新定義反向 proxy 與上的外部 web 服務進行通訊的埠。</span><span class="sxs-lookup"><span data-stu-id="c31f2-121">The external client communicates with the reverse proxy on port TCP 443, but you can redefine what port the reverse proxy communicates with the external web services on.</span></span> <span data-ttu-id="c31f2-122">拓撲產生器中的選項可覆寫 web 服務的預設聆聽埠，可讓您解決基礎結構中可能發生的偵聽埠衝突。</span><span class="sxs-lookup"><span data-stu-id="c31f2-122">The options in Topology Builder to override the default listening ports for the web services allows you to resolve listening port conflicts that may arise in your infrastructure.</span></span>

    
    </div>

3.  <span data-ttu-id="c31f2-123">Lync Server 2013 外部 web 服務期望來自用戶端的未修改主機標頭，以識別用戶端嘗試使用的服務和網頁伺服器目錄。</span><span class="sxs-lookup"><span data-stu-id="c31f2-123">Lync Server 2013 external web services expect an unmodified Host Header from the client to identify what service and web server directory the client is attempting to use.</span></span> <span data-ttu-id="c31f2-124">要求應顯示為來自反向 proxy</span><span class="sxs-lookup"><span data-stu-id="c31f2-124">Requests should appear as if they came from the reverse proxy</span></span>

4.  <span data-ttu-id="c31f2-125">[外部 web 服務] 使用定義的網頁伺服器虛擬目錄 (vDir) ，提供提供給用戶端的服務。</span><span class="sxs-lookup"><span data-stu-id="c31f2-125">The external web services use defined web server virtual directories (vDir) that provide the services offered to clients.</span></span> <span data-ttu-id="c31f2-126">特定的外部可識別 web 服務如下：</span><span class="sxs-lookup"><span data-stu-id="c31f2-126">Specific externally identifiable web services are:</span></span>
    
      - <span data-ttu-id="c31f2-127">Web 會議會議的「開會」 vDir</span><span class="sxs-lookup"><span data-stu-id="c31f2-127">The “Meet” vDir for web conference meetings</span></span>
    
      - <span data-ttu-id="c31f2-128">用於電話存取及電話會議的「撥入」 vDir</span><span class="sxs-lookup"><span data-stu-id="c31f2-128">The “Dialin” vDir for phone access and phone conferencing</span></span>
    
      - <span data-ttu-id="c31f2-129">Lync Windows Store 應用程式、Lync Mobile 和桌面用戶端 Lync 2013 的「自動探索」 vDir。</span><span class="sxs-lookup"><span data-stu-id="c31f2-129">The “Autodiscover” vDir for Lync Windows Store app, Lync Mobile, and the desktop client Lync 2013.</span></span> <span data-ttu-id="c31f2-130">Lync Server 2013 中的自動探索是由 DNS 名稱 "lyncdiscover" 所知道</span><span class="sxs-lookup"><span data-stu-id="c31f2-130">Autodiscover in Lync Server 2013 is known by the DNS name “lyncdiscover”</span></span>
    
      - <span data-ttu-id="c31f2-131">未定義的服務會透過直接呼叫外部 web 服務的方式來存取外部用戶端。</span><span class="sxs-lookup"><span data-stu-id="c31f2-131">Services not defined are accessed by the external client by direct calls to the external web services.</span></span> <span data-ttu-id="c31f2-132">例如，通訊群組擴充 (DLX) 和通訊錄服務 (ABS) 是透過直接呼叫外部 web 服務及關聯的 vDirs 來存取。</span><span class="sxs-lookup"><span data-stu-id="c31f2-132">For example, distribution group expansion (DLX) and the address book service (ABS) are accessed by direct calls to the external web services and associated vDirs.</span></span> <span data-ttu-id="c31f2-133">用戶端知道 vDir 的實際路徑，並根據此資訊建立統一記錄定位器 (URL) 。</span><span class="sxs-lookup"><span data-stu-id="c31f2-133">The client knows the actual path to the vDir and constructs a uniform record locator (URL) based on this information.</span></span> <span data-ttu-id="c31f2-134">用戶端會使用類似于的 URL 來存取通訊錄服務。 `https://externalweb.contoso.com/abs/handler`</span><span class="sxs-lookup"><span data-stu-id="c31f2-134">The client would access the address book service using a URL similar to `https://externalweb.contoso.com/abs/handler`</span></span>
    
      - <span data-ttu-id="c31f2-135">當會議已定義並設定為 Lync Server 拓撲的一部分時，Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="c31f2-135">The Office Web Apps Server when conferencing is defined and configured as part of the Lync Server topology</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c31f2-136">Office Web Apps Server 是個別的角色服務器，未設定為外部 Web 服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="c31f2-136">The Office Web Apps Server is a separate role server and is not configured as part of the external web services.</span></span> <span data-ttu-id="c31f2-137">此伺服器會另行發佈，以供用戶端存取使用。</span><span class="sxs-lookup"><span data-stu-id="c31f2-137">This server is separately published for client access.</span></span>

        
        </div>

5.  <span data-ttu-id="c31f2-138">定義每個服務的 SSL 橋接。</span><span class="sxs-lookup"><span data-stu-id="c31f2-138">Define SSL bridging for each service.</span></span> <span data-ttu-id="c31f2-139">外部埠 TCP 443 會對應至 TCP 4443 的外部 web 服務埠。</span><span class="sxs-lookup"><span data-stu-id="c31f2-139">The external port TCP 443 is mapped to the external web services port of TCP 4443.</span></span> <span data-ttu-id="c31f2-140">如果是未加密的 HTTP，埠 TCP 80 會對應至外部 web 服務埠 TCP 8080</span><span class="sxs-lookup"><span data-stu-id="c31f2-140">For unencrypted HTTP, port TCP 80 is mapped to the external web services port TCP 8080</span></span>

6.  <span data-ttu-id="c31f2-141">規劃反向 proxy 攔截器以發佈網頁伺服器資源</span><span class="sxs-lookup"><span data-stu-id="c31f2-141">Plan for reverse proxy listeners to publish web server resources</span></span>

7.  <span data-ttu-id="c31f2-142">根據所提供的服務，要求並設定反向 proxy 的憑證。</span><span class="sxs-lookup"><span data-stu-id="c31f2-142">Request and configure the certificate for the reverse proxy based on the services that will be offered.</span></span> <span data-ttu-id="c31f2-143">如果使用正確的主體替代名稱加以設定，則反向 proxy 伺服器上的所有已設定監聽器都可以共用此憑證</span><span class="sxs-lookup"><span data-stu-id="c31f2-143">If configured with the correct subject alternative names, this certificate can be shared by all configured listeners on the reverse proxy server</span></span>

<span data-ttu-id="c31f2-144">可用來規劃反向 Proxy 部署的資源：</span><span class="sxs-lookup"><span data-stu-id="c31f2-144">Resources available for planning your reverse proxy deployment:</span></span>

  - [<span data-ttu-id="c31f2-145">Lync Server 2013 中的資料收集</span><span class="sxs-lookup"><span data-stu-id="c31f2-145">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="c31f2-146">Lync Server 2013 的憑證摘要-反向 proxy</span><span class="sxs-lookup"><span data-stu-id="c31f2-146">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="c31f2-147">Lync Server 2013 中的埠摘要-反向 proxy</span><span class="sxs-lookup"><span data-stu-id="c31f2-147">Port summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-port-summary-reverse-proxy.md)

  - [<span data-ttu-id="c31f2-148">Lync Server 2013 中的 DNS 摘要-反向 proxy</span><span class="sxs-lookup"><span data-stu-id="c31f2-148">DNS summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

