---
title: Lync Server 2013：行動的技術需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for mobility
ms:assetid: 831be681-4de0-4e42-b04f-8879ca4dcd23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690030(v=OCS.15)
ms:contentKeyID: 48184679
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8df94773a551ee503ac435af8f31d0104dc38aa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536140"
---
# <a name="technical-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="9259a-102">Lync Server 2013 中行動的技術需求</span><span class="sxs-lookup"><span data-stu-id="9259a-102">Technical requirements for mobility in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9259a-103">_**主題上次修改日期：** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="9259a-103">_**Topic Last Modified:** 2014-07-24_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="9259a-104">行動使用者會遇到各種需要特別規劃的行動應用程式案例。</span><span class="sxs-lookup"><span data-stu-id="9259a-104">Mobile users encounter various mobile application scenarios that require special planning.</span></span> <span data-ttu-id="9259a-105">例如，在工作到達時，某人可能會開始使用行動應用程式，而不是工作，而是透過3G 網路來切換至公司 Wi-Fi 網路，然後在離開大樓時切換回3G。</span><span class="sxs-lookup"><span data-stu-id="9259a-105">For example, someone might start using a mobile application while away from work by connecting through the 3G network, then switch to the corporate Wi-Fi network when arriving at work, and then switch back to 3G when leaving the building.</span></span> <span data-ttu-id="9259a-106">您需要規劃環境來支援像這樣的網路轉換，以確保一致的使用者經驗。</span><span class="sxs-lookup"><span data-stu-id="9259a-106">You need to plan your environment to support such network transitions and guarantee a consistent user experience.</span></span> <span data-ttu-id="9259a-107">本節說明您必須具備的基礎結構需求，才能支援行動裝置應用程式和自動探索行動性資源。</span><span class="sxs-lookup"><span data-stu-id="9259a-107">This section describes the infrastructure requirements that you must have in order to support mobile applications and automatic discovery of mobility resources.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9259a-108">雖然行動裝置應用程式也可以連線到其他 Lync Server 2013 服務，但必須將所有行動應用程式 web 要求傳送至相同的外部 web 功能變數名稱。 (FQDN) 只適用于 Lync Server 2013 行動性服務。</span><span class="sxs-lookup"><span data-stu-id="9259a-108">Although mobile applications can also connect to other Lync Server 2013 services, the requirement to send all mobile application web requests to the same external web fully qualified domain name (FQDN) applies only to the Lync Server 2013 Mobility Service.</span></span> <span data-ttu-id="9259a-109">其他行動服務不需要這項設定。</span><span class="sxs-lookup"><span data-stu-id="9259a-109">Other mobility services do not require this configuration.</span></span>



</div>

<span data-ttu-id="9259a-110">在硬體負載平衡器中，cookie 親近性的需求會大幅減少，而且如果您使用 lync Server 2013 傳遞的 Lync Mobile，您可以取代傳輸控制通訊協定 (TCP) 相關性。</span><span class="sxs-lookup"><span data-stu-id="9259a-110">The requirement for cookie affinity in hardware load balancers is dramatically reduced, and you substitute Transmission Control Protocol (TCP) affinity if you are using the Lync Mobile delivered with Lync Server 2013.</span></span> <span data-ttu-id="9259a-111">Cookie 親近性仍可使用，但 web 服務不再需要它。</span><span class="sxs-lookup"><span data-stu-id="9259a-111">Cookie affinity can still be used, but the web services no longer require it.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9259a-112">不管來源點為內部或外部，所有的行動服務流量都會透過反向 proxy 進行。</span><span class="sxs-lookup"><span data-stu-id="9259a-112">All Mobility Service traffic goes through the reverse proxy, regardless of where the origination point is—internal or external.</span></span> <span data-ttu-id="9259a-113">在單一反向 proxy 或反向 proxy 的伺服器陣列，或提供反向 proxy 功能的裝置中，當透過介面 egressing 內部流量，並嘗試立即在相同介面上進行入口時，可能會發生問題。</span><span class="sxs-lookup"><span data-stu-id="9259a-113">In the case of a single reverse proxy or a farm of reverse proxies, or a device that is providing the reverse proxy function, an issue can arise when the internal traffic is egressing through an interface and attempting to immediately ingress on the same interface.</span></span> <span data-ttu-id="9259a-114">這通常會導致安全性規則侵犯所謂的 TCP 封包欺騙或僅僅是哄騙。</span><span class="sxs-lookup"><span data-stu-id="9259a-114">This often leads to a Security rule violation known as TCP packet spoofing or just spoofing.</span></span> <span data-ttu-id="9259a-115">將封包或封包的內指<EM>釘住</EM> (出口和立即加入) 必須允許行動才能運作。</span><span class="sxs-lookup"><span data-stu-id="9259a-115"><EM>Hair pinning</EM> (the egress and immediate ingress of a packet or series of packets) must be allowed in order for mobility to function.</span></span> <span data-ttu-id="9259a-116">解決這個問題的一種方法是使用不同于防火牆的反向 proxy， (應一定要在防火牆上強制執行哄騙防護規則，以供安全性考慮) 。</span><span class="sxs-lookup"><span data-stu-id="9259a-116">One way to resolve this issue is to use a reverse proxy that is separate from the firewall (the spoofing prevention rule should always be enforced at the firewall, for security purposes).</span></span> <span data-ttu-id="9259a-117">髮夾可以出現在反向 proxy 的外部介面，而不是防火牆外部介面。</span><span class="sxs-lookup"><span data-stu-id="9259a-117">The hairpin can occur at the external interface of the reverse proxy instead of the firewall external interface.</span></span> <span data-ttu-id="9259a-118">您偵測到防火牆上的哄騙，並放鬆反向 proxy 的規則，因此允許行動需要的髮夾。</span><span class="sxs-lookup"><span data-stu-id="9259a-118">You detect the spoofing at the firewall, and relax the rule at the reverse proxy, thereby allowing the hairpin that mobility requires.</span></span><BR><span data-ttu-id="9259a-119">使用網域名稱系統 (DNS) 主機或 CNAME 記錄來定義髮夾行為的反向 proxy (非防火牆) （若有的話）。</span><span class="sxs-lookup"><span data-stu-id="9259a-119">Use the Domain Name System (DNS) host or CNAME records to define the reverse proxy for the hairpin behavior (not the firewall), if at all possible.</span></span>



