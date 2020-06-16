---
title: 設定同盟路由與媒體流量
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d6af77188809b092050629c1b74cdab8b20a2cc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754959"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="41c3b-102">設定同盟路由與媒體流量</span><span class="sxs-lookup"><span data-stu-id="41c3b-102">Configure federation routes and media traffic</span></span>

 


<span data-ttu-id="41c3b-103">同盟是兩個或兩個以上 SIP 網域間的信任關係，其可允許不同組織中的使用者跨越網路界限進行通訊。</span><span class="sxs-lookup"><span data-stu-id="41c3b-103">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="41c3b-104">遷移至 Lync Server 2013 試驗集區之後，您必須從 Microsoft Office 通訊伺服器 2007 R2 Edge server 的同盟路由轉換為您的 Lync Server 2013 Edge server 的同盟路由。</span><span class="sxs-lookup"><span data-stu-id="41c3b-104">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Microsoft Office Communications Server 2007 R2 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="41c3b-105">請使用下列程式，將您 Office 通訊伺服器 2007 R2 Edge Server 和 Director 的同盟路由與媒體流量路由轉換至 Lync Server 2013 Edge Server，以進行單一網站部署。</span><span class="sxs-lookup"><span data-stu-id="41c3b-105">Use the procedures that follow to transition the federation route and the media traffic route from your Office Communications Server 2007 R2 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="41c3b-106">變更同盟路由與媒體流量路由需要您為 Lync Server 2013 和 Office 通訊伺服器 2007 R2 Edge server 排程維護停機時間。</span><span class="sxs-lookup"><span data-stu-id="41c3b-106">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Office Communications Server 2007 R2 Edge Servers.</span></span> <span data-ttu-id="41c3b-107">這整個轉換過程同時也意味著，在運行中斷期間無法使用同盟存取。</span><span class="sxs-lookup"><span data-stu-id="41c3b-107">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="41c3b-108">您應該將停機時間排在您預期使用者活動最少的時間。</span><span class="sxs-lookup"><span data-stu-id="41c3b-108">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="41c3b-109">您也應該要提供足夠的通知給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="41c3b-109">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="41c3b-110">請視情況規劃此運行中斷，並且在組織內設定適當的期望。</span><span class="sxs-lookup"><span data-stu-id="41c3b-110">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>




> [!IMPORTANT]  
> <span data-ttu-id="41c3b-111">如果舊版 Office 通訊伺服器 2007 R2 Edge Server 設定為使用 Access Edge service、Web 會議 Edge service 和 A/V Edge service 的相同 FQDN，則不支援此區段中的程式將同盟設定轉換為 Lync Server 2013 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="41c3b-111">If your legacy Office Communications Server 2007 R2 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section to transition the federation setting to a Lync Server 2013 Edge Server are not supported.</span></span> <span data-ttu-id="41c3b-112">如果舊版 Edge service 設定為使用相同的 FQDN，您必須先將所有使用者從 Office 通訊伺服器 2007 R2 遷移至 Lync Server 2013，然後在 Lync 2013 Server 的 [！] Edge Server 上啟用同盟，再解除委任 Office 通訊伺服器的 2007 R2 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="41c3b-112">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Office Communications Server 2007 R2 to Lync Server 2013, then decommission the Office Communications Server 2007 R2 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="41c3b-113">如需詳細資料，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="41c3b-113">For details, see the following topics:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="41c3b-114"><A href="move-remaining-users-to-lync-server-2013_1.md">將剩餘的使用者移至 Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="41c3b-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Move remaining users to Lync Server 2013</A></span></span></P>
> <LI>
> <P><span data-ttu-id="41c3b-115">「移除伺服器和伺服器角色」<A href="https://go.microsoft.com/fwlink/p/?linkid=268790">https://go.microsoft.com/fwlink/p/?LinkId=268790</A></span><span class="sxs-lookup"><span data-stu-id="41c3b-115">"Remove Servers and Server Roles" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268790">https://go.microsoft.com/fwlink/p/?LinkId=268790</A></span></span></P></LI></UL>




