---
title: 設定同盟路由及媒體流量
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 同盟是兩個或多個 SIP 網域之間的信任關係, 允許個別組織中的使用者在網路界限間進行通訊。 在您遷移到您的試用版池之後, 您必須從舊版 Edge 伺服器的同盟路由轉換到商務用 Skype Server 2019 Edge 伺服器的同盟路由。
ms.openlocfilehash: 6b76932c8b988dbed61cba1470f32a51f6585536
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193077"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="e8cf1-104">設定同盟路由及媒體流量</span><span class="sxs-lookup"><span data-stu-id="e8cf1-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="e8cf1-105">同盟是兩個或多個 SIP 網域之間的信任關係, 允許個別組織中的使用者在網路界限間進行通訊。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="e8cf1-106">在您遷移到您的試驗池之後, 您必須從先前版本的邊緣伺服器的同盟路由轉移到商務用 Skype Server 2019 Edge 伺服器的同盟路由。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="e8cf1-107">您可以使用下列程式, 將同盟路由及媒體流量路由從舊版的 Edge 伺服器與控制器轉換成商務用 Skype Server 2019 Edge 伺服器 (針對單一網站部署)。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e8cf1-108">變更同盟路由和媒體流量路由時, 需要您針對商務用 Skype Server 2019 和舊版 Edge 伺服器排程維護時間。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="e8cf1-109">此整個轉換程式也表示在停用期間將無法使用聯盟存取。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="e8cf1-110">您應該將停機時間排程為預期最少的使用者活動。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="e8cf1-111">您也應該為您的最終使用者提供足夠的通知。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="e8cf1-112">針對此中斷進行規劃, 並在您的組織中設定適當的預期。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="e8cf1-113">如果您的舊版 Edge 伺服器已設定為使用相同的 FQDN 來存取邊緣服務、網路會議邊緣服務以及 A/V 邊緣服務, 則不支援本節中的程式。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="e8cf1-114">如果舊版 Edge 服務設定為使用相同的 FQDN, 您必須先遷移所有的使用者, 然後在商務用 Skype Server 2019 Edge 伺服器上啟用同盟之後, 再解除舊版 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="e8cf1-115">如果您的 XMPP 同盟是透過商務用 Skype Server 2019 Edge 伺服器路由, 前一版的使用者將無法與 XMPP 聯盟合作夥伴通訊, 除非已將所有使用者移至商務用 Skype Server 2019、XMPP 原則以及已設定憑證之後, 已在商務用 Skype Server 2019 上設定 XMPP 聯盟合作夥伴, 最後再更新 DNS 專案。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="e8cf1-116">若要從商務用 Skype Server 2019 網站移除舊版同盟關聯</span><span class="sxs-lookup"><span data-stu-id="e8cf1-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="e8cf1-117">在商務用 Skype Server 2019 前端伺服器上, 在 [拓撲產生器] 中開啟現有的拓撲。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="e8cf1-118">在左窗格中, 流覽至位於 [**商務用 Skype] 伺服器**正下方的 [網站] 節點。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="e8cf1-119">以滑鼠右鍵按一下網站, 然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="e8cf1-120">在左窗格中, 選取 [**同盟路由**]。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="e8cf1-121">在 [**網站同盟路由指派**] 下, 清除 [**啟用 SIP 同盟**] 核取方塊, 以停用同盟路由與舊版環境。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="e8cf1-122">按一下 **[確定]** 以關閉 [編輯屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="e8cf1-123">從 [**拓撲**建立器] 中, 選取 [頂層節點**商務用 Skype Server**]。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="e8cf1-124">從 [**動作**] 功能表中, 按一下 [**發佈拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="e8cf1-125">按一下 **[下一步**] 完成發佈程式, 然後在發佈程式完成時按一下 **[完成]** 。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="e8cf1-126">將舊版 Edge 伺服器設定為非聯盟邊緣伺服器</span><span class="sxs-lookup"><span data-stu-id="e8cf1-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="e8cf1-127">在左窗格中, 流覽至 [舊版安裝] 節點, 然後流覽至 [**邊緣池**] 節點。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="e8cf1-128">以滑鼠右鍵按一下邊緣伺服器, 然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="e8cf1-129">在左窗格中選取 **[一般**]。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="e8cf1-130">清除 [**針對此 Edge 池啟用同盟 (埠 5061)** ] 核取方塊, 然後選取 **[確定]** 以關閉頁面。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="e8cf1-131">從 [**動作**] 功能表中, 選取 [**發佈拓撲**], 然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="e8cf1-132">**發佈嚮導**完成後, 請按一下 **[完成**] 以關閉嚮導。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="e8cf1-133">確認 [拓撲建立器] 中已停用舊版 Edge 伺服器的同盟。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="e8cf1-134">在舊版 Edge 伺服器上設定憑證</span><span class="sxs-lookup"><span data-stu-id="e8cf1-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="e8cf1-135">從舊版 Edge 伺服器匯出外部存取 Proxy 證書與私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="e8cf1-136">在商務用 Skype Server 2019 Edge 伺服器上, 然後匯入上一個步驟的 [存取 Proxy 外部憑證]。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="e8cf1-137">將存取 Proxy 外部憑證指派給 Edge 伺服器的商務用 Skype Server 2019 外部介面。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="e8cf1-138">商務用 Skype Server 2019 Edge 伺服器的內部介面憑證應該從信任的 CA 要求並加以指派。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="e8cf1-139">若要將先前版本的同盟路由變更為使用商務用 Skype Server 2019 Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="e8cf1-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="e8cf1-140">從拓撲建立器, 在左窗格中, 流覽至**商務用 Skype Server 2019**節點, 然後移至 [**邊緣池**] 節點。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="e8cf1-141">以滑鼠右鍵按一下邊緣伺服器, 然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="e8cf1-142">在左窗格中選取 **[一般**]。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="e8cf1-143">選取 [針對**此 Edge 池啟用同盟 (埠 5061)**] 的核取方塊, 然後按一下 **[確定]** 以關閉頁面。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="e8cf1-144">從 [**動作**] 功能表中, 選取 [**發佈拓撲**], 然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="e8cf1-145">**發佈嚮導**完成後, 請按一下 **[完成**] 以關閉嚮導。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="e8cf1-146">確認 **[同盟 (埠 5061)** ] 已設定\*\*\*\* 為 [拓撲建立器]。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="e8cf1-147">更新商務用 Skype Server 2019 Edge 伺服器同盟下一個躍點</span><span class="sxs-lookup"><span data-stu-id="e8cf1-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="e8cf1-148">從拓撲建立器, 在左窗格中, 流覽至**商務用 Skype Server 2019**節點, 然後移至 [**邊緣池**] 節點。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="e8cf1-149">展開節點, 以滑鼠右鍵按一下列出的邊緣伺服器, 然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="e8cf1-150">在 [**一般**] 頁面上的 **[下一個躍點選取範圍]** 底下, 從下拉式清單中選取 [商務用 Skype Server 2019] 池。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="e8cf1-151">按一下 **[確定]** 以關閉 [編輯屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="e8cf1-152">從 [**拓撲**建立器] 中, 選取 [頂層節點**商務用 Skype Server**]。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="e8cf1-153">從 [**動作**] 功能表中, 按一下 [**發佈拓撲**] 並完成嚮導。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="e8cf1-154">若要設定商務用 Skype Server 2019 Edge 伺服器輸出媒體路徑</span><span class="sxs-lookup"><span data-stu-id="e8cf1-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="e8cf1-155">從 [拓撲建立器], 在左窗格中, 流覽至 [**商務用 Skype Server 2019** ] 節點, 然後移至 [**標準版] 前端伺服器**或 [**企業版] 前端池**的 [池]。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="e8cf1-156">以滑鼠右鍵按一下該池子, 然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="e8cf1-157">在 [**關聯**性] 區段中, 選取 [**關聯邊緣池 (適用于媒體元件)** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="e8cf1-158">從下拉式方塊中, 選取 [商務用 Skype Server 2019 Edge 伺服器]。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="e8cf1-159">按一下 **[確定]** 以關閉 [**編輯屬性**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="e8cf1-160">開啟商務用 Skype Server 2019 Edge 伺服器同盟</span><span class="sxs-lookup"><span data-stu-id="e8cf1-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="e8cf1-161">從拓撲建立器, 在左窗格中, 流覽至**商務用 Skype Server 2019**節點, 然後移至 [**邊緣池**] 節點。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="e8cf1-162">展開節點, 以滑鼠右鍵按一下列出的邊緣伺服器, 然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e8cf1-163">只有單一邊緣池才能啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="e8cf1-164">如果您有多個邊緣池, 請選取一個, 以做為聯盟邊界池。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="e8cf1-165">在 [**一般**] 頁面上, 確認已選取 [**針對此 Edge 池啟用同盟 (埠 5061)** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="e8cf1-166">按一下 **[確定]** 以關閉 [編輯屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="e8cf1-167">流覽至 [網站] 節點。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="e8cf1-168">以滑鼠右鍵按一下網站, 然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="e8cf1-169">在左窗格中, 按一下 [**同盟路由**]。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="e8cf1-170">在 [**網站同盟路由指派**] 底下, 選取 [**啟用 SIP 同盟**], 然後從清單中選取 [商務用 Skype server 2019 Edge 伺服器]。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="e8cf1-171">按一下 **[確定]** 以關閉 [**編輯屬性**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="e8cf1-172">針對多網站部署, 請在每個網站完成此程式。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="e8cf1-173">發佈 Edge 伺服器設定變更</span><span class="sxs-lookup"><span data-stu-id="e8cf1-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="e8cf1-174">從 [**拓撲**建立器] 中, 選取 [頂層節點**商務用 Skype Server**]。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="e8cf1-175">從 [**動作**] 功能表中, 選取 [**發佈拓撲**] 並完成嚮導。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="e8cf1-176">等到對部署中的所有池進行 Active Directory 複製。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e8cf1-177">您可能會看到下列訊息:**警告: 拓撲包含一個以上的同盟邊緣伺服器。在遷移到較新版產品的過程中, 可能會發生這種情況。在這種情況下, 只有一台邊緣伺服器會主動用於同盟。確認外部 DNS SRV 記錄指向正確的邊緣伺服器。如果您想要將多個同盟邊緣伺服器部署成同時作用 (也就是不是遷移案例), 請確認所有聯盟夥伴都使用商務用 Skype 伺服器。確認外部 DNS SRV 記錄列出所有啟用同盟的 Edge 伺服器。**</span><span class="sxs-lookup"><span data-stu-id="e8cf1-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="e8cf1-178">此為預期警告, 且可以放心地忽略。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="e8cf1-179">若要設定商務用 Skype Server 2019 Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="e8cf1-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="e8cf1-180">將所有商務用 Skype Server 2019 Edge 伺服器連線。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="e8cf1-181">更新外部防火牆路由規則或硬體負載平衡器設定, 以將外部存取 (通常是埠 443) 和同盟 (通常是埠 5061) 的 SIP 流量傳送到商務用 Skype Server 2019 Edge 伺服器, 而不是舊版 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e8cf1-182">如果您沒有硬體負載平衡器, 您需要更新同盟的 DNS A 記錄, 以解析為新的商務用 Skype Server 存取邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="e8cf1-183">若要以最小的中斷來完成這項作業, 請減少外部商務用 Skype Server 存取邊緣 FQDN 的 TLL 值, 讓 DNS 更新為指向新的商務用 Skype Server 存取邊緣、同盟和遠端存取將會很快更新。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="e8cf1-184">停止每個 Edge 伺服器電腦上的**商務用 Skype Server 存取邊緣**。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="e8cf1-185">從每個舊版 Edge 伺服器電腦, 從 [**管理工具**] 開啟 [**服務**] 小工具。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="e8cf1-186">在 [服務] 清單中, 尋找**商務用 Skype Server 存取邊緣**。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="e8cf1-187">以滑鼠右鍵按一下服務名稱, 然後選取 [**停止**] 停止服務。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="e8cf1-188">將啟動類型設定為 [**停用**]。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="e8cf1-189">按一下 **[確定**] 以關閉 [**屬性**] 視窗。</span><span class="sxs-lookup"><span data-stu-id="e8cf1-189">Click **OK** to close the **Properties** window.</span></span> 
    

