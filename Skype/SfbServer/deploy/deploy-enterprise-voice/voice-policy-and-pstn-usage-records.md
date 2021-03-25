---
title: 在商務用 Skype 中建立或修改語音原則及設定 PSTN 使用方式記錄
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
description: 摘要：使用商務用 Skype Server 控制台建立或修改語音原則及設定 PSTN 使用方式記錄。
ms.openlocfilehash: ca97c4c75004849f2ea404c083878da6c726c2e6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105759"
---
# <a name="create-or-modify-a-voice-policy-and-configure-pstn-usage-records-in-skype-for-business"></a><span data-ttu-id="79ad5-103">在商務用 Skype 中建立或修改語音原則及設定 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="79ad5-103">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>

<span data-ttu-id="79ad5-104">**摘要：** 使用商務用 Skype Server 控制台建立或修改語音原則和設定 PSTN 使用方式記錄。</span><span class="sxs-lookup"><span data-stu-id="79ad5-104">**Summary:** Create or modify voice policies and configure PSTN usage records by using the Skype for Business Server Control Panel.</span></span>

> [!NOTE]
> <span data-ttu-id="79ad5-105">每個語音原則都必須至少有一個相關聯的公用交換電話網路 (PSTN) 使用方式記錄。</span><span class="sxs-lookup"><span data-stu-id="79ad5-105">Each voice policy must have at least one associated Public Switched Telephone Network (PSTN) usage record.</span></span> <span data-ttu-id="79ad5-106">若要查看您 Enterprise Voice 部署中所有可用的 PSTN 使用方式記錄清單，並查看其屬性，請參閱 [在商務用 Skype 中查看 PSTN 使用方式記錄](view-pstn-usage-records.md)。</span><span class="sxs-lookup"><span data-stu-id="79ad5-106">To see a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see [View PSTN usage records in Skype for Business](view-pstn-usage-records.md).</span></span>

### <a name="to-create-a-voice-policy"></a><span data-ttu-id="79ad5-107">若要建立語音原則</span><span class="sxs-lookup"><span data-stu-id="79ad5-107">To create a voice policy</span></span>

1. <span data-ttu-id="79ad5-108">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="79ad5-108">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="79ad5-109">在左導覽列中，依序按一下 [ **語音路由** ] 及 [ **語音原則**]。</span><span class="sxs-lookup"><span data-stu-id="79ad5-109">In the left navigation bar, click **Voice Routing** and then click **Voice Policy**.</span></span>

3. <span data-ttu-id="79ad5-110">在 [ **語音原則** ] 頁面上，按一下 [ **新增** ]，然後選取新原則的範圍：</span><span class="sxs-lookup"><span data-stu-id="79ad5-110">On the **Voice Policy** page, click **New** and then select a scope for the new policy:</span></span>

   - <span data-ttu-id="79ad5-111">**網站原則** 適用于整個網站，但任何指派給使用者原則的使用者或群組除外。</span><span class="sxs-lookup"><span data-stu-id="79ad5-111">**Site policy** applies to an entire site, except any users or groups that are assigned to a user policy.</span></span> <span data-ttu-id="79ad5-112">如果您為 [原則] 範圍選取 [網站]，請從 [ **選取網站** ] 對話方塊中選擇網站。</span><span class="sxs-lookup"><span data-stu-id="79ad5-112">If you select Site for a policy scope, choose the site from the **Select a Site** dialog box.</span></span> <span data-ttu-id="79ad5-113">如果已為網站建立語音原則，則網站不會出現在 [ **選取網站** ] 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="79ad5-113">If a voice policy has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>

   - <span data-ttu-id="79ad5-114">**使用者原則** 可以套用至指定的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="79ad5-114">**User policy** can be applied to specified users or groups.</span></span>

4. <span data-ttu-id="79ad5-115">若語音原則範圍是 [使用者]，請在 [ **名稱** ] 欄位中輸入原則的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="79ad5-115">If the voice policy scope is User, enter a descriptive name for the policy in the **Name** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="79ad5-116">若語音原則範圍是網站，**新語音原則** 中的 [**名稱**] 欄位會預先填入網站名稱，而且無法變更。</span><span class="sxs-lookup"><span data-stu-id="79ad5-116">If the voice policy scope is Site, the **Name** field in **New Voice Policy** is prepopulated with the site name and cannot be changed.</span></span>

5. <span data-ttu-id="79ad5-117"> (選用) 請輸入語音原則的其他描述性資訊。</span><span class="sxs-lookup"><span data-stu-id="79ad5-117">(Optional) Enter additional descriptive information for the voice policy.</span></span>

