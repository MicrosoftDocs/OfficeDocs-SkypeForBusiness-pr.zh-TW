---
title: Lync Server 2013：判定 DNS 需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Determine DNS requirements
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398758(v=OCS.15)
ms:contentKeyID: 48184839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e299f138a28ba4863250d2e0be1f31f705f4a173
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="1e2ae-102">針對 Lync Server 2013 判定 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="1e2ae-102">Determine DNS requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e2ae-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="1e2ae-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="1e2ae-104">使用下列流程圖來判斷網域名稱系統（DNS）需求。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-104">Use the following flow chart to determine Domain Name System (DNS) requirements.</span></span> <span data-ttu-id="1e2ae-105">Lync Server 2013 的累積更新變更：2月2013日會在其適用的地方注明。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-105">Changes for the Cumulative Updates for Lync Server 2013: February 2013 are noted where they apply.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1e2ae-106">Microsoft Lync Server 2013 支援使用 IPv6 定址。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-106">Microsoft Lync Server 2013 supports the use of IPv6 addressing.</span></span> <span data-ttu-id="1e2ae-107">若要使用 IPv6 位址，您也必須為 IPv6 DNS 提供支援，並設定 DNS 主機 AAAA （稱為「四 A」）記錄。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-107">To use IPv6 addresses, you must also provide support for IPv6 DNS and configure DNS host AAAA (known as “quad-A”) records.</span></span> <span data-ttu-id="1e2ae-108">在使用 IPv4 與 IPv6 的部署中，最好是設定及維護 IPv4 和 IPv6 主機 AAAA 的主機 A 記錄。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-108">In deployments where both IPv4 and IPv6 are being used, it is best to configure and maintain both host A records for IPv4 and host AAAA for IPv6.</span></span> <span data-ttu-id="1e2ae-109">即使您的部署已完全轉換為 IPv6，但是當外部使用者仍在使用 IPv4 時，仍可能需要 IPv4 DNS 主機記錄。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-109">Even if your deployment has transitioned fully to IPv6, IPv4 DNS host records may still be required when external users are still using IPv4.</span></span>



</div>

<span data-ttu-id="1e2ae-110">**決定 DNS 需求流程圖**</span><span class="sxs-lookup"><span data-stu-id="1e2ae-110">**Determining DNS Requirements Flow Chart**</span></span>

<span data-ttu-id="1e2ae-111">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span><span class="sxs-lookup"><span data-stu-id="1e2ae-111">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1e2ae-112">根據預設，未加入網域之電腦的電腦名稱稱是主機名稱，而不是完全限定的功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-112">By default the computer name of a computer that is not joined to a domain is a host name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="1e2ae-113">拓撲建造器使用 Fqdn，而不是主機名稱。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-113">Topology Builder uses FQDNs, not host names.</span></span> <span data-ttu-id="1e2ae-114">因此，您必須在要部署為邊緣伺服器且未加入網域的電腦名稱稱上設定 DNS 尾碼。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-114">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="1e2ae-115">在指派 Lync Server、Edge 伺服器和池的 Fqdn 時，<STRONG>只使用標準字元</STRONG>（包括 a-z、A 至 z、0–9和連字號）。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-115"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="1e2ae-116">請勿使用 Unicode 字元或底線。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-116">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="1e2ae-117">外部 DNS 和公用 Ca 通常不支援 FQDN 中的非標準字元（也就是當 FQDN 必須指派給憑證中的 SN）時。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-117">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="1e2ae-118">如需其他詳細資料，請參閱<A href="lync-server-2013-configure-dns-host-records.md">設定 Lync Server 2013 的 DNS 主機記錄</A></span><span class="sxs-lookup"><span data-stu-id="1e2ae-118">For additional details, see <A href="lync-server-2013-configure-dns-host-records.md">Configure DNS Host records for Lync Server 2013</A></span></span>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a><span data-ttu-id="1e2ae-119">Lync 用戶端如何找到服務</span><span class="sxs-lookup"><span data-stu-id="1e2ae-119">How Lync Clients Locate Services</span></span>

<span data-ttu-id="1e2ae-120">Microsoft Lync 2010、Lync 2013 和 Lync Mobile 與用戶端在 Lync Server 2013 中尋找及存取服務的方式類似。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-120">Microsoft Lync 2010, Lync 2013, and Lync Mobile are similar in how the client finds and accesses services in Lync Server 2013.</span></span> <span data-ttu-id="1e2ae-121">[重要例外] 是使用不同服務位置程式的 Lync Windows Store app。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-121">The notable exception is the Lync Windows Store app that uses a different service location process.</span></span> <span data-ttu-id="1e2ae-122">本節詳細說明用戶端如何尋找服務的兩個案例，首先是使用一系列 SRV 與主機記錄的傳統方法，第二個只使用自動探索服務記錄。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-122">This section details two scenarios of how the clients locate services, first the traditional method using a series of SRV and A host records, second using only the Autodiscover service records.</span></span> <span data-ttu-id="1e2ae-123">對桌面用戶端的累加性更新從 Lync Server 2010 變更所有用戶端的 DNS 位置程式，DNS 查詢程式會繼續，直到傳回成功的查詢為止，或是已耗盡可能的 DNS 記錄清單，且最終的錯誤會傳回用戶端。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-123">Cumulative updates to the desktop clients change the DNS location process from Lync Server 2010 For all clients, the DNS query process continues until a successful query is returned, or the list of possible DNS records is exhausted, and the final error is returned to the client.</span></span>

<span data-ttu-id="1e2ae-124">在 DNS 查閱期間，除了 Lync Windows Store 應用程式**之外**，對於所有用戶端，都以下列順序查詢並傳回用戶端的 SRV 記錄：</span><span class="sxs-lookup"><span data-stu-id="1e2ae-124">For all clients **except** for the Lync Windows Store app During DNS lookup, SRV records are queried and returned to the client in the following order:</span></span>

1.  <span data-ttu-id="1e2ae-125">lyncdiscoverinternal.\<內部\> Web 服務的自動探索服務的網域 A （主機）記錄</span><span class="sxs-lookup"><span data-stu-id="1e2ae-125">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="1e2ae-126">lyncdiscover.\<外部\> Web 服務的自動探索服務的網域 A （主機）記錄</span><span class="sxs-lookup"><span data-stu-id="1e2ae-126">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