</div>

<span data-ttu-id="9259a-120">Lync Server 2013 支援 Lync 2010 Mobile 和 Lync 2013 行動用戶端的行動服務。</span><span class="sxs-lookup"><span data-stu-id="9259a-120">Lync Server 2013 supports mobility services for Lync 2010 Mobile and Lync 2013 mobile clients.</span></span> <span data-ttu-id="9259a-121">這兩個用戶端都使用 Lync Server 2013 自動探索服務來尋找其行動性進入點，但是會因其所使用的行動服務而有所不同。</span><span class="sxs-lookup"><span data-stu-id="9259a-121">Both clients use the Lync Server 2013 Autodiscover Service to find its mobility entry point, but differ on which mobility service they use.</span></span> <span data-ttu-id="9259a-122">Lync 2010 Mobile 使用行動服務（稱為 *Mcx*），並以 Lync Server 2010 的累計更新引進：11月2011。</span><span class="sxs-lookup"><span data-stu-id="9259a-122">Lync 2010 Mobile uses the Mobility Service known as *Mcx*, introduced with the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="9259a-123">Lync 2013 行動用戶端使用整合通訊 Web API （或 *UCWA*）作為其行動服務提供者。</span><span class="sxs-lookup"><span data-stu-id="9259a-123">Lync 2013 mobile clients use the Unified Communications Web API, or *UCWA*, as their mobility service provider.</span></span>

<div>

## <a name="internal-and-external-dns-configuration"></a><span data-ttu-id="9259a-124">內部和外部 DNS 設定</span><span class="sxs-lookup"><span data-stu-id="9259a-124">Internal and External DNS Configuration</span></span>

<span data-ttu-id="9259a-125">「行動服務 Mcx (引進 Lync Server 2010 的累計更新（) 年11月2011日）和 UCWA (中引入的累計更新（適用于 Lync Server 2013：二月 2013) 使用 DNS 以相同的方式）。</span><span class="sxs-lookup"><span data-stu-id="9259a-125">The Mobility Services Mcx (introduced with the Cumulative Update for Lync Server 2010: November 2011) and UCWA (introduced in the Cumulative Updates for Lync Server 2013: February 2013) use DNS in the same way.</span></span>

