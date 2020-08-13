---
title: Lync Server 2013：在拓撲產生器中定義轉送伺服器
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
ms.openlocfilehash: 782491b0df1c8d2432a9b4c69240293ccc126e7c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="7f551-102">在 Lync Server 2013 的拓撲產生器中定義轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="7f551-102">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f551-103">_**主題上次修改日期：** 2013-03-25_</span><span class="sxs-lookup"><span data-stu-id="7f551-103">_**Topic Last Modified:** 2013-03-25_</span></span>

<span data-ttu-id="7f551-104">遵循此主題中的步驟，使用拓撲產生器來定義獨立的轉送伺服器或集區組合，並在先前未部署 Enterprise Voice 之網站上使用前端集區。</span><span class="sxs-lookup"><span data-stu-id="7f551-104">Follow the steps in this topic to use Topology Builder to define a stand-alone Mediation Server or a pool collocated with a Front End pool at a site for which you did not previously deploy Enterprise Voice.</span></span>

<span data-ttu-id="7f551-105">您可以使用屬於 Administrators 群組成員的帳戶來定義拓撲。</span><span class="sxs-lookup"><span data-stu-id="7f551-105">You can define a topology using an account that is a member of the Administrators group.</span></span>

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a><span data-ttu-id="7f551-106">定義轉送伺服器組合至前端集區</span><span class="sxs-lookup"><span data-stu-id="7f551-106">Define Mediation Server collocated to a Front End pool</span></span>

<span data-ttu-id="7f551-107">請遵循本主題中的步驟，使用拓撲產生器，將轉送伺服器組合定義至先前未部署 Enterprise Voice 之網站的前端集區。</span><span class="sxs-lookup"><span data-stu-id="7f551-107">Follow the steps in this topic to use Topology Builder to define a Mediation Server collocated to a Front End pool in a site where Enterprise Voice has not been previously deployed.</span></span>

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="7f551-108">若要將轉送伺服器新增至前端集區</span><span class="sxs-lookup"><span data-stu-id="7f551-108">To Add a Mediation Server to a Front End pool</span></span>

1.  <span data-ttu-id="7f551-109">啟動拓撲產生器：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="7f551-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="7f551-110">在 [拓撲產生器] 的主控台樹中，展開您要定義前端集區的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="7f551-110">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>

3.  <span data-ttu-id="7f551-111">在主控台樹中，以滑鼠右鍵按一下您想要的前端集區類型，然後按一下 [**新增前端集**區]。</span><span class="sxs-lookup"><span data-stu-id="7f551-111">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>

4.  <span data-ttu-id="7f551-112">完整瀏覽 [定義新前端集區]\*\*\*\* 精靈，直到到達 [選取組合的伺服器角色]\*\*\*\* 頁面為止。</span><span class="sxs-lookup"><span data-stu-id="7f551-112">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>

5.  <span data-ttu-id="7f551-113">在 [**選取組合伺服器角色**] 中，選取 [**組合轉送伺服器**] 選項。</span><span class="sxs-lookup"><span data-stu-id="7f551-113">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="7f551-114">如果您選取的前端集區類型是 Enterprise Edition，則轉送伺服器元件將會安裝在該前端集區的所有前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="7f551-114">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="7f551-115">轉送伺服器所使用的<STRONG>下一個躍點集</STRONG>區將是轉送伺服器組合所在的前端集區。</span><span class="sxs-lookup"><span data-stu-id="7f551-115">The <STRONG>Next hop pool</STRONG> used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="7f551-116">轉送伺服器所使用的<STRONG>edge 集</STRONG>區將是與組合轉送伺服器的前端集區相關聯的相同 edge 集區。</span><span class="sxs-lookup"><span data-stu-id="7f551-116">The <STRONG>Edge pool</STRONG> used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="7f551-117">按一下 [**成為預設值**]，使用此前端集區，將來自 Microsoft Office 通訊伺服器 2007 R2 的呼叫路由傳送至 PSTN。</span><span class="sxs-lookup"><span data-stu-id="7f551-117">Click **Make Default** to use this Front End pool to route calls from Microsoft Office Communications Server 2007 R2 to the PSTN.</span></span>

7.  <span data-ttu-id="7f551-118">完成將一或多個對等專案關聯至前端集區時，按一下 **[完成]** 。</span><span class="sxs-lookup"><span data-stu-id="7f551-118">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7f551-119">在繼續進行企業語音部署程式的下一個步驟之前，請確定轉送伺服器集區 (（即「轉送伺服器元件」組合) 的前端集區）是使用您指定的 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="7f551-119">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span>

    
    </div>

