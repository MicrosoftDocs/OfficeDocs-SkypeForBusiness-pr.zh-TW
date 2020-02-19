---
title: Lync Server 2013： 在拓撲產生器中定義閘道
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
ms.openlocfilehash: 40881b38c83ebf254a60773060b642d183b7dfaa
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="c975a-102">在 Lync Server 2013 中的拓撲產生器中定義閘道</span><span class="sxs-lookup"><span data-stu-id="c975a-102">Define a gateway in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c975a-103">_**主題上次修改日期：** 2012年-10-04_</span><span class="sxs-lookup"><span data-stu-id="c975a-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="c975a-104">請遵循下列步驟，使用拓撲產生器來定義與建立關聯的中繼伺服器已啟用企業語音之使用者提供連線至公用交換的電話網路 (PSTN)*對等*。</span><span class="sxs-lookup"><span data-stu-id="c975a-104">Follow these steps to use Topology Builder to define a *peer* with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="c975a-105">對等網路，到中繼伺服器可以是 PSTN 閘道、 IP PBX 或工作階段界限控制器 (SBC) 的網際網路電話語音服務提供者 (ITSP) 您藉由設定 SIP 主幹連接。</span><span class="sxs-lookup"><span data-stu-id="c975a-105">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c975a-106">本主題假設您已設定至少一個內部的前端集區或 Standard Edition server 中使用組合式還是獨立式中繼伺服器，具有至少一個中央網站中所述<A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">定義和設定 Lync Server 2013 中的前端集區或 Standard Edition server</A>和<A href="lync-server-2013-publish-the-topology.md">發佈 Lync Server 2013 中的拓撲</A>中部署文件。</span><span class="sxs-lookup"><span data-stu-id="c975a-106">This topic assumes that you have set up at least one internal Front End pool or Standard Edition server in at least one central site with a collocated or stand-alone Mediation Server, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="c975a-107">本主題也假設您已經驗證您的基礎結構符合<A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Lync Server 2013 中的 Enterprise Voice 的軟體先決條件</A>和<A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Lync Server 2013 中的 Enterprise voice 的安全性和組態必要條件</A>中所述的先決條件。</span><span class="sxs-lookup"><span data-stu-id="c975a-107">This topic also assumes that you have verified that your infrastructure meets the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="c975a-108">定義中繼伺服器的對等</span><span class="sxs-lookup"><span data-stu-id="c975a-108">To Define a Peer for the Mediation Server</span></span>