<span data-ttu-id="9259a-126">當您使用自動探索時，行動裝置會使用 DNS 來尋找資源。</span><span class="sxs-lookup"><span data-stu-id="9259a-126">When you use Automatic Discovery, mobile devices use DNS to locate resources.</span></span> <span data-ttu-id="9259a-127">在 DNS 查閱期間，會先嘗試連線至與內部 DNS 記錄 (lyncdiscoverinternal 相關聯的 FQDN。 \<internal domain name\>) 。</span><span class="sxs-lookup"><span data-stu-id="9259a-127">During the DNS lookup, a connection is first attempted to the FQDN that is associated with the internal DNS record (lyncdiscoverinternal.\<internal domain name\>).</span></span> <span data-ttu-id="9259a-128">若使用內部 DNS 記錄無法進行連線，則會使用外部 DNS 記錄 (lyncdiscover，嘗試連線。 \<sipdomain\>) 。</span><span class="sxs-lookup"><span data-stu-id="9259a-128">If a connection cannot be made by using the internal DNS record, a connection is attempted by using the external DNS record (lyncdiscover.\<sipdomain\>).</span></span> <span data-ttu-id="9259a-129">在網路內部的行動裝置會連線至內部自動探索服務 URL，而在網路外部的行動裝置則會連線至外部自動探索服務 URL。</span><span class="sxs-lookup"><span data-stu-id="9259a-129">A mobile device that is internal to the network connects to the internal Autodiscover Service URL, and a mobile device that is external to the network connects to the external Autodiscover Service URL.</span></span> <span data-ttu-id="9259a-130">外部自動探索要求會透過反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="9259a-130">External Autodiscover requests go through the reverse proxy.</span></span> <span data-ttu-id="9259a-131">Lync Server 2013 自動探索服務會傳回使用者主集區的所有 Web 服務 URLs，包括行動性服務 (Mcx 及 UCWA) URLs。</span><span class="sxs-lookup"><span data-stu-id="9259a-131">The Lync Server 2013 Autodiscover Service returns all Web Services URLs for the user's home pool, including the Mobility Service (Mcx and UCWA) URLs.</span></span> <span data-ttu-id="9259a-132">不過，內部 Mobility Service URL 和外部 Mobility Service URL 都會與外部 Web 服務 FQDN 相關聯。</span><span class="sxs-lookup"><span data-stu-id="9259a-132">However, both the internal Mobility Service URL and the external Mobility Service URL are associated with the external Web Services FQDN.</span></span> <span data-ttu-id="9259a-133">因此，不論行動裝置在網路內部或外部，裝置都會透過反向 proxy 從外部連線到 Lync Server 2013 行動服務。</span><span class="sxs-lookup"><span data-stu-id="9259a-133">Therefore, regardless of whether a mobile device is internal or external to the network, the device always connects to the Lync Server 2013 Mobility Service externally through the reverse proxy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9259a-134">務必要瞭解您的部署可包含多個不同的命名空間，以供內部和外部使用。</span><span class="sxs-lookup"><span data-stu-id="9259a-134">It is important to understand that your deployment can consist of multiple distinct namespaces for internal and external use.</span></span> <span data-ttu-id="9259a-135">您的 SIP 功能變數名稱可能與內部部署功能變數名稱不同。</span><span class="sxs-lookup"><span data-stu-id="9259a-135">Your SIP domain name may be different than the internal deployment domain name.</span></span> <span data-ttu-id="9259a-136">例如，您的 SIP 網域可能是 <STRONG>contoso.com</STRONG>，而您的內部部署可能是 <STRONG>contoso.net</STRONG>的。</span><span class="sxs-lookup"><span data-stu-id="9259a-136">For example, your SIP domain may be <STRONG>contoso.com</STRONG>, while your internal deployment may be <STRONG>contoso.net</STRONG>.</span></span> <span data-ttu-id="9259a-137">登入 Lync Server 的使用者將會使用 SIP 功能變數名稱，例如 <STRONG>john@contoso.com</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="9259a-137">Users who log in to Lync Server will use the SIP domain name, such as <STRONG>john@contoso.com</STRONG>.</span></span> <span data-ttu-id="9259a-138">當您在拓撲產生器中 (定義為 <STRONG>外部 web 服務</STRONG>) 的外部 web 服務時，功能變數名稱和 SIP 功能變數名稱將會一致，如 DNS 中所定義。</span><span class="sxs-lookup"><span data-stu-id="9259a-138">When addressing the external web services (defined in Topology Builder as <STRONG>External web services</STRONG>), the domain name and the SIP domain name will be consistent, as defined in DNS.</span></span> <span data-ttu-id="9259a-139">當您在拓撲產生器中定義內部 web 服務 (以作為 <STRONG>內部 web 服務</STRONG>) 時，內部 web 服務的預設名稱將會是前端伺服器、前端集區、Director 或 director 集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="9259a-139">When addressing the internal Web services (defined in Topology Builder as <STRONG>Internal web services</STRONG>), the default name of the internal web services will be the FQDN of the Front End Server, Front End pool, Director, or Director pool.</span></span> <span data-ttu-id="9259a-140">您可以選擇覆寫內部 web 服務名稱。</span><span class="sxs-lookup"><span data-stu-id="9259a-140">You have the option to override the internal web services name.</span></span> <span data-ttu-id="9259a-141">您應該使用內部功能變數名稱 (，而不是 [內部 web 服務] 的 [SIP 功能變數名稱]) ，並定義 DNS 主機 A (，否則 IPv6，AAAA) 記錄會反映已覆寫的名稱。</span><span class="sxs-lookup"><span data-stu-id="9259a-141">You should use the internal domain name (and not the SIP domain name) for internal web services and define the DNS host A (or, for IPv6, AAAA) record to reflect the overridden name.</span></span> <span data-ttu-id="9259a-142">例如，預設的內部 web 服務 FQDN 可能是 <STRONG>pool01.contoso.net</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="9259a-142">For example, the default internal web services FQDN may be <STRONG>pool01.contoso.net</STRONG>.</span></span> <span data-ttu-id="9259a-143">已覆寫的內部 web 服務 FQDN 可能是 <STRONG>webpool.contoso.net</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="9259a-143">An overridden internal web services FQDN may be <STRONG>webpool.contoso.net</STRONG>.</span></span> <span data-ttu-id="9259a-144">以這種方式定義 web 服務，可協助確定服務的內部和外部位置（而非使用使用者的地點）。</span><span class="sxs-lookup"><span data-stu-id="9259a-144">Defining the web services in this way helps to ensure that the internal and external locality of the services—and not the locality of the user who is using them—is observed.</span></span><BR><span data-ttu-id="9259a-145">不過，因為 web 服務是在拓撲產生器中定義的，而且可以覆寫內部 web 服務名稱，只要產生的 web 服務名稱、驗證它的憑證，以及定義該名稱的 DNS 記錄，您就可以使用您想要的任何功能變數名稱（包括 SIP 功能變數名稱）來定義內部 web 服務。</span><span class="sxs-lookup"><span data-stu-id="9259a-145">However, because the web services are defined in Topology Builder and the internal web services name can be overridden, as long as the resulting web services name, the certificate that validates it, and the DNS records that define it, are consistent, you can define the internal web services with any domain name—including the SIP domain name—that you want.</span></span> <span data-ttu-id="9259a-146">最後，名稱為 IP 位址的解析是由 DNS 主機記錄和一致的命名空間所決定。</span><span class="sxs-lookup"><span data-stu-id="9259a-146">Ultimately, the resolution for the name to the IP address is determined by DNS host records and a consistent namespace.</span></span><BR><span data-ttu-id="9259a-147">針對本主題和範例，內部功能變數名稱是用來示範拓撲和 DNS 定義。</span><span class="sxs-lookup"><span data-stu-id="9259a-147">For the purposes of this topic and the examples, the internal domain name is used to illustrate the topology and the DNS definitions.</span></span>



