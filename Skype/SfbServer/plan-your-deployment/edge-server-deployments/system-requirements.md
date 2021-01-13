---
title: 商務用 Skype Server 中的 Edge Server 系統需求
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: 摘要：瞭解在商務用 Skype Server 中 Edge Server 的系統需求。
ms.openlocfilehash: e066249498febbd5e622546533f49422320c7c87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813763"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a><span data-ttu-id="a9a66-103">商務用 Skype Server 中的 Edge Server 系統需求</span><span class="sxs-lookup"><span data-stu-id="a9a66-103">Edge Server system requirements in Skype for Business Server</span></span>
 
<span data-ttu-id="a9a66-104">**摘要：** 深入瞭解在商務用 Skype Server 中的 Edge Server 的系統需求。</span><span class="sxs-lookup"><span data-stu-id="a9a66-104">**Summary:** Learn about the system requirements for Edge Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="a9a66-105">當您前往商務用 Skype Server Edge Server 部署時，您需要針對環境本身中的伺服器或伺服器進行下列作業，以及規劃環境結構。</span><span class="sxs-lookup"><span data-stu-id="a9a66-105">When it comes to your Skype for Business Server Edge Server deployment, these are the things you'll need to do for the server or servers that are in the environment itself, as well as planning for the environment structure.</span></span> <span data-ttu-id="a9a66-106">如需拓撲、DNS、憑證及其他基礎結構問題的詳細資訊，請參閱環境需求檔。</span><span class="sxs-lookup"><span data-stu-id="a9a66-106">For more information on topology, DNS, certificates, and other infrastructure concerns, check out the environmental requirements documentation.</span></span>
  
## <a name="components"></a><span data-ttu-id="a9a66-107">元件</span><span class="sxs-lookup"><span data-stu-id="a9a66-107">Components</span></span>

<span data-ttu-id="a9a66-108">當您討論 Edge Server 環境時，我們會參考大多數在周邊網路中部署的元件， (這是指在工作組或位於商務用 Skype Server 域結構之外的網域中) 。</span><span class="sxs-lookup"><span data-stu-id="a9a66-108">When discussing the Edge Server environment, we're referencing components that are, for the most part, deployed in a perimeter network (that's to say it's either in a workgroup or a domain that's outside your Skype for Business Server domain structure).</span></span>
  
<span data-ttu-id="a9a66-109">請記住，這些是您在成功部署 Edge 時需要記住的元件：</span><span class="sxs-lookup"><span data-stu-id="a9a66-109">Keeping that in mind, these are the components you're going to need to keep in mind for deploying your Edge successfully:</span></span>
  
