---
title: Lync Server 2013：定義您的 edge 拓撲
description: Lync Server 2013：定義您的 edge 拓撲。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define your edge topology
ms:assetid: 787b23f1-8fa0-4c37-abf2-c516c5dd66f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398591(v=OCS.15)
ms:contentKeyID: 48184562
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd4aa16ca23d24f0edd92189216030ef926fc841
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572939"
---
# <a name="define-your-edge-topology-in-lync-server-2013"></a><span data-ttu-id="fb870-103">在 Lync Server 2013 中定義您的 edge 拓撲</span><span class="sxs-lookup"><span data-stu-id="fb870-103">Define your edge topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb870-104">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="fb870-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="fb870-105">您必須使用拓撲產生器來建立拓撲，而且必須先設定至少一個內部前端集區或 Standard Edition server，才能部署 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="fb870-105">You must use Topology Builder to build your topology and you must set up at least one internal Front End pool or Standard Edition server before you can deploy your Edge Server.</span></span> <span data-ttu-id="fb870-106">使用下列程式可定義單一 Edge Server 的 edge 拓撲，然後使用在 [Lync server 2013 中發佈拓撲中](lync-server-2013-publish-your-topology.md) 的程式，並 [將 lync server 2013 拓撲複製到外部媒體以進行 edge 安裝](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) ，以發行拓撲，並使其可供 edge Server 使用。</span><span class="sxs-lookup"><span data-stu-id="fb870-106">Use the following procedure to define the edge topology for a single Edge Server, and then use the procedures in [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) to publish the topology and make it available to your Edge Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fb870-p102">內部 Edge 介面和外部 Edge 介面必須使用相同類型的負載平衡。您不能在一個 Edge 介面上使用 DNS 負載平衡，而在另一個 Edge 介面上使用硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="fb870-p102">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="fb870-109">若要在新增或移除伺服器角色時，成功發行、啟用或停用拓撲，您必須以 RTCUniversalServerAdmins 和 Domain Admins 群組成員的使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="fb870-109">To successfully publish, enable, or disable a topology when adding or removing a server role, you must be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="fb870-110">您也可以授與當伺服器角色新增至使用者帳戶時所需的管理員權限。</span><span class="sxs-lookup"><span data-stu-id="fb870-110">You can also grant the administrator rights and permissions required for adding server roles to a user account.</span></span> <span data-ttu-id="fb870-111">如需詳細資訊，請參閱 Standard Edition server 或 Enterprise Edition server 部署檔中的 [Lync server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md) 。</span><span class="sxs-lookup"><span data-stu-id="fb870-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="fb870-112">若要進行其他組態變更，則僅需要 RTCUniversalServerAdmins 群組的成員資格。</span><span class="sxs-lookup"><span data-stu-id="fb870-112">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="fb870-113">如果您已在定義及發行內部拓撲時定義 Edge 拓撲，而且不需要對先前所定義的 Edge 拓撲進行變更，則不需要再定義和發行它一次。</span><span class="sxs-lookup"><span data-stu-id="fb870-113">If you defined your edge topology when you defined and published your internal topology, and no changes are required to the edge topology that you previously defined, you do not need to do define it and publish it again.</span></span> <span data-ttu-id="fb870-114">只有需要對 Edge 拓撲進行變更時，才要使用下列程序。</span><span class="sxs-lookup"><span data-stu-id="fb870-114">Use the following procedure only if you need to make changes to your edge topology.</span></span> <span data-ttu-id="fb870-115">您必須讓先前定義及發佈的拓撲可供 Edge Server 使用，您可以使用 [匯出 Lync Server 2013 拓撲中的程式，並將它複製到 edge 安裝的外部媒體](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)。</span><span class="sxs-lookup"><span data-stu-id="fb870-115">You must make the previously defined and published topology available to your Edge Servers, which you do by using the procedure in [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fb870-116">您無法從 Edge Server 執行拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="fb870-116">You cannot run Topology Builder from an Edge Server.</span></span> <span data-ttu-id="fb870-117">您必須從前端伺服器或 Standard Edition Server 加以執行。</span><span class="sxs-lookup"><span data-stu-id="fb870-117">You must run it from your Front End Server or Standard Edition servers.</span></span>



</div>

<span data-ttu-id="fb870-118">定義 Edge Server 拓撲的程式是在拓撲產生器中完成。</span><span class="sxs-lookup"><span data-stu-id="fb870-118">The process to define your Edge Server topology is done in Topology Builder.</span></span> <span data-ttu-id="fb870-119">以下列出三個您可用來規劃和設定的主要 Edge Server 拓撲類型：</span><span class="sxs-lookup"><span data-stu-id="fb870-119">The three primary types of Edge Server topologies that you plan and configure are listed below:</span></span>

  - <span data-ttu-id="fb870-120">定義單一 Edge Server 的拓撲</span><span class="sxs-lookup"><span data-stu-id="fb870-120">To define the Topology for a Single Edge Server</span></span>

  - <span data-ttu-id="fb870-121">定義負載平衡 Edge Server 集區的拓撲</span><span class="sxs-lookup"><span data-stu-id="fb870-121">To define the Topology for a Load Balanced Edge Server Pool</span></span>

  - <span data-ttu-id="fb870-122">定義硬體負載平衡 Edge 集區的拓撲</span><span class="sxs-lookup"><span data-stu-id="fb870-122">To define the Topology for a Hardware Load Balanced Edge Pool</span></span>

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a><span data-ttu-id="fb870-123">若要定義單一 Edge Server 的拓撲</span><span class="sxs-lookup"><span data-stu-id="fb870-123">To define the topology for a single Edge Server</span></span>

