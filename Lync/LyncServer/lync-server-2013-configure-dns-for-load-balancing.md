---
title: Lync Server 2013：設定 DNS 以進行負載平衡
description: Lync Server 2013：設定 DNS 以進行負載平衡。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for load balancing
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398251(v=OCS.15)
ms:contentKeyID: 48183540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b13db22d65ee67723ebc0a31544137d467d5c6b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553449"
---
# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="969a0-103">在 Lync Server 2013 中設定 DNS 以進行負載平衡</span><span class="sxs-lookup"><span data-stu-id="969a0-103">Configure DNS for load balancing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="969a0-104">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="969a0-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="969a0-105">若要順利完成此程序，您至少應該以 Domain Admins 群組成員或 DnsAdmins 群組成員的身分登入伺服器或網域。</span><span class="sxs-lookup"><span data-stu-id="969a0-105">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="969a0-106">網域名稱系統 (DNS) 負載平衡會平衡 Lync Server 2013 特有的網路流量，例如 SIP 流量和媒體流量。</span><span class="sxs-lookup"><span data-stu-id="969a0-106">Domain Name System (DNS) Load Balancing balances the network traffic that is unique to Lync Server 2013, such as SIP traffic and media traffic.</span></span> <span data-ttu-id="969a0-107">前端集區、Edge 集區、Director 集區和獨立中繼集區支援 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="969a0-107">DNS load balancing is supported for Front End pools, Edge pools, Director pools, and stand-alone Mediation pools.</span></span> <span data-ttu-id="969a0-108">設定為使用 DNS 負載平衡的集區必須有兩個完全合格的功能變數名稱 (Fqdn) 定義： DNS 負載平衡所使用的一般集區 FQDN (例如，pool1.contoso.com) ，且解析為集區中伺服器的實體 Ip，以及集區 Web 服務的另一個 FQDN (例如，web1.contoso.net) ，可解析為集區的虛擬 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="969a0-108">A pool that is configured to use DNS load balancing must have two fully qualified domain names (FQDNs) defined: the regular pool FQDN that is used by DNS load balancing (for example, pool1.contoso.com) and that resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web Services (for example, web1.contoso.net), which resolves to the virtual IP address of the pool.</span></span> <span data-ttu-id="969a0-109">如需 DNS 負載平衡的詳細資訊，請參閱規劃檔中的 [Lync Server 2013 中的 DNS 負載平衡](lync-server-2013-dns-load-balancing.md) 。</span><span class="sxs-lookup"><span data-stu-id="969a0-109">For details about DNS Load Balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="969a0-110">用戶端到伺服器的 HTTPS 流量仍需要硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="969a0-110">Hardware load balancing is still required for client to server HTTPS traffic.</span></span>



</div>

<span data-ttu-id="969a0-111">您必須先進行下列步驟，才能使用 DNS 負載平衡：</span><span class="sxs-lookup"><span data-stu-id="969a0-111">Before you can use DNS load balancing, you must do the following:</span></span>

1.  <span data-ttu-id="969a0-112">覆寫內部 Web 服務集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="969a0-112">Override the internal Web Services pool FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="969a0-113">如果決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 必須與其他任何前端集區、Director 或 Director 集區是唯一的。</span><span class="sxs-lookup"><span data-stu-id="969a0-113">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

2.  <span data-ttu-id="969a0-114">建立 DNS A 主機記錄，以便將集區 FQDN 解析為集區中所有伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="969a0-114">Create DNS A host records to resolve the pool FQDN to the IP addresses of all the servers in the pool.</span></span>

3.  <span data-ttu-id="969a0-115">啟用 IP 位址隨機化，或針對 Windows Server DNS 啟用循環配置資源。</span><span class="sxs-lookup"><span data-stu-id="969a0-115">Enable IP Address randomization or, for Windows Server DNS, enable round robin.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="969a0-116">預設應啟用循環配置資源。</span><span class="sxs-lookup"><span data-stu-id="969a0-116">Round robin should be enabled by default.</span></span>

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a><span data-ttu-id="969a0-117">覆寫內部 Web 服務 FQDN</span><span class="sxs-lookup"><span data-stu-id="969a0-117">To override internal Web services FQDN</span></span>

