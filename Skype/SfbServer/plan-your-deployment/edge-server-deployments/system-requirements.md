---
title: 商務用 Skype Server 中的邊緣伺服器系統需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: 摘要：瞭解在商務用 Skype Server 中 Edge 伺服器的系統需求。
ms.openlocfilehash: 01a5cce8dd1ccb85d322b6c66615d022c8d6c2df
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2019
ms.locfileid: "36187807"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a><span data-ttu-id="ef7cc-103">商務用 Skype Server 中的邊緣伺服器系統需求</span><span class="sxs-lookup"><span data-stu-id="ef7cc-103">Edge Server system requirements in Skype for Business Server</span></span>
 
<span data-ttu-id="ef7cc-104">**摘要：** 瞭解商務用 Skype Server 中 Edge 伺服器的系統需求。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-104">**Summary:** Learn about the system requirements for Edge Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="ef7cc-105">在您的商務用 Skype Server Edge 伺服器部署中，這些是您針對環境本身中的伺服器或伺服器所需執行的操作，以及規劃環境結構。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-105">When it comes to your Skype for Business Server Edge Server deployment, these are the things you'll need to do for the server or servers that are in the environment itself, as well as planning for the environment structure.</span></span> <span data-ttu-id="ef7cc-106">如需有關拓撲、DNS、憑證及其他基礎結構問題的詳細資訊，請參閱環境需求檔。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-106">For more information on topology, DNS, certificates, and other infrastructure concerns, check out the environmental requirements documentation.</span></span>
  
## <a name="components"></a><span data-ttu-id="ef7cc-107">元件</span><span class="sxs-lookup"><span data-stu-id="ef7cc-107">Components</span></span>

<span data-ttu-id="ef7cc-108">在討論 Edge 伺服器環境時，我們會參照大多數在周邊網路中部署的元件（也就是在工作組或商務用 Skype Server 網域結構以外的網域中）。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-108">When discussing the Edge Server environment, we're referencing components that are, for the most part, deployed in a perimeter network (that's to say it's either in a workgroup or a domain that's outside your Skype for Business Server domain structure).</span></span>
  
<span data-ttu-id="ef7cc-109">請記住這一點，您必須牢記以下元件，才能成功部署 Edge：</span><span class="sxs-lookup"><span data-stu-id="ef7cc-109">Keeping that in mind, these are the components you're going to need to keep in mind for deploying your Edge successfully:</span></span>
  
