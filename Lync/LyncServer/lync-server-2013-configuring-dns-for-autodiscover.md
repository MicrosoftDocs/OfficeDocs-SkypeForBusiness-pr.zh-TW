---
title: Lync Server 2013： 設定 DNS 自動探索
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring DNS for Autodiscover
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945656(v=OCS.15)
ms:contentKeyID: 51541528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70aa869c353e0acba0d526823f7624334b445767
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="9e832-102">Lync Server 2013 中的自動探索設定 DNS</span><span class="sxs-lookup"><span data-stu-id="9e832-102">Configuring DNS for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e832-103">_**主題上次修改日期：** 2012年-12-12_</span><span class="sxs-lookup"><span data-stu-id="9e832-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="9e832-104">若要支援 Lync 用戶端自動探索，您需要建立下列網域名稱系統 (DNS) 記錄：</span><span class="sxs-lookup"><span data-stu-id="9e832-104">To support autodiscovery for Lync clients, you need to create the following Domain Name System (DNS) records:</span></span>

  - <span data-ttu-id="9e832-105">內部 DNS 記錄，以支援 Lync 用戶端連線從貴組織的網路</span><span class="sxs-lookup"><span data-stu-id="9e832-105">An internal DNS record to support Lync clients who connect from within your organization's network</span></span>

  - <span data-ttu-id="9e832-106">外部或公用 DNS 記錄，以支援 Lync 用戶端從網際網路連線</span><span class="sxs-lookup"><span data-stu-id="9e832-106">An external, or public, DNS record to support Lync clients who connect from the Internet</span></span>