> [!IMPORTANT]  
> <span data-ttu-id="41c3b-116">如果您的 XMPP 同盟是透過 Lync Server 2013 Edge Server 路由傳送，舊版 Office 通訊伺服器 2007 R2 使用者將無法與 XMPP 同盟協力廠商通訊，除非所有使用者都已移至 Lync Server 2013、已設定 XMPP 原則和憑證，所以已在 Lync Server 2013 上設定 XMPP 同盟協力廠商，最後更新 DNS 專案。</span><span class="sxs-lookup"><span data-stu-id="41c3b-116">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Office Communications Server 2007 R2 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



<span data-ttu-id="41c3b-117">若要在新增或移除伺服器角色時順利發行、啟用或停用拓撲，您應該以 RTCUniversalServerAdmins 和 Domain Admins 群組成員的使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="41c3b-117">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="41c3b-118">此外也可委派正確的使用者權限來新增伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="41c3b-118">It is also possible to delegate the proper user rights and permissions for adding server roles.</span></span> <span data-ttu-id="41c3b-119">如需詳細資訊，請參閱 Standard Edition server 或 Enterprise Edition server 部署檔中的[Lync server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="41c3b-119">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="41c3b-120">若要進行其他組態變更，則僅需要 RTCUniversalServerAdmins 群組中的成員資格。</span><span class="sxs-lookup"><span data-stu-id="41c3b-120">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="41c3b-121">從 Lync Server 2013 網站移除舊版同盟關聯</span><span class="sxs-lookup"><span data-stu-id="41c3b-121">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="41c3b-122">使用拓撲產生器，開啟試驗集區拓撲。</span><span class="sxs-lookup"><span data-stu-id="41c3b-122">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="41c3b-123">在左窗格中，瀏覽至該站台節點。</span><span class="sxs-lookup"><span data-stu-id="41c3b-123">In the left pane, navigate to the site node.</span></span>

3.  <span data-ttu-id="41c3b-124">以滑鼠右鍵按一下站台，然後按一下 [編輯屬性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="41c3b-124">Right-click the site, and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="41c3b-125">選取左窗格中的 [同盟路由]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="41c3b-125">Select **Federation route** in the left pane.</span></span>

5.  <span data-ttu-id="41c3b-126">在 [網站同盟路由指派] 底下，清除 [**啟用 SIP 同盟**] 旁邊的核取方塊，以停用通過**BackCompatSite**的同盟路由。</span><span class="sxs-lookup"><span data-stu-id="41c3b-126">Under Site federation route assignment, clear the check box next to **Enable SIP federation** to disable the federation route through the **BackCompatSite**.</span></span>
    
    <span data-ttu-id="41c3b-127">![[編輯屬性] 對話方塊，同盟路由](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "[編輯屬性] 對話方塊，同盟路由")</span><span class="sxs-lookup"><span data-stu-id="41c3b-127">![Edit Properties dialog, Federation route](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Edit Properties dialog, Federation route")</span></span>

6.  <span data-ttu-id="41c3b-128">按一下 [確定]\*\*\*\*，以關閉 [編輯屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="41c3b-128">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="41c3b-129">從 [**拓撲**產生器] 中，選取上方節點 [ **Lync Server**]。</span><span class="sxs-lookup"><span data-stu-id="41c3b-129">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="41c3b-130">從 [**動作**] 功能表中，按一下 [**發行拓撲**]，然後完成嚮導。</span><span class="sxs-lookup"><span data-stu-id="41c3b-130">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="41c3b-131">將舊版 Edge Server 設定成非同盟 Edge Server</span><span class="sxs-lookup"><span data-stu-id="41c3b-131">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="41c3b-132">從 [**拓撲**產生器] 的 [**動作**] 功能表中，按一下 [**合併 Office 通訊伺服器 2007 R2 拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="41c3b-132">From **Topology Builder**, from the **Action** menu click **Merge Office Communications Server 2007 R2 Topology**.</span></span>

2.  <span data-ttu-id="41c3b-133">按 [下一步]\*\*\*\* 繼續。</span><span class="sxs-lookup"><span data-stu-id="41c3b-133">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="41c3b-134">在 [指定 Edge 設定]\*\*\*\* 中，選取您目前設定以進行同盟的 [Edge Server 內部 FQDN]\*\*\*\*，然後按一下 [變更]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="41c3b-134">On the **Specify Edge Setup**, select the **Edge Server Internal FQDN** that is currently configured for federation, and then click **Change**.</span></span>
    
    <span data-ttu-id="41c3b-135">![合併 OCS 2007 R2 拓撲，指定 Edge 設定](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "合併 OCS 2007 R2 拓撲，指定 Edge 設定")</span><span class="sxs-lookup"><span data-stu-id="41c3b-135">![Merge OCS 2007 R2 Topology, Specify Edge Setup](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Merge OCS 2007 R2 Topology, Specify Edge Setup")</span></span>

4.  <span data-ttu-id="41c3b-136">按 [下一步]\*\*\*\* 並接受預設值，直到抵達 [指定外部 Edge]\*\*\*\* 頁面為止：</span><span class="sxs-lookup"><span data-stu-id="41c3b-136">Click **Next** and accept the default settings until you get to the **Specify External Edge** page:</span></span>
    
    <span data-ttu-id="41c3b-137">![拓撲產生器的 [指定外部 Edge] 頁面](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "拓撲產生器的 [指定外部 Edge] 頁面")</span><span class="sxs-lookup"><span data-stu-id="41c3b-137">![Topology Builder Specify External Edge page](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Topology Builder Specify External Edge page")</span></span>

5.  <span data-ttu-id="41c3b-138">In **Specify External Edge**, clear the **This Edge pool is used for federation and public IM connectivity** check box.</span><span class="sxs-lookup"><span data-stu-id="41c3b-138">In **Specify External Edge**, clear the **This Edge pool is used for federation and public IM connectivity** check box.</span></span> <span data-ttu-id="41c3b-139">This will remove the federation association with the BackCompatSite.</span><span class="sxs-lookup"><span data-stu-id="41c3b-139">This will remove the federation association with the BackCompatSite.</span></span>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="41c3b-140">This step is important.</span><span class="sxs-lookup"><span data-stu-id="41c3b-140">This step is important.</span></span> <span data-ttu-id="41c3b-141">You must clear this option to remove the legacy federation association.</span><span class="sxs-lookup"><span data-stu-id="41c3b-141">You must clear this option to remove the legacy federation association.</span></span>



6.  <span data-ttu-id="41c3b-142">按 [下一步]\*\*\*\* 並接受精靈剩餘頁面的預設值。</span><span class="sxs-lookup"><span data-stu-id="41c3b-142">Click **Next** and accept the default settings of the remaining pages of the wizard.</span></span>

7.  <span data-ttu-id="41c3b-143">在 [摘要]\*\*\*\* 中按 [下一步]\*\*\*\*，以開始合併拓撲。</span><span class="sxs-lookup"><span data-stu-id="41c3b-143">In **Summary**, click **Next** to begin merging the topologies.</span></span>

8.  <span data-ttu-id="41c3b-144">在 [**狀態**] 欄中，確認值為 [**成功**]，然後按一下 **[完成**] 以關閉嚮導。</span><span class="sxs-lookup"><span data-stu-id="41c3b-144">In the **Status** column, verify that the value is **Success**, and then click **Finish** to close the wizard.</span></span>

9.  <span data-ttu-id="41c3b-145">從 [**動作**] 功能表中，選取 [**發行拓撲**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="41c3b-145">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

10. <span data-ttu-id="41c3b-146">當 [發行精靈]\*\*\*\* 完成之後，按一下 [完成]\*\*\*\*，以關閉精靈。</span><span class="sxs-lookup"><span data-stu-id="41c3b-146">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>
    
    <span data-ttu-id="41c3b-147">![在合併後顯示網站的拓撲產生器](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "在合併後顯示網站的拓撲產生器")</span><span class="sxs-lookup"><span data-stu-id="41c3b-147">![Topology Builder with site displayed after merge](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Topology Builder with site displayed after merge")</span></span>
    
    <span data-ttu-id="41c3b-148">如上圖所示，[**網站同盟路由指派**] 底下的**SIP 同盟**設定為 [**已停用**]。</span><span class="sxs-lookup"><span data-stu-id="41c3b-148">As shown in the previous figure, the **SIP federation** located under **Site federation route assignment** is set to **Disabled**.</span></span>

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="41c3b-149">在 Lync Server 2013 Edge Server 上設定憑證</span><span class="sxs-lookup"><span data-stu-id="41c3b-149">To configure certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="41c3b-150">從舊版 Office 通訊伺服器 2007 R2 Edge Server 匯出外部存取 Proxy 憑證與私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="41c3b-150">Export the external Access Proxy certificate, with the private key, from the legacy Office Communications Server 2007 R2 Edge Server.</span></span>

2.  <span data-ttu-id="41c3b-151">在 Lync Server 2013 Edge Server 上，匯入上一個步驟中的 Access Proxy 外部憑證。</span><span class="sxs-lookup"><span data-stu-id="41c3b-151">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="41c3b-152">將 Access Proxy 外部憑證指派給 Edge Server 的 Lync Server 2013 外部介面。</span><span class="sxs-lookup"><span data-stu-id="41c3b-152">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="41c3b-153">不應變更 Lync Server 2013 Edge Server 的內部介面憑證。</span><span class="sxs-lookup"><span data-stu-id="41c3b-153">The internal interface certificate of the Lync Server 2013 Edge Server should not be changed.</span></span>

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="41c3b-154">若要變更 Office 通訊伺服器 2007 R2 同盟路由以使用 Lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="41c3b-154">To change Office Communications Server 2007 R2 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="41c3b-155">在 Office 通訊伺服器 2007 R2 Standard Edition server 或前端伺服器上，開啟 Office 通訊伺服器 2007 R2 系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="41c3b-155">On the Office Communications Server 2007 R2 Standard Edition server or Front End Server, open the Office Communications Server 2007 R2 Administrative tool.</span></span>

2.  <span data-ttu-id="41c3b-156">In the left pane, expand the top node, and then right-click the **Forest** node.</span><span class="sxs-lookup"><span data-stu-id="41c3b-156">In the left pane, expand the top node, and then right-click the **Forest** node.</span></span> <span data-ttu-id="41c3b-157">Select **Properties**, and then click **Global Properties**.</span><span class="sxs-lookup"><span data-stu-id="41c3b-157">Select **Properties**, and then click **Global Properties**.</span></span>

3.  <span data-ttu-id="41c3b-158">按一下 [同盟]\*\*\*\* 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="41c3b-158">Click the **Federation** tab.</span></span>

4.  <span data-ttu-id="41c3b-159">選取核取方塊以啟用同盟與公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="41c3b-159">Select the check box to enable federation and Public IM connectivity.</span></span>

5.  <span data-ttu-id="41c3b-160">輸入 Lync Server 2013 Edge Server 的 FQDN，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="41c3b-160">Enter the FQDN of the Lync Server 2013 Edge Server, and then click **OK**.</span></span>
    
    <span data-ttu-id="41c3b-161">![OCS 全域屬性，[同盟] 索引標籤](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS 全域屬性，[同盟] 索引標籤")</span><span class="sxs-lookup"><span data-stu-id="41c3b-161">![OCS Global Properties, Federation tab](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS Global Properties, Federation tab")</span></span>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="41c3b-162">開啟 Lync Server 2013 Edge Server federation</span><span class="sxs-lookup"><span data-stu-id="41c3b-162">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="41c3b-163">在 [拓撲產生器] 的左窗格中，流覽至 [Lync Server 2013 **Edge pool** ] 節點。</span><span class="sxs-lookup"><span data-stu-id="41c3b-163">From Topology Builder, in the left pane, navigate to the Lync Server 2013 **Edge pools** node.</span></span>

2.  <span data-ttu-id="41c3b-164">展開節點，再以滑鼠右鍵按一下所列出的 Edge Server，然後按一下 [編輯屬性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="41c3b-164">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="41c3b-165">只可對單一 Edge 集區啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="41c3b-165">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="41c3b-166">如果您有多個 Edge 集區，請選取其中一個做為同盟 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="41c3b-166">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>



3.  <span data-ttu-id="41c3b-167">選取 [一般]\*\*\*\* 頁面的 [啟用此 Edge 集區的同盟 (連接埠 5061)]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="41c3b-167">On the **General** page, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
    <span data-ttu-id="41c3b-168">![編輯內容，一般，啟用 Edge Federation](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "編輯內容，一般，啟用 Edge Federation")</span><span class="sxs-lookup"><span data-stu-id="41c3b-168">![Edit Properties, General, Enable Edge Federation](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Edit Properties, General, Enable Edge Federation")</span></span>

4.  <span data-ttu-id="41c3b-169">按一下 [確定]\*\*\*\*，以關閉 [編輯屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="41c3b-169">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="41c3b-170">然後，瀏覽至站台節點。</span><span class="sxs-lookup"><span data-stu-id="41c3b-170">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="41c3b-171">以滑鼠右鍵按一下站台，然後按一下 [編輯屬性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="41c3b-171">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="41c3b-172">在左窗格中，按一下 [同盟路由]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="41c3b-172">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="41c3b-173">在 [**網站同盟路由指派**] 底下，選取 [**啟用 SIP 同盟**]，然後從清單中選取所列的 Lync server 2013 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="41c3b-173">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>

9.  <span data-ttu-id="41c3b-174">按一下 [確定]\*\*\*\* 關閉 [編輯內容]\*\*\*\* 頁面。</span><span class="sxs-lookup"><span data-stu-id="41c3b-174">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="41c3b-175">![編輯內容，一般，關聯 Edge 集區](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "編輯內容，一般，關聯 Edge 集區")</span><span class="sxs-lookup"><span data-stu-id="41c3b-175">![Edit Properties, General, Associate Edge pool](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>
    
    <span data-ttu-id="41c3b-176">如有部署多個站台，請逐一在各個站台上完成此程序。</span><span class="sxs-lookup"><span data-stu-id="41c3b-176">For multi-site deployments, complete this procedure at each site.</span></span>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="41c3b-177">設定 Lync Server 2013 Edge Server 輸出媒體路徑</span><span class="sxs-lookup"><span data-stu-id="41c3b-177">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="41c3b-178">在 [**拓撲**產生器] 中，流覽至 [ **Standard Edition 前端伺服器**] 或 [ **Enterprise edition 前端**集區] 底下的 [Lync Server 2013 集區]。</span><span class="sxs-lookup"><span data-stu-id="41c3b-178">From **Topology Builder**, navigate to the Lync Server 2013 pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="41c3b-179">以滑鼠右鍵按一下集區，然後按一下 [編輯屬性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="41c3b-179">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="41c3b-180">選取 [關聯]\*\*\*\* 區段底下的 [關聯 Edge 集區 (適用於媒體元件)]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="41c3b-180">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>

4.  <span data-ttu-id="41c3b-181">從下拉式清單方塊中，選取 [Lync Server 2013 Edge Server]。</span><span class="sxs-lookup"><span data-stu-id="41c3b-181">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>
    
    <span data-ttu-id="41c3b-182">![[編輯屬性] 對話方塊，關聯 Edge 集區](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "[編輯屬性] 對話方塊，關聯 Edge 集區")</span><span class="sxs-lookup"><span data-stu-id="41c3b-182">![Edit Properties dialog, Associate Edge Pool](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Edit Properties dialog, Associate Edge Pool")</span></span>

5.  <span data-ttu-id="41c3b-183">按一下 [確定]\*\*\*\* 關閉 [編輯內容]\*\*\*\* 頁面。</span><span class="sxs-lookup"><span data-stu-id="41c3b-183">Click **OK** to close the **Edit Properties** page.</span></span>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="41c3b-184">發行 Edge Server 的設定變更</span><span class="sxs-lookup"><span data-stu-id="41c3b-184">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="41c3b-185">從 [**拓撲**產生器] 中，選取上方節點 [ **Lync Server**]。</span><span class="sxs-lookup"><span data-stu-id="41c3b-185">From **Topology Builder**, select the top node **Lync Server**.</span></span>

2.  <span data-ttu-id="41c3b-186">從 [動作]\*\*\*\* 功能表中，選取 [發行拓撲]\*\*\*\*，然後完成精靈。</span><span class="sxs-lookup"><span data-stu-id="41c3b-186">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="41c3b-187">等候部署中所有集區的 Active Directory 複寫作業開始。</span><span class="sxs-lookup"><span data-stu-id="41c3b-187">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="41c3b-188">您將會見到下列訊息：</span><span class="sxs-lookup"><span data-stu-id="41c3b-188">You may see the following message:</span></span><BR><span data-ttu-id="41c3b-189"><STRONG>警告：拓撲包含多個同盟 Edge Server。移轉至最新版本的產品時可能會發生此問題。在這個情況下，僅會啟動一個 Edge Server 以主動用於同盟。請確認外部 DNS SRV 記錄有指向正確的 Edge Server。若您想同時部署多部主動的同盟 Edge Server (亦即，不是在移轉案例中)，請確認所有同盟協力廠商都是使用 Office Communications Server 2007 R2 或 Lync Server，並確認外部 DNS SRV 記錄有提列所有啟用同盟的 Edge Servers。</STRONG></span><span class="sxs-lookup"><span data-stu-id="41c3b-189"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Office Communications Server 2007 R2 or Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="41c3b-190">此為預期中的警告，可以不予理會。</span><span class="sxs-lookup"><span data-stu-id="41c3b-190">This warning is expected and can be safely ignored.</span></span>



## <a name="to-verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="41c3b-191">確認外部使用者的同盟及遠端存取</span><span class="sxs-lookup"><span data-stu-id="41c3b-191">To verify federation and remote access for external users</span></span>

1.  <span data-ttu-id="41c3b-192">在 Lync Server 2013 前端伺服器上，開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="41c3b-192">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="41c3b-193">若要確認同盟及遠端存取的狀態，請從命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="41c3b-193">To verify the status of federation and remote access, from the command line, type the following:</span></span>
    
        Get-CsAccessEdgeConfiguration

3.  <span data-ttu-id="41c3b-194">若要啟用同盟和遠端存取，請在命令列中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="41c3b-194">To enable federation and remote access, from the command line, type the following:</span></span>
    
        Set-CsAccessEdgeConfiguration
    
    <span data-ttu-id="41c3b-195">如需這些 Cmdlet 的詳細資訊，請參閱下列主題： [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg398574\(v=ocs.15\))和[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg413017\(v=ocs.15\))。</span><span class="sxs-lookup"><span data-stu-id="41c3b-195">For more information on these cmdlets, see the following topics: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg398574\(v=ocs.15\)) and [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg413017\(v=ocs.15\)).</span></span>

4.  <span data-ttu-id="41c3b-196">請等到複寫完成後，才能讓 Lync Server 2013 Edge server 成為線上，並測試同盟與外部存取。</span><span class="sxs-lookup"><span data-stu-id="41c3b-196">Wait until replication has completed before bringing the Lync Server 2013 Edge servers online, and testing federation and external access.</span></span>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="41c3b-197">設定 Lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="41c3b-197">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="41c3b-198">讓所有的 Lync Server 2013 Edge server 線上。</span><span class="sxs-lookup"><span data-stu-id="41c3b-198">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="41c3b-199">更新外部防火牆路由規則或硬體負載平衡器設定，以將外部存取（通常是埠443）及同盟（通常是埠5061）的 SIP 流量傳送至 Lync Server 2013 Edge Server，而不是使用舊版 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="41c3b-199">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="41c3b-200">如果您沒有硬體負載平衡器，則必須更新同盟的 DNS A 記錄，以解析新的 Lync Server Access Edge server。</span><span class="sxs-lookup"><span data-stu-id="41c3b-200">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve the new Lync Server Access Edge server.</span></span> <span data-ttu-id="41c3b-201">若要達到最低的中斷，請減少外部 Lync Server Access Edge FQDN 的 TTL 值，以便在更新 DNS 以指向新的 Lync Server Access Edge server 時，會快速更新同盟和遠端存取。</span><span class="sxs-lookup"><span data-stu-id="41c3b-201">To accomplish this with minimum disruption, reduce the TTL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge server, federation and remote access will be updated quickly.</span></span>



3.  <span data-ttu-id="41c3b-202">接下來，停止每台 Edge Server 電腦的**Lync Server Access Edge** 。</span><span class="sxs-lookup"><span data-stu-id="41c3b-202">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="41c3b-203">從每個舊版 Edge Server 電腦上，從 [系統**管理工具**] 中開啟 [**服務**] 小程式。</span><span class="sxs-lookup"><span data-stu-id="41c3b-203">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="41c3b-204">在服務清單中，尋找 [Office Communications Server Access Edge]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="41c3b-204">In the services list, find **Office Communications Server Access Edge**.</span></span>

6.  <span data-ttu-id="41c3b-205">以滑鼠右鍵按一下服務名稱，然後選取 [停止]\*\*\*\* 停止服務。</span><span class="sxs-lookup"><span data-stu-id="41c3b-205">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="41c3b-206">將 [啟動類型] 設為 [停用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="41c3b-206">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="41c3b-207">按一下 [確定]\*\*\*\*，以關閉 [屬性]\*\*\*\* 視窗。</span><span class="sxs-lookup"><span data-stu-id="41c3b-207">Click **OK** to close the **Properties** window.</span></span>

## <a name="to-test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="41c3b-208">測試外部使用者與外部存取的連線能力</span><span class="sxs-lookup"><span data-stu-id="41c3b-208">To Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="41c3b-209">至少一個同盟網域的使用者、Lync Server 2013 上的內部使用者，以及 Office 通訊伺服器 2007 R2 上的使用者。</span><span class="sxs-lookup"><span data-stu-id="41c3b-209">Users from at least one federated domain, an internal user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="41c3b-210">測試立即訊息 (IM)、目前狀態、音訊/視訊 (A/V) 及桌面共用。</span><span class="sxs-lookup"><span data-stu-id="41c3b-210">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="41c3b-211">您的組織支援的每個公用 IM 服務提供者（及布建已完成）的使用者，與 Lync Server 2013 上的使用者和 Office 通訊伺服器 2007 R2 上的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="41c3b-211">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="41c3b-212">確認匿名使用者可以加入會議。</span><span class="sxs-lookup"><span data-stu-id="41c3b-212">Verify anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="41c3b-213">使用遠端使用者存取（從內部網路外部（但不含 VPN）2007登錄 office 通訊伺服器 2007 R2 的使用者，與 Lync Server 2013 上的使用者，以及 Office 通訊伺服器 2007 R2 上的使用者。</span><span class="sxs-lookup"><span data-stu-id="41c3b-213">A user hosted on Office Communications Server 2007 R2 using remote user access (logging into Office Communications Server 2007 R2 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="41c3b-214">測試 IM、目前狀態、A/V 及桌面共用。</span><span class="sxs-lookup"><span data-stu-id="41c3b-214">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="41c3b-215">在 lync server 2013 上主控的使用者，該使用者是在 lync server 2013 上使用遠端使用者存取（從內部網路以外的地方登入 Lync Server 2013），以及 Office 通訊伺服器 2007 R2 上的使用者。</span><span class="sxs-lookup"><span data-stu-id="41c3b-215">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="41c3b-216">測試 IM、目前狀態、A/V 及桌面共用。</span><span class="sxs-lookup"><span data-stu-id="41c3b-216">Test IM, presence, A/V, and desktop sharing.</span></span>

