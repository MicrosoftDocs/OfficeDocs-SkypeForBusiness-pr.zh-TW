---
title: 在商務用 Skype Server 中建立 VIS 集區
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
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 摘要：使用拓撲產生器，在商務用 Skype Server 中建立影片 Interop 伺服器集區。
ms.openlocfilehash: 7c6f45b232151d99cbce169826c8110cf4a8d494
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802053"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a><span data-ttu-id="3eb67-103">在商務用 Skype Server 中建立 VIS 集區</span><span class="sxs-lookup"><span data-stu-id="3eb67-103">Create a VIS pool in Skype for Business Server</span></span>
 
<span data-ttu-id="3eb67-104">**摘要：** 使用拓撲產生器，在商務用 Skype Server 中建立影片 Interop 伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="3eb67-104">**Summary:** Create a Video Interop Server pool in Skype for Business Server using Topology Builder.</span></span>
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a><span data-ttu-id="3eb67-105">使用拓撲產生器建立 VIS 或 VIS 集區</span><span class="sxs-lookup"><span data-stu-id="3eb67-105">Create a VIS or VIS pool using Topology Builder</span></span>

1. <span data-ttu-id="3eb67-106">在前端伺服器上開啟拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="3eb67-106">Open Topology Builder on the front end server.</span></span> <span data-ttu-id="3eb67-107">在 [拓撲產生器] 的左窗格中，以滑鼠右鍵按一下 [ **影片 Interop 伺服器** 集區]，然後選擇 [ **新增影片 interop 伺服器集** 區]</span><span class="sxs-lookup"><span data-stu-id="3eb67-107">From the left pane of Topology Builder, right click on **Video Interop Server Pools** and choose **New Video Interop Server Pool**.</span></span> 
    
