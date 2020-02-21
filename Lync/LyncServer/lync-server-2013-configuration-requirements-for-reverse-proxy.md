---
title: Lync Server 2013： 設定反向 proxy 需求
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
ms.openlocfilehash: 13026da5515615610c960fe4648d5c58f64f99fe
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="7ea67-102">Lync Server 2013 中的反向 proxy 的設定需求</span><span class="sxs-lookup"><span data-stu-id="7ea67-102">Configuration requirements for reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ea67-103">_**上次修改主題：** 2013年-03-05_</span><span class="sxs-lookup"><span data-stu-id="7ea67-103">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="7ea67-104">Lync Server 2013 施加在從外部用戶端的通訊，然後傳遞至 Director 集區、 前端伺服器或前端集區裝載在 Director 上的外部 Web 服務上的一些需求。</span><span class="sxs-lookup"><span data-stu-id="7ea67-104">Lync Server 2013 imposes a few requirements on communications from the external client that are then passed on to the external Web services hosted on the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="7ea67-105">如果您為使用者提供了會議，也是負責發佈 Office Web Apps Server，反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="7ea67-105">The reverse proxy is also responsible for publishing the Office Web Apps Server, if you are offering conferencing to your users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7ea67-106">Lync Server 2013 不指定特定的反向 proxy，您必須使用。</span><span class="sxs-lookup"><span data-stu-id="7ea67-106">Lync Server 2013 does not specify a particular reverse proxy that you must use.</span></span> <span data-ttu-id="7ea67-107">Lync Server 2013 只定義反向 proxy 必須能夠執行的作業需求。</span><span class="sxs-lookup"><span data-stu-id="7ea67-107">Lync Server 2013 only defines operational requirements that the reverse proxy must be able to do.</span></span> <span data-ttu-id="7ea67-108">一般而言，您已部署在您的基礎結構中的反向 proxy 可能無法符合需求。</span><span class="sxs-lookup"><span data-stu-id="7ea67-108">Typically, the reverse proxy that you already have deployed in your infrastructure may be able to meet the requirements.</span></span>



</div>

<div>

## <a name="reverse-proxy-requirements"></a><span data-ttu-id="7ea67-109">反向 Proxy 需求</span><span class="sxs-lookup"><span data-stu-id="7ea67-109">Reverse Proxy Requirements</span></span>

