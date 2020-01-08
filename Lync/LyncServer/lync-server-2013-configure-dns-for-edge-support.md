---
title: Lync Server 2013：設定 Edge 支援的 DNS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DNS for edge support
ms:assetid: 955493e6-aa29-424d-bb81-1ef87b3b15e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398756(v=OCS.15)
ms:contentKeyID: 48184894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79e1712b3425c7cce4020799b37f10aba894aeb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a><span data-ttu-id="a229f-102">在 Lync Server 2013 中設定 Edge 支援的 DNS</span><span class="sxs-lookup"><span data-stu-id="a229f-102">Configure DNS for edge support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a229f-103">_**主題上次修改日期：** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="a229f-103">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="a229f-104">您必須設定內部和外部邊緣介面的網域名稱系統（DNS）記錄，包括 Edge 伺服器與反向 proxy 介面。</span><span class="sxs-lookup"><span data-stu-id="a229f-104">You must configure Domain Name System (DNS) records for internal and external edge interfaces, including both Edge Server and reverse proxy interfaces.</span></span> <span data-ttu-id="a229f-105">根據預設，Edge 伺服器不會加入網域，也不會有完整的功能變數名稱（完整功能變數名稱）。</span><span class="sxs-lookup"><span data-stu-id="a229f-105">By default, Edge Servers are not joined to a domain and will not have a fully qualified domain name (fully qualified domain name).</span></span> <span data-ttu-id="a229f-106">Edge 伺服器只是由短（電腦）名稱所參照，而不是以完整的功能變數名稱來引用。</span><span class="sxs-lookup"><span data-stu-id="a229f-106">The Edge Server is only referred to by the short (machine) name, not a fully qualified domain name.</span></span> <span data-ttu-id="a229f-107">不過，拓撲產生器使用 Fqdn，而不是簡稱。</span><span class="sxs-lookup"><span data-stu-id="a229f-107">However, Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="a229f-108">Edge 伺服器的名稱必須與拓撲建立器所使用的 FQDN 相符。</span><span class="sxs-lookup"><span data-stu-id="a229f-108">The name of the Edge Server must match the FQDN used by Topology Builder.</span></span> <span data-ttu-id="a229f-109">若要這樣做，您可以定義一個 DNS 尾碼，在與電腦名稱稱結合時，會產生預期的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a229f-109">To do this, you define a DNS suffix that, when combined with the machine name, results in the expected FQDN.</span></span> <span data-ttu-id="a229f-110">您可以在 [電腦名稱稱] 和 [Edge 伺服器（未加入網域）] 中，使用下列程式，將 DNS 尾碼新增到電腦名稱稱中。</span><span class="sxs-lookup"><span data-stu-id="a229f-110">Use the following procedure in “To add the DNS suffix to the computer name on and Edge Server that is not joined to a domain” to add the DNS suffix to the computer name.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a229f-111">根據預設，DNS 會使用迴圈法演算法來旋轉查詢答案中傳回的資源記錄資料順序，這些記錄是針對已查詢的 DNS 功能變數名稱，有多個相同類型的資源記錄。</span><span class="sxs-lookup"><span data-stu-id="a229f-111">By default, DNS uses a round robin algorithm to rotate the order of resource record data returned in query answers where multiple resource records of the same type exist for a queried DNS domain name.</span></span> <span data-ttu-id="a229f-112">Lync Server 2013 DNS 負載平衡，視 dns 負載平衡機制的一部分而定。</span><span class="sxs-lookup"><span data-stu-id="a229f-112">Lync Server 2013 DNS load balancing, depends on DNS round-robin as a part of the DNS Load Balancing mechanism.</span></span> <span data-ttu-id="a229f-113">確認沒有停用迴圈設定。</span><span class="sxs-lookup"><span data-stu-id="a229f-113">Verify that round-robin setting has not been disabled.</span></span> <span data-ttu-id="a229f-114">如果您使用的 DNS 伺服器不是執行 Windows 作業系統，請確認已啟用 [迴圈式資源記錄排序]。</span><span class="sxs-lookup"><span data-stu-id="a229f-114">If you are using a DNS server that is not running a Windows operating system, verify that round-robin resource record ordering is enabled.</span></span>