1.  <span data-ttu-id="969a0-118">啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="969a0-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="969a0-119">從主控台樹狀目錄展開 Enterprise Edition 前端集區節點。</span><span class="sxs-lookup"><span data-stu-id="969a0-119">From the console tree, expand the Enterprise Edition Front End pools node.</span></span>

3.  <span data-ttu-id="969a0-120">以滑鼠右鍵按一下集區、按一下 **[編輯內容]**，然後按一下 **[Web 服務]**。</span><span class="sxs-lookup"><span data-stu-id="969a0-120">Right-click the pool, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="969a0-121">在 **[內部 Web 服務]** 下方，選取 **[覆寫 FQDN]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="969a0-121">Below **Internal web services**, select the **Override FQDN** check box.</span></span>

5.  <span data-ttu-id="969a0-122">輸入用於解析為集區伺服器之實體 IP 位址的集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="969a0-122">Type the pool FQDN that resolves to the physical IP addresses of the servers in the pool.</span></span>

6.  <span data-ttu-id="969a0-123">在 **[外部 Web 服務]** 下方，輸入用於解析為集區虛擬 IP 位址的外部集區 FQDN，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="969a0-123">Below **External web services**, type the external pool FQDN that resolves to the virtual IP addresses of the pool, and then click **OK**.</span></span>

