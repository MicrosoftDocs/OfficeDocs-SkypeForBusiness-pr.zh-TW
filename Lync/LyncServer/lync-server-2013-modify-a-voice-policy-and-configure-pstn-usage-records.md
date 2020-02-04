---
title: Lync Server 2013：修改語音原則及設定 PSTN 使用記錄
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a voice policy and configure PSTN usage records
ms:assetid: 6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398511(v=OCS.15)
ms:contentKeyID: 48184419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dda549bbb8b1f29a3aef8690a8e666e7a182bd29
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737163"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="c7950-102">在 Lync Server 2013 中修改語音原則和設定 PSTN 使用狀況記錄</span><span class="sxs-lookup"><span data-stu-id="c7950-102">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7950-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c7950-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c7950-104">如果您想要修改語音原則，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="c7950-104">Follow these steps if you want to modify a voice policy.</span></span> <span data-ttu-id="c7950-105">如果您想要建立新的語音原則，請參閱[建立語音原則，並在 Lync Server 2013 中針對程式設定 PSTN 使用記錄](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)。</span><span class="sxs-lookup"><span data-stu-id="c7950-105">If you want to create a new voice policy, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c7950-106">如果指派給語音原則的使用者沒有關聯的公用交換電話網絡（PSTN）使用記錄，使用者就無法進行撥出通話。</span><span class="sxs-lookup"><span data-stu-id="c7950-106">If a user is assigned to a voice policy has no associated public switched telephone network (PSTN) usage records, the user cannot place outbound calls.</span></span> <span data-ttu-id="c7950-107">如需企業語音部署中所有可用的 PSTN 使用記錄清單，並查看其屬性，請參閱<A href="lync-server-2013-view-pstn-usage-records.md">在 Lync Server 2013 中查看 PSTN 使用狀況記錄</A>。</span><span class="sxs-lookup"><span data-stu-id="c7950-107">For a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-modify-a-voice-policy"></a><span data-ttu-id="c7950-108">修改語音原則</span><span class="sxs-lookup"><span data-stu-id="c7950-108">To modify a voice policy</span></span>

1.  <span data-ttu-id="c7950-109">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="c7950-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="c7950-110">如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="c7950-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="c7950-111">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="c7950-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c7950-112">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="c7950-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c7950-113">在左側導覽列中，按一下 [**語音路由**]，然後按一下 [**語音策略**]。</span><span class="sxs-lookup"><span data-stu-id="c7950-113">In the left navigation bar, click **Voice Routing**, and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="c7950-114">在 [**語音原則**] 頁面上，按兩下語音原則名稱。</span><span class="sxs-lookup"><span data-stu-id="c7950-114">On the **Voice Policy** page, double-click a voice policy name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c7950-115">在建立語音原則時，會設定範圍和名稱。</span><span class="sxs-lookup"><span data-stu-id="c7950-115">The scope and name were set when the voice policy was created.</span></span> <span data-ttu-id="c7950-116">它們無法變更。</span><span class="sxs-lookup"><span data-stu-id="c7950-116">They cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="c7950-117">可選在 [**編輯語音原則**] 中，輸入語音原則的其他描述性資訊。</span><span class="sxs-lookup"><span data-stu-id="c7950-117">(Optional) In **Edit Voice Policy**, enter additional descriptive information for the voice policy.</span></span>