6. <span data-ttu-id="79ad5-118">選取或清除下列核取方塊，以啟用或停用此語音原則的每個 **通話功能** ：</span><span class="sxs-lookup"><span data-stu-id="79ad5-118">Select or clear the following check boxes to enable or disable each of the **Calling features** for this voice policy:</span></span>

   - <span data-ttu-id="79ad5-119">**語音信箱轉義** 會在設定同時震鈴時，將來電立即路由傳送至使用者的行動電話語音信箱系統，而且電話會關閉、電池計量不足或範圍外。</span><span class="sxs-lookup"><span data-stu-id="79ad5-119">**Voice mail escape** prevents calls from being immediately routed to the user's mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>

     > [!NOTE]
     > <span data-ttu-id="79ad5-120">此功能僅可透過商務用 Skype Server 管理命令介面進行設定</span><span class="sxs-lookup"><span data-stu-id="79ad5-120">This feature is only configurable through the Skype for Business Server Management Shell</span></span>

   - <span data-ttu-id="79ad5-121">**[來電轉接]** 可讓使用者將來電轉接到其他電話和用戶端裝置。</span><span class="sxs-lookup"><span data-stu-id="79ad5-121">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="79ad5-122">商務用 Skype 伺服器為來電轉接提供了相當廣泛的設定選項。</span><span class="sxs-lookup"><span data-stu-id="79ad5-122">Skype for Business Server provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="79ad5-123">例如，如果組織不想讓來電向外轉接到 PSTN，系統管理員可套用特殊語音原則以部署此限制。</span><span class="sxs-lookup"><span data-stu-id="79ad5-123">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="79ad5-124">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="79ad5-124">Enabled by default.</span></span>

   - <span data-ttu-id="79ad5-125">**[委派]** 可讓使用者指定其他使用者，來代表他們撥號和接聽電話。</span><span class="sxs-lookup"><span data-stu-id="79ad5-125">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="79ad5-126">在商務用 Skype Server 中，代理人可以設定同時震鈴，讓其主管來電撥打所有代理人同時震鈴的目標。</span><span class="sxs-lookup"><span data-stu-id="79ad5-126">In Skype for Business Server, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate's simultaneous ringing targets.</span></span> <span data-ttu-id="79ad5-127">這樣可在回應撥至主管的通話時給予代理人更大的彈性。</span><span class="sxs-lookup"><span data-stu-id="79ad5-127">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="79ad5-128">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="79ad5-128">Enabled by default.</span></span>

   - <span data-ttu-id="79ad5-129">**[通話轉接]** 可讓使用者將通話轉接給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="79ad5-129">**Call transfer** enables users to transfer calls to other users.</span></span> <span data-ttu-id="79ad5-130">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="79ad5-130">Enabled by default.</span></span>

   - <span data-ttu-id="79ad5-131">**通話駐留** 可讓使用者駐留通話，然後從不同的電話或用戶端挑選來電。</span><span class="sxs-lookup"><span data-stu-id="79ad5-131">**Call park** enables users to park calls on hold and then pick up the call from a different phone or client.</span></span> <span data-ttu-id="79ad5-132">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="79ad5-132">Disabled by default.</span></span>

   - <span data-ttu-id="79ad5-133">**[同時響鈴]** 可讓來電在更多電話 (例如，行動電話) 或其他端點裝置上發出鈴聲。</span><span class="sxs-lookup"><span data-stu-id="79ad5-133">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="79ad5-134">商務用 Skype 伺服器為同時震鈴提供大量的設定選項。</span><span class="sxs-lookup"><span data-stu-id="79ad5-134">Skype for Business Server provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="79ad5-135">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="79ad5-135">Enabled by default.</span></span>

   - <span data-ttu-id="79ad5-136">**[小組通話]** 可讓所定義小組的使用者接聽該小組其他成員的通話。</span><span class="sxs-lookup"><span data-stu-id="79ad5-136">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="79ad5-137">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="79ad5-137">Enabled by default.</span></span>

   - <span data-ttu-id="79ad5-138">**PSTN 重新路由功能** 可讓指派此原則的使用者所進行的呼叫，如果 WAN 擁塞或無法使用，則會在 PSTN 上進行重新路由傳送。</span><span class="sxs-lookup"><span data-stu-id="79ad5-138">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the PSTN if the WAN is congested or unavailable.</span></span> <span data-ttu-id="79ad5-139">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="79ad5-139">Enabled by default.</span></span>

   - <span data-ttu-id="79ad5-140">**頻寬原則覆寫** 可讓系統管理員覆寫特定使用者的通話許可控制原則決定。</span><span class="sxs-lookup"><span data-stu-id="79ad5-140">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user.</span></span> <span data-ttu-id="79ad5-141">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="79ad5-141">Disabled by default.</span></span>

     > [!NOTE]
     > <span data-ttu-id="79ad5-142">系統只會針對撥入給使用者的來電，而不會針對使用者撥出的電話覆寫此原則。</span><span class="sxs-lookup"><span data-stu-id="79ad5-142">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user.</span></span> <span data-ttu-id="79ad5-143">工作階段建立之後，便可準確地記錄頻寬使用量。</span><span class="sxs-lookup"><span data-stu-id="79ad5-143">After the session is established, the bandwidth consumption will be accurately recorded.</span></span> <span data-ttu-id="79ad5-144">此設定應該謹慎使用，且應該保留以供適當的通話許可控制決定。</span><span class="sxs-lookup"><span data-stu-id="79ad5-144">This setting should be used sparingly and should be reserved for appropriate call admission control decisions.</span></span>

   - <span data-ttu-id="79ad5-145">**惡意呼叫追蹤功能** 可讓使用者報告惡意來電 (例如威脅) 使用用戶端 UI，進而將通話詳細資料記錄中的呼叫標記 (cdr) 。</span><span class="sxs-lookup"><span data-stu-id="79ad5-145">**Malicious call tracing** enables users to report malicious calls (such as threats) by using the client UI, which in turn flags the calls in the Call Detail Records (CDRs).</span></span> <span data-ttu-id="79ad5-146">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="79ad5-146">Disabled by default.</span></span>

   - <span data-ttu-id="79ad5-147">[**忙碌] 選項** 會啟用或停用指定之語音原則的 [忙碌] 選項。</span><span class="sxs-lookup"><span data-stu-id="79ad5-147">**Busy options** enables or disables Busy Options for the specified voice policy.</span></span> <span data-ttu-id="79ad5-148">「忙碌選項」允許將來電路由傳送至語音信箱，或在通話的目標使用者在電話上時，使用占線信號來拒絕。</span><span class="sxs-lookup"><span data-stu-id="79ad5-148">Busy Options allows incoming calls to be routed to voice mail or rejected with a busy signal when the call's target user is on the phone.</span></span> <span data-ttu-id="79ad5-149">「忙碌選項」是2016年7月累積更新所引進的新語音原則。</span><span class="sxs-lookup"><span data-stu-id="79ad5-149">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update.</span></span> <span data-ttu-id="79ad5-150">檢查此參數可啟用 [忙碌選項]，並取消選中它會停用 [忙碌] 選項。</span><span class="sxs-lookup"><span data-stu-id="79ad5-150">Checking this parameter enables Busy Options, and unchecking it disables Busy Options.</span></span> <span data-ttu-id="79ad5-151">如需詳細資訊，請參閱 [Plan For 商務用 Skype server 的繁忙選項](../../plan-your-deployment/enterprise-voice-solution/busy-options.md) 及 [安裝及設定商務用 Skype Server 的繁忙選項](install-and-configure-busy-options.md)。</span><span class="sxs-lookup"><span data-stu-id="79ad5-151">For more information, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md) and [Install and configure Busy Options for Skype for Business Server](install-and-configure-busy-options.md).</span></span>

