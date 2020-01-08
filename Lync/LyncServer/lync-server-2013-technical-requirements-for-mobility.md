---
title: Lync Server 2013：行動技術需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for mobility
ms:assetid: 831be681-4de0-4e42-b04f-8879ca4dcd23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690030(v=OCS.15)
ms:contentKeyID: 48184679
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac74f7e9e85829e500900e03d4b7cfedf89d1e0b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="03d9c-102">Lync Server 2013 行動技術需求</span><span class="sxs-lookup"><span data-stu-id="03d9c-102">Technical requirements for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03d9c-103">_**主題上次修改日期：** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="03d9c-103">_**Topic Last Modified:** 2014-07-24_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="03d9c-104">行動使用者遇到各種需要特殊規劃的行動應用程式案例。</span><span class="sxs-lookup"><span data-stu-id="03d9c-104">Mobile users encounter various mobile application scenarios that require special planning.</span></span> <span data-ttu-id="03d9c-105">例如，某個人可能會在不在工作的情況下開始使用行動應用程式，方法是透過3G 網路連線，然後在進行工作時切換至公司 Wi-fi 網路，然後在離開建築物時切換回3G。</span><span class="sxs-lookup"><span data-stu-id="03d9c-105">For example, someone might start using a mobile application while away from work by connecting through the 3G network, then switch to the corporate Wi-Fi network when arriving at work, and then switch back to 3G when leaving the building.</span></span> <span data-ttu-id="03d9c-106">您需要規劃您的環境以支援此類網路轉換，並保證一致的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="03d9c-106">You need to plan your environment to support such network transitions and guarantee a consistent user experience.</span></span> <span data-ttu-id="03d9c-107">本節說明您必須具備哪些基礎結構需求，才能支援行動裝置應用程式及自動探索行動資源。</span><span class="sxs-lookup"><span data-stu-id="03d9c-107">This section describes the infrastructure requirements that you must have in order to support mobile applications and automatic discovery of mobility resources.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="03d9c-108">雖然行動裝置應用程式也可以連線到其他 Lync Server 2013 服務，但將所有行動應用程式的 web 要求傳送到相同的外部網站完全限定功能變數名稱（FQDN）的需求，只適用于 Lync Server 2013 行動服務。</span><span class="sxs-lookup"><span data-stu-id="03d9c-108">Although mobile applications can also connect to other Lync Server 2013 services, the requirement to send all mobile application web requests to the same external web fully qualified domain name (FQDN) applies only to the Lync Server 2013 Mobility Service.</span></span> <span data-ttu-id="03d9c-109">其他行動服務不需要此設定。</span><span class="sxs-lookup"><span data-stu-id="03d9c-109">Other mobility services do not require this configuration.</span></span>



</div>

<span data-ttu-id="03d9c-110">在硬體負載平衡器中，cookie 關聯的需求大大減少，而且如果您使用的是使用 Lync Server 2013 傳送的 Lync Mobile，就可以取代傳輸控制通訊協定（TCP）關聯性。</span><span class="sxs-lookup"><span data-stu-id="03d9c-110">The requirement for cookie affinity in hardware load balancers is dramatically reduced, and you substitute Transmission Control Protocol (TCP) affinity if you are using the Lync Mobile delivered with Lync Server 2013.</span></span> <span data-ttu-id="03d9c-111">Cookie 關聯仍可以使用，但 web 服務不再需要它。</span><span class="sxs-lookup"><span data-stu-id="03d9c-111">Cookie affinity can still be used, but the web services no longer require it.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="03d9c-112">無論來源點在哪裡（內部或外部），所有行動服務流量都會透過反向 proxy 進行。</span><span class="sxs-lookup"><span data-stu-id="03d9c-112">All Mobility Service traffic goes through the reverse proxy, regardless of where the origination point is—internal or external.</span></span> <span data-ttu-id="03d9c-113">如果是單一反向 proxy 或反向代理伺服器群，或提供反向 proxy 函式的裝置，則在透過介面 egressing 內部通信量並嘗試立即進入相同介面時，可能會發生問題。</span><span class="sxs-lookup"><span data-stu-id="03d9c-113">In the case of a single reverse proxy or a farm of reverse proxies, or a device that is providing the reverse proxy function, an issue can arise when the internal traffic is egressing through an interface and attempting to immediately ingress on the same interface.</span></span> <span data-ttu-id="03d9c-114">這通常會導致安全規則違反所謂 TCP 資料包欺騙或只是哄騙。</span><span class="sxs-lookup"><span data-stu-id="03d9c-114">This often leads to a Security rule violation known as TCP packet spoofing or just spoofing.</span></span> <span data-ttu-id="03d9c-115">若要讓行動正常運作，必須允許 [<EM>頭髮釘</EM>選] （資料包或一系列資料包的出局和直接進入）。</span><span class="sxs-lookup"><span data-stu-id="03d9c-115"><EM>Hair pinning</EM> (the egress and immediate ingress of a packet or series of packets) must be allowed in order for mobility to function.</span></span> <span data-ttu-id="03d9c-116">解決此問題的其中一個方法是使用與防火牆不同的反向 proxy （哄騙預防規則應該在防火牆上強制執行，出於安全性考慮）。</span><span class="sxs-lookup"><span data-stu-id="03d9c-116">One way to resolve this issue is to use a reverse proxy that is separate from the firewall (the spoofing prevention rule should always be enforced at the firewall, for security purposes).</span></span> <span data-ttu-id="03d9c-117">Hairpin 可以在反向 proxy 的外部介面（而非防火牆外部介面）發生。</span><span class="sxs-lookup"><span data-stu-id="03d9c-117">The hairpin can occur at the external interface of the reverse proxy instead of the firewall external interface.</span></span> <span data-ttu-id="03d9c-118">您會在防火牆上偵測欺騙，並在反向 proxy 中放寬規則，從而允許行動需要的 hairpin。</span><span class="sxs-lookup"><span data-stu-id="03d9c-118">You detect the spoofing at the firewall, and relax the rule at the reverse proxy, thereby allowing the hairpin that mobility requires.</span></span><BR><span data-ttu-id="03d9c-119">如果可能的話，請使用網域名稱系統（DNS）主機或 CNAME 記錄來定義 hairpin 行為的反向 proxy （而非防火牆）。</span><span class="sxs-lookup"><span data-stu-id="03d9c-119">Use the Domain Name System (DNS) host or CNAME records to define the reverse proxy for the hairpin behavior (not the firewall), if at all possible.</span></span>