6.  <span data-ttu-id="c7950-118">選取或清除下列核取方塊，以啟用或停用每個**通話功能**：</span><span class="sxs-lookup"><span data-stu-id="c7950-118">Select or clear the following check boxes to enable or disable each of the **Calling features**:</span></span>
    
      - <span data-ttu-id="c7950-119">**語音信箱轉義**可防止呼叫在同時進行同時撥打，且手機已關閉、不在電池或超出範圍時，立即路由到使用者的行動電話語音信箱系統。</span><span class="sxs-lookup"><span data-stu-id="c7950-119">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c7950-120">此功能僅可透過 Lync Server Management 命令介面進行設定</span><span class="sxs-lookup"><span data-stu-id="c7950-120">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="c7950-121">[**來電轉接**] 可讓使用者將來電轉接至其他電話與用戶端裝置。</span><span class="sxs-lookup"><span data-stu-id="c7950-121">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="c7950-122">Lync Server 2013 為來電轉接提供了相當廣泛的配置選項。</span><span class="sxs-lookup"><span data-stu-id="c7950-122">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="c7950-123">例如，如果組織不想允許將來電轉寄至 PSTN，系統管理員可以套用特殊的語音原則來部署此限制。</span><span class="sxs-lookup"><span data-stu-id="c7950-123">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="c7950-124">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="c7950-124">Enabled by default.</span></span>
    
      - <span data-ttu-id="c7950-125">**委派**可讓使用者指定其他使用者代表自己傳送和接收來電。</span><span class="sxs-lookup"><span data-stu-id="c7950-125">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="c7950-126">在 Lync Server 2013 中，代理人可以設定同時撥打的電話，讓他/她的主管撥打電話給所有代理人同時撥打的目標。</span><span class="sxs-lookup"><span data-stu-id="c7950-126">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="c7950-127">這可為委派提供更大的彈性，以回應導向給 manager 的呼叫。</span><span class="sxs-lookup"><span data-stu-id="c7950-127">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="c7950-128">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="c7950-128">Enabled by default.</span></span>
    
      - <span data-ttu-id="c7950-129">[**來電轉接**] 可讓使用者將來電轉接給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="c7950-129">**Call transfer** enables users to transfer calls to other users.</span></span> <span data-ttu-id="c7950-130">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="c7950-130">Enabled by default.</span></span>
    
      - <span data-ttu-id="c7950-131">**通話寄存**可讓使用者在保留時停止通話，然後從不同的電話或用戶端挑選通話。</span><span class="sxs-lookup"><span data-stu-id="c7950-131">**Call park** enables users to park calls on hold, and then pick up the call from a different phone or client.</span></span> <span data-ttu-id="c7950-132">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="c7950-132">Disabled by default.</span></span>
    
      - <span data-ttu-id="c7950-133">**同時撥打**可讓來電撥打其他手機（例如行動電話）或其他端點裝置。</span><span class="sxs-lookup"><span data-stu-id="c7950-133">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="c7950-134">Lync Server 2013 可提供更廣泛的配置選項以進行同時撥打。</span><span class="sxs-lookup"><span data-stu-id="c7950-134">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="c7950-135">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="c7950-135">Enabled by default.</span></span>
    
      - <span data-ttu-id="c7950-136">**團隊通話**可讓已定義的小組中的使用者接聽小組其他成員的來電。</span><span class="sxs-lookup"><span data-stu-id="c7950-136">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="c7950-137">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="c7950-137">Enabled by default.</span></span>
    
      - <span data-ttu-id="c7950-138">**PSTN 重新路由**可讓指派此原則的使用者進行呼叫，以便在 WAN 擁塞或無法使用的情況下，在公用交換電話網絡（PSTN）上重新路由。</span><span class="sxs-lookup"><span data-stu-id="c7950-138">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable.</span></span> <span data-ttu-id="c7950-139">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="c7950-139">Enabled by default.</span></span>
    
      - <span data-ttu-id="c7950-140">[**頻寬原則覆蓋**] 可讓系統管理員覆寫特定使用者的呼叫許可控制（CAC）原則決策。</span><span class="sxs-lookup"><span data-stu-id="c7950-140">**Bandwidth policy override** enables administrators to override call admission control (CAC) policy decisions for a particular user.</span></span> <span data-ttu-id="c7950-141">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="c7950-141">Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c7950-142">此原則只會覆寫給來電給使用者，而不會覆寫給使用者發出的撥出通話。</span><span class="sxs-lookup"><span data-stu-id="c7950-142">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user.</span></span> <span data-ttu-id="c7950-143">會話建立之後，就會精確地記錄頻寬使用量。</span><span class="sxs-lookup"><span data-stu-id="c7950-143">After the session is established, the bandwidth consumption will be accurately recorded.</span></span> <span data-ttu-id="c7950-144">此設定應該謹慎使用。</span><span class="sxs-lookup"><span data-stu-id="c7950-144">This setting should be used sparingly.</span></span>

        
        </div>
    
      - <span data-ttu-id="c7950-145">**惡意的通話追蹤功能**可讓使用者使用用戶端 UI 報告惡意通話（例如炸彈威脅），進而在通話詳細資料記錄（CDRs）中標記通話。</span><span class="sxs-lookup"><span data-stu-id="c7950-145">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) using the client UI, which in turn flags the calls in the call detail records (CDRs).</span></span> <span data-ttu-id="c7950-146">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="c7950-146">Disabled by default.</span></span>

