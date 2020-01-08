---
title: Lync Server 2013：行動性的 DNS 需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for mobility
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48185624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fb933e20b8da627ad48a30802ff86c7ed95faff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975885"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a><span data-ttu-id="ecca8-102">使用 Lync Server 2013 行動的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="ecca8-102">DNS requirements for mobility with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ecca8-103">_**主題上次修改日期：** 2012-11-13_</span><span class="sxs-lookup"><span data-stu-id="ecca8-103">_**Topic Last Modified:** 2012-11-13_</span></span>

<span data-ttu-id="ecca8-104">當您部署 Lync Server 2013 行動功能功能時，您可以使用 Microsoft Lync Server 2013 自動探索服務中提供的新 Url，或者您可以使用現有的 Web 服務 Url。</span><span class="sxs-lookup"><span data-stu-id="ecca8-104">When you deploy the Lync Server 2013 mobility feature, you can use the new URLs that are available with the Microsoft Lync Server 2013 Autodiscover Service, or you can use your existing Web Services URLs.</span></span> <span data-ttu-id="ecca8-105">如果您使用現有的 Url，使用者必須在其行動裝置設定中手動輸入 Url。</span><span class="sxs-lookup"><span data-stu-id="ecca8-105">If you use your existing URLs, users need to manually enter the URLs in their mobile device settings.</span></span> <span data-ttu-id="ecca8-106">此選項通常用來進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="ecca8-106">This option is typically used for troubleshooting.</span></span> <span data-ttu-id="ecca8-107">當您使用新的 Url 時，行動用戶端可以自動探索 Lync Server 2013 資源。</span><span class="sxs-lookup"><span data-stu-id="ecca8-107">When you use the new URLs, mobile clients can automatically discover Lync Server 2013 resources.</span></span> <span data-ttu-id="ecca8-108">當您支援自動探索時，您必須新增新的網域名稱系統（DNS）記錄。</span><span class="sxs-lookup"><span data-stu-id="ecca8-108">When you support automatic discovery, you need to add new Domain Name System (DNS) records.</span></span> <span data-ttu-id="ecca8-109">本節說明自動探索所需的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="ecca8-109">This section describes the DNS records that are required for automatic discovery.</span></span>

<span data-ttu-id="ecca8-110">若要支援自動探索，您需要針對每個 SIP 網域建立下列 DNS 記錄：</span><span class="sxs-lookup"><span data-stu-id="ecca8-110">To support automatic discovery, you need to create the following DNS records for each SIP domain:</span></span>

  - <span data-ttu-id="ecca8-111">支援從貴組織的網路中連線之行動使用者的內部 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="ecca8-111">An internal DNS record to support mobile users who connect from within your organization's network</span></span>

  - <span data-ttu-id="ecca8-112">外部或公用的 DNS 記錄，以支援從網際網路連線的行動使用者</span><span class="sxs-lookup"><span data-stu-id="ecca8-112">An external, or public, DNS record to support mobile users who connect from the Internet</span></span>

<span data-ttu-id="ecca8-113">內部自動探索 URL 不應該是從您的網路外部定址的。</span><span class="sxs-lookup"><span data-stu-id="ecca8-113">The internal automatic discovery URL should not be addressable from outside your network.</span></span> <span data-ttu-id="ecca8-114">外部自動探索 URL 不應該是您的網路中的可定址 URL。</span><span class="sxs-lookup"><span data-stu-id="ecca8-114">The external automatic discovery URL should not be addressable from within your network.</span></span> <span data-ttu-id="ecca8-115">不過，如果您無法滿足外部 URL 的這項需求，行動用戶端功能應該不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="ecca8-115">However, if you cannot meet this requirement for the external URL, mobile client functionally should not be affected.</span></span>

<span data-ttu-id="ecca8-116">DNS 記錄可以是 CNAME 記錄或（主機）記錄。</span><span class="sxs-lookup"><span data-stu-id="ecca8-116">The DNS records can be either CNAME records or A (host) records.</span></span>

<span data-ttu-id="ecca8-117">**內部 DNS 記錄**</span><span class="sxs-lookup"><span data-stu-id="ecca8-117">**Internal DNS records**</span></span>

