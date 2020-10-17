---
title: Lync Server 2013：修改撥號對應表
description: Lync Server 2013：修改撥號對應表。
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
ms.openlocfilehash: 9e173552970c6b1799076b3f3b05d59ed6f0719e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550499"
---
# <a name="modify-a-dial-plan-in-lync-server-2013"></a><span data-ttu-id="a6cf0-103">在 Lync Server 2013 中修改撥號對應表</span><span class="sxs-lookup"><span data-stu-id="a6cf0-103">Modify a dial plan in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6cf0-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a6cf0-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a6cf0-105">若要修改現有的撥號對應表，請執行下列程式中的步驟。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-105">To modify an existing dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="a6cf0-106">如果您想要建立新的撥號對應表，請參閱 [在 Lync Server 2013 中建立撥號](lync-server-2013-create-a-dial-plan.md)對應表。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-106">If you want to create a new dial plan, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<div>

## <a name="to-modify-a-dial-plan"></a><span data-ttu-id="a6cf0-107">修改撥號對應表</span><span class="sxs-lookup"><span data-stu-id="a6cf0-107">To modify a dial plan</span></span>

1.  <span data-ttu-id="a6cf0-108">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="a6cf0-109">如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="a6cf0-110">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a6cf0-111">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a6cf0-112">在左導覽列中，依序按一下 [語音路由]\*\*\*\* 和 [撥號對應表]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-112">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="a6cf0-113">在 [撥號對應表]\*\*\*\* 頁面上，按兩下撥號對應表名稱。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-113">On the **Dial Plan** page, double-click a dial plan name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a6cf0-114">建立撥號對應表時設定撥號對應表的範圍和名稱。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-114">The dial plan scope and name were set when the dial plan was created.</span></span> <span data-ttu-id="a6cf0-115">您無法加以變更。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-115">They cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="a6cf0-116"> (選用) 在 [ **編輯撥號**對應表] 中，編輯 [ **簡易名稱** ] 欄位（預先填入 **名稱** ] 欄位中顯示的相同名稱），以指定反映撥號對應表所套用之網站、服務或使用者的更具描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-116">(Optional) In **Edit Dial Plan**, edit the **Simple name** field, which is prepopulated with the same name that appears in the **Name** field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a6cf0-117">在 Lync Server 2013 部署內的所有撥號對應表中， <STRONG>簡單名稱</STRONG> 必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-117">The <STRONG>Simple name</STRONG> must be unique among all dial plans within the Lync Server 2013 deployment.</span></span> <span data-ttu-id="a6cf0-118">它不得超過256的 Unicode 字元，每個字元可以是字母或數位字元、連字號 ( ) 、句點 ( ) 、正負號 (+) 或底線 (_) 。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-118">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), a plus sign (+), or an underscore (_).</span></span><BR><span data-ttu-id="a6cf0-119">[ <STRONG>簡單名稱</STRONG> ] 欄位中不允許使用空格。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-119">Spaces are not allowed in the <STRONG>Simple name</STRONG> field.</span></span>

    
    </div>

6.  <span data-ttu-id="a6cf0-120"> (選用) 在 [ **描述** ] 欄位中，輸入撥號對應表的描述資訊。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-120">(Optional) In the **Description** field, type descriptive information about the dial plan.</span></span>

7.  <span data-ttu-id="a6cf0-121"> (選用) 若您要使用此撥號對應表作為撥入存取號碼的地區，請指定 **電話撥入式會議區域**。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-121">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**.</span></span> <span data-ttu-id="a6cf0-122">如果您不想要將此撥號對應表用於撥入存取號碼，請將此欄位保留空白。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-122">If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a6cf0-123">必須使用電話撥入式會議區域，才能將電話撥入式會議存取號碼與一或多個撥號對應表產生關聯。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-123">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

    
    </div>

