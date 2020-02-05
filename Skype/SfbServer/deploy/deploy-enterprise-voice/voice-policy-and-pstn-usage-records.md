---
title: 在商務用 Skype 中建立或修改語音原則及設定 PSTN 使用記錄
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 摘要：使用商務用 Skype Server 控制台建立或修改語音原則，並設定 PSTN 使用記錄。
ms.openlocfilehash: 6fe67c9c3764196559740e114419dc427cdeadf3
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766966"
---
# <a name="create-or-modify-a-voice-policy-and-configure-pstn-usage-records-in-skype-for-business"></a><span data-ttu-id="53351-103">在商務用 Skype 中建立或修改語音原則及設定 PSTN 使用記錄</span><span class="sxs-lookup"><span data-stu-id="53351-103">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>

<span data-ttu-id="53351-104">**摘要：** 使用商務用 Skype Server 的 [控制台] 建立或修改語音原則，並設定 PSTN 使用記錄。</span><span class="sxs-lookup"><span data-stu-id="53351-104">**Summary:** Create or modify voice policies and configure PSTN usage records by using the Skype for Business Server Control Panel.</span></span>

> [!NOTE]
> <span data-ttu-id="53351-105">每個語音原則都必須至少有一個相關聯的公用交換電話網絡（PSTN）使用量記錄。</span><span class="sxs-lookup"><span data-stu-id="53351-105">Each voice policy must have at least one associated Public Switched Telephone Network (PSTN) usage record.</span></span> <span data-ttu-id="53351-106">若要查看企業語音部署中所有可用的 PSTN 使用記錄清單，並查看其屬性，請參閱[在商務用 Skype 中查看 pstn 使用狀況記錄](view-pstn-usage-records.md)。</span><span class="sxs-lookup"><span data-stu-id="53351-106">To see a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see [View PSTN usage records in Skype for Business](view-pstn-usage-records.md).</span></span>

### <a name="to-create-a-voice-policy"></a><span data-ttu-id="53351-107">建立語音原則</span><span class="sxs-lookup"><span data-stu-id="53351-107">To create a voice policy</span></span>

1. <span data-ttu-id="53351-108">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="53351-108">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="53351-109">在左側導覽列中，按一下 [**語音路由**]，然後按一下 [**語音策略**]。</span><span class="sxs-lookup"><span data-stu-id="53351-109">In the left navigation bar, click **Voice Routing** and then click **Voice Policy**.</span></span>

3. <span data-ttu-id="53351-110">在 [**語音原則**] 頁面上，按一下 [**新增**]，然後選取新原則的範圍：</span><span class="sxs-lookup"><span data-stu-id="53351-110">On the **Voice Policy** page, click **New** and then select a scope for the new policy:</span></span>

   - <span data-ttu-id="53351-111">除了任何指派給使用者原則的使用者或群組之外，**網站原則**也適用于整個網站。</span><span class="sxs-lookup"><span data-stu-id="53351-111">**Site policy** applies to an entire site, except any users or groups that are assigned to a user policy.</span></span> <span data-ttu-id="53351-112">如果您為原則範圍選取 [網站]，請從 [**選取網站**] 對話方塊中選擇網站。</span><span class="sxs-lookup"><span data-stu-id="53351-112">If you select Site for a policy scope, choose the site from the **Select a Site** dialog box.</span></span> <span data-ttu-id="53351-113">如果已為網站建立語音原則，該網站不會出現在 [**選取網站**] 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="53351-113">If a voice policy has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>

   - <span data-ttu-id="53351-114">**使用者原則**可以套用至指定的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="53351-114">**User policy** can be applied to specified users or groups.</span></span>

4. <span data-ttu-id="53351-115">如果語音原則範圍是 User，請在 [Name] （**名稱**）欄位中，輸入原則的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="53351-115">If the voice policy scope is User, enter a descriptive name for the policy in the **Name** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="53351-116">如果語音原則範圍是 [網站]，**新語音原則**中的 [Name] （**名稱**）欄位會預先填入網站名稱，且無法變更。</span><span class="sxs-lookup"><span data-stu-id="53351-116">If the voice policy scope is Site, the **Name** field in **New Voice Policy** is prepopulated with the site name and cannot be changed.</span></span>

5. <span data-ttu-id="53351-117">可選輸入語音原則的其他描述性資訊。</span><span class="sxs-lookup"><span data-stu-id="53351-117">(Optional) Enter additional descriptive information for the voice policy.</span></span>

