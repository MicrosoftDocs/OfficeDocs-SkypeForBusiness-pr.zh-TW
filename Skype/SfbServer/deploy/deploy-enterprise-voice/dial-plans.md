---
title: 在商務用 Skype Server 中建立或修改撥號對應表
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
ms.assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
description: 摘要：瞭解如何使用商務用 Skype Server 控制台建立或修改撥號對應表。
ms.openlocfilehash: 718d0733aa5fabc072991708d09983ce8cb4267d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104899"
---
# <a name="create-or-modify-a-dial-plan-in-skype-for-business-server"></a><span data-ttu-id="d7da7-103">在商務用 Skype Server 中建立或修改撥號對應表</span><span class="sxs-lookup"><span data-stu-id="d7da7-103">Create or modify a dial plan in Skype for Business Server</span></span>

<span data-ttu-id="d7da7-104">**摘要：** 瞭解如何使用商務用 Skype Server 控制台建立或修改撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="d7da7-104">**Summary:** Learn how to create or modify a dial plan by using the Skype for Business Server Control Panel.</span></span>

### <a name="to-create-a-dial-plan"></a><span data-ttu-id="d7da7-105">建立撥號對應表</span><span class="sxs-lookup"><span data-stu-id="d7da7-105">To create a dial plan</span></span>

1. <span data-ttu-id="d7da7-106">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="d7da7-106">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="d7da7-107">在左導覽列中，依序按一下 [語音路由] 和 [撥號對應表]。</span><span class="sxs-lookup"><span data-stu-id="d7da7-107">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

3. <span data-ttu-id="d7da7-108">在 [ **撥號** 對應表] 頁面上，按一下 [ **新增** ]，然後選取撥號對應表的範圍：</span><span class="sxs-lookup"><span data-stu-id="d7da7-108">On the **Dial Plan** page, click **New** and select a scope for the dial plan:</span></span>

   - <span data-ttu-id="d7da7-109">**網站撥號** 對應表適用于整個網站，但任何指派給使用者撥號對應表的使用者或群組除外。</span><span class="sxs-lookup"><span data-stu-id="d7da7-109">**Site dial plan** applies to an entire site, except any users or groups that are assigned to a user dial plan.</span></span> <span data-ttu-id="d7da7-110">如果您針對撥號對應表的範圍選取 [ **網站** ]，必須從 [ **選取網站** ] 對話方塊中選擇網站。</span><span class="sxs-lookup"><span data-stu-id="d7da7-110">If you select **Site** for a dial plan's scope, you must choose the site from the **Select a Site** dialog box.</span></span> <span data-ttu-id="d7da7-111">如果已為網站建立撥號對應表，該網站不會出現在 [ **選取網站** ] 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="d7da7-111">If a dial plan has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>

   - <span data-ttu-id="d7da7-112">**集區撥號** 對應表可以套用到公用交換電話網路 (PSTN) 閘道或註冊機構。</span><span class="sxs-lookup"><span data-stu-id="d7da7-112">**Pool dial plan** can apply to a public switched telephone network (PSTN) gateway or a Registrar.</span></span> <span data-ttu-id="d7da7-113">如果您選取 [ **集** 區] 作為撥號對應表的範圍，請從 [ **選取服務** ] 對話方塊中選擇 PSTN 閘道或註冊機。</span><span class="sxs-lookup"><span data-stu-id="d7da7-113">If you select **Pool** for a dial plan's scope, choose the PSTN gateway or Registrar from the **Select a Service** dialog box.</span></span> <span data-ttu-id="d7da7-114">如果已為服務 (PSTN 閘道或註冊機) 建立撥號對應表，則該服務不會出現在清單中。</span><span class="sxs-lookup"><span data-stu-id="d7da7-114">If a dial plan has already been created for a service (PSTN gateway or Registrar), the service does not appear in the list.</span></span>

   - <span data-ttu-id="d7da7-115">**使用者撥號** 對應表可以套用至指定的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="d7da7-115">**User dial plan** can be applied to specified users or groups.</span></span>

     > [!NOTE]
     > <span data-ttu-id="d7da7-116">在您選取撥號對應表範圍後，就無法變更。</span><span class="sxs-lookup"><span data-stu-id="d7da7-116">After you select the dial plan scope, it cannot be changed.</span></span>

