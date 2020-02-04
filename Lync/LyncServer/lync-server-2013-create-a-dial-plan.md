---
title: Lync Server 2013：建立撥號方案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a dial plan
ms:assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398909(v=OCS.15)
ms:contentKeyID: 48185424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1d4647f374fd65c0be52da111b7ef2d41c0faae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-dial-plan-in-lync-server-2013"></a><span data-ttu-id="ebcf8-102">在 Lync Server 2013 中建立撥號方案</span><span class="sxs-lookup"><span data-stu-id="ebcf8-102">Create a dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebcf8-103">_**主題上次修改日期：** 2013-10-24_</span><span class="sxs-lookup"><span data-stu-id="ebcf8-103">_**Topic Last Modified:** 2013-10-24_</span></span>

<span data-ttu-id="ebcf8-104">若要建立新的撥號方案，請執行下列程式中的步驟。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-104">To create a new dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="ebcf8-105">如果您想要編輯撥號方案，請參閱[在 Lync Server 2013 中修改撥號計畫](lync-server-2013-modify-a-dial-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-105">If you want to edit a dial plan, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

<div>

## <a name="to-create-a-dial-plan"></a><span data-ttu-id="ebcf8-106">建立撥號方案</span><span class="sxs-lookup"><span data-stu-id="ebcf8-106">To create a dial plan</span></span>

1.  <span data-ttu-id="ebcf8-107">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="ebcf8-108">如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ebcf8-109">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ebcf8-110">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ebcf8-111">在左側導覽列中，按一下 [**語音路由**]，然後按一下 [**撥號計畫**]。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-111">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="ebcf8-112">在 [**撥號方案**] 頁面上，按一下 [**新增**]，然後選取撥號方案的範圍：</span><span class="sxs-lookup"><span data-stu-id="ebcf8-112">On the **Dial Plan** page, click **New** and select a scope for the dial plan:</span></span>
    
      - <span data-ttu-id="ebcf8-113">除了任何指派給使用者撥號方案的使用者或群組之外，**網站撥號計畫**也適用于整個網站。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-113">**Site dial plan** applies to an entire site, except any users or groups that are assigned to a user dial plan.</span></span> <span data-ttu-id="ebcf8-114">如果您選取 [**網站**] 作為撥號方案的範圍，則必須從 [**選取網站**] 對話方塊中選擇網站。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-114">If you select **Site** for a dial plan’s scope, you must choose the site from the **Select a Site** dialog box.</span></span> <span data-ttu-id="ebcf8-115">如果已為網站建立撥號方案，該網站不會出現在 [**選取網站**] 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-115">If a dial plan has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>
    
      - <span data-ttu-id="ebcf8-116">您可以將**池撥號方案**套用至公用的交換式電話網絡（PSTN）閘道或註冊機構。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-116">**Pool dial plan** can apply to a public switched telephone network (PSTN) gateway or a Registrar.</span></span> <span data-ttu-id="ebcf8-117">如果您為撥號方案的範圍選取 [**泳池**]，請從 [**選取服務**] 對話方塊中選擇 PSTN 閘道或註冊機構。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-117">If you select **Pool** for a dial plan’s scope, choose the PSTN gateway or Registrar from the **Select a Service** dialog box.</span></span> <span data-ttu-id="ebcf8-118">如果已為服務（PSTN 閘道或註冊機構）建立撥號方案，該服務不會出現在清單中。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-118">If a dial plan has already been created for a service (PSTN gateway or Registrar), the service does not appear in the list.</span></span>
    
      - <span data-ttu-id="ebcf8-119">您可以將**使用者撥號方案**套用至指定的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-119">**User dial plan** can be applied to specified users or groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ebcf8-120">在您選取撥號方案範圍之後，就無法變更它。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-120">After you select the dial plan scope, it cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="ebcf8-121">如果您要建立使用者撥號方案，請在 [**新增撥號方案**] 對話方塊上的 [**名稱**] 欄位中，輸入描述性的名稱。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-121">If you are creating a user dial plan, enter a descriptive name in the **Name** field on the **New Dial Plan** dialog box.</span></span> <span data-ttu-id="ebcf8-122">儲存此名稱之後，就無法變更。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-122">After this name is saved, it cannot be changed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ebcf8-123">針對網站撥號方案，[<STRONG>名稱</STRONG>] 欄位會預先填入網站名稱，且無法變更。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-123">For site dial plans, the <STRONG>Name</STRONG> field is prepopulated with the site name and cannot be changed.</span></span><BR><span data-ttu-id="ebcf8-124">針對池撥號方案，使用 PSTN 閘道或註冊機構名稱預先填入<STRONG>name</STRONG>欄位，且無法變更。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-124">For pool dial plans, the <STRONG>Name</STRONG> field is prepopulated with the PSTN gateway or Registrar name and cannot be changed.</span></span>

    
    </div>

