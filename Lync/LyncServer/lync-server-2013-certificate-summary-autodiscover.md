---
title: Lync Server 2013：憑證摘要-自動探索
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Autodiscover
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945616(v=OCS.15)
ms:contentKeyID: 51541451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 196b3dacec792097a4760ef134ead91f267a53d1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499310"
---
# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="477f0-102">Lync Server 2013 中的憑證摘要-自動探索</span><span class="sxs-lookup"><span data-stu-id="477f0-102">Certificate summary - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="477f0-103">_**主題上次修改日期：** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="477f0-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="477f0-104">Lync Server 2013 自動探索服務會在 Director 和前端集區伺服器上執行，當您在 DNS 中發佈時，可供 Lync 用戶端用來尋找伺服器和使用者服務。</span><span class="sxs-lookup"><span data-stu-id="477f0-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by Lync clients to locate server and user services.</span></span> <span data-ttu-id="477f0-105">若要從 Lync Server 2010 升級，但未部署行動性，用戶端可以使用自動探索之前，必須修改執行自動探索服務之任何 Director 和前端伺服器上的憑證主體替代名稱清單。</span><span class="sxs-lookup"><span data-stu-id="477f0-105">If you are upgrading from Lync Server 2010 and did not deploy Mobility, before clients can use automatic discovery, you must modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="477f0-106">此外，可能還需要針對在反向 Proxy 上用於外部 Web 服務發行規則的憑證，修改主體替代名稱清單。</span><span class="sxs-lookup"><span data-stu-id="477f0-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="477f0-107">在反向 proxy 上是否要使用主體替代名稱清單的決策，取決於您是在埠80上還是在埠443上發行自動探索服務：</span><span class="sxs-lookup"><span data-stu-id="477f0-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="477f0-108">**已在埠 80**     上發行如果自動探索服務的初始查詢發生在埠80上，則不需要憑證變更。</span><span class="sxs-lookup"><span data-stu-id="477f0-108">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="477f0-109">這是因為執行 Lync 的行動裝置會在外部存取埠80上的反向 proxy，然後在內部將其橋接至 Director 或前端8080伺服器。</span><span class="sxs-lookup"><span data-stu-id="477f0-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be bridged to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="477f0-110">如需詳細資訊，請參閱 [Lync Server 2013 中](lync-server-2013-technical-requirements-for-mobility.md)的「使用埠80的初始自動探索程式」一節行動的技術需求。</span><span class="sxs-lookup"><span data-stu-id="477f0-110">For details, see the "Initial Autodiscover Process Using Port 80" section [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="477f0-111">**已在埠 443**     上發行外部 web 服務發行規則所使用之憑證上的主體替代名稱清單必須包含\*lyncdiscover。 \<sipdomain\> \*</span><span class="sxs-lookup"><span data-stu-id="477f0-111">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>*</span></span> <span data-ttu-id="477f0-112">組織內每個 SIP 網域的專案。</span><span class="sxs-lookup"><span data-stu-id="477f0-112">entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="477f0-113">強烈建議使用 HTTPS over HTTP。</span><span class="sxs-lookup"><span data-stu-id="477f0-113">We highly recommend using HTTPS over HTTP.</span></span> <span data-ttu-id="477f0-114">HTTPS 使用憑證來加密流量。</span><span class="sxs-lookup"><span data-stu-id="477f0-114">HTTPS uses certificates to encrypt traffic.</span></span> <span data-ttu-id="477f0-115">HTTP 不提供加密，而且傳送的任何資料都會是純文字。</span><span class="sxs-lookup"><span data-stu-id="477f0-115">HTTP does not provide for encryption, and any data sent will be plain text.</span></span>

    
    </div>

<span data-ttu-id="477f0-116">使用內部憑證授權單位單位重新發起憑證，通常是一種簡單的處理方式。</span><span class="sxs-lookup"><span data-stu-id="477f0-116">Reissuing certificates by using an internal certificate authority is typically a simple process.</span></span> <span data-ttu-id="477f0-117">不過，對於用於 web 服務發行規則的公用憑證，新增多個主體別名專案會變得很昂貴。</span><span class="sxs-lookup"><span data-stu-id="477f0-117">But for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="477f0-118">若要解決此問題，我們支援經由埠80的初始自動探索連線，然後重新導向 Director 或前端伺服器上的埠8080。</span><span class="sxs-lookup"><span data-stu-id="477f0-118">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="477f0-119">如果您的 Lync Server 2013 基礎結構使用內部憑證授權單位所發行的內部憑證 (CA) ，且您計畫支援以無線方式連線的行動裝置，則必須在行動裝置上安裝內部 CA 的根憑證鏈，或是必須變更為 Lync Server 2013 基礎結構上的公用憑證。</span><span class="sxs-lookup"><span data-stu-id="477f0-119">If your Lync Server 2013 infrastructure uses internal certificates that are issued from an internal certification authority (CA) and you plan to support mobile devices connecting wirelessly, either the root certificate chain from the internal CA must be installed on the mobile devices or you must change to a public certificate on your Lync Server 2013 infrastructure.</span></span>



