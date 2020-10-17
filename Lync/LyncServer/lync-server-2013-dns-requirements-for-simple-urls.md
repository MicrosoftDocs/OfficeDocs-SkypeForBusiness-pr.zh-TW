---
title: Lync Server 2013：簡易 URLs 的 DNS 需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for simple URLs
ms:assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425874(v=OCS.15)
ms:contentKeyID: 48183912
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98db338c48bbb764aefe3d5cab4bcba58b2b23c4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501370"
---
# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="50bab-102">Lync Server 2013 中簡易 URLs 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="50bab-102">DNS requirements for simple URLs in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50bab-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="50bab-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="50bab-104">Lync Server 2013 支援簡單的 URLs，讓使用者加入會議變得更容易，並讓系統管理員更輕鬆取得 Lync Server 系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="50bab-104">Lync Server 2013 supports simple URLs, which make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span> <span data-ttu-id="50bab-105">如需簡單 URLs 的詳細資訊，請參閱 [在 Lync Server 2013 中規劃簡易 URLs](lync-server-2013-planning-for-simple-urls.md)。</span><span class="sxs-lookup"><span data-stu-id="50bab-105">For details about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span></span>

<span data-ttu-id="50bab-106">Lync Server 支援下列三個簡單 URLs：「開會」、「Dial-In」和「系統管理」。您必須設定「符合」和「Dial-In」的簡易 URLs，且 Admin 簡易 URL 是選用的。</span><span class="sxs-lookup"><span data-stu-id="50bab-106">Lync Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="50bab-107">需要用來支援簡單 URL 的網域名稱系統 (DNS) 記錄，視您定義這些簡單 URL 的方式而定，以及是否要支援簡單 URL 的災害復原。</span><span class="sxs-lookup"><span data-stu-id="50bab-107">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span>

<div>

## <a name="simple-url-option-1"></a><span data-ttu-id="50bab-108">簡單 URL 選項 1</span><span class="sxs-lookup"><span data-stu-id="50bab-108">Simple URL Option 1</span></span>

<span data-ttu-id="50bab-109">在選項 1 中，您為每個簡單 URL 各建立一個新的基底 URL。</span><span class="sxs-lookup"><span data-stu-id="50bab-109">In Option 1, you create a new base URL for each simple URL.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="50bab-p103">當使用者按一下簡單 URL 會議連結時，DNS A 記錄解析為的伺服器會判斷要啟動的正確用戶端軟體。用戶端軟體啟動後，便會自動與裝載會議的集區進行通訊。透過這個方式，無論簡單 URL DNS A 記錄是解析為哪個伺服器或集區，都會將使用者導向至包含會議內容的正確伺服器。</span><span class="sxs-lookup"><span data-stu-id="50bab-p103">When a user clicks a simple URL meeting link, the server that the DNS A record resolves to determines the correct client software to start. After the client software is started, it automatically communicates with the pool where the conference is hosted. This way, users are directed to the appropriate server for meeting content no matter which server or pool the simple URL DNS A records resolve to.</span></span>



</div>

