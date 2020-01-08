---
title: Lync Server 2013：針對自動探索設定 DNS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring DNS for Autodiscover
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945656(v=OCS.15)
ms:contentKeyID: 51541528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c490cac475f3b9a9c8038636f4ac7f6670f22637
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="a014b-102">在 Lync Server 2013 中針對自動探索設定 DNS</span><span class="sxs-lookup"><span data-stu-id="a014b-102">Configuring DNS for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a014b-103">_**主題上次修改日期：** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="a014b-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="a014b-104">若要支援 Lync 用戶端的自動探索，您需要建立下列網域名稱系統（DNS）記錄：</span><span class="sxs-lookup"><span data-stu-id="a014b-104">To support autodiscovery for Lync clients, you need to create the following Domain Name System (DNS) records:</span></span>

  - <span data-ttu-id="a014b-105">支援從貴組織網路內部連線的 Lync 用戶端的內部 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="a014b-105">An internal DNS record to support Lync clients who connect from within your organization's network</span></span>

  - <span data-ttu-id="a014b-106">支援連線至網際網路的 Lync 用戶端的外部或公用 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="a014b-106">An external, or public, DNS record to support Lync clients who connect from the Internet</span></span>

<span data-ttu-id="a014b-107">您必須為每個 SIP 網域建立內部 DNS 記錄和外部 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="a014b-107">You must create an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="a014b-108">DNS 記錄可以是 [（主機）記錄] 或 [CNAME 記錄]，這是根據您使用其他消費者替換名稱（SAN）建立新憑證的能力而定。</span><span class="sxs-lookup"><span data-stu-id="a014b-108">The DNS records can be either A (host) records or CNAME records, based on your ability to create new certificates with the additional subject alternate name (SAN).</span></span> <span data-ttu-id="a014b-109">如果您無法使用 lyncdiscover 來要求並部署新的外部（公開）憑證。\<網功能變數名稱稱\> SAN 中，請使用 HTTP/TCP 埠80的程式。</span><span class="sxs-lookup"><span data-stu-id="a014b-109">If you are not able to request and deploy a new external (public) certificate with the lyncdiscover.\<domain name\> SAN, use the procedure for using HTTP/TCP port 80.</span></span> <span data-ttu-id="a014b-110">下列程式描述如何建立內部和外部 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="a014b-110">The following procedures describe how to create internal and external DNS records.</span></span>

<div>

## <a name="to-create-dns-cname-records"></a><span data-ttu-id="a014b-111">建立 DNS CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="a014b-111">To create DNS CNAME records</span></span>

1.  <span data-ttu-id="a014b-112">登入 DNS 伺服器，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a014b-112">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="a014b-113">若要建立內部 DNS 記錄，請以網域系統管理員群組或 DnsAdmins 群組成員的身分登入您網路中的 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="a014b-113">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="a014b-114">若要建立外部 DNS 記錄，請連接到您的公用 DNS 提供者。</span><span class="sxs-lookup"><span data-stu-id="a014b-114">To create an external DNS record, connect to your public DNS provider.</span></span>

