---
title: 設定同盟路由與媒體流量
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed16ac6b8aceea6828b600ce18da8b9a72827846
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="61090-102">設定同盟路由與媒體流量</span><span class="sxs-lookup"><span data-stu-id="61090-102">Configure federation routes and media traffic</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61090-103">_**主題上次修改日期：** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="61090-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="61090-104">同盟是兩個或多個 SIP 網域之間的信任關係，允許個別組織中的使用者在網路界限間進行通訊。</span><span class="sxs-lookup"><span data-stu-id="61090-104">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="61090-105">在您遷移至 Lync Server 2013 試生產池之後，您必須從 Lync Server 2010 Edge 伺服器的同盟路由轉移到 Lync Server 2013 Edge 伺服器的同盟路由。</span><span class="sxs-lookup"><span data-stu-id="61090-105">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Lync Server 2010 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="61090-106">您可以使用下列程式，將同盟路由及媒體流量路由從 Lync Server 2010 Edge 伺服器與控制器轉換為 Lync Server 2013 Edge 伺服器（針對單一網站部署）。</span><span class="sxs-lookup"><span data-stu-id="61090-106">Use the following procedures to transition the federation route and the media traffic route from your Lync Server 2010 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="61090-107">變更同盟路由和媒體流量路由時，需要您針對 Lync Server 2013 和 Lync Server 2010 Edge 伺服器排程維護時間。</span><span class="sxs-lookup"><span data-stu-id="61090-107">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Lync Server 2010 Edge Servers.</span></span> <span data-ttu-id="61090-108">此整個轉換程式也表示在停用期間將無法使用聯盟存取。</span><span class="sxs-lookup"><span data-stu-id="61090-108">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="61090-109">您應該將停機時間排程為預期最少的使用者活動。</span><span class="sxs-lookup"><span data-stu-id="61090-109">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="61090-110">您也應該為您的最終使用者提供足夠的通知。</span><span class="sxs-lookup"><span data-stu-id="61090-110">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="61090-111">針對此中斷進行規劃，並在您的組織中設定適當的預期。</span><span class="sxs-lookup"><span data-stu-id="61090-111">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="61090-112">如果您的舊版 Lync Server 2010 Edge 伺服器已設定為使用相同的 FQDN 來存取邊緣服務、網路會議邊緣服務以及 A/V 邊緣服務，則不支援本節中的程式。</span><span class="sxs-lookup"><span data-stu-id="61090-112">If your legacy Lync Server 2010 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="61090-113">如果舊版 Edge 服務設定為使用相同的 FQDN，您必須先將所有使用者從 Lync Server 2010 遷移至 Lync Server 2013，然後在 Lync Server 2013 Edge 伺服器上啟用同盟之前，先解除 Lync Server 2010 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="61090-113">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Lync Server 2010 to Lync Server 2013, then decommission the Lync Server 2010 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="61090-114">如果您的 XMPP 同盟是透過 Lync Server 2013 Edge 伺服器路由，舊版 Lync Server 2010 使用者將無法與 XMPP 聯盟夥伴通訊，除非已將所有使用者移至 Lync Server 2013、XMPP 原則與憑證已設定，已在 Lync Server 2013 上設定 XMPP 聯盟合作夥伴，最後更新了 DNS 專案。</span><span class="sxs-lookup"><span data-stu-id="61090-114">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Lync Server 2010 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="61090-115">若要從 Lync Server 2013 網站移除舊版同盟關聯</span><span class="sxs-lookup"><span data-stu-id="61090-115">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="61090-116">在 Lync Server 2013 前端伺服器上，在 [拓撲產生器] 中開啟現有的拓撲。</span><span class="sxs-lookup"><span data-stu-id="61090-116">On the Lync Server 2013 Front End server, open the existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="61090-117">在左窗格中，流覽至 [ **Lync Server**] 正下方的 [網站] 節點。</span><span class="sxs-lookup"><span data-stu-id="61090-117">In the left pane, navigate to the site node, which is located directly below **Lync Server**.</span></span>

