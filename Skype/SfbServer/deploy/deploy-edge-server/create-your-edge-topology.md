---
title: 為商務用 Skype Server 建立邊緣拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 摘要：瞭解如何在商務用 Skype Server 中建立、發佈及匯出邊緣伺服器拓撲。
ms.openlocfilehash: 3abde687899f240174e91d2583321bcdc6855fff
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768326"
---
# <a name="create-your-edge-topology-for-skype-for-business-server"></a><span data-ttu-id="ce8d4-103">為商務用 Skype Server 建立邊緣拓撲</span><span class="sxs-lookup"><span data-stu-id="ce8d4-103">Create your Edge topology for Skype for Business Server</span></span>
 
<span data-ttu-id="ce8d4-104">**摘要：** 瞭解如何在商務用 Skype Server 中建立、發佈及匯出 Edge 伺服器拓撲。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-104">**Summary:** Learn how to build, publish, and export your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="ce8d4-105">[拓撲建立器] 是您在建立邊緣伺服器拓撲時所需使用的工具，就與商務用 Skype Server 的任何拓撲元件搭配使用一樣。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-105">Topology Builder is the tool you need to use to build your Edge Server topology, just as it's used for any topology component for Skype for Business Server.</span></span> <span data-ttu-id="ce8d4-106">在遵循下列步驟之前，您必須先設定至少一個前端池或標準版伺服器。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-106">Before following the steps below, you will need to have set up at least one Front End pool or a Standard Edition server.</span></span>
  
<span data-ttu-id="ce8d4-107">我們會在本文中涵蓋下列主題：</span><span class="sxs-lookup"><span data-stu-id="ce8d4-107">We cover the following topics in this article:</span></span>
  
- <span data-ttu-id="ce8d4-108">建立您的邊緣伺服器拓撲</span><span class="sxs-lookup"><span data-stu-id="ce8d4-108">Build your Edge Server topology</span></span>
    
- <span data-ttu-id="ce8d4-109">發佈 Edge 伺服器拓撲</span><span class="sxs-lookup"><span data-stu-id="ce8d4-109">Publish your Edge Server topology</span></span>
    
- <span data-ttu-id="ce8d4-110">匯出邊緣伺服器拓撲</span><span class="sxs-lookup"><span data-stu-id="ce8d4-110">Export your Edge Server topology</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="ce8d4-111">若要遵循下列步驟，您必須登入如下所述的網域伺服器，就像是下列網域群組成員的使用者：</span><span class="sxs-lookup"><span data-stu-id="ce8d4-111">To follow the steps below, you're going to need to log into the domain servers mentioned below as a user who's a member of the following domain groups:</span></span> 
  
- <span data-ttu-id="ce8d4-112">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ce8d4-112">RTCUniversalServerAdmins</span></span>
    
- <span data-ttu-id="ce8d4-113">網域管理員</span><span class="sxs-lookup"><span data-stu-id="ce8d4-113">Domain Admins</span></span>
    
## <a name="build-your-edge-server-topology"></a><span data-ttu-id="ce8d4-114">建立您的邊緣伺服器拓撲</span><span class="sxs-lookup"><span data-stu-id="ce8d4-114">Build your Edge Server topology</span></span>

<span data-ttu-id="ce8d4-115">第一個部署步驟是建立您的商務用 Skype Server Edge 伺服器拓撲，其中包含三個選項的其中一個：</span><span class="sxs-lookup"><span data-stu-id="ce8d4-115">The first deployment step is building your Skype for Business Server Edge Server topology, which consists of one of three options:</span></span>
  
- <span data-ttu-id="ce8d4-116">單一邊緣伺服器</span><span class="sxs-lookup"><span data-stu-id="ce8d4-116">A single Edge Server</span></span>
    
- <span data-ttu-id="ce8d4-117">DNS 負載平衡的邊緣池（一或多個伺服器）</span><span class="sxs-lookup"><span data-stu-id="ce8d4-117">A DNS load balanced Edge pool (one or more servers)</span></span>
    
- <span data-ttu-id="ce8d4-118">硬體負載平衡的邊緣池（一或多個伺服器）</span><span class="sxs-lookup"><span data-stu-id="ce8d4-118">A hardware load balanced Edge pool (one or more servers)</span></span>
    
<span data-ttu-id="ce8d4-119">如果您不確定所需的專案，請在開始執行下列步驟之前，請先走完規劃檔。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-119">If you aren't sure what you need, then before you start following these steps, it's a good time to go over the Planning documentation.</span></span> <span data-ttu-id="ce8d4-120">否則，讓我們開始吧。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-120">Otherwise, let's begin.</span></span>
  
