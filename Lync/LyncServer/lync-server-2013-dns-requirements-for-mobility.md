---
title: Lync Server 2013：行動性的 DNS 需求
description: Lync Server 2013：行動性的 DNS 需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for mobility
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48185624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2a8377dc7c856bb7250817cb3b8b66ed7789d3b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574299"
---
# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a><span data-ttu-id="d48a1-103">使用 Lync Server 2013 行動的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="d48a1-103">DNS requirements for mobility with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d48a1-104">_**主題上次修改日期：** 2012-11-13_</span><span class="sxs-lookup"><span data-stu-id="d48a1-104">_**Topic Last Modified:** 2012-11-13_</span></span>

<span data-ttu-id="d48a1-105">當您部署 Lync Server 2013 行動功能時，您可以使用 Microsoft Lync Server 2013 自動探索服務提供的新 URLs，也可以使用現有的 Web 服務 URLs。</span><span class="sxs-lookup"><span data-stu-id="d48a1-105">When you deploy the Lync Server 2013 mobility feature, you can use the new URLs that are available with the Microsoft Lync Server 2013 Autodiscover Service, or you can use your existing Web Services URLs.</span></span> <span data-ttu-id="d48a1-106">如果您使用現有的 URLs，使用者必須在行動裝置設定中手動輸入 URLs。</span><span class="sxs-lookup"><span data-stu-id="d48a1-106">If you use your existing URLs, users need to manually enter the URLs in their mobile device settings.</span></span> <span data-ttu-id="d48a1-107">此選項通常用於疑難排解。</span><span class="sxs-lookup"><span data-stu-id="d48a1-107">This option is typically used for troubleshooting.</span></span> <span data-ttu-id="d48a1-108">當您使用新的 URLs 時，行動用戶端可以自動探索 Lync Server 2013 資源。</span><span class="sxs-lookup"><span data-stu-id="d48a1-108">When you use the new URLs, mobile clients can automatically discover Lync Server 2013 resources.</span></span> <span data-ttu-id="d48a1-109">當您支援自動探索時，您必須新增網域名稱系統 (DNS) 記錄。</span><span class="sxs-lookup"><span data-stu-id="d48a1-109">When you support automatic discovery, you need to add new Domain Name System (DNS) records.</span></span> <span data-ttu-id="d48a1-110">本節說明自動探索所需的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="d48a1-110">This section describes the DNS records that are required for automatic discovery.</span></span>

<span data-ttu-id="d48a1-111">若要支援自動探索，您必須為每個 SIP 網域建立下列 DNS 記錄：</span><span class="sxs-lookup"><span data-stu-id="d48a1-111">To support automatic discovery, you need to create the following DNS records for each SIP domain:</span></span>

  - <span data-ttu-id="d48a1-112">內部 DNS 記錄，以支援從組織網路內部連線的行動使用者</span><span class="sxs-lookup"><span data-stu-id="d48a1-112">An internal DNS record to support mobile users who connect from within your organization's network</span></span>

  - <span data-ttu-id="d48a1-113">外部 (或公用) DNS 記錄，以支援從網際網路連線的行動使用者</span><span class="sxs-lookup"><span data-stu-id="d48a1-113">An external, or public, DNS record to support mobile users who connect from the Internet</span></span>

<span data-ttu-id="d48a1-114">內部自動探索 URL 應該不能從您的網路外部定址。</span><span class="sxs-lookup"><span data-stu-id="d48a1-114">The internal automatic discovery URL should not be addressable from outside your network.</span></span> <span data-ttu-id="d48a1-115">外部自動探索 URL 應該不能從您的網路內部定址。</span><span class="sxs-lookup"><span data-stu-id="d48a1-115">The external automatic discovery URL should not be addressable from within your network.</span></span> <span data-ttu-id="d48a1-116">不過，如果您無法滿足外部 URL 的此需求，行動用戶端功能應該不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="d48a1-116">However, if you cannot meet this requirement for the external URL, mobile client functionally should not be affected.</span></span>

<span data-ttu-id="d48a1-117">DNS 記錄可以是 CNAME 記錄或 A (主機) 記錄。</span><span class="sxs-lookup"><span data-stu-id="d48a1-117">The DNS records can be either CNAME records or A (host) records.</span></span>

<span data-ttu-id="d48a1-118">**內部 DNS 記錄**</span><span class="sxs-lookup"><span data-stu-id="d48a1-118">**Internal DNS records**</span></span>

