---
title: 為商務用 Skype Server 建立 Edge 拓撲
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
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5ea18841-afdc-4ccb-8d86-30584c1f5aca
description: 摘要：瞭解如何在商務用 Skype Server 中建立、發佈和匯出 Edge Server 拓撲。
ms.openlocfilehash: 8dff318b5d198eb1e8d59ef465bf648125f31327
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804393"
---
# <a name="create-your-edge-topology-for-skype-for-business-server"></a><span data-ttu-id="5c0d5-103">為商務用 Skype Server 建立 Edge 拓撲</span><span class="sxs-lookup"><span data-stu-id="5c0d5-103">Create your Edge topology for Skype for Business Server</span></span>
 
<span data-ttu-id="5c0d5-104">**摘要：** 瞭解如何在商務用 Skype Server 中建立、發佈和匯出 Edge Server 拓撲。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-104">**Summary:** Learn how to build, publish, and export your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="5c0d5-105">拓撲產生器是您用來建立 Edge Server 拓撲的工具，就如同用於商務用 Skype Server 的任何拓撲元件。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-105">Topology Builder is the tool you need to use to build your Edge Server topology, just as it's used for any topology component for Skype for Business Server.</span></span> <span data-ttu-id="5c0d5-106">在執行下列步驟之前，您必須先設定至少一個前端集區或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-106">Before following the steps below, you will need to have set up at least one Front End pool or a Standard Edition server.</span></span>
  
<span data-ttu-id="5c0d5-107">本文包含下列主題：</span><span class="sxs-lookup"><span data-stu-id="5c0d5-107">We cover the following topics in this article:</span></span>
  
- <span data-ttu-id="5c0d5-108">建立 Edge Server 拓撲</span><span class="sxs-lookup"><span data-stu-id="5c0d5-108">Build your Edge Server topology</span></span>
    
- <span data-ttu-id="5c0d5-109">發佈 Edge Server 拓撲</span><span class="sxs-lookup"><span data-stu-id="5c0d5-109">Publish your Edge Server topology</span></span>
    
- <span data-ttu-id="5c0d5-110">匯出 Edge Server 拓撲</span><span class="sxs-lookup"><span data-stu-id="5c0d5-110">Export your Edge Server topology</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="5c0d5-111">若要遵循下列步驟，您必須以下列網域群組成員的使用者身分登入下列網域伺服器：</span><span class="sxs-lookup"><span data-stu-id="5c0d5-111">To follow the steps below, you're going to need to log into the domain servers mentioned below as a user who's a member of the following domain groups:</span></span> 
  
- <span data-ttu-id="5c0d5-112">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5c0d5-112">RTCUniversalServerAdmins</span></span>
    
- <span data-ttu-id="5c0d5-113">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="5c0d5-113">Domain Admins</span></span>
    
## <a name="build-your-edge-server-topology"></a><span data-ttu-id="5c0d5-114">建立 Edge Server 拓撲</span><span class="sxs-lookup"><span data-stu-id="5c0d5-114">Build your Edge Server topology</span></span>

<span data-ttu-id="5c0d5-115">第一個部署步驟是建立您的商務用 Skype Server Edge Server 拓撲，此拓撲是由下列三個選項之一所組成：</span><span class="sxs-lookup"><span data-stu-id="5c0d5-115">The first deployment step is building your Skype for Business Server Edge Server topology, which consists of one of three options:</span></span>
  
- <span data-ttu-id="5c0d5-116">單一 Edge Server</span><span class="sxs-lookup"><span data-stu-id="5c0d5-116">A single Edge Server</span></span>
    
- <span data-ttu-id="5c0d5-117"> (一或多部伺服器上的 DNS 負載平衡 Edge 集區) </span><span class="sxs-lookup"><span data-stu-id="5c0d5-117">A DNS load balanced Edge pool (one or more servers)</span></span>
    
- <span data-ttu-id="5c0d5-118"> (一或多部伺服器的硬體負載平衡 Edge 集區) </span><span class="sxs-lookup"><span data-stu-id="5c0d5-118">A hardware load balanced Edge pool (one or more servers)</span></span>
    
<span data-ttu-id="5c0d5-119">如果您不確定需要的專案，請在開始執行下列步驟之前，請先移至規劃檔。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-119">If you aren't sure what you need, then before you start following these steps, it's a good time to go over the Planning documentation.</span></span> <span data-ttu-id="5c0d5-120">否則，讓我們開始吧。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-120">Otherwise, let's begin.</span></span>
  
### <a name="defining-the-topology-for-a-single-edge-server"></a><span data-ttu-id="5c0d5-121">定義單一 Edge Server 的拓撲</span><span class="sxs-lookup"><span data-stu-id="5c0d5-121">Defining the topology for a single Edge Server</span></span>

