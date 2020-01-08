---
title: Lync Server 2013：簡單 URL 的 DNS 需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for simple URLs
ms:assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425874(v=OCS.15)
ms:contentKeyID: 48183912
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adcf537db908fcc0b69e95bec99b73a0e57e9ab4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="7368a-102">Lync Server 2013 中簡單 URL 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="7368a-102">DNS requirements for simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7368a-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="7368a-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="7368a-104">Lync Server 2013 支援簡單的 Url，讓您的使用者更容易加入會議，並讓您能更輕鬆地進入 Lync Server 管理工具給您的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="7368a-104">Lync Server 2013 supports simple URLs, which make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span> <span data-ttu-id="7368a-105">如需簡單 Url 的詳細資料，請參閱[規劃 Lync Server 2013 中的簡單 url](lync-server-2013-planning-for-simple-urls.md)。</span><span class="sxs-lookup"><span data-stu-id="7368a-105">For details about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span></span>

<span data-ttu-id="7368a-106">Lync Server 支援下列三個簡單的 Url： [開會]、[撥入] 和 [管理員]。您必須設定適用于 [開會及撥入] 的簡單 Url，且 [管理員簡易 URL] 是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="7368a-106">Lync Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="7368a-107">您需要支援簡單 Url 的網域名稱系統（DNS）記錄，取決於您如何定義這些簡單的 Url，以及是否要支援簡單 Url 的災害復原。</span><span class="sxs-lookup"><span data-stu-id="7368a-107">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span>

<div>

## <a name="simple-url-option-1"></a><span data-ttu-id="7368a-108">簡單的 URL 選項1</span><span class="sxs-lookup"><span data-stu-id="7368a-108">Simple URL Option 1</span></span>

<span data-ttu-id="7368a-109">在選項1中，您為每個簡單的 URL 建立新的基 URL。</span><span class="sxs-lookup"><span data-stu-id="7368a-109">In Option 1, you create a new base URL for each simple URL.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="7368a-110">當使用者按一下簡單的 URL 會議連結時，DNS A 記錄所解析的伺服器會決定要啟動的正確用戶端軟體。</span><span class="sxs-lookup"><span data-stu-id="7368a-110">When a user clicks a simple URL meeting link, the server that the DNS A record resolves to determines the correct client software to start.</span></span> <span data-ttu-id="7368a-111">用戶端軟體啟動之後，就會自動與該會議的主機池進行通訊。</span><span class="sxs-lookup"><span data-stu-id="7368a-111">After the client software is started, it automatically communicates with the pool where the conference is hosted.</span></span> <span data-ttu-id="7368a-112">如此一來，無論簡單的 URL DNS A 記錄解析到哪個伺服器或池中，使用者都會被導向會議內容的適當伺服器。</span><span class="sxs-lookup"><span data-stu-id="7368a-112">This way, users are directed to the appropriate server for meeting content no matter which server or pool the simple URL DNS A records resolve to.</span></span>



</div>

