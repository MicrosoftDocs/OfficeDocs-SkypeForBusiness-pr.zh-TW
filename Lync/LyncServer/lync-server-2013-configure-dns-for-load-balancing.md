---
title: Lync Server 2013：設定 DNS 負載平衡
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
ms.openlocfilehash: f5b68bf226c71d65835791577ab9a45f18b2a10e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="4ab50-102">在 Lync Server 2013 中設定 DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="4ab50-102">Configure DNS for load balancing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ab50-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="4ab50-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="4ab50-104">若要成功完成此程式，您必須以網域管理員群組或 DnsAdmins 群組成員的身分登入伺服器或網域。</span><span class="sxs-lookup"><span data-stu-id="4ab50-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="4ab50-105">網域名稱系統（DNS）負載平衡會平衡 Lync Server 2013 （例如 SIP 流量及媒體流量）獨有的網路流量。</span><span class="sxs-lookup"><span data-stu-id="4ab50-105">Domain Name System (DNS) Load Balancing balances the network traffic that is unique to Lync Server 2013, such as SIP traffic and media traffic.</span></span> <span data-ttu-id="4ab50-106">前端池、邊緣池、控制器池和獨立的轉送池都支援 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="4ab50-106">DNS load balancing is supported for Front End pools, Edge pools, Director pools, and stand-alone Mediation pools.</span></span> <span data-ttu-id="4ab50-107">設定為使用 DNS 負載平衡的池必須有兩個完整的功能變數名稱（Fqdn）：由 DNS 負載平衡所使用的一般池 FQDN （例如 pool1.contoso.com），並解析為池中伺服器的實際 Ip以及池的 Web 服務（例如，web1.contoso.net）的另一個 FQDN，可解析為該池的虛擬 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="4ab50-107">A pool that is configured to use DNS load balancing must have two fully qualified domain names (FQDNs) defined: the regular pool FQDN that is used by DNS load balancing (for example, pool1.contoso.com) and that resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web Services (for example, web1.contoso.net), which resolves to the virtual IP address of the pool.</span></span> <span data-ttu-id="4ab50-108">如需有關 DNS 負載平衡的詳細資料，請參閱規劃檔中的[Lync Server 2013 中的 DNS 負載平衡](lync-server-2013-dns-load-balancing.md)。</span><span class="sxs-lookup"><span data-stu-id="4ab50-108">For details about DNS Load Balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4ab50-109">用戶端到伺服器 HTTPS 流量仍需要硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="4ab50-109">Hardware load balancing is still required for client to server HTTPS traffic.</span></span>



</div>

<span data-ttu-id="4ab50-110">在您可以使用 DNS 負載平衡之前，您必須執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="4ab50-110">Before you can use DNS load balancing, you must do the following:</span></span>

1.  <span data-ttu-id="4ab50-111">覆寫內部 Web 服務池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="4ab50-111">Override the internal Web Services pool FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="4ab50-112">如果決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 都必須與任何其他的前端池、控制器或主管池是唯一的。</span><span class="sxs-lookup"><span data-stu-id="4ab50-112">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

2.  <span data-ttu-id="4ab50-113">建立 DNS 主機記錄，以將池 FQDN 解析成池中所有伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="4ab50-113">Create DNS A host records to resolve the pool FQDN to the IP addresses of all the servers in the pool.</span></span>

3.  <span data-ttu-id="4ab50-114">啟用 IP 位址隨機化，或針對 Windows Server DNS 啟用迴圈複用。</span><span class="sxs-lookup"><span data-stu-id="4ab50-114">Enable IP Address randomization or, for Windows Server DNS, enable round robin.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4ab50-115">預設會啟用迴圈複用。</span><span class="sxs-lookup"><span data-stu-id="4ab50-115">Round robin should be enabled by default.</span></span>

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a><span data-ttu-id="4ab50-116">覆寫內部 Web 服務 FQDN</span><span class="sxs-lookup"><span data-stu-id="4ab50-116">To override internal Web services FQDN</span></span>