7. <span data-ttu-id="79ad5-152">若要為此語音原則來關聯及設定 PSTN 使用方式記錄，請執行下列任何一項動作：</span><span class="sxs-lookup"><span data-stu-id="79ad5-152">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="79ad5-p114">若要從您 Enterprise Voice 部署中所有可用的 PSTN 使用方式記錄清單中選擇一或多個記錄，請按一下 **[選取]**。反白顯示您想要與此語音原則關聯的記錄，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-p114">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>

   - <span data-ttu-id="79ad5-155">若要從此語音原則中移除 PSTN 使用方式記錄，請反白顯示記錄，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-155">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="79ad5-156">若要定義新的 PSTN 使用方式記錄，並將它與此語音原則關聯，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="79ad5-156">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>

     <span data-ttu-id="79ad5-157">a.</span><span class="sxs-lookup"><span data-stu-id="79ad5-157">a.</span></span> <span data-ttu-id="79ad5-158">按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="79ad5-158">Click **New**.</span></span>

     <span data-ttu-id="79ad5-159">b.</span><span class="sxs-lookup"><span data-stu-id="79ad5-159">b.</span></span> <span data-ttu-id="79ad5-160">在 **[名稱]** 欄位中，輸入記錄的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="79ad5-160">In the **Name** field, enter a unique descriptive name for the record.</span></span> <span data-ttu-id="79ad5-161">例如，您可能想要為位於 Redmond 的全職員工建立 PSTN 使用方式記錄 namedRedmond，並為臨時員工建立另一個 namedRedmondTemps。</span><span class="sxs-lookup"><span data-stu-id="79ad5-161">For example, you may want to create a PSTN usage record namedRedmond for full-time employees located in Redmond, and another namedRedmondTemps for temporary employees.</span></span>

     > [!NOTE]
     > <span data-ttu-id="79ad5-p117">PSTN 使用方式記錄名稱必須是 Enterprise Voice 部署內的唯一名稱。儲存記錄之後，就無法編輯 **[名稱]** 欄位。</span><span class="sxs-lookup"><span data-stu-id="79ad5-p117">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="79ad5-164">c.</span><span class="sxs-lookup"><span data-stu-id="79ad5-164">c.</span></span> <span data-ttu-id="79ad5-165">使用下列任一方法針對此 PSTN 使用方式記錄建立關聯及設定路由：</span><span class="sxs-lookup"><span data-stu-id="79ad5-165">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="79ad5-166">若要從 Enterprise Voice 部署中所有可用路由的清單中選擇一個或多個路由，請按一下 **[選取]**，並反白顯示想要與此 PSTN 使用方式記錄建立關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-166">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="79ad5-167">若要從 PSTN 使用方式記錄中移除路由，請反白顯示路由，然後按一下 [ **移除**]。</span><span class="sxs-lookup"><span data-stu-id="79ad5-167">To remove a route from the PSTN usage record, highlight the route, and then click **Remove**.</span></span>

   - <span data-ttu-id="79ad5-168">若要定義新的路由，並將它與此 PSTN 使用方式記錄關聯，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-168">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="79ad5-169">如需詳細資訊，請參閱 [Create or modify voice route In 商務用 Skype](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="79ad5-169">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="79ad5-170">若要編輯已與此 PSTN 使用方式記錄關聯的路由，請反白顯示路由，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-170">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="79ad5-171">d.</span><span class="sxs-lookup"><span data-stu-id="79ad5-171">d.</span></span> <span data-ttu-id="79ad5-172">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-172">Click **OK**.</span></span>

   - <span data-ttu-id="79ad5-173">若要編輯已經與此語音原則建立關聯的 PSTN 使用方式記錄，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="79ad5-173">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="79ad5-174">a.</span><span class="sxs-lookup"><span data-stu-id="79ad5-174">a.</span></span> <span data-ttu-id="79ad5-175">反白顯示您想要編輯的 PSTN 使用方式記錄，然後按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="79ad5-175">Highlight the PSTN usage record that you want to edit, and then click **Show details**.</span></span>

     <span data-ttu-id="79ad5-176">b.</span><span class="sxs-lookup"><span data-stu-id="79ad5-176">b.</span></span> <span data-ttu-id="79ad5-177">使用下列任一方法，針對此 PSTN 使用方式記錄來建立關聯及設定路由：</span><span class="sxs-lookup"><span data-stu-id="79ad5-177">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="79ad5-178">若要從 Enterprise Voice 部署中所有可用路由的清單中選擇一個或多個路由，請按一下 **[選取]**，並反白顯示想要與此 PSTN 使用方式記錄關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-178">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="79ad5-179">若要從此 PSTN 使用方式記錄中移除路由，請反白顯示路由，然後按一下 [ **移除**]。</span><span class="sxs-lookup"><span data-stu-id="79ad5-179">To remove a route from this PSTN usage record, highlight the route, and then click **Remove**.</span></span>

   - <span data-ttu-id="79ad5-180">若要定義新的路由，並將它與此 PSTN 使用方式記錄關聯，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-180">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="79ad5-181">如需詳細資訊，請參閱 [Create or modify voice route In 商務用 Skype](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="79ad5-181">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="79ad5-182">若要編輯已與此 PSTN 使用方式記錄相關聯的路由，請反白顯示路由和 lick **顯示詳細資料**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-182">To edit a route that is already associated with this PSTN usage record, highlight the route and lick **Show details**.</span></span>

     <span data-ttu-id="79ad5-183">c.</span><span class="sxs-lookup"><span data-stu-id="79ad5-183">c.</span></span> <span data-ttu-id="79ad5-184">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-184">Click **OK**.</span></span>

8. <span data-ttu-id="79ad5-185">排列 PSTN 使用方式記錄，以獲得最佳效能。</span><span class="sxs-lookup"><span data-stu-id="79ad5-185">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="79ad5-186">若要變更記錄在清單中的位置，請反白顯示記錄名稱，然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="79ad5-186">To change a record's position in the list, highlight the record name and click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="79ad5-187">PSTN 使用方式記錄列在語音原則中的順序十分重要。</span><span class="sxs-lookup"><span data-stu-id="79ad5-187">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="79ad5-188">商務用 Skype 伺服器從上而向中取得清單。</span><span class="sxs-lookup"><span data-stu-id="79ad5-188">Skype for Business Server traverses the list from the top down.</span></span> <span data-ttu-id="79ad5-189">建議您依使用頻率來組織清單，例如：RedmondLocal、RedmondLongDist、RedmondInternational 和 RedmondBackup。</span><span class="sxs-lookup"><span data-stu-id="79ad5-189">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

