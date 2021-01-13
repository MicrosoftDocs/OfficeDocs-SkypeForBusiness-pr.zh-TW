---
title: 在商務用 Skype Server 的拓撲產生器中定義閘道
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 摘要：瞭解如何在商務用 Skype Server 的拓撲產生器中定義 PSTN 閘道。
ms.openlocfilehash: be68c853cdcd530b05ad4b0949f722788e77d0df
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837023"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="ba5f5-103">在商務用 Skype Server 的拓撲產生器中定義閘道</span><span class="sxs-lookup"><span data-stu-id="ba5f5-103">Define a gateway in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="ba5f5-104">**摘要：** 瞭解如何在商務用 Skype Server 的拓撲產生器中定義 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="ba5f5-104">**Summary:** Learn how to define a PSTN gateway in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="ba5f5-105">請遵循下列步驟，使用拓撲產生器來定義與轉送伺服器相關聯的對等對等能力，以便為已啟用 Enterprise Voice 的使用者提供公用交換電話網路 (PSTN) 連線。</span><span class="sxs-lookup"><span data-stu-id="ba5f5-105">Follow these steps to use Topology Builder to define a peer with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="ba5f5-106">對等與轉送伺服器的對等可以是 Internet 電話語音服務提供者 (SBC) 的 PSTN 閘道、IP-PBX 或會話邊界控制器， (透過設定 SIP 主幹來連接的 ITSP) 。</span><span class="sxs-lookup"><span data-stu-id="ba5f5-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>
  
### <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="ba5f5-107">若要定義轉送伺服器的對等</span><span class="sxs-lookup"><span data-stu-id="ba5f5-107">To define a peer for the Mediation Server</span></span>

1. <span data-ttu-id="ba5f5-108">啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype server 2015**]，然後按一下 [ **商務用 skype server 2015Topology** 建立器]。</span><span class="sxs-lookup"><span data-stu-id="ba5f5-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="ba5f5-109">在 [商務用 Skype 伺服器] 底下，您的網站名稱，共用元件，以滑鼠右鍵按一下 [ **PSTN 閘道** ] 節點，然後按一下 [ **新增 pstn 閘道**]。</span><span class="sxs-lookup"><span data-stu-id="ba5f5-109">Under Skype for Business Server, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
3. <span data-ttu-id="ba5f5-110">在 **[定義新的 IP/PSTN 閘道]** 中，輸入對等的完整網域名稱 (FQDN) 或 IP 位址，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ba5f5-110">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ba5f5-111">如果您指定傳輸層安全性 (TLS) 做為傳輸類型，您必須指定 FQDN 而非轉送伺服器對等的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="ba5f5-111">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="ba5f5-112">定義您新的 PSTN 閘道的 IP 位址的聆聽模式 (IPv4 或 IPv6)，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ba5f5-112">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>

5. <span data-ttu-id="ba5f5-113">定義 PSTN 閘道的根主幹。</span><span class="sxs-lookup"><span data-stu-id="ba5f5-113">Define a root trunk for the PSTN gateway.</span></span> <span data-ttu-id="ba5f5-114">主幹是由元組唯一識別的轉送伺服器與閘道之間的邏輯連接。</span><span class="sxs-lookup"><span data-stu-id="ba5f5-114">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="ba5f5-115">{轉送伺服器 FQDN、轉送伺服器接聽埠 (TLS 或 TCP) ：閘道 IP 和 FQDN，閘道聆聽埠}</span><span class="sxs-lookup"><span data-stu-id="ba5f5-115">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
     - <span data-ttu-id="ba5f5-116">在拓撲產生器中定義 PSTN 閘道時，您必須定義一個根主幹，以順利將 PSTN 閘道新增至您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="ba5f5-116">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
     - <span data-ttu-id="ba5f5-117">必須先移除關聯的 PSTN 閘道，才能移除根主幹。</span><span class="sxs-lookup"><span data-stu-id="ba5f5-117">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
6. <span data-ttu-id="ba5f5-118">在 [ **IP/PSTN 閘道的聆聽埠**] 底下，輸入閘道、PBX 或 SBC 將用於從轉送伺服器將其與 PSTN 閘道根主幹相關聯的 SIP 郵件所使用的收聽埠。</span><span class="sxs-lookup"><span data-stu-id="ba5f5-118">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="ba5f5-119"> (依預設，在 PSTN 閘道、PBX 或 SBC 上，傳輸控制通訊協定 (TCP) 和5067的傳輸層安全性 (TLS) 的埠是5066。</span><span class="sxs-lookup"><span data-stu-id="ba5f5-119">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="ba5f5-120">在分支網站上的 Survivable 分支裝置中，TCP 和5082的預設埠為5081，以供 TLS 使用。 ) </span><span class="sxs-lookup"><span data-stu-id="ba5f5-120">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>
    
7. <span data-ttu-id="ba5f5-121">在 **[SIP 傳輸通訊協定]** 下，按一下對等使用的傳輸類型，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ba5f5-121">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ba5f5-122">基於安全性考慮，強烈建議您將對等部署至可使用 TLS 的轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="ba5f5-122">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
8. <span data-ttu-id="ba5f5-123">在 [關聯的轉送伺服器] 底下，選取要與此 PSTN 閘道 **之** 根主幹產生關聯的轉送伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="ba5f5-123">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>
    
9. <span data-ttu-id="ba5f5-124">在 [關聯的中繼 **伺服器埠**] 底下，輸入轉送伺服器將用於來自閘道的 SIP 訊息的聆聽埠。</span><span class="sxs-lookup"><span data-stu-id="ba5f5-124">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ba5f5-125">在商務用 Skype Server 中使用多個主幹支援，您可以在轉送伺服器上定義多個 SIP 信號埠，以與多個 PSTN 閘道進行通訊。</span><span class="sxs-lookup"><span data-stu-id="ba5f5-125">With multiple trunk support in Skype for Business Server, you can define multiple SIP signaling ports on the Mediation Server for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="ba5f5-126">在定義主幹時，關聯的中繼 **伺服器埠** 必須位於轉送伺服器所允許之個別通訊埠的偵聽埠範圍內。</span><span class="sxs-lookup"><span data-stu-id="ba5f5-126">When defining a trunk, the **Associated Mediation Server port** must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="ba5f5-127">此埠範圍是在商務用 Skype Server 和中繼集區所定義。</span><span class="sxs-lookup"><span data-stu-id="ba5f5-127">This port range is defined under Skype for Business Server and Mediation Pools.</span></span> <span data-ttu-id="ba5f5-128">在感興趣的轉送伺服器集區上按一下滑鼠右鍵，然後選取 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="ba5f5-128">Right-click the Mediation Server pool of interest, and select **Edit Properties**.</span></span> <span data-ttu-id="ba5f5-129">在 **[聆聽連接埠]** 欄位中指定連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="ba5f5-129">Specify the port range in the **Listening ports** field.</span></span>
  
10. <span data-ttu-id="ba5f5-130">確定您定義的對等機器正在執行，並使用您指定的 FQDN 或 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="ba5f5-130">Be sure that the peer you defined is running and using the FQDN or IP address that you specified.</span></span> <span data-ttu-id="ba5f5-131">然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="ba5f5-131">Then click **Finish**.</span></span>
    
11. <span data-ttu-id="ba5f5-132">以滑鼠右鍵按一下 [ **商務用 Skype 伺服器** ] 節點，然後按一下 [ **發行拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="ba5f5-132">Right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
    

