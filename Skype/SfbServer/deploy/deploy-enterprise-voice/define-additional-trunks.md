---
title: 在商務用 Skype Server 中定義拓撲產生器中的其他主幹
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
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 摘要：瞭解如何在商務用 Skype Server 的拓撲產生器中，定義轉送伺服器與閘道對等之間的其他主幹。
ms.openlocfilehash: 3aab744761420ab631f17e6b56391f1fab120ccf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836993"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="62bc0-103">在商務用 Skype Server 中定義拓撲產生器中的其他主幹</span><span class="sxs-lookup"><span data-stu-id="62bc0-103">Define additional trunks in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="62bc0-104">**摘要：** 瞭解如何在商務用 Skype Server 的拓撲產生器中，定義轉送伺服器與閘道對等之間的其他主幹。</span><span class="sxs-lookup"><span data-stu-id="62bc0-104">**Summary:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="62bc0-105">請遵循下列步驟來定義您可以將對等與轉送伺服器產生關聯的其他主幹。</span><span class="sxs-lookup"><span data-stu-id="62bc0-105">Follow these steps to define an additional trunk to which you can associate a peer with a Mediation Server.</span></span> <span data-ttu-id="62bc0-106">對等使用者可為使用者啟用企業語音，以連線到公用交換電話網路 (PSTN) 。</span><span class="sxs-lookup"><span data-stu-id="62bc0-106">A peer provides users enabled for Enterprise Voice with connectivity to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="62bc0-107">對等可以是 Internet 電話語音服務提供者的 PSTN 閘道、IP-PBX 或會話邊界控制器 (SBC)  (ITSP) 。</span><span class="sxs-lookup"><span data-stu-id="62bc0-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span>
  
<span data-ttu-id="62bc0-108">主幹是轉送伺服器與閘道之間的邏輯連接。</span><span class="sxs-lookup"><span data-stu-id="62bc0-108">A trunk is a logical connection between a Mediation Server and a gateway.</span></span>
  
> [!NOTE]
> <span data-ttu-id="62bc0-109">本主題假設您已安裝具有至少一個組合或獨立轉送伺服器或集區的 PSTN 閘道和根主幹，如在部署檔中的 [ [商務用 Skype Server](define-a-gateway.md) 中的拓撲產生器中定義閘道] 所述。</span><span class="sxs-lookup"><span data-stu-id="62bc0-109">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in [Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) in the Deployment documentation.</span></span>
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="62bc0-110">在轉送伺服器與閘道對等間定義其他主幹</span><span class="sxs-lookup"><span data-stu-id="62bc0-110">To define an additional trunk between a Mediation Server and a gateway peer</span></span>

1. <span data-ttu-id="62bc0-111">啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype server 2015**]，然後按一下 [ **商務用 skype server 2015Topology** 建立器]。</span><span class="sxs-lookup"><span data-stu-id="62bc0-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="62bc0-112">在 [商務用 Skype 伺服器] 底下，您的網站名稱， **共用元件**，以滑鼠右鍵按一下 **主幹** 節點，然後按一下 [ **新增主幹**]。</span><span class="sxs-lookup"><span data-stu-id="62bc0-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
   1. <span data-ttu-id="62bc0-113">在 [ **定義新的主幹**] 中，指定可唯一識別主幹的易記名稱。</span><span class="sxs-lookup"><span data-stu-id="62bc0-113">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="62bc0-114">您不能有兩個具有相同名稱的主幹。</span><span class="sxs-lookup"><span data-stu-id="62bc0-114">You cannot have two trunks with the same name.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="62bc0-115">如果您指定傳輸層安全性 (TLS) 做為傳輸類型，您必須指定 FQDN 而非轉送伺服器對等的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="62bc0-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
3. <span data-ttu-id="62bc0-116">在 [ **關聯的 pstn 閘道**] 底下，選取 PSTN 閘道對等相關聯的主幹。</span><span class="sxs-lookup"><span data-stu-id="62bc0-116">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    5. <span data-ttu-id="62bc0-117">在 [ **適用于 PSTN 閘道的聆聽埠**] 底下，輸入對等 (PSTN 閘道、IP-PBX 或 SBC) 將要從轉送伺服器接收 SIP 郵件的收聽埠，該伺服器將會與此主幹產生關聯。</span><span class="sxs-lookup"><span data-stu-id="62bc0-117">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="62bc0-118">傳輸控制通訊協定 (TCP) 和5067的傳輸層安全性 (TLS) 的預設對等埠為5066。</span><span class="sxs-lookup"><span data-stu-id="62bc0-118">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="62bc0-119">Survivable 的預設分支裝置埠是5081的 TCP 和5082的 TLS。</span><span class="sxs-lookup"><span data-stu-id="62bc0-119">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>
    
4. <span data-ttu-id="62bc0-120">在 [ **SIP 傳輸通訊協定**] 下，按一下對等使用的傳輸類型。</span><span class="sxs-lookup"><span data-stu-id="62bc0-120">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="62bc0-121">基於安全性考慮，強烈建議您將對等部署至可使用 TLS 的轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="62bc0-121">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
5. <span data-ttu-id="62bc0-122">在 [關聯的中繼 **伺服器**] 底下，選取要與此對等的根主幹相關聯的轉送伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="62bc0-122">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>
    
6. <span data-ttu-id="62bc0-123">在 [關聯的中繼 **伺服器埠**] 底下，輸入轉送伺服器接收來自對等的 SIP 訊息的聆聽埠。</span><span class="sxs-lookup"><span data-stu-id="62bc0-123">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="62bc0-124">在商務用 Skype Server 中有多個主幹支援，無法使用 **IP/PSTN 閘道** 的相同 **關聯轉送伺服器埠** 和偵聽通訊埠來設定具有不同主幹名稱的兩個主幹</span><span class="sxs-lookup"><span data-stu-id="62bc0-124">With multiple trunk support in Skype for Business Server, two trunks with different trunk names cannot be configured with the same **Associated Mediation Server port** and **Listening Port for IP/PSTN gateway**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="62bc0-125">在商務用 Skype Server 中使用多個主幹支援，可在轉送伺服器上定義多個 SIP 信號埠，以進行與多個對等專案的通訊。</span><span class="sxs-lookup"><span data-stu-id="62bc0-125">With multiple trunk support in Skype for Business Server, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="62bc0-126">在定義主幹時，關聯的中繼 **伺服器埠** 號碼必須位於轉送伺服器所允許之個別通訊埠的偵聽埠範圍內。</span><span class="sxs-lookup"><span data-stu-id="62bc0-126">When defining a trunk, the **Associated Mediation Server port** number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="62bc0-127">此埠範圍是在商務用 Skype Server 和轉送伺服器集區所定義。</span><span class="sxs-lookup"><span data-stu-id="62bc0-127">This port range is defined under Skype for Business Server and Mediation Server pools.</span></span> <span data-ttu-id="62bc0-128">在相關的轉送伺服器集區上按一下滑鼠右鍵，然後選取 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="62bc0-128">Right-click the relevant Mediation Server pool, and select **Edit Properties**.</span></span> <span data-ttu-id="62bc0-129">在 **[聆聽連接埠]** 欄位中指定連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="62bc0-129">Specify the port range in the **Listening ports** field.</span></span>
  
7. <span data-ttu-id="62bc0-130">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="62bc0-130">Click **OK**.</span></span> 
    

