---
title: Lync Server 2013：自動探索服務需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Autodiscover service requirements
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48183368
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ea9d9be05561d200696a5ad0256c0d5424cf9b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="autodiscover-service-requirements-for-lync-server-2013"></a><span data-ttu-id="cca9a-102">Lync Server 2013 的自動探索服務需求</span><span class="sxs-lookup"><span data-stu-id="cca9a-102">Autodiscover service requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cca9a-103">_**主題上次修改日期：** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="cca9a-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="cca9a-104">Microsoft Lync Server 2013 自動探索服務會在主管和前端池伺服器上執行，並在 DNS 中發佈時，可供執行 Lync Mobile 的行動裝置使用，以找出行動服務。</span><span class="sxs-lookup"><span data-stu-id="cca9a-104">The Microsoft Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by mobile devices running Lync Mobile to locate mobility services.</span></span> <span data-ttu-id="cca9a-105">在執行 Lync Mobile 的行動裝置上，您可以充分利用自動探索，您必須在執行自動探索服務的任何主管和前端伺服器上修改證書消費者備用名稱清單。</span><span class="sxs-lookup"><span data-stu-id="cca9a-105">Before mobile devices running Lync Mobile can take advantage of automatic discovery, you need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="cca9a-106">此外，可能還需要針對反向代理伺服器上的外部 web 服務發佈規則，在證書上修改消費者備用名稱清單。</span><span class="sxs-lookup"><span data-stu-id="cca9a-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="cca9a-107">如需董事、前端伺服器及反向 proxy 所需的主題替換名稱專案的詳細資料，請參閱規劃行動[中的 Lync Server 2013 行動技術需求](lync-server-2013-technical-requirements-for-mobility.md)。</span><span class="sxs-lookup"><span data-stu-id="cca9a-107">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) in Planning for Mobility.</span></span>

<span data-ttu-id="cca9a-108">在反向 proxy 上使用 subject 備用名稱清單的決策是依據您是否要在埠80或埠443上發佈自動探索服務而定：</span><span class="sxs-lookup"><span data-stu-id="cca9a-108">The decision about using subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="cca9a-109">**已在埠 80**   上發佈如果自動探索服務的初始查詢是在埠80上進行，則不需要進行憑證變更。</span><span class="sxs-lookup"><span data-stu-id="cca9a-109">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="cca9a-110">這是因為執行 Lync 的行動裝置會在外部存取埠80上的反向 proxy，然後在內部將埠8080重新導向到控制器或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="cca9a-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="cca9a-111">如需詳細資訊，請參閱本主題稍後的「使用埠80的初始自動探索進程」一節。</span><span class="sxs-lookup"><span data-stu-id="cca9a-111">For details, see the “Initial Autodiscover Process Using Port 80” section later in this topic.</span></span>

  - <span data-ttu-id="cca9a-112">**已在埠 443**   上發佈：外部 web 服務發佈規則所使用的憑證上的使用方式備用名稱清單必須包含\*lyncdiscover。\<針對\> \*貴組織內的每個 SIP 網域 sipdomain 專案。</span><span class="sxs-lookup"><span data-stu-id="cca9a-112">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>* entry for each SIP domain within your organization.</span></span>

<span data-ttu-id="cca9a-113">使用內部憑證授權單位重新頒發憑證通常是一個簡單的程式，但適用于在 web 服務發佈規則上使用的公用憑證，新增多個消費者替換名稱專案可能會變得很昂貴。</span><span class="sxs-lookup"><span data-stu-id="cca9a-113">Reissuing certificates using an internal certificate authority is typically a simple process but for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="cca9a-114">若要解決此問題，我們支援經由埠80的初始自動探索連線，然後再重新導向控制器或前端伺服器上的埠8080。</span><span class="sxs-lookup"><span data-stu-id="cca9a-114">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<span data-ttu-id="cca9a-115">例如，假設執行 Lync Mobile 的行動用戶端已設定為使用自動探索功能，在初始要求中使用「自動探索」功能來登入 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="cca9a-115">For example, assume that a mobile client running Lync Mobile is configured to sign in to Lync Server 2013 using the automatic discovery feature using HTTP for the initial request.</span></span>

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a><span data-ttu-id="cca9a-116">使用埠80的行動裝置初始自動探索進程</span><span class="sxs-lookup"><span data-stu-id="cca9a-116">Initial Autodiscover Process for Mobile Devices Using Port 80</span></span>

1.  <span data-ttu-id="cca9a-117">執行 Lync Mobile 的行動裝置會使用 DNS （記錄存在）查閱 lyncdiscover.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="cca9a-117">Mobile device running Lync Mobile looks up lyncdiscover.contoso.com using DNS, where an A record exists.</span></span>

2.  <span data-ttu-id="cca9a-118">外部 DNS 會將外部 web 服務的 IP 位址傳回用戶端。</span><span class="sxs-lookup"><span data-stu-id="cca9a-118">External DNS returns the IP address for the external web services to the client.</span></span>

