---
title: Lync Server 2013：瞭解自動探索
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Understanding Autodiscover
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945654(v=OCS.15)
ms:contentKeyID: 51541522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae8a4965674952cfa5822c24e887ed4d5a02b798
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-autodiscover-in-lync-server-2013"></a><span data-ttu-id="32156-102">瞭解 Lync Server 2013 中的自動探索</span><span class="sxs-lookup"><span data-stu-id="32156-102">Understanding Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32156-103">_**主題上次修改日期：** 2013-06-03_</span><span class="sxs-lookup"><span data-stu-id="32156-103">_**Topic Last Modified:** 2013-06-03_</span></span>

<span data-ttu-id="32156-104">Lync Server 2013 自動探索服務是最初在 Microsoft Lync Server 2010 中引入的一項功能，可做為 Lync Server 2010 的累積更新：11月2011。</span><span class="sxs-lookup"><span data-stu-id="32156-104">The Lync Server 2013 Autodiscover Service is a feature that was originally introduced in Microsoft Lync Server 2010 as part of the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="32156-105">除了修正程式之外，此累積更新提供 Lync Mobile 和 Lync 2013 用戶端的支援。</span><span class="sxs-lookup"><span data-stu-id="32156-105">In addition to fixes, this cumulative update delivered support for Lync Mobile and Lync 2013 clients.</span></span>

<span data-ttu-id="32156-106">在 Lync Server 2013 中，自動探索服務是外部和內部行動用戶端作業的一部分，而且自動探索也會延伸至新的用戶端，例如最近推出的 Windows 8 版 Lync Windows Store 應用程式。</span><span class="sxs-lookup"><span data-stu-id="32156-106">In Lync Server 2013, the Autodiscover Service is an integral part of the operation of external and internal mobile clients, and Autodiscover is also extended to new clients, such as the recently introduced Lync Windows Store app for Windows 8.</span></span> <span data-ttu-id="32156-107">Lync 2013 桌面用戶端也會使用自動探索功能。</span><span class="sxs-lookup"><span data-stu-id="32156-107">Autodiscover is also used by the Lync 2013 desktop clients.</span></span> <span data-ttu-id="32156-108">在 Lync Server 中，系統會透過所需的網域名稱系統（DNS）記錄 lyncdiscover 識別自動探索 **。\<網域\> **與**lyncdiscoverinternal。\<網域\>**。</span><span class="sxs-lookup"><span data-stu-id="32156-108">Autodiscover is recognized in Lync Server by the required domain name system (DNS) records **lyncdiscover.\<domain\>** and **lyncdiscoverinternal.\<domain\>**.</span></span> <span data-ttu-id="32156-109">此外，更新版本的 Lync 2010 和 Lync 2013 桌面用戶端喜歡自動探索網功能變數名稱稱系統（DNS） SRV 記錄（只有在 lyncdiscover 時才使用 DNS SRV 記錄）。\<[\>網域] 或 [lyncdiscoverinternal]。\<網域\>沒有回應或無法解決。</span><span class="sxs-lookup"><span data-stu-id="32156-109">Additionally, newer versions of the Lync 2010 and Lync 2013 desktop client prefer Autodiscover over the domain name system (DNS) SRV records, using DNS SRV records only if lyncdiscover.\<domain\> or lyncdiscoverinternal.\<domain\> does not respond or does not resolve.</span></span> <span data-ttu-id="32156-110">適用于 Windows 8 和 Lync Mobile 的 Lync Windows Store 應用程式會獨佔使用自動探索，不會參照傳統的 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="32156-110">The Lync Windows Store app for Windows 8 and Lync Mobile uses Autodiscover exclusively and will not refer to the traditional DNS SRV records.</span></span>

<span data-ttu-id="32156-111">在 Lync Server 2013 中，會展開 [自動探索]，以便與用戶端提供哪些元素、功能和通訊方法供用戶端使用。</span><span class="sxs-lookup"><span data-stu-id="32156-111">In Lync Server 2013, Autodiscover is expanded to communicate to the client which elements, features, and communication methods are available to the client.</span></span> <span data-ttu-id="32156-112">資訊是透過從用戶端傳送的要求來傳遞，而 Lync Server web 服務則會以明確定義的回應來回應，讓用戶端可以使用哪些專案，以及如何以自動探索的格式來聯繫這些功能。回應檔。</span><span class="sxs-lookup"><span data-stu-id="32156-112">The information is communicated through a request that is sent from the client, and the Lync Server web services responds with a clearly defined response that names what is available to the client, and how to contact those features in the format of the Autodiscover Response document.</span></span>