2. <span data-ttu-id="3eb67-108">這會開啟 [ **建立新的視頻 Interop 伺服器集** 區] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="3eb67-108">This will open up a **Create a new Video Interop Server Pool** wizard.</span></span> <span data-ttu-id="3eb67-109">提供新的視頻 Interop 伺服器的集區 FQDN，然後選取 [ **此集區擁有一個伺服器** ] 或 [ **此集區擁有多部伺服器** （根據您的需求）]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3eb67-109">Provide the Pool FQDN for the new Video Interop Server and select either **This pool has one server** or **This pool has multiple servers** based on your requirement, then press **Next**.</span></span>
    
    <span data-ttu-id="3eb67-110">如果您想要部署 Video Interop 伺服器集區以提供高可用性，請選取 [ **此集區擁有多部伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="3eb67-110">If you want to deploy a Video Interop Server pool to provide high availability, select **This pool has multiple servers**.</span></span> <span data-ttu-id="3eb67-111">使用此選項時，請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="3eb67-111">Keep in mind with this option that:</span></span> 
    
    - <span data-ttu-id="3eb67-112">您必須部署 DNS 負載平衡以支援視頻 Interop 伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="3eb67-112">You must deploy DNS load balancing to support Video Interop Server pools.</span></span> 
    
   - <span data-ttu-id="3eb67-113">在下一個頁面上，針對 [ **定義此集區中的電腦** ] 專案中，將集區中每一部伺服器的 **電腦 FQDN** 輸入文字欄位，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="3eb67-113">On the next page, for the **Define the computers in this pool** item, enter the **Computer FQDN** of each server in the pool into the text field, and then click **Add**.</span></span> <span data-ttu-id="3eb67-114">重複此步驟，將另一個視頻 Interop 伺服器新增至集區。</span><span class="sxs-lookup"><span data-stu-id="3eb67-114">Repeat this step to add another Video Interop Server to the pool.</span></span> <span data-ttu-id="3eb67-115">定義集區中的所有電腦後，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3eb67-115">When you have defined all the computers in the pool, press **Next**.</span></span>
    
     <span data-ttu-id="3eb67-116">如果您只想要在集區中部署一個視頻 Interop 伺服器，因為您不需要高可用性，請選取 [ **此集區擁有一部伺服器** ]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3eb67-116">If you want to deploy only one Video Interop Server in the pool because you do not require high availability, then select **This pool has one server** and press **Next**.</span></span>
    
3. <span data-ttu-id="3eb67-117">從下拉式清單中選取 [下一個躍點集區/FE]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3eb67-117">Select the next hop pool/FE from the drop-down list and press **Next**.</span></span>
    
4. <span data-ttu-id="3eb67-118">選取要與 VIS 建立關聯的 Edge 集區，然後按下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="3eb67-118">Select an Edge Pool to associate with the VIS and press **Finish**.</span></span>
    
5. <span data-ttu-id="3eb67-119">設定 TCP 或 TLS 埠。</span><span class="sxs-lookup"><span data-stu-id="3eb67-119">Set a TCP or TLS port.</span></span>
    
    <span data-ttu-id="3eb67-120">從拓撲產生器的左窗格中選取新加入的視頻 Interop 伺服器，以滑鼠右鍵按一下，然後選擇 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="3eb67-120">Select the newly added Video Interop Server from the left pane of Topology Builder, right click it and choose **Edit Properties**.</span></span> <span data-ttu-id="3eb67-121">根據您的需求啟用或更新 TCP 或 TLS 埠，然後選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3eb67-121">Enable or Update the TCP or TLS port per your requirement and choose **OK**.</span></span> <span data-ttu-id="3eb67-122">雖然新增了預設 TLS，但只有 TCP 已透過 Cisco 整合通訊管理員 (CallManager 或 CUCM) 進行完整測試。</span><span class="sxs-lookup"><span data-stu-id="3eb67-122">Although by default TLS is added, only TCP has been fully tested with Cisco Unified Communications Manager (CallManager, or CUCM).</span></span>
    
6. <span data-ttu-id="3eb67-123">新增影片閘道。</span><span class="sxs-lookup"><span data-stu-id="3eb67-123">Add a video gateway.</span></span> <span data-ttu-id="3eb67-124">若要執行此動作，請展開 [共用元件]，以滑鼠右鍵按一下 [**影片閘道**]，然後選取 [**新增 vcd**</span><span class="sxs-lookup"><span data-stu-id="3eb67-124">To do this, Expand Shared Components, right click on **Video Gateways** and select **New Video Gateway**.</span></span>
    
7. <span data-ttu-id="3eb67-125">提供視頻閘道 FQDN 或 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3eb67-125">Provide the video gateway FQDN or IP address.</span></span> <span data-ttu-id="3eb67-126">影片閘道可能位於子域或不同的網域中。</span><span class="sxs-lookup"><span data-stu-id="3eb67-126">The video gateway could be in a subdomain or a different domain.</span></span> <span data-ttu-id="3eb67-127">您系統的 VTCs 所使用的 CUCM 會用作影片閘道。</span><span class="sxs-lookup"><span data-stu-id="3eb67-127">The CUCM used by your system's VTCs serves as a video gateway.</span></span>
    
8. <span data-ttu-id="3eb67-128">視需要選取 [IPv4] 或 [IPv6]。</span><span class="sxs-lookup"><span data-stu-id="3eb67-128">Select either IPv4 or IPv6 as appropriate.</span></span> <span data-ttu-id="3eb67-129">您可以使用所有設定的 IP 位址，或將服務使用方式限制為選取的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3eb67-129">You can use all configured IP addresses or limit service usage to selected IP addresses.</span></span>
    
9. <span data-ttu-id="3eb67-130">選取視頻閘道的聆聽埠。</span><span class="sxs-lookup"><span data-stu-id="3eb67-130">Select the listening port of the video gateway.</span></span> <span data-ttu-id="3eb67-131">選取傳輸通訊協定 (TCP 或 TLS) ，並將其與設定為影片 SIP 主幹的視頻 Interop 伺服器建立關聯。</span><span class="sxs-lookup"><span data-stu-id="3eb67-131">Select the Transport protocol (TCP or TLS) and associate it with a Video Interop Server which is set up for a video SIP trunk.</span></span> <span data-ttu-id="3eb67-132">視頻閘道的傳輸通訊協定應符合為 VIS 設定的傳輸通訊協定。</span><span class="sxs-lookup"><span data-stu-id="3eb67-132">The Transport Protocol for the video gateway should match the Transport Protocol configured for the VIS.</span></span>
    
10. <span data-ttu-id="3eb67-133">在上述步驟完成之後，會新增相對應的 SIP 影片主幹。</span><span class="sxs-lookup"><span data-stu-id="3eb67-133">A corresponding SIP Video trunk is added after the above step is completed.</span></span> <span data-ttu-id="3eb67-134">以滑鼠右鍵按一下 SIP 影片主幹，然後選取剛新增的主幹。</span><span class="sxs-lookup"><span data-stu-id="3eb67-134">Right click on the SIP Video Trunk, and select the trunk that was just added.</span></span> <span data-ttu-id="3eb67-135">影片的 SIP 主幹名稱、關聯的視頻 Interop 伺服器、SIP 傳輸通訊協定和埠均可全部變更。</span><span class="sxs-lookup"><span data-stu-id="3eb67-135">The video SIP Trunk name, associated Video Interop Server, SIP Transport protocol and port can all be changed.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="3eb67-136">影片 Interop 伺服器支援1： N 主幹。</span><span class="sxs-lookup"><span data-stu-id="3eb67-136">A Video Interop Server supports 1:N trunks.</span></span> <span data-ttu-id="3eb67-137">因此可以新增多個主幹，這與單一的視頻 Interop 伺服器相關聯，每個主幹會在不同的視頻閘道上終止。</span><span class="sxs-lookup"><span data-stu-id="3eb67-137">Hence multiple trunks can be added, which are associated with a single Video Interop Server, where each trunk terminates on a different Video Gateway.</span></span> <span data-ttu-id="3eb67-138">其限制是，特定的視頻閘道具有一個且只能定義為商務用 Skype 伺服器部署的一個主幹。</span><span class="sxs-lookup"><span data-stu-id="3eb67-138">The limitation is that a particular Video Gateway has one and only one trunk that can be defined to the Skype for Business Server deployment.</span></span>
  
11. <span data-ttu-id="3eb67-139">依照在 [商務用 Skype Server 2015 中建立及發行新拓撲](../../deploy/install/create-and-publish-new-topology.md)中所述的方式，發佈拓撲檔。</span><span class="sxs-lookup"><span data-stu-id="3eb67-139">Publish the Topology Document as described in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3eb67-140">若要改善復原能力，您可能想要設定第二個視頻 Interop 伺服器或 VIS 集區，或是備份前端集區。</span><span class="sxs-lookup"><span data-stu-id="3eb67-140">To improve resiliency, you may want to configure a second Video Interop Server or VIS pool, or a backup Front End pool.</span></span> <span data-ttu-id="3eb67-141">如需詳細資訊，請參閱 [恢復機制](../../plan-your-deployment/video-interop-server.md#resiliency) 。</span><span class="sxs-lookup"><span data-stu-id="3eb67-141">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
<span data-ttu-id="3eb67-142">現在，使用拓撲產生器執行的所有工作都是完整的。</span><span class="sxs-lookup"><span data-stu-id="3eb67-142">All tasks performed using Topology Builder should now be complete.</span></span> <span data-ttu-id="3eb67-143">繼續在新的 VIS 伺服器或伺服器上安裝軟體。</span><span class="sxs-lookup"><span data-stu-id="3eb67-143">Proceed to installing the software on the new VIS server or servers.</span></span>
## <a name="see-also"></a><span data-ttu-id="3eb67-144">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3eb67-144">See also</span></span>

[<span data-ttu-id="3eb67-145">在商務用 Skype Server 中部署 VIS 伺服器角色</span><span class="sxs-lookup"><span data-stu-id="3eb67-145">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)

[<span data-ttu-id="3eb67-146">在商務用 Skype Server 中規劃影片 Interop 伺服器</span><span class="sxs-lookup"><span data-stu-id="3eb67-146">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  
[<span data-ttu-id="3eb67-147">在商務用 Skype Server 2015 中建立及發行新的拓撲</span><span class="sxs-lookup"><span data-stu-id="3eb67-147">Create and publish new topology in Skype for Business Server 2015</span></span>](../../deploy/install/create-and-publish-new-topology.md)