3.  <span data-ttu-id="cca9a-119">執行 Lync Mobile 的行動裝置會http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com將要求傳送到反向 proxy</span><span class="sxs-lookup"><span data-stu-id="cca9a-119">Mobile device running Lync Mobile sends request http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com to the reverse proxy</span></span>

4.  <span data-ttu-id="cca9a-120">Web 發佈規則會將埠80的要求從外部橋接到內部的埠8080，然後將其路由到控制器或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="cca9a-120">The web publishing rule will bridge the request from port 80 externally to port 8080 internally, which will then route it to either a Director or Front End Server.</span></span>
    
    <span data-ttu-id="cca9a-121">因為要求是 HTTP 而不是 HTTPS，所以外部 web 服務發佈規則的憑證不需要任何修改，即可支援自動探索服務。</span><span class="sxs-lookup"><span data-stu-id="cca9a-121">Since the request is HTTP and not HTTPS, no modifications are needed to the certificate on the external web service publishing rule to support the Autodiscover Service.</span></span>

5.  <span data-ttu-id="cca9a-122">自動探索服務會傳回外部 web 服務 Url （以 HTTPS 格式）。</span><span class="sxs-lookup"><span data-stu-id="cca9a-122">The Autodiscover Service returns the external web service URLs (in HTTPS format).</span></span>

6.  <span data-ttu-id="cca9a-123">執行 Lync Mobile 的行動裝置可以重新連線到埠443上的反向 proxy，並重新4443導向至在使用者的家用版池中執行的行動服務。</span><span class="sxs-lookup"><span data-stu-id="cca9a-123">The mobile device running Lync Mobile can then reconnect to the reverse proxy on port 443 and is redirected over 4443 to the mobility service running on the user’s home pool.</span></span>
    
    <span data-ttu-id="cca9a-124">由於 HTTPS 查詢是針對外部 web 服務 URL 與自動探索服務 URL，因此它會成功，因為憑證已包含外部 web 服務完整功能變數名稱（Fqdn）的消費者備用名稱專案。</span><span class="sxs-lookup"><span data-stu-id="cca9a-124">Since the HTTPS query is to the external web services URL vs. the Autodiscover Service URL, it succeeds because the certificate will already contain subject alternative name entries for the external web services fully qualified domain names (FQDNs).</span></span>
    
    <span data-ttu-id="cca9a-125">在這種情況下，不需要有任何憑證變更即可支援行動。</span><span class="sxs-lookup"><span data-stu-id="cca9a-125">In this scenario, there are no certificate changes required to support mobility.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cca9a-126">如果目標網頁伺服器的憑證沒有 lyncdiscover.contoso.com 的對應值做為 subject 替換名稱清單值：</span><span class="sxs-lookup"><span data-stu-id="cca9a-126">If the target web server has a certificate that does not have a matching value for lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="cca9a-127">a.&nbsp;&nbsp;&nbsp;Web 服務器會以「伺服器 Hello」而不是憑證來回應。</span><span class="sxs-lookup"><span data-stu-id="cca9a-127">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server Hello” and no certificate.</span></span><BR><span data-ttu-id="cca9a-128">b.&nbsp;&nbsp;&nbsp;執行 Lync mobile 的行動裝置會立即終止會話。</span><span class="sxs-lookup"><span data-stu-id="cca9a-128">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile immediately terminates the session.</span></span><BR><span data-ttu-id="cca9a-129">如果目標網頁伺服器的憑證包含 lyncdiscover.contoso.com 做為 subject 替換名稱清單值：</span><span class="sxs-lookup"><span data-stu-id="cca9a-129">If the target web server has a certificate that includes lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="cca9a-130">a.&nbsp;&nbsp;&nbsp;Web 服務器會以「伺服器 hello」和憑證來回應。</span><span class="sxs-lookup"><span data-stu-id="cca9a-130">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server hello” and a certificate.</span></span><BR><span data-ttu-id="cca9a-131">b.&nbsp;&nbsp;&nbsp;執行 Lync mobile 的行動裝置會驗證憑證並完成握手。</span><span class="sxs-lookup"><span data-stu-id="cca9a-131">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile validates the certificate and completes the handshake.</span></span>

    
    </div>

<span data-ttu-id="cca9a-132">若要在您的反向 proxy 伺服器上使用埠80來支援自動探索服務的初始連線，您可以建立與此範例類似 Forefront 威脅管理閘道2010反向 proxy web 發佈規則的 HTTP 發佈規則：</span><span class="sxs-lookup"><span data-stu-id="cca9a-132">To support an initial connection to the Autodiscover Service using port 80 on your reverse proxy server, you can create an http publishing rule similar to this example for a Forefront Threat Management Gateway 2010 reverse proxy web publishing rule:</span></span>

1.  <span data-ttu-id="cca9a-133">建立新的 web 發佈規則（例如， **Lync Server 自動探索（HTTP）**）。</span><span class="sxs-lookup"><span data-stu-id="cca9a-133">Create a new web publishing rule (for example, **Lync Server Autodiscover (HTTP)**).</span></span>