<span data-ttu-id="32156-113">瞭解自動探索回應檔的最佳方式，包括 web 服務透過這份檔將功能傳達給用戶端的方式，是在 Lync web 服務自動探索回應檔的一般回應中 dissect 及定義每一行。</span><span class="sxs-lookup"><span data-stu-id="32156-113">The best way to understand the Autodiscover response document, including how the web services communicate features to clients through this document, is to dissect and define each line in a typical response from the Lync web service Autodiscover response document.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="32156-114">在後續的詳細資料中，使用者已透過回應驗證要求驗證至主伺服器。</span><span class="sxs-lookup"><span data-stu-id="32156-114">In the details that follow, the user has already authenticated to the home server by responding to an authentication request.</span></span>



</div>

<div class="">


> [!NOTE]  
> <span data-ttu-id="32156-115">Lync 自動探索 Web 服務是在<STRONG>Microsoft 開發人員網路</STRONG>（MSDN）文件庫的 [<STRONG>開啟規格</STRONG>] 區段中的 [ <STRONG>microsoft Office 通訊協定</STRONG>] 中定義。</span><span class="sxs-lookup"><span data-stu-id="32156-115">The Lync Autodiscover Web Service is defined in the <STRONG>Microsoft Office Protocols</STRONG> in the <STRONG>Open Specifications</STRONG> section of the <STRONG>Microsoft Developer Network</STRONG> (MSDN) library.</span></span> <span data-ttu-id="32156-116">如需詳細資訊，請參閱完整的規格檔：「Lync 自動探索 Web 服務通訊<A href="http://go.microsoft.com/fwlink/?linkid=273839">http://go.microsoft.com/fwlink/?LinkId=273839</A>協定」，網址為：。</span><span class="sxs-lookup"><span data-stu-id="32156-116">For details, see the full specification document, "Lync Autodiscover Web Service Protocol," at: <A href="http://go.microsoft.com/fwlink/?linkid=273839">http://go.microsoft.com/fwlink/?LinkId=273839</A>.</span></span> <span data-ttu-id="32156-117">如需有關驗證的詳細資訊，請參閱「OC 驗證 Web <A href="http://go.microsoft.com/fwlink/?linkid=279015">http://go.microsoft.com/fwlink/?LinkId=279015</A>服務通訊協定」。</span><span class="sxs-lookup"><span data-stu-id="32156-117">For details about authentication, see "OC Authentication Web Service Protocol" at <A href="http://go.microsoft.com/fwlink/?linkid=279015">http://go.microsoft.com/fwlink/?LinkId=279015</A>.</span></span>



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a><span data-ttu-id="32156-118">Lync Server Web 服務自動探索回應</span><span class="sxs-lookup"><span data-stu-id="32156-118">The Lync Server Web Service Autodiscover Response</span></span>

<span data-ttu-id="32156-119">傳送自動探索要求時所傳回的回應，對於內部或外部用戶端而言是相同的。</span><span class="sxs-lookup"><span data-stu-id="32156-119">The response returned when the Autodiscover request is sent is the same for an internal or an external client.</span></span> <span data-ttu-id="32156-120">某些位置的可感知參數可能會變更。</span><span class="sxs-lookup"><span data-stu-id="32156-120">Some parameters that are location–aware may change.</span></span> <span data-ttu-id="32156-121">如果收到用戶端要求，但實際的池不是您所取得的那一個，則會針對該使用者設定使用者的主文件庫。</span><span class="sxs-lookup"><span data-stu-id="32156-121">If a client request is received, but the actual pool is other than the one that has been contacted, the user’s home pool will be set for that user.</span></span> <span data-ttu-id="32156-122">如果同事的使用者帳戶位於不同的文檔池中，但是從同一個 office 登入，則回應會稍有不同。</span><span class="sxs-lookup"><span data-stu-id="32156-122">A colleague whose user account is on a different pool, but logging in from the same office, would get a slightly different response.</span></span> <span data-ttu-id="32156-123">回應會指出該使用者的正確前端伺服器或頂層端池。</span><span class="sxs-lookup"><span data-stu-id="32156-123">The response indicates the correct Front End Server or Front End pool for that user.</span></span>

<span data-ttu-id="32156-124">自動探索回應檔的範例：</span><span class="sxs-lookup"><span data-stu-id="32156-124">An example of an Autodiscover Response document:</span></span>

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">
       <User>
          <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>
          <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>
          <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>
          <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>
          <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>
          <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>
          <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>
          <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>
          <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>
          <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>
          <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>
          <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>
          <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>
       </User>
    </AutodiscoverResponse>

<div>

