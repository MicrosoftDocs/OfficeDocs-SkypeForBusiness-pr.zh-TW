---
title: Lync Server 2013：判斷 DNS 需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine DNS requirements
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398758(v=OCS.15)
ms:contentKeyID: 48184839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3f1bc8cd839b986a4830ad32f797835c56e9ebd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198126"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="determine-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="8b3b2-102">決定 Lync Server 2013 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="8b3b2-102">Determine DNS requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b3b2-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="8b3b2-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="8b3b2-104">使用下列流程圖判斷網域名稱系統 (DNS) 需求。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-104">Use the following flow chart to determine Domain Name System (DNS) requirements.</span></span> <span data-ttu-id="8b3b2-105">Lync Server 2013： 2 2013 月的累計更新的變更會在其適用的地方注明。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-105">Changes for the Cumulative Updates for Lync Server 2013: February 2013 are noted where they apply.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8b3b2-106">Microsoft Lync Server 2013 支援使用 IPv6 定址。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-106">Microsoft Lync Server 2013 supports the use of IPv6 addressing.</span></span> <span data-ttu-id="8b3b2-107">若要使用 IPv6 位址，還必須針對 IPv6 DNS 提供支援，並設定 DNS 主機 AAAA (稱為「四 A」 ) 記錄。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-107">To use IPv6 addresses, you must also provide support for IPv6 DNS and configure DNS host AAAA (known as “quad-A”) records.</span></span> <span data-ttu-id="8b3b2-108">在使用 IPv4 和 IPv6 的部署中，最好是設定及維護主機 A 記錄，以供 IPv6 的 IPv4 和主機 AAAA。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-108">In deployments where both IPv4 and IPv6 are being used, it is best to configure and maintain both host A records for IPv4 and host AAAA for IPv6.</span></span> <span data-ttu-id="8b3b2-109">即使您的部署已完全轉換為 IPv6，當外部使用者仍在使用 IPv4 時，可能仍然需要 IPv4 DNS 主機記錄。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-109">Even if your deployment has transitioned fully to IPv6, IPv4 DNS host records may still be required when external users are still using IPv4.</span></span>



</div>

<span data-ttu-id="8b3b2-110">**決定 DNS 需求流程圖表**</span><span class="sxs-lookup"><span data-stu-id="8b3b2-110">**Determining DNS Requirements Flow Chart**</span></span>

<span data-ttu-id="8b3b2-111">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span><span class="sxs-lookup"><span data-stu-id="8b3b2-111">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8b3b2-112">依預設，未加入網域之電腦的電腦名稱稱為主機名稱，而不是完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-112">By default the computer name of a computer that is not joined to a domain is a host name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="8b3b2-113">拓撲產生器使用 Fqdn，而非主機名稱。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-113">Topology Builder uses FQDNs, not host names.</span></span> <span data-ttu-id="8b3b2-114">因此，在未加入網域但要部署為 Edge Server 電腦的電腦名稱中，您必須設定 DNS 尾碼。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-114">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="8b3b2-115">當您為 Lync Server、Edge Server 以及集區指派 FQDN 時，只能使用標準字元<STRONG></STRONG> (包括 A–Z、a–z、0–9 與連字號)。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-115"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="8b3b2-116">請勿使用 Unicode 字元或底線。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-116">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="8b3b2-117">也就是當 FQDN 必須指派給憑證的 SN 時，外部 DNS 與公用 CA 通常不支援在 FQDN 中使用非標準字元。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-117">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="8b3b2-118">如需其他詳細資料，請參閱<A href="lync-server-2013-configure-dns-host-records.md">設定 Lync Server 2013 的 DNS 主機記錄</A></span><span class="sxs-lookup"><span data-stu-id="8b3b2-118">For additional details, see <A href="lync-server-2013-configure-dns-host-records.md">Configure DNS Host records for Lync Server 2013</A></span></span>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a><span data-ttu-id="8b3b2-119">Lync 用戶端如何尋找服務</span><span class="sxs-lookup"><span data-stu-id="8b3b2-119">How Lync Clients Locate Services</span></span>

<span data-ttu-id="8b3b2-120">Microsoft Lync 2010、Lync 2013 和 Lync Mobile 類似于用戶端在 Lync Server 2013 中尋找和存取服務的方式。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-120">Microsoft Lync 2010, Lync 2013, and Lync Mobile are similar in how the client finds and accesses services in Lync Server 2013.</span></span> <span data-ttu-id="8b3b2-121">值得注意的例外狀況是 Lync Windows Store 應用程式使用不同的服務位置處理常式。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-121">The notable exception is the Lync Windows Store app that uses a different service location process.</span></span> <span data-ttu-id="8b3b2-122">本節詳細說明用戶端如何尋找服務的兩種情形，先使用一系列 SRV 和主機記錄的傳統方法，第二個是使用自動探索服務記錄。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-122">This section details two scenarios of how the clients locate services, first the traditional method using a series of SRV and A host records, second using only the Autodiscover service records.</span></span> <span data-ttu-id="8b3b2-123">對桌面用戶端的累計更新會變更所有用戶端之 Lync Server 2010 的 DNS 位置進程; DNS 查詢程式會繼續，直到傳回成功的查詢或可能的 DNS 記錄清單已耗盡，最後的錯誤會傳回給用戶端。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-123">Cumulative updates to the desktop clients change the DNS location process from Lync Server 2010 For all clients, the DNS query process continues until a successful query is returned, or the list of possible DNS records is exhausted, and the final error is returned to the client.</span></span>

<span data-ttu-id="8b3b2-124">針對所有用戶端（DNS 查閱期間的 Lync Windows Store 應用程式**除外**），會依下列順序查詢和傳回用戶端的 SRV 記錄：</span><span class="sxs-lookup"><span data-stu-id="8b3b2-124">For all clients **except** for the Lync Windows Store app During DNS lookup, SRV records are queried and returned to the client in the following order:</span></span>

1.  <span data-ttu-id="8b3b2-125">lyncdiscoverinternal。 \<網域 \> A 為內部 Web 服務上的自動探索服務 (主機) 記錄</span><span class="sxs-lookup"><span data-stu-id="8b3b2-125">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="8b3b2-126">lyncdiscover。 \<網域 \> A (主 Web 服務上自動探索服務的主機) 記錄</span><span class="sxs-lookup"><span data-stu-id="8b3b2-126">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

