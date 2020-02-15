---
title: Lync Server 2013： 憑證摘要-自動探索
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
ms.openlocfilehash: ae57440d4843151da61d24a9ff015778a5c65b07
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="dd847-102">憑證摘要-Lync Server 2013 中的自動探索</span><span class="sxs-lookup"><span data-stu-id="dd847-102">Certificate summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd847-103">_**上次修改主題：** 2013年-02-14_</span><span class="sxs-lookup"><span data-stu-id="dd847-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="dd847-104">Lync Server 2013 自動探索服務執行 Director 與前端集區伺服器，而且當發佈在 DNS 中，可以用於 Lync 用戶端所尋找伺服器和使用者的服務。</span><span class="sxs-lookup"><span data-stu-id="dd847-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by Lync clients to locate server and user services.</span></span> <span data-ttu-id="dd847-105">如果您從 Lync Server 2010 升級，並沒有不部署行動性，才能用戶端可以使用自動探索，您必須修改任何 Director 與前端伺服器執行自動探索服務的憑證主體替代名稱清單。</span><span class="sxs-lookup"><span data-stu-id="dd847-105">If you are upgrading from Lync Server 2010 and did not deploy Mobility, before clients can use automatic discovery, you must modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="dd847-106">此外，可能還需要針對在反向 Proxy 上用於外部 Web 服務發行規則的憑證，修改主體替代名稱清單。</span><span class="sxs-lookup"><span data-stu-id="dd847-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="dd847-107">決定是否要在反向 proxy 上使用主體替代名稱清單根據您是否發佈連接埠 80 或連接埠 443 上的自動探索服務：</span><span class="sxs-lookup"><span data-stu-id="dd847-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="dd847-108">**在 [連接埠 80 上發佈**   如果自動探索服務的初始查詢發生透過連接埠 80，不需要任何憑證變更。</span><span class="sxs-lookup"><span data-stu-id="dd847-108">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="dd847-109">這是因為執行 Lync 的行動裝置會存取外部連接埠 80 上的反向 proxy，然後橋接至 Director 或前端伺服器上連接埠 8080 內部。</span><span class="sxs-lookup"><span data-stu-id="dd847-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be bridged to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="dd847-110">如需詳細資訊，請參閱 「 初始自動探索程序使用連接埠 80 」 一節[的 Technical requirements for Lync Server 2013 中的行動性](lync-server-2013-technical-requirements-for-mobility.md)。</span><span class="sxs-lookup"><span data-stu-id="dd847-110">For details, see the "Initial Autodiscover Process Using Port 80" section [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="dd847-111">**在 [連接埠 443 上發行**   上使用的外部 web 服務發行規則憑證的主體替代名稱清單必須包含*lyncdiscover。\<sipdomain\>* 每個 SIP 網域組織內的項目。</span><span class="sxs-lookup"><span data-stu-id="dd847-111">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>* entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="dd847-112">我們強烈建議使用 HTTPS over HTTP。</span><span class="sxs-lookup"><span data-stu-id="dd847-112">We highly recommend using HTTPS over HTTP.</span></span> <span data-ttu-id="dd847-113">HTTPS 使用憑證來加密的流量。</span><span class="sxs-lookup"><span data-stu-id="dd847-113">HTTPS uses certificates to encrypt traffic.</span></span> <span data-ttu-id="dd847-114">HTTP 不提供加密，並傳送任何資料都將純文字。</span><span class="sxs-lookup"><span data-stu-id="dd847-114">HTTP does not provide for encryption, and any data sent will be plain text.</span></span>

    
    </div>

<span data-ttu-id="dd847-115">使用內部憑證授權單位作為憑證，通常是簡單的程序。</span><span class="sxs-lookup"><span data-stu-id="dd847-115">Reissuing certificates by using an internal certificate authority is typically a simple process.</span></span> <span data-ttu-id="dd847-116">但對於使用 web 服務發行規則的公用憑證，新增多個主體替代名稱項目可能會變得昂貴。</span><span class="sxs-lookup"><span data-stu-id="dd847-116">But for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="dd847-117">若要解決此問題，我們可以支援的初始自動探索連線通訊埠 80，然後重新導向至 Director 或前端伺服器上的連接埠 8080。</span><span class="sxs-lookup"><span data-stu-id="dd847-117">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dd847-118">如果您的 Lync Server 2013 基礎結構使用從內部憑證授權單位 (CA) 發出的內部憑證，且想要支援行動裝置以無線方式連線，則必須先安裝來自內部 CA 的任一根憑證鏈結在行動裝置或您必須變更為使用公用憑證上您的 Lync Server 2013 基礎結構。</span><span class="sxs-lookup"><span data-stu-id="dd847-118">If your Lync Server 2013 infrastructure uses internal certificates that are issued from an internal certification authority (CA) and you plan to support mobile devices connecting wirelessly, either the root certificate chain from the internal CA must be installed on the mobile devices or you must change to a public certificate on your Lync Server 2013 infrastructure.</span></span>



</div>

<span data-ttu-id="dd847-119">本主題說明 Director、 前端伺服器和反向 proxy 所需的新增的主體替代名稱。</span><span class="sxs-lookup"><span data-stu-id="dd847-119">This topic describes the added subject alternative names required for the Director, Front End Server and reverse proxy.</span></span> <span data-ttu-id="dd847-120">僅新增的主體替代名稱 (SAN) 參照。</span><span class="sxs-lookup"><span data-stu-id="dd847-120">Only the added subject alternative names (SAN) are referenced.</span></span> <span data-ttu-id="dd847-121">請參閱規劃的區段在憑證上的其他項目上的指引。</span><span class="sxs-lookup"><span data-stu-id="dd847-121">Refer to the planning sections for guidance on the other entries on certificates.</span></span> <span data-ttu-id="dd847-122">如需詳細資訊，請參閱[Lync Server 2013 中 Director 的案例](lync-server-2013-scenarios-for-the-director.md)、 [Lync Server 2013 中的外部使用者存取的案例](lync-server-2013-scenarios-for-external-user-access.md)和[Lync Server 2013 中的反向 proxy 案例](lync-server-2013-scenarios-for-reverse-proxy.md)。</span><span class="sxs-lookup"><span data-stu-id="dd847-122">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md), and [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span></span>

<span data-ttu-id="dd847-123">下表定義 Director 集區、 前端集區]，和反向 proxy 的自動探索 SAN 項目：</span><span class="sxs-lookup"><span data-stu-id="dd847-123">The following tables define the Autodiscover SAN entries for the Director pool, the Front End pool, and the reverse proxy:</span></span>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="dd847-124">Director 集區憑證需求</span><span class="sxs-lookup"><span data-stu-id="dd847-124">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dd847-125">描述</span><span class="sxs-lookup"><span data-stu-id="dd847-125">Description</span></span></th>
<th><span data-ttu-id="dd847-126">主體替代名稱項目</span><span class="sxs-lookup"><span data-stu-id="dd847-126">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd847-127">內部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="dd847-127">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="dd847-128">SAN = lyncdiscoverinternal。&lt;內部網域名稱&gt;</span><span class="sxs-lookup"><span data-stu-id="dd847-128">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd847-129">外部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="dd847-129">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="dd847-130">SAN = lyncdiscover。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="dd847-130">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="dd847-131">您將與新的 SAN 項目最近更新的憑證指派給預設憑證時。</span><span class="sxs-lookup"><span data-stu-id="dd847-131">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="dd847-132">或者，您可以使用 SAN = \*。&lt;sipdomain&gt;。</span><span class="sxs-lookup"><span data-stu-id="dd847-132">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;.</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="dd847-133">前端集區憑證需求</span><span class="sxs-lookup"><span data-stu-id="dd847-133">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dd847-134">描述</span><span class="sxs-lookup"><span data-stu-id="dd847-134">Description</span></span></th>
<th><span data-ttu-id="dd847-135">主體替代名稱項目</span><span class="sxs-lookup"><span data-stu-id="dd847-135">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd847-136">內部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="dd847-136">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="dd847-137">SAN = lyncdiscoverinternal。&lt;內部網域名稱&gt;</span><span class="sxs-lookup"><span data-stu-id="dd847-137">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd847-138">外部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="dd847-138">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="dd847-139">SAN = lyncdiscover。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="dd847-139">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="dd847-140">您將與新的 SAN 項目最近更新的憑證指派給預設憑證時。</span><span class="sxs-lookup"><span data-stu-id="dd847-140">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="dd847-141">或者，您可以使用 SAN = \*。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="dd847-141">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="dd847-142">反向 Proxy (公用 CA) 憑證需求</span><span class="sxs-lookup"><span data-stu-id="dd847-142">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dd847-143">描述</span><span class="sxs-lookup"><span data-stu-id="dd847-143">Description</span></span></th>
<th><span data-ttu-id="dd847-144">主體別名項目</span><span class="sxs-lookup"><span data-stu-id="dd847-144">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd847-145">外部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="dd847-145">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="dd847-146">SAN = lyncdiscover。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="dd847-146">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="dd847-147">您將與新的 SAN 項目最近更新的憑證指派給反向 proxy 上的 SSL 接聽程式時。</span><span class="sxs-lookup"><span data-stu-id="dd847-147">You assign the newly updated certificate with the new SAN entry to the SSL Listener on the reverse proxy.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

