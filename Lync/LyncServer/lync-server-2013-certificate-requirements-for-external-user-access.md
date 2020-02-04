---
title: Lync Server 2013：外部使用者存取的憑證需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for external user access
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398920(v=OCS.15)
ms:contentKeyID: 48185503
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1b6495dbad5350f94873099985922f1adc198f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="63fe0-102">Lync Server 2013 中的外部使用者存取的憑證需求</span><span class="sxs-lookup"><span data-stu-id="63fe0-102">Certificate requirements for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63fe0-103">_**主題上次修改日期：** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="63fe0-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="63fe0-104">Microsoft Lync Server 2013 通訊軟體支援使用單一公用憑證來存取和網路會議 Edge 外部介面，以及 A/V 驗證服務。</span><span class="sxs-lookup"><span data-stu-id="63fe0-104">Microsoft Lync Server 2013 communications software supports the use of a single public certificate for access and web conferencing Edge external interfaces, plus the A/V Authentication service.</span></span> <span data-ttu-id="63fe0-105">Edge 內部介面通常會使用內部憑證授權單位（CA）所頒發的私人憑證，但是也可以使用公用憑證（前提是它是來自信任的公用 CA）。</span><span class="sxs-lookup"><span data-stu-id="63fe0-105">The Edge internal interface typically uses a private certificate issued by an internal certification authority (CA), but can also use a public certificate, provided that it is from a trusted public CA.</span></span> <span data-ttu-id="63fe0-106">您部署中的反向 proxy 會使用公用憑證，並使用 HTTP （也就是透過 HTTP 傳輸層安全性），將反向 proxy 中的通訊加密到用戶端，以及將反向 proxy 加密到內部伺服器。</span><span class="sxs-lookup"><span data-stu-id="63fe0-106">The reverse proxy in your deployment uses a public certificate and encrypts the communication from the reverse proxy to clients and the reverse proxy to internal servers by using HTTP (that is, Transport Layer Security over HTTP).</span></span>

