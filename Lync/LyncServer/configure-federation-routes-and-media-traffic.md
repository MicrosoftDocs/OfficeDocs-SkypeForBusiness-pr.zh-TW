---
title: 設定同盟路由與媒體流量
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b07e0bfe62fe6d09521d1f9d5dc2d84aa975d5e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503350"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="55ed6-102">設定同盟路由與媒體流量</span><span class="sxs-lookup"><span data-stu-id="55ed6-102">Configure federation routes and media traffic</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55ed6-103">_**主題上次修改日期：** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="55ed6-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="55ed6-104">同盟是兩個或兩個以上 SIP 網域間的信任關係，其可允許不同組織中的使用者跨越網路界限進行通訊。</span><span class="sxs-lookup"><span data-stu-id="55ed6-104">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="55ed6-105">遷移至 Lync Server 2013 試驗集區之後，您必須從 Lync server 2010 Edge server 的同盟路由轉換為您的 Lync Server 2013 Edge server 的同盟路由。</span><span class="sxs-lookup"><span data-stu-id="55ed6-105">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Lync Server 2010 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="55ed6-106">請使用下列程式，將 Lync Server 2010 Edge Server 和 Director 的同盟路由與媒體流量路由轉換至 Lync Server 2013 Edge Server，以進行單一網站部署。</span><span class="sxs-lookup"><span data-stu-id="55ed6-106">Use the following procedures to transition the federation route and the media traffic route from your Lync Server 2010 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="55ed6-107">變更同盟路由與媒體流量路由需要您為 Lync Server 2013 和 Lync Server 2010 Edge Server 排定維護停機時間。</span><span class="sxs-lookup"><span data-stu-id="55ed6-107">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Lync Server 2010 Edge Servers.</span></span> <span data-ttu-id="55ed6-108">這整個轉換過程同時也意味著，在運行中斷期間無法使用同盟存取。</span><span class="sxs-lookup"><span data-stu-id="55ed6-108">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="55ed6-109">您應該將停機時間排在您預期使用者活動最少的時間。</span><span class="sxs-lookup"><span data-stu-id="55ed6-109">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="55ed6-110">您也應該要提供足夠的通知給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="55ed6-110">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="55ed6-111">請視情況規劃此運行中斷，並且在組織內設定適當的期望。</span><span class="sxs-lookup"><span data-stu-id="55ed6-111">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="55ed6-112">如果舊版 Lync Server 2010 Edge Server 設定為使用 Access Edge service、Web 會議 Edge service 和 A/V Edge service 的相同 FQDN，則不支援本節中的程式。</span><span class="sxs-lookup"><span data-stu-id="55ed6-112">If your legacy Lync Server 2010 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="55ed6-113">如果舊版 Edge service 設定為使用相同的 FQDN，您必須先將所有使用者從 Lync Server 2010 遷移至 Lync Server 2013，然後在 2013 Lync server 的 [！] Edge Server 上啟用同盟之前解除委任 Lync Server 2010 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="55ed6-113">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Lync Server 2010 to Lync Server 2013, then decommission the Lync Server 2010 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="55ed6-114">如果您的 XMPP 同盟是透過 Lync Server 2013 Edge Server 路由傳送，舊版 Lync Server 2010 使用者將無法與 XMPP 同盟協力廠商通訊，除非所有使用者都已移至 Lync Server 2013、已設定 XMPP 原則和憑證，所以已在 Lync Server 2013 上設定 XMPP 同盟協力廠商，最後更新 DNS 專案。</span><span class="sxs-lookup"><span data-stu-id="55ed6-114">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Lync Server 2010 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="55ed6-115">從 Lync Server 2013 網站移除舊版同盟關聯</span><span class="sxs-lookup"><span data-stu-id="55ed6-115">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="55ed6-116">在 Lync Server 2013 前端伺服器上，在拓撲產生器中開啟現有的拓撲。</span><span class="sxs-lookup"><span data-stu-id="55ed6-116">On the Lync Server 2013 Front End server, open the existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="55ed6-117">在左窗格中，流覽至 [ **Lync Server**] 正下方的 [網站] 節點。</span><span class="sxs-lookup"><span data-stu-id="55ed6-117">In the left pane, navigate to the site node, which is located directly below **Lync Server**.</span></span>