<span data-ttu-id="9e832-107">您必須為每個 SIP 網域建立內部 DNS 記錄及外部 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="9e832-107">You must create an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="9e832-108">DNS 記錄可以是其中一個 A （主機） 記錄或 CNAME 記錄，根據您建立新的憑證與其他主體替代名稱 (SAN) 的能力。</span><span class="sxs-lookup"><span data-stu-id="9e832-108">The DNS records can be either A (host) records or CNAME records, based on your ability to create new certificates with the additional subject alternate name (SAN).</span></span> <span data-ttu-id="9e832-109">如果您不可以要求並部署 lyncdiscover 與新的外部 （公用） 憑證。\<網域名稱\>SAN (英文），使用此程序使用 HTTP/TCP 連接埠 80。</span><span class="sxs-lookup"><span data-stu-id="9e832-109">If you are not able to request and deploy a new external (public) certificate with the lyncdiscover.\<domain name\> SAN, use the procedure for using HTTP/TCP port 80.</span></span> <span data-ttu-id="9e832-110">下列程序說明如何建立內部及外部 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="9e832-110">The following procedures describe how to create internal and external DNS records.</span></span>

<div>

## <a name="to-create-dns-cname-records"></a><span data-ttu-id="9e832-111">建立 DNS CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="9e832-111">To create DNS CNAME records</span></span>

1.  <span data-ttu-id="9e832-112">登入 DNS 伺服器，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9e832-112">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="9e832-113">若要建立內部 DNS 記錄，請以 Domain Admins 群組成員身分或 DnsAdmins 群組成員身分，登入您網路中的 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="9e832-113">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="9e832-114">若要建立外部 DNS 記錄，請連線至公用 DNS 提供者。</span><span class="sxs-lookup"><span data-stu-id="9e832-114">To create an external DNS record, connect to your public DNS provider.</span></span>

2.  <span data-ttu-id="9e832-115">開啟 DNS 系統管理嵌入式管理單元：依序按一下 [開始]\*\*\*\*、[系統管理工具]\*\*\*\* 和 [DNS]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9e832-115">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="9e832-116">執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="9e832-116">Do one of the following:</span></span>
    
      - <span data-ttu-id="9e832-117">針對內部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 Active Directory 網域 (例如 contoso.local) 的 [正向對應區域]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9e832-117">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="9e832-118">此網域是 Active Directory 網域，您的 Lync Server 2013&nbsp;安裝 Director 集區與前端集區。</span><span class="sxs-lookup"><span data-stu-id="9e832-118">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="9e832-119">針對外部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 SIP 網域 (例如 contoso.com) 的 [正向對應區域]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9e832-119">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="9e832-120">確認主機 A 記錄存在，您的 Director 集區，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9e832-120">Verify that a host A record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="9e832-121">針對內部 DNS 記錄，主機 A 記錄應該存在的內部 Web 服務完整的網域名稱 (FQDN) Director 集區 (例如 lyncwebdir01.contoso.local)。</span><span class="sxs-lookup"><span data-stu-id="9e832-121">For an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="9e832-122">針對外部 DNS 記錄，您的 Director 集區 (例如 lyncwebextdir.contoso.com) 的外部 web 服務 FQDN 應有存在的主機 A 記錄。</span><span class="sxs-lookup"><span data-stu-id="9e832-122">For an external DNS record, a host A record should exist for the external web services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="9e832-123">確認主機 A 記錄存在，您的前端集區，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9e832-123">Verify that a host A record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="9e832-124">針對內部 DNS 記錄，您的前端集區 (例如 lyncwebpool01.contoso.local) 的內部 Web 服務 fqdn 應有存在主機 A 記錄。</span><span class="sxs-lookup"><span data-stu-id="9e832-124">For an internal DNS record, a host A record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="9e832-125">針對外部 DNS 記錄，您的前端集區 (例如 lyncwebextpool01.contoso.com) 的外部 Web 服務 fqdn 應有存在主機 A 記錄。</span><span class="sxs-lookup"><span data-stu-id="9e832-125">For an external DNS record, a host A record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="9e832-126">針對內部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 SIP 網域 (例如 contoso.com) 的 [正向對應區域]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9e832-126">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9e832-127">如果您要建立外部 DNS 記錄，從步驟 3 就已展開 SIP 網域的 [正向對應區域]<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="9e832-127">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="9e832-128">用滑鼠右鍵按一下 SIP 網域名稱，然後按一下 [新增別名 (CNAME)]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9e832-128">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="9e832-129">在 [別名]\*\*\*\* 中，輸入下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="9e832-129">In **Alias name**, type one of the following:</span></span>
    
      - <span data-ttu-id="9e832-130">針對內部 DNS 記錄，輸入 lyncdiscoverinternal 作為內部自動探索服務 URL 的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="9e832-130">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="9e832-131">針對外部 DNS 記錄，輸入 lyncdiscover 作為外部自動探索服務 URL 的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="9e832-131">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="9e832-132">在 [目標主機完整網域名稱 (FQDN)]\*\*\*\* 中，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="9e832-132">In **Fully qualified domain name (FQDN) for target host**, do one of the following:</span></span>
    
      - <span data-ttu-id="9e832-133">針對內部 DNS 記錄，輸入或瀏覽至您的 Director 集區 (例如 lyncwebdir01.contoso.local)，內部 Web 服務 FQDN，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="9e832-133">For an internal DNS record, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local), and then click **OK**.</span></span>
    
      - <span data-ttu-id="9e832-134">針對外部 DNS 記錄，輸入或瀏覽至您的 Director 集區 (例如 lyncwebextdir.contoso.com)，外部 Web 服務 FQDN，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="9e832-134">For an external DNS record, type or browse to the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9e832-135">如果您不使用 Director，使用內部和外部 Web 服務 FQDN 的前端集區或單一伺服器的前端伺服器或 Standard Edition server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="9e832-135">If you do not use a Director, use the internal and external Web Services FQDN for the Front End pool, or, for a single server, the FQDN for the Front End Server or Standard Edition server.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9e832-136">您必須在您支援 Lync Server 2013 環境中的每個 SIP 網域的正向對應區域中建立新的自動探索 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="9e832-136">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a><span data-ttu-id="9e832-137">建立 DNS A 記錄</span><span class="sxs-lookup"><span data-stu-id="9e832-137">To create DNS A records</span></span>

1.  <span data-ttu-id="9e832-138">登入 DNS 伺服器，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9e832-138">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="9e832-139">若要建立內部 DNS 記錄，請以 Domain Admins 群組成員身分或 DnsAdmins 群組成員身分，登入您網路中的 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="9e832-139">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="9e832-140">若要建立外部 DNS 記錄，連線至您的公用 DNS 提供者或外部 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="9e832-140">To create an external DNS record, connect to your public DNS provider or external DNS server.</span></span>

