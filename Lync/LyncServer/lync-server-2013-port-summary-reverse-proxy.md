---
title: Lync Server 2013：埠摘要-反向 proxy
description: Lync Server 2013：埠摘要-反向 proxy。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Reverse proxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48184251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf07800c91f5a28165eb05e14e2d775758460f50
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555249"
---
# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="df620-103">Lync Server 2013 中的埠摘要-反向 proxy</span><span class="sxs-lookup"><span data-stu-id="df620-103">Port summary - Reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df620-104">_**主題上次修改日期：** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="df620-104">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="df620-105">反向 Proxy 對於防火牆和連接埠/通訊協定具有最低需求。</span><span class="sxs-lookup"><span data-stu-id="df620-105">The reverse proxy has minimal requirements for firewall and port/protocol.</span></span>

  - <span data-ttu-id="df620-106">外部防火牆需求為 HTTPS/TCP/443 和選用的 HTTP/TCP/80。</span><span class="sxs-lookup"><span data-stu-id="df620-106">External firewall requirements are the HTTPS/TCP/443 and the optional HTTP/TCP/80.</span></span> <span data-ttu-id="df620-107">HTTPS 用於透過反向 proxy 進行 SSL 和 TLS 的安全通訊。</span><span class="sxs-lookup"><span data-stu-id="df620-107">HTTPS is used for SSL and TLS secure communications through the reverse proxy.</span></span> <span data-ttu-id="df620-108">如果您選擇允許在修改憑證時存取自動探索服務，可能會證明困難或不會有成本。</span><span class="sxs-lookup"><span data-stu-id="df620-108">HTTP is used if you choose to allow access to the Autodiscover Service when modifying certificates might prove difficult or not cost justified.</span></span>

  - <span data-ttu-id="df620-109">用戶端預期會聯繫 HTTPS 上的 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="df620-109">Clients expect to contact the Office Web Apps Server on HTTPS.</span></span> <span data-ttu-id="df620-110">Office Web Apps Server 期望來自 HTTPS/TCP/443 的內部用戶端進行通訊。</span><span class="sxs-lookup"><span data-stu-id="df620-110">The Office Web Apps Server expects communication from internal clients on HTTPS/TCP/443.</span></span> <span data-ttu-id="df620-111">建議的設定是允許 HTTPS/TCP/443 從反向 proxy 到 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="df620-111">The recommended configuration is to allow HTTPS/TCP/443 from the reverse proxy to the Office Web Apps Server.</span></span>

  - <span data-ttu-id="df620-112">埠8080是用來將流量從反向 proxy 內部介面路由傳送至前端伺服器、前端集區虛擬 IP (VIP) 或選用的 Director 或 Director 集區 VIP。</span><span class="sxs-lookup"><span data-stu-id="df620-112">Port 8080 is used to route traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP.</span></span> <span data-ttu-id="df620-113">在需要修改外部 web 服務發行規則憑證的情況下（例如，如果您有大量 SIP 網域) 時，執行 Lync 的行動裝置會需要端口 TCP 8080，以找出自動探索服務 (例如）。</span><span class="sxs-lookup"><span data-stu-id="df620-113">Port TCP 8080 is required for mobile devices running Lync to locate the Autodiscover Service in situations where modifying the external web service publishing rule certificate is undesirable (for example, if you have a large number of SIP domains).</span></span> <span data-ttu-id="df620-114">如果您選擇取得含有必要 SAN 項目的新憑證，則不需要使用連接埠 TCP 8080，其為選用項目。</span><span class="sxs-lookup"><span data-stu-id="df620-114">If you choose to acquire new certificates with the necessary SAN entries, the port TCP 8080 is not needed and is optional.</span></span>

  - <span data-ttu-id="df620-115">埠4443用於從反向 proxy 內部介面到前端伺服器、前端集區虛擬 IP (VIP) 或選用的 Director 或 Director 集區 VIP 的流量</span><span class="sxs-lookup"><span data-stu-id="df620-115">Port 4443 is used for traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP</span></span>
    
    <span data-ttu-id="df620-116">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="df620-116">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>  
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="df620-117">請不要將 4443 over TCP 的反向 proxy 與來自 Standard Edition server 的 TCP 流量和管理中央管理存放區角色的前端集區的內部4443部署混淆。</span><span class="sxs-lookup"><span data-stu-id="df620-117">Do not confuse the 4443 over TCP from the reverse proxy to the internal deployment for the port 4443 over TCP traffic from the Standard Edition server or the Front End pool that manages the Central Management store role.</span></span>

    
    </div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="df620-118">埠與通訊協定詳細資料</span><span class="sxs-lookup"><span data-stu-id="df620-118">Port and Protocol Details</span></span>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="df620-119">反向 Proxy 伺服器的防火牆詳細資料：外部介面</span><span class="sxs-lookup"><span data-stu-id="df620-119">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="df620-120">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="df620-120">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="df620-121">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="df620-121">Source IP Address</span></span></th>
<th><span data-ttu-id="df620-122">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="df620-122">Destination IP Address</span></span></th>
<th><span data-ttu-id="df620-123">注意事項</span><span class="sxs-lookup"><span data-stu-id="df620-123">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="df620-124">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="df620-124">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="df620-125">任何</span><span class="sxs-lookup"><span data-stu-id="df620-125">Any</span></span></p></td>
<td><p><span data-ttu-id="df620-126">反向 Proxy 接聽程式</span><span class="sxs-lookup"><span data-stu-id="df620-126">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="df620-127"> (選用) 使用者進入 HTTP://publishedSiteFQDN 時重新導向至 HTTPS &lt; &gt; 。</span><span class="sxs-lookup"><span data-stu-id="df620-127">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span></p>
<p><span data-ttu-id="df620-128">在組織不想要修改外部 Web 服務發行規則憑證的情況下，如果為執行 Lync 的行動裝置使用 Office Web Apps for 會議和自動探索服務，也是必要的。</span><span class="sxs-lookup"><span data-stu-id="df620-128">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df620-129">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="df620-129">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="df620-130">任何</span><span class="sxs-lookup"><span data-stu-id="df620-130">Any</span></span></p></td>
<td><p><span data-ttu-id="df620-131">反向 Proxy 接聽程式</span><span class="sxs-lookup"><span data-stu-id="df620-131">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="df620-132">通訊錄下載、通訊錄 Web 查詢服務、自動探索、用戶端更新、會議內容、裝置更新、群組擴充、Office Web Apps for 會議、電話撥入式會議及會議。</span><span class="sxs-lookup"><span data-stu-id="df620-132">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="df620-133">反向 Proxy 伺服器的防火牆詳細資料：內部介面</span><span class="sxs-lookup"><span data-stu-id="df620-133">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="df620-134">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="df620-134">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="df620-135">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="df620-135">Source IP Address</span></span></th>
<th><span data-ttu-id="df620-136">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="df620-136">Destination IP Address</span></span></th>
<th><span data-ttu-id="df620-137">注意事項</span><span class="sxs-lookup"><span data-stu-id="df620-137">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="df620-138">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="df620-138">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="df620-139">內部反向 Proxy 介面</span><span class="sxs-lookup"><span data-stu-id="df620-139">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="df620-140">前端伺服器、前端集區、Director、Director 集區</span><span class="sxs-lookup"><span data-stu-id="df620-140">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="df620-141">在組織不想要修改外部 web 服務發行規則憑證的情況下，如果對執行 Lync 的行動裝置使用自動探索服務，則為必要的。</span><span class="sxs-lookup"><span data-stu-id="df620-141">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p>
<p><span data-ttu-id="df620-142">傳送至反向 Proxy 外部介面之連接埠 80 的流量，會從反向 Proxy 內部介面重新導向至連接埠 8080 上的集區，讓集區 Web 服務能夠將它與內部 Web 流量區分開來。</span><span class="sxs-lookup"><span data-stu-id="df620-142">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df620-143">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="df620-143">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="df620-144">內部反向 Proxy 介面</span><span class="sxs-lookup"><span data-stu-id="df620-144">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="df620-145">前端伺服器、前端集區、Director、Director 集區</span><span class="sxs-lookup"><span data-stu-id="df620-145">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="df620-146">傳送至反向 Proxy 外部介面之連接埠 443 上的流量，系統會重新導向至來自反向 Proxy 內部介面之連接埠 4443 上的集區，因此集區 Web 服務可以將它與內部 Web 流量區分開來。</span><span class="sxs-lookup"><span data-stu-id="df620-146">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df620-147">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="df620-147">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="df620-148">內部反向 Proxy 介面</span><span class="sxs-lookup"><span data-stu-id="df620-148">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="df620-149">適用于會議的 Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="df620-149">Office Web Apps for conferencing</span></span></p></td>
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

