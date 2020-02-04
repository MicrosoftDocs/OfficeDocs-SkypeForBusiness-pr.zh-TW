---
title: Lync Server 2013： [認證摘要]-自動探索
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
ms.openlocfilehash: 8956c8a0ed4e149f336e6670aaf5b262f1868748
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="dd5a9-102">憑證摘要-Lync Server 2013 中的自動探索</span><span class="sxs-lookup"><span data-stu-id="dd5a9-102">Certificate summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd5a9-103">_**主題上次修改日期：** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="dd5a9-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="dd5a9-104">Lync Server 2013 自動探索服務會在主管和前端池伺服器上執行，並在 DNS 中發佈時，可供 Lync 用戶端用來尋找伺服器和使用者服務。</span><span class="sxs-lookup"><span data-stu-id="dd5a9-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by Lync clients to locate server and user services.</span></span> <span data-ttu-id="dd5a9-105">如果您是從 Lync Server 2010 升級且沒有部署行動，在用戶端可以使用自動搜尋之前，您必須在執行自動探索服務的任何主管和前端伺服器上修改證書消費者備用名稱清單。</span><span class="sxs-lookup"><span data-stu-id="dd5a9-105">If you are upgrading from Lync Server 2010 and did not deploy Mobility, before clients can use automatic discovery, you must modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="dd5a9-106">此外，可能還需要針對反向代理伺服器上的外部 web 服務發佈規則，在證書上修改消費者備用名稱清單。</span><span class="sxs-lookup"><span data-stu-id="dd5a9-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="dd5a9-107">有關是否要在反向代理伺服器上使用 subject 備用名稱清單的決策是依據您是否要在埠80或埠443上發佈自動探索服務而定：</span><span class="sxs-lookup"><span data-stu-id="dd5a9-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="dd5a9-108">**已在埠 80**   上發佈如果自動探索服務的初始查詢是在埠80上進行，則不需要進行憑證變更。</span><span class="sxs-lookup"><span data-stu-id="dd5a9-108">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="dd5a9-109">這是因為執行 Lync 的行動裝置會在外部存取埠80上的反向 proxy，然後在內部的埠8080上將其橋接至控制器或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="dd5a9-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be bridged to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="dd5a9-110">如需詳細資訊，請參閱[Lync Server 2013 中的行動技術需求](lync-server-2013-technical-requirements-for-mobility.md)（使用埠80的初始自動探索程式）一節。</span><span class="sxs-lookup"><span data-stu-id="dd5a9-110">For details, see the "Initial Autodiscover Process Using Port 80" section [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="dd5a9-111">**已在埠 443**   上發佈：外部 web 服務發佈規則所使用的憑證上的使用方式備用名稱清單必須包含\*lyncdiscover。\<針對\> \*貴組織內的每個 SIP 網域 sipdomain 專案。</span><span class="sxs-lookup"><span data-stu-id="dd5a9-111">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>* entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="dd5a9-112">我們強烈建議您在 HTTP 上使用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="dd5a9-112">We highly recommend using HTTPS over HTTP.</span></span> <span data-ttu-id="dd5a9-113">HTTPS 使用憑證來加密流量。</span><span class="sxs-lookup"><span data-stu-id="dd5a9-113">HTTPS uses certificates to encrypt traffic.</span></span> <span data-ttu-id="dd5a9-114">HTTP 不提供加密，且傳送的任何資料都會是純文字。</span><span class="sxs-lookup"><span data-stu-id="dd5a9-114">HTTP does not provide for encryption, and any data sent will be plain text.</span></span>

    
    </div>

<span data-ttu-id="dd5a9-115">使用內部憑證授權單位重新頒發憑證通常是一個簡單的程式。</span><span class="sxs-lookup"><span data-stu-id="dd5a9-115">Reissuing certificates by using an internal certificate authority is typically a simple process.</span></span> <span data-ttu-id="dd5a9-116">但針對 web 服務發佈規則所使用的公用憑證，新增多個消費者替換名稱專案可能會變得很昂貴。</span><span class="sxs-lookup"><span data-stu-id="dd5a9-116">But for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="dd5a9-117">若要解決此問題，我們支援經由埠80的初始自動探索連線，然後再重新導向控制器或前端伺服器上的埠8080。</span><span class="sxs-lookup"><span data-stu-id="dd5a9-117">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dd5a9-118">如果您的 Lync Server 2013 基礎結構使用內部認證機構（CA）頒發的內部憑證，且您打算支援以無線方式連線的行動裝置，則必須安裝內部 CA 的根憑證鏈在行動裝置上，或者您必須在 Lync Server 2013 基礎結構上變更為公用憑證。</span><span class="sxs-lookup"><span data-stu-id="dd5a9-118">If your Lync Server 2013 infrastructure uses internal certificates that are issued from an internal certification authority (CA) and you plan to support mobile devices connecting wirelessly, either the root certificate chain from the internal CA must be installed on the mobile devices or you must change to a public certificate on your Lync Server 2013 infrastructure.</span></span>



</div>

<span data-ttu-id="dd5a9-119">本主題描述的是主管、前端伺服器和反向 proxy 所需的已加入主題替代名稱。</span><span class="sxs-lookup"><span data-stu-id="dd5a9-119">This topic describes the added subject alternative names required for the Director, Front End Server and reverse proxy.</span></span> <span data-ttu-id="dd5a9-120">只會參照新增的主體替換名稱（SAN）。</span><span class="sxs-lookup"><span data-stu-id="dd5a9-120">Only the added subject alternative names (SAN) are referenced.</span></span> <span data-ttu-id="dd5a9-121">請參閱規劃章節，以取得有關憑證上其他專案的指導方針。</span><span class="sxs-lookup"><span data-stu-id="dd5a9-121">Refer to the planning sections for guidance on the other entries on certificates.</span></span> <span data-ttu-id="dd5a9-122">如需詳細資訊，請參閱 lync [server 2013 中的主管案例](lync-server-2013-scenarios-for-the-director.md)、 [lync server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)，以及[lync server 2013 中的反向 proxy](lync-server-2013-scenarios-for-reverse-proxy.md)案例。</span><span class="sxs-lookup"><span data-stu-id="dd5a9-122">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md), and [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span></span>

<span data-ttu-id="dd5a9-123">下表定義控制器池、前端池及反向 proxy 的自動探索 SAN 專案：</span><span class="sxs-lookup"><span data-stu-id="dd5a9-123">The following tables define the Autodiscover SAN entries for the Director pool, the Front End pool, and the reverse proxy:</span></span>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="dd5a9-124">控制器池證書需求</span><span class="sxs-lookup"><span data-stu-id="dd5a9-124">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dd5a9-125">說明</span><span class="sxs-lookup"><span data-stu-id="dd5a9-125">Description</span></span></th>
<th><span data-ttu-id="dd5a9-126">消費者替換名稱專案</span><span class="sxs-lookup"><span data-stu-id="dd5a9-126">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd5a9-127">內部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="dd5a9-127">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="dd5a9-128">SAN = lyncdiscoverinternal。&lt;內部網功能變數名稱稱&gt;</span><span class="sxs-lookup"><span data-stu-id="dd5a9-128">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd5a9-129">外部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="dd5a9-129">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="dd5a9-130">SAN = lyncdiscover。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="dd5a9-130">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="dd5a9-131">您可以將新的已更新憑證，以新的 SAN 專案指派給預設憑證。</span><span class="sxs-lookup"><span data-stu-id="dd5a9-131">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="dd5a9-132">或者，您也可以使用 SAN = \*。&lt;sipdomain&gt;。</span><span class="sxs-lookup"><span data-stu-id="dd5a9-132">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;.</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="dd5a9-133">前端池憑證需求</span><span class="sxs-lookup"><span data-stu-id="dd5a9-133">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dd5a9-134">說明</span><span class="sxs-lookup"><span data-stu-id="dd5a9-134">Description</span></span></th>
<th><span data-ttu-id="dd5a9-135">消費者替換名稱專案</span><span class="sxs-lookup"><span data-stu-id="dd5a9-135">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd5a9-136">內部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="dd5a9-136">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="dd5a9-137">SAN = lyncdiscoverinternal。&lt;內部網功能變數名稱稱&gt;</span><span class="sxs-lookup"><span data-stu-id="dd5a9-137">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd5a9-138">外部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="dd5a9-138">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="dd5a9-139">SAN = lyncdiscover。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="dd5a9-139">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="dd5a9-140">您可以將新的已更新憑證，以新的 SAN 專案指派給預設憑證。</span><span class="sxs-lookup"><span data-stu-id="dd5a9-140">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="dd5a9-141">或者，您也可以使用 SAN = \*。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="dd5a9-141">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="dd5a9-142">反向 Proxy （公用 CA）憑證需求</span><span class="sxs-lookup"><span data-stu-id="dd5a9-142">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dd5a9-143">說明</span><span class="sxs-lookup"><span data-stu-id="dd5a9-143">Description</span></span></th>
<th><span data-ttu-id="dd5a9-144">消費者替換名稱專案</span><span class="sxs-lookup"><span data-stu-id="dd5a9-144">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd5a9-145">外部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="dd5a9-145">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="dd5a9-146">SAN = lyncdiscover。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="dd5a9-146">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="dd5a9-147">您可以將新的已更新憑證，以新的 SAN 專案指派給反向 proxy 上的 SSL 偵聽程式。</span><span class="sxs-lookup"><span data-stu-id="dd5a9-147">You assign the newly updated certificate with the new SAN entry to the SSL Listener on the reverse proxy.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

