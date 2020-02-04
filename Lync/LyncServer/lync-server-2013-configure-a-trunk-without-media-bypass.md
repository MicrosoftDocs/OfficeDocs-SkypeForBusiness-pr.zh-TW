---
title: Lync Server 2013：不使用媒體旁路來設定幹線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk without media bypass
ms:assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425831(v=OCS.15)
ms:contentKeyID: 48183825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09fe6841fa8aab5a68017f92313395dc4d8ab55c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-without-media-bypass-in-lync-server-2013"></a><span data-ttu-id="27c29-102">在 Lync Server 2013 中設定沒有媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="27c29-102">Configure a trunk without media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27c29-103">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="27c29-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="27c29-104">如果您想要在停用媒體旁路的情況下設定幹線，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="27c29-104">If you want to configure a trunk with media bypass disabled, follow these steps.</span></span> <span data-ttu-id="27c29-105">如果您想要設定啟用媒體旁路的幹線，請參閱[使用 Lync Server 2013 中的媒體旁路來設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="27c29-105">If you want to configure a trunk with media bypass enabled, see [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

<span data-ttu-id="27c29-106">主幹設定（如下所述）將套用至 trunks 的一組參數群組指派給此幹線設定。</span><span class="sxs-lookup"><span data-stu-id="27c29-106">A trunk configuration, as described below, groups a set of parameters that are applied to trunks assigned this trunk configuration.</span></span> <span data-ttu-id="27c29-107">您可以將特定的主幹設定設為全域（所有 trunks，而不會有更具體的網站或池配置），或是到網站或池中。</span><span class="sxs-lookup"><span data-stu-id="27c29-107">A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool.</span></span> <span data-ttu-id="27c29-108">[池層級中繼] 設定是用來將特定主幹設定的範圍限定在單一干線中。</span><span class="sxs-lookup"><span data-stu-id="27c29-108">The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkGenericSteps"></span>

<div>

## <a name="to-configure-a-trunk-without-media-bypass"></a><span data-ttu-id="27c29-109">在沒有媒體旁路的情況下設定幹線</span><span class="sxs-lookup"><span data-stu-id="27c29-109">To configure a trunk without media bypass</span></span>

1.  <span data-ttu-id="27c29-110">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="27c29-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="27c29-111">如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="27c29-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="27c29-112">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="27c29-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="27c29-113">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="27c29-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="27c29-114">在左側導覽列中，按一下 [**語音路由**]，然後按一下 [**幹線**設定]。</span><span class="sxs-lookup"><span data-stu-id="27c29-114">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="27c29-115">在 [**幹線**設定] 頁面上，使用下列其中一種方法來設定幹線：</span><span class="sxs-lookup"><span data-stu-id="27c29-115">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="27c29-116">按兩下現有的幹線（例如，**全域**幹線），以顯示 [**編輯主幹**設定] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="27c29-116">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="27c29-117">按一下 [**新增**]，然後選取新主幹設定的範圍：</span><span class="sxs-lookup"><span data-stu-id="27c29-117">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="27c29-118">**網站主幹：** 在 [**選取網站**] 中選擇此主幹設定的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="27c29-118">**Site trunk:** Choose the site for this trunk configuration in **Select a Site** , and then click **OK**.</span></span> <span data-ttu-id="27c29-119">請注意，如果已為網站建立中繼設定，網站就不會出現在 [**選取網站**] 中。</span><span class="sxs-lookup"><span data-stu-id="27c29-119">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="27c29-120">此主幹設定將會套用至網站中的所有 trunks。</span><span class="sxs-lookup"><span data-stu-id="27c29-120">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="27c29-121">**池主幹：** 在 [**選取服務**] 中，選擇此幹線設定適用的主幹名稱，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="27c29-121">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to in **Select a Service** and click **OK**.</span></span> <span data-ttu-id="27c29-122">這個幹線可以是根主幹，或拓撲建立器中定義的任何其他 trunks。</span><span class="sxs-lookup"><span data-stu-id="27c29-122">This trunk can be the root trunk, or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="27c29-123">請注意，如果已為特定主幹建立幹線設定，主幹不會出現在 [**選取服務**] 中。</span><span class="sxs-lookup"><span data-stu-id="27c29-123">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="27c29-124">在您選取主幹設定的範圍之後，就無法變更它。</span><span class="sxs-lookup"><span data-stu-id="27c29-124">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="27c29-125">[ <STRONG>Name</STRONG> ] （名稱）欄位會填入與中繼設定的關聯網站或服務名稱，且無法變更。</span><span class="sxs-lookup"><span data-stu-id="27c29-125">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="27c29-126">選取下列其中一個**加密支援等級**選項：</span><span class="sxs-lookup"><span data-stu-id="27c29-126">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="27c29-127">**必要：** 安全即時傳輸通訊協定（SRTP）加密必須用來協助保護中繼伺服器與閘道或私人分支 exchange （PBX）之間的流量。</span><span class="sxs-lookup"><span data-stu-id="27c29-127">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="27c29-128">**選用：** 如果服務提供者或設備製造商支援，則會使用 SRTP 加密。</span><span class="sxs-lookup"><span data-stu-id="27c29-128">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="27c29-129">**不支援：** 服務提供者或設備製造商不支援 SRTP 加密，因此將無法使用。</span><span class="sxs-lookup"><span data-stu-id="27c29-129">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