<span data-ttu-id="ecca8-118">您需要建立下列其中一個內部 DNS 記錄：</span><span class="sxs-lookup"><span data-stu-id="ecca8-118">You need to create one of the following internal DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ecca8-119">記錄類型</span><span class="sxs-lookup"><span data-stu-id="ecca8-119">Record type</span></span></th>
<th><span data-ttu-id="ecca8-120">主機名稱或 SRV 定義</span><span class="sxs-lookup"><span data-stu-id="ecca8-120">Host name or SRV definition</span></span></th>
<th><span data-ttu-id="ecca8-121">解析為</span><span class="sxs-lookup"><span data-stu-id="ecca8-121">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ecca8-122">CNAME</span><span class="sxs-lookup"><span data-stu-id="ecca8-122">CNAME</span></span></p></td>
<td><p><span data-ttu-id="ecca8-123">lyncdiscoverinternal.&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="ecca8-123">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="ecca8-124">內部 Web 服務適用于主管池的完整功能變數名稱（FQDN）（如果有的話），如果您沒有控制器，則是適用于您的前端池</span><span class="sxs-lookup"><span data-stu-id="ecca8-124">Internal Web Services fully qualified domain name (FQDN) for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecca8-125">A （主機）</span><span class="sxs-lookup"><span data-stu-id="ecca8-125">A (host)</span></span></p></td>
<td><p><span data-ttu-id="ecca8-126">lyncdiscoverinternal.&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="ecca8-126">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="ecca8-127">如果您沒有控制器，則內部 Web 服務 IP 位址（虛擬 IP （VIP）位址是使用負載平衡器），如果您有一個或多個 [前端] 池</span><span class="sxs-lookup"><span data-stu-id="ecca8-127">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ecca8-128">**外部 DNS 記錄**</span><span class="sxs-lookup"><span data-stu-id="ecca8-128">**External DNS records**</span></span>

<span data-ttu-id="ecca8-129">您需要建立下列其中一個外部 DNS 記錄：</span><span class="sxs-lookup"><span data-stu-id="ecca8-129">You need to create one of the following external DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ecca8-130">記錄類型</span><span class="sxs-lookup"><span data-stu-id="ecca8-130">Record type</span></span></th>
<th><span data-ttu-id="ecca8-131">主機名稱</span><span class="sxs-lookup"><span data-stu-id="ecca8-131">Host name</span></span></th>
<th><span data-ttu-id="ecca8-132">解析為</span><span class="sxs-lookup"><span data-stu-id="ecca8-132">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ecca8-133">CNAME</span><span class="sxs-lookup"><span data-stu-id="ecca8-133">CNAME</span></span></p></td>
<td><p><span data-ttu-id="ecca8-134">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="ecca8-134">lyncdiscover.</span></span> <span data-ttu-id="ecca8-135">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="ecca8-135">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="ecca8-136">您的控制器池的外部 Web 服務 FQDN （如果有的話），如果您沒有控制器，則是適用于您的前端池</span><span class="sxs-lookup"><span data-stu-id="ecca8-136">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecca8-137">A （主機）</span><span class="sxs-lookup"><span data-stu-id="ecca8-137">A (host)</span></span></p></td>
<td><p><span data-ttu-id="ecca8-138">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="ecca8-138">lyncdiscover.</span></span> <span data-ttu-id="ecca8-139">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="ecca8-139">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="ecca8-140">外部或公用 IP 位址（如果您使用的是負載平衡器，則為 [VIP 位址]）</span><span class="sxs-lookup"><span data-stu-id="ecca8-140">External or public IP address (VIP address if you use a load balancer) of the reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecca8-141">DNS-SRV</span><span class="sxs-lookup"><span data-stu-id="ecca8-141">SRV</span></span></p></td>
<td><p><span data-ttu-id="ecca8-142">_sipfederationtls. _tcp。</span><span class="sxs-lookup"><span data-stu-id="ecca8-142">_sipfederationtls._tcp.</span></span> <span data-ttu-id="ecca8-143">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="ecca8-143">&lt;sipdomain&gt;</span></span></p>
<p><span data-ttu-id="ecca8-144">解析為存取邊緣服務的主機（A 或 AAAA）記錄</span><span class="sxs-lookup"><span data-stu-id="ecca8-144">Resolves to host (A or AAAA) record for the Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ecca8-145">若要支援推播通知服務和 Apple 推播通知服務，您可以為擁有 Microsoft Lync 行動用戶端的每個 SIP 網域建立一個 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="ecca8-145">To support Push Notification Service and Apple Push Notification service, you create one SRV record for each SIP domain that has Microsoft Lync Mobile clients.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="ecca8-146">這個需求只適用于 Apple 或 Microsoft 的行動裝置上的 Microsoft Lync Mobile 用戶端。</span><span class="sxs-lookup"><span data-stu-id="ecca8-146">This requirement applies only to Microsoft Lync Mobile clients on Apple or Microsoft based mobile devices.</span></span> <span data-ttu-id="ecca8-147">Andriod 和 Nokia Symbian 裝置不使用推播通知。</span><span class="sxs-lookup"><span data-stu-id="ecca8-147">Andriod and Nokia Symbian devices do not use push notification.</span></span>


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="ecca8-148">Lyncdiscover （也稱為自動探索）會透過反向 proxy 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="ecca8-148">Lyncdiscover, also known as autodiscover, traffic goes through the reverse proxy.</span></span> <span data-ttu-id="ecca8-149">SRV 記錄指向透過存取邊緣服務解析的記錄。</span><span class="sxs-lookup"><span data-stu-id="ecca8-149">SRV record points to a record that resolves through the Access Edge service.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