</div>

<span data-ttu-id="9259a-148">下圖說明行動性服務和自動探索服務在使用內部和外部 DNS 設定時的行動應用程式 web 要求流程。</span><span class="sxs-lookup"><span data-stu-id="9259a-148">The following diagram illustrates the flow of mobile application web requests for the Mobility Service and for the Autodiscover Service when using an internal and external DNS configuration.</span></span>

<span data-ttu-id="9259a-149">**使用 AutoDiscover 的行動服務流程**</span><span class="sxs-lookup"><span data-stu-id="9259a-149">**Mobility service flow using AutoDiscover**</span></span>

<span data-ttu-id="9259a-150">![cdb96424-96f2-4abf-88d7-1d32d1010ffd](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4abf-88d7-1d32d1010ffd")</span><span class="sxs-lookup"><span data-stu-id="9259a-150">![cdb96424-96f2-4abf-88d7-1d32d1010ffd](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4abf-88d7-1d32d1010ffd")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9259a-151">此圖表說明一般 web 服務。</span><span class="sxs-lookup"><span data-stu-id="9259a-151">The diagram illustrates generic web services.</span></span> <span data-ttu-id="9259a-152">名為行動的虛擬目錄會描述行動性服務 Mcx 和/或 UCWA。</span><span class="sxs-lookup"><span data-stu-id="9259a-152">A virtual directory named Mobility depicts the Mobility services Mcx and/or UCWA.</span></span> <span data-ttu-id="9259a-153">若尚未對 Lync Server 2013 套用累計更新，請執行下列步驟：2月2013，您可能會在內部和外部 Web 服務上定義虛擬目錄 Ucwa。</span><span class="sxs-lookup"><span data-stu-id="9259a-153">If you have not applied the Cumulative Updates for Lync Server 2013: February 2013, you may or may not have the virtual directory Ucwa defined on your internal and external Web services.</span></span> <span data-ttu-id="9259a-154">您將會具備虛擬目錄自動探索，而且可能會有虛擬目錄 Mcx。</span><span class="sxs-lookup"><span data-stu-id="9259a-154">You will have a virtual directory Autodiscover, and you may have a virtual directory Mcx.</span></span><BR><span data-ttu-id="9259a-155">不管您部署的行動服務技術為何，自動探索和服務探索的運作方式都相同。</span><span class="sxs-lookup"><span data-stu-id="9259a-155">Autodiscover and the discovery of services work the same way, regardless of the mobility services technology that you have deployed.</span></span>



</div>

