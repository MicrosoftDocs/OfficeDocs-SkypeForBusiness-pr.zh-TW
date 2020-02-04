---
title: Lync Server 2013：修改撥號對應表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a dial plan
ms:assetid: a91f02df-cf60-40cf-82fe-e0342c118b91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412797(v=OCS.15)
ms:contentKeyID: 48185099
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd4c007933eb7186e412ada1a3f4c35b241f5eff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-dial-plan-in-lync-server-2013"></a><span data-ttu-id="59b03-102">在 Lync Server 2013 中修改撥號對應表</span><span class="sxs-lookup"><span data-stu-id="59b03-102">Modify a dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59b03-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="59b03-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="59b03-104">若要修改現有的撥號方案，請執行下列程式中的步驟。</span><span class="sxs-lookup"><span data-stu-id="59b03-104">To modify an existing dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="59b03-105">如果您想要建立新的撥號方案，請參閱[在 Lync Server 2013 中建立撥號方案](lync-server-2013-create-a-dial-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="59b03-105">If you want to create a new dial plan, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<div>

## <a name="to-modify-a-dial-plan"></a><span data-ttu-id="59b03-106">修改撥號方案</span><span class="sxs-lookup"><span data-stu-id="59b03-106">To modify a dial plan</span></span>

1.  <span data-ttu-id="59b03-107">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="59b03-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="59b03-108">如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="59b03-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="59b03-109">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="59b03-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="59b03-110">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="59b03-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="59b03-111">在左側導覽列中，按一下 [**語音路由**]，然後按一下 [**撥號計畫**]。</span><span class="sxs-lookup"><span data-stu-id="59b03-111">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="59b03-112">在 [**撥號方案**] 頁面上，按兩下撥號方案名稱。</span><span class="sxs-lookup"><span data-stu-id="59b03-112">On the **Dial Plan** page, double-click a dial plan name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="59b03-113">在建立撥號對應表時設定撥號計畫範圍和名稱。</span><span class="sxs-lookup"><span data-stu-id="59b03-113">The dial plan scope and name were set when the dial plan was created.</span></span> <span data-ttu-id="59b03-114">它們無法變更。</span><span class="sxs-lookup"><span data-stu-id="59b03-114">They cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="59b03-115">可選在 [**編輯撥號**對應表] 中，編輯 [簡稱] 欄位中預先填入相同名稱的 [ **Simple name** ] **（名稱）** 欄位，以指定更具描述性的名稱，以反映要套用撥號方案的網站、服務或使用者。</span><span class="sxs-lookup"><span data-stu-id="59b03-115">(Optional) In **Edit Dial Plan**, edit the **Simple name** field, which is prepopulated with the same name that appears in the **Name** field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="59b03-116"><STRONG>簡單名稱</STRONG>在 Lync Server 2013 部署中的所有撥號方案中都必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="59b03-116">The <STRONG>Simple name</STRONG> must be unique among all dial plans within the Lync Server 2013 deployment.</span></span> <span data-ttu-id="59b03-117">它不能超過 256 Unicode 字元，每個字元都可以是字母或數位字元、連字號（-）、句點（.）、加號（+）或底線（_）。</span><span class="sxs-lookup"><span data-stu-id="59b03-117">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), a plus sign (+), or an underscore (_).</span></span><BR><span data-ttu-id="59b03-118">[<STRONG>簡易名稱</STRONG>] 欄位中不允許有空格。</span><span class="sxs-lookup"><span data-stu-id="59b03-118">Spaces are not allowed in the <STRONG>Simple name</STRONG> field.</span></span>

    
    </div>

6.  <span data-ttu-id="59b03-119">可選在 [**描述**] 欄位中，輸入撥號方案的說明資訊。</span><span class="sxs-lookup"><span data-stu-id="59b03-119">(Optional) In the **Description** field, type descriptive information about the dial plan.</span></span>