1. <span data-ttu-id="5c0d5-122">登入您的商務用 Skype server Standard Edition server，或商務用 Skype Server 前端集區。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-122">Log onto your Skype for Business Server Standard Edition server, or a Skype for Business Server Front End pool.</span></span>
    
2. <span data-ttu-id="5c0d5-123">一旦存在，開啟 **商務用 Skype Server 拓撲** 產生器。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-123">Once there, open **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="5c0d5-124">在主控台樹中，展開您要部署 Edge Server 的網站。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-124">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="5c0d5-125">以滑鼠右鍵按一下 [ **edge** 集區]，然後按一下 [ **新增 edge 集** 區]。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-125">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="5c0d5-126">在 [**定義新的 Edge 集** 區] 畫面上，按一下 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-126">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="5c0d5-127">在 [ **定義 edge 集區 FQDN** ] 畫面上，輸入要使用 Edge Server 的內部完整功能變數名稱 (FQDN) ，然後選取 [ **單一電腦集** 區]，完成後，按一下 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-127">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge Server is going to use, and select **Single computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="5c0d5-128">在 [ **選取功能** ] 畫面上，您可以選擇：</span><span class="sxs-lookup"><span data-stu-id="5c0d5-128">On the **Select features** screen, you have a choice:</span></span>
    
   - <span data-ttu-id="5c0d5-129">您可能想要對 SIP 存取服務、商務用 Skype Server Web 會議服務和您的 A/V Edge service 使用相同的 FQDN 和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-129">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server Web Conferencing service, and your A/V Edge service.</span></span> <span data-ttu-id="5c0d5-130">如果是的話，您必須選擇 [ **使用單一 FQDN 和 IP 位址] 核取方塊** (，並記住以下的步驟 9) </span><span class="sxs-lookup"><span data-stu-id="5c0d5-130">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
   - <span data-ttu-id="5c0d5-131">如果您打算啟用同盟，請選擇 [ **啟用此 Edge 集區的同盟 (埠 5061)** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-131">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="5c0d5-132">按一下 **[下一步]** 後，您會在 [ **IP 選項** ] 畫面上找到您自己。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-132">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen.</span></span> <span data-ttu-id="5c0d5-133">選項如下：</span><span class="sxs-lookup"><span data-stu-id="5c0d5-133">Your options are as follows:</span></span>
    
   - <span data-ttu-id="5c0d5-134">在內部介面上啟用 IPv4</span><span class="sxs-lookup"><span data-stu-id="5c0d5-134">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="5c0d5-135">在內部介面上啟用 IPv6</span><span class="sxs-lookup"><span data-stu-id="5c0d5-135">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="5c0d5-136">在外部介面上啟用 IPv4</span><span class="sxs-lookup"><span data-stu-id="5c0d5-136">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="5c0d5-137">在外部介面上啟用 IPv6</span><span class="sxs-lookup"><span data-stu-id="5c0d5-137">Enable IPv6 on the external interface</span></span>
    
   <span data-ttu-id="5c0d5-138">不管您是使用 IPv4 或 IPv6 位址，還是要在內部或外部于您的 Edge Server 上套用這些位址，這些位址都是非常明確的， (您必須記住此步驟 10) 。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-138">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 10).</span></span> <span data-ttu-id="5c0d5-139">您也可以選擇將 Edge Server 或 Edge 集區設定為使用網路位址轉譯 (NAT) 位址的外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-139">You also have the option of configuring your Edge Server or your Edge pool to use a network address translation (NAT) address for the external IP address.</span></span> <span data-ttu-id="5c0d5-140">您可以選擇 **此 Edge 集區的外部 IP 位址由 NAT 轉譯** ] 核取方塊來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-140">You can do this by choosing **The external IP address of this Edge pool is translated by NAT** check box .</span></span> <span data-ttu-id="5c0d5-141">準備好時，按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-141">Click **Next** when ready.</span></span>
    
9. <span data-ttu-id="5c0d5-142">在 [外部 Fqdn] 畫面上，您的選擇取決於您在步驟7中所做的選擇。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-142">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="5c0d5-143">如果您已勾選 [ **使用單一 FQDN 和 IP 位址** ] 核取方塊，您必須在 [ **SIP 存取** ] 方塊中輸入單一的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-143">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="5c0d5-144">接著，您必須為每個 edge service 輸入不同的埠號碼，以允許所有 edge service 彼此獨立連接。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-144">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="5c0d5-145">建議您在5061的 **SIP Access** edge service 中，使用 **Web 會議** Edge service 的444，以及 **A/V** Edge service 的443。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-145">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="5c0d5-146">完成時，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-146">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="5c0d5-147">如果您未選取 [ **使用單一 FQDN 和 IP 位址** ] 核取方塊，則您現在必須為 **SIP Access** Edge service、 **Web 會議** Edge service 和 **A/V** Edge service 輸入三個外部 fqdn。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-147">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="5c0d5-148">完成時，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-148">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="5c0d5-149">您現在已經位於 [ **定義內部 IP 位址** ] 畫面。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-149">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="5c0d5-150">在這裡，您會根據您在步驟8中所做的選擇，在 [ **內部 IPv4 位址** ] 和 [ **內部 IPv6 位址** ] 文字方塊中輸入 Edge Server 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-150">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="5c0d5-151">準備好時，按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-151">Click **Next** when ready.</span></span>
    