</div>

<span data-ttu-id="03d9c-120">Lync Server 2013 支援 Lync 2010 Mobile 和 Lync 2013 行動用戶端的行動裝置服務。</span><span class="sxs-lookup"><span data-stu-id="03d9c-120">Lync Server 2013 supports mobility services for Lync 2010 Mobile and Lync 2013 mobile clients.</span></span> <span data-ttu-id="03d9c-121">兩個用戶端都使用 Lync Server 2013 自動探索服務來找出其行動進入點，但它們所使用的行動服務有所不同。</span><span class="sxs-lookup"><span data-stu-id="03d9c-121">Both clients use the Lync Server 2013 Autodiscover Service to find its mobility entry point, but differ on which mobility service they use.</span></span> <span data-ttu-id="03d9c-122">Lync 2010 Mobile 會使用行動服務（稱為*Mcx*），並在 Lync Server 2010 的累積更新：年11月2011。</span><span class="sxs-lookup"><span data-stu-id="03d9c-122">Lync 2010 Mobile uses the Mobility Service known as *Mcx*, introduced with the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="03d9c-123">Lync 2013 行動用戶端使用整合通訊 Web API （或*UCWA*）作為其行動服務提供者。</span><span class="sxs-lookup"><span data-stu-id="03d9c-123">Lync 2013 mobile clients use the Unified Communications Web API, or *UCWA*, as their mobility service provider.</span></span>

<div>

## <a name="internal-and-external-dns-configuration"></a><span data-ttu-id="03d9c-124">內部和外部 DNS 配置</span><span class="sxs-lookup"><span data-stu-id="03d9c-124">Internal and External DNS Configuration</span></span>

<span data-ttu-id="03d9c-125">行動服務 Mcx （在 Lync Server 2010：2011年11月）和 UCWA （在 Lync Server 2013 的累加更新中引入）與（在 Lync Server 2013 的累積更新中所述）以相同的方式使用 DNS。</span><span class="sxs-lookup"><span data-stu-id="03d9c-125">The Mobility Services Mcx (introduced with the Cumulative Update for Lync Server 2010: November 2011) and UCWA (introduced in the Cumulative Updates for Lync Server 2013: February 2013) use DNS in the same way.</span></span>

