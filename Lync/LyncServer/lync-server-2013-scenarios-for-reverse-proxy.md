---
title: 反向 proxy 的 Lync Server 2013： 案例
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
ms.openlocfilehash: be05e3b63b73daeecbd4c0b34d9a893a8e27fa83
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="c537e-102">Lync Server 2013 中的反向 proxy 案例</span><span class="sxs-lookup"><span data-stu-id="c537e-102">Scenarios for reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c537e-103">_**上次修改主題：** 2013年-01-21_</span><span class="sxs-lookup"><span data-stu-id="c537e-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="c537e-104">反向 proxy 所需 Lync Server 2013 中提供的服務和資源，例如會議和撥入簡單 Url、 通訊錄、 會議內容、 通訊群組清單擴充、 行動性服務和其他人存取。</span><span class="sxs-lookup"><span data-stu-id="c537e-104">Reverse proxies are required in Lync Server 2013 for providing access to services and resources such as the meeting and dial-in Simple URLs, address book, meeting content, distribution list expansion, mobility services, and others.</span></span> <span data-ttu-id="c537e-105">Lync Server 2013 中的一般反向 proxy 案例是允許外部用戶端 （例如，桌面用戶端或 Lync Web App 用戶端） 存取 Director 或前端伺服器的外部 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="c537e-105">The typical reverse proxy scenario in Lync Server 2013 is to allow external clients (for example, the desktop client or Lync Web App client) access to the Director or Front End Server external Web Services.</span></span>

<span data-ttu-id="c537e-106">**反向 proxy 及外部 web 服務**</span><span class="sxs-lookup"><span data-stu-id="c537e-106">**Reverse proxy and external web services**</span></span>

<span data-ttu-id="c537e-107">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="c537e-107">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>

<span data-ttu-id="c537e-108">在規劃階段，您可以定義反向 proxy 需求 Lync Server 2013 部署中。</span><span class="sxs-lookup"><span data-stu-id="c537e-108">During the planning phase, you define the requirements for the reverse proxy in a Lync Server 2013 deployment.</span></span> <span data-ttu-id="c537e-109">反向 proxy 啟用下列外部用戶端存取功能：</span><span class="sxs-lookup"><span data-stu-id="c537e-109">The reverse proxy enables access to features for the following external clients:</span></span>

  - <span data-ttu-id="c537e-110">Microsoft Lync 2013 桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="c537e-110">Microsoft Lync 2013 desktop client</span></span>

  - <span data-ttu-id="c537e-111">Microsoft Lync Web App</span><span class="sxs-lookup"><span data-stu-id="c537e-111">Microsoft Lync Web App</span></span>

  - <span data-ttu-id="c537e-112">Microsoft Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="c537e-112">Microsoft Lync Mobile</span></span>

  - <span data-ttu-id="c537e-113">Lync Windows 市集應用程式</span><span class="sxs-lookup"><span data-stu-id="c537e-113">Lync Windows Store app</span></span>

<span data-ttu-id="c537e-114">當您在規劃 Lync Server 2013 部署，您會將 Lync Server 2013 的實際需求對應至反向 proxy 功能。</span><span class="sxs-lookup"><span data-stu-id="c537e-114">When planning your Lync Server 2013 deployment, you map the actual requirements for Lync Server 2013 to the reverse proxy features.</span></span>

1.  <span data-ttu-id="c537e-115">外部用戶端會連線到連接埠 TCP 443 上的反向 proxy，並會使用安全通訊端層 (SSL) 或傳輸層安全性 (TLS)。</span><span class="sxs-lookup"><span data-stu-id="c537e-115">External clients will connect to the reverse proxy on port TCP 443 and will use secure socket layer (SSL) or transport layer security (TLS).</span></span> <span data-ttu-id="c537e-116">Microsoft Lync 行動用戶端可以連線連接埠 TCP 80，但是只有當執行初始連線至 Lync 探索服務及系統管理員已設定適當的網域名稱系統 (DNS) CNAME （或別名） 記錄，並接受該這將不會加密的通訊。</span><span class="sxs-lookup"><span data-stu-id="c537e-116">Microsoft Lync Mobile clients can connect on port TCP 80, but only when performing the initial connection to the Lync discover services and the administrator has configured the proper domain name system (DNS) CNAME (or alias) records, and accepts that this communication will not be encrypted.</span></span>