3.  <span data-ttu-id="1e2ae-127">\_sipinternaltls.\_tcp。\<內部\> TLS 連線的網域 SRV （服務定位器）記錄</span><span class="sxs-lookup"><span data-stu-id="1e2ae-127">\_sipinternaltls.\_tcp.\<domain\>   SRV (service locator) record for internal TLS connections</span></span>

4.  <span data-ttu-id="1e2ae-128">\_sipinternal.\_tcp。\<內部\> TCP 連線的網域 SRV （服務定位器）記錄（只有在 TCP 允許時才會執行）</span><span class="sxs-lookup"><span data-stu-id="1e2ae-128">\_sipinternal.\_tcp.\<domain\>   SRV (service locator) record for internal TCP connections (performed only if TCP is allowed)</span></span>

5.  <span data-ttu-id="1e2ae-129">\_呼吸.\_tls。\<外部\> TLS 連線的網域 SRV （服務定位器）記錄</span><span class="sxs-lookup"><span data-stu-id="1e2ae-129">\_sip.\_tls.\<domain\>   SRV (service locator) record for external TLS connections</span></span>

6.  <span data-ttu-id="1e2ae-130">sipinternal.\<前\>端池或控制器的網域 A （主機）記錄，只能在內部網路上解析</span><span class="sxs-lookup"><span data-stu-id="1e2ae-130">sipinternal.\<domain\>   A (host) record for the Front End pool or Director, resolvable only on the internal network</span></span>

7.  <span data-ttu-id="1e2ae-131">呼吸.\<在\>用戶端為外部網路的前端池或控制器的網域 A （主機）記錄，或存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="1e2ae-131">sip.\<domain\>   A (host) record for the Front End pool or Director on the internal network, or the Access Edge service when the client is external</span></span>

8.  <span data-ttu-id="1e2ae-132">sipexternal.\<客戶\>端的網域 A （主機）記錄，用於存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="1e2ae-132">sipexternal.\<domain\>   A (host) record for the Access Edge service when the client is external</span></span>

<span data-ttu-id="1e2ae-133">Lync Windows Store 應用程式會完全變更程式，因為它使用兩筆記錄：</span><span class="sxs-lookup"><span data-stu-id="1e2ae-133">The Lync Windows Store app changes the process completely because it uses two records:</span></span>

1.  <span data-ttu-id="1e2ae-134">lyncdiscoverinternal.\<內部\> Web 服務的自動探索服務的網域 A （主機）記錄</span><span class="sxs-lookup"><span data-stu-id="1e2ae-134">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="1e2ae-135">lyncdiscover.\<外部\> Web 服務的自動探索服務的網域 A （主機）記錄</span><span class="sxs-lookup"><span data-stu-id="1e2ae-135">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

<span data-ttu-id="1e2ae-136">沒有任何其他記錄類型的回退。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-136">There is no fallback to the other record types.</span></span>

<span data-ttu-id="1e2ae-137">與較舊的用戶端相比，更新之用戶端所用的方法之間的差異是，自動探索服務成為找出所有服務的首選方法。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-137">The difference between the methods used for newer clients as compared to older clients is that the Autodiscover service is becoming the preferred method to locate all services.</span></span>

<span data-ttu-id="1e2ae-138">當連線成功時，自動探索服務會傳回使用者的主文件庫的所有 Web 服務 Url，包括行動服務（稱為由在 IIS 中為服務建立的虛擬目錄的 Mcx）、Microsoft Lync Web App 及網頁排程程式 Url。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-138">When a connection is successful, the Autodiscover Service returns all the Web Services URLs for the user's home pool, including the Mobility Service (known as Mcx by the virtual directory created for the service in IIS), Microsoft Lync Web App and Web scheduler URLs.</span></span> <span data-ttu-id="1e2ae-139">不過，內部行動服務 URL 與外部行動服務 URL 都與外部 Web 服務 FQDN 相關聯。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-139">However, both the internal Mobility Service URL and the external Mobility Service URL is associated with the external Web Services FQDN.</span></span> <span data-ttu-id="1e2ae-140">因此，無論行動裝置是內部還是外部的網路，該裝置都永遠能透過反向 proxy 連線到外部行動服務。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-140">Therefore, regardless of whether a mobile device is internal or external to the network, the device always connects to the Mobility Service externally through the reverse proxy.</span></span>

<span data-ttu-id="1e2ae-141">如果 Lync Server 2013 的累積更新：已安裝2月2013，自動探索服務也會傳回內部/UCWA、External/UCWA 和 UCWA 的參照。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-141">If the Cumulative Updates for Lync Server 2013: February 2013 has been installed, the Autodiscover Service also returns references to Internal/UCWA, External/UCWA and UCWA.</span></span> <span data-ttu-id="1e2ae-142">這些專案是指整合通訊 Web API （UCWA）網頁元件。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-142">These entries refer to the Unified Communications Web API (UCWA) web component.</span></span> <span data-ttu-id="1e2ae-143">目前只會使用 [專案 UCWA]，並提供網頁元件 URL 的參照。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-143">Currently, only the entry UCWA is used and provides a reference to a URL for the web component.</span></span> <span data-ttu-id="1e2ae-144">UCWA 是由 Lync 2013 行動用戶端使用，而不是 Lync 2010 行動用戶端所使用的 Mcx 行動服務。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-144">UCWA is used by Lync 2013 Mobile clients instead of the Mcx Mobility Service used by the Lync 2010 Mobile clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1e2ae-145">建立 SRV 記錄時，請務必記住，必須在建立 DNS SRV 記錄的同一個網域中，指向 DNS A 和 AAAA （如果您使用的是 IPv6 定址）記錄。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-145">When creating SRV records, it is important to remember that they must point to a DNS A and AAAA (if you are using IPv6 addressing) record in the same domain in which the DNS SRV record is created.</span></span> <span data-ttu-id="1e2ae-146">例如，如果 SRV 記錄是在 contoso.com 中，A 和 AAAA （如果您使用的是 IPv6 定址）記錄不能位於 fabrikam.com 中。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-146">For example, if the SRV record is in contoso.com, the A and AAAA (if you are using IPv6 addressing) record it points to cannot be in fabrikam.com.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="1e2ae-147">預設設定是透過外部網站引導所有行動用戶端流量。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-147">The default configuration is to direct all mobile client traffic through the external site.</span></span> <span data-ttu-id="1e2ae-148">您可以將設定修改為只傳回內部 URL （如果這比您的需求更可取）。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-148">You can modify settings to return only the internal URL, if this is more preferable for your requirements.</span></span> <span data-ttu-id="1e2ae-149">有了這種設定，使用者就只能在他們的行動裝置上使用 Lync 行動應用程式（只有在商業網路內）。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-149">With this configuration, users can use Lync mobile applications on their mobile devices only when they are inside the corporate network.</span></span> <span data-ttu-id="1e2ae-150">若要定義這項設定，您可以使用<STRONG>CsMcxConfiguration</STRONG> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-150">To define this configuration, you use the <STRONG>Set-CsMcxConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="1e2ae-151">雖然行動裝置應用程式也可以連線至其他 Lync Server 2013 服務（例如通訊錄服務），但內部行動應用程式的 web 要求只能針對行動服務移至外部網頁 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-151">Although mobile applications can also connect to other Lync Server 2013 services, such as Address Book Service, internal mobile application web requests go to the external web FQDN only for the Mobility Service.</span></span> <span data-ttu-id="1e2ae-152">其他服務要求（例如通訊錄要求）不需要此設定。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-152">Other service requests, such as Address Book requests, do not require this configuration.</span></span>