8.  <span data-ttu-id="7f551-120">接下來，遵循 [部署指南檔] 中的 [在[Lync server 2013 中發佈拓撲](lync-server-2013-publish-the-topology.md)] 中的程式，將轉送伺服器新增至您的拓撲，然後再繼續進行下一個修改轉送伺服器的聆聽埠（如有需要）的步驟。</span><span class="sxs-lookup"><span data-stu-id="7f551-120">Next, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment Guide documentation to add the Mediation Server to your topology before proceeding to the next step of modifying the listening ports of the Mediation Server if needed.</span></span> <span data-ttu-id="7f551-121">您必須在每次使用拓撲產生器來定義或修改拓撲時，發行您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="7f551-121">You must publish your topology each time you use Topology Builder to define or modify your topology.</span></span>

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a><span data-ttu-id="7f551-122">定義獨立轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="7f551-122">Define stand-alone Mediation Server</span></span>

<span data-ttu-id="7f551-123">遵循此主題中的步驟，使用拓撲產生器來定義獨立的轉送伺服器或集區，該網站的 Enterprise Voice 先前尚未部署。</span><span class="sxs-lookup"><span data-stu-id="7f551-123">Follow the steps in this topic to use Topology Builder to define a stand-alone Mediation Server or pool at a site where Enterprise Voice has not been previously deployed.</span></span>

<span data-ttu-id="7f551-124">如果您已在此網站上部署組合至前端集區的轉送伺服器，則可以略過本節並[在 Lync server 2013 中安裝轉送伺服器的](lync-server-2013-install-the-files-for-mediation-server.md)檔案，然後再繼續設定[lync server 2013 中的主幹](lync-server-2013-configuring-trunks.md)。</span><span class="sxs-lookup"><span data-stu-id="7f551-124">If you already deployed Mediation Servers collocated to Front End pools at this site, you can skip this section and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) before proceeding to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7f551-125">本節假設您已安裝至少一個前端集區（如<A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">定義及設定 Lync server 2013 中的前端集區或 Standard Edition server</A>所述），並在部署指南檔中<A href="lync-server-2013-publish-the-topology.md">發佈 lync server 2013 中的拓撲</A>。</span><span class="sxs-lookup"><span data-stu-id="7f551-125">This section assumes that you have already setup at least one Front End pool, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment Guide documentation.</span></span>



</div>

<div>

## <a name="to-add-a-mediation-server"></a><span data-ttu-id="7f551-126">新增中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="7f551-126">To Add a Mediation Server</span></span>

1.  <span data-ttu-id="7f551-127">啟動拓撲產生器：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="7f551-127">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="7f551-128">在 [拓撲產生器] 的主控台樹中，展開您要定義轉送伺服器的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="7f551-128">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>

3.  <span data-ttu-id="7f551-129">在主控台樹中，以滑鼠右鍵按一下 **[中繼**集區] 節點，然後按一下 [**轉送伺服器集**區]。</span><span class="sxs-lookup"><span data-stu-id="7f551-129">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>

4.  <span data-ttu-id="7f551-130">在 [**定義新**的中繼集區] 中，輸入轉送伺服器集區的完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="7f551-130">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>

5.  <span data-ttu-id="7f551-131">接著執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="7f551-131">Next, do one of the following:</span></span>
    
      - <span data-ttu-id="7f551-132">如果您想要在集區中部署多個轉送伺服器以提供高可用性，請選取 [**多部電腦集**區]。</span><span class="sxs-lookup"><span data-stu-id="7f551-132">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7f551-133">您必須部署 DNS 負載平衡，以支援具有多部轉送伺服器的轉送伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="7f551-133">You must deploy DNS load balancing to support Mediation Server pools that have multiple Mediation Servers.</span></span> <span data-ttu-id="7f551-134">如需詳細資訊，請參閱規劃檔中的在<A href="lync-server-2013-dns-load-balancing.md">Lync server 2013</A>中使用 dns 負載平衡的轉送伺服器集區一節。</span><span class="sxs-lookup"><span data-stu-id="7f551-134">For details, see the Using DNS Load Balancing on Mediation Server Pools section of <A href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</A> in the Planning documentation.</span></span>

        
        </div>
    
      - <span data-ttu-id="7f551-135">如果您只想要在集區中部署一個轉送伺服器，因為您不需要高可用性，請選取 [**單一電腦集**區]。</span><span class="sxs-lookup"><span data-stu-id="7f551-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="7f551-136">略過下列步驟。</span><span class="sxs-lookup"><span data-stu-id="7f551-136">Skip the following step.</span></span>

6.  <span data-ttu-id="7f551-137">如果您在上一個步驟中，在 [定義此集區中的電腦]\*\*\*\* 項目上選取了 [多部電腦集區]\*\*\*\*，則可按一下 [電腦 FQDN]\*\*\*\*、鍵入集區中每一部伺服器的 FQDN，然後按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7f551-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="7f551-138">針對您要新增至集區的所有其他轉送伺服器重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="7f551-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="7f551-139">在定義集區中的所有電腦之後，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7f551-139">When you have defined all the computers in the pool, click **Next**.</span></span>

