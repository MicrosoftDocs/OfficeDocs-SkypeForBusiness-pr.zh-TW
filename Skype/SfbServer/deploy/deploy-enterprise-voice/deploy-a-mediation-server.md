---
title: 在商務用 Skype Server 中的拓撲產生器中部署轉送伺服器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
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
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 摘要：瞭解如何在商務用 Skype Server 的拓撲產生器中定義及部署轉送伺服器。
ms.openlocfilehash: b74819d7e68f76392beaa89427b3cf76f24b82d9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836913"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="4a0d6-103">在商務用 Skype Server 中的拓撲產生器中部署轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="4a0d6-103">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="4a0d6-104">**摘要：** 瞭解如何在商務用 Skype Server 的拓撲產生器中定義及部署轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-104">**Summary:** Learn how to define and deploy a Mediation Server in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="4a0d6-105">「企業語音工作負載」、電話撥入式會議和高級 Enterprise Voice 應用程式 (回應群組應用程式、通話駐留應用程式、通話許可控制 (CAC) ) 等）都可用於前端集區。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-105">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="4a0d6-106">轉送伺服器的功能已內置於前端伺服器中。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-106">The functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="4a0d6-107">不需要個別的獨立轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-107">A separate stand-alone Mediation Server is not necessary.</span></span> 
  
<span data-ttu-id="4a0d6-108">唯一例外情況是設定 SIP 主幹以連接至網際網路電話語音服務提供者的會話邊界控制器。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="4a0d6-109">若要將您的企業語音基礎結構連線至 SIP 主幹提供者，則必須部署個別的轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>
  
<span data-ttu-id="4a0d6-110">[商務用 Skype 伺服器之間的連線] (前端集區或獨立中繼) 伺服器上的轉送伺服器組合，以及將閘道定義為稱為主幹的邏輯關聯。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-110">The connection between Skype for Business Server (either a Mediation Server collocated on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a trunk.</span></span> <span data-ttu-id="4a0d6-111">本節中的主題說明如何定義主幹及如何在連接至 SIP 主幹時，部署獨立的轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>
  
## <a name="define-a-mediation-server-in-topology-builder"></a><span data-ttu-id="4a0d6-112">在拓撲產生器中定義中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="4a0d6-112">Define a Mediation Server in Topology Builder</span></span>

<span data-ttu-id="4a0d6-113">您可以在前端集區上新增轉送伺服器做為組合角色，或定義個別獨立的轉送伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-113">You can add Mediation Server as a collocated role on a Front End pool, or define a separate standalone Mediation Server pool.</span></span>
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="4a0d6-114">若要將轉送伺服器新增至前端集區</span><span class="sxs-lookup"><span data-stu-id="4a0d6-114">To add a Mediation Server to a Front End pool</span></span>

1. <span data-ttu-id="4a0d6-115">啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype server 2015**]，然後按一下 [ **商務用 skype server 2015Topology** 建立器]。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="4a0d6-116">在 [拓撲產生器] 的主控台樹中，展開您要定義前端集區的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-116">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>
    
3. <span data-ttu-id="4a0d6-117">在主控台樹中，以滑鼠右鍵按一下您想要的前端集區類型，然後按一下 [ **新增前端集** 區]。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-117">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>
    
4. <span data-ttu-id="4a0d6-118">完整瀏覽 [定義新前端集區] 精靈，直到到達 [選取組合的伺服器角色] 頁面為止。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-118">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>
    
5. <span data-ttu-id="4a0d6-119">在 [ **選取組合伺服器角色**] 中，選取 [ **組合轉送伺服器**] 選項。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-119">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4a0d6-120">如果您選取的前端集區類型是 Enterprise Edition，則轉送伺服器元件將會安裝在該前端集區的所有前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-120">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="4a0d6-121">轉送伺服器所使用的 **下一個躍點集** 區將是轉送伺服器組合所在的前端集區。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-121">The **Next hop pool** used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="4a0d6-122">轉送伺服器所使用的 **edge 集** 區將是與組合轉送伺服器的前端集區相關聯的相同 edge 集區。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-122">The **Edge pool** used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span>
  
6. <span data-ttu-id="4a0d6-123">按一下 [ **成為預設** ]，使用此前端集區，將通話路由傳送至 PSTN。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-123">Click **Make Default** to use this Front End pool to route calls to the PSTN.</span></span>
    
7. <span data-ttu-id="4a0d6-124">完成將一或多個對等專案關聯至前端集區時，按一下 **[完成]** 。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-124">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4a0d6-125">在繼續進行企業語音部署程式的下一個步驟之前，請確定轉送伺服器集區 (（即「轉送伺服器元件」組合) 的前端集區）是使用您指定的 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-125">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span> 
  
8. <span data-ttu-id="4a0d6-126">在 **商務用 Skype Server 2015** 節點上按一下滑鼠右鍵，然後按一下 [ **發行拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-126">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
### <a name="to-add-a-standalone-mediation-server"></a><span data-ttu-id="4a0d6-127">新增獨立的轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="4a0d6-127">To add a standalone Mediation Server</span></span>

1. <span data-ttu-id="4a0d6-128">啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype server 2015**]，然後按一下 [ **商務用 skype server 2015Topology** 建立器]。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-128">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="4a0d6-129">在 [拓撲產生器] 的主控台樹中，展開您要定義轉送伺服器的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-129">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>
    