11. <span data-ttu-id="5c0d5-152">在 [ **定義外部 IP 位址** ] 畫面上，您可以根據您先前的選擇，使用一些選項：</span><span class="sxs-lookup"><span data-stu-id="5c0d5-152">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="5c0d5-153">您可以針對所有服務使用單一 FQDN。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-153">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="5c0d5-154">如果是的話，請輸入您的外部 IPv4 或 IPv6 位址 (您在 [ **SIP 存取** ] 文字方塊中使用) ，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-154">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="5c0d5-155">您可能已選擇為服務使用三個不同的 Fqdn 和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-155">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="5c0d5-156">如果是這種情況，請為 **SIP Access** Edge Service、 **Web 會議** Edge service 及 **A/V** Edge service 輸入您的外部 IPv4 或 IPv6 位址，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-156">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5c0d5-157">如果您先前未選擇啟用和指派 IPv6 定址，您就不會看到此對話方塊。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-157">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box.</span></span> <span data-ttu-id="5c0d5-158">這是正常的，請移至下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-158">That's normal, just go to the next step.</span></span> 
  
12. <span data-ttu-id="5c0d5-159">如果您選擇在步驟8中使用 NAT 回來，您現在會看到 [ **公用 IP 位址** ] textbox 的畫面。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-159">If you chose to use NAT back in Step 8, you'll now get a screen with a **Public IP address** textbox.</span></span> <span data-ttu-id="5c0d5-160">您必須輸入您為 A/V Edge service 設定的公用 IPv4 和/或 IPv6 位址，才能由 NAT 轉譯。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-160">You'll need to enter the public IPv4 and/or IPv6 address you've set for the A/V Edge service, to be translated by NAT.</span></span> <span data-ttu-id="5c0d5-161">然後按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-161">Then click **Next**.</span></span>
    
13. <span data-ttu-id="5c0d5-162">[下一屏向上] 是 **定義下一個躍點**。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-162">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="5c0d5-163">在 [ **下一個躍點集區]** 方塊中，選取您的內部集區名稱，其可能是前端集區或獨立集區。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-163">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="5c0d5-164">如果您的環境中有 Director，您應該選擇 Director。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-164">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="5c0d5-165">然後按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-165">Then click **Next**.</span></span>
    
14. <span data-ttu-id="5c0d5-166">在 [ **建立前端** 集區] 畫面上，您必須指定一或多個要與此 Edge Server 產生關聯的內部集區（包括前端集區和 Standard Edition 伺服器）。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-166">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition servers, to associate with this Edge Server.</span></span> <span data-ttu-id="5c0d5-167">只需選擇您要使用此 Edge Server 與支援的外部使用者進行通訊的內部集區名稱。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-167">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="5c0d5-168">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-168">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5c0d5-169">請注意，如果您的內部集區或獨立伺服器已使用不同的商務用 Skype Server Edge Server，則不能有多個關聯。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-169">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="5c0d5-170">如果您選擇的內部集區或獨立伺服器在該情況下，您將會看到警告，告知您其他 Edge Server，您可以決定是否要繼續。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-170">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="5c0d5-171">如果您要繼續進行這個新的關聯，其他 Edge Server 的連線將停止。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-171">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
15. <span data-ttu-id="5c0d5-172">按一下下一個畫面上的 **[完成]** 。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-172">Click **Finish** on the next screen.</span></span>
    
16. <span data-ttu-id="5c0d5-173">現在您將能夠發佈此更新的技術，並遵循在 [商務用 Skype server 的部署 edge](deploy-edge-servers.md) server 中的指示，從這裡部署至 Edge server。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-173">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="5c0d5-174">定義 DNS 負載平衡 Edge Server 集區的拓撲</span><span class="sxs-lookup"><span data-stu-id="5c0d5-174">Defining the topology for a DNS load balanced Edge Server pool</span></span>

1. <span data-ttu-id="5c0d5-175">登入商務用 Skype server Standard Edition server，或商務用 Skype Server 前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-175">Log onto your Skype for Business Server Standard Edition server, or a Skype for Business Server Front End Server.</span></span>
    
