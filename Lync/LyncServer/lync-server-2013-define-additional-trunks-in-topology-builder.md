---
title: Lync Server 2013：在拓撲產生器中定義其他主幹
description: Lync Server 2013：在拓撲產生器中定義其他主幹。
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
ms.openlocfilehash: 57983d3e4d6a47c14f2dcdc153fe6872a33eb6e9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567559"
---
# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="22a71-103">在 Lync Server 2013 中的拓撲產生器中定義其他主幹</span><span class="sxs-lookup"><span data-stu-id="22a71-103">Define additional trunks in Topology Builder in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22a71-104">_**主題上次修改日期：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="22a71-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="22a71-105">請遵循下列步驟，使用拓撲產生器來定義您可以將 *對等* 與轉送伺服器產生關聯的其他主幹。</span><span class="sxs-lookup"><span data-stu-id="22a71-105">Follow these steps to use Topology Builder to define an additional trunk to which you can associate a *peer* with a Mediation Server.</span></span> <span data-ttu-id="22a71-106">對等使用者可為使用者啟用企業語音，以連線到公用交換電話網路 (PSTN) 。</span><span class="sxs-lookup"><span data-stu-id="22a71-106">A peer provides users enabled for Enterprise Voice with connectivity to the public switched telephone network (PSTN).</span></span> <span data-ttu-id="22a71-107">對等可以是 Internet 電話語音服務提供者的 PSTN 閘道、IP-PBX 或會話邊界控制器 (SBC)  (ITSP) 。</span><span class="sxs-lookup"><span data-stu-id="22a71-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span> <span data-ttu-id="22a71-108">主幹定義轉送伺服器和對等之間的連線。</span><span class="sxs-lookup"><span data-stu-id="22a71-108">The trunk defines this connection between the Mediation Server and peer.</span></span> <span data-ttu-id="22a71-109">每個轉送伺服器可以定義多個主幹。</span><span class="sxs-lookup"><span data-stu-id="22a71-109">Multiple trunks can be defined per Mediation Server.</span></span> <span data-ttu-id="22a71-110">轉送伺服器可以與多個對等專案產生關聯。</span><span class="sxs-lookup"><span data-stu-id="22a71-110">A Mediation Server can be associated with multiple peers.</span></span>

<span data-ttu-id="22a71-111">主幹是由元組唯一識別的轉送伺服器與閘道之間的邏輯連接：</span><span class="sxs-lookup"><span data-stu-id="22a71-111">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple:</span></span>