3. <span data-ttu-id="4a0d6-130">在主控台樹中，以滑鼠右鍵按一下 **[中繼** 集區] 節點，然後按一下 [ **轉送伺服器集** 區]。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-130">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>
    
4. <span data-ttu-id="4a0d6-131">在 [ **定義新** 的中繼集區] 中，輸入轉送伺服器集區的完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-131">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>
    
5. <span data-ttu-id="4a0d6-132">接著執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="4a0d6-132">Next, do one of the following:</span></span>
    
   - <span data-ttu-id="4a0d6-133">如果您想要在集區中部署多個轉送伺服器以提供高可用性，請選取 [ **多部電腦集** 區]。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-133">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="4a0d6-134">您必須 [部署](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) 以支援具有多部轉送伺服器的轉送伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-134">You must [deploy](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) to support Mediation Server pools that have multiple Mediation Servers.</span></span>
  
   - <span data-ttu-id="4a0d6-135">如果您只想要在集區中部署一個轉送伺服器，因為您不需要高可用性，請選取 [ **單一電腦集** 區]。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="4a0d6-136">略過下列步驟。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-136">Skip the following step.</span></span>
    
6. <span data-ttu-id="4a0d6-137">如果您在上一個步驟中，在 [定義此集區中的電腦] 項目上選取了 [多部電腦集區]，則可按一下 [電腦 FQDN]、鍵入集區中每一部伺服器的 FQDN，然後按一下 [新增]。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="4a0d6-138">針對您要新增至集區的所有其他轉送伺服器重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="4a0d6-139">在定義集區中的所有電腦之後，按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-139">When you have defined all the computers in the pool, click **Next**.</span></span>
    
7. <span data-ttu-id="4a0d6-140">在 [ **選取下一個躍點]** 頁面上，按一下 **[下一個躍點集區]**，然後按一下將使用此轉送伺服器集區的前端集區 FQDN，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>
    
8. <span data-ttu-id="4a0d6-141">在 **[選取 Edge Server]** 頁面上，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="4a0d6-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
   - <span data-ttu-id="4a0d6-142">如果您想要為已啟用 Enterprise Voice 的外部使用者提供 PSTN 連線，請在 [ **選取此轉送伺服器使用的 Edge 集** 區] 下，按一下將使用此轉送伺服器集區的 edge Server 集區 FQDN，以提供 PSTN 連線到這些外部使用者，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
   - <span data-ttu-id="4a0d6-143">如果您不打算為外部使用者啟用 Enterprise Voice，或是不想要在內部網路以外為使用者提供 PSTN 連線能力，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>
    
9. <span data-ttu-id="4a0d6-144">在 **商務用 Skype Server 2015** 節點上按一下滑鼠右鍵，然後按一下 [ **發行拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-144">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="4a0d6-145">定義轉送伺服器聆聽埠</span><span class="sxs-lookup"><span data-stu-id="4a0d6-145">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="4a0d6-146">遵循此主題中的步驟，使用拓撲產生器定義轉送伺服器或集區將接受來自閘道對等的傳入連線的聆聽埠。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-146">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>
  
### <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="4a0d6-147">修改轉送伺服器的聆聽埠</span><span class="sxs-lookup"><span data-stu-id="4a0d6-147">To Modify the Mediation Server Listening Ports</span></span>

1. <span data-ttu-id="4a0d6-148">啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype server 2015**]，然後按一下 [ **商務用 skype server 2015Topology** 建立器]。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-148">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="4a0d6-149">在 [拓撲產生器] 的主控台樹中，展開 [中繼集區 **] 節點，** 然後以滑鼠右鍵按一下先前建立的轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-149">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>
    
3. <span data-ttu-id="4a0d6-150">根據預設，轉送伺服器上的 SIP 聆聽埠為從商務用 Skype Server 中的 TLS 流量5070，而5067用於來自對等 (的 TLS 流量，例如閘道、PBXes 或 SBCs) 。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-150">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Skype for Business Server, and 5067 for TLS traffic from peers (such as gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="4a0d6-151">TCP 連接埠預設是停用的。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-151">TCP port is disabled by default.</span></span> <span data-ttu-id="4a0d6-152">如果您的閘道不支援 TLS，則必須啟用 TCP 連接埠。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-152">You must enable TCP port if you have gateways that do not support TLS.</span></span>
    
4. <span data-ttu-id="4a0d6-153">指定所需的 TLS 或 TCP 接聽埠範圍，轉送伺服器將接受來自 PSTN 閘道的傳入連線。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-153">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4a0d6-154">若未勾選 [啟用 TCP 連接埠]，則不一定要輸入 TCP 連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-154">Entering a TCP port range is not required if **Enable TCP port** is not checked.</span></span> <span data-ttu-id="4a0d6-155">此為選用設定。</span><span class="sxs-lookup"><span data-stu-id="4a0d6-155">This setting is optional.</span></span>
  