- [<span data-ttu-id="a9a66-110">Edge Server</span><span class="sxs-lookup"><span data-stu-id="a9a66-110">Edge Servers</span></span>](system-requirements.md#EdgeServers)
    
- [<span data-ttu-id="a9a66-111">反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="a9a66-111">Reverse proxies</span></span>](system-requirements.md#ReverseProxies)
    
- [<span data-ttu-id="a9a66-112">防火牆</span><span class="sxs-lookup"><span data-stu-id="a9a66-112">Firewalls</span></span>](system-requirements.md#Firewalls)
    
- <span data-ttu-id="a9a66-113">[Director](system-requirements.md#Directors) (這些是選用性的，如果包含的話，它們就會位於您的內部網路上) </span><span class="sxs-lookup"><span data-stu-id="a9a66-113">[Directors](system-requirements.md#Directors) (these are optional, and if they're included, they'll be located on your internal network)</span></span>
    
- <span data-ttu-id="a9a66-114">[負載平衡](system-requirements.md#LoadBalancers) 器 (您可以使用 DNS 負載平衡或硬體負載平衡器 (HLB) ，但是針對單一 Edge Server，不需要這麼做) </span><span class="sxs-lookup"><span data-stu-id="a9a66-114">[Load Balancers](system-requirements.md#LoadBalancers) (you can have DNS load balancing or a hardware load balancer (HLB), but for a single Edge Server, this isn't needed)</span></span>
    
<span data-ttu-id="a9a66-115">我們每個下列各項都有詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="a9a66-115">We have more detail on each of these below:</span></span>
  
### <a name="edge-servers"></a><span data-ttu-id="a9a66-116">Edge Server</span><span class="sxs-lookup"><span data-stu-id="a9a66-116">Edge Servers</span></span>
<span data-ttu-id="a9a66-117"><a name="EdgeServers"> </a></span><span class="sxs-lookup"><span data-stu-id="a9a66-117"><a name="EdgeServers"> </a></span></span>

<span data-ttu-id="a9a66-118">這些是部署在周邊環境中的商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="a9a66-118">These are the Skype for Business servers deployed in your perimeter environment.</span></span> <span data-ttu-id="a9a66-119">其角色是針對內部商務用 Skype Server 部署所提供的服務，傳送和接收網路流量給外部使用者。</span><span class="sxs-lookup"><span data-stu-id="a9a66-119">Their role is to send and receive network traffic to external users for the services offered by your internal Skype for Business Server deployment.</span></span> <span data-ttu-id="a9a66-120">若要成功執行這項作業，每個 Edge Server 都會執行：</span><span class="sxs-lookup"><span data-stu-id="a9a66-120">To do this successfully, each Edge Server runs:</span></span>
  
- <span data-ttu-id="a9a66-121">**Access Edge service**：為輸出和輸入會話初始通訊協定 (SIP) 流量提供單一信任的連線點。</span><span class="sxs-lookup"><span data-stu-id="a9a66-121">**Access Edge service**: Provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>
    
- <span data-ttu-id="a9a66-122">**Web 會議 Edge service**：可讓外部使用者加入內部商務用 Skype 伺服器環境所主控的會議。</span><span class="sxs-lookup"><span data-stu-id="a9a66-122">**Web Conferencing Edge service**: Enables external users to join meetings that are hosted on your internal Skype for Business Server environment.</span></span>
    
- <span data-ttu-id="a9a66-123">**A/V Edge service**：讓外部使用者可以使用音訊、影片、應用程式共用和檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="a9a66-123">**A/V Edge service**: Makes audio, video, application sharing and file transfer available to external users.</span></span>
    
- <span data-ttu-id="a9a66-124">**XMPP Proxy 服務**：接受及傳送可延伸的訊息和顯示狀態通訊協定 (XMPP) 與已設定 XMPP 同盟協力廠商的郵件。</span><span class="sxs-lookup"><span data-stu-id="a9a66-124">**XMPP Proxy service**: Accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>
    
<span data-ttu-id="a9a66-125">已授權的外部使用者可以使用 Edge Server 連線到內部的商務用 Skype Server 部署，但在其他情況下，不會為任何人提供內部網路的其他存取權。</span><span class="sxs-lookup"><span data-stu-id="a9a66-125">Authorized external users can use your Edge Servers to connect to your internal Skype for Business Server deployment, but otherwise, they provide no other access to your internal network for anyone.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a9a66-126">Edge Server 會進行部署，以提供啟用商務用 Skype 用戶端和其他 Edge Server (在同盟情況) 中的連線。</span><span class="sxs-lookup"><span data-stu-id="a9a66-126">Edge Servers are deployed to provide connections for enabled Skype for Business clients and other Edge Servers (in federation scenarios).</span></span> <span data-ttu-id="a9a66-127">您無法從其他端點用戶端或伺服器類型進行連線。</span><span class="sxs-lookup"><span data-stu-id="a9a66-127">You can't connect from other end point client or server types.</span></span> <span data-ttu-id="a9a66-128">XMPP 閘道伺服器可允許與已設定 XMPP 合作夥伴的連線。</span><span class="sxs-lookup"><span data-stu-id="a9a66-128">The XMPP Gateway server can allow connections with configured XMPP partners.</span></span> <span data-ttu-id="a9a66-129">不過，這些是唯一可以運作的用戶端和同盟類型。</span><span class="sxs-lookup"><span data-stu-id="a9a66-129">But again, those are the only client and federation types that will work.</span></span> 

> [!NOTE]
> <span data-ttu-id="a9a66-130">XMPP 閘道和 proxy 可用於商務用 Skype Server 2015，但在商務用 Skype Server 2019 中已不再支援。</span><span class="sxs-lookup"><span data-stu-id="a9a66-130">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="a9a66-131">如需詳細資訊，請參閱 [遷移 XMPP 同盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 。</span><span class="sxs-lookup"><span data-stu-id="a9a66-131">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
  
### <a name="reverse-proxies"></a><span data-ttu-id="a9a66-132">反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="a9a66-132">Reverse proxies</span></span>
<span data-ttu-id="a9a66-133"><a name="ReverseProxies"> </a></span><span class="sxs-lookup"><span data-stu-id="a9a66-133"><a name="ReverseProxies"> </a></span></span>

<span data-ttu-id="a9a66-134">反向 proxy (RP) server 沒有商務用 Skype 伺服器角色，但為 Edge Server 部署的基本元件。</span><span class="sxs-lookup"><span data-stu-id="a9a66-134">A reverse proxy (RP) server has no Skype for Business Server role, but is an essential component of an Edge Server deployment.</span></span> <span data-ttu-id="a9a66-135">反向 proxy 允許外部使用者執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="a9a66-135">A reverse proxy allows external users to:</span></span>
  
- <span data-ttu-id="a9a66-136">使用簡單 URLs 連線到會議或電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="a9a66-136">connect to meetings or dial-in conferences using simple URLs.</span></span>
    
- <span data-ttu-id="a9a66-137">下載會議內容。</span><span class="sxs-lookup"><span data-stu-id="a9a66-137">download meeting content.</span></span>
    
- <span data-ttu-id="a9a66-138">展開 [通訊群組]。</span><span class="sxs-lookup"><span data-stu-id="a9a66-138">expand distribution groups.</span></span>
    
- <span data-ttu-id="a9a66-139">取得以使用者為基礎的憑證，以供用戶端憑證驗證</span><span class="sxs-lookup"><span data-stu-id="a9a66-139">get user-based certificates for client certificate based authentication</span></span>
    
- <span data-ttu-id="a9a66-140">從通訊錄服務器下載檔案，或將查詢提交至通訊錄 Web 查詢服務。</span><span class="sxs-lookup"><span data-stu-id="a9a66-140">download files from the Address Book Server, or to submit queries to the Address Book Web Query service.</span></span>
    
- <span data-ttu-id="a9a66-141">取得用戶端和裝置軟體的更新。</span><span class="sxs-lookup"><span data-stu-id="a9a66-141">obtain updates to client and device software.</span></span>
    
<span data-ttu-id="a9a66-142">對於行動裝置：</span><span class="sxs-lookup"><span data-stu-id="a9a66-142">And for mobile devices:</span></span>
  
- <span data-ttu-id="a9a66-143">它可讓他們自動探索前端伺服器提供行動性服務。</span><span class="sxs-lookup"><span data-stu-id="a9a66-143">it lets them automatically discover Front End Servers offering mobility services.</span></span>
    
- <span data-ttu-id="a9a66-144">它會啟用從 Microsoft 365 或 Office 365 到行動裝置的推播通知。</span><span class="sxs-lookup"><span data-stu-id="a9a66-144">it enables push notifications from Microsoft 365 or Office 365 to mobile devices.</span></span>
    
<span data-ttu-id="a9a66-145">目前的反向 proxy 建議可在商務用 Skype 頁面的 [電話語音基礎結構](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) 上找到。</span><span class="sxs-lookup"><span data-stu-id="a9a66-145">Our current reverse proxy recommendations can be found on the [Telephony Infrastructure for Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) page.</span></span> <span data-ttu-id="a9a66-146">您的反向 proxy：</span><span class="sxs-lookup"><span data-stu-id="a9a66-146">So your reverse proxy:</span></span>
  
- <span data-ttu-id="a9a66-147">應該可以使用傳輸層安全性 (TLS) （透過公用憑證將其引入您的環境），以連線至已發佈的外部 Web 服務：</span><span class="sxs-lookup"><span data-stu-id="a9a66-147">should be able to use transport layer security (TLS) that's introduced to your environment via public certificates to connect to the published external Web services of:</span></span>
    
  - <span data-ttu-id="a9a66-148">Director 或 Director 集區</span><span class="sxs-lookup"><span data-stu-id="a9a66-148">Director or Director pool</span></span>
    
  - <span data-ttu-id="a9a66-149">前端伺服器或前端集區</span><span class="sxs-lookup"><span data-stu-id="a9a66-149">Front End Server or Front End pool</span></span>
    
- <span data-ttu-id="a9a66-150">必須能夠發佈使用憑證進行加密的內部網站，或在必要時以未加密的方式發佈。</span><span class="sxs-lookup"><span data-stu-id="a9a66-150">needs to be able to publish internal Web sites using certificates for encryption, or publish them over an unencrypted means, if needed.</span></span>
    
- <span data-ttu-id="a9a66-151">應該可以透過使用完整功能變數名稱 (FQDN) ，從外部發佈內部主控的網站。</span><span class="sxs-lookup"><span data-stu-id="a9a66-151">should be able to publish an internally hosted web site externally by using a fully qualified domain name (FQDN).</span></span>
    
- <span data-ttu-id="a9a66-152">必須能夠發佈主控網站的所有內容。</span><span class="sxs-lookup"><span data-stu-id="a9a66-152">needs to be able to publish all the contents of your hosted web site.</span></span> <span data-ttu-id="a9a66-153">根據預設，您可以使用 **/\\** _ 指令，大多數的網頁伺服器都可以辨識此指令，以表示「在網頁伺服器上發行所有內容」。</span><span class="sxs-lookup"><span data-stu-id="a9a66-153">By default, you can use the **/\\** _ directive, which is recognized by most web servers to mean "Publish all content on the web server."</span></span> <span data-ttu-id="a9a66-154">您也可以修改此指令，例如， _*/Uwca/ \\* \*_，這表示「發行虛擬目錄 Ucwa 下的所有內容」。</span><span class="sxs-lookup"><span data-stu-id="a9a66-154">You can also modify the directive—for example, _*/Uwca/\\*\*_, which means "Publish all content under the virtual directory Ucwa."</span></span>
    
- <span data-ttu-id="a9a66-155">必須要求與用戶端的 TLS 連線，用戶端會從您發佈的網站要求內容。</span><span class="sxs-lookup"><span data-stu-id="a9a66-155">must require TLS connections with clients that request content from your published website.</span></span>
    
- <span data-ttu-id="a9a66-156">必須接受主體替代名稱 (SAN) 專案的憑證。</span><span class="sxs-lookup"><span data-stu-id="a9a66-156">has to accept certificates with subject alternative name (SAN) entries.</span></span>
    
- <span data-ttu-id="a9a66-157">必須能夠允許將憑證系結至攔截器或介面，以供外部 web 服務 FQDN 解析。</span><span class="sxs-lookup"><span data-stu-id="a9a66-157">needs to be able to allow the binding of a certificate to a listener or interface through which the external web services FQDN will resolve.</span></span> <span data-ttu-id="a9a66-158">監聽器設定優於介面。</span><span class="sxs-lookup"><span data-stu-id="a9a66-158">Listener configurations are preferable to interfaces.</span></span> <span data-ttu-id="a9a66-159">在單一介面上可以設定許多監聽器。</span><span class="sxs-lookup"><span data-stu-id="a9a66-159">Many listeners can be configured on a single interface.</span></span>
    
- <span data-ttu-id="a9a66-160">必須允許設定主機標頭處理。</span><span class="sxs-lookup"><span data-stu-id="a9a66-160">must allow for the configuration of host header handling.</span></span> <span data-ttu-id="a9a66-161">通常會以透明的方式傳遞要求用戶端所傳送的原始主機標頭，而不是反向 proxy 進行修改。</span><span class="sxs-lookup"><span data-stu-id="a9a66-161">Often, the original host header sent by the requesting client must be passed transparently, instead of being modified by the reverse proxy.</span></span>
    
- <span data-ttu-id="a9a66-162">應該允許從一個外部定義的埠橋接 TLS 流量 (例如，TCP 443) 至另一個已定義的埠 (例如，TCP 4443) 。</span><span class="sxs-lookup"><span data-stu-id="a9a66-162">should allow bridging of TLS traffic from one externally defined port (for example, TCP 443) to another defined port (for example, TCP 4443).</span></span> <span data-ttu-id="a9a66-163">您的反向 proxy 可能會在接收時解密封包，然後在傳送時重新加密封包。</span><span class="sxs-lookup"><span data-stu-id="a9a66-163">Your reverse proxy may decrypt the packet on receipt and then reencrypt the packet on sending.</span></span>
    
- <span data-ttu-id="a9a66-164">應該允許從一個埠 (橋接未加密的 TCP 流量例如，TCP 80) 到另一個 (（例如，TCP 8080) ）。</span><span class="sxs-lookup"><span data-stu-id="a9a66-164">should allow bridging of unencrypted TCP traffic from one port (for example, TCP 80) to another (for example, TCP 8080).</span></span>
    
- <span data-ttu-id="a9a66-165">需要允許設定或接受 NTLM 驗證、沒有驗證，以及透過驗證。</span><span class="sxs-lookup"><span data-stu-id="a9a66-165">needs to allow configuration of, or accept, NTLM authentication, no authentication, and pass-through authentication.</span></span>
    
<span data-ttu-id="a9a66-166">如果您的反向 proxy 可以解決此清單中的所有需求，您應該可以走好，但請在上述連結中記住我們的建議。</span><span class="sxs-lookup"><span data-stu-id="a9a66-166">If your reverse proxy can address all the needs in this list, you should be good to go, but please keep in mind our recommendations at the link provided above.</span></span>
  
### <a name="firewalls"></a><span data-ttu-id="a9a66-167">防火牆</span><span class="sxs-lookup"><span data-stu-id="a9a66-167">Firewalls</span></span>
<span data-ttu-id="a9a66-168"><a name="Firewalls"> </a></span><span class="sxs-lookup"><span data-stu-id="a9a66-168"><a name="Firewalls"> </a></span></span>

<span data-ttu-id="a9a66-169">您必須將 Edge 部署置於外部防火牆背後，但建議您在 Edge 環境和您的內部環境之間有兩個防火牆，一個外部的防火牆，一個內部的防火牆。</span><span class="sxs-lookup"><span data-stu-id="a9a66-169">You need to put your Edge deployment behind an external firewall, but we recommend having two firewalls, one external, and one internal between the Edge environment and your internal environment.</span></span> <span data-ttu-id="a9a66-170">我們案例中的所有檔都有兩個防火牆。</span><span class="sxs-lookup"><span data-stu-id="a9a66-170">All our documentation in our Scenarios will have two firewalls.</span></span> <span data-ttu-id="a9a66-171">我們建議兩個防火牆，因為它可確保從一個網路 edge 嚴格地路由傳送到另一個，並將內部網路的防火牆保護加倍。</span><span class="sxs-lookup"><span data-stu-id="a9a66-171">We recommend two firewalls because it ensures strict routing from one network edge to the other, and doubles the firewall protection for your internal network.</span></span>
  
### <a name="directors"></a><span data-ttu-id="a9a66-172">董事</span><span class="sxs-lookup"><span data-stu-id="a9a66-172">Directors</span></span>
<span data-ttu-id="a9a66-173"><a name="Directors"> </a></span><span class="sxs-lookup"><span data-stu-id="a9a66-173"><a name="Directors"> </a></span></span>

<span data-ttu-id="a9a66-174">這是選用的角色。</span><span class="sxs-lookup"><span data-stu-id="a9a66-174">This is an optional role.</span></span> <span data-ttu-id="a9a66-175">它可以是單一伺服器或執行 Director 角色之伺服器的集區。</span><span class="sxs-lookup"><span data-stu-id="a9a66-175">It can be a single server or a pool of servers running the Director role.</span></span> <span data-ttu-id="a9a66-176">這是在內部商務用 Skype 伺服器環境中找到的角色。</span><span class="sxs-lookup"><span data-stu-id="a9a66-176">It's a role found on the internal Skype for Business Server environment.</span></span>
  
<span data-ttu-id="a9a66-177">Director 是一個內部的下一個躍點伺服器，可從目的地為商務用 Skype 伺服器內部伺服器的 Edge server 接收輸入 SIP 流量。</span><span class="sxs-lookup"><span data-stu-id="a9a66-177">The Director is an internal next hop server which receives inbound SIP traffic from the Edge Servers that's destined for Skype for Business Server internal servers.</span></span> <span data-ttu-id="a9a66-178">它會 preauthenticates 輸入要求並將其重新導向至使用者的主集區或伺服器。</span><span class="sxs-lookup"><span data-stu-id="a9a66-178">It preauthenticates inbound requests and redirects them to a user's home pool or server.</span></span> <span data-ttu-id="a9a66-179">這種預驗證可讓您丟棄未識別的使用者帳戶要求。</span><span class="sxs-lookup"><span data-stu-id="a9a66-179">This preauthentication allows you to drop unidentified user account requests.</span></span>
  
<span data-ttu-id="a9a66-180">為何這麼做？</span><span class="sxs-lookup"><span data-stu-id="a9a66-180">Why does that matter?</span></span> <span data-ttu-id="a9a66-181">Director 的一個重要功能是保護 Standard Edition server 和前端伺服器或前端集區免受惡意流量（例如拒絕服務 (DoS) 攻擊）。</span><span class="sxs-lookup"><span data-stu-id="a9a66-181">An important function for a Director is to protect Standard Edition servers and Front End Servers or Front End pools from malicious traffic, such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="a9a66-182">如果您的網路因外部流量無效而淹沒，則流量會停止在 Director 上。</span><span class="sxs-lookup"><span data-stu-id="a9a66-182">If your network is flooded with invalid external traffic, the traffic stops at the Director.</span></span>
  
### <a name="load-balancers"></a><span data-ttu-id="a9a66-183">負載平衡器</span><span class="sxs-lookup"><span data-stu-id="a9a66-183">Load Balancers</span></span>
<span data-ttu-id="a9a66-184"><a name="LoadBalancers"> </a></span><span class="sxs-lookup"><span data-stu-id="a9a66-184"><a name="LoadBalancers"> </a></span></span>

<span data-ttu-id="a9a66-185">商務用 Skype 伺服器調整式合併 Edge 拓撲已針對新部署的 DNS 負載平衡進行優化，我們建議這樣做。</span><span class="sxs-lookup"><span data-stu-id="a9a66-185">The Skype for Business Server scaled consolidated Edge topology is optimized for DNS load balancing for new deployments, and we recommend this.</span></span> <span data-ttu-id="a9a66-186">如果您需要高可用性，建議使用硬體負載平衡器以取得一個特定狀況：</span><span class="sxs-lookup"><span data-stu-id="a9a66-186">If you need high availability, we recommend using a hardware load balancer for one specific situation:</span></span>
  
- <span data-ttu-id="a9a66-187">Exchange UM （適用于使用 Exchange *um _ 的* 遠端使用者）在 exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="a9a66-187">Exchange UM for remote users using Exchange UM _ *prior*\* to Exchange 2013.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="a9a66-188">請務必注意，您不能混合負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="a9a66-188">It's vital to note that you can't mix load-balancers.</span></span> <span data-ttu-id="a9a66-189">在商務用 Skype 伺服器環境中，所有介面都必須使用 DNS 或 HLB。</span><span class="sxs-lookup"><span data-stu-id="a9a66-189">In your Skype for Business Server environment all interfaces must use either DNS or HLB.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a9a66-190">Direct server 回郵 (DSR) NAT 不支援商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="a9a66-190">Direct server return (DSR) NAT isn't supported for Skype for Business Server.</span></span> 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="a9a66-191">執行 A/V Edge service 之 Edge Server Edge Server 的硬體負載平衡器需求</span><span class="sxs-lookup"><span data-stu-id="a9a66-191">hardware load balancer requirements for Edge Servers Edge Servers running the A/V Edge service</span></span>

<span data-ttu-id="a9a66-192">針對執行 A/V Edge service 的任何 Edge Server，這些需求如下：</span><span class="sxs-lookup"><span data-stu-id="a9a66-192">For any Edge Server running the A/V Edge service, these are the requirements:</span></span>
  
- <span data-ttu-id="a9a66-193">關閉內部及外部埠 443 (的 TCP Nagling。 Nagling 是將數個小型封包合併成單一較大的封包的程式，以獲得更有效率的傳輸) 。</span><span class="sxs-lookup"><span data-stu-id="a9a66-193">Turn off TCP nagling for both internal and external ports 443 (nagling is the process of combining several small packets into a single, larger packet for more efficient transmission).</span></span>
    
- <span data-ttu-id="a9a66-194">關閉外部埠範圍 50000-59999 的 TCP Nagling。</span><span class="sxs-lookup"><span data-stu-id="a9a66-194">Turn off TCP nagling for the external port range 50000 - 59999.</span></span>
    
- <span data-ttu-id="a9a66-195">請勿在您的內部或外部防火牆上使用 NAT。</span><span class="sxs-lookup"><span data-stu-id="a9a66-195">Don't use NAT on your internal or external firewalls.</span></span>
    
- <span data-ttu-id="a9a66-196">您的 Edge 內部介面必須位於與 Edge Server 外部介面不同的網路上，而且必須停用兩者之間的路由。</span><span class="sxs-lookup"><span data-stu-id="a9a66-196">Your Edge internal interface must be on a different network than your Edge Server external interface, and routing between them must be disabled.</span></span>
    
- <span data-ttu-id="a9a66-197">任何執行 A/V Edge service 之 Edge Server 的外部介面，都必須使用可公開路由傳送的 IP 位址，而且任何 Edge 外部 IP 位址上都沒有 NAT 或埠轉譯。</span><span class="sxs-lookup"><span data-stu-id="a9a66-197">The external interface of any Edge Server running the A/V Edge service must use publicly routable IP addresses and no NAT or port translation on any of the Edge external IP addresses.</span></span>
    
#### <a name="hlb-requirements"></a><span data-ttu-id="a9a66-198">HLB 需求</span><span class="sxs-lookup"><span data-stu-id="a9a66-198">HLB requirements</span></span>

<span data-ttu-id="a9a66-199">商務用 Skype 伺服器沒有許多 cookie 的關聯性需求。</span><span class="sxs-lookup"><span data-stu-id="a9a66-199">Skype for Business Server doesn't have a lot of cookie-based affinity requirements.</span></span> <span data-ttu-id="a9a66-200">因此，您不需要使用 cookie 型暫留， **除非** (，而且這是商務用 skype server 2015 特有的) 您將在商務用 skype server 環境中有 Lync Server 2010 前端伺服器或前端集區。</span><span class="sxs-lookup"><span data-stu-id="a9a66-200">So you don't need to use a cookie-based persistence **unless** (and this is Skype for Business Server 2015-specific) you're going to have Lync Server 2010 Front End Servers or Front End pools in your Skype for Business Server environment.</span></span> <span data-ttu-id="a9a66-201">在 Lync Server 2010 的設定方法中，將需要以 cookie 為基礎的關聯性。</span><span class="sxs-lookup"><span data-stu-id="a9a66-201">They would need cookie-based affinity in the configuration method recommended for Lync Server 2010.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a9a66-202">如果您決定為您的 HLB 開啟 cookie 基礎的親近性，即使您的環境不需要，也不會發生問題。</span><span class="sxs-lookup"><span data-stu-id="a9a66-202">If you decide to turn cookie-based affinity on for your HLB, there won't be a problem doing so, even if your environment doesn't need it.</span></span> 
  
<span data-ttu-id="a9a66-203">如果您的環境 **不** 需要以 cookie 為基礎的相似性：</span><span class="sxs-lookup"><span data-stu-id="a9a66-203">If your environment **doesn't** need cookie-based affinity:</span></span>
  
- <span data-ttu-id="a9a66-204">在埠443的反向 proxy 發行規則上，將 [ **轉寄主機標頭** ] 設定為 **True**。</span><span class="sxs-lookup"><span data-stu-id="a9a66-204">On the reverse proxy publishing rule for port 443, set **Forward host header** to **True**.</span></span> <span data-ttu-id="a9a66-205">這可確保原始 URL 已轉寄。</span><span class="sxs-lookup"><span data-stu-id="a9a66-205">This will ensure the original URL is forwarded.</span></span>
    
<span data-ttu-id="a9a66-206">針對需要以 cookie 為基礎之 **相似性的部署** ：</span><span class="sxs-lookup"><span data-stu-id="a9a66-206">For deployments that **do** need cookie-based affinity:</span></span>
  
- <span data-ttu-id="a9a66-207">在埠443的反向 proxy 發行規則上，將 [ **轉寄主機標頭** ] 設定為 **True**。</span><span class="sxs-lookup"><span data-stu-id="a9a66-207">On the reverse proxy publishing rule for port 443, set **Forward host header** to **True**.</span></span> <span data-ttu-id="a9a66-208">這可確保原始 URL 已轉寄。</span><span class="sxs-lookup"><span data-stu-id="a9a66-208">This will ensure the original URL is forwarded.</span></span>
    
- <span data-ttu-id="a9a66-209">硬體負載平衡器 cookie **不得** 標示為 HTTPOnly。</span><span class="sxs-lookup"><span data-stu-id="a9a66-209">The hardware load balancer cookie **must not** be marked httpOnly.</span></span>
    
- <span data-ttu-id="a9a66-210">硬體負載平衡器 cookie **不得** 具有到期時間。</span><span class="sxs-lookup"><span data-stu-id="a9a66-210">The hardware load balancer cookie **must not** have an expiration time.</span></span>
    
- <span data-ttu-id="a9a66-211">硬體負載平衡器 cookie **必須** 命名為 **MS-WSMAN** (這是 Web 服務預期的值，而且無法變更) 。</span><span class="sxs-lookup"><span data-stu-id="a9a66-211">The hardware load balancer cookie **must** be named **MS-WSMAN** (this is the value that the Web services expect, and it can't be changed).</span></span>
    
- <span data-ttu-id="a9a66-212">您 **必須** 在每個傳入的 HTTP 要求沒有 COOKIE 的 HTTP 回應中設定硬體負載平衡器 cookie，不論相同 TCP 連線上先前的 HTTP 回應是否已取得 cookie。</span><span class="sxs-lookup"><span data-stu-id="a9a66-212">The hardware load balancer cookie **must** be set in every HTTP response for which the incoming HTTP request didn't have a cookie, regardless of whether a previous HTTP response on that same TCP connection had gotten a cookie.</span></span> <span data-ttu-id="a9a66-213">如果您的硬體負載平衡器優化 cookie 插入只會在每個 TCP 連線時發生一次，則 **不得** 使用該優化。</span><span class="sxs-lookup"><span data-stu-id="a9a66-213">If your hardware load balancer optimizes cookie insert to only occur once per TCP connection, that optimization **must not** be used.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a9a66-214">對於商務用 Skype 伺服器及其用戶端，HLB 設定使用來源-親近性和20分鐘的 TCP 會話存留時間，因為會話狀態是透過用戶端使用狀況和/或應用程式互動來維護的，所以很正常。</span><span class="sxs-lookup"><span data-stu-id="a9a66-214">It's typical for HLB configurations to use source-affinity and 20 minute TCP session lifetime, which is fine for Skype for Business Server and its clients, because session state is maintained through client usage, and/or application interaction.</span></span> 
  
<span data-ttu-id="a9a66-215">如果您要部署行動裝置，HLB 必須能夠在 TCP 會話內負載平衡個別的要求 (實際上，您必須能夠根據目標 IP 位址) ，對個別要求進行負載平衡。</span><span class="sxs-lookup"><span data-stu-id="a9a66-215">If you're deploying mobile devices, your HLB must be able to load balance individual requests within a TCP session (in effect, you need to be able to load balance an individual request based on the target IP address).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a9a66-216">F5 HLBs 具有一個稱為 OneConnect 的功能。</span><span class="sxs-lookup"><span data-stu-id="a9a66-216">F5 HLBs have a feature called OneConnect.</span></span> <span data-ttu-id="a9a66-217">它可確保針對 TCP 連線中的每個要求進行個別的負載平衡。</span><span class="sxs-lookup"><span data-stu-id="a9a66-217">It ensures that each request within a TCP connection is individually load balanced.</span></span> <span data-ttu-id="a9a66-218">如果您要部署行動裝置，請確定您的 HLB 廠商支援相同的功能。</span><span class="sxs-lookup"><span data-stu-id="a9a66-218">If you're deploying mobile devices, ensure your HLB vendor supports the same functionality.</span></span> <span data-ttu-id="a9a66-219">最新的 iOS 行動裝置應用程式需要 TLS 版本1.2。</span><span class="sxs-lookup"><span data-stu-id="a9a66-219">The latest iOS mobile apps require TLS version 1.2.</span></span> <span data-ttu-id="a9a66-220">如果您需要深入瞭解，按 F5 會為此提供特定設定。</span><span class="sxs-lookup"><span data-stu-id="a9a66-220">If you need to know more, F5 provides specific settings for this.</span></span> 
  
<span data-ttu-id="a9a66-221">以下是 (選用) Director 的 HLB 需求，以及 (必要的) 前端集區 Web 服務：</span><span class="sxs-lookup"><span data-stu-id="a9a66-221">Here are the HLB requirements for the (optional) Director and (required) Front End pool Web Services:</span></span>
  
- <span data-ttu-id="a9a66-222">針對您的內部 Web 服務 VIPs，請在 HLB 上設定 (內部埠80，443) 的 Source_addr 持續性。</span><span class="sxs-lookup"><span data-stu-id="a9a66-222">For your internal Web Services VIPs, set Source_addr persistence (internal port 80, 443) on your HLB.</span></span> <span data-ttu-id="a9a66-223">若為商務用 Skype Server，Source_addr 持續性表示來自單一 IP 位址的多個連線，永遠會傳送至一部伺服器，以維護會話狀態。</span><span class="sxs-lookup"><span data-stu-id="a9a66-223">For Skype for Business Server, Source_addr persistence means that multiple connections coming from a single IP address are always sent to one server, to maintain session state.</span></span>
    
- <span data-ttu-id="a9a66-224">使用的 TCP 閒置超時為1800秒。</span><span class="sxs-lookup"><span data-stu-id="a9a66-224">Use a TCP idle timeout of 1800 seconds.</span></span>
    
- <span data-ttu-id="a9a66-225">在反向 proxy 與下一個躍點集區 HLB 之間的防火牆上，建立規則以允許埠4443上的 HTTPs：流量，從反向 proxy 到您的 HLB。</span><span class="sxs-lookup"><span data-stu-id="a9a66-225">On the firewall between your reverse proxy and your next hop pool's HLB, create a rule to allow https: traffic on port 4443, from your reverse proxy to your HLB.</span></span> <span data-ttu-id="a9a66-226">您的 HLB 需要設定為接聽埠80、443及4443。</span><span class="sxs-lookup"><span data-stu-id="a9a66-226">Your HLB needs to be configured to listen on ports 80, 443, and 4443.</span></span>
    
#### <a name="summary-of-hlb-affinity-requirements"></a><span data-ttu-id="a9a66-227">HLB 相關性需求摘要</span><span class="sxs-lookup"><span data-stu-id="a9a66-227">Summary of HLB affinity requirements</span></span>

|<span data-ttu-id="a9a66-228">**用戶端/使用者位置**</span><span class="sxs-lookup"><span data-stu-id="a9a66-228">**Client/user location**</span></span>|<span data-ttu-id="a9a66-229">**外部 Web 服務 FQDN 相似性需求**</span><span class="sxs-lookup"><span data-stu-id="a9a66-229">**External web services FQDN affinity requirements**</span></span>|<span data-ttu-id="a9a66-230">**內部 web 服務 FQSN 關聯性需求**</span><span class="sxs-lookup"><span data-stu-id="a9a66-230">**Internal web services FQSN affinity requirements**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a9a66-231">商務用 Skype Web App (內部及外部使用者) </span><span class="sxs-lookup"><span data-stu-id="a9a66-231">Skype for Business Web App (internal and external users)</span></span>  <br/> <span data-ttu-id="a9a66-232">行動裝置 (內部及外部使用者</span><span class="sxs-lookup"><span data-stu-id="a9a66-232">Mobile device (internal and external users</span></span>  <br/> |<span data-ttu-id="a9a66-233">無相似性</span><span class="sxs-lookup"><span data-stu-id="a9a66-233">No affinity</span></span>  <br/> |<span data-ttu-id="a9a66-234">來源位址相似性</span><span class="sxs-lookup"><span data-stu-id="a9a66-234">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="a9a66-235">商務用 Skype Web App (僅限外部使用者) </span><span class="sxs-lookup"><span data-stu-id="a9a66-235">Skype for Business Web App (external users only)</span></span>  <br/> <span data-ttu-id="a9a66-236">行動裝置 (內部及外部使用者</span><span class="sxs-lookup"><span data-stu-id="a9a66-236">Mobile device (internal and external users</span></span>  <br/> |<span data-ttu-id="a9a66-237">無相似性</span><span class="sxs-lookup"><span data-stu-id="a9a66-237">No affinity</span></span>  <br/> |<span data-ttu-id="a9a66-238">來源位址相似性</span><span class="sxs-lookup"><span data-stu-id="a9a66-238">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="a9a66-239">僅限內部使用者 (商務用 Skype Web App) </span><span class="sxs-lookup"><span data-stu-id="a9a66-239">Skype for Business Web App (internal users only)</span></span>  <br/> <span data-ttu-id="a9a66-240">行動裝置 (未部署)</span><span class="sxs-lookup"><span data-stu-id="a9a66-240">Mobile device (not deployed)</span></span>  <br/> |<span data-ttu-id="a9a66-241">無相似性</span><span class="sxs-lookup"><span data-stu-id="a9a66-241">No affinity</span></span>  <br/> |<span data-ttu-id="a9a66-242">來源位址相似性</span><span class="sxs-lookup"><span data-stu-id="a9a66-242">Source address affinity</span></span>  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a><span data-ttu-id="a9a66-243">HLBs 的埠監視</span><span class="sxs-lookup"><span data-stu-id="a9a66-243">Port monitoring for HLBs</span></span>

<span data-ttu-id="a9a66-244">您可以在硬體負載平衡器上定義埠監視，以決定何時不再提供特定服務，因為硬體或通訊失敗。</span><span class="sxs-lookup"><span data-stu-id="a9a66-244">You define port monitoring on your hardware load balancers to determine when specific services are no longer available, due to hardware or communications failure.</span></span> <span data-ttu-id="a9a66-245">例如，如果前端伺服器服務 (RTCSRV) 停止，因為前端伺服器或前端集區失敗，則 HLB 監視也應停止接收 Web 服務的流量。</span><span class="sxs-lookup"><span data-stu-id="a9a66-245">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="a9a66-246">您應該在 HLB 上執行埠監視，以監視下列 HLB 外部介面：</span><span class="sxs-lookup"><span data-stu-id="a9a66-246">You should implement port monitoring on the HLB to monitor the following for your HLB external interface:</span></span>
  
|<span data-ttu-id="a9a66-247">**虛擬 IP/連接埠**</span><span class="sxs-lookup"><span data-stu-id="a9a66-247">**Virtual IP/Port**</span></span>|<span data-ttu-id="a9a66-248">**節點連接埠**</span><span class="sxs-lookup"><span data-stu-id="a9a66-248">**Node Port**</span></span>|<span data-ttu-id="a9a66-249">**節點電腦/監視器**</span><span class="sxs-lookup"><span data-stu-id="a9a66-249">**Node Machine/Monitor**</span></span>|<span data-ttu-id="a9a66-250">**持續性設定檔**</span><span class="sxs-lookup"><span data-stu-id="a9a66-250">**Persistence Profile**</span></span>|<span data-ttu-id="a9a66-251">**附註**</span><span class="sxs-lookup"><span data-stu-id="a9a66-251">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a9a66-252">\<pool\>web_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="a9a66-252">\<pool\>web_mco_443_vs</span></span>  <br/> <span data-ttu-id="a9a66-253">443</span><span class="sxs-lookup"><span data-stu-id="a9a66-253">443</span></span>  <br/> |<span data-ttu-id="a9a66-254">4443</span><span class="sxs-lookup"><span data-stu-id="a9a66-254">4443</span></span>  <br/> |<span data-ttu-id="a9a66-255">前端</span><span class="sxs-lookup"><span data-stu-id="a9a66-255">Front End</span></span>  <br/> <span data-ttu-id="a9a66-256">5061</span><span class="sxs-lookup"><span data-stu-id="a9a66-256">5061</span></span>  <br/> |<span data-ttu-id="a9a66-257">無</span><span class="sxs-lookup"><span data-stu-id="a9a66-257">None</span></span>  <br/> |<span data-ttu-id="a9a66-258">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="a9a66-258">HTTPS</span></span>  <br/> |
|<span data-ttu-id="a9a66-259">\<pool\>web_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="a9a66-259">\<pool\>web_mco_80_vs</span></span>  <br/> <span data-ttu-id="a9a66-260">80</span><span class="sxs-lookup"><span data-stu-id="a9a66-260">80</span></span>  <br/> |<span data-ttu-id="a9a66-261">8080</span><span class="sxs-lookup"><span data-stu-id="a9a66-261">8080</span></span>  <br/> |<span data-ttu-id="a9a66-262">前端</span><span class="sxs-lookup"><span data-stu-id="a9a66-262">Front End</span></span>  <br/> <span data-ttu-id="a9a66-263">5061</span><span class="sxs-lookup"><span data-stu-id="a9a66-263">5061</span></span>  <br/> |<span data-ttu-id="a9a66-264">無</span><span class="sxs-lookup"><span data-stu-id="a9a66-264">None</span></span>  <br/> |<span data-ttu-id="a9a66-265">HTTP:</span><span class="sxs-lookup"><span data-stu-id="a9a66-265">HTTP</span></span>  <br/> |
   
## <a name="hardware-and-software-requirements"></a><span data-ttu-id="a9a66-266">硬體及軟體需求</span><span class="sxs-lookup"><span data-stu-id="a9a66-266">Hardware and software requirements</span></span>

<span data-ttu-id="a9a66-267">我們已在商務用 skype server 2015 的整體 [伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) 和  [商務用 skype server 2019 檔的系統需求](../../../SfBServer2019/plan/system-requirements.md) 中，涵蓋了 Edge server 的硬體和軟體需求。</span><span class="sxs-lookup"><span data-stu-id="a9a66-267">We've covered Edge Server hardware and software requirements in our overall [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and  [System requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) documentation.</span></span>
  
## <a name="collocation"></a><span data-ttu-id="a9a66-268">搭配</span><span class="sxs-lookup"><span data-stu-id="a9a66-268">Collocation</span></span>

<span data-ttu-id="a9a66-269">我們已在我們的《商務用 [Skype server 檔」的拓撲基礎](../../plan-your-deployment/topology-basics/topology-basics.md) 上涵蓋 Edge server 組合。</span><span class="sxs-lookup"><span data-stu-id="a9a66-269">We've covered Edge Server collocation in our [Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md) documentation.</span></span>
  

