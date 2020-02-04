---
title: 設定同盟路由與媒體流量
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7af8228a7537f1bbef4e92af852834459281a817
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728173"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="6f0ed-102">設定同盟路由與媒體流量</span><span class="sxs-lookup"><span data-stu-id="6f0ed-102">Configure federation routes and media traffic</span></span>

 


<span data-ttu-id="6f0ed-103">同盟是兩個或多個 SIP 網域之間的信任關係，允許個別組織中的使用者在網路界限間進行通訊。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-103">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="6f0ed-104">在您遷移至 Lync Server 2013 試生產池之後，您必須從 Microsoft Office 通訊伺服器 2007 R2 Edge 伺服器的同盟路由轉換為 Lync Server 2013 Edge 伺服器的同盟路由。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-104">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Microsoft Office Communications Server 2007 R2 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="6f0ed-105">使用下列程式，將同盟路由及媒體流量路由從您的 Office 通訊伺服器 2007 R2 Edge 伺服器與控制器轉移到 Lync Server 2013 Edge 伺服器（針對單一網站部署）。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-105">Use the procedures that follow to transition the federation route and the media traffic route from your Office Communications Server 2007 R2 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="6f0ed-106">變更同盟路由和媒體流量路由時，需要您針對 Lync Server 2013 和 Office 通訊伺服器 2007 R2 Edge 伺服器排程維護時間。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-106">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Office Communications Server 2007 R2 Edge Servers.</span></span> <span data-ttu-id="6f0ed-107">此整個轉換程式也表示在停用期間將無法使用聯盟存取。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-107">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="6f0ed-108">您應該將停機時間排程為預期最少的使用者活動。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-108">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="6f0ed-109">您也應該為您的最終使用者提供足夠的通知。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-109">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="6f0ed-110">針對此中斷進行規劃，並在您的組織中設定適當的預期。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-110">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>




> [!IMPORTANT]  
> <span data-ttu-id="6f0ed-111">如果您的舊版 Office 通訊伺服器 2007 R2 Edge 伺服器已設定為使用 [存取邊緣服務]、[Web 會議 Edge 服務] 和 [A/V 邊緣] 服務的相同 FQDN，則不支援此區段中的程式將同盟設定轉換為 Lync Server 2013 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-111">If your legacy Office Communications Server 2007 R2 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section to transition the federation setting to a Lync Server 2013 Edge Server are not supported.</span></span> <span data-ttu-id="6f0ed-112">如果舊版 Edge 服務設定為使用相同的 FQDN，您必須先將所有使用者從 Office 通訊伺服器 2007 R2 遷移至 Lync Server 2013，然後在啟用同盟之前，先解除 Office 通訊伺服器 2007 R2 Edge 伺服器Lync Server 2013 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-112">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Office Communications Server 2007 R2 to Lync Server 2013, then decommission the Office Communications Server 2007 R2 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="6f0ed-113">如需詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="6f0ed-113">For details, see the following topics:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="6f0ed-114"><A href="move-remaining-users-to-lync-server-2013_1.md">將剩餘使用者移到 Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="6f0ed-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Move remaining users to Lync Server 2013</A></span></span></P>
> <LI>
> <P><span data-ttu-id="6f0ed-115">"移除伺服器和伺服器角色"<A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></span><span class="sxs-lookup"><span data-stu-id="6f0ed-115">"Remove Servers and Server Roles" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></span></span></P></LI></UL>




> [!IMPORTANT]  
> <span data-ttu-id="6f0ed-116">如果您的 XMPP 同盟是透過 Lync Server 2013 Edge 伺服器路由，舊版 Office 通訊伺服器 2007 R2 使用者將無法與 XMPP 聯盟夥伴通訊，除非已將所有使用者移至 Lync Server 2013、XMPP 原則和已設定憑證之後，已在 Lync Server 2013 上設定 XMPP 聯盟合作夥伴，最後更新了 DNS 專案。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-116">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Office Communications Server 2007 R2 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



