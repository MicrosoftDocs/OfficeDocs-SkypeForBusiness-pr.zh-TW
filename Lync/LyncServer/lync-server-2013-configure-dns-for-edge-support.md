---
title: Lync Server 2013：設定 edge 支援的 DNS
description: Lync Server 2013：設定 edge 支援的 DNS。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for edge support
ms:assetid: 955493e6-aa29-424d-bb81-1ef87b3b15e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398756(v=OCS.15)
ms:contentKeyID: 48184894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 706f4915adda58dbb72b8dd8921e0cc612833718
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555889"
---
# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a><span data-ttu-id="85feb-103">在 Lync Server 2013 中設定 edge 支援的 DNS</span><span class="sxs-lookup"><span data-stu-id="85feb-103">Configure DNS for edge support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85feb-104">_**主題上次修改日期：** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="85feb-104">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="85feb-105">您必須設定網域名稱系統 (DNS) 內部和外部 edge 介面的記錄，包括 Edge Server 和反向 proxy 介面。</span><span class="sxs-lookup"><span data-stu-id="85feb-105">You must configure Domain Name System (DNS) records for internal and external edge interfaces, including both Edge Server and reverse proxy interfaces.</span></span> <span data-ttu-id="85feb-106">根據預設，Edge Server 並未加入網域，而且不會有完整功能變數名稱 (完整功能變數名稱) 。</span><span class="sxs-lookup"><span data-stu-id="85feb-106">By default, Edge Servers are not joined to a domain and will not have a fully qualified domain name (fully qualified domain name).</span></span> <span data-ttu-id="85feb-107">Edge Server 只是由 short (機器) 名稱，而不是完整功能變數名稱所參照。</span><span class="sxs-lookup"><span data-stu-id="85feb-107">The Edge Server is only referred to by the short (machine) name, not a fully qualified domain name.</span></span> <span data-ttu-id="85feb-108">不過，拓撲產生器會使用 Fqdn，而非短名稱。</span><span class="sxs-lookup"><span data-stu-id="85feb-108">However, Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="85feb-109">Edge Server 的名稱必須符合拓撲產生器所使用的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="85feb-109">The name of the Edge Server must match the FQDN used by Topology Builder.</span></span> <span data-ttu-id="85feb-110">若要這麼做，您可以定義 DNS 尾碼，當與機器名稱合併時，會產生預期的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="85feb-110">To do this, you define a DNS suffix that, when combined with the machine name, results in the expected FQDN.</span></span> <span data-ttu-id="85feb-111">在 [將 dns 尾碼新增至未加入網域的電腦名稱稱和 Edge Server] 中，使用下列程式，將 DNS 尾碼新增至電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="85feb-111">Use the following procedure in “To add the DNS suffix to the computer name on and Edge Server that is not joined to a domain” to add the DNS suffix to the computer name.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="85feb-112">根據預設，DNS 會使用迴圈演算法，以旋轉查詢答案中傳回的資源記錄資料的順序，其中，已查詢的 DNS 功能變數名稱有多個相同類型的資源記錄。</span><span class="sxs-lookup"><span data-stu-id="85feb-112">By default, DNS uses a round robin algorithm to rotate the order of resource record data returned in query answers where multiple resource records of the same type exist for a queried DNS domain name.</span></span> <span data-ttu-id="85feb-113">Lync Server 2013 DNS 負載平衡會因 dns 負載平衡機制的一部分，而定為 dns 迴圈。</span><span class="sxs-lookup"><span data-stu-id="85feb-113">Lync Server 2013 DNS load balancing, depends on DNS round-robin as a part of the DNS Load Balancing mechanism.</span></span> <span data-ttu-id="85feb-114">確認未停用 [迴圈] 設定。</span><span class="sxs-lookup"><span data-stu-id="85feb-114">Verify that round-robin setting has not been disabled.</span></span> <span data-ttu-id="85feb-115">如果您使用不是執行 Windows 作業系統的 DNS 伺服器，請確認是否已啟用迴圈資源記錄排序。</span><span class="sxs-lookup"><span data-stu-id="85feb-115">If you are using a DNS server that is not running a Windows operating system, verify that round-robin resource record ordering is enabled.</span></span>