7.  <span data-ttu-id="7f551-140">在 [**選取下一個躍點]** 頁面上，按一下 **[下一個躍點集區]**，然後按一下將使用此轉送伺服器集區的前端集區 FQDN，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7f551-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>

8.  <span data-ttu-id="7f551-141">在 **[選取 Edge Server]** 頁面上，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="7f551-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
      - <span data-ttu-id="7f551-142">如果您想要為已啟用 Enterprise Voice 的外部使用者提供 PSTN 連線，請在 [**選取此轉送伺服器使用的 Edge 集**區] 下，按一下將使用此轉送伺服器集區的 edge Server 集區 FQDN，以提供 PSTN 連線到這些外部使用者，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7f551-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
      - <span data-ttu-id="7f551-143">如果您不打算為外部使用者啟用 Enterprise Voice，或是不想要在內部網路以外為使用者提供 PSTN 連線能力，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7f551-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>

9.  <span data-ttu-id="7f551-144">接下來，遵循在 [部署檔] 中的 [在[Lync Server 2013 中發佈拓撲](lync-server-2013-publish-the-topology.md)] 中的程式，將轉送伺服器新增至拓撲。</span><span class="sxs-lookup"><span data-stu-id="7f551-144">Next, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation to add the Mediation Server to the topology.</span></span> <span data-ttu-id="7f551-145">您必須在每次使用拓撲產生器建立或修改拓撲時發佈拓撲，以便使用資料來安裝執行 Lync Server 之伺服器的檔案。</span><span class="sxs-lookup"><span data-stu-id="7f551-145">You must publish your topology each time you use Topology Builder to build or modify your topology so that the data can be used to install the files for servers that are running Lync Server.</span></span> <span data-ttu-id="7f551-146">接著，視需要進行後續步驟，修改中繼伺服器上的聆聽連接埠。</span><span class="sxs-lookup"><span data-stu-id="7f551-146">Then continue to the next steps to modify the listening ports on the Mediation Server, if necessary.</span></span>

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="7f551-147">定義轉送伺服器聆聽埠</span><span class="sxs-lookup"><span data-stu-id="7f551-147">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="7f551-148">遵循此主題中的步驟，使用拓撲產生器定義轉送伺服器或集區將接受來自閘道對等的傳入連線的聆聽埠。</span><span class="sxs-lookup"><span data-stu-id="7f551-148">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="7f551-149">修改轉送伺服器的聆聽埠</span><span class="sxs-lookup"><span data-stu-id="7f551-149">To Modify the Mediation Server Listening Ports</span></span>

1.  <span data-ttu-id="7f551-150">啟動拓撲產生器：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="7f551-150">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="7f551-151">在 [拓撲產生器] 的主控台樹中，展開 [中繼集區 **] 節點，** 然後以滑鼠右鍵按一下先前建立的轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="7f551-151">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>

3.  <span data-ttu-id="7f551-152">根據預設，轉送伺服器上的 SIP 聆聽埠為5070來自 Lync Server 的 TLS 流量，5067用於來自對等 (閘道、PBXes 或 SBCs) 的 TLS 流量。</span><span class="sxs-lookup"><span data-stu-id="7f551-152">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Lync Server, 5067 for TLS traffic from peers (gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="7f551-153">TCP 連接埠預設是停用的。</span><span class="sxs-lookup"><span data-stu-id="7f551-153">TCP port is disabled by default.</span></span> <span data-ttu-id="7f551-154">如果您的閘道不支援 TLS，則必須啟用 TCP 連接埠。</span><span class="sxs-lookup"><span data-stu-id="7f551-154">You must enable TCP port if you have gateways that do not support TLS.</span></span>

4.  <span data-ttu-id="7f551-155">指定所需的 TLS 或 TCP 接聽埠範圍，轉送伺服器將接受來自 PSTN 閘道的傳入連線。</span><span class="sxs-lookup"><span data-stu-id="7f551-155">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7f551-156">若未勾選 [啟用 TCP 連接埠]<STRONG></STRONG>，則不一定要輸入 TCP 連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="7f551-156">Entering a TCP port range is not required if <STRONG>Enable TCP port</STRONG> is not checked.</span></span> <span data-ttu-id="7f551-157">此為選用設定。</span><span class="sxs-lookup"><span data-stu-id="7f551-157">This setting is optional.</span></span>

    
    </div>

<span data-ttu-id="7f551-158">接下來，在 Lync server 2013 中的拓撲產生器中[定義閘道](lync-server-2013-define-a-gateway-in-topology-builder.md)，並遵循在[lync Server 2013 中安裝轉送伺服器](lync-server-2013-install-the-files-for-mediation-server.md)的檔案中的程式，在集區中的每個轉送伺服器上安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="7f551-158">Next, [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) and install the files on each Mediation Server in the pool by following the procedures in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

