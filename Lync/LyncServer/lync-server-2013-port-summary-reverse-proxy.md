---
title: Lync Server 2013：連接埠摘要 - 反向 Proxy
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Reverse proxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48184251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a86b993a35210934f5ebef61464c11a153bf297
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="48dc4-102">Lync Server 2013 中的連接埠摘要 - 反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="48dc4-102">Port summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48dc4-103">_**主題上次修改日期：** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="48dc4-103">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="48dc4-104">反向 proxy 對防火牆和埠/通訊協定的需求最低。</span><span class="sxs-lookup"><span data-stu-id="48dc4-104">The reverse proxy has minimal requirements for firewall and port/protocol.</span></span>

  - <span data-ttu-id="48dc4-105">外部防火牆需求是 HTTPS/TCP/443 以及選用的 HTTP/TCP/80。</span><span class="sxs-lookup"><span data-stu-id="48dc4-105">External firewall requirements are the HTTPS/TCP/443 and the optional HTTP/TCP/80.</span></span> <span data-ttu-id="48dc4-106">HTTPS 是透過反向 proxy 使用 SSL 和 TLS 安全通訊。</span><span class="sxs-lookup"><span data-stu-id="48dc4-106">HTTPS is used for SSL and TLS secure communications through the reverse proxy.</span></span> <span data-ttu-id="48dc4-107">如果您選擇在修改憑證時允許存取自動探索服務，可能會證明困難或不是成本。</span><span class="sxs-lookup"><span data-stu-id="48dc4-107">HTTP is used if you choose to allow access to the Autodiscover Service when modifying certificates might prove difficult or not cost justified.</span></span>

  - <span data-ttu-id="48dc4-108">用戶端預期要與 HTTPS 上的 Office Web Apps 伺服器取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="48dc4-108">Clients expect to contact the Office Web Apps Server on HTTPS.</span></span> <span data-ttu-id="48dc4-109">Office Web Apps 伺服器預期從 HTTPS/TCP/443 上的內部用戶端進行通訊。</span><span class="sxs-lookup"><span data-stu-id="48dc4-109">The Office Web Apps Server expects communication from internal clients on HTTPS/TCP/443.</span></span> <span data-ttu-id="48dc4-110">建議的設定是允許從反向 proxy 的 HTTPS/TCP/443 到 Office Web Apps 伺服器。</span><span class="sxs-lookup"><span data-stu-id="48dc4-110">The recommended configuration is to allow HTTPS/TCP/443 from the reverse proxy to the Office Web Apps Server.</span></span>

  - <span data-ttu-id="48dc4-111">Port 8080 是用來將流量從反向 proxy 內部介面路由到前端伺服器、前端池虛擬 IP （VIP），或是選用控制器或控制器池 VIP。</span><span class="sxs-lookup"><span data-stu-id="48dc4-111">Port 8080 is used to route traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP.</span></span> <span data-ttu-id="48dc4-112">在執行 Lync 的行動裝置上，如果您需要修改外部 web 服務發佈規則憑證的情況（例如，如果您有大量 SIP 網域），則必須使用埠 TCP 8080 來尋找自動探索服務。</span><span class="sxs-lookup"><span data-stu-id="48dc4-112">Port TCP 8080 is required for mobile devices running Lync to locate the Autodiscover Service in situations where modifying the external web service publishing rule certificate is undesirable (for example, if you have a large number of SIP domains).</span></span> <span data-ttu-id="48dc4-113">如果您選擇要用所需的 SAN 專案來取得新憑證，則不需要端口 TCP 8080，且是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="48dc4-113">If you choose to acquire new certificates with the necessary SAN entries, the port TCP 8080 is not needed and is optional.</span></span>

  - <span data-ttu-id="48dc4-114">埠4443用於從反向 proxy 內部介面到前端伺服器、前端池虛擬 IP （VIP）或選用控制器或控制器池 VIP 的流量</span><span class="sxs-lookup"><span data-stu-id="48dc4-114">Port 4443 is used for traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP</span></span>
    
    <span data-ttu-id="48dc4-115">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-") 45b7-a8b7-a8c89f09c97c</span><span class="sxs-lookup"><span data-stu-id="48dc4-115">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>  
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="48dc4-116">請不要將4443的 TCP 從反向 proxy 與來自標準版 server 的內部4443部署，或是管理中央管理儲存角色的前端池。</span><span class="sxs-lookup"><span data-stu-id="48dc4-116">Do not confuse the 4443 over TCP from the reverse proxy to the internal deployment for the port 4443 over TCP traffic from the Standard Edition server or the Front End pool that manages the Central Management store role.</span></span>

    
    </div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="48dc4-117">埠與通訊協定詳細資料</span><span class="sxs-lookup"><span data-stu-id="48dc4-117">Port and Protocol Details</span></span>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="48dc4-118">反向 Proxy 伺服器的防火牆詳細資料：外部介面</span><span class="sxs-lookup"><span data-stu-id="48dc4-118">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48dc4-119">通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="48dc4-119">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="48dc4-120">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="48dc4-120">Source IP Address</span></span></th>
