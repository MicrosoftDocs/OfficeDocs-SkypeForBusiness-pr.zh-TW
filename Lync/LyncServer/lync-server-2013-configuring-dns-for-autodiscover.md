---
title: Lync Server 2013：設定自動探索的 DNS
description: Lync Server 2013：設定自動探索的 DNS。
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
ms.openlocfilehash: 98a56cf3aa260bcbec9099e65958a9b17c3eaf26
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548459"
---
# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="12fe4-103">在 Lync Server 2013 中設定自動探索的 DNS</span><span class="sxs-lookup"><span data-stu-id="12fe4-103">Configuring DNS for Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12fe4-104">_**主題上次修改日期：** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="12fe4-104">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="12fe4-105">若要支援 Lync 用戶端的自動探索，您必須建立下列網域名稱系統 (DNS) 記錄：</span><span class="sxs-lookup"><span data-stu-id="12fe4-105">To support autodiscovery for Lync clients, you need to create the following Domain Name System (DNS) records:</span></span>

  - <span data-ttu-id="12fe4-106">內部 DNS 記錄，以支援從組織網路內部連線的 Lync 用戶端</span><span class="sxs-lookup"><span data-stu-id="12fe4-106">An internal DNS record to support Lync clients who connect from within your organization's network</span></span>

  - <span data-ttu-id="12fe4-107">支援從網際網路連線之 Lync 用戶端的外部（或公用） DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="12fe4-107">An external, or public, DNS record to support Lync clients who connect from the Internet</span></span>

<span data-ttu-id="12fe4-108">您必須為每個 SIP 網域建立內部 DNS 記錄及外部 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="12fe4-108">You must create an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="12fe4-109">DNS 記錄可以是 (主機) 記錄或 CNAME 記錄，其依據您使用其他主體別名 (SAN) 建立新憑證的能力。</span><span class="sxs-lookup"><span data-stu-id="12fe4-109">The DNS records can be either A (host) records or CNAME records, based on your ability to create new certificates with the additional subject alternate name (SAN).</span></span> <span data-ttu-id="12fe4-110">如果您無法向 lyncdiscover 要求及部署新的外部 (公開) 憑證。\<domain name\></span><span class="sxs-lookup"><span data-stu-id="12fe4-110">If you are not able to request and deploy a new external (public) certificate with the lyncdiscover.\<domain name\></span></span> <span data-ttu-id="12fe4-111">SAN，請使用 HTTP/TCP 埠80的程式。</span><span class="sxs-lookup"><span data-stu-id="12fe4-111">SAN, use the procedure for using HTTP/TCP port 80.</span></span> <span data-ttu-id="12fe4-112">下列程序說明如何建立內部及外部 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="12fe4-112">The following procedures describe how to create internal and external DNS records.</span></span>

<div>

## <a name="to-create-dns-cname-records"></a><span data-ttu-id="12fe4-113">建立 DNS CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="12fe4-113">To create DNS CNAME records</span></span>

1.  <span data-ttu-id="12fe4-114">登入 DNS 伺服器，如下所示：</span><span class="sxs-lookup"><span data-stu-id="12fe4-114">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="12fe4-115">若要建立內部 DNS 記錄，請以 Domain Admins 群組成員身分或 DnsAdmins 群組成員身分，登入您網路中的 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="12fe4-115">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="12fe4-116">若要建立外部 DNS 記錄，請連線至公用 DNS 提供者。</span><span class="sxs-lookup"><span data-stu-id="12fe4-116">To create an external DNS record, connect to your public DNS provider.</span></span>