7.  <span data-ttu-id="969a0-124">在主控台樹中，按一下 [ **Lync Server 2013**]，然後在 [ **動作** ] 窗格中，按一下 [ **發行拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="969a0-124">From the console tree, click **Lync Server 2013**, and then in the **Actions** pane, click **Publish Topology**.</span></span>

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a><span data-ttu-id="969a0-125">建立所有內部集區伺服器的 DNS 主機 (A) 記錄</span><span class="sxs-lookup"><span data-stu-id="969a0-125">To create DNS Host (A) Records for all internal pool servers</span></span>

1.  <span data-ttu-id="969a0-126">依序按一下 **[開始]**、**[所有程式]**、**[系統管理工具]** 和 **[DNS]**。</span><span class="sxs-lookup"><span data-stu-id="969a0-126">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="969a0-127">在 **[DNS 管理員]** 中，按一下管理記錄的 DNS 伺服器，將其展開。</span><span class="sxs-lookup"><span data-stu-id="969a0-127">In **DNS Manager**, click the DNS Server that manages your records to expand it.</span></span>

3.  <span data-ttu-id="969a0-128">按一下 **[正向對應區域]** 將其展開。</span><span class="sxs-lookup"><span data-stu-id="969a0-128">Click **Forward Lookup Zones** to expand it.</span></span>

4.  <span data-ttu-id="969a0-129">以滑鼠右鍵按一下您要新增記錄的 DNS 網域，然後按一下 **[新增主機 (A 或 AAAA)]**。</span><span class="sxs-lookup"><span data-stu-id="969a0-129">Right-click the DNS domain that you need to add records to, and then click **New Host (A or AAAA)**.</span></span>

5.  <span data-ttu-id="969a0-130">在 [ **名稱** ] 方塊中，輸入主機記錄的名稱 (功能變數名稱將會自動附加) 中。</span><span class="sxs-lookup"><span data-stu-id="969a0-130">In the **Name** box, type the name of the host record (the domain name will be automatically appended).</span></span>

6.  <span data-ttu-id="969a0-131">在 [IP 位址] 方塊中，輸入個別前端伺服器的 IP 位址，然後選取 **[建立關聯的指標 (PTR) 記錄]** 或 **[允許已驗證的使用者更新相同擁有者名稱的 DNS 記錄]** (如果適用的話)。</span><span class="sxs-lookup"><span data-stu-id="969a0-131">In the IP Address box, type the IP address of the individual Front End Server and then select **Create associated pointer (PTR) record** or **Allow any authenticated user to update DNS records with the same owner name**, if applicable.</span></span>

7.  <span data-ttu-id="969a0-132">繼續為其他將參與 DNS 負載平衡的所有成員前端伺服器建立記錄。</span><span class="sxs-lookup"><span data-stu-id="969a0-132">Continue creating records for all member Front End Servers that will participate in DNS Load Balancing.</span></span>
    
    <span data-ttu-id="969a0-133">例如，如果您有個名為 pool1.contoso.com 的集區以及三個前端伺服器，您可以建立下列 DNS 項目：</span><span class="sxs-lookup"><span data-stu-id="969a0-133">For example, if you had a pool named pool1.contoso.com and three Front End Servers, you would create the following DNS entries:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="969a0-134">FQDN</span><span class="sxs-lookup"><span data-stu-id="969a0-134">FQDN</span></span></th>
    <th><span data-ttu-id="969a0-135">Type (類型)</span><span class="sxs-lookup"><span data-stu-id="969a0-135">Type</span></span></th>
    <th><span data-ttu-id="969a0-136">Data (資料)</span><span class="sxs-lookup"><span data-stu-id="969a0-136">Data</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="969a0-137">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="969a0-137">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="969a0-138">主機 (A)</span><span class="sxs-lookup"><span data-stu-id="969a0-138">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="969a0-139">192.168.1.1</span><span class="sxs-lookup"><span data-stu-id="969a0-139">192.168.1.1</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="969a0-140">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="969a0-140">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="969a0-141">主機 (A)</span><span class="sxs-lookup"><span data-stu-id="969a0-141">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="969a0-142">192.168.1.2</span><span class="sxs-lookup"><span data-stu-id="969a0-142">192.168.1.2</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="969a0-143">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="969a0-143">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="969a0-144">主機 (A)</span><span class="sxs-lookup"><span data-stu-id="969a0-144">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="969a0-145">192.168.1.3</span><span class="sxs-lookup"><span data-stu-id="969a0-145">192.168.1.3</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="969a0-146">如需建立 DNS 主機 () 記錄的詳細資訊，請參閱 [設定 Lync Server 2013 的 Dns 主機記錄](lync-server-2013-configure-dns-host-records.md)。</span><span class="sxs-lookup"><span data-stu-id="969a0-146">For details about creating DNS Host (A) records, see [Configure DNS Host records for Lync Server 2013](lync-server-2013-configure-dns-host-records.md).</span></span>

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a><span data-ttu-id="969a0-147">啟用 Windows Server 的循環配置資源</span><span class="sxs-lookup"><span data-stu-id="969a0-147">To enable round robin for Windows Server</span></span>

1.  <span data-ttu-id="969a0-148">依序按一下 **[開始]**、**[所有程式]**、**[系統管理工具]** 和 **[DNS]**。</span><span class="sxs-lookup"><span data-stu-id="969a0-148">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="969a0-149">展開 **[DNS]**，以滑鼠右鍵按一下您要設定的 DNS 伺服器，然後按一下 **[內容]**。</span><span class="sxs-lookup"><span data-stu-id="969a0-149">Expand **DNS**, right-click the DNS server you want to configure, and then click **Properties**.</span></span>

3.  <span data-ttu-id="969a0-150">按一下 **[進階]** 索引標籤，選取 **[啟用循環配置資源]** 和 **[啟用網路遮罩次序]**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="969a0-150">Click the **Advanced** tab, select **Enable round robin** and **Enable netmask ordering**, and then click **OK**.</span></span>
    
    <span data-ttu-id="969a0-151">![[DNS 迴圈複用] 對話方塊](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "[DNS 迴圈複用] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="969a0-151">![DNS Round Robin dialog box](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "DNS Round Robin dialog box")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="969a0-152">預設應啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="969a0-152">This feature should be enabled by default.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="969a0-153">另請參閱</span><span class="sxs-lookup"><span data-stu-id="969a0-153">See Also</span></span>


[<span data-ttu-id="969a0-154">Lync Server 2013 中的 DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="969a0-154">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