<span data-ttu-id="7ea67-110">Lync Server 2013 預期的反向 proxy，以執行的功能作業包括：</span><span class="sxs-lookup"><span data-stu-id="7ea67-110">The functional operations that Lync Server 2013 expect a reverse proxy to perform are:</span></span>

  - <span data-ttu-id="7ea67-111">使用安全通訊端層 (SSL) 和傳輸層安全性 (TLS) 連線至已發行外部 Web 服務 Director 的 Director 集區、 前端伺服器或前端集區使用公用憑證授權單位取得憑證來實作。</span><span class="sxs-lookup"><span data-stu-id="7ea67-111">Use secure socket layer (SSL) and transport layer security (TLS) implemented by using certificates acquired from a public certification authority to connect to the published external Web services of the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="7ea67-112">Director 與前端伺服器可以使用硬體負載平衡器是負載平衡集區中。</span><span class="sxs-lookup"><span data-stu-id="7ea67-112">The Director and the Front End Server can be in a load-balanced pool by using hardware load balancers.</span></span>

  - <span data-ttu-id="7ea67-113">能夠發佈內部網路網站使用的憑證進行加密，或將它們發行透過未加密的方法，如有需要。</span><span class="sxs-lookup"><span data-stu-id="7ea67-113">Able to publish internal Web sites using certificates for encryption, or publish them over an unencrypted means, if needed.</span></span>

  - <span data-ttu-id="7ea67-114">用以發佈內部代管的網站外部使用的完整的網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="7ea67-114">Able to publish an internally hosted web site externally by using a fully qualified domain name (FQDN).</span></span>

  - <span data-ttu-id="7ea67-115">用以發佈主控網站的所有內容。</span><span class="sxs-lookup"><span data-stu-id="7ea67-115">Able to publish all contents of the hosted web site.</span></span> <span data-ttu-id="7ea67-116">根據預設，您可以使用**/** 指示詞，大部分的網頁伺服器辨識表示 「 發佈網頁伺服器上的所有內容 」。</span><span class="sxs-lookup"><span data-stu-id="7ea67-116">By default, you can use the **/\*** directive, which is recognized by most web servers to mean "Publish all content on the web server."</span></span> <span data-ttu-id="7ea67-117">您也可以修改指示詞 — 例如， **/Uwca/\***，這表示 「 發佈虛擬目錄 Ucwa 下的所有內容。 」</span><span class="sxs-lookup"><span data-stu-id="7ea67-117">You can also modify the directive—for example, **/Uwca/\***, which means "Publish all content under the virtual directory Ucwa."</span></span>

  - <span data-ttu-id="7ea67-118">必須是可設定為需要與用戶端要求內容從發佈網站的 Secure Sockets Layer (SSL) 和/或傳輸層安全性 (TLS) 連線。</span><span class="sxs-lookup"><span data-stu-id="7ea67-118">Must be configurable to require Secure Sockets Layer (SSL) and/or Transport Layer Security (TLS) connections with clients that request content from a published website.</span></span>

  - <span data-ttu-id="7ea67-119">必須接受憑證主體替代名稱 (SAN) 項目。</span><span class="sxs-lookup"><span data-stu-id="7ea67-119">Must accept certificates with subject alternative name (SAN) entries.</span></span>

  - <span data-ttu-id="7ea67-120">必須能夠允許的接聽程式或外部 web 服務 FQDN 會解析透過的介面的憑證繫結。</span><span class="sxs-lookup"><span data-stu-id="7ea67-120">Must be able to allow binding of a certificate to a listener or interface through which the external web services FQDN will resolve.</span></span> <span data-ttu-id="7ea67-121">接聽程式的設定會優先於介面。</span><span class="sxs-lookup"><span data-stu-id="7ea67-121">Listener configurations are preferable to interfaces.</span></span> <span data-ttu-id="7ea67-122">許多接聽程式可以在單一介面上設定。</span><span class="sxs-lookup"><span data-stu-id="7ea67-122">Many listeners can be configured on a single interface.</span></span>

  - <span data-ttu-id="7ea67-123">必須允許主機標頭處理的設定。</span><span class="sxs-lookup"><span data-stu-id="7ea67-123">Must allow for the configuration of host header handling.</span></span> <span data-ttu-id="7ea67-124">通常，必須無障礙，傳遞要求的用戶端所傳送的原始主機標頭而非要修改的反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="7ea67-124">Often, the original host header sent by the requesting client must be passed transparently, instead of being modified by the reverse proxy.</span></span>

  - <span data-ttu-id="7ea67-125">從一個的 SSL 和 TLS 流量的外部橋接至另一個定義的連接埠 (例如，TCP 4443) 定義連接埠 (例如，TCP 443)。</span><span class="sxs-lookup"><span data-stu-id="7ea67-125">Bridging of SSL and TLS traffic from one externally defined port (for example, TCP 443) to another defined port (for example, TCP 4443).</span></span> <span data-ttu-id="7ea67-126">反向 proxy 可能解密在收到封包，然後重新加密上傳送的封包。</span><span class="sxs-lookup"><span data-stu-id="7ea67-126">The reverse proxy may decrypt the packet on receipt and then reencrypt the packet on sending.</span></span>

  - <span data-ttu-id="7ea67-127">從一個連接埠 (例如，TCP 80) 未加密的 TCP 流量，（例如，TCP 8080） 之間的橋接。</span><span class="sxs-lookup"><span data-stu-id="7ea67-127">Bridging of unencrypted TCP traffic from one port (for example, TCP 80) to another (for example, TCP 8080).</span></span>

  - <span data-ttu-id="7ea67-128">允許組態，或接受，NTLM 驗證不驗證並通過驗證。</span><span class="sxs-lookup"><span data-stu-id="7ea67-128">Allow configuration of, or accept, NTLM authentication, No authentication and Pass-through authentication.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

