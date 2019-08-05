---
title: 在商務用 Skype Server 的 [拓撲 Builder] 中定義閘道
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: '摘要: 瞭解如何在商務用 Skype Server 的 [拓撲產生器] 中定義 PSTN 閘道。'
ms.openlocfilehash: 39e2bdf041055e392b88cc25594b45c2529161d3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190405"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="8063c-103">在商務用 Skype Server 的 [拓撲 Builder] 中定義閘道</span><span class="sxs-lookup"><span data-stu-id="8063c-103">Define a gateway in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="8063c-104">**摘要:** 瞭解如何在商務用 Skype Server 的 [拓撲建立器] 中定義 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="8063c-104">**Summary:** Learn how to define a PSTN gateway in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="8063c-105">請依照下列步驟使用拓撲 Builder 來定義對等, 您可以將該對等與中繼伺服器建立關聯, 以便為啟用企業語音的使用者提供公用的交換電話網絡 (PSTN) 連線。</span><span class="sxs-lookup"><span data-stu-id="8063c-105">Follow these steps to use Topology Builder to define a peer with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="8063c-106">對轉送伺服器的對等可以是 PSTN 閘道、IP PBX 或會話邊界控制器 (ITSP), 您可以透過設定 SIP 幹線來連線該服務提供者。</span><span class="sxs-lookup"><span data-stu-id="8063c-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>
  
### <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="8063c-107">若要為中繼伺服器定義對等</span><span class="sxs-lookup"><span data-stu-id="8063c-107">To define a peer for the Mediation Server</span></span>

1. <span data-ttu-id="8063c-108">啟動拓撲產生器: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype server 2015**], 然後按一下 [**商務用 skype server 2015Topology**建立器]。</span><span class="sxs-lookup"><span data-stu-id="8063c-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="8063c-109">在商務用 Skype Server、您的網站名稱、共用元件中, 以滑鼠右鍵按一下**PSTN 閘道**節點, 然後按一下 [**新 pstn 閘道**]。</span><span class="sxs-lookup"><span data-stu-id="8063c-109">Under Skype for Business Server, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
3. <span data-ttu-id="8063c-110">在 [**定義新的 IP/PSTN 閘道**] 中, 輸入對等的完整功能變數名稱 (FQDN) 或 IP 位址, 然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8063c-110">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8063c-111">如果您將傳輸層安全性 (TLS) 指定為傳輸類型, 您必須指定 FQDN, 而不是對轉送伺服器對等的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8063c-111">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="8063c-112">定義新 PSTN 閘道之 IP 位址的偵聽模式 (IPv4 或 IPv6), 然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8063c-112">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>

5. <span data-ttu-id="8063c-113">為 PSTN 閘道定義根幹線。</span><span class="sxs-lookup"><span data-stu-id="8063c-113">Define a root trunk for the PSTN gateway.</span></span> <span data-ttu-id="8063c-114">幹線是由元組唯一識別的中繼伺服器與閘道之間的邏輯連線。</span><span class="sxs-lookup"><span data-stu-id="8063c-114">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="8063c-115">{轉送伺服器 FQDN, 中繼伺服器偵聽埠 (TLS 或 TCP): 閘道 IP 和 FQDN, 閘道偵聽埠}</span><span class="sxs-lookup"><span data-stu-id="8063c-115">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
     - <span data-ttu-id="8063c-116">在拓撲建立器中定義 PSTN 閘道時, 您必須定義根幹線, 才能成功將 PSTN 閘道新增到您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="8063c-116">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
     - <span data-ttu-id="8063c-117">移除關聯的 PSTN 閘道之後, 才能移除根主幹。</span><span class="sxs-lookup"><span data-stu-id="8063c-117">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
6. <span data-ttu-id="8063c-118">在 [ **IP/PSTN 閘道偵聽埠**] 底下, 輸入閘道、PBX 或 SBC 將用來處理來自中繼伺服器的 SIP 訊息的偵聽埠, 該埠會與 PSTN 閘道的根幹線產生關聯。</span><span class="sxs-lookup"><span data-stu-id="8063c-118">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="8063c-119">(根據預設, 埠在 PSTN 閘道、PBX 或 SBC 上的傳輸控制通訊協定 (TCP) 和 5067 (針對傳輸層安全性 (TLS)) 都是5066。</span><span class="sxs-lookup"><span data-stu-id="8063c-119">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="8063c-120">在分支網站的 Survivable 分支裝置上, 預設埠為 5081 (適用于 TCP, 而5082則為 TLS)。)</span><span class="sxs-lookup"><span data-stu-id="8063c-120">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>
    
7. <span data-ttu-id="8063c-121">在 [ **SIP 傳輸通訊協定**] 底下, 按一下對等所使用的傳輸類型, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="8063c-121">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8063c-122">出於安全性考慮, 我們強烈建議您將對等部署到可使用 TLS 的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="8063c-122">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
8. <span data-ttu-id="8063c-123">在 [**關聯的中繼伺服器**] 底下, 選取 [中繼伺服器] 池以與此 PSTN 閘道的根幹線建立關聯。</span><span class="sxs-lookup"><span data-stu-id="8063c-123">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>
    
9. <span data-ttu-id="8063c-124">在 [**關聯的中繼伺服器埠**] 底下, 輸入中繼伺服器將用於來自閘道的 SIP 訊息的偵聽埠。</span><span class="sxs-lookup"><span data-stu-id="8063c-124">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8063c-125">在商務用 Skype Server 中有多個幹線支援, 您可以在中繼伺服器上定義多個 SIP 信號埠, 以便與多個 PSTN 閘道進行通訊。</span><span class="sxs-lookup"><span data-stu-id="8063c-125">With multiple trunk support in Skype for Business Server, you can define multiple SIP signaling ports on the Mediation Server for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="8063c-126">在定義主幹時,**關聯的中繼伺服器埠**必須位於中繼伺服器所允許之各個通訊協定的偵聽埠範圍內。</span><span class="sxs-lookup"><span data-stu-id="8063c-126">When defining a trunk, the **Associated Mediation Server port** must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="8063c-127">此埠範圍是在商務用 Skype Server 和轉送池所定義。</span><span class="sxs-lookup"><span data-stu-id="8063c-127">This port range is defined under Skype for Business Server and Mediation Pools.</span></span> <span data-ttu-id="8063c-128">以滑鼠右鍵按一下感興趣的中繼伺服器池, 然後選取 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="8063c-128">Right-click the Mediation Server pool of interest, and select **Edit Properties**.</span></span> <span data-ttu-id="8063c-129">在 [**偵聽埠**] 欄位中指定埠範圍。</span><span class="sxs-lookup"><span data-stu-id="8063c-129">Specify the port range in the **Listening ports** field.</span></span>
  
10. <span data-ttu-id="8063c-130">請確定您定義的對等是執行中, 並使用您所指定的 FQDN 或 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8063c-130">Be sure that the peer you defined is running and using the FQDN or IP address that you specified.</span></span> <span data-ttu-id="8063c-131">然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="8063c-131">Then click **Finish**.</span></span>
    
11. <span data-ttu-id="8063c-132">以滑鼠右鍵按一下**商務用 Skype Server**節點, 然後按一下 [**發佈拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="8063c-132">Right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
    