### <a name="simple-url-option-1"></a><span data-ttu-id="7368a-113">簡單的 URL 選項1</span><span class="sxs-lookup"><span data-stu-id="7368a-113">Simple URL Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7368a-114"><strong>簡單的 URL</strong></span><span class="sxs-lookup"><span data-stu-id="7368a-114"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="7368a-115"><strong>範例</strong></span><span class="sxs-lookup"><span data-stu-id="7368a-115"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7368a-116">符合</span><span class="sxs-lookup"><span data-stu-id="7368a-116">Meet</span></span></p></td>
<td><p><span data-ttu-id="7368a-117">https://meet.contoso.comhttps://meet.fabrikam.com等等（針對貴組織中的每個 SIP 網域一個）</span><span class="sxs-lookup"><span data-stu-id="7368a-117">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7368a-118">撥入</span><span class="sxs-lookup"><span data-stu-id="7368a-118">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7368a-119">管理員</span><span class="sxs-lookup"><span data-stu-id="7368a-119">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7368a-120">如果您使用選項1，您必須定義下列各項：</span><span class="sxs-lookup"><span data-stu-id="7368a-120">If you use Option 1, you must define the following:</span></span>

  - <span data-ttu-id="7368a-121">針對每個符合簡單的 URL，您需要一個 DNS A 記錄，將 URL 解析為主管的 IP 位址（如果您已部署）。</span><span class="sxs-lookup"><span data-stu-id="7368a-121">For each Meet simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed.</span></span> <span data-ttu-id="7368a-122">否則，它應該解析為前端池負載平衡器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7368a-122">Otherwise, it should resolve to the IP address of the load balancer of a Front End pool.</span></span> <span data-ttu-id="7368a-123">如果您沒有部署某個池，且使用的是標準版 server 部署，則 DNS A 記錄必須解析為貴組織中某個標準版伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7368a-123">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>
    
    <span data-ttu-id="7368a-124">如果您的組織中有多個 SIP 網域，且您使用這個選項，您必須為每個 SIP 網域建立符合簡單的 Url，且您需要每個符合簡單 URL 的 DNS A 記錄。</span><span class="sxs-lookup"><span data-stu-id="7368a-124">If you have more than one SIP domain in your organization and you use this option, you must create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="7368a-125">例如，如果您同時擁有 contoso.com 和 fabrikam.com，您將會建立https://meet.contoso.com與https://meet.fabrikam.com的 DNS A 記錄。</span><span class="sxs-lookup"><span data-stu-id="7368a-125">For example, if you have both contoso.com and fabrikam.com, you will create DNS A records for both https://meet.contoso.com and https://meet.fabrikam.com.</span></span>
    
    <span data-ttu-id="7368a-126">或者，如果您有多個 SIP 網域，而且想要將這些簡單 Url 的 DNS 記錄與證書需求減到最小，請使用 Option 3，如本主題稍後所述。</span><span class="sxs-lookup"><span data-stu-id="7368a-126">Alternatively, if you have multiple SIP domains and you want to minimize the DNS record and certificate requirements for these simple URLs, use Option 3 as described later in this topic.</span></span>

  - <span data-ttu-id="7368a-127">若是撥入式簡易 URL，您需要 DNS A 記錄，將 URL 解析為主管的 IP 位址（如果您已部署的話）。</span><span class="sxs-lookup"><span data-stu-id="7368a-127">For the Dial-in simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed.</span></span> <span data-ttu-id="7368a-128">否則，它應該解析為前端池負載平衡器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7368a-128">Otherwise, it should resolve to the IP address of the load balancer of a Front End pool.</span></span> <span data-ttu-id="7368a-129">如果您沒有部署某個池，且使用的是標準版 server 部署，則 DNS A 記錄必須解析為貴組織中某個標準版伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7368a-129">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

  - <span data-ttu-id="7368a-130">[管理員] 簡單 URL 僅限內部版本。</span><span class="sxs-lookup"><span data-stu-id="7368a-130">The Admin simple URL is internal only.</span></span> <span data-ttu-id="7368a-131">它需要一個 DNS A 記錄，將 URL 解析為主管的 IP 位址（如果您已部署）。</span><span class="sxs-lookup"><span data-stu-id="7368a-131">It requires a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed.</span></span> <span data-ttu-id="7368a-132">否則，它應該解析為前端池負載平衡器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7368a-132">Otherwise, it should resolve to the IP address of the load balancer of a Front End pool.</span></span> <span data-ttu-id="7368a-133">如果您沒有部署某個池，且使用的是標準版 server 部署，則 DNS A 記錄必須解析為貴組織中某個標準版伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7368a-133">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

</div>

<div>

## <a name="simple-url-option-2"></a><span data-ttu-id="7368a-134">簡單的 URL 選項2</span><span class="sxs-lookup"><span data-stu-id="7368a-134">Simple URL Option 2</span></span>

<span data-ttu-id="7368a-135">有了選項2、[開會]、[撥入] 和 [系統管理] 的簡單 Url，都有共同的基底 URL，例如 lync.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="7368a-135">With Option 2, the Meet, Dial-in, and Admin simple URLs all have a common base URL, such as lync.contoso.com.</span></span> <span data-ttu-id="7368a-136">因此，對於這些簡單的 Url，只需要一個 DNS A 記錄，即可將 lync.contoso.com 解析為主管池或頂層端池的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7368a-136">Therefore, you need only one DNS A record for these simple URLs, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool.</span></span> <span data-ttu-id="7368a-137">如果您沒有部署某個池，且使用的是標準版 server 部署，則 DNS A 記錄必須解析為貴組織中某個標準版伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7368a-137">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