</div>

<span data-ttu-id="1e2ae-153">行動裝置支援手動搜尋服務。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-153">Mobile devices support manual discovery of services.</span></span> <span data-ttu-id="1e2ae-154">在這種情況下，每個使用者都必須使用完整的內部和外部自動探索服務 Uri 來設定行動裝置設定，包括通訊協定和路徑，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1e2ae-154">In this case, each user must configure the mobile device settings with the full internal and external Autodiscover Service URIs, including the protocol and path, as follows:</span></span>

  - <span data-ttu-id="1e2ae-155">HTTPs://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root 以進行外部存取</span><span class="sxs-lookup"><span data-stu-id="1e2ae-155">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>

  - <span data-ttu-id="1e2ae-156">HTTPs://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root （內部存取）</span><span class="sxs-lookup"><span data-stu-id="1e2ae-156">https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root for internal access</span></span>

<span data-ttu-id="1e2ae-157">我們建議您使用自動探索，而不是手動搜尋。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-157">We recommend that you use automatic discovery, rather than manual discovery.</span></span> <span data-ttu-id="1e2ae-158">不過，您可以使用手動設定來針對行動裝置連線問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-158">However, manual settings can be useful for troubleshooting mobile device connectivity issues.</span></span>

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a><span data-ttu-id="1e2ae-159">使用 Lync Server 設定分割大腦 DNS</span><span class="sxs-lookup"><span data-stu-id="1e2ae-159">Configuring Split-Brain DNS with Lync Server</span></span>

<span data-ttu-id="1e2ae-160">使用分割大腦 DNS 是由多個名稱來命名，例如，分割 DNS 或分割範圍的 DNS。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-160">Split-brain DNS is known by a number of names, for example, split DNS or split-horizon DNS.</span></span> <span data-ttu-id="1e2ae-161">簡單地說，它描述了有兩個具有相同命名空間的 DNS 區域的 DNS 設定，但有一個 DNS 區域服務僅供內部使用的要求，以及另一個 dns 區域服務僅限外部的要求。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-161">Simply, it describes a DNS configuration where there are two DNS zones with the same namespace – but one DNS zone services internal-only requests, and the other DNS zone services external-only requests.</span></span> <span data-ttu-id="1e2ae-162">不過，內部 DNS 中包含的許多 DNS SRV 與 A 記錄，都不會包含在外部 DNS 中，反之也是如此。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-162">However, many of the DNS SRV and A records contained in the internal DNS will not be contained in the external DNS, and the reverse is also true.</span></span> <span data-ttu-id="1e2ae-163">在內部和外部 DNS （例如，www.contoso.com）中同時存在相同的 DNS 記錄的情況下，傳回的 IP 位址會根據啟動查詢的位置（內部或外部）而有所不同。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-163">In cases where the same DNS record exists in both the internal and external DNS (for example, www.contoso.com), the IP address returned will be different based on where (internal or external) the query was initiated.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1e2ae-164">目前不支援行動性的 LyncDiscover 和 LyncDiscoverInternal DNS 記錄，因此不支援移動功能的分裂式 DNS。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-164">Currently, Split-Brain DNS is not supported for the mobility, or more specifically, the LyncDiscover and LyncDiscoverInternal DNS records.</span></span> <span data-ttu-id="1e2ae-165">LyncDiscover 必須在外部 DNS 伺服器上定義，而 LyncDiscoverInternal 必須在內部 DNS 伺服器上定義。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-165">LyncDiscover must be defined on an external DNS server and LyncDiscoverInternal must be defined on an internal DNS server.</span></span>



</div>

<span data-ttu-id="1e2ae-166">出於這些主題的目的，將會使用「分割大腦」等詞。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-166">For the purposes of these topics, the term split-brain DNS will be used.</span></span>