2.  <span data-ttu-id="9e832-141">開啟 DNS 系統管理嵌入式管理單元：依序按一下 [開始]\*\*\*\*、[系統管理工具]\*\*\*\* 和 [DNS]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9e832-141">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="9e832-142">執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="9e832-142">Do one of the following:</span></span>
    
      - <span data-ttu-id="9e832-143">針對內部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 Active Directory 網域 (例如 contoso.local) 的 [正向對應區域]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9e832-143">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="9e832-144">此網域是 Active Directory 網域，您的 Lync Server 2013&nbsp;安裝 Director 集區與前端集區。</span><span class="sxs-lookup"><span data-stu-id="9e832-144">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="9e832-145">針對外部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 SIP 網域 (例如 contoso.com) 的 [正向對應區域]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9e832-145">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="9e832-146">確認主機 A （對於 IPv6 為 AAAA) 記錄存在，您的 Director 集區，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9e832-146">Verify that a host A (for IPv6, AAAA) record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="9e832-147">針對內部 DNS 記錄，您的 Director 集區 (例如 lyncwebdir01.contoso.local) 的內部 Web 服務 fqdn 應有存在主機 A （對於 IPv6 為 AAAA) 記錄。</span><span class="sxs-lookup"><span data-stu-id="9e832-147">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="9e832-148">針對外部 DNS 記錄，您的 Director 集區 (例如 lyncwebextdir.contoso.com) 的外部 Web 服務 fqdn 應有存在主機 A （對於 IPv6 為 AAAA) 記錄。</span><span class="sxs-lookup"><span data-stu-id="9e832-148">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="9e832-149">確認主機 A （對於 IPv6 為 AAAA) 記錄存在，您的前端集區，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9e832-149">Verify that a host A (for IPv6, AAAA) record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="9e832-150">針對內部 DNS 記錄，您的前端集區 (例如 lyncwebpool01.contoso.local) 的內部 Web 服務 fqdn 應有存在主機 A （對於 IPv6 為 AAAA) 記錄。</span><span class="sxs-lookup"><span data-stu-id="9e832-150">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="9e832-151">針對外部 DNS 記錄，您的前端集區 (例如 lyncwebextpool01.contoso.com) 的外部 Web 服務 fqdn 應有存在主機 A （對於 IPv6 為 AAAA) 記錄。</span><span class="sxs-lookup"><span data-stu-id="9e832-151">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="9e832-152">針對內部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 SIP 網域 (例如 contoso.com) 的 [正向對應區域]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9e832-152">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9e832-153">如果您要建立外部 DNS 記錄，從步驟 3 就已展開 SIP 網域的 [正向對應區域]<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="9e832-153">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="9e832-154">用滑鼠右鍵按一下 SIP 網域名稱，然後按一下 [新增主機 (A 或 AAAA)]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9e832-154">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="9e832-155">在 [名稱]\*\*\*\* 中輸入主機名稱，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9e832-155">In **Name**, type the host name as follows:</span></span>
    
      - <span data-ttu-id="9e832-156">針對內部 DNS 記錄，輸入 lyncdiscoverinternal 作為內部自動探索服務 URL 的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="9e832-156">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="9e832-157">針對外部 DNS 記錄，輸入 lyncdiscover 作為外部自動探索服務 URL 的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="9e832-157">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9e832-158">網域名稱是從定義記錄所在的區域取得，因此，不需要當作 A 記錄的一部分來輸入。</span><span class="sxs-lookup"><span data-stu-id="9e832-158">The domain name is assumed from the zone in which the record is defined and, therefore, does not need to be entered as part of the A record.</span></span>

    
    </div>

9.  <span data-ttu-id="9e832-159">在 [IP 位址]\*\*\*\* 中輸入 IP 位址，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9e832-159">In **IP Address**, type the IP address as follows:</span></span>
    
      - <span data-ttu-id="9e832-160">針對內部 DNS 記錄，輸入 Director 的內部 Web 服務 IP 位址 （或者，如果您使用負載平衡器，請輸入虛擬 IP (VIP) Director 負載平衡器）。</span><span class="sxs-lookup"><span data-stu-id="9e832-160">For an internal DNS record, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="9e832-161">如果您不使用 Director、 輸入 IP 位址的前端伺服器或 Standard Edition server，或，如果您使用負載平衡器中，輸入前端集區負載平衡器的 VIP。</span><span class="sxs-lookup"><span data-stu-id="9e832-161">If you do not use a Director, type the IP address of the Front End Server or Standard Edition server, or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

        
        </div>
    
      - <span data-ttu-id="9e832-162">針對外部 DNS 記錄，輸入反向 Proxy 的外部或公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="9e832-162">For an external DNS record, type the external or public IP address of the reverse proxy.</span></span>

10. <span data-ttu-id="9e832-163">按一下 [新增主機]\*\*\*\*，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9e832-163">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="9e832-164">如果要建立其他 A 記錄，請重複步驟 8 到 10。</span><span class="sxs-lookup"><span data-stu-id="9e832-164">To create an additional A record, repeat steps 8 through 10.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9e832-165">您必須在您支援 Lync Server 2013 環境中的每個 SIP 網域的正向對應區域中建立新的 lyncdiscover 和 lyncdiscoverinternal A 記錄。</span><span class="sxs-lookup"><span data-stu-id="9e832-165">You must create a new lyncdiscover and lyncdiscoverinternal A records in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

12. <span data-ttu-id="9e832-166">完成建立 A (對於 IPv6 為 AAAA) 記錄時，按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9e832-166">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

