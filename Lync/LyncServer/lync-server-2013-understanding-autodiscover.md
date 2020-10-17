---
title: Lync Server 2013：瞭解自動探索
description: Lync Server 2013：瞭解自動探索。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Autodiscover
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945654(v=OCS.15)
ms:contentKeyID: 51541522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 295aba4bffbe5d17070702203cfd933284cb12c0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547349"
---
# <a name="understanding-autodiscover-in-lync-server-2013"></a><span data-ttu-id="f3637-103">瞭解 Lync Server 2013 中的自動探索</span><span class="sxs-lookup"><span data-stu-id="f3637-103">Understanding Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3637-104">_**主題上次修改日期：** 2013-06-03_</span><span class="sxs-lookup"><span data-stu-id="f3637-104">_**Topic Last Modified:** 2013-06-03_</span></span>

<span data-ttu-id="f3637-105">Lync Server 2013 自動探索服務是一項功能，最初是在 Lync Server 2010： 11 2011 月的累計更新中所引進的 Microsoft Lync Server 2010 中。</span><span class="sxs-lookup"><span data-stu-id="f3637-105">The Lync Server 2013 Autodiscover Service is a feature that was originally introduced in Microsoft Lync Server 2010 as part of the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="f3637-106">除了修正之外，此累積更新可提供 Lync Mobile 和 Lync 2013 用戶端的支援。</span><span class="sxs-lookup"><span data-stu-id="f3637-106">In addition to fixes, this cumulative update delivered support for Lync Mobile and Lync 2013 clients.</span></span>

<span data-ttu-id="f3637-107">在 Lync Server 2013 中，自動探索服務是外部和內部行動用戶端作業的一部分，而自動探索也會延伸至新的用戶端，例如最近引進的適用于 Windows 8 的 Lync Windows Store 應用程式。</span><span class="sxs-lookup"><span data-stu-id="f3637-107">In Lync Server 2013, the Autodiscover Service is an integral part of the operation of external and internal mobile clients, and Autodiscover is also extended to new clients, such as the recently introduced Lync Windows Store app for Windows 8.</span></span> <span data-ttu-id="f3637-108">Lync 2013 桌面用戶端也會使用自動探索。</span><span class="sxs-lookup"><span data-stu-id="f3637-108">Autodiscover is also used by the Lync 2013 desktop clients.</span></span> <span data-ttu-id="f3637-109">使用必要的網域名稱系統 (DNS) 記錄 lyncdiscover，可在 Lync Server 中識別自動探索 \*\*。 \<domain\> \*\*</span><span class="sxs-lookup"><span data-stu-id="f3637-109">Autodiscover is recognized in Lync Server by the required domain name system (DNS) records **lyncdiscover.\<domain\>**</span></span> <span data-ttu-id="f3637-110">和\*\*lyncdiscoverinternal。 \<domain\> \*\*</span><span class="sxs-lookup"><span data-stu-id="f3637-110">and **lyncdiscoverinternal.\<domain\>**.</span></span> <span data-ttu-id="f3637-111">此外，更新版本的 Lync 2010 和 Lync 2013 桌面用戶端更喜歡透過網域名稱系統自動探索 (DNS) SRV 記錄，只會在 lyncdiscover 時使用 DNS SRV 記錄。\<domain\></span><span class="sxs-lookup"><span data-stu-id="f3637-111">Additionally, newer versions of the Lync 2010 and Lync 2013 desktop client prefer Autodiscover over the domain name system (DNS) SRV records, using DNS SRV records only if lyncdiscover.\<domain\></span></span> <span data-ttu-id="f3637-112">或 lyncdiscoverinternal。\<domain\></span><span class="sxs-lookup"><span data-stu-id="f3637-112">or lyncdiscoverinternal.\<domain\></span></span> <span data-ttu-id="f3637-113">未回應或未解決。</span><span class="sxs-lookup"><span data-stu-id="f3637-113">does not respond or does not resolve.</span></span> <span data-ttu-id="f3637-114">適用于 Windows 8 和 Lync Mobile 的 Lync Windows 應用商店應用程式會以獨佔方式使用自動探索，不會參照傳統的 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="f3637-114">The Lync Windows Store app for Windows 8 and Lync Mobile uses Autodiscover exclusively and will not refer to the traditional DNS SRV records.</span></span>

