---
title: Lync Server 2013：在拓撲建立器中定義其他 trunks
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define additional trunks in Topology Builder
ms:assetid: e68b8377-50a2-452a-bf5c-910929e34236
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721915(v=OCS.15)
ms:contentKeyID: 49733849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c55e8073bd1ad1bb2db69096e4e58aa2b148e775
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="22f88-102">在 Lync Server 2013 的拓撲產生器中定義其他 trunks</span><span class="sxs-lookup"><span data-stu-id="22f88-102">Define additional trunks in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22f88-103">_**主題上次修改日期：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="22f88-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="22f88-104">請依照下列步驟使用拓撲建立器來定義您可以將*對等*與轉送伺服器建立關聯的其他主幹。</span><span class="sxs-lookup"><span data-stu-id="22f88-104">Follow these steps to use Topology Builder to define an additional trunk to which you can associate a *peer* with a Mediation Server.</span></span> <span data-ttu-id="22f88-105">對等可為使用者提供可連線至公用交換電話網絡（PSTN）的企業語音功能。</span><span class="sxs-lookup"><span data-stu-id="22f88-105">A peer provides users enabled for Enterprise Voice with connectivity to the public switched telephone network (PSTN).</span></span> <span data-ttu-id="22f88-106">對等可以是 PSTN 閘道、IP PBX，或網際網路電話服務提供者（ITSP）的會話邊界控制器（SBC）。</span><span class="sxs-lookup"><span data-stu-id="22f88-106">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span> <span data-ttu-id="22f88-107">幹線會在中繼伺服器與對等之間定義此連接。</span><span class="sxs-lookup"><span data-stu-id="22f88-107">The trunk defines this connection between the Mediation Server and peer.</span></span> <span data-ttu-id="22f88-108">您可以針對每個中繼伺服器定義多個 trunks。</span><span class="sxs-lookup"><span data-stu-id="22f88-108">Multiple trunks can be defined per Mediation Server.</span></span> <span data-ttu-id="22f88-109">中繼伺服器可以與多個對等建立關聯。</span><span class="sxs-lookup"><span data-stu-id="22f88-109">A Mediation Server can be associated with multiple peers.</span></span>

<span data-ttu-id="22f88-110">幹線是由元組唯一識別的中繼伺服器與閘道之間的邏輯連線：</span><span class="sxs-lookup"><span data-stu-id="22f88-110">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple:</span></span>

<span data-ttu-id="22f88-111">{轉送伺服器 FQDN，中繼伺服器偵聽埠（TLS 或 TCP）：閘道 IP 和 FQDN，閘道偵聽埠}</span><span class="sxs-lookup"><span data-stu-id="22f88-111">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="22f88-112">本主題假設您已使用至少一個 collocated 或獨立的中繼伺服器或池來設定 PSTN 閘道和根幹線，如在部署檔中的<A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Lync Server 2013 定義閘道</A>中所述。</span><span class="sxs-lookup"><span data-stu-id="22f88-112">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="22f88-113">本主題假設您已在至少一個中心網站中設定了至少一個前端池或標準版伺服器，如在<A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013 中定義及設定前端池或標準版伺服器</A>中所述，並在部署檔中<A href="lync-server-2013-publish-the-topology.md">發佈 lync server 2013 中的拓撲</A>。</span><span class="sxs-lookup"><span data-stu-id="22f88-113">This topic assumes that you have set up at least one Front End pool or Standard Edition server in at least one central site, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="22f88-114">在中繼伺服器與閘道對等之間定義額外主幹</span><span class="sxs-lookup"><span data-stu-id="22f88-114">To Define an additional Trunk between a Mediation Server and a Gateway Peer</span></span>

1.  <span data-ttu-id="22f88-115">啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="22f88-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="22f88-116">在 Lync Server 2013、您的網站名稱、**共用元件**中，以滑鼠右鍵按一下 [ **Trunks** ] 節點，然後按一下 [**新主幹**]。</span><span class="sxs-lookup"><span data-stu-id="22f88-116">Under Lync Server 2013, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
    
    <span data-ttu-id="22f88-117">![Lync Server 拓撲產生器檔案結構畫面](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server 拓撲產生器檔案結構畫面")</span><span class="sxs-lookup"><span data-stu-id="22f88-117">![Lync Server Topology Builder file structure screen](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server Topology Builder file structure screen")</span></span>