<span data-ttu-id="1e2ae-167">如果您正在設定分割大腦 DNS，下列內部和外部區域會包含每個區域中所需的 DNS 記錄類型摘要。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-167">If you are configuring split-brain DNS, the following internal and external zone contain a summary of the types of DNS records required in each zone.</span></span> <span data-ttu-id="1e2ae-168">如需詳細資訊，請參閱[Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-168">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="1e2ae-169">**內部 DNS：**</span><span class="sxs-lookup"><span data-stu-id="1e2ae-169">**Internal DNS:**</span></span>

  - <span data-ttu-id="1e2ae-170">包含一個名為 contoso.com 的 DNS 區域，其具有權威性</span><span class="sxs-lookup"><span data-stu-id="1e2ae-170">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="1e2ae-171">內部 contoso.com 區域包含：</span><span class="sxs-lookup"><span data-stu-id="1e2ae-171">The internal contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="1e2ae-172">DNS A 與 AAAA （如果您使用的是 IPv6 定址）與內部 Lync Server 2013 用戶端自動設定的 SRV 記錄（選用）</span><span class="sxs-lookup"><span data-stu-id="1e2ae-172">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for internal Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="1e2ae-173">DNS A 與 AAAA （如果您使用的是 IPv6 定址），或可自動探索 Lync Server 2013 Web Services 的 CNAME 記錄（選用）</span><span class="sxs-lookup"><span data-stu-id="1e2ae-173">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services (optional)</span></span>
    
      - <span data-ttu-id="1e2ae-174">DNS A 與 AAAA （如果您使用的是 IPv6 定址）記錄的前端池名稱、導演或主管池名稱，以及所有在商業網路中執行 Lync Server 2013 的內部伺服器</span><span class="sxs-lookup"><span data-stu-id="1e2ae-174">DNS A and AAAA (if you are using IPv6 addressing) records for Front End pool name, Director or Director pool name, and all internal servers running Lync Server 2013 in the corporate network</span></span>
    
      - <span data-ttu-id="1e2ae-175">DNS A 和 AAAA （如果您使用的是 IPv6 定址），適用于周邊網路中每個 Lync Server 2013、Edge 伺服器的邊緣內部介面的記錄</span><span class="sxs-lookup"><span data-stu-id="1e2ae-175">DNS A and AAAA (if you are using IPv6 addressing) records for the Edge internal interface of each Lync Server 2013, Edge Server in the perimeter network</span></span>
    
      - <span data-ttu-id="1e2ae-176">DNS A 和 AAAA （如果您使用的是針對周邊網路中每個反向 proxy 伺服器的內部介面使用 IPv6 定址）記錄（對於反向 proxy 管理，則為選用）</span><span class="sxs-lookup"><span data-stu-id="1e2ae-176">DNS A and AAAA (if you are using IPv6 addressing) records for the internal interface of each reverse proxy server in the perimeter network (optional for management of reverse proxy)</span></span>
    
      - <span data-ttu-id="1e2ae-177">周邊網路中的所有 Lync Server 2013 Edge 伺服器內部邊緣介面使用內部 DNS 區域來解析要 contoso.com 的查詢</span><span class="sxs-lookup"><span data-stu-id="1e2ae-177">All Lync Server 2013  Edge Server internal edge interfaces in the perimeter network use the internal DNS zone for resolving queries to contoso.com</span></span>
    
      - <span data-ttu-id="1e2ae-178">所有執行 Lync Server 2013 的伺服器，以及在商業網路中執行 Lync 2013 的用戶端指向內部 DNS 伺服器，以解析要 contoso.com 的查詢，或在每個 Edge 伺服器上使用 HOSTS 檔案，或在清單 A 和 AAAA （如果您使用 IPv6 定址）記錄進行下一個躍點伺服器，特別是主管或主管 VIP、前臺端池 VIP 或標準版伺服器</span><span class="sxs-lookup"><span data-stu-id="1e2ae-178">All servers running Lync Server 2013 and clients running Lync 2013 in the corporate network point to the internal DNS servers for resolving queries to contoso.com, or use of HOSTS file on each Edge server and list A and AAAA (if you are using IPv6 addressing) records for next hop server, specifically the Director or Director VIP, Front End pool VIP, or Standard Edition server</span></span>

<span data-ttu-id="1e2ae-179">**外部 DNS：**</span><span class="sxs-lookup"><span data-stu-id="1e2ae-179">**External DNS:**</span></span>

  - <span data-ttu-id="1e2ae-180">包含一個名為 contoso.com 的 DNS 區域，其具有權威性</span><span class="sxs-lookup"><span data-stu-id="1e2ae-180">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="1e2ae-181">外部 contoso.com 區域包含：</span><span class="sxs-lookup"><span data-stu-id="1e2ae-181">The external contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="1e2ae-182">DNS A 與 AAAA （如果您使用的是 IPv6 定址）和 Lync Server 2013 用戶端自動設定的 SRV 記錄（選用）</span><span class="sxs-lookup"><span data-stu-id="1e2ae-182">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="1e2ae-183">DNS A 與 AAAA （如果您使用的是 IPv6 定址）或 CNAME 記錄，以自動探索 Lync Server 2013 Web 服務以搭配行動使用</span><span class="sxs-lookup"><span data-stu-id="1e2ae-183">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services for use with mobility</span></span>
    
      - <span data-ttu-id="1e2ae-184">DNS A 和 AAAA （如果您使用的是 IPv6 定址），以及周邊網路中每個 Lync Server 2013、Edge 伺服器或硬體負載平衡器虛擬 IP （VIP）之 Edge 外部介面的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="1e2ae-184">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for the Edge external interface of each Lync Server 2013, Edge Server or hardware load balancer virtual IP (VIP) in the perimeter network</span></span>
    
      - <span data-ttu-id="1e2ae-185">DNS A 與 AAAA （如果您是使用 IPv6 定址），在周邊網路中的反向 proxy 伺服器或 VIP 的外部介面</span><span class="sxs-lookup"><span data-stu-id="1e2ae-185">DNS A and AAAA (if you are using IPv6 addressing) records for the external interface of the reverse proxy server or VIP for a pool of reverse proxy servers in the perimeter network</span></span>

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a><span data-ttu-id="1e2ae-186">不含分裂的 DNS 的自動設定</span><span class="sxs-lookup"><span data-stu-id="1e2ae-186">Automatic Configuration without Split-Brain DNS</span></span>

<span data-ttu-id="1e2ae-187">如果內部 DNS 區域包含\_sipinternaltls，則使用分割大腦 DNS，在內部登入的 Lync Server 2013 使用者可以利用自動設定。\_使用中的每個 SIP 網域的 tcp SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-187">Using split-brain DNS, a Lync Server 2013 user that signs in internally can take advantage of automatic configuration if the internal DNS zone contains a \_sipinternaltls.\_tcp SRV record for each SIP domain in use.</span></span> <span data-ttu-id="1e2ae-188">不過，如果您不使用分割大腦 DNS，除非本區段稍後所述的其中一個因應措施，否則執行 Lync 之用戶端的內部自動設定將無法運作。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-188">However, if you do not use split-brain DNS, internal automatic configuration of clients running Lync will not work unless one of the workarounds described in later in this section is implemented.</span></span> <span data-ttu-id="1e2ae-189">這是因為 Lync Server 2013 需要使用者的 SIP URI，以符合為自動設定所指定的前端池網域。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-189">This is because Lync Server 2013 requires the user’s SIP URI to match the domain of the Front End pool designated for automatic configuration.</span></span> <span data-ttu-id="1e2ae-190">這也是舊版 Communicator 的情況。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-190">This was also the case with earlier versions of Communicator.</span></span>