2. <span data-ttu-id="5c0d5-176">一旦存在，開啟 **商務用 Skype Server 拓撲** 產生器。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-176">Once there, open **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="5c0d5-177">在主控台樹中，展開您要部署 Edge Server 的網站。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-177">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="5c0d5-178">以滑鼠右鍵按一下 [ **edge** 集區]，然後按一下 [ **新增 edge 集** 區]。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-178">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="5c0d5-179">在 [**定義新的 Edge 集** 區] 畫面上，按一下 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-179">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="5c0d5-180">在 [ **定義 edge 集區 FQDN** ] 畫面上，輸入要使用 Edge 集區的內部完整功能變數名稱 (FQDN) ，然後選取 [多部 **電腦集** 區]，完成後，按一下 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-180">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge pool is going to use, and select **Multiple computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="5c0d5-181">在 [ **選取功能** ] 畫面上，您可以選擇：</span><span class="sxs-lookup"><span data-stu-id="5c0d5-181">On the **Select features** screen, you have a choice:</span></span>
    
    - <span data-ttu-id="5c0d5-182">您可能想要對 SIP 存取服務、商務用 Skype Server Web 會議服務和您的 A/V Edge service 使用相同的 FQDN 和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-182">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server Web Conferencing Service, and your A/V Edge service.</span></span> <span data-ttu-id="5c0d5-183">如果是的話，您必須選擇 [ **使用單一 FQDN 和 IP 位址] 核取方塊** (，並記住以下的步驟 9) </span><span class="sxs-lookup"><span data-stu-id="5c0d5-183">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
    - <span data-ttu-id="5c0d5-184">如果您打算啟用同盟，請選擇 [ **啟用此 Edge 集區的同盟 (埠 5061)** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-184">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="5c0d5-185">按一下 **[下一步]** 後，您會在 [ **IP 選項** ] 畫面上找到您自己。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-185">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen.</span></span> <span data-ttu-id="5c0d5-186">選項如下：</span><span class="sxs-lookup"><span data-stu-id="5c0d5-186">Your options are as follows:</span></span>
    
    - <span data-ttu-id="5c0d5-187">在內部介面上啟用 IPv4</span><span class="sxs-lookup"><span data-stu-id="5c0d5-187">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="5c0d5-188">在內部介面上啟用 IPv6</span><span class="sxs-lookup"><span data-stu-id="5c0d5-188">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="5c0d5-189">在外部介面上啟用 IPv4</span><span class="sxs-lookup"><span data-stu-id="5c0d5-189">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="5c0d5-190">在外部介面上啟用 IPv6</span><span class="sxs-lookup"><span data-stu-id="5c0d5-190">Enable IPv6 on the external interface</span></span>
    
     <span data-ttu-id="5c0d5-191">不管您是使用 IPv4 或 IPv6 位址，還是要在內部或外部于您的 Edge Server 上套用這些位址，這些位址都有很好的自我說明 (您必須記住這一點，) 步驟11。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-191">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 11).</span></span> <span data-ttu-id="5c0d5-192">您也可以選擇將 Edge Server 或 Edge 集區設定為使用網路位址轉譯 (NAT) 位址的外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-192">You also have the option of configuring your Edge Server or your Edge pool to use a network address translation (NAT) address for the external IP address.</span></span> <span data-ttu-id="5c0d5-193">您可以選擇 **此 Edge 集區的外部 IP 位址由 NAT 轉譯** ] 核取方塊來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-193">You can do this by choosing **The external IP address of this Edge pool is translated by NAT** check box .</span></span> <span data-ttu-id="5c0d5-194">準備好時，按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-194">Click **Next** when ready.</span></span>
    
9. <span data-ttu-id="5c0d5-195">在 [外部 Fqdn] 畫面上，您的選擇取決於您在步驟7中所做的選擇。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-195">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="5c0d5-196">如果您已勾選 [ **使用單一 FQDN 和 IP 位址** ] 核取方塊，您必須在 [ **SIP 存取** ] 方塊中輸入單一的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-196">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="5c0d5-197">接著，您必須為每個 edge service 輸入不同的埠號碼，以允許所有 edge service 彼此獨立連接。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-197">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="5c0d5-198">建議您在5061的 **SIP Access** edge service 中，使用 **Web 會議** Edge service 的444，以及 **A/V** Edge service 的443。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-198">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="5c0d5-199">完成時，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-199">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="5c0d5-200">如果您未選取 [ **使用單一 FQDN 和 IP 位址** ] 核取方塊，則您現在必須為 **SIP Access** Edge service、 **Web 會議** Edge service 和 **A/V** Edge service 輸入三個外部 fqdn。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-200">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="5c0d5-201">完成時，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-201">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="5c0d5-202">現在您已到達 [ **定義此集區中的電腦** ] 畫面。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-202">Now you've reached the **Define the computers in this pool** screen.</span></span> <span data-ttu-id="5c0d5-203">按一下 [新增] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-203">Click the **Add** button.</span></span>
    