1.  <span data-ttu-id="fb870-124">啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="fb870-124">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="fb870-125">在主控台樹狀目錄中，展開想要部署 Edge Server 的網站。</span><span class="sxs-lookup"><span data-stu-id="fb870-125">In the console tree, expand the site in which you want to deploy an Edge Server.</span></span>

3.  <span data-ttu-id="fb870-126">以滑鼠右鍵按一下 [ **Edge**集區]，然後按一下 [ **新增 edge 集**區]。</span><span class="sxs-lookup"><span data-stu-id="fb870-126">Right-click **Edge pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="fb870-127">在 **[定義新的 Edge 集區]** 中，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fb870-127">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="fb870-128">在 **[定義 Edge 集區 FQDN]** 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fb870-128">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="fb870-129">在 **[集區 FQDN]** 中，輸入 Edge Server 適用的內部介面的完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="fb870-129">In **Pool FQDN**, type the fully qualified domain name (FQDN) of the internal interface for the Edge Server.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="fb870-130">您指定的名稱必須與伺服器上設定的電腦名稱一模一樣。</span><span class="sxs-lookup"><span data-stu-id="fb870-130">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="fb870-131">根據預設，未加入網域的電腦，其電腦名稱是簡稱，而不是 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fb870-131">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="fb870-132">拓撲產生器使用 Fqdn，而非短名稱。</span><span class="sxs-lookup"><span data-stu-id="fb870-132">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="fb870-133">因此，在要部署為 Edge Server 的電腦 (未加入網域) 名稱中，您必須設定 DNS 尾碼。</span><span class="sxs-lookup"><span data-stu-id="fb870-133">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="fb870-134">當您為 Lync Server、Edge Server 及集區指派 FQDN 時，只能使用標準字元 (包括 A–Z、a–z、0–9 與連字號)。</span><span class="sxs-lookup"><span data-stu-id="fb870-134">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="fb870-135">請勿使用 Unicode 字元或底線。</span><span class="sxs-lookup"><span data-stu-id="fb870-135">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="fb870-136">當 FQDN 必須指派給憑證的 SN 時，外部 DNS 與公用 CA 通常不支援在 FQDN 中使用非標準字元。</span><span class="sxs-lookup"><span data-stu-id="fb870-136">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="fb870-137">如需將 DNS 尾碼新增至電腦名稱稱的詳細資訊，請參閱 <A href="lync-server-2013-configure-dns-for-edge-support.md">在 Lync Server 2013 中設定 edge 支援的 dns</A>。</span><span class="sxs-lookup"><span data-stu-id="fb870-137">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>
    
      - <span data-ttu-id="fb870-138">按一下 **[單一電腦集區]**，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fb870-138">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="fb870-139">在 **[選取功能]** 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fb870-139">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="fb870-140">如果您打算針對 SIP 存取服務、Lync Server 2013 Web 會議服務，以及 A/V Edge service 使用單一 FQDN 和 IP 位址，請選取 [ **使用單一 fqdn 和 Ip 位址** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fb870-140">If you plan to use a single FQDN and IP address for the SIP Access service, Lync Server 2013 Web Conferencing service, and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="fb870-141">如果您打算啟用同盟，請選取 [啟用此 Edge 集區的同盟 (連接埠 5061)]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fb870-141">If you plan to enable federation select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="fb870-p108">您可以選取此選項，但是只能將組織中的一個 Edge 集區或 Edge Server 發行到外部，以進行同盟。所有由同盟使用者 (包括公用立即訊息 (IM) 使用者) 進行的存取都會通過相同的 Edge 集區或單一 Edge Server。例如，如果您的部署範圍包括分別部署在紐約與倫敦的一個 Edge 集區或單一 Edge Server，而您針對紐約的 Edge 集區或單一 Edge Server 啟用了同盟支援，則同盟使用者的訊號流量會通過紐約的 Edge 集區或單一 Edge Server。儘管位於倫敦的內部使用者在致電倫敦的同盟使用者時，使用了倫敦集區或 Edge Server 以傳送音訊/視訊流量，與倫敦的使用者進行通訊時也適用這種情況。</span><span class="sxs-lookup"><span data-stu-id="fb870-p108">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="fb870-146">如果您打算針對部署支援 Extensible Messaging and Presence Protocol (XMPP)，請選取 [啟用 XMPP 同盟 (連接埠 5269)]\*\*\*\* 核取方塊</span><span class="sxs-lookup"><span data-stu-id="fb870-146">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="fb870-147">在 [選取 IP 選項]\*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fb870-147">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="fb870-148">**在內部介面上啟用 IPv4**：若要將 IPv4 位址套用至 edge Server 或 edge 集區內部介面，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fb870-148">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="fb870-149">**在內部介面上啟用 IPv6**：若要將 IPv6 位址套用至 edge Server 或 edge 集區內部介面，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fb870-149">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="fb870-150">**在外部介面上啟用 IPv4**：若要將 IPv4 位址套用至 edge Server 或 edge 集區外部介面，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fb870-150">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="fb870-151">**在外部介面上啟用 IPv6**：若要將 IPv6 位址套用至 edge Server 或 edge 集區外部介面，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fb870-151">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="fb870-152">您也可以將 Edge Server 或 Edge 集區設定為使用網路位址轉譯位址的外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="fb870-152">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="fb870-153">您可以藉由選取 [此 Edge 集區的外部 IP 位址由 NAT 轉譯]\*\*\*\* 核取方塊，來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="fb870-153">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

8.  <span data-ttu-id="fb870-154">在 **[外部 FQDN]** 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fb870-154">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="fb870-155">如果您在 **[選取功能]** 中已選擇針對 SIP 存取、Web 會議服務和 A/V Edge Service 使用單一 FQDN 和 IP 位址，請在 **[SIP 存取]** 中輸入外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fb870-155">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="fb870-p110">如果您選擇此選項，則必須為每個 Edge Service 分別指定不同的連接埠號碼 (建議的連接埠設定：Access Edge Service 為 5061、Web Conferencing Edge Service 為 444，A/V Edge Service 為 443)。選取此選項，不僅有助於防止潛在的連線問題，也可以簡化組態，原因是之後您就可以針對這三個服務使用相同的連接埠號碼 (例如，443)。</span><span class="sxs-lookup"><span data-stu-id="fb870-p110">If you choose this option, you must specify a different port number for each of the edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). Selecting this option can help prevent potential connectivity issues, and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="fb870-158">如果您在 **[選取功能]** 中未選擇使用單一 FQDN 和 IP 位址，請輸入 **[SIP 存取]**、**[Web 會議]** 和 **[音訊/視訊]** 的外部 FQDN，並保留預設連接埠。</span><span class="sxs-lookup"><span data-stu-id="fb870-158">If in **Select features** you did not chose to use a single FQDN and IP Address, type the External FQDNs for **SIP Access**, **Web Conferencing** and **Audio Video**, keeping the default ports.</span></span>