</div>

<span data-ttu-id="477f0-120">本主題說明 Director、前端伺服器及反向 proxy 所需的主體替代名稱。</span><span class="sxs-lookup"><span data-stu-id="477f0-120">This topic describes the added subject alternative names required for the Director, Front End Server and reverse proxy.</span></span> <span data-ttu-id="477f0-121">只會參考 (SAN) 所新增的主體替代名稱。</span><span class="sxs-lookup"><span data-stu-id="477f0-121">Only the added subject alternative names (SAN) are referenced.</span></span> <span data-ttu-id="477f0-122">如需憑證上其他專案的指引，請參閱規劃章節。</span><span class="sxs-lookup"><span data-stu-id="477f0-122">Refer to the planning sections for guidance on the other entries on certificates.</span></span> <span data-ttu-id="477f0-123">如需詳細資訊，請參閱 lync server [2013 中的 Director 案例](lync-server-2013-scenarios-for-the-director.md)、 [lync server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)，以及 [lync server 2013 中的反向 proxy](lync-server-2013-scenarios-for-reverse-proxy.md)案例。</span><span class="sxs-lookup"><span data-stu-id="477f0-123">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md), and [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span></span>

<span data-ttu-id="477f0-124">下表定義 Director 集區、前端集區和反向 proxy 的自動探索 SAN 專案：</span><span class="sxs-lookup"><span data-stu-id="477f0-124">The following tables define the Autodiscover SAN entries for the Director pool, the Front End pool, and the reverse proxy:</span></span>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="477f0-125">Director 集區憑證需求</span><span class="sxs-lookup"><span data-stu-id="477f0-125">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="477f0-126">描述</span><span class="sxs-lookup"><span data-stu-id="477f0-126">Description</span></span></th>
<th><span data-ttu-id="477f0-127">主體替代名稱項目</span><span class="sxs-lookup"><span data-stu-id="477f0-127">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="477f0-128">內部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="477f0-128">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="477f0-129">SAN = lyncdiscoverinternal。 &lt;內部功能變數名稱&gt;</span><span class="sxs-lookup"><span data-stu-id="477f0-129">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="477f0-130">外部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="477f0-130">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="477f0-131">SAN = lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="477f0-131">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="477f0-132">您可以將新的已更新憑證以新的 SAN 專案指派給預設憑證。</span><span class="sxs-lookup"><span data-stu-id="477f0-132">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="477f0-133">或者，您也可以使用 SAN = \*。 &lt;microsoft.rtc.management.xds.sipdomain &gt; 。</span><span class="sxs-lookup"><span data-stu-id="477f0-133">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;.</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="477f0-134">前端集區憑證需求</span><span class="sxs-lookup"><span data-stu-id="477f0-134">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="477f0-135">描述</span><span class="sxs-lookup"><span data-stu-id="477f0-135">Description</span></span></th>
<th><span data-ttu-id="477f0-136">主體替代名稱項目</span><span class="sxs-lookup"><span data-stu-id="477f0-136">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="477f0-137">內部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="477f0-137">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="477f0-138">SAN = lyncdiscoverinternal。 &lt;內部功能變數名稱&gt;</span><span class="sxs-lookup"><span data-stu-id="477f0-138">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="477f0-139">外部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="477f0-139">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="477f0-140">SAN = lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="477f0-140">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="477f0-141">您可以將新的已更新憑證以新的 SAN 專案指派給預設憑證。</span><span class="sxs-lookup"><span data-stu-id="477f0-141">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="477f0-142">或者，您也可以使用 SAN = \*。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="477f0-142">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="477f0-143">反向 Proxy (公用 CA) 憑證需求</span><span class="sxs-lookup"><span data-stu-id="477f0-143">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="477f0-144">描述</span><span class="sxs-lookup"><span data-stu-id="477f0-144">Description</span></span></th>
<th><span data-ttu-id="477f0-145">主體別名項目</span><span class="sxs-lookup"><span data-stu-id="477f0-145">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="477f0-146">外部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="477f0-146">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="477f0-147">SAN = lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="477f0-147">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="477f0-148">您可以將新的已更新憑證，指派給反向 proxy 上的 SSL 攔截器。</span><span class="sxs-lookup"><span data-stu-id="477f0-148">You assign the newly updated certificate with the new SAN entry to the SSL Listener on the reverse proxy.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