<span data-ttu-id="1e2ae-191">例如，如果您有兩個 SIP 網域在使用中，則需要下列 DNS 服務（SRV）記錄：</span><span class="sxs-lookup"><span data-stu-id="1e2ae-191">For example, if you have two SIP domains in use, the following DNS service (SRV) records would be required:</span></span>

  - <span data-ttu-id="1e2ae-192">如果使用者登入 bob@contoso.com，下列 SRV 記錄將可用於自動設定，因為使用者的 SIP 網域（contoso.com）與自動設定前端池的網域相符。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-192">If a user signs in as bob@contoso.com the following SRV record will work for automatic configuration because the user’s SIP domain (contoso.com) matches the domain of automatic configuration Front End pool):</span></span>
    
     <span data-ttu-id="1e2ae-193">\_sipinternaltls.\_tcp.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-193">\_sipinternaltls.\_tcp.contoso.com.</span></span> <span data-ttu-id="1e2ae-194">在 SRV 0 0 5061 pool01.contoso.com 中的86400</span><span class="sxs-lookup"><span data-stu-id="1e2ae-194">86400 IN SRV 0 0 5061 pool01.contoso.com</span></span>

  - <span data-ttu-id="1e2ae-195">如果使用者登入 alice@fabrikam.com，下列 DNS SRV 記錄將可在第二個 SIP 網域自動設定時運作。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-195">If a user signs in as alice@fabrikam.com the following DNS SRV record will work for automatic configuration of the second SIP domain.</span></span>
    
     <span data-ttu-id="1e2ae-196">\_sipinternaltls.\_tcp.fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-196">\_sipinternaltls.\_tcp.fabrikam.com.</span></span> <span data-ttu-id="1e2ae-197">在 SRV 0 0 5061 pool01.fabrikam.com 中的86400</span><span class="sxs-lookup"><span data-stu-id="1e2ae-197">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="1e2ae-198">若要進行比較，如果使用者登入 tim@litwareinc.com，下列 DNS SRV 記錄將無法自動設定，因為用戶端的 SIP 網域（litwareinc.com）與池所在的網域（fabrikam.com）不相符。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-198">For comparison, if a user signs in as tim@litwareinc.com the following DNS SRV record will not work for automatic configuration, because the client’s SIP domain (litwareinc.com) does not match the domain that the pool is in (fabrikam.com):</span></span>

 <span data-ttu-id="1e2ae-199">\_sipinternaltls.\_tcp.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-199">\_sipinternaltls.\_tcp.litwareinc.com.</span></span> <span data-ttu-id="1e2ae-200">在 SRV 0 0 5061 pool01.fabrikam.com 中的86400</span><span class="sxs-lookup"><span data-stu-id="1e2ae-200">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="1e2ae-201">如果執行 Lync 的用戶端需要自動設定，請選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="1e2ae-201">If automatic configuration is required for clients running Lync, select one of the following options:</span></span>

  - <span data-ttu-id="1e2ae-202">**[群組原則物件**   ] 使用群組原則物件（gpo）來填入正確的伺服器值。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-202">**Group Policy Objects**   Use Group Policy objects (GPOs) to populate the correct server values.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1e2ae-203">這個選項不會啟用自動設定，但會自動進行手動設定的程式，因此，如果使用這個方法，就不需要與自動設定相關聯的 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-203">This option does not enable automatic configuration, but it does automate the process of manual configuration, so if this approach is used, the SRV records associated with automatic configuration are not required.</span></span>

    
    </div>

  - <span data-ttu-id="1e2ae-204">**[相符內部區域**   ]：在內部 dns 中建立與外部 DNS 區域相符的區域（例如，contoso.com），並建立 DNS a 和 AAAA （如果您使用的是 IPv6 定址）與自動設定使用的 Lync Server 2013 池相對應的記錄。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-204">**Matching internal zone**   Create a zone in the internal DNS that matches the external DNS zone (for example, contoso.com) and create DNS A and AAAA (if you are using IPv6 addressing) records corresponding to the Lync Server 2013 pool used for automatic configuration.</span></span> <span data-ttu-id="1e2ae-205">例如，如果使用者是駐留在 pool01.contoso.net 上，但登入 Lync 作為 bob@contoso.com，請建立一個名為 contoso.com 的內部 DNS 區域，並在其中加入，建立一個 DNS A 和 AAAA （如果使用 IPv6 定址）記錄 pool01.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-205">For example, if a user is homed on pool01.contoso.net but signs into Lync as bob@contoso.com, create an internal DNS zone called contoso.com and inside it, create a DNS A and AAAA (if IPv6 addressing is used) record for pool01.contoso.com.</span></span>

  - <span data-ttu-id="1e2ae-206">**固定指標內部區域**   如果您在內部 DNS 中建立整個區域不是選項，您可以建立與自動設定所需的 SRV 記錄相對應的 pin 點（即專用）區域，並使用 dnscmd 填入這些區域。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-206">**Pin-point internal zone**   If you are creating an entire zone in the internal DNS is not an option, you can create pin-point (that is, dedicated) zones that correspond to the SRV records that are required for automatic configuration, and populate those zones using dnscmd.exe.</span></span> <span data-ttu-id="1e2ae-207">Dnscmd .exe 是必要的，因為 DNS 使用者介面不支援建立 pin 點區域。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-207">Dnscmd.exe is required because the DNS user interface does not support creation of pin-point zones.</span></span> <span data-ttu-id="1e2ae-208">例如，如果 SIP 網域是 contoso.com，而且您有一個名為 pool01 的前端池（其中包含兩個前端伺服器），則您必須在內部 DNS 中有下列 pin 點區域和記錄：</span><span class="sxs-lookup"><span data-stu-id="1e2ae-208">For example, if the SIP domain is contoso.com and you have a Front End pool called pool01 that contains two Front End Servers, you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    <span data-ttu-id="1e2ae-209">如果您的環境包含第二個 SIP 網域（例如，fabrikam.com），則您必須在內部 DNS 中有下列 pin 點區域和記錄：</span><span class="sxs-lookup"><span data-stu-id="1e2ae-209">If your environment contains a second SIP domain (for example, fabrikam.com), you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> <span data-ttu-id="1e2ae-210">前端池 FQDN 會出現兩次，但有兩個不同的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-210">The Front End pool FQDN appears twice, but with two different IP addresses.</span></span> <span data-ttu-id="1e2ae-211">這是因為使用了 DNS 負載平衡，但如果使用硬體負載平衡，就只有單一前端池專案。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-211">This is because DNS load balancing is used, but if hardware load balancing is used, there would be only a single Front End pool entry.</span></span> <span data-ttu-id="1e2ae-212">此外，contoso.com 範例與 fabrikam.com 範例之間的前端池 FQDN 值會變更，但 IP 位址會保持不變。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-212">Also, the Front End pool FQDN values change between the contoso.com example and the fabrikam.com example, but the IP addresses remain the same.</span></span> <span data-ttu-id="1e2ae-213">這是因為使用者從任一 SIP 網域登入，請使用相同的 [前端] 池來自動進行設定。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-213">This is because users signing in from either SIP domain, use the same Front End pool for automatic configuration.</span></span>



