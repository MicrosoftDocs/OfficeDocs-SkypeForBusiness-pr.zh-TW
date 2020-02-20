---
title: Lync Server 2013： 設定網路介面卡
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network adapters
ms:assetid: 6519ed80-020f-47a3-851c-03dea5eac5d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429707(v=OCS.15)
ms:contentKeyID: 48184320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd2609c8b8a900b9c970943a2f24bc0462eafb85
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147666"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-network-adapters-in-lync-server-2013"></a><span data-ttu-id="7d147-102">在 Lync Server 2013 中設定網路介面卡</span><span class="sxs-lookup"><span data-stu-id="7d147-102">Configure network adapters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d147-103">_**上次修改主題：** 2013年-11-07_</span><span class="sxs-lookup"><span data-stu-id="7d147-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="7d147-104">您必須指派一或多個 IP 位址給外部網路介面卡，同時至少指派一個 IP 位址給內部網路介面卡。</span><span class="sxs-lookup"><span data-stu-id="7d147-104">You must assign one or more IP addresses to the external network adapter and at least one IP address to the internal network adapter.</span></span>

<span data-ttu-id="7d147-105">下列程序，在執行 Forefront Threat Management Gateway (TMG) 2010年或網際網路資訊伺服器應用程式要求路由傳送的伺服器會有兩個網路介面卡：</span><span class="sxs-lookup"><span data-stu-id="7d147-105">In the following procedures, the server running either Forefront Threat Management Gateway (TMG) 2010 or Internet Information Server Application Request Routing has two network adapters:</span></span>

  - <span data-ttu-id="7d147-106">公用 (外部) 網路介面卡，適用於嘗試連線至您的網站之用戶端 (亦即，通常是透過網際網路)。</span><span class="sxs-lookup"><span data-stu-id="7d147-106">A public, or external, network adapter, for clients that attempt to connect to your website (that is, usually over the Internet).</span></span>

  - <span data-ttu-id="7d147-107">私用，或內部網路介面，執行 Lync Server 的內部伺服器的主控 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="7d147-107">A private, or internal, network interface, for internal servers running Lync Server that are hosting Web Services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7d147-108">類似於 Edge Server，您的預設閘道上設定外部網路介面卡僅。</span><span class="sxs-lookup"><span data-stu-id="7d147-108">Similar to the Edge Servers, you set the default gateway on the external network adapter only.</span></span> <span data-ttu-id="7d147-109">預設閘道會是將流量導向網際網路之路由器或對外防火牆的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7d147-109">The default gateway will be the IP address of the router or external facing firewall that directs traffic to the Internet.</span></span> <span data-ttu-id="7d147-110">對於從反向 Proxy 至對內網路介面卡的流量，必須將持續的靜態路由 (例如 Windows Server 中的 route 命令) 使用於包含由 Web 發行規則參照之伺服器的所有子網路。</span><span class="sxs-lookup"><span data-stu-id="7d147-110">For traffic that is destined from the reverse proxy to the internal facing network adaptor, you must use persistent static routes (such as the route command in Windows Server) for all subnets containing servers referenced by the web publishing rules.</span></span> <span data-ttu-id="7d147-111">設定一個持續的路由，不會造成成為路由器的電腦。</span><span class="sxs-lookup"><span data-stu-id="7d147-111">Setting a persistent route does not cause the computer to become a router.</span></span> <span data-ttu-id="7d147-112">如果未啟用 IP 轉寄，電腦做只以將特定目的地是另一個網路，以適當的介面的流量導向。</span><span class="sxs-lookup"><span data-stu-id="7d147-112">If IP forwarding is not enabled, the computer is acting only to direct specific traffic destined for another network to the appropriate interface.</span></span> <span data-ttu-id="7d147-113">這基本上設定兩個閘道 – 1 才能做為指向的外部網路，，一個用於內部介面並登入該路由器或其他網路流量的預設值。</span><span class="sxs-lookup"><span data-stu-id="7d147-113">This is essentially setting two gateways – one as the default pointing to the external networks, and one for traffic destined to the internal interface and on to a router or other network.</span></span><BR><span data-ttu-id="7d147-p102">然而，如果將網路的路由器設定為摘要路由，可能不需要為所有子網路建立持續路由。建立連線至已定義路由器之網路的持續路由，然後使用該路由器為預設閘道。如果不確定網路的設定方式，而且對需要建立的持續路由需要指引，請諮詢您公司的網路工程師。</span><span class="sxs-lookup"><span data-stu-id="7d147-p102">However, creating persistent routes for all subnets may not be necessary if your network’s routers are configured to summarize routes. Create a persistent route to the network where the router is defined and use the router as the default gateway. If you are not sure how your network is configured and need guidance on what persistent routes need to be created, consult with your company’s Network Engineers.</span></span><BR><span data-ttu-id="7d147-117">反向 proxy 必須能夠解析內部 Director 或前端伺服器的 DNS 主機 (A) 記錄，並在網頁發行規則中使用下一個躍點集區 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="7d147-117">The reverse proxy must be able to resolve the DNS host (A) records for the internal Director or Front End Server and next hop pool FQDNs used in the web publishing rules.</span></span> <span data-ttu-id="7d147-118">就像 Edge Server，基於安全性考量，建議您不需設定為使用位於內部網路 DNS 伺服器的反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="7d147-118">As with the Edge Servers, for security reasons, we recommend that you do not configure a reverse proxy to use a DNS server located in the internal network.</span></span> <span data-ttu-id="7d147-119">這表示在周邊中需要 DNS 伺服器，或者，需要反向 Proxy 上的 HOST 檔案項目會將這每一個 FQDN 解析為伺服器的內部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7d147-119">This means you either need DNS servers in the perimeter, or you need HOSTS file entries on the reverse proxy that resolves each of these FQDNs to the internal IP address of the servers.</span></span>



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a><span data-ttu-id="7d147-120">設定反向 Proxy 電腦的網路介面卡</span><span class="sxs-lookup"><span data-stu-id="7d147-120">To configure the network adapter cards on the reverse proxy computer</span></span>