<span data-ttu-id="9259a-p110">如果不管是來自公司網路內部或外部行動使用者都要支援，則內部和外部 Web FQDN 都必須符合某些先決條件。此外，依據您選擇實作的功能，您可能還需要符合其他需求。</span><span class="sxs-lookup"><span data-stu-id="9259a-p110">To support mobile users from both inside and outside the corporate network, your internal and external web FQDNs must meet some prerequisites. In addition, you may need to meet other requirements, depending on the features you choose to implement:</span></span>

  - <span data-ttu-id="9259a-158">新的 DNS、CNAME 或 (主機（如果 IPv6，則為 AAAA) 記錄），以進行自動探索。</span><span class="sxs-lookup"><span data-stu-id="9259a-158">New DNS, CNAME or A (host, if IPv6, AAAA) records, for automatic discovery.</span></span>

  - <span data-ttu-id="9259a-159">新增防火牆規則（如果您想要透過您的 Wi-Fi 網路支援推播通知）。</span><span class="sxs-lookup"><span data-stu-id="9259a-159">New firewall rule, if you want to support push notifications through your Wi-Fi network.</span></span>

  - <span data-ttu-id="9259a-160">內部伺服器憑證和反向 proxy 憑證上的主體替代名稱，以進行自動探索。</span><span class="sxs-lookup"><span data-stu-id="9259a-160">Subject alternative names on internal server certificates and reverse proxy certificates, for automatic discovery.</span></span>

  - <span data-ttu-id="9259a-161">前端伺服器硬體負載平衡器設定會變更來源親近性。</span><span class="sxs-lookup"><span data-stu-id="9259a-161">Front End Server hardware load balancer configuration changes source affinity.</span></span>

<span data-ttu-id="9259a-162">您的拓撲必須符合下列需求，才能支援行動性服務和自動探索服務：</span><span class="sxs-lookup"><span data-stu-id="9259a-162">Your topology must meet the following requirements to support the Mobility Service and the Autodiscover Service:</span></span>

  - <span data-ttu-id="9259a-163">前端集區內部 web FQDN 必須與前端集區外部 web FQDN 不同。</span><span class="sxs-lookup"><span data-stu-id="9259a-163">The Front End pool internal web FQDN must be distinct from the Front End pool external web FQDN.</span></span>

  - <span data-ttu-id="9259a-164">內部 Web FQDN 必須只解析為公司網路內部，並且可以從公司網路內部存取。</span><span class="sxs-lookup"><span data-stu-id="9259a-164">The internal web FQDN must only resolve to and be accessible from inside the corporate network.</span></span>

  - <span data-ttu-id="9259a-165">外部 web FQDN 必須僅解析為且可從網際網路存取。</span><span class="sxs-lookup"><span data-stu-id="9259a-165">The external web FQDN must only resolve to and be accessible from the Internet.</span></span>

  - <span data-ttu-id="9259a-p111">針對在公司網路內部的使用者，Mobility Service URL 必須定址至外部 Web FQDN。此需求適用於 Mobility Service，並且只套用至這個 URL。</span><span class="sxs-lookup"><span data-stu-id="9259a-p111">For a user who is inside the corporate network, the Mobility Service URL must be addressed to the external web FQDN. This requirement is for the Mobility Service and applies only to this URL.</span></span>

  - <span data-ttu-id="9259a-168">對於位於公司網路外部的使用者，要求必須移至前端集區或 Director 的外部 web FQDN。</span><span class="sxs-lookup"><span data-stu-id="9259a-168">For a user who is outside the corporate network, the request must go to the external web FQDN of the Front End pool or Director.</span></span>

<span data-ttu-id="9259a-169">如果您支援自動探索，則需要為每個 SIP 網域建立下列 DNS 記錄：</span><span class="sxs-lookup"><span data-stu-id="9259a-169">If you support automatic discovery, you need to create the following DNS records for each SIP domain:</span></span>

  - <span data-ttu-id="9259a-170">內部 DNS 記錄，以支援從組織網路內部連線的行動使用者。</span><span class="sxs-lookup"><span data-stu-id="9259a-170">An internal DNS record to support mobile users who connect from within your organization's network.</span></span>

  - <span data-ttu-id="9259a-171">外部或公開的 DNS 記錄，以支援從網際網路連線的行動使用者。</span><span class="sxs-lookup"><span data-stu-id="9259a-171">An external, or public, DNS record to support mobile users who connect from the Internet.</span></span>

<span data-ttu-id="9259a-172">內部自動探索 URL 應該不能從您的網路外部定址。</span><span class="sxs-lookup"><span data-stu-id="9259a-172">The internal automatic discovery URL should not be addressable from outside your network.</span></span> <span data-ttu-id="9259a-173">外部自動探索 URL 應該不能從您的網路內部定址。</span><span class="sxs-lookup"><span data-stu-id="9259a-173">The external automatic discovery URL should not be addressable from within your network.</span></span> <span data-ttu-id="9259a-174">不過，如果您無法滿足外部 URL 的這項需求，行動用戶端功能可能不會受到影響，因為通常會先嘗試內部 URL。</span><span class="sxs-lookup"><span data-stu-id="9259a-174">However, if you cannot meet this requirement for the external URL, mobile client functionally will probably not be affected, because the internal URL is always tried first.</span></span>

