---
title: Lync Server 2013：反向 proxy 的設定需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration requirements for reverse proxy
ms:assetid: c37d688a-28e4-4822-80cc-6add59c71052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945651(v=OCS.15)
ms:contentKeyID: 51541518
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 555169f6de67ae23bc63d81aad549b0033a6696c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507740"
---
# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="3171f-102">Lync Server 2013 中反向 proxy 的設定需求</span><span class="sxs-lookup"><span data-stu-id="3171f-102">Configuration requirements for reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3171f-103">_**主題上次修改日期：** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="3171f-103">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="3171f-104">Lync Server 2013 對從外部用戶端進行通訊的需求，對傳送到 Director、Director 集區、前端伺服器或前端集區上的外部 Web 服務很有一定的需求。</span><span class="sxs-lookup"><span data-stu-id="3171f-104">Lync Server 2013 imposes a few requirements on communications from the external client that are then passed on to the external Web services hosted on the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="3171f-105">反向 proxy 也負責發佈 Office Web Apps Server （如果您為使用者提供會議）。</span><span class="sxs-lookup"><span data-stu-id="3171f-105">The reverse proxy is also responsible for publishing the Office Web Apps Server, if you are offering conferencing to your users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3171f-106">Lync Server 2013 未指定您必須使用的特定反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="3171f-106">Lync Server 2013 does not specify a particular reverse proxy that you must use.</span></span> <span data-ttu-id="3171f-107">Lync Server 2013 僅定義反向 proxy 必須能夠執行的運作需求。</span><span class="sxs-lookup"><span data-stu-id="3171f-107">Lync Server 2013 only defines operational requirements that the reverse proxy must be able to do.</span></span> <span data-ttu-id="3171f-108">一般來說，您已部署在基礎結構中的反向 proxy 可能能夠符合需求。</span><span class="sxs-lookup"><span data-stu-id="3171f-108">Typically, the reverse proxy that you already have deployed in your infrastructure may be able to meet the requirements.</span></span>



</div>

<div>

## <a name="reverse-proxy-requirements"></a><span data-ttu-id="3171f-109">反向 Proxy 需求</span><span class="sxs-lookup"><span data-stu-id="3171f-109">Reverse Proxy Requirements</span></span>