9.  <span data-ttu-id="fb870-159">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fb870-159">Click **Next**.</span></span>

10. <span data-ttu-id="fb870-p111">在 [定義內部 IP 位址]\*\*\*\* 中，視需要在 [內部 IPv4 位址]\*\*\*\* 和 [內部 IPv6 位址]\*\*\*\*  中鍵入 Edge Server 的 IP 位址。按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb870-p111">In **Define the Internal IP address**, type the IP address of your Edge Server in **Internal IPv4 address** and **Internal IPv6 address** as is appropriate for your requirements. Click **Next**.</span></span>

11. <span data-ttu-id="fb870-162">在 **[定義外部 IP 位址]** 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fb870-162">In **Define the External IP address**, do the following:</span></span>
    
      - <span data-ttu-id="fb870-163">如果您選擇針對 SIP 存取、Web 會議服務和 A/V Edge Service 使用單一 FQDN 和 IP 位址，請在 [SIP 存取]\*\*\*\* 中鍵入 Edge Server 的外部 IPv4 位址，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb870-163">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="fb870-164">如果您選擇使用 IPv6 位址，請在 [SIP 存取]\*\*\*\* 中鍵入 Edge Server 的外部 IPv6 位址，然後按 [下一步]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="fb870-164">If you chose to use IPv6 addresses, type the external IPv6 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="fb870-165">如果您未選擇針對 SIP 存取、Web 會議服務和 A/V Edge Service 使用單一 FQDN 和 IP 位址，請在 [SIP 存取]\*\*\*\*、[Web 會議]\*\*\*\* 和 [A/V 會議]\*\*\*\* 中鍵入 Edge Server 的外部 IPv4 位址，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb870-165">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="fb870-166">如果您選擇使用 IPv6 位址且未選擇針對 SIP 存取、Web 會議服務和 A/V Edge Service 使用單一 FQDN 和 IP 位址，請在 [SIP 存取]\*\*\*\*、[Web 會議]\*\*\*\* 和 [A/V 會議]\*\*\*\* 中鍵入 Edge Server 的外部 IPv6 位址，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb870-166">If you chose to use IPv6 addresses and did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="fb870-167">如果您未選擇啟用和指派 IPv6 位址，將不會看見此對話方塊。</span><span class="sxs-lookup"><span data-stu-id="fb870-167">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

        
        </div>

12. <span data-ttu-id="fb870-p112">如果您選擇使用 NAT，則會出現一個對話方塊。在 [A/V Edge Service 的公用 IPv4 位址]\*\*\*\* 中，鍵入要由 NAT 轉譯的公用 IPv4 位址，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb870-p112">If you chose to use NAT, a dialog box appears. In **Public IPv4 address for the A/V Edge service**, type the public IPv4 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fb870-170">這應該是 A/V Edge Service 的外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="fb870-170">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

13. <span data-ttu-id="fb870-p113">如果您選擇使用 NAT 和 IPv6 位址，則會出現一個對話方塊。在 [A/V Edge Service 的公用 IPv6 位址]\*\*\*\* 中，鍵入要由 NAT 轉譯的公用 IPv6 位址，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb870-p113">If you chose to use NAT and IPv6 addresses, a dialog box appears. In **Public IPv6 address for the A/V Edge service**, type the public IPv6 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fb870-173">這應該是 A/V Edge Service 的外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="fb870-173">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

14. <span data-ttu-id="fb870-p114">在 [定義下一個躍點]\*\*\*\* 的 [下一個躍點集區]\*\*\*\* 中，選取內部集區 (可以是前端集區或 Standard Edition 集區) 的名稱。或者，如果您的部署包括 Director，請選取 Director。然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb870-p114">In **Define the next hop**, in **Next hop pool**, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the Director. Then, click **Next**.</span></span>

