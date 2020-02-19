---
title: Lync Server 2013： 外部使用者存取的憑證需求
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
ms.openlocfilehash: 0561c2d6b36090a9499abf360373cf0468cdbda8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135269"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="f74e4-102">Lync Server 2013 中的外部使用者存取的憑證需求</span><span class="sxs-lookup"><span data-stu-id="f74e4-102">Certificate requirements for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f74e4-103">_**主題上次修改日期：** 2016年-03-29_</span><span class="sxs-lookup"><span data-stu-id="f74e4-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="f74e4-104">Microsoft Lync Server 2013 通訊軟體支援單一公用憑證使用的存取權和 web 會議 Edge 外部介面以及 A / V 驗證服務。</span><span class="sxs-lookup"><span data-stu-id="f74e4-104">Microsoft Lync Server 2013 communications software supports the use of a single public certificate for access and web conferencing Edge external interfaces, plus the A/V Authentication service.</span></span> <span data-ttu-id="f74e4-105">Edge 內部介面通常使用內部憑證授權單位 (CA) 所發出的私人憑證，但前提是它是來自受信任的公用 CA，則也可以使用公用憑證。</span><span class="sxs-lookup"><span data-stu-id="f74e4-105">The Edge internal interface typically uses a private certificate issued by an internal certification authority (CA), but can also use a public certificate, provided that it is from a trusted public CA.</span></span> <span data-ttu-id="f74e4-106">您的部署中的反向 proxy 使用公用憑證，並使用 HTTP （亦即傳輸層安全性 over HTTP） 來加密來自反向 proxy 通訊用戶端和反向 proxy 內部伺服器。</span><span class="sxs-lookup"><span data-stu-id="f74e4-106">The reverse proxy in your deployment uses a public certificate and encrypts the communication from the reverse proxy to clients and the reverse proxy to internal servers by using HTTP (that is, Transport Layer Security over HTTP).</span></span>