<span data-ttu-id="7368a-138">請注意，如果您的組織中有多個 SIP 網域，您仍然必須建立符合每個 SIP 網域的簡單 Url，而且您需要每個符合簡單 URL 的 DNS A 記錄。</span><span class="sxs-lookup"><span data-stu-id="7368a-138">Note that if you have more than one SIP domain in your organization, you must still create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="7368a-139">在這個範例中，雖然三個簡單的 Url 都是以 lync.contoso.com 為基礎，但 fabrikam.com 的另一個基本 url 是以不同的基 URL 來設定。</span><span class="sxs-lookup"><span data-stu-id="7368a-139">In this example, while three simple URLs are all based on lync.contoso.com, an additional Meet simple URL for fabrikam.com is set up with a different base URL.</span></span> <span data-ttu-id="7368a-140">在這個範例中，您必須同時為兩個和https://lync.contoso.com https://lync.fabrikam.com兩個都建立 DNS A 記錄。</span><span class="sxs-lookup"><span data-stu-id="7368a-140">In this example, you must create DNS A records for both https://lync.contoso.com and https://lync.fabrikam.com.</span></span> <span data-ttu-id="7368a-141">如果您有多個 SIP 網域，則簡單的 URL 選項3會顯示另一個處理命名和 DNS A 記錄的方式。</span><span class="sxs-lookup"><span data-stu-id="7368a-141">Simple URL Option 3 shows another way to handle naming and DNS A records if you have multiple SIP domains.</span></span>

### <a name="simple-url-option-2"></a><span data-ttu-id="7368a-142">簡單的 URL 選項2</span><span class="sxs-lookup"><span data-stu-id="7368a-142">Simple URL Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7368a-143"><strong>簡單的 URL</strong></span><span class="sxs-lookup"><span data-stu-id="7368a-143"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="7368a-144"><strong>範例</strong></span><span class="sxs-lookup"><span data-stu-id="7368a-144"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7368a-145">符合</span><span class="sxs-lookup"><span data-stu-id="7368a-145">Meet</span></span></p></td>
<td><p><span data-ttu-id="7368a-146">https://lync.contoso.com/Meethttps://lync.fabrikam.com/Meet等等（針對貴組織中的每個 SIP 網域一個）</span><span class="sxs-lookup"><span data-stu-id="7368a-146">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7368a-147">撥入</span><span class="sxs-lookup"><span data-stu-id="7368a-147">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7368a-148">管理員</span><span class="sxs-lookup"><span data-stu-id="7368a-148">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a><span data-ttu-id="7368a-149">簡單的 URL 選項3</span><span class="sxs-lookup"><span data-stu-id="7368a-149">Simple URL Option 3</span></span>

<span data-ttu-id="7368a-150">如果您有許多 SIP 網域，而您想要讓它們擁有不同的簡單 Url，但想要將這些簡單 Url 的 DNS 記錄與證書需求減至最少，選項3就是最實用的方法。</span><span class="sxs-lookup"><span data-stu-id="7368a-150">Option 3 is most useful if you have many SIP domains, and you want them to have separate simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span> <span data-ttu-id="7368a-151">在這個範例中，您只需要一個 DNS A 記錄，該記錄會將 lync.contoso.com 解析為主管池或頂層端池的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7368a-151">In this example, you need only one DNS A record, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool.</span></span>

### <a name="simple-url-option-3"></a><span data-ttu-id="7368a-152">簡單的 URL 選項3</span><span class="sxs-lookup"><span data-stu-id="7368a-152">Simple URL Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7368a-153"><strong>簡單的 URL</strong></span><span class="sxs-lookup"><span data-stu-id="7368a-153"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="7368a-154"><strong>範例</strong></span><span class="sxs-lookup"><span data-stu-id="7368a-154"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7368a-155">符合</span><span class="sxs-lookup"><span data-stu-id="7368a-155">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7368a-156">撥入</span><span class="sxs-lookup"><span data-stu-id="7368a-156">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7368a-157">管理員</span><span class="sxs-lookup"><span data-stu-id="7368a-157">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="7368a-158">簡單 Url 的災害復原選項</span><span class="sxs-lookup"><span data-stu-id="7368a-158">Disaster Recovery Option for Simple URLs</span></span>