<span data-ttu-id="f3637-115">在 Lync Server 2013 中，自動探索已展開，可與用戶端通訊，以與用戶端使用哪些元素、功能和通訊方式。</span><span class="sxs-lookup"><span data-stu-id="f3637-115">In Lync Server 2013, Autodiscover is expanded to communicate to the client which elements, features, and communication methods are available to the client.</span></span> <span data-ttu-id="f3637-116">透過用戶端傳送的要求來傳遞資訊，且 Lync Server web 服務會以明確定義的回應來回應，該回應會以名稱明確定義的回應，以命名用戶端可使用的內容，以及如何與自動探索回應檔的格式聯繫這些功能。</span><span class="sxs-lookup"><span data-stu-id="f3637-116">The information is communicated through a request that is sent from the client, and the Lync Server web services responds with a clearly defined response that names what is available to the client, and how to contact those features in the format of the Autodiscover Response document.</span></span>

<span data-ttu-id="f3637-117">瞭解自動探索回應檔的最佳方式，包含 web 服務透過此檔對用戶端進行通訊的方式，是要在 Lync web 服務自動探索回應檔的一般回應中 dissect 及定義每一行。</span><span class="sxs-lookup"><span data-stu-id="f3637-117">The best way to understand the Autodiscover response document, including how the web services communicate features to clients through this document, is to dissect and define each line in a typical response from the Lync web service Autodiscover response document.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="f3637-118">在後續的詳細資料中，使用者已透過回應驗證要求來驗證主伺服器。</span><span class="sxs-lookup"><span data-stu-id="f3637-118">In the details that follow, the user has already authenticated to the home server by responding to an authentication request.</span></span>



</div>

<div class="">


> [!NOTE]  
> <span data-ttu-id="f3637-119">Lync 自動探索 Web 服務是在 microsoft <STRONG>Developer Network</STRONG> (MSDN) 程式庫的 [<STRONG>開啟規格</STRONG>] 區段中的 [ <STRONG>microsoft Office 通訊協定</STRONG>] 中定義的。</span><span class="sxs-lookup"><span data-stu-id="f3637-119">The Lync Autodiscover Web Service is defined in the <STRONG>Microsoft Office Protocols</STRONG> in the <STRONG>Open Specifications</STRONG> section of the <STRONG>Microsoft Developer Network</STRONG> (MSDN) library.</span></span> <span data-ttu-id="f3637-120">如需詳細資訊，請參閱：的完整規格檔「Lync 自動探索 Web 服務通訊協定」 <A href="https://go.microsoft.com/fwlink/?linkid=273839">https://go.microsoft.com/fwlink/?LinkId=273839</A> 。</span><span class="sxs-lookup"><span data-stu-id="f3637-120">For details, see the full specification document, "Lync Autodiscover Web Service Protocol," at: <A href="https://go.microsoft.com/fwlink/?linkid=273839">https://go.microsoft.com/fwlink/?LinkId=273839</A>.</span></span> <span data-ttu-id="f3637-121">如需驗證的詳細資訊，請參閱 at 中的「OC 驗證 Web 服務通訊協定」 <A href="https://go.microsoft.com/fwlink/?linkid=279015">https://go.microsoft.com/fwlink/?LinkId=279015</A> 。</span><span class="sxs-lookup"><span data-stu-id="f3637-121">For details about authentication, see "OC Authentication Web Service Protocol" at <A href="https://go.microsoft.com/fwlink/?linkid=279015">https://go.microsoft.com/fwlink/?LinkId=279015</A>.</span></span>



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a><span data-ttu-id="f3637-122">Lync Server Web 服務自動探索回應</span><span class="sxs-lookup"><span data-stu-id="f3637-122">The Lync Server Web Service Autodiscover Response</span></span>

