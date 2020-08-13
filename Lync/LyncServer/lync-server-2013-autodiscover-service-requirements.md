---
title: Lync Server 2013：自動探索服務需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Autodiscover service requirements
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48183368
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ec6c3ada06312f816a75f5539593336addc8d2b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="autodiscover-service-requirements-for-lync-server-2013"></a><span data-ttu-id="31ad1-102">Lync Server 2013 的自動探索服務需求</span><span class="sxs-lookup"><span data-stu-id="31ad1-102">Autodiscover service requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31ad1-103">_**主題上次修改日期：** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="31ad1-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="31ad1-104">在 Director 和前端集區伺服器上執行的 Microsoft Lync Server 2013 自動探索服務，以及在 DNS 中發佈時，可供執行 Lync Mobile 的行動裝置使用，以找出行動性服務。</span><span class="sxs-lookup"><span data-stu-id="31ad1-104">The Microsoft Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by mobile devices running Lync Mobile to locate mobility services.</span></span> <span data-ttu-id="31ad1-105">在執行 Lync Mobile 的行動裝置可以充分利用自動探索之前，您必須在執行自動探索服務的任何 Director 和前端伺服器上修改憑證主體替代名稱清單。</span><span class="sxs-lookup"><span data-stu-id="31ad1-105">Before mobile devices running Lync Mobile can take advantage of automatic discovery, you need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="31ad1-106">此外，可能還需要針對在反向 Proxy 上用於外部 Web 服務發行規則的憑證，修改主體替代名稱清單。</span><span class="sxs-lookup"><span data-stu-id="31ad1-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="31ad1-107">如需 Director、前端伺服器及反向 proxy 所需的主體替代名稱專案的詳細資訊，請參閱規劃行動性時，[在 Lync Server 2013 中行動的技術需求](lync-server-2013-technical-requirements-for-mobility.md)。</span><span class="sxs-lookup"><span data-stu-id="31ad1-107">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) in Planning for Mobility.</span></span>

<span data-ttu-id="31ad1-108">有關在反向 Proxy 上使用主體替代名稱清單的決策，取決於您是在連接埠 80 還是連接埠 443 上發行自動探索服務：</span><span class="sxs-lookup"><span data-stu-id="31ad1-108">The decision about using subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="31ad1-109">**已在埠 80**     上發行如果自動探索服務的初始查詢發生在埠80上，則不需要憑證變更。</span><span class="sxs-lookup"><span data-stu-id="31ad1-109">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="31ad1-110">這是因為執行 Lync 的行動裝置會在外部存取埠80上的反向 proxy，然後再重新導向埠8080上的 Director 或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="31ad1-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="31ad1-111">如需詳細資訊，請參閱本主題稍後的＜使用連接埠 80 的初始自動探索程序＞。</span><span class="sxs-lookup"><span data-stu-id="31ad1-111">For details, see the “Initial Autodiscover Process Using Port 80” section later in this topic.</span></span>

  - <span data-ttu-id="31ad1-112">**已在埠 443**     上發行外部 web 服務發行規則所使用之憑證上的主體替代名稱清單必須包含\*lyncdiscover。 \<組織 \> \*內每個 SIP 網域的 microsoft.rtc.management.xds.sipdomain 專案。</span><span class="sxs-lookup"><span data-stu-id="31ad1-112">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>* entry for each SIP domain within your organization.</span></span>

<span data-ttu-id="31ad1-113">使用內部憑證授權單位來重新發出憑證通常是個簡單的程序，但是針對用於 Web 服務發行規則的公用憑證，新增多個主體替代名稱項目會變得很昂貴。</span><span class="sxs-lookup"><span data-stu-id="31ad1-113">Reissuing certificates using an internal certificate authority is typically a simple process but for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="31ad1-114">若要解決此問題，我們支援經由埠80的初始自動探索連線，然後重新導向 Director 或前端伺服器上的埠8080。</span><span class="sxs-lookup"><span data-stu-id="31ad1-114">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<span data-ttu-id="31ad1-115">例如，假設執行 Lync Mobile 的行動用戶端已設定為使用使用 HTTP 的「自動探索」功能，登入 Lync Server 2013，以進行初始要求。</span><span class="sxs-lookup"><span data-stu-id="31ad1-115">For example, assume that a mobile client running Lync Mobile is configured to sign in to Lync Server 2013 using the automatic discovery feature using HTTP for the initial request.</span></span>

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a><span data-ttu-id="31ad1-116">使用埠80的行動裝置初始自動探索過程</span><span class="sxs-lookup"><span data-stu-id="31ad1-116">Initial Autodiscover Process for Mobile Devices Using Port 80</span></span>

1.  <span data-ttu-id="31ad1-117">執行 Lync Mobile 的行動裝置會使用 DNS 來查尋 lyncdiscover.contoso.com，其中 A 記錄存在。</span><span class="sxs-lookup"><span data-stu-id="31ad1-117">Mobile device running Lync Mobile looks up lyncdiscover.contoso.com using DNS, where an A record exists.</span></span>