### <a name="simple-url-option-1"></a><span data-ttu-id="50bab-113">簡單 URL 選項 1</span><span class="sxs-lookup"><span data-stu-id="50bab-113">Simple URL Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50bab-114"><strong>簡單 URL</strong></span><span class="sxs-lookup"><span data-stu-id="50bab-114"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="50bab-115"><strong>範例</strong></span><span class="sxs-lookup"><span data-stu-id="50bab-115"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50bab-116">滿足</span><span class="sxs-lookup"><span data-stu-id="50bab-116">Meet</span></span></p></td>
<td><p><span data-ttu-id="50bab-117">https://meet.contoso.com、等等 https://meet.fabrikam.com 等等 (組織中的每個 SIP 網域) </span><span class="sxs-lookup"><span data-stu-id="50bab-117">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50bab-118">撥入</span><span class="sxs-lookup"><span data-stu-id="50bab-118">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50bab-119">系統管理員</span><span class="sxs-lookup"><span data-stu-id="50bab-119">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="50bab-120">如果使用選項 1，您必須定義下列項目：</span><span class="sxs-lookup"><span data-stu-id="50bab-120">If you use Option 1, you must define the following:</span></span>

  - <span data-ttu-id="50bab-p104">對於每個 Meet 簡單 URL，如果您已部署 Director，則需要有一筆 DNS A 記錄，並讓其將 URL 解析為 Director 的 IP 位址。否則，即應解析為前端集區的負載平衡器的 IP 位址。如果您未部署集區，且使用 Standard Edition Server 部署，則 DNS A 記錄必須解析為組織中某部 Standard Edition Server 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="50bab-p104">For each Meet simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>
    
    <span data-ttu-id="50bab-124">如果組織中有多個 SIP 網域而您使用此選項，您必須為每個 SIP 網域建立 Meet 簡單 URL，且每個 Meet 簡單 URL 各需有一筆 DNS A 記錄。</span><span class="sxs-lookup"><span data-stu-id="50bab-124">If you have more than one SIP domain in your organization and you use this option, you must create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="50bab-125">例如，如果您同時有 contoso.com 和 fabrikam.com，您會同時為和建立 DNS A 記錄 https://meet.contoso.com https://meet.fabrikam.com 。</span><span class="sxs-lookup"><span data-stu-id="50bab-125">For example, if you have both contoso.com and fabrikam.com, you will create DNS A records for both https://meet.contoso.com and https://meet.fabrikam.com.</span></span>
    
    <span data-ttu-id="50bab-126">或者，如果您有多個 SIP 網域且想減少這些簡單 URL 的 DNS 記錄和憑證需求，請使用本主題稍後所述的選項 3。</span><span class="sxs-lookup"><span data-stu-id="50bab-126">Alternatively, if you have multiple SIP domains and you want to minimize the DNS record and certificate requirements for these simple URLs, use Option 3 as described later in this topic.</span></span>

  - <span data-ttu-id="50bab-p106">對於 Dial-in 簡單 URL，如果您已部署 Director，則需要有一筆 DNS A 記錄，並讓其將 URL 解析為 Director 的 IP 位址。否則，即應解析為前端集區的負載平衡器的 IP 位址。如果您未部署集區，且使用 Standard Edition Server 部署，則 DNS A 記錄必須解析為組織中某部 Standard Edition Server 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="50bab-p106">For the Dial-in simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

  - <span data-ttu-id="50bab-p107">Admin 簡單 URL 僅限內部使用。如果您已部署 Director，則需要有一筆 DNS A 記錄，並讓其將 URL 解析為 Director 的 IP 位址。否則，即應解析為前端集區的負載平衡器的 IP 位址。如果您未部署集區，且使用 Standard Edition Server 部署，則 DNS A 記錄必須解析為組織中某部 Standard Edition Server 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="50bab-p107">The Admin simple URL is internal only. It requires a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

</div>

<div>

## <a name="simple-url-option-2"></a><span data-ttu-id="50bab-134">簡單 URL 選項 2</span><span class="sxs-lookup"><span data-stu-id="50bab-134">Simple URL Option 2</span></span>

<span data-ttu-id="50bab-p108">在選項 2 中，Meet、Dial-in 和 Admin 簡單 URL 全都使用同一個基底 URL，例如 lync.contoso.com。因此，這些簡單 URL 只需要有一筆 DNS A 記錄，並讓其將 lync.contoso.com 解析為 Director 集區或前端集區的 IP 位址即可。如果您未部署集區，且使用 Standard Edition Server 部署，則 DNS A 記錄必須解析為組織中某部 Standard Edition Server 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="50bab-p108">With Option 2, the Meet, Dial-in, and Admin simple URLs all have a common base URL, such as lync.contoso.com. Therefore, you need only one DNS A record for these simple URLs, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