<span data-ttu-id="03d9c-126">當您使用自動探索時，行動裝置會使用 DNS 來找出資源。</span><span class="sxs-lookup"><span data-stu-id="03d9c-126">When you use Automatic Discovery, mobile devices use DNS to locate resources.</span></span> <span data-ttu-id="03d9c-127">在 DNS 查詢期間，先嘗試連線到與內部 DNS 記錄（lyncdiscoverinternal）相關聯的 FQDN。\<內部網功能變數名稱稱\>）。</span><span class="sxs-lookup"><span data-stu-id="03d9c-127">During the DNS lookup, a connection is first attempted to the FQDN that is associated with the internal DNS record (lyncdiscoverinternal.\<internal domain name\>).</span></span> <span data-ttu-id="03d9c-128">如果使用內部 DNS 記錄無法建立連線，則會使用外部 DNS 記錄（lyncdiscover）嘗試連線。\<sipdomain\>）。</span><span class="sxs-lookup"><span data-stu-id="03d9c-128">If a connection cannot be made by using the internal DNS record, a connection is attempted by using the external DNS record (lyncdiscover.\<sipdomain\>).</span></span> <span data-ttu-id="03d9c-129">網路內部的行動裝置會連接到內部自動探索服務 URL，而網路外部的行動裝置則會連線至外部自動探索服務 URL。</span><span class="sxs-lookup"><span data-stu-id="03d9c-129">A mobile device that is internal to the network connects to the internal Autodiscover Service URL, and a mobile device that is external to the network connects to the external Autodiscover Service URL.</span></span> <span data-ttu-id="03d9c-130">外部自動探索要求會透過反向 proxy 進行。</span><span class="sxs-lookup"><span data-stu-id="03d9c-130">External Autodiscover requests go through the reverse proxy.</span></span> <span data-ttu-id="03d9c-131">Lync Server 2013 自動探索服務會傳回使用者主區的所有 Web 服務 Url，包括行動服務（Mcx 和 UCWA） Url。</span><span class="sxs-lookup"><span data-stu-id="03d9c-131">The Lync Server 2013 Autodiscover Service returns all Web Services URLs for the user's home pool, including the Mobility Service (Mcx and UCWA) URLs.</span></span> <span data-ttu-id="03d9c-132">不過，內部行動服務 URL 與外部行動服務 URL 都與外部 Web 服務 FQDN 相關聯。</span><span class="sxs-lookup"><span data-stu-id="03d9c-132">However, both the internal Mobility Service URL and the external Mobility Service URL are associated with the external Web Services FQDN.</span></span> <span data-ttu-id="03d9c-133">因此，無論行動裝置是在網路內部或外部，裝置都必須透過反向 proxy，在外部連線到 Lync Server 2013 行動服務。</span><span class="sxs-lookup"><span data-stu-id="03d9c-133">Therefore, regardless of whether a mobile device is internal or external to the network, the device always connects to the Lync Server 2013 Mobility Service externally through the reverse proxy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="03d9c-134">請務必瞭解，您的部署可包含多個不同的命名空間來供內部和外部使用。</span><span class="sxs-lookup"><span data-stu-id="03d9c-134">It is important to understand that your deployment can consist of multiple distinct namespaces for internal and external use.</span></span> <span data-ttu-id="03d9c-135">您的 SIP 功能變數名稱可能與內部部署網域的名稱不同。</span><span class="sxs-lookup"><span data-stu-id="03d9c-135">Your SIP domain name may be different than the internal deployment domain name.</span></span> <span data-ttu-id="03d9c-136">例如，您的 SIP 網域可能是<STRONG>contoso.com</STRONG>，而您的內部部署可能是<STRONG>contoso.net</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="03d9c-136">For example, your SIP domain may be <STRONG>contoso.com</STRONG>, while your internal deployment may be <STRONG>contoso.net</STRONG>.</span></span> <span data-ttu-id="03d9c-137">登入 Lync Server 的使用者將會使用 SIP 功能變數名稱，例如<STRONG>john@contoso.com</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="03d9c-137">Users who log in to Lync Server will use the SIP domain name, such as <STRONG>john@contoso.com</STRONG>.</span></span> <span data-ttu-id="03d9c-138">當您將外部 web 服務（在拓撲建立器中定義為<STRONG>外部 web 服務</STRONG>）定址時，功能變數名稱和 SIP 功能變數名稱會保持一致，如 DNS 中所定義。</span><span class="sxs-lookup"><span data-stu-id="03d9c-138">When addressing the external web services (defined in Topology Builder as <STRONG>External web services</STRONG>), the domain name and the SIP domain name will be consistent, as defined in DNS.</span></span> <span data-ttu-id="03d9c-139">當您將內部 Web 服務（在拓撲建立器中定義為<STRONG>內部 web 服務</STRONG>）定址時，內部 web 服務的預設名稱將是前端伺服器、前端池、控制器或控制器池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="03d9c-139">When addressing the internal Web services (defined in Topology Builder as <STRONG>Internal web services</STRONG>), the default name of the internal web services will be the FQDN of the Front End Server, Front End pool, Director, or Director pool.</span></span> <span data-ttu-id="03d9c-140">您可以選擇覆寫內部 web 服務名稱。</span><span class="sxs-lookup"><span data-stu-id="03d9c-140">You have the option to override the internal web services name.</span></span> <span data-ttu-id="03d9c-141">您應該使用內部 web 服務的內部功能變數名稱（而不是 SIP 功能變數名稱），並定義 DNS 主機 A （或 IPv6、AAAA）記錄來反映覆寫的名稱。</span><span class="sxs-lookup"><span data-stu-id="03d9c-141">You should use the internal domain name (and not the SIP domain name) for internal web services and define the DNS host A (or, for IPv6, AAAA) record to reflect the overridden name.</span></span> <span data-ttu-id="03d9c-142">例如，預設的內部 web 服務 FQDN 可能是<STRONG>pool01.contoso.net</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="03d9c-142">For example, the default internal web services FQDN may be <STRONG>pool01.contoso.net</STRONG>.</span></span> <span data-ttu-id="03d9c-143">已重寫的內部 web 服務 FQDN 可能是<STRONG>webpool.contoso.net</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="03d9c-143">An overridden internal web services FQDN may be <STRONG>webpool.contoso.net</STRONG>.</span></span> <span data-ttu-id="03d9c-144">以這種方式定義 web 服務有助於確保服務的內部和外部位置（而不是使用它們的使用者所在地）是觀察到的。</span><span class="sxs-lookup"><span data-stu-id="03d9c-144">Defining the web services in this way helps to ensure that the internal and external locality of the services—and not the locality of the user who is using them—is observed.</span></span><BR><span data-ttu-id="03d9c-145">不過，因為 web 服務是在拓撲建立器中定義的，而且內部 web 服務名稱可以覆寫，只要產生的 web 服務名稱、驗證它的憑證，以及定義它的 DNS 記錄，就會是一致的，您可以定義包含您想要的任何功能變數名稱（包括 SIP 功能變數名稱）的內部 web 服務。</span><span class="sxs-lookup"><span data-stu-id="03d9c-145">However, because the web services are defined in Topology Builder and the internal web services name can be overridden, as long as the resulting web services name, the certificate that validates it, and the DNS records that define it, are consistent, you can define the internal web services with any domain name—including the SIP domain name—that you want.</span></span> <span data-ttu-id="03d9c-146">最後，名稱對 IP 位址的解析是由 DNS 主機記錄和一致的命名空間決定。</span><span class="sxs-lookup"><span data-stu-id="03d9c-146">Ultimately, the resolution for the name to the IP address is determined by DNS host records and a consistent namespace.</span></span><BR><span data-ttu-id="03d9c-147">針對本主題和範例，內部功能變數名稱是用來說明拓撲與 DNS 定義。</span><span class="sxs-lookup"><span data-stu-id="03d9c-147">For the purposes of this topic and the examples, the internal domain name is used to illustrate the topology and the DNS definitions.</span></span>