2.  <span data-ttu-id="c537e-117">Lync Server 2013 外部 web 服務 （前端伺服器及/或 Director 上部署） 預期從連接埠 TCP 4443 上的反向 proxy 的連線，它會預期連線將 SSL/TLS。</span><span class="sxs-lookup"><span data-stu-id="c537e-117">Lync Server 2013 external web services (deployed on the Front End Server and/or the Director) expect a connection from a reverse proxy on port TCP 4443, and it expects that the connection will be SSL/TLS.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c537e-118">外部 web 服務的建議的預設聆聽連接埠是 TCP 8080 HTTP 流量，以及 TCP 4443 用於 HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="c537e-118">The suggested default listening ports for the external web services are TCP 8080 for HTTP traffic, and TCP 4443 for HTTPS traffic.</span></span> <span data-ttu-id="c537e-119">拓撲產生器可提供機會讓覆寫預設值，並定義您自己的外部 web 服務的聆聽連接埠。</span><span class="sxs-lookup"><span data-stu-id="c537e-119">Topology Builder provides an opportunity to override the defaults and define your own listening ports for the external web services.</span></span> <span data-ttu-id="c537e-120">請務必注意反向 proxy 進行通訊的外部 web 服務，並與反向 proxy 的外部用戶端進行通訊。</span><span class="sxs-lookup"><span data-stu-id="c537e-120">It’s important to note that the reverse proxy communicates with the external web services, and the external clients communicate with the reverse proxy.</span></span> <span data-ttu-id="c537e-121">外部用戶端會與連接埠 TCP 443 上的反向 proxy 進行通訊，但是您可以重新定義反向 proxy 會與上的外部 web 服務進行通訊的連接埠。</span><span class="sxs-lookup"><span data-stu-id="c537e-121">The external client communicates with the reverse proxy on port TCP 443, but you can redefine what port the reverse proxy communicates with the external web services on.</span></span> <span data-ttu-id="c537e-122">在拓撲產生器的選項來覆寫預設的聆聽連接埠的 web 服務可讓您解決可能發生在您的基礎結構的聆聽連接埠衝突。</span><span class="sxs-lookup"><span data-stu-id="c537e-122">The options in Topology Builder to override the default listening ports for the web services allows you to resolve listening port conflicts that may arise in your infrastructure.</span></span>

    
    </div>

3.  <span data-ttu-id="c537e-123">Lync Server 2013 外部 web 服務預期用戶端來識別哪些服務未修改的主機標頭及 web 伺服器目錄用戶端嘗試使用。</span><span class="sxs-lookup"><span data-stu-id="c537e-123">Lync Server 2013 external web services expect an unmodified Host Header from the client to identify what service and web server directory the client is attempting to use.</span></span> <span data-ttu-id="c537e-124">要求應該看起來好像他們來自反向 proxy</span><span class="sxs-lookup"><span data-stu-id="c537e-124">Requests should appear as if they came from the reverse proxy</span></span>