7.  <span data-ttu-id="59b03-120">可選如果您想要使用此撥號方案作為撥入號碼的地區，請指定**電話撥入式會議區域**。</span><span class="sxs-lookup"><span data-stu-id="59b03-120">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**.</span></span> <span data-ttu-id="59b03-121">如果您不想將這個撥號方案用於撥入存取電話號碼，請將此欄位留白。</span><span class="sxs-lookup"><span data-stu-id="59b03-121">If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="59b03-122">電話撥入式會議區域需要將電話撥入式會議存取號碼與一或多個撥號方案建立關聯。</span><span class="sxs-lookup"><span data-stu-id="59b03-122">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

    
    </div>

8.  <span data-ttu-id="59b03-123">可選在 [**外部存取前置**詞] 欄位中，只有在使用者需要撥一或多個額外的前導數位來取得外部線路時，才指定值（例如9）。</span><span class="sxs-lookup"><span data-stu-id="59b03-123">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits to get an external line (for example, 9).</span></span> <span data-ttu-id="59b03-124">您可以輸入最多四個字元的前置詞值（也就是\# \*、、及0-9）。</span><span class="sxs-lookup"><span data-stu-id="59b03-124">You can type in a prefix value of up to four characters (that is, \#, \*, and 0-9).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="59b03-125">如果您指定外部存取前置詞，就不需要建立新的正常化規則來容納該前置詞。</span><span class="sxs-lookup"><span data-stu-id="59b03-125">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

    
    </div>