</div>

<span data-ttu-id="03d9c-148">下圖說明行動裝置應用程式在使用內部和外部 DNS 設定時，針對行動服務和自動探索服務的流程 web 要求流程。</span><span class="sxs-lookup"><span data-stu-id="03d9c-148">The following diagram illustrates the flow of mobile application web requests for the Mobility Service and for the Autodiscover Service when using an internal and external DNS configuration.</span></span>

<span data-ttu-id="03d9c-149">**使用自動探索的行動服務流程**</span><span class="sxs-lookup"><span data-stu-id="03d9c-149">**Mobility service flow using AutoDiscover**</span></span>

<span data-ttu-id="03d9c-150">![cdb96424-96f2-4abf-88d7-1d32d1010ffd](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4abf-88d7-1d32d1010ffd")</span><span class="sxs-lookup"><span data-stu-id="03d9c-150">![cdb96424-96f2-4abf-88d7-1d32d1010ffd](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4abf-88d7-1d32d1010ffd")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="03d9c-151">圖表說明一般 web 服務。</span><span class="sxs-lookup"><span data-stu-id="03d9c-151">The diagram illustrates generic web services.</span></span> <span data-ttu-id="03d9c-152">名為 [行動] 的虛擬目錄會描繪行動服務 Mcx 和/或 UCWA。</span><span class="sxs-lookup"><span data-stu-id="03d9c-152">A virtual directory named Mobility depicts the Mobility services Mcx and/or UCWA.</span></span> <span data-ttu-id="03d9c-153">如果您尚未套用 Lync Server 2013 的累積更新：2月2013，可能是您的內部和外部 Web 服務定義了虛擬目錄 Ucwa。</span><span class="sxs-lookup"><span data-stu-id="03d9c-153">If you have not applied the Cumulative Updates for Lync Server 2013: February 2013, you may or may not have the virtual directory Ucwa defined on your internal and external Web services.</span></span> <span data-ttu-id="03d9c-154">您將會擁有虛擬目錄自動探索，而且您可能會有虛擬目錄 Mcx。</span><span class="sxs-lookup"><span data-stu-id="03d9c-154">You will have a virtual directory Autodiscover, and you may have a virtual directory Mcx.</span></span><BR><span data-ttu-id="03d9c-155">不論您已部署的行動服務技術為何，自動探索與服務探索的運作方式都一樣。</span><span class="sxs-lookup"><span data-stu-id="03d9c-155">Autodiscover and the discovery of services work the same way, regardless of the mobility services technology that you have deployed.</span></span>



</div>

<span data-ttu-id="03d9c-156">若要支援從公司網路內部和外部的行動使用者，您的內部和外部 web Fqdn 必須符合某些先決條件。</span><span class="sxs-lookup"><span data-stu-id="03d9c-156">To support mobile users from both inside and outside the corporate network, your internal and external web FQDNs must meet some prerequisites.</span></span> <span data-ttu-id="03d9c-157">此外，您可能需要滿足其他需求，視您選擇要執行的功能而定：</span><span class="sxs-lookup"><span data-stu-id="03d9c-157">In addition, you may need to meet other requirements, depending on the features you choose to implement:</span></span>

  - <span data-ttu-id="03d9c-158">新的 DNS、CNAME 或 A （主機，if IPv6、AAAA）記錄，用於自動搜尋。</span><span class="sxs-lookup"><span data-stu-id="03d9c-158">New DNS, CNAME or A (host, if IPv6, AAAA) records, for automatic discovery.</span></span>

  - <span data-ttu-id="03d9c-159">如果您想要透過 Wi-fi 網路支援推播通知，請選擇 [新增防火牆規則]。</span><span class="sxs-lookup"><span data-stu-id="03d9c-159">New firewall rule, if you want to support push notifications through your Wi-Fi network.</span></span>

  - <span data-ttu-id="03d9c-160">內部伺服器憑證上的消費者替代名稱和反向 proxy 憑證，用於自動搜尋。</span><span class="sxs-lookup"><span data-stu-id="03d9c-160">Subject alternative names on internal server certificates and reverse proxy certificates, for automatic discovery.</span></span>

  - <span data-ttu-id="03d9c-161">前端伺服器硬體負載平衡器設定會變更來源關聯性。</span><span class="sxs-lookup"><span data-stu-id="03d9c-161">Front End Server hardware load balancer configuration changes source affinity.</span></span>