4.  <span data-ttu-id="c537e-125">外部 web 服務使用定義的 web 伺服器虛擬目錄 (vDir) 提供給用戶端提供服務。</span><span class="sxs-lookup"><span data-stu-id="c537e-125">The external web services use defined web server virtual directories (vDir) that provide the services offered to clients.</span></span> <span data-ttu-id="c537e-126">是特定外部識別 web 服務：</span><span class="sxs-lookup"><span data-stu-id="c537e-126">Specific externally identifiable web services are:</span></span>
    
      - <span data-ttu-id="c537e-127">「 符合 「 vDir web 會議會議</span><span class="sxs-lookup"><span data-stu-id="c537e-127">The “Meet” vDir for web conference meetings</span></span>
    
      - <span data-ttu-id="c537e-128">適用於電話存取和電話會議 」 Dialin 」 vDir</span><span class="sxs-lookup"><span data-stu-id="c537e-128">The “Dialin” vDir for phone access and phone conferencing</span></span>
    
      - <span data-ttu-id="c537e-129">Lync Windows 市集應用程式、 Lync Mobile 和 Lync 2013 的桌面用戶端 「 自動探索 」 vDir。</span><span class="sxs-lookup"><span data-stu-id="c537e-129">The “Autodiscover” vDir for Lync Windows Store app, Lync Mobile, and the desktop client Lync 2013.</span></span> <span data-ttu-id="c537e-130">Lync Server 2013 中的自動探索已知 DNS 名稱"lyncdiscover"</span><span class="sxs-lookup"><span data-stu-id="c537e-130">Autodiscover in Lync Server 2013 is known by the DNS name “lyncdiscover”</span></span>
    
      - <span data-ttu-id="c537e-131">外部用戶端存取來直接呼叫的外部 web 服務的服務未定義的。</span><span class="sxs-lookup"><span data-stu-id="c537e-131">Services not defined are accessed by the external client by direct calls to the external web services.</span></span> <span data-ttu-id="c537e-132">例如，通訊群組擴充 (DLX) 和通訊錄服務 (ABS) 以存取直接呼叫的外部 web 服務和相關聯的 vDirs。</span><span class="sxs-lookup"><span data-stu-id="c537e-132">For example, distribution group expansion (DLX) and the address book service (ABS) are accessed by direct calls to the external web services and associated vDirs.</span></span> <span data-ttu-id="c537e-133">用戶端至 vDir 知道的實際路徑，並建構根據這項資訊統一記錄定位器 (URL)。</span><span class="sxs-lookup"><span data-stu-id="c537e-133">The client knows the actual path to the vDir and constructs a uniform record locator (URL) based on this information.</span></span> <span data-ttu-id="c537e-134">用戶端可存取通訊錄服務使用類似的 URL`https://externalweb.contoso.com/abs/handler`</span><span class="sxs-lookup"><span data-stu-id="c537e-134">The client would access the address book service using a URL similar to `https://externalweb.contoso.com/abs/handler`</span></span>
    
      - <span data-ttu-id="c537e-135">Office Web Apps Server 時會議是定義及設定 Lync Server 拓撲的一部分</span><span class="sxs-lookup"><span data-stu-id="c537e-135">The Office Web Apps Server when conferencing is defined and configured as part of the Lync Server topology</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c537e-136">Office Web Apps Server 是不同的角色伺服器，且未設定的外部 web 服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="c537e-136">The Office Web Apps Server is a separate role server and is not configured as part of the external web services.</span></span> <span data-ttu-id="c537e-137">此伺服器分開發佈的用戶端存取。</span><span class="sxs-lookup"><span data-stu-id="c537e-137">This server is separately published for client access.</span></span>

        
        </div>

5.  <span data-ttu-id="c537e-138">定義 SSL 橋接的每項服務。</span><span class="sxs-lookup"><span data-stu-id="c537e-138">Define SSL bridging for each service.</span></span> <span data-ttu-id="c537e-139">外部連接埠 TCP 443 會對應至外部 web 服務的連接埠 TCP 4443。</span><span class="sxs-lookup"><span data-stu-id="c537e-139">The external port TCP 443 is mapped to the external web services port of TCP 4443.</span></span> <span data-ttu-id="c537e-140">未加密 http 連接埠 TCP 80 會對應至外部 web 服務連接埠 TCP 8080</span><span class="sxs-lookup"><span data-stu-id="c537e-140">For unencrypted HTTP, port TCP 80 is mapped to the external web services port TCP 8080</span></span>

6.  <span data-ttu-id="c537e-141">若要發佈的 web 伺服器資源的反向 proxy 接聽程式的計劃</span><span class="sxs-lookup"><span data-stu-id="c537e-141">Plan for reverse proxy listeners to publish web server resources</span></span>

7.  <span data-ttu-id="c537e-142">要求，並設定為基礎的服務，則會提供反向 proxy 的憑證。</span><span class="sxs-lookup"><span data-stu-id="c537e-142">Request and configure the certificate for the reverse proxy based on the services that will be offered.</span></span> <span data-ttu-id="c537e-143">此憑證如果設定正確的主體替代名稱，可以共用的反向 proxy 伺服器上的所有設定接聽程式</span><span class="sxs-lookup"><span data-stu-id="c537e-143">If configured with the correct subject alternative names, this certificate can be shared by all configured listeners on the reverse proxy server</span></span>

<span data-ttu-id="c537e-144">可用來規劃反向 Proxy 部署的資源：</span><span class="sxs-lookup"><span data-stu-id="c537e-144">Resources available for planning your reverse proxy deployment:</span></span>

  - [<span data-ttu-id="c537e-145">Lync Server 2013 中的資料收集</span><span class="sxs-lookup"><span data-stu-id="c537e-145">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="c537e-146">憑證摘要-Lync Server 2013 中的反向 proxy</span><span class="sxs-lookup"><span data-stu-id="c537e-146">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="c537e-147">連接埠摘要-Lync Server 2013 中的反向 proxy</span><span class="sxs-lookup"><span data-stu-id="c537e-147">Port summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-port-summary-reverse-proxy.md)

  - [<span data-ttu-id="c537e-148">DNS 摘要-Lync Server 2013 中的反向 proxy</span><span class="sxs-lookup"><span data-stu-id="c537e-148">DNS summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

