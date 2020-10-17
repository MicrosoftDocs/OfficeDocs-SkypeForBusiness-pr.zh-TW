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
ms.openlocfilehash: 37494b3f8389709681ffc92a17d388b71baddd70
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517950"
---
# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="58fcd-102">Lync Server 2013 中外部使用者存取的憑證需求</span><span class="sxs-lookup"><span data-stu-id="58fcd-102">Certificate requirements for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58fcd-103">_**主題上次修改日期：** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="58fcd-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="58fcd-104">Microsoft Lync Server 2013 通訊軟體支援使用單一公用憑證進行存取和 web 會議 Edge 外部介面，以及 A/V 驗證服務。</span><span class="sxs-lookup"><span data-stu-id="58fcd-104">Microsoft Lync Server 2013 communications software supports the use of a single public certificate for access and web conferencing Edge external interfaces, plus the A/V Authentication service.</span></span> <span data-ttu-id="58fcd-105">Edge 內部介面一般會使用內部憑證授權單位單位 (CA) 所發行的私人憑證，但也可以使用公用憑證，但前提是該憑證來自于信任的公用 CA。</span><span class="sxs-lookup"><span data-stu-id="58fcd-105">The Edge internal interface typically uses a private certificate issued by an internal certification authority (CA), but can also use a public certificate, provided that it is from a trusted public CA.</span></span> <span data-ttu-id="58fcd-106">您部署中的反向 proxy 會使用公用憑證，並使用 HTTP (，也就是透過 HTTP) 傳輸層安全性，將反向 proxy 中的通訊與用戶端和反向 proxy 加密為內部伺服器。</span><span class="sxs-lookup"><span data-stu-id="58fcd-106">The reverse proxy in your deployment uses a public certificate and encrypts the communication from the reverse proxy to clients and the reverse proxy to internal servers by using HTTP (that is, Transport Layer Security over HTTP).</span></span>