<span data-ttu-id="03d9c-162">您的拓朴必須符合下列需求，才能支援行動服務和自動探索服務：</span><span class="sxs-lookup"><span data-stu-id="03d9c-162">Your topology must meet the following requirements to support the Mobility Service and the Autodiscover Service:</span></span>

  - <span data-ttu-id="03d9c-163">前端池內部網站 FQDN 必須與前端池外部 web FQDN 不同。</span><span class="sxs-lookup"><span data-stu-id="03d9c-163">The Front End pool internal web FQDN must be distinct from the Front End pool external web FQDN.</span></span>

  - <span data-ttu-id="03d9c-164">內部網站 FQDN 必須只能解析到公司網路內部，且可供存取。</span><span class="sxs-lookup"><span data-stu-id="03d9c-164">The internal web FQDN must only resolve to and be accessible from inside the corporate network.</span></span>

  - <span data-ttu-id="03d9c-165">外部 web FQDN 必須只能解析到網際網路，且可從網際網路存取。</span><span class="sxs-lookup"><span data-stu-id="03d9c-165">The external web FQDN must only resolve to and be accessible from the Internet.</span></span>

  - <span data-ttu-id="03d9c-166">對於位於公司網路內部的使用者，行動服務 URL 必須定址至外部網頁 FQDN。</span><span class="sxs-lookup"><span data-stu-id="03d9c-166">For a user who is inside the corporate network, the Mobility Service URL must be addressed to the external web FQDN.</span></span> <span data-ttu-id="03d9c-167">此需求適用于行動服務，且僅適用于此 URL。</span><span class="sxs-lookup"><span data-stu-id="03d9c-167">This requirement is for the Mobility Service and applies only to this URL.</span></span>

  - <span data-ttu-id="03d9c-168">對於公司網路以外的使用者，要求必須移至前端池或主管的外部 web FQDN。</span><span class="sxs-lookup"><span data-stu-id="03d9c-168">For a user who is outside the corporate network, the request must go to the external web FQDN of the Front End pool or Director.</span></span>

<span data-ttu-id="03d9c-169">如果您支援自動探索，您必須為每個 SIP 網域建立下列 DNS 記錄：</span><span class="sxs-lookup"><span data-stu-id="03d9c-169">If you support automatic discovery, you need to create the following DNS records for each SIP domain:</span></span>

  - <span data-ttu-id="03d9c-170">內部 DNS 記錄可支援從貴組織的網路中連線的行動使用者。</span><span class="sxs-lookup"><span data-stu-id="03d9c-170">An internal DNS record to support mobile users who connect from within your organization's network.</span></span>

  - <span data-ttu-id="03d9c-171">外部或公用的 DNS 記錄，可支援從網際網路連線的行動使用者。</span><span class="sxs-lookup"><span data-stu-id="03d9c-171">An external, or public, DNS record to support mobile users who connect from the Internet.</span></span>

<span data-ttu-id="03d9c-172">內部自動探索 URL 不應該是從您的網路外部定址的。</span><span class="sxs-lookup"><span data-stu-id="03d9c-172">The internal automatic discovery URL should not be addressable from outside your network.</span></span> <span data-ttu-id="03d9c-173">外部自動探索 URL 不應該是您的網路中的可定址 URL。</span><span class="sxs-lookup"><span data-stu-id="03d9c-173">The external automatic discovery URL should not be addressable from within your network.</span></span> <span data-ttu-id="03d9c-174">不過，如果您無法滿足外部 URL 的這項需求，行動用戶端功能可能不會受到影響，因為內部 URL 總是首先嘗試。</span><span class="sxs-lookup"><span data-stu-id="03d9c-174">However, if you cannot meet this requirement for the external URL, mobile client functionally will probably not be affected, because the internal URL is always tried first.</span></span>

