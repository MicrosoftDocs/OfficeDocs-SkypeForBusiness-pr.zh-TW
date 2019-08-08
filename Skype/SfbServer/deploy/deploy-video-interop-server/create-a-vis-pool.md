---
title: 在商務用 Skype Server 中建立 VIS 池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: '摘要: 使用拓撲產生器在商務用 Skype 伺服器中建立視頻互通性伺服器池。'
ms.openlocfilehash: dc97fde4447778be20cb60d86cddac65b663c321
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235659"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a><span data-ttu-id="d27ed-103">在商務用 Skype Server 中建立 VIS 池</span><span class="sxs-lookup"><span data-stu-id="d27ed-103">Create a VIS pool in Skype for Business Server</span></span>
 
<span data-ttu-id="d27ed-104">**摘要:** 在商務用 Skype Server 中使用 [拓撲建立器] 建立視頻互通性伺服器池。</span><span class="sxs-lookup"><span data-stu-id="d27ed-104">**Summary:** Create a Video Interop Server pool in Skype for Business Server using Topology Builder.</span></span>
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a><span data-ttu-id="d27ed-105">使用拓撲產生器建立 VIS 或 VIS 池</span><span class="sxs-lookup"><span data-stu-id="d27ed-105">Create a VIS or VIS pool using Topology Builder</span></span>