3.  <span data-ttu-id="8b3b2-127">\_sipinternaltls。 \_tcp。 \<\>內部 TLS 連線的網域 SRV (服務定位器) 記錄</span><span class="sxs-lookup"><span data-stu-id="8b3b2-127">\_sipinternaltls.\_tcp.\<domain\>   SRV (service locator) record for internal TLS connections</span></span>

4.  <span data-ttu-id="8b3b2-128">\_sipinternal。 \_tcp。 \<\>只有在允許 TCP 時，才會 (執行內部 tcp 連線的網域 SRV (服務定位器) 記錄) </span><span class="sxs-lookup"><span data-stu-id="8b3b2-128">\_sipinternal.\_tcp.\<domain\>   SRV (service locator) record for internal TCP connections (performed only if TCP is allowed)</span></span>

5.  <span data-ttu-id="8b3b2-129">\_sip。 \_tls。 \<\>外部 TLS 連線的網域 SRV (服務定位器) 記錄</span><span class="sxs-lookup"><span data-stu-id="8b3b2-129">\_sip.\_tls.\<domain\>   SRV (service locator) record for external TLS connections</span></span>

6.  <span data-ttu-id="8b3b2-130">sipinternal。 \<網域 \> A (主機) 記錄的前端集區或 Director，只可在內部網路上加以解析</span><span class="sxs-lookup"><span data-stu-id="8b3b2-130">sipinternal.\<domain\>   A (host) record for the Front End pool or Director, resolvable only on the internal network</span></span>

7.  <span data-ttu-id="8b3b2-131">sip。 \<網域 \> A (主機在內部網路上的前端集區或 Director) 記錄，或用戶端為外部用戶端時的 Access Edge service。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-131">sip.\<domain\>   A (host) record for the Front End pool or Director on the internal network, or the Access Edge service when the client is external</span></span>

8.  <span data-ttu-id="8b3b2-132">sipexternal。 \<網域 \> A 當用戶端為外部用戶端時，存取 Edge service 的 (主機) 記錄</span><span class="sxs-lookup"><span data-stu-id="8b3b2-132">sipexternal.\<domain\>   A (host) record for the Access Edge service when the client is external</span></span>

<span data-ttu-id="8b3b2-133">「Lync Windows Store」應用程式會完全變更該處理常式，因為它使用兩筆記錄：</span><span class="sxs-lookup"><span data-stu-id="8b3b2-133">The Lync Windows Store app changes the process completely because it uses two records:</span></span>

1.  <span data-ttu-id="8b3b2-134">lyncdiscoverinternal。 \<網域 \> A 為內部 Web 服務上的自動探索服務 (主機) 記錄</span><span class="sxs-lookup"><span data-stu-id="8b3b2-134">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="8b3b2-135">lyncdiscover。 \<網域 \> A (主 Web 服務上自動探索服務的主機) 記錄</span><span class="sxs-lookup"><span data-stu-id="8b3b2-135">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

<span data-ttu-id="8b3b2-136">其他記錄類型都沒有任何回退。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-136">There is no fallback to the other record types.</span></span>

<span data-ttu-id="8b3b2-137">與舊版用戶端相比，更新的用戶端所用的方法之間的差異是，自動探索服務正成為尋找所有服務的慣用方法。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-137">The difference between the methods used for newer clients as compared to older clients is that the Autodiscover service is becoming the preferred method to locate all services.</span></span>

<span data-ttu-id="8b3b2-138">連線成功時，自動探索服務會傳回使用者主集區的所有 Web 服務 URLs，包括行動服務 (稱為 Mcx，其為在 IIS) 中為服務建立的虛擬目錄、Microsoft Lync Web App 和 Web 排程器 URLs。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-138">When a connection is successful, the Autodiscover Service returns all the Web Services URLs for the user's home pool, including the Mobility Service (known as Mcx by the virtual directory created for the service in IIS), Microsoft Lync Web App and Web scheduler URLs.</span></span> <span data-ttu-id="8b3b2-139">不過，內部行動服務 URL 和外部行動服務 URL 都會與外部 Web 服務 FQDN 相關聯。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-139">However, both the internal Mobility Service URL and the external Mobility Service URL is associated with the external Web Services FQDN.</span></span> <span data-ttu-id="8b3b2-140">因此，不論行動裝置在網路內部或外部，裝置永遠都透過反向 proxy 連線到外部行動服務。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-140">Therefore, regardless of whether a mobile device is internal or external to the network, the device always connects to the Mobility Service externally through the reverse proxy.</span></span>

<span data-ttu-id="8b3b2-141">如果已安裝 Lync Server 2013 2013 的累計更新，則自動探索服務也會傳回對 Internal/UCWA、External/UCWA 和 UCWA 的參照。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-141">If the Cumulative Updates for Lync Server 2013: February 2013 has been installed, the Autodiscover Service also returns references to Internal/UCWA, External/UCWA and UCWA.</span></span> <span data-ttu-id="8b3b2-142">這些項目是指 Unified Communications Web API (UCWA) Web 元件。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-142">These entries refer to the Unified Communications Web API (UCWA) web component.</span></span> <span data-ttu-id="8b3b2-143">目前只會使用專案 UCWA，並提供網頁元件的 URL 參照。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-143">Currently, only the entry UCWA is used and provides a reference to a URL for the web component.</span></span> <span data-ttu-id="8b3b2-144">Lync 2013 行動用戶端會使用 UCWA，而不是 Lync 2010 行動用戶端所使用的 Mcx 行動服務。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-144">UCWA is used by Lync 2013 Mobile clients instead of the Mcx Mobility Service used by the Lync 2010 Mobile clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8b3b2-145">建立 SRV 記錄時，請務必記住，如果您在建立 DNS SRV 記錄的相同網域中使用 IPv6 定址) 記錄，這些記錄必須指向 DNS A 和 AAAA (。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-145">When creating SRV records, it is important to remember that they must point to a DNS A and AAAA (if you are using IPv6 addressing) record in the same domain in which the DNS SRV record is created.</span></span> <span data-ttu-id="8b3b2-146">例如，如果 SRV 記錄是在 contoso.com 中，則 A 和 AAAA (如果您使用 IPv6 定址) 記錄它指向的是 fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-146">For example, if the SRV record is in contoso.com, the A and AAAA (if you are using IPv6 addressing) record it points to cannot be in fabrikam.com.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="8b3b2-147">預設設定是透過外部網站指引所有行動用戶端流量。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-147">The default configuration is to direct all mobile client traffic through the external site.</span></span> <span data-ttu-id="8b3b2-148">您可以修改設定以只傳回內部 URL （如果這對您的需求更可取）。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-148">You can modify settings to return only the internal URL, if this is more preferable for your requirements.</span></span> <span data-ttu-id="8b3b2-149">透過這種設定，使用者只有在公司網路內部時，才可以在其行動裝置上使用 Lync 行動應用程式。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-149">With this configuration, users can use Lync mobile applications on their mobile devices only when they are inside the corporate network.</span></span> <span data-ttu-id="8b3b2-150">若要定義此設定，您可以使用<STRONG>Set-CsMcxConfiguration</STRONG> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-150">To define this configuration, you use the <STRONG>Set-CsMcxConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="8b3b2-151">雖然行動裝置應用程式也可以連線到其他 Lync Server 2013 服務，例如通訊錄服務，但內部行動應用程式 web 要求只會移至行動服務的外部 web FQDN。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-151">Although mobile applications can also connect to other Lync Server 2013 services, such as Address Book Service, internal mobile application web requests go to the external web FQDN only for the Mobility Service.</span></span> <span data-ttu-id="8b3b2-152">其他服務要求（例如通訊錄要求）不需要這項設定。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-152">Other service requests, such as Address Book requests, do not require this configuration.</span></span>