2.  <span data-ttu-id="31ad1-118">外部 DNS 將外部 web 服務的 IP 位址傳回給用戶端。</span><span class="sxs-lookup"><span data-stu-id="31ad1-118">External DNS returns the IP address for the external web services to the client.</span></span>

3.  <span data-ttu-id="31ad1-119">執行 Lync Mobile 的行動裝置會將要求傳送 http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com 給反向 proxy</span><span class="sxs-lookup"><span data-stu-id="31ad1-119">Mobile device running Lync Mobile sends request http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com to the reverse proxy</span></span>

4.  <span data-ttu-id="31ad1-120">網頁發行規則會將來自埠80的要求從外部橋接至埠8080，然後再將它路由傳送到 Director 或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="31ad1-120">The web publishing rule will bridge the request from port 80 externally to port 8080 internally, which will then route it to either a Director or Front End Server.</span></span>
    
    <span data-ttu-id="31ad1-121">由於要求是 HTTP 而不是 HTTPS，所以不需要修改外部 Web 服務發行規則的憑證來支援自動探索服務。</span><span class="sxs-lookup"><span data-stu-id="31ad1-121">Since the request is HTTP and not HTTPS, no modifications are needed to the certificate on the external web service publishing rule to support the Autodiscover Service.</span></span>

5.  <span data-ttu-id="31ad1-122">自動探索服務會傳回外部 Web 服務 URL (以 HTTPS 格式)。</span><span class="sxs-lookup"><span data-stu-id="31ad1-122">The Autodiscover Service returns the external web service URLs (in HTTPS format).</span></span>

6.  <span data-ttu-id="31ad1-123">執行 Lync Mobile 的行動裝置可以重新連接至埠443上的反向 proxy，並重新4443導向至使用者主集區上執行的行動服務。</span><span class="sxs-lookup"><span data-stu-id="31ad1-123">The mobile device running Lync Mobile can then reconnect to the reverse proxy on port 443 and is redirected over 4443 to the mobility service running on the user’s home pool.</span></span>
    
    <span data-ttu-id="31ad1-124">由於 HTTPS 查詢是針對外部 Web 服務 URL 對自動探索服務 URL，所以會成功，因為憑證已包含外部 Web 服務完整網域名稱 (FQDN) 的主體替代名稱項目。</span><span class="sxs-lookup"><span data-stu-id="31ad1-124">Since the HTTPS query is to the external web services URL vs. the Autodiscover Service URL, it succeeds because the certificate will already contain subject alternative name entries for the external web services fully qualified domain names (FQDNs).</span></span>
    
    <span data-ttu-id="31ad1-125">在此情況下，不需要變更憑證以支援行動性。</span><span class="sxs-lookup"><span data-stu-id="31ad1-125">In this scenario, there are no certificate changes required to support mobility.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="31ad1-126">如果目標 Web 伺服器的憑證沒有 lyncdiscover.contoso.com 的相符值，以作為主體替代名稱清單值，則：</span><span class="sxs-lookup"><span data-stu-id="31ad1-126">If the target web server has a certificate that does not have a matching value for lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="31ad1-127">a。 &nbsp; &nbsp; &nbsp;Web 服務器以「伺服器 Hello」回應，但沒有憑證。</span><span class="sxs-lookup"><span data-stu-id="31ad1-127">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server Hello” and no certificate.</span></span><BR><span data-ttu-id="31ad1-128">b。 &nbsp; &nbsp; &nbsp;運作 Lync Mobile 的行動裝置會立即終止會話。</span><span class="sxs-lookup"><span data-stu-id="31ad1-128">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile immediately terminates the session.</span></span><BR><span data-ttu-id="31ad1-129">如果目標 Web 伺服器的憑證包含 lyncdiscover.contoso.com，以作為主體替代名稱清單值，則：</span><span class="sxs-lookup"><span data-stu-id="31ad1-129">If the target web server has a certificate that includes lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="31ad1-130">a。 &nbsp; &nbsp; &nbsp;網頁伺服器會以「伺服器 hello」和憑證回應。</span><span class="sxs-lookup"><span data-stu-id="31ad1-130">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server hello” and a certificate.</span></span><BR><span data-ttu-id="31ad1-131">b。 &nbsp; &nbsp; &nbsp;執行 Lync Mobile 的行動裝置會驗證憑證，並完成握手。</span><span class="sxs-lookup"><span data-stu-id="31ad1-131">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile validates the certificate and completes the handshake.</span></span>

    
    </div>

<span data-ttu-id="31ad1-132">若要使用反向 Proxy 伺服器上的連接埠 80 來支援初始連線至自動探索服務，您可以建立 http 發行規則，類似用於 Forefront Threat Management Gateway 2010 反向 Proxy 網頁發行規則的下列範例：</span><span class="sxs-lookup"><span data-stu-id="31ad1-132">To support an initial connection to the Autodiscover Service using port 80 on your reverse proxy server, you can create an http publishing rule similar to this example for a Forefront Threat Management Gateway 2010 reverse proxy web publishing rule:</span></span>