4. <span data-ttu-id="d7da7-117">如果您要建立使用者撥號對應表，請在 [**新增撥號** 對應表] 對話方塊的 [**名稱**] 欄位中輸入描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="d7da7-117">If you are creating a user dial plan, enter a descriptive name in the **Name** field on the **New Dial Plan** dialog box.</span></span> <span data-ttu-id="d7da7-118">儲存此名稱後，就無法變更。</span><span class="sxs-lookup"><span data-stu-id="d7da7-118">After this name is saved, it cannot be changed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d7da7-119">針對網站撥號對應表，[ **名稱** ] 欄位會預先填入網站名稱，而且無法變更。 > 針對集區撥號對應表，[ **名稱** ] 欄位會預先填入 PSTN 閘道或註冊機名稱，而且無法變更。</span><span class="sxs-lookup"><span data-stu-id="d7da7-119">For site dial plans, the **Name** field is prepopulated with the site name and cannot be changed.> For pool dial plans, the **Name** field is prepopulated with the PSTN gateway or Registrar name and cannot be changed.</span></span>

5. <span data-ttu-id="d7da7-120">[ **簡單名稱** ] 欄位會預先填入 [ **名稱** ] 欄位中顯示的相同名稱。</span><span class="sxs-lookup"><span data-stu-id="d7da7-120">The **Simple name** field is prepopulated with the same name that appears in the **Name** field.</span></span> <span data-ttu-id="d7da7-121">您可以選擇性地編輯此欄位，以指定更具描述性的名稱，以反映套用撥號對應表的網站、服務或使用者。</span><span class="sxs-lookup"><span data-stu-id="d7da7-121">You can optionally edit this field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="d7da7-122">在您部署中的所有撥號對應表中， **簡單名稱** 必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="d7da7-122">The **Simple name** must be unique among all dial plans in your deployment.</span></span> <span data-ttu-id="d7da7-123">它不得超過256的 Unicode 字元，每個 Unicode 字元可以是字母或數位字元、連字號 ( ) 、句點 ( ) 或底線 (_) 。 **不支援** > 字元包含如 RFC 3966 中所定義的空格和保留字元 (<http://www.ietf.org/rfc/rfc3966.txt>) 。</span><span class="sxs-lookup"><span data-stu-id="d7da7-123">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), or an underscore (_).> Characters **not supported** include spaces and Reserved characters as defined in RFC 3966 (<http://www.ietf.org/rfc/rfc3966.txt>).</span></span> <span data-ttu-id="d7da7-124">**簡單名稱** 中 **不支援** 的保留字元包含下列專案： > ";""/" "?"":" "@" "&amp;" "=" "+" "$" ","</span><span class="sxs-lookup"><span data-stu-id="d7da7-124">Reserved characters that are **not supported** in the **Simple Name** include the following:> ";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span></span>

6. <span data-ttu-id="d7da7-125"> (選用) 在 [ **描述** ] 欄位中，您可以輸入撥號對應表的其他描述性資訊。</span><span class="sxs-lookup"><span data-stu-id="d7da7-125">(Optional) In the **Description** field, you can type additional descriptive information about the dial plan.</span></span>

7. <span data-ttu-id="d7da7-126"> (選用) 若您要使用此撥號對應表作為撥入存取號碼的地區，請指定 **電話撥入式會議區域**。</span><span class="sxs-lookup"><span data-stu-id="d7da7-126">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**.</span></span> <span data-ttu-id="d7da7-127">如果您不想要將此撥號對應表用於撥入存取號碼，請將此欄位保留空白。</span><span class="sxs-lookup"><span data-stu-id="d7da7-127">If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d7da7-128">必須使用電話撥入式會議區域，才能將電話撥入式會議存取號碼與一或多個撥號對應表產生關聯。</span><span class="sxs-lookup"><span data-stu-id="d7da7-128">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

8. <span data-ttu-id="d7da7-129"> (選用) 在 [ **外部存取前置** 詞] 欄位中，只有在使用者需要撥打一或多個其他前導數位時，才指定值 (例如，9) 以取得外部行。</span><span class="sxs-lookup"><span data-stu-id="d7da7-129">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="d7da7-130">您可以輸入最多四個字元的前置詞值 ( #、\* 及 0-9) 。</span><span class="sxs-lookup"><span data-stu-id="d7da7-130">You can type in a prefix value of up to four characters (#, \*, and 0-9).</span></span>

    > [!NOTE]
    > <span data-ttu-id="d7da7-131">如果您指定了外部存取前置詞，則不需要建立新的正規化規則來容納前置詞。</span><span class="sxs-lookup"><span data-stu-id="d7da7-131">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

9. <span data-ttu-id="d7da7-132">建立和設定撥號對應表的正規化規則，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d7da7-132">Associate and configure normalization rules for the dial plan as follows:</span></span>

    - <span data-ttu-id="d7da7-133">若要從 Enterprise Voice 部署中所有可用的正規化規則清單中選擇一個或多個規則，請按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="d7da7-133">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="d7da7-134">在 [ **選取正規化規則**] 中，反白顯示您想要與撥號對應表產生關聯的規則，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d7da7-134">In **Select Normalization Rules**, highlight the rules you want to associate with the dial plan and then click **OK**.</span></span>

   - <span data-ttu-id="d7da7-135">若要定義新的正規化規則，並將它與撥號對應表產生關聯，請按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="d7da7-135">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="d7da7-136">如需定義新規則的詳細資訊，請參閱 [在商務用 Skype 中建立或修改正規化規則](normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="d7da7-136">For details about defining a new rule, see [Create or modify a normalization rule in Skype for Business](normalization-rules.md).</span></span>

   - <span data-ttu-id="d7da7-137">若要編輯已與撥號對應表相關聯的正規化規則，請反白顯示規則名稱，然後按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="d7da7-137">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span>

   - <span data-ttu-id="d7da7-138">若要複製現有的正規化規則，以做為定義新規則的起點，請反白顯示規則名稱，然後按一下 [ **複製**]，然後按一下 [ **貼** 上]。</span><span class="sxs-lookup"><span data-stu-id="d7da7-138">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span>

   - <span data-ttu-id="d7da7-139">若要從撥號對應表中移除正規化規則，請反白顯示規則名稱，然後按一下 [ **移除**]。</span><span class="sxs-lookup"><span data-stu-id="d7da7-139">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="d7da7-140">每個撥號對應表至少必須有一個相關聯的正常化規則。</span><span class="sxs-lookup"><span data-stu-id="d7da7-140">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="d7da7-141">如需如何判斷撥號對應表所需之所有正規化規則的相關資訊，請參閱規劃檔中的在 [商務用 Skype Server 中規劃輸出語音路由](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) 。</span><span class="sxs-lookup"><span data-stu-id="d7da7-141">For information about how to determine all of the normalization rules a dial plan requires, see [Plan for outbound voice routing in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) in the Planning documentation.</span></span>

10. <span data-ttu-id="d7da7-142">確認撥號對應表的正規化規則依正確的順序排列。</span><span class="sxs-lookup"><span data-stu-id="d7da7-142">Verify that the dial plan's normalization rules are arranged in the correct order.</span></span> <span data-ttu-id="d7da7-143">若要變更規則在清單中的位置，請反白顯示規則名稱，然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="d7da7-143">To change a rule's position in the list, highlight the rule name and then click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d7da7-144">商務用 Skype 伺服器從左上部取得正規化規則清單，並使用符合撥號號碼的第一個規則。</span><span class="sxs-lookup"><span data-stu-id="d7da7-144">Skype for Business Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="d7da7-145">如果您設定撥號對應表，讓已撥號的號碼可以比對多個正規化規則，請確定限制性以上的規則排序的限制性較低。</span><span class="sxs-lookup"><span data-stu-id="d7da7-145">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span> <span data-ttu-id="d7da7-146">> 預設值 **保持所有** 正規化規則 ^ ( \d {11}) $ 符合任何11位數的數位。</span><span class="sxs-lookup"><span data-stu-id="d7da7-146">> The default **Keep All** normalization rule^(\d{11})$ matches any 11-digit number.</span></span> <span data-ttu-id="d7da7-147">例如，如果您新增的正規化規則符合11位數的開始1425的數位，請確定 [ **全部保留** ] 的排序低於較嚴格的 ^ (1425 {7}) $ rule。</span><span class="sxs-lookup"><span data-stu-id="d7da7-147">For example, if you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that **Keep All** is sorted below the more restrictive^(1425\d{7})$ rule.</span></span>

11. <span data-ttu-id="d7da7-148"> (選用) 請輸入號碼以測試撥號對應表，然後按一下 [ **移至**]。</span><span class="sxs-lookup"><span data-stu-id="d7da7-148">(Optional) Enter a number to test the dial plan and then click **Go**.</span></span> <span data-ttu-id="d7da7-149">測試結果會顯示在 [ **輸入要測試的號碼**] 底下。</span><span class="sxs-lookup"><span data-stu-id="d7da7-149">The test results are displayed under **Enter a number to test**.</span></span>

12. <span data-ttu-id="d7da7-150">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d7da7-150">Click **OK**.</span></span>

13. <span data-ttu-id="d7da7-151">在 [ **撥號** 對應表] 頁面上，按一下 [ **認可**]，然後按一下 [ **全部認可**]。</span><span class="sxs-lookup"><span data-stu-id="d7da7-151">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d7da7-152">每當您建立撥號對應表時，都必須執行「 **認可全部** 」命令來發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="d7da7-152">Any time you create a dial plan, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="d7da7-153">如需詳細資訊，請參閱 Operations 檔中的在 [商務用 Skype 中發佈待定的變更至語音路由](voice-route-config-changes.md) 設定。</span><span class="sxs-lookup"><span data-stu-id="d7da7-153">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-modify-a-dial-plan"></a><span data-ttu-id="d7da7-154">修改撥號對應表</span><span class="sxs-lookup"><span data-stu-id="d7da7-154">To modify a dial plan</span></span>

1. <span data-ttu-id="d7da7-155">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="d7da7-155">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="d7da7-156">如需詳細資訊，請參閱＜**Delegate Setup Permissions**＞。</span><span class="sxs-lookup"><span data-stu-id="d7da7-156">For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="d7da7-157">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="d7da7-157">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="d7da7-158">在左導覽列中，依序按一下 [語音路由] 和 [撥號對應表]。</span><span class="sxs-lookup"><span data-stu-id="d7da7-158">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4. <span data-ttu-id="d7da7-159">在 [撥號對應表] 頁面上，按兩下撥號對應表名稱。</span><span class="sxs-lookup"><span data-stu-id="d7da7-159">On the **Dial Plan** page, double-click a dial plan name.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d7da7-160">建立撥號對應表時設定撥號對應表的範圍和名稱。</span><span class="sxs-lookup"><span data-stu-id="d7da7-160">The dial plan scope and name were set when the dial plan was created.</span></span> <span data-ttu-id="d7da7-161">您無法加以變更。</span><span class="sxs-lookup"><span data-stu-id="d7da7-161">They cannot be changed.</span></span>

5. <span data-ttu-id="d7da7-162"> (選用) 在 [ **編輯撥號** 對應表] 中，編輯 [ **簡易名稱** ] 欄位（預先填入 **名稱** ] 欄位中顯示的相同名稱），以指定反映撥號對應表所套用之網站、服務或使用者的更具描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="d7da7-162">(Optional) In **Edit Dial Plan**, edit the **Simple name** field, which is prepopulated with the same name that appears in the **Name** field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d7da7-163">在 Lync Server 2013 部署內的所有撥號對應表中， **簡單名稱** 必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="d7da7-163">The **Simple name** must be unique among all dial plans within the Lync Server 2013 deployment.</span></span> <span data-ttu-id="d7da7-164">它不得超過256的 Unicode 字元，每個字元可以是字母或數位字元、連字號 ( ) 、句點 ( ) 、正負號 (+) 或底線 (_) 。 [ **簡單名稱** ] 欄位中不允許 > 空格。</span><span class="sxs-lookup"><span data-stu-id="d7da7-164">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), a plus sign (+), or an underscore (_).> Spaces are not allowed in the **Simple name** field.</span></span>

6. <span data-ttu-id="d7da7-165"> (選用) 在 [ **描述** ] 欄位中，輸入撥號對應表的描述資訊。</span><span class="sxs-lookup"><span data-stu-id="d7da7-165">(Optional) In the **Description** field, type descriptive information about the dial plan.</span></span>

7. <span data-ttu-id="d7da7-166"> (選用) 若您要使用此撥號對應表作為撥入存取號碼的地區，請指定 **電話撥入式會議區域**。</span><span class="sxs-lookup"><span data-stu-id="d7da7-166">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**.</span></span> <span data-ttu-id="d7da7-167">如果您不想要將此撥號對應表用於撥入存取號碼，請將此欄位保留空白。</span><span class="sxs-lookup"><span data-stu-id="d7da7-167">If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d7da7-168">必須使用電話撥入式會議區域，才能將電話撥入式會議存取號碼與一或多個撥號對應表產生關聯。</span><span class="sxs-lookup"><span data-stu-id="d7da7-168">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

8. <span data-ttu-id="d7da7-169"> (選用) 在 [ **外部存取前置** 詞] 欄位中，只有在使用者需要撥打一或多個其他前導數位以取得外部行時，才指定值 (例如，9) 。</span><span class="sxs-lookup"><span data-stu-id="d7da7-169">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits to get an external line (for example, 9).</span></span> <span data-ttu-id="d7da7-170">您可以輸入最多四個字元的前置詞值 (，也就是 #、\* 及 0-9) 。</span><span class="sxs-lookup"><span data-stu-id="d7da7-170">You can type in a prefix value of up to four characters (that is, #, \*, and 0-9).</span></span>

    > [!NOTE]
    > <span data-ttu-id="d7da7-171">如果您指定了外部存取前置詞，則不需要建立新的正規化規則來容納前置詞。</span><span class="sxs-lookup"><span data-stu-id="d7da7-171">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

9. <span data-ttu-id="d7da7-172">關聯及設定撥號對應表的正規化規則：</span><span class="sxs-lookup"><span data-stu-id="d7da7-172">Associate and configure normalization rules for the dial plan:</span></span>

   - <span data-ttu-id="d7da7-173">若要從 Enterprise Voice 部署中所有可用的正規化規則清單中選擇一個或多個規則，請按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="d7da7-173">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="d7da7-174">在 [ **選取正規化規則** ] 對話方塊中，反白顯示您想要與撥號對應表產生關聯的規則，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d7da7-174">In the **Select Normalization Rules** dialog box, highlight the rules that you want to associate with the dial plan and then click **OK**.</span></span>

   - <span data-ttu-id="d7da7-175">若要定義新的正規化規則，並將它與撥號對應表產生關聯，請按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="d7da7-175">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="d7da7-176">如需定義新規則的詳細資訊，請參閱 [在商務用 Skype 中建立或修改正規化規則](normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="d7da7-176">For details about defining a new rule, see [Create or modify a normalization rule in Skype for Business](normalization-rules.md).</span></span>

   - <span data-ttu-id="d7da7-177">若要編輯已與撥號對應表相關聯的正規化規則，請反白顯示規則名稱，然後按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="d7da7-177">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span>

   - <span data-ttu-id="d7da7-178">若要複製現有的正規化規則，以做為定義新規則的起點，請反白顯示規則名稱，然後按一下 [ **複製**]，然後按一下 [ **貼** 上]。</span><span class="sxs-lookup"><span data-stu-id="d7da7-178">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span>

   - <span data-ttu-id="d7da7-179">若要從撥號對應表中移除正規化規則，請反白顯示規則名稱，然後按一下 [ **移除**]。</span><span class="sxs-lookup"><span data-stu-id="d7da7-179">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="d7da7-180">每個撥號對應表至少必須有一個相關聯的正常化規則。</span><span class="sxs-lookup"><span data-stu-id="d7da7-180">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="d7da7-181">如需如何判斷撥號對應表所需之所有正規化規則的詳細資訊，請參閱規劃檔中的 [在商務用 Skype Server 中規劃輸出語音路由](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) 。</span><span class="sxs-lookup"><span data-stu-id="d7da7-181">For details about how to determine all of the normalization rules a dial plan requires, see [Plan for outbound voice routing in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) in the Planning documentation.</span></span>

10. <span data-ttu-id="d7da7-182">確認撥號對應表的正規化規則依正確的順序排列。</span><span class="sxs-lookup"><span data-stu-id="d7da7-182">Verify that the dial plan's normalization rules are arranged in the correct order.</span></span> <span data-ttu-id="d7da7-183">若要變更規則在清單中的位置，請反白顯示規則名稱，然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="d7da7-183">To change a rule's position in the list, highlight the rule name and then click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d7da7-184">商務用 Skype 伺服器從左上部取得正規化規則清單，並使用符合撥號號碼的第一個規則。</span><span class="sxs-lookup"><span data-stu-id="d7da7-184">Skype for Business Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="d7da7-185">如果您設定撥號對應表，讓已撥號的號碼可以比對多個正規化規則，請確定限制性以上的規則排序的限制性較低。</span><span class="sxs-lookup"><span data-stu-id="d7da7-185">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span> <span data-ttu-id="d7da7-186">> 預設值 **保持所有** 正規化規則 ^ ( \d {11}) $ 符合任何11位數的數位。</span><span class="sxs-lookup"><span data-stu-id="d7da7-186">> The default **Keep All** normalization rule^(\d{11})$ matches any 11-digit number.</span></span> <span data-ttu-id="d7da7-187">例如，如果您新增的正規化規則符合11位數的開始1425的數位，請確定 [ **全部保留** ] 的專案排序低於較嚴格的 ^ (1425 {7}) $ rule。</span><span class="sxs-lookup"><span data-stu-id="d7da7-187">If, for example, you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that **Keep All** is sorted below the more restrictive^(1425\d{7})$ rule.</span></span>

11. <span data-ttu-id="d7da7-188"> (選用) 請輸入號碼以測試撥號對應表，然後按一下 [ **移至**]。</span><span class="sxs-lookup"><span data-stu-id="d7da7-188">(Optional) Enter a number to test the dial plan and then click **Go**.</span></span> <span data-ttu-id="d7da7-189">測試結果會顯示在 [ **輸入要測試的號碼**] 底下。</span><span class="sxs-lookup"><span data-stu-id="d7da7-189">The test results are displayed under **Enter a number to test**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d7da7-190">您可以儲存尚未通過測試的撥號對應表，然後再加以重新設定。</span><span class="sxs-lookup"><span data-stu-id="d7da7-190">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="d7da7-191">如需詳細資訊，請參閱 [測試語音路由](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing)。</span><span class="sxs-lookup"><span data-stu-id="d7da7-191">For details, see [Testing Voice Routing](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing).</span></span>

12. <span data-ttu-id="d7da7-192">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d7da7-192">Click **OK**.</span></span>

13. <span data-ttu-id="d7da7-193">在 [ **撥號** 對應表] 頁面上，按一下 [ **認可**]，然後按一下 [ **全部認可**]。</span><span class="sxs-lookup"><span data-stu-id="d7da7-193">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d7da7-194">每當您建立或修改撥號對應表時，都必須執行「 **認可全部** 」命令來發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="d7da7-194">Any time you create or modify a dial plan, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="d7da7-195">如需詳細資訊，請參閱 Operations 檔中的在 [商務用 Skype 中發佈待定的變更至語音路由](voice-route-config-changes.md) 設定。</span><span class="sxs-lookup"><span data-stu-id="d7da7-195">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7da7-196">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d7da7-196">See also</span></span>

[<span data-ttu-id="d7da7-197">在商務用 Skype 中將擱置的變更發佈至語音路由設定</span><span class="sxs-lookup"><span data-stu-id="d7da7-197">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)