<span data-ttu-id="f3637-123">傳送自動探索要求給內部或外部用戶端時所傳回的回應。</span><span class="sxs-lookup"><span data-stu-id="f3637-123">The response returned when the Autodiscover request is sent is the same for an internal or an external client.</span></span> <span data-ttu-id="f3637-124">有些位置識別的參數可能會變更。</span><span class="sxs-lookup"><span data-stu-id="f3637-124">Some parameters that are location–aware may change.</span></span> <span data-ttu-id="f3637-125">如果接收到用戶端要求，但是實際的集區不是已連接的集區，則會為該使用者設定使用者的主集區。</span><span class="sxs-lookup"><span data-stu-id="f3637-125">If a client request is received, but the actual pool is other than the one that has been contacted, the user’s home pool will be set for that user.</span></span> <span data-ttu-id="f3637-126">如果同事的使用者帳戶位於不同的集區，但從相同的 office 登入，將會稍有不同的回應。</span><span class="sxs-lookup"><span data-stu-id="f3637-126">A colleague whose user account is on a different pool, but logging in from the same office, would get a slightly different response.</span></span> <span data-ttu-id="f3637-127">回應會指出正確的前端伺服器或該使用者的前端集區。</span><span class="sxs-lookup"><span data-stu-id="f3637-127">The response indicates the correct Front End Server or Front End pool for that user.</span></span>

<span data-ttu-id="f3637-128">自動探索回應檔的範例：</span><span class="sxs-lookup"><span data-stu-id="f3637-128">An example of an Autodiscover Response document:</span></span>

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

## <a name="autodiscover-response-document-details"></a><span data-ttu-id="f3637-129">自動探索回應檔詳細資料</span><span class="sxs-lookup"><span data-stu-id="f3637-129">Autodiscover Response Document Details</span></span>

<span data-ttu-id="f3637-130">自動探索回應檔可以是兩種格式的其中一種。</span><span class="sxs-lookup"><span data-stu-id="f3637-130">The Autodiscover Response document can be in one of two formats.</span></span> <span data-ttu-id="f3637-131">預設格式為 JavaScript 物件標記法 (JSON) 。</span><span class="sxs-lookup"><span data-stu-id="f3637-131">The default format is a JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="f3637-132">另一種格式是可擴展標記語言 (XML) 檔。</span><span class="sxs-lookup"><span data-stu-id="f3637-132">The other format is extensible markup language (XML) document.</span></span> <span data-ttu-id="f3637-133">此範例會使用 XML。</span><span class="sxs-lookup"><span data-stu-id="f3637-133">The XML is used for this example.</span></span> <span data-ttu-id="f3637-134">要求和回應是可預測的，因為檔具有決定格式的定義架構。</span><span class="sxs-lookup"><span data-stu-id="f3637-134">The request and response are predictable because the document has a defined schema that determines the format.</span></span> <span data-ttu-id="f3637-135">檔中描述所用架構的行是要求或回應中的第一行：</span><span class="sxs-lookup"><span data-stu-id="f3637-135">The line in the document that describes the schema used is the first line in the request or response:</span></span>

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

<span data-ttu-id="f3637-136">**AccessLocation = "External"** 的定義表示來自外部使用者的要求。</span><span class="sxs-lookup"><span data-stu-id="f3637-136">The definition of **AccessLocation=”External”** indicates that the request was made from an external user.</span></span>

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