1.  <span data-ttu-id="31ad1-133">建立新的網頁發行規則 (例如，**Lync Server 自動探索 (HTTP)**)。</span><span class="sxs-lookup"><span data-stu-id="31ad1-133">Create a new web publishing rule (for example, **Lync Server Autodiscover (HTTP)**).</span></span>

2.  <span data-ttu-id="31ad1-134">在 [公用名稱]\*\*\*\* 中，輸入 lyncdiscover.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="31ad1-134">In **Public Name**, enter lyncdiscover.contoso.com.</span></span>

3.  <span data-ttu-id="31ad1-135">在 [橋接]\*\*\*\* 索引標籤中，只選取將要求從連接埠 80 橋接至連接埠 8080 的選項。</span><span class="sxs-lookup"><span data-stu-id="31ad1-135">On the **Bridging** tab, select only the option to bridge requests from Port 80 to Port 8080.</span></span>

4.  <span data-ttu-id="31ad1-136">在 [驗證]\*\*\*\* 索引標籤上，選取 [無驗證]\*\*\*\* 和 [用戶端無法直接驗證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="31ad1-136">On the **Authentication** tab, select **No authentication**, and **Client cannot authenticate directly**.</span></span>

5.  <span data-ttu-id="31ad1-137">認可變更，並將規則移至 Lync 規則清單的頂端 (的處理順序) 中。</span><span class="sxs-lookup"><span data-stu-id="31ad1-137">Commit changes, and move the rule to the top of the list of Lync rules (first in processing order).</span></span>

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="31ad1-138">分割網域部署的行動性</span><span class="sxs-lookup"><span data-stu-id="31ad1-138">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="31ad1-139">共用 SIP 位址空間 (也稱為「分割網域」**) 或「混合式部署」** 是一種跨內部部署與線上環境來部署使用者的設定。</span><span class="sxs-lookup"><span data-stu-id="31ad1-139">A shared SIP address space, also known as a *split-domain*, or a *hybrid deployment* is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="31ad1-140">預期的結果是要讓使用者 (無論其主伺服器是位在內部部署或線上) 登入部署，並重新導向至其主伺服器位置。</span><span class="sxs-lookup"><span data-stu-id="31ad1-140">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), to log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="31ad1-141">為了達到此目的，Microsoft Lync Server 2013 的自動探索功能是用來將線上使用者重新導向至線上拓撲。</span><span class="sxs-lookup"><span data-stu-id="31ad1-141">To accomplish this, the Autodiscover feature of Microsoft Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="31ad1-142">這是透過使用 Lync Server 管理命令介面和 Cmdlet **Get-CsHostingProvider**和**Get-cshostingprovider，設定**自動探索統一資源定位器 (URL) 來完成。</span><span class="sxs-lookup"><span data-stu-id="31ad1-142">This is done by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell and the cmdlets **Get-CsHostingProvider** and **Set-CsHostingProvider**.</span></span>

<span data-ttu-id="31ad1-143">您需要收集和記錄下列部署的屬性：</span><span class="sxs-lookup"><span data-stu-id="31ad1-143">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="31ad1-144">從 Lync Server 管理命令介面中，輸入</span><span class="sxs-lookup"><span data-stu-id="31ad1-144">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="31ad1-p105">在結果中尋找具有 **ProxyFQDN** 屬性的線上提供者。例如，sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="31ad1-p105">In the results, find the online provider with the attribute **ProxyFQDN**. For example, sipfed.online.lync.com</span></span>

  - <span data-ttu-id="31ad1-147">記錄 ProxyFQDN 的值</span><span class="sxs-lookup"><span data-stu-id="31ad1-147">Record the value of the ProxyFQDN</span></span>

  - <span data-ttu-id="31ad1-148">在內部部署 Lync Server 控制台中啟用同盟，允許與線上提供者同盟</span><span class="sxs-lookup"><span data-stu-id="31ad1-148">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider</span></span>

  - <span data-ttu-id="31ad1-p106">為線上提供者啟用同盟。依預設，所有線上使用者都會啟用網域同盟，並可與所有網域通訊</span><span class="sxs-lookup"><span data-stu-id="31ad1-p106">Enable federation for the online provider. By default, all online users are enabled for domain federation and can communicate with all domains</span></span>

  - <span data-ttu-id="31ad1-151">如果您將會定義封鎖及允許的網域，請決定您要明確允許或封鎖的網域</span><span class="sxs-lookup"><span data-stu-id="31ad1-151">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block</span></span>

  - <span data-ttu-id="31ad1-152">若為線上同盟，您必須規劃防火牆例外、憑證及 DNS 主機 (若使用 IPv6，則為 A 或 AAAA) 記錄。</span><span class="sxs-lookup"><span data-stu-id="31ad1-152">For online federation, you must plan for firewall exceptions, certificates and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="31ad1-153">此外，您必須設定同盟原則。</span><span class="sxs-lookup"><span data-stu-id="31ad1-153">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="31ad1-154">如需詳細資訊，請參閱[規劃 Lync Server 2013 和 Office 通訊伺服器同盟](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span><span class="sxs-lookup"><span data-stu-id="31ad1-154">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

