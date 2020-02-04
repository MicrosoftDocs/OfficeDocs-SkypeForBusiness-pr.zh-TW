---
title: Lync Server 2013：在拓撲建立器中定義中繼伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Mediation Server in Topology Builder
ms:assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398391(v=OCS.15)
ms:contentKeyID: 48184217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdff7da86bd7298511ea0ef384b2736a47882a03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="d4321-102">在 Lync Server 2013 的拓撲產生器中定義中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="d4321-102">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4321-103">_**主題上次修改日期：** 2013-03-25_</span><span class="sxs-lookup"><span data-stu-id="d4321-103">_**Topic Last Modified:** 2013-03-25_</span></span>

<span data-ttu-id="d4321-104">請依照本主題中的步驟，使用拓撲 Builder 來定義獨立的中繼伺服器，或在您先前沒有部署企業語音的網站上使用 [collocated] 池。</span><span class="sxs-lookup"><span data-stu-id="d4321-104">Follow the steps in this topic to use Topology Builder to define a stand-alone Mediation Server or a pool collocated with a Front End pool at a site for which you did not previously deploy Enterprise Voice.</span></span>

<span data-ttu-id="d4321-105">您可以使用系統管理員群組成員的帳戶來定義拓撲。</span><span class="sxs-lookup"><span data-stu-id="d4321-105">You can define a topology using an account that is a member of the Administrators group.</span></span>

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a><span data-ttu-id="d4321-106">定義轉送伺服器 collocated 到前端池</span><span class="sxs-lookup"><span data-stu-id="d4321-106">Define Mediation Server collocated to a Front End pool</span></span>

<span data-ttu-id="d4321-107">請依照本主題中的步驟，使用拓撲建立器，在尚未部署企業語音的網站中，將中繼伺服器 collocated 定義為 [前端] 池。</span><span class="sxs-lookup"><span data-stu-id="d4321-107">Follow the steps in this topic to use Topology Builder to define a Mediation Server collocated to a Front End pool in a site where Enterprise Voice has not been previously deployed.</span></span>

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="d4321-108">將中繼伺服器新增到前端池</span><span class="sxs-lookup"><span data-stu-id="d4321-108">To Add a Mediation Server to a Front End pool</span></span>

1.  <span data-ttu-id="d4321-109">啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="d4321-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="d4321-110">在拓撲建立器中，在主控台樹狀結構中，展開您要為其定義前端池的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="d4321-110">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>

3.  <span data-ttu-id="d4321-111">在主控台樹狀結構中，以滑鼠右鍵按一下您想要的前端池類型，然後按一下 [**新增前端池 ...**]。</span><span class="sxs-lookup"><span data-stu-id="d4321-111">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>