11. <span data-ttu-id="5c0d5-204">您現在已經位於 [ **定義內部 IP 位址** ] 畫面。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-204">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="5c0d5-205">在這裡，您會根據您在步驟8中所做的選擇，在 [ **內部 IPv4 位址** ] 和 [ **內部 IPv6 位址** ] 文字方塊中輸入 Edge Server 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-205">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="5c0d5-206">準備好時，按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-206">Click **Next** when ready.</span></span>
    
12. <span data-ttu-id="5c0d5-207">在 [ **定義外部 IP 位址** ] 畫面上，您可以根據您先前的選擇，使用一些選項：</span><span class="sxs-lookup"><span data-stu-id="5c0d5-207">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="5c0d5-208">您可以針對所有服務使用單一 FQDN。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-208">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="5c0d5-209">如果是的話，請輸入您的外部 IPv4 或 IPv6 位址 (您在 [ **SIP 存取** ] 文字方塊中使用) ，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-209">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="5c0d5-210">您可能已選擇為服務使用三個不同的 Fqdn 和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-210">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="5c0d5-211">如果是這種情況，請為 **SIP Access** Edge Service、 **Web 會議** Edge service 及 **A/V** Edge service 輸入您的外部 IPv4 或 IPv6 位址，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-211">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5c0d5-212">如果您先前未選擇啟用和指派 IPv6 定址，您就不會看到此對話方塊。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-212">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box.</span></span> <span data-ttu-id="5c0d5-213">這是正常的，請移至下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-213">That's normal, just go to the next step.</span></span> 
  
13. <span data-ttu-id="5c0d5-214">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-214">Click **Finish**.</span></span> <span data-ttu-id="5c0d5-215">您剛才建立的 Edge Server 現在應該會列在 [ **定義此集區中的電腦** ] 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-215">The Edge Server you just created should now be listed in the **Define the computers in this pool** dialog box.</span></span>
    
14. <span data-ttu-id="5c0d5-216">在 [ **定義此集區中的電腦** ] 畫面仍然開啟時，請再次按一下 [ **新增** ] 按鈕，然後重複步驟11到13，直到您已新增您要在此集區中使用的所有 Edge server 為止。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-216">While still on the **Define the computers in this pool** screen, click the **Add** button again and repeat steps 11 through 13 until you've added all the Edge Servers you intend to have in this pool.</span></span> <span data-ttu-id="5c0d5-217">完成時，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-217">When this is complete, click **Next**.</span></span>
    
15. <span data-ttu-id="5c0d5-218">如果您選擇在步驟8中使用 NAT 回來，您現在會看到 [ **公用 IP 位址** ] textbox 的畫面。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-218">If you chose to use NAT back in Step 8, you'll now get a screen with a **Public IP address** textbox.</span></span> <span data-ttu-id="5c0d5-219">您必須輸入您為 A/V Edge service 設定的公用 IPv4 和/或 IPv6 位址，才能由 NAT 轉譯。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-219">You'll need to enter the public IPv4 and/or IPv6 address you've set for the A/V Edge service, to be translated by NAT.</span></span> <span data-ttu-id="5c0d5-220">然後按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-220">Then click **Next**.</span></span>
    
16. <span data-ttu-id="5c0d5-221">[下一屏向上] 是 **定義下一個躍點**。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-221">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="5c0d5-222">在 [ **下一個躍點集區]** 方塊中，選取您的內部集區名稱，其可能是前端集區或獨立集區。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-222">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="5c0d5-223">如果您的環境中有 Director，您應該選擇 Director。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-223">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="5c0d5-224">然後按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-224">Then click **Next**.</span></span>
    
17. <span data-ttu-id="5c0d5-225">在 [ **建立前端** 集區] 畫面上，您必須指定一或多個要與此 Edge Server 產生關聯的內部集區（包括前端集區和 Standard Edition 集區）。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-225">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition pools, to associate with this Edge Server.</span></span> <span data-ttu-id="5c0d5-226">只需選擇您要使用此 Edge Server 與支援的外部使用者進行通訊的內部集區名稱。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-226">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="5c0d5-227">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-227">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5c0d5-228">請注意，如果您的內部集區或獨立伺服器已使用不同的商務用 Skype Server Edge Server，則不能有多個關聯。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-228">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="5c0d5-229">如果您選擇的內部集區或獨立伺服器在該情況下，您將會看到警告，告知您其他 Edge Server，您可以決定是否要繼續。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-229">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="5c0d5-230">如果您要繼續進行這個新的關聯，其他 Edge Server 的連線將停止。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-230">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
18. <span data-ttu-id="5c0d5-231">按一下下一個畫面上的 **[完成]** 。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-231">Click **Finish** on the next screen.</span></span>
    
