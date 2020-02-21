---
title: Lync Server 2013： 在拓撲產生器中定義其他主幹
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
ms.openlocfilehash: d5632a5f28a5a56d077235e28be41c19b5496c10
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="ce2b4-102">在 Lync Server 2013 中的拓撲產生器中定義其他主幹</span><span class="sxs-lookup"><span data-stu-id="ce2b4-102">Define additional trunks in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce2b4-103">_**主題上次修改日期：** 2012年-10-04_</span><span class="sxs-lookup"><span data-stu-id="ce2b4-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="ce2b4-104">請遵循下列步驟，使用拓撲產生器來定義要您可以將關聯的*對等*中繼伺服器的其他主幹。</span><span class="sxs-lookup"><span data-stu-id="ce2b4-104">Follow these steps to use Topology Builder to define an additional trunk to which you can associate a *peer* with a Mediation Server.</span></span> <span data-ttu-id="ce2b4-105">對等網路提供連線至公用交換的電話網路 (PSTN) 啟用 Enterprise Voice 的使用者。</span><span class="sxs-lookup"><span data-stu-id="ce2b4-105">A peer provides users enabled for Enterprise Voice with connectivity to the public switched telephone network (PSTN).</span></span> <span data-ttu-id="ce2b4-106">PSTN 閘道、 IP PBX 或工作階段界限控制器 (SBC) 的網際網路電話語音服務提供者 (ITSP)，可以是對等。</span><span class="sxs-lookup"><span data-stu-id="ce2b4-106">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span> <span data-ttu-id="ce2b4-107">主幹定義此中繼伺服器和對等之間的連線。</span><span class="sxs-lookup"><span data-stu-id="ce2b4-107">The trunk defines this connection between the Mediation Server and peer.</span></span> <span data-ttu-id="ce2b4-108">每個中繼伺服器，您可以定義多個主幹。</span><span class="sxs-lookup"><span data-stu-id="ce2b4-108">Multiple trunks can be defined per Mediation Server.</span></span> <span data-ttu-id="ce2b4-109">中繼伺服器可與多個對等相關聯。</span><span class="sxs-lookup"><span data-stu-id="ce2b4-109">A Mediation Server can be associated with multiple peers.</span></span>

<span data-ttu-id="ce2b4-110">主幹是中繼伺服器與專門由 tuple 識別閘道之間的邏輯連接：</span><span class="sxs-lookup"><span data-stu-id="ce2b4-110">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple:</span></span>

<span data-ttu-id="ce2b4-111">{中繼伺服器 FQDN] 中，中繼伺服器接聽連接埠 （TLS 或 TCP）： 閘道 IP 與 FQDN、 閘道聆聽連接埠}</span><span class="sxs-lookup"><span data-stu-id="ce2b4-111">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ce2b4-112">本主題假設您所安裝的 PSTN 閘道與根主幹，且至少一個使用組合式還是獨立式中繼伺服器或集區中所述<A href="lync-server-2013-define-a-gateway-in-topology-builder.md">定義在 Lync Server 2013 中的拓撲產生器的閘道</A>部署文件中。</span><span class="sxs-lookup"><span data-stu-id="ce2b4-112">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ce2b4-113">本主題假設您已設定至少一個前端集區或 Standard Edition server 在至少一個中央網站中所述<A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">定義和設定 Lync Server 2013 中的前端集區或 Standard Edition server</A>和<A href="lync-server-2013-publish-the-topology.md">發佈 Lync Server 2013 中的拓撲</A>中部署文件。</span><span class="sxs-lookup"><span data-stu-id="ce2b4-113">This topic assumes that you have set up at least one Front End pool or Standard Edition server in at least one central site, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="ce2b4-114">若要定義中繼伺服器和閘道對等之間的其他主幹</span><span class="sxs-lookup"><span data-stu-id="ce2b4-114">To Define an additional Trunk between a Mediation Server and a Gateway Peer</span></span>

1.  <span data-ttu-id="ce2b4-115">啟動拓撲產生器： 按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 拓撲產生器]**。</span><span class="sxs-lookup"><span data-stu-id="ce2b4-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="ce2b4-116">在 [Lync Server 2013 中，您的網站名稱，**共用元件**，以滑鼠右鍵按一下 [**主幹**] 節點中，然後再按一下 [**新主幹**。</span><span class="sxs-lookup"><span data-stu-id="ce2b4-116">Under Lync Server 2013, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
    
    <span data-ttu-id="ce2b4-117">![Lync Server 拓撲產生器檔案結構畫面](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server 拓撲產生器檔案結構畫面")</span><span class="sxs-lookup"><span data-stu-id="ce2b4-117">![Lync Server Topology Builder file structure screen](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server Topology Builder file structure screen")</span></span>