7.  <span data-ttu-id="c7950-147">若要關聯及設定此語音原則的 PSTN 使用記錄，請執行下列任何一項操作：</span><span class="sxs-lookup"><span data-stu-id="c7950-147">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="c7950-148">若要從企業語音部署中所有可用的 PSTN 使用記錄清單中選擇一或多筆記錄，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="c7950-148">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="c7950-149">醒目提示您想要與此語音原則相關聯的記錄，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c7950-149">Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="c7950-150">若要從此語音原則中移除 PSTN 使用記錄，請醒目提示該記錄，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="c7950-150">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="c7950-151">若要定義新的 PSTN 使用記錄，並將它與此語音原則關聯，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c7950-151">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="c7950-152">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="c7950-152">Click **New**.</span></span>
        
        2.  <span data-ttu-id="c7950-153">在 [**名稱**] 欄位中，為記錄輸入唯一的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="c7950-153">In the **Name** field, enter a unique descriptive name for the record.</span></span> <span data-ttu-id="c7950-154">例如，您可能會想要針對雷蒙德中的全職員工建立名為**redmond**的 PSTN 使用記錄，以及另一個名為 [ **RedmondTemps** ] 的其他記錄，以供暫時員工使用。</span><span class="sxs-lookup"><span data-stu-id="c7950-154">For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another record named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="c7950-155">PSTN 使用記錄名稱在企業語音部署中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="c7950-155">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="c7950-156">在儲存記錄之後，[<STRONG>名稱</STRONG>] 欄位就無法進行編輯。</span><span class="sxs-lookup"><span data-stu-id="c7950-156">After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="c7950-157">使用下列任何一種方法來關聯及設定此 PSTN 使用記錄的路線：</span><span class="sxs-lookup"><span data-stu-id="c7950-157">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="c7950-158">若要從企業語音部署中所有可用路由的清單中選擇一或多個路由，請按一下 [**選取**]，然後醒目提示您要與此 PSTN 使用記錄建立關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c7950-158">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="c7950-159">若要從 PSTN 使用量記錄移除路由，請將路由反白顯示，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="c7950-159">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="c7950-160">若要定義新的路由，並將它與此 PSTN 使用量記錄建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="c7950-160">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="c7950-161">如需詳細資訊，請參閱[在 Lync Server 2013 中建立語音路由](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="c7950-161">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="c7950-162">若要編輯已與此 PSTN 使用記錄相關聯的路線，請醒目提示該路線，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="c7950-162">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="c7950-163">如需詳細資訊，請參閱[在 Lync Server 2013 中修改語音路線](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="c7950-163">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="c7950-164">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c7950-164">Click **OK**.</span></span>
    
      - <span data-ttu-id="c7950-165">若要編輯已與此語音原則相關聯的 PSTN 使用記錄，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c7950-165">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="c7950-166">醒目提示您要編輯的 PSTN 使用記錄，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="c7950-166">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="c7950-167">使用下列任何一種方法來關聯及設定此 PSTN 使用記錄的路線：</span><span class="sxs-lookup"><span data-stu-id="c7950-167">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="c7950-168">若要從企業語音部署中所有可用路由的清單中選擇一或多個路由，請按一下 [**選取**]，然後醒目提示您要與此 PSTN 使用記錄建立關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c7950-168">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="c7950-169">若要從這個 PSTN 使用量記錄移除路由，請將路由反白顯示，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="c7950-169">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="c7950-170">若要定義新的路由，並將它與此 PSTN 使用量記錄建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="c7950-170">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="c7950-171">如需詳細資訊，請參閱[在 Lync Server 2013 中建立語音路由](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="c7950-171">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="c7950-172">若要編輯已與此 PSTN 使用記錄相關聯的路線，請醒目提示該路線，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="c7950-172">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="c7950-173">如需詳細資訊，請參閱[在 Lync Server 2013 中修改語音路線](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="c7950-173">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="c7950-174">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c7950-174">Click **OK**.</span></span>

8.  <span data-ttu-id="c7950-175">排列 PSTN 使用狀況記錄，以獲得最佳效能。</span><span class="sxs-lookup"><span data-stu-id="c7950-175">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="c7950-176">若要變更記錄在清單中的位置，請醒目提示記錄名稱，然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="c7950-176">To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c7950-177">PSTN 使用記錄在語音原則中列出的順序非常重要。</span><span class="sxs-lookup"><span data-stu-id="c7950-177">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="c7950-178">Lync Server 會從上到下遍歷清單。</span><span class="sxs-lookup"><span data-stu-id="c7950-178">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="c7950-179">我們建議您依使用頻率來組織清單，例如： RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup。</span><span class="sxs-lookup"><span data-stu-id="c7950-179">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

9.  <span data-ttu-id="c7950-180">若要將 PSTN 使用記錄與此語音原則中的來電轉接和同時撥打進行關聯與設定，請執行下列任何一項操作：</span><span class="sxs-lookup"><span data-stu-id="c7950-180">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="c7950-181">若要使用與此語音原則相同的來電轉接和同時撥打的相同 PSTN 使用記錄，請從下拉式功能表中選取 [**呼叫 PSTN**使用方式] 的選項路由。</span><span class="sxs-lookup"><span data-stu-id="c7950-181">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="c7950-182">若要允許來電轉接及同時撥打至僅限內部 Lync 使用者，請選取 [僅從下拉式功能表**傳送給內部 lync 使用者**]。</span><span class="sxs-lookup"><span data-stu-id="c7950-182">To allow call forwarding and simultaneous ringing to internal Lync users only, select **Route to internal Lync users only** from the drop-down menu.</span></span> <span data-ttu-id="c7950-183">通話不會轉寄到外部 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="c7950-183">Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="c7950-184">若要指定不同于此語音原則來電轉接和同時撥打的 PSTN 使用記錄，請從下拉式功能表中選取 [**使用自訂 PSTN**的選項傳送]。</span><span class="sxs-lookup"><span data-stu-id="c7950-184">To specify different PSTN usage records for call forwarding and simultaneous ringing than those used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu.</span></span> <span data-ttu-id="c7950-185">這個選項會顯示一個控制項，可選取現有的 PSTN 使用記錄，或建立新的 PSTN 使用記錄，特別是來電轉接和同時撥打。</span><span class="sxs-lookup"><span data-stu-id="c7950-185">This option displays a control to select existing PSTN usage records or to create new PSTN usage records, specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="c7950-186">若要從來電轉移和同時撥打的 PSTN 使用記錄清單中選擇一或多筆記錄，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="c7950-186">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**.</span></span> <span data-ttu-id="c7950-187">醒目提示您要與此來電轉接和同時撥打原則相關聯的記錄，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c7950-187">Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="c7950-188">若要從此來電轉接和同時撥打原則移除 PSTN 使用記錄，請醒目提示該記錄，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="c7950-188">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="c7950-189">若要定義新的 PSTN 使用記錄，並將它與此來電轉接和同時撥打原則關聯，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c7950-189">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="c7950-190">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="c7950-190">Click **New**.</span></span>
            
            2.  <span data-ttu-id="c7950-191">在 [**名稱**] 欄位中，為記錄輸入唯一的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="c7950-191">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="c7950-192">PSTN 使用記錄名稱在企業語音部署中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="c7950-192">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="c7950-193">在儲存記錄之後，[<STRONG>名稱</STRONG>] 欄位就無法進行編輯。</span><span class="sxs-lookup"><span data-stu-id="c7950-193">After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="c7950-194">使用下列任何一種方法來關聯及設定此 PSTN 使用記錄的路線：</span><span class="sxs-lookup"><span data-stu-id="c7950-194">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="c7950-195">若要從企業語音部署中所有可用路由的清單中選擇一或多個路由，請按一下 [**選取**]，然後醒目提示您要與此 PSTN 使用記錄建立關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c7950-195">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="c7950-196">若要從 PSTN 使用量記錄移除路由，請將路由反白顯示，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="c7950-196">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="c7950-197">若要定義新的路由，並將它與此 PSTN 使用量記錄建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="c7950-197">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="c7950-198">如需詳細資訊，請參閱[在 Lync Server 2013 中建立語音路由](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="c7950-198">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="c7950-199">若要編輯已與此 PSTN 使用記錄相關聯的路線，請醒目提示該路線，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="c7950-199">To edit a route that is already associated with this PSTN usage record, highlight the route, and then click **Show details**.</span></span> <span data-ttu-id="c7950-200">如需詳細資訊，請參閱[在 Lync Server 2013 中修改語音路線](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="c7950-200">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="c7950-201">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c7950-201">Click **OK**.</span></span>
        
          - <span data-ttu-id="c7950-202">若要編輯已與此語音原則相關聯的 PSTN 使用記錄，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c7950-202">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="c7950-203">醒目提示您要編輯的 PSTN 使用記錄，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="c7950-203">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="c7950-204">使用下列任何一種方法來關聯及設定此 PSTN 使用記錄的路線：</span><span class="sxs-lookup"><span data-stu-id="c7950-204">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="c7950-205">若要從企業語音部署中的所有可用路由清單中選擇一或多個路由，請按一下 [**選取**]，然後醒目提示您要與此 PSTN 使用記錄建立關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c7950-205">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="c7950-206">若要從這個 PSTN 使用量記錄移除路由，請將路由反白顯示，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="c7950-206">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="c7950-207">若要定義新的路由，並將它與此 PSTN 使用量記錄建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="c7950-207">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="c7950-208">如需詳細資訊，請參閱[在 Lync Server 2013 中建立語音路由](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="c7950-208">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="c7950-209">若要編輯已與此 PSTN 使用記錄相關聯的路線，請醒目提示該路線，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="c7950-209">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="c7950-210">如需詳細資訊，請參閱[在 Lync Server 2013 中修改語音路線](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="c7950-210">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="c7950-211">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c7950-211">Click **OK**.</span></span>

10. <span data-ttu-id="c7950-212">可選輸入數位以測試語音原則，然後按一下 [ **Go**] （執行）。</span><span class="sxs-lookup"><span data-stu-id="c7950-212">(Optional) Enter a number to test the voice policy and click **Go**.</span></span> <span data-ttu-id="c7950-213">測試結果會顯示在 [已**翻譯的號碼] 下以進行測試**。</span><span class="sxs-lookup"><span data-stu-id="c7950-213">The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c7950-214">您可以儲存尚未經過測試的語音原則，稍後再重新設定。</span><span class="sxs-lookup"><span data-stu-id="c7950-214">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="c7950-215">如需詳細資訊，請參閱<A href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中測試語音路由</A>。</span><span class="sxs-lookup"><span data-stu-id="c7950-215">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

11. <span data-ttu-id="c7950-216">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c7950-216">Click **OK**.</span></span>

12. <span data-ttu-id="c7950-217">在 [**語音原則**] 頁面上，按一下 [**認可**]，然後按一下 [**全部確認**]。</span><span class="sxs-lookup"><span data-stu-id="c7950-217">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c7950-218">每當您建立或修改語音原則時，您都必須執行 [<STRONG>全部提交</STRONG>] 命令來發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="c7950-218">Whenever you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="c7950-219">如需詳細資訊，請參閱在 Operations 檔中<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">發佈 Lync Server 2013 中的語音路由設定的未決變更</A>。</span><span class="sxs-lookup"><span data-stu-id="c7950-219">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

13. <span data-ttu-id="c7950-220">可選語音信箱轉義會偵測到使用者的行動電話語音信箱立即接聽通話，然後中斷通話與行動電話語音信箱的連線。</span><span class="sxs-lookup"><span data-stu-id="c7950-220">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="c7950-221">這可讓呼叫繼續撥打使用者的其他端點，讓使用者有機會接聽通話。</span><span class="sxs-lookup"><span data-stu-id="c7950-221">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="c7950-222">如需如何設定語音信箱原則的詳細資料，請參閱[在 Lync Server 2013 中設定語音信箱轉義](lync-server-2013-configuring-voice-mail-escape.md)。</span><span class="sxs-lookup"><span data-stu-id="c7950-222">For details about how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c7950-223">請參閱</span><span class="sxs-lookup"><span data-stu-id="c7950-223">See Also</span></span>


[<span data-ttu-id="c7950-224">在 Lync Server 2013 中建立語音原則和設定 PSTN 使用記錄</span><span class="sxs-lookup"><span data-stu-id="c7950-224">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="c7950-225">在 Lync Server 2013 中查看 PSTN 使用狀況記錄</span><span class="sxs-lookup"><span data-stu-id="c7950-225">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="c7950-226">在 Lync Server 2013 中建立語音路由</span><span class="sxs-lookup"><span data-stu-id="c7950-226">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="c7950-227">在 Lync Server 2013 中修改語音路線</span><span class="sxs-lookup"><span data-stu-id="c7950-227">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="c7950-228">在 Lync Server 2013 中發佈語音路由設定的擱置變更</span><span class="sxs-lookup"><span data-stu-id="c7950-228">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="c7950-229">在 Lync Server 2013 中設定語音信箱轉義</span><span class="sxs-lookup"><span data-stu-id="c7950-229">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="c7950-230">在 Lync Server 2013 中測試語音路由</span><span class="sxs-lookup"><span data-stu-id="c7950-230">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