4.  <span data-ttu-id="d4321-112">流覽 [**定義新的前臺端池**] 嚮導，直到您到達 [**選取 collocated 伺服器角色**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="d4321-112">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>

5.  <span data-ttu-id="d4321-113">在 [**選取 collocated 伺服器角色**] 中，核取 [ **Collocate 中繼伺服器**] 的選項。</span><span class="sxs-lookup"><span data-stu-id="d4321-113">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="d4321-114">如果您選取的 [前端] 池類型是 [企業版]，則會將轉送伺服器元件安裝在該前端池的所有前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="d4321-114">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="d4321-115">中繼伺服器所使用的<STRONG>下一個躍點池</STRONG>將是中繼伺服器正在 Collocated 的前端池。</span><span class="sxs-lookup"><span data-stu-id="d4321-115">The <STRONG>Next hop pool</STRONG> used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="d4321-116">中繼伺服器所使用的<STRONG>邊緣池</STRONG>將是與中繼伺服器所 Collocated 之前端池相關聯的同一個 edge 池。</span><span class="sxs-lookup"><span data-stu-id="d4321-116">The <STRONG>Edge pool</STRONG> used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="d4321-117">按一下 [**設為預設值**]，使用此前端池將來自 Microsoft Office 通訊伺服器 2007 R2 的呼叫路由至 PSTN。</span><span class="sxs-lookup"><span data-stu-id="d4321-117">Click **Make Default** to use this Front End pool to route calls from Microsoft Office Communications Server 2007 R2 to the PSTN.</span></span>

7.  <span data-ttu-id="d4321-118">當您完成將一或多個對等專案關聯到前端池之後，按一下 **[完成]** 。</span><span class="sxs-lookup"><span data-stu-id="d4321-118">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d4321-119">在您繼續進行企業語音部署程式中的下一個步驟之前，請確認已將中繼伺服器池（例如，擁有中繼伺服器元件 collocated 的前臺端池）使用您所指定的 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="d4321-119">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span>

    
    </div>

8.  <span data-ttu-id="d4321-120">接著，遵循在[Lync server 2013 中發佈拓撲](lync-server-2013-publish-the-topology.md)中的程式，在 [部署指南] 檔中，將轉送伺服器新增到您的拓撲，然後再繼續進行下一個修改中繼伺服器的偵聽埠（如有需要）。</span><span class="sxs-lookup"><span data-stu-id="d4321-120">Next, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment Guide documentation to add the Mediation Server to your topology before proceeding to the next step of modifying the listening ports of the Mediation Server if needed.</span></span> <span data-ttu-id="d4321-121">您必須在每次使用 [拓撲建立器] 定義或修改拓撲時發佈您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="d4321-121">You must publish your topology each time you use Topology Builder to define or modify your topology.</span></span>

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a><span data-ttu-id="d4321-122">定義獨立的中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="d4321-122">Define stand-alone Mediation Server</span></span>

<span data-ttu-id="d4321-123">請依照本主題中的步驟，使用拓撲建立器，在尚未預先部署企業語音的網站上定義獨立的中繼伺服器或池。</span><span class="sxs-lookup"><span data-stu-id="d4321-123">Follow the steps in this topic to use Topology Builder to define a stand-alone Mediation Server or pool at a site where Enterprise Voice has not been previously deployed.</span></span>

<span data-ttu-id="d4321-124">如果您已在此網站上將已部署的轉送伺服器 collocated 到前端池，您可以略過此區段，並[在 Lync server 2013 中安裝用於轉送服務伺服器](lync-server-2013-install-the-files-for-mediation-server.md)的檔案，然後再繼續[在 lync server 2013 中設定 trunks](lync-server-2013-configuring-trunks.md)。</span><span class="sxs-lookup"><span data-stu-id="d4321-124">If you already deployed Mediation Servers collocated to Front End pools at this site, you can skip this section and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) before proceeding to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d4321-125">本節假設您已安裝至少一個前端池，如在<A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013 定義及設定前端池或標準版伺服器中</A>所述，並在部署指南檔中<A href="lync-server-2013-publish-the-topology.md">發佈 lync server 2013 中的拓撲</A>。</span><span class="sxs-lookup"><span data-stu-id="d4321-125">This section assumes that you have already setup at least one Front End pool, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment Guide documentation.</span></span>



</div>

<div>

## <a name="to-add-a-mediation-server"></a><span data-ttu-id="d4321-126">新增中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="d4321-126">To Add a Mediation Server</span></span>

1.  <span data-ttu-id="d4321-127">啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="d4321-127">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="d4321-128">在拓撲建立器中，在主控台樹狀結構中，展開您要定義轉送伺服器的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="d4321-128">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>

3.  <span data-ttu-id="d4321-129">在主控台樹中，以滑鼠右鍵按一下 [**轉送緩衝集區**] 節點，然後按一下 [**轉送伺服器池**]。</span><span class="sxs-lookup"><span data-stu-id="d4321-129">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>

4.  <span data-ttu-id="d4321-130">在 [**定義新的仲介池**] 中，輸入中繼伺服器池的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="d4321-130">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>

5.  <span data-ttu-id="d4321-131">接著，請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="d4321-131">Next, do one of the following:</span></span>
    
      - <span data-ttu-id="d4321-132">如果您想要在池中部署多個轉送伺服器來提供高可用性，請選取 [**多個電腦池**]。</span><span class="sxs-lookup"><span data-stu-id="d4321-132">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d4321-133">您必須部署 DNS 負載平衡，以支援擁有多個轉送伺服器的中繼伺服器池。</span><span class="sxs-lookup"><span data-stu-id="d4321-133">You must deploy DNS load balancing to support Mediation Server pools that have multiple Mediation Servers.</span></span> <span data-ttu-id="d4321-134">如需詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-dns-load-balancing.md">Lync server 2013</A>中的 [在中繼伺服器池中使用 Dns 負載平衡] 區段。</span><span class="sxs-lookup"><span data-stu-id="d4321-134">For details, see the Using DNS Load Balancing on Mediation Server Pools section of <A href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</A> in the Planning documentation.</span></span>

        
        </div>
    
      - <span data-ttu-id="d4321-135">如果您只想在池中部署一個轉送伺服器，因為您不需要高可用性，請選取 [**單一電腦池**]。</span><span class="sxs-lookup"><span data-stu-id="d4321-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="d4321-136">略過下列步驟。</span><span class="sxs-lookup"><span data-stu-id="d4321-136">Skip the following step.</span></span>

6.  <span data-ttu-id="d4321-137">如果您在上一個步驟中選取了**多個電腦池**，請在 [**定義此池中的電腦**] 專案中，按一下 [**電腦 FQDN**]，輸入池中每個伺服器的 FQDN，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="d4321-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="d4321-138">針對您要新增至池中的所有其他轉送伺服器，重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="d4321-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="d4321-139">在池中定義所有電腦之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d4321-139">When you have defined all the computers in the pool, click **Next**.</span></span>