1. <span data-ttu-id="d27ed-106">在前端伺服器上開啟拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="d27ed-106">Open Topology Builder on the front end server.</span></span> <span data-ttu-id="d27ed-107">從 [拓撲建立器] 的左窗格中, 以滑鼠右鍵按一下 [**影片互通性伺服器池**], 然後選擇 [**新增視頻互通性伺服器**</span><span class="sxs-lookup"><span data-stu-id="d27ed-107">From the left pane of Topology Builder, right click on **Video Interop Server Pools** and choose **New Video Interop Server Pool**.</span></span> 
    
2. <span data-ttu-id="d27ed-108">這將會開啟 [**建立新的視頻互通性伺服器池**] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="d27ed-108">This will open up a **Create a new Video Interop Server Pool** wizard.</span></span> <span data-ttu-id="d27ed-109">為新的視頻交互操作伺服器提供 [池 FQDN], 然後選取 [**此池擁有一個伺服器**] 或 [**此池中有多個伺服器**(根據您的需求)], 然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d27ed-109">Provide the Pool FQDN for the new Video Interop Server and select either **This pool has one server** or **This pool has multiple servers** based on your requirement, then press **Next**.</span></span>
    
    <span data-ttu-id="d27ed-110">如果您想要部署視頻互通性伺服器池來提供高可用性, 請選取 [**此池子擁有多個伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="d27ed-110">If you want to deploy a Video Interop Server pool to provide high availability, select **This pool has multiple servers**.</span></span> <span data-ttu-id="d27ed-111">請記住, 這個選項如下:</span><span class="sxs-lookup"><span data-stu-id="d27ed-111">Keep in mind with this option that:</span></span> 
    
    - <span data-ttu-id="d27ed-112">您必須部署 DNS 負載平衡, 以支援視頻互通性伺服器池。</span><span class="sxs-lookup"><span data-stu-id="d27ed-112">You must deploy DNS load balancing to support Video Interop Server pools.</span></span> 
    
   - <span data-ttu-id="d27ed-113">在下一頁的 [**定義此 pool 中的電腦**] 專案中, 將池中每個伺服器的**電腦 FQDN**輸入至 [文字] 欄位, 然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="d27ed-113">On the next page, for the **Define the computers in this pool** item, enter the **Computer FQDN** of each server in the pool into the text field, and then click **Add**.</span></span> <span data-ttu-id="d27ed-114">重複此步驟, 將另一個影片交互操作伺服器新增至該資源庫。</span><span class="sxs-lookup"><span data-stu-id="d27ed-114">Repeat this step to add another Video Interop Server to the pool.</span></span> <span data-ttu-id="d27ed-115">在池中定義所有電腦之後, 請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d27ed-115">When you have defined all the computers in the pool, press **Next**.</span></span>
    
     <span data-ttu-id="d27ed-116">如果您只想在池中部署一個視頻交互操作伺服器, 因為您不需要高可用性, 請選取 [**此池有一個伺服器**], 然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d27ed-116">If you want to deploy only one Video Interop Server in the pool because you do not require high availability, then select **This pool has one server** and press **Next**.</span></span>
    
3. <span data-ttu-id="d27ed-117">從下拉式清單中選取下一個躍點池子/FE, 然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d27ed-117">Select the next hop pool/FE from the drop-down list and press **Next**.</span></span>
    
4. <span data-ttu-id="d27ed-118">選取要與 VIS 建立關聯的邊緣池, 然後按下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="d27ed-118">Select an Edge Pool to associate with the VIS and press **Finish**.</span></span>
    
5. <span data-ttu-id="d27ed-119">設定 TCP 或 TLS 埠。</span><span class="sxs-lookup"><span data-stu-id="d27ed-119">Set a TCP or TLS port.</span></span>
    
    <span data-ttu-id="d27ed-120">從 [拓撲建立器] 的左窗格選取 [新增的視頻互通性伺服器], 以滑鼠右鍵按一下它, 然後選擇 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="d27ed-120">Select the newly added Video Interop Server from the left pane of Topology Builder, right click it and choose **Edit Properties**.</span></span> <span data-ttu-id="d27ed-121">根據您的需求啟用或更新 TCP 或 TLS 埠, 然後選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d27ed-121">Enable or Update the TCP or TLS port per your requirement and choose **OK**.</span></span> <span data-ttu-id="d27ed-122">雖然已新增預設的 TLS, 但只有 TCP 經過 Cisco 整合通訊管理員 (CallManager 或 CUCM) 才能完全測試。</span><span class="sxs-lookup"><span data-stu-id="d27ed-122">Although by default TLS is added, only TCP has been fully tested with Cisco Unified Communications Manager (CallManager, or CUCM).</span></span>
    
6. <span data-ttu-id="d27ed-123">新增視頻閘道。</span><span class="sxs-lookup"><span data-stu-id="d27ed-123">Add a video gateway.</span></span> <span data-ttu-id="d27ed-124">若要這樣做, 請展開 [共用元件], 以滑鼠右鍵按一下 [**視頻閘道**], 然後選取 [**新增視頻**</span><span class="sxs-lookup"><span data-stu-id="d27ed-124">To do this, Expand Shared Components, right click on **Video Gateways** and select **New Video Gateway**.</span></span>
    
7. <span data-ttu-id="d27ed-125">提供 [視頻閘道 FQDN] 或 [IP 位址]。</span><span class="sxs-lookup"><span data-stu-id="d27ed-125">Provide the video gateway FQDN or IP address.</span></span> <span data-ttu-id="d27ed-126">[視頻閘道] 可能位於子域或其他網域中。</span><span class="sxs-lookup"><span data-stu-id="d27ed-126">The video gateway could be in a subdomain or a different domain.</span></span> <span data-ttu-id="d27ed-127">您系統的 VTCs 所使用的 CUCM 會做為視頻閘道。</span><span class="sxs-lookup"><span data-stu-id="d27ed-127">The CUCM used by your system's VTCs serves as a video gateway.</span></span>
    
8. <span data-ttu-id="d27ed-128">視需要選取 [IPv4] 或 [IPv6]。</span><span class="sxs-lookup"><span data-stu-id="d27ed-128">Select either IPv4 or IPv6 as appropriate.</span></span> <span data-ttu-id="d27ed-129">您可以使用所有設定的 IP 位址, 或將服務使用限制在選取的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d27ed-129">You can use all configured IP addresses or limit service usage to selected IP addresses.</span></span>
    
9. <span data-ttu-id="d27ed-130">選取視頻閘道的偵聽埠。</span><span class="sxs-lookup"><span data-stu-id="d27ed-130">Select the listening port of the video gateway.</span></span> <span data-ttu-id="d27ed-131">選取傳輸通訊協定 (TCP 或 TLS), 並將它與針對視頻 SIP 幹線設定的視頻互通性伺服器建立關聯。</span><span class="sxs-lookup"><span data-stu-id="d27ed-131">Select the Transport protocol (TCP or TLS) and associate it with a Video Interop Server which is set up for a video SIP trunk.</span></span> <span data-ttu-id="d27ed-132">視頻閘道的傳輸通訊協定應該與為 VIS 設定的傳輸通訊協定相符。</span><span class="sxs-lookup"><span data-stu-id="d27ed-132">The Transport Protocol for the video gateway should match the Transport Protocol configured for the VIS.</span></span>
    
10. <span data-ttu-id="d27ed-133">在上述步驟完成之後, 就會新增對應的 SIP 視頻幹線。</span><span class="sxs-lookup"><span data-stu-id="d27ed-133">A corresponding SIP Video trunk is added after the above step is completed.</span></span> <span data-ttu-id="d27ed-134">以滑鼠右鍵按一下 SIP 影片幹線, 然後選取剛剛新增的主幹。</span><span class="sxs-lookup"><span data-stu-id="d27ed-134">Right click on the SIP Video Trunk, and select the trunk that was just added.</span></span> <span data-ttu-id="d27ed-135">影片的主幹名稱、相關聯的視頻互通性伺服器、SIP 傳輸通訊協定和埠都可以全部變更。</span><span class="sxs-lookup"><span data-stu-id="d27ed-135">The video SIP Trunk name, associated Video Interop Server, SIP Transport protocol and port can all be changed.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="d27ed-136">影片交互操作伺服器支援 1: N trunks。</span><span class="sxs-lookup"><span data-stu-id="d27ed-136">A Video Interop Server supports 1:N trunks.</span></span> <span data-ttu-id="d27ed-137">因此, 您可以新增多個 trunks, 與單一的視頻交互操作伺服器產生關聯, 而每個幹線則會在不同的視頻閘道上結束。</span><span class="sxs-lookup"><span data-stu-id="d27ed-137">Hence multiple trunks can be added, which are associated with a single Video Interop Server, where each trunk terminates on a different Video Gateway.</span></span> <span data-ttu-id="d27ed-138">限制是某個特定的視頻閘道有一個且只有一個主幹, 可以定義到商務用 Skype Server 部署。</span><span class="sxs-lookup"><span data-stu-id="d27ed-138">The limitation is that a particular Video Gateway has one and only one trunk that can be defined to the Skype for Business Server deployment.</span></span>
  
11. <span data-ttu-id="d27ed-139">如在[商務用 Skype Server 2015 中建立和發佈新的拓撲](../../deploy/install/create-and-publish-new-topology.md)中所述, 發佈拓撲檔。</span><span class="sxs-lookup"><span data-stu-id="d27ed-139">Publish the Topology Document as described in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d27ed-140">若要改善復原能力, 您可能會想要設定第二個視頻互通性伺服器或 VIS 池, 或備份前端池。</span><span class="sxs-lookup"><span data-stu-id="d27ed-140">To improve resiliency, you may want to configure a second Video Interop Server or VIS pool, or a backup Front End pool.</span></span> <span data-ttu-id="d27ed-141">如需詳細資訊, 請參閱[復原機制](../../plan-your-deployment/video-interop-server.md#resiliency)。</span><span class="sxs-lookup"><span data-stu-id="d27ed-141">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
<span data-ttu-id="d27ed-142">使用拓撲產生器執行的所有工作現在都應該已完成。</span><span class="sxs-lookup"><span data-stu-id="d27ed-142">All tasks performed using Topology Builder should now be complete.</span></span> <span data-ttu-id="d27ed-143">繼續在新的 VIS 伺服器或伺服器上安裝軟體。</span><span class="sxs-lookup"><span data-stu-id="d27ed-143">Proceed to installing the software on the new VIS server or servers.</span></span>
## <a name="see-also"></a><span data-ttu-id="d27ed-144">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d27ed-144">See also</span></span>

[<span data-ttu-id="d27ed-145">在商務用 Skype Server 中部署 VIS 伺服器角色</span><span class="sxs-lookup"><span data-stu-id="d27ed-145">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)

[<span data-ttu-id="d27ed-146">在商務用 Skype Server 中規劃影片互通性伺服器</span><span class="sxs-lookup"><span data-stu-id="d27ed-146">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  
[<span data-ttu-id="d27ed-147">在商務用 Skype Server 2015 中建立和發佈新的拓撲</span><span class="sxs-lookup"><span data-stu-id="d27ed-147">Create and publish new topology in Skype for Business Server 2015</span></span>](../../deploy/install/create-and-publish-new-topology.md)