3.  <span data-ttu-id="22f88-118">在 [**定義新主幹**] 中，指定要唯一識別主幹的易記名稱。</span><span class="sxs-lookup"><span data-stu-id="22f88-118">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="22f88-119">您不能有兩個名稱相同的 trunks。</span><span class="sxs-lookup"><span data-stu-id="22f88-119">You cannot have two trunks with the same name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22f88-120">如果您將傳輸層安全性（TLS）指定為傳輸類型，您必須指定 FQDN，而不是對轉送伺服器對等的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="22f88-120">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="22f88-121">在 [**關聯的 PSTN 閘道**] 底下，選取 PSTN 閘道對，以與此幹線建立關聯。</span><span class="sxs-lookup"><span data-stu-id="22f88-121">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    
    <span data-ttu-id="22f88-122">![主幹之 PSTN 閘道對等的內容設定](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "主幹之 PSTN 閘道對等的內容設定")</span><span class="sxs-lookup"><span data-stu-id="22f88-122">![Property settings for PSTN gateway peer for trunk](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Property settings for PSTN gateway peer for trunk")</span></span>

5.  <span data-ttu-id="22f88-123">在 [ **PSTN 閘道的偵聽埠**] 底下，輸入對等（PSTN 閘道、IP PBX 或 SBC）的偵聽埠，將會從要與此幹線關聯的中繼伺服器接收 SIP 訊息。</span><span class="sxs-lookup"><span data-stu-id="22f88-123">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="22f88-124">預設對等埠是針對傳輸控制通訊協定（TCP）和5067（針對傳輸層安全性（TLS））的5066。</span><span class="sxs-lookup"><span data-stu-id="22f88-124">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="22f88-125">預設的 Survivable 分支裝置埠是適用于 TCP 的5081，以及適用于 TLS 的5082。</span><span class="sxs-lookup"><span data-stu-id="22f88-125">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>

6.  <span data-ttu-id="22f88-126">在 [ **SIP 傳輸通訊協定**] 底下，按一下對等所使用的傳輸類型。</span><span class="sxs-lookup"><span data-stu-id="22f88-126">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22f88-127">出於安全性考慮，我們強烈建議您將對等部署到可使用 TLS 的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="22f88-127">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

7.  <span data-ttu-id="22f88-128">在 [**關聯的中繼伺服器**] 底下，選取 [轉送伺服器] 池以與此對等方的根幹線建立關聯</span><span class="sxs-lookup"><span data-stu-id="22f88-128">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>

8.  <span data-ttu-id="22f88-129">在 [**關聯的中繼伺服器埠**] 底下，輸入中繼伺服器將從對等接收 SIP 訊息的偵聽埠。</span><span class="sxs-lookup"><span data-stu-id="22f88-129">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22f88-130">在 Lync Server 2013 有多個幹線支援的情況下，您無法使用相同的<STRONG>關聯中繼伺服器埠</STRONG>和<STRONG>偵聽埠（IP/PSTN 閘道</STRONG>）來設定具有不同主幹名稱的兩個 trunks</span><span class="sxs-lookup"><span data-stu-id="22f88-130">With multiple trunk support in Lync Server 2013, two trunks with different trunk names cannot be configured with the same <STRONG>Associated Mediation Server port</STRONG> and <STRONG>Listening Port for IP/PSTN gateway</STRONG></span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22f88-131">在 Lync Server 2013 有多個幹線支援的情況下，可以在中繼伺服器上定義多個 SIP 信號埠，以便與多個對等進行通訊。</span><span class="sxs-lookup"><span data-stu-id="22f88-131">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="22f88-132">在定義主幹時，<STRONG>關聯的中繼伺服器埠</STRONG>編號必須在中繼伺服器所允許之個別通訊協定的偵聽埠範圍內。</span><span class="sxs-lookup"><span data-stu-id="22f88-132">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="22f88-133">此埠範圍是在 Lync Server 2013 和中繼伺服器池底下定義。</span><span class="sxs-lookup"><span data-stu-id="22f88-133">This port range is defined under Lync Server 2013 and Mediation Server pools.</span></span> <span data-ttu-id="22f88-134">以滑鼠右鍵按一下相關的中繼伺服器池，然後選取 [<STRONG>編輯屬性</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="22f88-134">Right-click the relevant Mediation Server pool, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="22f88-135">在 [<STRONG>偵聽埠</STRONG>] 欄位中指定埠範圍。</span><span class="sxs-lookup"><span data-stu-id="22f88-135">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

9.  <span data-ttu-id="22f88-136">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22f88-136">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="22f88-137">請參閱</span><span class="sxs-lookup"><span data-stu-id="22f88-137">See Also</span></span>


[<span data-ttu-id="22f88-138">在 Lync Server 2013 的拓撲產生器中修改主幹</span><span class="sxs-lookup"><span data-stu-id="22f88-138">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

