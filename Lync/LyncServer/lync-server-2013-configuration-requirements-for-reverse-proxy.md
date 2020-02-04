---
title: Lync Server 2013：反向 proxy 的配置需求
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
ms.openlocfilehash: 37a2a535ddaa90efa2f4140236b52788fa58e41a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="b08bb-102">Lync Server 2013 中的反向 proxy 設定需求</span><span class="sxs-lookup"><span data-stu-id="b08bb-102">Configuration requirements for reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b08bb-103">_**主題上次修改日期：** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="b08bb-103">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="b08bb-104">Lync Server 2013 對來自外部用戶端的通訊有一些需求，就是傳送到主管、主管池、前端伺服器或頂層端池所託管的外部 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="b08bb-104">Lync Server 2013 imposes a few requirements on communications from the external client that are then passed on to the external Web services hosted on the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="b08bb-105">如果您是向使用者提供會議，則反向 proxy 也負責發佈 Office Web Apps 伺服器。</span><span class="sxs-lookup"><span data-stu-id="b08bb-105">The reverse proxy is also responsible for publishing the Office Web Apps Server, if you are offering conferencing to your users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b08bb-106">Lync Server 2013 不會指定您必須使用的特定反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="b08bb-106">Lync Server 2013 does not specify a particular reverse proxy that you must use.</span></span> <span data-ttu-id="b08bb-107">Lync Server 2013 只定義反向 proxy 必須能夠執行的操作需求。</span><span class="sxs-lookup"><span data-stu-id="b08bb-107">Lync Server 2013 only defines operational requirements that the reverse proxy must be able to do.</span></span> <span data-ttu-id="b08bb-108">通常，您已在您的基礎結構中部署的反向 proxy 可能能夠滿足需求。</span><span class="sxs-lookup"><span data-stu-id="b08bb-108">Typically, the reverse proxy that you already have deployed in your infrastructure may be able to meet the requirements.</span></span>



</div>

<div>

## <a name="reverse-proxy-requirements"></a><span data-ttu-id="b08bb-109">反向 Proxy 需求</span><span class="sxs-lookup"><span data-stu-id="b08bb-109">Reverse Proxy Requirements</span></span>