2.  <span data-ttu-id="a014b-115">開啟 [DNS 管理] 管理單元：按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **dns**]。</span><span class="sxs-lookup"><span data-stu-id="a014b-115">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="a014b-116">請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="a014b-116">Do one of the following:</span></span>
    
      - <span data-ttu-id="a014b-117">如果是內部 DNS 記錄，請在 DNS 伺服器的主控台樹中，展開 Active Directory 網域的 [**正向查閱區域**] （例如，[contoso. local]）。</span><span class="sxs-lookup"><span data-stu-id="a014b-117">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a014b-118">這個網域是您在其中安裝 Lync Server 2013&nbsp;控制器池和前端池的 Active Directory 網域。</span><span class="sxs-lookup"><span data-stu-id="a014b-118">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="a014b-119">針對外部 DNS 記錄，請在 DNS 伺服器的主控台樹中，展開您 SIP 網域的**正向查閱區域**（例如，contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="a014b-119">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="a014b-120">驗證主機 A 記錄是否針對您的主管池而存在，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a014b-120">Verify that a host A record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="a014b-121">對於內部 DNS 記錄，對於內部 Web 服務，您的控制器池必須有一個主機 A 記錄（例如，lyncwebdir01）的主機 A 記錄。</span><span class="sxs-lookup"><span data-stu-id="a014b-121">For an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="a014b-122">對於外部 DNS 記錄，您的控制器池的外部 web 服務 FQDN 應該有一個主機 A 記錄（例如，lyncwebextdir.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="a014b-122">For an external DNS record, a host A record should exist for the external web services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="a014b-123">驗證主機 A 記錄是否存在於您的前臺池，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a014b-123">Verify that a host A record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="a014b-124">如果是內部 DNS 記錄，則主機 A 記錄應該存在於您的前端池（例如，lyncwebpool01）的內部 Web 服務 FQDN 中。</span><span class="sxs-lookup"><span data-stu-id="a014b-124">For an internal DNS record, a host A record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="a014b-125">如果是外部 DNS 記錄，則主機 A 記錄應該存在於您的前端池的外部 Web 服務 FQDN （例如，lyncwebextpool01.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="a014b-125">For an external DNS record, a host A record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="a014b-126">如果是內部 DNS 記錄，請在您的 DNS 伺服器的主控台樹中，展開您 SIP 網域的**正向查閱區域**（例如，contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="a014b-126">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a014b-127">如果您要建立外部 DNS 記錄，您的 SIP 網域已在步驟3中展開 [<STRONG>轉寄查閱區域</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="a014b-127">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="a014b-128">以滑鼠右鍵按一下 SIP 網功能變數名稱稱，然後按一下 **[新增別名（CNAME）**]。</span><span class="sxs-lookup"><span data-stu-id="a014b-128">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="a014b-129">在 [**別名名稱**] 中，輸入下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="a014b-129">In **Alias name**, type one of the following:</span></span>
    
      - <span data-ttu-id="a014b-130">針對內部 DNS 記錄，請輸入 lyncdiscoverinternal 做為內部自動探索服務 URL 的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="a014b-130">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="a014b-131">針對外部 DNS 記錄，請輸入 lyncdiscover 做為外部自動探索服務 URL 的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="a014b-131">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="a014b-132">在 [**目標主機的完整功能變數名稱（FQDN）**] 中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="a014b-132">In **Fully qualified domain name (FQDN) for target host**, do one of the following:</span></span>
    
      - <span data-ttu-id="a014b-133">針對內部 DNS 記錄，請輸入或流覽至您的主管池（例如，lyncwebdir01）的內部 Web 服務 FQDN，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a014b-133">For an internal DNS record, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local), and then click **OK**.</span></span>
    
      - <span data-ttu-id="a014b-134">針對外部 DNS 記錄，請輸入或流覽至主管池的外部 Web 服務 FQDN （例如，lyncwebextdir.contoso.com），然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a014b-134">For an external DNS record, type or browse to the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a014b-135">如果您不是使用 Director，請針對前端池使用內部和外部 Web 服務 FQDN，或針對單一伺服器（前端伺服器或標準版伺服器的 FQDN）。</span><span class="sxs-lookup"><span data-stu-id="a014b-135">If you do not use a Director, use the internal and external Web Services FQDN for the Front End pool, or, for a single server, the FQDN for the Front End Server or Standard Edition server.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a014b-136">您必須在 Lync Server 2013 環境支援的每個 SIP 網域的轉寄查閱區域中建立新的自動探索 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="a014b-136">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a><span data-ttu-id="a014b-137">建立 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="a014b-137">To create DNS A records</span></span>

1.  <span data-ttu-id="a014b-138">登入 DNS 伺服器，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a014b-138">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="a014b-139">若要建立內部 DNS 記錄，請以網域系統管理員群組或 DnsAdmins 群組成員的身分登入您網路中的 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="a014b-139">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="a014b-140">若要建立外部 DNS 記錄，請連接到您的公用 DNS 提供者或外部 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="a014b-140">To create an external DNS record, connect to your public DNS provider or external DNS server.</span></span>

2.  <span data-ttu-id="a014b-141">開啟 [DNS 管理] 管理單元：按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **dns**]。</span><span class="sxs-lookup"><span data-stu-id="a014b-141">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="a014b-142">請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="a014b-142">Do one of the following:</span></span>
    
      - <span data-ttu-id="a014b-143">如果是內部 DNS 記錄，請在 DNS 伺服器的主控台樹中，展開 Active Directory 網域的 [**正向查閱區域**] （例如，[contoso. local]）。</span><span class="sxs-lookup"><span data-stu-id="a014b-143">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a014b-144">這個網域是您在其中安裝 Lync Server 2013&nbsp;控制器池和前端池的 Active Directory 網域。</span><span class="sxs-lookup"><span data-stu-id="a014b-144">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="a014b-145">針對外部 DNS 記錄，請在 DNS 伺服器的主控台樹中，展開您 SIP 網域的**正向查閱區域**（例如，contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="a014b-145">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="a014b-146">確認主機 A （適用于 IPv6、AAAA）記錄對於您的主管池是否存在，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a014b-146">Verify that a host A (for IPv6, AAAA) record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="a014b-147">對於內部 DNS 記錄，您的控制器池（例如，lyncwebdir01）應該有主機 A （適用于 IPv6、AAAA）的記錄。</span><span class="sxs-lookup"><span data-stu-id="a014b-147">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="a014b-148">針對外部 DNS 記錄，您的主管池（例如，lyncwebextdir.contoso.com）應該有一個主機 A （適用于 IPv6、AAAA）記錄。</span><span class="sxs-lookup"><span data-stu-id="a014b-148">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="a014b-149">針對您的前臺池，確認主機 A （針對 IPv6、AAAA）記錄存在如下所示：</span><span class="sxs-lookup"><span data-stu-id="a014b-149">Verify that a host A (for IPv6, AAAA) record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="a014b-150">對於內部 DNS 記錄，您的主機 A （適用于 IPv6、AAAA）記錄應該存在於您的前端池（例如，lyncwebpool01）內部 Web 服務 FQDN 中。</span><span class="sxs-lookup"><span data-stu-id="a014b-150">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="a014b-151">對於外部 DNS 記錄，您的前端池（例如，lyncwebextpool01.contoso.com）應該有主機 A （適用于 IPv6、AAAA）記錄。</span><span class="sxs-lookup"><span data-stu-id="a014b-151">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="a014b-152">如果是內部 DNS 記錄，請在您的 DNS 伺服器的主控台樹中，展開您 SIP 網域的**正向查閱區域**（例如，contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="a014b-152">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a014b-153">如果您要建立外部 DNS 記錄，您的 SIP 網域已在步驟3中展開 [<STRONG>轉寄查閱區域</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="a014b-153">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="a014b-154">以滑鼠右鍵按一下 SIP 網功能變數名稱稱，然後按一下 **[新增主機（A 或 AAAA）**]。</span><span class="sxs-lookup"><span data-stu-id="a014b-154">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="a014b-155">在 [**名稱**] 中，輸入主機名稱，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a014b-155">In **Name**, type the host name as follows:</span></span>
    
      - <span data-ttu-id="a014b-156">針對內部 DNS 記錄，請輸入 lyncdiscoverinternal 做為內部自動探索服務 URL 的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="a014b-156">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="a014b-157">針對外部 DNS 記錄，請輸入 lyncdiscover 做為外部自動探索服務 URL 的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="a014b-157">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a014b-158">功能變數名稱是從定義該記錄的區域中假設，因此不需要在 A 記錄中輸入該功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="a014b-158">The domain name is assumed from the zone in which the record is defined and, therefore, does not need to be entered as part of the A record.</span></span>

    
    </div>