<span data-ttu-id="6f0ed-117">若要在新增或移除伺服器角色時成功發佈、啟用或停用拓撲，您應該以 RTCUniversalServerAdmins 和網域系統管理員群組成員的使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-117">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="6f0ed-118">您也可以委派適當的使用者權利和許可權來新增伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-118">It is also possible to delegate the proper user rights and permissions for adding server roles.</span></span> <span data-ttu-id="6f0ed-119">如需詳細資訊，請參閱在標準版 server 或 Enterprise Edition server 部署檔中的[Lync Server 2013 委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-119">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="6f0ed-120">針對其他設定變更，只需要 RTCUniversalServerAdmins 群組中的成員資格。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-120">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="6f0ed-121">若要從 Lync Server 2013 網站移除舊版同盟關聯</span><span class="sxs-lookup"><span data-stu-id="6f0ed-121">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="6f0ed-122">使用 [拓撲建立器] 開啟 [試驗] 泳池拓撲。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-122">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="6f0ed-123">在左窗格中，流覽至 [網站] 節點。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-123">In the left pane, navigate to the site node.</span></span>

3.  <span data-ttu-id="6f0ed-124">以滑鼠右鍵按一下網站，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-124">Right-click the site, and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="6f0ed-125">選取左窗格中的 [**同盟路由**]。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-125">Select **Federation route** in the left pane.</span></span>

5.  <span data-ttu-id="6f0ed-126">在 [網站同盟路由指派] 下，清除 [**啟用 SIP 聯盟**] 旁的核取方塊，以停用**BackCompatSite**的同盟路由。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-126">Under Site federation route assignment, clear the check box next to **Enable SIP federation** to disable the federation route through the **BackCompatSite**.</span></span>
    
    <span data-ttu-id="6f0ed-127">![[編輯內容] 對話方塊，同盟路由](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "[編輯內容] 對話方塊，同盟路由")</span><span class="sxs-lookup"><span data-stu-id="6f0ed-127">![Edit Properties dialog, Federation route](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Edit Properties dialog, Federation route")</span></span>

6.  <span data-ttu-id="6f0ed-128">按一下 **[確定]** 以關閉 [編輯屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-128">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="6f0ed-129">從**拓撲**建立器中，選取頂端節點**Lync Server**。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-129">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="6f0ed-130">從 [**動作**] 功能表中，按一下 [**發佈拓撲**] 並完成嚮導。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-130">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="6f0ed-131">將舊版 Edge 伺服器設定為非聯盟邊緣伺服器</span><span class="sxs-lookup"><span data-stu-id="6f0ed-131">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="6f0ed-132">從 [**拓撲**建立器] 的 [**動作**] 功能表中，按一下 [**合併 Office 通訊伺服器 2007 R2 拓撲結構**]。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-132">From **Topology Builder**, from the **Action** menu click **Merge Office Communications Server 2007 R2 Topology**.</span></span>

2.  <span data-ttu-id="6f0ed-133">請按 [下一步]\*\*\*\* 繼續。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-133">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="6f0ed-134">在 [**指定邊緣設定**] 上，選取目前針對 [同盟] 設定的**邊緣伺服器內部 FQDN** ，然後按一下 [**變更**]。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-134">On the **Specify Edge Setup**, select the **Edge Server Internal FQDN** that is currently configured for federation, and then click **Change**.</span></span>
    
    <span data-ttu-id="6f0ed-135">![合併 OCS 2007 R2 拓撲，指定 Edge 設定](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "合併 OCS 2007 R2 拓撲，指定 Edge 設定")</span><span class="sxs-lookup"><span data-stu-id="6f0ed-135">![Merge OCS 2007 R2 Topology, Specify Edge Setup](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Merge OCS 2007 R2 Topology, Specify Edge Setup")</span></span>

4.  <span data-ttu-id="6f0ed-136">按一下 **[下一步]** ，接受預設設定，直到您到達 [**指定外部邊緣**] 頁面為止：</span><span class="sxs-lookup"><span data-stu-id="6f0ed-136">Click **Next** and accept the default settings until you get to the **Specify External Edge** page:</span></span>
    
    <span data-ttu-id="6f0ed-137">![拓撲產生器的 [指定外部 Edge] 頁面](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "拓撲產生器的 [指定外部 Edge] 頁面")</span><span class="sxs-lookup"><span data-stu-id="6f0ed-137">![Topology Builder Specify External Edge page](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Topology Builder Specify External Edge page")</span></span>

5.  <span data-ttu-id="6f0ed-138">在 [**指定外部邊緣**] 中，清除 [**此 Edge 池用於同盟與公用 IM**連線] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-138">In **Specify External Edge**, clear the **This Edge pool is used for federation and public IM connectivity** check box.</span></span> <span data-ttu-id="6f0ed-139">這將會移除與 BackCompatSite 的同盟關聯。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-139">This will remove the federation association with the BackCompatSite.</span></span>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6f0ed-140">這個步驟非常重要。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-140">This step is important.</span></span> <span data-ttu-id="6f0ed-141">您必須清除此選項才能移除舊版同盟關聯。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-141">You must clear this option to remove the legacy federation association.</span></span>



6.  <span data-ttu-id="6f0ed-142">按一下 **[下一步**]，然後接受嚮導剩餘頁面的預設設定。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-142">Click **Next** and accept the default settings of the remaining pages of the wizard.</span></span>

7.  <span data-ttu-id="6f0ed-143">在 [**摘要**] 中，按一下 **[下一步]** 以開始合併拓撲。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-143">In **Summary**, click **Next** to begin merging the topologies.</span></span>

8.  <span data-ttu-id="6f0ed-144">在 [**狀態**] 欄中，確認此值為 [**成功**]，然後按一下 **[完成**] 以關閉嚮導。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-144">In the **Status** column, verify that the value is **Success**, and then click **Finish** to close the wizard.</span></span>

9.  <span data-ttu-id="6f0ed-145">從 [**動作**] 功能表中，選取 [**發佈拓撲**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-145">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

10. <span data-ttu-id="6f0ed-146">**發佈嚮導**完成後，請按一下 **[完成**] 以關閉嚮導。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-146">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>
    
    <span data-ttu-id="6f0ed-147">![具有合併之後顯示之網站的拓撲產生器](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "具有合併之後顯示之網站的拓撲產生器")</span><span class="sxs-lookup"><span data-stu-id="6f0ed-147">![Topology Builder with site displayed after merge](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Topology Builder with site displayed after merge")</span></span>
    
    <span data-ttu-id="6f0ed-148">如上圖所示，位於 [**網站同盟路由指派**] 下的**SIP 同盟**設定為 [**已停用**]。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-148">As shown in the previous figure, the **SIP federation** located under **Site federation route assignment** is set to **Disabled**.</span></span>

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="6f0ed-149">在 Lync Server 2013 Edge 伺服器上設定憑證</span><span class="sxs-lookup"><span data-stu-id="6f0ed-149">To configure certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="6f0ed-150">從舊版 Office 通訊伺服器 2007 R2 Edge 伺服器匯出外部存取 Proxy 證書與私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-150">Export the external Access Proxy certificate, with the private key, from the legacy Office Communications Server 2007 R2 Edge Server.</span></span>

2.  <span data-ttu-id="6f0ed-151">在 Lync Server 2013 Edge 伺服器上，從上一個步驟匯入 [存取 Proxy 外部憑證]。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-151">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="6f0ed-152">將存取 Proxy 外部憑證指派給 Edge 伺服器的 Lync Server 2013 外部介面。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-152">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="6f0ed-153">Lync Server 2013 Edge 伺服器的內部介面憑證不應變更。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-153">The internal interface certificate of the Lync Server 2013 Edge Server should not be changed.</span></span>

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="6f0ed-154">若要將 Office 通訊伺服器 2007 R2 同盟路由變更為使用 Lync Server 2013 Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="6f0ed-154">To change Office Communications Server 2007 R2 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="6f0ed-155">在 Office 通訊伺服器 2007 R2 標準版伺服器或前端伺服器上，開啟 Office 通訊伺服器 2007 R2 管理工具。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-155">On the Office Communications Server 2007 R2 Standard Edition server or Front End Server, open the Office Communications Server 2007 R2 Administrative tool.</span></span>

2.  <span data-ttu-id="6f0ed-156">在左窗格中，展開上方節點，然後以滑鼠右鍵按一下 [**林**] 節點。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-156">In the left pane, expand the top node, and then right-click the **Forest** node.</span></span> <span data-ttu-id="6f0ed-157">選取 [**屬性**]，然後按一下 [**全域屬性**]。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-157">Select **Properties**, and then click **Global Properties**.</span></span>

3.  <span data-ttu-id="6f0ed-158">按一下 [**聯盟**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-158">Click the **Federation** tab.</span></span>

4.  <span data-ttu-id="6f0ed-159">選取核取方塊以啟用同盟與公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-159">Select the check box to enable federation and Public IM connectivity.</span></span>

5.  <span data-ttu-id="6f0ed-160">輸入 Lync Server 2013 Edge 伺服器的 FQDN，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-160">Enter the FQDN of the Lync Server 2013 Edge Server, and then click **OK**.</span></span>
    
    <span data-ttu-id="6f0ed-161">![OCS 通用內容，[同盟] 索引標籤](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS 通用內容，[同盟] 索引標籤")</span><span class="sxs-lookup"><span data-stu-id="6f0ed-161">![OCS Global Properties, Federation tab](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS Global Properties, Federation tab")</span></span>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="6f0ed-162">若要開啟 Lync Server 2013 Edge 伺服器同盟</span><span class="sxs-lookup"><span data-stu-id="6f0ed-162">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="6f0ed-163">從拓撲建立器，在左窗格中，流覽至 [Lync Server 2013 **Edge 池**] 節點。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-163">From Topology Builder, in the left pane, navigate to the Lync Server 2013 **Edge pools** node.</span></span>

2.  <span data-ttu-id="6f0ed-164">展開節點，以滑鼠右鍵按一下列出的邊緣伺服器，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-164">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="6f0ed-165">只有單一邊緣池才能啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-165">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="6f0ed-166">如果您有多個邊緣池，請選取一個，以做為聯盟邊界池。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-166">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>



3.  <span data-ttu-id="6f0ed-167">在 [**一般**] 頁面上，選取 [**針對此 Edge 池啟用同盟（埠5061）** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-167">On the **General** page, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
    <span data-ttu-id="6f0ed-168">![編輯內容，一般，啟用 Edge 同盟](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "編輯內容，一般，啟用 Edge 同盟")</span><span class="sxs-lookup"><span data-stu-id="6f0ed-168">![Edit Properties, General, Enable Edge Federation](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Edit Properties, General, Enable Edge Federation")</span></span>

4.  <span data-ttu-id="6f0ed-169">按一下 **[確定]** 以關閉 [編輯屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-169">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="6f0ed-170">接下來，流覽至 [網站] 節點。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-170">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="6f0ed-171">以滑鼠右鍵按一下網站，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-171">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="6f0ed-172">在左窗格中，按一下 [**同盟路由**]。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-172">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="6f0ed-173">在 [**網站同盟路由指派**] 底下，選取 [**啟用 SIP 同盟**]，然後從清單中選取 [Lync server 2013 Edge 伺服器]。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-173">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>

9.  <span data-ttu-id="6f0ed-174">按一下 **[確定]** 以關閉 [**編輯屬性**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-174">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="6f0ed-175">![編輯內容，一般，關聯 Edge 集區](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "編輯內容，一般，關聯 Edge 集區")</span><span class="sxs-lookup"><span data-stu-id="6f0ed-175">![Edit Properties, General, Associate Edge pool](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>
    
    <span data-ttu-id="6f0ed-176">針對多網站部署，請在每個網站完成此程式。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-176">For multi-site deployments, complete this procedure at each site.</span></span>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="6f0ed-177">設定 Lync Server 2013 Edge 伺服器出站媒體路徑</span><span class="sxs-lookup"><span data-stu-id="6f0ed-177">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="6f0ed-178">從**拓撲**建立器，流覽至**標準版前端伺服器**或**企業版前端池**下方的 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-178">From **Topology Builder**, navigate to the Lync Server 2013 pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="6f0ed-179">以滑鼠右鍵按一下該池子，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-179">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="6f0ed-180">在 [**關聯**性] 區段中，選取 [**關聯邊緣池（適用于媒體元件）** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-180">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>

4.  <span data-ttu-id="6f0ed-181">從下拉式方塊中，選取 [Lync Server 2013 Edge 伺服器]。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-181">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>
    
    <span data-ttu-id="6f0ed-182">![[編輯內容] 對話方塊，關聯 Edge 集區](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "[編輯內容] 對話方塊，關聯 Edge 集區")</span><span class="sxs-lookup"><span data-stu-id="6f0ed-182">![Edit Properties dialog, Associate Edge Pool](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Edit Properties dialog, Associate Edge Pool")</span></span>

5.  <span data-ttu-id="6f0ed-183">按一下 **[確定]** 以關閉 [**編輯屬性**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-183">Click **OK** to close the **Edit Properties** page.</span></span>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="6f0ed-184">發佈 Edge 伺服器設定變更</span><span class="sxs-lookup"><span data-stu-id="6f0ed-184">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="6f0ed-185">從**拓撲**建立器中，選取頂端節點**Lync Server**。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-185">From **Topology Builder**, select the top node **Lync Server**.</span></span>

2.  <span data-ttu-id="6f0ed-186">從 [**動作**] 功能表中，選取 [**發佈拓撲**] 並完成嚮導。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-186">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="6f0ed-187">等到對部署中的所有池進行 Active Directory 複製。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-187">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="6f0ed-188">您可能會看到下列訊息：</span><span class="sxs-lookup"><span data-stu-id="6f0ed-188">You may see the following message:</span></span><BR><span data-ttu-id="6f0ed-189"><STRONG>警告：拓朴包含一個以上的同盟邊緣伺服器。在遷移到較新版產品的過程中，可能會發生這種情況。在這種情況下，只有一台邊緣伺服器會主動用於同盟。確認外部 DNS SRV 記錄指向正確的邊緣伺服器。如果您想要將多個同盟邊緣伺服器部署成同時作用（也就是不是遷移案例），請確認所有聯盟夥伴都使用 Office 通訊伺服器 2007 R2 或 Lync Server。確認外部 DNS SRV 記錄列出所有啟用同盟的 Edge 伺服器。</STRONG></span><span class="sxs-lookup"><span data-stu-id="6f0ed-189"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Office Communications Server 2007 R2 or Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="6f0ed-190">此為預期警告，且可以放心地忽略。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-190">This warning is expected and can be safely ignored.</span></span>



## <a name="to-verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="6f0ed-191">驗證外部使用者的同盟與遠端存取權</span><span class="sxs-lookup"><span data-stu-id="6f0ed-191">To verify federation and remote access for external users</span></span>

1.  <span data-ttu-id="6f0ed-192">從 Lync Server 2013 前端伺服器，開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-192">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="6f0ed-193">若要驗證同盟和遠端存取的狀態，請從命令列輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="6f0ed-193">To verify the status of federation and remote access, from the command line, type the following:</span></span>
    
        Get-CsAccessEdgeConfiguration

3.  <span data-ttu-id="6f0ed-194">若要啟用同盟和遠端存取，請從命令列輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="6f0ed-194">To enable federation and remote access, from the command line, type the following:</span></span>
    
        Set-CsAccessEdgeConfiguration
    
    <span data-ttu-id="6f0ed-195">如需這些 Cmdlet 的詳細資訊，請參閱下列主題： [CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg398574\(v=ocs.15\))及[設定 CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg413017\(v=ocs.15\))。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-195">For more information on these cmdlets, see the following topics: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg398574\(v=ocs.15\)) and [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg413017\(v=ocs.15\)).</span></span>

4.  <span data-ttu-id="6f0ed-196">等到複製完成之後，再將 Lync Server 2013 Edge 伺服器連線，然後測試同盟與外部存取。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-196">Wait until replication has completed before bringing the Lync Server 2013 Edge servers online, and testing federation and external access.</span></span>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="6f0ed-197">設定 Lync Server 2013 Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="6f0ed-197">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="6f0ed-198">將所有 Lync Server 2013 Edge 伺服器連線。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-198">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="6f0ed-199">更新外部防火牆路由規則或硬體負載平衡器設定，以傳送 SIP 流量（通常是埠443）和同盟（通常是埠5061）至 Lync Server 2013 Edge 伺服器，而不是舊版 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-199">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="6f0ed-200">如果您沒有硬體負載平衡器，您需要更新同盟的 DNS A 記錄，以解析新的 Lync Server Access Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-200">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve the new Lync Server Access Edge server.</span></span> <span data-ttu-id="6f0ed-201">若要以最小的中斷來完成此作業，請減少外部 Lync Server 存取邊緣 FQDN 的 TTL 值，以便將 DNS 更新為指向新的 Lync Server 存取邊緣伺服器、同盟和遠端存取將會很快更新。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-201">To accomplish this with minimum disruption, reduce the TTL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge server, federation and remote access will be updated quickly.</span></span>



3.  <span data-ttu-id="6f0ed-202">接下來，從每個 Edge 伺服器電腦停止**Lync Server 存取邊緣**。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-202">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="6f0ed-203">從每個舊版 Edge 伺服器電腦，從 [**管理工具**] 開啟 [**服務**] 小工具。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-203">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="6f0ed-204">在 [服務] 清單中，尋找 [ **Office 通訊伺服器存取邊緣**]。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-204">In the services list, find **Office Communications Server Access Edge**.</span></span>

6.  <span data-ttu-id="6f0ed-205">以滑鼠右鍵按一下服務名稱，然後選取 [**停止**] 停止服務。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-205">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="6f0ed-206">將啟動類型設定為 [**停用**]。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-206">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="6f0ed-207">按一下 **[確定**] 以關閉 [**屬性**] 視窗。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-207">Click **OK** to close the **Properties** window.</span></span>

## <a name="to-test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="6f0ed-208">測試外部使用者與外部存取的連線能力</span><span class="sxs-lookup"><span data-stu-id="6f0ed-208">To Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="6f0ed-209">至少有一個聯盟網域的使用者，也就是 Lync Server 2013 上的內部使用者，以及 Office 通訊伺服器 2007 R2 上的使用者。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-209">Users from at least one federated domain, an internal user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="6f0ed-210">測試立即訊息（IM）、目前狀態、音訊/視頻（A/V）與桌面共用。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-210">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="6f0ed-211">貴組織支援的每個公用 IM 服務提供者的使用者（以及已完成哪些預配）與 Lync Server 2013 上的使用者通訊，以及 Office 通訊伺服器 2007 R2 上的使用者。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-211">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="6f0ed-212">確認匿名使用者可以加入會議。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-212">Verify anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="6f0ed-213">在 Office 通訊伺服器 2007 R2 上使用遠端使用者存取（從內部網路外部（不含 VPN）登入 Office 通訊伺服器 2007 R2 的使用者，與 Lync Server 2013 上的使用者，以及 Office 通訊伺服器 2007 R2 上的使用者。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-213">A user hosted on Office Communications Server 2007 R2 using remote user access (logging into Office Communications Server 2007 R2 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="6f0ed-214">測試 IM、目前狀態、A/V 與桌面共用。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-214">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="6f0ed-215">在 Lync Server 2013 上使用遠端使用者存取（從內部網路外部2013（不含 VPN）與使用者在 Lync server 2013 上以及 Office 通訊伺服器 2007 R2 上的使用者所託管的使用者。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-215">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="6f0ed-216">測試 IM、目前狀態、A/V 與桌面共用。</span><span class="sxs-lookup"><span data-stu-id="6f0ed-216">Test IM, presence, A/V, and desktop sharing.</span></span>