<span data-ttu-id="03d9c-175">DNS 記錄可以是 CNAME 記錄或 A （如果是 IPv6、AAAA）記錄。</span><span class="sxs-lookup"><span data-stu-id="03d9c-175">The DNS records can be either CNAME records or A (host, if IPv6, AAAA) records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="03d9c-176">行動裝置用戶端不支援來自不同網域的多個安全通訊端層（SSL）憑證。</span><span class="sxs-lookup"><span data-stu-id="03d9c-176">Mobile device clients do not support multiple Secure Sockets Layer (SSL) certificates from different domains.</span></span> <span data-ttu-id="03d9c-177">因此，不支援在 HTTPS 上對不同網域進行 CNAME 重新導向。</span><span class="sxs-lookup"><span data-stu-id="03d9c-177">Therefore, CNAME redirection to different domains is not supported over HTTPS.</span></span> <span data-ttu-id="03d9c-178">例如，在 HTTPS 中不支援重新導向 director.contoso.net 位址的 lyncdiscover.contoso.com 的 DNS CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="03d9c-178">For example, a DNS CNAME record for lyncdiscover.contoso.com that redirects to an address of director.contoso.net is not supported over HTTPS.</span></span> <span data-ttu-id="03d9c-179">在這種拓撲中，行動裝置用戶端必須針對第一個要求使用 HTTP，才能透過 HTTP 解析 CNAME 重新導向。</span><span class="sxs-lookup"><span data-stu-id="03d9c-179">In such a topology, a mobile device client needs to use HTTP for the first request, so that the CNAME redirection is resolved over HTTP.</span></span> <span data-ttu-id="03d9c-180">後續要求接著使用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="03d9c-180">Subsequent requests then use HTTPS.</span></span> <span data-ttu-id="03d9c-181">若要支援這種情況，您必須使用埠80（HTTP）的 web 發佈規則來設定您的反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="03d9c-181">To support this scenario, you need to configure your reverse proxy with a web publishing rule for port 80 (HTTP).</span></span> <span data-ttu-id="03d9c-182">如需詳細資訊，請參閱在<A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013 中設定反向 proxy 以進行行動</A>中的 [針對埠80建立 web 發佈規則]。</span><span class="sxs-lookup"><span data-stu-id="03d9c-182">For details, see "To create a web publishing rule for port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="03d9c-183">在 HTTPS 上支援 CNAME 重新導向至同一個網域。</span><span class="sxs-lookup"><span data-stu-id="03d9c-183">CNAME redirection to the same domain is supported over HTTPS.</span></span> <span data-ttu-id="03d9c-184">在這種情況下，目的地網域的憑證會涵蓋來源網域。</span><span class="sxs-lookup"><span data-stu-id="03d9c-184">In this case, the destination domain's certificate covers the originating domain.</span></span>



</div>

<span data-ttu-id="03d9c-185">如需有關您案例所需之 DNS 記錄的詳細資訊，請參閱[在 Lync Server 2013 中的 [dns 摘要]-自動](lync-server-2013-dns-summary-autodiscover.md)探索。</span><span class="sxs-lookup"><span data-stu-id="03d9c-185">For details about the DNS records required for your scenario, see [DNS summary - Autodiscover in Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md).</span></span>

</div>

<div>

## <a name="port-and-firewall-requirements"></a><span data-ttu-id="03d9c-186">埠和防火牆需求</span><span class="sxs-lookup"><span data-stu-id="03d9c-186">Port and Firewall Requirements</span></span>

<span data-ttu-id="03d9c-187">如果您支援推播通知，且希望 Apple 行動裝置透過您的 Wi-fi 網路接收推播通知，您也需要在企業 Wi-fi 網路上開啟埠5223。</span><span class="sxs-lookup"><span data-stu-id="03d9c-187">If you support push notifications and want Apple mobile devices to receive push notifications over your Wi-Fi network, you also need to open port 5223 on your enterprise Wi-Fi network.</span></span> <span data-ttu-id="03d9c-188">埠5223是 Apple 推播通知服務（APNS）使用的輸出 TCP 埠。</span><span class="sxs-lookup"><span data-stu-id="03d9c-188">Port 5223 is an outbound TCP port used by the Apple Push Notification Service (APNS).</span></span> <span data-ttu-id="03d9c-189">行動裝置會啟動連線。</span><span class="sxs-lookup"><span data-stu-id="03d9c-189">The mobile device initiates the connection.</span></span> <span data-ttu-id="03d9c-190">如需詳細資訊[http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629) ，請參閱。</span><span class="sxs-lookup"><span data-stu-id="03d9c-190">For details, see [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629) .</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="03d9c-191">使用 Lync 2013 行動用戶端的 Apple 裝置不需要推播通知。</span><span class="sxs-lookup"><span data-stu-id="03d9c-191">An Apple device using the Lync 2013 Mobile client does not require push notifications.</span></span>



</div>

<span data-ttu-id="03d9c-192">請注意，如果使用者是託管在 Survivable 分支裝置（SBA），則需要下列埠：</span><span class="sxs-lookup"><span data-stu-id="03d9c-192">Note that if a user is homed on a Survivable Branch Appliance (SBA) then the following ports are required:</span></span>

  - <span data-ttu-id="03d9c-193">UcwaSipExternalListeningPort 需要端口5088</span><span class="sxs-lookup"><span data-stu-id="03d9c-193">UcwaSipExternalListeningPort requires port 5088</span></span>

  - <span data-ttu-id="03d9c-194">UcwaSipPrimaryListeningPort 需要端口5089</span><span class="sxs-lookup"><span data-stu-id="03d9c-194">UcwaSipPrimaryListeningPort requires port 5089</span></span>

