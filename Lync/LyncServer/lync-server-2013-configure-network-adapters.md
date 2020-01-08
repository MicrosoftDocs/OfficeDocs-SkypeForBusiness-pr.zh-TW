---
title: Lync Server 2013：設定網路介面卡
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network adapters
ms:assetid: 6519ed80-020f-47a3-851c-03dea5eac5d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429707(v=OCS.15)
ms:contentKeyID: 48184320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3469e9d5fa3f7aeb45bc8f35ff692d97d09b8481
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-adapters-in-lync-server-2013"></a><span data-ttu-id="3ff43-102">在 Lync Server 2013 中設定網路介面卡</span><span class="sxs-lookup"><span data-stu-id="3ff43-102">Configure network adapters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ff43-103">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="3ff43-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="3ff43-104">您必須將一個或多個 IP 位址指派給外部網路介面卡，並將至少一個 IP 位址指派給內部網路介面卡。</span><span class="sxs-lookup"><span data-stu-id="3ff43-104">You must assign one or more IP addresses to the external network adapter and at least one IP address to the internal network adapter.</span></span>

<span data-ttu-id="3ff43-105">在下列程式中，執行 Forefront 威脅管理閘道（TMG）2010或 Internet Information Server 應用程式要求路由的伺服器會有兩個網路介面卡：</span><span class="sxs-lookup"><span data-stu-id="3ff43-105">In the following procedures, the server running either Forefront Threat Management Gateway (TMG) 2010 or Internet Information Server Application Request Routing has two network adapters:</span></span>

  - <span data-ttu-id="3ff43-106">公用或外部網路介面卡，適用于嘗試連線至您的網站的用戶端（通常是透過網際網路）。</span><span class="sxs-lookup"><span data-stu-id="3ff43-106">A public, or external, network adapter, for clients that attempt to connect to your website (that is, usually over the Internet).</span></span>

  - <span data-ttu-id="3ff43-107">一種專用或內部網路介面，適用于執行承載 Web 服務之 Lync Server 的內部伺服器。</span><span class="sxs-lookup"><span data-stu-id="3ff43-107">A private, or internal, network interface, for internal servers running Lync Server that are hosting Web Services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3ff43-108">與邊緣伺服器類似，您只能在外部網路介面卡上設定預設閘道。</span><span class="sxs-lookup"><span data-stu-id="3ff43-108">Similar to the Edge Servers, you set the default gateway on the external network adapter only.</span></span> <span data-ttu-id="3ff43-109">預設閘道將是路由器的 IP 位址，或將流量導向網際網路的外部防火牆。</span><span class="sxs-lookup"><span data-stu-id="3ff43-109">The default gateway will be the IP address of the router or external facing firewall that directs traffic to the Internet.</span></span> <span data-ttu-id="3ff43-110">針對寄件者為從反向 proxy 傳送到內部面向內部網路介面卡的流量，您必須針對所有包含 web 發佈規則所參照之伺服器的子網，使用永久靜態路由（例如 Windows Server 中的 route 命令）。</span><span class="sxs-lookup"><span data-stu-id="3ff43-110">For traffic that is destined from the reverse proxy to the internal facing network adaptor, you must use persistent static routes (such as the route command in Windows Server) for all subnets containing servers referenced by the web publishing rules.</span></span> <span data-ttu-id="3ff43-111">設定持久路由不會導致電腦成為路由器。</span><span class="sxs-lookup"><span data-stu-id="3ff43-111">Setting a persistent route does not cause the computer to become a router.</span></span> <span data-ttu-id="3ff43-112">如果沒有啟用 IP 轉寄，電腦只會作用至將特定通信量傳送給另一個網路至適當的介面。</span><span class="sxs-lookup"><span data-stu-id="3ff43-112">If IP forwarding is not enabled, the computer is acting only to direct specific traffic destined for another network to the appropriate interface.</span></span> <span data-ttu-id="3ff43-113">這主要是設定兩個閘道，一個是指向外部網路的預設閘道，另一個是傳送給內部介面並移至路由器或其他網路的通信量。</span><span class="sxs-lookup"><span data-stu-id="3ff43-113">This is essentially setting two gateways – one as the default pointing to the external networks, and one for traffic destined to the internal interface and on to a router or other network.</span></span><BR><span data-ttu-id="3ff43-114">不過，如果您的網路路由器設定為 [摘要路由]，則可能不需要為所有子網建立持久路由。</span><span class="sxs-lookup"><span data-stu-id="3ff43-114">However, creating persistent routes for all subnets may not be necessary if your network’s routers are configured to summarize routes.</span></span> <span data-ttu-id="3ff43-115">建立一個持久路由至定義路由器的網路，然後使用路由器作為預設閘道。</span><span class="sxs-lookup"><span data-stu-id="3ff43-115">Create a persistent route to the network where the router is defined and use the router as the default gateway.</span></span> <span data-ttu-id="3ff43-116">如果您不確定網路的設定方式，而且需要建立何種持久路由的指導方針，請諮詢貴公司的網路工程師。</span><span class="sxs-lookup"><span data-stu-id="3ff43-116">If you are not sure how your network is configured and need guidance on what persistent routes need to be created, consult with your company’s Network Engineers.</span></span><BR><span data-ttu-id="3ff43-117">反向 proxy 必須能夠解析內部控制器或前端伺服器的 DNS 主機（A）記錄，以及 web 發佈規則中使用的下一個躍點池 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="3ff43-117">The reverse proxy must be able to resolve the DNS host (A) records for the internal Director or Front End Server and next hop pool FQDNs used in the web publishing rules.</span></span> <span data-ttu-id="3ff43-118">與邊緣伺服器一樣，出於安全性考慮，我們建議您不要將反向 proxy 設定為使用位於內部網路中的 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="3ff43-118">As with the Edge Servers, for security reasons, we recommend that you do not configure a reverse proxy to use a DNS server located in the internal network.</span></span> <span data-ttu-id="3ff43-119">這表示您可能需要在週邊伺服器中都有 DNS 伺服器，否則您需要將這些 Fqdn 解析成伺服器內部 IP 位址的反向 proxy 上的主機檔案專案。</span><span class="sxs-lookup"><span data-stu-id="3ff43-119">This means you either need DNS servers in the perimeter, or you need HOSTS file entries on the reverse proxy that resolves each of these FQDNs to the internal IP address of the servers.</span></span>



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a><span data-ttu-id="3ff43-120">在反向 proxy 電腦上設定網路介面卡</span><span class="sxs-lookup"><span data-stu-id="3ff43-120">To configure the network adapter cards on the reverse proxy computer</span></span>

