---
title: 設定同盟路由與媒體流量
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 同盟是兩個或兩個以上 SIP 網域間的信任關係，其可允許不同組織中的使用者跨越網路界限進行通訊。 遷移至試驗集區之後，您必須從舊版 Edge Server 的同盟路由轉換為商務用 Skype Server 2019 Edge Server 的同盟路由。
ms.openlocfilehash: 2fafe991b8d09a477d084bdf2081d240e4830589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754033"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="0f63a-104">設定同盟路由與媒體流量</span><span class="sxs-lookup"><span data-stu-id="0f63a-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="0f63a-105">同盟是兩個或兩個以上 SIP 網域間的信任關係，其可允許不同組織中的使用者跨越網路界限進行通訊。</span><span class="sxs-lookup"><span data-stu-id="0f63a-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="0f63a-106">遷移至試驗集區之後，您必須從舊版之 Edge Server 的同盟路由轉換為商務用 Skype Server 2019 Edge Server 的同盟路由。</span><span class="sxs-lookup"><span data-stu-id="0f63a-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="0f63a-107">請使用下列程式，將舊版之 Edge Server 和 Director 的同盟路由與媒體流量路由轉換為商務用 Skype Server 2019 Edge Server，以進行單一網站部署。</span><span class="sxs-lookup"><span data-stu-id="0f63a-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0f63a-108">變更同盟路由與媒體流量路由需要您為商務用 Skype Server 2019 和舊版 Edge server 排程維護停機時間。</span><span class="sxs-lookup"><span data-stu-id="0f63a-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="0f63a-109">這整個轉換過程同時也意味著，在運行中斷期間無法使用同盟存取。</span><span class="sxs-lookup"><span data-stu-id="0f63a-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="0f63a-110">您應該將停機時間排在您預期使用者活動最少的時間。</span><span class="sxs-lookup"><span data-stu-id="0f63a-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="0f63a-111">您也應該要提供足夠的通知給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="0f63a-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="0f63a-112">請視情況規劃此運行中斷，並且在組織內設定適當的期望。</span><span class="sxs-lookup"><span data-stu-id="0f63a-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="0f63a-113">如果舊版 Edge Server 設定為使用「Access Edge service」、「Web 會議 Edge service」和「A/V Edge service」的相同 FQDN，則不支援本節中的程式。</span><span class="sxs-lookup"><span data-stu-id="0f63a-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="0f63a-114">如果舊版 Edge service 設定為使用相同的 FQDN，您必須先遷移所有的使用者，然後在啟用商務用 Skype Server 2019 Edge Server 上的同盟之前，解除舊版 Edge Server 的授權。</span><span class="sxs-lookup"><span data-stu-id="0f63a-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="0f63a-115">如果您的 XMPP 同盟是透過商務用 Skype Server 2019 Edge Server 路由傳送，舊版的使用者將無法與 XMPP 同盟協力廠商通訊，除非所有使用者都已移至商務用 Skype Server 2019、已設定 XMPP 原則和憑證，但已在商務用 Skype Server 2019 上設定 XMPP 同盟協力廠商。和，最後，已更新 DNS 專案。</span><span class="sxs-lookup"><span data-stu-id="0f63a-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="0f63a-116">從商務用 Skype Server 2019 網站移除舊版同盟關聯</span><span class="sxs-lookup"><span data-stu-id="0f63a-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="0f63a-117">在商務用 Skype Server 2019 前端伺服器上，在拓撲產生器中開啟現有的拓撲。</span><span class="sxs-lookup"><span data-stu-id="0f63a-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="0f63a-118">在左窗格中，流覽至網站節點，該節點直接位於商務用**Skype Server**。</span><span class="sxs-lookup"><span data-stu-id="0f63a-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="0f63a-119">以滑鼠右鍵按一下站台，然後按一下 [編輯屬性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f63a-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="0f63a-120">在左窗格中，選取 [**同盟路由**]。</span><span class="sxs-lookup"><span data-stu-id="0f63a-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="0f63a-121">在 [**網站同盟路由指派**] 底下，清除 [**啟用 SIP 同盟**] 核取方塊，以停用透過舊版環境的同盟路由。</span><span class="sxs-lookup"><span data-stu-id="0f63a-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="0f63a-122">按一下 [確定]\*\*\*\*，以關閉 [編輯屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="0f63a-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="0f63a-123">從 [**拓撲**產生器] 中，選取上方節點的**商務用 Skype 伺服器**。</span><span class="sxs-lookup"><span data-stu-id="0f63a-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="0f63a-124">從 [**動作**] 功能表中，按一下 [**發行拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="0f63a-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="0f63a-125">按 **[下一步]** 完成發佈程式，然後在發佈程式完成時按一下 **[完成]** 。</span><span class="sxs-lookup"><span data-stu-id="0f63a-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="0f63a-126">將舊版 Edge Server 設定成非同盟 Edge Server</span><span class="sxs-lookup"><span data-stu-id="0f63a-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="0f63a-127">在左窗格中，流覽至 [舊版安裝] 節點，然後流覽至 [ **Edge**集區] 節點。</span><span class="sxs-lookup"><span data-stu-id="0f63a-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="0f63a-128">以滑鼠右鍵按一下 Edge server，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="0f63a-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="0f63a-129">在左窗格中選取 **[一般**]。</span><span class="sxs-lookup"><span data-stu-id="0f63a-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="0f63a-130">清除 [**啟用此 Edge 集區的同盟（埠5061）** ] 核取方塊，然後選取 **[確定]** 以關閉頁面。</span><span class="sxs-lookup"><span data-stu-id="0f63a-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="0f63a-131">從 [**動作**] 功能表中，選取 [**發行拓撲**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="0f63a-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="0f63a-132">當 [發行精靈]\*\*\*\* 完成之後，按一下 [完成]\*\*\*\*，以關閉精靈。</span><span class="sxs-lookup"><span data-stu-id="0f63a-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="0f63a-133">確認已在拓撲產生器中停用舊版 Edge server 的同盟。</span><span class="sxs-lookup"><span data-stu-id="0f63a-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="0f63a-134">在舊版 Edge Server 上設定憑證</span><span class="sxs-lookup"><span data-stu-id="0f63a-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="0f63a-135">從舊版 Edge Server 匯出外部存取 Proxy 憑證與私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="0f63a-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="0f63a-136">在商務用 Skype Server 2019 Edge Server 上，然後匯入上一個步驟的 Access Proxy 外部憑證。</span><span class="sxs-lookup"><span data-stu-id="0f63a-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="0f63a-137">將 Access Proxy 外部憑證指派給 Edge Server 的商務用 Skype Server 2019 外部介面。</span><span class="sxs-lookup"><span data-stu-id="0f63a-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="0f63a-138">商務用 Skype Server 2019 Edge Server 的內部介面憑證應從信任的 CA 要求並被指派。</span><span class="sxs-lookup"><span data-stu-id="0f63a-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="0f63a-139">若要變更先前版本的同盟路由，以使用商務用 Skype Server 2019 Edge Server</span><span class="sxs-lookup"><span data-stu-id="0f63a-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="0f63a-140">在 [拓撲產生器] 的左窗格中，流覽至 [**商務用 Skype 伺服器 2019** ] 節點，然後流覽至 [ **Edge**集區] 節點。</span><span class="sxs-lookup"><span data-stu-id="0f63a-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="0f63a-141">以滑鼠右鍵按一下 Edge server，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="0f63a-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="0f63a-142">在左窗格中選取 **[一般**]。</span><span class="sxs-lookup"><span data-stu-id="0f63a-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="0f63a-143">選取 [**啟用此 Edge 集區的同盟（埠5061）**] 核取方塊，然後按一下 **[確定]** 以關閉頁面。</span><span class="sxs-lookup"><span data-stu-id="0f63a-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="0f63a-144">從 [**動作**] 功能表中，選取 [**發行拓撲**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="0f63a-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="0f63a-145">當 [發行精靈]\*\*\*\* 完成之後，按一下 [完成]\*\*\*\*，以關閉精靈。</span><span class="sxs-lookup"><span data-stu-id="0f63a-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="0f63a-146">確認已在拓撲產生器中將**同盟（埠5061）** 設為 [**已啟用**]。</span><span class="sxs-lookup"><span data-stu-id="0f63a-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="0f63a-147">更新商務用 Skype Server 2019 Edge Server 同盟的下一個躍點</span><span class="sxs-lookup"><span data-stu-id="0f63a-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="0f63a-148">在 [拓撲產生器] 的左窗格中，流覽至 [**商務用 Skype 伺服器 2019** ] 節點，然後流覽至 [ **Edge**集區] 節點。</span><span class="sxs-lookup"><span data-stu-id="0f63a-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="0f63a-149">展開節點，再以滑鼠右鍵按一下所列出的 Edge Server，然後按一下 [編輯屬性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f63a-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="0f63a-150">在 [**一般**] 頁面的 **[下一個躍點選取範圍]** 下，從下拉式清單中選取 [商務用 Skype 伺服器2019集區]。</span><span class="sxs-lookup"><span data-stu-id="0f63a-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="0f63a-151">按一下 [確定]\*\*\*\*，以關閉 [編輯屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="0f63a-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="0f63a-152">從 [**拓撲**產生器] 中，選取上方節點的**商務用 Skype 伺服器**。</span><span class="sxs-lookup"><span data-stu-id="0f63a-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="0f63a-153">從 [**動作**] 功能表中，按一下 [**發行拓撲**]，然後完成嚮導。</span><span class="sxs-lookup"><span data-stu-id="0f63a-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="0f63a-154">設定商務用 Skype Server 2019 Edge Server 輸出媒體路徑</span><span class="sxs-lookup"><span data-stu-id="0f63a-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="0f63a-155">在 [拓撲產生器] 的左窗格中，流覽至 [**商務用 Skype 伺服器 2019** ] 節點，然後流覽至 [ **Standard edition 前端伺服器**] 或 [ **Enterprise edition 前端**集區] 底下的集區。</span><span class="sxs-lookup"><span data-stu-id="0f63a-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="0f63a-156">以滑鼠右鍵按一下集區，然後按一下 [編輯屬性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f63a-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="0f63a-157">選取 [關聯]\*\*\*\* 區段底下的 [關聯 Edge 集區 (適用於媒體元件)]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="0f63a-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="0f63a-158">從下拉式清單方塊中，選取商務用 Skype Server 2019 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="0f63a-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="0f63a-159">按一下 [確定]\*\*\*\* 關閉 [編輯內容]\*\*\*\* 頁面。</span><span class="sxs-lookup"><span data-stu-id="0f63a-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="0f63a-160">開啟商務用 Skype Server 2019 Edge Server federation</span><span class="sxs-lookup"><span data-stu-id="0f63a-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="0f63a-161">在 [拓撲產生器] 的左窗格中，流覽至 [**商務用 Skype 伺服器 2019** ] 節點，然後流覽至 [ **Edge**集區] 節點。</span><span class="sxs-lookup"><span data-stu-id="0f63a-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="0f63a-162">展開節點，再以滑鼠右鍵按一下所列出的 Edge Server，然後按一下 [編輯屬性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f63a-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="0f63a-163">只可對單一 Edge 集區啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="0f63a-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="0f63a-164">如果您有多個 Edge 集區，請選取其中一個做為同盟 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="0f63a-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="0f63a-165">在 [**一般**] 頁面上，確認已選取 [**啟用此 Edge 集區的同盟（埠5061）** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="0f63a-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="0f63a-166">按一下 [確定]\*\*\*\*，以關閉 [編輯屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="0f63a-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="0f63a-167">流覽至網站節點。</span><span class="sxs-lookup"><span data-stu-id="0f63a-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="0f63a-168">以滑鼠右鍵按一下站台，然後按一下 [編輯屬性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f63a-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="0f63a-169">在左窗格中，按一下 [同盟路由]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f63a-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="0f63a-170">在 [**網站同盟路由指派**] 底下，選取 [**啟用 SIP 同盟**]，然後從清單中選取所列的商務用 Skype server 2019 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="0f63a-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="0f63a-171">按一下 **[確定]** 關閉 **[編輯內容]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="0f63a-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="0f63a-172">如有部署多個站台，請逐一在各個站台上完成此程序。</span><span class="sxs-lookup"><span data-stu-id="0f63a-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="0f63a-173">發行 Edge Server 的設定變更</span><span class="sxs-lookup"><span data-stu-id="0f63a-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="0f63a-174">從 [**拓撲**產生器] 中，選取上方節點的**商務用 Skype 伺服器**。</span><span class="sxs-lookup"><span data-stu-id="0f63a-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="0f63a-175">從 [動作]\*\*\*\* 功能表中，選取 [發行拓撲]\*\*\*\*，然後完成精靈。</span><span class="sxs-lookup"><span data-stu-id="0f63a-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="0f63a-176">等候部署中所有集區的 Active Directory 複寫作業開始。</span><span class="sxs-lookup"><span data-stu-id="0f63a-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0f63a-177">您可能會看到下列訊息：**警告：此拓撲包含一個以上的同盟 Edge Server。這可能會在將產品遷移至較新版本的產品時發生。在此情況下，只有一部 Edge Server 會積極用於同盟。驗證外部 DNS SRV 記錄是否指向正確的 Edge Server。如果您想要將多個同盟 Edge Server 同時部署為作用中（即不是遷移案例），請確認所有同盟夥伴皆使用商務用 Skype 伺服器。驗證外部 DNS SRV 記錄是否列出所有啟用同盟的 Edge Server。**</span><span class="sxs-lookup"><span data-stu-id="0f63a-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="0f63a-178">此為預期中的警告，可以不予理會。</span><span class="sxs-lookup"><span data-stu-id="0f63a-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="0f63a-179">設定商務用 Skype Server 2019 Edge Server</span><span class="sxs-lookup"><span data-stu-id="0f63a-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="0f63a-180">讓所有商務用 Skype Server 2019 Edge Server 線上。</span><span class="sxs-lookup"><span data-stu-id="0f63a-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="0f63a-181">更新外部防火牆路由規則或硬體負載平衡器設定，以將外部存取（通常是埠443）及同盟（通常是埠5061）的 SIP 流量傳送到商務用 Skype Server 2019 Edge Server，而不是舊版 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="0f63a-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0f63a-182">如果您沒有硬體負載平衡器，您必須更新 DNS A 記錄的同盟，以解析為新的商務用 Skype Server Access Edge server。</span><span class="sxs-lookup"><span data-stu-id="0f63a-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="0f63a-183">若要以極少的中斷來達到此目的，請降低外部商務用 Skype Server Access Edge FQDN 的 TLL 值，以便在更新 DNS 以指向新的商務用 Skype Server Access Edge 時，會快速更新同盟和遠端存取。</span><span class="sxs-lookup"><span data-stu-id="0f63a-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="0f63a-184">從每一部 Edge Server 電腦停止**商務用 Skype Server Access Edge** 。</span><span class="sxs-lookup"><span data-stu-id="0f63a-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="0f63a-185">從每個舊版 Edge Server 電腦上，從 [系統**管理工具**] 中開啟 [**服務**] 小程式。</span><span class="sxs-lookup"><span data-stu-id="0f63a-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="0f63a-186">在 [服務] 清單中，尋找**商務用 Skype Server Access Edge**。</span><span class="sxs-lookup"><span data-stu-id="0f63a-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="0f63a-187">以滑鼠右鍵按一下服務名稱，然後選取 [停止]\*\*\*\* 停止服務。</span><span class="sxs-lookup"><span data-stu-id="0f63a-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="0f63a-188">將 [啟動類型] 設為 [停用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f63a-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="0f63a-189">按一下 [確定]\*\*\*\*，以關閉 [屬性]\*\*\*\* 視窗。</span><span class="sxs-lookup"><span data-stu-id="0f63a-189">Click **OK** to close the **Properties** window.</span></span> 
    