3.  <span data-ttu-id="61090-118">以滑鼠右鍵按一下網站，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="61090-118">Right-click the site and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="61090-119">在左窗格中，選取 [**同盟路由**]。</span><span class="sxs-lookup"><span data-stu-id="61090-119">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="61090-120">在 [**網站同盟路由指派**] 下，清除 [**啟用 SIP 同盟**] 核取方塊，以停用來自舊版 Lync Server 2010 環境的同盟路由。</span><span class="sxs-lookup"><span data-stu-id="61090-120">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy Lync Server 2010 environment.</span></span>
    
    <span data-ttu-id="61090-121">[![編輯屬性] 對話方塊，[同盟路由] 頁面][(images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "編輯屬性] 對話方塊，[同盟路由] 頁面")</span><span class="sxs-lookup"><span data-stu-id="61090-121">![Edit Properties dialog, Federation route page](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>

6.  <span data-ttu-id="61090-122">按一下 **[確定]** 以關閉 [編輯屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="61090-122">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="61090-123">從**拓撲**建立器中，選取頂端節點**Lync Server**。</span><span class="sxs-lookup"><span data-stu-id="61090-123">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="61090-124">從 [**動作**] 功能表中，按一下 [**發佈拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="61090-124">From the **Action** menu, click **Publish Topology**.</span></span>

9.  <span data-ttu-id="61090-125">按一下 **[下一步**] 完成發佈程式，然後在發佈程式完成時按一下 **[完成]** 。</span><span class="sxs-lookup"><span data-stu-id="61090-125">Click **Next** to complete the publishing process and then click **Finish** when the publishing process has completed.</span></span>

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="61090-126">將舊版 Edge 伺服器設定為非聯盟邊緣伺服器</span><span class="sxs-lookup"><span data-stu-id="61090-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="61090-127">在左窗格中，流覽至**Lync Server 2010**節點，然後移至 [**邊緣池**] 節點。</span><span class="sxs-lookup"><span data-stu-id="61090-127">In the left pane, navigate to the **Lync Server 2010** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="61090-128">以滑鼠右鍵按一下邊緣伺服器，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="61090-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="61090-129">在左窗格中選取 **[一般**]。</span><span class="sxs-lookup"><span data-stu-id="61090-129">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="61090-130">清除 [**針對此 Edge 池啟用同盟（埠5061）** ] 核取方塊專案，然後選取 **[確定]** 以關閉頁面。</span><span class="sxs-lookup"><span data-stu-id="61090-130">Clear the **Enable federation for this Edge pool (port 5061)** check box entry and select **OK** to close the page.</span></span>
    
    <span data-ttu-id="61090-131">![編輯屬性，一般，清除啟用同盟](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "編輯屬性，一般，清除啟用同盟")</span><span class="sxs-lookup"><span data-stu-id="61090-131">![Edit Properties, General, clear Enable federation](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Edit Properties, General, clear Enable federation")</span></span>

5.  <span data-ttu-id="61090-132">從 [**動作**] 功能表中，選取 [**發佈拓撲**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="61090-132">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="61090-133">**發佈嚮導**完成後，請按一下 **[完成**] 以關閉嚮導。</span><span class="sxs-lookup"><span data-stu-id="61090-133">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="61090-134">驗證舊版 Edge 伺服器的同盟已停用。</span><span class="sxs-lookup"><span data-stu-id="61090-134">Verify federation for the legacy Edge server is disabled.</span></span>
    
    <span data-ttu-id="61090-135">![拓撲建立器、邊緣池、同盟已停用](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "拓撲建立器、edge 池、同盟已停用")</span><span class="sxs-lookup"><span data-stu-id="61090-135">![Topology Builder, Edge pool, federation disabled](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Topology Builder, Edge pool, federation disabled")</span></span>

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a><span data-ttu-id="61090-136">在 Lync Server 2010 Edge 伺服器上設定憑證</span><span class="sxs-lookup"><span data-stu-id="61090-136">To configure certificates on the Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="61090-137">從舊版 Lync Server 2010 Edge 伺服器匯出外部存取 Proxy 證書與私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="61090-137">Export the external Access Proxy certificate, with the private key, from the legacy Lync Server 2010 Edge Server.</span></span>

2.  <span data-ttu-id="61090-138">在 Lync Server 2013 Edge 伺服器上，從上一個步驟匯入 [存取 Proxy 外部憑證]。</span><span class="sxs-lookup"><span data-stu-id="61090-138">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="61090-139">將存取 Proxy 外部憑證指派給 Edge 伺服器的 Lync Server 2013 外部介面。</span><span class="sxs-lookup"><span data-stu-id="61090-139">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="61090-140">必須從信任的 CA 要求並指派 Lync Server 2013 Edge 伺服器的內部介面憑證。</span><span class="sxs-lookup"><span data-stu-id="61090-140">The internal interface certificate of the Lync Server 2013 Edge Server should be requested from a trusted CA and assigned.</span></span>

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="61090-141">若要將 Lync Server 2010 同盟路由變更為使用 Lync Server 2013 Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="61090-141">To change Lync Server 2010 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="61090-142">從拓撲建立器，在左窗格中，流覽至**Lync Server 2013**節點，然後流覽至 [**邊緣池**] 節點。</span><span class="sxs-lookup"><span data-stu-id="61090-142">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="61090-143">以滑鼠右鍵按一下邊緣伺服器，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="61090-143">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="61090-144">在左窗格中選取 **[一般**]。</span><span class="sxs-lookup"><span data-stu-id="61090-144">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="61090-145">選取 [針對**此 Edge 池啟用同盟的核取方塊專案（埠5061）** ]，然後按一下 **[確定]** 以關閉頁面。</span><span class="sxs-lookup"><span data-stu-id="61090-145">Select the check box entry for **Enable federation for this Edge pool (port 5061)** and then click **OK** to close the page.</span></span>
    
    <span data-ttu-id="61090-146">![[編輯屬性] 對話方塊，一般頁面 [](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "編輯屬性] 對話方塊，[一般] 頁面")</span><span class="sxs-lookup"><span data-stu-id="61090-146">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

5.  <span data-ttu-id="61090-147">從 [**動作**] 功能表中，選取 [**發佈拓撲**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="61090-147">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="61090-148">**發佈嚮導**完成後，請按一下 **[完成**] 以關閉嚮導。</span><span class="sxs-lookup"><span data-stu-id="61090-148">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="61090-149">驗證**同盟（埠5061）** 已設定為 [**啟用**]。</span><span class="sxs-lookup"><span data-stu-id="61090-149">Verify **Federation (port 5061)** is set to **Enabled**.</span></span>
    
    <span data-ttu-id="61090-150">![拓撲建立器、邊緣池、同盟啟用](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "拓撲建立器、edge 池、已啟用同盟")</span><span class="sxs-lookup"><span data-stu-id="61090-150">![Topology Builder, Edge pool, Federation enabled](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Topology Builder, Edge pool, Federation enabled")</span></span>

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a><span data-ttu-id="61090-151">更新 Lync Server 2013 Edge 伺服器同盟下一個躍點</span><span class="sxs-lookup"><span data-stu-id="61090-151">To update Lync Server 2013 Edge Server federation next hop</span></span>

1.  <span data-ttu-id="61090-152">從拓撲建立器，在左窗格中，流覽至**Lync Server 2013**節點，然後流覽至 [**邊緣池**] 節點。</span><span class="sxs-lookup"><span data-stu-id="61090-152">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="61090-153">展開節點，以滑鼠右鍵按一下列出的邊緣伺服器，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="61090-153">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="61090-154">在 [**一般**] 頁面上的 **[下一個躍點選取範圍]** 底下，從下拉式清單中選取 [Lync Server 2013] 池。</span><span class="sxs-lookup"><span data-stu-id="61090-154">On the **General** page, under **Next hop selection**, select from the drop-down list the Lync Server 2013  pool.</span></span>
    
    <span data-ttu-id="61090-155">![[編輯屬性] 對話方塊，[下一個躍點] 頁面 [](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "編輯屬性] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="61090-155">![Edit Properties dialog, Next hop page](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Edit Properties dialog, Next hop page")</span></span>

4.  <span data-ttu-id="61090-156">按一下 **[確定]** 以關閉 [編輯屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="61090-156">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="61090-157">從**拓撲**建立器中，選取頂端節點**Lync Server** 。</span><span class="sxs-lookup"><span data-stu-id="61090-157">From **Topology Builder**, select the top node **Lync Server** .</span></span>

6.  <span data-ttu-id="61090-158">從 [**動作**] 功能表中，按一下 [**發佈拓撲**] 並完成嚮導。</span><span class="sxs-lookup"><span data-stu-id="61090-158">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="61090-159">設定 Lync Server 2013 Edge 伺服器出站媒體路徑</span><span class="sxs-lookup"><span data-stu-id="61090-159">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="61090-160">從 [拓撲建立器] 的左窗格中，流覽至 [ **Lync Server 2013** ] 節點，然後移至 [**標準版] 前端伺服器**或 [**企業版] 前端池**的 [池]。</span><span class="sxs-lookup"><span data-stu-id="61090-160">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="61090-161">以滑鼠右鍵按一下該池子，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="61090-161">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="61090-162">在 [**關聯**性] 區段中，選取 [**關聯邊緣池（適用于媒體元件）** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="61090-162">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>
    
    <span data-ttu-id="61090-163">![編輯屬性、一般、關聯邊緣池](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "編輯屬性、一般、關聯邊緣池")</span><span class="sxs-lookup"><span data-stu-id="61090-163">![Edit Properties, General, Associate Edge pool](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>

4.  <span data-ttu-id="61090-164">從下拉式方塊中，選取 [Lync Server 2013 Edge 伺服器]。</span><span class="sxs-lookup"><span data-stu-id="61090-164">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>

5.  <span data-ttu-id="61090-165">按一下 **[確定]** 以關閉 [**編輯屬性**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="61090-165">Click **OK** to close the **Edit Properties** page.</span></span>

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="61090-166">若要開啟 Lync Server 2013 Edge 伺服器同盟</span><span class="sxs-lookup"><span data-stu-id="61090-166">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="61090-167">從拓撲建立器，在左窗格中，流覽至**Lync Server 2013**節點，然後流覽至 [**邊緣池**] 節點。</span><span class="sxs-lookup"><span data-stu-id="61090-167">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="61090-168">展開節點，以滑鼠右鍵按一下列出的邊緣伺服器，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="61090-168">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="61090-169">只有單一邊緣池才能啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="61090-169">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="61090-170">如果您有多個邊緣池，請選取一個，以做為聯盟邊界池。</span><span class="sxs-lookup"><span data-stu-id="61090-170">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>

    
    </div>

3.  <span data-ttu-id="61090-171">在 [**一般**] 頁面上，確認已核取 [**啟用此 Edge 池的同盟（埠5061）** ] 設定。</span><span class="sxs-lookup"><span data-stu-id="61090-171">On the **General** page, verify the **Enable federation for this Edge pool (Port 5061)** setting is checked.</span></span>
    
    <span data-ttu-id="61090-172">![[編輯屬性] 對話方塊，一般頁面 [](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "編輯屬性] 對話方塊，[一般] 頁面")</span><span class="sxs-lookup"><span data-stu-id="61090-172">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

4.  <span data-ttu-id="61090-173">按一下 **[確定]** 以關閉 [編輯屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="61090-173">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="61090-174">接下來，流覽至 [網站] 節點。</span><span class="sxs-lookup"><span data-stu-id="61090-174">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="61090-175">以滑鼠右鍵按一下網站，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="61090-175">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="61090-176">在左窗格中，按一下 [**同盟路由**]。</span><span class="sxs-lookup"><span data-stu-id="61090-176">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="61090-177">在 [**網站同盟路由指派**] 底下，選取 [**啟用 SIP 同盟**]，然後從清單中選取 [Lync server 2013 Edge 伺服器]。</span><span class="sxs-lookup"><span data-stu-id="61090-177">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>
    
    <span data-ttu-id="61090-178">![編輯屬性、同盟路由頁面](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "編輯屬性、同盟路由頁面")</span><span class="sxs-lookup"><span data-stu-id="61090-178">![Edit Properties, Federation route page](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Edit Properties, Federation route page")</span></span>

9.  <span data-ttu-id="61090-179">按一下 **[確定]** 以關閉 [**編輯屬性**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="61090-179">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="61090-180">針對多網站部署，請在每個網站完成此程式。</span><span class="sxs-lookup"><span data-stu-id="61090-180">For multi-site deployments, complete this procedure at each site.</span></span>

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="61090-181">發佈 Edge 伺服器設定變更</span><span class="sxs-lookup"><span data-stu-id="61090-181">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="61090-182">從**拓撲**建立器中，選取頂端節點**Lync Server** 。</span><span class="sxs-lookup"><span data-stu-id="61090-182">From **Topology Builder**, select the top node **Lync Server** .</span></span>

2.  <span data-ttu-id="61090-183">從 [**動作**] 功能表中，選取 [**發佈拓撲**] 並完成嚮導。</span><span class="sxs-lookup"><span data-stu-id="61090-183">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="61090-184">等到對部署中的所有池進行 Active Directory 複製。</span><span class="sxs-lookup"><span data-stu-id="61090-184">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="61090-185">您可能會看到下列訊息：</span><span class="sxs-lookup"><span data-stu-id="61090-185">You may see the following message:</span></span><BR><span data-ttu-id="61090-186"><STRONG>警告：拓朴包含一個以上的同盟邊緣伺服器。在遷移到較新版產品的過程中，可能會發生這種情況。在這種情況下，只有一台邊緣伺服器會主動用於同盟。確認外部 DNS SRV 記錄指向正確的邊緣伺服器。如果您想要將多個同盟邊緣伺服器部署成同時作用（也就是不是遷移案例），請確認所有聯盟夥伴都使用 Lync Server。確認外部 DNS SRV 記錄列出所有啟用同盟的 Edge 伺服器。</STRONG></span><span class="sxs-lookup"><span data-stu-id="61090-186"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="61090-187">此為預期警告，且可以放心地忽略。</span><span class="sxs-lookup"><span data-stu-id="61090-187">This warning is expected and can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="61090-188">設定 Lync Server 2013 Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="61090-188">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="61090-189">將所有 Lync Server 2013 Edge 伺服器連線。</span><span class="sxs-lookup"><span data-stu-id="61090-189">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="61090-190">更新外部防火牆路由規則或硬體負載平衡器設定，以傳送 SIP 流量（通常是埠443）和同盟（通常是埠5061）至 Lync Server 2013 Edge 伺服器，而不是舊版 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="61090-190">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="61090-191">如果您沒有硬體負載平衡器，您需要更新同盟的 DNS A 記錄，以解析為新的 Lync Server 存取邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="61090-191">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Lync Server Access Edge server.</span></span> <span data-ttu-id="61090-192">若要以最小的中斷來完成此作業，請減少外部 Lync Server 存取邊緣 FQDN 的 TLL 值，讓 DNS 更新為指向新的 Lync Server 存取邊緣、同盟和遠端存取將會很快更新。</span><span class="sxs-lookup"><span data-stu-id="61090-192">To accomplish this with minimum disruption, reduce the TLL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge, federation and remote access will be updated quickly.</span></span>

    
    </div>

3.  <span data-ttu-id="61090-193">接下來，從每個 Edge 伺服器電腦停止**Lync Server 存取邊緣**。</span><span class="sxs-lookup"><span data-stu-id="61090-193">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="61090-194">從每個舊版 Edge 伺服器電腦，從 [**管理工具**] 開啟 [**服務**] 小工具。</span><span class="sxs-lookup"><span data-stu-id="61090-194">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="61090-195">在 [服務] 清單中，尋找 [ **Lync Server 存取權] 邊緣**。</span><span class="sxs-lookup"><span data-stu-id="61090-195">In the services list, find **Lync Server Access Edge**.</span></span>

6.  <span data-ttu-id="61090-196">以滑鼠右鍵按一下服務名稱，然後選取 [**停止**] 停止服務。</span><span class="sxs-lookup"><span data-stu-id="61090-196">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="61090-197">將啟動類型設定為 [**停用**]。</span><span class="sxs-lookup"><span data-stu-id="61090-197">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="61090-198">按一下 **[確定**] 以關閉 [**屬性**] 視窗。</span><span class="sxs-lookup"><span data-stu-id="61090-198">Click **OK** to close the **Properties** window.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

