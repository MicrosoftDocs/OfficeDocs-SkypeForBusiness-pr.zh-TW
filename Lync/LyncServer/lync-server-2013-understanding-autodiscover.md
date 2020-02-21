---
title: Lync Server 2013： 了解自動探索
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
ms.openlocfilehash: edaa9a938fe893ebca6f4e8abee4a3f41d1527dc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-autodiscover-in-lync-server-2013"></a><span data-ttu-id="3967e-102">了解在 Lync Server 2013 中的自動探索</span><span class="sxs-lookup"><span data-stu-id="3967e-102">Understanding Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3967e-103">_**上次修改主題：** 2013年-06-03_</span><span class="sxs-lookup"><span data-stu-id="3967e-103">_**Topic Last Modified:** 2013-06-03_</span></span>

<span data-ttu-id="3967e-104">Lync Server 2013 自動探索服務是一種功能，原本 Microsoft Lync Server 2010 中引進一部分的 Lync Server 2010 累計更新： 2011 年 11 月。</span><span class="sxs-lookup"><span data-stu-id="3967e-104">The Lync Server 2013 Autodiscover Service is a feature that was originally introduced in Microsoft Lync Server 2010 as part of the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="3967e-105">修正程式，除了這個累計更新會傳遞 Lync Mobile 和 Lync 2013 用戶端的支援。</span><span class="sxs-lookup"><span data-stu-id="3967e-105">In addition to fixes, this cumulative update delivered support for Lync Mobile and Lync 2013 clients.</span></span>

<span data-ttu-id="3967e-106">在 Lync Server 2013 中，自動探索服務的外部及內部行動用戶端，作業不可或缺的一部分，自動探索也會延伸至新的用戶端，例如 Windows 8 的最近引進 Lync Windows 市集應用程式。</span><span class="sxs-lookup"><span data-stu-id="3967e-106">In Lync Server 2013, the Autodiscover Service is an integral part of the operation of external and internal mobile clients, and Autodiscover is also extended to new clients, such as the recently introduced Lync Windows Store app for Windows 8.</span></span> <span data-ttu-id="3967e-107">Lync 2013 桌面用戶端也會使用自動探索。</span><span class="sxs-lookup"><span data-stu-id="3967e-107">Autodiscover is also used by the Lync 2013 desktop clients.</span></span> <span data-ttu-id="3967e-108">自動探索會辨識在 Lync 伺服器所需的網域名稱系統 (DNS) 記錄**lyncdiscover。\<網域\>** 和**lyncdiscoverinternal。\<網域\>**。</span><span class="sxs-lookup"><span data-stu-id="3967e-108">Autodiscover is recognized in Lync Server by the required domain name system (DNS) records **lyncdiscover.\<domain\>** and **lyncdiscoverinternal.\<domain\>**.</span></span> <span data-ttu-id="3967e-109">此外，較新版本的 Lync 2010 和 Lync 2013 桌面用戶端的偏好自動探索網域名稱系統 (DNS) SRV 記錄，使用 DNS SRV 記錄，只有當透過 lyncdiscover。\<網域\>或 lyncdiscoverinternal。\<網域\>沒有回應或無法解決。</span><span class="sxs-lookup"><span data-stu-id="3967e-109">Additionally, newer versions of the Lync 2010 and Lync 2013 desktop client prefer Autodiscover over the domain name system (DNS) SRV records, using DNS SRV records only if lyncdiscover.\<domain\> or lyncdiscoverinternal.\<domain\> does not respond or does not resolve.</span></span> <span data-ttu-id="3967e-110">適用於 Windows 8 和 Lync Mobile Lync Windows 市集應用程式以獨佔模式使用自動探索，而且不會參照傳統 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="3967e-110">The Lync Windows Store app for Windows 8 and Lync Mobile uses Autodiscover exclusively and will not refer to the traditional DNS SRV records.</span></span>

<span data-ttu-id="3967e-111">在 Lync Server 2013 中，自動探索會擴充為用戶端的項目、 功能及通訊方法，可使用的用戶端進行通訊。</span><span class="sxs-lookup"><span data-stu-id="3967e-111">In Lync Server 2013, Autodiscover is expanded to communicate to the client which elements, features, and communication methods are available to the client.</span></span> <span data-ttu-id="3967e-112">資訊傳達透過用戶端上，從傳送要求，並命名項目定義明確回應 Lync Server web 服務回應可供用戶端，以及如何連絡這些功能的格式為自動探索回應文件。</span><span class="sxs-lookup"><span data-stu-id="3967e-112">The information is communicated through a request that is sent from the client, and the Lync Server web services responds with a clearly defined response that names what is available to the client, and how to contact those features in the format of the Autodiscover Response document.</span></span>