<span data-ttu-id="3171f-110">Lync Server 2013 預期反向 proxy 執行的功能作業如下：</span><span class="sxs-lookup"><span data-stu-id="3171f-110">The functional operations that Lync Server 2013 expect a reverse proxy to perform are:</span></span>

  - <span data-ttu-id="3171f-111">使用安全通訊端層 (SSL) 和傳輸層安全性 (TLS) ，其使用從公用憑證授權單位取得的憑證來連線至 Director、Director 集區、前端伺服器或前端集區的已發佈外部 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="3171f-111">Use secure socket layer (SSL) and transport layer security (TLS) implemented by using certificates acquired from a public certification authority to connect to the published external Web services of the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="3171f-112">Director 和前端伺服器可以使用硬體負載平衡器在負載平衡集區中。</span><span class="sxs-lookup"><span data-stu-id="3171f-112">The Director and the Front End Server can be in a load-balanced pool by using hardware load balancers.</span></span>

  - <span data-ttu-id="3171f-113">可以使用憑證來發佈內部網站，也可以在必要時以未加密的方式發佈。</span><span class="sxs-lookup"><span data-stu-id="3171f-113">Able to publish internal Web sites using certificates for encryption, or publish them over an unencrypted means, if needed.</span></span>

  - <span data-ttu-id="3171f-114">可以使用完整功能變數名稱 (FQDN) ，從外部發佈內部主控的網站。</span><span class="sxs-lookup"><span data-stu-id="3171f-114">Able to publish an internally hosted web site externally by using a fully qualified domain name (FQDN).</span></span>

  - <span data-ttu-id="3171f-115">能夠發佈主控網站的所有內容。</span><span class="sxs-lookup"><span data-stu-id="3171f-115">Able to publish all contents of the hosted web site.</span></span> <span data-ttu-id="3171f-116">根據預設，您可以使用 **/\*** 大多數網頁伺服器所識別的指令，以表示「在網頁伺服器上發行所有內容」。</span><span class="sxs-lookup"><span data-stu-id="3171f-116">By default, you can use the **/\*** directive, which is recognized by most web servers to mean "Publish all content on the web server."</span></span> <span data-ttu-id="3171f-117">您也可以修改此指令，例如， \*\*/Uwca/ \* \*\*，這表示「發行虛擬目錄 Ucwa 下的所有內容」。</span><span class="sxs-lookup"><span data-stu-id="3171f-117">You can also modify the directive—for example, **/Uwca/\***, which means "Publish all content under the virtual directory Ucwa."</span></span>

  - <span data-ttu-id="3171f-118">必須可設定為需要安全通訊端層 (SSL) 和/或傳輸層安全性 (TLS) 與要求來自已發佈網站之內容的用戶端的連線。</span><span class="sxs-lookup"><span data-stu-id="3171f-118">Must be configurable to require Secure Sockets Layer (SSL) and/or Transport Layer Security (TLS) connections with clients that request content from a published website.</span></span>

  - <span data-ttu-id="3171f-119">必須接受主體替代名稱 (SAN) 專案的憑證。</span><span class="sxs-lookup"><span data-stu-id="3171f-119">Must accept certificates with subject alternative name (SAN) entries.</span></span>

  - <span data-ttu-id="3171f-120">必須能夠將憑證系結至攔截器或介面，以供外部 web 服務 FQDN 解析。</span><span class="sxs-lookup"><span data-stu-id="3171f-120">Must be able to allow binding of a certificate to a listener or interface through which the external web services FQDN will resolve.</span></span> <span data-ttu-id="3171f-121">監聽器設定優於介面。</span><span class="sxs-lookup"><span data-stu-id="3171f-121">Listener configurations are preferable to interfaces.</span></span> <span data-ttu-id="3171f-122">在單一介面上可以設定許多監聽器。</span><span class="sxs-lookup"><span data-stu-id="3171f-122">Many listeners can be configured on a single interface.</span></span>

  - <span data-ttu-id="3171f-123">必須允許設定主機標頭處理。</span><span class="sxs-lookup"><span data-stu-id="3171f-123">Must allow for the configuration of host header handling.</span></span> <span data-ttu-id="3171f-124">通常會以透明的方式傳遞要求用戶端所傳送的原始主機標頭，而不是反向 proxy 進行修改。</span><span class="sxs-lookup"><span data-stu-id="3171f-124">Often, the original host header sent by the requesting client must be passed transparently, instead of being modified by the reverse proxy.</span></span>

  - <span data-ttu-id="3171f-125">橋接從外部定義埠 (的 SSL 和 TLS 流量，例如，TCP 443) 至另一個已定義的埠 (例如，TCP 4443) 。</span><span class="sxs-lookup"><span data-stu-id="3171f-125">Bridging of SSL and TLS traffic from one externally defined port (for example, TCP 443) to another defined port (for example, TCP 4443).</span></span> <span data-ttu-id="3171f-126">反向 proxy 可能會解密資料包上的封包，然後在傳送時重新加密此封包。</span><span class="sxs-lookup"><span data-stu-id="3171f-126">The reverse proxy may decrypt the packet on receipt and then reencrypt the packet on sending.</span></span>

  - <span data-ttu-id="3171f-127">橋接單一端口 (的未加密 TCP 流量例如，TCP 80) 到另一個 (例如，TCP 8080) 。</span><span class="sxs-lookup"><span data-stu-id="3171f-127">Bridging of unencrypted TCP traffic from one port (for example, TCP 80) to another (for example, TCP 8080).</span></span>

  - <span data-ttu-id="3171f-128">允許設定或接受 NTLM 驗證，不具驗證及透過驗證。</span><span class="sxs-lookup"><span data-stu-id="3171f-128">Allow configuration of, or accept, NTLM authentication, No authentication and Pass-through authentication.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

