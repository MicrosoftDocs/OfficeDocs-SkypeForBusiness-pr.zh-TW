---
title: Lync Server 2013：埠摘要-自動探索
description: Lync Server 2013：埠摘要-自動探索。
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
ms.openlocfilehash: 20a5ef54d4ad8419fd6e73909f97764bf1290c22
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543139"
---
# <a name="port-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="ef3ca-103">Lync Server 2013 中的埠摘要-自動探索</span><span class="sxs-lookup"><span data-stu-id="ef3ca-103">Port summary - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef3ca-104">_**主題上次修改日期：** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="ef3ca-104">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="ef3ca-105">Lync Server 2013 自動探索服務會在 Director 和前端集區伺服器上執行，並會在使用和主控記錄的 DNS 中發佈時，供 `lyncdiscover.<domain>` `lyncdiscoverinternal.<domain>` 用戶端用來找出 lync server 功能。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-105">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS using the `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` host records, can be used by clients to locate Lync Server features.</span></span> <span data-ttu-id="ef3ca-106">為了讓執行 Lync Mobile 的行動裝置使用自動探索，您可能需要先修改執行自動探索服務之任何 Director 和前端伺服器上的憑證主體替代名稱清單。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-106">In order for mobile devices running Lync Mobile to use Autodiscover, you may first need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="ef3ca-107">此外，可能還需要針對在反向 Proxy 上用於外部 Web 服務發行規則的憑證，修改主體替代名稱清單。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-107">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="ef3ca-108">在反向 proxy 上是否要使用主體替代名稱清單的決策，取決於您是在埠80上還是在埠443上發行自動探索服務：</span><span class="sxs-lookup"><span data-stu-id="ef3ca-108">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="ef3ca-109">**已在埠 80**     上發行若為行動裝置，當自動探索服務的初始查詢在埠80上發生時，不需要憑證變更。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-109">**Published on port 80**   For Mobile devices, no certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="ef3ca-110">這是因為執行 Lync 的行動裝置會在外部存取埠80上的反向 proxy，然後再重新導向埠8080上的 Director 或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span>

  - <span data-ttu-id="ef3ca-111">**已在埠 443**     上發行外部 web 服務發行規則所使用之憑證上的主體替代名稱清單必須包含 `lyncdiscover.<sipdomain>` 組織內每個 SIP 網域的專案。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-111">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a `lyncdiscover.<sipdomain>` entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ef3ca-112">若要在您部署行動性的 Lync Server 2010 中進行全新安裝或升級，您可以使用埠80來自動探索行動性服務，或使用適當的主體名稱和主體替代名稱重新頒發憑證。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-112">For new installations or upgrades from Lync Server 2010 where you deployed Mobility, you either used Port 80 for Autodiscover of the Mobility service, or reissued certificates with the proper subject name and subject alternative names in place.</span></span> <span data-ttu-id="ef3ca-113">檢查 Director 和前端伺服器上的憑證，以確認您選擇的是哪一個路徑。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-113">Review the certificates on your Director and Front End Server to confirm which path you chose.</span></span>

    
    </div>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="ef3ca-114">反向 Proxy 伺服器的防火牆詳細資料：外部介面</span><span class="sxs-lookup"><span data-stu-id="ef3ca-114">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ef3ca-115">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="ef3ca-115">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ef3ca-116">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ef3ca-116">Source IP Address</span></span></th>
<th><span data-ttu-id="ef3ca-117">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ef3ca-117">Destination IP Address</span></span></th>
<th><span data-ttu-id="ef3ca-118">注意事項</span><span class="sxs-lookup"><span data-stu-id="ef3ca-118">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ef3ca-119">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="ef3ca-119">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="ef3ca-120">任何</span><span class="sxs-lookup"><span data-stu-id="ef3ca-120">Any</span></span></p></td>
<td><p><span data-ttu-id="ef3ca-121">反向 Proxy 接聽程式</span><span class="sxs-lookup"><span data-stu-id="ef3ca-121">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="ef3ca-122"> (選用) 使用者進入 HTTP://publishedSiteFQDN 時重新導向至 HTTPS &lt; &gt; 。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-122">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span> <span data-ttu-id="ef3ca-123">在組織不想要修改外部 Web 服務發行規則憑證的情況下，如果為執行 Lync 的行動裝置使用 Office Web Apps for 會議和自動探索服務，也是必要的。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-123">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef3ca-124">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ef3ca-124">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ef3ca-125">任何</span><span class="sxs-lookup"><span data-stu-id="ef3ca-125">Any</span></span></p></td>
<td><p><span data-ttu-id="ef3ca-126">反向 Proxy 接聽程式</span><span class="sxs-lookup"><span data-stu-id="ef3ca-126">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="ef3ca-127">通訊錄下載、通訊錄 Web 查詢服務、自動探索、用戶端更新、會議內容、裝置更新、群組擴充、Office Web Apps for 會議、電話撥入式會議及會議。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-127">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="ef3ca-128">反向 Proxy 伺服器的防火牆詳細資料：內部介面</span><span class="sxs-lookup"><span data-stu-id="ef3ca-128">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ef3ca-129">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="ef3ca-129">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ef3ca-130">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ef3ca-130">Source IP Address</span></span></th>
<th><span data-ttu-id="ef3ca-131">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ef3ca-131">Destination IP Address</span></span></th>
<th><span data-ttu-id="ef3ca-132">注意事項</span><span class="sxs-lookup"><span data-stu-id="ef3ca-132">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ef3ca-133">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="ef3ca-133">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="ef3ca-134">內部反向 Proxy 介面</span><span class="sxs-lookup"><span data-stu-id="ef3ca-134">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="ef3ca-135">前端伺服器、前端集區、Director、Director 集區、Office Web Apps for 會議</span><span class="sxs-lookup"><span data-stu-id="ef3ca-135">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="ef3ca-136">在組織不想要修改外部 web 服務發行規則憑證的情況下，如果對執行 Lync 的行動裝置使用自動探索服務，則為必要的。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-136">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span> <span data-ttu-id="ef3ca-137">傳送至反向 Proxy 外部介面之連接埠 80 的流量，會從反向 Proxy 內部介面重新導向至連接埠 8080 上的集區，讓集區 Web 服務能夠將它與內部 Web 流量區分開來。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-137">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef3ca-138">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="ef3ca-138">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="ef3ca-139">內部反向 Proxy 介面</span><span class="sxs-lookup"><span data-stu-id="ef3ca-139">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="ef3ca-140">前端伺服器、前端集區、Director、Director 集區、Office Web Apps for 會議</span><span class="sxs-lookup"><span data-stu-id="ef3ca-140">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="ef3ca-141">傳送至反向 Proxy 外部介面之連接埠 443 上的流量，系統會重新導向至來自反向 Proxy 內部介面之連接埠 4443 上的集區，因此集區 Web 服務可以將它與內部 Web 流量區分開來。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-141">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

