---
title: Lync Server 2013：建立語音原則及設定 PSTN 使用記錄
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a voice policy and configure PSTN usage records
ms:assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399027(v=OCS.15)
ms:contentKeyID: 48185693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c11eafa265bf2ba20e8a68a84231092dcb01ffa3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977732"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="84bd0-102">在 Lync Server 2013 中建立語音原則和設定 PSTN 使用記錄</span><span class="sxs-lookup"><span data-stu-id="84bd0-102">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84bd0-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="84bd0-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="84bd0-104">如果您想要建立新的語音原則，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="84bd0-104">Follow these steps if you want to create a new voice policy.</span></span> <span data-ttu-id="84bd0-105">如果您想要編輯語音原則，請參閱[修改語音原則以及在 Lync Server 2013 中設定 PSTN 使用記錄](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)，以取得程式。</span><span class="sxs-lookup"><span data-stu-id="84bd0-105">If you want to edit a voice policy, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="84bd0-106">每個語音原則都必須至少有一個相關聯的公用交換電話網絡（PSTN）使用量記錄。</span><span class="sxs-lookup"><span data-stu-id="84bd0-106">Each voice policy must have at least one associated public switched telephone network (PSTN) usage record.</span></span> <span data-ttu-id="84bd0-107">若要查看企業語音部署中所有可用的 PSTN 使用記錄清單，並查看其屬性，請參閱<A href="lync-server-2013-view-pstn-usage-records.md">在 Lync Server 2013 中查看 pstn 使用狀況記錄</A>。</span><span class="sxs-lookup"><span data-stu-id="84bd0-107">To see a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-a-voice-policy"></a><span data-ttu-id="84bd0-108">建立語音原則</span><span class="sxs-lookup"><span data-stu-id="84bd0-108">To create a voice policy</span></span>

1.  <span data-ttu-id="84bd0-109">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="84bd0-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="84bd0-110">如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="84bd0-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="84bd0-111">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="84bd0-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="84bd0-112">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="84bd0-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="84bd0-113">在左側導覽列中，按一下 [**語音路由**]，然後按一下 [**語音策略**]。</span><span class="sxs-lookup"><span data-stu-id="84bd0-113">In the left navigation bar, click **Voice Routing** and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="84bd0-114">在 [**語音原則**] 頁面上，按一下 [**新增**]，然後選取新原則的範圍：</span><span class="sxs-lookup"><span data-stu-id="84bd0-114">On the **Voice Policy** page, click **New** and then select a scope for the new policy:</span></span>
    
      - <span data-ttu-id="84bd0-115">除了任何指派給使用者原則的使用者或群組之外，**網站原則**也適用于整個網站。</span><span class="sxs-lookup"><span data-stu-id="84bd0-115">**Site policy** applies to an entire site, except any users or groups that are assigned to a user policy.</span></span> <span data-ttu-id="84bd0-116">如果您為原則範圍選取 [網站]，請從 [**選取網站**] 對話方塊中選擇網站。</span><span class="sxs-lookup"><span data-stu-id="84bd0-116">If you select Site for a policy scope, choose the site from the **Select a Site** dialog box.</span></span> <span data-ttu-id="84bd0-117">如果已為網站建立語音原則，該網站不會出現在 [**選取網站**] 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="84bd0-117">If a voice policy has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>
    
      - <span data-ttu-id="84bd0-118">**使用者原則**可以套用至指定的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="84bd0-118">**User policy** can be applied to specified users or groups.</span></span>

5.  <span data-ttu-id="84bd0-119">如果語音原則範圍是 User，請在 [Name] （**名稱**）欄位中，輸入原則的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="84bd0-119">If the voice policy scope is User, enter a descriptive name for the policy in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="84bd0-120">如果語音原則範圍是 [網站]，<STRONG>新語音原則</STRONG>中的 [Name] （<STRONG>名稱</STRONG>）欄位會預先填入網站名稱，且無法變更。</span><span class="sxs-lookup"><span data-stu-id="84bd0-120">If the voice policy scope is Site, the <STRONG>Name</STRONG> field in <STRONG>New Voice Policy</STRONG> is prepopulated with the site name and cannot be changed.</span></span>

    
    </div>