9.  <span data-ttu-id="59b03-126">針對撥號方案建立並設定正常化規則：</span><span class="sxs-lookup"><span data-stu-id="59b03-126">Associate and configure normalization rules for the dial plan:</span></span>
    
      - <span data-ttu-id="59b03-127">若要從企業語音部署中所有可用的正常化規則清單中選擇一或多個規則，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="59b03-127">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="59b03-128">在 [**選取正常化規則**] 對話方塊中，醒目提示您要與撥號計畫建立關聯的規則，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="59b03-128">In the **Select Normalization Rules** dialog box, highlight the rules that you want to associate with the dial plan and then click **OK**.</span></span>
    
      - <span data-ttu-id="59b03-129">若要定義新的正常化規則，並將它與撥號方案建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="59b03-129">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="59b03-130">如需有關定義新規則的詳細資料，請參閱[在 Lync Server 2013 中定義正常化規則](lync-server-2013-defining-normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="59b03-130">For details about defining a new rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="59b03-131">若要編輯已經與撥號方案相關聯的正常化規則，請醒目提示 [規則名稱]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="59b03-131">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span> <span data-ttu-id="59b03-132">如需有關編輯規則的詳細資訊，請參閱[在 Lync Server 2013 中定義正常化規則](lync-server-2013-defining-normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="59b03-132">For details about editing the rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="59b03-133">若要複製現有的正常化規則，以做為定義新規則的起點，請醒目提示規則名稱，然後按一下 [**複製**]，然後按一下 [**貼**上]。</span><span class="sxs-lookup"><span data-stu-id="59b03-133">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="59b03-134">如需編輯複本的詳細資料，請參閱[在 Lync Server 2013 中定義正常化規則](lync-server-2013-defining-normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="59b03-134">For details about editing the copy, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="59b03-135">若要從撥號方案中移除正常化規則，請醒目提示規則名稱，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="59b03-135">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="59b03-136">每個撥號方案都必須至少有一個相關聯的正常化規則。</span><span class="sxs-lookup"><span data-stu-id="59b03-136">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="59b03-137">如需如何判斷撥號方案所需的所有正常化規則的詳細資料，請參閱規劃檔中的<A href="lync-server-2013-dial-plans-and-normalization-rules.md">Lync Server 2013 中的撥號方案和正常化規則</A>。</span><span class="sxs-lookup"><span data-stu-id="59b03-137">For details about how to determine all of the normalization rules a dial plan requires, see <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

10. <span data-ttu-id="59b03-138">確認撥號方案的正常化規則依正確順序排列。</span><span class="sxs-lookup"><span data-stu-id="59b03-138">Verify that the dial plan’s normalization rules are arranged in the correct order.</span></span> <span data-ttu-id="59b03-139">若要變更規則在清單中的位置，請醒目提示 [規則名稱]，然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="59b03-139">To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="59b03-140">Lync Server 會從上到下遍歷正常化規則清單，並使用與撥號號碼相符的第一個規則。</span><span class="sxs-lookup"><span data-stu-id="59b03-140">Lync Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="59b03-141">如果您設定撥號方案，讓撥入的號碼可以符合多個正常化規則，請確定更嚴格的規則排序在限制性較低的規則上方。</span><span class="sxs-lookup"><span data-stu-id="59b03-141">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span><BR><span data-ttu-id="59b03-142">預設 [<STRONG>保留所有</STRONG>正常化規則<STRONG>^ （\d{11}）] $</STRONG>符合任何11位數的數位。</span><span class="sxs-lookup"><span data-stu-id="59b03-142">The default <STRONG>Keep All</STRONG> normalization rule <STRONG>^(\d{11})$</STRONG> matches any 11-digit number.</span></span> <span data-ttu-id="59b03-143">例如，如果您要新增的正常化規則與從1425開始的11位數數位相符，請確定 [<STRONG>全部保留</STRONG>] 的排序次序低於較強的<STRONG>^ （1425 \ d{7}） $</STRONG>規則。</span><span class="sxs-lookup"><span data-stu-id="59b03-143">If, for example, you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that <STRONG>Keep All</STRONG> is sorted below the more restrictive <STRONG>^(1425\d{7})$</STRONG> rule.</span></span>

    
    </div>

11. <span data-ttu-id="59b03-144">可選輸入數位以測試撥號計畫，**然後按一下 [** 執行]。</span><span class="sxs-lookup"><span data-stu-id="59b03-144">(Optional) Enter a number to test the dial plan and then click **Go**.</span></span> <span data-ttu-id="59b03-145">測試結果會顯示在 [**輸入要測試的號碼**] 下。</span><span class="sxs-lookup"><span data-stu-id="59b03-145">The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="59b03-146">您可以儲存尚未經過測試的撥號方案，稍後再重新設定。</span><span class="sxs-lookup"><span data-stu-id="59b03-146">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="59b03-147">如需詳細資訊，請參閱<A href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中測試語音路由</A>。</span><span class="sxs-lookup"><span data-stu-id="59b03-147">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="59b03-148">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59b03-148">Click **OK**.</span></span>

13. <span data-ttu-id="59b03-149">在 [**撥號方案**] 頁面上，按一下 [**認可**]，然後按一下 [**全部提交**]。</span><span class="sxs-lookup"><span data-stu-id="59b03-149">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="59b03-150">每當您建立或修改撥號方案時，您都必須執行 [<STRONG>全部提交</STRONG>] 命令才能發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="59b03-150">Any time you create or modify a dial plan, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="59b03-151">如需詳細資訊，請參閱在 Operations 檔中<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">發佈 Lync Server 2013 中的語音路由設定的未決變更</A>。</span><span class="sxs-lookup"><span data-stu-id="59b03-151">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="59b03-152">請參閱</span><span class="sxs-lookup"><span data-stu-id="59b03-152">See Also</span></span>


[<span data-ttu-id="59b03-153">在 Lync Server 2013 中建立撥號方案</span><span class="sxs-lookup"><span data-stu-id="59b03-153">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="59b03-154">在 Lync Server 2013 中發佈語音路由設定的擱置變更</span><span class="sxs-lookup"><span data-stu-id="59b03-154">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="59b03-155">在 Lync Server 2013 中定義正規化規則</span><span class="sxs-lookup"><span data-stu-id="59b03-155">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