<span data-ttu-id="9259a-175">DNS 記錄可以是 CNAME 記錄或 (主機，如果是 IPv6，AAAA) 記錄。</span><span class="sxs-lookup"><span data-stu-id="9259a-175">The DNS records can be either CNAME records or A (host, if IPv6, AAAA) records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9259a-176">行動裝置用戶端不支援來自不同網域的多個 Secure Sockets Layer (SSL) 憑證。</span><span class="sxs-lookup"><span data-stu-id="9259a-176">Mobile device clients do not support multiple Secure Sockets Layer (SSL) certificates from different domains.</span></span> <span data-ttu-id="9259a-177">因此，不支援透過 HTTPS 將 CNAME 重新導向至不同的網域。</span><span class="sxs-lookup"><span data-stu-id="9259a-177">Therefore, CNAME redirection to different domains is not supported over HTTPS.</span></span> <span data-ttu-id="9259a-178">例如，不支援透過 HTTPS 將 lyncdiscover.contoso.com 的 DNS CNAME 記錄重新導向至 director.contoso.net 的位址。</span><span class="sxs-lookup"><span data-stu-id="9259a-178">For example, a DNS CNAME record for lyncdiscover.contoso.com that redirects to an address of director.contoso.net is not supported over HTTPS.</span></span> <span data-ttu-id="9259a-179">在這樣的拓撲中，行動裝置用戶端需要使用 HTTP 來進行第一個要求，以透過 HTTP 來解析 CNAME 重新導向。</span><span class="sxs-lookup"><span data-stu-id="9259a-179">In such a topology, a mobile device client needs to use HTTP for the first request, so that the CNAME redirection is resolved over HTTP.</span></span> <span data-ttu-id="9259a-180">後續的要求則會使用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="9259a-180">Subsequent requests then use HTTPS.</span></span> <span data-ttu-id="9259a-181">若要支援此案例，您需要以連接埠 80 的 Web 發行規則來設定反向 Proxy (HTTP)。</span><span class="sxs-lookup"><span data-stu-id="9259a-181">To support this scenario, you need to configure your reverse proxy with a web publishing rule for port 80 (HTTP).</span></span> <span data-ttu-id="9259a-182">如需詳細資訊，請參閱在 <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013 中設定行動的反向 proxy</A>中的「為埠80建立 web 發行規則」。</span><span class="sxs-lookup"><span data-stu-id="9259a-182">For details, see "To create a web publishing rule for port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="9259a-183">支援透過 HTTPS 將 CNAME 重新導向至相同網域。</span><span class="sxs-lookup"><span data-stu-id="9259a-183">CNAME redirection to the same domain is supported over HTTPS.</span></span> <span data-ttu-id="9259a-184">在此情況下，目的網域的憑證會涵蓋原始網域。</span><span class="sxs-lookup"><span data-stu-id="9259a-184">In this case, the destination domain's certificate covers the originating domain.</span></span>



</div>

<span data-ttu-id="9259a-185">如需您案例所需之 DNS 記錄的詳細資訊，請參閱 [Lync Server 2013 中的 dns 摘要-自動](lync-server-2013-dns-summary-autodiscover.md)探索。</span><span class="sxs-lookup"><span data-stu-id="9259a-185">For details about the DNS records required for your scenario, see [DNS summary - Autodiscover in Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md).</span></span>

</div>

<div>

## <a name="port-and-firewall-requirements"></a><span data-ttu-id="9259a-186">連接埠和防火牆需求</span><span class="sxs-lookup"><span data-stu-id="9259a-186">Port and Firewall Requirements</span></span>

<span data-ttu-id="9259a-187">如果您支援推入通知，並且想要讓 Apple 行動裝置透過 Wi-Fi 網路來接收推入通知，您也需要在企業 Wi-Fi 網路上開啟連接埠 5223。</span><span class="sxs-lookup"><span data-stu-id="9259a-187">If you support push notifications and want Apple mobile devices to receive push notifications over your Wi-Fi network, you also need to open port 5223 on your enterprise Wi-Fi network.</span></span> <span data-ttu-id="9259a-188">連接埠 5223 是 Apple Push Notification Service (APNS) 使用的輸出 TCP 連接埠。</span><span class="sxs-lookup"><span data-stu-id="9259a-188">Port 5223 is an outbound TCP port used by the Apple Push Notification Service (APNS).</span></span> <span data-ttu-id="9259a-189">行動裝置會初始化連接。</span><span class="sxs-lookup"><span data-stu-id="9259a-189">The mobile device initiates the connection.</span></span> <span data-ttu-id="9259a-190">如需詳細資訊，請參閱 [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629) 。</span><span class="sxs-lookup"><span data-stu-id="9259a-190">For details, see [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629) .</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="9259a-191">使用 Lync 2013 行動用戶端的 Apple 裝置不需要推播通知。</span><span class="sxs-lookup"><span data-stu-id="9259a-191">An Apple device using the Lync 2013 Mobile client does not require push notifications.</span></span>



</div>

<span data-ttu-id="9259a-192">請注意，如果使用者位於 Survivable Branch 裝置 (SBA) 則需要下列埠：</span><span class="sxs-lookup"><span data-stu-id="9259a-192">Note that if a user is homed on a Survivable Branch Appliance (SBA) then the following ports are required:</span></span>

  - <span data-ttu-id="9259a-193">UcwaSipExternalListeningPort 需要端口5088</span><span class="sxs-lookup"><span data-stu-id="9259a-193">UcwaSipExternalListeningPort requires port 5088</span></span>

  - <span data-ttu-id="9259a-194">UcwaSipPrimaryListeningPort 需要端口5089</span><span class="sxs-lookup"><span data-stu-id="9259a-194">UcwaSipPrimaryListeningPort requires port 5089</span></span>