<span data-ttu-id="50bab-138">請注意，如果組織中有多個 SIP 網域，您仍必須為每個 SIP 網域建立 Meet 簡單 URL，且每個 Meet 簡單 URL 各需有一筆 DNS A 記錄。</span><span class="sxs-lookup"><span data-stu-id="50bab-138">Note that if you have more than one SIP domain in your organization, you must still create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="50bab-139">在此範例中，除了有三個全都以 lync.contoso.com 為基礎的簡單 URL 外，還有一個針對 fabrikam.com 所設定，使用不同基底 URL 的 Meet 簡單 URL。</span><span class="sxs-lookup"><span data-stu-id="50bab-139">In this example, while three simple URLs are all based on lync.contoso.com, an additional Meet simple URL for fabrikam.com is set up with a different base URL.</span></span> <span data-ttu-id="50bab-140">在此範例中，您必須建立和的 DNS A https://lync.contoso.com 記錄 https://lync.fabrikam.com 。</span><span class="sxs-lookup"><span data-stu-id="50bab-140">In this example, you must create DNS A records for both https://lync.contoso.com and https://lync.fabrikam.com.</span></span> <span data-ttu-id="50bab-141">簡單 URL 選項 3 顯示當有多個 SIP 網域時，另一個處理命名和 DNS A 記錄的方式。</span><span class="sxs-lookup"><span data-stu-id="50bab-141">Simple URL Option 3 shows another way to handle naming and DNS A records if you have multiple SIP domains.</span></span>

### <a name="simple-url-option-2"></a><span data-ttu-id="50bab-142">簡單 URL 選項 2</span><span class="sxs-lookup"><span data-stu-id="50bab-142">Simple URL Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50bab-143"><strong>簡單 URL</strong></span><span class="sxs-lookup"><span data-stu-id="50bab-143"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="50bab-144"><strong>範例</strong></span><span class="sxs-lookup"><span data-stu-id="50bab-144"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50bab-145">滿足</span><span class="sxs-lookup"><span data-stu-id="50bab-145">Meet</span></span></p></td>
<td><p><span data-ttu-id="50bab-146">https://lync.contoso.com/Meet、等等 https://lync.fabrikam.com/Meet 等等 (組織中的每個 SIP 網域) </span><span class="sxs-lookup"><span data-stu-id="50bab-146">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50bab-147">撥入</span><span class="sxs-lookup"><span data-stu-id="50bab-147">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50bab-148">系統管理員</span><span class="sxs-lookup"><span data-stu-id="50bab-148">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a><span data-ttu-id="50bab-149">簡單 URL 選項 3</span><span class="sxs-lookup"><span data-stu-id="50bab-149">Simple URL Option 3</span></span>

<span data-ttu-id="50bab-p110">如果您有許多 SIP 網域，且想要每個網域各有不同的簡單 URL，但想要減少這些簡單 URL 的 DNS 記錄和憑證需求，則採用選項 3 最適合。在此範例中，您僅需要有一筆 DNS A 記錄，並讓其將 lync.contoso.com 解析為 Director 集區或前端集區的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="50bab-p110">Option 3 is most useful if you have many SIP domains, and you want them to have separate simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs. In this example, you need only one DNS A record, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool.</span></span>

### <a name="simple-url-option-3"></a><span data-ttu-id="50bab-152">簡單 URL 選項 3</span><span class="sxs-lookup"><span data-stu-id="50bab-152">Simple URL Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50bab-153"><strong>簡單 URL</strong></span><span class="sxs-lookup"><span data-stu-id="50bab-153"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="50bab-154"><strong>範例</strong></span><span class="sxs-lookup"><span data-stu-id="50bab-154"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50bab-155">滿足</span><span class="sxs-lookup"><span data-stu-id="50bab-155">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50bab-156">撥入</span><span class="sxs-lookup"><span data-stu-id="50bab-156">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50bab-157">系統管理員</span><span class="sxs-lookup"><span data-stu-id="50bab-157">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="50bab-158">簡單 URL 的災害復原選項</span><span class="sxs-lookup"><span data-stu-id="50bab-158">Disaster Recovery Option for Simple URLs</span></span>

