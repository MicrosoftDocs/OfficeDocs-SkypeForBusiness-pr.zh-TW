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
ms.openlocfilehash: b74da23cb0139a982a30207b61032f043f795b76
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-host-records-for-lync-server-2013"></a><span data-ttu-id="a3929-102">為 Lync Server 2013 設定 DNS 主機記錄</span><span class="sxs-lookup"><span data-stu-id="a3929-102">Configure DNS Host records for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3929-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="a3929-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="a3929-104">若要成功完成此程式，您應該以網域系統管理員群組或 DnsAdmins 群組的成員的身分登入伺服器或網域。</span><span class="sxs-lookup"><span data-stu-id="a3929-104">To successfully complete this procedure, you should be logged on to the server or domain at minimum as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<div>

## <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="a3929-105">設定 DNS 主機 A 記錄</span><span class="sxs-lookup"><span data-stu-id="a3929-105">To configure DNS Host A records</span></span>

1.  <span data-ttu-id="a3929-106">在 [網域名稱系統（DNS）] 伺服器上，按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **DNS**]。</span><span class="sxs-lookup"><span data-stu-id="a3929-106">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="a3929-107">在您網域的 [主控台樹] 中，展開 [**轉寄查閱區域**]，然後以滑鼠右鍵按一下將安裝 Lync Server 2013 的網域。</span><span class="sxs-lookup"><span data-stu-id="a3929-107">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="a3929-108">按一下 **[新增主機（A 或 AAAA）**]。</span><span class="sxs-lookup"><span data-stu-id="a3929-108">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="a3929-109">按一下 [**名稱**]，輸入該池的主機名稱（功能變數名稱是從定義該記錄的區域中假設，而且不需要輸入為 A 記錄的一部分）。</span><span class="sxs-lookup"><span data-stu-id="a3929-109">Click **Name**, type the host name for the pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="a3929-110">按一下 [ **IP 位址**]，輸入前端池的負載平衡器虛擬 IP （VIP）。</span><span class="sxs-lookup"><span data-stu-id="a3929-110">Click **IP Address**, type the virtual IP (VIP) of the load balancer for the Front End pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a3929-111">在使用主管池的部署中，簡單 Url 的主機（A）記錄應該指向控制器負載平衡器的 VIP。</span><span class="sxs-lookup"><span data-stu-id="a3929-111">In deployments that use a Director pool, the host (A) records for the simple URLs should point to the VIP of the Director load balancer.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a3929-112">如果您只部署一個不含負載平衡器即可連線至拓撲的 Enterprise Edition 伺服器或主管，或者如果您部署的是標準版 server，請輸入企業版 server、標準版伺服器或控制器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a3929-112">If you deploy only one Enterprise Edition server or Director that is connected to the topology without a load balancer, or if you deploy a Standard Edition server, type the IP address of the Enterprise Edition server, Standard Edition server, or Director.</span></span> <span data-ttu-id="a3929-113">如果您在一個池中部署多個企業版伺服器或控制器，則需要負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="a3929-113">A load balancer is required if you deploy more than one Enterprise Edition server or Director in a pool.</span></span> <span data-ttu-id="a3929-114">負載平衡器不搭配標準版伺服器使用。</span><span class="sxs-lookup"><span data-stu-id="a3929-114">Load balancers are not used with Standard Edition servers.</span></span>

    
    </div>

6.  <span data-ttu-id="a3929-115">按一下 [**新增主機**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a3929-115">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="a3929-116">若要建立額外的 A 記錄，請重複步驟4和5。</span><span class="sxs-lookup"><span data-stu-id="a3929-116">To create an additional A record, repeat steps 4 and 5.</span></span>

8.  <span data-ttu-id="a3929-117">當您完成建立所需的所有記錄之後，按一下 [**完成**]。</span><span class="sxs-lookup"><span data-stu-id="a3929-117">When you are finished creating all the A records that you need, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