<span data-ttu-id="9259a-195">如需有關自動探索的埠和通訊協定需求的詳細資訊和指引，請參閱 [Lync Server 2013 中的埠摘要-自動](lync-server-2013-port-summary-autodiscover.md)探索。</span><span class="sxs-lookup"><span data-stu-id="9259a-195">For additional details and guidance on port and protocol requirements for Autodiscover, see [Port summary - Autodiscover in Lync Server 2013](lync-server-2013-port-summary-autodiscover.md).</span></span>

</div>

<div>

## <a name="certificate-requirements"></a><span data-ttu-id="9259a-196">憑證需求</span><span class="sxs-lookup"><span data-stu-id="9259a-196">Certificate Requirements</span></span>

<span data-ttu-id="9259a-197">如果您支援 Lync 行動用戶端的自動探索，則需要修改憑證上的主體替代名稱清單，以支援從行動用戶端進行安全連線。</span><span class="sxs-lookup"><span data-stu-id="9259a-197">If you support automatic discovery for Lync mobile clients, you need to modify the subject alternative name lists on certificates to support secure connections from the mobile clients.</span></span> <span data-ttu-id="9259a-198">您必須要求並指派新的憑證，針對執行自動探索服務的每個前端伺服器及 Director，新增本節中所述的主體替代名稱專案。</span><span class="sxs-lookup"><span data-stu-id="9259a-198">You need to request and assign new certificates, adding the subject alternative name entries described in this section, for each Front End Server and Director that runs the Autodiscover Service.</span></span> <span data-ttu-id="9259a-199">建議的方法是也為反向 Proxy 修改憑證上的主體替代名稱清單。</span><span class="sxs-lookup"><span data-stu-id="9259a-199">The recommended approach is to also modify the subject alternative names lists on certificates for your reverse proxies.</span></span> <span data-ttu-id="9259a-200">您需要針對組織中的每個 SIP 網域，新增主體替代名稱項目。</span><span class="sxs-lookup"><span data-stu-id="9259a-200">You need to add subject alternative name entries for every SIP domain in your organization.</span></span>

<span data-ttu-id="9259a-201">使用內部憑證授權單位重新發出憑證通常是很簡單的程序，但是新增多個主體替代名稱項目至反向 Proxy 所使用的公用憑證會很昂貴。</span><span class="sxs-lookup"><span data-stu-id="9259a-201">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="9259a-202">如果您有很多 SIP 網域，新增主體替代名稱會非常昂貴，您可以設定反向 Proxy，透過使用 HTTP 的連接埠 80 來發行初始自動探索服務要求，而不要透過使用 HTTPS 的連接埠 443 (預設值)。</span><span class="sxs-lookup"><span data-stu-id="9259a-202">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to make the initial Autodiscover Service request over port 80 using HTTP, instead of port 443 using HTTPS (the default configuration).</span></span> <span data-ttu-id="9259a-203">然後將要求重新導向至 Director 或前端集區的埠8080。</span><span class="sxs-lookup"><span data-stu-id="9259a-203">The request is then redirected to port 8080 on the Director or Front End pool.</span></span> <span data-ttu-id="9259a-204">當您在連接埠 80 上發行初始自動探索服務要求時，不需要變更反向 Proxy 的憑證，因為要求是使用 HTTP，而不是 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="9259a-204">When you publish the initial Autodiscover Service request on port 80, you do not need to change certificates for the reverse proxy, because the request uses HTTP rather than HTTPS.</span></span> <span data-ttu-id="9259a-205">這種方法是受支援的，但我們不建議您這麼做。</span><span class="sxs-lookup"><span data-stu-id="9259a-205">This approach is supported, but we do not recommend it.</span></span>

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a><span data-ttu-id="9259a-206">Internet Information Services (IIS) 需求</span><span class="sxs-lookup"><span data-stu-id="9259a-206">Internet Information Services (IIS) Requirements</span></span>

<span data-ttu-id="9259a-207">建議您使用 IIS 7.5、IIS 8.0 或 IIS 8.5 進行行動。</span><span class="sxs-lookup"><span data-stu-id="9259a-207">We recommend that you use IIS 7.5, IIS 8.0, or IIS 8.5 for mobility.</span></span> <span data-ttu-id="9259a-208">行動服務安裝程式會設定 ASP.NET 中的旗標，以提升效能。</span><span class="sxs-lookup"><span data-stu-id="9259a-208">The Mobility Service installer sets flags in ASP.NET to improve performance.</span></span> <span data-ttu-id="9259a-209">IIS 7.5 預設會在 Windows Server 2008 R2 上安裝，IIS 8.0 是安裝在 Windows Server 2012 上，而 IIS 8.5 則安裝在 Windows server 2012 R2 上。</span><span class="sxs-lookup"><span data-stu-id="9259a-209">IIS 7.5 is installed by default on Windows Server 2008 R2, IIS 8.0 is installed on Windows Server 2012, and IIS 8.5 is installed on Windows Server 2012 R2.</span></span> <span data-ttu-id="9259a-210">行動服務安裝程式會自動變更 ASP.NET 設定。</span><span class="sxs-lookup"><span data-stu-id="9259a-210">The Mobility Service installer automatically changes the ASP.NET settings.</span></span>

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="9259a-211">硬體負載平衡器需求</span><span class="sxs-lookup"><span data-stu-id="9259a-211">Hardware Load Balancer Requirements</span></span>