1.  <span data-ttu-id="4ab50-117">啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="4ab50-117">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="4ab50-118">從主控台樹中，展開 [企業版前端池] 節點。</span><span class="sxs-lookup"><span data-stu-id="4ab50-118">From the console tree, expand the Enterprise Edition Front End pools node.</span></span>

3.  <span data-ttu-id="4ab50-119">以滑鼠右鍵按一下該池，按一下 [**編輯屬性**]，然後按一下 [ **Web 服務**]。</span><span class="sxs-lookup"><span data-stu-id="4ab50-119">Right-click the pool, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="4ab50-120">在 [**內部 web 服務**] 底下，選取 [覆**寫 FQDN** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="4ab50-120">Below **Internal web services**, select the **Override FQDN** check box.</span></span>

5.  <span data-ttu-id="4ab50-121">輸入可解析為池中伺服器之物理 IP 位址的 [池 FQDN]。</span><span class="sxs-lookup"><span data-stu-id="4ab50-121">Type the pool FQDN that resolves to the physical IP addresses of the servers in the pool.</span></span>

6.  <span data-ttu-id="4ab50-122">在 [**外部 web 服務**] 底下，輸入可解析為該池之虛擬 IP 位址的外部池 FQDN，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="4ab50-122">Below **External web services**, type the external pool FQDN that resolves to the virtual IP addresses of the pool, and then click **OK**.</span></span>

7.  <span data-ttu-id="4ab50-123">在主控台樹中，按一下 [ **Lync Server 2013**]，然後在 [**動作**] 窗格中，按一下 [**發佈拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="4ab50-123">From the console tree, click **Lync Server 2013**, and then in the **Actions** pane, click **Publish Topology**.</span></span>

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a><span data-ttu-id="4ab50-124">若要建立所有內部池伺服器的 DNS 主機（A）記錄</span><span class="sxs-lookup"><span data-stu-id="4ab50-124">To create DNS Host (A) Records for all internal pool servers</span></span>

1.  <span data-ttu-id="4ab50-125">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [系統**管理工具**]，然後按一下 [ **DNS**]。</span><span class="sxs-lookup"><span data-stu-id="4ab50-125">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="4ab50-126">在 [ **Dns 管理員**] 中，按一下記錄管理的 DNS 伺服器加以展開。</span><span class="sxs-lookup"><span data-stu-id="4ab50-126">In **DNS Manager**, click the DNS Server that manages your records to expand it.</span></span>

3.  <span data-ttu-id="4ab50-127">按一下 [**轉寄查閱區域**] 將它展開。</span><span class="sxs-lookup"><span data-stu-id="4ab50-127">Click **Forward Lookup Zones** to expand it.</span></span>

4.  <span data-ttu-id="4ab50-128">以滑鼠右鍵按一下您需要新增記錄的 DNS 網域，然後按一下 **[新增主機（A 或 AAAA）**]。</span><span class="sxs-lookup"><span data-stu-id="4ab50-128">Right-click the DNS domain that you need to add records to, and then click **New Host (A or AAAA)**.</span></span>

5.  <span data-ttu-id="4ab50-129">在 [**名稱**] 方塊中，輸入主機記錄的名稱（將會自動附加功能變數名稱）。</span><span class="sxs-lookup"><span data-stu-id="4ab50-129">In the **Name** box, type the name of the host record (the domain name will be automatically appended).</span></span>

6.  <span data-ttu-id="4ab50-130">在 [IP 位址] 方塊中，輸入個別前端伺服器的 IP 位址，然後選取 [**建立相關的指標（PTR）記錄**] 或 **[允許任何經過驗證的使用者使用相同的擁有者名稱來更新 DNS 記錄**] （如果適用的話）。</span><span class="sxs-lookup"><span data-stu-id="4ab50-130">In the IP Address box, type the IP address of the individual Front End Server and then select **Create associated pointer (PTR) record** or **Allow any authenticated user to update DNS records with the same owner name**, if applicable.</span></span>

7.  <span data-ttu-id="4ab50-131">針對將參與 DNS 負載平衡的所有成員前端伺服器，繼續建立記錄。</span><span class="sxs-lookup"><span data-stu-id="4ab50-131">Continue creating records for all member Front End Servers that will participate in DNS Load Balancing.</span></span>
    
    <span data-ttu-id="4ab50-132">例如，如果您有一個名為 pool1.contoso.com 和三個前端伺服器的池，您會建立下列 DNS 專案：</span><span class="sxs-lookup"><span data-stu-id="4ab50-132">For example, if you had a pool named pool1.contoso.com and three Front End Servers, you would create the following DNS entries:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="4ab50-133">稱</span><span class="sxs-lookup"><span data-stu-id="4ab50-133">FQDN</span></span></th>
    <th><span data-ttu-id="4ab50-134">類型</span><span class="sxs-lookup"><span data-stu-id="4ab50-134">Type</span></span></th>
    <th><span data-ttu-id="4ab50-135">資料</span><span class="sxs-lookup"><span data-stu-id="4ab50-135">Data</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="4ab50-136">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4ab50-136">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="4ab50-137">主機（A）</span><span class="sxs-lookup"><span data-stu-id="4ab50-137">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="4ab50-138">192.168.1.1</span><span class="sxs-lookup"><span data-stu-id="4ab50-138">192.168.1.1</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="4ab50-139">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4ab50-139">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="4ab50-140">主機（A）</span><span class="sxs-lookup"><span data-stu-id="4ab50-140">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="4ab50-141">192.168.1.2</span><span class="sxs-lookup"><span data-stu-id="4ab50-141">192.168.1.2</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="4ab50-142">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4ab50-142">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="4ab50-143">主機（A）</span><span class="sxs-lookup"><span data-stu-id="4ab50-143">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="4ab50-144">192.168.1.3</span><span class="sxs-lookup"><span data-stu-id="4ab50-144">192.168.1.3</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="4ab50-145">如需建立 DNS 主機（A）記錄的詳細資料，請參閱[設定 Lync Server 2013 的 DNS 主機記錄](lync-server-2013-configure-dns-host-records.md)。</span><span class="sxs-lookup"><span data-stu-id="4ab50-145">For details about creating DNS Host (A) records, see [Configure DNS Host records for Lync Server 2013](lync-server-2013-configure-dns-host-records.md).</span></span>

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a><span data-ttu-id="4ab50-146">若要啟用 Windows Server 的迴圈複用</span><span class="sxs-lookup"><span data-stu-id="4ab50-146">To enable round robin for Windows Server</span></span>

1.  <span data-ttu-id="4ab50-147">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [系統**管理工具**]，然後按一下 [ **DNS**]。</span><span class="sxs-lookup"><span data-stu-id="4ab50-147">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="4ab50-148">展開 [ **DNS**]，以滑鼠右鍵按一下您要設定的 DNS 伺服器，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="4ab50-148">Expand **DNS**, right-click the DNS server you want to configure, and then click **Properties**.</span></span>

3.  <span data-ttu-id="4ab50-149">按一下 [**高級**] 索引標籤，選取 [**啟用迴圈複用**並**啟用網路遮罩排序**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="4ab50-149">Click the **Advanced** tab, select **Enable round robin** and **Enable netmask ordering**, and then click **OK**.</span></span>
    
    <span data-ttu-id="4ab50-150">![DNS 循環配置資源對話方塊](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "DNS 循環配置資源對話方塊")</span><span class="sxs-lookup"><span data-stu-id="4ab50-150">![DNS Round Robin dialog box](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "DNS Round Robin dialog box")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4ab50-151">預設會啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="4ab50-151">This feature should be enabled by default.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4ab50-152">請參閱</span><span class="sxs-lookup"><span data-stu-id="4ab50-152">See Also</span></span>


[<span data-ttu-id="4ab50-153">Lync Server 2013 中的 DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="4ab50-153">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