9.  <span data-ttu-id="a014b-159">在 [ **Ip 位址**] 中，輸入 ip 位址，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a014b-159">In **IP Address**, type the IP address as follows:</span></span>
    
      - <span data-ttu-id="a014b-160">如果是內部 DNS 記錄，請輸入主管的內部 Web 服務 IP 位址（或者，如果您使用負載平衡器，請輸入控制器負載平衡器的虛擬 IP （VIP））。</span><span class="sxs-lookup"><span data-stu-id="a014b-160">For an internal DNS record, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a014b-161">如果您不使用 Director，請輸入前端伺服器或標準版伺服器的 IP 位址，或者，如果您使用負載平衡器，請輸入前端池負載平衡器的 VIP。</span><span class="sxs-lookup"><span data-stu-id="a014b-161">If you do not use a Director, type the IP address of the Front End Server or Standard Edition server, or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

        
        </div>
    
      - <span data-ttu-id="a014b-162">針對外部 DNS 記錄，請輸入反向 proxy 的外部或公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a014b-162">For an external DNS record, type the external or public IP address of the reverse proxy.</span></span>

10. <span data-ttu-id="a014b-163">按一下 [**新增主機**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a014b-163">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="a014b-164">若要建立額外的 A 記錄，請重複步驟8到10。</span><span class="sxs-lookup"><span data-stu-id="a014b-164">To create an additional A record, repeat steps 8 through 10.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a014b-165">您必須在 Lync Server 2013 環境中所支援的每個 SIP 網域的轉寄式查閱區域中，建立新的 lyncdiscover，並 lyncdiscoverinternal 記錄。</span><span class="sxs-lookup"><span data-stu-id="a014b-165">You must create a new lyncdiscover and lyncdiscoverinternal A records in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

12. <span data-ttu-id="a014b-166">完成建立（適用于 IPv6、AAAA）記錄之後，按一下 [**完成**]。</span><span class="sxs-lookup"><span data-stu-id="a014b-166">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