8.  <span data-ttu-id="a6cf0-124"> (選用) 在 [ **外部存取前置** 詞] 欄位中，只有在使用者需要撥打一或多個其他前導數位以取得外部行時，才指定值 (例如，9) 。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-124">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits to get an external line (for example, 9).</span></span> <span data-ttu-id="a6cf0-125">您可以輸入最多四個字元的前置詞值 (，也就是，，， \# \* 及 0-9) 。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-125">You can type in a prefix value of up to four characters (that is, \#, \*, and 0-9).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a6cf0-126">如果您指定了外部存取前置詞，則不需要建立新的正規化規則來容納前置詞。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-126">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

    
    </div>

9.  <span data-ttu-id="a6cf0-127">關聯及設定撥號對應表的正規化規則：</span><span class="sxs-lookup"><span data-stu-id="a6cf0-127">Associate and configure normalization rules for the dial plan:</span></span>
    
      - <span data-ttu-id="a6cf0-128">若要從 Enterprise Voice 部署中所有可用的正規化規則清單中選擇一個或多個規則，請按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-128">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="a6cf0-129">在 [ **選取正規化規則** ] 對話方塊中，反白顯示您想要與撥號對應表產生關聯的規則，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-129">In the **Select Normalization Rules** dialog box, highlight the rules that you want to associate with the dial plan and then click **OK**.</span></span>
    
      - <span data-ttu-id="a6cf0-130">若要定義新的正規化規則，並將它與撥號對應表產生關聯，請按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-130">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="a6cf0-131">如需定義新規則的詳細資訊，請參閱 [在 Lync Server 2013 中定義正常化規則](lync-server-2013-defining-normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-131">For details about defining a new rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="a6cf0-132">若要編輯已與撥號對應表相關聯的正規化規則，請反白顯示規則名稱，然後按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-132">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span> <span data-ttu-id="a6cf0-133">如需編輯規則的詳細資訊，請參閱 [在 Lync Server 2013 中定義正常化規則](lync-server-2013-defining-normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-133">For details about editing the rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="a6cf0-134">若要複製現有的正規化規則，以做為定義新規則的起點，請反白顯示規則名稱，然後按一下 [ **複製**]，然後按一下 [ **貼**上]。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-134">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="a6cf0-135">如需編輯複本的詳細資訊，請參閱 [在 Lync Server 2013 中定義正常化規則](lync-server-2013-defining-normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-135">For details about editing the copy, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="a6cf0-136">若要從撥號對應表中移除正規化規則，請反白顯示規則名稱，然後按一下 [ **移除**]。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-136">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a6cf0-137">每個撥號對應表至少必須有一個相關聯的正常化規則。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-137">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="a6cf0-138">如需如何判斷撥號對應表所需之所有正規化規則的詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Lync Server 2013 中的撥號對應表和正常化規則</A> 。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-138">For details about how to determine all of the normalization rules a dial plan requires, see <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

10. <span data-ttu-id="a6cf0-139">確認撥號對應表的正規化規則依正確的順序排列。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-139">Verify that the dial plan’s normalization rules are arranged in the correct order.</span></span> <span data-ttu-id="a6cf0-140">若要變更規則在清單中的位置，請反白顯示規則名稱，然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-140">To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a6cf0-141">Lync Server 會從左上部遍歷正規化規則清單，並使用符合撥號號碼的第一個規則。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-141">Lync Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="a6cf0-142">如果您設定撥號對應表，讓已撥號的號碼可以比對多個正規化規則，請確定限制性以上的規則排序的限制性較低。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-142">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span><BR><span data-ttu-id="a6cf0-143">預設 <STRONG>保持所有</STRONG> 正規化規則 <STRONG>^ ( \d {11}) $</STRONG> 符合任何11位數的數位。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-143">The default <STRONG>Keep All</STRONG> normalization rule <STRONG>^(\d{11})$</STRONG> matches any 11-digit number.</span></span> <span data-ttu-id="a6cf0-144">例如，如果您新增的正規化規則符合11位數的開始1425的數位，請確定 [ <STRONG>全部保留</STRONG> ] 的專案排序低於較嚴格的 <STRONG>^ (1425 {7}) $</STRONG> rule。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-144">If, for example, you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that <STRONG>Keep All</STRONG> is sorted below the more restrictive <STRONG>^(1425\d{7})$</STRONG> rule.</span></span>

    
    </div>

11. <span data-ttu-id="a6cf0-145"> (選用) 請輸入號碼以測試撥號對應表，然後按一下 [ **移至**]。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-145">(Optional) Enter a number to test the dial plan and then click **Go**.</span></span> <span data-ttu-id="a6cf0-146">測試結果會顯示在 [ **輸入要測試的號碼**] 底下。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-146">The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a6cf0-147">您可以儲存尚未通過測試的撥號對應表，然後再加以重新設定。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-147">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="a6cf0-148">如需詳細資訊，請參閱 <A href="lync-server-2013-test-voice-routing.md">Test voice routing In Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-148">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="a6cf0-149">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-149">Click **OK**.</span></span>

13. <span data-ttu-id="a6cf0-150">在 [ **撥號** 對應表] 頁面上，按一下 [ **認可**]，然後按一下 [ **全部認可**]。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-150">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a6cf0-151">每當您建立或修改撥號對應表時，都必須執行「 <STRONG>認可全部</STRONG> 」命令來發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-151">Any time you create or modify a dial plan, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="a6cf0-152">如需詳細資訊，請參閱 Operations 檔中的在 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中發佈擱置的變更至語音路由</A> 設定。</span><span class="sxs-lookup"><span data-stu-id="a6cf0-152">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a6cf0-153">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a6cf0-153">See Also</span></span>


[<span data-ttu-id="a6cf0-154">在 Lync Server 2013 中建立撥號對應表</span><span class="sxs-lookup"><span data-stu-id="a6cf0-154">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="a6cf0-155">在 Lync Server 2013 中將擱置的變更發佈至語音路由設定</span><span class="sxs-lookup"><span data-stu-id="a6cf0-155">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="a6cf0-156">在 Lync Server 2013 中定義正常化規則</span><span class="sxs-lookup"><span data-stu-id="a6cf0-156">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