<span data-ttu-id="f3637-137">目前未使用 SipServerInternalAccess 和 SipServerExternalAccess。</span><span class="sxs-lookup"><span data-stu-id="f3637-137">SipServerInternalAccess and SipServerExternalAccess are currently not used.</span></span> <span data-ttu-id="f3637-138">這些專案會保留以供日後使用。</span><span class="sxs-lookup"><span data-stu-id="f3637-138">These entries are reserved for future use.</span></span>

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

<span data-ttu-id="f3637-139">SipClientInternalAccess 和 SipClientExternalAccess 描述內部或外部用戶端用來存取定義的 SIP 伺服器的完整功能變數名稱和埠。</span><span class="sxs-lookup"><span data-stu-id="f3637-139">SipClientInternalAccess and SipClientExternalAccess describe the fully qualified domain name and port that an internal or external client will use to access the defined SIP Server.</span></span> <span data-ttu-id="f3637-140">Lync 桌面用戶端和 Lync Windows Store 應用程式會根據其位置 (內部或外部) 來使用這些專案，以找出 Director 或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="f3637-140">The Lync desktop client and the Lync Windows Store app use these entries, based on their location (internal or external) to find the Director or Front End Server.</span></span>

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

<span data-ttu-id="f3637-141">`Autodiscover`參考資料包含自動探索服務的服務進入點。</span><span class="sxs-lookup"><span data-stu-id="f3637-141">The `Autodiscover` references contain the service entry points for the Autodiscover service.</span></span> <span data-ttu-id="f3637-142">Token 屬性包含服務的名稱，而 href 是定義可找到服務之用戶端的 URL。</span><span class="sxs-lookup"><span data-stu-id="f3637-142">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="f3637-143">外部網路上的用戶端使用 `External/Autodiscover` 。</span><span class="sxs-lookup"><span data-stu-id="f3637-143">Clients on an external network use the `External/Autodiscover`.</span></span> <span data-ttu-id="f3637-144">自動探索服務會安裝為部署程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="f3637-144">The Autodiscover service is installed as part of the deployment process.</span></span> <span data-ttu-id="f3637-145">`Internal/Autodiscover` 目前未使用，且保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="f3637-145">`Internal/Autodiscover` is not currently used, and is reserved for future use.</span></span>

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

<span data-ttu-id="f3637-146">`AuthBroker`參考資料包含內部及外部驗證代理程式服務的服務進入點，在此情況下為 sip .svc。</span><span class="sxs-lookup"><span data-stu-id="f3637-146">The `AuthBroker` references contain the service entry points for the internal and the external authentication broker service, in this case, sip.svc.</span></span> <span data-ttu-id="f3637-147">Token 屬性包含服務的名稱，而 href 是定義可找到服務之用戶端的 URL。</span><span class="sxs-lookup"><span data-stu-id="f3637-147">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="f3637-148">內部網路上使用的用戶端 `Internal/AuthBroker` 。</span><span class="sxs-lookup"><span data-stu-id="f3637-148">Clients on the internal network with use `Internal/AuthBroker`.</span></span> <span data-ttu-id="f3637-149">外部網路上的用戶端使用 `External/AuthBroker` 。</span><span class="sxs-lookup"><span data-stu-id="f3637-149">Clients on an external network use the `External/AuthBroker`.</span></span> <span data-ttu-id="f3637-150">AuthBroker 服務會安裝為內部 Lync Server 2013 部署 web 服務之部署程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="f3637-150">The AuthBroker service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

<span data-ttu-id="f3637-151">`WebScheduler`權杖會參考用戶端存取的 URLs，以供 Lync Server 會議以 web 為基礎的排程。</span><span class="sxs-lookup"><span data-stu-id="f3637-151">The `WebScheduler` token references the URLs for client access to the web-based scheduling for Lync Server conferences.</span></span> <span data-ttu-id="f3637-152">目前只 `External/WebScheduler` 會使用。</span><span class="sxs-lookup"><span data-stu-id="f3637-152">Currently, only the `External/WebScheduler` is used.</span></span> <span data-ttu-id="f3637-153">WebScheduler 安裝為內部 Lync Server 2013 部署 web 服務部署程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="f3637-153">The WebScheduler is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