6.  <span data-ttu-id="27c29-130">請確定已清除 [**啟用媒體旁路**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="27c29-130">Be sure that the **Enable media bypass** check box is cleared.</span></span>

7.  <span data-ttu-id="27c29-131">如果有已知的媒體端接點，請選取 [**集中式媒體處理**] 核取方塊（例如，在媒體端接的公用交換電話網絡（PSTN）閘道與 [信號終止] 相同）。</span><span class="sxs-lookup"><span data-stu-id="27c29-131">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a public switched telephone network (PSTN) gateway where the media termination has the same IP as the signaling termination).</span></span> <span data-ttu-id="27c29-132">如果主幹沒有已知的媒體端接點，請清除此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="27c29-132">Clear this check box if the trunk does not have a well-known media termination point.</span></span>

8.  <span data-ttu-id="27c29-133">如果乾線對等支援接收來自中繼伺服器的 SIP，請選取 [**啟用傳送參照至閘道**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="27c29-133">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>

9.  <span data-ttu-id="27c29-134">可選若要啟用站間路由，請將 PSTN 使用記錄關聯並設定為此主幹設定。</span><span class="sxs-lookup"><span data-stu-id="27c29-134">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration.</span></span> <span data-ttu-id="27c29-135">與此幹線設定相關聯的 PSTN 用法，將會針對並非來自 Lync 端點之幹線的所有撥入電話套用。</span><span class="sxs-lookup"><span data-stu-id="27c29-135">The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint.</span></span> <span data-ttu-id="27c29-136">若要管理與幹線設定相關聯的 PSTN 使用記錄，請使用下列其中一種方法：</span><span class="sxs-lookup"><span data-stu-id="27c29-136">To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="27c29-137">若要從企業語音部署中所有可用的 PSTN 使用記錄清單中選取一或多筆記錄，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="27c29-137">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="27c29-138">醒目提示您要與此主幹設定關聯的記錄，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="27c29-138">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="27c29-139">若要從此幹線設定中移除 PSTN 使用記錄，請選取該記錄，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="27c29-139">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="27c29-140">若要定義新的 PSTN 使用記錄，並將它與此幹線設定關聯，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="27c29-140">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="27c29-141">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="27c29-141">Click **New**.</span></span>
        
        2.  <span data-ttu-id="27c29-142">在 [**名稱**] 欄位中，為記錄指定唯一的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="27c29-142">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="27c29-143">PSTN 使用記錄名稱在企業語音部署中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="27c29-143">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="27c29-144">在儲存記錄之後，[<STRONG>名稱</STRONG>] 欄位就無法進行編輯。</span><span class="sxs-lookup"><span data-stu-id="27c29-144">After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="27c29-145">使用下列其中一種方法來關聯及設定此 PSTN 使用記錄的路線：</span><span class="sxs-lookup"><span data-stu-id="27c29-145">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="27c29-146">若要從企業語音部署中所有可用路由的清單中選取一或多個路由，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="27c29-146">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="27c29-147">醒目提示您想要與此 PSTN 使用記錄產生關聯的路線，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="27c29-147">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="27c29-148">若要從 PSTN 使用量記錄移除路由，請選取路由，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="27c29-148">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="27c29-149">若要定義新的路由，並將它與此 PSTN 使用記錄建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="27c29-149">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="27c29-150">如需詳細資訊，請參閱[在 Lync Server 2013 中建立語音路由](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="27c29-150">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="27c29-151">若要編輯與此 PSTN 使用記錄相關聯的路線，請選取該路線，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="27c29-151">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="27c29-152">如需詳細資訊，請參閱[在 Lync Server 2013 中修改語音路線](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="27c29-152">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="27c29-153">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="27c29-153">Click **OK**.</span></span>
    
      - <span data-ttu-id="27c29-154">若要編輯已與此幹線設定關聯的 PSTN 使用記錄，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="27c29-154">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="27c29-155">選取您要編輯的 PSTN 使用量記錄，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="27c29-155">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="27c29-156">使用下列其中一種方法來關聯及設定此 PSTN 使用記錄的路線：</span><span class="sxs-lookup"><span data-stu-id="27c29-156">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="27c29-157">若要從企業語音部署中所有可用路由的清單中選取一或多個路由，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="27c29-157">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="27c29-158">醒目提示您想要與此 PSTN 使用記錄產生關聯的路線，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="27c29-158">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="27c29-159">若要從 PSTN 使用量記錄移除路由，請選取路由，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="27c29-159">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="27c29-160">若要定義新的路由，並將它與此 PSTN 使用記錄建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="27c29-160">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="27c29-161">如需詳細資訊，請參閱[在 Lync Server 2013 中建立語音路由](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="27c29-161">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="27c29-162">若要編輯與此 PSTN 使用記錄相關聯的路線，請選取該路線，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="27c29-162">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="27c29-163">如需詳細資訊，請參閱[在 Lync Server 2013 中修改語音路線](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="27c29-163">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="27c29-164">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="27c29-164">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="27c29-165">將 PSTN 使用記錄與正在設定主幹的中繼伺服器對等相關聯是很重要的。</span><span class="sxs-lookup"><span data-stu-id="27c29-165">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="27c29-166">如果中繼伺服器對等是 PSTN 閘道或會話邊界控制器（SBC），強烈建議您不要將幹線設定與路由至 PSTN 目的地的 PSTN 使用記錄或任何其他透過 Lync 連接的任何其他下游系統關聯伺服器.</span><span class="sxs-lookup"><span data-stu-id="27c29-166">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

10. <span data-ttu-id="27c29-167">排列 PSTN 使用狀況記錄，以獲得最佳效能。</span><span class="sxs-lookup"><span data-stu-id="27c29-167">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="27c29-168">若要變更記錄在清單中的位置，請選取 PSTN 使用記錄，然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="27c29-168">To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="27c29-169">PSTN 使用記錄在幹線設定中的顯示順序非常重要。</span><span class="sxs-lookup"><span data-stu-id="27c29-169">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="27c29-170">Lync Server 會從上到下遍歷清單。</span><span class="sxs-lookup"><span data-stu-id="27c29-170">Lync Server traverses the list from top to down.</span></span>

    
    </div>

11. <span data-ttu-id="27c29-171">應選取 [**啟用 RTP 閉鎖**]，以便為 NAT 或防火牆後的用戶端使用旁路媒體，以及支援閉鎖的 SBC。</span><span class="sxs-lookup"><span data-stu-id="27c29-171">**Enable RTP Latching** should be selected to enable bypass media for clients behind a NAT or firewall and an SBC that supports latching.</span></span>

12. <span data-ttu-id="27c29-172">應選取 [**啟用轉寄通話記錄**]，以允許將通話記錄資訊傳送到中繼伺服器的閘道對等。</span><span class="sxs-lookup"><span data-stu-id="27c29-172">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

13. <span data-ttu-id="27c29-173">[**啟用前 P-已斷言身分識別的資料**] 必須選取，才能讓 PAI 通話發信方資訊在中繼伺服器端和閘道端之間（反之亦然），在目前狀態中轉寄。</span><span class="sxs-lookup"><span data-stu-id="27c29-173">**Enable forward P-Asserted-Identity data** should be selected to enable PAI call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

14. <span data-ttu-id="27c29-174">若要啟用快速容錯移轉，請選取 [**啟用輸出路由容錯移轉計時器**]。</span><span class="sxs-lookup"><span data-stu-id="27c29-174">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="27c29-175">與此幹線關聯的閘道可以在處理撥出通話的10秒內發出通知。</span><span class="sxs-lookup"><span data-stu-id="27c29-175">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="27c29-176">如果中繼伺服器未收到此通知，就會將重新路由至另一個主幹。</span><span class="sxs-lookup"><span data-stu-id="27c29-176">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="27c29-177">在延遲可能會延遲回應時間的網路上，或閘道需要10秒以上的時間才能回應，就應該停用 [快速容錯移轉]。</span><span class="sxs-lookup"><span data-stu-id="27c29-177">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

15. <span data-ttu-id="27c29-178">可選關聯並設定主幹的**通話數轉譯規則**。</span><span class="sxs-lookup"><span data-stu-id="27c29-178">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="27c29-179">這些翻譯規則會套用至撥出通話的電話號碼</span><span class="sxs-lookup"><span data-stu-id="27c29-179">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="27c29-180">若要從企業語音部署中提供的所有翻譯規則清單中選擇一或多個規則，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="27c29-180">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="27c29-181">在 [**選取翻譯規則**] 中，按一下您要與主幹建立關聯的規則，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="27c29-181">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="27c29-182">若要定義新的翻譯規則，並將其與骨幹建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="27c29-182">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="27c29-183">如需有關定義新規則的詳細資料，請參閱在部署檔中的[Lync Server 2013 中定義翻譯規則](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="27c29-183">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="27c29-184">若要編輯已經與主幹建立關聯的翻譯規則，請按一下規則名稱，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="27c29-184">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="27c29-185">如需詳細資訊，請參閱在部署檔中的[Lync Server 2013 定義翻譯規則](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="27c29-185">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="27c29-186">若要複製現有的翻譯規則，以做為定義新規則的起點，請按一下規則名稱，然後按一下 [**複製**]，然後按一下 [**貼**上]。</span><span class="sxs-lookup"><span data-stu-id="27c29-186">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="27c29-187">如需詳細資訊，請參閱[在 Lync Server 2013 中定義翻譯規則](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="27c29-187">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="27c29-188">若要從主幹中移除翻譯規則，請將規則名稱醒目提示，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="27c29-188">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="安全性" alt="security" /><span data-ttu-id="27c29-190">安全性注意事項：</span><span class="sxs-lookup"><span data-stu-id="27c29-190">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="27c29-191">如果您已在關聯的中繼對等上設定翻譯規則，請不要將翻譯規則與幹線建立關聯，因為這兩個規則可能會衝突。</span><span class="sxs-lookup"><span data-stu-id="27c29-191">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

16. <span data-ttu-id="27c29-192">可選關聯並設定主幹的已**呼叫數位轉譯規則**。</span><span class="sxs-lookup"><span data-stu-id="27c29-192">(Optional) Associate and configure **called number translation rules** for the trunk.</span></span> <span data-ttu-id="27c29-193">翻譯規則會套用至撥出通話中呼叫的號碼。</span><span class="sxs-lookup"><span data-stu-id="27c29-193">The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="27c29-194">若要從企業語音部署中提供的所有翻譯規則清單中選擇一或多個規則，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="27c29-194">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="27c29-195">在 [**選取翻譯規則**] 中，按一下您要與主幹建立關聯的規則，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="27c29-195">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="27c29-196">若要定義新的翻譯規則，並將其與骨幹建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="27c29-196">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="27c29-197">如需有關定義新規則的詳細資料，請參閱在部署檔中的[Lync Server 2013 中定義翻譯規則](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="27c29-197">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="27c29-198">若要編輯已經與主幹建立關聯的翻譯規則，請按一下規則名稱，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="27c29-198">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="27c29-199">如需詳細資訊，請參閱在部署檔中的[Lync Server 2013 定義翻譯規則](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="27c29-199">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="27c29-200">若要複製現有的翻譯規則，以做為定義新規則的起點，請按一下規則名稱，然後按一下 [**複製**]，然後按一下 [**貼**上]。</span><span class="sxs-lookup"><span data-stu-id="27c29-200">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="27c29-201">如需詳細資訊，請參閱[在 Lync Server 2013 中定義翻譯規則](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="27c29-201">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="27c29-202">若要從主幹中移除翻譯規則，請將規則名稱醒目提示，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="27c29-202">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="27c29-203">如果您已在關聯的中繼對等上設定翻譯規則，請不要將翻譯規則與幹線建立關聯，因為這兩個規則可能會衝突。</span><span class="sxs-lookup"><span data-stu-id="27c29-203">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="27c29-204">確定主幹的轉譯規則依正確順序排列。</span><span class="sxs-lookup"><span data-stu-id="27c29-204">Make sure that the trunk’s translation rules are arranged in the correct order.</span></span> <span data-ttu-id="27c29-205">若要變更規則在清單中的位置，請醒目提示 [規則名稱]，然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="27c29-205">To change a rule’s position in the list, highlight the rule name, and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="27c29-206">Lync Server 會從上到下遍歷翻譯規則清單，並使用與撥號號碼相符的第一個規則。</span><span class="sxs-lookup"><span data-stu-id="27c29-206">Lync Server traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="27c29-207">如果您設定幹線，讓撥入的號碼可以符合多個翻譯規則，請確定更嚴格的規則，在限制性較低的規則之上排序。</span><span class="sxs-lookup"><span data-stu-id="27c29-207">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="27c29-208">例如，如果您已包含符合任何11位數的翻譯規則，以及只符合以 + 1425 開頭的11位數的翻譯規則，請確定符合任何11位數的規則，以更嚴格的<EM>規則排序。</EM></span><span class="sxs-lookup"><span data-stu-id="27c29-208">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

18. <span data-ttu-id="27c29-209">當您完成設定主幹時，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="27c29-209">When you are finished configuring the trunk, click **OK**.</span></span>

19. <span data-ttu-id="27c29-210">在 [**幹線**設定] 頁面上，按一下 [**認可**]，然後按一下 [**全部確認**]。</span><span class="sxs-lookup"><span data-stu-id="27c29-210">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="27c29-211">每當您建立或修改幹線設定時，您都必須執行 [<STRONG>全部提交</STRONG>] 命令才能發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="27c29-211">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="27c29-212">如需詳細資訊，請參閱在 Operations 檔中<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">發佈 Lync Server 2013 中的語音路由設定的未決變更</A>。</span><span class="sxs-lookup"><span data-stu-id="27c29-212">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="27c29-213">請參閱</span><span class="sxs-lookup"><span data-stu-id="27c29-213">See Also</span></span>


<span data-ttu-id="27c29-214">[在 Lync Server 2013 中使用 [旁路媒體] 設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="27c29-214">[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)</span></span>  


[<span data-ttu-id="27c29-215">在 Lync Server 2013 中定義轉譯規則</span><span class="sxs-lookup"><span data-stu-id="27c29-215">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

