---
title: Lync Server 2013：設定 DNS 主機記錄
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e96c23741430f17b6d343606526df230f74c032
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537130"
---
# <a name="configure-dns-host-records-for-lync-server-2013"></a><span data-ttu-id="96e37-102">設定 Lync Server 2013 的 DNS 主機記錄</span><span class="sxs-lookup"><span data-stu-id="96e37-102">Configure DNS Host records for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96e37-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="96e37-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="96e37-104">要成功完成此程序，必須至少以 Domain Admins 群組成員或 DnsAdmins 群組成員的身分登入伺服器或網域。</span><span class="sxs-lookup"><span data-stu-id="96e37-104">To successfully complete this procedure, you should be logged on to the server or domain at minimum as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<div>

## <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="96e37-105">設定 DNS 主機 A 記錄</span><span class="sxs-lookup"><span data-stu-id="96e37-105">To configure DNS Host A records</span></span>

1.  <span data-ttu-id="96e37-106">在網域名稱系統 (DNS) 伺服器上，依序按一下 **[開始]**、**[系統管理工具]** 和 **[DNS]**。</span><span class="sxs-lookup"><span data-stu-id="96e37-106">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="96e37-107">在您網域的主控台樹中，展開 [ **正向對應區域**]，然後在將安裝 Lync Server 2013 的網域上按一下滑鼠右鍵。</span><span class="sxs-lookup"><span data-stu-id="96e37-107">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="96e37-108">按一下 **[新增主機 (A 或 AAAA)]**。</span><span class="sxs-lookup"><span data-stu-id="96e37-108">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="96e37-109">按一下 **[名稱]**，然後輸入集區的主機名稱 (網域名稱會從記錄定義所在的區域取得，而不需輸入為 A 記錄的一部分)。</span><span class="sxs-lookup"><span data-stu-id="96e37-109">Click **Name**, type the host name for the pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="96e37-110">按一下 [ **IP 位址**]，輸入前端集區之負載平衡器的虛擬 IP (VIP) 。</span><span class="sxs-lookup"><span data-stu-id="96e37-110">Click **IP Address**, type the virtual IP (VIP) of the load balancer for the Front End pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="96e37-111">在使用 Director 集區的部署中，簡單 URL 的主機 (A) 記錄應指向 Director 負載平衡器的 VIP。</span><span class="sxs-lookup"><span data-stu-id="96e37-111">In deployments that use a Director pool, the host (A) records for the simple URLs should point to the VIP of the Director load balancer.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="96e37-p101">如果您僅部署一個不使用負載平衡器就連線至拓撲的 Enterprise Edition Server 或 Director，或是您部署了一部 Standard Edition Server，請輸入 Enterprise Edition Server、Standard Edition Server 或 Director 的 IP 位址。如果您要在集區中部署多個 Enterprise Edition Server 或 Director，則需要負載平衡器。負載平衡器無法用於 Standard Edition Server。</span><span class="sxs-lookup"><span data-stu-id="96e37-p101">If you deploy only one Enterprise Edition server or Director that is connected to the topology without a load balancer, or if you deploy a Standard Edition server, type the IP address of the Enterprise Edition server, Standard Edition server, or Director. A load balancer is required if you deploy more than one Enterprise Edition server or Director in a pool. Load balancers are not used with Standard Edition servers.</span></span>

    
    </div>

6.  <span data-ttu-id="96e37-115">按一下 **[新增主機]**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="96e37-115">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="96e37-116">如果要建立其他的 A 記錄，請重複步驟 4 和 5。</span><span class="sxs-lookup"><span data-stu-id="96e37-116">To create an additional A record, repeat steps 4 and 5.</span></span>

8.  <span data-ttu-id="96e37-117">完成建立所需的所有 A 記錄時，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="96e37-117">When you are finished creating all the A records that you need, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