6.  <span data-ttu-id="84bd0-121">可選輸入語音原則的其他描述性資訊。</span><span class="sxs-lookup"><span data-stu-id="84bd0-121">(Optional) Enter additional descriptive information for the voice policy.</span></span>

7.  <span data-ttu-id="84bd0-122">選取或清除下列核取方塊，以啟用或停用此語音原則的每個**通話功能**：</span><span class="sxs-lookup"><span data-stu-id="84bd0-122">Select or clear the following check boxes to enable or disable each of the **Calling features** for this voice policy:</span></span>
    
      - <span data-ttu-id="84bd0-123">**語音信箱轉義**可防止呼叫在同時進行同時撥打，且手機已關閉、不在電池或超出範圍時，立即路由到使用者的行動電話語音信箱系統。</span><span class="sxs-lookup"><span data-stu-id="84bd0-123">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="84bd0-124">此功能僅可透過 Lync Server Management 命令介面進行設定</span><span class="sxs-lookup"><span data-stu-id="84bd0-124">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="84bd0-125">[**來電轉接**] 可讓使用者將來電轉接至其他電話與用戶端裝置。</span><span class="sxs-lookup"><span data-stu-id="84bd0-125">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="84bd0-126">Lync Server 2013 為來電轉接提供了相當廣泛的配置選項。</span><span class="sxs-lookup"><span data-stu-id="84bd0-126">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="84bd0-127">例如，如果組織不想允許將來電轉寄至 PSTN，系統管理員可以套用特殊的語音原則來部署此限制。</span><span class="sxs-lookup"><span data-stu-id="84bd0-127">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="84bd0-128">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="84bd0-128">Enabled by default.</span></span>
    
      - <span data-ttu-id="84bd0-129">**委派**可讓使用者指定其他使用者代表自己傳送和接收來電。</span><span class="sxs-lookup"><span data-stu-id="84bd0-129">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="84bd0-130">在 Lync Server 2013 中，代理人可以設定同時撥打的電話，讓他/她的主管撥打電話給所有代理人同時撥打的目標。</span><span class="sxs-lookup"><span data-stu-id="84bd0-130">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="84bd0-131">這可為委派提供更大的彈性，以回應導向給 manager 的呼叫。</span><span class="sxs-lookup"><span data-stu-id="84bd0-131">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="84bd0-132">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="84bd0-132">Enabled by default.</span></span>
    
      - <span data-ttu-id="84bd0-133">[**來電轉接**] 可讓使用者將來電轉接給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="84bd0-133">**Call transfer** enables users to transfer calls to other users.</span></span> <span data-ttu-id="84bd0-134">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="84bd0-134">Enabled by default.</span></span>
    
      - <span data-ttu-id="84bd0-135">**通話寄存**可讓使用者保留通話，然後從不同的電話或用戶端挑選通話。</span><span class="sxs-lookup"><span data-stu-id="84bd0-135">**Call park** enables users to park calls on hold and then pick up the call from a different phone or client.</span></span> <span data-ttu-id="84bd0-136">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="84bd0-136">Disabled by default.</span></span>
    
      - <span data-ttu-id="84bd0-137">**同時撥打**可讓來電撥打其他手機（例如行動電話）或其他端點裝置。</span><span class="sxs-lookup"><span data-stu-id="84bd0-137">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="84bd0-138">Lync Server 2013 可提供更廣泛的配置選項以進行同時撥打。</span><span class="sxs-lookup"><span data-stu-id="84bd0-138">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="84bd0-139">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="84bd0-139">Enabled by default.</span></span>
    
      - <span data-ttu-id="84bd0-140">**團隊通話**可讓已定義的小組中的使用者接聽小組其他成員的來電。</span><span class="sxs-lookup"><span data-stu-id="84bd0-140">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="84bd0-141">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="84bd0-141">Enabled by default.</span></span>
    
      - <span data-ttu-id="84bd0-142">**PSTN 重新路由**可讓指派此原則的使用者進行呼叫，以便在 WAN 擁塞或無法使用的情況下，在公用交換電話網絡（PSTN）上重新路由。</span><span class="sxs-lookup"><span data-stu-id="84bd0-142">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable.</span></span> <span data-ttu-id="84bd0-143">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="84bd0-143">Enabled by default.</span></span>
    
      - <span data-ttu-id="84bd0-144">[**頻寬原則覆蓋**] 可讓系統管理員覆寫特定使用者的呼叫許可控制原則決定。</span><span class="sxs-lookup"><span data-stu-id="84bd0-144">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user.</span></span> <span data-ttu-id="84bd0-145">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="84bd0-145">Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="84bd0-146">此原則只會覆寫給來電給使用者，而不會覆寫給使用者發出的撥出通話。</span><span class="sxs-lookup"><span data-stu-id="84bd0-146">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user.</span></span> <span data-ttu-id="84bd0-147">會話建立之後，就會精確地記錄頻寬使用量。</span><span class="sxs-lookup"><span data-stu-id="84bd0-147">After the session is established, the bandwidth consumption will be accurately recorded.</span></span> <span data-ttu-id="84bd0-148">此設定應該謹慎使用，且應保留適當的呼叫許可控制決定。</span><span class="sxs-lookup"><span data-stu-id="84bd0-148">This setting should be used sparingly and should be reserved for appropriate call admission control decisions.</span></span>

        
        </div>
    
      - <span data-ttu-id="84bd0-149">**惡意的通話追蹤功能**可讓使用者透過用戶端 UI （例如炸彈威脅）來報告惡意通話（例如炸彈威脅），進而在通話詳細資料記錄（CDRs）中標記通話。</span><span class="sxs-lookup"><span data-stu-id="84bd0-149">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) by using the client UI, which in turn flags the calls in the call detail records (CDRs).</span></span> <span data-ttu-id="84bd0-150">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="84bd0-150">Disabled by default.</span></span>