</div>

<span data-ttu-id="85feb-116">在「**建立 DNS srv 記錄**」中，使用下列程式來建立及驗證每個 DNS srv 記錄。</span><span class="sxs-lookup"><span data-stu-id="85feb-116">Use the following procedures in “**To create a DNS SRV record**” to create and verify each DNS SRV record.</span></span> <span data-ttu-id="85feb-117">使用「**建立 Dns a 記錄**」中的程式，定義外部使用者存取所需的 DNS a 記錄。</span><span class="sxs-lookup"><span data-stu-id="85feb-117">Use the procedure in “**To create a DNS A record**” to define the DNS A records required for external user access.</span></span> <span data-ttu-id="85feb-118">若要確認記錄是否已設定且運作正常，請參閱本主題中的「**驗證 DNS 記錄**」。</span><span class="sxs-lookup"><span data-stu-id="85feb-118">To confirm that the records are configured and working correctly, see “**To verify a DNS record**” in this topic.</span></span> <span data-ttu-id="85feb-119">如需支援外部使用者存取所需的每一筆記錄的詳細資訊，請參閱 [決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="85feb-119">For details about each record required to support external user access, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a><span data-ttu-id="85feb-120">將 DNS 尾碼新增至未加入網域之 Edge Server 上的電腦名稱</span><span class="sxs-lookup"><span data-stu-id="85feb-120">To add the DNS suffix to the computer name on an Edge Server that is not joined to a domain</span></span>

1.  <span data-ttu-id="85feb-121">在電腦上，按一下 **[開始]**，並在 **[電腦]** 上按一下滑鼠右鍵，然後按一下 **[內容]**。</span><span class="sxs-lookup"><span data-stu-id="85feb-121">On the computer, click **Start**, right-click **Computer**, and then click **Properties**.</span></span>

2.  <span data-ttu-id="85feb-122">在 **[電腦名稱、網域及工作群組設定]** 下，按一下 **[變更設定]**。</span><span class="sxs-lookup"><span data-stu-id="85feb-122">Under **Computer name, domain, and workgroup settings**, click **Change settings**.</span></span>

3.  <span data-ttu-id="85feb-123">在 **[電腦名稱]** 索引標籤上，按一下 **[變更]**。</span><span class="sxs-lookup"><span data-stu-id="85feb-123">On the **Computer Name** tab, click **Change**.</span></span>

4.  <span data-ttu-id="85feb-124">在 **[電腦名稱/網域變更]** 中，按一下 **[其他]**。</span><span class="sxs-lookup"><span data-stu-id="85feb-124">In **Computer Name/Domain Changes**, click **More**.</span></span>

5.  <span data-ttu-id="85feb-125">在 **[DNS 尾碼和 NetBIOS 電腦名稱]** 的 **[這部電腦的主要 DNS 尾碼]** 中，輸入內部網域的名稱 (例如，corp.contoso.com)，然後按三次 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="85feb-125">In **DNS Suffix and NetBIOS Computer Name**, in **Primary DNS suffix of this computer**, type the name of your internal domain (for example, corp.contoso.com), and then click **OK** three times.</span></span>

6.  <span data-ttu-id="85feb-126">重新啟動電腦。</span><span class="sxs-lookup"><span data-stu-id="85feb-126">Restart the computer.</span></span>

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a><span data-ttu-id="85feb-127">建立 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="85feb-127">To create a DNS SRV record</span></span>

1.  <span data-ttu-id="85feb-128">在適當的 DNS 伺服器上，按一下 [ **開始**]，按一下 [ **控制台**]，按一下 [系統 **管理工具**]，然後按一下 [ **DNS**]。</span><span class="sxs-lookup"><span data-stu-id="85feb-128">On the appropriate DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="85feb-129">您必須設定 DNS，讓遠端使用者和同盟協力廠商能夠使用： 1) 外部 DNS 查閱的外部 DNS 專案;2) 周邊網路中的 Edge Server 所使用的 DNS 查閱專案， (也稱為 DMZ、隔離區域及遮罩式子網) （包括執行 Lync Server 2013 的內部伺服器記錄）;和 3) 執行 Lync Server 2013 的內部用戶端和伺服器查閱的內部 DNS 專案。</span><span class="sxs-lookup"><span data-stu-id="85feb-129">You need to configure DNS so that there are: 1) external DNS entries for external DNS lookups by remote users and federated partners; 2) entries for DNS lookups for use by the Edge Servers within the perimeter network (also known as DMZ, demilitarized zone, and screened subnet), including A records for the internal servers running Lync Server 2013; and 3) internal DNS entries for lookups by the internal clients and servers running Lync Server 2013.</span></span>

    
    </div>