<span data-ttu-id="9259a-212">在支援前端集區的硬體負載平衡器上，必須為來源設定 Web 服務流量的外部 Web 服務虛擬 IPs (Vip) 。</span><span class="sxs-lookup"><span data-stu-id="9259a-212">On the hardware load balancer that is supporting the Front End pool, the external Web Services virtual IPs (VIPs) for Web Services traffic must be configured for source.</span></span> <span data-ttu-id="9259a-213">來源相關性可協助確保將單一用戶端的多個連線傳送至一部伺服器以維護會話狀態。</span><span class="sxs-lookup"><span data-stu-id="9259a-213">Source affinity helps to ensure that multiple connections from a single client are sent to one server to maintain session state.</span></span> <span data-ttu-id="9259a-214">如需關聯性需求的詳細資訊，請參閱 [Lync Server 2013 的負載平衡需求](lync-server-2013-load-balancing-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9259a-214">For details about affinity requirements, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

<span data-ttu-id="9259a-215">如果您只想要在內部 Wi-Fi 網路上支援 Lync 行動用戶端，則應該針對 [外部 Web 服務] Vip 所述，設定來源的內部 Web 服務 VIPS。</span><span class="sxs-lookup"><span data-stu-id="9259a-215">If you plan to support Lync mobile clients only over your internal Wi-Fi network, you should configure the internal Web Services VIPS for source as described for external Web Services VIPs.</span></span> <span data-ttu-id="9259a-216">在此情況下，您應該 \_ 針對硬體負載平衡器上的內部 Web 服務 vip，使用來源位址 (或 TCP) 相關性。</span><span class="sxs-lookup"><span data-stu-id="9259a-216">In this situation, you should use source\_addr (or TCP) affinity for the internal Web Services VIPs on the hardware load balancer.</span></span> <span data-ttu-id="9259a-217">如需詳細資訊，請參閱 [Lync Server 2013 的負載平衡需求](lync-server-2013-load-balancing-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9259a-217">For details, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

</div>

<div>

## <a name="reverse-proxy-requirements"></a><span data-ttu-id="9259a-218">反向 Proxy 需求</span><span class="sxs-lookup"><span data-stu-id="9259a-218">Reverse Proxy Requirements</span></span>

<span data-ttu-id="9259a-219">如果您支援 Lync 行動用戶端的自動探索，您必須更新目前的發行規則，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9259a-219">If you support automatic discovery for Lync mobile clients, you need to update the current publishing rule as follows:</span></span>

  - <span data-ttu-id="9259a-220">如果您決定更新反向 proxy 憑證上的主體替代名稱清單，並使用 HTTPS 來進行初始自動探索服務要求，您必須更新 lyncdiscover 的 web 發行 \<sipdomain\> 規則。</span><span class="sxs-lookup"><span data-stu-id="9259a-220">If you decide to update the subject alternative names lists on the reverse proxy certificates and use HTTPS for the initial Autodiscover Service request, you must update the web publishing rule for lyncdiscover.\<sipdomain\>.</span></span> <span data-ttu-id="9259a-221">一般來說，這會結合前端集區上的外部 Web 服務 URL 的發行規則。</span><span class="sxs-lookup"><span data-stu-id="9259a-221">Typically, this is combined with the publishing rule for the external Web Services URL on the Front End pool.</span></span>

  - <span data-ttu-id="9259a-222">如果您決定使用 HTTP 來進行初始自動探索服務要求，這樣就不需要更新反向 proxy 憑證上的主體替代名稱清單，您必須為 port HTTP/TCP 80 建立新的 web 發行規則（如果沒有的話）。</span><span class="sxs-lookup"><span data-stu-id="9259a-222">If you decide to use HTTP for the initial Autodiscover Service request so that you do not need to update the subject alternative names list on the reverse proxy certificates, you must create a new web publishing rule for port HTTP/TCP 80, if one does not already exist.</span></span> <span data-ttu-id="9259a-223">如果 HTTP/TCP 80 的規則已經存在，您可以將該規則更新為包含 lyncdiscover。\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="9259a-223">If a rule for HTTP/TCP 80 does already exist, you can update that rule to include the lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="9259a-224">進入。</span><span class="sxs-lookup"><span data-stu-id="9259a-224">entry.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