7.  <span data-ttu-id="d4321-140">在 [**選取下一個躍點]** 頁面上，按一下 **[下一個躍點池]**，然後按一下將使用此中繼伺服器池的前端池 FQDN，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d4321-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>

8.  <span data-ttu-id="d4321-141">在 [**選取邊緣伺服器**] 頁面上，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="d4321-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
      - <span data-ttu-id="d4321-142">如果您想要提供支援企業語音的 PSTN 連線，請在 [**選取此中繼伺服器所使用的 Edge 池**] 底下，按一下將使用此轉送服務伺服器池的 edge 伺服器池，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d4321-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
      - <span data-ttu-id="d4321-143">如果您不打算為企業語音啟用外部使用者，或者如果您不想在內部網路外部向使用者提供 PSTN 連線，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d4321-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>

9.  <span data-ttu-id="d4321-144">接著，按照在您的部署檔中[發佈 Lync server 2013](lync-server-2013-publish-the-topology.md)中的拓撲中的程式，將轉送伺服器新增到拓撲。</span><span class="sxs-lookup"><span data-stu-id="d4321-144">Next, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation to add the Mediation Server to the topology.</span></span> <span data-ttu-id="d4321-145">您必須在每次使用 [拓撲建立器] 建立或修改拓撲時發佈拓撲，才能使用資料來安裝執行 Lync Server 的伺服器的檔案。</span><span class="sxs-lookup"><span data-stu-id="d4321-145">You must publish your topology each time you use Topology Builder to build or modify your topology so that the data can be used to install the files for servers that are running Lync Server.</span></span> <span data-ttu-id="d4321-146">然後，繼續進行後續步驟來修改中繼伺服器上的偵聽埠（如有需要）。</span><span class="sxs-lookup"><span data-stu-id="d4321-146">Then continue to the next steps to modify the listening ports on the Mediation Server, if necessary.</span></span>

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="d4321-147">定義中繼伺服器偵聽埠</span><span class="sxs-lookup"><span data-stu-id="d4321-147">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="d4321-148">請依照本主題中的步驟，使用拓撲建立器定義中繼伺服器或池將接受來自閘道對等傳入連線的偵聽埠。</span><span class="sxs-lookup"><span data-stu-id="d4321-148">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="d4321-149">修改中繼伺服器偵聽埠</span><span class="sxs-lookup"><span data-stu-id="d4321-149">To Modify the Mediation Server Listening Ports</span></span>

1.  <span data-ttu-id="d4321-150">啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="d4321-150">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="d4321-151">在 [拓撲建立器] 中，展開 [**轉送緩衝集區**] 節點，然後以滑鼠右鍵按一下先前建立的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="d4321-151">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>

3.  <span data-ttu-id="d4321-152">根據預設，在中繼伺服器上的 SIP 偵聽埠是來自 Lync Server 的 TLS 流量5070，從對等（閘道、PBXes 或 SBCs）進行 TLS 流量的5067。</span><span class="sxs-lookup"><span data-stu-id="d4321-152">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Lync Server, 5067 for TLS traffic from peers (gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="d4321-153">TCP 埠預設為停用。</span><span class="sxs-lookup"><span data-stu-id="d4321-153">TCP port is disabled by default.</span></span> <span data-ttu-id="d4321-154">如果您的閘道不支援 TLS，您就必須啟用 TCP 埠。</span><span class="sxs-lookup"><span data-stu-id="d4321-154">You must enable TCP port if you have gateways that do not support TLS.</span></span>

4.  <span data-ttu-id="d4321-155">指定所需的 TLS 或 TCP 偵聽埠範圍，中繼伺服器將接受 PSTN 閘道的傳入連線。</span><span class="sxs-lookup"><span data-stu-id="d4321-155">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d4321-156">如果沒有核取 [<STRONG>啟用 tcp 埠</STRONG>]，則不需要輸入 tcp 埠範圍。</span><span class="sxs-lookup"><span data-stu-id="d4321-156">Entering a TCP port range is not required if <STRONG>Enable TCP port</STRONG> is not checked.</span></span> <span data-ttu-id="d4321-157">此設定是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="d4321-157">This setting is optional.</span></span>

    
    </div>

<span data-ttu-id="d4321-158">接下來，在[Lync server 2013 的拓撲建立器中定義閘道](lync-server-2013-define-a-gateway-in-topology-builder.md)，然後按照在[Lync Server 2013 中安裝轉送伺服器](lync-server-2013-install-the-files-for-mediation-server.md)的檔案中的程式，在池中的每個中繼伺服器上安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="d4321-158">Next, [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) and install the files on each Mediation Server in the pool by following the procedures in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