<span data-ttu-id="58fcd-107">以下是用於 access 和 web 會議 Edge 外部介面及 A/V 驗證服務之公用憑證的需求：</span><span class="sxs-lookup"><span data-stu-id="58fcd-107">Following are the requirements for the public certificate used for access and web conferencing Edge external interfaces, and the A/V authentication service:</span></span>

  - <span data-ttu-id="58fcd-108">憑證必須由支援主體替代名稱的已核准公用 CA 所發出。</span><span class="sxs-lookup"><span data-stu-id="58fcd-108">The certificate must be issued by an approved public CA that supports subject alternative name.</span></span> <span data-ttu-id="58fcd-109">如需詳細資訊，請參閱 Microsoft 知識庫文章929395：「Exchange Server 和通訊伺服器的整合通訊憑證合作夥伴」，網址為 [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834) 。</span><span class="sxs-lookup"><span data-stu-id="58fcd-109">For details, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

  - <span data-ttu-id="58fcd-110">若要在 Edge 集區上使用此憑證，該憑證必須建立為可匯出，並在 Edge 集區中的每個 Edge Server 上使用相同的憑證。</span><span class="sxs-lookup"><span data-stu-id="58fcd-110">If the certificate will be used on an Edge pool, it must be created as exportable, with the same certificate used on each Edge Server in the Edge pool.</span></span> <span data-ttu-id="58fcd-111">可匯出的私密金鑰需求是用於 A/V 驗證服務，此服務必須在集區中所有 Edge Server 上使用相同的私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="58fcd-111">The exportable private key requirement is for the purposes of the A/V Authentication service, which must use the same private key across all Edge Servers in the pool.</span></span>

  - <span data-ttu-id="58fcd-112">如果您想要最大化 Audio/Video 服務的正常運作時間，請複查憑證需求，以實現與其他外部 Edge 憑證) 目的不同的另 A/V 一個 A/V Edge 服務憑證， (也就是另一個 Edge service 憑證。</span><span class="sxs-lookup"><span data-stu-id="58fcd-112">If you want to maximize the uptime for your Audio/Video services, review the certificate requirements for implementing a decoupled A/V Edge service certificate (that is, a separate A/V Edge service certificate from the other External Edge certificate purposes).</span></span> <span data-ttu-id="58fcd-113">如需詳細資訊，請參閱在 lync server 2013 中的 [變更會影響 Edge server 規劃](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)、 [在 lync server 2013 中規劃 edge server 憑證](lync-server-2013-plan-for-edge-server-certificates.md) ，以及在 [lync Server 2013 中使用-擲入 Set-CsCertificate 中的 OAuth 憑證](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)。</span><span class="sxs-lookup"><span data-stu-id="58fcd-113">For details, see [Changes in Lync Server 2013 that affect Edge Server planning](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [Plan for Edge Server certificates in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) and [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span></span>

  - <span data-ttu-id="58fcd-114">憑證的主體名稱是 Access Edge service 外部介面的完整功能變數名稱 (FQDN) 或硬體負載平衡器 VIP (例如，access.contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="58fcd-114">The subject name of the certificate is the Access Edge service external interface fully qualified domain name (FQDN) or hardware load balancer VIP (for example, access.contoso.com).</span></span> <span data-ttu-id="58fcd-115">).</span><span class="sxs-lookup"><span data-stu-id="58fcd-115">).</span></span> <span data-ttu-id="58fcd-116">主體名稱不能包含萬用字元，它必須是明確的名稱。</span><span class="sxs-lookup"><span data-stu-id="58fcd-116">The subject name can’t have a wildcard character, it must be an explicit name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="58fcd-117">對於 Lync Server 2013，這已不再是必要的需求，但仍建議用於與 Office 通訊伺服器相容。</span><span class="sxs-lookup"><span data-stu-id="58fcd-117">For Lync Server 2013, this is no longer a requirement, but it is still recommended for compatibility with Office Communications Server.</span></span>

    
    </div>

  - <span data-ttu-id="58fcd-118">主體替代名稱清單包含下列的 Fqdn：</span><span class="sxs-lookup"><span data-stu-id="58fcd-118">The subject alternative name list contains the FQDNs of the following:</span></span>
    
      - <span data-ttu-id="58fcd-119">Access Edge service 外部介面或硬體負載平衡器 VIP (例如，sip.contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="58fcd-119">The Access Edge service external interface or hardware load balancer VIP (for example, sip.contoso.com).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="58fcd-120">雖然憑證主體名稱等於 access Edge FQDN，但主體替代名稱也必須包含 access Edge FQDN，因為傳輸層安全性 (TLS) 會忽略主體名稱，並使用主體替代名稱專案進行驗證。</span><span class="sxs-lookup"><span data-stu-id="58fcd-120">Even though the certificate subject name is equal to the access Edge FQDN, the subject alternative name must also contain the access Edge FQDN because Transport Layer Security (TLS) ignores the subject name and uses the subject alternative name entries for validation.</span></span>

        
        </div>
    
      - <span data-ttu-id="58fcd-121">Web 會議 Edge 外部介面或硬體負載平衡器 VIP (例如，webcon.contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="58fcd-121">The web conferencing Edge external interface or hardware load balancer VIP (for example, webcon.contoso.com).</span></span>
    
      - <span data-ttu-id="58fcd-122">如果您使用的是用戶端自動設定或同盟，也請包含您公司內使用的任何 SIP 網域 Fqdn (例如，sip.contoso.com、sip.fabrikam.com) 。</span><span class="sxs-lookup"><span data-stu-id="58fcd-122">If you are using client auto-configuration or federation, also include any SIP domain FQDNs used within your company (for example, sip.contoso.com, sip.fabrikam.com).</span></span>
    
      - <span data-ttu-id="58fcd-123">A/V Edge service 不使用主體名稱或主體替代名稱專案。</span><span class="sxs-lookup"><span data-stu-id="58fcd-123">The A/V Edge service does not use the subject name or the subject alternative names entries.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="58fcd-124">主體替代名稱清單中的 Fqdn 順序無關緊要。</span><span class="sxs-lookup"><span data-stu-id="58fcd-124">The order of the FQDNs in the subject alternative names list does not matter.</span></span>

    
    </div>

<span data-ttu-id="58fcd-125">如果您要在網站上部署多個負載平衡 Edge server，則每台 Edge Server 上安裝的 A/V 驗證服務憑證必須來自同一個 CA，而且必須使用相同的私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="58fcd-125">If you are deploying multiple, load-balanced Edge Servers at a site, the A/V authentication service certificate that is installed on each Edge Server must be from the same CA and must use the same private key.</span></span> <span data-ttu-id="58fcd-126">請注意，不論該憑證是用於一部 Edge Server，還是在許多 Edge Server 上，其私密金鑰都必須可匯出。</span><span class="sxs-lookup"><span data-stu-id="58fcd-126">Note that the certificate's private key must be exportable, regardless of whether it is used on one Edge Server or many Edge Servers.</span></span> <span data-ttu-id="58fcd-127">如果您從 Edge Server 之外的任何電腦要求憑證，也必須可匯出。</span><span class="sxs-lookup"><span data-stu-id="58fcd-127">It must also be exportable if you request the certificate from any computer other than the Edge Server.</span></span> <span data-ttu-id="58fcd-128">因為 A/V 驗證服務不使用主體名稱或主體替代名稱，您可以重複使用 access Edge 憑證，只要訪問 Edge 和 web 會議 Edge 符合主體名稱和主體替代名稱的需求，即可匯出憑證的私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="58fcd-128">Because the A/V authentication service does not use the subject name or subject alternative name, you can reuse the access Edge certificate as long as the subject name and subject alternative name requirements are met for the access Edge and the web conferencing Edge and the certificate’s private key is exportable.</span></span>

<span data-ttu-id="58fcd-129">Edge 內部介面所使用之私人 (或公開) 憑證的需求如下：</span><span class="sxs-lookup"><span data-stu-id="58fcd-129">Requirements for the private (or public) certificate used for the Edge internal interface are as follows:</span></span>

  - <span data-ttu-id="58fcd-130">憑證可以由內部 CA 或核准的公用憑證 CA 所發出。</span><span class="sxs-lookup"><span data-stu-id="58fcd-130">The certificate can be issued by an internal CA or an approved public certificate CA.</span></span>

  - <span data-ttu-id="58fcd-131">憑證的主體名稱通常是 Edge 內部介面 FQDN 或硬體負載平衡器 VIP (例如，lsedge.contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="58fcd-131">The subject name of the certificate is typically the Edge internal interface FQDN or hardware load balancer VIP (for example, lsedge.contoso.com).</span></span> <span data-ttu-id="58fcd-132">不過，您可以在 Edge internal 上使用萬用字元憑證。</span><span class="sxs-lookup"><span data-stu-id="58fcd-132">However, you can use a wildcard certificate on the Edge internal.</span></span>

  - <span data-ttu-id="58fcd-133">不需要主體替代名稱清單。</span><span class="sxs-lookup"><span data-stu-id="58fcd-133">No subject alternative name list is required.</span></span>

<span data-ttu-id="58fcd-134">您的部署服務要求中的反向 proxy：</span><span class="sxs-lookup"><span data-stu-id="58fcd-134">The reverse proxy in your deployment services requests for:</span></span>

  - <span data-ttu-id="58fcd-135">外部使用者存取會議內容的會議</span><span class="sxs-lookup"><span data-stu-id="58fcd-135">External user access to meeting content for meetings</span></span>

  - <span data-ttu-id="58fcd-136">外部使用者存取可展開及顯示通訊群組的成員</span><span class="sxs-lookup"><span data-stu-id="58fcd-136">External user access to expand and display members of distribution groups</span></span>

  - <span data-ttu-id="58fcd-137">外部使用者從通訊錄服務存取可下載的檔案</span><span class="sxs-lookup"><span data-stu-id="58fcd-137">External user access to downloadable files from the Address Book Service</span></span>

  - <span data-ttu-id="58fcd-138">對 Lync Web App 用戶端的外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="58fcd-138">External user access to the Lync Web App client</span></span>

  - <span data-ttu-id="58fcd-139">外部使用者存取電話撥入式會議設定網頁</span><span class="sxs-lookup"><span data-stu-id="58fcd-139">External user access to the Dial-in Conferencing Settings web page</span></span>

  - <span data-ttu-id="58fcd-140">存取位置資訊服務的外部使用者</span><span class="sxs-lookup"><span data-stu-id="58fcd-140">External user access to the Location Information Service</span></span>

  - <span data-ttu-id="58fcd-141">外部裝置存取裝置更新服務並取得更新</span><span class="sxs-lookup"><span data-stu-id="58fcd-141">External device access to the Device Update Service and obtain updates</span></span>

<span data-ttu-id="58fcd-142">反向 proxy 會將內部伺服器 Web 元件發佈 URLs。</span><span class="sxs-lookup"><span data-stu-id="58fcd-142">The reverse proxy publishes the internal server Web Components URLs.</span></span> <span data-ttu-id="58fcd-143">Web 元件 URLs 會在 Director、前端伺服器或前端集區上定義為拓撲產生器中的 **外部 Web 服務** 。</span><span class="sxs-lookup"><span data-stu-id="58fcd-143">The Web Components URLs are defined on the Director, Front End Server or Front End pool as the **External web services** in Topology Builder.</span></span>

<span data-ttu-id="58fcd-144">在指派給反向 proxy 之憑證的主體替代名稱欄位中，支援萬用字元專案。</span><span class="sxs-lookup"><span data-stu-id="58fcd-144">Wildcard entries are supported in the subject alternative name field of the certificate assigned to the reverse proxy.</span></span> <span data-ttu-id="58fcd-145">如需如何設定反向 proxy 之憑證要求的詳細資訊，請參閱 [在 Lync Server 2013 中要求和設定反向 HTTP proxy 的憑證](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)。</span><span class="sxs-lookup"><span data-stu-id="58fcd-145">For details about how to configure the certificate request for the reverse proxy, see [Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="58fcd-146">另請參閱</span><span class="sxs-lookup"><span data-stu-id="58fcd-146">See Also</span></span>


[<span data-ttu-id="58fcd-147">Lync Server 2013 中的萬用字元憑證支援</span><span class="sxs-lookup"><span data-stu-id="58fcd-147">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

