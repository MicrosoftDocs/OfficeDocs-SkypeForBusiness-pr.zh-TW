---
title: 在商務用 Skype Server 的 [拓撲產生器] 中部署轉送伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: '摘要: 瞭解如何在商務用 Skype Server 的 [拓撲建立器] 中定義及部署中繼伺服器。'
ms.openlocfilehash: 23d1567816c56408b276672fdd0330b0aa3d635c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245811"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="773c7-103">在商務用 Skype Server 的 [拓撲產生器] 中部署轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="773c7-103">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="773c7-104">**摘要:** 瞭解如何在商務用 Skype Server 的 [拓撲建立器] 中定義及部署中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="773c7-104">**Summary:** Learn how to define and deploy a Mediation Server in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="773c7-105">[企業語音工作]、[電話撥入式會議] 和 [高級企業語音應用程式] (回應群組應用程式、通話駐留應用程式、通話許可控制 (CAC) 等) 都可在前端池中使用。</span><span class="sxs-lookup"><span data-stu-id="773c7-105">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="773c7-106">轉送伺服器的功能是內嵌在前端伺服器中。</span><span class="sxs-lookup"><span data-stu-id="773c7-106">The functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="773c7-107">不需要個別獨立的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="773c7-107">A separate stand-alone Mediation Server is not necessary.</span></span> 
  
<span data-ttu-id="773c7-108">唯一的例外是如果您將 SIP 主幹設定為連線至網際網路電話服務提供者的會話框線控制器。</span><span class="sxs-lookup"><span data-stu-id="773c7-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="773c7-109">若要將企業語音結構連線至 SIP 中繼提供者, 必須部署個別的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="773c7-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>
  
<span data-ttu-id="773c7-110">商務用 Skype 伺服器 (在前端池或獨立的中繼伺服器上的中繼伺服器 collocated) 和閘道之間的連線是指稱為主幹的邏輯關聯。</span><span class="sxs-lookup"><span data-stu-id="773c7-110">The connection between Skype for Business Server (either a Mediation Server collocated on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a trunk.</span></span> <span data-ttu-id="773c7-111">本節中的主題描述如何定義主幹, 以及如果您連線到 SIP 主幹, 如何部署獨立的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="773c7-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>
  
## <a name="define-a-mediation-server-in-topology-builder"></a><span data-ttu-id="773c7-112">在拓撲建立器中定義中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="773c7-112">Define a Mediation Server in Topology Builder</span></span>

<span data-ttu-id="773c7-113">您可以將轉送伺服器新增為前端池的 collocated 角色, 或定義獨立的獨立轉送伺服器池。</span><span class="sxs-lookup"><span data-stu-id="773c7-113">You can add Mediation Server as a collocated role on a Front End pool, or define a separate standalone Mediation Server pool.</span></span>
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="773c7-114">將中繼伺服器新增到前端池</span><span class="sxs-lookup"><span data-stu-id="773c7-114">To add a Mediation Server to a Front End pool</span></span>

1. <span data-ttu-id="773c7-115">啟動拓撲產生器: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype server 2015**], 然後按一下 [**商務用 skype server 2015Topology**建立器]。</span><span class="sxs-lookup"><span data-stu-id="773c7-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="773c7-116">在拓撲建立器中, 在主控台樹狀結構中, 展開您要為其定義前端池的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="773c7-116">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>
    
3. <span data-ttu-id="773c7-117">在主控台樹狀結構中, 以滑鼠右鍵按一下您想要的前端池類型, 然後按一下 [**新增前端池 ...**]。</span><span class="sxs-lookup"><span data-stu-id="773c7-117">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>
    