1.  <span data-ttu-id="7d147-121">在 Windows Server 2008、 Windows Server 2008 R2、 Windows Server 2012 或 Windows Server 2012 R2 伺服器正在執行與反向 proxy，開啟 [按一下**啟動**，指向 **[控制台]**、 [**網路和共用中心**]，然後按一下 [**變更介面卡設定**[**變更介面卡設定**]。</span><span class="sxs-lookup"><span data-stu-id="7d147-121">On the Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 server running as the reverse proxy, open **Change Adapter Settings** by clicking **Start**, pointing to **Control Panel**, clicking **Network and Sharing Center**, and then clicking **Change Adapter Settings**.</span></span>

2.  <span data-ttu-id="7d147-122">以滑鼠右鍵按一下要用於外部介面的外部網路連線，然後按一下 **[內容]**。</span><span class="sxs-lookup"><span data-stu-id="7d147-122">Right-click the external network connection that you want to use for the external interface, and then click **Properties**.</span></span>

3.  <span data-ttu-id="7d147-123">在 **[內容]** 頁面上，按一下 **[網路]** 索引標籤，並按一下 **[這個連線使用下列項目]** 清單中的 **[網際網路通訊協定第 4 版 (TCP/IPv4)]**，然後按一下 **[內容]**。</span><span class="sxs-lookup"><span data-stu-id="7d147-123">On the **Properties** page, click the **Networking** tab, click **Internet Protocol Version 4 (TCP/IPv4)** in the **This connection uses the following items** list, and then click **Properties**.</span></span>

4.  <span data-ttu-id="7d147-124">在 **[網際網路通訊協定 (TCP/IP) 內容]** 頁面上，視需要設定網路介面卡所連接網路子網路的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7d147-124">On the **Internet Protocol (TCP/IP) Properties** page, configure the IP addresses as appropriate for the network subnet to which the network adapter is attached.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7d147-125">如果反向 proxy 已經由其他應用程式，如使用 HTTPS/TCP/443，發佈 Outlook Web Access 中，您 [要新增另一個 IP 位址，以便您可以將 Lync Server 2013 Web 服務，在 HTTPS/TCP/443 上發佈而不干擾現有規則及 web 接聽程式，或您要將新的外部 FQDN 名稱新增至主體替代名稱的其中一個取代現有的憑證。</span><span class="sxs-lookup"><span data-stu-id="7d147-125">If the reverse proxy is already being used by other applications that use HTTPS/TCP/443, such as for publishing Outlook Web Access, you either need to add another IP address so that you can publish the Lync Server 2013 Web Services on HTTPS/TCP/443 without interfering with the existing rules and web listeners, or you need to replace the existing certificate with one that adds the new external FQDN names to the subject alternative name.</span></span>

    
    </div>

5.  <span data-ttu-id="7d147-126">按一下 **[確定]**，然後再按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="7d147-126">Click **OK**, and then click **OK**.</span></span>

6.  <span data-ttu-id="7d147-127">在 **[網路連線]** 中，以滑鼠右鍵按一下要用於內部介面的內部網路連線，然後按一下 **[內容]**。</span><span class="sxs-lookup"><span data-stu-id="7d147-127">In **Network Connections**, right-click the internal network connection that you want to use for the internal interface, and then click **Properties**.</span></span>

7.  <span data-ttu-id="7d147-128">重複步驟 3 到 5，設定內部網路連線。</span><span class="sxs-lookup"><span data-stu-id="7d147-128">Repeat steps 3 through 5 to configure the internal network connection.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