<span data-ttu-id="03d9c-195">如需有關自動探索的埠與通訊協定需求的其他詳細資料與指示，請參閱[在 Lync Server 2013 中的 [埠摘要](lync-server-2013-port-summary-autodiscover.md)]。</span><span class="sxs-lookup"><span data-stu-id="03d9c-195">For additional details and guidance on port and protocol requirements for Autodiscover, see [Port summary - Autodiscover in Lync Server 2013](lync-server-2013-port-summary-autodiscover.md).</span></span>

</div>

<div>

## <a name="certificate-requirements"></a><span data-ttu-id="03d9c-196">證書需求</span><span class="sxs-lookup"><span data-stu-id="03d9c-196">Certificate Requirements</span></span>

<span data-ttu-id="03d9c-197">如果您支援 Lync 行動用戶端的自動探索，您必須修改憑證上的消費者備用名稱清單，以支援行動用戶端的安全連線。</span><span class="sxs-lookup"><span data-stu-id="03d9c-197">If you support automatic discovery for Lync mobile clients, you need to modify the subject alternative name lists on certificates to support secure connections from the mobile clients.</span></span> <span data-ttu-id="03d9c-198">您需要針對每個執行自動探索服務的前端伺服器和控制器，在此區段中，為每個運行的 [消費者替換名稱] 專案提出要求並指派新的憑證。</span><span class="sxs-lookup"><span data-stu-id="03d9c-198">You need to request and assign new certificates, adding the subject alternative name entries described in this section, for each Front End Server and Director that runs the Autodiscover Service.</span></span> <span data-ttu-id="03d9c-199">建議的方法也是在您的反向代理伺服器的憑證上修改 [subject] 備用名稱清單。</span><span class="sxs-lookup"><span data-stu-id="03d9c-199">The recommended approach is to also modify the subject alternative names lists on certificates for your reverse proxies.</span></span> <span data-ttu-id="03d9c-200">您需要針對貴組織中的每個 SIP 網域，新增消費者備用名稱專案。</span><span class="sxs-lookup"><span data-stu-id="03d9c-200">You need to add subject alternative name entries for every SIP domain in your organization.</span></span>

<span data-ttu-id="03d9c-201">使用內部憑證授權單位重新頒發憑證通常是一個簡單的程式，但新增多個 subject 替換名稱專案到反向 proxy 使用的公用憑證可能會很昂貴。</span><span class="sxs-lookup"><span data-stu-id="03d9c-201">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="03d9c-202">如果您有許多 SIP 網域，增加消費者備用名稱的費用相當昂貴，您可以設定反向 proxy，透過使用 HTTP 的埠80來進行初始自動探索服務要求，而不是使用 HTTPS （預設設定）的埠443。</span><span class="sxs-lookup"><span data-stu-id="03d9c-202">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to make the initial Autodiscover Service request over port 80 using HTTP, instead of port 443 using HTTPS (the default configuration).</span></span> <span data-ttu-id="03d9c-203">然後，該要求會重新導向至主管或頂層端池中的埠8080。</span><span class="sxs-lookup"><span data-stu-id="03d9c-203">The request is then redirected to port 8080 on the Director or Front End pool.</span></span> <span data-ttu-id="03d9c-204">當您在埠80上發佈初始自動探索服務要求時，您不需要變更反向 proxy 的憑證，因為要求是使用 HTTP 而不是 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="03d9c-204">When you publish the initial Autodiscover Service request on port 80, you do not need to change certificates for the reverse proxy, because the request uses HTTP rather than HTTPS.</span></span> <span data-ttu-id="03d9c-205">此方法受支援，但我們不建議這樣做。</span><span class="sxs-lookup"><span data-stu-id="03d9c-205">This approach is supported, but we do not recommend it.</span></span>

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a><span data-ttu-id="03d9c-206">網際網路資訊服務（IIS）需求</span><span class="sxs-lookup"><span data-stu-id="03d9c-206">Internet Information Services (IIS) Requirements</span></span>

<span data-ttu-id="03d9c-207">我們建議您使用 IIS 7.5、IIS 8.0 或 IIS 8.5 來進行行動。</span><span class="sxs-lookup"><span data-stu-id="03d9c-207">We recommend that you use IIS 7.5, IIS 8.0, or IIS 8.5 for mobility.</span></span> <span data-ttu-id="03d9c-208">行動服務安裝程式會在 ASP.NET 中設定旗標來改善效能。</span><span class="sxs-lookup"><span data-stu-id="03d9c-208">The Mobility Service installer sets flags in ASP.NET to improve performance.</span></span> <span data-ttu-id="03d9c-209">預設會在 Windows Server 2008 R2 上安裝 IIS 7.5，IIS 8.0 已安裝在 Windows Server 2012 上，而 IIS 8.5 則安裝在 Windows Server 2012 R2 上。</span><span class="sxs-lookup"><span data-stu-id="03d9c-209">IIS 7.5 is installed by default on Windows Server 2008 R2, IIS 8.0 is installed on Windows Server 2012, and IIS 8.5 is installed on Windows Server 2012 R2.</span></span> <span data-ttu-id="03d9c-210">行動服務安裝程式會自動變更 ASP.NET 設定。</span><span class="sxs-lookup"><span data-stu-id="03d9c-210">The Mobility Service installer automatically changes the ASP.NET settings.</span></span>

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="03d9c-211">硬體負載平衡器需求</span><span class="sxs-lookup"><span data-stu-id="03d9c-211">Hardware Load Balancer Requirements</span></span>