6. <span data-ttu-id="53351-118">選取或清除下列核取方塊，以啟用或停用此語音原則的每個**通話功能**：</span><span class="sxs-lookup"><span data-stu-id="53351-118">Select or clear the following check boxes to enable or disable each of the **Calling features** for this voice policy:</span></span>

   - <span data-ttu-id="53351-119">**語音信箱轉義**可防止呼叫在同時進行同時撥打，且手機已關閉、不在電池或超出範圍時，立即路由到使用者的行動電話語音信箱系統。</span><span class="sxs-lookup"><span data-stu-id="53351-119">**Voice mail escape** prevents calls from being immediately routed to the user's mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>

     > [!NOTE]
     > <span data-ttu-id="53351-120">此功能僅可透過商務用 Skype Server Management 命令介面進行設定</span><span class="sxs-lookup"><span data-stu-id="53351-120">This feature is only configurable through the Skype for Business Server Management Shell</span></span>

   - <span data-ttu-id="53351-121">[**來電轉接**] 可讓使用者將來電轉接至其他電話與用戶端裝置。</span><span class="sxs-lookup"><span data-stu-id="53351-121">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="53351-122">商務用 Skype 伺服器為來電轉接提供了相當廣泛的配置選項。</span><span class="sxs-lookup"><span data-stu-id="53351-122">Skype for Business Server provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="53351-123">例如，如果組織不想允許將來電轉寄至 PSTN，系統管理員可以套用特殊的語音原則來部署此限制。</span><span class="sxs-lookup"><span data-stu-id="53351-123">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="53351-124">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="53351-124">Enabled by default.</span></span>

   - <span data-ttu-id="53351-125">**委派**可讓使用者指定其他使用者代表自己傳送和接收來電。</span><span class="sxs-lookup"><span data-stu-id="53351-125">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="53351-126">在商務用 Skype Server 中，代理人可以設定同時撥打的電話，讓其主管的來電撥打所有代理人同時撥打的目標。</span><span class="sxs-lookup"><span data-stu-id="53351-126">In Skype for Business Server, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate's simultaneous ringing targets.</span></span> <span data-ttu-id="53351-127">這可為委派提供更大的彈性，以回應導向給 manager 的呼叫。</span><span class="sxs-lookup"><span data-stu-id="53351-127">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="53351-128">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="53351-128">Enabled by default.</span></span>

   - <span data-ttu-id="53351-129">[**來電轉接**] 可讓使用者將來電轉接給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="53351-129">**Call transfer** enables users to transfer calls to other users.</span></span> <span data-ttu-id="53351-130">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="53351-130">Enabled by default.</span></span>

   - <span data-ttu-id="53351-131">**通話寄存**可讓使用者保留通話，然後從不同的電話或用戶端挑選通話。</span><span class="sxs-lookup"><span data-stu-id="53351-131">**Call park** enables users to park calls on hold and then pick up the call from a different phone or client.</span></span> <span data-ttu-id="53351-132">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="53351-132">Disabled by default.</span></span>

   - <span data-ttu-id="53351-133">**同時撥打**可讓來電撥打其他手機（例如行動電話）或其他端點裝置。</span><span class="sxs-lookup"><span data-stu-id="53351-133">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="53351-134">商務用 Skype 伺服器提供大量的配置選項來同時撥打。</span><span class="sxs-lookup"><span data-stu-id="53351-134">Skype for Business Server provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="53351-135">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="53351-135">Enabled by default.</span></span>

   - <span data-ttu-id="53351-136">**團隊通話**可讓已定義的小組中的使用者接聽小組其他成員的來電。</span><span class="sxs-lookup"><span data-stu-id="53351-136">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="53351-137">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="53351-137">Enabled by default.</span></span>

   - <span data-ttu-id="53351-138">**PSTN 重新路由**可讓指派此原則的使用者所進行的呼叫，如果 WAN 擁塞或無法使用，則會在 PSTN 上重新路由。</span><span class="sxs-lookup"><span data-stu-id="53351-138">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the PSTN if the WAN is congested or unavailable.</span></span> <span data-ttu-id="53351-139">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="53351-139">Enabled by default.</span></span>

   - <span data-ttu-id="53351-140">[**頻寬原則覆蓋**] 可讓系統管理員覆寫特定使用者的呼叫許可控制原則決定。</span><span class="sxs-lookup"><span data-stu-id="53351-140">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user.</span></span> <span data-ttu-id="53351-141">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="53351-141">Disabled by default.</span></span>

     > [!NOTE]
     > <span data-ttu-id="53351-142">此原則只會覆寫給來電給使用者，而不會覆寫給使用者發出的撥出通話。</span><span class="sxs-lookup"><span data-stu-id="53351-142">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user.</span></span> <span data-ttu-id="53351-143">會話建立之後，就會精確地記錄頻寬使用量。</span><span class="sxs-lookup"><span data-stu-id="53351-143">After the session is established, the bandwidth consumption will be accurately recorded.</span></span> <span data-ttu-id="53351-144">此設定應該謹慎使用，且應保留適當的呼叫許可控制決定。</span><span class="sxs-lookup"><span data-stu-id="53351-144">This setting should be used sparingly and should be reserved for appropriate call admission control decisions.</span></span>

   - <span data-ttu-id="53351-145">**惡意的通話追蹤功能**可讓使用者使用用戶端 UI 來舉報惡意通話（例如威脅），進而在通話詳細資料記錄（CDRs）中標示通話。</span><span class="sxs-lookup"><span data-stu-id="53351-145">**Malicious call tracing** enables users to report malicious calls (such as threats) by using the client UI, which in turn flags the calls in the Call Detail Records (CDRs).</span></span> <span data-ttu-id="53351-146">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="53351-146">Disabled by default.</span></span>

   - <span data-ttu-id="53351-147">[**忙碌] 選項**可讓您啟用或停用指定語音原則的 Busy 選項。</span><span class="sxs-lookup"><span data-stu-id="53351-147">**Busy options** enables or disables Busy Options for the specified voice policy.</span></span> <span data-ttu-id="53351-148">[忙碌] 選項可讓來電傳送至語音信箱，或當通話的目標使用者在電話上時，使用占線信號來拒絕來電。</span><span class="sxs-lookup"><span data-stu-id="53351-148">Busy Options allows incoming calls to be routed to voice mail or rejected with a busy signal when the call's target user is on the phone.</span></span> <span data-ttu-id="53351-149">[忙碌選項] 是2016年7月累計更新引進的新語音原則。</span><span class="sxs-lookup"><span data-stu-id="53351-149">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update.</span></span> <span data-ttu-id="53351-150">核取此參數可啟用 Busy 選項，取消核取則會停用 [忙碌] 選項。</span><span class="sxs-lookup"><span data-stu-id="53351-150">Checking this parameter enables Busy Options, and unchecking it disables Busy Options.</span></span> <span data-ttu-id="53351-151">如需詳細資訊，請參閱[規劃商務用 Skype server 的繁忙選項](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)，以及[安裝及設定商務用 Skype Server 的 busy 選項](install-and-configure-busy-options.md)。</span><span class="sxs-lookup"><span data-stu-id="53351-151">For more information, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md) and [Install and configure Busy Options for Skype for Business Server](install-and-configure-busy-options.md).</span></span>

