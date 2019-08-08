---
title: 在商務用 Skype Server 中建立或修改撥號方案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
description: '摘要: 瞭解如何使用商務用 Skype Server [控制台] 建立或修改撥號方案。'
ms.openlocfilehash: 456bd4c46b371da260340fab4e2b7152d14f7924
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240727"
---
# <a name="create-or-modify-a-dial-plan-in-skype-for-business-server"></a><span data-ttu-id="196b8-103">在商務用 Skype Server 中建立或修改撥號方案</span><span class="sxs-lookup"><span data-stu-id="196b8-103">Create or modify a dial plan in Skype for Business Server</span></span>

<span data-ttu-id="196b8-104">**摘要:** 瞭解如何使用商務用 Skype Server [控制台] 建立或修改撥號方案。</span><span class="sxs-lookup"><span data-stu-id="196b8-104">**Summary:** Learn how to create or modify a dial plan by using the Skype for Business Server Control Panel.</span></span>

### <a name="to-create-a-dial-plan"></a><span data-ttu-id="196b8-105">建立撥號方案</span><span class="sxs-lookup"><span data-stu-id="196b8-105">To create a dial plan</span></span>

1. <span data-ttu-id="196b8-106">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="196b8-106">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="196b8-107">在左側導覽列中, 按一下 [**語音路由**], 然後按一下 [**撥號計畫**]。</span><span class="sxs-lookup"><span data-stu-id="196b8-107">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

3. <span data-ttu-id="196b8-108">在 [**撥號方案**] 頁面上, 按一下 [**新增**], 然後選取撥號方案的範圍:</span><span class="sxs-lookup"><span data-stu-id="196b8-108">On the **Dial Plan** page, click **New** and select a scope for the dial plan:</span></span>

   - <span data-ttu-id="196b8-109">除了任何指派給使用者撥號方案的使用者或群組之外,**網站撥號計畫**也適用于整個網站。</span><span class="sxs-lookup"><span data-stu-id="196b8-109">**Site dial plan** applies to an entire site, except any users or groups that are assigned to a user dial plan.</span></span> <span data-ttu-id="196b8-110">如果您選取 [**網站**] 作為撥號方案的範圍, 則必須從 [**選取網站**] 對話方塊中選擇網站。</span><span class="sxs-lookup"><span data-stu-id="196b8-110">If you select **Site** for a dial plan's scope, you must choose the site from the **Select a Site** dialog box.</span></span> <span data-ttu-id="196b8-111">如果已為網站建立撥號方案, 該網站不會出現在 [**選取網站**] 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="196b8-111">If a dial plan has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>

   - <span data-ttu-id="196b8-112">您可以將**池撥號方案**套用至公用的交換式電話網絡 (PSTN) 閘道或註冊機構。</span><span class="sxs-lookup"><span data-stu-id="196b8-112">**Pool dial plan** can apply to a public switched telephone network (PSTN) gateway or a Registrar.</span></span> <span data-ttu-id="196b8-113">如果您為撥號方案的範圍選取 [**泳池**], 請從 [**選取服務**] 對話方塊中選擇 PSTN 閘道或註冊機構。</span><span class="sxs-lookup"><span data-stu-id="196b8-113">If you select **Pool** for a dial plan's scope, choose the PSTN gateway or Registrar from the **Select a Service** dialog box.</span></span> <span data-ttu-id="196b8-114">如果已為服務 (PSTN 閘道或註冊機構) 建立撥號方案, 該服務不會出現在清單中。</span><span class="sxs-lookup"><span data-stu-id="196b8-114">If a dial plan has already been created for a service (PSTN gateway or Registrar), the service does not appear in the list.</span></span>

   - <span data-ttu-id="196b8-115">您可以將**使用者撥號方案**套用至指定的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="196b8-115">**User dial plan** can be applied to specified users or groups.</span></span>

     > [!NOTE]
     > <span data-ttu-id="196b8-116">在您選取撥號方案範圍之後, 就無法變更它。</span><span class="sxs-lookup"><span data-stu-id="196b8-116">After you select the dial plan scope, it cannot be changed.</span></span>