</div>

<span data-ttu-id="1e2ae-214">如需詳細資訊，請參閱 DMTF 博客文章：「Communicator 自動設定和分割大腦 DNS」 [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707)。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-214">For details, see the DMTF blog article, "Communicator Automatic Configuration and Split-Brain DNS," at [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1e2ae-215">每個博客及其 URL 的內容可能會變更，恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-215">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a><span data-ttu-id="1e2ae-216">針對災害復原設定網域名稱系統（DNS）</span><span class="sxs-lookup"><span data-stu-id="1e2ae-216">Configuring the domain name system (DNS) for Disaster Recovery</span></span>

<span data-ttu-id="1e2ae-217">若要設定 DNS 將 Lync Server 2013 Web 流量重新導向到災害復原與容錯移轉網站，您必須使用支援 GeoDNS 的 DNS 提供者。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-217">To configure DNS to redirect Lync Server 2013 Web traffic to your disaster recovery and failover sites, you must be using a DNS provider that supports GeoDNS.</span></span> <span data-ttu-id="1e2ae-218">您可以設定 Web 的 DNS 記錄以支援災害復原，因此即使一個完整的前端池已關閉，使用 Web 服務的功能仍會繼續。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-218">You can set up your DNS records for Web to support disaster recovery, so that features that use Web services continue even if one entire Front End pool goes down.</span></span> <span data-ttu-id="1e2ae-219">這個災害復原功能支援自動探索（Lyncdiscover URL）、符合和撥入簡單的 Url。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-219">This disaster recovery feature supports the Autodiscover (Lyncdiscover URL), Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="1e2ae-220">您可以在 GeoDNS 提供者處，定義及設定其他 DNS 主機（A 和 AAAA （如果使用 IPv6 的話），以進行內部和外部的 Web 服務解析。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-220">You define and configure additional DNS host (A and AAAA if using IPv6) records for internal and external resolution of Web services at your GeoDNS provider.</span></span> <span data-ttu-id="1e2ae-221">下列詳細資料假設您的提供者已將成對的 pool、地理位置與 GeoDNS 支援，或者將其設定為使用 Pool1 作為主要版本，並在發生通訊遺失或硬體故障時容錯移轉到 Pool2。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-221">The following details assume paired pools, geographically dispersed, and GeoDNS supported by your provider with either round-robin DNS, or configured to use Pool1 as primary, and fail over to Pool2 in the event of communications loss or hardware failure.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1e2ae-222">GeoDNS 記錄（範例）</span><span class="sxs-lookup"><span data-stu-id="1e2ae-222">GeoDNS record (example)</span></span></th>
<th><span data-ttu-id="1e2ae-223">資源庫記錄（範例）</span><span class="sxs-lookup"><span data-stu-id="1e2ae-223">Pool records (example)</span></span></th>
<th><span data-ttu-id="1e2ae-224">CNAME 記錄（範例）</span><span class="sxs-lookup"><span data-stu-id="1e2ae-224">CNAME records (example)</span></span></th>
<th><span data-ttu-id="1e2ae-225">DNS 設定（選取一個選項）</span><span class="sxs-lookup"><span data-stu-id="1e2ae-225">DNS settings (select one option)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e2ae-226">Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-226">Meet-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1e2ae-227">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-227">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1e2ae-228">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-228">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1e2ae-229">Meet.contoso.com 別名至 Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-229">Meet.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1e2ae-230">Meet.contoso.com 別名至 Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-230">Meet.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1e2ae-231">在池之間進行迴圈複用</span><span class="sxs-lookup"><span data-stu-id="1e2ae-231">Round Robin between pools</span></span></p>
<p><span data-ttu-id="1e2ae-232">如果失敗，請使用 [主要]，連線到副</span><span class="sxs-lookup"><span data-stu-id="1e2ae-232">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e2ae-233">Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-233">Meet-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1e2ae-234">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-234">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1e2ae-235">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-235">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1e2ae-236">Meet.contoso.com 別名至 Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-236">Meet.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1e2ae-237">Meet.contoso.com 別名至 Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-237">Meet.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1e2ae-238">在池之間進行迴圈複用</span><span class="sxs-lookup"><span data-stu-id="1e2ae-238">Round Robin between pools</span></span></p>
<p><span data-ttu-id="1e2ae-239">如果失敗，請使用 [主要]，連線到副</span><span class="sxs-lookup"><span data-stu-id="1e2ae-239">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e2ae-240">Dialin-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-240">Dialin-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1e2ae-241">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-241">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1e2ae-242">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-242">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1e2ae-243">Dialin.contoso.com 別名至 Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-243">Dialin.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1e2ae-244">Dialin.contoso.com 別名至 Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-244">Dialin.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1e2ae-245">在池之間進行迴圈複用</span><span class="sxs-lookup"><span data-stu-id="1e2ae-245">Round Robin between pools</span></span></p>
<p><span data-ttu-id="1e2ae-246">如果失敗，請使用 [主要]，連線到副</span><span class="sxs-lookup"><span data-stu-id="1e2ae-246">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e2ae-247">Dialin-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-247">Dialin-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1e2ae-248">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-248">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1e2ae-249">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-249">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1e2ae-250">Dialin.contoso.com 別名至 Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-250">Dialin.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1e2ae-251">Dialin.contoso.com 別名至 Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-251">Dialin.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1e2ae-252">在池之間進行迴圈複用</span><span class="sxs-lookup"><span data-stu-id="1e2ae-252">Round Robin between pools</span></span></p>
<p><span data-ttu-id="1e2ae-253">如果失敗，請使用 [主要]，連線到副</span><span class="sxs-lookup"><span data-stu-id="1e2ae-253">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e2ae-254">Lyncdiscoverint-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-254">Lyncdiscoverint-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1e2ae-255">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-255">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1e2ae-256">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-256">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1e2ae-257">Lyncdiscoverinternal.contoso.com 別名至 Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-257">Lyncdiscoverinternal.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1e2ae-258">Lyncdiscoverinternal.contoso.com 別名至 Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-258">Lyncdiscoverinternal.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1e2ae-259">在池之間進行迴圈複用</span><span class="sxs-lookup"><span data-stu-id="1e2ae-259">Round Robin between pools</span></span></p>
<p><span data-ttu-id="1e2ae-260">如果失敗，請使用 [主要]，連線到副</span><span class="sxs-lookup"><span data-stu-id="1e2ae-260">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e2ae-261">Lyncdiscover-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-261">Lyncdiscover-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1e2ae-262">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-262">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1e2ae-263">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-263">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1e2ae-264">Lyncdiscover.contoso.com 別名至 Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-264">Lyncdiscover.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1e2ae-265">Lyncdiscover.contoso.com 別名至 Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-265">Lyncdiscover.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1e2ae-266">在池之間進行迴圈複用</span><span class="sxs-lookup"><span data-stu-id="1e2ae-266">Round Robin between pools</span></span></p>
<p><span data-ttu-id="1e2ae-267">如果失敗，請使用 [主要]，連線到副</span><span class="sxs-lookup"><span data-stu-id="1e2ae-267">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e2ae-268">Scheduler-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-268">Scheduler-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1e2ae-269">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-269">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1e2ae-270">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-270">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1e2ae-271">Scheduler.contoso.com 別名至 Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-271">Scheduler.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1e2ae-272">Scheduler.contoso.com 別名至 Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-272">Scheduler.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1e2ae-273">在池之間進行迴圈複用</span><span class="sxs-lookup"><span data-stu-id="1e2ae-273">Round Robin between pools</span></span></p>
<p><span data-ttu-id="1e2ae-274">如果失敗，請使用 [主要]，連線到副</span><span class="sxs-lookup"><span data-stu-id="1e2ae-274">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e2ae-275">Scheduler-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-275">Scheduler-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1e2ae-276">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-276">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1e2ae-277">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-277">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1e2ae-278">Scheduler.contoso.com 別名至 Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-278">Scheduler.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="1e2ae-279">Scheduler.contoso.com 別名至 Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1e2ae-279">Scheduler.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1e2ae-280">在池之間進行迴圈複用</span><span class="sxs-lookup"><span data-stu-id="1e2ae-280">Round Robin between pools</span></span></p>
<p><span data-ttu-id="1e2ae-281">如果失敗，請使用 [主要]，連線到副</span><span class="sxs-lookup"><span data-stu-id="1e2ae-281">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a><span data-ttu-id="1e2ae-282">DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="1e2ae-282">DNS Load Balancing</span></span>