<th><span data-ttu-id="48dc4-121">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="48dc4-121">Destination IP Address</span></span></th>
<th><span data-ttu-id="48dc4-122">筆記</span><span class="sxs-lookup"><span data-stu-id="48dc4-122">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48dc4-123">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="48dc4-123">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="48dc4-124">每</span><span class="sxs-lookup"><span data-stu-id="48dc4-124">Any</span></span></p></td>
<td><p><span data-ttu-id="48dc4-125">反向 proxy 偵聽程式</span><span class="sxs-lookup"><span data-stu-id="48dc4-125">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="48dc4-126">可選如果使用者進入 HTTP://&lt;publishedSiteFQDN&gt;，則重定向至 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="48dc4-126">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span></p>
<p><span data-ttu-id="48dc4-127">如果您在組織不想要修改外部 Web 服務發佈規則憑證的情況下，使用 Office Web Apps for 會議，以及執行 Lync 之行動裝置的自動探索服務，也需要。</span><span class="sxs-lookup"><span data-stu-id="48dc4-127">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48dc4-128">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="48dc4-128">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="48dc4-129">每</span><span class="sxs-lookup"><span data-stu-id="48dc4-129">Any</span></span></p></td>
<td><p><span data-ttu-id="48dc4-130">反向 proxy 偵聽程式</span><span class="sxs-lookup"><span data-stu-id="48dc4-130">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="48dc4-131">通訊錄下載、通訊錄網頁查詢服務、自動探索、用戶端更新、會議內容、裝置更新、群組延伸、Office Web Apps for 會議、電話撥入式會議及會議。</span><span class="sxs-lookup"><span data-stu-id="48dc4-131">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="48dc4-132">反向 Proxy 伺服器的防火牆詳細資料：內部介面</span><span class="sxs-lookup"><span data-stu-id="48dc4-132">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48dc4-133">通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="48dc4-133">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="48dc4-134">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="48dc4-134">Source IP Address</span></span></th>
<th><span data-ttu-id="48dc4-135">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="48dc4-135">Destination IP Address</span></span></th>
<th><span data-ttu-id="48dc4-136">筆記</span><span class="sxs-lookup"><span data-stu-id="48dc4-136">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48dc4-137">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="48dc4-137">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="48dc4-138">內部反向 proxy 介面</span><span class="sxs-lookup"><span data-stu-id="48dc4-138">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="48dc4-139">前端伺服器、前端池、導演、控制器池</span><span class="sxs-lookup"><span data-stu-id="48dc4-139">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="48dc4-140">如果組織不想要修改外部 web 服務發佈規則憑證的情況下，在執行 Lync 的行動裝置上使用自動探索服務，則是必要的。</span><span class="sxs-lookup"><span data-stu-id="48dc4-140">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p>
<p><span data-ttu-id="48dc4-141">在反向 proxy 外部介面上傳送到埠80的流量，會從反向 proxy 內部介面重新導向到埠8080上的 pool，讓 pool Web 服務可以區別內部網路流量。</span><span class="sxs-lookup"><span data-stu-id="48dc4-141">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48dc4-142">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="48dc4-142">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="48dc4-143">內部反向 proxy 介面</span><span class="sxs-lookup"><span data-stu-id="48dc4-143">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="48dc4-144">前端伺服器、前端池、導演、控制器池</span><span class="sxs-lookup"><span data-stu-id="48dc4-144">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="48dc4-145">在反向 proxy 外部介面上傳送到埠443的流量，會從反向 proxy 內部介面重新導向到埠4443上的 pool，讓 pool web 服務可以區別內部網路流量。</span><span class="sxs-lookup"><span data-stu-id="48dc4-145">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48dc4-146">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="48dc4-146">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="48dc4-147">內部反向 proxy 介面</span><span class="sxs-lookup"><span data-stu-id="48dc4-147">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="48dc4-148">適用于會議的 Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="48dc4-148">Office Web Apps for conferencing</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