8.  <span data-ttu-id="84bd0-151">若要關聯及設定此語音原則的 PSTN 使用記錄，請執行下列任何一項操作：</span><span class="sxs-lookup"><span data-stu-id="84bd0-151">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="84bd0-152">若要從企業語音部署中所有可用的 PSTN 使用記錄清單中選擇一或多筆記錄，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="84bd0-152">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="84bd0-153">醒目提示您想要與此語音原則相關聯的記錄，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="84bd0-153">Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="84bd0-154">若要從此語音原則中移除 PSTN 使用記錄，請醒目提示該記錄，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="84bd0-154">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="84bd0-155">若要定義新的 PSTN 使用記錄，並將它與此語音原則關聯，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="84bd0-155">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="84bd0-156">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="84bd0-156">Click **New**.</span></span>
        
        2.  <span data-ttu-id="84bd0-157">在 [**名稱**] 欄位中，為記錄輸入唯一的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="84bd0-157">In the **Name** field, enter a unique descriptive name for the record.</span></span> <span data-ttu-id="84bd0-158">例如，您可能會想要為位於雷蒙德的全職員工，以及臨時性員工的另一個命名**RedmondTemps** ，建立名為**雷蒙德**的 PSTN 使用記錄。</span><span class="sxs-lookup"><span data-stu-id="84bd0-158">For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="84bd0-159">PSTN 使用記錄名稱在企業語音部署中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="84bd0-159">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="84bd0-160">在儲存記錄之後，[<STRONG>名稱</STRONG>] 欄位就無法進行編輯。</span><span class="sxs-lookup"><span data-stu-id="84bd0-160">After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="84bd0-161">使用下列任何一種方法來關聯及設定此 PSTN 使用記錄的路線：</span><span class="sxs-lookup"><span data-stu-id="84bd0-161">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="84bd0-162">若要從企業語音部署中所有可用路由的清單中選擇一或多個路由，請按一下 [**選取**]，然後醒目提示您要與此 PSTN 使用記錄建立關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="84bd0-162">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="84bd0-163">若要從 PSTN 使用量記錄移除路由，請將路由反白顯示，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="84bd0-163">To remove a route from the PSTN usage record, highlight the route, and then click **Remove**.</span></span>
            
              - <span data-ttu-id="84bd0-164">若要定義新的路由，並將它與此 PSTN 使用量記錄建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="84bd0-164">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="84bd0-165">如需詳細資訊，請參閱[在 Lync Server 2013 中建立語音路由](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="84bd0-165">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="84bd0-166">若要編輯已與此 PSTN 使用記錄相關聯的路線，請醒目提示該路線，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="84bd0-166">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="84bd0-167">如需詳細資訊，請參閱[在 Lync Server 2013 中修改語音路線](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="84bd0-167">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="84bd0-168">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="84bd0-168">Click **OK**.</span></span>
    
      - <span data-ttu-id="84bd0-169">若要編輯已與此語音原則相關聯的 PSTN 使用記錄，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="84bd0-169">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="84bd0-170">醒目提示您要編輯的 PSTN 使用記錄，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="84bd0-170">Highlight the PSTN usage record that you want to edit, and then click **Show details**.</span></span>
        
        2.  <span data-ttu-id="84bd0-171">使用下列任何一種方法來關聯及設定此 PSTN 使用記錄的路線：</span><span class="sxs-lookup"><span data-stu-id="84bd0-171">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="84bd0-172">若要從企業語音部署中的所有可用路由清單中選擇一或多個路由，請按一下 [**選取**]，然後醒目提示您要與此 PSTN 使用記錄建立關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="84bd0-172">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="84bd0-173">若要從這個 PSTN 使用記錄移除路由，請將路由反白顯示，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="84bd0-173">To remove a route from this PSTN usage record, highlight the route, and then click **Remove**.</span></span>
            
              - <span data-ttu-id="84bd0-174">若要定義新的路由，並將它與此 PSTN 使用量記錄建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="84bd0-174">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="84bd0-175">如需詳細資訊，請參閱[在 Lync Server 2013 中建立語音路由](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="84bd0-175">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="84bd0-176">若要編輯已與此 PSTN 使用記錄相關聯的路線，請醒目提示 [路線]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="84bd0-176">To edit a route that is already associated with this PSTN usage record, highlight the route and lick **Show details**.</span></span> <span data-ttu-id="84bd0-177">如需詳細資訊，請參閱[在 Lync Server 2013 中修改語音路線](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="84bd0-177">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="84bd0-178">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="84bd0-178">Click **OK**.</span></span>

9.  <span data-ttu-id="84bd0-179">排列 PSTN 使用狀況記錄，以獲得最佳效能。</span><span class="sxs-lookup"><span data-stu-id="84bd0-179">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="84bd0-180">若要變更記錄在清單中的位置，請醒目提示記錄名稱，然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="84bd0-180">To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="84bd0-181">PSTN 使用記錄在語音原則中列出的順序非常重要。</span><span class="sxs-lookup"><span data-stu-id="84bd0-181">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="84bd0-182">Lync Server 會從上到下遍歷清單。</span><span class="sxs-lookup"><span data-stu-id="84bd0-182">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="84bd0-183">我們建議您依使用頻率來組織清單，例如： RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup。</span><span class="sxs-lookup"><span data-stu-id="84bd0-183">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

10. <span data-ttu-id="84bd0-184">若要將 PSTN 使用記錄與此語音原則中的來電轉接和同時撥打進行關聯與設定，請執行下列任何一項操作：</span><span class="sxs-lookup"><span data-stu-id="84bd0-184">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="84bd0-185">若要使用與此語音原則相同的來電轉接和同時撥打的相同 PSTN 使用記錄，請從下拉式功能表中選取 [**呼叫 PSTN**使用方式] 的選項路由。</span><span class="sxs-lookup"><span data-stu-id="84bd0-185">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="84bd0-186">若要只允許來電轉接及同時撥打給內部 Lync 使用者，請從下拉式功能表中選取 [**僅限內部 lync 使用者的傳送**] 選項。</span><span class="sxs-lookup"><span data-stu-id="84bd0-186">To allow call forwarding and simultaneous ringing to internal Lync users only, select the option **Route to internal Lync users only** from the drop-down menu.</span></span> <span data-ttu-id="84bd0-187">通話不會轉寄到外部 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="84bd0-187">Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="84bd0-188">若要指定不同的來電轉接與此語音原則所用的 PSTN 使用記錄，請從下拉式功能表中選取 [**使用自訂 PSTN**的選項路由]。</span><span class="sxs-lookup"><span data-stu-id="84bd0-188">To specify different PSTN usage records for call forwarding and simultaneous ringing than used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu.</span></span> <span data-ttu-id="84bd0-189">這個選項會顯示一個控制項來選取現有的 PSTN 使用記錄，或專門針對來電轉接和同時撥打建立新的 PSTN 使用記錄。</span><span class="sxs-lookup"><span data-stu-id="84bd0-189">This option displays a control to select existing PSTN usage records or create new PSTN usage records specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="84bd0-190">若要從來電轉移和同時撥打的 PSTN 使用記錄清單中選擇一或多筆記錄，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="84bd0-190">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**.</span></span> <span data-ttu-id="84bd0-191">醒目提示您要與此來電轉接和同時撥打原則相關聯的記錄，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="84bd0-191">Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="84bd0-192">若要從此來電轉接和同時撥打原則移除 PSTN 使用記錄，請醒目提示該記錄，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="84bd0-192">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="84bd0-193">若要定義新的 PSTN 使用記錄，並將它與此來電轉接和同時撥打原則關聯，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="84bd0-193">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="84bd0-194">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="84bd0-194">Click **New**.</span></span>
            
            2.  <span data-ttu-id="84bd0-195">在 [**名稱**] 欄位中，為記錄輸入唯一的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="84bd0-195">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="84bd0-196">PSTN 使用記錄名稱在企業語音部署中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="84bd0-196">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="84bd0-197">在儲存記錄之後，[<STRONG>名稱</STRONG>] 欄位就無法進行編輯。</span><span class="sxs-lookup"><span data-stu-id="84bd0-197">After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="84bd0-198">使用下列任何一種方法來關聯及設定此 PSTN 使用記錄的路線：</span><span class="sxs-lookup"><span data-stu-id="84bd0-198">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="84bd0-199">若要從企業語音部署中所有可用路由的清單中選擇一或多個路由，請按一下 [**選取**]，然後醒目提示您要與此 PSTN 使用記錄建立關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="84bd0-199">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="84bd0-200">若要從 PSTN 使用量記錄移除路由，請將路由反白顯示，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="84bd0-200">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="84bd0-201">若要定義新的路由，並將它與此 PSTN 使用量記錄建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="84bd0-201">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="84bd0-202">如需詳細資訊，請參閱[在 Lync Server 2013 中建立語音路由](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="84bd0-202">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="84bd0-203">若要編輯已與此 PSTN 使用記錄相關聯的路線，請醒目提示該路線，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="84bd0-203">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="84bd0-204">如需詳細資訊，請參閱[在 Lync Server 2013 中修改語音路線](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="84bd0-204">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="84bd0-205">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="84bd0-205">Click **OK**.</span></span>
        
          - <span data-ttu-id="84bd0-206">若要編輯已與此語音原則相關聯的 PSTN 使用記錄，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="84bd0-206">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="84bd0-207">醒目提示您要編輯的 PSTN 使用記錄，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="84bd0-207">Highlight the PSTN usage record you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="84bd0-208">使用下列任何一種方法來關聯及設定此 PSTN 使用記錄的路線：</span><span class="sxs-lookup"><span data-stu-id="84bd0-208">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="84bd0-209">若要從企業語音部署中所有可用路由的清單中選擇一或多個路由，請按一下 [**選取**]，然後醒目提示您要與此 PSTN 使用記錄建立關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="84bd0-209">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="84bd0-210">若要從這個 PSTN 使用量記錄移除路由，請將路由反白顯示，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="84bd0-210">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="84bd0-211">若要定義新的路由，並將它與此 PSTN 使用量記錄建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="84bd0-211">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="84bd0-212">如需詳細資訊，請參閱[在 Lync Server 2013 中建立語音路由](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="84bd0-212">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="84bd0-213">若要編輯已與此 PSTN 使用記錄相關聯的路線，請醒目提示該路線，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="84bd0-213">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="84bd0-214">如需詳細資訊，請參閱[在 Lync Server 2013 中修改語音路線](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="84bd0-214">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="84bd0-215">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="84bd0-215">Click **OK**.</span></span>

11. <span data-ttu-id="84bd0-216">可選輸入數位以測試語音原則，然後按一下 [ **Go**] （執行）。</span><span class="sxs-lookup"><span data-stu-id="84bd0-216">(Optional) Enter a number to test the voice policy and click **Go**.</span></span> <span data-ttu-id="84bd0-217">測試結果會顯示在 [已**翻譯的號碼] 下以進行測試**。</span><span class="sxs-lookup"><span data-stu-id="84bd0-217">The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="84bd0-218">您可以儲存尚未經過測試的語音原則，稍後再重新設定。</span><span class="sxs-lookup"><span data-stu-id="84bd0-218">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="84bd0-219">如需詳細資訊，請參閱<A href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中測試語音路由</A>。</span><span class="sxs-lookup"><span data-stu-id="84bd0-219">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="84bd0-220">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="84bd0-220">Click **OK**.</span></span>

13. <span data-ttu-id="84bd0-221">在 [**語音原則**] 頁面上，按一下 [**認可**]，然後按一下 [**全部確認**]。</span><span class="sxs-lookup"><span data-stu-id="84bd0-221">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="84bd0-222">每當您建立或修改語音原則時，您都必須執行 [<STRONG>全部提交</STRONG>] 命令才能發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="84bd0-222">Any time you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="84bd0-223">如需詳細資訊，請參閱在 Operations 檔中<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">發佈 Lync Server 2013 中的語音路由設定的未決變更</A>。</span><span class="sxs-lookup"><span data-stu-id="84bd0-223">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

14. <span data-ttu-id="84bd0-224">可選語音信箱轉義會偵測到使用者的行動電話語音信箱立即接聽通話，然後中斷通話與行動電話語音信箱的連線。</span><span class="sxs-lookup"><span data-stu-id="84bd0-224">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="84bd0-225">這可讓呼叫繼續撥打使用者的其他端點，讓使用者有機會接聽通話。</span><span class="sxs-lookup"><span data-stu-id="84bd0-225">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="84bd0-226">如需如何設定語音信箱原則的詳細資料，請參閱[在 Lync Server 2013 中設定語音信箱轉義](lync-server-2013-configuring-voice-mail-escape.md)。</span><span class="sxs-lookup"><span data-stu-id="84bd0-226">For details on how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="84bd0-227">請參閱</span><span class="sxs-lookup"><span data-stu-id="84bd0-227">See Also</span></span>


[<span data-ttu-id="84bd0-228">在 Lync Server 2013 中修改語音原則和設定 PSTN 使用狀況記錄</span><span class="sxs-lookup"><span data-stu-id="84bd0-228">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="84bd0-229">在 Lync Server 2013 中查看 PSTN 使用狀況記錄</span><span class="sxs-lookup"><span data-stu-id="84bd0-229">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="84bd0-230">在 Lync Server 2013 中建立語音路由</span><span class="sxs-lookup"><span data-stu-id="84bd0-230">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="84bd0-231">在 Lync Server 2013 中修改語音路線</span><span class="sxs-lookup"><span data-stu-id="84bd0-231">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="84bd0-232">在 Lync Server 2013 中發佈語音路由設定的擱置變更</span><span class="sxs-lookup"><span data-stu-id="84bd0-232">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="84bd0-233">在 Lync Server 2013 中設定語音信箱轉義</span><span class="sxs-lookup"><span data-stu-id="84bd0-233">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="84bd0-234">在 Lync Server 2013 中測試語音路由</span><span class="sxs-lookup"><span data-stu-id="84bd0-234">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

