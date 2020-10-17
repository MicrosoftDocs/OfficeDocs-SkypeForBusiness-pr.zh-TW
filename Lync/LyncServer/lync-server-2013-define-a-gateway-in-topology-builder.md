---
title: Lync Server 2013：在拓撲產生器中定義閘道
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a gateway in Topology Builder
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48184036
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f23ef91f7f0a6f1205f5f95326b8ebe58b66df4b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516490"
---
# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="eae5b-102">在 Lync Server 2013 中的拓撲產生器中定義閘道</span><span class="sxs-lookup"><span data-stu-id="eae5b-102">Define a gateway in Topology Builder in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eae5b-103">_**主題上次修改日期：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="eae5b-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="eae5b-104">請遵循下列步驟，使用拓撲產生器來定義與轉送伺服器相關聯的 *對等對等* 能力，以便為已啟用 Enterprise Voice 的使用者提供公用交換電話網路 (PSTN) 連線。</span><span class="sxs-lookup"><span data-stu-id="eae5b-104">Follow these steps to use Topology Builder to define a *peer* with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="eae5b-105">對等與轉送伺服器的對等可以是 Internet 電話語音服務提供者 (SBC) 的 PSTN 閘道、IP-PBX 或會話邊界控制器， (透過設定 SIP 主幹來連接的 ITSP) 。</span><span class="sxs-lookup"><span data-stu-id="eae5b-105">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eae5b-106">本主題假設您已在至少一個中央網站使用組合或獨立轉送伺服器的情況下設定至少一個內部前端集區或 Standard Edition server，如在 <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013 中定義及設定前端集區或 Standard edition server</A> ，以及在部署檔中 <A href="lync-server-2013-publish-the-topology.md">發佈 lync server 2013 中的拓撲</A> 所述。</span><span class="sxs-lookup"><span data-stu-id="eae5b-106">This topic assumes that you have set up at least one internal Front End pool or Standard Edition server in at least one central site with a collocated or stand-alone Mediation Server, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="eae5b-107">本主題也假設您已驗證您的基礎結構符合在 lync server 2013 中的 <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Enterprise voice 的軟體必要條件</A> 和 <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">安全性和設定先決條件（適用于 lync server 2013 中的 enterprise</A>voice）中所述的必要條件。</span><span class="sxs-lookup"><span data-stu-id="eae5b-107">This topic also assumes that you have verified that your infrastructure meets the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="eae5b-108">定義中繼伺服器的對等</span><span class="sxs-lookup"><span data-stu-id="eae5b-108">To Define a Peer for the Mediation Server</span></span>