<span data-ttu-id="3967e-113">若要了解自動探索回應文件，包括 web 服務的用戶端中，透過此文件的功能的通訊方式的最佳方式是仔細分析，並在 [從 Lync web 服務自動探索回應的文件的一般回應中定義每一行。</span><span class="sxs-lookup"><span data-stu-id="3967e-113">The best way to understand the Autodiscover response document, including how the web services communicate features to clients through this document, is to dissect and define each line in a typical response from the Lync web service Autodiscover response document.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="3967e-114">在巨集中接續的詳細資訊，使用者已經至主伺服器驗證所回應驗證要求。</span><span class="sxs-lookup"><span data-stu-id="3967e-114">In the details that follow, the user has already authenticated to the home server by responding to an authentication request.</span></span>



</div>

<div class="">


> [!NOTE]  
> <span data-ttu-id="3967e-115"><STRONG>開放規格</STRONG>] 區段中的<STRONG>Microsoft Developer Network</STRONG> (MSDN) 程式庫中的<STRONG>Microsoft Office 通訊協定</STRONG>中定義 Lync 自動探索 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="3967e-115">The Lync Autodiscover Web Service is defined in the <STRONG>Microsoft Office Protocols</STRONG> in the <STRONG>Open Specifications</STRONG> section of the <STRONG>Microsoft Developer Network</STRONG> (MSDN) library.</span></span> <span data-ttu-id="3967e-116">如需詳細資訊，請參閱完整規格文件中，「 Lync 自動探索 Web 服務通訊協定，「: <A href="https://go.microsoft.com/fwlink/?linkid=273839">https://go.microsoft.com/fwlink/?LinkId=273839</A>。</span><span class="sxs-lookup"><span data-stu-id="3967e-116">For details, see the full specification document, "Lync Autodiscover Web Service Protocol," at: <A href="https://go.microsoft.com/fwlink/?linkid=273839">https://go.microsoft.com/fwlink/?LinkId=273839</A>.</span></span> <span data-ttu-id="3967e-117">如需驗證的詳細資訊，請參閱 「 OC 驗證 Web 服務通訊協定" <A href="https://go.microsoft.com/fwlink/?linkid=279015">https://go.microsoft.com/fwlink/?LinkId=279015</A>。</span><span class="sxs-lookup"><span data-stu-id="3967e-117">For details about authentication, see "OC Authentication Web Service Protocol" at <A href="https://go.microsoft.com/fwlink/?linkid=279015">https://go.microsoft.com/fwlink/?LinkId=279015</A>.</span></span>



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a><span data-ttu-id="3967e-118">Lync Server Web 服務自動探索回應</span><span class="sxs-lookup"><span data-stu-id="3967e-118">The Lync Server Web Service Autodiscover Response</span></span>

<span data-ttu-id="3967e-119">傳回傳送自動探索要求時的回應是相同的內部或外部的用戶端。</span><span class="sxs-lookup"><span data-stu-id="3967e-119">The response returned when the Autodiscover request is sent is the same for an internal or an external client.</span></span> <span data-ttu-id="3967e-120">位置 – 知道一些參數可能會變更。</span><span class="sxs-lookup"><span data-stu-id="3967e-120">Some parameters that are location–aware may change.</span></span> <span data-ttu-id="3967e-121">如果收到用戶端要求時，但實際的集區是已連絡以外，使用者的主集區會設定為該使用者。</span><span class="sxs-lookup"><span data-stu-id="3967e-121">If a client request is received, but the actual pool is other than the one that has been contacted, the user’s home pool will be set for that user.</span></span> <span data-ttu-id="3967e-122">使用者帳戶是另一個集區，但從相同的 office，登入同事會取得稍有不同的回應。</span><span class="sxs-lookup"><span data-stu-id="3967e-122">A colleague whose user account is on a different pool, but logging in from the same office, would get a slightly different response.</span></span> <span data-ttu-id="3967e-123">回應指出正確的前端伺服器或前端集區，為該使用者。</span><span class="sxs-lookup"><span data-stu-id="3967e-123">The response indicates the correct Front End Server or Front End pool for that user.</span></span>

<span data-ttu-id="3967e-124">自動探索回應文件的範例：</span><span class="sxs-lookup"><span data-stu-id="3967e-124">An example of an Autodiscover Response document:</span></span>

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

## <a name="autodiscover-response-document-details"></a><span data-ttu-id="3967e-125">自動探索回應文件詳細資料</span><span class="sxs-lookup"><span data-stu-id="3967e-125">Autodiscover Response Document Details</span></span>

