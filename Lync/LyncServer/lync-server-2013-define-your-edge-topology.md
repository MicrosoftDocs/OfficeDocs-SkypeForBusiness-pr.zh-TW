---
title: Lync Server 2013：定義 Edge 拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define your edge topology
ms:assetid: 787b23f1-8fa0-4c37-abf2-c516c5dd66f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398591(v=OCS.15)
ms:contentKeyID: 48184562
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8364d2167b719e020ecebc3808c2ca850d14bc0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-your-edge-topology-in-lync-server-2013"></a><span data-ttu-id="8c70c-102">在 Lync Server 2013 中定義 Edge 拓撲</span><span class="sxs-lookup"><span data-stu-id="8c70c-102">Define your edge topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c70c-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="8c70c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="8c70c-104">您必須使用拓撲建立器來建立拓撲，而且您必須先設定至少一個內部前端池或標準版伺服器，才能部署邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="8c70c-104">You must use Topology Builder to build your topology and you must set up at least one internal Front End pool or Standard Edition server before you can deploy your Edge Server.</span></span> <span data-ttu-id="8c70c-105">使用下列程式定義單一邊緣伺服器的邊緣拓朴，然後使用在[Lync server 2013 中發佈拓撲中](lync-server-2013-publish-your-topology.md)的程式，並[匯出 lync server 2013 拓撲，並將它複製到外部媒體以進行 edge 安裝](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)，以發佈拓撲並讓它可供您的邊緣伺服器使用。</span><span class="sxs-lookup"><span data-stu-id="8c70c-105">Use the following procedure to define the edge topology for a single Edge Server, and then use the procedures in [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) to publish the topology and make it available to your Edge Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8c70c-106">內部 Edge 介面和外部 Edge 介面必須使用相同類型的負載平衡。</span><span class="sxs-lookup"><span data-stu-id="8c70c-106">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="8c70c-107">您不能在一個 Edge 介面上使用 DNS 負載平衡，而在另一個 Edge 介面上使用硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="8c70c-107">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="8c70c-108">若要在新增或移除伺服器角色時成功發佈、啟用或停用拓撲，您必須以 RTCUniversalServerAdmins 和網域系統管理員群組成員的使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="8c70c-108">To successfully publish, enable, or disable a topology when adding or removing a server role, you must be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="8c70c-109">您也可以將伺服器角色加入伺服器角色所需的管理員權利和許可權授與使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="8c70c-109">You can also grant the administrator rights and permissions required for adding server roles to a user account.</span></span> <span data-ttu-id="8c70c-110">如需詳細資訊，請參閱在標準版 server 或 Enterprise Edition server 部署檔中的[Lync Server 2013 委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="8c70c-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="8c70c-111">針對其他設定變更，只需要 RTCUniversalServerAdmins 群組中的成員資格。</span><span class="sxs-lookup"><span data-stu-id="8c70c-111">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="8c70c-112">如果您在定義併發布內部拓撲時定義了 edge 拓撲，且您先前定義的邊緣拓撲不需要變更，則您不需要進行定義並再次發佈。</span><span class="sxs-lookup"><span data-stu-id="8c70c-112">If you defined your edge topology when you defined and published your internal topology, and no changes are required to the edge topology that you previously defined, you do not need to do define it and publish it again.</span></span> <span data-ttu-id="8c70c-113">只有在您需要變更 edge 拓撲時，才能使用下列程式。</span><span class="sxs-lookup"><span data-stu-id="8c70c-113">Use the following procedure only if you need to make changes to your edge topology.</span></span> <span data-ttu-id="8c70c-114">您必須使用[匯出 Lync Server 2013 拓撲中的程式，並將它複製到外部媒體以進行 edge 安裝](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)，以讓您的邊緣伺服器使用先前定義及發佈的拓撲。</span><span class="sxs-lookup"><span data-stu-id="8c70c-114">You must make the previously defined and published topology available to your Edge Servers, which you do by using the procedure in [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8c70c-115">您無法從 Edge 伺服器執行拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="8c70c-115">You cannot run Topology Builder from an Edge Server.</span></span> <span data-ttu-id="8c70c-116">您必須從前端伺服器或標準版伺服器執行此程式。</span><span class="sxs-lookup"><span data-stu-id="8c70c-116">You must run it from your Front End Server or Standard Edition servers.</span></span>



</div>

<span data-ttu-id="8c70c-117">定義 Edge 伺服器拓撲的程式是在拓撲建立器中完成。</span><span class="sxs-lookup"><span data-stu-id="8c70c-117">The process to define your Edge Server topology is done in Topology Builder.</span></span> <span data-ttu-id="8c70c-118">您規劃和設定的三種主要的邊緣伺服器拓撲類型如下所示：</span><span class="sxs-lookup"><span data-stu-id="8c70c-118">The three primary types of Edge Server topologies that you plan and configure are listed below:</span></span>

  - <span data-ttu-id="8c70c-119">若要定義單一邊緣伺服器的拓撲</span><span class="sxs-lookup"><span data-stu-id="8c70c-119">To define the Topology for a Single Edge Server</span></span>

  - <span data-ttu-id="8c70c-120">若要定義負載平衡的邊緣伺服器池的拓撲</span><span class="sxs-lookup"><span data-stu-id="8c70c-120">To define the Topology for a Load Balanced Edge Server Pool</span></span>

  - <span data-ttu-id="8c70c-121">定義硬體負載平衡邊緣池的拓撲</span><span class="sxs-lookup"><span data-stu-id="8c70c-121">To define the Topology for a Hardware Load Balanced Edge Pool</span></span>

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a><span data-ttu-id="8c70c-122">若要定義單一邊緣伺服器的拓撲</span><span class="sxs-lookup"><span data-stu-id="8c70c-122">To define the topology for a single Edge Server</span></span>

1.  <span data-ttu-id="8c70c-123">啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="8c70c-123">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="8c70c-124">在主控台樹中，展開您要在其中部署邊緣伺服器的網站。</span><span class="sxs-lookup"><span data-stu-id="8c70c-124">In the console tree, expand the site in which you want to deploy an Edge Server.</span></span>

3.  <span data-ttu-id="8c70c-125">以滑鼠右鍵按一下 [**邊緣池**]，然後按一下 [**新增邊緣池**]。</span><span class="sxs-lookup"><span data-stu-id="8c70c-125">Right-click **Edge pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="8c70c-126">在 [**定義新的邊緣] 池中**，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-126">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="8c70c-127">在 [**定義邊緣池 FQDN**] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8c70c-127">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="8c70c-128">在 [**池 FQDN**] 中，輸入邊緣伺服器內部介面的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="8c70c-128">In **Pool FQDN**, type the fully qualified domain name (FQDN) of the internal interface for the Edge Server.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="8c70c-129">您指定的名稱必須與伺服器上設定的電腦名稱相同。</span><span class="sxs-lookup"><span data-stu-id="8c70c-129">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="8c70c-130">根據預設，未加入網域之電腦的電腦名稱稱是簡稱，不是 FQDN。</span><span class="sxs-lookup"><span data-stu-id="8c70c-130">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="8c70c-131">拓撲產生器會使用 FQDN，而非簡稱。</span><span class="sxs-lookup"><span data-stu-id="8c70c-131">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="8c70c-132">因此，您必須在要部署為邊緣伺服器且未加入網域的電腦名稱稱上設定 DNS 尾碼。</span><span class="sxs-lookup"><span data-stu-id="8c70c-132">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="8c70c-133">在指派 Lync Server、Edge 伺服器和池的 Fqdn 時，只使用標準字元（包括 A-z、A 至 z、0–9和連字號）。</span><span class="sxs-lookup"><span data-stu-id="8c70c-133">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="8c70c-134">請勿使用 Unicode 字元或底線。</span><span class="sxs-lookup"><span data-stu-id="8c70c-134">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="8c70c-135">外部 DNS 和公用 Ca 通常不支援 FQDN 中的非標準字元（當 FQDN 必須指派給憑證中的 SN 時）。</span><span class="sxs-lookup"><span data-stu-id="8c70c-135">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="8c70c-136">如需新增 DNS 尾碼至電腦名稱稱的詳細資料，請參閱<A href="lync-server-2013-configure-dns-for-edge-support.md">在 Lync Server 2013 中設定支援 edge 的 dns</A>。</span><span class="sxs-lookup"><span data-stu-id="8c70c-136">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>
    
      - <span data-ttu-id="8c70c-137">按一下 [**單一電腦池**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-137">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="8c70c-138">在 [**選取功能**] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8c70c-138">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="8c70c-139">如果您打算針對 SIP Access 服務使用單一 FQDN 和 IP 位址、Lync Server 2013 Web 會議服務，以及 A/V 邊緣服務，請選取 [**使用單一 FQDN 和 Ip 位址**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8c70c-139">If you plan to use a single FQDN and IP address for the SIP Access service, Lync Server 2013 Web Conferencing service, and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="8c70c-140">如果您打算啟用同盟，請選取 [**針對此 Edge 池啟用同盟（埠5061）** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8c70c-140">If you plan to enable federation select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8c70c-141">您可以選取這個選項，但貴組織中只有一個邊界池或邊緣伺服器可以在外部針對同盟進行發佈。</span><span class="sxs-lookup"><span data-stu-id="8c70c-141">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation.</span></span> <span data-ttu-id="8c70c-142">同盟使用者的所有存取權，包括公用立即訊息（IM）使用者，請流覽相同的邊緣池或單層伺服器。</span><span class="sxs-lookup"><span data-stu-id="8c70c-142">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="8c70c-143">例如，如果您的部署包含在紐約部署的邊緣池或單層伺服器，且在倫敦部署，且您在紐約的邊緣池或單一邊緣伺服器上啟用同盟支援，則聯盟使用者的信號流量將會透過紐約進行。[邊緣] 池或 [單一邊緣] 伺服器。</span><span class="sxs-lookup"><span data-stu-id="8c70c-143">For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="8c70c-144">儘管位於倫敦的內部使用者在致電倫敦的同盟使用者時，使用了倫敦集區或 Edge Server 以傳送音訊/視訊流量，與倫敦的使用者進行通訊時也適用這種情況。</span><span class="sxs-lookup"><span data-stu-id="8c70c-144">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="8c70c-145">如果您打算針對您的部署支援可擴展的訊息和目前狀態通訊協定（XMPP），請選取 [**啟用 XMPP 同盟（埠5269）** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8c70c-145">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="8c70c-146">在 [**選取 IP 選項**] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8c70c-146">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="8c70c-147">**在內部介面上啟用 ipv4**：如果您想要將 ipv4 位址套用至 edge 伺服器或 edge 池內部介面，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8c70c-147">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="8c70c-148">**在內部介面上啟用 ipv6**：如果您想要將 ipv6 位址套用至 edge 伺服器或 edge 池內部介面，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8c70c-148">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="8c70c-149">**在外部介面上啟用 ipv4**：如果您想要將 ipv4 位址套用至 edge 伺服器或 edge 池外部介面，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8c70c-149">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="8c70c-150">**在外部介面上啟用 ipv6**：如果您想要將 ipv6 位址套用至 edge 伺服器或 edge 池外部介面，請選取核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8c70c-150">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="8c70c-151">您也可以將 Edge 伺服器或 Edge 池設定為使用網路位址轉譯位址作為外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8c70c-151">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="8c70c-152">您可以選取**此邊緣池的外部 IP 位址（由 NAT 轉譯**）來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="8c70c-152">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

8.  <span data-ttu-id="8c70c-153">在**外部 fqdn**中，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8c70c-153">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="8c70c-154">如果在 [**選取的功能**] 中選擇要針對 sip 存取、Web 會議服務和 a/V 邊緣服務輸入單一 FQDN 和 IP 位址，請在 [ **sip 存取**] 中輸入外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="8c70c-154">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8c70c-155">如果您選擇此選項，您必須為每個 edge 服務指定不同的埠號碼（建議的埠設定：5061以取得存取邊緣服務、444網頁會議 Edge 服務，以及 A/V 邊緣服務的443）。</span><span class="sxs-lookup"><span data-stu-id="8c70c-155">If you choose this option, you must specify a different port number for each of the edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="8c70c-156">選取此選項可協助防止潛在的連線問題，並簡化設定，因為您可以在所有三個服務中使用相同的埠號碼（例如，443）。</span><span class="sxs-lookup"><span data-stu-id="8c70c-156">Selecting this option can help prevent potential connectivity issues, and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="8c70c-157">如果在 **[選取的功能**您未選擇使用單一 FQDN 和 IP 位址] 中，請輸入**SIP 存取**的外部 fqdn、 **Web 會議**和**音訊影片**，並保留預設埠。</span><span class="sxs-lookup"><span data-stu-id="8c70c-157">If in **Select features** you did not chose to use a single FQDN and IP Address, type the External FQDNs for **SIP Access**, **Web Conferencing** and **Audio Video**, keeping the default ports.</span></span>

9.  <span data-ttu-id="8c70c-158">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-158">Click **Next**.</span></span>

10. <span data-ttu-id="8c70c-159">在 [**定義內部 IP 位址**] 中，在 [**內部 IPv4 位址**] 和 [**內部 IPv6 位址**] 中輸入 Edge 伺服器的 IP 位址，以符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="8c70c-159">In **Define the Internal IP address**, type the IP address of your Edge Server in **Internal IPv4 address** and **Internal IPv6 address** as is appropriate for your requirements.</span></span> <span data-ttu-id="8c70c-160">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-160">Click **Next**.</span></span>

11. <span data-ttu-id="8c70c-161">在 [**定義外部 IP 位址**] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8c70c-161">In **Define the External IP address**, do the following:</span></span>
    
      - <span data-ttu-id="8c70c-162">如果您選擇要針對 SIP 存取、Web 會議服務和 A/V 邊緣服務使用單一 FQDN 和 IP 位址，請在 [ **Sip 存取**] 中輸入 Edge 伺服器的外部 IPv4 位址，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-162">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="8c70c-163">如果您選擇使用 IPv6 位址，請在 [ **SIP 存取**] 中輸入 Edge 伺服器的外部 IPv6 位址，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-163">If you chose to use IPv6 addresses, type the external IPv6 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="8c70c-164">如果您沒有選擇要針對 SIP 存取、Web 會議服務和 A/V 邊緣服務使用單一 FQDN 和 IP 位址，請在 [ **Sip 存取**]、[ **web 會議**] 和 [ **a/v 會議**] 中輸入 Edge 伺服器的外部 IPv4 位址，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-164">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="8c70c-165">如果您選擇使用 IPv6 位址，但未選擇使用單一 FQDN 和 IP 位址進行 SIP 存取、Web 會議服務及 A/V 邊緣服務，請在**SIP 存取**、 **Web 會議**和**a/v 會議**中輸入 Edge 伺服器的外部 IPv6 位址，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-165">If you chose to use IPv6 addresses and did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8c70c-166">如果您沒有選擇啟用並指派 IPv6 定址，就不會看到此對話方塊。</span><span class="sxs-lookup"><span data-stu-id="8c70c-166">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

        
        </div>

12. <span data-ttu-id="8c70c-167">如果您選擇使用 NAT，就會出現一個對話方塊。</span><span class="sxs-lookup"><span data-stu-id="8c70c-167">If you chose to use NAT, a dialog box appears.</span></span> <span data-ttu-id="8c70c-168">在**A/V 邊緣服務的公用 ipv4 位址**中，輸入要由 NAT 轉譯的公用 ipv4 位址，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-168">In **Public IPv4 address for the A/V Edge service**, type the public IPv4 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8c70c-169">這應該是 A/V Edge 服務的外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8c70c-169">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

13. <span data-ttu-id="8c70c-170">如果您選擇使用 NAT 和 IPv6 位址，則會顯示對話方塊。</span><span class="sxs-lookup"><span data-stu-id="8c70c-170">If you chose to use NAT and IPv6 addresses, a dialog box appears.</span></span> <span data-ttu-id="8c70c-171">在**A/V 邊緣服務的公用 ipv6 位址**中，輸入要由 NAT 轉譯的公用 ipv6 位址，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-171">In **Public IPv6 address for the A/V Edge service**, type the public IPv6 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8c70c-172">這應該是 A/V Edge 服務的外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8c70c-172">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

14. <span data-ttu-id="8c70c-173">在 [**定義下一個躍點**] 中的 **[下一個躍點] 池中**，選取內部池的名稱，該名稱可以是 [前端] 池或 [標準版] 池。</span><span class="sxs-lookup"><span data-stu-id="8c70c-173">In **Define the next hop**, in **Next hop pool**, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool.</span></span> <span data-ttu-id="8c70c-174">或者，如果您的部署包含控制器，請選取 [主管]。</span><span class="sxs-lookup"><span data-stu-id="8c70c-174">Or, if your deployment includes a Director, select the Director.</span></span> <span data-ttu-id="8c70c-175">然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-175">Then, click **Next**.</span></span>

15. <span data-ttu-id="8c70c-176">在 [**關聯前端池**] 中，指定一個或多個內部池（可包含要與此 edge 伺服器關聯的前端池和標準版伺服器），方法是選取要使用此 edge 伺服器與支援的外部使用者進行通訊的內部池名稱。</span><span class="sxs-lookup"><span data-stu-id="8c70c-176">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pools that are to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8c70c-177">只有一個負載平衡的邊緣池或單一邊緣伺服器可以與 A/V 流量的每個內部池產生關聯。</span><span class="sxs-lookup"><span data-stu-id="8c70c-177">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic.</span></span> <span data-ttu-id="8c70c-178">如果您已經有與邊緣池或邊緣伺服器相關聯的內部池，就會出現警告，指出內部池已經與邊緣池或邊緣伺服器相關聯。</span><span class="sxs-lookup"><span data-stu-id="8c70c-178">If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server.</span></span> <span data-ttu-id="8c70c-179">如果您選取的池已與另一個 Edge 伺服器關聯，就會變更關聯。</span><span class="sxs-lookup"><span data-stu-id="8c70c-179">If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

16. <span data-ttu-id="8c70c-180">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-180">Click **Finish**.</span></span>

17. <span data-ttu-id="8c70c-181">發佈您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="8c70c-181">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="8c70c-182">若要定義 DNS 負載平衡邊緣伺服器池的拓撲</span><span class="sxs-lookup"><span data-stu-id="8c70c-182">To define the topology for a DNS load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="8c70c-183">啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="8c70c-183">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="8c70c-184">在主控台樹中，展開您要部署邊緣伺服器的網站。</span><span class="sxs-lookup"><span data-stu-id="8c70c-184">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="8c70c-185">以滑鼠右鍵按一下 [**邊緣池**]，然後按一下 [**新增邊緣池**]。</span><span class="sxs-lookup"><span data-stu-id="8c70c-185">Right-click **Edge Pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="8c70c-186">在 [**定義新的邊緣] 池中**，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-186">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="8c70c-187">在 [**定義邊緣池 FQDN**] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8c70c-187">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="8c70c-188">在 [**池 FQDN**] 中，輸入邊緣池內部連接的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="8c70c-188">In **Pool FQDN**, type the fully qualified domain name (FQDN) for the internal connection of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="8c70c-189">您指定的池名稱必須是內部邊緣池名稱。</span><span class="sxs-lookup"><span data-stu-id="8c70c-189">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="8c70c-190">必須將它定義為 FQDN。</span><span class="sxs-lookup"><span data-stu-id="8c70c-190">This must be defined as a FQDN.</span></span> <span data-ttu-id="8c70c-191">拓撲產生器會使用 FQDN，而非簡稱。</span><span class="sxs-lookup"><span data-stu-id="8c70c-191">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="8c70c-192">在指派 Lync Server、Edge 伺服器和池的 Fqdn 時，只使用標準字元（包括 A-z、A 至 z、0–9和連字號）。</span><span class="sxs-lookup"><span data-stu-id="8c70c-192">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="8c70c-193">請勿使用 Unicode 字元或底線。</span><span class="sxs-lookup"><span data-stu-id="8c70c-193">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="8c70c-194">外部 DNS 和公用 Ca 通常不支援 FQDN 中的非標準字元（當 FQDN 必須指派給憑證中的 SN 時）。</span><span class="sxs-lookup"><span data-stu-id="8c70c-194">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
      - <span data-ttu-id="8c70c-195">按一下 [**多個電腦池**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-195">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="8c70c-196">在 [**選取功能**] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8c70c-196">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="8c70c-197">如果您打算針對 SIP 存取使用單一 FQDN 和 IP 位址，Lync Server 2013 Web 會議服務和 A/V Edge 服務，請選取 [**使用單一 FQDN 和 Ip 位址**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8c70c-197">If you plan to use a single FQDN and IP address for the SIP access, Lync Server 2013 Web Conferencing service and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="8c70c-198">如果您打算啟用同盟，請選取 [**針對此 Edge 池啟用同盟（埠5061）** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8c70c-198">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span> <span data-ttu-id="8c70c-199">按一下 **[下一步]**</span><span class="sxs-lookup"><span data-stu-id="8c70c-199">Click **Next**</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8c70c-200">您可以選取這個選項，但貴組織中只有一個邊界池或邊緣伺服器可以在外部針對同盟進行發佈。</span><span class="sxs-lookup"><span data-stu-id="8c70c-200">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation.</span></span> <span data-ttu-id="8c70c-201">同盟使用者的所有存取權，包括公用立即訊息（IM）使用者，請流覽相同的邊緣池或單層伺服器。</span><span class="sxs-lookup"><span data-stu-id="8c70c-201">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="8c70c-202">例如，如果您的部署範圍包括分別部署在紐約與倫敦的一個 Edge 集區或單一 Edge Server，而您針對紐約的 Edge 集區或單一 Edge Server 啟用了同盟支援，則同盟使用者的訊號流量會通過紐約的 Edge 集區或單一 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="8c70c-202">For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="8c70c-203">儘管位於倫敦的內部使用者在致電倫敦的同盟使用者時，使用了倫敦集區或 Edge Server 以傳送音訊/視訊流量，與倫敦的使用者進行通訊時也適用這種情況。</span><span class="sxs-lookup"><span data-stu-id="8c70c-203">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="8c70c-204">如果您打算針對您的部署支援可擴展的訊息和目前狀態通訊協定（XMPP），請選取 [**啟用 XMPP 同盟（埠5269）** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8c70c-204">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="8c70c-205">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-205">Click **Next**.</span></span>

8.  <span data-ttu-id="8c70c-206">在 [**選取 IP 選項**] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8c70c-206">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="8c70c-207">**在內部介面上啟用 ipv4**：如果您想要將 ipv4 位址套用至 edge 伺服器或 edge 池內部介面，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8c70c-207">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="8c70c-208">**在內部介面上啟用 ipv6**：如果您想要將 ipv6 位址套用至 edge 伺服器或 edge 池內部介面，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8c70c-208">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="8c70c-209">**在外部介面上啟用 ipv4**：如果您想要將 ipv4 位址套用至 edge 伺服器或 edge 池外部介面，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8c70c-209">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="8c70c-210">**在外部介面上啟用 ipv6**：如果您想要將 ipv6 位址套用至 edge 伺服器或 edge 池外部介面，請選取核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8c70c-210">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="8c70c-211">您也可以將 Edge 伺服器或 Edge 池設定為使用網路位址轉譯位址作為外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8c70c-211">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="8c70c-212">您可以選取**此邊緣池的外部 IP 位址（由 NAT 轉譯**）來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="8c70c-212">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

9.  <span data-ttu-id="8c70c-213">在**外部 fqdn**中，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8c70c-213">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="8c70c-214">如果在 [**選取的功能**] 中選擇要針對 sip 存取、Web 會議服務和 a/V 邊緣服務輸入單一 FQDN 和 IP 位址，請在 [ **sip 存取**] 中輸入外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="8c70c-214">If in **Select features** you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8c70c-215">如果您選擇此選項，您必須為每個 Edge 服務指定不同的埠號碼（建議的埠設定：5061以取得存取邊緣服務、444網頁會議 Edge 服務，以及 A/V 邊緣服務的443）。</span><span class="sxs-lookup"><span data-stu-id="8c70c-215">If you choose this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="8c70c-216">選取此選項時，您可以協助防止潛在的連線問題並簡化設定，因為您可以在所有三個服務中使用相同的埠號碼（例如，443）。</span><span class="sxs-lookup"><span data-stu-id="8c70c-216">By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="8c70c-217">如果在 [**選取的功能**您未選擇使用單一 FQDN 和 IP 位址] 中，輸入您在 [ **SIP 存取**] 中針對邊緣池公開的公用方所選擇的 fqdn。</span><span class="sxs-lookup"><span data-stu-id="8c70c-217">If in **Select features** you did not chose to use a single FQDN and IP Address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**.</span></span> <span data-ttu-id="8c70c-218">在 [ **Web 會議**] 中，輸入您針對邊緣池的公用方程式所選取的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="8c70c-218">In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="8c70c-219">在 [**音訊/影片**] 中，輸入您針對 Edge 池的公用方程式所選取的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="8c70c-219">In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="8c70c-220">使用預設埠。</span><span class="sxs-lookup"><span data-stu-id="8c70c-220">Use the default ports.</span></span>

10. <span data-ttu-id="8c70c-221">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-221">Click **Next**.</span></span>

11. <span data-ttu-id="8c70c-222">在 [**定義此池中的電腦**] 中，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="8c70c-222">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="8c70c-223">在 [**內部 FQDN 和 IP 位址**] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8c70c-223">In **Internal FQDN and IP address**, do the following:</span></span>
    
      - <span data-ttu-id="8c70c-224">在 [**內部 IPv4 位址**] 中，輸入 [IPv4 位址] 和 [**內部 IPv6 位址**]，以符合您想要在此池中建立的第一個邊緣伺服器的需求。</span><span class="sxs-lookup"><span data-stu-id="8c70c-224">In **Internal IPv4 address**, type the IPv4 address and **Internal IPv6 address** as is appropriate for your requirements for the first Edge Server that you want to create in this pool.</span></span>
    
      - <span data-ttu-id="8c70c-225">在 [**內部 FQDN**] 中，輸入您要在此池中建立的第一個邊緣伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="8c70c-225">In **Internal FQDN**, type the FQDN of the first Edge Server that you want to create in this pool.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8c70c-226">您指定的名稱必須與伺服器上設定的電腦名稱相同。</span><span class="sxs-lookup"><span data-stu-id="8c70c-226">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="8c70c-227">根據預設，未加入網域之電腦的電腦名稱是簡稱，不是 FQDN。</span><span class="sxs-lookup"><span data-stu-id="8c70c-227">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="8c70c-228">拓撲產生器會使用 FQDN，而非簡稱。</span><span class="sxs-lookup"><span data-stu-id="8c70c-228">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="8c70c-229">因此，您必須在要部署為邊緣伺服器且未加入網域的電腦名稱稱上設定 DNS 尾碼。</span><span class="sxs-lookup"><span data-stu-id="8c70c-229">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="8c70c-230">指派 Lync Server、Edge 伺服器、池及陣列的 Fqdn 時，只能使用標準字元（包括 A-z、A – z、0–9和連字號）。</span><span class="sxs-lookup"><span data-stu-id="8c70c-230">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, pools, and arrays.</span></span> <span data-ttu-id="8c70c-231">請勿使用 Unicode 字元或底線。</span><span class="sxs-lookup"><span data-stu-id="8c70c-231">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="8c70c-232">外部 DNS 和公用 Ca 通常不支援 FQDN 中的非標準字元（當 FQDN 必須指派給憑證中的 SN 時）。</span><span class="sxs-lookup"><span data-stu-id="8c70c-232">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="8c70c-233">如需新增 DNS 尾碼至電腦名稱稱的詳細資料，請參閱<A href="lync-server-2013-configure-dns-for-edge-support.md">在 Lync Server 2013 中設定支援 edge 的 dns</A>。</span><span class="sxs-lookup"><span data-stu-id="8c70c-233">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>

13. <span data-ttu-id="8c70c-234">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-234">Click **Next**.</span></span>

14. <span data-ttu-id="8c70c-235">在 [**定義外部 IP 位址**] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8c70c-235">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="8c70c-236">如果您選擇使用單一 FQDN 和 IP 位址來進行 SIP 存取、Web 會議服務及 A/V 邊緣服務，請在**SIP 存取**中輸入 Edge 伺服器的外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8c70c-236">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="8c70c-237">如果您未選擇針對 SIP 存取、Web 會議服務和 A/V 會議服務使用單一 FQDN 和 IP 位址，請輸入您為此 Edge 池伺服器公開的公用端，以進行**Sip 存取**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-237">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="8c70c-238">在 [ **Web 會議**] 中，輸入您針對此 Edge 池伺服器的公開方程式所選取的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8c70c-238">In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="8c70c-239">在**A/V 會議**中，輸入您針對此 Edge 池伺服器的公開方程式選取的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8c70c-239">In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

15. <span data-ttu-id="8c70c-240">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-240">Click **Next**.</span></span>

16. <span data-ttu-id="8c70c-241">如果您選擇啟用 IPv6 位址，請在 [**定義外部 IP 位址**] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8c70c-241">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="8c70c-242">如果您選擇要針對 SIP 存取、Web 會議服務和 A/V 邊緣服務使用單一 FQDN 和 IP 位址，請在**SIP 存取**中輸入 Edge 伺服器的外部 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="8c70c-242">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="8c70c-243">如果您沒有選擇要針對 SIP 存取、Web 會議服務和 A/V 會議服務使用單一 FQDN 和 IP 位址，請輸入您為此 Edge 池伺服器公開的公用端的 IPv6 位址，以進行**SIP 存取**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-243">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="8c70c-244">在 [ **Web 會議**] 中，輸入您針對此 Edge 池伺服器的公開方程式所選取的 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="8c70c-244">In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="8c70c-245">在**A/V 會議**中，輸入您針對此 Edge 池伺服器的公開方程式所選取的 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="8c70c-245">In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8c70c-246">如果您沒有選擇啟用並指派 IPv6 定址，就不會看到此對話方塊。</span><span class="sxs-lookup"><span data-stu-id="8c70c-246">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

17. <span data-ttu-id="8c70c-247">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-247">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8c70c-248">您現在會在 [<STRONG>定義此池中的電腦</STRONG>] 對話方塊中，看到您在您的池中建立的第一個 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="8c70c-248">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

18. <span data-ttu-id="8c70c-249">在 [**定義此池中的電腦**] 中，按一下 [**新增**]，然後針對您想要新增到 [邊緣] 池的第二邊緣伺服器重複步驟11到14。</span><span class="sxs-lookup"><span data-stu-id="8c70c-249">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to you Edge pool.</span></span>

19. <span data-ttu-id="8c70c-250">重複步驟11到14之後，請在 [**定義此池中的電腦**] 中按一下 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="8c70c-250">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8c70c-251">此時，您可以在您的池中看到兩個邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="8c70c-251">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

20. <span data-ttu-id="8c70c-252">如果您選擇使用 NAT，就會出現一個對話方塊。</span><span class="sxs-lookup"><span data-stu-id="8c70c-252">If you chose to use NAT, a dialog box appears.</span></span> <span data-ttu-id="8c70c-253">在 [**公用 IP 位址**] 中，輸入要由 NAT 轉譯的公用 IPv4 與 IPv6 （視需要）位址，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-253">In **Public IP address**, type the public IPv4 and IPv6 (as appropriate) addresses to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8c70c-254">這應該是 A/V 邊緣的外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8c70c-254">This should be the external IP Address of the A/V Edge.</span></span>

    
    </div>

21. <span data-ttu-id="8c70c-255">在 [**定義下一個躍點**] 中的 [**下一個躍點池]** 清單中，選取內部池的名稱，該名稱可以是 [前端] 池或 [標準版] 池。</span><span class="sxs-lookup"><span data-stu-id="8c70c-255">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool.</span></span> <span data-ttu-id="8c70c-256">或者，如果您的部署包含控制器，請選取主管的名稱。</span><span class="sxs-lookup"><span data-stu-id="8c70c-256">Or, if your deployment includes a Director, select the name of the Director.</span></span> <span data-ttu-id="8c70c-257">然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-257">Then, click **Next**.</span></span>

22. <span data-ttu-id="8c70c-258">在 [**關聯前端池**] 中，指定一個或多個內部池（可包含要與此 edge 伺服器關聯的前端池和標準版伺服器），方法是選取要使用此 edge 伺服器與支援的外部使用者進行通訊的內部池名稱。</span><span class="sxs-lookup"><span data-stu-id="8c70c-258">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8c70c-259">只有一個負載平衡的邊緣池或單一邊緣伺服器可以與 A/V 流量的每個內部池產生關聯。</span><span class="sxs-lookup"><span data-stu-id="8c70c-259">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic.</span></span> <span data-ttu-id="8c70c-260">如果您已經有與邊緣池或邊緣伺服器相關聯的內部池，就會出現警告，指出內部池已經與邊緣池或邊緣伺服器相關聯。</span><span class="sxs-lookup"><span data-stu-id="8c70c-260">If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server.</span></span> <span data-ttu-id="8c70c-261">如果您選取的池已與另一個 Edge 伺服器關聯，就會變更關聯。</span><span class="sxs-lookup"><span data-stu-id="8c70c-261">If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

23. <span data-ttu-id="8c70c-262">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-262">Click **Finish**.</span></span>

24. <span data-ttu-id="8c70c-263">發佈您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="8c70c-263">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="8c70c-264">定義硬體負載平衡邊緣伺服器池的拓撲</span><span class="sxs-lookup"><span data-stu-id="8c70c-264">To define the topology for a hardware load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="8c70c-265">啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="8c70c-265">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="8c70c-266">在主控台樹中，展開您要部署邊緣伺服器的網站。</span><span class="sxs-lookup"><span data-stu-id="8c70c-266">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="8c70c-267">以滑鼠右鍵按一下 [**邊緣池**]，然後選取 [**新增邊緣池**]。</span><span class="sxs-lookup"><span data-stu-id="8c70c-267">Right-click **Edge Pools**, and then select **New Edge Pool**.</span></span>

4.  <span data-ttu-id="8c70c-268">在 [**定義新的邊緣] 池中**，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-268">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="8c70c-269">在 [**定義邊緣池 FQDN**] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8c70c-269">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="8c70c-270">在 [ **FQDN**] 中，輸入您針對邊緣池的內部端所選取的完整功能變數名稱（fqdn）。</span><span class="sxs-lookup"><span data-stu-id="8c70c-270">In **FQDN**, type the fully qualified domain name (FQDN) you have chosen for the internal side of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="8c70c-271">您指定的池名稱必須是內部邊緣池名稱。</span><span class="sxs-lookup"><span data-stu-id="8c70c-271">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="8c70c-272">必須將它定義為 FQDN。</span><span class="sxs-lookup"><span data-stu-id="8c70c-272">This must be defined as a FQDN.</span></span> <span data-ttu-id="8c70c-273">拓撲產生器會使用 FQDN，而非簡稱。</span><span class="sxs-lookup"><span data-stu-id="8c70c-273">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="8c70c-274">在指派 Lync Server、Edge 伺服器和池的 Fqdn 時，只使用標準字元（包括 A-z、A 至 z、0–9和連字號）。</span><span class="sxs-lookup"><span data-stu-id="8c70c-274">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="8c70c-275">請勿使用 Unicode 字元或底線。</span><span class="sxs-lookup"><span data-stu-id="8c70c-275">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="8c70c-276">外部 DNS 和公用 Ca 通常不支援 FQDN 中的非標準字元（當 FQDN 必須指派給憑證中的 SN 時）。</span><span class="sxs-lookup"><span data-stu-id="8c70c-276">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
    <!-- end list -->
    
      - <span data-ttu-id="8c70c-277">按一下 [**多個電腦池**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-277">Click **Multiple computer pool**, and then **Next**.</span></span>

6.  <span data-ttu-id="8c70c-278">在 [**選取功能**] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8c70c-278">In **Select features** do the following:</span></span>
    
      - <span data-ttu-id="8c70c-279">如果您打算針對 SIP access 服務使用單一 FQDN 和 IP 位址、Lync Server Web 會議服務和 A/V 邊緣服務，請選取 [**使用單一 FQDN & IP 位址**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8c70c-279">If you plan to use a single FQDN and IP address for the SIP access service, Lync Server Web Conferencing service, and A/V Edge service, select the **Use a single FQDN & IP Address** check box.</span></span>
    
      - <span data-ttu-id="8c70c-280">如果您打算啟用同盟，請選取 [**針對此 Edge 池啟用同盟（埠5061）** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8c70c-280">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8c70c-281">您可以選取這個選項，但貴組織中只有一個邊界池或邊緣伺服器可以在外部針對同盟進行發佈。</span><span class="sxs-lookup"><span data-stu-id="8c70c-281">You can select this option, but only one Edge pool or Edge Server in your organization may be published externally for federation.</span></span> <span data-ttu-id="8c70c-282">同盟使用者的所有存取權，包括公用立即訊息（IM）使用者，請流覽相同的邊緣池或單層伺服器。</span><span class="sxs-lookup"><span data-stu-id="8c70c-282">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="8c70c-283">例如，如果您的部署範圍包括分別部署在紐約與倫敦的一個 Edge 集區或單一 Edge Server，而您針對紐約的 Edge 集區或單一 Edge Server 啟用了同盟支援，則同盟使用者的訊號流量會通過紐約的 Edge 集區或單一 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="8c70c-283">For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="8c70c-284">儘管位於倫敦的內部使用者在致電倫敦的同盟使用者時，使用了倫敦集區或 Edge Server 以傳送音訊/視訊流量，與倫敦的使用者進行通訊時也適用這種情況。</span><span class="sxs-lookup"><span data-stu-id="8c70c-284">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="8c70c-285">如果您打算針對您的部署支援可擴展的訊息和目前狀態通訊協定（XMPP），請選取 [**啟用 XMPP 同盟（埠5269）** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8c70c-285">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="8c70c-286">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-286">Click **Next**.</span></span>

8.  <span data-ttu-id="8c70c-287">在 [**選取 IP 選項**] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8c70c-287">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="8c70c-288">**在內部介面上啟用 ipv4**：如果您想要將 ipv4 位址套用至 edge 伺服器或 edge 池內部介面，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8c70c-288">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="8c70c-289">**在內部介面上啟用 ipv6**：如果您想要將 ipv6 位址套用至 edge 伺服器或 edge 池內部介面，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8c70c-289">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="8c70c-290">**在外部介面上啟用 ipv4**：如果您想要將 ipv4 位址套用至 edge 伺服器或 edge 池外部介面，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8c70c-290">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="8c70c-291">**在外部介面上啟用 ipv6**：如果您想要將 ipv6 位址套用至 edge 伺服器或 edge 池外部介面，請選取核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8c70c-291">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8c70c-292"><STRONG>請勿</STRONG>選取 [<STRONG>邊緣池的外部 IP 位址是由 NAT 轉譯</STRONG>] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8c70c-292"><STRONG>Do Not</STRONG> select the <STRONG>The external IP address of the Edge pool is translated by NAT</STRONG> check box.</span></span> <span data-ttu-id="8c70c-293">如果您使用的是硬體負載平衡，就不支援網路位址轉譯（NAT）。</span><span class="sxs-lookup"><span data-stu-id="8c70c-293">Network address translation (NAT) is not supported when you are using hardware load balancing.</span></span>

    
    </div>

9.  <span data-ttu-id="8c70c-294">在**外部 fqdn**中，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8c70c-294">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="8c70c-295">如果在 [**選取的功能**] 中選擇要針對 sip 存取、Web 會議服務和 a/V 邊緣服務輸入單一 FQDN 和 IP 位址，請在 [ **sip 存取**] 中輸入外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="8c70c-295">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8c70c-296">如果您選擇要選取此選項，您必須為每個 Edge 服務指定不同的埠號碼（建議的埠設定：5061以取得存取邊緣服務、444網頁會議 Edge 服務，以及 A/V 邊緣服務的443）。</span><span class="sxs-lookup"><span data-stu-id="8c70c-296">If you choose to select this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="8c70c-297">選取此選項時，您可以協助防止潛在的連線問題並簡化設定，因為您可以在所有三個服務中使用相同的埠號碼（例如，443）。</span><span class="sxs-lookup"><span data-stu-id="8c70c-297">By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="8c70c-298">如果在 [**選取的功能**您未選擇使用單一 FQDN 和 IP 位址] 中，輸入您在 [ **SIP 存取**] 中針對邊緣池公開的公用方所選擇的 fqdn。</span><span class="sxs-lookup"><span data-stu-id="8c70c-298">If in **Select features** you did not chose to use a single FQDN and IP address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**.</span></span> <span data-ttu-id="8c70c-299">在 [ **Web 會議**] 中，輸入您針對邊緣池的公用方程式所選取的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="8c70c-299">In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="8c70c-300">在 [**音訊/影片**] 中，輸入您針對 Edge 池的公用方程式所選取的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="8c70c-300">In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="8c70c-301">使用預設埠。</span><span class="sxs-lookup"><span data-stu-id="8c70c-301">Use the default ports.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8c70c-302">這些將是該池的公用虛擬 IP （VIP） Fqdn。</span><span class="sxs-lookup"><span data-stu-id="8c70c-302">These will be the publicly facing virtual IP (VIP) FQDNs for the pool.</span></span>

        
        </div>

10. <span data-ttu-id="8c70c-303">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-303">Click **Next**.</span></span>

11. <span data-ttu-id="8c70c-304">在 [**定義此池中的電腦**] 中，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="8c70c-304">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="8c70c-305">在 [**定義外部 IP 位址**] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8c70c-305">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="8c70c-306">如果您選擇要針對 SIP 存取、Web 會議服務和 A/V 邊緣服務使用單一 FQDN 和 IP 位址，請在**Sip 存取**中輸入 edge 伺服器的外部 IPv4 位址。在**sip 存取**中，EDGE 伺服器的外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8c70c-306">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**.external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="8c70c-307">如果您未選擇針對 SIP 存取、Web 會議服務和 A/V 會議服務使用單一 FQDN 和 IP 位址，請輸入您為此 Edge 池伺服器公開的公用端，以進行**Sip 存取**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-307">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="8c70c-308">在 [ **Web 會議**] 中，輸入您針對此 Edge 池伺服器的公開方程式所選取的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8c70c-308">In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="8c70c-309">在**A/V 會議**中，輸入您針對此 Edge 池伺服器的公開方程式選取的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8c70c-309">In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

13. <span data-ttu-id="8c70c-310">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-310">Click **Next**.</span></span>

14. <span data-ttu-id="8c70c-311">如果您選擇啟用 IPv6 位址，請在 [**定義外部 IP 位址**] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8c70c-311">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="8c70c-312">如果您選擇要針對 SIP 存取、Web 會議服務和 A/V 邊緣服務使用單一 FQDN 和 IP 位址，請在**SIP 存取**中輸入 Edge 伺服器的外部 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="8c70c-312">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="8c70c-313">如果您沒有選擇要針對 SIP 存取、Web 會議服務和 A/V 會議服務使用單一 FQDN 和 IP 位址，請輸入您為此 Edge 池伺服器公開的公用端的 IPv6 位址，以進行**SIP 存取**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-313">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="8c70c-314">在 [ **Web 會議**] 中，輸入您針對此 Edge 池伺服器的公開方程式所選取的 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="8c70c-314">In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="8c70c-315">在**A/V 會議**中，輸入您針對此 Edge 池伺服器的公開方程式所選取的 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="8c70c-315">In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8c70c-316">如果您沒有選擇啟用並指派 IPv6 定址，就不會看到此對話方塊。</span><span class="sxs-lookup"><span data-stu-id="8c70c-316">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

15. <span data-ttu-id="8c70c-317">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-317">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8c70c-318">您現在會在 [<STRONG>定義此池中的電腦</STRONG>] 對話方塊中，看到您在您的池中建立的第一個 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="8c70c-318">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

16. <span data-ttu-id="8c70c-319">在 [**定義此池中的電腦**] 中，按一下 [**新增**]，然後針對您想要新增到 Edge 池中的第二台邊緣伺服器重複步驟11至14。</span><span class="sxs-lookup"><span data-stu-id="8c70c-319">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to your Edge pool.</span></span>

17. <span data-ttu-id="8c70c-320">重複步驟11到14之後，請在 [**定義此池中的電腦**] 中按一下 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="8c70c-320">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8c70c-321">此時，您可以在您的池中看到兩個邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="8c70c-321">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

18. <span data-ttu-id="8c70c-322">在 [**定義下一個躍點**] 中的 [**下一個躍點池]** 清單中，選取內部池的名稱，該名稱可以是 [前端] 池或 [標準版] 池。</span><span class="sxs-lookup"><span data-stu-id="8c70c-322">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool.</span></span> <span data-ttu-id="8c70c-323">或者，如果您的部署包含控制器，請選取主管的名稱。</span><span class="sxs-lookup"><span data-stu-id="8c70c-323">Or, if your deployment includes a Director, select the name of the Director.</span></span> <span data-ttu-id="8c70c-324">然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-324">Then, click **Next**.</span></span>

19. <span data-ttu-id="8c70c-325">在 [**關聯前端池**] 中，指定一個或多個內部池（可包含要與此 edge 伺服器關聯的前端池和標準版伺服器），方法是選取要使用此 edge 伺服器與支援的外部使用者進行通訊的內部池名稱。</span><span class="sxs-lookup"><span data-stu-id="8c70c-325">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8c70c-326">只有一個負載平衡的邊緣池或單一邊緣伺服器可以與 A/V 流量的每個內部池產生關聯。</span><span class="sxs-lookup"><span data-stu-id="8c70c-326">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic.</span></span> <span data-ttu-id="8c70c-327">如果您已經有與邊緣池或邊緣伺服器相關聯的內部池，就會出現警告，指出內部池已經與邊緣池或邊緣伺服器相關聯。</span><span class="sxs-lookup"><span data-stu-id="8c70c-327">If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server.</span></span> <span data-ttu-id="8c70c-328">如果您選取的池已與另一個 Edge 伺服器關聯，就會變更關聯。</span><span class="sxs-lookup"><span data-stu-id="8c70c-328">If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

20. <span data-ttu-id="8c70c-329">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="8c70c-329">Click **Finish**.</span></span>

21. <span data-ttu-id="8c70c-330">發佈您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="8c70c-330">Publish your topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

