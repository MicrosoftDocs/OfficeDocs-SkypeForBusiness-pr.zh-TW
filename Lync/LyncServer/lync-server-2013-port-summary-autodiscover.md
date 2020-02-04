---
title: Lync Server 2013：埠摘要-自動探索
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Autodiscover
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945642(v=OCS.15)
ms:contentKeyID: 51541497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 945e3ed9d532f27676e250c29ab415646bd967ec
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="1976d-102">埠摘要-Lync Server 2013 中的自動探索</span><span class="sxs-lookup"><span data-stu-id="1976d-102">Port summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1976d-103">_**主題上次修改日期：** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="1976d-103">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="1976d-104">Lync Server 2013 自動探索服務會在主管和前端池伺服器上執行，當您使用`lyncdiscover.<domain>`與`lyncdiscoverinternal.<domain>`主機記錄在 DNS 中發佈時，可供用戶端用來尋找 Lync Server 功能。</span><span class="sxs-lookup"><span data-stu-id="1976d-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS using the `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` host records, can be used by clients to locate Lync Server features.</span></span> <span data-ttu-id="1976d-105">若要在執行 Lync Mobile 的行動裝置上使用自動探索功能，您可能必須先在執行自動探索服務的任何主管和前端伺服器上修改證書受領人備用名稱清單。</span><span class="sxs-lookup"><span data-stu-id="1976d-105">In order for mobile devices running Lync Mobile to use Autodiscover, you may first need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="1976d-106">此外，可能還需要針對反向代理伺服器上的外部 web 服務發佈規則，在證書上修改消費者備用名稱清單。</span><span class="sxs-lookup"><span data-stu-id="1976d-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="1976d-107">有關是否要在反向代理伺服器上使用 subject 備用名稱清單的決策是依據您是否要在埠80或埠443上發佈自動探索服務而定：</span><span class="sxs-lookup"><span data-stu-id="1976d-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="1976d-108">**在**   適用于行動裝置的埠80上發佈，如果自動探索服務的初始查詢是在埠80上進行，則不需要進行任何憑證變更。</span><span class="sxs-lookup"><span data-stu-id="1976d-108">**Published on port 80**   For Mobile devices, no certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="1976d-109">這是因為執行 Lync 的行動裝置會在外部存取埠80上的反向 proxy，然後在內部將埠8080重新導向到控制器或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="1976d-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span>

  - <span data-ttu-id="1976d-110">**已在埠 443**   上發佈對於外部 web 服務發佈規則所使用的憑證，您必須為貴組織`lyncdiscover.<sipdomain>`內的每個 SIP 網域包含一個專案。</span><span class="sxs-lookup"><span data-stu-id="1976d-110">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a `lyncdiscover.<sipdomain>` entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1976d-111">如果您是從已部署行動性的 Lync Server 2010 進行全新安裝或升級，您可以使用埠80來自動探索行動服務，或以適當的受領人名稱和 subject 替代名稱來重新頒發憑證。</span><span class="sxs-lookup"><span data-stu-id="1976d-111">For new installations or upgrades from Lync Server 2010 where you deployed Mobility, you either used Port 80 for Autodiscover of the Mobility service, or reissued certificates with the proper subject name and subject alternative names in place.</span></span> <span data-ttu-id="1976d-112">查看主管和前端伺服器上的憑證，確認您選擇的是哪個路徑。</span><span class="sxs-lookup"><span data-stu-id="1976d-112">Review the certificates on your Director and Front End Server to confirm which path you chose.</span></span>

    
    </div>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="1976d-113">反向 Proxy 伺服器的防火牆詳細資料：外部介面</span><span class="sxs-lookup"><span data-stu-id="1976d-113">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1976d-114">通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="1976d-114">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="1976d-115">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="1976d-115">Source IP Address</span></span></th>
<th><span data-ttu-id="1976d-116">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="1976d-116">Destination IP Address</span></span></th>
<th><span data-ttu-id="1976d-117">筆記</span><span class="sxs-lookup"><span data-stu-id="1976d-117">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1976d-118">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="1976d-118">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="1976d-119">每</span><span class="sxs-lookup"><span data-stu-id="1976d-119">Any</span></span></p></td>
<td><p><span data-ttu-id="1976d-120">反向 proxy 偵聽程式</span><span class="sxs-lookup"><span data-stu-id="1976d-120">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="1976d-121">可選如果使用者進入 HTTP://&lt;publishedSiteFQDN&gt;，則重定向至 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="1976d-121">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span> <span data-ttu-id="1976d-122">如果您在組織不想要修改外部 Web 服務發佈規則憑證的情況下，使用 Office Web Apps for 會議，以及執行 Lync 之行動裝置的自動探索服務，也需要。</span><span class="sxs-lookup"><span data-stu-id="1976d-122">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1976d-123">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="1976d-123">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="1976d-124">每</span><span class="sxs-lookup"><span data-stu-id="1976d-124">Any</span></span></p></td>
<td><p><span data-ttu-id="1976d-125">反向 proxy 偵聽程式</span><span class="sxs-lookup"><span data-stu-id="1976d-125">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="1976d-126">通訊錄下載、通訊錄網頁查詢服務、自動探索、用戶端更新、會議內容、裝置更新、群組延伸、Office Web Apps for 會議、電話撥入式會議及會議。</span><span class="sxs-lookup"><span data-stu-id="1976d-126">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="1976d-127">反向 Proxy 伺服器的防火牆詳細資料：內部介面</span><span class="sxs-lookup"><span data-stu-id="1976d-127">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1976d-128">通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="1976d-128">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="1976d-129">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="1976d-129">Source IP Address</span></span></th>
<th><span data-ttu-id="1976d-130">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="1976d-130">Destination IP Address</span></span></th>
<th><span data-ttu-id="1976d-131">筆記</span><span class="sxs-lookup"><span data-stu-id="1976d-131">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1976d-132">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="1976d-132">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="1976d-133">內部反向 proxy 介面</span><span class="sxs-lookup"><span data-stu-id="1976d-133">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="1976d-134">[前端伺服器]、[前端] 池、[主管]、[控制器] 池、[會議的 Office Web Apps]</span><span class="sxs-lookup"><span data-stu-id="1976d-134">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="1976d-135">如果組織不想要修改外部 web 服務發佈規則憑證的情況下，在執行 Lync 的行動裝置上使用自動探索服務，則是必要的。</span><span class="sxs-lookup"><span data-stu-id="1976d-135">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span> <span data-ttu-id="1976d-136">在反向 proxy 外部介面上傳送到埠80的流量，會從反向 proxy 內部介面重新導向到埠8080上的 pool，讓 pool Web 服務可以區別內部網路流量。</span><span class="sxs-lookup"><span data-stu-id="1976d-136">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1976d-137">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="1976d-137">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="1976d-138">內部反向 proxy 介面</span><span class="sxs-lookup"><span data-stu-id="1976d-138">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="1976d-139">[前端伺服器]、[前端] 池、[主管]、[控制器] 池、[會議的 Office Web Apps]</span><span class="sxs-lookup"><span data-stu-id="1976d-139">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="1976d-140">在反向 proxy 外部介面上傳送到埠443的流量，會從反向 proxy 內部介面重新導向到埠4443上的 pool，讓 pool web 服務可以區別內部網路流量。</span><span class="sxs-lookup"><span data-stu-id="1976d-140">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