</div>

<span data-ttu-id="8b3b2-153">行動裝置支援手動探索服務。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-153">Mobile devices support manual discovery of services.</span></span> <span data-ttu-id="8b3b2-154">在此情況下，每一位使用者都必須使用完整的內部及外部自動探索服務 URIs （包括通訊協定和路徑）設定行動裝置設定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8b3b2-154">In this case, each user must configure the mobile device settings with the full internal and external Autodiscover Service URIs, including the protocol and path, as follows:</span></span>

  - <span data-ttu-id="8b3b2-155">HTTPs:// \< ExtPoolFQDN \> /Autodiscover/autodiscoverservice.svc/Root for external access</span><span class="sxs-lookup"><span data-stu-id="8b3b2-155">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>

  - <span data-ttu-id="8b3b2-156">HTTPs:// \< IntPoolFQDN \> /AutoDiscover/AutoDiscover.svc/Root for internal access</span><span class="sxs-lookup"><span data-stu-id="8b3b2-156">https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root for internal access</span></span>

<span data-ttu-id="8b3b2-157">建議您使用自動探索，而不是手動探索。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-157">We recommend that you use automatic discovery, rather than manual discovery.</span></span> <span data-ttu-id="8b3b2-158">不過，手動設定可用於疑難排解行動裝置連線問題。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-158">However, manual settings can be useful for troubleshooting mobile device connectivity issues.</span></span>

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a><span data-ttu-id="8b3b2-159">使用 Lync Server 設定 Split-Brain DNS</span><span class="sxs-lookup"><span data-stu-id="8b3b2-159">Configuring Split-Brain DNS with Lync Server</span></span>

<span data-ttu-id="8b3b2-160">Split-大腦 DNS 是以許多名稱命名，例如分割 DNS 或分割水準的 DNS。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-160">Split-brain DNS is known by a number of names, for example, split DNS or split-horizon DNS.</span></span> <span data-ttu-id="8b3b2-161">簡而言之，它會描述具有相同命名空間的兩個 DNS 區域的 DNS 設定，但有一個 DNS 區域服務僅限內部內部的要求，而另一個 dns 區域服務僅限外部的要求。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-161">Simply, it describes a DNS configuration where there are two DNS zones with the same namespace – but one DNS zone services internal-only requests, and the other DNS zone services external-only requests.</span></span> <span data-ttu-id="8b3b2-162">不過，內部 DNS 中包含的許多 DNS SRV 和記錄不會包含在外部 DNS 中，反過來也是如此。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-162">However, many of the DNS SRV and A records contained in the internal DNS will not be contained in the external DNS, and the reverse is also true.</span></span> <span data-ttu-id="8b3b2-163">在內部和外部 DNS (都存在相同的 DNS 記錄時，例如，www.contoso.com) 時，傳回的 IP 位址會因開始查詢 (內部或外部) 的位置而有所不同。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-163">In cases where the same DNS record exists in both the internal and external DNS (for example, www.contoso.com), the IP address returned will be different based on where (internal or external) the query was initiated.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8b3b2-164">目前，行動性（或特別是 LyncDiscover 和 LyncDiscoverInternal DNS 記錄）不支援 Split-Brain DNS。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-164">Currently, Split-Brain DNS is not supported for the mobility, or more specifically, the LyncDiscover and LyncDiscoverInternal DNS records.</span></span> <span data-ttu-id="8b3b2-165">LyncDiscover 必須在外部 DNS 伺服器上定義，而 LyncDiscoverInternal 必須定義在內部 DNS 伺服器上。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-165">LyncDiscover must be defined on an external DNS server and LyncDiscoverInternal must be defined on an internal DNS server.</span></span>



</div>

<span data-ttu-id="8b3b2-166">針對這些主題的目的，將會使用「分裂大腦型 DNS」。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-166">For the purposes of these topics, the term split-brain DNS will be used.</span></span>

