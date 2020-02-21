---
title: Lync Server 2013： 連接埠摘要-自動探索
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
ms.openlocfilehash: 93750418bce8ea98d0cee385232bc09bb0bd63bc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="ea5ea-102">連接埠摘要-Lync Server 2013 中的自動探索</span><span class="sxs-lookup"><span data-stu-id="ea5ea-102">Port summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea5ea-103">_**上次修改主題：** 2013年-03-05_</span><span class="sxs-lookup"><span data-stu-id="ea5ea-103">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="ea5ea-104">Lync Server 2013 自動探索服務會執行 Director 與前端集區伺服器，以及當 DNS 使用發佈`lyncdiscover.<domain>`和`lyncdiscoverinternal.<domain>`主機記錄，可以用戶端用來尋找 [Lync Server 功能。</span><span class="sxs-lookup"><span data-stu-id="ea5ea-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS using the `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` host records, can be used by clients to locate Lync Server features.</span></span> <span data-ttu-id="ea5ea-105">為了讓執行 Lync 行動裝置的行動裝置使用自動探索，您可能需要先修改任何 Director 與前端伺服器執行自動探索服務的憑證主體替代名稱清單。</span><span class="sxs-lookup"><span data-stu-id="ea5ea-105">In order for mobile devices running Lync Mobile to use Autodiscover, you may first need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="ea5ea-106">此外，可能還需要針對在反向 Proxy 上用於外部 Web 服務發行規則的憑證，修改主體替代名稱清單。</span><span class="sxs-lookup"><span data-stu-id="ea5ea-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="ea5ea-107">決定是否要在反向 proxy 上使用主體替代名稱清單根據您是否發佈連接埠 80 或連接埠 443 上的自動探索服務：</span><span class="sxs-lookup"><span data-stu-id="ea5ea-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="ea5ea-108">**在 [連接埠 80 上發佈**   的行動裝置，沒有任何憑證變更所需如果透過連接埠 80，自動探索服務的初始查詢就會發生。</span><span class="sxs-lookup"><span data-stu-id="ea5ea-108">**Published on port 80**   For Mobile devices, no certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="ea5ea-109">這是因為執行 Lync 的行動裝置會存取外部連接埠 80 上的反向 proxy，然後重新導向至 Director 或前端伺服器上連接埠 8080 內部。</span><span class="sxs-lookup"><span data-stu-id="ea5ea-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span>

  - <span data-ttu-id="ea5ea-110">**在 [連接埠 443 上發行**   發行規則必須包含外部 web 服務所使用的憑證上的 [主旨替代名稱] 清單`lyncdiscover.<sipdomain>`每個 SIP 網域組織內的項目。</span><span class="sxs-lookup"><span data-stu-id="ea5ea-110">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a `lyncdiscover.<sipdomain>` entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ea5ea-111">對於新的安裝或從您部署行動性的 Lync Server 2010 的升級，您連接埠 80 用於自動探索的 Mobility service，或重新發出憑證的適當的主體名稱和主體替代名稱就地。</span><span class="sxs-lookup"><span data-stu-id="ea5ea-111">For new installations or upgrades from Lync Server 2010 where you deployed Mobility, you either used Port 80 for Autodiscover of the Mobility service, or reissued certificates with the proper subject name and subject alternative names in place.</span></span> <span data-ttu-id="ea5ea-112">檢閱您選擇的憑證上 Director 與前端伺服器，以確認的路徑。</span><span class="sxs-lookup"><span data-stu-id="ea5ea-112">Review the certificates on your Director and Front End Server to confirm which path you chose.</span></span>

    
    </div>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="ea5ea-113">反向 Proxy 伺服器的防火牆詳細資料：外部介面</span><span class="sxs-lookup"><span data-stu-id="ea5ea-113">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea5ea-114">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="ea5ea-114">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ea5ea-115">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ea5ea-115">Source IP Address</span></span></th>
<th><span data-ttu-id="ea5ea-116">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ea5ea-116">Destination IP Address</span></span></th>
<th><span data-ttu-id="ea5ea-117">附註</span><span class="sxs-lookup"><span data-stu-id="ea5ea-117">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea5ea-118">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="ea5ea-118">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="ea5ea-119">任何</span><span class="sxs-lookup"><span data-stu-id="ea5ea-119">Any</span></span></p></td>
<td><p><span data-ttu-id="ea5ea-120">反向 Proxy 接聽程式</span><span class="sxs-lookup"><span data-stu-id="ea5ea-120">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="ea5ea-121">（選用）重新導向至 HTTPS 使用者輸入 http://&lt;publishedSiteFQDN&gt;。</span><span class="sxs-lookup"><span data-stu-id="ea5ea-121">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span> <span data-ttu-id="ea5ea-122">如果使用 Office Web Apps 會議] 和 [在組織不想要修改外部 web 服務發行規則憑證的情況中執行 Lync 的行動裝置的自動探索服務，也需要。</span><span class="sxs-lookup"><span data-stu-id="ea5ea-122">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea5ea-123">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ea5ea-123">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ea5ea-124">任何</span><span class="sxs-lookup"><span data-stu-id="ea5ea-124">Any</span></span></p></td>
<td><p><span data-ttu-id="ea5ea-125">反向 Proxy 接聽程式</span><span class="sxs-lookup"><span data-stu-id="ea5ea-125">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="ea5ea-126">通訊錄下載、 通訊錄 Web 查詢服務、 自動探索、 用戶端更新、 會議內容、 裝置更新、 群組擴充，Office Web Apps for 會議、 電話撥入式會議及會議。</span><span class="sxs-lookup"><span data-stu-id="ea5ea-126">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="ea5ea-127">反向 Proxy 伺服器的防火牆詳細資料：內部介面</span><span class="sxs-lookup"><span data-stu-id="ea5ea-127">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea5ea-128">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="ea5ea-128">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ea5ea-129">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ea5ea-129">Source IP Address</span></span></th>
<th><span data-ttu-id="ea5ea-130">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ea5ea-130">Destination IP Address</span></span></th>
<th><span data-ttu-id="ea5ea-131">附註</span><span class="sxs-lookup"><span data-stu-id="ea5ea-131">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea5ea-132">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="ea5ea-132">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="ea5ea-133">內部反向 Proxy 介面</span><span class="sxs-lookup"><span data-stu-id="ea5ea-133">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="ea5ea-134">前端伺服器上，前端集區、 Director、 Director 集區，Office Web Apps for 會議</span><span class="sxs-lookup"><span data-stu-id="ea5ea-134">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="ea5ea-135">如果在組織不想要修改外部 web 服務發行規則憑證的情況中執行 Lync 的行動裝置使用自動探索服務，需要。</span><span class="sxs-lookup"><span data-stu-id="ea5ea-135">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span> <span data-ttu-id="ea5ea-136">傳送至反向 Proxy 外部介面之連接埠 80 的流量，會從反向 Proxy 內部介面重新導向至連接埠 8080 上的集區，讓集區 Web 服務能夠將它與內部 Web 流量區分開來。</span><span class="sxs-lookup"><span data-stu-id="ea5ea-136">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea5ea-137">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="ea5ea-137">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="ea5ea-138">內部反向 Proxy 介面</span><span class="sxs-lookup"><span data-stu-id="ea5ea-138">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="ea5ea-139">前端伺服器上，前端集區、 Director、 Director 集區，Office Web Apps for 會議</span><span class="sxs-lookup"><span data-stu-id="ea5ea-139">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="ea5ea-140">傳送至反向 Proxy 外部介面之連接埠 443 上的流量，系統會重新導向至來自反向 Proxy 內部介面之連接埠 4443 上的集區，因此集區 Web 服務可以將它與內部 Web 流量區分開來。</span><span class="sxs-lookup"><span data-stu-id="ea5ea-140">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