## <a name="autodiscover-response-document-details"></a><span data-ttu-id="32156-125">自動探索回應檔詳細資料</span><span class="sxs-lookup"><span data-stu-id="32156-125">Autodiscover Response Document Details</span></span>

<span data-ttu-id="32156-126">自動探索回應檔可以是兩種格式的其中之一。</span><span class="sxs-lookup"><span data-stu-id="32156-126">The Autodiscover Response document can be in one of two formats.</span></span> <span data-ttu-id="32156-127">預設格式是 JavaScript 物件符號（JSON）。</span><span class="sxs-lookup"><span data-stu-id="32156-127">The default format is a JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="32156-128">另一種格式是可擴展標記語言（XML）檔。</span><span class="sxs-lookup"><span data-stu-id="32156-128">The other format is extensible markup language (XML) document.</span></span> <span data-ttu-id="32156-129">此範例會使用 XML。</span><span class="sxs-lookup"><span data-stu-id="32156-129">The XML is used for this example.</span></span> <span data-ttu-id="32156-130">要求和回應是可預測的，因為檔的定義架構決定了格式。</span><span class="sxs-lookup"><span data-stu-id="32156-130">The request and response are predictable because the document has a defined schema that determines the format.</span></span> <span data-ttu-id="32156-131">檔中描述所使用之架構的行是要求或回應中的第一行：</span><span class="sxs-lookup"><span data-stu-id="32156-131">The line in the document that describes the schema used is the first line in the request or response:</span></span>

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

<span data-ttu-id="32156-132">**AccessLocation = "External"** 的定義代表來自外部使用者的要求。</span><span class="sxs-lookup"><span data-stu-id="32156-132">The definition of **AccessLocation=”External”** indicates that the request was made from an external user.</span></span>

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

<span data-ttu-id="32156-133">目前未使用 SipServerInternalAccess 和 SipServerExternalAccess。</span><span class="sxs-lookup"><span data-stu-id="32156-133">SipServerInternalAccess and SipServerExternalAccess are currently not used.</span></span> <span data-ttu-id="32156-134">這些專案會保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="32156-134">These entries are reserved for future use.</span></span>

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

<span data-ttu-id="32156-135">SipClientInternalAccess 和 SipClientExternalAccess 說明內部或外部用戶端將用來存取已定義 SIP 伺服器的完整功能變數名稱和埠。</span><span class="sxs-lookup"><span data-stu-id="32156-135">SipClientInternalAccess and SipClientExternalAccess describe the fully qualified domain name and port that an internal or external client will use to access the defined SIP Server.</span></span> <span data-ttu-id="32156-136">Lync 桌面用戶端和 Lync Windows Store 應用程式會根據其位置（內部或外部），使用這些專案來尋找控制器或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="32156-136">The Lync desktop client and the Lync Windows Store app use these entries, based on their location (internal or external) to find the Director or Front End Server.</span></span>

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

<span data-ttu-id="32156-137">`Autodiscover`參照包含自動探索服務的服務進入點。</span><span class="sxs-lookup"><span data-stu-id="32156-137">The `Autodiscover` references contain the service entry points for the Autodiscover service.</span></span> <span data-ttu-id="32156-138">Token 屬性包含服務的名稱，href 是定義可找到服務之用戶端的 URL。</span><span class="sxs-lookup"><span data-stu-id="32156-138">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="32156-139">外部網路上的`External/Autodiscover`用戶端使用。</span><span class="sxs-lookup"><span data-stu-id="32156-139">Clients on an external network use the `External/Autodiscover`.</span></span> <span data-ttu-id="32156-140">自動探索服務會安裝為部署程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="32156-140">The Autodiscover service is installed as part of the deployment process.</span></span> <span data-ttu-id="32156-141">`Internal/Autodiscover`目前不使用，且已保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="32156-141">`Internal/Autodiscover` is not currently used, and is reserved for future use.</span></span>

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

<span data-ttu-id="32156-142">`AuthBroker`參照包含內部和外部驗證 broker 服務的服務進入點，在此案例中為 [sip.]。</span><span class="sxs-lookup"><span data-stu-id="32156-142">The `AuthBroker` references contain the service entry points for the internal and the external authentication broker service, in this case, sip.svc.</span></span> <span data-ttu-id="32156-143">Token 屬性包含服務的名稱，href 是定義可找到服務之用戶端的 URL。</span><span class="sxs-lookup"><span data-stu-id="32156-143">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="32156-144">內部網路上使用`Internal/AuthBroker`的用戶端。</span><span class="sxs-lookup"><span data-stu-id="32156-144">Clients on the internal network with use `Internal/AuthBroker`.</span></span> <span data-ttu-id="32156-145">外部網路上的`External/AuthBroker`用戶端使用。</span><span class="sxs-lookup"><span data-stu-id="32156-145">Clients on an external network use the `External/AuthBroker`.</span></span> <span data-ttu-id="32156-146">AuthBroker 服務已安裝為內部 Lync Server 2013 部署 web 服務部署程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="32156-146">The AuthBroker service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