<span data-ttu-id="22a71-112">{轉送伺服器 FQDN、轉送伺服器接聽埠 (TLS 或 TCP) ：閘道 IP 和 FQDN，閘道聆聽埠}</span><span class="sxs-lookup"><span data-stu-id="22a71-112">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="22a71-113">本主題假設您已安裝具有至少一個組合或獨立轉送伺服器或集區的 PSTN 閘道和根主幹，如在部署檔中的 [在 Lync Server 2013 中的拓撲產生器中 <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">定義閘道</A> ] 所述。</span><span class="sxs-lookup"><span data-stu-id="22a71-113">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="22a71-114">本主題假設您已在至少一個中央網站中設定至少一個前端集區或 Standard Edition server，如在 <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013 中定義及設定前端集區或 Standard edition server</A> ，以及在部署檔中 <A href="lync-server-2013-publish-the-topology.md">發佈 lync server 2013</A> 中所述的拓撲。</span><span class="sxs-lookup"><span data-stu-id="22a71-114">This topic assumes that you have set up at least one Front End pool or Standard Edition server in at least one central site, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="22a71-115">在轉送伺服器與閘道對等間定義其他主幹</span><span class="sxs-lookup"><span data-stu-id="22a71-115">To Define an additional Trunk between a Mediation Server and a Gateway Peer</span></span>

1.  <span data-ttu-id="22a71-116">啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="22a71-116">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="22a71-117">在 [Lync Server 2013] 底下，您的網站名稱， **共用元件**，以滑鼠右鍵按一下 **主幹** 節點，然後按一下 [ **新增主幹**]。</span><span class="sxs-lookup"><span data-stu-id="22a71-117">Under Lync Server 2013, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
    
    <span data-ttu-id="22a71-118">![Lync Server 拓撲產生器檔結構畫面](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server 拓撲產生器檔結構畫面")</span><span class="sxs-lookup"><span data-stu-id="22a71-118">![Lync Server Topology Builder file structure screen](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server Topology Builder file structure screen")</span></span>

3.  <span data-ttu-id="22a71-119">在 [ **定義新的主幹**] 中，指定可唯一識別主幹的易記名稱。</span><span class="sxs-lookup"><span data-stu-id="22a71-119">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="22a71-120">您不能有兩個具有相同名稱的主幹。</span><span class="sxs-lookup"><span data-stu-id="22a71-120">You cannot have two trunks with the same name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22a71-121">如果您指定傳輸層安全性 (TLS) 做為傳輸類型，您必須指定 FQDN 而非轉送伺服器對等的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="22a71-121">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="22a71-122">在 [ **關聯的 pstn 閘道**] 底下，選取 PSTN 閘道對等相關聯的主幹。</span><span class="sxs-lookup"><span data-stu-id="22a71-122">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    
    <span data-ttu-id="22a71-123">![PSTN 閘道對等屬性設定（適用于主幹）](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "PSTN 閘道對等屬性設定（適用于主幹）")</span><span class="sxs-lookup"><span data-stu-id="22a71-123">![Property settings for PSTN gateway peer for trunk](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Property settings for PSTN gateway peer for trunk")</span></span>

5.  <span data-ttu-id="22a71-124">在 [ **適用于 PSTN 閘道的聆聽埠**] 底下，輸入對等 (PSTN 閘道、IP-PBX 或 SBC) 將要從轉送伺服器接收 SIP 郵件的收聽埠，該伺服器將會與此主幹產生關聯。</span><span class="sxs-lookup"><span data-stu-id="22a71-124">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="22a71-125">傳輸控制通訊協定 (TCP) 和5067的傳輸層安全性 (TLS) 的預設對等埠為5066。</span><span class="sxs-lookup"><span data-stu-id="22a71-125">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="22a71-126">Survivable 的預設分支裝置埠是5081的 TCP 和5082的 TLS。</span><span class="sxs-lookup"><span data-stu-id="22a71-126">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>

6.  <span data-ttu-id="22a71-127">在 [ **SIP 傳輸通訊協定**] 下，按一下對等使用的傳輸類型。</span><span class="sxs-lookup"><span data-stu-id="22a71-127">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22a71-128">基於安全性考慮，強烈建議您將對等部署至可使用 TLS 的轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="22a71-128">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

7.  <span data-ttu-id="22a71-129">在 [關聯的中繼 **伺服器**] 底下，選取要與此對等的根主幹相關聯的轉送伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="22a71-129">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>

8.  <span data-ttu-id="22a71-130">在 [關聯的中繼 **伺服器埠**] 底下，輸入轉送伺服器接收來自對等的 SIP 訊息的聆聽埠。</span><span class="sxs-lookup"><span data-stu-id="22a71-130">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22a71-131">在 Lync Server 2013 中有多個主幹支援，無法使用<STRONG>IP/PSTN 閘道</STRONG>的相同<STRONG>關聯轉送伺服器埠</STRONG>和偵聽埠來設定具有不同主幹名稱的兩個主幹</span><span class="sxs-lookup"><span data-stu-id="22a71-131">With multiple trunk support in Lync Server 2013, two trunks with different trunk names cannot be configured with the same <STRONG>Associated Mediation Server port</STRONG> and <STRONG>Listening Port for IP/PSTN gateway</STRONG></span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22a71-132">在 Lync Server 2013 中有多個主幹支援，可在轉送伺服器上定義多個 SIP 信號埠，以與多個對等機進行通訊。</span><span class="sxs-lookup"><span data-stu-id="22a71-132">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="22a71-133">在定義主幹時，關聯的中繼 <STRONG>伺服器埠</STRONG> 號碼必須位於轉送伺服器所允許之個別通訊埠的偵聽埠範圍內。</span><span class="sxs-lookup"><span data-stu-id="22a71-133">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="22a71-134">此埠範圍是在 [Lync Server 2013 和轉送伺服器集區] 下定義。</span><span class="sxs-lookup"><span data-stu-id="22a71-134">This port range is defined under Lync Server 2013 and Mediation Server pools.</span></span> <span data-ttu-id="22a71-135">在相關的轉送伺服器集區上按一下滑鼠右鍵，然後選取 [ <STRONG>編輯屬性</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="22a71-135">Right-click the relevant Mediation Server pool, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="22a71-136">在 <STRONG>[聆聽連接埠]</STRONG> 欄位中指定連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="22a71-136">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

9.  <span data-ttu-id="22a71-137">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22a71-137">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="22a71-138">另請參閱</span><span class="sxs-lookup"><span data-stu-id="22a71-138">See Also</span></span>


[<span data-ttu-id="22a71-139">在 Lync Server 2013 中的拓撲產生器中修改主幹</span><span class="sxs-lookup"><span data-stu-id="22a71-139">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