<span data-ttu-id="3967e-126">自動探索回應文件可以是下列兩種格式。</span><span class="sxs-lookup"><span data-stu-id="3967e-126">The Autodiscover Response document can be in one of two formats.</span></span> <span data-ttu-id="3967e-127">預設的格式是 JavaScript Object Notation (JSON)。</span><span class="sxs-lookup"><span data-stu-id="3967e-127">The default format is a JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="3967e-128">其他格式為 「 可延伸標記語言 (XML) 的文件。</span><span class="sxs-lookup"><span data-stu-id="3967e-128">The other format is extensible markup language (XML) document.</span></span> <span data-ttu-id="3967e-129">本範例會使用 XML。</span><span class="sxs-lookup"><span data-stu-id="3967e-129">The XML is used for this example.</span></span> <span data-ttu-id="3967e-130">要求和回應都可預測，因為文件有定義的結構描述會決定格式。</span><span class="sxs-lookup"><span data-stu-id="3967e-130">The request and response are predictable because the document has a defined schema that determines the format.</span></span> <span data-ttu-id="3967e-131">說明使用的結構描述的文件中的一行是要求或回應中的第一行：</span><span class="sxs-lookup"><span data-stu-id="3967e-131">The line in the document that describes the schema used is the first line in the request or response:</span></span>

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

<span data-ttu-id="3967e-132">定義**AccessLocation = 「 外部 」** 指出要求已從外部使用者進行。</span><span class="sxs-lookup"><span data-stu-id="3967e-132">The definition of **AccessLocation=”External”** indicates that the request was made from an external user.</span></span>

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

<span data-ttu-id="3967e-133">SipServerInternalAccess 和 SipServerExternalAccess 目前未使用。</span><span class="sxs-lookup"><span data-stu-id="3967e-133">SipServerInternalAccess and SipServerExternalAccess are currently not used.</span></span> <span data-ttu-id="3967e-134">這些項目會保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="3967e-134">These entries are reserved for future use.</span></span>

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

<span data-ttu-id="3967e-135">SipClientInternalAccess 和 SipClientExternalAccess 說明的完整的網域名稱和內部或外部用戶端用來存取已定義的 SIP 伺服器的連接埠。</span><span class="sxs-lookup"><span data-stu-id="3967e-135">SipClientInternalAccess and SipClientExternalAccess describe the fully qualified domain name and port that an internal or external client will use to access the defined SIP Server.</span></span> <span data-ttu-id="3967e-136">Lync 桌面用戶端和 Lync Windows 市集應用程式會使用這些項目，根據其位置 （內部或外部），可尋找 Director 或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="3967e-136">The Lync desktop client and the Lync Windows Store app use these entries, based on their location (internal or external) to find the Director or Front End Server.</span></span>

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

<span data-ttu-id="3967e-137">`Autodiscover`參考包含了自動探索服務的服務進入點。</span><span class="sxs-lookup"><span data-stu-id="3967e-137">The `Autodiscover` references contain the service entry points for the Autodiscover service.</span></span> <span data-ttu-id="3967e-138">語彙基元屬性包含名稱的服務，且 href 定義為用戶端的 URL 可以找到此服務。</span><span class="sxs-lookup"><span data-stu-id="3967e-138">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="3967e-139">在外部網路使用的用戶端`External/Autodiscover`。</span><span class="sxs-lookup"><span data-stu-id="3967e-139">Clients on an external network use the `External/Autodiscover`.</span></span> <span data-ttu-id="3967e-140">自動探索服務會安裝做為部署程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="3967e-140">The Autodiscover service is installed as part of the deployment process.</span></span> <span data-ttu-id="3967e-141">`Internal/Autodiscover`目前不使用，並保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="3967e-141">`Internal/Autodiscover` is not currently used, and is reserved for future use.</span></span>

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

<span data-ttu-id="3967e-142">`AuthBroker`參考包含了服務項目指向的內部和外部驗證代理人服務] 中，在此情況下，sip.svc。</span><span class="sxs-lookup"><span data-stu-id="3967e-142">The `AuthBroker` references contain the service entry points for the internal and the external authentication broker service, in this case, sip.svc.</span></span> <span data-ttu-id="3967e-143">語彙基元屬性包含名稱的服務，且 href 定義為用戶端的 URL 可以找到此服務。</span><span class="sxs-lookup"><span data-stu-id="3967e-143">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="3967e-144">使用內部網路上的用戶端`Internal/AuthBroker`。</span><span class="sxs-lookup"><span data-stu-id="3967e-144">Clients on the internal network with use `Internal/AuthBroker`.</span></span> <span data-ttu-id="3967e-145">在外部網路使用的用戶端`External/AuthBroker`。</span><span class="sxs-lookup"><span data-stu-id="3967e-145">Clients on an external network use the `External/AuthBroker`.</span></span> <span data-ttu-id="3967e-146">AuthBroker 服務會安裝您的內部 Lync Server 2013 部署 web 服務的部署程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="3967e-146">The AuthBroker service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