6.  <span data-ttu-id="ebcf8-125">[**簡稱] 欄位會**預先填入與 [**名稱**] 欄位中相同的名稱。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-125">The **Simple name** field is prepopulated with the same name that appears in the **Name** field.</span></span> <span data-ttu-id="ebcf8-126">您可以選擇性地編輯此欄位，以指定更具描述性的名稱，以反映要套用撥號方案的網站、服務或使用者。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-126">You can optionally edit this field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ebcf8-127"><STRONG>簡單名稱</STRONG>在 Lync Server 部署中的所有撥號方案中都必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-127">The <STRONG>Simple name</STRONG> must be unique among all dial plans within the Lync Server deployment.</span></span> <span data-ttu-id="ebcf8-128">它不能超過 256 Unicode 字元，每個字元都可以是字母或數位字元、連字號（-）、句號（.）或底線（_）。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-128">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), or an underscore (_).</span></span><BR><span data-ttu-id="ebcf8-129"><STRONG>不支援</STRONG>的字元包括 RFC 3966 （http://www.ietf.org/rfc/rfc3966.txt).）中定義的空格和保留字元。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-129">Characters <STRONG>not supported</STRONG> include spaces and Reserved characters as defined in RFC 3966 (http://www.ietf.org/rfc/rfc3966.txt).</span></span> <span data-ttu-id="ebcf8-130"><STRONG>簡單名稱</STRONG>中<STRONG>不支援</STRONG>的保留字元包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="ebcf8-130">Reserved characters that are <STRONG>not supported</STRONG> in the <STRONG>Simple Name</STRONG> include the following:</span></span><BR><span data-ttu-id="ebcf8-131">";""/" "?"":" "@" "&amp;" "=" "+" "$" ","</span><span class="sxs-lookup"><span data-stu-id="ebcf8-131">";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span></span>

    
    </div>

7.  <span data-ttu-id="ebcf8-132">可選在 [**描述**] 欄位中，您可以輸入撥號方案的其他描述性資訊。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-132">(Optional) In the **Description** field, you can type additional descriptive information about the dial plan.</span></span>

8.  <span data-ttu-id="ebcf8-133">可選如果您想要使用此撥號方案作為撥入號碼的地區，請指定**電話撥入式會議區域**。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-133">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**.</span></span> <span data-ttu-id="ebcf8-134">如果您不想將這個撥號方案用於撥入存取電話號碼，請將此欄位留白。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-134">If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ebcf8-135">電話撥入式會議區域需要將電話撥入式會議存取號碼與一或多個撥號方案建立關聯。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-135">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

    
    </div>

9.  <span data-ttu-id="ebcf8-136">可選在 [**外部存取前置**詞] 欄位中，只有在使用者需要撥一或多個額外的前導數位（例如9）來取得外部線路時，才指定值。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-136">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="ebcf8-137">您可以輸入最多四個字元（\#、 \*和0-9）的前置詞值。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-137">You can type in a prefix value of up to four characters (\#, \*, and 0-9).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ebcf8-138">如果您指定外部存取前置詞，就不需要建立新的正常化規則來容納該前置詞。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-138">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

    
    </div>

10. <span data-ttu-id="ebcf8-139">針對撥號方案建立並設定正常化規則，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ebcf8-139">Associate and configure normalization rules for the dial plan as follows:</span></span>
    
      - <span data-ttu-id="ebcf8-140">若要從企業語音部署中所有可用的正常化規則清單中選擇一或多個規則，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-140">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="ebcf8-141">在 [**選取正常化規則**] 中，醒目提示您要與撥號計畫建立關聯的規則，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-141">In **Select Normalization Rules**, highlight the rules you want to associate with the dial plan and then click **OK**.</span></span>
    
      - <span data-ttu-id="ebcf8-142">若要定義新的正常化規則，並將它與撥號方案建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-142">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="ebcf8-143">如需有關定義新規則的詳細資料，請參閱[在 Lync Server 2013 中定義正常化規則](lync-server-2013-defining-normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-143">For details about defining a new rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="ebcf8-144">若要編輯已經與撥號方案相關聯的正常化規則，請醒目提示 [規則名稱]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-144">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span> <span data-ttu-id="ebcf8-145">如需有關編輯規則的詳細資訊，請參閱[在 Lync Server 2013 中定義正常化規則](lync-server-2013-defining-normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-145">For details about editing the rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="ebcf8-146">若要複製現有的正常化規則，以做為定義新規則的起點，請醒目提示規則名稱，然後按一下 [**複製**]，然後按一下 [**貼**上]。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-146">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="ebcf8-147">如需編輯複本的詳細資料，請參閱[在 Lync Server 2013 中定義正常化規則](lync-server-2013-defining-normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-147">For details about editing the copy, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="ebcf8-148">若要從撥號方案中移除正常化規則，請醒目提示規則名稱，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-148">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ebcf8-149">每個撥號方案都必須至少有一個相關聯的正常化規則。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-149">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="ebcf8-150">如需如何判斷撥號方案所需的所有正常化規則的相關資訊，請參閱規劃檔中的<A href="lync-server-2013-dial-plans-and-normalization-rules.md">Lync Server 2013 中的撥號方案和正常化規則</A>。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-150">For information about how to determine all of the normalization rules a dial plan requires, see <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

11. <span data-ttu-id="ebcf8-151">確認撥號方案的正常化規則依正確順序排列。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-151">Verify that the dial plan’s normalization rules are arranged in the correct order.</span></span> <span data-ttu-id="ebcf8-152">若要變更規則在清單中的位置，請醒目提示 [規則名稱]，然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-152">To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ebcf8-153">Lync Server 會從上到下遍歷正常化規則清單，並使用與撥號號碼相符的第一個規則。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-153">Lync Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="ebcf8-154">如果您設定撥號方案，讓撥入的號碼可以符合多個正常化規則，請確定更嚴格的規則排序在限制性較低的規則上方。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-154">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span><BR><span data-ttu-id="ebcf8-155">預設 [<STRONG>保留所有</STRONG>正常化規則<STRONG>^ （\d{11}）] $</STRONG>符合任何11位數的數位。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-155">The default <STRONG>Keep All</STRONG> normalization rule <STRONG>^(\d{11})$</STRONG> matches any 11-digit number.</span></span> <span data-ttu-id="ebcf8-156">例如，如果您要新增的正常化規則與從1425開始的11位數數位相符，請確定 [<STRONG>全部保留</STRONG>] 的排序次序低於較強的<STRONG>^ （1425 \{7}d） $</STRONG>規則。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-156">For example, if you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that <STRONG>Keep All</STRONG> is sorted below the more restrictive <STRONG>^(1425\d{7})$</STRONG> rule.</span></span>

    
    </div>

12. <span data-ttu-id="ebcf8-157">可選輸入數位以測試撥號計畫，**然後按一下 [** 執行]。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-157">(Optional) Enter a number to test the dial plan and then click **Go**.</span></span> <span data-ttu-id="ebcf8-158">測試結果會顯示在 [**輸入要測試的號碼**] 下。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-158">The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ebcf8-159">您可以儲存尚未經過測試的撥號方案，稍後再重新設定。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-159">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="ebcf8-160">如需詳細資訊，請參閱<A href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中測試語音路由</A>。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-160">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

13. <span data-ttu-id="ebcf8-161">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-161">Click **OK**.</span></span>

14. <span data-ttu-id="ebcf8-162">在 [**撥號方案**] 頁面上，按一下 [**認可**]，然後按一下 [**全部提交**]。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-162">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ebcf8-163">每當您建立撥號方案時，您都必須執行 [<STRONG>全部提交</STRONG>] 命令來發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-163">Any time you create a dial plan, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="ebcf8-164">如需詳細資訊，請參閱在 Operations 檔中<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">發佈 Lync Server 2013 中的語音路由設定的未決變更</A>。</span><span class="sxs-lookup"><span data-stu-id="ebcf8-164">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ebcf8-165">請參閱</span><span class="sxs-lookup"><span data-stu-id="ebcf8-165">See Also</span></span>


[<span data-ttu-id="ebcf8-166">在 Lync Server 2013 中修改撥號對應表</span><span class="sxs-lookup"><span data-stu-id="ebcf8-166">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="ebcf8-167">在 Lync Server 2013 中發佈語音路由設定的擱置變更</span><span class="sxs-lookup"><span data-stu-id="ebcf8-167">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="ebcf8-168">在 Lync Server 2013 中定義正規化規則</span><span class="sxs-lookup"><span data-stu-id="ebcf8-168">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

