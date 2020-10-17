---
title: Lync Server 2013： DNS 摘要-反向 proxy
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a468e74206fdc6bad8f078267688450636b8a725
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532140"
---
# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="94134-102">Lync Server 2013 中的 DNS 摘要-反向 proxy</span><span class="sxs-lookup"><span data-stu-id="94134-102">DNS summary - Reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94134-103">_**主題上次修改日期：** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="94134-103">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="94134-104">您可以在反向 Proxy 上設定兩片網路介面卡，如下所示：</span><span class="sxs-lookup"><span data-stu-id="94134-104">You configure two network adapters in your reverse proxy as follows:</span></span>

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a><span data-ttu-id="94134-105">反向 Proxy 網路介面卡需求</span><span class="sxs-lookup"><span data-stu-id="94134-105">Reverse Proxy Network Adapter Requirements</span></span>

  - <span data-ttu-id="94134-106">**網路介面卡 1 (內部介面)** 範例</span><span class="sxs-lookup"><span data-stu-id="94134-106">**Network adapter 1 (Internal Interface)** example</span></span>
    
    <span data-ttu-id="94134-107">已指派 172.25.33.40 的內部介面。</span><span class="sxs-lookup"><span data-stu-id="94134-107">Internal interface with 172.25.33.40 assigned.</span></span>
    
    <span data-ttu-id="94134-108">未定義預設閘道。</span><span class="sxs-lookup"><span data-stu-id="94134-108">No default gateway is defined.</span></span>
    
    <span data-ttu-id="94134-109">確定有從包含反向 proxy 內部介面的網路到包含 Lync Server 前端集區伺服器的任何網路的路由 (例如，從172.25.33.0 到 192.168.10.0) 。</span><span class="sxs-lookup"><span data-stu-id="94134-109">Ensure there is a route from the network containing the reverse proxy internal interface to any networks that contain Lync Server Front End pool servers (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="94134-110">**網路介面卡 2 (外部介面)** 範例</span><span class="sxs-lookup"><span data-stu-id="94134-110">**Network adapter 2 (External Interface)** example</span></span>
    
    <span data-ttu-id="94134-111">至少指派一個公用 IP 位址給這個網路介面卡。</span><span class="sxs-lookup"><span data-stu-id="94134-111">A minimum of one public IP address is assigned to this network adapter.</span></span>
    
    <span data-ttu-id="94134-p101">已將閘道定義為指向您外部周邊中的路由器或整合式防火牆 (此範例中為 10.45.16.1)。</span><span class="sxs-lookup"><span data-stu-id="94134-p101">Gateway is defined to point to the router or integrated firewall in your outer perimeter. (10.45.16.1 in the scenario examples)</span></span>

### <a name="dns-records-required-for-reverse-proxy"></a><span data-ttu-id="94134-114">反向 Proxy 所需的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="94134-114">DNS Records Required for Reverse Proxy</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="94134-115">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="94134-115">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="94134-116">FQDN</span><span class="sxs-lookup"><span data-stu-id="94134-116">FQDN</span></span></th>
<th><span data-ttu-id="94134-117">IP 位址</span><span class="sxs-lookup"><span data-stu-id="94134-117">IP address</span></span></th>
<th><span data-ttu-id="94134-118">對應至/註解</span><span class="sxs-lookup"><span data-stu-id="94134-118">Maps to/comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="94134-119">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="94134-119">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="94134-120">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94134-120">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="94134-121">為對外發佈的資源指派聆聽程式</span><span class="sxs-lookup"><span data-stu-id="94134-121">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="94134-p102">從內部部署到外部 Web 服務。您可為所有集區及單一伺服器，針對要使用此反向 Proxy，且具有已定義之外部 Web 服務的 SIP 網域，定義及建立其他記錄。</span><span class="sxs-lookup"><span data-stu-id="94134-p102">External web services from the internal deployment. Additional records can be defined and created for all pools and single servers for any SIP domain that will use this reverse proxy, and has defined external web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94134-124">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="94134-124">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="94134-125">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94134-125">webdirext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="94134-126">為對外發佈的資源指派聆聽程式</span><span class="sxs-lookup"><span data-stu-id="94134-126">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="94134-127">部署中 Director 或 Director 集區的外部 web 服務。</span><span class="sxs-lookup"><span data-stu-id="94134-127">External web services for the Directors or Director pools in your deployment.</span></span> <span data-ttu-id="94134-128">您可以定義多個具有不同 Director 的 Director，其可能會與其他 SIP 網域產生關聯。</span><span class="sxs-lookup"><span data-stu-id="94134-128">You can define as many Directors as there are distinct Directors, of which may be associated with other SIP domains.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="94134-129">定義及發佈 Director 的 DNS 記錄不是前端集區或 Director 決定。</span><span class="sxs-lookup"><span data-stu-id="94134-129">Defining the DNS records for and publishing the Directors is not an either the Front End pool or the Director decision.</span></span> <span data-ttu-id="94134-130">如果您使用 Director，則必須定義及發佈 Director 和前端集區外部 web 服務。</span><span class="sxs-lookup"><span data-stu-id="94134-130">You must define and publish both the Director and the Front End pool external web services if you are using Directors.</span></span> <span data-ttu-id="94134-131">若要將特定流量類型 (用於驗證及其他使用) ，請先將它傳送給 Director （如果是在拓撲中定義）。</span><span class="sxs-lookup"><span data-stu-id="94134-131">Specific traffic types (for authentication and other uses) will be sent to the Director first, if it is defined in the topology.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94134-132">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="94134-132">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="94134-133">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94134-133">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="94134-134">為對外發佈的資源指派聆聽程式</span><span class="sxs-lookup"><span data-stu-id="94134-134">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="94134-135">電話撥入式會議已對外發行</span><span class="sxs-lookup"><span data-stu-id="94134-135">Dial-in conferencing published externally</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94134-136">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="94134-136">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="94134-137">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94134-137">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="94134-138">為對外發佈的資源指派聆聽程式</span><span class="sxs-lookup"><span data-stu-id="94134-138">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="94134-139">已對外發行會議</span><span class="sxs-lookup"><span data-stu-id="94134-139">Conferences published externally</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94134-140">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="94134-140">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="94134-141">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94134-141">officewebapps01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="94134-142">Office Web Apps Server 的指派監聽器</span><span class="sxs-lookup"><span data-stu-id="94134-142">Assigned listener for Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="94134-143">Office Web Apps Server 內部部署或在周邊環境中部署，並已發佈供外部用戶端存取</span><span class="sxs-lookup"><span data-stu-id="94134-143">Office Web Apps Server deployed internally or in the perimeter, and published for external client access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94134-144">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="94134-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="94134-145">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94134-145">lyncdiscover.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="94134-146">為對外發佈的資源指派聆聽程式</span><span class="sxs-lookup"><span data-stu-id="94134-146">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="94134-147">Lync 探索外部發佈 AutoDiscover 的外部記錄，並包含行動性、Microsoft Lync Web App 及排程器 Web app</span><span class="sxs-lookup"><span data-stu-id="94134-147">Lync Discover External record for externally published AutoDiscover, and includes Mobility, Microsoft Lync Web App, and scheduler Web app</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