<span data-ttu-id="f74e4-107">以下是用來存取與 web 會議 Edge 外部介面以及 A 的公用憑證的需求 / V 驗證服務：</span><span class="sxs-lookup"><span data-stu-id="f74e4-107">Following are the requirements for the public certificate used for access and web conferencing Edge external interfaces, and the A/V authentication service:</span></span>

  - <span data-ttu-id="f74e4-108">憑證必須支援主體替代名稱核准公用 CA 所發出。</span><span class="sxs-lookup"><span data-stu-id="f74e4-108">The certificate must be issued by an approved public CA that supports subject alternative name.</span></span> <span data-ttu-id="f74e4-109">如需詳細資訊，請參閱 Microsoft 知識庫文件 929395，「 整合通訊憑證合作夥伴的 Exchange Server 和 Communications Server，" [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)。</span><span class="sxs-lookup"><span data-stu-id="f74e4-109">For details, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

  - <span data-ttu-id="f74e4-110">如果憑證將用於 Edge 集區上，則必須加以建立為可匯出私密金鑰，與 Edge 集區中每部 Edge Server 上使用的同一個憑證。</span><span class="sxs-lookup"><span data-stu-id="f74e4-110">If the certificate will be used on an Edge pool, it must be created as exportable, with the same certificate used on each Edge Server in the Edge pool.</span></span> <span data-ttu-id="f74e4-111">可匯出私密金鑰的重要需求是基於的 A / V 驗證服務，必須跨所有 Edge Server 集區中使用相同的私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="f74e4-111">The exportable private key requirement is for the purposes of the A/V Authentication service, which must use the same private key across all Edge Servers in the pool.</span></span>

  - <span data-ttu-id="f74e4-112">如果您要最大化音訊/視訊服務的執行時間，請檢閱實作低耦合的憑證需求 A / V Edge service 憑證 (也就是個別的 A / V Edge service 憑證從其他外部邊緣憑證用途)。</span><span class="sxs-lookup"><span data-stu-id="f74e4-112">If you want to maximize the uptime for your Audio/Video services, review the certificate requirements for implementing a decoupled A/V Edge service certificate (that is, a separate A/V Edge service certificate from the other External Edge certificate purposes).</span></span> <span data-ttu-id="f74e4-113">如需詳細資訊，請參閱[影響 Edge Server 規劃的 Lync Server 2013 中變更](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)、 [Lync Server 2013 中的 Edge Server 憑證的計劃](lync-server-2013-plan-for-edge-server-certificates.md)和[Lync Server 2013 中的預備 AV 與 OAuth 憑證使用-Roll 在 Set-cscertificate 中](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)。</span><span class="sxs-lookup"><span data-stu-id="f74e4-113">For details, see [Changes in Lync Server 2013 that affect Edge Server planning](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [Plan for Edge Server certificates in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) and [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span></span>

  - <span data-ttu-id="f74e4-114">憑證的主體名稱是 Access Edge service 外部介面完整的網域名稱 (FQDN) 或硬體負載平衡器 VIP (例如，access.contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="f74e4-114">The subject name of the certificate is the Access Edge service external interface fully qualified domain name (FQDN) or hardware load balancer VIP (for example, access.contoso.com).</span></span> <span data-ttu-id="f74e4-115">).</span><span class="sxs-lookup"><span data-stu-id="f74e4-115">).</span></span> <span data-ttu-id="f74e4-116">主體名稱不能有萬用字元，它必須是明確的名稱。</span><span class="sxs-lookup"><span data-stu-id="f74e4-116">The subject name can’t have a wildcard character, it must be an explicit name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f74e4-117">Lync Server 2013 中，這已不再是必要條件，但仍建議與 Office Communications Server 的相容性。</span><span class="sxs-lookup"><span data-stu-id="f74e4-117">For Lync Server 2013, this is no longer a requirement, but it is still recommended for compatibility with Office Communications Server.</span></span>

    
    </div>

  - <span data-ttu-id="f74e4-118">主體替代名稱清單包含下列 Fqdn:</span><span class="sxs-lookup"><span data-stu-id="f74e4-118">The subject alternative name list contains the FQDNs of the following:</span></span>
    
      - <span data-ttu-id="f74e4-119">Access Edge service 外部介面或硬體負載平衡器 VIP (例如 sip.contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="f74e4-119">The Access Edge service external interface or hardware load balancer VIP (for example, sip.contoso.com).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f74e4-120">即使憑證主體名稱相當於存取 Edge FQDN，主體替代名稱也必須包含存取 Edge FQDN 因為傳輸層安全性 (TLS) 會忽略主體名稱，並使用的主體替代名稱項目驗證。</span><span class="sxs-lookup"><span data-stu-id="f74e4-120">Even though the certificate subject name is equal to the access Edge FQDN, the subject alternative name must also contain the access Edge FQDN because Transport Layer Security (TLS) ignores the subject name and uses the subject alternative name entries for validation.</span></span>

        
        </div>
    
      - <span data-ttu-id="f74e4-121">Web 會議 Edge 外部介面或硬體負載平衡器 VIP (例如，webcon.contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="f74e4-121">The web conferencing Edge external interface or hardware load balancer VIP (for example, webcon.contoso.com).</span></span>
    
      - <span data-ttu-id="f74e4-122">如果您使用用戶端自動設定或同盟，也包含任何 SIP 網域 （例如 sip.contoso.com、 sip.fabrikam.com） 公司內使用的 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="f74e4-122">If you are using client auto-configuration or federation, also include any SIP domain FQDNs used within your company (for example, sip.contoso.com, sip.fabrikam.com).</span></span>
    
      - <span data-ttu-id="f74e4-123">A / V Edge service 不會使用主體名稱或主體替代名稱項目。</span><span class="sxs-lookup"><span data-stu-id="f74e4-123">The A/V Edge service does not use the subject name or the subject alternative names entries.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f74e4-124">在主體替代名稱清單中 Fqdn 的順序不拘。</span><span class="sxs-lookup"><span data-stu-id="f74e4-124">The order of the FQDNs in the subject alternative names list does not matter.</span></span>

    
    </div>

<span data-ttu-id="f74e4-125">如果您要部署多個、 負載平衡 Edge Server，在網站、 A / V 驗證服務的憑證安裝在每部 Edge Server 上必須從同一個 CA，且必須使用相同的私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="f74e4-125">If you are deploying multiple, load-balanced Edge Servers at a site, the A/V authentication service certificate that is installed on each Edge Server must be from the same CA and must use the same private key.</span></span> <span data-ttu-id="f74e4-126">請注意，憑證的私密金鑰必須可匯出私密金鑰，不論是否在一部 Edge Server 或多個 Edge Server 上使用。</span><span class="sxs-lookup"><span data-stu-id="f74e4-126">Note that the certificate's private key must be exportable, regardless of whether it is used on one Edge Server or many Edge Servers.</span></span> <span data-ttu-id="f74e4-127">它也必須可匯出如果您要求憑證從 Edge Server 以外的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="f74e4-127">It must also be exportable if you request the certificate from any computer other than the Edge Server.</span></span> <span data-ttu-id="f74e4-128">因為 A / V 驗證服務不會使用主體名稱或主體替代名稱，您可以重複使用邊緣憑證，只要主體名稱與主體別名需求都符合適用於 access Edge 和 web 會議 Edge 的存取權和憑證的私密金鑰為可匯出。</span><span class="sxs-lookup"><span data-stu-id="f74e4-128">Because the A/V authentication service does not use the subject name or subject alternative name, you can reuse the access Edge certificate as long as the subject name and subject alternative name requirements are met for the access Edge and the web conferencing Edge and the certificate’s private key is exportable.</span></span>

<span data-ttu-id="f74e4-129">用於 Edge 內部介面的私人 （或公用） 憑證的需求如下所示：</span><span class="sxs-lookup"><span data-stu-id="f74e4-129">Requirements for the private (or public) certificate used for the Edge internal interface are as follows:</span></span>

  - <span data-ttu-id="f74e4-130">憑證可以由內部 CA 或認可的公用憑證 CA 發行。</span><span class="sxs-lookup"><span data-stu-id="f74e4-130">The certificate can be issued by an internal CA or an approved public certificate CA.</span></span>

  - <span data-ttu-id="f74e4-131">憑證的主體名稱通常是 Edge 內部介面 FQDN 或硬體負載平衡器 VIP (例如，lsedge.contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="f74e4-131">The subject name of the certificate is typically the Edge internal interface FQDN or hardware load balancer VIP (for example, lsedge.contoso.com).</span></span> <span data-ttu-id="f74e4-132">不過，您可以使用萬用字元憑證上的內部邊緣。</span><span class="sxs-lookup"><span data-stu-id="f74e4-132">However, you can use a wildcard certificate on the Edge internal.</span></span>

  - <span data-ttu-id="f74e4-133">需要沒有主體替代名稱清單。</span><span class="sxs-lookup"><span data-stu-id="f74e4-133">No subject alternative name list is required.</span></span>

<span data-ttu-id="f74e4-134">您的部署中的反向 proxy 服務要求：</span><span class="sxs-lookup"><span data-stu-id="f74e4-134">The reverse proxy in your deployment services requests for:</span></span>

  - <span data-ttu-id="f74e4-135">外部使用者存取會議的會議內容</span><span class="sxs-lookup"><span data-stu-id="f74e4-135">External user access to meeting content for meetings</span></span>

  - <span data-ttu-id="f74e4-136">外部使用者存取展開並顯示通訊群組的成員</span><span class="sxs-lookup"><span data-stu-id="f74e4-136">External user access to expand and display members of distribution groups</span></span>

  - <span data-ttu-id="f74e4-137">可下載的檔案從通訊錄服務的外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="f74e4-137">External user access to downloadable files from the Address Book Service</span></span>

  - <span data-ttu-id="f74e4-138">Lync Web App 用戶端的外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="f74e4-138">External user access to the Lync Web App client</span></span>

  - <span data-ttu-id="f74e4-139">電話撥入式會議設定網頁的外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="f74e4-139">External user access to the Dial-in Conferencing Settings web page</span></span>

  - <span data-ttu-id="f74e4-140">外部使用者存取位置資訊服務</span><span class="sxs-lookup"><span data-stu-id="f74e4-140">External user access to the Location Information Service</span></span>

  - <span data-ttu-id="f74e4-141">外部裝置存取裝置更新服務並取得更新</span><span class="sxs-lookup"><span data-stu-id="f74e4-141">External device access to the Device Update Service and obtain updates</span></span>

<span data-ttu-id="f74e4-142">反向 proxy 發佈的內部伺服器 Web 元件 Url。</span><span class="sxs-lookup"><span data-stu-id="f74e4-142">The reverse proxy publishes the internal server Web Components URLs.</span></span> <span data-ttu-id="f74e4-143">Web 元件 Url 會定義 Director、 前端伺服器或前端集區上，為 [拓撲產生器中的**外部 web 服務**。</span><span class="sxs-lookup"><span data-stu-id="f74e4-143">The Web Components URLs are defined on the Director, Front End Server or Front End pool as the **External web services** in Topology Builder.</span></span>

<span data-ttu-id="f74e4-144">指派給反向 proxy 憑證的主體替代名稱欄位支援萬用字元項目。</span><span class="sxs-lookup"><span data-stu-id="f74e4-144">Wildcard entries are supported in the subject alternative name field of the certificate assigned to the reverse proxy.</span></span> <span data-ttu-id="f74e4-145">如需如何設定反向 proxy 的憑證要求的詳細資訊，請參閱[要求並設定憑證以供您在 Lync Server 2013 中的反向 HTTP proxy](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)。</span><span class="sxs-lookup"><span data-stu-id="f74e4-145">For details about how to configure the certificate request for the reverse proxy, see [Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="f74e4-146">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f74e4-146">See Also</span></span>


[<span data-ttu-id="f74e4-147">Lync Server 2013 中的萬用字元憑證支援</span><span class="sxs-lookup"><span data-stu-id="f74e4-147">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