<span data-ttu-id="b08bb-110">Lync Server 2013 預期要執行反向 proxy 的功能作業如下：</span><span class="sxs-lookup"><span data-stu-id="b08bb-110">The functional operations that Lync Server 2013 expect a reverse proxy to perform are:</span></span>

  - <span data-ttu-id="b08bb-111">使用安全通訊端層（SSL）和傳輸層安全性（TLS），方法是使用從公用憑證授權單位取得的憑證連線至主管、主管池、前端伺服器或頂層端池的已發佈外部 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="b08bb-111">Use secure socket layer (SSL) and transport layer security (TLS) implemented by using certificates acquired from a public certification authority to connect to the published external Web services of the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="b08bb-112">控制器和前端伺服器可以在負載平衡的池中使用硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="b08bb-112">The Director and the Front End Server can be in a load-balanced pool by using hardware load balancers.</span></span>

  - <span data-ttu-id="b08bb-113">如果需要，您可以使用憑證來發佈內部網站，或以未加密的方式發佈它們。</span><span class="sxs-lookup"><span data-stu-id="b08bb-113">Able to publish internal Web sites using certificates for encryption, or publish them over an unencrypted means, if needed.</span></span>

  - <span data-ttu-id="b08bb-114">您可以使用完整的功能變數名稱（FQDN），在外部發佈內部託管的網站。</span><span class="sxs-lookup"><span data-stu-id="b08bb-114">Able to publish an internally hosted web site externally by using a fully qualified domain name (FQDN).</span></span>

  - <span data-ttu-id="b08bb-115">能夠發佈託管網站的所有內容。</span><span class="sxs-lookup"><span data-stu-id="b08bb-115">Able to publish all contents of the hosted web site.</span></span> <span data-ttu-id="b08bb-116">根據預設，您可以使用\*\* / \*\*此指令，大多數的 web 伺服器都會辨識此指示，表示「在 web 伺服器上發佈所有內容」。</span><span class="sxs-lookup"><span data-stu-id="b08bb-116">By default, you can use the **/\*** directive, which is recognized by most web servers to mean "Publish all content on the web server."</span></span> <span data-ttu-id="b08bb-117">您也可以修改指令（例如 **/Uwca/\***），這表示「在虛擬目錄 Ucwa 中發佈所有內容」。</span><span class="sxs-lookup"><span data-stu-id="b08bb-117">You can also modify the directive—for example, **/Uwca/\***, which means "Publish all content under the virtual directory Ucwa."</span></span>

  - <span data-ttu-id="b08bb-118">必須可設定為需要安全通訊端層（SSL）與/或傳輸層安全性（TLS）連線至從已發佈網站要求內容的用戶端。</span><span class="sxs-lookup"><span data-stu-id="b08bb-118">Must be configurable to require Secure Sockets Layer (SSL) and/or Transport Layer Security (TLS) connections with clients that request content from a published website.</span></span>

  - <span data-ttu-id="b08bb-119">必須接受使用 [消費者備用名稱（SAN）] 專案的憑證。</span><span class="sxs-lookup"><span data-stu-id="b08bb-119">Must accept certificates with subject alternative name (SAN) entries.</span></span>

  - <span data-ttu-id="b08bb-120">必須能夠將憑證系結到偵聽程式或介面，才能透過外部 web 服務 FQDN 解析。</span><span class="sxs-lookup"><span data-stu-id="b08bb-120">Must be able to allow binding of a certificate to a listener or interface through which the external web services FQDN will resolve.</span></span> <span data-ttu-id="b08bb-121">偵聽程式設定優於介面。</span><span class="sxs-lookup"><span data-stu-id="b08bb-121">Listener configurations are preferable to interfaces.</span></span> <span data-ttu-id="b08bb-122">許多監聽器可以在單一介面上設定。</span><span class="sxs-lookup"><span data-stu-id="b08bb-122">Many listeners can be configured on a single interface.</span></span>

  - <span data-ttu-id="b08bb-123">必須允許主機標頭處理的設定。</span><span class="sxs-lookup"><span data-stu-id="b08bb-123">Must allow for the configuration of host header handling.</span></span> <span data-ttu-id="b08bb-124">通常，由要求用戶端傳送的原始主機標頭必須透明地傳遞，而不是由反向 proxy 進行修改。</span><span class="sxs-lookup"><span data-stu-id="b08bb-124">Often, the original host header sent by the requesting client must be passed transparently, instead of being modified by the reverse proxy.</span></span>

  - <span data-ttu-id="b08bb-125">將 SSL 和 TLS 流量從一個外部定義的埠（例如，TCP 443）橋接到另一個已定義的埠（例如，TCP 4443）。</span><span class="sxs-lookup"><span data-stu-id="b08bb-125">Bridging of SSL and TLS traffic from one externally defined port (for example, TCP 443) to another defined port (for example, TCP 4443).</span></span> <span data-ttu-id="b08bb-126">反向 proxy 可能會在接收時解密資料包，然後在傳送時 reencrypt 該資料包。</span><span class="sxs-lookup"><span data-stu-id="b08bb-126">The reverse proxy may decrypt the packet on receipt and then reencrypt the packet on sending.</span></span>

  - <span data-ttu-id="b08bb-127">從一個埠（例如 tcp 80）到另一個埠（例如，TCP 8080）橋接未加密的 TCP 流量。</span><span class="sxs-lookup"><span data-stu-id="b08bb-127">Bridging of unencrypted TCP traffic from one port (for example, TCP 80) to another (for example, TCP 8080).</span></span>

  - <span data-ttu-id="b08bb-128">允許設定或接受 NTLM 驗證，無驗證與傳遞驗證。</span><span class="sxs-lookup"><span data-stu-id="b08bb-128">Allow configuration of, or accept, NTLM authentication, No authentication and Pass-through authentication.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