19. <span data-ttu-id="5c0d5-232">現在您將能夠發佈此更新的技術，並遵循在 [商務用 Skype server 的部署 edge](deploy-edge-servers.md) server 中的指示，從這裡部署至 Edge server。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-232">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="5c0d5-233">定義硬體負載平衡 Edge Server 集區的拓撲</span><span class="sxs-lookup"><span data-stu-id="5c0d5-233">Defining the topology for a hardware load balanced Edge Server pool</span></span>

1. <span data-ttu-id="5c0d5-234">登入商務用 Skype server Standard Edition server，或商務用 Skype Server 前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-234">Log onto your Skype for Business Server Standard Edition server, or a Skype for Business Server Front End Server.</span></span>
    
2. <span data-ttu-id="5c0d5-235">一旦存在，開啟 **商務用 Skype Server 拓撲** 產生器。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-235">Once there, open **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="5c0d5-236">在主控台樹中，展開您要部署 Edge Server 的網站。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-236">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="5c0d5-237">以滑鼠右鍵按一下 [ **edge** 集區]，然後按一下 [ **新增 edge 集** 區]。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-237">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="5c0d5-238">在 [**定義新的 Edge 集** 區] 畫面上，按一下 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-238">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="5c0d5-239">在 [ **定義 edge 集區 FQDN** ] 畫面上，輸入要使用 Edge 集區的內部完整功能變數名稱 (FQDN) ，然後選取 [多部 **電腦集** 區]，完成後，按一下 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-239">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge pool is going to use, and select **Multiple computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="5c0d5-240">在 [ **選取功能** ] 畫面上，您可以選擇：</span><span class="sxs-lookup"><span data-stu-id="5c0d5-240">On the **Select features** screen, you have a choice:</span></span>
    
   - <span data-ttu-id="5c0d5-241">您可能想要對 SIP 存取服務、商務用 Skype Server Web 會議服務和您的 A/V Edge service 使用相同的 FQDN 和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-241">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server Web Conferencing Service, and your A/V Edge service.</span></span> <span data-ttu-id="5c0d5-242">如果是的話，您必須選擇 [ **使用單一 FQDN 和 IP 位址] 核取方塊** (，並記住以下的步驟 9) </span><span class="sxs-lookup"><span data-stu-id="5c0d5-242">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
   - <span data-ttu-id="5c0d5-243">如果您打算啟用同盟，請選擇 [ **啟用此 Edge 集區的同盟 (埠 5061)** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-243">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="5c0d5-244">按一下 **[下一步]** 後，您會在 [ **IP 選項** ] 畫面上找到您自己。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-244">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen.</span></span> <span data-ttu-id="5c0d5-245">選項如下：</span><span class="sxs-lookup"><span data-stu-id="5c0d5-245">Your options are as follows:</span></span>
    
   - <span data-ttu-id="5c0d5-246">在內部介面上啟用 IPv4</span><span class="sxs-lookup"><span data-stu-id="5c0d5-246">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="5c0d5-247">在內部介面上啟用 IPv6</span><span class="sxs-lookup"><span data-stu-id="5c0d5-247">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="5c0d5-248">在外部介面上啟用 IPv4</span><span class="sxs-lookup"><span data-stu-id="5c0d5-248">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="5c0d5-249">在外部介面上啟用 IPv6</span><span class="sxs-lookup"><span data-stu-id="5c0d5-249">Enable IPv6 on the external interface</span></span>
    
     <span data-ttu-id="5c0d5-250">不管您是使用 IPv4 或 IPv6 位址，還是要在內部或外部于您的 Edge Server 上套用這些位址，這些位址都有很好的自我說明 (您必須記住這一點，) 步驟11。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-250">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 11).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="5c0d5-251">與其他兩個拓撲選項不同的是，使用硬體負載平衡器時，您 **不能** 選取 [選項]。 **Edge 集區的外部 IP 位址是由 NAT 轉譯**。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-251">Unlike the other two topology options, when using a hardware load balancer, you **MUST NOT** select the option **The external IP address of the Edge Pool is translated by NAT**.</span></span> <span data-ttu-id="5c0d5-252">這是 **不受支援** 的。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-252">This is **not supported**.</span></span>
  
9. <span data-ttu-id="5c0d5-253">在 [外部 Fqdn] 畫面上，您的選擇取決於您在步驟7中所做的選擇。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-253">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="5c0d5-254">如果您已勾選 [ **使用單一 FQDN 和 IP 位址** ] 核取方塊，您必須在 [ **SIP 存取** ] 方塊中輸入單一的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-254">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="5c0d5-255">接著，您必須為每個 edge service 輸入不同的埠號碼，以允許所有 edge service 彼此獨立連接。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-255">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="5c0d5-256">建議您在5061的 **SIP Access** edge service 中，使用 **Web 會議** Edge service 的444，以及 **A/V** Edge service 的443。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-256">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="5c0d5-257">完成時，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-257">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="5c0d5-258">如果您未選取 [ **使用單一 FQDN 和 IP 位址** ] 核取方塊，則您現在必須為 **SIP Access** Edge service、 **Web 會議** Edge service 和 **A/V** Edge service 輸入三個外部 fqdn。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-258">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="5c0d5-259">完成時，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-259">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="5c0d5-260">現在您已到達 [ **定義此集區中的電腦** ] 畫面。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-260">Now you've reached the **Define the computers in this pool** screen.</span></span> <span data-ttu-id="5c0d5-261">按一下 [新增] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-261">Click the **Add** button.</span></span>
    
11. <span data-ttu-id="5c0d5-262">您現在已經位於 [ **定義內部 IP 位址** ] 畫面。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-262">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="5c0d5-263">在這裡，您會根據您在步驟8中所做的選擇，在 [ **內部 IPv4 位址** ] 和 [ **內部 IPv6 位址** ] 文字方塊中輸入 Edge Server 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-263">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="5c0d5-264">準備好時，按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-264">Click **Next** when ready.</span></span>
    
12. <span data-ttu-id="5c0d5-265">在 [ **定義外部 IP 位址** ] 畫面上，您可以根據您先前的選擇，使用一些選項：</span><span class="sxs-lookup"><span data-stu-id="5c0d5-265">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="5c0d5-266">您可以針對所有服務使用單一 FQDN。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-266">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="5c0d5-267">如果是的話，請輸入您的外部 IPv4 或 IPv6 位址 (您在 [ **SIP 存取** ] 文字方塊中使用) ，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-267">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="5c0d5-268">您可能已選擇為服務使用三個不同的 Fqdn 和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-268">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="5c0d5-269">如果是這種情況，請為 **SIP Access** Edge Service、 **Web 會議** Edge service 及 **A/V** Edge service 輸入您的外部 IPv4 或 IPv6 位址，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-269">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5c0d5-270">如果您先前未選擇啟用和指派 IPv6 定址，您就不會看到此對話方塊。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-270">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box.</span></span> <span data-ttu-id="5c0d5-271">這是正常的，請移至下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-271">That's normal, just go to the next step.</span></span> 
  
13. <span data-ttu-id="5c0d5-272">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-272">Click **Finish**.</span></span> <span data-ttu-id="5c0d5-273">您剛才建立的 Edge Server 現在應該會列在 [ **定義此集區中的電腦** ] 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-273">The Edge Server you just created should now be listed in the **Define the computers in this pool** dialog box.</span></span>
    
14. <span data-ttu-id="5c0d5-274">在 [ **定義此集區中的電腦** ] 畫面仍然開啟時，請再次按一下 [ **新增** ] 按鈕，然後重複步驟11到13，直到您已新增您要在此集區中使用的所有 Edge server 為止。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-274">While still on the **Define the computers in this pool** screen, click the **Add** button again and repeat steps 11 through 13 until you've added all the Edge Servers you intend to have in this pool.</span></span> <span data-ttu-id="5c0d5-275">完成時，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-275">When this is complete, click **Next**.</span></span>
    
15. <span data-ttu-id="5c0d5-276">[下一屏向上] 是 **定義下一個躍點**。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-276">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="5c0d5-277">在 [ **下一個躍點集區]** 方塊中，選取您的內部集區名稱，其可能是前端集區或獨立集區。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-277">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="5c0d5-278">如果您的環境中有 Director，您應該選擇 Director。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-278">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="5c0d5-279">然後按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-279">Then click **Next**.</span></span>
    
16. <span data-ttu-id="5c0d5-280">在 [ **建立前端** 集區] 畫面上，您必須指定一或多個要與此 Edge Server 產生關聯的內部集區（包括前端集區和 Standard Edition 集區）。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-280">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition pools, to associate with this Edge Server.</span></span> <span data-ttu-id="5c0d5-281">只需選擇您要使用此 Edge Server 與支援的外部使用者進行通訊的內部集區名稱。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-281">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="5c0d5-282">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-282">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5c0d5-283">請注意，如果您的內部集區或獨立伺服器已使用不同的商務用 Skype Server Edge Server，則不能有多個關聯。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-283">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="5c0d5-284">如果您選擇的內部集區或獨立伺服器在該情況下，您將會看到警告，告知您其他 Edge Server，您可以決定是否要繼續。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-284">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="5c0d5-285">如果您要繼續進行這個新的關聯，其他 Edge Server 的連線將停止。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-285">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
17. <span data-ttu-id="5c0d5-286">按一下下一個畫面上的 **[完成]** 。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-286">Click **Finish** on the next screen.</span></span>
    
18. <span data-ttu-id="5c0d5-287">現在您將能夠發佈此更新的技術，並遵循在 [商務用 Skype server 的部署 edge](deploy-edge-servers.md) server 中的指示，從這裡部署至 Edge server。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-287">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
## <a name="publish-your-edge-server-topology"></a><span data-ttu-id="5c0d5-288">發佈 Edge Server 拓撲</span><span class="sxs-lookup"><span data-stu-id="5c0d5-288">Publish your Edge Server topology</span></span>

<span data-ttu-id="5c0d5-289">當您完成上述步驟之後，就可以發佈這個新的拓撲，也可以將它匯出至您的商務用 Skype Server Edge Server 或 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-289">Once you've finished the steps above, it's time to publish this new topology, which will also allow you to export it to your Skype for Business Server Edge Server or Edge pool.</span></span> <span data-ttu-id="5c0d5-290">依照下列步驟執行：</span><span class="sxs-lookup"><span data-stu-id="5c0d5-290">Follow these steps:</span></span>
  
1. <span data-ttu-id="5c0d5-291">啟動 **拓撲** 產生器 (（如果尚未從先前的程式) 啟動）。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-291">Start **Topology Builder** (if it's not started already from the previous procedure).</span></span>
    
2. <span data-ttu-id="5c0d5-292">在 [ **拓撲** 產生器] 的主控台樹中，以滑鼠右鍵按一下 [ **商務用 skype 伺服器** ]，然後按一下 [商務用 **skype server 拓撲** 產生器]。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-292">In **Topology Builder**, in the console tree, right-click **Skype for Business Server** and then click **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="5c0d5-293">在嚮導的 [ **歡迎** ] 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-293">On the **Welcome** page of the wizard, click **Next**.</span></span>
    
4. <span data-ttu-id="5c0d5-294">在 [ **建立其他資料庫** ] 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-294">On the **Create other databases** page, click **Next**.</span></span>
    
5. <span data-ttu-id="5c0d5-295">當狀態指出資料庫建立成功時，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="5c0d5-295">When the status indicates that the database creation succeeded, do the following:</span></span>
    
    - <span data-ttu-id="5c0d5-296">若要查看記錄檔，請按一下 [ **查看記錄** 檔]。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-296">To view the log, click **View log**.</span></span>
    
    - <span data-ttu-id="5c0d5-297">按一下 **[完成]**，關閉精靈。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-297">To close the wizard, click **Finish**.</span></span>
    
## <a name="export-your-edge-server-topology"></a><span data-ttu-id="5c0d5-298">匯出 Edge Server 拓撲</span><span class="sxs-lookup"><span data-stu-id="5c0d5-298">Export your Edge Server topology</span></span>

<span data-ttu-id="5c0d5-299">若要順利部署，商務用 Skype Server 部署嚮導需要存取中央管理存放區資料。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-299">To deploy successfully, the Skype for Business Server Deployment Wizard needs access to the Central Management store data.</span></span> <span data-ttu-id="5c0d5-300">對於您網域或樹系中的內部伺服器，這通常是直接的。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-300">For internal servers in your domain or forest, this typically is straightforward.</span></span> <span data-ttu-id="5c0d5-301">Edge Server 位於網域之外，因此必須手動將拓撲檔案匯出至 Edge Server 位置，通常是在實體媒體上。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-301">Edge Servers are outside of the domain, and so it's necessary to manually export the topology file to the Edge Server location, usually on a physical media.</span></span> <span data-ttu-id="5c0d5-302">這會透過 PowerShell: 執行這種匯出</span><span class="sxs-lookup"><span data-stu-id="5c0d5-302">This export is done via PowerShell:</span></span>
  
1. <span data-ttu-id="5c0d5-303">啟動 **商務用 Skype Server 管理命令** 介面。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-303">Start the **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="5c0d5-304">在 **商務用 Skype Server 管理命令** 介面中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="5c0d5-304">In the **Skype for Business Server Management Shell**, run the following:</span></span>
    
   ```powershell
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. <span data-ttu-id="5c0d5-305">將匯出的檔案複製到外部媒體 (例如，您可以從 Edge Server 位置) 的 USB 磁片磁碟機或網路共用。</span><span class="sxs-lookup"><span data-stu-id="5c0d5-305">Copy the exported file to external media (for example, a USB drive or network share that you can reach from the Edge Server's location).</span></span>
    