### <a name="defining-the-topology-for-a-single-edge-server"></a><span data-ttu-id="ce8d4-121">定義單一邊緣伺服器的拓撲</span><span class="sxs-lookup"><span data-stu-id="ce8d4-121">Defining the topology for a single Edge Server</span></span>

1. <span data-ttu-id="ce8d4-122">登入您的商務用 Skype Server 標準版伺服器，或商務用 Skype Server 前端池。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-122">Log onto your Skype for Business Server Standard Edition server, or a Skype for Business Server Front End pool.</span></span>
    
2. <span data-ttu-id="ce8d4-123">在該處開啟 [**商務用 Skype 伺服器拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-123">Once there, open **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="ce8d4-124">在主控台樹中，展開您要部署邊緣伺服器的網站。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-124">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="ce8d4-125">以滑鼠右鍵按一下 [**邊緣池**]，然後按一下 [**新增邊緣池**]。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-125">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="ce8d4-126">按一下 [**定義新的邊緣池**] 畫面上的 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-126">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="ce8d4-127">在 [**定義 edge 池 FQDN** ] 畫面上，輸入邊緣伺服器要使用的內部完整功能變數名稱（FQDN），然後選取 [**單一電腦] 池**，然後在 [完成時，按一下 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-127">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge Server is going to use, and select **Single computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="ce8d4-128">在 [**選取功能**] 畫面上，您可以選擇：</span><span class="sxs-lookup"><span data-stu-id="ce8d4-128">On the **Select features** screen, you have a choice:</span></span>
    
   - <span data-ttu-id="ce8d4-129">您可能想要針對 SIP 存取服務、商務用 Skype Server Web 會議服務和您的 A/V 邊緣服務使用相同的 FQDN 和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-129">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server Web Conferencing service, and your A/V Edge service.</span></span> <span data-ttu-id="ce8d4-130">如果是這樣，您必須選擇 [**使用單一 FQDN 和 IP 位址] 核取方塊**（並在下面的步驟9中繼續）</span><span class="sxs-lookup"><span data-stu-id="ce8d4-130">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
   - <span data-ttu-id="ce8d4-131">如果您打算啟用同盟，請選擇 [**針對此 Edge 池啟用同盟（埠5061）** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-131">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="ce8d4-132">按一下 **[下一步]** 之後，您會在 [ **IP 選項**] 畫面上找到自己。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-132">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen.</span></span> <span data-ttu-id="ce8d4-133">選項如下所示：</span><span class="sxs-lookup"><span data-stu-id="ce8d4-133">Your options are as follows:</span></span>
    
   - <span data-ttu-id="ce8d4-134">在內部介面上啟用 IPv4</span><span class="sxs-lookup"><span data-stu-id="ce8d4-134">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="ce8d4-135">在內部介面上啟用 IPv6</span><span class="sxs-lookup"><span data-stu-id="ce8d4-135">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="ce8d4-136">在外部介面上啟用 IPv4</span><span class="sxs-lookup"><span data-stu-id="ce8d4-136">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="ce8d4-137">在外部介面上啟用 IPv6</span><span class="sxs-lookup"><span data-stu-id="ce8d4-137">Enable IPv6 on the external interface</span></span>
    
   <span data-ttu-id="ce8d4-138">無論您使用的是 IPv4 或 IPv6 位址，這些位址都一目了然，而您是要在邊緣伺服器（內部或外部）套用這些位址（在步驟10中，您將需要記住這一點）。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-138">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 10).</span></span> <span data-ttu-id="ce8d4-139">您也可以選擇將 Edge 伺服器或 Edge 池設定為使用網路位址轉譯（NAT）位址作為外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-139">You also have the option of configuring your Edge Server or your Edge pool to use a network address translation (NAT) address for the external IP address.</span></span> <span data-ttu-id="ce8d4-140">您可以選擇 [**此 Edge 池的外部 IP 位址是由 NAT 轉譯**] 核取方塊來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-140">You can do this by choosing **The external IP address of this Edge pool is translated by NAT** check box .</span></span> <span data-ttu-id="ce8d4-141">準備就緒時，按一下 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-141">Click **Next** when ready.</span></span>
    
9. <span data-ttu-id="ce8d4-142">在 [外部 Fqdn] 畫面上，您的選項取決於您在上述步驟7中所做的選取。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-142">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="ce8d4-143">如果您已核取 [**使用單一 FQDN 和 IP 位址**] 核取方塊，您必須在 [ **SIP 存取**] 方塊中輸入單一的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-143">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="ce8d4-144">接著，您必須針對每個 edge 服務輸入不同的埠號碼，以允許它們彼此獨立連線。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-144">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="ce8d4-145">我們建議將5061用於**SIP 存取**邊緣服務、444的**網路會議**Edge 服務，以及**A/V**邊緣服務的443。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-145">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="ce8d4-146">完成時，請按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-146">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="ce8d4-147">如果您沒有核取 [**使用單一 FQDN 和 IP 位址**] 核取方塊，您現在必須為**SIP 存取**邊緣服務、**網路會議**Edge 服務和**a/V**邊緣服務輸入三個外部 fqdn。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-147">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="ce8d4-148">完成時，請按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-148">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="ce8d4-149">您現在已在 [**定義內部 IP 位址**] 畫面上。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-149">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="ce8d4-150">在這裡，您會在 [**內部 IPv4 位址**] 和 [**內部 IPv6 位址**] 文字方塊中輸入 Edge 伺服器的 IP 位址，視您在步驟8中所做的選擇而定。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-150">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="ce8d4-151">準備就緒時，按一下 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-151">Click **Next** when ready.</span></span>
    
11. <span data-ttu-id="ce8d4-152">在 [**定義外部 IP 位址**] 畫面上，您可以選擇幾個選項（視您先前的選項而定）：</span><span class="sxs-lookup"><span data-stu-id="ce8d4-152">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="ce8d4-153">您可能會在所有服務中使用單一 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-153">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="ce8d4-154">如果是，請在 [ **SIP 存取**] 文字方塊中輸入您的外部 IPv4 或 IPv6 位址（無論您使用的是哪一個），然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-154">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="ce8d4-155">您可能已選擇針對服務使用三個不同的 Fqdn 和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-155">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="ce8d4-156">如果是這種情況，請為**SIP 存取**邊緣服務、**網路會議**Edge 服務和**A/V**邊緣服務輸入您的外部 IPv4 或 IPv6 位址，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-156">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ce8d4-157">如果您先前沒有選擇啟用並指派 IPv6 定址，您就不會看到這個對話方塊。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-157">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box.</span></span> <span data-ttu-id="ce8d4-158">那是正常的，請移至下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-158">That's normal, just go to the next step.</span></span> 
  
12. <span data-ttu-id="ce8d4-159">如果您選擇在步驟8中使用 NAT，您現在會看到一個畫面，其中包含**公用 IP 位址**textbox。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-159">If you chose to use NAT back in Step 8, you'll now get a screen with a **Public IP address** textbox.</span></span> <span data-ttu-id="ce8d4-160">您必須輸入您為 A/V Edge 服務設定的公用 IPv4 和/或 IPv6 位址，才能由 NAT 進行翻譯。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-160">You'll need to enter the public IPv4 and/or IPv6 address you've set for the A/V Edge service, to be translated by NAT.</span></span> <span data-ttu-id="ce8d4-161">然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-161">Then click **Next**.</span></span>
    
13. <span data-ttu-id="ce8d4-162">[下一個畫面向上] 是 [**定義下一個躍點]**。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-162">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="ce8d4-163">在 [**下一個躍點池]** 方塊中，選取您的內部池名稱，這可能是前端池或獨立池。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-163">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="ce8d4-164">如果您的環境中有主管，您應該選擇控制器。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-164">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="ce8d4-165">然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-165">Then click **Next**.</span></span>
    
14. <span data-ttu-id="ce8d4-166">在 [**關聯前端池**] 畫面上，您必須指定一個或多個內部池（包括前端池和標準版伺服器），才能與此 Edge 伺服器建立關聯。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-166">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition servers, to associate with this Edge Server.</span></span> <span data-ttu-id="ce8d4-167">只要選擇您想要使用此 Edge 伺服器與支援的外部使用者通訊的內部池名稱即可。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-167">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="ce8d4-168">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-168">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ce8d4-169">請記住，如果您的內部池或獨立伺服器已使用不同的商務用 Skype Server Edge 伺服器，則它們不能有多個關聯性。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-169">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="ce8d4-170">如果您選擇在這種情況下的內部池或獨立伺服器，您會看到一個警告，告訴您其他邊緣伺服器，您可以決定是否要繼續進行。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-170">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="ce8d4-171">如果您要繼續這個新的關聯，則與其他邊緣伺服器的連線將會停止。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-171">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
15. <span data-ttu-id="ce8d4-172">按一下下一個畫面上的 **[完成]** 。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-172">Click **Finish** on the next screen.</span></span>
    
16. <span data-ttu-id="ce8d4-173">現在，您可以發佈此更新的技術，並依照[商務用 Skype Server 中部署邊緣](deploy-edge-servers.md)伺服器中的指示，從這裡部署到您的 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-173">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="ce8d4-174">定義 DNS 負載平衡邊緣伺服器池的拓撲</span><span class="sxs-lookup"><span data-stu-id="ce8d4-174">Defining the topology for a DNS load balanced Edge Server pool</span></span>

1. <span data-ttu-id="ce8d4-175">登入您的商務用 Skype Server 標準版伺服器，或商務用 Skype Server 前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-175">Log onto your Skype for Business Server Standard Edition server, or a Skype for Business Server Front End Server.</span></span>
    
2. <span data-ttu-id="ce8d4-176">在該處開啟 [**商務用 Skype 伺服器拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-176">Once there, open **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="ce8d4-177">在主控台樹中，展開您要部署邊緣伺服器的網站。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-177">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="ce8d4-178">以滑鼠右鍵按一下 [**邊緣池**]，然後按一下 [**新增邊緣池**]。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-178">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="ce8d4-179">按一下 [**定義新的邊緣池**] 畫面上的 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-179">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="ce8d4-180">在 [**定義 edge 池 FQDN** ] 畫面上，輸入邊緣池要使用的內部完整功能變數名稱（FQDN），然後選取**多個電腦池**，然後在 [完成時按一下 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-180">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge pool is going to use, and select **Multiple computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="ce8d4-181">在 [**選取功能**] 畫面上，您可以選擇：</span><span class="sxs-lookup"><span data-stu-id="ce8d4-181">On the **Select features** screen, you have a choice:</span></span>
    
    - <span data-ttu-id="ce8d4-182">您可能想要針對 SIP 存取服務、商務用 Skype Server Web 會議服務和您的 A/V 邊緣服務使用相同的 FQDN 和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-182">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server Web Conferencing Service, and your A/V Edge service.</span></span> <span data-ttu-id="ce8d4-183">如果是這樣，您必須選擇 [**使用單一 FQDN 和 IP 位址] 核取方塊**（並在下面的步驟9中繼續）</span><span class="sxs-lookup"><span data-stu-id="ce8d4-183">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
    - <span data-ttu-id="ce8d4-184">如果您打算啟用同盟，請選擇 [**針對此 Edge 池啟用同盟（埠5061）** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-184">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="ce8d4-185">按一下 **[下一步]** 之後，您會在 [ **IP 選項**] 畫面上找到自己。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-185">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen.</span></span> <span data-ttu-id="ce8d4-186">選項如下所示：</span><span class="sxs-lookup"><span data-stu-id="ce8d4-186">Your options are as follows:</span></span>
    
    - <span data-ttu-id="ce8d4-187">在內部介面上啟用 IPv4</span><span class="sxs-lookup"><span data-stu-id="ce8d4-187">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="ce8d4-188">在內部介面上啟用 IPv6</span><span class="sxs-lookup"><span data-stu-id="ce8d4-188">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="ce8d4-189">在外部介面上啟用 IPv4</span><span class="sxs-lookup"><span data-stu-id="ce8d4-189">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="ce8d4-190">在外部介面上啟用 IPv6</span><span class="sxs-lookup"><span data-stu-id="ce8d4-190">Enable IPv6 on the external interface</span></span>
    
     <span data-ttu-id="ce8d4-191">無論您使用的是 IPv4 或 IPv6 位址，這些位址都是一目了然的，而且您要在邊緣伺服器或外部將這些位址套用到您的電腦上（在步驟11中，您將需要記住這一點）。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-191">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 11).</span></span> <span data-ttu-id="ce8d4-192">您也可以選擇將 Edge 伺服器或 Edge 池設定為使用網路位址轉譯（NAT）位址作為外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-192">You also have the option of configuring your Edge Server or your Edge pool to use a network address translation (NAT) address for the external IP address.</span></span> <span data-ttu-id="ce8d4-193">您可以選擇 [**此 Edge 池的外部 IP 位址是由 NAT 轉譯**] 核取方塊來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-193">You can do this by choosing **The external IP address of this Edge pool is translated by NAT** check box .</span></span> <span data-ttu-id="ce8d4-194">準備就緒時，按一下 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-194">Click **Next** when ready.</span></span>
    
9. <span data-ttu-id="ce8d4-195">在 [外部 Fqdn] 畫面上，您的選項取決於您在上述步驟7中所做的選取。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-195">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="ce8d4-196">如果您已核取 [**使用單一 FQDN 和 IP 位址**] 核取方塊，您必須在 [ **SIP 存取**] 方塊中輸入單一的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-196">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="ce8d4-197">接著，您必須針對每個 edge 服務輸入不同的埠號碼，以允許它們彼此獨立連線。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-197">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="ce8d4-198">我們建議將5061用於**SIP 存取**邊緣服務、444的**網路會議**Edge 服務，以及**A/V**邊緣服務的443。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-198">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="ce8d4-199">完成時，請按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-199">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="ce8d4-200">如果您沒有核取 [**使用單一 FQDN 和 IP 位址**] 核取方塊，您現在必須為**SIP 存取**邊緣服務、**網路會議**Edge 服務和**a/V**邊緣服務輸入三個外部 fqdn。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-200">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="ce8d4-201">完成時，請按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-201">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="ce8d4-202">現在您已到達 [**定義此池中的電腦**] 畫面。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-202">Now you've reached the **Define the computers in this pool** screen.</span></span> <span data-ttu-id="ce8d4-203">按一下 [**新增**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-203">Click the **Add** button.</span></span>
    
11. <span data-ttu-id="ce8d4-204">您現在已在 [**定義內部 IP 位址**] 畫面上。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-204">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="ce8d4-205">在這裡，您會在 [**內部 IPv4 位址**] 和 [**內部 IPv6 位址**] 文字方塊中輸入 Edge 伺服器的 IP 位址，視您在步驟8中所做的選擇而定。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-205">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="ce8d4-206">準備就緒時，按一下 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-206">Click **Next** when ready.</span></span>
    
12. <span data-ttu-id="ce8d4-207">在 [**定義外部 IP 位址**] 畫面上，您可以選擇幾個選項（視您先前的選項而定）：</span><span class="sxs-lookup"><span data-stu-id="ce8d4-207">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="ce8d4-208">您可能會在所有服務中使用單一 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-208">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="ce8d4-209">如果是，請在 [ **SIP 存取**] 文字方塊中輸入您的外部 IPv4 或 IPv6 位址（無論您使用的是哪一個），然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-209">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="ce8d4-210">您可能已選擇針對服務使用三個不同的 Fqdn 和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-210">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="ce8d4-211">如果是這種情況，請為**SIP 存取**邊緣服務、**網路會議**Edge 服務和**A/V**邊緣服務輸入您的外部 IPv4 或 IPv6 位址，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-211">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ce8d4-212">如果您先前沒有選擇啟用並指派 IPv6 定址，您就不會看到這個對話方塊。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-212">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box.</span></span> <span data-ttu-id="ce8d4-213">那是正常的，請移至下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-213">That's normal, just go to the next step.</span></span> 
  
13. <span data-ttu-id="ce8d4-214">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-214">Click **Finish**.</span></span> <span data-ttu-id="ce8d4-215">您剛建立的邊緣伺服器現在應該會列在 [**定義此池中的電腦**] 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-215">The Edge Server you just created should now be listed in the **Define the computers in this pool** dialog box.</span></span>
    
14. <span data-ttu-id="ce8d4-216">當仍在 [**定義此 pool 的電腦**] 畫面中，請再次按一下 [**新增**] 按鈕，然後重複步驟11到13，直到您已新增您想在此池中擁有的所有邊緣伺服器為止。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-216">While still on the **Define the computers in this pool** screen, click the **Add** button again and repeat steps 11 through 13 until you've added all the Edge Servers you intend to have in this pool.</span></span> <span data-ttu-id="ce8d4-217">完成後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-217">When this is complete, click **Next**.</span></span>
    
15. <span data-ttu-id="ce8d4-218">如果您選擇在步驟8中使用 NAT，您現在會看到一個畫面，其中包含**公用 IP 位址**textbox。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-218">If you chose to use NAT back in Step 8, you'll now get a screen with a **Public IP address** textbox.</span></span> <span data-ttu-id="ce8d4-219">您必須輸入您為 A/V Edge 服務設定的公用 IPv4 和/或 IPv6 位址，才能由 NAT 進行翻譯。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-219">You'll need to enter the public IPv4 and/or IPv6 address you've set for the A/V Edge service, to be translated by NAT.</span></span> <span data-ttu-id="ce8d4-220">然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-220">Then click **Next**.</span></span>
    
16. <span data-ttu-id="ce8d4-221">[下一個畫面向上] 是 [**定義下一個躍點]**。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-221">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="ce8d4-222">在 [**下一個躍點池]** 方塊中，選取您的內部池名稱，這可能是前端池或獨立池。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-222">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="ce8d4-223">如果您的環境中有主管，您應該選擇控制器。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-223">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="ce8d4-224">然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-224">Then click **Next**.</span></span>
    
17. <span data-ttu-id="ce8d4-225">在 [**關聯前端池**] 畫面上，您必須指定一個或多個內部池（包括前端池和標準版池），才能與此 Edge 伺服器建立關聯。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-225">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition pools, to associate with this Edge Server.</span></span> <span data-ttu-id="ce8d4-226">只要選擇您想要使用此 Edge 伺服器與支援的外部使用者通訊的內部池名稱即可。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-226">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="ce8d4-227">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-227">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ce8d4-228">請記住，如果您的內部池或獨立伺服器已使用不同的商務用 Skype Server Edge 伺服器，則它們不能有多個關聯性。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-228">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="ce8d4-229">如果您選擇在這種情況下的內部池或獨立伺服器，您會看到一個警告，告訴您其他邊緣伺服器，您可以決定是否要繼續進行。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-229">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="ce8d4-230">如果您要繼續這個新的關聯，則與其他邊緣伺服器的連線將會停止。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-230">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
18. <span data-ttu-id="ce8d4-231">按一下下一個畫面上的 **[完成]** 。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-231">Click **Finish** on the next screen.</span></span>
    
19. <span data-ttu-id="ce8d4-232">現在，您可以發佈此更新的技術，並依照[商務用 Skype Server 中部署邊緣](deploy-edge-servers.md)伺服器中的指示，從這裡部署到您的 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-232">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="ce8d4-233">定義硬體負載平衡邊緣伺服器池的拓撲</span><span class="sxs-lookup"><span data-stu-id="ce8d4-233">Defining the topology for a hardware load balanced Edge Server pool</span></span>

1. <span data-ttu-id="ce8d4-234">登入您的商務用 Skype Server 標準版伺服器，或商務用 Skype Server 前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-234">Log onto your Skype for Business Server Standard Edition server, or a Skype for Business Server Front End Server.</span></span>
    
2. <span data-ttu-id="ce8d4-235">在該處開啟 [**商務用 Skype 伺服器拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-235">Once there, open **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="ce8d4-236">在主控台樹中，展開您要部署邊緣伺服器的網站。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-236">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="ce8d4-237">以滑鼠右鍵按一下 [**邊緣池**]，然後按一下 [**新增邊緣池**]。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-237">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="ce8d4-238">按一下 [**定義新的邊緣池**] 畫面上的 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-238">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="ce8d4-239">在 [**定義 edge 池 FQDN** ] 畫面上，輸入邊緣池要使用的內部完整功能變數名稱（FQDN），然後選取**多個電腦池**，然後在 [完成時按一下 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-239">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge pool is going to use, and select **Multiple computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="ce8d4-240">在 [**選取功能**] 畫面上，您可以選擇：</span><span class="sxs-lookup"><span data-stu-id="ce8d4-240">On the **Select features** screen, you have a choice:</span></span>
    
   - <span data-ttu-id="ce8d4-241">您可能想要針對 SIP 存取服務、商務用 Skype Server Web 會議服務和您的 A/V 邊緣服務使用相同的 FQDN 和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-241">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server Web Conferencing Service, and your A/V Edge service.</span></span> <span data-ttu-id="ce8d4-242">如果是這樣，您必須選擇 [**使用單一 FQDN 和 IP 位址] 核取方塊**（並在下面的步驟9中繼續）</span><span class="sxs-lookup"><span data-stu-id="ce8d4-242">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
   - <span data-ttu-id="ce8d4-243">如果您打算啟用同盟，請選擇 [**針對此 Edge 池啟用同盟（埠5061）** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-243">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="ce8d4-244">按一下 **[下一步]** 之後，您會在 [ **IP 選項**] 畫面上找到自己。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-244">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen.</span></span> <span data-ttu-id="ce8d4-245">選項如下所示：</span><span class="sxs-lookup"><span data-stu-id="ce8d4-245">Your options are as follows:</span></span>
    
   - <span data-ttu-id="ce8d4-246">在內部介面上啟用 IPv4</span><span class="sxs-lookup"><span data-stu-id="ce8d4-246">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="ce8d4-247">在內部介面上啟用 IPv6</span><span class="sxs-lookup"><span data-stu-id="ce8d4-247">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="ce8d4-248">在外部介面上啟用 IPv4</span><span class="sxs-lookup"><span data-stu-id="ce8d4-248">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="ce8d4-249">在外部介面上啟用 IPv6</span><span class="sxs-lookup"><span data-stu-id="ce8d4-249">Enable IPv6 on the external interface</span></span>
    
     <span data-ttu-id="ce8d4-250">無論您使用的是 IPv4 或 IPv6 位址，這些位址都是一目了然的，而且您要在邊緣伺服器或外部將這些位址套用到您的電腦上（在步驟11中，您將需要記住這一點）。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-250">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 11).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="ce8d4-251">在使用硬體負載平衡器時，除了其他兩個拓撲選項之外，您**不得**選取選項 **：由 NAT 轉譯邊緣池的外部 IP 位址**。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-251">Unlike the other two topology options, when using a hardware load balancer, you **MUST NOT** select the option **The external IP address of the Edge Pool is translated by NAT**.</span></span> <span data-ttu-id="ce8d4-252">**不支援**這種情況。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-252">This is **not supported**.</span></span>
  
9. <span data-ttu-id="ce8d4-253">在 [外部 Fqdn] 畫面上，您的選項取決於您在上述步驟7中所做的選取。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-253">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="ce8d4-254">如果您已核取 [**使用單一 FQDN 和 IP 位址**] 核取方塊，您必須在 [ **SIP 存取**] 方塊中輸入單一的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-254">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="ce8d4-255">接著，您必須針對每個 edge 服務輸入不同的埠號碼，以允許它們彼此獨立連線。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-255">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="ce8d4-256">我們建議將5061用於**SIP 存取**邊緣服務、444的**網路會議**Edge 服務，以及**A/V**邊緣服務的443。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-256">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="ce8d4-257">完成時，請按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-257">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="ce8d4-258">如果您沒有核取 [**使用單一 FQDN 和 IP 位址**] 核取方塊，您現在必須為**SIP 存取**邊緣服務、**網路會議**Edge 服務和**a/V**邊緣服務輸入三個外部 fqdn。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-258">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="ce8d4-259">完成時，請按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-259">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="ce8d4-260">現在您已到達 [**定義此池中的電腦**] 畫面。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-260">Now you've reached the **Define the computers in this pool** screen.</span></span> <span data-ttu-id="ce8d4-261">按一下 [**新增**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-261">Click the **Add** button.</span></span>
    
11. <span data-ttu-id="ce8d4-262">您現在已在 [**定義內部 IP 位址**] 畫面上。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-262">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="ce8d4-263">在這裡，您會在 [**內部 IPv4 位址**] 和 [**內部 IPv6 位址**] 文字方塊中輸入 Edge 伺服器的 IP 位址，視您在步驟8中所做的選擇而定。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-263">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="ce8d4-264">準備就緒時，按一下 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-264">Click **Next** when ready.</span></span>
    
12. <span data-ttu-id="ce8d4-265">在 [**定義外部 IP 位址**] 畫面上，您可以選擇幾個選項（視您先前的選項而定）：</span><span class="sxs-lookup"><span data-stu-id="ce8d4-265">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="ce8d4-266">您可能會在所有服務中使用單一 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-266">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="ce8d4-267">如果是，請在 [ **SIP 存取**] 文字方塊中輸入您的外部 IPv4 或 IPv6 位址（無論您使用的是哪一個），然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-267">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="ce8d4-268">您可能已選擇針對服務使用三個不同的 Fqdn 和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-268">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="ce8d4-269">如果是這種情況，請為**SIP 存取**邊緣服務、**網路會議**Edge 服務和**A/V**邊緣服務輸入您的外部 IPv4 或 IPv6 位址，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-269">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ce8d4-270">如果您先前沒有選擇啟用並指派 IPv6 定址，您就不會看到這個對話方塊。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-270">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box.</span></span> <span data-ttu-id="ce8d4-271">那是正常的，請移至下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-271">That's normal, just go to the next step.</span></span> 
  
13. <span data-ttu-id="ce8d4-272">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-272">Click **Finish**.</span></span> <span data-ttu-id="ce8d4-273">您剛建立的邊緣伺服器現在應該會列在 [**定義此池中的電腦**] 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-273">The Edge Server you just created should now be listed in the **Define the computers in this pool** dialog box.</span></span>
    
14. <span data-ttu-id="ce8d4-274">當仍在 [**定義此 pool 的電腦**] 畫面中，請再次按一下 [**新增**] 按鈕，然後重複步驟11到13，直到您已新增您想在此池中擁有的所有邊緣伺服器為止。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-274">While still on the **Define the computers in this pool** screen, click the **Add** button again and repeat steps 11 through 13 until you've added all the Edge Servers you intend to have in this pool.</span></span> <span data-ttu-id="ce8d4-275">完成後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-275">When this is complete, click **Next**.</span></span>
    
15. <span data-ttu-id="ce8d4-276">[下一個畫面向上] 是 [**定義下一個躍點]**。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-276">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="ce8d4-277">在 [**下一個躍點池]** 方塊中，選取您的內部池名稱，這可能是前端池或獨立池。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-277">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="ce8d4-278">如果您的環境中有主管，您應該選擇控制器。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-278">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="ce8d4-279">然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-279">Then click **Next**.</span></span>
    
16. <span data-ttu-id="ce8d4-280">在 [**關聯前端池**] 畫面上，您必須指定一個或多個內部池（包括前端池和標準版池），才能與此 Edge 伺服器建立關聯。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-280">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition pools, to associate with this Edge Server.</span></span> <span data-ttu-id="ce8d4-281">只要選擇您想要使用此 Edge 伺服器與支援的外部使用者通訊的內部池名稱即可。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-281">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="ce8d4-282">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-282">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ce8d4-283">請記住，如果您的內部池或獨立伺服器已使用不同的商務用 Skype Server Edge 伺服器，則它們不能有多個關聯性。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-283">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="ce8d4-284">如果您選擇在這種情況下的內部池或獨立伺服器，您會看到一個警告，告訴您其他邊緣伺服器，您可以決定是否要繼續進行。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-284">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="ce8d4-285">如果您要繼續這個新的關聯，則與其他邊緣伺服器的連線將會停止。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-285">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
17. <span data-ttu-id="ce8d4-286">按一下下一個畫面上的 **[完成]** 。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-286">Click **Finish** on the next screen.</span></span>
    
18. <span data-ttu-id="ce8d4-287">現在，您可以發佈此更新的技術，並依照[商務用 Skype Server 中部署邊緣](deploy-edge-servers.md)伺服器中的指示，從這裡部署到您的 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-287">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
## <a name="publish-your-edge-server-topology"></a><span data-ttu-id="ce8d4-288">發佈 Edge 伺服器拓撲</span><span class="sxs-lookup"><span data-stu-id="ce8d4-288">Publish your Edge Server topology</span></span>

<span data-ttu-id="ce8d4-289">完成上述步驟後，就可以發佈這個新的拓朴，這也會讓您將它匯出到商務用 Skype Server Edge 伺服器或 Edge 池。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-289">Once you've finished the steps above, it's time to publish this new topology, which will also allow you to export it to your Skype for Business Server Edge Server or Edge pool.</span></span> <span data-ttu-id="ce8d4-290">請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="ce8d4-290">Follow these steps:</span></span>
  
1. <span data-ttu-id="ce8d4-291">啟動**拓撲**建立器（如果尚未從上一個程式開始）。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-291">Start **Topology Builder** (if it's not started already from the previous procedure).</span></span>
    
2. <span data-ttu-id="ce8d4-292">在**拓撲**建立器中，于主控台樹狀結構中，以滑鼠右鍵按一下 [**商務用 skype 伺服器**]，然後按一下 [**商務用 skype server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-292">In **Topology Builder**, in the console tree, right-click **Skype for Business Server** and then click **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="ce8d4-293">在嚮導的 [**歡迎**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-293">On the **Welcome** page of the wizard, click **Next**.</span></span>
    
4. <span data-ttu-id="ce8d4-294">在 [**建立其他資料庫**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-294">On the **Create other databases** page, click **Next**.</span></span>
    
5. <span data-ttu-id="ce8d4-295">當狀態指出資料庫建立成功時，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ce8d4-295">When the status indicates that the database creation succeeded, do the following:</span></span>
    
    - <span data-ttu-id="ce8d4-296">若要查看記錄，請按一下 [**查看記錄**]。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-296">To view the log, click **View log**.</span></span>
    
    - <span data-ttu-id="ce8d4-297">若要關閉嚮導，請按一下 **[完成**]。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-297">To close the wizard, click **Finish**.</span></span>
    
## <a name="export-your-edge-server-topology"></a><span data-ttu-id="ce8d4-298">匯出邊緣伺服器拓撲</span><span class="sxs-lookup"><span data-stu-id="ce8d4-298">Export your Edge Server topology</span></span>

<span data-ttu-id="ce8d4-299">若要成功部署，商務用 Skype Server 部署嚮導需要存取中央管理儲存區資料。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-299">To deploy successfully, the Skype for Business Server Deployment Wizard needs access to the Central Management store data.</span></span> <span data-ttu-id="ce8d4-300">對於網域或樹林中的內部伺服器來說，這通常相當簡單。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-300">For internal servers in your domain or forest, this typically is straightforward.</span></span> <span data-ttu-id="ce8d4-301">Edge 伺服器位於網域以外，因此您必須手動將拓撲檔案匯出到 Edge 伺服器位置，通常是在物理媒體上。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-301">Edge Servers are outside of the domain, and so it's necessary to manually export the topology file to the Edge Server location, usually on a physical media.</span></span> <span data-ttu-id="ce8d4-302">此匯出是透過 PowerShell 完成：</span><span class="sxs-lookup"><span data-stu-id="ce8d4-302">This export is done via PowerShell:</span></span>
  
1. <span data-ttu-id="ce8d4-303">啟動**商務用 Skype Server 管理命令**介面。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-303">Start the **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ce8d4-304">在**商務用 Skype Server Management 命令**介面中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ce8d4-304">In the **Skype for Business Server Management Shell**, run the following:</span></span>
    
   ```powershell
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. <span data-ttu-id="ce8d4-305">將匯出的檔案複製到外部媒體（例如，您可以從邊緣伺服器位置存取的 USB 磁片磁碟機或網路共用）。</span><span class="sxs-lookup"><span data-stu-id="ce8d4-305">Copy the exported file to external media (for example, a USB drive or network share that you can reach from the Edge Server's location).</span></span>
    