<span data-ttu-id="63fe0-107">以下是適用于 access 和網路會議 Edge 外部介面以及 A/V 驗證服務的公用憑證需求：</span><span class="sxs-lookup"><span data-stu-id="63fe0-107">Following are the requirements for the public certificate used for access and web conferencing Edge external interfaces, and the A/V authentication service:</span></span>

  - <span data-ttu-id="63fe0-108">憑證必須由支援消費者備用名稱的核准公用 CA 頒發。</span><span class="sxs-lookup"><span data-stu-id="63fe0-108">The certificate must be issued by an approved public CA that supports subject alternative name.</span></span> <span data-ttu-id="63fe0-109">如需詳細資訊，請參閱 Microsoft 知識庫文章929395、「Exchange Server 的整合通訊憑證合作夥伴和通訊伺服器」 [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)。</span><span class="sxs-lookup"><span data-stu-id="63fe0-109">For details, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

  - <span data-ttu-id="63fe0-110">如果要在 Edge 池中使用憑證，必須將它建立為可匯出，並在 Edge 池中的每個邊緣伺服器上使用相同的憑證。</span><span class="sxs-lookup"><span data-stu-id="63fe0-110">If the certificate will be used on an Edge pool, it must be created as exportable, with the same certificate used on each Edge Server in the Edge pool.</span></span> <span data-ttu-id="63fe0-111">可匯出的私密金鑰需求是針對 A/V 驗證服務的用途，必須在整個池中的所有邊緣伺服器上使用相同的私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="63fe0-111">The exportable private key requirement is for the purposes of the A/V Authentication service, which must use the same private key across all Edge Servers in the pool.</span></span>

  - <span data-ttu-id="63fe0-112">如果您想要最大化音訊/視頻服務的正常執行時間，請參閱實現已分離的 A/V 邊緣服務憑證（也就是與其他外部邊緣憑證用途不同的 A/V 邊緣服務憑證）的憑證需求。</span><span class="sxs-lookup"><span data-stu-id="63fe0-112">If you want to maximize the uptime for your Audio/Video services, review the certificate requirements for implementing a decoupled A/V Edge service certificate (that is, a separate A/V Edge service certificate from the other External Edge certificate purposes).</span></span> <span data-ttu-id="63fe0-113">如需詳細資訊，請參閱[Lync server 2013 中的變更，這些變更會影響 Edge 伺服器規劃](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)、在 lync server [2013 中規劃 edge 伺服器憑證](lync-server-2013-plan-for-edge-server-certificates.md)，以及在[lync Server 中暫存 AV 和 OAuth 憑證2013使用 CsCertificate 設定](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)。</span><span class="sxs-lookup"><span data-stu-id="63fe0-113">For details, see [Changes in Lync Server 2013 that affect Edge Server planning](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [Plan for Edge Server certificates in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) and [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span></span>

  - <span data-ttu-id="63fe0-114">憑證的受領人名稱是存取邊緣服務外部介面完整功能變數名稱（FQDN）或硬體負載平衡器 VIP （例如 access.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="63fe0-114">The subject name of the certificate is the Access Edge service external interface fully qualified domain name (FQDN) or hardware load balancer VIP (for example, access.contoso.com).</span></span> <span data-ttu-id="63fe0-115">).</span><span class="sxs-lookup"><span data-stu-id="63fe0-115">).</span></span> <span data-ttu-id="63fe0-116">Subject 名稱不能包含萬用字元，它必須是明確的名稱。</span><span class="sxs-lookup"><span data-stu-id="63fe0-116">The subject name can’t have a wildcard character, it must be an explicit name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="63fe0-117">對於 Lync Server 2013，已不再需要這項功能，但在與 Office 通訊伺服器相容時仍有建議。</span><span class="sxs-lookup"><span data-stu-id="63fe0-117">For Lync Server 2013, this is no longer a requirement, but it is still recommended for compatibility with Office Communications Server.</span></span>

    
    </div>

  - <span data-ttu-id="63fe0-118">[Subject 替換名稱] 清單包含下列的 Fqdn：</span><span class="sxs-lookup"><span data-stu-id="63fe0-118">The subject alternative name list contains the FQDNs of the following:</span></span>
    
      - <span data-ttu-id="63fe0-119">存取邊緣服務外部介面或硬體負載平衡器 VIP （例如，sip.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="63fe0-119">The Access Edge service external interface or hardware load balancer VIP (for example, sip.contoso.com).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="63fe0-120">雖然證書受領人名稱等於存取邊緣 FQDN，但 subject 備用名稱也必須包含存取邊緣 FQDN，因為傳輸層安全性（TLS）會忽略消費者名稱，並使用 subject 替換名稱專案來規則.</span><span class="sxs-lookup"><span data-stu-id="63fe0-120">Even though the certificate subject name is equal to the access Edge FQDN, the subject alternative name must also contain the access Edge FQDN because Transport Layer Security (TLS) ignores the subject name and uses the subject alternative name entries for validation.</span></span>

        
        </div>
    
      - <span data-ttu-id="63fe0-121">網路會議 Edge 外部介面或硬體負載平衡器 VIP （例如，webcon.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="63fe0-121">The web conferencing Edge external interface or hardware load balancer VIP (for example, webcon.contoso.com).</span></span>
    
      - <span data-ttu-id="63fe0-122">如果您使用的是用戶端自動設定或同盟，也包括貴公司內使用的任何 SIP 網域 Fqdn （例如 sip.contoso.com、sip.fabrikam.com）。</span><span class="sxs-lookup"><span data-stu-id="63fe0-122">If you are using client auto-configuration or federation, also include any SIP domain FQDNs used within your company (for example, sip.contoso.com, sip.fabrikam.com).</span></span>
    
      - <span data-ttu-id="63fe0-123">A/V Edge 服務不會使用 [subject 名稱] 或 [subject 替換名稱] 專案。</span><span class="sxs-lookup"><span data-stu-id="63fe0-123">The A/V Edge service does not use the subject name or the subject alternative names entries.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="63fe0-124">[Subject 替換名稱] 清單中的 Fqdn 順序不重要。</span><span class="sxs-lookup"><span data-stu-id="63fe0-124">The order of the FQDNs in the subject alternative names list does not matter.</span></span>

    
    </div>

<span data-ttu-id="63fe0-125">如果您要在網站上部署多個負載平衡的邊緣伺服器，則每個 Edge 伺服器上安裝的 A/V 驗證服務憑證都必須來自同一個 CA，且必須使用相同的私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="63fe0-125">If you are deploying multiple, load-balanced Edge Servers at a site, the A/V authentication service certificate that is installed on each Edge Server must be from the same CA and must use the same private key.</span></span> <span data-ttu-id="63fe0-126">請注意，無論是否在一台邊緣伺服器或多台邊緣伺服器上使用，證書的私密金鑰都必須是可匯出的。</span><span class="sxs-lookup"><span data-stu-id="63fe0-126">Note that the certificate's private key must be exportable, regardless of whether it is used on one Edge Server or many Edge Servers.</span></span> <span data-ttu-id="63fe0-127">如果您要求來自邊緣伺服器以外的任何電腦的憑證，也必須是可匯出的。</span><span class="sxs-lookup"><span data-stu-id="63fe0-127">It must also be exportable if you request the certificate from any computer other than the Edge Server.</span></span> <span data-ttu-id="63fe0-128">因為 A/V 驗證服務不使用 subject 名稱或消費者的替換名稱，所以只要存取邊緣名稱和網路會議 Edge 符合消費者名稱和消費者的替換名稱需求，就可以重複使用 [存取邊緣] 憑證，而證書的私密金鑰則是可匯出的。</span><span class="sxs-lookup"><span data-stu-id="63fe0-128">Because the A/V authentication service does not use the subject name or subject alternative name, you can reuse the access Edge certificate as long as the subject name and subject alternative name requirements are met for the access Edge and the web conferencing Edge and the certificate’s private key is exportable.</span></span>