2.  <span data-ttu-id="cca9a-134">在 [**公用名稱**] 中，輸入 lyncdiscover.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="cca9a-134">In **Public Name**, enter lyncdiscover.contoso.com.</span></span>

3.  <span data-ttu-id="cca9a-135">在 [**橋接**] 索引標籤上，只選取將埠80中的要求橋接到埠8080的選項。</span><span class="sxs-lookup"><span data-stu-id="cca9a-135">On the **Bridging** tab, select only the option to bridge requests from Port 80 to Port 8080.</span></span>

4.  <span data-ttu-id="cca9a-136">在 [**驗證**] 索引標籤上，選取 [**無驗證**]，而且**用戶端無法直接驗證**。</span><span class="sxs-lookup"><span data-stu-id="cca9a-136">On the **Authentication** tab, select **No authentication**, and **Client cannot authenticate directly**.</span></span>

5.  <span data-ttu-id="cca9a-137">[提交變更]，然後將規則移至 Lync 規則清單的頂端（首先是處理順序）。</span><span class="sxs-lookup"><span data-stu-id="cca9a-137">Commit changes, and move the rule to the top of the list of Lync rules (first in processing order).</span></span>

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="cca9a-138">分割網域部署的行動性</span><span class="sxs-lookup"><span data-stu-id="cca9a-138">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="cca9a-139">共用的 SIP 位址空間（又稱為*分割網域*）或是*混合式部署*，是在內部部署和線上環境中部署使用者的配置。</span><span class="sxs-lookup"><span data-stu-id="cca9a-139">A shared SIP address space, also known as a *split-domain*, or a *hybrid deployment* is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="cca9a-140">您想要的結果是，無論其主伺服器位於何處（內部部署或線上），都能讓使用者登入並重新導向到其主伺服器位置。</span><span class="sxs-lookup"><span data-stu-id="cca9a-140">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), to log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="cca9a-141">若要完成這項作業，請使用 Microsoft Lync Server 2013 的自動探索功能，將線上使用者重新導向至線上拓撲。</span><span class="sxs-lookup"><span data-stu-id="cca9a-141">To accomplish this, the Autodiscover feature of Microsoft Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="cca9a-142">您可以透過使用 Lync Server 管理命令介面和 Cmdlet **CsHostingProvider**和**Set-CsHostingProvider**來設定自動探索統一資源定位器（URL）來完成這項工作。</span><span class="sxs-lookup"><span data-stu-id="cca9a-142">This is done by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell and the cmdlets **Get-CsHostingProvider** and **Set-CsHostingProvider**.</span></span>

<span data-ttu-id="cca9a-143">您將需要收集並錄製下列已部署的屬性：</span><span class="sxs-lookup"><span data-stu-id="cca9a-143">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="cca9a-144">從 Lync Server 管理命令介面輸入</span><span class="sxs-lookup"><span data-stu-id="cca9a-144">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="cca9a-145">在結果中，尋找具有屬性**ProxyFQDN**的線上提供者。</span><span class="sxs-lookup"><span data-stu-id="cca9a-145">In the results, find the online provider with the attribute **ProxyFQDN**.</span></span> <span data-ttu-id="cca9a-146">例如，sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cca9a-146">For example, sipfed.online.lync.com</span></span>

  - <span data-ttu-id="cca9a-147">記錄 ProxyFQDN 的值</span><span class="sxs-lookup"><span data-stu-id="cca9a-147">Record the value of the ProxyFQDN</span></span>

  - <span data-ttu-id="cca9a-148">在內部部署的 Lync Server 控制台中啟用同盟，允許與線上提供者同盟</span><span class="sxs-lookup"><span data-stu-id="cca9a-148">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider</span></span>

  - <span data-ttu-id="cca9a-149">針對線上提供者啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="cca9a-149">Enable federation for the online provider.</span></span> <span data-ttu-id="cca9a-150">根據預設，所有的線上使用者都會啟用網域同盟，而且可以與所有網域通訊</span><span class="sxs-lookup"><span data-stu-id="cca9a-150">By default, all online users are enabled for domain federation and can communicate with all domains</span></span>

  - <span data-ttu-id="cca9a-151">如果您要定義封鎖和允許的網域，請判斷您將明確允許或明確封鎖的網域</span><span class="sxs-lookup"><span data-stu-id="cca9a-151">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block</span></span>

  - <span data-ttu-id="cca9a-152">針對線上同盟，您必須規劃防火牆例外狀況、憑證和 DNS 主機（A 或 AAAA （如果使用 IPv6）記錄）。</span><span class="sxs-lookup"><span data-stu-id="cca9a-152">For online federation, you must plan for firewall exceptions, certificates and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="cca9a-153">此外，您必須設定同盟原則。</span><span class="sxs-lookup"><span data-stu-id="cca9a-153">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="cca9a-154">如需詳細資訊，請參閱[規劃 Lync Server 2013 和 Office 通訊伺服器同盟](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span><span class="sxs-lookup"><span data-stu-id="cca9a-154">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