<span data-ttu-id="1e2ae-283">DNS 負載平衡通常是在應用程式層級實現。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-283">DNS load balancing is typically implemented at the application level.</span></span> <span data-ttu-id="1e2ae-284">應用程式（例如，執行 Lync 的用戶端），連線到池完整功能變數名稱（FQDN）的 [DNS A] 和 [AAAA （如果使用 IPv6 定址）] 記錄查詢中傳回的其中一個 IP 位址，即可嘗試連線到池中的伺服器。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-284">The application (for example, a client running Lync), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="1e2ae-285">例如，如果在名為 pool01.contoso.com 的池中有三個前端伺服器，則會發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="1e2ae-285">For example, if there are three front end servers in a pool named pool01.contoso.com, the following will happen:</span></span>

  - <span data-ttu-id="1e2ae-286">執行 Lync 查詢 DNS pool01.contoso.com 的用戶端。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-286">Clients running Lync query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="1e2ae-287">查詢會傳回三個 IP 位址，並以下列方式將它們加以緩存（不一定依順序）：</span><span class="sxs-lookup"><span data-stu-id="1e2ae-287">The query returns three IP addresses and caches them as follows (not necessarily in this order):</span></span>
    
    <span data-ttu-id="1e2ae-288">pool01.contoso.com 192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="1e2ae-288">pool01.contoso.com      192.168.10.90</span></span>
    
    <span data-ttu-id="1e2ae-289">pool01.contoso.com 192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="1e2ae-289">pool01.contoso.com      192.168.10.91</span></span>
    
    <span data-ttu-id="1e2ae-290">pool01.contoso.com 192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="1e2ae-290">pool01.contoso.com      192.168.10.92</span></span>

  - <span data-ttu-id="1e2ae-291">用戶端會嘗試建立與其中一個 IP 位址的傳輸控制通訊協定（TCP）連線。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-291">The client attempts to establish a Transmission Control Protocol (TCP) connection to one of the IP addresses.</span></span> <span data-ttu-id="1e2ae-292">如果失敗，用戶端會嘗試在快取中的下一個 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-292">If that fails, the client tries the next IP address in the cache.</span></span>

  - <span data-ttu-id="1e2ae-293">如果 TCP 連線成功，用戶端會協商 TLS，連線到 pool01.contoso.com 上的主要註冊機構。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-293">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>

  - <span data-ttu-id="1e2ae-294">如果用戶端在未成功連線的情況下嘗試所有快取的專案，系統會通知使用者目前沒有任何執行 Lync Server 2013 的伺服器可供使用。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-294">If the client tries all cached entries without a successful connection, the user is notified that no servers running Lync Server 2013 are available at the moment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1e2ae-295">以 dns 為基礎的負載平衡不同于 DNS 迴圈（DNS RR），主要是依靠 DNS 來提供負載平衡，以提供與池中伺服器相對應的 IP 位址的不同順序。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-295">DNS-based load balancing is different from DNS round robin (DNS RR) which typically refers to load balancing by relying on DNS to provide a different order of IP addresses corresponding to the servers in a pool.</span></span> <span data-ttu-id="1e2ae-296">通常 DNS RR 只會啟用負載分配，但不會啟用容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-296">Typically DNS RR only enables load distribution, but does not enable failover.</span></span> <span data-ttu-id="1e2ae-297">例如，如果連線到 DNS A 和 AAAA 傳回的一個 IP 位址（如果您使用的是 IPv6 定址）查詢失敗，連線就會失敗。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-297">For example, if the connection to the one IP address returned by the DNS A and AAAA (if you are using IPv6 addressing) query fails, the connection fails.</span></span> <span data-ttu-id="1e2ae-298">因此，DNS 迴圈方式本身的可靠性低於 DNS 的負載平衡。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-298">Therefore, DNS round robin by itself is less reliable than DNS-based load balancing.</span></span> <span data-ttu-id="1e2ae-299">您可以將 DNS 迴圈與 DNS 負載平衡搭配使用。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-299">You can use DNS round robin in conjunction with DNS load balancing.</span></span>