3.  <span data-ttu-id="55ed6-118">以滑鼠右鍵按一下網站，然後按一下 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="55ed6-118">Right-click the site and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="55ed6-119">在左窗格中，選取 [ **同盟路由**]。</span><span class="sxs-lookup"><span data-stu-id="55ed6-119">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="55ed6-120">在 [ **網站同盟路由指派**] 底下，清除 [ **啟用 SIP 同盟** ] 核取方塊，以停用透過舊版 Lync Server 2010 環境的同盟路由。</span><span class="sxs-lookup"><span data-stu-id="55ed6-120">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy Lync Server 2010 environment.</span></span>
    
    <span data-ttu-id="55ed6-121">![[編輯屬性] 對話方塊，[同盟路由] 頁面](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "[編輯屬性] 對話方塊，[同盟路由] 頁面")</span><span class="sxs-lookup"><span data-stu-id="55ed6-121">![Edit Properties dialog, Federation route page](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>

6.  <span data-ttu-id="55ed6-122">按一下 [確定]\*\*\*\*，以關閉 [編輯屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="55ed6-122">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="55ed6-123">從 [ **拓撲**產生器] 中，選取上方節點 [ **Lync Server**]。</span><span class="sxs-lookup"><span data-stu-id="55ed6-123">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="55ed6-124">從 [ **動作** ] 功能表中，按一下 [ **發行拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="55ed6-124">From the **Action** menu, click **Publish Topology**.</span></span>

9.  <span data-ttu-id="55ed6-125">按 **[下一步]** 完成發佈程式，然後在發佈程式完成時按一下 **[完成]** 。</span><span class="sxs-lookup"><span data-stu-id="55ed6-125">Click **Next** to complete the publishing process and then click **Finish** when the publishing process has completed.</span></span>

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="55ed6-126">將舊版 Edge Server 設定成非同盟 Edge Server</span><span class="sxs-lookup"><span data-stu-id="55ed6-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="55ed6-127">在左窗格中，流覽至 [ **Lync Server 2010** ] 節點，然後流覽至 [ **Edge** 集區] 節點。</span><span class="sxs-lookup"><span data-stu-id="55ed6-127">In the left pane, navigate to the **Lync Server 2010** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="55ed6-128">以滑鼠右鍵按一下 Edge server，然後按一下 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="55ed6-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="55ed6-129">在左窗格中選取 **[一般** ]。</span><span class="sxs-lookup"><span data-stu-id="55ed6-129">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="55ed6-130">清除 [ \*\*啟用此 Edge 集區的同盟 (埠 5061) \*\* ] 核取方塊專案，然後選取 **[確定]** 以關閉頁面。</span><span class="sxs-lookup"><span data-stu-id="55ed6-130">Clear the **Enable federation for this Edge pool (port 5061)** check box entry and select **OK** to close the page.</span></span>
    
    <span data-ttu-id="55ed6-131">![編輯內容，一般，清除啟用同盟](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "編輯內容，一般，清除啟用同盟")</span><span class="sxs-lookup"><span data-stu-id="55ed6-131">![Edit Properties, General, clear Enable federation](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Edit Properties, General, clear Enable federation")</span></span>

5.  <span data-ttu-id="55ed6-132">從 [ **動作** ] 功能表中，選取 [ **發行拓撲**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="55ed6-132">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="55ed6-133">當 [發行精靈]\*\*\*\* 完成之後，按一下 [完成]\*\*\*\*，以關閉精靈。</span><span class="sxs-lookup"><span data-stu-id="55ed6-133">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="55ed6-134">驗證舊版 Edge server 的同盟功能已停用。</span><span class="sxs-lookup"><span data-stu-id="55ed6-134">Verify federation for the legacy Edge server is disabled.</span></span>
    
    <span data-ttu-id="55ed6-135">![拓撲產生器，Edge 集區，已停用同盟](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "拓撲產生器，Edge 集區，已停用同盟")</span><span class="sxs-lookup"><span data-stu-id="55ed6-135">![Topology Builder, Edge pool, federation disabled](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Topology Builder, Edge pool, federation disabled")</span></span>

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a><span data-ttu-id="55ed6-136">在 Lync Server 2010 Edge Server 上設定憑證</span><span class="sxs-lookup"><span data-stu-id="55ed6-136">To configure certificates on the Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="55ed6-137">從舊版 Lync Server 2010 Edge Server 匯出外部存取 Proxy 憑證及私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="55ed6-137">Export the external Access Proxy certificate, with the private key, from the legacy Lync Server 2010 Edge Server.</span></span>

2.  <span data-ttu-id="55ed6-138">在 Lync Server 2013 Edge Server 上，匯入上一個步驟中的 Access Proxy 外部憑證。</span><span class="sxs-lookup"><span data-stu-id="55ed6-138">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="55ed6-139">將 Access Proxy 外部憑證指派給 Edge Server 的 Lync Server 2013 外部介面。</span><span class="sxs-lookup"><span data-stu-id="55ed6-139">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="55ed6-140">Lync Server 2013 Edge Server 的內部介面憑證應從受信任的 CA 要求並被指派。</span><span class="sxs-lookup"><span data-stu-id="55ed6-140">The internal interface certificate of the Lync Server 2013 Edge Server should be requested from a trusted CA and assigned.</span></span>

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="55ed6-141">若要變更 Lync Server 2010 同盟路由以使用 Lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="55ed6-141">To change Lync Server 2010 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="55ed6-142">在 [拓撲產生器] 的左窗格中，流覽至 [ **Lync Server 2013** ] 節點，然後流覽至 [ **Edge** 集區] 節點。</span><span class="sxs-lookup"><span data-stu-id="55ed6-142">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="55ed6-143">以滑鼠右鍵按一下 Edge server，然後按一下 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="55ed6-143">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="55ed6-144">在左窗格中選取 **[一般** ]。</span><span class="sxs-lookup"><span data-stu-id="55ed6-144">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="55ed6-145">選取 [ \*\*啟用此 Edge 集 \*\* 區的同盟] 的核取方塊專案 (埠 5061) 然後按一下 **[確定]** 以關閉頁面。</span><span class="sxs-lookup"><span data-stu-id="55ed6-145">Select the check box entry for **Enable federation for this Edge pool (port 5061)** and then click **OK** to close the page.</span></span>
    
    <span data-ttu-id="55ed6-146">![[編輯屬性] 對話方塊，[一般] 頁面](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "[編輯屬性] 對話方塊，[一般] 頁面")</span><span class="sxs-lookup"><span data-stu-id="55ed6-146">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

5.  <span data-ttu-id="55ed6-147">從 [ **動作** ] 功能表中，選取 [ **發行拓撲**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="55ed6-147">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="55ed6-148">當 [發行精靈]\*\*\*\* 完成之後，按一下 [完成]\*\*\*\*，以關閉精靈。</span><span class="sxs-lookup"><span data-stu-id="55ed6-148">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="55ed6-149">驗證 \*\*同盟 (埠 5061) \*\* 設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="55ed6-149">Verify **Federation (port 5061)** is set to **Enabled**.</span></span>
    
    <span data-ttu-id="55ed6-150">![拓撲產生器，Edge 集區，啟用同盟](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "拓撲產生器，Edge 集區，啟用同盟")</span><span class="sxs-lookup"><span data-stu-id="55ed6-150">![Topology Builder, Edge pool, Federation enabled](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Topology Builder, Edge pool, Federation enabled")</span></span>

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a><span data-ttu-id="55ed6-151">更新 Lync Server 2013 Edge Server 同盟的下一個躍點</span><span class="sxs-lookup"><span data-stu-id="55ed6-151">To update Lync Server 2013 Edge Server federation next hop</span></span>

1.  <span data-ttu-id="55ed6-152">在 [拓撲產生器] 的左窗格中，流覽至 [ **Lync Server 2013** ] 節點，然後流覽至 [ **Edge** 集區] 節點。</span><span class="sxs-lookup"><span data-stu-id="55ed6-152">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="55ed6-153">展開節點，再以滑鼠右鍵按一下所列出的 Edge Server，然後按一下 [編輯屬性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="55ed6-153">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="55ed6-154">在 [ **一般** ] 頁面的 **[下一個躍點選取範圍]** 下，從下拉式清單中選取 [Lync Server 2013 集區]。</span><span class="sxs-lookup"><span data-stu-id="55ed6-154">On the **General** page, under **Next hop selection**, select from the drop-down list the Lync Server 2013  pool.</span></span>
    
    <span data-ttu-id="55ed6-155">![[編輯屬性] 對話方塊，[下一個躍點] 頁面](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "[編輯屬性] 對話方塊，[下一個躍點] 頁面")</span><span class="sxs-lookup"><span data-stu-id="55ed6-155">![Edit Properties dialog, Next hop page](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Edit Properties dialog, Next hop page")</span></span>

4.  <span data-ttu-id="55ed6-156">按一下 [確定]\*\*\*\*，以關閉 [編輯屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="55ed6-156">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="55ed6-157">從 [ **拓撲**產生器] 中，選取上方節點 [ **Lync Server** ]。</span><span class="sxs-lookup"><span data-stu-id="55ed6-157">From **Topology Builder**, select the top node **Lync Server** .</span></span>

6.  <span data-ttu-id="55ed6-158">從 [ **動作** ] 功能表中，按一下 [ **發行拓撲** ]，然後完成嚮導。</span><span class="sxs-lookup"><span data-stu-id="55ed6-158">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="55ed6-159">設定 Lync Server 2013 Edge Server 輸出媒體路徑</span><span class="sxs-lookup"><span data-stu-id="55ed6-159">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="55ed6-160">在 [拓撲產生器] 的左窗格中，流覽至 [ **Lync Server 2013** ] 節點，然後流覽至 [ **Standard edition 前端伺服器** ] 或 [ **Enterprise edition 前端**集區] 底下的集區。</span><span class="sxs-lookup"><span data-stu-id="55ed6-160">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="55ed6-161">以滑鼠右鍵按一下集區，然後按一下 [編輯屬性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="55ed6-161">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="55ed6-162">選取 [關聯]\*\*\*\* 區段底下的 [關聯 Edge 集區 (適用於媒體元件)]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="55ed6-162">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>
    
    <span data-ttu-id="55ed6-163">![編輯內容，一般，關聯 Edge 集區](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "編輯內容，一般，關聯 Edge 集區")</span><span class="sxs-lookup"><span data-stu-id="55ed6-163">![Edit Properties, General, Associate Edge pool](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>

4.  <span data-ttu-id="55ed6-164">從下拉式清單方塊中，選取 [Lync Server 2013 Edge Server]。</span><span class="sxs-lookup"><span data-stu-id="55ed6-164">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>

5.  <span data-ttu-id="55ed6-165">按一下 [確定]\*\*\*\* 關閉 [編輯內容]\*\*\*\* 頁面。</span><span class="sxs-lookup"><span data-stu-id="55ed6-165">Click **OK** to close the **Edit Properties** page.</span></span>

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="55ed6-166">開啟 Lync Server 2013 Edge Server federation</span><span class="sxs-lookup"><span data-stu-id="55ed6-166">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="55ed6-167">在 [拓撲產生器] 的左窗格中，流覽至 [ **Lync Server 2013** ] 節點，然後流覽至 [ **Edge** 集區] 節點。</span><span class="sxs-lookup"><span data-stu-id="55ed6-167">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="55ed6-168">展開節點，再以滑鼠右鍵按一下所列出的 Edge Server，然後按一下 [編輯屬性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="55ed6-168">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="55ed6-169">只可對單一 Edge 集區啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="55ed6-169">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="55ed6-170">如果您有多個 Edge 集區，請選取其中一個做為同盟 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="55ed6-170">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>

    
    </div>

3.  <span data-ttu-id="55ed6-171">在 [ **一般** ] 頁面上，確認已選取 [ \*\*啟用此 Edge 集區的同盟 (埠 5061) \*\* 設定]。</span><span class="sxs-lookup"><span data-stu-id="55ed6-171">On the **General** page, verify the **Enable federation for this Edge pool (Port 5061)** setting is checked.</span></span>
    
    <span data-ttu-id="55ed6-172">![[編輯屬性] 對話方塊，[一般] 頁面](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "[編輯屬性] 對話方塊，[一般] 頁面")</span><span class="sxs-lookup"><span data-stu-id="55ed6-172">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

4.  <span data-ttu-id="55ed6-173">按一下 [確定]\*\*\*\*，以關閉 [編輯屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="55ed6-173">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="55ed6-174">然後，瀏覽至站台節點。</span><span class="sxs-lookup"><span data-stu-id="55ed6-174">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="55ed6-175">以滑鼠右鍵按一下站台，然後按一下 [編輯屬性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="55ed6-175">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="55ed6-176">在左窗格中，按一下 [同盟路由]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="55ed6-176">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="55ed6-177">在 [ **網站同盟路由指派**] 底下，選取 [ **啟用 SIP 同盟**]，然後從清單中選取所列的 Lync server 2013 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="55ed6-177">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>
    
    <span data-ttu-id="55ed6-178">![編輯屬性、同盟路由頁面](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "編輯屬性、同盟路由頁面")</span><span class="sxs-lookup"><span data-stu-id="55ed6-178">![Edit Properties, Federation route page](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Edit Properties, Federation route page")</span></span>

9.  <span data-ttu-id="55ed6-179">按一下 **[確定]** 關閉 **[編輯內容]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="55ed6-179">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="55ed6-180">如有部署多個站台，請逐一在各個站台上完成此程序。</span><span class="sxs-lookup"><span data-stu-id="55ed6-180">For multi-site deployments, complete this procedure at each site.</span></span>

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="55ed6-181">發行 Edge Server 的設定變更</span><span class="sxs-lookup"><span data-stu-id="55ed6-181">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="55ed6-182">從 [ **拓撲**產生器] 中，選取上方節點 [ **Lync Server** ]。</span><span class="sxs-lookup"><span data-stu-id="55ed6-182">From **Topology Builder**, select the top node **Lync Server** .</span></span>

2.  <span data-ttu-id="55ed6-183">從 [動作]\*\*\*\* 功能表中，選取 [發行拓撲]\*\*\*\*，然後完成精靈。</span><span class="sxs-lookup"><span data-stu-id="55ed6-183">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="55ed6-184">等候部署中所有集區的 Active Directory 複寫作業開始。</span><span class="sxs-lookup"><span data-stu-id="55ed6-184">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="55ed6-185">您將會見到下列訊息：</span><span class="sxs-lookup"><span data-stu-id="55ed6-185">You may see the following message:</span></span><BR><span data-ttu-id="55ed6-186"><STRONG>警告：此拓撲包含一個以上的同盟 Edge Server。這可能會在將產品遷移至較新版本的產品時發生。在此情況下，只有一部 Edge Server 會積極用於同盟。驗證外部 DNS SRV 記錄是否指向正確的 Edge Server。如果您想要將多個同盟 Edge Server 同時部署為作用中 (也就是說，不是遷移案例) ，請確認所有同盟協力廠商都在使用 Lync Server。驗證外部 DNS SRV 記錄是否列出所有啟用同盟的 Edge Server。</STRONG></span><span class="sxs-lookup"><span data-stu-id="55ed6-186"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="55ed6-187">此為預期中的警告，可以不予理會。</span><span class="sxs-lookup"><span data-stu-id="55ed6-187">This warning is expected and can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="55ed6-188">設定 Lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="55ed6-188">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="55ed6-189">讓所有的 Lync Server 2013 Edge server 線上。</span><span class="sxs-lookup"><span data-stu-id="55ed6-189">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="55ed6-190">更新外部防火牆路由規則或硬體負載平衡器設定，以傳送外部存取 (的 SIP 流量，通常是埠 443) 和同盟 (的埠 5061) 至 Lync Server 2013 Edge Server，而不是舊版 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="55ed6-190">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="55ed6-191">如果您沒有硬體負載平衡器，則需要更新同盟的 DNS A 記錄，以解析為新的 Lync Server Access Edge server。</span><span class="sxs-lookup"><span data-stu-id="55ed6-191">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Lync Server Access Edge server.</span></span> <span data-ttu-id="55ed6-192">若要達到最低的中斷，請縮小外部 Lync Server Access Edge FQDN 的 TLL 值，以便在更新 DNS 以指向新的 Lync Server Access Edge 時，會快速更新同盟和遠端存取。</span><span class="sxs-lookup"><span data-stu-id="55ed6-192">To accomplish this with minimum disruption, reduce the TLL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge, federation and remote access will be updated quickly.</span></span>

    
    </div>

3.  <span data-ttu-id="55ed6-193">接下來，停止每台 Edge Server 電腦的 **Lync Server Access Edge** 。</span><span class="sxs-lookup"><span data-stu-id="55ed6-193">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="55ed6-194">從每個舊版 Edge Server 電腦上，從 [系統**管理工具**] 中開啟 [**服務**] 小程式。</span><span class="sxs-lookup"><span data-stu-id="55ed6-194">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="55ed6-195">在 [服務] 清單中，尋找 [ **Lync Server Access Edge**]。</span><span class="sxs-lookup"><span data-stu-id="55ed6-195">In the services list, find **Lync Server Access Edge**.</span></span>

6.  <span data-ttu-id="55ed6-196">以滑鼠右鍵按一下服務名稱，然後選取 [停止]\*\*\*\* 停止服務。</span><span class="sxs-lookup"><span data-stu-id="55ed6-196">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="55ed6-197">將 [啟動類型] 設為 [停用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="55ed6-197">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="55ed6-198">按一下 [確定]\*\*\*\*，以關閉 [屬性]\*\*\*\* 視窗。</span><span class="sxs-lookup"><span data-stu-id="55ed6-198">Click **OK** to close the **Properties** window.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