<span data-ttu-id="63fe0-129">用於 Edge 內部介面的私人（或公用）憑證的需求如下：</span><span class="sxs-lookup"><span data-stu-id="63fe0-129">Requirements for the private (or public) certificate used for the Edge internal interface are as follows:</span></span>

  - <span data-ttu-id="63fe0-130">證書可以由內部 CA 或核准的公用證書 CA 頒發。</span><span class="sxs-lookup"><span data-stu-id="63fe0-130">The certificate can be issued by an internal CA or an approved public certificate CA.</span></span>

  - <span data-ttu-id="63fe0-131">證書的消費者名稱通常是 Edge 內部介面 FQDN 或硬體負載平衡器 VIP （例如 lsedge.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="63fe0-131">The subject name of the certificate is typically the Edge internal interface FQDN or hardware load balancer VIP (for example, lsedge.contoso.com).</span></span> <span data-ttu-id="63fe0-132">不過，您可以在邊緣內部使用萬用字元憑證。</span><span class="sxs-lookup"><span data-stu-id="63fe0-132">However, you can use a wildcard certificate on the Edge internal.</span></span>

  - <span data-ttu-id="63fe0-133">不需要 subject 備用名稱清單。</span><span class="sxs-lookup"><span data-stu-id="63fe0-133">No subject alternative name list is required.</span></span>

<span data-ttu-id="63fe0-134">您的部署服務要求中的反向 proxy：</span><span class="sxs-lookup"><span data-stu-id="63fe0-134">The reverse proxy in your deployment services requests for:</span></span>

  - <span data-ttu-id="63fe0-135">外部使用者存取會議內容的許可權</span><span class="sxs-lookup"><span data-stu-id="63fe0-135">External user access to meeting content for meetings</span></span>

  - <span data-ttu-id="63fe0-136">外部使用者存取權展開及顯示通訊群組的成員</span><span class="sxs-lookup"><span data-stu-id="63fe0-136">External user access to expand and display members of distribution groups</span></span>

  - <span data-ttu-id="63fe0-137">外部使用者從通訊錄服務存取可下載的檔案</span><span class="sxs-lookup"><span data-stu-id="63fe0-137">External user access to downloadable files from the Address Book Service</span></span>

  - <span data-ttu-id="63fe0-138">外部使用者存取 Lync Web App 用戶端的許可權</span><span class="sxs-lookup"><span data-stu-id="63fe0-138">External user access to the Lync Web App client</span></span>

  - <span data-ttu-id="63fe0-139">外部使用者存取電話撥入式會議設定網頁</span><span class="sxs-lookup"><span data-stu-id="63fe0-139">External user access to the Dial-in Conferencing Settings web page</span></span>

  - <span data-ttu-id="63fe0-140">外部使用者存取位置資訊服務的許可權</span><span class="sxs-lookup"><span data-stu-id="63fe0-140">External user access to the Location Information Service</span></span>

  - <span data-ttu-id="63fe0-141">外部裝置存取裝置更新服務和取得更新</span><span class="sxs-lookup"><span data-stu-id="63fe0-141">External device access to the Device Update Service and obtain updates</span></span>

<span data-ttu-id="63fe0-142">反向 proxy 會發佈內部伺服器網頁元件 Url。</span><span class="sxs-lookup"><span data-stu-id="63fe0-142">The reverse proxy publishes the internal server Web Components URLs.</span></span> <span data-ttu-id="63fe0-143">網頁元件 Url 是在主管、前端伺服器或頂層端池上定義，作為拓撲建立器中的**外部 Web 服務**。</span><span class="sxs-lookup"><span data-stu-id="63fe0-143">The Web Components URLs are defined on the Director, Front End Server or Front End pool as the **External web services** in Topology Builder.</span></span>

<span data-ttu-id="63fe0-144">在指派給反向 proxy 的憑證的 [subject 替換名稱] 欄位中，支援萬用字元專案。</span><span class="sxs-lookup"><span data-stu-id="63fe0-144">Wildcard entries are supported in the subject alternative name field of the certificate assigned to the reverse proxy.</span></span> <span data-ttu-id="63fe0-145">如需如何針對反向 proxy 設定證書申請的詳細資料，請參閱[在 Lync Server 2013 中針對您的反向 HTTP Proxy 要求和設定憑證](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)。</span><span class="sxs-lookup"><span data-stu-id="63fe0-145">For details about how to configure the certificate request for the reverse proxy, see [Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="63fe0-146">請參閱</span><span class="sxs-lookup"><span data-stu-id="63fe0-146">See Also</span></span>


[<span data-ttu-id="63fe0-147">Lync Server 2013 中的萬用字元憑證支援</span><span class="sxs-lookup"><span data-stu-id="63fe0-147">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