1.  <span data-ttu-id="eae5b-109">啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="eae5b-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="eae5b-110">在 [Lync Server 2013] 底下，您的網站名稱，共用元件，以滑鼠右鍵按一下 [ **PSTN 閘道** ] 節點，然後按一下 [ **新增 pstn 閘道**]。</span><span class="sxs-lookup"><span data-stu-id="eae5b-110">Under Lync Server 2013, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
    
    <span data-ttu-id="eae5b-111">![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span><span class="sxs-lookup"><span data-stu-id="eae5b-111">![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span></span>

3.  <span data-ttu-id="eae5b-112">在 **[定義新的 IP/PSTN 閘道]** 中，輸入對等的完整網域名稱 (FQDN) 或 IP 位址，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="eae5b-112">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    <span data-ttu-id="eae5b-113">![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span><span class="sxs-lookup"><span data-stu-id="eae5b-113">![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eae5b-114">如果您指定傳輸層安全性 (TLS) 做為傳輸類型，您必須指定 FQDN 而非轉送伺服器對等的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="eae5b-114">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="eae5b-115">定義您新的 PSTN 閘道的 IP 位址的聆聽模式 (IPv4 或 IPv6)，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="eae5b-115">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>
    
    <span data-ttu-id="eae5b-116">![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")</span><span class="sxs-lookup"><span data-stu-id="eae5b-116">![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")</span></span>

5.  <span data-ttu-id="eae5b-117">定義 PSTN 閘道的*根主幹*。</span><span class="sxs-lookup"><span data-stu-id="eae5b-117">Define a *root trunk* for the PSTN gateway.</span></span> <span data-ttu-id="eae5b-118">主幹是由元組唯一識別的轉送伺服器與閘道之間的邏輯連接。</span><span class="sxs-lookup"><span data-stu-id="eae5b-118">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="eae5b-119">{轉送伺服器 FQDN、轉送伺服器接聽埠 (TLS 或 TCP) ：閘道 IP 和 FQDN，閘道聆聽埠}</span><span class="sxs-lookup"><span data-stu-id="eae5b-119">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
      - <span data-ttu-id="eae5b-120">在拓撲產生器中定義 PSTN 閘道時，您必須定義一個根主幹，以順利將 PSTN 閘道新增至您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="eae5b-120">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
      - <span data-ttu-id="eae5b-121">必須先移除關聯的 PSTN 閘道，才能移除根主幹。</span><span class="sxs-lookup"><span data-stu-id="eae5b-121">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
    <span data-ttu-id="eae5b-122">![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")</span><span class="sxs-lookup"><span data-stu-id="eae5b-122">![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")</span></span>

6.  <span data-ttu-id="eae5b-123">在 [ **IP/PSTN 閘道的聆聽埠**] 底下，輸入閘道、PBX 或 SBC 將用於從轉送伺服器將其與 PSTN 閘道根主幹相關聯的 SIP 郵件所使用的收聽埠。</span><span class="sxs-lookup"><span data-stu-id="eae5b-123">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="eae5b-124"> (依預設，在 PSTN 閘道、PBX 或 SBC 上，傳輸控制通訊協定 (TCP) 和5067的傳輸層安全性 (TLS) 的埠是5066。</span><span class="sxs-lookup"><span data-stu-id="eae5b-124">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="eae5b-125">在分支網站上的 Survivable 分支裝置中，TCP 和5082的預設埠為5081，以供 TLS 使用。 ) </span><span class="sxs-lookup"><span data-stu-id="eae5b-125">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>

7.  <span data-ttu-id="eae5b-126">在 **[SIP 傳輸通訊協定]** 下，按一下對等使用的傳輸類型，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="eae5b-126">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eae5b-127">基於安全性考慮，強烈建議您將對等部署至可使用 TLS 的轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="eae5b-127">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

8.  <span data-ttu-id="eae5b-128">在 [關聯的轉送伺服器] 底下，選取要與此 PSTN 閘道 **之**根主幹產生關聯的轉送伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="eae5b-128">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>

9.  <span data-ttu-id="eae5b-129">在 [關聯的中繼 **伺服器埠**] 底下，輸入轉送伺服器將用於來自閘道的 SIP 訊息的聆聽埠。</span><span class="sxs-lookup"><span data-stu-id="eae5b-129">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eae5b-130">在 Lync Server 2013 中有多個主幹支援，可在轉送伺服器上定義多個 SIP 信號埠，以用於與多個 PSTN 閘道進行通訊。</span><span class="sxs-lookup"><span data-stu-id="eae5b-130">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server to be used for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="eae5b-131">在定義主幹時，關聯的中繼 <STRONG>伺服器埠</STRONG> 必須位於轉送伺服器所允許之個別通訊埠的偵聽埠範圍內。</span><span class="sxs-lookup"><span data-stu-id="eae5b-131">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="eae5b-132">此埠範圍是在 [Lync Server 2013] 和 [中繼集區] 下定義。</span><span class="sxs-lookup"><span data-stu-id="eae5b-132">This port range is defined under Lync Server 2013 and Mediation Pools.</span></span> <span data-ttu-id="eae5b-133">在感興趣的轉送伺服器集區上按一下滑鼠右鍵，然後選取 [ <STRONG>編輯屬性</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="eae5b-133">Right-click the Mediation Server pool of interest, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="eae5b-134">在 <STRONG>[聆聽連接埠]</STRONG> 欄位中指定連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="eae5b-134">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

10. <span data-ttu-id="eae5b-135">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="eae5b-135">Click **Finish**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="eae5b-136">繼續下一個步驟之前，請確定您定義的對等正在執行中，且使用您指定的 FQDN 或 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="eae5b-136">Before you finish this step, be sure that the peer that you defined is running and using the FQDN or IP address that you specified.</span></span>



</div>

<span data-ttu-id="eae5b-137">接下來，若要將對等新增至拓撲，請遵循部署檔中的在 [Lync Server 2013 中發佈拓撲](lync-server-2013-publish-the-topology.md) 中的程式。</span><span class="sxs-lookup"><span data-stu-id="eae5b-137">Next, to add the peer to the topology, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span> <span data-ttu-id="eae5b-138">您必須在每次使用拓撲產生器來建立或修改拓撲時發佈拓撲，如此才能使用資料來安裝執行 Lync Server 之伺服器的檔案。</span><span class="sxs-lookup"><span data-stu-id="eae5b-138">You must publish your topology each time that you use Topology Builder to build or modify your topology, so that the data can be used to install the files for servers that are running Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eae5b-139">另請參閱</span><span class="sxs-lookup"><span data-stu-id="eae5b-139">See Also</span></span>


[<span data-ttu-id="eae5b-140">在 Lync Server 2013 中的拓撲產生器中修改主幹</span><span class="sxs-lookup"><span data-stu-id="eae5b-140">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