<span data-ttu-id="8b3b2-167">如果您正在設定分裂大腦 DNS，下列內部及外部區域會包含每個區域中所需之 DNS 記錄類型的摘要。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-167">If you are configuring split-brain DNS, the following internal and external zone contain a summary of the types of DNS records required in each zone.</span></span> <span data-ttu-id="8b3b2-168">如需詳細資訊，請參閱[Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-168">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="8b3b2-169">**內部 DNS：**</span><span class="sxs-lookup"><span data-stu-id="8b3b2-169">**Internal DNS:**</span></span>

  - <span data-ttu-id="8b3b2-170">包含稱為 contoso.com 的 DNS 區域，其具有權威性</span><span class="sxs-lookup"><span data-stu-id="8b3b2-170">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="8b3b2-171">內部 contoso.com 區域包含：</span><span class="sxs-lookup"><span data-stu-id="8b3b2-171">The internal contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="8b3b2-172">DNS A 和 AAAA (如果您使用 IPv6 定址) 和 SRV 記錄進行內部 Lync Server 2013 用戶端自動設定 (選用) </span><span class="sxs-lookup"><span data-stu-id="8b3b2-172">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for internal Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="8b3b2-173">DNS A 和 AAAA (如果您使用 IPv6 定址) 或 CNAME 記錄來自動探索 Lync Server 2013 Web 服務 (選用) </span><span class="sxs-lookup"><span data-stu-id="8b3b2-173">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services (optional)</span></span>
    
      - <span data-ttu-id="8b3b2-174">DNS A 和 AAAA (如果您使用 IPv6 定址) 記錄的前端集區名稱、Director 或 Director 集區名稱，以及在公司網路中執行 Lync Server 2013 的所有內部伺服器</span><span class="sxs-lookup"><span data-stu-id="8b3b2-174">DNS A and AAAA (if you are using IPv6 addressing) records for Front End pool name, Director or Director pool name, and all internal servers running Lync Server 2013 in the corporate network</span></span>
    
      - <span data-ttu-id="8b3b2-175">DNS A 和 AAAA (如果您使用 IPv6 定址) 周邊網路中每個 Lync Server 2013，Edge Server 的 Edge 內部介面記錄。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-175">DNS A and AAAA (if you are using IPv6 addressing) records for the Edge internal interface of each Lync Server 2013, Edge Server in the perimeter network</span></span>
    
      - <span data-ttu-id="8b3b2-176">DNS A 和 AAAA (如果您使用 IPv6 定址周邊網路中每個反向 proxy 伺服器的內部介面的) 記錄 (反向 proxy 的管理選用) </span><span class="sxs-lookup"><span data-stu-id="8b3b2-176">DNS A and AAAA (if you are using IPv6 addressing) records for the internal interface of each reverse proxy server in the perimeter network (optional for management of reverse proxy)</span></span>
    
      - <span data-ttu-id="8b3b2-177">周邊網路中所有的 Lync Server 2013 Edge Server internal edge 介面都使用內部 DNS 區域，以將查詢解析為 contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-177">All Lync Server 2013  Edge Server internal edge interfaces in the perimeter network use the internal DNS zone for resolving queries to contoso.com</span></span>
    
      - <span data-ttu-id="8b3b2-178">在公司網路中執行 lync Server 2013 和執行 Lync 2013 之用戶端的所有伺服器指向內部 DNS 伺服器，用來解析 contoso.com 中的查詢，或在每個 Edge (server 上使用主機檔案，以及使用 IPv6) 定址下一個躍點伺服器（特別是 Director 或 Director VIP、前端集區 VIP 或 Standard Edition server）的記錄。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-178">All servers running Lync Server 2013 and clients running Lync 2013 in the corporate network point to the internal DNS servers for resolving queries to contoso.com, or use of HOSTS file on each Edge server and list A and AAAA (if you are using IPv6 addressing) records for next hop server, specifically the Director or Director VIP, Front End pool VIP, or Standard Edition server</span></span>

<span data-ttu-id="8b3b2-179">**外部 DNS：**</span><span class="sxs-lookup"><span data-stu-id="8b3b2-179">**External DNS:**</span></span>

  - <span data-ttu-id="8b3b2-180">包含稱為 contoso.com 的 DNS 區域，其具有權威性</span><span class="sxs-lookup"><span data-stu-id="8b3b2-180">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="8b3b2-181">外部 contoso.com 區域包含：</span><span class="sxs-lookup"><span data-stu-id="8b3b2-181">The external contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="8b3b2-182">DNS A 和 AAAA (如果您使用 IPv6 定址) 和 SRV 記錄進行 Lync Server 2013 用戶端自動設定 (選用) </span><span class="sxs-lookup"><span data-stu-id="8b3b2-182">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="8b3b2-183">DNS A 和 AAAA (如果您使用 IPv6 定址) 或 CNAME 記錄來自動探索 Lync Server 2013 Web 服務，以搭配行動性使用</span><span class="sxs-lookup"><span data-stu-id="8b3b2-183">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services for use with mobility</span></span>
    
      - <span data-ttu-id="8b3b2-184">DNS A 和 AAAA (如果您使用 IPv6 定址) 和 SRV 記錄，以用於周邊網路中每個 Lync Server 2013、Edge Server 或硬體負載平衡器虛擬 IP (VIP) 的 Edge 外部介面。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-184">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for the Edge external interface of each Lync Server 2013, Edge Server or hardware load balancer virtual IP (VIP) in the perimeter network</span></span>
    
      - <span data-ttu-id="8b3b2-185">DNS A 和 AAAA (如果針對周邊網路中的反向 proxy 伺服器集區，使用反向 proxy 伺服器或 VIP 之外部介面的 IPv6 定址) 記錄</span><span class="sxs-lookup"><span data-stu-id="8b3b2-185">DNS A and AAAA (if you are using IPv6 addressing) records for the external interface of the reverse proxy server or VIP for a pool of reverse proxy servers in the perimeter network</span></span>

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a><span data-ttu-id="8b3b2-186">不 Split-Brain DNS 的自動設定</span><span class="sxs-lookup"><span data-stu-id="8b3b2-186">Automatic Configuration without Split-Brain DNS</span></span>

<span data-ttu-id="8b3b2-187">在內部 DNS 區域包含 sipinternaltls 時，使用分裂大腦 DNS，在內部登入的 Lync Server 2013 使用者可以利用自動設定 \_ 。 \_使用中的每個 SIP 網域的 tcp SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-187">Using split-brain DNS, a Lync Server 2013 user that signs in internally can take advantage of automatic configuration if the internal DNS zone contains a \_sipinternaltls.\_tcp SRV record for each SIP domain in use.</span></span> <span data-ttu-id="8b3b2-188">不過，如果您不使用「分裂大腦」 DNS，則除非執行本節稍後所述的其中一個變通方法，否則執行 Lync 之用戶端的內部自動設定將無法運作。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-188">However, if you do not use split-brain DNS, internal automatic configuration of clients running Lync will not work unless one of the workarounds described in later in this section is implemented.</span></span> <span data-ttu-id="8b3b2-189">這是因為 Lync Server 2013 需要使用者的 SIP URI，以符合為自動設定指定之前端集區的網域。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-189">This is because Lync Server 2013 requires the user’s SIP URI to match the domain of the Front End pool designated for automatic configuration.</span></span> <span data-ttu-id="8b3b2-190">舊版的 Communicator 也是如此。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-190">This was also the case with earlier versions of Communicator.</span></span>