1.  <span data-ttu-id="c975a-109">啟動拓撲產生器： 按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 拓撲產生器]**。</span><span class="sxs-lookup"><span data-stu-id="c975a-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="c975a-110">在 [Lync Server 2013 中，您的網站名稱，共用元件]，以滑鼠右鍵按一下 [ **PSTN 閘道**] 節點，然後再按一下 [**新的 PSTN 閘道**。</span><span class="sxs-lookup"><span data-stu-id="c975a-110">Under Lync Server 2013, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
    
    <span data-ttu-id="c975a-111">![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span><span class="sxs-lookup"><span data-stu-id="c975a-111">![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span></span>

3.  <span data-ttu-id="c975a-112">在 **[定義新的 IP/PSTN 閘道]** 中，輸入對等的完整網域名稱 (FQDN) 或 IP 位址，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c975a-112">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    <span data-ttu-id="c975a-113">![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span><span class="sxs-lookup"><span data-stu-id="c975a-113">![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c975a-114">如果您指定傳輸層安全性 (TLS) 作為傳輸類型，您必須指定的 FQDN，而不是對等的中繼伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c975a-114">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="c975a-115">定義您新的 PSTN 閘道的 IP 位址的聆聽模式 (IPv4 或 IPv6)，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c975a-115">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>
    
    <span data-ttu-id="c975a-116">![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")</span><span class="sxs-lookup"><span data-stu-id="c975a-116">![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")</span></span>

5.  <span data-ttu-id="c975a-117">定義 PSTN 閘道的*根主幹*。</span><span class="sxs-lookup"><span data-stu-id="c975a-117">Define a *root trunk* for the PSTN gateway.</span></span> <span data-ttu-id="c975a-118">主幹是中繼伺服器與專門由 tuple 識別閘道之間的邏輯連線。</span><span class="sxs-lookup"><span data-stu-id="c975a-118">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="c975a-119">{中繼伺服器 FQDN] 中，中繼伺服器接聽連接埠 （TLS 或 TCP）： 閘道 IP 與 FQDN、 閘道聆聽連接埠}</span><span class="sxs-lookup"><span data-stu-id="c975a-119">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
      - <span data-ttu-id="c975a-120">在拓撲產生器中定義 PSTN 閘道，您必須定義根主幹，才能成功新增至您的拓撲的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="c975a-120">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
      - <span data-ttu-id="c975a-121">必須先移除關聯的 PSTN 閘道，才能移除根主幹。</span><span class="sxs-lookup"><span data-stu-id="c975a-121">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
    <span data-ttu-id="c975a-122">![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")</span><span class="sxs-lookup"><span data-stu-id="c975a-122">![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")</span></span>

6.  <span data-ttu-id="c975a-123">在 [ **IP/PSTN 閘道的聆聽連接埠**，輸入閘道、 PBX 或 SBC 將用來從要與 PSTN 閘道的根主幹建立關聯的中繼伺服器的 SIP 訊息的聆聽連接埠。</span><span class="sxs-lookup"><span data-stu-id="c975a-123">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="c975a-124">（預設的連接埠是 5066 傳輸控制通訊協定 (TCP) 及 5067 PSTN 閘道、 PBX 或 SBC 上的傳輸層安全性 (TLS)。</span><span class="sxs-lookup"><span data-stu-id="c975a-124">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="c975a-125">Survivable Branch Appliance 分支網站，在預設連接埠是 5081 tcp 及 tls 5082）。</span><span class="sxs-lookup"><span data-stu-id="c975a-125">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>

7.  <span data-ttu-id="c975a-126">在 **[SIP 傳輸通訊協定]** 下，按一下對等使用的傳輸類型，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c975a-126">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c975a-127">基於安全性考量，我們強烈建議您將對等部署至中繼伺服器可以使用 TLS。</span><span class="sxs-lookup"><span data-stu-id="c975a-127">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

8.  <span data-ttu-id="c975a-128">在 [**相關中繼伺服器**，選取要與這個 PSTN 閘道的根主幹建立關聯的中繼伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="c975a-128">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>

9.  <span data-ttu-id="c975a-129">在 [**相關中繼伺服器連接埠**，輸入中繼伺服器用於來自閘道的 SIP 訊息的聆聽連接埠。</span><span class="sxs-lookup"><span data-stu-id="c975a-129">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c975a-130">支援多個主幹 Lync Server 2013 中，可以定義多個 SIP 信號連接埠中繼伺服器用於與多個 PSTN 閘道的通訊。</span><span class="sxs-lookup"><span data-stu-id="c975a-130">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server to be used for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="c975a-131">定義主幹時,<STRONG>相關聯的中繼伺服器連接埠</STRONG>必須範圍內的個別中繼伺服器所允許的通訊協定的聆聽連接埠。</span><span class="sxs-lookup"><span data-stu-id="c975a-131">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="c975a-132">Lync Server 2013 與中繼集區] 底下定義這個連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="c975a-132">This port range is defined under Lync Server 2013 and Mediation Pools.</span></span> <span data-ttu-id="c975a-133">感興趣，中繼伺服器集區上按一下滑鼠右鍵，然後選取 [<STRONG>編輯內容]</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="c975a-133">Right-click the Mediation Server pool of interest, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="c975a-134">在 <STRONG>[聆聽連接埠]</STRONG> 欄位中指定連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="c975a-134">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

10. <span data-ttu-id="c975a-135">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="c975a-135">Click **Finish**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c975a-136">繼續下一個步驟之前，請確定您定義的對等正在執行中，且使用您指定的 FQDN 或 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c975a-136">Before you finish this step, be sure that the peer that you defined is running and using the FQDN or IP address that you specified.</span></span>



</div>

<span data-ttu-id="c975a-137">接下來，若要新增至拓撲的對等網路，請遵循[發佈 Lync Server 2013 中的拓撲](lync-server-2013-publish-the-topology.md)中部署文件中的程序。</span><span class="sxs-lookup"><span data-stu-id="c975a-137">Next, to add the peer to the topology, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span> <span data-ttu-id="c975a-138">您必須發佈您的拓樸每次您建立或修改您的拓撲，使用拓撲產生器，使資料可以用來安裝在執行 Lync Server 伺服器的檔案。</span><span class="sxs-lookup"><span data-stu-id="c975a-138">You must publish your topology each time that you use Topology Builder to build or modify your topology, so that the data can be used to install the files for servers that are running Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c975a-139">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c975a-139">See Also</span></span>


[<span data-ttu-id="c975a-140">修改主幹在 Lync Server 2013 中的拓撲產生器</span><span class="sxs-lookup"><span data-stu-id="c975a-140">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