<span data-ttu-id="50bab-159">如果您有多個網站包含前端集區，而您的 DNS 提供者支援 GeoDNS，您可以設定您的 DNS 記錄以進行簡單的 URLs 以支援嚴重損壞修復，這樣一來，即使一部整個前端集區已停機，也能繼續簡易 URL 功能。</span><span class="sxs-lookup"><span data-stu-id="50bab-159">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="50bab-160">此災害復原功能支援 Meet 及 Dial-In 簡單 URL。</span><span class="sxs-lookup"><span data-stu-id="50bab-160">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="50bab-p112">如要如此設定，請建立兩個 GeoDNS 位址。每個位址都包含兩個 DNS A 或 CNAME 記錄，這兩個記錄會解析為針對災害復原目的而配對的兩個集區。一個 GeoDNS 位址用於內部存取，並解析為該兩個集區的內部 Web FQDN 或負載平衡器 IP 位址。另一個 GeoDNS 位址用於外部存取，並解析為該兩個集區的外部 Web FQDN 或負載平衡器 IP 位址。下列範例針對 Meet 簡單 URL，並使用集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="50bab-p112">To configure this, create two GeoDNS addresses. Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes. One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools. The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools. The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span>

   ```console
    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com
   ```

   ```console
   Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com
   ``` 

<span data-ttu-id="50bab-166">然後建立 CNAME 記錄，其中會將 Meet 簡單 URL (例如 meet.contoso.com) 解析為兩個 GeoDNS 位址。</span><span class="sxs-lookup"><span data-stu-id="50bab-166">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="50bab-167">如果網路使用<EM>「髮夾」</EM> (將所有簡單 URL 流量透過外部連結路由，包括來自組織內的流量)，則可僅設定外部 GeoDNS 位址，並將 Meet 簡單 URL 僅解析為該外部位址。</span><span class="sxs-lookup"><span data-stu-id="50bab-167">If your network uses <EM>hairpinning</EM> (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>



</div>

<span data-ttu-id="50bab-168">使用此方法時，可設定每個 GeoDNS 位址使用循環配置資源方法來散發要求至兩個集區，或者主要連線至一個集區 (例如地理位置上較近的集區)，然後僅在連線失敗時才使用另一個集區。</span><span class="sxs-lookup"><span data-stu-id="50bab-168">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span>

<span data-ttu-id="50bab-169">針對 Dial-In 簡單 URL 也可以設定相同的組態。</span><span class="sxs-lookup"><span data-stu-id="50bab-169">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="50bab-170">若要這麼做，請建立如先前範例中的其他記錄，並以 `dialin` `meet` DNS 記錄取代。</span><span class="sxs-lookup"><span data-stu-id="50bab-170">To do so, create additional records like those in the previous example, substituting `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="50bab-171">針對 Admin 簡單 URL，請使用本節中先前列出的三個選項。</span><span class="sxs-lookup"><span data-stu-id="50bab-171">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>

<span data-ttu-id="50bab-172">此組態一旦設定，就必須使用監控應用程式，設定 HTTP 監控以監看失敗。</span><span class="sxs-lookup"><span data-stu-id="50bab-172">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="50bab-173">若要進行外部存取，請確定 HTTPS 對兩個集區的外部 web FQDN 或負載平衡器 IP 位址的 HTTPS GET 自動探索要求成功。</span><span class="sxs-lookup"><span data-stu-id="50bab-173">For external access, monitor to make sure that HTTPS GET autodiscovery requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="50bab-174">例如，下列要求不得包含任何 **ACCEPT** 標頭且必須傳回 **200 OK**。</span><span class="sxs-lookup"><span data-stu-id="50bab-174">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>

```console
    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

<span data-ttu-id="50bab-p115">針對內部存取，則必須監控該兩個集區之內部 Web FQDN 或負載平衡器 IP 位址的連接埠 5061。如果偵測到任何連線失敗，這些集區的 VIP 必須關閉連接埠 80、443 及 444。</span><span class="sxs-lookup"><span data-stu-id="50bab-p115">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools. If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 444.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