<span data-ttu-id="7368a-159">如果您有多個包含前端池的網站，而且您的 DNS 提供者支援 GeoDNS，您可以針對簡單的 Url 設定您的 DNS 記錄，以支援災害復原，因此即使一個完整的前端池已停止，簡單的 URL 功能仍會繼續。</span><span class="sxs-lookup"><span data-stu-id="7368a-159">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="7368a-160">這個災害復原功能支援 [開會] 和 [撥入] 簡單的 Url。</span><span class="sxs-lookup"><span data-stu-id="7368a-160">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="7368a-161">若要設定這一點，請建立兩個 GeoDNS 位址。</span><span class="sxs-lookup"><span data-stu-id="7368a-161">To configure this, create two GeoDNS addresses.</span></span> <span data-ttu-id="7368a-162">每個位址都有兩個 DNS A 或 CNAME 記錄，可解析成成對組成的兩個池以進行災害復原。</span><span class="sxs-lookup"><span data-stu-id="7368a-162">Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes.</span></span> <span data-ttu-id="7368a-163">一個 GeoDNS 位址用於內部存取，並解析為兩個池的內部網路 FQDN 或負載平衡器 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7368a-163">One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="7368a-164">其他 GeoDNS 位址是用於外部存取，並解析為兩個池的外部 web FQDN 或負載平衡器 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7368a-164">The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="7368a-165">下列是使用池之 Fqdn 的 [符合簡單 URL] 的範例。</span><span class="sxs-lookup"><span data-stu-id="7368a-165">The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span>

   ```
    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com
   ```

   ```
   Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com
   ``` 

<span data-ttu-id="7368a-166">然後建立可將您的符合簡單 URL （例如 meet.contoso.com）解析成兩個 GeoDNS 位址的 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="7368a-166">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="7368a-167">如果您的網路使用的是<EM>hairpinning</EM> （透過外部連結路由所有簡單的 URL 流量，包括來自貴組織內部的流量），則您可以只設定外部 GeoDNS 位址，並將您的 [符合簡單 url] 解析為僅限外部地址。</span><span class="sxs-lookup"><span data-stu-id="7368a-167">If your network uses <EM>hairpinning</EM> (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>



</div>

<span data-ttu-id="7368a-168">當您使用此方法時，您可以設定每個 GeoDNS 位址，以使用迴圈複用方法將要求發佈到兩個池，或主要連線到一個池（例如位於地理位置較近的池中），並使用其他池（例如連接失敗。</span><span class="sxs-lookup"><span data-stu-id="7368a-168">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span>

<span data-ttu-id="7368a-169">您可以針對撥入簡易 URL 設定相同的配置。</span><span class="sxs-lookup"><span data-stu-id="7368a-169">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="7368a-170">若要這樣做，請建立如先前範例中的其他記錄， `dialin`並`meet`在 DNS 記錄中取代。</span><span class="sxs-lookup"><span data-stu-id="7368a-170">To do so, create additional records like those in the previous example, substituting `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="7368a-171">針對系統管理員簡易 URL，請使用本節前面所列的三個選項之一。</span><span class="sxs-lookup"><span data-stu-id="7368a-171">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>

<span data-ttu-id="7368a-172">設定此設定之後，您必須使用監視應用程式來設定 HTTP 監視來監視失敗。</span><span class="sxs-lookup"><span data-stu-id="7368a-172">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="7368a-173">針對外部存取，請務必確認 HTTPS 取得對外部網路 FQDN 的自動探索要求，或兩個池的負載平衡器 IP 位址成功。</span><span class="sxs-lookup"><span data-stu-id="7368a-173">For external access, monitor to make sure that HTTPS GET autodiscovery requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="7368a-174">例如，下列要求不能包含任何**ACCEPT**標頭，而且必須傳回**200 OK**。</span><span class="sxs-lookup"><span data-stu-id="7368a-174">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>

    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root

<span data-ttu-id="7368a-175">針對內部存取，您必須在兩個池的內部網路 FQDN 或負載平衡器 IP 位址上，監視埠5061。</span><span class="sxs-lookup"><span data-stu-id="7368a-175">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="7368a-176">如果偵測到任何連線失敗，這些池的 VIP 必須關閉埠80、443和444。</span><span class="sxs-lookup"><span data-stu-id="7368a-176">If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 444.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