<span data-ttu-id="f3637-154">`Internal/Mcx` 而且， `External/Mcx` 也就是 Lync Server 2010 的累計更新所引進的行動服務位置：11月2011。</span><span class="sxs-lookup"><span data-stu-id="f3637-154">`Internal/Mcx` and `External/Mcx` are the locations of the Mobility services, introduced in Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="f3637-155">在所有支援的裝置上，Lync 2010 Mobile 會繼續使用這些參考。</span><span class="sxs-lookup"><span data-stu-id="f3637-155">These references will continue to be used by Lync 2010 Mobile on all supported devices.</span></span> <span data-ttu-id="f3637-156">Mcx 服務會安裝為內部 Lync Server 2013 部署 web 服務之部署程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="f3637-156">The Mcx service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

<span data-ttu-id="f3637-157">**Internal/Ucwa**、 **External/Ucwa** 和 **Ucwa** 提供一種方法，讓用戶端存取整合通訊 Web 應用程式程式設計介面 (Ucwa API 或僅僅是 Ucwa) 。</span><span class="sxs-lookup"><span data-stu-id="f3637-157">**Internal/Ucwa**, **External/Ucwa** and **Ucwa** provide a means for clients to access the Unified Communications Web Application Programming Interface (UCWA API, or simply UCWA).</span></span> <span data-ttu-id="f3637-158">`Internal/Ucwa` 和 `External/Ucwa` 虛擬目錄是保留以供未來功能增強使用的訪問點，不會使用。</span><span class="sxs-lookup"><span data-stu-id="f3637-158">`Internal/Ucwa` and `External/Ucwa` virtual directories are access points reserved for future feature enhancement, and are not used.</span></span> <span data-ttu-id="f3637-159">`Ucwa`虛擬目錄用於 Microsoft Lync Mobile (引進于所有支援的裝置上的 Lync Server 2013) 。</span><span class="sxs-lookup"><span data-stu-id="f3637-159">The `Ucwa` virtual directory is used for Microsoft Lync Mobile (introduced with Lync Server 2013) on all supported devices.</span></span> <span data-ttu-id="f3637-160">UCWA 服務會安裝為內部 Lync Server 2013 部署 web 服務之部署程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="f3637-160">The UCWA service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

<span data-ttu-id="f3637-161">`Internal/XFrame`、 **External/XFrame** 及 **XFrame** 提供 UCWA 型伺服器應用程式的存取權。</span><span class="sxs-lookup"><span data-stu-id="f3637-161">`Internal/XFrame`, **External/XFrame** and **XFrame** provide access for UCWA-based server applications.</span></span> <span data-ttu-id="f3637-162">XFrame 已安裝為內部 Lync Server 2013 部署 web 服務之部署程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="f3637-162">XFrame is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

<span data-ttu-id="f3637-163">`Self`權杖是指用戶端 (使用者回應類型) 進行要求的特定資訊。</span><span class="sxs-lookup"><span data-stu-id="f3637-163">The `Self` token refers to information specific to the client (user response type) that is making the request.</span></span> <span data-ttu-id="f3637-164">進行此要求的用戶端為外部用戶端，此自動探索參考是自動探索服務的使用者部分。</span><span class="sxs-lookup"><span data-stu-id="f3637-164">The client that made this request was external, and this Autodiscover reference is to the user portion of the Autodiscover service.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f3637-165">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f3637-165">See Also</span></span>


[<span data-ttu-id="f3637-166">Lync Server 2013 之外部使用者存取元件的系統需求</span><span class="sxs-lookup"><span data-stu-id="f3637-166">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[<span data-ttu-id="f3637-167">在 Lync Server 2013 中規劃自動探索</span><span class="sxs-lookup"><span data-stu-id="f3637-167">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