15. <span data-ttu-id="fb870-177">在 **[建立前端集區的關聯]** 中，指定一個或多個要與此 Edge Server 相關聯的內部集區 (可包括前端集區及 Standard Edition 伺服器)，方法是選取要使用此 Edge Server 與所支援外部使用者進行通訊的內部集區的名稱。</span><span class="sxs-lookup"><span data-stu-id="fb870-177">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pools that are to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fb870-p115">針對 A/V 流量，每個內部集區都只能與一個負載平衡 Edge 集區或單一 Edge Server 相關聯。如果您已有與 Edge 集區或 Edge Server 相關聯的內部集區，則會出現警告，指出內部集區已與 Edge 集區或 Edge Server 相關聯。如果您選取已經與其他 Edge Server 相關聯的集區，將會使關聯產生變更。</span><span class="sxs-lookup"><span data-stu-id="fb870-p115">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

16. <span data-ttu-id="fb870-181">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="fb870-181">Click **Finish**.</span></span>

17. <span data-ttu-id="fb870-182">發行您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="fb870-182">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="fb870-183">為 DNS 負載平衡 Edge Server 集區定義拓撲</span><span class="sxs-lookup"><span data-stu-id="fb870-183">To define the topology for a DNS load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="fb870-184">啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="fb870-184">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="fb870-185">在主控台樹狀目錄中，展開想要部署 Edge Server 的網站。</span><span class="sxs-lookup"><span data-stu-id="fb870-185">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="fb870-186">以滑鼠右鍵按一下 [Edge 集區]\*\*\*\*，然後按一下 [新增 Edge 集區]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb870-186">Right-click **Edge Pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="fb870-187">在 [定義新的 Edge 集區]\*\*\*\* 中，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb870-187">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="fb870-188">在 [定義 Edge 集區 FQDN]\*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fb870-188">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="fb870-189">在 [集區 FQDN]\*\*\*\* 中，鍵入適用於 Edge 集區之內部連線的完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="fb870-189">In **Pool FQDN**, type the fully qualified domain name (FQDN) for the internal connection of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="fb870-190">您為集區指定的名稱必須是內部 Edge 集區名稱。</span><span class="sxs-lookup"><span data-stu-id="fb870-190">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="fb870-191">此名稱必須定義為 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fb870-191">This must be defined as a FQDN.</span></span> <span data-ttu-id="fb870-192">拓撲產生器使用 Fqdn，而非短名稱。</span><span class="sxs-lookup"><span data-stu-id="fb870-192">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="fb870-193">當您為 Lync Server、Edge Server 以及集區指派 FQDN 時，只能使用標準字元 (包括 A–Z、a–z、0–9 與連字號)。</span><span class="sxs-lookup"><span data-stu-id="fb870-193">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="fb870-194">請勿使用 Unicode 字元或底線。</span><span class="sxs-lookup"><span data-stu-id="fb870-194">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="fb870-195">當必須將 FQDN 指派給憑證的 SN 時，外部 DNS 與公用 CA 通常不支援在 FQDN 中使用非標準字元。</span><span class="sxs-lookup"><span data-stu-id="fb870-195">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
      - <span data-ttu-id="fb870-196">按一下 [多部電腦集區]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb870-196">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="fb870-197">在 [選取功能]\*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fb870-197">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="fb870-198">如果您打算針對 SIP 存取、Lync Server 2013 Web 會議服務和 A/V Edge service 使用單一 FQDN 和 IP 位址，請選取 [ **使用單一 fqdn 和 Ip 位址** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fb870-198">If you plan to use a single FQDN and IP address for the SIP access, Lync Server 2013 Web Conferencing service and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="fb870-p117">如果您打算啟用同盟，請選取 [啟用此 Edge 集區的同盟 (連接埠 5061)]\*\*\*\* 核取方塊。按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb870-p117">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box. Click **Next**</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="fb870-p118">您可以選取此選項，但是只能將組織中的一個 Edge 集區或一部 Edge Server 發行到外部，以進行同盟。所有由同盟使用者 (包括公用立即訊息 (IM) 使用者) 進行的存取都會通過相同的 Edge 集區或單一 Edge Server。例如，如果您的部署包括了分別部署在紐約與倫敦的一個 Edge 集區或單一 Edge Server，而您針對紐約的 Edge 集區或單一 Edge Server 啟用了同盟支援，則同盟使用者的訊號流量會通過紐約的 Edge 集區或單一 Edge Server。儘管位於倫敦的內部使用者在致電倫敦的同盟使用者時，使用了倫敦集區或 Edge Server 來傳送 A/V 流量，與倫敦的使用者進行通訊時也適用這種情況。</span><span class="sxs-lookup"><span data-stu-id="fb870-p118">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="fb870-205">如果您打算針對部署支援 Extensible Messaging and Presence Protocol (XMPP)，請選取 [啟用 XMPP 同盟 (連接埠 5269)]\*\*\*\* 核取方塊</span><span class="sxs-lookup"><span data-stu-id="fb870-205">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="fb870-206">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb870-206">Click **Next**.</span></span>

8.  <span data-ttu-id="fb870-207">在 [選取 IP 選項]\*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fb870-207">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="fb870-208">**在內部介面上啟用 IPv4**：若要將 IPv4 位址套用至 edge Server 或 edge 集區內部介面，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fb870-208">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="fb870-209">**在內部介面上啟用 IPv6**：若要將 IPv6 位址套用至 edge Server 或 edge 集區內部介面，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fb870-209">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="fb870-210">**在外部介面上啟用 IPv4**：若要將 IPv4 位址套用至 edge Server 或 edge 集區外部介面，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fb870-210">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="fb870-211">**在外部介面上啟用 IPv6**：若要將 IPv6 位址套用至 edge Server 或 edge 集區外部介面，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fb870-211">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="fb870-212">您也可以將 Edge Server 或 Edge 集區設定為使用網路位址轉譯位址的外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="fb870-212">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="fb870-213">您可以藉由選取 [此 Edge 集區的外部 IP 位址由 NAT 轉譯]\*\*\*\* 核取方塊，來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="fb870-213">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

9.  <span data-ttu-id="fb870-214">在 [外部 FQDN]\*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fb870-214">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="fb870-215">如果您在 [選取功能]\*\*\*\* 中選擇針對 SIP 存取、Web 會議服務和 A/V Edge Service 使用單一 FQDN 和 IP 位址，請在 [SIP 存取]\*\*\*\* 中輸入外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fb870-215">If in **Select features** you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="fb870-p120">如果您選擇此選項，則必須為每個 Edge Service 指定不同的連接埠號碼 (建議的連接埠設定：Access Edge Service 為 5061、Web Conferencing Edge Service 為 444，A/V Edge Service 為 443)。選取此選項，不僅有助於防止潛在的連線問題，也可以簡化組態，因為之後您就可針對這三個服務使用相同的連接埠號碼 (例如，443)。</span><span class="sxs-lookup"><span data-stu-id="fb870-p120">If you choose this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="fb870-p121">如果您在 [選取功能]\*\*\*\* 中未選擇使用單一 FQDN 和 IP 位址，請在 [SIP 存取]\*\*\*\* 中，鍵入您為 Edge 集區之對外端選擇的 FQDN。在 [Web 會議]\*\*\*\* 中，鍵入您為此 Edge 集區伺服器之對外端選擇的 IP 位址。在 [音訊/視訊]\*\*\*\* 中，鍵入您為 Edge 集區之對外端選擇的 FQDN。請使用預設連接埠。</span><span class="sxs-lookup"><span data-stu-id="fb870-p121">If in **Select features** you did not chose to use a single FQDN and IP Address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**. In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool. In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool. Use the default ports.</span></span>

10. <span data-ttu-id="fb870-222">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb870-222">Click **Next**.</span></span>

11. <span data-ttu-id="fb870-223">在 **[定義此集區中的電腦]** 中，按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="fb870-223">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="fb870-224">在 [內部 FQDN 和 IP 位址]\*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fb870-224">In **Internal FQDN and IP address**, do the following:</span></span>
    
      - <span data-ttu-id="fb870-225">在 [內部 IPv4 位址]\*\*\*\* 中，針對想要在此集區中建立的第一部 Edge Server 適用的需求鍵入 IPv4 位址和 [內部 IPv6 位址]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb870-225">In **Internal IPv4 address**, type the IPv4 address and **Internal IPv6 address** as is appropriate for your requirements for the first Edge Server that you want to create in this pool.</span></span>
    
      - <span data-ttu-id="fb870-226">在 [內部 FQDN]\*\*\*\* 中，鍵入想要在此集區中建立的第一部 Edge Server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fb870-226">In **Internal FQDN**, type the FQDN of the first Edge Server that you want to create in this pool.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="fb870-227">您指定的名稱必須與伺服器上設定的電腦名稱一模一樣。</span><span class="sxs-lookup"><span data-stu-id="fb870-227">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="fb870-228">根據預設，未加入網域的電腦，其電腦名稱是簡短名稱，而不是 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fb870-228">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="fb870-229">拓撲產生器使用 Fqdn，而非短名稱。</span><span class="sxs-lookup"><span data-stu-id="fb870-229">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="fb870-230">因此，在要部署為 Edge Server 的電腦 (未加入網域) 名稱中，您必須設定 DNS 尾碼。</span><span class="sxs-lookup"><span data-stu-id="fb870-230">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="fb870-231">當您為 Lync Server、Edge Server、集區及陣列指派 FQDN 時，只能使用標準字元 (包括 A–Z、a–z、0–9 與連字號)。</span><span class="sxs-lookup"><span data-stu-id="fb870-231">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, pools, and arrays.</span></span> <span data-ttu-id="fb870-232">請勿使用 Unicode 字元或底線。</span><span class="sxs-lookup"><span data-stu-id="fb870-232">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="fb870-233">當 FQDN 必須指派給憑證的 SN 時，外部 DNS 與公用 CA 通常不支援在 FQDN 中使用非標準字元。</span><span class="sxs-lookup"><span data-stu-id="fb870-233">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="fb870-234">如需將 DNS 尾碼新增至電腦名稱稱的詳細資訊，請參閱 <A href="lync-server-2013-configure-dns-for-edge-support.md">在 Lync Server 2013 中設定 edge 支援的 dns</A>。</span><span class="sxs-lookup"><span data-stu-id="fb870-234">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>

13. <span data-ttu-id="fb870-235">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb870-235">Click **Next**.</span></span>

14. <span data-ttu-id="fb870-236">在 **[定義外部 IP 位址]** 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fb870-236">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="fb870-237">如果您選擇針對 SIP 存取、Web 會議服務和 A/V Edge Service 使用單一 FQDN 和 IP 位址，請在 **[SIP 存取]** 中輸入 Edge Server 的外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="fb870-237">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="fb870-p123">如果您未選擇針對 SIP 存取、Web 會議服務和 A/V 會議服務使用單一 FQDN 和 IP 位址，請在 [SIP 存取]\*\*\*\* 中鍵入您已為此 Edge 集區伺服器之對外端選擇的 IP 位址。在 [Web 會議]\*\*\*\* 中，鍵入您已為此 Edge 集區伺服器之對外端選擇的 IP 位址。在 [A/V 會議]\*\*\*\* 中，鍵入您已為此 Edge 集區伺服器之對外端選擇的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="fb870-p123">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

15. <span data-ttu-id="fb870-241">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb870-241">Click **Next**.</span></span>

16. <span data-ttu-id="fb870-242">如果您選擇啟用 IPv6 位址，請在 [定義外部 IP 位址]\*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fb870-242">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="fb870-243">如果您選擇針對 SIP 存取、Web 會議服務和 A/V Edge Service 使用單一 FQDN 和 IP 位址，請在 [SIP 存取]\*\*\*\* 中鍵入 Edge Server 的外部 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="fb870-243">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="fb870-p124">如果您未選擇針對 SIP 存取、Web 會議服務和 A/V 會議服務使用單一 FQDN 和 IP 位址，請在 [SIP 存取]\*\*\*\* 中鍵入您已為此 Edge 集區伺服器之對外端選擇的 IPv6 位址。在 [Web 會議]\*\*\*\* 中，鍵入您已為此 Edge 集區伺服器之對外端選擇的 IPv6 位址。在 [A/V 會議]\*\*\*\* 中，鍵入您已為此 Edge 集區伺服器之對外端選擇的 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="fb870-p124">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fb870-247">如果您未選擇啟用和指派 IPv6 位址，將不會看見此對話方塊。</span><span class="sxs-lookup"><span data-stu-id="fb870-247">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

17. <span data-ttu-id="fb870-248">按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb870-248">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fb870-249">您現在可以在 [定義此集區中的電腦]<STRONG></STRONG> 對話方塊中看到剛才在集區中建立的第一部 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="fb870-249">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

18. <span data-ttu-id="fb870-250">在 [定義此集區中的電腦]\*\*\*\* 中，按一下 [新增]\*\*\*\*，然後針對想要新增至 Edge 集區的第二部 Edge Server 重複執行步驟 11 到 14。</span><span class="sxs-lookup"><span data-stu-id="fb870-250">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to you Edge pool.</span></span>

19. <span data-ttu-id="fb870-251">重複執行步驟 11 到 14 之後，按一下 [定義此集區中的電腦]\*\*\*\* 中的 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb870-251">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fb870-252">此時，您可以在集區中同時看到這兩部 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="fb870-252">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

20. <span data-ttu-id="fb870-p125">如果您選擇使用 NAT，則會出現一個對話方塊。在 [公用 IP 位址]\*\*\*\* 中，鍵入要由 NAT 轉譯的公用 IPv4 和 IPv6 (如果適當) 位址，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb870-p125">If you chose to use NAT, a dialog box appears. In **Public IP address**, type the public IPv4 and IPv6 (as appropriate) addresses to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fb870-255">此處的 IP 位址應是 A/V Edge 的外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="fb870-255">This should be the external IP Address of the A/V Edge.</span></span>

    
    </div>

21. <span data-ttu-id="fb870-p126">在 [定義下一個躍點]\*\*\*\* 的 [下一個躍點集區]\*\*\*\* 清單中，選取內部集區 (可以是前端集區或 Standard Edition 集區) 的名稱。或者，如果您的部署包括 Director，請選取 Director 的名稱。然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb870-p126">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the name of the Director. Then, click **Next**.</span></span>

22. <span data-ttu-id="fb870-259">在 **[建立前端集區的關聯]** 中，指定一個或多個要與此 Edge Server 相關聯的內部集區 (可包括前端集區及 Standard Edition 伺服器)，方法是選取要使用此 Edge Server 與所支援外部使用者進行通訊的內部集區的名稱。</span><span class="sxs-lookup"><span data-stu-id="fb870-259">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fb870-p127">針對 A/V 流量，每個內部集區都只能與一個負載平衡 Edge 集區或單一 Edge Server 相關聯。如果您已有與 Edge 集區或 Edge Server 相關聯的內部集區，則會出現警告，指出內部集區已與 Edge 集區或 Edge Server 相關聯。如果您選取已經與其他 Edge Server 相關聯的集區，將會使關聯產生變更。</span><span class="sxs-lookup"><span data-stu-id="fb870-p127">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

23. <span data-ttu-id="fb870-263">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="fb870-263">Click **Finish**.</span></span>

24. <span data-ttu-id="fb870-264">發行您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="fb870-264">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="fb870-265">定義硬體負載平衡 Edge Server 集區的拓撲</span><span class="sxs-lookup"><span data-stu-id="fb870-265">To define the topology for a hardware load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="fb870-266">啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="fb870-266">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="fb870-267">在主控台樹狀目錄中，展開想要部署 Edge Server 的網站。</span><span class="sxs-lookup"><span data-stu-id="fb870-267">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="fb870-268">以滑鼠右鍵按一下 [ **Edge**集區]，然後選取 [ **新增 edge 集**區]。</span><span class="sxs-lookup"><span data-stu-id="fb870-268">Right-click **Edge Pools**, and then select **New Edge Pool**.</span></span>

4.  <span data-ttu-id="fb870-269">在 **[定義新的 Edge 集區]** 中，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fb870-269">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="fb870-270">在 **[定義 Edge 集區 FQDN]** 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fb870-270">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="fb870-271">在 [FQDN]\*\*\*\* 中，鍵入您已為 Edge 集區之對內端選擇的完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="fb870-271">In **FQDN**, type the fully qualified domain name (FQDN) you have chosen for the internal side of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="fb870-272">您為集區指定的名稱必須是內部 Edge 集區名稱。</span><span class="sxs-lookup"><span data-stu-id="fb870-272">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="fb870-273">此名稱必須定義為 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fb870-273">This must be defined as a FQDN.</span></span> <span data-ttu-id="fb870-274">拓撲產生器使用 Fqdn，而非短名稱。</span><span class="sxs-lookup"><span data-stu-id="fb870-274">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="fb870-275">當您為 Lync Server、Edge Server 以及集區指派 FQDN 時，只能使用標準字元 (包括 A–Z、a–z、0–9 與連字號)。</span><span class="sxs-lookup"><span data-stu-id="fb870-275">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="fb870-276">請勿使用 Unicode 字元或底線。</span><span class="sxs-lookup"><span data-stu-id="fb870-276">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="fb870-277">當 FQDN 必須指派給憑證的 SN 時，外部 DNS 與公用 CA 通常不支援在 FQDN 中使用非標準字元。</span><span class="sxs-lookup"><span data-stu-id="fb870-277">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
    <!-- end list -->
    
      - <span data-ttu-id="fb870-278">按一下 [ **多部電腦集**區]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fb870-278">Click **Multiple computer pool**, and then **Next**.</span></span>

6.  <span data-ttu-id="fb870-279">在 **[選取功能]** 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fb870-279">In **Select features** do the following:</span></span>
    
      - <span data-ttu-id="fb870-280">如果您打算針對 SIP 存取服務、Lync Server Web 會議服務和 A/V Edge service 使用單一 FQDN 和 IP 位址，請選取 [ **使用單一 fqdn & IP 位址** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fb870-280">If you plan to use a single FQDN and IP address for the SIP access service, Lync Server Web Conferencing service, and A/V Edge service, select the **Use a single FQDN & IP Address** check box.</span></span>
    
      - <span data-ttu-id="fb870-281">如果您打算啟用同盟，請選取 **[啟用此 Edge 集區的同盟 (連接埠 5061)]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fb870-281">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="fb870-p129">您可以選取此選項，但是只能將組織中的一個 Edge 集區或一部 Edge Server 發行到外部，以進行同盟。所有由同盟使用者 (包括公用立即訊息 (IM) 使用者) 進行的存取都會通過相同的 Edge 集區或單一 Edge Server。例如，如果您的部署包括了分別部署於紐約與倫敦的一個 Edge 集區或單一 Edge Server，而您針對紐約的 Edge 集區或單一 Edge Server 啟用了同盟支援，則同盟使用者的訊號流量會通過紐約的 Edge 集區或單一 Edge Server。儘管位於倫敦的內部使用者在致電倫敦的同盟使用者時，使用了倫敦集區或 Edge Server 來傳送 A/V 流量，與倫敦的使用者進行通訊時也適用這種情況。</span><span class="sxs-lookup"><span data-stu-id="fb870-p129">You can select this option, but only one Edge pool or Edge Server in your organization may be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="fb870-286">如果您打算針對部署支援 Extensible Messaging and Presence Protocol (XMPP)，請選取 [啟用 XMPP 同盟 (連接埠 5269)]\*\*\*\* 核取方塊</span><span class="sxs-lookup"><span data-stu-id="fb870-286">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="fb870-287">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb870-287">Click **Next**.</span></span>

8.  <span data-ttu-id="fb870-288">在 [選取 IP 選項]\*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fb870-288">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="fb870-289">**在內部介面上啟用 IPv4**：若要將 IPv4 位址套用至 edge Server 或 edge 集區內部介面，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fb870-289">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="fb870-290">**在內部介面上啟用 IPv6**：若要將 IPv6 位址套用至 edge Server 或 edge 集區內部介面，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fb870-290">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="fb870-291">**在外部介面上啟用 IPv4**：若要將 IPv4 位址套用至 edge Server 或 edge 集區外部介面，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fb870-291">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="fb870-292">**在外部介面上啟用 IPv6**：若要將 IPv6 位址套用至 edge Server 或 edge 集區外部介面，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fb870-292">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="fb870-p130"><STRONG>「請不要」</STRONG>選取 [由 NAT 轉譯此 Edge 集區的外部 IP 位址]<STRONG></STRONG> 核取方塊。當您使用硬體負載平衡時，不支援網路位址轉譯 (NAT)。</span><span class="sxs-lookup"><span data-stu-id="fb870-p130"><STRONG>Do Not</STRONG> select the <STRONG>The external IP address of the Edge pool is translated by NAT</STRONG> check box. Network address translation (NAT) is not supported when you are using hardware load balancing.</span></span>

    
    </div>

9.  <span data-ttu-id="fb870-295">在 [外部 FQDN]\*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fb870-295">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="fb870-296">如果您在 [選取功能]\*\*\*\* 中選擇針對 SIP 存取、Web 會議服務和 A/V Edge Service 使用單一 FQDN 和 IP 位址，請在 [SIP 存取]\*\*\*\* 中鍵入外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fb870-296">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="fb870-p131">如果您選取此選項，則必須為每個 Edge Service 分別指定不同的連接埠號碼 (建議的連接埠設定：Access Edge Service 為 5061、Web Conferencing Edge Service 為 444，A/V Edge Service 為 443)。選取此選項，不僅有助於防止潛在的連線問題，也可以簡化組態，因為之後您就可以針對這三個服務使用相同的連接埠號碼 (例如，443)。</span><span class="sxs-lookup"><span data-stu-id="fb870-p131">If you choose to select this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="fb870-p132">如果您在 [選取功能]\*\*\*\* 中未選擇使用單一 FQDN 和 IP 位址，請在 [SIP 存取]\*\*\*\* 中，鍵入您為 Edge 集區之對外端選擇的 FQDN。在 [Web 會議]\*\*\*\* 中，鍵入您為 Edge 集區之對外端選擇的 FQDN。在 [音訊/視訊]\*\*\*\* 中，鍵入您為 Edge 集區之對外端選擇的 FQDN。請使用預設連接埠。</span><span class="sxs-lookup"><span data-stu-id="fb870-p132">If in **Select features** you did not chose to use a single FQDN and IP address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**. In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool. In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool. Use the default ports.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="fb870-303">這些會是集區的對外虛擬 IP (VIP) FQDN。</span><span class="sxs-lookup"><span data-stu-id="fb870-303">These will be the publicly facing virtual IP (VIP) FQDNs for the pool.</span></span>

        
        </div>

10. <span data-ttu-id="fb870-304">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb870-304">Click **Next**.</span></span>

11. <span data-ttu-id="fb870-305">在 [定義此集區中的電腦]\*\*\*\* 中，按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb870-305">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="fb870-306">在 [定義外部 IP 位址]\*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fb870-306">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="fb870-307">如果您選擇針對 SIP 存取、Web 會議服務和 A/V Edge Service 使用單一 FQDN 和 IP 位址，請在 [SIP 存取]\*\*\*\* 中鍵入 Edge Server 的外部 IPv4 位址，並在 [SIP 存取]\*\*\*\* 中鍵入 Edge Server 的外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="fb870-307">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**.external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="fb870-p133">如果您未選擇針對 SIP 存取、Web 會議服務和 A/V 會議服務使用單一 FQDN 和 IP 位址，請在 [SIP 存取]\*\*\*\* 中鍵入您已為此 Edge 集區伺服器之對外端選擇的 IP 位址。在 [Web 會議]\*\*\*\* 中，鍵入您為此 Edge 集區伺服器之對外端選擇的 IP 位址。在 [A/V 會議]\*\*\*\* 中，鍵入您已為此 Edge 集區伺服器之對外端選擇的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="fb870-p133">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

13. <span data-ttu-id="fb870-311">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb870-311">Click **Next**.</span></span>

14. <span data-ttu-id="fb870-312">如果您選擇啟用 IPv6 位址，請在 [定義外部 IP 位址]\*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fb870-312">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="fb870-313">如果您選擇針對 SIP 存取、Web 會議服務和 A/V Edge Service 使用單一 FQDN 和 IP 位址，請在 [SIP 存取]\*\*\*\* 中鍵入 Edge Server 的外部 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="fb870-313">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="fb870-p134">如果您未選擇針對 SIP 存取、Web 會議服務和 A/V 會議服務使用單一 FQDN 和 IP 位址，請在 [SIP 存取]\*\*\*\* 中鍵入您已為此 Edge 集區伺服器之對外端選擇的 IPv6 位址。在 [Web 會議]\*\*\*\* 中，鍵入您已為此 Edge 集區伺服器之對外端選擇的 IPv6 位址。在 [A/V 會議]\*\*\*\* 中，鍵入您已為此 Edge 集區伺服器之對外端選擇的 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="fb870-p134">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fb870-317">如果您未選擇啟用和指派 IPv6 位址，將不會看見此對話方塊。</span><span class="sxs-lookup"><span data-stu-id="fb870-317">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

15. <span data-ttu-id="fb870-318">按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb870-318">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fb870-319">您現在可以在 <STRONG>[定義此集區中的電腦]</STRONG> 對話方塊中看到剛才在集區中建立的第一個 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="fb870-319">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

16. <span data-ttu-id="fb870-320">在 [定義此集區中的電腦]\*\*\*\* 中，按一下 [新增]\*\*\*\*，然後針對想要新增至 Edge 集區的第二個 Edge Server 重複步驟 11 到 14。</span><span class="sxs-lookup"><span data-stu-id="fb870-320">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to your Edge pool.</span></span>

17. <span data-ttu-id="fb870-321">重複步驟 11 到 14 之後，按一下 **[定義此集區中的電腦]** 中的 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fb870-321">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fb870-322">此時，您可以在集區中同時看到這兩個 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="fb870-322">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

18. <span data-ttu-id="fb870-p135">在 **[定義下一個躍點]** 的 **[下一個躍點集區]** 清單中，選取內部集區 (可以是前端集區或 Standard Edition 集區) 的名稱。或者，如果您的部署包括 Director，請選取 Director 的名稱。然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fb870-p135">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the name of the Director. Then, click **Next**.</span></span>

19. <span data-ttu-id="fb870-326">在 **[建立前端集區的關聯]** 中，指定一個或多個要與此 Edge Server 相關聯的內部集區 (可包括前端集區及 Standard Edition 伺服器)，方法是選取要使用此 Edge Server 與所支援外部使用者進行通訊的內部集區的名稱。</span><span class="sxs-lookup"><span data-stu-id="fb870-326">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fb870-p136">針對 A/V 流量，每個內部集區都只能與一個負載平衡 Edge 集區或單一 Edge Server 相關聯。如果您已有與 Edge 集區或 Edge Server 相關聯的內部集區，則會出現警告，指出內部集區已與 Edge 集區或 Edge Server 相關聯。如果您選取已經與其他 Edge Server 相關聯的集區，將會使關聯產生變更。</span><span class="sxs-lookup"><span data-stu-id="fb870-p136">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

20. <span data-ttu-id="fb870-330">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="fb870-330">Click **Finish**.</span></span>

21. <span data-ttu-id="fb870-331">發行您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="fb870-331">Publish your topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