3.  <span data-ttu-id="ce2b4-118">在 [**定義新的主幹**，指定來唯一地識別主幹的易記名稱。</span><span class="sxs-lookup"><span data-stu-id="ce2b4-118">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="ce2b4-119">您不能有相同名稱的兩個主幹。</span><span class="sxs-lookup"><span data-stu-id="ce2b4-119">You cannot have two trunks with the same name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ce2b4-120">如果您指定傳輸層安全性 (TLS) 作為傳輸類型，您必須指定的 FQDN，而不是對等的中繼伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="ce2b4-120">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="ce2b4-121">在 [**關聯的 PSTN 閘道**] 中，選取要與此主幹建立關聯的 PSTN 閘道對等。</span><span class="sxs-lookup"><span data-stu-id="ce2b4-121">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    
    <span data-ttu-id="ce2b4-122">![主幹的 PSTN 閘道對等的屬性設定](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "主幹的 PSTN 閘道對等的屬性設定")</span><span class="sxs-lookup"><span data-stu-id="ce2b4-122">![Property settings for PSTN gateway peer for trunk](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Property settings for PSTN gateway peer for trunk")</span></span>

5.  <span data-ttu-id="ce2b4-123">[ **PSTN 閘道的聆聽連接埠**，] 下方輸入 [聆聽連接埠，對等網路 （PSTN 閘道、 IP-PBX 或 SBC） 會接收 SIP 訊息是要與此主幹建立關聯的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="ce2b4-123">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="ce2b4-124">預設的對等網路連接埠是 5066 傳輸控制通訊協定 (TCP) 及 5067 用於傳輸層安全性 (TLS)。</span><span class="sxs-lookup"><span data-stu-id="ce2b4-124">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="ce2b4-125">預設 Survivable Branch Appliance 連接埠是 5081 tcp 和 tls 5082。</span><span class="sxs-lookup"><span data-stu-id="ce2b4-125">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>

6.  <span data-ttu-id="ce2b4-126">在 [ **SIP 傳輸通訊協定**] 下按一下對等使用的傳輸類型。</span><span class="sxs-lookup"><span data-stu-id="ce2b4-126">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ce2b4-127">基於安全性考量，我們強烈建議您將對等部署至中繼伺服器可以使用 TLS。</span><span class="sxs-lookup"><span data-stu-id="ce2b4-127">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

7.  <span data-ttu-id="ce2b4-128">在 [**相關中繼伺服器**，選取要與此對等的根主幹建立關聯的中繼伺服器集區</span><span class="sxs-lookup"><span data-stu-id="ce2b4-128">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>

8.  <span data-ttu-id="ce2b4-129">在 [**相關中繼伺服器連接埠**，輸入中繼伺服器將會從對等接收 SIP 訊息的聆聽連接埠。</span><span class="sxs-lookup"><span data-stu-id="ce2b4-129">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ce2b4-130">支援多個主幹 Lync Server 2013 中，兩個不同主幹名稱的主幹不能設定同一個<STRONG>相關聯的中繼伺服器連接埠</STRONG>與<STRONG>IP/PSTN 閘道的聆聽連接埠</STRONG></span><span class="sxs-lookup"><span data-stu-id="ce2b4-130">With multiple trunk support in Lync Server 2013, two trunks with different trunk names cannot be configured with the same <STRONG>Associated Mediation Server port</STRONG> and <STRONG>Listening Port for IP/PSTN gateway</STRONG></span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ce2b4-131">支援多個主幹 Lync Server 2013 中，多個 SIP 訊號連接埠可定義通訊中繼伺服器上具有多個對等。</span><span class="sxs-lookup"><span data-stu-id="ce2b4-131">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="ce2b4-132">定義主幹時, 的<STRONG>相關聯的中繼伺服器連接埠</STRONG>號碼必須範圍內的個別中繼伺服器所允許的通訊協定的聆聽連接埠。</span><span class="sxs-lookup"><span data-stu-id="ce2b4-132">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="ce2b4-133">此連接埠範圍定義在 Lync Server 2013 和中繼伺服器集區之下。</span><span class="sxs-lookup"><span data-stu-id="ce2b4-133">This port range is defined under Lync Server 2013 and Mediation Server pools.</span></span> <span data-ttu-id="ce2b4-134">以滑鼠右鍵按一下相關的中繼伺服器集區]，然後選取 [<STRONG>編輯內容]</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="ce2b4-134">Right-click the relevant Mediation Server pool, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="ce2b4-135">在 <STRONG>[聆聽連接埠]</STRONG> 欄位中指定連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="ce2b4-135">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

9.  <span data-ttu-id="ce2b4-136">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ce2b4-136">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ce2b4-137">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ce2b4-137">See Also</span></span>


[<span data-ttu-id="ce2b4-138">修改主幹在 Lync Server 2013 中的拓撲產生器</span><span class="sxs-lookup"><span data-stu-id="ce2b4-138">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