<span data-ttu-id="32156-147">`WebScheduler`權杖會參照用戶端存取 Lync Server 會議的網路排程的 url。</span><span class="sxs-lookup"><span data-stu-id="32156-147">The `WebScheduler` token references the URLs for client access to the web-based scheduling for Lync Server conferences.</span></span> <span data-ttu-id="32156-148">目前只`External/WebScheduler`使用。</span><span class="sxs-lookup"><span data-stu-id="32156-148">Currently, only the `External/WebScheduler` is used.</span></span> <span data-ttu-id="32156-149">WebScheduler 已安裝為您內部 Lync Server 2013 部署 web 服務部署程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="32156-149">The WebScheduler is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

<span data-ttu-id="32156-150">`Internal/Mcx`而且`External/Mcx`是行動服務的位置，在 Lync Server 2010 的累加更新中引入：2011年11月。</span><span class="sxs-lookup"><span data-stu-id="32156-150">`Internal/Mcx` and `External/Mcx` are the locations of the Mobility services, introduced in Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="32156-151">Lync 2010 Mobile 會繼續在所有支援的裝置上使用這些參考。</span><span class="sxs-lookup"><span data-stu-id="32156-151">These references will continue to be used by Lync 2010 Mobile on all supported devices.</span></span> <span data-ttu-id="32156-152">Mcx 服務已安裝為內部 Lync Server 2013 部署 web 服務部署程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="32156-152">The Mcx service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

<span data-ttu-id="32156-153">**Internal/Ucwa**、 **External/Ucwa**和**Ucwa**提供一種方式讓用戶端存取整合通訊 Web 應用程式程式設計介面（Ucwa API 或只是 Ucwa）。</span><span class="sxs-lookup"><span data-stu-id="32156-153">**Internal/Ucwa**, **External/Ucwa** and **Ucwa** provide a means for clients to access the Unified Communications Web Application Programming Interface (UCWA API, or simply UCWA).</span></span> <span data-ttu-id="32156-154">`Internal/Ucwa`而且`External/Ucwa`虛擬目錄是保留給未來功能增強的存取點，不會使用。</span><span class="sxs-lookup"><span data-stu-id="32156-154">`Internal/Ucwa` and `External/Ucwa` virtual directories are access points reserved for future feature enhancement, and are not used.</span></span> <span data-ttu-id="32156-155">`Ucwa`虛擬目錄用於 Microsoft Lync Mobile （在所有支援的裝置上推出 Lync Server 2013）。</span><span class="sxs-lookup"><span data-stu-id="32156-155">The `Ucwa` virtual directory is used for Microsoft Lync Mobile (introduced with Lync Server 2013) on all supported devices.</span></span> <span data-ttu-id="32156-156">UCWA 服務已安裝為內部 Lync Server 2013 部署 web 服務部署程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="32156-156">The UCWA service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

<span data-ttu-id="32156-157">`Internal/XFrame`、**外部/XFrame**和**XFRAME**提供對 UCWA 伺服器應用程式的存取權。</span><span class="sxs-lookup"><span data-stu-id="32156-157">`Internal/XFrame`, **External/XFrame** and **XFrame** provide access for UCWA-based server applications.</span></span> <span data-ttu-id="32156-158">XFrame 已安裝為您內部 Lync Server 2013 部署 web 服務部署程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="32156-158">XFrame is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

<span data-ttu-id="32156-159">`Self`標記是指發出要求之用戶端（使用者回應類型）專用的資訊。</span><span class="sxs-lookup"><span data-stu-id="32156-159">The `Self` token refers to information specific to the client (user response type) that is making the request.</span></span> <span data-ttu-id="32156-160">發出此要求的用戶端是外部的，而這個自動探索參照是對自動探索服務的使用者部分。</span><span class="sxs-lookup"><span data-stu-id="32156-160">The client that made this request was external, and this Autodiscover reference is to the user portion of the Autodiscover service.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="32156-161">請參閱</span><span class="sxs-lookup"><span data-stu-id="32156-161">See Also</span></span>


[<span data-ttu-id="32156-162">外部使用者為 Lync Server 2013 存取元件的系統需求</span><span class="sxs-lookup"><span data-stu-id="32156-162">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[<span data-ttu-id="32156-163">規劃 Lync Server 2013 中的自動探索</span><span class="sxs-lookup"><span data-stu-id="32156-163">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

