---
title: 在商務用 Skype Server 的 [拓撲產生器] 中定義其他 trunks
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
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: '摘要: 瞭解如何在商務用 Skype Server 的 [拓撲產生器] 中定義其他主幹與 [閘道對等]。'
ms.openlocfilehash: de6cfd45c9e5f8440fcbcf6b6098a82edda752f0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193537"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="192da-103">在商務用 Skype Server 的 [拓撲產生器] 中定義其他 trunks</span><span class="sxs-lookup"><span data-stu-id="192da-103">Define additional trunks in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="192da-104">**摘要:** 瞭解如何在商務用 Skype Server 的 [拓撲建立器] 中, 定義在中繼伺服器與閘道對等之間的其他主幹。</span><span class="sxs-lookup"><span data-stu-id="192da-104">**Summary:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="192da-105">請依照下列步驟來定義您可以將對等與中繼伺服器產生關聯的其他主幹。</span><span class="sxs-lookup"><span data-stu-id="192da-105">Follow these steps to define an additional trunk to which you can associate a peer with a Mediation Server.</span></span> <span data-ttu-id="192da-106">對等可為使用者提供可連線至公用交換電話網絡 (PSTN) 的企業語音功能。</span><span class="sxs-lookup"><span data-stu-id="192da-106">A peer provides users enabled for Enterprise Voice with connectivity to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="192da-107">對等可以是 PSTN 閘道、IP PBX, 或網際網路電話服務提供者 (ITSP) 的會話邊界控制器 (SBC)。</span><span class="sxs-lookup"><span data-stu-id="192da-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span>
  
<span data-ttu-id="192da-108">主幹是中繼伺服器與閘道之間的邏輯連線。</span><span class="sxs-lookup"><span data-stu-id="192da-108">A trunk is a logical connection between a Mediation Server and a gateway.</span></span>
  
> [!NOTE]
> <span data-ttu-id="192da-109">本主題假設您已使用至少一個 collocated 或獨立的中繼伺服器或池來設定 PSTN 閘道和根幹線, 如所述, 請參閱在部署檔中的商務用 Skype Server 中的 [拓撲建立器] 中的 [[定義閘道](define-a-gateway.md)]。</span><span class="sxs-lookup"><span data-stu-id="192da-109">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in [Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) in the Deployment documentation.</span></span>
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="192da-110">在中繼伺服器與閘道對等之間定義額外主幹</span><span class="sxs-lookup"><span data-stu-id="192da-110">To define an additional trunk between a Mediation Server and a gateway peer</span></span>

1. <span data-ttu-id="192da-111">啟動拓撲產生器: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype server 2015**], 然後按一下 [**商務用 skype server 2015Topology**建立器]。</span><span class="sxs-lookup"><span data-stu-id="192da-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="192da-112">在商務用 Skype Server、您的網站名稱、**共用元件**中, 以滑鼠右鍵按一下 [ **Trunks** ] 節點, 然後按一下 [**新幹線**]。</span><span class="sxs-lookup"><span data-stu-id="192da-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
   1. <span data-ttu-id="192da-113">在 [**定義新主幹**] 中, 指定要唯一識別主幹的易記名稱。</span><span class="sxs-lookup"><span data-stu-id="192da-113">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="192da-114">您不能有兩個名稱相同的 trunks。</span><span class="sxs-lookup"><span data-stu-id="192da-114">You cannot have two trunks with the same name.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="192da-115">如果您將傳輸層安全性 (TLS) 指定為傳輸類型, 您必須指定 FQDN, 而不是對轉送伺服器對等的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="192da-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
3. <span data-ttu-id="192da-116">在 [**關聯的 PSTN 閘道**] 底下, 選取 PSTN 閘道對, 以與此幹線建立關聯。</span><span class="sxs-lookup"><span data-stu-id="192da-116">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    5. <span data-ttu-id="192da-117">在 [ **PSTN 閘道的偵聽埠**] 底下, 輸入對等 (PSTN 閘道、IP PBX 或 SBC) 的偵聽埠, 將會從要與此幹線關聯的中繼伺服器接收 SIP 訊息。</span><span class="sxs-lookup"><span data-stu-id="192da-117">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="192da-118">預設對等埠是針對傳輸控制通訊協定 (TCP) 和 5067 (針對傳輸層安全性 (TLS)) 的5066。</span><span class="sxs-lookup"><span data-stu-id="192da-118">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="192da-119">預設的 Survivable 分支裝置埠是適用于 TCP 的 5081, 以及適用于 TLS 的5082。</span><span class="sxs-lookup"><span data-stu-id="192da-119">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>
    
4. <span data-ttu-id="192da-120">在 [ **SIP 傳輸通訊協定**] 底下, 按一下對等所使用的傳輸類型。</span><span class="sxs-lookup"><span data-stu-id="192da-120">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="192da-121">出於安全性考慮, 我們強烈建議您將對等部署到可使用 TLS 的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="192da-121">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
5. <span data-ttu-id="192da-122">在 [**關聯的中繼伺服器**] 底下, 選取 [轉送伺服器] 池以與此對等方的根幹線建立關聯</span><span class="sxs-lookup"><span data-stu-id="192da-122">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>
    
6. <span data-ttu-id="192da-123">在 [**關聯的中繼伺服器埠**] 底下, 輸入中繼伺服器將從對等接收 SIP 訊息的偵聽埠。</span><span class="sxs-lookup"><span data-stu-id="192da-123">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="192da-124">在商務用 Skype Server 中有多個幹線支援, 不能使用相同的**關聯中繼伺服器埠**和**偵聽埠 (適用于 IP/PSTN 閘道**) 來設定不同主幹名稱的兩個 trunks</span><span class="sxs-lookup"><span data-stu-id="192da-124">With multiple trunk support in Skype for Business Server, two trunks with different trunk names cannot be configured with the same **Associated Mediation Server port** and **Listening Port for IP/PSTN gateway**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="192da-125">在商務用 Skype Server 中有多個幹線支援, 您可以在中繼伺服器上定義多個 SIP 信號埠, 以便與多個對等進行通訊。</span><span class="sxs-lookup"><span data-stu-id="192da-125">With multiple trunk support in Skype for Business Server, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="192da-126">在定義主幹時,**關聯的中繼伺服器埠**編號必須在中繼伺服器所允許之個別通訊協定的偵聽埠範圍內。</span><span class="sxs-lookup"><span data-stu-id="192da-126">When defining a trunk, the **Associated Mediation Server port** number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="192da-127">此埠範圍是在商務用 Skype Server 和中繼伺服器池底下定義。</span><span class="sxs-lookup"><span data-stu-id="192da-127">This port range is defined under Skype for Business Server and Mediation Server pools.</span></span> <span data-ttu-id="192da-128">以滑鼠右鍵按一下相關的中繼伺服器池, 然後選取 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="192da-128">Right-click the relevant Mediation Server pool, and select **Edit Properties**.</span></span> <span data-ttu-id="192da-129">在 [**偵聽埠**] 欄位中指定埠範圍。</span><span class="sxs-lookup"><span data-stu-id="192da-129">Specify the port range in the **Listening ports** field.</span></span>
  
7. <span data-ttu-id="192da-130">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="192da-130">Click **OK**.</span></span> 
    