<span data-ttu-id="d48a1-119">您必須建立下列其中一個內部 DNS 記錄：</span><span class="sxs-lookup"><span data-stu-id="d48a1-119">You need to create one of the following internal DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d48a1-120">記錄類型</span><span class="sxs-lookup"><span data-stu-id="d48a1-120">Record type</span></span></th>
<th><span data-ttu-id="d48a1-121">主機名稱或 SRV 定義</span><span class="sxs-lookup"><span data-stu-id="d48a1-121">Host name or SRV definition</span></span></th>
<th><span data-ttu-id="d48a1-122">解析為</span><span class="sxs-lookup"><span data-stu-id="d48a1-122">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d48a1-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="d48a1-123">CNAME</span></span></p></td>
<td><p><span data-ttu-id="d48a1-124">lyncdiscoverinternal。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="d48a1-124">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="d48a1-125">內部 Web 服務完整功能變數名稱 (Director 集區的 FQDN) （如果有的話），或如果您沒有 Director，則為前端集區。</span><span class="sxs-lookup"><span data-stu-id="d48a1-125">Internal Web Services fully qualified domain name (FQDN) for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48a1-126">A (主機)</span><span class="sxs-lookup"><span data-stu-id="d48a1-126">A (host)</span></span></p></td>
<td><p><span data-ttu-id="d48a1-127">lyncdiscoverinternal。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="d48a1-127">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="d48a1-128">內部 Web 服務 IP 位址 (虛擬 IP (VIP) 位址如果您擁有 Director 集區的負載平衡器) （如果有的話），或如果您沒有 Director，則使用的前端集區。</span><span class="sxs-lookup"><span data-stu-id="d48a1-128">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d48a1-129">**外部 DNS 記錄**</span><span class="sxs-lookup"><span data-stu-id="d48a1-129">**External DNS records**</span></span>

<span data-ttu-id="d48a1-130">您需要建立下列其中一項外部 DNS 記錄：</span><span class="sxs-lookup"><span data-stu-id="d48a1-130">You need to create one of the following external DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d48a1-131">記錄類型</span><span class="sxs-lookup"><span data-stu-id="d48a1-131">Record type</span></span></th>
<th><span data-ttu-id="d48a1-132">主機名稱</span><span class="sxs-lookup"><span data-stu-id="d48a1-132">Host name</span></span></th>
<th><span data-ttu-id="d48a1-133">解析為</span><span class="sxs-lookup"><span data-stu-id="d48a1-133">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d48a1-134">CNAME</span><span class="sxs-lookup"><span data-stu-id="d48a1-134">CNAME</span></span></p></td>
<td><p><span data-ttu-id="d48a1-135">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="d48a1-135">lyncdiscover.</span></span> <span data-ttu-id="d48a1-136">&lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="d48a1-136">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="d48a1-137">Director 集區的外部 Web 服務 FQDN （如果有的話），或如果您沒有 Director，則為前端集區。</span><span class="sxs-lookup"><span data-stu-id="d48a1-137">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d48a1-138">A (主機)</span><span class="sxs-lookup"><span data-stu-id="d48a1-138">A (host)</span></span></p></td>
<td><p><span data-ttu-id="d48a1-139">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="d48a1-139">lyncdiscover.</span></span> <span data-ttu-id="d48a1-140">&lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="d48a1-140">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="d48a1-141">當您使用反向 proxy 的負載平衡器) 時，的外部或公用 IP 位址 (VIP 位址</span><span class="sxs-lookup"><span data-stu-id="d48a1-141">External or public IP address (VIP address if you use a load balancer) of the reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d48a1-142">SRV</span><span class="sxs-lookup"><span data-stu-id="d48a1-142">SRV</span></span></p></td>
<td><p><span data-ttu-id="d48a1-143">_sipfederationtls _sipfederationtls._tcp。</span><span class="sxs-lookup"><span data-stu-id="d48a1-143">_sipfederationtls._tcp.</span></span> <span data-ttu-id="d48a1-144">&lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="d48a1-144">&lt;sipdomain&gt;</span></span></p>
<p><span data-ttu-id="d48a1-145">解析為 Access Edge service 的主機 (A 或 AAAA) 記錄</span><span class="sxs-lookup"><span data-stu-id="d48a1-145">Resolves to host (A or AAAA) record for the Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="d48a1-146">若要支援推播通知服務和 Apple Push Notification 服務，您可以為每個具有 Microsoft Lync Mobile 用戶端的 SIP 網域建立一個 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="d48a1-146">To support Push Notification Service and Apple Push Notification service, you create one SRV record for each SIP domain that has Microsoft Lync Mobile clients.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="d48a1-147">這項需求只適用于 Apple 或 Microsoft 移動裝置上的 Microsoft Lync 行動用戶端。</span><span class="sxs-lookup"><span data-stu-id="d48a1-147">This requirement applies only to Microsoft Lync Mobile clients on Apple or Microsoft based mobile devices.</span></span> <span data-ttu-id="d48a1-148">Andriod 和 Nokia Symbian 裝置不使用推播通知。</span><span class="sxs-lookup"><span data-stu-id="d48a1-148">Andriod and Nokia Symbian devices do not use push notification.</span></span>


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="d48a1-149">Lyncdiscover （也稱為自動探索）流量會透過反向 proxy 進行。</span><span class="sxs-lookup"><span data-stu-id="d48a1-149">Lyncdiscover, also known as autodiscover, traffic goes through the reverse proxy.</span></span> <span data-ttu-id="d48a1-150">SRV 記錄指向透過 Access Edge service 解析的記錄。</span><span class="sxs-lookup"><span data-stu-id="d48a1-150">SRV record points to a record that resolves through the Access Edge service.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