9. <span data-ttu-id="79ad5-190">若要針對此語音原則中的來電轉接和同時鈴響建立關聯並設定 PSTN 使用方式記錄，請執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="79ad5-190">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="79ad5-191">若要依據此語音原則針對來電轉接和同時響鈴使用相同的 PSTN 使用方式記錄，請從下拉式功能表中選取 **[使用通話 PSTN 使用方式的路由]** 選項。</span><span class="sxs-lookup"><span data-stu-id="79ad5-191">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>

   - <span data-ttu-id="79ad5-192">若要允許來電轉接和同時響鈴至內部商務用 Skype 使用者，請選取 [ **僅從下拉式功能表路由傳送至內部商務用 skype 使用者** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="79ad5-192">To allow call forwarding and simultaneous ringing to internal Skype for Business users only, select the option **Route to internal Skype for Business users only** from the drop-down menu.</span></span> <span data-ttu-id="79ad5-193">通話不會轉接至外部 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="79ad5-193">Calls will not be forwarded to external PSTN numbers.</span></span>

   - <span data-ttu-id="79ad5-194">若要為此語音原則指定不同的 PSTN 使用方式記錄來進行來電轉接和同時響鈴，請從下拉式功能表中選取 [ **使用自訂 PSTN 使用** 方式的選項路由]。</span><span class="sxs-lookup"><span data-stu-id="79ad5-194">To specify different PSTN usage records for call forwarding and simultaneous ringing than used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu.</span></span> <span data-ttu-id="79ad5-195">這個選項會顯示一個控制項，以選取現有的 PSTN 使用方式記錄，或專門針對來電轉接和同時響鈴建立新的 PSTN 使用方式記錄。</span><span class="sxs-lookup"><span data-stu-id="79ad5-195">This option displays a control to select existing PSTN usage records or create new PSTN usage records specifically for call forwarding and simultaneous ringing.</span></span>

   - <span data-ttu-id="79ad5-p129">若要針對來電轉接和同時響鈴從所有可用的 PSTN 使用方式記錄清單中選擇一筆或多筆記錄，請按一下 **[選取]**。反白顯示想要與此來電轉接和同時鈴響原則關聯的記錄，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-p129">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>

   - <span data-ttu-id="79ad5-198">若要從此來電轉接和同時鈴響原則移除 PSTN 使用方式記錄，請反白顯示記錄，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-198">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="79ad5-199">若要定義新的 PSTN 使用方式記錄，並建立其與此來電轉接和同時鈴響的關聯，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="79ad5-199">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>

     <span data-ttu-id="79ad5-200">a.</span><span class="sxs-lookup"><span data-stu-id="79ad5-200">a.</span></span> <span data-ttu-id="79ad5-201">按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="79ad5-201">Click **New**.</span></span>

     <span data-ttu-id="79ad5-202">b.</span><span class="sxs-lookup"><span data-stu-id="79ad5-202">b.</span></span> <span data-ttu-id="79ad5-203">在 **[名稱]** 欄位中，輸入記錄的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="79ad5-203">In the **Name** field, enter a unique descriptive name for the record.</span></span>

     > [!NOTE]
     > <span data-ttu-id="79ad5-p132">PSTN 使用方式記錄名稱必須是 Enterprise Voice 部署內的唯一名稱。儲存記錄之後，就無法編輯 **[名稱]** 欄位。</span><span class="sxs-lookup"><span data-stu-id="79ad5-p132">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="79ad5-206">c.</span><span class="sxs-lookup"><span data-stu-id="79ad5-206">c.</span></span> <span data-ttu-id="79ad5-207">使用下列任一方法針對此 PSTN 使用方式記錄建立關聯及設定路由：</span><span class="sxs-lookup"><span data-stu-id="79ad5-207">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="79ad5-208">若要從 Enterprise Voice 部署中所有可用路由的清單中選擇一個或多個路由，請按一下 **[選取]**，並反白顯示想要與此 PSTN 使用方式記錄建立關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-208">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="79ad5-209">若要從 PSTN 使用方式記錄中移除路由，請反白顯示路由，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-209">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="79ad5-210">若要定義新的路由，並將它與此 PSTN 使用方式記錄關聯，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-210">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="79ad5-211">如需詳細資訊，請參閱 [Create or modify voice route In 商務用 Skype](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="79ad5-211">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="79ad5-212">若要編輯已與此 PSTN 使用方式記錄關聯的路由，請反白顯示路由，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-212">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="79ad5-213">d.</span><span class="sxs-lookup"><span data-stu-id="79ad5-213">d.</span></span> <span data-ttu-id="79ad5-214">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-214">Click **OK**.</span></span>

   - <span data-ttu-id="79ad5-215">若要編輯已經與此語音原則建立關聯的 PSTN 使用方式記錄，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="79ad5-215">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="79ad5-216">a.</span><span class="sxs-lookup"><span data-stu-id="79ad5-216">a.</span></span> <span data-ttu-id="79ad5-217">反白顯示您想要編輯的 PSTN 使用方式記錄，然後按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="79ad5-217">Highlight the PSTN usage record you want to edit and click **Show details**.</span></span>

     <span data-ttu-id="79ad5-218">b.</span><span class="sxs-lookup"><span data-stu-id="79ad5-218">b.</span></span> <span data-ttu-id="79ad5-219">使用下列任一方法針對此 PSTN 使用方式記錄建立關聯及設定路由：</span><span class="sxs-lookup"><span data-stu-id="79ad5-219">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="79ad5-220">若要從您 Enterprise Voice 部署中所有可用的路由清單中選擇一或多個路由，請按一下 **[選取]**，反白顯示您想要與此 PSTN 使用方式記錄關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-220">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="79ad5-221">若要從此 PSTN 使用記錄移除路由，請反白顯示路由，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-221">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="79ad5-222">若要定義新的路由，並將它與此 PSTN 使用方式記錄關聯，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-222">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="79ad5-223">如需詳細資訊，請參閱 [Create or modify voice route In 商務用 Skype](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="79ad5-223">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="79ad5-224">若要編輯已與此 PSTN 使用方式記錄關聯的路由，請反白顯示路由，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-224">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="79ad5-225">c.</span><span class="sxs-lookup"><span data-stu-id="79ad5-225">c.</span></span> <span data-ttu-id="79ad5-226">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-226">Click **OK**.</span></span>

10. <span data-ttu-id="79ad5-227">(選用) 輸入號碼以測試語音原則，然後按一下 **[執行]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-227">(Optional) Enter a number to test the voice policy and click **Go**.</span></span> <span data-ttu-id="79ad5-228">測試結果會顯示在 **[要測試的轉譯號碼]** 下方。</span><span class="sxs-lookup"><span data-stu-id="79ad5-228">The test results are displayed under **Translated number to test**.</span></span>

11. <span data-ttu-id="79ad5-229">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-229">Click **OK**.</span></span>

12. <span data-ttu-id="79ad5-230">在 **[語音原則]** 頁面上，依序按一下 **[認可]** 和 **[全部認可]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-230">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="79ad5-231">任何時候建立或修改語音原則時，都必須執行「 **認可全部** 」命令，才能發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="79ad5-231">Any time you create or modify a voice policy, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="79ad5-232">如需詳細資訊，請參閱 Operations 檔中的在 [商務用 Skype 中發佈待定的變更至語音路由](voice-route-config-changes.md) 設定。</span><span class="sxs-lookup"><span data-stu-id="79ad5-232">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

13. <span data-ttu-id="79ad5-233"> (選用) 語音訊息轉義會偵測到使用者的行動電話語音信箱立即接聽通話，並將通話中斷與行動電話語音信箱的通話。</span><span class="sxs-lookup"><span data-stu-id="79ad5-233">(Optional) Voicemail Escape detects that a call was immediately answered by the user's mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="79ad5-234">這可讓通話繼續撥打使用者的其他端點，讓使用者接聽通話的機會。</span><span class="sxs-lookup"><span data-stu-id="79ad5-234">This allows the call to continue to ring on the user's other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="79ad5-235">如需如何設定語音信箱原則的詳細資訊，請參閱 [configure voice mail escape In 商務用 Skype](configure-voice-mail-escape.md)。</span><span class="sxs-lookup"><span data-stu-id="79ad5-235">For details on how to configure a voice mail policy, see [Configure voice mail escape in Skype for Business](configure-voice-mail-escape.md).</span></span>

### <a name="to-modify-a-voice-policy"></a><span data-ttu-id="79ad5-236">若要修改語音原則</span><span class="sxs-lookup"><span data-stu-id="79ad5-236">To modify a voice policy</span></span>

1. <span data-ttu-id="79ad5-237">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="79ad5-237">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="79ad5-238">在左導覽列中，依序按一下 **[語音路由]** 和 **[語音原則]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-238">In the left navigation bar, click **Voice Routing**, and then click **Voice Policy**.</span></span>

3. <span data-ttu-id="79ad5-239">在 **[語音原則]** 頁面上，按兩下語音原則名稱。</span><span class="sxs-lookup"><span data-stu-id="79ad5-239">On the **Voice Policy** page, double-click a voice policy name.</span></span>

    > [!NOTE]
    > <span data-ttu-id="79ad5-p143">範圍和名稱在語音原則建立時就已設定。您無法加以變更。</span><span class="sxs-lookup"><span data-stu-id="79ad5-p143">The scope and name were set when the voice policy was created. They cannot be changed.</span></span>

4. <span data-ttu-id="79ad5-242">(選用) 在 **[編輯語音原則]** 中，輸入語音原則的其他描述性資訊。</span><span class="sxs-lookup"><span data-stu-id="79ad5-242">(Optional) In **Edit Voice Policy**, enter additional descriptive information for the voice policy.</span></span>

5. <span data-ttu-id="79ad5-243">選取或清除下列核取方塊以啟用或停用每個 **[撥號功能]**：</span><span class="sxs-lookup"><span data-stu-id="79ad5-243">Select or clear the following check boxes to enable or disable each of the **Calling features**:</span></span>

   - <span data-ttu-id="79ad5-244">**語音信箱轉義** 會在設定同時震鈴時，將來電立即路由傳送至使用者的行動電話語音信箱系統，而且電話會關閉、電池計量不足或範圍外。</span><span class="sxs-lookup"><span data-stu-id="79ad5-244">**Voice mail escape** prevents calls from being immediately routed to the user's mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>

     > [!NOTE]
     > <span data-ttu-id="79ad5-245">此功能僅可透過商務用 Skype Server 管理命令介面進行設定</span><span class="sxs-lookup"><span data-stu-id="79ad5-245">This feature is only configurable through the Skype for Business Server Management Shell</span></span>

   - <span data-ttu-id="79ad5-246">**[來電轉接]** 可讓使用者將來電轉接到其他電話和用戶端裝置。</span><span class="sxs-lookup"><span data-stu-id="79ad5-246">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="79ad5-247">商務用 Skype 伺服器為來電轉接提供了相當廣泛的設定選項。</span><span class="sxs-lookup"><span data-stu-id="79ad5-247">Skype for Business Server provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="79ad5-248">例如，如果組織不想讓來電向外轉接到 PSTN，系統管理員可套用特殊語音原則以部署此限制。</span><span class="sxs-lookup"><span data-stu-id="79ad5-248">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="79ad5-249">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="79ad5-249">Enabled by default.</span></span>

   - <span data-ttu-id="79ad5-250">**[委派]** 可讓使用者指定其他使用者，來代表他們撥號和接聽電話。</span><span class="sxs-lookup"><span data-stu-id="79ad5-250">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="79ad5-251">在商務用 Skype Server 中，代理人可以設定同時震鈴，讓其主管來電撥打所有代理人同時震鈴的目標。</span><span class="sxs-lookup"><span data-stu-id="79ad5-251">In Skype for Business Server, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate's simultaneous ringing targets.</span></span> <span data-ttu-id="79ad5-252">這樣可在回應撥至主管的通話時給予代理人更大的彈性。</span><span class="sxs-lookup"><span data-stu-id="79ad5-252">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="79ad5-253">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="79ad5-253">Enabled by default.</span></span>

   - <span data-ttu-id="79ad5-p146">**[通話轉接]** 可讓使用者將通話轉接給其他使用者。預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="79ad5-p146">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>

   - <span data-ttu-id="79ad5-p147">**[通話駐留]** 可讓使用者將通話駐留成保留狀態，然後由不同電話或用戶端接聽通話。預設為停用。</span><span class="sxs-lookup"><span data-stu-id="79ad5-p147">**Call park** enables users to park calls on hold, and then pick up the call from a different phone or client. Disabled by default.</span></span>

   - <span data-ttu-id="79ad5-258">**[同時響鈴]** 可讓來電在更多電話 (例如，行動電話) 或其他端點裝置上發出鈴聲。</span><span class="sxs-lookup"><span data-stu-id="79ad5-258">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="79ad5-259">商務用 Skype 伺服器為同時震鈴提供大量的設定選項。</span><span class="sxs-lookup"><span data-stu-id="79ad5-259">Skype for Business Server provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="79ad5-260">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="79ad5-260">Enabled by default.</span></span>

   - <span data-ttu-id="79ad5-261">**[小組通話]** 可讓所定義小組的使用者接聽該小組其他成員的通話。</span><span class="sxs-lookup"><span data-stu-id="79ad5-261">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="79ad5-262">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="79ad5-262">Enabled by default.</span></span>

   - <span data-ttu-id="79ad5-263">**PSTN 重新路由功能** 可讓指派此原則的使用者所進行的呼叫，如果 WAN 擁塞或無法使用，則會在 PSTN 上進行重新路由傳送。</span><span class="sxs-lookup"><span data-stu-id="79ad5-263">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the PSTN if the WAN is congested or unavailable.</span></span> <span data-ttu-id="79ad5-264">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="79ad5-264">Enabled by default.</span></span>

   - <span data-ttu-id="79ad5-265">**頻寬原則覆寫** 可讓系統管理員覆寫特定使用者的 CAC 原則決定。</span><span class="sxs-lookup"><span data-stu-id="79ad5-265">**Bandwidth policy override** enables administrators to override CAC policy decisions for a particular user.</span></span> <span data-ttu-id="79ad5-266">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="79ad5-266">Disabled by default.</span></span>

     > [!NOTE]
     > <span data-ttu-id="79ad5-p152">系統只會針對撥入給使用者的來電，而不會針對使用者撥出的電話覆寫此原則。工作階段建立之後，便可準確地記錄頻寬使用量。請謹慎使用此設定。</span><span class="sxs-lookup"><span data-stu-id="79ad5-p152">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly.</span></span>

   - <span data-ttu-id="79ad5-270">**惡意的呼叫追蹤功能** 可讓使用者報告惡意來電 (例如威脅) 使用用戶端 UI，進而旗標 cdr 中的呼叫。</span><span class="sxs-lookup"><span data-stu-id="79ad5-270">**Malicious call tracing** enables users to report malicious calls (such as threats) using the client UI, which in turn flags the calls in the CDRs.</span></span> <span data-ttu-id="79ad5-271">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="79ad5-271">Disabled by default.</span></span>

6. <span data-ttu-id="79ad5-272">若要為此語音原則來關聯及設定 PSTN 使用方式記錄，請執行下列任何一項動作：</span><span class="sxs-lookup"><span data-stu-id="79ad5-272">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="79ad5-p154">若要從您 Enterprise Voice 部署中所有可用的 PSTN 使用方式記錄清單中選擇一或多個記錄，請按一下 **[選取]**。反白顯示您想要與此語音原則關聯的記錄，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-p154">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>

   - <span data-ttu-id="79ad5-275">若要從此語音原則中移除 PSTN 使用方式記錄，請反白顯示記錄，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-275">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="79ad5-276">若要定義新的 PSTN 使用方式記錄，並將它與此語音原則關聯，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="79ad5-276">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>

     <span data-ttu-id="79ad5-277">a.</span><span class="sxs-lookup"><span data-stu-id="79ad5-277">a.</span></span> <span data-ttu-id="79ad5-278">按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="79ad5-278">Click **New**.</span></span>

     <span data-ttu-id="79ad5-279">b.</span><span class="sxs-lookup"><span data-stu-id="79ad5-279">b.</span></span> <span data-ttu-id="79ad5-280">在 **[名稱]** 欄位中，輸入記錄的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="79ad5-280">In the **Name** field, enter a unique descriptive name for the record.</span></span> <span data-ttu-id="79ad5-281">例如，您可能想要為位於 Redmond 的全職員工建立 PSTN 使用方式記錄 namedRedmond，以及暫時員工的另一筆記錄 namedRedmondTemps。</span><span class="sxs-lookup"><span data-stu-id="79ad5-281">For example, you may want to create a PSTN usage record namedRedmond for full-time employees located in Redmond, and another record namedRedmondTemps for temporary employees.</span></span>

     > [!NOTE]
     > <span data-ttu-id="79ad5-p157">PSTN 使用方式記錄名稱必須是 Enterprise Voice 部署內的唯一名稱。儲存記錄之後，就無法編輯 **[名稱]** 欄位。</span><span class="sxs-lookup"><span data-stu-id="79ad5-p157">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="79ad5-284">c.</span><span class="sxs-lookup"><span data-stu-id="79ad5-284">c.</span></span> <span data-ttu-id="79ad5-285">使用下列任一方法針對此 PSTN 使用方式記錄建立關聯及設定路由：</span><span class="sxs-lookup"><span data-stu-id="79ad5-285">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="79ad5-286">若要從 Enterprise Voice 部署中所有可用路由的清單中選擇一個或多個路由，請按一下 **[選取]**，並反白顯示想要與此 PSTN 使用方式記錄建立關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-286">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="79ad5-287">若要從 PSTN 使用方式記錄中移除路由，請反白顯示路由，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-287">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="79ad5-288">若要定義新的路由，並將它與此 PSTN 使用方式記錄關聯，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-288">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="79ad5-289">如需詳細資訊，請參閱 [Create or modify voice route In 商務用 Skype](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="79ad5-289">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="79ad5-290">若要編輯已與此 PSTN 使用方式記錄關聯的路由，請反白顯示路由，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-290">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="79ad5-291">d.</span><span class="sxs-lookup"><span data-stu-id="79ad5-291">d.</span></span> <span data-ttu-id="79ad5-292">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-292">Click **OK**.</span></span>

   - <span data-ttu-id="79ad5-293">若要編輯已經與此語音原則建立關聯的 PSTN 使用方式記錄，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="79ad5-293">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="79ad5-294">a.</span><span class="sxs-lookup"><span data-stu-id="79ad5-294">a.</span></span> <span data-ttu-id="79ad5-295">反白顯示希望編輯的 PSTN 使用方式記錄，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-295">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>

     <span data-ttu-id="79ad5-296">b.</span><span class="sxs-lookup"><span data-stu-id="79ad5-296">b.</span></span> <span data-ttu-id="79ad5-297">使用下列任一方法針對此 PSTN 使用方式記錄建立關聯及設定路由：</span><span class="sxs-lookup"><span data-stu-id="79ad5-297">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="79ad5-298">若要從您 Enterprise Voice 部署中所有可用的路由清單中選擇一或多個路由，請按一下 **[選取]**，反白顯示您想要與此 PSTN 使用方式記錄關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-298">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="79ad5-299">若要從此 PSTN 使用記錄移除路由，請反白顯示路由，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-299">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="79ad5-300">若要定義新的路由，並將它與此 PSTN 使用方式記錄關聯，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-300">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="79ad5-301">如需詳細資訊，請參閱 [Create or modify voice route In 商務用 Skype](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="79ad5-301">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="79ad5-302">若要編輯已與此 PSTN 使用方式記錄關聯的路由，請反白顯示路由，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-302">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="79ad5-303">c.</span><span class="sxs-lookup"><span data-stu-id="79ad5-303">c.</span></span> <span data-ttu-id="79ad5-304">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-304">Click **OK**.</span></span>

7. <span data-ttu-id="79ad5-305">排列 PSTN 使用方式記錄，以獲得最佳效能。</span><span class="sxs-lookup"><span data-stu-id="79ad5-305">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="79ad5-306">若要變更記錄在清單中的位置，請反白顯示記錄名稱，然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="79ad5-306">To change a record's position in the list, highlight the record name and click the up or down arrow.</span></span>

    > [!NOTE]
    > <span data-ttu-id="79ad5-307">PSTN 使用方式記錄列在語音原則中的順序十分重要。</span><span class="sxs-lookup"><span data-stu-id="79ad5-307">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="79ad5-308">商務用 Skype 伺服器從上而向中取得清單。</span><span class="sxs-lookup"><span data-stu-id="79ad5-308">Skype for Business Server traverses the list from the top down.</span></span> <span data-ttu-id="79ad5-309">建議您依使用頻率來組織清單，例如：RedmondLocal、RedmondLongDist、RedmondInternational 和 RedmondBackup。</span><span class="sxs-lookup"><span data-stu-id="79ad5-309">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

8. <span data-ttu-id="79ad5-310">若要針對此語音原則中的來電轉接和同時鈴響建立關聯並設定 PSTN 使用方式記錄，請執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="79ad5-310">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="79ad5-311">若要依據此語音原則針對來電轉接和同時響鈴使用相同的 PSTN 使用方式記錄，請從下拉式功能表中選取 **[使用通話 PSTN 使用方式的路由]** 選項。</span><span class="sxs-lookup"><span data-stu-id="79ad5-311">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>

   - <span data-ttu-id="79ad5-312">若要允許來電轉接和同時響鈴至內部商務用 Skype 使用者，請選取 [僅從下拉式功能表 **路由傳送至內部商務用 skype 使用者** ]。</span><span class="sxs-lookup"><span data-stu-id="79ad5-312">To allow call forwarding and simultaneous ringing to internal Skype for Business users only, select **Route to internal Skype for Business users only** from the drop-down menu.</span></span> <span data-ttu-id="79ad5-313">通話不會轉接至外部 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="79ad5-313">Calls will not be forwarded to external PSTN numbers.</span></span>

   - <span data-ttu-id="79ad5-p168">若要針對用於此語音原則之外的來電轉接和同時響鈴指定其他 PSTN 使用方式記錄，請從下拉式功能表中選取 **[使用自訂 PSTN 使用方式的路由]** 選項。此選項會特別針對來電轉接和同時響鈴顯示控制項，用來選取現有 PSTN 使用方式記錄或建立新的 PSTN 使用方式記錄。</span><span class="sxs-lookup"><span data-stu-id="79ad5-p168">To specify different PSTN usage records for call forwarding and simultaneous ringing than those used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or to create new PSTN usage records, specifically for call forwarding and simultaneous ringing.</span></span>

   - <span data-ttu-id="79ad5-p169">若要針對來電轉接和同時響鈴從所有可用的 PSTN 使用方式記錄清單中選擇一筆或多筆記錄，請按一下 **[選取]**。反白顯示想要與此來電轉接和同時鈴響原則關聯的記錄，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-p169">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>

   - <span data-ttu-id="79ad5-318">若要從此來電轉接和同時鈴響原則移除 PSTN 使用方式記錄，請反白顯示記錄，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-318">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="79ad5-319">若要定義新的 PSTN 使用方式記錄，並建立其與此來電轉接和同時鈴響的關聯，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="79ad5-319">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>

     <span data-ttu-id="79ad5-320">a.</span><span class="sxs-lookup"><span data-stu-id="79ad5-320">a.</span></span> <span data-ttu-id="79ad5-321">按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="79ad5-321">Click **New**.</span></span>

     <span data-ttu-id="79ad5-322">b.</span><span class="sxs-lookup"><span data-stu-id="79ad5-322">b.</span></span> <span data-ttu-id="79ad5-323">在 **[名稱]** 欄位中，輸入記錄的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="79ad5-323">In the **Name** field, enter a unique descriptive name for the record.</span></span>

     > [!NOTE]
     > <span data-ttu-id="79ad5-p172">PSTN 使用方式記錄名稱必須是 Enterprise Voice 部署內的唯一名稱。儲存記錄之後，就無法編輯 **[名稱]** 欄位。</span><span class="sxs-lookup"><span data-stu-id="79ad5-p172">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="79ad5-326">c.</span><span class="sxs-lookup"><span data-stu-id="79ad5-326">c.</span></span> <span data-ttu-id="79ad5-327">使用下列任一方法針對此 PSTN 使用方式記錄建立關聯及設定路由：</span><span class="sxs-lookup"><span data-stu-id="79ad5-327">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="79ad5-328">若要從 Enterprise Voice 部署中所有可用路由的清單中選擇一個或多個路由，請按一下 **[選取]**，並反白顯示想要與此 PSTN 使用方式記錄建立關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-328">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="79ad5-329">若要從 PSTN 使用方式記錄中移除路由，請反白顯示路由，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-329">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="79ad5-330">若要定義新的路由，並將它與此 PSTN 使用方式記錄關聯，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-330">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="79ad5-331">如需詳細資訊，請參閱 [Create or modify voice route In 商務用 Skype](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="79ad5-331">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="79ad5-332">若要編輯已經與此 PSTN 使用方式記錄建立關聯的路由，請反白顯示路由，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-332">To edit a route that is already associated with this PSTN usage record, highlight the route, and then click **Show details**.</span></span> <span data-ttu-id="79ad5-333">如需詳細資訊，請參閱＜[Modify a Voice Route](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-voice-route)＞。</span><span class="sxs-lookup"><span data-stu-id="79ad5-333">For details, see [Modify a Voice Route](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-voice-route).</span></span>

     <span data-ttu-id="79ad5-334">d.</span><span class="sxs-lookup"><span data-stu-id="79ad5-334">d.</span></span> <span data-ttu-id="79ad5-335">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-335">Click **OK**.</span></span>

   - <span data-ttu-id="79ad5-336">若要編輯已經與此語音原則建立關聯的 PSTN 使用方式記錄，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="79ad5-336">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="79ad5-337">a.</span><span class="sxs-lookup"><span data-stu-id="79ad5-337">a.</span></span> <span data-ttu-id="79ad5-338">反白顯示希望編輯的 PSTN 使用方式記錄，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-338">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>

     <span data-ttu-id="79ad5-339">b.</span><span class="sxs-lookup"><span data-stu-id="79ad5-339">b.</span></span> <span data-ttu-id="79ad5-340">使用下列任一方法，針對此 PSTN 使用方式記錄來建立關聯及設定路由：</span><span class="sxs-lookup"><span data-stu-id="79ad5-340">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

     - <span data-ttu-id="79ad5-341">若要從 Enterprise Voice 部署中所有可用路由的清單中選擇一個或多個路由，請按一下 **[選取]**，並反白顯示想要與此 PSTN 使用方式記錄關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-341">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>

     - <span data-ttu-id="79ad5-342">若要從此 PSTN 使用方式記錄中移除路由，請反白顯示路由，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-342">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>

     - <span data-ttu-id="79ad5-343">若要定義新的路由，並將它與此 PSTN 使用方式記錄關聯，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-343">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="79ad5-344">如需詳細資訊，請參閱 [Create or modify voice route In 商務用 Skype](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="79ad5-344">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

     - <span data-ttu-id="79ad5-345">若要編輯已與此 PSTN 使用方式記錄關聯的路由，請反白顯示路由，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-345">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="79ad5-346">如需詳細資訊，請參閱＜[Modify a Voice Route](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-voice-route)＞。</span><span class="sxs-lookup"><span data-stu-id="79ad5-346">For details, see [Modify a Voice Route](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-voice-route).</span></span>

     <span data-ttu-id="79ad5-347">c.</span><span class="sxs-lookup"><span data-stu-id="79ad5-347">c.</span></span> <span data-ttu-id="79ad5-348">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-348">Click **OK**.</span></span>

9. <span data-ttu-id="79ad5-349">(選用) 輸入號碼以測試語音原則，然後按一下 **[執行]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-349">(Optional) Enter a number to test the voice policy and click **Go**.</span></span> <span data-ttu-id="79ad5-350">測試結果會顯示在 **[要測試的轉譯號碼]** 下方。</span><span class="sxs-lookup"><span data-stu-id="79ad5-350">The test results are displayed under **Translated number to test**.</span></span>

10. <span data-ttu-id="79ad5-351">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-351">Click **OK**.</span></span>

11. <span data-ttu-id="79ad5-352">在 **[語音原則]** 頁面上，依序按一下 **[認可]** 和 **[全部認可]**。</span><span class="sxs-lookup"><span data-stu-id="79ad5-352">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="79ad5-353">只要建立或修改語音原則，就必須執行 **[全部認可]** 命令來發行設定變更。</span><span class="sxs-lookup"><span data-stu-id="79ad5-353">Whenever you create or modify a voice policy, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="79ad5-354">如需詳細資訊，請參閱 Operations 檔中的在 [商務用 Skype 中發佈待定的變更至語音路由](voice-route-config-changes.md) 設定。</span><span class="sxs-lookup"><span data-stu-id="79ad5-354">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

12. <span data-ttu-id="79ad5-355"> (選用) 語音訊息轉義會偵測到使用者的行動電話語音信箱立即接聽通話，並將通話中斷與行動電話語音信箱的通話。</span><span class="sxs-lookup"><span data-stu-id="79ad5-355">(Optional) Voicemail Escape detects that a call was immediately answered by the user's mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="79ad5-356">這可讓通話繼續撥打使用者的其他端點，讓使用者接聽通話的機會。</span><span class="sxs-lookup"><span data-stu-id="79ad5-356">This allows the call to continue to ring on the user's other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="79ad5-357">如需如何設定語音信箱原則的詳細資訊，請參閱 [configure voice mail escape In 商務用 Skype](configure-voice-mail-escape.md)。</span><span class="sxs-lookup"><span data-stu-id="79ad5-357">For details about how to configure a voice mail policy, see [Configure voice mail escape in Skype for Business](configure-voice-mail-escape.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="79ad5-358">另請參閱</span><span class="sxs-lookup"><span data-stu-id="79ad5-358">See also</span></span>

[<span data-ttu-id="79ad5-359">在商務用 Skype 中查看 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="79ad5-359">View PSTN usage records in Skype for Business</span></span>](view-pstn-usage-records.md)

[<span data-ttu-id="79ad5-360">在商務用 Skype 中建立或修改語音路由</span><span class="sxs-lookup"><span data-stu-id="79ad5-360">Create or modify a voice route in Skype for Business</span></span>](create-or-modify-a-voice-route.md)

[<span data-ttu-id="79ad5-361">在商務用 Skype 中將擱置的變更發佈至語音路由設定</span><span class="sxs-lookup"><span data-stu-id="79ad5-361">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

[<span data-ttu-id="79ad5-362">在商務用 Skype 中設定語音信箱轉義</span><span class="sxs-lookup"><span data-stu-id="79ad5-362">Configure voice mail escape in Skype for Business</span></span>](configure-voice-mail-escape.md)