4. <span data-ttu-id="196b8-117">如果您要建立使用者撥號方案, 請在 [**新增撥號方案**] 對話方塊上的 [**名稱**] 欄位中, 輸入描述性的名稱。</span><span class="sxs-lookup"><span data-stu-id="196b8-117">If you are creating a user dial plan, enter a descriptive name in the **Name** field on the **New Dial Plan** dialog box.</span></span> <span data-ttu-id="196b8-118">儲存此名稱之後, 就無法變更。</span><span class="sxs-lookup"><span data-stu-id="196b8-118">After this name is saved, it cannot be changed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="196b8-119">針對網站撥號方案, [**名稱**] 欄位是使用網站名稱預先填入, 且無法變更。針對池撥號方案 >, [name] (**名稱**) 欄位會預先填入 PSTN 閘道或註冊機構名稱, 且無法變更。</span><span class="sxs-lookup"><span data-stu-id="196b8-119">For site dial plans, the **Name** field is prepopulated with the site name and cannot be changed.> For pool dial plans, the **Name** field is prepopulated with the PSTN gateway or Registrar name and cannot be changed.</span></span>

5. <span data-ttu-id="196b8-120">[ \*\*\*\* 簡稱] 欄位會預先填入與 [**名稱**] 欄位中相同的名稱。</span><span class="sxs-lookup"><span data-stu-id="196b8-120">The **Simple name** field is prepopulated with the same name that appears in the **Name** field.</span></span> <span data-ttu-id="196b8-121">您可以選擇性地編輯此欄位, 以指定更具描述性的名稱, 以反映要套用撥號方案的網站、服務或使用者。</span><span class="sxs-lookup"><span data-stu-id="196b8-121">You can optionally edit this field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="196b8-122">**簡單名稱**在您部署中的所有撥號方案中都必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="196b8-122">The **Simple name** must be unique among all dial plans in your deployment.</span></span> <span data-ttu-id="196b8-123">它不能超過 256 Unicode 字元, 每個字元都可以是字母或數位字元、連字號 (-)、句號 (.) 或底線 (_)。**不支援**> 字元包括 RFC 3966 (<http://www.ietf.org/rfc/rfc3966.txt>) 中定義的空格和保留字元。</span><span class="sxs-lookup"><span data-stu-id="196b8-123">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), or an underscore (_).> Characters **not supported** include spaces and Reserved characters as defined in RFC 3966 (<http://www.ietf.org/rfc/rfc3966.txt>).</span></span> <span data-ttu-id="196b8-124">**簡單名稱**中**不支援**的保留字元包括下列各項: > ";""/" "?"":" "@" "&amp;" "=" "+" "$" ","</span><span class="sxs-lookup"><span data-stu-id="196b8-124">Reserved characters that are **not supported** in the **Simple Name** include the following:> ";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span></span>

6. <span data-ttu-id="196b8-125">可選在 [**描述**] 欄位中, 您可以輸入撥號方案的其他描述性資訊。</span><span class="sxs-lookup"><span data-stu-id="196b8-125">(Optional) In the **Description** field, you can type additional descriptive information about the dial plan.</span></span>

7. <span data-ttu-id="196b8-126">可選如果您想要使用此撥號方案作為撥入號碼的地區, 請指定**電話撥入式會議區域**。</span><span class="sxs-lookup"><span data-stu-id="196b8-126">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**.</span></span> <span data-ttu-id="196b8-127">如果您不想將這個撥號方案用於撥入存取電話號碼, 請將此欄位留白。</span><span class="sxs-lookup"><span data-stu-id="196b8-127">If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>

    > [!NOTE]
    > <span data-ttu-id="196b8-128">電話撥入式會議區域需要將電話撥入式會議存取號碼與一或多個撥號方案建立關聯。</span><span class="sxs-lookup"><span data-stu-id="196b8-128">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

8. <span data-ttu-id="196b8-129">可選在 [**外部存取前置**詞] 欄位中, 只有在使用者需要撥一或多個額外的前導數位 (例如 9) 來取得外部線路時, 才指定值。</span><span class="sxs-lookup"><span data-stu-id="196b8-129">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="196b8-130">您可以輸入最多四個字元 (#、\* 及 0-9) 的前置詞值。</span><span class="sxs-lookup"><span data-stu-id="196b8-130">You can type in a prefix value of up to four characters (#, \*, and 0-9).</span></span>

    > [!NOTE]
    > <span data-ttu-id="196b8-131">如果您指定外部存取前置詞, 就不需要建立新的正常化規則來容納該前置詞。</span><span class="sxs-lookup"><span data-stu-id="196b8-131">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

9. <span data-ttu-id="196b8-132">針對撥號方案建立並設定正常化規則, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="196b8-132">Associate and configure normalization rules for the dial plan as follows:</span></span>

    - <span data-ttu-id="196b8-133">若要從企業語音部署中所有可用的正常化規則清單中選擇一或多個規則, 請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="196b8-133">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="196b8-134">在 [**選取正常化規則**] 中, 醒目提示您要與撥號計畫建立關聯的規則, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="196b8-134">In **Select Normalization Rules**, highlight the rules you want to associate with the dial plan and then click **OK**.</span></span>

   - <span data-ttu-id="196b8-135">若要定義新的正常化規則, 並將它與撥號方案建立關聯, 請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="196b8-135">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="196b8-136">如需有關定義新規則的詳細資料, 請參閱[在商務用 Skype 中建立或修改正常化規則](normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="196b8-136">For details about defining a new rule, see [Create or modify a normalization rule in Skype for Business](normalization-rules.md).</span></span>

   - <span data-ttu-id="196b8-137">若要編輯已經與撥號方案相關聯的正常化規則, 請醒目提示 [規則名稱], 然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="196b8-137">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span>

   - <span data-ttu-id="196b8-138">若要複製現有的正常化規則, 以做為定義新規則的起點, 請醒目提示規則名稱, 然後按一下 [**複製**], 然後按一下 [**貼**上]。</span><span class="sxs-lookup"><span data-stu-id="196b8-138">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span>

   - <span data-ttu-id="196b8-139">若要從撥號方案中移除正常化規則, 請醒目提示規則名稱, 然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="196b8-139">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="196b8-140">每個撥號方案都必須至少有一個相關聯的正常化規則。</span><span class="sxs-lookup"><span data-stu-id="196b8-140">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="196b8-141">如需如何判斷撥號方案所需的所有正常化規則的相關資訊, 請參閱規劃檔中的[商務用 Skype 伺服器中的出站語音路由規劃](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="196b8-141">For information about how to determine all of the normalization rules a dial plan requires, see [Plan for outbound voice routing in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) in the Planning documentation.</span></span>

10. <span data-ttu-id="196b8-142">確認撥號方案的正常化規則依正確順序排列。</span><span class="sxs-lookup"><span data-stu-id="196b8-142">Verify that the dial plan's normalization rules are arranged in the correct order.</span></span> <span data-ttu-id="196b8-143">若要變更規則在清單中的位置, 請醒目提示 [規則名稱], 然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="196b8-143">To change a rule's position in the list, highlight the rule name and then click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="196b8-144">商務用 Skype 伺服器會從上而下遍歷正常化規則清單, 並使用與撥號號碼相符的第一個規則。</span><span class="sxs-lookup"><span data-stu-id="196b8-144">Skype for Business Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="196b8-145">如果您設定撥號方案, 讓撥入的號碼可以符合多個正常化規則, 請確定更嚴格的規則排序在限制性較低的規則上方。</span><span class="sxs-lookup"><span data-stu-id="196b8-145">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span> <span data-ttu-id="196b8-146">> [**保留所有**正常化規則 ^ (\d{11}) $] 的預設值是符合任何11位數的數位。</span><span class="sxs-lookup"><span data-stu-id="196b8-146">> The default **Keep All** normalization rule^(\d{11})$ matches any 11-digit number.</span></span> <span data-ttu-id="196b8-147">例如, 如果您要新增的正常化規則與從1425開始的11位數數位相符, 請確定 [**全部保留**] 的排序次序低於較強的 ^ (1425 \{7}d) $ 規則。</span><span class="sxs-lookup"><span data-stu-id="196b8-147">For example, if you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that **Keep All** is sorted below the more restrictive^(1425\d{7})$ rule.</span></span>

11. <span data-ttu-id="196b8-148">可選輸入數位以測試撥號計畫, 然後按一下 [執行\*\*\*\*]。</span><span class="sxs-lookup"><span data-stu-id="196b8-148">(Optional) Enter a number to test the dial plan and then click **Go**.</span></span> <span data-ttu-id="196b8-149">測試結果會顯示在 [**輸入要測試的號碼**] 下。</span><span class="sxs-lookup"><span data-stu-id="196b8-149">The test results are displayed under **Enter a number to test**.</span></span>

12. <span data-ttu-id="196b8-150">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="196b8-150">Click **OK**.</span></span>

13. <span data-ttu-id="196b8-151">在 [**撥號方案**] 頁面上, 按一下 [**認可**], 然後按一下 [**全部提交**]。</span><span class="sxs-lookup"><span data-stu-id="196b8-151">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="196b8-152">每當您建立撥號方案時, 您都必須執行 [**全部提交**] 命令來發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="196b8-152">Any time you create a dial plan, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="196b8-153">如需詳細資訊, 請參閱在作業檔中[發佈商務用 Skype 中的語音路由設定的待處理變更](voice-route-config-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="196b8-153">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-modify-a-dial-plan"></a><span data-ttu-id="196b8-154">修改撥號方案</span><span class="sxs-lookup"><span data-stu-id="196b8-154">To modify a dial plan</span></span>

1. <span data-ttu-id="196b8-155">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="196b8-155">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="196b8-156">如需詳細資訊, 請參閱**委派設定許可權**。</span><span class="sxs-lookup"><span data-stu-id="196b8-156">For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="196b8-157">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="196b8-157">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="196b8-158">在左側導覽列中, 按一下 [**語音路由**], 然後按一下 [**撥號計畫**]。</span><span class="sxs-lookup"><span data-stu-id="196b8-158">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4. <span data-ttu-id="196b8-159">在 [**撥號方案**] 頁面上, 按兩下撥號方案名稱。</span><span class="sxs-lookup"><span data-stu-id="196b8-159">On the **Dial Plan** page, double-click a dial plan name.</span></span>

    > [!NOTE]
    > <span data-ttu-id="196b8-160">在建立撥號對應表時設定撥號計畫範圍和名稱。</span><span class="sxs-lookup"><span data-stu-id="196b8-160">The dial plan scope and name were set when the dial plan was created.</span></span> <span data-ttu-id="196b8-161">它們無法變更。</span><span class="sxs-lookup"><span data-stu-id="196b8-161">They cannot be changed.</span></span>

5. <span data-ttu-id="196b8-162">可選在 [**編輯撥號**對應表] 中, 編輯 [簡稱] 欄位中預先填入相同名稱的 [ **Simple name** ] (名稱) 欄位, 以指定更具描述性的名稱, 以反映要套用撥號方案的網站、服務或使用者。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="196b8-162">(Optional) In **Edit Dial Plan**, edit the **Simple name** field, which is prepopulated with the same name that appears in the **Name** field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="196b8-163">**簡單名稱**在 Lync Server 2013 部署中的所有撥號方案中都必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="196b8-163">The **Simple name** must be unique among all dial plans within the Lync Server 2013 deployment.</span></span> <span data-ttu-id="196b8-164">它不能超過 256 Unicode 字元, 每個字元都可以是字母或數位字元、連字號 (-)、句點 (.)、加號 (+) 或底線 (_)。 [**簡易名稱**] 欄位中不允許 > 空格。</span><span class="sxs-lookup"><span data-stu-id="196b8-164">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), a plus sign (+), or an underscore (_).> Spaces are not allowed in the **Simple name** field.</span></span>

6. <span data-ttu-id="196b8-165">可選在 [**描述**] 欄位中, 輸入撥號方案的說明資訊。</span><span class="sxs-lookup"><span data-stu-id="196b8-165">(Optional) In the **Description** field, type descriptive information about the dial plan.</span></span>

7. <span data-ttu-id="196b8-166">可選如果您想要使用此撥號方案作為撥入號碼的地區, 請指定**電話撥入式會議區域**。</span><span class="sxs-lookup"><span data-stu-id="196b8-166">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**.</span></span> <span data-ttu-id="196b8-167">如果您不想將這個撥號方案用於撥入存取電話號碼, 請將此欄位留白。</span><span class="sxs-lookup"><span data-stu-id="196b8-167">If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>

    > [!NOTE]
    > <span data-ttu-id="196b8-168">電話撥入式會議區域需要將電話撥入式會議存取號碼與一或多個撥號方案建立關聯。</span><span class="sxs-lookup"><span data-stu-id="196b8-168">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

8. <span data-ttu-id="196b8-169">可選在 [**外部存取前置**詞] 欄位中, 只有在使用者需要撥一或多個額外的前導數位來取得外部線路時, 才指定值 (例如 9)。</span><span class="sxs-lookup"><span data-stu-id="196b8-169">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits to get an external line (for example, 9).</span></span> <span data-ttu-id="196b8-170">您可以輸入最多四個字元 (也就是 #、\* 及 0-9) 的前置詞值。</span><span class="sxs-lookup"><span data-stu-id="196b8-170">You can type in a prefix value of up to four characters (that is, #, \*, and 0-9).</span></span>

    > [!NOTE]
    > <span data-ttu-id="196b8-171">如果您指定外部存取前置詞, 就不需要建立新的正常化規則來容納該前置詞。</span><span class="sxs-lookup"><span data-stu-id="196b8-171">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

9. <span data-ttu-id="196b8-172">針對撥號方案建立並設定正常化規則:</span><span class="sxs-lookup"><span data-stu-id="196b8-172">Associate and configure normalization rules for the dial plan:</span></span>

   - <span data-ttu-id="196b8-173">若要從企業語音部署中所有可用的正常化規則清單中選擇一或多個規則, 請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="196b8-173">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="196b8-174">在 [**選取正常化規則**] 對話方塊中, 醒目提示您要與撥號計畫建立關聯的規則, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="196b8-174">In the **Select Normalization Rules** dialog box, highlight the rules that you want to associate with the dial plan and then click **OK**.</span></span>

   - <span data-ttu-id="196b8-175">若要定義新的正常化規則, 並將它與撥號方案建立關聯, 請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="196b8-175">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="196b8-176">如需有關定義新規則的詳細資料, 請參閱[在商務用 Skype 中建立或修改正常化規則](normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="196b8-176">For details about defining a new rule, see [Create or modify a normalization rule in Skype for Business](normalization-rules.md).</span></span>

   - <span data-ttu-id="196b8-177">若要編輯已經與撥號方案相關聯的正常化規則, 請醒目提示 [規則名稱], 然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="196b8-177">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span>

   - <span data-ttu-id="196b8-178">若要複製現有的正常化規則, 以做為定義新規則的起點, 請醒目提示規則名稱, 然後按一下 [**複製**], 然後按一下 [**貼**上]。</span><span class="sxs-lookup"><span data-stu-id="196b8-178">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span>

   - <span data-ttu-id="196b8-179">若要從撥號方案中移除正常化規則, 請醒目提示規則名稱, 然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="196b8-179">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="196b8-180">每個撥號方案都必須至少有一個相關聯的正常化規則。</span><span class="sxs-lookup"><span data-stu-id="196b8-180">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="196b8-181">如需如何判斷撥號方案所需的所有正常化規則的詳細資料, 請參閱規劃檔中的[商務用 Skype 伺服器中的出站語音路由規劃](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="196b8-181">For details about how to determine all of the normalization rules a dial plan requires, see [Plan for outbound voice routing in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) in the Planning documentation.</span></span>

10. <span data-ttu-id="196b8-182">確認撥號方案的正常化規則依正確順序排列。</span><span class="sxs-lookup"><span data-stu-id="196b8-182">Verify that the dial plan's normalization rules are arranged in the correct order.</span></span> <span data-ttu-id="196b8-183">若要變更規則在清單中的位置, 請醒目提示 [規則名稱], 然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="196b8-183">To change a rule's position in the list, highlight the rule name and then click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="196b8-184">商務用 Skype 伺服器會從上而下遍歷正常化規則清單, 並使用與撥號號碼相符的第一個規則。</span><span class="sxs-lookup"><span data-stu-id="196b8-184">Skype for Business Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="196b8-185">如果您設定撥號方案, 讓撥入的號碼可以符合多個正常化規則, 請確定更嚴格的規則排序在限制性較低的規則上方。</span><span class="sxs-lookup"><span data-stu-id="196b8-185">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span> <span data-ttu-id="196b8-186">> [**保留所有**正常化規則 ^ (\d{11}) $] 的預設值是符合任何11位數的數位。</span><span class="sxs-lookup"><span data-stu-id="196b8-186">> The default **Keep All** normalization rule^(\d{11})$ matches any 11-digit number.</span></span> <span data-ttu-id="196b8-187">例如, 如果您要新增的正常化規則與從1425開始的11位數數位相符, 請確定 [**全部保留**] 的排序次序低於較強的 ^ (1425 \ d{7}) $ 規則。</span><span class="sxs-lookup"><span data-stu-id="196b8-187">If, for example, you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that **Keep All** is sorted below the more restrictive^(1425\d{7})$ rule.</span></span>

11. <span data-ttu-id="196b8-188">可選輸入數位以測試撥號計畫, 然後按一下 [執行\*\*\*\*]。</span><span class="sxs-lookup"><span data-stu-id="196b8-188">(Optional) Enter a number to test the dial plan and then click **Go**.</span></span> <span data-ttu-id="196b8-189">測試結果會顯示在 [**輸入要測試的號碼**] 下。</span><span class="sxs-lookup"><span data-stu-id="196b8-189">The test results are displayed under **Enter a number to test**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="196b8-190">您可以儲存尚未經過測試的撥號方案, 稍後再重新設定。</span><span class="sxs-lookup"><span data-stu-id="196b8-190">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="196b8-191">如需詳細資訊, 請參閱[測試語音路由](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="196b8-191">For details, see [Testing Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span></span>

12. <span data-ttu-id="196b8-192">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="196b8-192">Click **OK**.</span></span>

13. <span data-ttu-id="196b8-193">在 [**撥號方案**] 頁面上, 按一下 [**認可**], 然後按一下 [**全部提交**]。</span><span class="sxs-lookup"><span data-stu-id="196b8-193">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="196b8-194">每當您建立或修改撥號方案時, 您都必須執行 [**全部提交**] 命令才能發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="196b8-194">Any time you create or modify a dial plan, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="196b8-195">如需詳細資訊, 請參閱在作業檔中[發佈商務用 Skype 中的語音路由設定的待處理變更](voice-route-config-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="196b8-195">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="196b8-196">另請參閱</span><span class="sxs-lookup"><span data-stu-id="196b8-196">See also</span></span>

<span data-ttu-id="196b8-197">[在商務用 Skype 中發佈 [語音路由設定] 的擱置變更](voice-route-config-changes.md)</span><span class="sxs-lookup"><span data-stu-id="196b8-197">[Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md)</span></span>