</div>

<span data-ttu-id="1e2ae-300">DNS 負載平衡用於下列用途：</span><span class="sxs-lookup"><span data-stu-id="1e2ae-300">DNS load balancing is used for the following:</span></span>

  - <span data-ttu-id="1e2ae-301">將伺服器間 SIP 負載平衡到邊緣伺服器</span><span class="sxs-lookup"><span data-stu-id="1e2ae-301">Load balancing server-to-server SIP to the Edge Servers</span></span>

  - <span data-ttu-id="1e2ae-302">[負載平衡] 應用程式服務（UCAS）應用程式（例如會議自動語音應答、回應群組及通話駐留）</span><span class="sxs-lookup"><span data-stu-id="1e2ae-302">Load balancing Unified Communications Application Services (UCAS) applications such as Conferencing Auto Attendant, Response Group, and Call Park</span></span>

  - <span data-ttu-id="1e2ae-303">防止新連線至 UCAS 的應用程式（也稱為 "排出"）</span><span class="sxs-lookup"><span data-stu-id="1e2ae-303">Preventing new connections to UCAS applications (also known as "draining")</span></span>

  - <span data-ttu-id="1e2ae-304">負載平衡用戶端與邊緣伺服器之間的所有用戶端與伺服器流量</span><span class="sxs-lookup"><span data-stu-id="1e2ae-304">Load balancing all client-to-server traffic between clients and Edge Servers</span></span>

<span data-ttu-id="1e2ae-305">DNS 負載平衡無法用於下列專案：</span><span class="sxs-lookup"><span data-stu-id="1e2ae-305">DNS load balancing cannot be used for the following:</span></span>

  - <span data-ttu-id="1e2ae-306">從用戶端到伺服器的 web 流量到控制器或前端伺服器</span><span class="sxs-lookup"><span data-stu-id="1e2ae-306">Client-to-server web traffic to Director or Front End Servers</span></span>

<span data-ttu-id="1e2ae-307">DNS 負載平衡與同盟流量：</span><span class="sxs-lookup"><span data-stu-id="1e2ae-307">DNS load balancing and federated traffic:</span></span>

<span data-ttu-id="1e2ae-308">如果 DNS SRV 查詢傳回多個 DNS 記錄，存取邊緣服務將會使用最小的數值優先順序和最高的數位權重來挑選 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-308">If multiple DNS records are returned by a DNS SRV query, the Access Edge service always picks the DNS SRV record with the lowest numeric priority and highest numeric weight.</span></span> <span data-ttu-id="1e2ae-309">網際網路工程工作強制檔「用於指定服務位置的 DNS RR （DNS SRV）」指定是否已<http://www.ietf.org/rfc/rfc2782.txt>定義多個 DNS srv 記錄、首先使用優先順序，然後再使用 [粗細]。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-309">The Internet Engineering Task Force document “A DNS RR for specifying the location of services (DNS SRV)” <http://www.ietf.org/rfc/rfc2782.txt> specifies that if there are multiple DNS SRV records defined, priority is first used, then weight.</span></span> <span data-ttu-id="1e2ae-310">例如，DNS SRV 記錄 A 的粗細為20，且優先順序為40，而 DNS SRV 記錄 B 的權重為10且優先順序為50。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-310">For example DNS SRV record A has a weight of 20 and a priority of 40 and DNS SRV record B has a weight of 10 and priority of 50.</span></span> <span data-ttu-id="1e2ae-311">將會選取具有優先順序40的 DNS SRV 記錄 A。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-311">DNS SRV record A with priority 40 will be selected.</span></span> <span data-ttu-id="1e2ae-312">下列規則適用于 DNS SRV 記錄選擇：</span><span class="sxs-lookup"><span data-stu-id="1e2ae-312">The following rules apply to DNS SRV record selection:</span></span>

  - <span data-ttu-id="1e2ae-313">首先考慮優先順序。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-313">Priority is considered first.</span></span> <span data-ttu-id="1e2ae-314">用戶端必須嘗試與 DNS SRV 記錄所定義的目標主機取得其所能達到的最低優先順序。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-314">A client MUST attempt to contact the target host defined by the DNS SRV record with the lowest numbered priority it can reach.</span></span> <span data-ttu-id="1e2ae-315">必須按照權欄位所定義的順序來嘗試使用相同優先順序的目標。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-315">Targets with the same priority SHOULD be tried in an order defined by the weight field.</span></span>

  - <span data-ttu-id="1e2ae-316">[體重] 欄位指定具有相同優先順序之專案的相對權重。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-316">The weight field specifies a relative weight for entries with the same priority.</span></span> <span data-ttu-id="1e2ae-317">應將較大的粗細指定成按比例較高的選取幾率。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-317">Larger weights SHOULD be given a proportionately higher probability of being selected.</span></span> <span data-ttu-id="1e2ae-318">如果沒有任何伺服器可供您選擇，DNS 管理員就應該使用權重0。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-318">DNS administrators SHOULD use Weight 0 when there isn’t any server selection to do.</span></span> <span data-ttu-id="1e2ae-319">如果記錄中包含的權重大於0，則權重為0的記錄應該有很小的選取機會。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-319">In the presence of records containing weights greater than 0, records with weight 0 should have a very small chance of being selected.</span></span>

<span data-ttu-id="1e2ae-320">如果傳回多個具有相同優先順序和寬度的 DNS SRV 記錄，則 Access Edge 服務會選取首先從 DNS 伺服器接收的 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="1e2ae-320">If multiple DNS SRV records with equal priority and weight are returned, the Access Edge service will select the SRV record that was received first from the DNS server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