7. <span data-ttu-id="53351-152">若要關聯及設定此語音原則的 PSTN 使用記錄，請執行下列任何一項操作：</span><span class="sxs-lookup"><span data-stu-id="53351-152">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="53351-153">若要從企業語音部署中所有可用的 PSTN 使用記錄清單中選擇一或多筆記錄，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="53351-153">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="53351-154">醒目提示您想要與此語音原則相關聯的記錄，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="53351-154">Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>

   - <span data-ttu-id="53351-155">若要從此語音原則中移除 PSTN 使用記錄，請醒目提示該記錄，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="53351-155">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="53351-156">若要定義新的 PSTN 使用記錄，並將它與此語音原則關聯，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="53351-156">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>

     <span data-ttu-id="53351-157">是.</span><span class="sxs-lookup"><span data-stu-id="53351-157">a.</span></span> <span data-ttu-id="53351-158">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="53351-158">Click **New**.</span></span>

     <span data-ttu-id="53351-159">乙.</span><span class="sxs-lookup"><span data-stu-id="53351-159">b.</span></span> <span data-ttu-id="53351-160">在 [**名稱**] 欄位中，為記錄輸入唯一的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="53351-160">In the **Name** field, enter a unique descriptive name for the record.</span></span> <span data-ttu-id="53351-161">例如，您可能會想要為位於雷蒙德的全職員工建立 PSTN 使用記錄 namedRedmond，以及針對暫時員工的另一個 namedRedmondTemps。</span><span class="sxs-lookup"><span data-stu-id="53351-161">For example, you may want to create a PSTN usage record namedRedmond for full-time employees located in Redmond, and another namedRedmondTemps for temporary employees.</span></span>

     > [!NOTE]
     > <span data-ttu-id="53351-162">PSTN 使用記錄名稱在企業語音部署中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="53351-162">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="53351-163">在儲存記錄之後，[**名稱**] 欄位就無法進行編輯。</span><span class="sxs-lookup"><span data-stu-id="53351-163">After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="53351-164">c-clip.</span><span class="sxs-lookup"><span data-stu-id="53351-164">c.</span></span> <span data-ttu-id="53351-165">使用下列任何一種方法來關聯及設定此 PSTN 使用記錄的路線：</span><span class="sxs-lookup"><span data-stu-id="53351-165">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="53351-166">若要從企業語音部署中所有可用路由的清單中選擇一或多個路由，請按一下 [**選取**]，然後醒目提示您要與此 PSTN 使用記錄建立關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="53351-166">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="53351-167">若要從 PSTN 使用量記錄移除路由，請將路由反白顯示，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="53351-167">To remove a route from the PSTN usage record, highlight the route, and then click **Remove**.</span></span>

   - <span data-ttu-id="53351-168">若要定義新的路由，並將它與此 PSTN 使用量記錄建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="53351-168">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="53351-169">如需詳細資訊，請參閱[在商務用 Skype 中建立或修改語音路線](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="53351-169">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="53351-170">若要編輯已與此 PSTN 使用記錄相關聯的路線，請醒目提示該路線，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="53351-170">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="53351-171">希望.</span><span class="sxs-lookup"><span data-stu-id="53351-171">d.</span></span> <span data-ttu-id="53351-172">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="53351-172">Click **OK**.</span></span>

   - <span data-ttu-id="53351-173">若要編輯已與此語音原則相關聯的 PSTN 使用記錄，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="53351-173">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="53351-174">是.</span><span class="sxs-lookup"><span data-stu-id="53351-174">a.</span></span> <span data-ttu-id="53351-175">醒目提示您要編輯的 PSTN 使用記錄，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="53351-175">Highlight the PSTN usage record that you want to edit, and then click **Show details**.</span></span>

     <span data-ttu-id="53351-176">乙.</span><span class="sxs-lookup"><span data-stu-id="53351-176">b.</span></span> <span data-ttu-id="53351-177">使用下列任何一種方法來關聯及設定此 PSTN 使用記錄的路線：</span><span class="sxs-lookup"><span data-stu-id="53351-177">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="53351-178">若要從企業語音部署中的所有可用路由清單中選擇一或多個路由，請按一下 [**選取**]，然後醒目提示您要與此 PSTN 使用記錄建立關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="53351-178">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="53351-179">若要從這個 PSTN 使用記錄移除路由，請將路由反白顯示，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="53351-179">To remove a route from this PSTN usage record, highlight the route, and then click **Remove**.</span></span>

   - <span data-ttu-id="53351-180">若要定義新的路由，並將它與此 PSTN 使用量記錄建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="53351-180">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="53351-181">如需詳細資訊，請參閱[在商務用 Skype 中建立或修改語音路線](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="53351-181">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="53351-182">若要編輯已與此 PSTN 使用記錄相關聯的路線，請醒目提示 [路線]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="53351-182">To edit a route that is already associated with this PSTN usage record, highlight the route and lick **Show details**.</span></span>

     <span data-ttu-id="53351-183">c-clip.</span><span class="sxs-lookup"><span data-stu-id="53351-183">c.</span></span> <span data-ttu-id="53351-184">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="53351-184">Click **OK**.</span></span>

8. <span data-ttu-id="53351-185">排列 PSTN 使用狀況記錄，以獲得最佳效能。</span><span class="sxs-lookup"><span data-stu-id="53351-185">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="53351-186">若要變更記錄在清單中的位置，請醒目提示記錄名稱，然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="53351-186">To change a record's position in the list, highlight the record name and click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="53351-187">PSTN 使用記錄在語音原則中列出的順序非常重要。</span><span class="sxs-lookup"><span data-stu-id="53351-187">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="53351-188">商務用 Skype 伺服器會從上到下遍歷清單。</span><span class="sxs-lookup"><span data-stu-id="53351-188">Skype for Business Server traverses the list from the top down.</span></span> <span data-ttu-id="53351-189">我們建議您依使用頻率來組織清單，例如： RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup。</span><span class="sxs-lookup"><span data-stu-id="53351-189">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

9. <span data-ttu-id="53351-190">若要將 PSTN 使用記錄與此語音原則中的來電轉接和同時撥打進行關聯與設定，請執行下列任何一項操作：</span><span class="sxs-lookup"><span data-stu-id="53351-190">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="53351-191">若要使用與此語音原則相同的來電轉接和同時撥打的相同 PSTN 使用記錄，請從下拉式功能表中選取 [**呼叫 PSTN**使用方式] 的選項路由。</span><span class="sxs-lookup"><span data-stu-id="53351-191">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>

   - <span data-ttu-id="53351-192">若要允許來電轉接及同時撥打至內部商務用 Skype 使用者，請從下拉式功能表中選取 [**僅限內部商務用 skype 使用者**] 的選項。</span><span class="sxs-lookup"><span data-stu-id="53351-192">To allow call forwarding and simultaneous ringing to internal Skype for Business users only, select the option **Route to internal Skype for Business users only** from the drop-down menu.</span></span> <span data-ttu-id="53351-193">通話不會轉寄到外部 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="53351-193">Calls will not be forwarded to external PSTN numbers.</span></span>

   - <span data-ttu-id="53351-194">若要指定不同的來電轉接與此語音原則所用的 PSTN 使用記錄，請從下拉式功能表中選取 [**使用自訂 PSTN**的選項路由]。</span><span class="sxs-lookup"><span data-stu-id="53351-194">To specify different PSTN usage records for call forwarding and simultaneous ringing than used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu.</span></span> <span data-ttu-id="53351-195">這個選項會顯示一個控制項來選取現有的 PSTN 使用記錄，或專門針對來電轉接和同時撥打建立新的 PSTN 使用記錄。</span><span class="sxs-lookup"><span data-stu-id="53351-195">This option displays a control to select existing PSTN usage records or create new PSTN usage records specifically for call forwarding and simultaneous ringing.</span></span>

   - <span data-ttu-id="53351-196">若要從來電轉移和同時撥打的 PSTN 使用記錄清單中選擇一或多筆記錄，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="53351-196">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**.</span></span> <span data-ttu-id="53351-197">醒目提示您要與此來電轉接和同時撥打原則相關聯的記錄，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="53351-197">Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>

   - <span data-ttu-id="53351-198">若要從此來電轉接和同時撥打原則移除 PSTN 使用記錄，請醒目提示該記錄，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="53351-198">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="53351-199">若要定義新的 PSTN 使用記錄，並將它與此來電轉接和同時撥打原則關聯，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="53351-199">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>

     <span data-ttu-id="53351-200">是.</span><span class="sxs-lookup"><span data-stu-id="53351-200">a.</span></span> <span data-ttu-id="53351-201">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="53351-201">Click **New**.</span></span>

     <span data-ttu-id="53351-202">乙.</span><span class="sxs-lookup"><span data-stu-id="53351-202">b.</span></span> <span data-ttu-id="53351-203">在 [**名稱**] 欄位中，為記錄輸入唯一的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="53351-203">In the **Name** field, enter a unique descriptive name for the record.</span></span>

     > [!NOTE]
     > <span data-ttu-id="53351-204">PSTN 使用記錄名稱在企業語音部署中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="53351-204">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="53351-205">在儲存記錄之後，[**名稱**] 欄位就無法進行編輯。</span><span class="sxs-lookup"><span data-stu-id="53351-205">After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="53351-206">c-clip.</span><span class="sxs-lookup"><span data-stu-id="53351-206">c.</span></span> <span data-ttu-id="53351-207">使用下列任何一種方法來關聯及設定此 PSTN 使用記錄的路線：</span><span class="sxs-lookup"><span data-stu-id="53351-207">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="53351-208">若要從企業語音部署中所有可用路由的清單中選擇一或多個路由，請按一下 [**選取**]，然後醒目提示您要與此 PSTN 使用記錄建立關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="53351-208">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="53351-209">若要從 PSTN 使用量記錄移除路由，請將路由反白顯示，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="53351-209">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="53351-210">若要定義新的路由，並將它與此 PSTN 使用量記錄建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="53351-210">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="53351-211">如需詳細資訊，請參閱[在商務用 Skype 中建立或修改語音路線](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="53351-211">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="53351-212">若要編輯已與此 PSTN 使用記錄相關聯的路線，請醒目提示該路線，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="53351-212">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="53351-213">希望.</span><span class="sxs-lookup"><span data-stu-id="53351-213">d.</span></span> <span data-ttu-id="53351-214">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="53351-214">Click **OK**.</span></span>

   - <span data-ttu-id="53351-215">若要編輯已與此語音原則相關聯的 PSTN 使用記錄，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="53351-215">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="53351-216">是.</span><span class="sxs-lookup"><span data-stu-id="53351-216">a.</span></span> <span data-ttu-id="53351-217">醒目提示您要編輯的 PSTN 使用記錄，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="53351-217">Highlight the PSTN usage record you want to edit and click **Show details**.</span></span>

     <span data-ttu-id="53351-218">乙.</span><span class="sxs-lookup"><span data-stu-id="53351-218">b.</span></span> <span data-ttu-id="53351-219">使用下列任何一種方法來關聯及設定此 PSTN 使用記錄的路線：</span><span class="sxs-lookup"><span data-stu-id="53351-219">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="53351-220">若要從企業語音部署中所有可用路由的清單中選擇一或多個路由，請按一下 [**選取**]，然後醒目提示您要與此 PSTN 使用記錄建立關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="53351-220">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="53351-221">若要從這個 PSTN 使用量記錄移除路由，請將路由反白顯示，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="53351-221">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="53351-222">若要定義新的路由，並將它與此 PSTN 使用量記錄建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="53351-222">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="53351-223">如需詳細資訊，請參閱[在商務用 Skype 中建立或修改語音路線](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="53351-223">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="53351-224">若要編輯已與此 PSTN 使用記錄相關聯的路線，請醒目提示該路線，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="53351-224">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="53351-225">c-clip.</span><span class="sxs-lookup"><span data-stu-id="53351-225">c.</span></span> <span data-ttu-id="53351-226">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="53351-226">Click **OK**.</span></span>

10. <span data-ttu-id="53351-227">可選輸入數位以測試語音原則，然後按一下 [ **Go**] （執行）。</span><span class="sxs-lookup"><span data-stu-id="53351-227">(Optional) Enter a number to test the voice policy and click **Go**.</span></span> <span data-ttu-id="53351-228">測試結果會顯示在 [已**翻譯的號碼] 下以進行測試**。</span><span class="sxs-lookup"><span data-stu-id="53351-228">The test results are displayed under **Translated number to test**.</span></span>

11. <span data-ttu-id="53351-229">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="53351-229">Click **OK**.</span></span>

12. <span data-ttu-id="53351-230">在 [**語音原則**] 頁面上，按一下 [**認可**]，然後按一下 [**全部確認**]。</span><span class="sxs-lookup"><span data-stu-id="53351-230">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="53351-231">每當您建立或修改語音原則時，您都必須執行 [**全部提交**] 命令才能發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="53351-231">Any time you create or modify a voice policy, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="53351-232">如需詳細資訊，請參閱在作業檔中[發佈商務用 Skype 中的語音路由設定的待處理變更](voice-route-config-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="53351-232">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

13. <span data-ttu-id="53351-233">可選語音信箱轉義會偵測到使用者的行動電話語音信箱立即接聽通話，然後中斷通話與行動電話語音信箱的連線。</span><span class="sxs-lookup"><span data-stu-id="53351-233">(Optional) Voicemail Escape detects that a call was immediately answered by the user's mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="53351-234">這可讓呼叫繼續撥打使用者的其他端點，讓使用者有機會接聽通話。</span><span class="sxs-lookup"><span data-stu-id="53351-234">This allows the call to continue to ring on the user's other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="53351-235">如需如何設定語音信箱原則的詳細資料，請參閱[在商務用 Skype 中設定語音信箱轉義](configure-voice-mail-escape.md)。</span><span class="sxs-lookup"><span data-stu-id="53351-235">For details on how to configure a voice mail policy, see [Configure voice mail escape in Skype for Business](configure-voice-mail-escape.md).</span></span>

### <a name="to-modify-a-voice-policy"></a><span data-ttu-id="53351-236">修改語音原則</span><span class="sxs-lookup"><span data-stu-id="53351-236">To modify a voice policy</span></span>

1. <span data-ttu-id="53351-237">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="53351-237">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="53351-238">在左側導覽列中，按一下 [**語音路由**]，然後按一下 [**語音策略**]。</span><span class="sxs-lookup"><span data-stu-id="53351-238">In the left navigation bar, click **Voice Routing**, and then click **Voice Policy**.</span></span>

3. <span data-ttu-id="53351-239">在 [**語音原則**] 頁面上，按兩下語音原則名稱。</span><span class="sxs-lookup"><span data-stu-id="53351-239">On the **Voice Policy** page, double-click a voice policy name.</span></span>

    > [!NOTE]
    > <span data-ttu-id="53351-240">在建立語音原則時，會設定範圍和名稱。</span><span class="sxs-lookup"><span data-stu-id="53351-240">The scope and name were set when the voice policy was created.</span></span> <span data-ttu-id="53351-241">它們無法變更。</span><span class="sxs-lookup"><span data-stu-id="53351-241">They cannot be changed.</span></span>

4. <span data-ttu-id="53351-242">可選在 [**編輯語音原則**] 中，輸入語音原則的其他描述性資訊。</span><span class="sxs-lookup"><span data-stu-id="53351-242">(Optional) In **Edit Voice Policy**, enter additional descriptive information for the voice policy.</span></span>

5. <span data-ttu-id="53351-243">選取或清除下列核取方塊，以啟用或停用每個**通話功能**：</span><span class="sxs-lookup"><span data-stu-id="53351-243">Select or clear the following check boxes to enable or disable each of the **Calling features**:</span></span>

   - <span data-ttu-id="53351-244">**語音信箱轉義**可防止呼叫在同時進行同時撥打，且手機已關閉、不在電池或超出範圍時，立即路由到使用者的行動電話語音信箱系統。</span><span class="sxs-lookup"><span data-stu-id="53351-244">**Voice mail escape** prevents calls from being immediately routed to the user's mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>

     > [!NOTE]
     > <span data-ttu-id="53351-245">此功能僅可透過商務用 Skype Server Management 命令介面進行設定</span><span class="sxs-lookup"><span data-stu-id="53351-245">This feature is only configurable through the Skype for Business Server Management Shell</span></span>

   - <span data-ttu-id="53351-246">[**來電轉接**] 可讓使用者將來電轉接至其他電話與用戶端裝置。</span><span class="sxs-lookup"><span data-stu-id="53351-246">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="53351-247">商務用 Skype 伺服器為來電轉接提供了相當廣泛的配置選項。</span><span class="sxs-lookup"><span data-stu-id="53351-247">Skype for Business Server provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="53351-248">例如，如果組織不想允許將來電轉寄至 PSTN，系統管理員可以套用特殊的語音原則來部署此限制。</span><span class="sxs-lookup"><span data-stu-id="53351-248">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="53351-249">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="53351-249">Enabled by default.</span></span>

   - <span data-ttu-id="53351-250">**委派**可讓使用者指定其他使用者代表自己傳送和接收來電。</span><span class="sxs-lookup"><span data-stu-id="53351-250">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="53351-251">在商務用 Skype Server 中，代理人可以設定同時撥打的電話，讓其主管的來電撥打所有代理人同時撥打的目標。</span><span class="sxs-lookup"><span data-stu-id="53351-251">In Skype for Business Server, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate's simultaneous ringing targets.</span></span> <span data-ttu-id="53351-252">這可為委派提供更大的彈性，以回應導向給 manager 的呼叫。</span><span class="sxs-lookup"><span data-stu-id="53351-252">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="53351-253">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="53351-253">Enabled by default.</span></span>

   - <span data-ttu-id="53351-254">[**來電轉接**] 可讓使用者將來電轉接給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="53351-254">**Call transfer** enables users to transfer calls to other users.</span></span> <span data-ttu-id="53351-255">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="53351-255">Enabled by default.</span></span>

   - <span data-ttu-id="53351-256">**通話寄存**可讓使用者在保留時停止通話，然後從不同的電話或用戶端挑選通話。</span><span class="sxs-lookup"><span data-stu-id="53351-256">**Call park** enables users to park calls on hold, and then pick up the call from a different phone or client.</span></span> <span data-ttu-id="53351-257">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="53351-257">Disabled by default.</span></span>

   - <span data-ttu-id="53351-258">**同時撥打**可讓來電撥打其他手機（例如行動電話）或其他端點裝置。</span><span class="sxs-lookup"><span data-stu-id="53351-258">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="53351-259">商務用 Skype 伺服器提供大量的配置選項來同時撥打。</span><span class="sxs-lookup"><span data-stu-id="53351-259">Skype for Business Server provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="53351-260">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="53351-260">Enabled by default.</span></span>

   - <span data-ttu-id="53351-261">**團隊通話**可讓已定義的小組中的使用者接聽小組其他成員的來電。</span><span class="sxs-lookup"><span data-stu-id="53351-261">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="53351-262">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="53351-262">Enabled by default.</span></span>

   - <span data-ttu-id="53351-263">**PSTN 重新路由**可讓指派此原則的使用者所進行的呼叫，如果 WAN 擁塞或無法使用，則會在 PSTN 上重新路由。</span><span class="sxs-lookup"><span data-stu-id="53351-263">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the PSTN if the WAN is congested or unavailable.</span></span> <span data-ttu-id="53351-264">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="53351-264">Enabled by default.</span></span>

   - <span data-ttu-id="53351-265">[**頻寬原則覆蓋**] 可讓系統管理員覆寫特定使用者的 CAC 原則決策。</span><span class="sxs-lookup"><span data-stu-id="53351-265">**Bandwidth policy override** enables administrators to override CAC policy decisions for a particular user.</span></span> <span data-ttu-id="53351-266">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="53351-266">Disabled by default.</span></span>

     > [!NOTE]
     > <span data-ttu-id="53351-267">此原則只會覆寫給來電給使用者，而不會覆寫給使用者發出的撥出通話。</span><span class="sxs-lookup"><span data-stu-id="53351-267">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user.</span></span> <span data-ttu-id="53351-268">會話建立之後，就會精確地記錄頻寬使用量。</span><span class="sxs-lookup"><span data-stu-id="53351-268">After the session is established, the bandwidth consumption will be accurately recorded.</span></span> <span data-ttu-id="53351-269">此設定應該謹慎使用。</span><span class="sxs-lookup"><span data-stu-id="53351-269">This setting should be used sparingly.</span></span>

   - <span data-ttu-id="53351-270">**惡意的通話追蹤功能**可讓使用者使用用戶端 UI 報告惡意通話（例如威脅），進而在 CDRs 中標示通話。</span><span class="sxs-lookup"><span data-stu-id="53351-270">**Malicious call tracing** enables users to report malicious calls (such as threats) using the client UI, which in turn flags the calls in the CDRs.</span></span> <span data-ttu-id="53351-271">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="53351-271">Disabled by default.</span></span>

6. <span data-ttu-id="53351-272">若要關聯及設定此語音原則的 PSTN 使用記錄，請執行下列任何一項操作：</span><span class="sxs-lookup"><span data-stu-id="53351-272">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="53351-273">若要從企業語音部署中所有可用的 PSTN 使用記錄清單中選擇一或多筆記錄，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="53351-273">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="53351-274">醒目提示您想要與此語音原則相關聯的記錄，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="53351-274">Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>

   - <span data-ttu-id="53351-275">若要從此語音原則中移除 PSTN 使用記錄，請醒目提示該記錄，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="53351-275">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="53351-276">若要定義新的 PSTN 使用記錄，並將它與此語音原則關聯，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="53351-276">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>

     <span data-ttu-id="53351-277">是.</span><span class="sxs-lookup"><span data-stu-id="53351-277">a.</span></span> <span data-ttu-id="53351-278">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="53351-278">Click **New**.</span></span>

     <span data-ttu-id="53351-279">乙.</span><span class="sxs-lookup"><span data-stu-id="53351-279">b.</span></span> <span data-ttu-id="53351-280">在 [**名稱**] 欄位中，為記錄輸入唯一的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="53351-280">In the **Name** field, enter a unique descriptive name for the record.</span></span> <span data-ttu-id="53351-281">例如，您可能會想要為位於雷蒙德的全職員工建立 PSTN 使用記錄 namedRedmond，以及針對暫時員工的另一筆記錄 namedRedmondTemps。</span><span class="sxs-lookup"><span data-stu-id="53351-281">For example, you may want to create a PSTN usage record namedRedmond for full-time employees located in Redmond, and another record namedRedmondTemps for temporary employees.</span></span>

     > [!NOTE]
     > <span data-ttu-id="53351-282">PSTN 使用記錄名稱在企業語音部署中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="53351-282">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="53351-283">在儲存記錄之後，[**名稱**] 欄位就無法進行編輯。</span><span class="sxs-lookup"><span data-stu-id="53351-283">After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="53351-284">c-clip.</span><span class="sxs-lookup"><span data-stu-id="53351-284">c.</span></span> <span data-ttu-id="53351-285">使用下列任何一種方法來關聯及設定此 PSTN 使用記錄的路線：</span><span class="sxs-lookup"><span data-stu-id="53351-285">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="53351-286">若要從企業語音部署中所有可用路由的清單中選擇一或多個路由，請按一下 [**選取**]，然後醒目提示您要與此 PSTN 使用記錄建立關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="53351-286">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="53351-287">若要從 PSTN 使用量記錄移除路由，請將路由反白顯示，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="53351-287">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="53351-288">若要定義新的路由，並將它與此 PSTN 使用量記錄建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="53351-288">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="53351-289">如需詳細資訊，請參閱[在商務用 Skype 中建立或修改語音路線](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="53351-289">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="53351-290">若要編輯已與此 PSTN 使用記錄相關聯的路線，請醒目提示該路線，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="53351-290">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="53351-291">希望.</span><span class="sxs-lookup"><span data-stu-id="53351-291">d.</span></span> <span data-ttu-id="53351-292">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="53351-292">Click **OK**.</span></span>

   - <span data-ttu-id="53351-293">若要編輯已與此語音原則相關聯的 PSTN 使用記錄，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="53351-293">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="53351-294">是.</span><span class="sxs-lookup"><span data-stu-id="53351-294">a.</span></span> <span data-ttu-id="53351-295">醒目提示您要編輯的 PSTN 使用記錄，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="53351-295">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>

     <span data-ttu-id="53351-296">乙.</span><span class="sxs-lookup"><span data-stu-id="53351-296">b.</span></span> <span data-ttu-id="53351-297">使用下列任何一種方法來關聯及設定此 PSTN 使用記錄的路線：</span><span class="sxs-lookup"><span data-stu-id="53351-297">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="53351-298">若要從企業語音部署中所有可用路由的清單中選擇一或多個路由，請按一下 [**選取**]，然後醒目提示您要與此 PSTN 使用記錄建立關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="53351-298">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="53351-299">若要從這個 PSTN 使用量記錄移除路由，請將路由反白顯示，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="53351-299">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="53351-300">若要定義新的路由，並將它與此 PSTN 使用量記錄建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="53351-300">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="53351-301">如需詳細資訊，請參閱[在商務用 Skype 中建立或修改語音路線](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="53351-301">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="53351-302">若要編輯已與此 PSTN 使用記錄相關聯的路線，請醒目提示該路線，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="53351-302">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="53351-303">c-clip.</span><span class="sxs-lookup"><span data-stu-id="53351-303">c.</span></span> <span data-ttu-id="53351-304">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="53351-304">Click **OK**.</span></span>

7. <span data-ttu-id="53351-305">排列 PSTN 使用狀況記錄，以獲得最佳效能。</span><span class="sxs-lookup"><span data-stu-id="53351-305">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="53351-306">若要變更記錄在清單中的位置，請醒目提示記錄名稱，然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="53351-306">To change a record's position in the list, highlight the record name and click the up or down arrow.</span></span>

    > [!NOTE]
    > <span data-ttu-id="53351-307">PSTN 使用記錄在語音原則中列出的順序非常重要。</span><span class="sxs-lookup"><span data-stu-id="53351-307">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="53351-308">商務用 Skype 伺服器會從上到下遍歷清單。</span><span class="sxs-lookup"><span data-stu-id="53351-308">Skype for Business Server traverses the list from the top down.</span></span> <span data-ttu-id="53351-309">我們建議您依使用頻率來組織清單，例如： RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup。</span><span class="sxs-lookup"><span data-stu-id="53351-309">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

8. <span data-ttu-id="53351-310">若要將 PSTN 使用記錄與此語音原則中的來電轉接和同時撥打進行關聯與設定，請執行下列任何一項操作：</span><span class="sxs-lookup"><span data-stu-id="53351-310">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="53351-311">若要使用與此語音原則相同的來電轉接和同時撥打的相同 PSTN 使用記錄，請從下拉式功能表中選取 [**呼叫 PSTN**使用方式] 的選項路由。</span><span class="sxs-lookup"><span data-stu-id="53351-311">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>

   - <span data-ttu-id="53351-312">若要允許來電轉接及同時撥打至內部商務用 Skype 使用者，請選取 [僅從下拉式功能表**傳送給內部商務用 skype 使用者**]。</span><span class="sxs-lookup"><span data-stu-id="53351-312">To allow call forwarding and simultaneous ringing to internal Skype for Business users only, select **Route to internal Skype for Business users only** from the drop-down menu.</span></span> <span data-ttu-id="53351-313">通話不會轉寄到外部 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="53351-313">Calls will not be forwarded to external PSTN numbers.</span></span>

   - <span data-ttu-id="53351-314">若要指定不同于此語音原則來電轉接和同時撥打的 PSTN 使用記錄，請從下拉式功能表中選取 [**使用自訂 PSTN**的選項傳送]。</span><span class="sxs-lookup"><span data-stu-id="53351-314">To specify different PSTN usage records for call forwarding and simultaneous ringing than those used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu.</span></span> <span data-ttu-id="53351-315">這個選項會顯示一個控制項，可選取現有的 PSTN 使用記錄，或建立新的 PSTN 使用記錄，特別是來電轉接和同時撥打。</span><span class="sxs-lookup"><span data-stu-id="53351-315">This option displays a control to select existing PSTN usage records or to create new PSTN usage records, specifically for call forwarding and simultaneous ringing.</span></span>

   - <span data-ttu-id="53351-316">若要從來電轉移和同時撥打的 PSTN 使用記錄清單中選擇一或多筆記錄，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="53351-316">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**.</span></span> <span data-ttu-id="53351-317">醒目提示您要與此來電轉接和同時撥打原則相關聯的記錄，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="53351-317">Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>

   - <span data-ttu-id="53351-318">若要從此來電轉接和同時撥打原則移除 PSTN 使用記錄，請醒目提示該記錄，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="53351-318">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="53351-319">若要定義新的 PSTN 使用記錄，並將它與此來電轉接和同時撥打原則關聯，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="53351-319">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>

     <span data-ttu-id="53351-320">是.</span><span class="sxs-lookup"><span data-stu-id="53351-320">a.</span></span> <span data-ttu-id="53351-321">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="53351-321">Click **New**.</span></span>

     <span data-ttu-id="53351-322">乙.</span><span class="sxs-lookup"><span data-stu-id="53351-322">b.</span></span> <span data-ttu-id="53351-323">在 [**名稱**] 欄位中，為記錄輸入唯一的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="53351-323">In the **Name** field, enter a unique descriptive name for the record.</span></span>

     > [!NOTE]
     > <span data-ttu-id="53351-324">PSTN 使用記錄名稱在企業語音部署中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="53351-324">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="53351-325">在儲存記錄之後，[**名稱**] 欄位就無法進行編輯。</span><span class="sxs-lookup"><span data-stu-id="53351-325">After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="53351-326">c-clip.</span><span class="sxs-lookup"><span data-stu-id="53351-326">c.</span></span> <span data-ttu-id="53351-327">使用下列任何一種方法來關聯及設定此 PSTN 使用記錄的路線：</span><span class="sxs-lookup"><span data-stu-id="53351-327">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="53351-328">若要從企業語音部署中所有可用路由的清單中選擇一或多個路由，請按一下 [**選取**]，然後醒目提示您要與此 PSTN 使用記錄建立關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="53351-328">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="53351-329">若要從 PSTN 使用量記錄移除路由，請將路由反白顯示，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="53351-329">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="53351-330">若要定義新的路由，並將它與此 PSTN 使用量記錄建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="53351-330">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="53351-331">如需詳細資訊，請參閱[在商務用 Skype 中建立或修改語音路線](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="53351-331">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="53351-332">若要編輯已與此 PSTN 使用記錄相關聯的路線，請醒目提示該路線，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="53351-332">To edit a route that is already associated with this PSTN usage record, highlight the route, and then click **Show details**.</span></span> <span data-ttu-id="53351-333">如需詳細資訊，請參閱[修改語音路線](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="53351-333">For details, see [Modify a Voice Route](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx).</span></span>

     <span data-ttu-id="53351-334">希望.</span><span class="sxs-lookup"><span data-stu-id="53351-334">d.</span></span> <span data-ttu-id="53351-335">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="53351-335">Click **OK**.</span></span>

   - <span data-ttu-id="53351-336">若要編輯已與此語音原則相關聯的 PSTN 使用記錄，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="53351-336">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="53351-337">是.</span><span class="sxs-lookup"><span data-stu-id="53351-337">a.</span></span> <span data-ttu-id="53351-338">醒目提示您要編輯的 PSTN 使用記錄，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="53351-338">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>

     <span data-ttu-id="53351-339">乙.</span><span class="sxs-lookup"><span data-stu-id="53351-339">b.</span></span> <span data-ttu-id="53351-340">使用下列任何一種方法來關聯及設定此 PSTN 使用記錄的路線：</span><span class="sxs-lookup"><span data-stu-id="53351-340">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

     - <span data-ttu-id="53351-341">若要從企業語音部署中的所有可用路由清單中選擇一或多個路由，請按一下 [**選取**]，然後醒目提示您要與此 PSTN 使用記錄建立關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="53351-341">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>

     - <span data-ttu-id="53351-342">若要從這個 PSTN 使用量記錄移除路由，請將路由反白顯示，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="53351-342">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>

     - <span data-ttu-id="53351-343">若要定義新的路由，並將它與此 PSTN 使用量記錄建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="53351-343">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="53351-344">如需詳細資訊，請參閱[在商務用 Skype 中建立或修改語音路線](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="53351-344">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

     - <span data-ttu-id="53351-345">若要編輯已與此 PSTN 使用記錄相關聯的路線，請醒目提示該路線，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="53351-345">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="53351-346">如需詳細資訊，請參閱[修改語音路線](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="53351-346">For details, see [Modify a Voice Route](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx).</span></span>

     <span data-ttu-id="53351-347">c-clip.</span><span class="sxs-lookup"><span data-stu-id="53351-347">c.</span></span> <span data-ttu-id="53351-348">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="53351-348">Click **OK**.</span></span>

9. <span data-ttu-id="53351-349">可選輸入數位以測試語音原則，然後按一下 [ **Go**] （執行）。</span><span class="sxs-lookup"><span data-stu-id="53351-349">(Optional) Enter a number to test the voice policy and click **Go**.</span></span> <span data-ttu-id="53351-350">測試結果會顯示在 [已**翻譯的號碼] 下以進行測試**。</span><span class="sxs-lookup"><span data-stu-id="53351-350">The test results are displayed under **Translated number to test**.</span></span>

10. <span data-ttu-id="53351-351">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="53351-351">Click **OK**.</span></span>

11. <span data-ttu-id="53351-352">在 [**語音原則**] 頁面上，按一下 [**認可**]，然後按一下 [**全部確認**]。</span><span class="sxs-lookup"><span data-stu-id="53351-352">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="53351-353">每當您建立或修改語音原則時，您都必須執行 [**全部提交**] 命令來發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="53351-353">Whenever you create or modify a voice policy, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="53351-354">如需詳細資訊，請參閱在作業檔中[發佈商務用 Skype 中的語音路由設定的待處理變更](voice-route-config-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="53351-354">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

12. <span data-ttu-id="53351-355">可選語音信箱轉義會偵測到使用者的行動電話語音信箱立即接聽通話，然後中斷通話與行動電話語音信箱的連線。</span><span class="sxs-lookup"><span data-stu-id="53351-355">(Optional) Voicemail Escape detects that a call was immediately answered by the user's mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="53351-356">這可讓呼叫繼續撥打使用者的其他端點，讓使用者有機會接聽通話。</span><span class="sxs-lookup"><span data-stu-id="53351-356">This allows the call to continue to ring on the user's other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="53351-357">如需如何設定語音信箱原則的詳細資料，請參閱[在商務用 Skype 中設定語音信箱轉義](configure-voice-mail-escape.md)。</span><span class="sxs-lookup"><span data-stu-id="53351-357">For details about how to configure a voice mail policy, see [Configure voice mail escape in Skype for Business](configure-voice-mail-escape.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="53351-358">另請參閱</span><span class="sxs-lookup"><span data-stu-id="53351-358">See also</span></span>

[<span data-ttu-id="53351-359">在商務用 Skype 中查看 PSTN 使用狀況記錄</span><span class="sxs-lookup"><span data-stu-id="53351-359">View PSTN usage records in Skype for Business</span></span>](view-pstn-usage-records.md)

[<span data-ttu-id="53351-360">在商務用 Skype 中建立或修改語音路線</span><span class="sxs-lookup"><span data-stu-id="53351-360">Create or modify a voice route in Skype for Business</span></span>](create-or-modify-a-voice-route.md)

<span data-ttu-id="53351-361">[在商務用 Skype 中發佈 [語音路由設定] 的擱置變更](voice-route-config-changes.md)</span><span class="sxs-lookup"><span data-stu-id="53351-361">[Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md)</span></span>

[<span data-ttu-id="53351-362">在商務用 Skype 中設定語音信箱轉義</span><span class="sxs-lookup"><span data-stu-id="53351-362">Configure voice mail escape in Skype for Business</span></span>](configure-voice-mail-escape.md)