<span data-ttu-id="03d9c-212">在支援 [前端] 池的硬體負載平衡器上，必須針對 [來源] 設定適用于 Web 服務流量的外部 Web 服務虛擬 Ip （Vip）。</span><span class="sxs-lookup"><span data-stu-id="03d9c-212">On the hardware load balancer that is supporting the Front End pool, the external Web Services virtual IPs (VIPs) for Web Services traffic must be configured for source.</span></span> <span data-ttu-id="03d9c-213">來源關聯有助於確保將來自單一用戶端的多個連線傳送到一個伺服器，以維持會話狀態。</span><span class="sxs-lookup"><span data-stu-id="03d9c-213">Source affinity helps to ensure that multiple connections from a single client are sent to one server to maintain session state.</span></span> <span data-ttu-id="03d9c-214">如需關聯需求的詳細資訊，請參閱[Lync Server 2013 的負載平衡需求](lync-server-2013-load-balancing-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="03d9c-214">For details about affinity requirements, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

<span data-ttu-id="03d9c-215">如果您打算只支援 Lync 行動用戶端的內部 Wi-fi 網路，請根據外部 Web 服務 Vip 的描述，設定來源的內部 Web 服務 VIP。</span><span class="sxs-lookup"><span data-stu-id="03d9c-215">If you plan to support Lync mobile clients only over your internal Wi-Fi network, you should configure the internal Web Services VIPS for source as described for external Web Services VIPs.</span></span> <span data-ttu-id="03d9c-216">在這種情況下，您應該\_針對硬體負載平衡器上的內部 Web 服務 vip，使用來源位址（或 TCP）關聯。</span><span class="sxs-lookup"><span data-stu-id="03d9c-216">In this situation, you should use source\_addr (or TCP) affinity for the internal Web Services VIPs on the hardware load balancer.</span></span> <span data-ttu-id="03d9c-217">如需詳細資訊，請參閱[Lync Server 2013 的負載平衡需求](lync-server-2013-load-balancing-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="03d9c-217">For details, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

</div>

<div>

## <a name="reverse-proxy-requirements"></a><span data-ttu-id="03d9c-218">反向 Proxy 需求</span><span class="sxs-lookup"><span data-stu-id="03d9c-218">Reverse Proxy Requirements</span></span>

<span data-ttu-id="03d9c-219">如果您支援 Lync 行動用戶端的自動探索功能，您需要更新目前的發佈規則，如下所示：</span><span class="sxs-lookup"><span data-stu-id="03d9c-219">If you support automatic discovery for Lync mobile clients, you need to update the current publishing rule as follows:</span></span>

  - <span data-ttu-id="03d9c-220">如果您決定要更新反向 proxy 憑證上的消費者備用名稱清單，並在初始自動探索服務要求中使用 HTTPS，您必須更新 lyncdiscover 的 web 發佈規則。\<sipdomain\>。</span><span class="sxs-lookup"><span data-stu-id="03d9c-220">If you decide to update the subject alternative names lists on the reverse proxy certificates and use HTTPS for the initial Autodiscover Service request, you must update the web publishing rule for lyncdiscover.\<sipdomain\>.</span></span> <span data-ttu-id="03d9c-221">通常，這會與前端池上的外部 Web 服務 URL 的發佈規則結合。</span><span class="sxs-lookup"><span data-stu-id="03d9c-221">Typically, this is combined with the publishing rule for the external Web Services URL on the Front End pool.</span></span>

  - <span data-ttu-id="03d9c-222">如果您決定在初始自動探索服務要求中使用 HTTP，因此您不需要更新反向 proxy 憑證上的 [subject] 備用名稱清單，您必須為埠 HTTP/TCP 80 建立新的 web 發佈規則（如果尚未有的話）。</span><span class="sxs-lookup"><span data-stu-id="03d9c-222">If you decide to use HTTP for the initial Autodiscover Service request so that you do not need to update the subject alternative names list on the reverse proxy certificates, you must create a new web publishing rule for port HTTP/TCP 80, if one does not already exist.</span></span> <span data-ttu-id="03d9c-223">如果 HTTP/TCP 80 的規則已經存在，您可以將該規則更新為包含 lyncdiscover。\<sipdomain\>專案。</span><span class="sxs-lookup"><span data-stu-id="03d9c-223">If a rule for HTTP/TCP 80 does already exist, you can update that rule to include the lyncdiscover.\<sipdomain\> entry.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