- [<span data-ttu-id="ef7cc-110">Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="ef7cc-110">Edge Servers</span></span>](system-requirements.md#EdgeServers)
    
- [<span data-ttu-id="ef7cc-111">反向代理</span><span class="sxs-lookup"><span data-stu-id="ef7cc-111">Reverse proxies</span></span>](system-requirements.md#ReverseProxies)
    
- [<span data-ttu-id="ef7cc-112">道</span><span class="sxs-lookup"><span data-stu-id="ef7cc-112">Firewalls</span></span>](system-requirements.md#Firewalls)
    
- <span data-ttu-id="ef7cc-113">[控制器](system-requirements.md#Directors)（這是選擇性的，如果隨附的話），就會位於您的內部網路上。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-113">[Directors](system-requirements.md#Directors) (these are optional, and if they're included, they'll be located on your internal network)</span></span>
    
- <span data-ttu-id="ef7cc-114">[負載平衡](system-requirements.md#LoadBalancers)器（您可以使用 DNS 負載平衡或硬體負載平衡器（HLB），但針對單一邊緣伺服器則不需要這麼做）</span><span class="sxs-lookup"><span data-stu-id="ef7cc-114">[Load Balancers](system-requirements.md#LoadBalancers) (you can have DNS load balancing or a hardware load balancer (HLB), but for a single Edge Server, this isn't needed)</span></span>
    
<span data-ttu-id="ef7cc-115">我們在下列各項中有更多詳細資料：</span><span class="sxs-lookup"><span data-stu-id="ef7cc-115">We have more detail on each of these below:</span></span>
  
### <a name="edge-servers"></a><span data-ttu-id="ef7cc-116">Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="ef7cc-116">Edge Servers</span></span>
<span data-ttu-id="ef7cc-117"><a name="EdgeServers"> </a></span><span class="sxs-lookup"><span data-stu-id="ef7cc-117"></span></span>

<span data-ttu-id="ef7cc-118">這些是部署在週邊環境中的商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-118">These are the Skype for Business servers deployed in your perimeter environment.</span></span> <span data-ttu-id="ef7cc-119">其角色是針對您內部商務用 Skype Server 部署所提供的服務，傳送和接收外部使用者的網路流量。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-119">Their role is to send and receive network traffic to external users for the services offered by your internal Skype for Business Server deployment.</span></span> <span data-ttu-id="ef7cc-120">若要成功執行此動作，每個 Edge 伺服器都會執行：</span><span class="sxs-lookup"><span data-stu-id="ef7cc-120">To do this successfully, each Edge Server runs:</span></span>
  
- <span data-ttu-id="ef7cc-121">**存取邊緣服務**：針對輸出與輸入會話初始通訊協定（SIP）流量，提供單一、受信任的連接點。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-121">**Access Edge service**: Provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>
    
- <span data-ttu-id="ef7cc-122">**網路會議 Edge 服務**：可讓外部使用者加入託管在內部商務用 Skype Server 環境中的會議。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-122">**Web Conferencing Edge service**: Enables external users to join meetings that are hosted on your internal Skype for Business Server environment.</span></span>
    
- <span data-ttu-id="ef7cc-123">**A/V 邊緣服務**：讓外部使用者可以使用音訊、影片、應用程式共用和檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-123">**A/V Edge service**: Makes audio, video, application sharing and file transfer available to external users.</span></span>
    
- <span data-ttu-id="ef7cc-124">**XMPP Proxy service**：在已設定的 XMPP 同盟合作夥伴中，接受和傳送可擴展的訊息和目前狀態通訊協定（XMPP）訊息。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-124">**XMPP Proxy service**: Accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>
    
<span data-ttu-id="ef7cc-125">已授權的外部使用者可以使用 Edge 伺服器連線到內部商務用 Skype Server 部署，否則不會提供任何人對您內部網路的其他存取權。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-125">Authorized external users can use your Edge Servers to connect to your internal Skype for Business Server deployment, but otherwise, they provide no other access to your internal network for anyone.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ef7cc-126">已部署邊緣伺服器來提供已啟用商務用 Skype 用戶端和其他邊緣伺服器（在同盟情況中）的連線。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-126">Edge Servers are deployed to provide connections for enabled Skype for Business clients and other Edge Servers (in federation scenarios).</span></span> <span data-ttu-id="ef7cc-127">您無法從其他端點用戶端或伺服器類型進行連線。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-127">You can't connect from other end point client or server types.</span></span> <span data-ttu-id="ef7cc-128">XMPP 閘道伺服器可以允許與已設定 XMPP 夥伴的連線。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-128">The XMPP Gateway server can allow connections with configured XMPP partners.</span></span> <span data-ttu-id="ef7cc-129">但同樣地，這些都是唯一的用戶端和同盟類型可運作。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-129">But again, those are the only client and federation types that will work.</span></span> 

> [!NOTE]
> <span data-ttu-id="ef7cc-130">XMPP 閘道和 proxy 可在商務用 Skype Server 2015 中使用，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-130">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="ef7cc-131">如需詳細資訊，請參閱[遷移 XMPP 同盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-131">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
  
### <a name="reverse-proxies"></a><span data-ttu-id="ef7cc-132">反向代理</span><span class="sxs-lookup"><span data-stu-id="ef7cc-132">Reverse proxies</span></span>
<span data-ttu-id="ef7cc-133"><a name="ReverseProxies"> </a></span><span class="sxs-lookup"><span data-stu-id="ef7cc-133"></span></span>

<span data-ttu-id="ef7cc-134">反向 proxy （RP）伺服器沒有商務用 Skype 伺服器角色，但是 Edge 伺服器部署的基本元件。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-134">A reverse proxy (RP) server has no Skype for Business Server role, but is an essential component of an Edge Server deployment.</span></span> <span data-ttu-id="ef7cc-135">反向 proxy 允許外部使用者進行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ef7cc-135">A reverse proxy allows external users to:</span></span>
  
- <span data-ttu-id="ef7cc-136">使用簡單的 Url 連線至會議或電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-136">connect to meetings or dial-in conferences using simple URLs.</span></span>
    
- <span data-ttu-id="ef7cc-137">下載會議內容。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-137">download meeting content.</span></span>
    
- <span data-ttu-id="ef7cc-138">展開 [通訊群組]。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-138">expand distribution groups.</span></span>
    
- <span data-ttu-id="ef7cc-139">取得用戶端憑證的基於使用者認證的驗證</span><span class="sxs-lookup"><span data-stu-id="ef7cc-139">get user-based certificates for client certificate based authentication</span></span>
    
- <span data-ttu-id="ef7cc-140">從通訊錄服務器下載檔案，或將查詢提交至通訊錄網頁查詢服務。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-140">download files from the Address Book Server, or to submit queries to the Address Book Web Query service.</span></span>
    
- <span data-ttu-id="ef7cc-141">取得用戶端與裝置軟體的更新。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-141">obtain updates to client and device software.</span></span>
    
<span data-ttu-id="ef7cc-142">針對行動裝置：</span><span class="sxs-lookup"><span data-stu-id="ef7cc-142">And for mobile devices:</span></span>
  
- <span data-ttu-id="ef7cc-143">它可讓他們自動探索提供行動服務的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-143">it lets them automatically discover Front End Servers offering mobility services.</span></span>
    
- <span data-ttu-id="ef7cc-144">它可讓您從 Office 365 推播通知至行動裝置。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-144">it enables push notifications from Office 365 to mobile devices.</span></span>
    
<span data-ttu-id="ef7cc-145">我們可以在商務用 Skype 頁面的[電話架構](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)中找到目前的反向 proxy 建議。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-145">Our current reverse proxy recommendations can be found on the [Telephony Infrastructure for Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) page.</span></span> <span data-ttu-id="ef7cc-146">所以您的反向 proxy：</span><span class="sxs-lookup"><span data-stu-id="ef7cc-146">So your reverse proxy:</span></span>
  
- <span data-ttu-id="ef7cc-147">應該能夠使用您的環境中引入的傳輸層安全性（TLS），透過公用憑證連線到已發佈的外部 Web 服務：</span><span class="sxs-lookup"><span data-stu-id="ef7cc-147">should be able to use transport layer security (TLS) that's introduced to your environment via public certificates to connect to the published external Web services of:</span></span>
    
  - <span data-ttu-id="ef7cc-148">主管或主管池</span><span class="sxs-lookup"><span data-stu-id="ef7cc-148">Director or Director pool</span></span>
    
  - <span data-ttu-id="ef7cc-149">前端伺服器或前端池</span><span class="sxs-lookup"><span data-stu-id="ef7cc-149">Front End Server or Front End pool</span></span>
    
- <span data-ttu-id="ef7cc-150">需要能夠使用憑證進行加密來發佈內部網站，或以未加密的方式發佈它們（如果需要的話）。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-150">needs to be able to publish internal Web sites using certificates for encryption, or publish them over an unencrypted means, if needed.</span></span>
    
- <span data-ttu-id="ef7cc-151">應該能夠使用完全限定的功能變數名稱（FQDN），在外部發佈內部託管的網站。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-151">should be able to publish an internally hosted web site externally by using a fully qualified domain name (FQDN).</span></span>
    
- <span data-ttu-id="ef7cc-152">需要能夠發佈您所託管網站的所有內容。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-152">needs to be able to publish all the contents of your hosted web site.</span></span> <span data-ttu-id="ef7cc-153">根據預設，您可以使用\*\* / \*\*\* 指令，大多數的 web 伺服器都會辨識此程式，表示「在 web 伺服器上發佈所有內容」。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-153">By default, you can use the **/\\**\* directive, which is recognized by most web servers to mean "Publish all content on the web server."</span></span> <span data-ttu-id="ef7cc-154">您也可以修改指令，例如 \* */Uwca/\\* \* \*，這表示「在虛擬目錄 Ucwa 中發佈所有內容」。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-154">You can also modify the directive—for example, \*\*/Uwca/\\*\*\*, which means "Publish all content under the virtual directory Ucwa."</span></span>
    
- <span data-ttu-id="ef7cc-155">必須與從您發佈的網站要求內容的用戶端，才需要 TLS 連線。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-155">must require TLS connections with clients that request content from your published website.</span></span>
    
- <span data-ttu-id="ef7cc-156">必須接受使用 [消費者備用名稱（SAN）] 專案的憑證。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-156">has to accept certificates with subject alternative name (SAN) entries.</span></span>
    
- <span data-ttu-id="ef7cc-157">需要能夠將憑證系結到偵聽程式或介面，才能透過外部 web 服務 FQDN 解析。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-157">needs to be able to allow the binding of a certificate to a listener or interface through which the external web services FQDN will resolve.</span></span> <span data-ttu-id="ef7cc-158">偵聽程式設定優於介面。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-158">Listener configurations are preferable to interfaces.</span></span> <span data-ttu-id="ef7cc-159">許多監聽器可以在單一介面上設定。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-159">Many listeners can be configured on a single interface.</span></span>
    
- <span data-ttu-id="ef7cc-160">必須允許主機標頭處理的設定。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-160">must allow for the configuration of host header handling.</span></span> <span data-ttu-id="ef7cc-161">通常，由要求用戶端傳送的原始主機標頭必須透明地傳遞，而不是由反向 proxy 進行修改。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-161">Often, the original host header sent by the requesting client must be passed transparently, instead of being modified by the reverse proxy.</span></span>
    
- <span data-ttu-id="ef7cc-162">應該允許將 TLS 流量從一個外部定義的埠（例如，TCP 443）橋接到另一個已定義的埠（例如，TCP 4443）。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-162">should allow bridging of TLS traffic from one externally defined port (for example, TCP 443) to another defined port (for example, TCP 4443).</span></span> <span data-ttu-id="ef7cc-163">您的反向 proxy 可能會在接收時解密資料包，然後在傳送時 reencrypt 該資料包。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-163">Your reverse proxy may decrypt the packet on receipt and then reencrypt the packet on sending.</span></span>
    
- <span data-ttu-id="ef7cc-164">應該允許將未加密 TCP 流量從一個埠（例如 TCP 80）橋接到另一個埠（例如 TCP 8080）。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-164">should allow bridging of unencrypted TCP traffic from one port (for example, TCP 80) to another (for example, TCP 8080).</span></span>
    
- <span data-ttu-id="ef7cc-165">需要允許設定或接受 NTLM 驗證、無驗證，以及傳遞驗證。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-165">needs to allow configuration of, or accept, NTLM authentication, no authentication, and pass-through authentication.</span></span>
    
<span data-ttu-id="ef7cc-166">如果您的反向 proxy 能滿足此清單中的所有需求，您應該可以開始使用，但請記住上述連結的建議。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-166">If your reverse proxy can address all the needs in this list, you should be good to go, but please keep in mind our recommendations at the link provided above.</span></span>
  
### <a name="firewalls"></a><span data-ttu-id="ef7cc-167">道</span><span class="sxs-lookup"><span data-stu-id="ef7cc-167">Firewalls</span></span>
<span data-ttu-id="ef7cc-168"><a name="Firewalls"> </a></span><span class="sxs-lookup"><span data-stu-id="ef7cc-168"></span></span>

<span data-ttu-id="ef7cc-169">您需要將 Edge 部署放在外部防火牆後面，但我們建議您在邊緣環境和您的內部環境中，有兩個防火牆（一個外部，一個內部）。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-169">You need to put your Edge deployment behind an external firewall, but we recommend having two firewalls, one external, and one internal between the Edge environment and your internal environment.</span></span> <span data-ttu-id="ef7cc-170">我們所有案例中的所有檔都將會有兩個防火牆。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-170">All our documentation in our Scenarios will have two firewalls.</span></span> <span data-ttu-id="ef7cc-171">我們建議您兩個防火牆，因為它可確保嚴格地從一個網路邊緣路由至另一個，並將內部網路的防火牆保護加倍。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-171">We recommend two firewalls because it ensures strict routing from one network edge to the other, and doubles the firewall protection for your internal network.</span></span>
  
### <a name="directors"></a><span data-ttu-id="ef7cc-172">控制器</span><span class="sxs-lookup"><span data-stu-id="ef7cc-172">Directors</span></span>
<span data-ttu-id="ef7cc-173"><a name="Directors"> </a></span><span class="sxs-lookup"><span data-stu-id="ef7cc-173"></span></span>

<span data-ttu-id="ef7cc-174">此為選用的角色。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-174">This is an optional role.</span></span> <span data-ttu-id="ef7cc-175">它可以是單一伺服器或執行主管角色的伺服器池。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-175">It can be a single server or a pool of servers running the Director role.</span></span> <span data-ttu-id="ef7cc-176">它是在內部商務用 Skype Server 環境中找到的角色。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-176">It's a role found on the internal Skype for Business Server environment.</span></span>
  
<span data-ttu-id="ef7cc-177">Director 是內部的下一個躍點伺服器，會從傳送給商務用 Skype Server 內部伺服器的邊緣伺服器接收入站 SIP 流量。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-177">The Director is an internal next hop server which receives inbound SIP traffic from the Edge Servers that's destined for Skype for Business Server internal servers.</span></span> <span data-ttu-id="ef7cc-178">它會 preauthenticates 輸入要求，並將它們重新導向至使用者的主文件池或伺服器。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-178">It preauthenticates inbound requests and redirects them to a user's home pool or server.</span></span> <span data-ttu-id="ef7cc-179">這個預驗證可讓您刪除不可識別的使用者帳戶要求。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-179">This preauthentication allows you to drop unidentified user account requests.</span></span>
  
<span data-ttu-id="ef7cc-180">為什麼這麼重要？</span><span class="sxs-lookup"><span data-stu-id="ef7cc-180">Why does that matter?</span></span> <span data-ttu-id="ef7cc-181">主管的重要功能是保護標準版伺服器與前端伺服器或前端池免遭惡意流量（例如拒絕服務（DoS）攻擊）。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-181">An important function for a Director is to protect Standard Edition servers and Front End Servers or Front End pools from malicious traffic, such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="ef7cc-182">如果您的網路充斥了不正確外部流量，通信量就會停止在 Director 上。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-182">If your network is flooded with invalid external traffic, the traffic stops at the Director.</span></span>
  
### <a name="load-balancers"></a><span data-ttu-id="ef7cc-183">負載平衡器</span><span class="sxs-lookup"><span data-stu-id="ef7cc-183">Load Balancers</span></span>
<span data-ttu-id="ef7cc-184"><a name="LoadBalancers"> </a></span><span class="sxs-lookup"><span data-stu-id="ef7cc-184"></span></span>

<span data-ttu-id="ef7cc-185">商務用 Skype 伺服器伸縮的合併邊緣拓朴已針對新部署的 DNS 負載平衡進行優化，我們建議這樣做。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-185">The Skype for Business Server scaled consolidated Edge topology is optimized for DNS load balancing for new deployments, and we recommend this.</span></span> <span data-ttu-id="ef7cc-186">如果您需要高可用性，建議您針對其中一個特定情況使用硬體負載平衡器：</span><span class="sxs-lookup"><span data-stu-id="ef7cc-186">If you need high availability, we recommend using a hardware load balancer for one specific situation:</span></span>
  
- <span data-ttu-id="ef7cc-187">Exchange 2013**之前**使用 exchange um 的遠端使用者的 exchange um。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-187">Exchange UM for remote users using Exchange UM **prior** to Exchange 2013.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="ef7cc-188">請務必注意，您無法混合負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-188">It's vital to note that you can't mix load-balancers.</span></span> <span data-ttu-id="ef7cc-189">在您的商務用 Skype Server 環境中，所有介面都必須使用 DNS 或 HLB。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-189">In your Skype for Business Server environment all interfaces must use either DNS or HLB.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ef7cc-190">商務用 Skype Server 不支援直接伺服器返回（DSR） NAT。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-190">Direct server return (DSR) NAT isn't supported for Skype for Business Server.</span></span> 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="ef7cc-191">執行 A/V 邊緣服務的邊緣伺服器邊緣伺服器的硬體負載平衡器需求</span><span class="sxs-lookup"><span data-stu-id="ef7cc-191">hardware load balancer requirements for Edge Servers Edge Servers running the A/V Edge service</span></span>

<span data-ttu-id="ef7cc-192">針對執行 A/V 邊緣服務的任何邊緣伺服器，以下是一些需求：</span><span class="sxs-lookup"><span data-stu-id="ef7cc-192">For any Edge Server running the A/V Edge service, these are the requirements:</span></span>
  
- <span data-ttu-id="ef7cc-193">關閉內部和外部埠443的 TCP Nagling （Nagling 是將幾個小型資料包合併成一個較大的資料包，以更有效率地傳輸）的程式。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-193">Turn off TCP nagling for both internal and external ports 443 (nagling is the process of combining several small packets into a single, larger packet for more efficient transmission).</span></span>
    
- <span data-ttu-id="ef7cc-194">關閉外部埠範圍 50000-59999 的 TCP Nagling。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-194">Turn off TCP nagling for the external port range 50000 - 59999.</span></span>
    
- <span data-ttu-id="ef7cc-195">請勿在您的內部或外部防火牆上使用 NAT。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-195">Don't use NAT on your internal or external firewalls.</span></span>
    
- <span data-ttu-id="ef7cc-196">您的 Edge 內部介面必須與邊緣伺服器外部介面在不同的網路上，而且必須停用它們之間的路由。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-196">Your Edge internal interface must be on a different network than your Edge Server external interface, and routing between them must be disabled.</span></span>
    
- <span data-ttu-id="ef7cc-197">執行 A/V 邊緣服務的任何邊緣伺服器的外部介面，都必須使用可公開路由的 IP 位址，而且任何邊緣外部 IP 位址都沒有 NAT 或埠轉譯。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-197">The external interface of any Edge Server running the A/V Edge service must use publicly routable IP addresses and no NAT or port translation on any of the Edge external IP addresses.</span></span>
    
#### <a name="hlb-requirements"></a><span data-ttu-id="ef7cc-198">HLB 需求</span><span class="sxs-lookup"><span data-stu-id="ef7cc-198">HLB requirements</span></span>

<span data-ttu-id="ef7cc-199">商務用 Skype 伺服器不會有許多 cookie 關聯需求。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-199">Skype for Business Server doesn't have a lot of cookie-based affinity requirements.</span></span> <span data-ttu-id="ef7cc-200">因此，您不需要使用以 cookie 為基礎的持久性，**除非**（這是商務用 skype server 2015），否則您會在商務用 skype server 環境中擁有 Lync Server 2010 前端伺服器或前端池。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-200">So you don't need to use a cookie-based persistence **unless** (and this is Skype for Business Server 2015-specific) you're going to have Lync Server 2010 Front End Servers or Front End pools in your Skype for Business Server environment.</span></span> <span data-ttu-id="ef7cc-201">它們在 Lync Server 2010 建議的設定方法中需要以 cookie 為基礎的關聯性。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-201">They would need cookie-based affinity in the configuration method recommended for Lync Server 2010.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ef7cc-202">如果您決定針對您的 HLB 開啟以 cookie 為基礎的關聯性，即使您的環境不需要它，也不會發生問題。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-202">If you decide to turn cookie-based affinity on for your HLB, there won't be a problem doing so, even if your environment doesn't need it.</span></span> 
  
<span data-ttu-id="ef7cc-203">如果您的環境**不**需要以 cookie 為基礎的關聯：</span><span class="sxs-lookup"><span data-stu-id="ef7cc-203">If your environment **doesn't** need cookie-based affinity:</span></span>
  
- <span data-ttu-id="ef7cc-204">在埠443的反向 proxy 發佈規則中，將 [**轉寄主機頭**] 設定為**True**。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-204">On the reverse proxy publishing rule for port 443, set **Forward host header** to **True**.</span></span> <span data-ttu-id="ef7cc-205">這可確保原始 URL 已轉寄。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-205">This will ensure the original URL is forwarded.</span></span>
    
<span data-ttu-id="ef7cc-206">針對需要以 cookie 為基礎的**關聯的部署**：</span><span class="sxs-lookup"><span data-stu-id="ef7cc-206">For deployments that **do** need cookie-based affinity:</span></span>
  
- <span data-ttu-id="ef7cc-207">在埠443的反向 proxy 發佈規則中，將 [**轉寄主機頭**] 設定為**True**。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-207">On the reverse proxy publishing rule for port 443, set **Forward host header** to **True**.</span></span> <span data-ttu-id="ef7cc-208">這可確保原始 URL 已轉寄。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-208">This will ensure the original URL is forwarded.</span></span>
    
- <span data-ttu-id="ef7cc-209">硬體負載平衡器 cookie**不**能標示為 [HTTPOnly]。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-209">The hardware load balancer cookie **must not** be marked httpOnly.</span></span>
    
- <span data-ttu-id="ef7cc-210">硬體負載平衡器 cookie**不**能有到期時間。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-210">The hardware load balancer cookie **must not** have an expiration time.</span></span>
    
- <span data-ttu-id="ef7cc-211">硬體負載平衡器 cookie**必須**命名為**MS-WSMAN** （這是 Web 服務預期的值，且無法變更）。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-211">The hardware load balancer cookie **must** be named **MS-WSMAN** (this is the value that the Web services expect, and it can't be changed).</span></span>
    
- <span data-ttu-id="ef7cc-212">硬體負載平衡器 cookie**必須**在每一個 HTTP 回應中設定（無論是否已在相同的 TCP 連線中先前的 HTTP 回應都已取得 cookie）。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-212">The hardware load balancer cookie **must** be set in every HTTP response for which the incoming HTTP request didn't have a cookie, regardless of whether a previous HTTP response on that same TCP connection had gotten a cookie.</span></span> <span data-ttu-id="ef7cc-213">如果您的硬體負載平衡器針對每個 TCP 連線優化 cookie 插入，則**不一定**要使用這種優化。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-213">If your hardware load balancer optimizes cookie insert to only occur once per TCP connection, that optimization **must not** be used.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ef7cc-214">典型的 HLB 設定是使用來源關聯和20分鐘 TCP 會話存留期（適用于商務用 Skype Server 及其用戶端），因為會話狀態是透過用戶端使用量和/或應用程式互動來維護。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-214">It's typical for HLB configurations to use source-affinity and 20 minute TCP session lifetime, which is fine for Skype for Business Server and its clients, because session state is maintained through client usage, and/or application interaction.</span></span> 
  
<span data-ttu-id="ef7cc-215">如果您要部署行動裝置，您的 HLB 必須能夠在 TCP 會話中的個別要求之間進行負載平衡（事實上，您必須能夠根據目標 IP 位址來負載平衡個別要求）。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-215">If you're deploying mobile devices, your HLB must be able to load balance individual requests within a TCP session (in effect, you need to be able to load balance an individual request based on the target IP address).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ef7cc-216">F5 HLBs 具有稱為 [OneConnect] 的功能。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-216">F5 HLBs have a feature called OneConnect.</span></span> <span data-ttu-id="ef7cc-217">它可確保 TCP 連線中的每個要求都有個別的負載平衡。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-217">It ensures that each request within a TCP connection is individually load balanced.</span></span> <span data-ttu-id="ef7cc-218">如果您要部署行動裝置，請確定您的 HLB 供應商支援相同的功能。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-218">If you're deploying mobile devices, ensure your HLB vendor supports the same functionality.</span></span> <span data-ttu-id="ef7cc-219">最新的 iOS 行動裝置 app 需要 TLS 版本1.2。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-219">The latest iOS mobile apps require TLS version 1.2.</span></span> <span data-ttu-id="ef7cc-220">如果您需要進一步瞭解，F5 會針對此提供特定設定。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-220">If you need to know more, F5 provides specific settings for this.</span></span> 
  
<span data-ttu-id="ef7cc-221">以下是（選用）主管及（必要）前端池 Web 服務的 HLB 需求：</span><span class="sxs-lookup"><span data-stu-id="ef7cc-221">Here are the HLB requirements for the (optional) Director and (required) Front End pool Web Services:</span></span>
  
- <span data-ttu-id="ef7cc-222">針對您的內部 Web 服務 Vip，請在您的 HLB 上設定 Source_addr 暫留（內部埠80，443）。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-222">For your internal Web Services VIPs, set Source_addr persistence (internal port 80, 443) on your HLB.</span></span> <span data-ttu-id="ef7cc-223">在商務用 Skype Server 中，Source_addr [暫留] 表示來自單一 IP 位址的多個連線總是傳送到一台伺服器，以維持會話狀態。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-223">For Skype for Business Server, Source_addr persistence means that multiple connections coming from a single IP address are always sent to one server, to maintain session state.</span></span>
    
- <span data-ttu-id="ef7cc-224">使用1800秒的 TCP 空閒超時。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-224">Use a TCP idle timeout of 1800 seconds.</span></span>
    
- <span data-ttu-id="ef7cc-225">在您的反向 proxy 與下一個躍點池的 HLB 之間，建立規則，允許從您的反向 proxy 到您的 HLB，在埠4443上進行 HTTPs：流量。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-225">On the firewall between your reverse proxy and your next hop pool's HLB, create a rule to allow https: traffic on port 4443, from your reverse proxy to your HLB.</span></span> <span data-ttu-id="ef7cc-226">您的 HLB 需要設定為偵聽埠80、443和4443。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-226">Your HLB needs to be configured to listen on ports 80, 443, and 4443.</span></span>
    
#### <a name="summary-of-hlb-affinity-requirements"></a><span data-ttu-id="ef7cc-227">HLB 關聯需求摘要</span><span class="sxs-lookup"><span data-stu-id="ef7cc-227">Summary of HLB affinity requirements</span></span>

|<span data-ttu-id="ef7cc-228">**用戶端/使用者位置**</span><span class="sxs-lookup"><span data-stu-id="ef7cc-228">**Client/user location**</span></span>|<span data-ttu-id="ef7cc-229">**外部 web 服務 FQDN 關聯需求**</span><span class="sxs-lookup"><span data-stu-id="ef7cc-229">**External web services FQDN affinity requirements**</span></span>|<span data-ttu-id="ef7cc-230">**內部 web 服務 FQSN 關聯需求**</span><span class="sxs-lookup"><span data-stu-id="ef7cc-230">**Internal web services FQSN affinity requirements**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ef7cc-231">商務用 Skype Web App （內部和外部使用者）</span><span class="sxs-lookup"><span data-stu-id="ef7cc-231">Skype for Business Web App (internal and external users)</span></span>  <br/> <span data-ttu-id="ef7cc-232">行動裝置（內部和外部使用者</span><span class="sxs-lookup"><span data-stu-id="ef7cc-232">Mobile device (internal and external users</span></span>  <br/> |<span data-ttu-id="ef7cc-233">沒有關聯性</span><span class="sxs-lookup"><span data-stu-id="ef7cc-233">No affinity</span></span>  <br/> |<span data-ttu-id="ef7cc-234">來源位址關聯</span><span class="sxs-lookup"><span data-stu-id="ef7cc-234">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="ef7cc-235">商務用 Skype Web App （僅限外部使用者）</span><span class="sxs-lookup"><span data-stu-id="ef7cc-235">Skype for Business Web App (external users only)</span></span>  <br/> <span data-ttu-id="ef7cc-236">行動裝置（內部和外部使用者</span><span class="sxs-lookup"><span data-stu-id="ef7cc-236">Mobile device (internal and external users</span></span>  <br/> |<span data-ttu-id="ef7cc-237">沒有關聯性</span><span class="sxs-lookup"><span data-stu-id="ef7cc-237">No affinity</span></span>  <br/> |<span data-ttu-id="ef7cc-238">來源位址關聯</span><span class="sxs-lookup"><span data-stu-id="ef7cc-238">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="ef7cc-239">商務用 Skype Web App （僅限內部使用者）</span><span class="sxs-lookup"><span data-stu-id="ef7cc-239">Skype for Business Web App (internal users only)</span></span>  <br/> <span data-ttu-id="ef7cc-240">行動裝置（未部署）</span><span class="sxs-lookup"><span data-stu-id="ef7cc-240">Mobile device (not deployed)</span></span>  <br/> |<span data-ttu-id="ef7cc-241">沒有關聯性</span><span class="sxs-lookup"><span data-stu-id="ef7cc-241">No affinity</span></span>  <br/> |<span data-ttu-id="ef7cc-242">來源位址關聯</span><span class="sxs-lookup"><span data-stu-id="ef7cc-242">Source address affinity</span></span>  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a><span data-ttu-id="ef7cc-243">HLBs 的埠監視</span><span class="sxs-lookup"><span data-stu-id="ef7cc-243">Port monitoring for HLBs</span></span>

<span data-ttu-id="ef7cc-244">您可以在硬體負載平衡器上定義埠監視，以判斷特定服務何時無法使用，因為硬體或通訊失敗。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-244">You define port monitoring on your hardware load balancers to determine when specific services are no longer available, due to hardware or communications failure.</span></span> <span data-ttu-id="ef7cc-245">例如，如果前端伺服器或前端池發生故障，[前端伺服器服務（RTCSRV）] 停止，則 HLB 監視也應該停止在 Web 服務上接收流量。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-245">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="ef7cc-246">您應該在 HLB 上執行埠監視，以監視 HLB 外部介面的下列事項：</span><span class="sxs-lookup"><span data-stu-id="ef7cc-246">You should implement port monitoring on the HLB to monitor the following for your HLB external interface:</span></span>
  
|<span data-ttu-id="ef7cc-247">**虛擬 IP/埠**</span><span class="sxs-lookup"><span data-stu-id="ef7cc-247">**Virtual IP/Port**</span></span>|<span data-ttu-id="ef7cc-248">**節點埠**</span><span class="sxs-lookup"><span data-stu-id="ef7cc-248">**Node Port**</span></span>|<span data-ttu-id="ef7cc-249">**節點電腦/監視器**</span><span class="sxs-lookup"><span data-stu-id="ef7cc-249">**Node Machine/Monitor**</span></span>|<span data-ttu-id="ef7cc-250">**持久性設定檔**</span><span class="sxs-lookup"><span data-stu-id="ef7cc-250">**Persistence Profile**</span></span>|<span data-ttu-id="ef7cc-251">**筆記**</span><span class="sxs-lookup"><span data-stu-id="ef7cc-251">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ef7cc-252">\<pool\>web_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="ef7cc-252">\<pool\>web_mco_443_vs</span></span>  <br/> <span data-ttu-id="ef7cc-253">443</span><span class="sxs-lookup"><span data-stu-id="ef7cc-253">443</span></span>  <br/> |<span data-ttu-id="ef7cc-254">4443</span><span class="sxs-lookup"><span data-stu-id="ef7cc-254">4443</span></span>  <br/> |<span data-ttu-id="ef7cc-255">前端</span><span class="sxs-lookup"><span data-stu-id="ef7cc-255">Front End</span></span>  <br/> <span data-ttu-id="ef7cc-256">5061</span><span class="sxs-lookup"><span data-stu-id="ef7cc-256">5061</span></span>  <br/> |<span data-ttu-id="ef7cc-257">無</span><span class="sxs-lookup"><span data-stu-id="ef7cc-257">None</span></span>  <br/> |<span data-ttu-id="ef7cc-258">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="ef7cc-258">HTTPS</span></span>  <br/> |
|<span data-ttu-id="ef7cc-259">\<pool\>web_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="ef7cc-259">\<pool\>web_mco_80_vs</span></span>  <br/> <span data-ttu-id="ef7cc-260">80</span><span class="sxs-lookup"><span data-stu-id="ef7cc-260">80</span></span>  <br/> |<span data-ttu-id="ef7cc-261">8080</span><span class="sxs-lookup"><span data-stu-id="ef7cc-261">8080</span></span>  <br/> |<span data-ttu-id="ef7cc-262">前端</span><span class="sxs-lookup"><span data-stu-id="ef7cc-262">Front End</span></span>  <br/> <span data-ttu-id="ef7cc-263">5061</span><span class="sxs-lookup"><span data-stu-id="ef7cc-263">5061</span></span>  <br/> |<span data-ttu-id="ef7cc-264">無</span><span class="sxs-lookup"><span data-stu-id="ef7cc-264">None</span></span>  <br/> |<span data-ttu-id="ef7cc-265">HTTP</span><span class="sxs-lookup"><span data-stu-id="ef7cc-265">HTTP</span></span>  <br/> |
   
## <a name="hardware-and-software-requirements"></a><span data-ttu-id="ef7cc-266">硬體和軟體需求</span><span class="sxs-lookup"><span data-stu-id="ef7cc-266">Hardware and software requirements</span></span>

<span data-ttu-id="ef7cc-267">我們已在商務用 skype Server 2015 和[商務用 Skype server 2019 檔的系統需求](../../../SfBServer2019/plan/system-requirements.md)[的完整伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)中，涵蓋了 Edge 伺服器硬體和軟體需求。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-267">We've covered Edge Server hardware and software requirements in our overall [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and  [System requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) documentation.</span></span>
  
## <a name="collocation"></a><span data-ttu-id="ef7cc-268">Collocation</span><span class="sxs-lookup"><span data-stu-id="ef7cc-268">Collocation</span></span>

<span data-ttu-id="ef7cc-269">我們已在我們[針對商務用 Skype Server 檔的拓撲基礎](../../plan-your-deployment/topology-basics/topology-basics.md)中涵蓋了 Edge 伺服器 collocation。</span><span class="sxs-lookup"><span data-stu-id="ef7cc-269">We've covered Edge Server collocation in our [Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md) documentation.</span></span>
  

