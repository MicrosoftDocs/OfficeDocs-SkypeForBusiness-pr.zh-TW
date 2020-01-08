---
title: Lync Server 2013：DNS 摘要 - 反向 Proxy
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47606fe71b271e01cc7fbefbcf319a2efe93f478
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981770"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="deabb-102">Lync Server 2013 中的 DNS 摘要 - 反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="deabb-102">DNS summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="deabb-103">_**主題上次修改日期：** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="deabb-103">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="deabb-104">您可以在反向 proxy 中設定兩個網路介面卡，如下所示：</span><span class="sxs-lookup"><span data-stu-id="deabb-104">You configure two network adapters in your reverse proxy as follows:</span></span>

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a><span data-ttu-id="deabb-105">反向 Proxy 網路介面卡需求</span><span class="sxs-lookup"><span data-stu-id="deabb-105">Reverse Proxy Network Adapter Requirements</span></span>

  - <span data-ttu-id="deabb-106">**網路介面卡1（內部介面）** 範例</span><span class="sxs-lookup"><span data-stu-id="deabb-106">**Network adapter 1 (Internal Interface)** example</span></span>
    
    <span data-ttu-id="deabb-107">已指派172.25.33.40 的內部介面。</span><span class="sxs-lookup"><span data-stu-id="deabb-107">Internal interface with 172.25.33.40 assigned.</span></span>
    
    <span data-ttu-id="deabb-108">未定義預設閘道。</span><span class="sxs-lookup"><span data-stu-id="deabb-108">No default gateway is defined.</span></span>
    
    <span data-ttu-id="deabb-109">請確定有一個從網路的路由，包含對包含 Lync Server 前端池伺服器的任何網路（例如從172.25.33.0 到192.168.10.0）的反向 proxy 內部介面。</span><span class="sxs-lookup"><span data-stu-id="deabb-109">Ensure there is a route from the network containing the reverse proxy internal interface to any networks that contain Lync Server Front End pool servers (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="deabb-110">**網路介面卡2（外部介面）** 範例</span><span class="sxs-lookup"><span data-stu-id="deabb-110">**Network adapter 2 (External Interface)** example</span></span>
    
    <span data-ttu-id="deabb-111">至少已將一個公用 IP 位址指派給此網路介面卡。</span><span class="sxs-lookup"><span data-stu-id="deabb-111">A minimum of one public IP address is assigned to this network adapter.</span></span>
    
    <span data-ttu-id="deabb-112">閘道定義為指向外部週邊中的路由器或整合式防火牆。</span><span class="sxs-lookup"><span data-stu-id="deabb-112">Gateway is defined to point to the router or integrated firewall in your outer perimeter.</span></span> <span data-ttu-id="deabb-113">（案例範例中的10.45.16.1）</span><span class="sxs-lookup"><span data-stu-id="deabb-113">(10.45.16.1 in the scenario examples)</span></span>

### <a name="dns-records-required-for-reverse-proxy"></a><span data-ttu-id="deabb-114">反向 Proxy 所需的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="deabb-114">DNS Records Required for Reverse Proxy</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="deabb-115">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="deabb-115">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="deabb-116">稱</span><span class="sxs-lookup"><span data-stu-id="deabb-116">FQDN</span></span></th>
<th><span data-ttu-id="deabb-117">IP 位址</span><span class="sxs-lookup"><span data-stu-id="deabb-117">IP address</span></span></th>
<th><span data-ttu-id="deabb-118">地圖/批註</span><span class="sxs-lookup"><span data-stu-id="deabb-118">Maps to/comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="deabb-119">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="deabb-119">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="deabb-120">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="deabb-120">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="deabb-121">外部發佈資源的指派監聽程式</span><span class="sxs-lookup"><span data-stu-id="deabb-121">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="deabb-122">內部部署的外部 web 服務。</span><span class="sxs-lookup"><span data-stu-id="deabb-122">External web services from the internal deployment.</span></span> <span data-ttu-id="deabb-123">您可以針對任何要使用此反向 proxy 的 SIP 網域，為所有的 pool 和單一伺服器定義及建立其他記錄，並已定義外部 web 服務。</span><span class="sxs-lookup"><span data-stu-id="deabb-123">Additional records can be defined and created for all pools and single servers for any SIP domain that will use this reverse proxy, and has defined external web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deabb-124">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="deabb-124">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="deabb-125">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="deabb-125">webdirext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="deabb-126">外部發佈資源的指派監聽程式</span><span class="sxs-lookup"><span data-stu-id="deabb-126">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="deabb-127">您部署中的控制器或控制器池的外部 web 服務。</span><span class="sxs-lookup"><span data-stu-id="deabb-127">External web services for the Directors or Director pools in your deployment.</span></span> <span data-ttu-id="deabb-128">您可以定義多個控制器，因為有不同的控制器，可能會與其他 SIP 網域產生關聯。</span><span class="sxs-lookup"><span data-stu-id="deabb-128">You can define as many Directors as there are distinct Directors, of which may be associated with other SIP domains.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="deabb-129">定義及發佈主管的 DNS 記錄並不是前端池或主管決策。</span><span class="sxs-lookup"><span data-stu-id="deabb-129">Defining the DNS records for and publishing the Directors is not an either the Front End pool or the Director decision.</span></span> <span data-ttu-id="deabb-130">如果您使用的是董事，您必須定義併發布主管和前端池外部 web 服務。</span><span class="sxs-lookup"><span data-stu-id="deabb-130">You must define and publish both the Director and the Front End pool external web services if you are using Directors.</span></span> <span data-ttu-id="deabb-131">特定流量類型（針對驗證及其他用途）會先傳送給主管（如果它是在拓撲中定義）。</span><span class="sxs-lookup"><span data-stu-id="deabb-131">Specific traffic types (for authentication and other uses) will be sent to the Director first, if it is defined in the topology.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deabb-132">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="deabb-132">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="deabb-133">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="deabb-133">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="deabb-134">外部發佈資源的指派監聽程式</span><span class="sxs-lookup"><span data-stu-id="deabb-134">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="deabb-135">外部發佈的電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="deabb-135">Dial-in conferencing published externally</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deabb-136">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="deabb-136">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="deabb-137">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="deabb-137">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="deabb-138">外部發佈資源的指派監聽程式</span><span class="sxs-lookup"><span data-stu-id="deabb-138">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="deabb-139">外部發佈的會議</span><span class="sxs-lookup"><span data-stu-id="deabb-139">Conferences published externally</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deabb-140">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="deabb-140">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="deabb-141">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="deabb-141">officewebapps01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="deabb-142">已指派給 Office Web Apps Server 的偵聽程式</span><span class="sxs-lookup"><span data-stu-id="deabb-142">Assigned listener for Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="deabb-143">Office Web Apps 伺服器是在內部部署或在週邊部署，且已針對外部用戶端存取發佈</span><span class="sxs-lookup"><span data-stu-id="deabb-143">Office Web Apps Server deployed internally or in the perimeter, and published for external client access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deabb-144">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="deabb-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="deabb-145">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="deabb-145">lyncdiscover.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="deabb-146">外部發佈資源的指派監聽程式</span><span class="sxs-lookup"><span data-stu-id="deabb-146">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="deabb-147">Lync 探索外部發佈的自動探索的外部記錄，並包含行動性、Microsoft Lync Web App 及排程程式 Web 應用程式</span><span class="sxs-lookup"><span data-stu-id="deabb-147">Lync Discover External record for externally published AutoDiscover, and includes Mobility, Microsoft Lync Web App, and scheduler Web app</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