<span data-ttu-id="3967e-147">`WebScheduler`語彙基元所參考的用戶端存取 web 型排程 Lync Server 會議的 Url。</span><span class="sxs-lookup"><span data-stu-id="3967e-147">The `WebScheduler` token references the URLs for client access to the web-based scheduling for Lync Server conferences.</span></span> <span data-ttu-id="3967e-148">目前，只有`External/WebScheduler`使用。</span><span class="sxs-lookup"><span data-stu-id="3967e-148">Currently, only the `External/WebScheduler` is used.</span></span> <span data-ttu-id="3967e-149">WebScheduler 安裝成您的內部 Lync Server 2013 部署 web 服務的部署程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="3967e-149">The WebScheduler is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

<span data-ttu-id="3967e-150">`Internal/Mcx`及`External/Mcx`是行動性服務，在 Lync Server 2010 的累計更新中引入的位置： 2011 年 11 月。</span><span class="sxs-lookup"><span data-stu-id="3967e-150">`Internal/Mcx` and `External/Mcx` are the locations of the Mobility services, introduced in Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="3967e-151">這些參考將會繼續可供所有支援的裝置上的 Lync 2010 Mobile。</span><span class="sxs-lookup"><span data-stu-id="3967e-151">These references will continue to be used by Lync 2010 Mobile on all supported devices.</span></span> <span data-ttu-id="3967e-152">Mcx 服務會安裝您的內部 Lync Server 2013 部署 web 服務的部署程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="3967e-152">The Mcx service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

<span data-ttu-id="3967e-153">**內部 /ucwa**、**外部 /ucwa**和**ucwa 的參考**可提供用戶端存取整合通訊 Web 應用程式發展介面 （UCWA API 或只是 UCWA） 方法。</span><span class="sxs-lookup"><span data-stu-id="3967e-153">**Internal/Ucwa**, **External/Ucwa** and **Ucwa** provide a means for clients to access the Unified Communications Web Application Programming Interface (UCWA API, or simply UCWA).</span></span> <span data-ttu-id="3967e-154">`Internal/Ucwa`及`External/Ucwa`虛擬目錄會保留供未來功能增強功能的存取點，並不會使用。</span><span class="sxs-lookup"><span data-stu-id="3967e-154">`Internal/Ucwa` and `External/Ucwa` virtual directories are access points reserved for future feature enhancement, and are not used.</span></span> <span data-ttu-id="3967e-155">`Ucwa`虛擬目錄適用於 Microsoft Lync Mobile （搭配 Lync Server 2013 引進） 的所有支援的裝置。</span><span class="sxs-lookup"><span data-stu-id="3967e-155">The `Ucwa` virtual directory is used for Microsoft Lync Mobile (introduced with Lync Server 2013) on all supported devices.</span></span> <span data-ttu-id="3967e-156">UCWA 服務會安裝您的內部 Lync Server 2013 部署 web 服務的部署程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="3967e-156">The UCWA service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

<span data-ttu-id="3967e-157">`Internal/XFrame`**外部/XFrame**和**XFrame**提供 UCWA 型伺服器應用程式的存取。</span><span class="sxs-lookup"><span data-stu-id="3967e-157">`Internal/XFrame`, **External/XFrame** and **XFrame** provide access for UCWA-based server applications.</span></span> <span data-ttu-id="3967e-158">XFrame 安裝成您的內部 Lync Server 2013 部署 web 服務的部署程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="3967e-158">XFrame is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

<span data-ttu-id="3967e-159">`Self`權杖是指提出要求的用戶端 （使用者的回應類型） 的特定資訊。</span><span class="sxs-lookup"><span data-stu-id="3967e-159">The `Self` token refers to information specific to the client (user response type) that is making the request.</span></span> <span data-ttu-id="3967e-160">進行這項要求用戶端的外部，且此自動探索參照到自動探索服務的使用者部份。</span><span class="sxs-lookup"><span data-stu-id="3967e-160">The client that made this request was external, and this Autodiscover reference is to the user portion of the Autodiscover service.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3967e-161">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3967e-161">See Also</span></span>


[<span data-ttu-id="3967e-162">Lync Server 2013 的外部使用者存取元件的系統需求</span><span class="sxs-lookup"><span data-stu-id="3967e-162">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[<span data-ttu-id="3967e-163">規劃 Lync Server 2013 中的自動探索</span><span class="sxs-lookup"><span data-stu-id="3967e-163">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