4. <span data-ttu-id="773c7-118">流覽 [**定義新的前臺端池**] 嚮導, 直到您到達 [**選取 collocated 伺服器角色**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="773c7-118">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>
    
5. <span data-ttu-id="773c7-119">在 [**選取 collocated 伺服器角色**] 中, 核取 [ **Collocate 中繼伺服器**] 的選項。</span><span class="sxs-lookup"><span data-stu-id="773c7-119">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="773c7-120">如果您選取的 [前端] 池類型是 [企業版], 則會將轉送伺服器元件安裝在該前端池的所有前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="773c7-120">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="773c7-121">中繼伺服器所使用的**下一個躍點池**將是中繼伺服器正在 Collocated 的前端池。</span><span class="sxs-lookup"><span data-stu-id="773c7-121">The **Next hop pool** used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="773c7-122">中繼伺服器所使用的**邊緣池**將是與中繼伺服器所 Collocated 之前端池相關聯的同一個 edge 池。</span><span class="sxs-lookup"><span data-stu-id="773c7-122">The **Edge pool** used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span>
  
6. <span data-ttu-id="773c7-123">按一下 [**設為預設值**], 使用這個前端池來路由來電至 PSTN。</span><span class="sxs-lookup"><span data-stu-id="773c7-123">Click **Make Default** to use this Front End pool to route calls to the PSTN.</span></span>
    
7. <span data-ttu-id="773c7-124">當您完成將一或多個對等專案關聯到前端池之後, 按一下 **[完成]** 。</span><span class="sxs-lookup"><span data-stu-id="773c7-124">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="773c7-125">在您繼續進行企業語音部署程式中的下一個步驟之前, 請確認已將中繼伺服器池 (例如, 擁有中繼伺服器元件 collocated 的前臺端池) 使用您所指定的 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="773c7-125">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span> 
  
8. <span data-ttu-id="773c7-126">以滑鼠右鍵按一下**商務用 Skype Server 2015**節點, 然後按一下 [**發佈拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="773c7-126">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
### <a name="to-add-a-standalone-mediation-server"></a><span data-ttu-id="773c7-127">新增獨立的轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="773c7-127">To add a standalone Mediation Server</span></span>

1. <span data-ttu-id="773c7-128">啟動拓撲產生器: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype server 2015**], 然後按一下 [**商務用 skype server 2015Topology**建立器]。</span><span class="sxs-lookup"><span data-stu-id="773c7-128">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="773c7-129">在拓撲建立器中, 在主控台樹狀結構中, 展開您要定義轉送伺服器的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="773c7-129">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>
    
3. <span data-ttu-id="773c7-130">在主控台樹中, 以滑鼠右鍵按一下 [**轉送緩衝集區**] 節點, 然後按一下 [**轉送伺服器池**]。</span><span class="sxs-lookup"><span data-stu-id="773c7-130">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>
    
4. <span data-ttu-id="773c7-131">在 [**定義新的仲介池**] 中, 輸入中繼伺服器池的完整功能變數名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="773c7-131">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>
    
5. <span data-ttu-id="773c7-132">接著, 請執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="773c7-132">Next, do one of the following:</span></span>
    
   - <span data-ttu-id="773c7-133">如果您想要在池中部署多個轉送伺服器來提供高可用性, 請選取 [**多個電腦池**]。</span><span class="sxs-lookup"><span data-stu-id="773c7-133">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="773c7-134">您必須[部署](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing), 才能支援擁有多個轉送伺服器的中繼伺服器池。</span><span class="sxs-lookup"><span data-stu-id="773c7-134">You must [deploy](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) to support Mediation Server pools that have multiple Mediation Servers.</span></span>
  
   - <span data-ttu-id="773c7-135">如果您只想在池中部署一個轉送伺服器, 因為您不需要高可用性, 請選取 [**單一電腦池**]。</span><span class="sxs-lookup"><span data-stu-id="773c7-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="773c7-136">略過下列步驟。</span><span class="sxs-lookup"><span data-stu-id="773c7-136">Skip the following step.</span></span>
    
6. <span data-ttu-id="773c7-137">如果您在上一個步驟中選取了**多個電腦池**, 請在 [**定義此池中的電腦**] 專案中, 按一下 [**電腦 FQDN**], 輸入池中每個伺服器的 FQDN, 然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="773c7-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="773c7-138">針對您要新增至池中的所有其他轉送伺服器, 重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="773c7-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="773c7-139">在池中定義所有電腦之後, 請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="773c7-139">When you have defined all the computers in the pool, click **Next**.</span></span>
    
7. <span data-ttu-id="773c7-140">在 [**選取下一個躍點]** 頁面上, 按一下 **[下一個躍點池]**, 然後按一下將使用此中繼伺服器池的前端池 FQDN, 然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="773c7-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>
    
8. <span data-ttu-id="773c7-141">在 [**選取邊緣伺服器**] 頁面上, 執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="773c7-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
   - <span data-ttu-id="773c7-142">如果您想要將 PSTN 連線提供給已啟用企業語音的外部使用者, 請在 [**選取此中繼伺服器所使用的 Edge 池**] 底下, 按一下將使用此轉送服務伺服器池的 edge 伺服器池 FQDN, 以提供 pstn 連線至這些外部使用者, 然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="773c7-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
   - <span data-ttu-id="773c7-143">如果您不打算為企業語音啟用外部使用者, 或者如果您不想在內部網路外部向使用者提供 PSTN 連線, 請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="773c7-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>
    
9. <span data-ttu-id="773c7-144">以滑鼠右鍵按一下**商務用 Skype Server 2015**節點, 然後按一下 [**發佈拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="773c7-144">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="773c7-145">定義中繼伺服器偵聽埠</span><span class="sxs-lookup"><span data-stu-id="773c7-145">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="773c7-146">請依照本主題中的步驟, 使用拓撲建立器定義中繼伺服器或池將接受來自閘道對等傳入連線的偵聽埠。</span><span class="sxs-lookup"><span data-stu-id="773c7-146">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>
  
### <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="773c7-147">修改中繼伺服器偵聽埠</span><span class="sxs-lookup"><span data-stu-id="773c7-147">To Modify the Mediation Server Listening Ports</span></span>

1. <span data-ttu-id="773c7-148">啟動拓撲產生器: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype server 2015**], 然後按一下 [**商務用 skype server 2015Topology**建立器]。</span><span class="sxs-lookup"><span data-stu-id="773c7-148">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="773c7-149">在 [拓撲建立器] 中, 展開 [**轉送緩衝集區**] 節點, 然後以滑鼠右鍵按一下先前建立的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="773c7-149">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>
    
3. <span data-ttu-id="773c7-150">根據預設, 中繼伺服器上的 SIP 偵聽埠為從商務用 Skype Server 提供 TLS 流量的 5070, 而5067則是來自對等 (例如閘道、PBXes 或 SBCs) 的 TLS 流量。</span><span class="sxs-lookup"><span data-stu-id="773c7-150">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Skype for Business Server, and 5067 for TLS traffic from peers (such as gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="773c7-151">TCP 埠預設為停用。</span><span class="sxs-lookup"><span data-stu-id="773c7-151">TCP port is disabled by default.</span></span> <span data-ttu-id="773c7-152">如果您的閘道不支援 TLS, 您就必須啟用 TCP 埠。</span><span class="sxs-lookup"><span data-stu-id="773c7-152">You must enable TCP port if you have gateways that do not support TLS.</span></span>
    
4. <span data-ttu-id="773c7-153">指定所需的 TLS 或 TCP 偵聽埠範圍, 中繼伺服器將接受 PSTN 閘道的傳入連線。</span><span class="sxs-lookup"><span data-stu-id="773c7-153">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="773c7-154">如果沒有核取 [**啟用 tcp 埠**], 則不需要輸入 tcp 埠範圍。</span><span class="sxs-lookup"><span data-stu-id="773c7-154">Entering a TCP port range is not required if **Enable TCP port** is not checked.</span></span> <span data-ttu-id="773c7-155">此設定是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="773c7-155">This setting is optional.</span></span>
  