2.  <span data-ttu-id="12fe4-117">開啟 DNS 系統管理嵌入式管理單元：依序按一下 [開始]\*\*\*\*、[系統管理工具]\*\*\*\* 和 [DNS]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="12fe4-117">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="12fe4-118">執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="12fe4-118">Do one of the following:</span></span>
    
      - <span data-ttu-id="12fe4-119">針對內部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 Active Directory 網域 (例如 contoso.local) 的 [正向對應區域]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="12fe4-119">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="12fe4-120">此網域是安裝 Lync Server 2013 &nbsp; Director 集區和前端集區的 Active Directory 網域。</span><span class="sxs-lookup"><span data-stu-id="12fe4-120">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="12fe4-121">針對外部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 SIP 網域 (例如 contoso.com) 的 [正向對應區域]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="12fe4-121">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="12fe4-122">請確認 Director 集區的主機 A 記錄存在，如下所示：</span><span class="sxs-lookup"><span data-stu-id="12fe4-122">Verify that a host A record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="12fe4-123">針對內部 DNS 記錄，主機 A 記錄應該存在於 Director 集區的內部 Web 服務完整功能變數名稱 (FQDN)  (例如，lyncwebdir01.contoso.local) 。</span><span class="sxs-lookup"><span data-stu-id="12fe4-123">For an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="12fe4-124">針對外部 DNS 記錄，Director 集區的外部 web 服務 FQDN 應該存在主機 A 記錄 (例如，lyncwebextdir.contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="12fe4-124">For an external DNS record, a host A record should exist for the external web services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="12fe4-125">請確認您的前端集區的主機 A 記錄存在，如下所示：</span><span class="sxs-lookup"><span data-stu-id="12fe4-125">Verify that a host A record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="12fe4-126">針對內部 DNS 記錄，您的前端集區的內部 Web 服務 FQDN 應該存在主機 A 記錄 (例如，lyncwebpool01.contoso.local local) 。</span><span class="sxs-lookup"><span data-stu-id="12fe4-126">For an internal DNS record, a host A record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="12fe4-127">針對外部 DNS 記錄，您的前端集區的外部 Web 服務 FQDN 應該會有主機 A 記錄 (例如，lyncwebextpool01.contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="12fe4-127">For an external DNS record, a host A record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="12fe4-128">針對內部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 SIP 網域 (例如 contoso.com) 的 [正向對應區域]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="12fe4-128">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="12fe4-129">如果您要建立外部 DNS 記錄，從步驟 3 就已展開 SIP 網域的 [正向對應區域]<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="12fe4-129">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="12fe4-130">用滑鼠右鍵按一下 SIP 網域名稱，然後按一下 [新增別名 (CNAME)]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="12fe4-130">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="12fe4-131">在 [別名]\*\*\*\* 中，輸入下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="12fe4-131">In **Alias name**, type one of the following:</span></span>
    
      - <span data-ttu-id="12fe4-132">針對內部 DNS 記錄，輸入 lyncdiscoverinternal 作為內部自動探索服務 URL 的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="12fe4-132">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="12fe4-133">針對外部 DNS 記錄，輸入 lyncdiscover 作為外部自動探索服務 URL 的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="12fe4-133">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="12fe4-134">在 [目標主機完整網域名稱 (FQDN)]\*\*\*\* 中，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="12fe4-134">In **Fully qualified domain name (FQDN) for target host**, do one of the following:</span></span>
    
      - <span data-ttu-id="12fe4-135">針對內部 DNS 記錄，輸入或流覽至 Director 集區的內部 Web 服務 FQDN (例如，lyncwebdir01.contoso.local local) ，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="12fe4-135">For an internal DNS record, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local), and then click **OK**.</span></span>
    
      - <span data-ttu-id="12fe4-136">針對外部 DNS 記錄，輸入或流覽至 Director 集區的外部 Web 服務 FQDN (例如，lyncwebextdir.contoso.com) ，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="12fe4-136">For an external DNS record, type or browse to the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="12fe4-137">如果您不使用 Director，請使用前端集區的內部及外部 Web 服務 FQDN，或針對單一伺服器（前端伺服器或 Standard Edition server 的 FQDN）。</span><span class="sxs-lookup"><span data-stu-id="12fe4-137">If you do not use a Director, use the internal and external Web Services FQDN for the Front End pool, or, for a single server, the FQDN for the Front End Server or Standard Edition server.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="12fe4-138">您必須在 Lync Server 2013 環境中所支援的每個 SIP 網域的正向對應區域中建立新的自動探索 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="12fe4-138">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a><span data-ttu-id="12fe4-139">建立 DNS A 記錄</span><span class="sxs-lookup"><span data-stu-id="12fe4-139">To create DNS A records</span></span>

1.  <span data-ttu-id="12fe4-140">登入 DNS 伺服器，如下所示：</span><span class="sxs-lookup"><span data-stu-id="12fe4-140">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="12fe4-141">若要建立內部 DNS 記錄，請以 Domain Admins 群組成員身分或 DnsAdmins 群組成員身分，登入您網路中的 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="12fe4-141">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="12fe4-142">若要建立外部 DNS 記錄，請連接至您的公用 DNS 提供者或外部 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="12fe4-142">To create an external DNS record, connect to your public DNS provider or external DNS server.</span></span>

2.  <span data-ttu-id="12fe4-143">開啟 DNS 系統管理嵌入式管理單元：依序按一下 [開始]\*\*\*\*、[系統管理工具]\*\*\*\* 和 [DNS]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="12fe4-143">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="12fe4-144">執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="12fe4-144">Do one of the following:</span></span>
    
      - <span data-ttu-id="12fe4-145">針對內部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 Active Directory 網域 (例如 contoso.local) 的 [正向對應區域]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="12fe4-145">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="12fe4-146">此網域是安裝 Lync Server 2013 &nbsp; Director 集區和前端集區的 Active Directory 網域。</span><span class="sxs-lookup"><span data-stu-id="12fe4-146">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="12fe4-147">針對外部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 SIP 網域 (例如 contoso.com) 的 [正向對應區域]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="12fe4-147">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="12fe4-148">針對您的 Director 集區，確認主機 A IPv6 的 (存在 AAAA) 記錄，如下所示：</span><span class="sxs-lookup"><span data-stu-id="12fe4-148">Verify that a host A (for IPv6, AAAA) record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="12fe4-149">針對內部 DNS 記錄，您的 Director 集區的內部 Web 服務 FQDN 應該會有一個主機 A (IPv6，AAAA) 記錄應該存在 (例如，lyncwebdir01.contoso.local) 。</span><span class="sxs-lookup"><span data-stu-id="12fe4-149">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="12fe4-150">針對外部 DNS 記錄，您的 Director 集區的外部 Web 服務 FQDN 應該會有一個主機的 (IPv6，AAAA) 記錄應該存在 (例如，lyncwebextdir.contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="12fe4-150">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="12fe4-151">請確認您的前端集區的主機 A (IPv6，AAAA) 記錄都存在，如下所示：</span><span class="sxs-lookup"><span data-stu-id="12fe4-151">Verify that a host A (for IPv6, AAAA) record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="12fe4-152">針對內部 DNS 記錄，a 主機 A IPv6 的 (，AAAA) 記錄應該存在於前端集區的內部 Web 服務 FQDN (例如，lyncwebpool01.contoso.local) 。</span><span class="sxs-lookup"><span data-stu-id="12fe4-152">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="12fe4-153">針對外部 DNS 記錄，a 主機 A IPv6 的 (，AAAA) 記錄應該存在於前端集區的外部 Web 服務 FQDN (例如，lyncwebextpool01.contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="12fe4-153">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="12fe4-154">針對內部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 SIP 網域 (例如 contoso.com) 的 [正向對應區域]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="12fe4-154">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="12fe4-155">如果您要建立外部 DNS 記錄，從步驟 3 就已展開 SIP 網域的 [正向對應區域]<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="12fe4-155">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="12fe4-156">用滑鼠右鍵按一下 SIP 網域名稱，然後按一下 [新增主機 (A 或 AAAA)]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="12fe4-156">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="12fe4-157">在 [名稱]\*\*\*\* 中輸入主機名稱，如下所示：</span><span class="sxs-lookup"><span data-stu-id="12fe4-157">In **Name**, type the host name as follows:</span></span>
    
      - <span data-ttu-id="12fe4-158">針對內部 DNS 記錄，輸入 lyncdiscoverinternal 作為內部自動探索服務 URL 的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="12fe4-158">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="12fe4-159">針對外部 DNS 記錄，輸入 lyncdiscover 作為外部自動探索服務 URL 的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="12fe4-159">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="12fe4-160">網域名稱是從定義記錄所在的區域取得，因此，不需要當作 A 記錄的一部分來輸入。</span><span class="sxs-lookup"><span data-stu-id="12fe4-160">The domain name is assumed from the zone in which the record is defined and, therefore, does not need to be entered as part of the A record.</span></span>

    
    </div>

9.  <span data-ttu-id="12fe4-161">在 [IP 位址]\*\*\*\* 中輸入 IP 位址，如下所示：</span><span class="sxs-lookup"><span data-stu-id="12fe4-161">In **IP Address**, type the IP address as follows:</span></span>
    
      - <span data-ttu-id="12fe4-162">針對內部 DNS 記錄，輸入 Director (的內部 Web 服務 IP 位址，或者，如果使用負載平衡器，請輸入 Director 負載平衡器) 的虛擬 IP (VIP) 。</span><span class="sxs-lookup"><span data-stu-id="12fe4-162">For an internal DNS record, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="12fe4-163">如果您不使用 Director，請輸入前端伺服器或 Standard Edition Server 的 IP 位址，或者，如果使用負載平衡器，請輸入前端集區負載平衡器的 VIP。</span><span class="sxs-lookup"><span data-stu-id="12fe4-163">If you do not use a Director, type the IP address of the Front End Server or Standard Edition server, or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

        
        </div>
    
      - <span data-ttu-id="12fe4-164">針對外部 DNS 記錄，輸入反向 Proxy 的外部或公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="12fe4-164">For an external DNS record, type the external or public IP address of the reverse proxy.</span></span>

10. <span data-ttu-id="12fe4-165">按一下 [新增主機]\*\*\*\*，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="12fe4-165">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="12fe4-166">如果要建立其他 A 記錄，請重複步驟 8 到 10。</span><span class="sxs-lookup"><span data-stu-id="12fe4-166">To create an additional A record, repeat steps 8 through 10.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="12fe4-167">您必須在 Lync Server 2013 環境中所支援的每個 SIP 網域的正向對應區域中建立新的 lyncdiscover 和 lyncdiscoverinternal A 記錄。</span><span class="sxs-lookup"><span data-stu-id="12fe4-167">You must create a new lyncdiscover and lyncdiscoverinternal A records in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

12. <span data-ttu-id="12fe4-168">完成建立 A (對於 IPv6 為 AAAA) 記錄時，按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="12fe4-168">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