</div>

<span data-ttu-id="a229f-115">您可以在「**建立 DNS SRV 記錄**」中使用下列程式來建立並驗證每個 DNS srv 記錄。</span><span class="sxs-lookup"><span data-stu-id="a229f-115">Use the following procedures in “**To create a DNS SRV record**” to create and verify each DNS SRV record.</span></span> <span data-ttu-id="a229f-116">使用 [**建立 DNS a 記錄**] 中的程式，定義外部使用者存取所需的 DNS a 記錄。</span><span class="sxs-lookup"><span data-stu-id="a229f-116">Use the procedure in “**To create a DNS A record**” to define the DNS A records required for external user access.</span></span> <span data-ttu-id="a229f-117">若要確認記錄是否已正確設定且正常運作，請參閱本主題中的「**驗證 DNS 記錄**」。</span><span class="sxs-lookup"><span data-stu-id="a229f-117">To confirm that the records are configured and working correctly, see “**To verify a DNS record**” in this topic.</span></span> <span data-ttu-id="a229f-118">如需支援外部使用者存取所需的每一筆記錄的詳細資訊，請參閱[判斷 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a229f-118">For details about each record required to support external user access, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a><span data-ttu-id="a229f-119">在未加入網域的邊緣伺服器上將 DNS 尾碼新增到電腦名稱稱</span><span class="sxs-lookup"><span data-stu-id="a229f-119">To add the DNS suffix to the computer name on an Edge Server that is not joined to a domain</span></span>

1.  <span data-ttu-id="a229f-120">在電腦上，按一下 [**開始**]，以滑鼠右鍵按一下 [**電腦**]，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="a229f-120">On the computer, click **Start**, right-click **Computer**, and then click **Properties**.</span></span>

2.  <span data-ttu-id="a229f-121">在 [**電腦名稱稱、網域及工作組設定**] 底下，按一下 [**變更設定**]。</span><span class="sxs-lookup"><span data-stu-id="a229f-121">Under **Computer name, domain, and workgroup settings**, click **Change settings**.</span></span>

3.  <span data-ttu-id="a229f-122">按一下 [**電腦名稱稱**] 索引標籤上的 [**變更**]。</span><span class="sxs-lookup"><span data-stu-id="a229f-122">On the **Computer Name** tab, click **Change**.</span></span>

4.  <span data-ttu-id="a229f-123">在 [**電腦名稱稱/網域變更**] 中，按一下 [**更多**]。</span><span class="sxs-lookup"><span data-stu-id="a229f-123">In **Computer Name/Domain Changes**, click **More**.</span></span>

5.  <span data-ttu-id="a229f-124">在 [ **DNS 尾碼及 NetBIOS 電腦名稱稱**]**的 [此電腦的主要 DNS 尾碼**] 中，輸入您的內部網功能變數名稱稱（例如，corp.contoso.com），然後按一下 **[確定]** 三次。</span><span class="sxs-lookup"><span data-stu-id="a229f-124">In **DNS Suffix and NetBIOS Computer Name**, in **Primary DNS suffix of this computer**, type the name of your internal domain (for example, corp.contoso.com), and then click **OK** three times.</span></span>

6.  <span data-ttu-id="a229f-125">重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="a229f-125">Restart the computer.</span></span>

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a><span data-ttu-id="a229f-126">建立 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="a229f-126">To create a DNS SRV record</span></span>

1.  <span data-ttu-id="a229f-127">在適當的 DNS 伺服器上，按一下 [**開始**]，按一下 [**控制台**]，按一下 [**管理工具**]，然後按一下 [ **DNS**]。</span><span class="sxs-lookup"><span data-stu-id="a229f-127">On the appropriate DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a229f-128">您需要設定 DNS，讓遠端使用者和聯盟夥伴的外部 DNS 查閱都有：1）外部 DNS 專案;2）用於周邊網路（也稱為 DMZ、網路隔離區域及遮罩子網）中的邊緣伺服器所使用的 DNS 查閱專案，包括執行 Lync Server 2013 的內部伺服器的記錄;與3）內部 DNS 專案，可供執行 Lync Server 2013 的內部用戶端和伺服器進行查閱。</span><span class="sxs-lookup"><span data-stu-id="a229f-128">You need to configure DNS so that there are: 1) external DNS entries for external DNS lookups by remote users and federated partners; 2) entries for DNS lookups for use by the Edge Servers within the perimeter network (also known as DMZ, demilitarized zone, and screened subnet), including A records for the internal servers running Lync Server 2013; and 3) internal DNS entries for lookups by the internal clients and servers running Lync Server 2013.</span></span>

    
    </div>

2.  <span data-ttu-id="a229f-129">在您 SIP 網域的 [主控台樹] 中，展開 [**轉寄查閱區域**]，然後以滑鼠右鍵按一下安裝 Lync Server 2013 的網域。</span><span class="sxs-lookup"><span data-stu-id="a229f-129">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain where Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="a229f-130">按一下 [**其他新記錄**]。</span><span class="sxs-lookup"><span data-stu-id="a229f-130">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="a229f-131">在 [**選取資源記錄類型**] 中，輸入 [**服務位置（SRV）**]，然後按一下 [**建立記錄**]。</span><span class="sxs-lookup"><span data-stu-id="a229f-131">In **Select a resource record type**, type **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="a229f-132">提供 DNS SRV 記錄所需的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="a229f-132">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-create-a-dns-a-record"></a><span data-ttu-id="a229f-133">建立 DNS A 記錄</span><span class="sxs-lookup"><span data-stu-id="a229f-133">To create a DNS A record</span></span>

1.  <span data-ttu-id="a229f-134">在 DNS 伺服器上，按一下 [**開始**]，按一下 [**控制台**]，按一下 [**管理工具**]，然後按一下 [ **DNS**]。</span><span class="sxs-lookup"><span data-stu-id="a229f-134">On the DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="a229f-135">在您 SIP 網域的 [主控台樹] 中，展開 [**轉寄查閱區域**]，然後以滑鼠右鍵按一下安裝 Lync Server 2013 的網域。</span><span class="sxs-lookup"><span data-stu-id="a229f-135">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="a229f-136">按一下 **[新增主機（A）**]。</span><span class="sxs-lookup"><span data-stu-id="a229f-136">Click **New Host (A)**.</span></span>

4.  <span data-ttu-id="a229f-137">提供 DNS SRV 記錄所需的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="a229f-137">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-verify-a-dns-record"></a><span data-ttu-id="a229f-138">驗證 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="a229f-138">To verify a DNS record</span></span>

1.  <span data-ttu-id="a229f-139">登入網域中的用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="a229f-139">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="a229f-140">按一下 [**開始**]，然後按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="a229f-140">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="a229f-141">在命令提示字元中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="a229f-141">At the command prompt, run the following command:</span></span>
    
        nslookup <FQDN edge interface>

4.  <span data-ttu-id="a229f-142">確認您收到的回復會解析為適當的 FQDN IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a229f-142">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a229f-143">請參閱</span><span class="sxs-lookup"><span data-stu-id="a229f-143">See Also</span></span>


[<span data-ttu-id="a229f-144">針對與主控 Exchange UM 的整合建立 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="a229f-144">Create a DNS SRV record for integration with hosted Exchange UM</span></span>](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[<span data-ttu-id="a229f-145">針對 Lync Server 2013 判定 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="a229f-145">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