2.  <span data-ttu-id="85feb-130">在 SIP 網域的主控台樹中，展開 [ **正向對應區域**]，然後在安裝 Lync Server 2013 的網域上按一下滑鼠右鍵。</span><span class="sxs-lookup"><span data-stu-id="85feb-130">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain where Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="85feb-131">按一下 [ **其他新記錄**]。</span><span class="sxs-lookup"><span data-stu-id="85feb-131">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="85feb-132">在 [ **選取資源記錄類型**] 中，輸入 [ \*\*服務位置 (SRV) \*\*]，然後按一下 [ **建立記錄**]。</span><span class="sxs-lookup"><span data-stu-id="85feb-132">In **Select a resource record type**, type **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="85feb-133">提供 DNS SRV 記錄的所有必要資訊。</span><span class="sxs-lookup"><span data-stu-id="85feb-133">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-create-a-dns-a-record"></a><span data-ttu-id="85feb-134">建立 DNS A 記錄</span><span class="sxs-lookup"><span data-stu-id="85feb-134">To create a DNS A record</span></span>

1.  <span data-ttu-id="85feb-135">在 DNS 伺服器上，按一下 [ **開始**]，按一下 [ **控制台**]，按一下 [系統 **管理工具**]，然後按一下 [ **DNS**]。</span><span class="sxs-lookup"><span data-stu-id="85feb-135">On the DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="85feb-136">在 SIP 網域的主控台樹中，展開 [ **正向對應區域**]，然後在安裝 Lync Server 2013 的網域上按一下滑鼠右鍵。</span><span class="sxs-lookup"><span data-stu-id="85feb-136">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="85feb-137">按一下 [ \*\*新增主機 () \*\*]。</span><span class="sxs-lookup"><span data-stu-id="85feb-137">Click **New Host (A)**.</span></span>

4.  <span data-ttu-id="85feb-138">提供 DNS SRV 記錄的所有必要資訊。</span><span class="sxs-lookup"><span data-stu-id="85feb-138">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-verify-a-dns-record"></a><span data-ttu-id="85feb-139">驗證 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="85feb-139">To verify a DNS record</span></span>

1.  <span data-ttu-id="85feb-140">登入網域中的用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="85feb-140">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="85feb-141">按一下 **[開始]**，再按一下 **[執行]**。</span><span class="sxs-lookup"><span data-stu-id="85feb-141">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="85feb-142">在命令提示字元中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="85feb-142">At the command prompt, run the following command:</span></span>
    
        nslookup <FQDN edge interface>

4.  <span data-ttu-id="85feb-143">請確認您收到的回復可解析為 FQDN 的適當 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="85feb-143">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="85feb-144">另請參閱</span><span class="sxs-lookup"><span data-stu-id="85feb-144">See Also</span></span>


[<span data-ttu-id="85feb-145">建立 DNS SRV 記錄，以與主控 Exchange UM 整合</span><span class="sxs-lookup"><span data-stu-id="85feb-145">Create a DNS SRV record for integration with hosted Exchange UM</span></span>](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[<span data-ttu-id="85feb-146">決定 Lync Server 2013 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="85feb-146">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