1.  <span data-ttu-id="3ff43-121">在 Windows Server 2008、Windows Server 2008 R2、Windows Server 2012 或以反向 proxy 身份執行的 Windows Server 2012 R2 伺服器上，按一下 [**開始**]，指向 [**控制台**]，按一下 [**網路和共用中心**]，然後按一下 [**變更配接器設定**]，即可開啟 [**變更配接器設定**]。</span><span class="sxs-lookup"><span data-stu-id="3ff43-121">On the Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 server running as the reverse proxy, open **Change Adapter Settings** by clicking **Start**, pointing to **Control Panel**, clicking **Network and Sharing Center**, and then clicking **Change Adapter Settings**.</span></span>

2.  <span data-ttu-id="3ff43-122">以滑鼠右鍵按一下您要用於外部介面的外部網路連線，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="3ff43-122">Right-click the external network connection that you want to use for the external interface, and then click **Properties**.</span></span>

3.  <span data-ttu-id="3ff43-123">在 [**屬性**] 頁面上，按一下 [**網路**] 索引標籤，按一下 [**此連線使用下列專案**] 清單中的 **[網際網路通訊協定版本4（TCP/IPv4）** ]，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="3ff43-123">On the **Properties** page, click the **Networking** tab, click **Internet Protocol Version 4 (TCP/IPv4)** in the **This connection uses the following items** list, and then click **Properties**.</span></span>

4.  <span data-ttu-id="3ff43-124">在 [**網際網路通訊協定（tcp/ip）屬性**] 頁面上，針對要連接網路介面卡的網路子網，設定適當的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3ff43-124">On the **Internet Protocol (TCP/IP) Properties** page, configure the IP addresses as appropriate for the network subnet to which the network adapter is attached.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3ff43-125">如果反向 proxy 已由使用 HTTPS/TCP/443 的其他應用程式使用，例如，若要發佈 Outlook Web Access，您需要新增另一個 IP 位址，以便在 HTTPS/TCP/443 上發佈 Lync Server 2013 Web 服務，而不會干擾現有的規則和網頁偵聽程式，或者您需要取代現有的憑證，並將新的外部 FQDN 名稱新增到 subject 替換名稱。</span><span class="sxs-lookup"><span data-stu-id="3ff43-125">If the reverse proxy is already being used by other applications that use HTTPS/TCP/443, such as for publishing Outlook Web Access, you either need to add another IP address so that you can publish the Lync Server 2013 Web Services on HTTPS/TCP/443 without interfering with the existing rules and web listeners, or you need to replace the existing certificate with one that adds the new external FQDN names to the subject alternative name.</span></span>

    
    </div>

5.  <span data-ttu-id="3ff43-126">按一下 **[確定]**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3ff43-126">Click **OK**, and then click **OK**.</span></span>

6.  <span data-ttu-id="3ff43-127">在 [**網路**連線] 中，以滑鼠右鍵按一下您要用於內部介面的內部網路連線，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="3ff43-127">In **Network Connections**, right-click the internal network connection that you want to use for the internal interface, and then click **Properties**.</span></span>

7.  <span data-ttu-id="3ff43-128">重複步驟3到5，設定內部網路連線。</span><span class="sxs-lookup"><span data-stu-id="3ff43-128">Repeat steps 3 through 5 to configure the internal network connection.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