<span data-ttu-id="8b3b2-191">例如，如果您有兩個使用中的 SIP 網域，則需要下列 DNS 服務 (SRV) 記錄：</span><span class="sxs-lookup"><span data-stu-id="8b3b2-191">For example, if you have two SIP domains in use, the following DNS service (SRV) records would be required:</span></span>

  - <span data-ttu-id="8b3b2-192">如果使用者登入 bob@contoso.com，下列 SRV 記錄將可用於自動設定，因為使用者的 SIP 網域 (contoso.com) 符合自動設定前端集區的網域) ：</span><span class="sxs-lookup"><span data-stu-id="8b3b2-192">If a user signs in as bob@contoso.com the following SRV record will work for automatic configuration because the user’s SIP domain (contoso.com) matches the domain of automatic configuration Front End pool):</span></span>
    
     <span data-ttu-id="8b3b2-193">\_sipinternaltls。 \_tcp.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-193">\_sipinternaltls.\_tcp.contoso.com.</span></span> <span data-ttu-id="8b3b2-194">pool01.contoso.com SRV 0 0 5061 中的86400</span><span class="sxs-lookup"><span data-stu-id="8b3b2-194">86400 IN SRV 0 0 5061 pool01.contoso.com</span></span>

  - <span data-ttu-id="8b3b2-195">如果使用者以 alice@fabrikam.com 登入，下列 DNS SRV 記錄將可用於自動設定第二個 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-195">If a user signs in as alice@fabrikam.com the following DNS SRV record will work for automatic configuration of the second SIP domain.</span></span>
    
     <span data-ttu-id="8b3b2-196">\_sipinternaltls。 \_tcp.fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-196">\_sipinternaltls.\_tcp.fabrikam.com.</span></span> <span data-ttu-id="8b3b2-197">pool01.fabrikam.com SRV 0 0 5061 中的86400</span><span class="sxs-lookup"><span data-stu-id="8b3b2-197">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="8b3b2-198">為了進行比較，如果使用者以 tim@litwareinc.com 登入，下列 DNS SRV 記錄將無法用於自動設定，因為用戶端的 SIP 網域 (litwareinc.com) 與集區位於 (fabrikam.com) 的網域不符：</span><span class="sxs-lookup"><span data-stu-id="8b3b2-198">For comparison, if a user signs in as tim@litwareinc.com the following DNS SRV record will not work for automatic configuration, because the client’s SIP domain (litwareinc.com) does not match the domain that the pool is in (fabrikam.com):</span></span>

 <span data-ttu-id="8b3b2-199">\_sipinternaltls。 \_tcp.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-199">\_sipinternaltls.\_tcp.litwareinc.com.</span></span> <span data-ttu-id="8b3b2-200">pool01.fabrikam.com SRV 0 0 5061 中的86400</span><span class="sxs-lookup"><span data-stu-id="8b3b2-200">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="8b3b2-201">若執行 Lync 的用戶端需要自動設定，請選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="8b3b2-201">If automatic configuration is required for clients running Lync, select one of the following options:</span></span>

  - <span data-ttu-id="8b3b2-202">**群組原則物件**    使用群組原則物件 (Gpo) 填滿正確的伺服器值。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-202">**Group Policy Objects**   Use Group Policy objects (GPOs) to populate the correct server values.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8b3b2-203">此選項不會啟用自動設定，但是它會自動執行手動設定的處理常式，因此，如果使用此方法，則不需要與自動設定相關聯的 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-203">This option does not enable automatic configuration, but it does automate the process of manual configuration, so if this approach is used, the SRV records associated with automatic configuration are not required.</span></span>

    
    </div>

  - <span data-ttu-id="8b3b2-204">**相符的內部區域**    在內部 DNS 中建立與外部 DNS 區域相符的區域 (例如，如果您使用的 IPv6 定址) 記錄對應到用於自動設定的 Lync Server 2013 集區，則 contoso.com) 並建立 DNS A 和 AAAA (。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-204">**Matching internal zone**   Create a zone in the internal DNS that matches the external DNS zone (for example, contoso.com) and create DNS A and AAAA (if you are using IPv6 addressing) records corresponding to the Lync Server 2013 pool used for automatic configuration.</span></span> <span data-ttu-id="8b3b2-205">例如，如果使用者是位於 pool01.contoso.net，但登入 Lync 做為 bob@contoso.com，請建立名為 contoso.com 的內部 DNS 區域，並在其中建立 DNS A 和 AAAA (如果 IPv6 定址是用於 pool01.contoso.com 的) 記錄。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-205">For example, if a user is homed on pool01.contoso.net but signs into Lync as bob@contoso.com, create an internal DNS zone called contoso.com and inside it, create a DNS A and AAAA (if IPv6 addressing is used) record for pool01.contoso.com.</span></span>

  - <span data-ttu-id="8b3b2-206">**Pin 點內部區域**    如果您在內部 DNS 中建立整個區域不是選項，您可以建立 pin 點 (，也就是與自動設定所需之 SRV 記錄相對應的專用) 區域，並使用 dnscmd.exe 填入這些區域。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-206">**Pin-point internal zone**   If you are creating an entire zone in the internal DNS is not an option, you can create pin-point (that is, dedicated) zones that correspond to the SRV records that are required for automatic configuration, and populate those zones using dnscmd.exe.</span></span> <span data-ttu-id="8b3b2-207">因為 DNS 使用者介面不支援建立 pin 點區域，所以需要 Dnscmd.exe。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-207">Dnscmd.exe is required because the DNS user interface does not support creation of pin-point zones.</span></span> <span data-ttu-id="8b3b2-208">例如，如果 SIP 網域是 contoso.com，而且您有一個名為 pool01 的前端集區，且該集區包含兩部前端伺服器，則您必須在內部 DNS 中包含下列 pin 點區域和記錄：</span><span class="sxs-lookup"><span data-stu-id="8b3b2-208">For example, if the SIP domain is contoso.com and you have a Front End pool called pool01 that contains two Front End Servers, you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    <span data-ttu-id="8b3b2-209">如果您的環境包含第二個 SIP 網域 (例如，fabrikam.com) ，您必須在內部 DNS 中包含下列 pin 點區域和記錄：</span><span class="sxs-lookup"><span data-stu-id="8b3b2-209">If your environment contains a second SIP domain (for example, fabrikam.com), you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> <span data-ttu-id="8b3b2-210">前端集區 FQDN 會出現兩次，但有兩個不同的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-210">The Front End pool FQDN appears twice, but with two different IP addresses.</span></span> <span data-ttu-id="8b3b2-211">這是因為會使用 DNS 負載平衡，但是如果使用硬體負載平衡，則只有一個前端集區專案。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-211">This is because DNS load balancing is used, but if hardware load balancing is used, there would be only a single Front End pool entry.</span></span> <span data-ttu-id="8b3b2-212">此外，contoso.com 範例和 fabrikam.com 範例之間的前端集區 FQDN 值也會變更，但 IP 位址會保持不變。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-212">Also, the Front End pool FQDN values change between the contoso.com example and the fabrikam.com example, but the IP addresses remain the same.</span></span> <span data-ttu-id="8b3b2-213">這是因為使用者從任何 SIP 網域登入，請使用相同的前端集區進行自動設定。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-213">This is because users signing in from either SIP domain, use the same Front End pool for automatic configuration.</span></span>



</div>

<span data-ttu-id="8b3b2-214">如需詳細資訊，請參閱 DMTF 博客文章：「Communicator Automatic Configuration and Split-Brain DNS」，網址為 [https://go.microsoft.com/fwlink/p/?linkId=200707](https://go.microsoft.com/fwlink/p/?linkid=200707) 。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-214">For details, see the DMTF blog article, "Communicator Automatic Configuration and Split-Brain DNS," at [https://go.microsoft.com/fwlink/p/?linkId=200707](https://go.microsoft.com/fwlink/p/?linkid=200707).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8b3b2-215">每個網誌的內容及其 URL 如有變更，恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-215">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a><span data-ttu-id="8b3b2-216">設定網域名稱系統 (DNS) 以進行嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="8b3b2-216">Configuring the domain name system (DNS) for Disaster Recovery</span></span>

<span data-ttu-id="8b3b2-217">若要設定 DNS 將 Lync Server 2013 網頁流量重新導向至您的嚴重損壞修復和容錯移轉網站，您必須使用支援 GeoDNS 的 DNS 提供者。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-217">To configure DNS to redirect Lync Server 2013 Web traffic to your disaster recovery and failover sites, you must be using a DNS provider that supports GeoDNS.</span></span> <span data-ttu-id="8b3b2-218">您可以設定 Web 的 DNS 記錄以支援嚴重損壞修復，這樣即使一個整個前端集區中斷時，使用 Web 服務的功能仍會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-218">You can set up your DNS records for Web to support disaster recovery, so that features that use Web services continue even if one entire Front End pool goes down.</span></span> <span data-ttu-id="8b3b2-219">此嚴重損壞修復功能支援自動探索 (Lyncdiscover URL) 、符合和 Dial-In 簡易 URLs。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-219">This disaster recovery feature supports the Autodiscover (Lyncdiscover URL), Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="8b3b2-220">您可以定義及設定其他 DNS 主機 (A 和 AAAA，如果您在 GeoDNS 提供者上使用 Web 服務的內部及外部解決方案 IPv6) 記錄。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-220">You define and configure additional DNS host (A and AAAA if using IPv6) records for internal and external resolution of Web services at your GeoDNS provider.</span></span> <span data-ttu-id="8b3b2-221">下列詳細資料假設成對的集區、地理位置上的集區，以及您的提供者使用迴圈 DNS 所支援的 GeoDNS，或設定為使用 Pool1 做為主要，並在發生通信遺失或硬體故障時容錯移轉至 Pool2。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-221">The following details assume paired pools, geographically dispersed, and GeoDNS supported by your provider with either round-robin DNS, or configured to use Pool1 as primary, and fail over to Pool2 in the event of communications loss or hardware failure.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b3b2-222">GeoDNS 記錄 (範例) </span><span class="sxs-lookup"><span data-stu-id="8b3b2-222">GeoDNS record (example)</span></span></th>
<th><span data-ttu-id="8b3b2-223">集區記錄 (範例) </span><span class="sxs-lookup"><span data-stu-id="8b3b2-223">Pool records (example)</span></span></th>
<th><span data-ttu-id="8b3b2-224">CNAME 記錄 (範例) </span><span class="sxs-lookup"><span data-stu-id="8b3b2-224">CNAME records (example)</span></span></th>
<th><span data-ttu-id="8b3b2-225">DNS 設定 (選取一個選項) </span><span class="sxs-lookup"><span data-stu-id="8b3b2-225">DNS settings (select one option)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b3b2-226">Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-226">Meet-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8b3b2-227">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-227">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="8b3b2-228">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-228">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8b3b2-229">Meet.contoso.com 別名至 Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-229">Meet.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="8b3b2-230">Meet.contoso.com 別名至 Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-230">Meet.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8b3b2-231">集區間的迴圈</span><span class="sxs-lookup"><span data-stu-id="8b3b2-231">Round Robin between pools</span></span></p>
<p><span data-ttu-id="8b3b2-232">使用主要，如果失敗則連接至次要</span><span class="sxs-lookup"><span data-stu-id="8b3b2-232">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b3b2-233">Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-233">Meet-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8b3b2-234">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-234">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="8b3b2-235">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-235">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8b3b2-236">Meet.contoso.com 別名至 Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-236">Meet.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="8b3b2-237">Meet.contoso.com 別名至 Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-237">Meet.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8b3b2-238">集區間的迴圈</span><span class="sxs-lookup"><span data-stu-id="8b3b2-238">Round Robin between pools</span></span></p>
<p><span data-ttu-id="8b3b2-239">使用主要，如果失敗則連接至次要</span><span class="sxs-lookup"><span data-stu-id="8b3b2-239">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b3b2-240">Dialin-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-240">Dialin-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8b3b2-241">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-241">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="8b3b2-242">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-242">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8b3b2-243">Dialin.contoso.com 別名至 Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-243">Dialin.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="8b3b2-244">Dialin.contoso.com 別名至 Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-244">Dialin.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8b3b2-245">集區間的迴圈</span><span class="sxs-lookup"><span data-stu-id="8b3b2-245">Round Robin between pools</span></span></p>
<p><span data-ttu-id="8b3b2-246">使用主要，如果失敗則連接至次要</span><span class="sxs-lookup"><span data-stu-id="8b3b2-246">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b3b2-247">Dialin-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-247">Dialin-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8b3b2-248">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-248">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="8b3b2-249">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-249">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8b3b2-250">Dialin.contoso.com 別名至 Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-250">Dialin.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="8b3b2-251">Dialin.contoso.com 別名至 Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-251">Dialin.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8b3b2-252">集區間的迴圈</span><span class="sxs-lookup"><span data-stu-id="8b3b2-252">Round Robin between pools</span></span></p>
<p><span data-ttu-id="8b3b2-253">使用主要，如果失敗則連接至次要</span><span class="sxs-lookup"><span data-stu-id="8b3b2-253">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b3b2-254">Lyncdiscoverint-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-254">Lyncdiscoverint-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8b3b2-255">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-255">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="8b3b2-256">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-256">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8b3b2-257">Lyncdiscoverinternal.contoso.com 別名至 Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-257">Lyncdiscoverinternal.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="8b3b2-258">Lyncdiscoverinternal.contoso.com 別名至 Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-258">Lyncdiscoverinternal.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8b3b2-259">集區間的迴圈</span><span class="sxs-lookup"><span data-stu-id="8b3b2-259">Round Robin between pools</span></span></p>
<p><span data-ttu-id="8b3b2-260">使用主要，如果失敗則連接至次要</span><span class="sxs-lookup"><span data-stu-id="8b3b2-260">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b3b2-261">Lyncdiscover-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-261">Lyncdiscover-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8b3b2-262">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-262">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="8b3b2-263">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-263">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8b3b2-264">Lyncdiscover.contoso.com 別名至 Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-264">Lyncdiscover.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="8b3b2-265">Lyncdiscover.contoso.com 別名至 Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-265">Lyncdiscover.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8b3b2-266">集區間的迴圈</span><span class="sxs-lookup"><span data-stu-id="8b3b2-266">Round Robin between pools</span></span></p>
<p><span data-ttu-id="8b3b2-267">使用主要，如果失敗則連接至次要</span><span class="sxs-lookup"><span data-stu-id="8b3b2-267">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b3b2-268">Scheduler-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-268">Scheduler-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8b3b2-269">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-269">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="8b3b2-270">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-270">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8b3b2-271">Scheduler.contoso.com 別名至 Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-271">Scheduler.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="8b3b2-272">Scheduler.contoso.com 別名至 Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-272">Scheduler.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8b3b2-273">集區間的迴圈</span><span class="sxs-lookup"><span data-stu-id="8b3b2-273">Round Robin between pools</span></span></p>
<p><span data-ttu-id="8b3b2-274">使用主要，如果失敗則連接至次要</span><span class="sxs-lookup"><span data-stu-id="8b3b2-274">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b3b2-275">Scheduler-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-275">Scheduler-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8b3b2-276">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-276">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="8b3b2-277">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-277">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8b3b2-278">Scheduler.contoso.com 別名至 Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-278">Scheduler.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="8b3b2-279">Scheduler.contoso.com 別名至 Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b3b2-279">Scheduler.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8b3b2-280">集區間的迴圈</span><span class="sxs-lookup"><span data-stu-id="8b3b2-280">Round Robin between pools</span></span></p>
<p><span data-ttu-id="8b3b2-281">使用主要，如果失敗則連接至次要</span><span class="sxs-lookup"><span data-stu-id="8b3b2-281">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a><span data-ttu-id="8b3b2-282">DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="8b3b2-282">DNS Load Balancing</span></span>

<span data-ttu-id="8b3b2-283">DNS 負載平衡通常是在應用層級實施。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-283">DNS load balancing is typically implemented at the application level.</span></span> <span data-ttu-id="8b3b2-284">應用程式 (例如，執行 Lync) 的用戶端會嘗試連線到集區中的伺服器，方法是連線至 DNS A 和 (AAAA 所傳回的其中一個 IP 位址。如果 IPv6 定址是用於集區完整功能變數名稱) FQDN (的記錄查詢。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-284">The application (for example, a client running Lync), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="8b3b2-285">例如，如果名為 pool01.contoso.com 的集區中有三部前端伺服器，則會發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="8b3b2-285">For example, if there are three front end servers in a pool named pool01.contoso.com, the following will happen:</span></span>

  - <span data-ttu-id="8b3b2-286">執行 Lync 查詢 DNS 以供 pool01.contoso.com 的用戶端。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-286">Clients running Lync query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="8b3b2-287">查詢會傳回三個 IP 位址，並將其快取如下 (不一定要依此順序) ：</span><span class="sxs-lookup"><span data-stu-id="8b3b2-287">The query returns three IP addresses and caches them as follows (not necessarily in this order):</span></span>
    
    <span data-ttu-id="8b3b2-288">pool01.contoso.com 192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="8b3b2-288">pool01.contoso.com      192.168.10.90</span></span>
    
    <span data-ttu-id="8b3b2-289">pool01.contoso.com 192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="8b3b2-289">pool01.contoso.com      192.168.10.91</span></span>
    
    <span data-ttu-id="8b3b2-290">pool01.contoso.com 192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="8b3b2-290">pool01.contoso.com      192.168.10.92</span></span>

  - <span data-ttu-id="8b3b2-291">用戶端會嘗試建立傳輸控制通訊協定 (TCP) 連接至其中一個 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-291">The client attempts to establish a Transmission Control Protocol (TCP) connection to one of the IP addresses.</span></span> <span data-ttu-id="8b3b2-292">如果失敗，用戶端會嘗試在快取中的下一個 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-292">If that fails, the client tries the next IP address in the cache.</span></span>

  - <span data-ttu-id="8b3b2-293">如果 TCP 連線成功，用戶端會協商 TLS，以連線至 pool01.contoso.com 上的主要註冊機構。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-293">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>

  - <span data-ttu-id="8b3b2-294">如果用戶端嘗試所有的快取專案，但連線失敗，則會通知使用者目前沒有任何執行 Lync Server 2013 的伺服器可供使用。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-294">If the client tries all cached entries without a successful connection, the user is notified that no servers running Lync Server 2013 are available at the moment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8b3b2-295">DNS 的負載平衡與 DNS 迴圈使用不同 (DNS RR) ，其主要指的是透過 DNS 提供與集區中伺服器對應的不同順序的負載平衡。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-295">DNS-based load balancing is different from DNS round robin (DNS RR) which typically refers to load balancing by relying on DNS to provide a different order of IP addresses corresponding to the servers in a pool.</span></span> <span data-ttu-id="8b3b2-296">通常 DNS RR 只會啟用負載分配，但不會啟用容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-296">Typically DNS RR only enables load distribution, but does not enable failover.</span></span> <span data-ttu-id="8b3b2-297">例如，如果您在使用 IPv6 定址) 查詢失敗時，由 DNS A 和 AAAA (所傳回的一個 IP 位址進行連線，連接就會失敗。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-297">For example, if the connection to the one IP address returned by the DNS A and AAAA (if you are using IPv6 addressing) query fails, the connection fails.</span></span> <span data-ttu-id="8b3b2-298">因此，來自于 DNS 的負載平衡，其本身的 [DNS] 迴圈是不夠可靠的。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-298">Therefore, DNS round robin by itself is less reliable than DNS-based load balancing.</span></span> <span data-ttu-id="8b3b2-299">您可以搭配 DNS 負載平衡使用 DNS 迴圈。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-299">You can use DNS round robin in conjunction with DNS load balancing.</span></span>



</div>

<span data-ttu-id="8b3b2-300">DNS 負載平衡用於下列專案：</span><span class="sxs-lookup"><span data-stu-id="8b3b2-300">DNS load balancing is used for the following:</span></span>

  - <span data-ttu-id="8b3b2-301">將伺服器對伺服器的 SIP 負載平衡至 Edge server</span><span class="sxs-lookup"><span data-stu-id="8b3b2-301">Load balancing server-to-server SIP to the Edge Servers</span></span>

  - <span data-ttu-id="8b3b2-302">負載平衡整合通訊應用程式服務 (UCAS) 應用程式，例如會議自動語音應答、回應群組和通話駐留</span><span class="sxs-lookup"><span data-stu-id="8b3b2-302">Load balancing Unified Communications Application Services (UCAS) applications such as Conferencing Auto Attendant, Response Group, and Call Park</span></span>

  - <span data-ttu-id="8b3b2-303">防止新連線 UCAS 應用程式 (也稱為「耗盡」 ) </span><span class="sxs-lookup"><span data-stu-id="8b3b2-303">Preventing new connections to UCAS applications (also known as "draining")</span></span>

  - <span data-ttu-id="8b3b2-304">在用戶端和 Edge server 之間負載平衡所有用戶端對伺服器流量</span><span class="sxs-lookup"><span data-stu-id="8b3b2-304">Load balancing all client-to-server traffic between clients and Edge Servers</span></span>

<span data-ttu-id="8b3b2-305">DNS 負載平衡無法用於下列專案：</span><span class="sxs-lookup"><span data-stu-id="8b3b2-305">DNS load balancing cannot be used for the following:</span></span>

  - <span data-ttu-id="8b3b2-306">對 Director 或前端伺服器的用戶端對伺服器網頁流量</span><span class="sxs-lookup"><span data-stu-id="8b3b2-306">Client-to-server web traffic to Director or Front End Servers</span></span>

<span data-ttu-id="8b3b2-307">DNS 負載平衡及同盟流量：</span><span class="sxs-lookup"><span data-stu-id="8b3b2-307">DNS load balancing and federated traffic:</span></span>

<span data-ttu-id="8b3b2-308">如果 DNS SRV 查詢傳回多個 DNS 記錄，Access Edge service 一定會選取具有最低的數值優先順序和最高數值權重的 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-308">If multiple DNS records are returned by a DNS SRV query, the Access Edge service always picks the DNS SRV record with the lowest numeric priority and highest numeric weight.</span></span> <span data-ttu-id="8b3b2-309">網際網路工程任務強制檔「用於指定服務位置 (DNS) SRV」的 DNS RR <http://www.ietf.org/rfc/rfc2782.txt> ）指定如果已定義多個 DNS srv 記錄，則會先使用優先順序，然後再使用「加權」。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-309">The Internet Engineering Task Force document “A DNS RR for specifying the location of services (DNS SRV)” <http://www.ietf.org/rfc/rfc2782.txt> specifies that if there are multiple DNS SRV records defined, priority is first used, then weight.</span></span> <span data-ttu-id="8b3b2-310">例如，DNS SRV 記錄 A 的權重為20，優先順序為40，而 DNS SRV 記錄 B 的權重為10，優先順序為50。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-310">For example DNS SRV record A has a weight of 20 and a priority of 40 and DNS SRV record B has a weight of 10 and priority of 50.</span></span> <span data-ttu-id="8b3b2-311">將會選取具有優先順序40的 DNS SRV 記錄 A。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-311">DNS SRV record A with priority 40 will be selected.</span></span> <span data-ttu-id="8b3b2-312">下列規則適用于 DNS SRV 記錄選取：</span><span class="sxs-lookup"><span data-stu-id="8b3b2-312">The following rules apply to DNS SRV record selection:</span></span>

  - <span data-ttu-id="8b3b2-313">優先順序會先考慮。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-313">Priority is considered first.</span></span> <span data-ttu-id="8b3b2-314">用戶端必須嘗試聯繫 DNS SRV 記錄所定義的目標主機，其可達到的最低優先順序。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-314">A client MUST attempt to contact the target host defined by the DNS SRV record with the lowest numbered priority it can reach.</span></span> <span data-ttu-id="8b3b2-315">應以「加權」欄位所定義的順序，嘗試相同優先順序的目標。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-315">Targets with the same priority SHOULD be tried in an order defined by the weight field.</span></span>

  - <span data-ttu-id="8b3b2-316">[加權] 欄位會指定具有相同優先順序之專案的相對權重。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-316">The weight field specifies a relative weight for entries with the same priority.</span></span> <span data-ttu-id="8b3b2-317">應將較大的權重按比例增加選取的概率。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-317">Larger weights SHOULD be given a proportionately higher probability of being selected.</span></span> <span data-ttu-id="8b3b2-318">DNS 管理員應該在沒有任何要執行的伺服器選擇時使用權重0。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-318">DNS administrators SHOULD use Weight 0 when there isn’t any server selection to do.</span></span> <span data-ttu-id="8b3b2-319">當記錄中包含的權重大於0時，具有權重0的記錄應該會有很小的可能被選取。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-319">In the presence of records containing weights greater than 0, records with weight 0 should have a very small chance of being selected.</span></span>

<span data-ttu-id="8b3b2-320">若傳回多個具有相同優先順序和權重的 DNS SRV 記錄，Access Edge service 會選取最先從 DNS 伺服器接收的 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="8b3b2-320">If multiple DNS SRV records with equal priority and weight are returned, the Access Edge service will select the SRV record that was received first from the DNS server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

