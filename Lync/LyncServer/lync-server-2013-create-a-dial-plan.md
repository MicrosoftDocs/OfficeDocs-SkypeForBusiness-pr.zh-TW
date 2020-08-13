---
title: Lync Server 2013：建立撥號對應表
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
ms.openlocfilehash: 382b04f9b0aa835d0230cb05fb56cb272546c038
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192926"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-dial-plan-in-lync-server-2013"></a><span data-ttu-id="4cbf4-102">在 Lync Server 2013 中建立撥號對應表</span><span class="sxs-lookup"><span data-stu-id="4cbf4-102">Create a dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4cbf4-103">_**主題上次修改日期：** 2013-10-24_</span><span class="sxs-lookup"><span data-stu-id="4cbf4-103">_**Topic Last Modified:** 2013-10-24_</span></span>

<span data-ttu-id="4cbf4-104">若要建立新的撥號對應表，請執行下列程式中的步驟。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-104">To create a new dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="4cbf4-105">如果您想要編輯撥號對應表，請參閱[在 Lync Server 2013 中修改撥號](lync-server-2013-modify-a-dial-plan.md)對應表。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-105">If you want to edit a dial plan, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

<div>

## <a name="to-create-a-dial-plan"></a><span data-ttu-id="4cbf4-106">建立撥號對應表</span><span class="sxs-lookup"><span data-stu-id="4cbf4-106">To create a dial plan</span></span>

1.  <span data-ttu-id="4cbf4-107">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="4cbf4-108">如需詳細資訊，請參閱[在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="4cbf4-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4cbf4-110">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4cbf4-111">在左導覽列中，依序按一下 [語音路由]\*\*\*\* 和 [撥號對應表]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-111">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="4cbf4-112">在 [**撥號**對應表] 頁面上，按一下 [**新增**]，然後選取撥號對應表的範圍：</span><span class="sxs-lookup"><span data-stu-id="4cbf4-112">On the **Dial Plan** page, click **New** and select a scope for the dial plan:</span></span>
    
      - <span data-ttu-id="4cbf4-113">**網站撥號**對應表適用于整個網站，但任何指派給使用者撥號對應表的使用者或群組除外。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-113">**Site dial plan** applies to an entire site, except any users or groups that are assigned to a user dial plan.</span></span> <span data-ttu-id="4cbf4-114">如果您針對撥號對應表的範圍選取 [**網站**]，必須從 [**選取網站**] 對話方塊中選擇網站。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-114">If you select **Site** for a dial plan’s scope, you must choose the site from the **Select a Site** dialog box.</span></span> <span data-ttu-id="4cbf4-115">如果已為網站建立撥號對應表，該網站不會出現在 [**選取網站**] 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-115">If a dial plan has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>
    
      - <span data-ttu-id="4cbf4-116">**集區撥號**對應表可以套用到公用交換電話網路 (PSTN) 閘道或註冊機構。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-116">**Pool dial plan** can apply to a public switched telephone network (PSTN) gateway or a Registrar.</span></span> <span data-ttu-id="4cbf4-117">如果您選取 [**集**區] 作為撥號對應表的範圍，請從 [**選取服務**] 對話方塊中選擇 PSTN 閘道或註冊機。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-117">If you select **Pool** for a dial plan’s scope, choose the PSTN gateway or Registrar from the **Select a Service** dialog box.</span></span> <span data-ttu-id="4cbf4-118">如果已為服務 (PSTN 閘道或註冊機) 建立撥號對應表，則該服務不會出現在清單中。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-118">If a dial plan has already been created for a service (PSTN gateway or Registrar), the service does not appear in the list.</span></span>
    
      - <span data-ttu-id="4cbf4-119">**使用者撥號**對應表可以套用至指定的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-119">**User dial plan** can be applied to specified users or groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4cbf4-120">在您選取撥號對應表範圍後，就無法變更。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-120">After you select the dial plan scope, it cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="4cbf4-121">如果您要建立使用者撥號對應表，請在 [**新增撥號**對應表] 對話方塊的 [**名稱**] 欄位中輸入描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-121">If you are creating a user dial plan, enter a descriptive name in the **Name** field on the **New Dial Plan** dialog box.</span></span> <span data-ttu-id="4cbf4-122">儲存此名稱後，就無法變更。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-122">After this name is saved, it cannot be changed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4cbf4-123">針對網站撥號對應表，[<STRONG>名稱</STRONG>] 欄位會預先填入網站名稱，而且無法變更。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-123">For site dial plans, the <STRONG>Name</STRONG> field is prepopulated with the site name and cannot be changed.</span></span><BR><span data-ttu-id="4cbf4-124">針對集區撥號對應表，[<STRONG>名稱</STRONG>] 欄位會預先填入 PSTN 閘道或註冊機名稱，而且無法變更。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-124">For pool dial plans, the <STRONG>Name</STRONG> field is prepopulated with the PSTN gateway or Registrar name and cannot be changed.</span></span>

    
    </div>

6.  <span data-ttu-id="4cbf4-125">[**簡單名稱**] 欄位會預先填入 [**名稱**] 欄位中顯示的相同名稱。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-125">The **Simple name** field is prepopulated with the same name that appears in the **Name** field.</span></span> <span data-ttu-id="4cbf4-126">您可以選擇性地編輯此欄位，以指定更具描述性的名稱，以反映套用撥號對應表的網站、服務或使用者。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-126">You can optionally edit this field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4cbf4-127">在 Lync Server 部署內的所有撥號對應表中，<STRONG>簡單名稱</STRONG>必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-127">The <STRONG>Simple name</STRONG> must be unique among all dial plans within the Lync Server deployment.</span></span> <span data-ttu-id="4cbf4-128">它不得超過256的 Unicode 字元，每個字元可以是字母或數位字元、連字號 ( ) 、句點 ( ) 或底線 (_) 。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-128">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), or an underscore (_).</span></span><BR><span data-ttu-id="4cbf4-129"><STRONG>不支援</STRONG>的字元包括 RFC 3966 (中所定義的空格和保留字元 http://www.ietf.org/rfc/rfc3966.txt) 。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-129">Characters <STRONG>not supported</STRONG> include spaces and Reserved characters as defined in RFC 3966 (http://www.ietf.org/rfc/rfc3966.txt).</span></span> <span data-ttu-id="4cbf4-130">在<STRONG>簡易名稱</STRONG>中<STRONG>不支援</STRONG>的保留字元包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="4cbf4-130">Reserved characters that are <STRONG>not supported</STRONG> in the <STRONG>Simple Name</STRONG> include the following:</span></span><BR><span data-ttu-id="4cbf4-131">";""/" "?"":" "@" "&amp;" "=" "+" "$" ","</span><span class="sxs-lookup"><span data-stu-id="4cbf4-131">";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span></span>

    
    </div>

7.  <span data-ttu-id="4cbf4-132"> (選用) 在 [**描述**] 欄位中，您可以輸入撥號對應表的其他描述性資訊。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-132">(Optional) In the **Description** field, you can type additional descriptive information about the dial plan.</span></span>

8.  <span data-ttu-id="4cbf4-133"> (選用) 若您要使用此撥號對應表作為撥入存取號碼的地區，請指定**電話撥入式會議區域**。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-133">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**.</span></span> <span data-ttu-id="4cbf4-134">如果您不想要將此撥號對應表用於撥入存取號碼，請將此欄位保留空白。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-134">If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4cbf4-135">必須使用電話撥入式會議區域，才能將電話撥入式會議存取號碼與一或多個撥號對應表產生關聯。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-135">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

    
    </div>

9.  <span data-ttu-id="4cbf4-136"> (選用) 在 [**外部存取前置**詞] 欄位中，只有在使用者需要撥打一或多個其他前導數位時，才指定值 (例如，9) 以取得外部行。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-136">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="4cbf4-137">您可以輸入最多四個字元的前置詞值 (\# ， \* 及 0-9) 。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-137">You can type in a prefix value of up to four characters (\#, \*, and 0-9).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4cbf4-138">如果您指定了外部存取前置詞，則不需要建立新的正規化規則來容納前置詞。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-138">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

    
    </div>

10. <span data-ttu-id="4cbf4-139">建立和設定撥號對應表的正規化規則，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4cbf4-139">Associate and configure normalization rules for the dial plan as follows:</span></span>
    
      - <span data-ttu-id="4cbf4-140">若要從 Enterprise Voice 部署中所有可用的正規化規則清單中選擇一個或多個規則，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-140">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="4cbf4-141">在 [**選取正規化規則**] 中，反白顯示您想要與撥號對應表產生關聯的規則，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-141">In **Select Normalization Rules**, highlight the rules you want to associate with the dial plan and then click **OK**.</span></span>
    
      - <span data-ttu-id="4cbf4-142">若要定義新的正規化規則，並將它與撥號對應表產生關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-142">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="4cbf4-143">如需定義新規則的詳細資訊，請參閱[在 Lync Server 2013 中定義正常化規則](lync-server-2013-defining-normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-143">For details about defining a new rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="4cbf4-144">若要編輯已與撥號對應表相關聯的正規化規則，請反白顯示規則名稱，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-144">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span> <span data-ttu-id="4cbf4-145">如需編輯規則的詳細資訊，請參閱[在 Lync Server 2013 中定義正常化規則](lync-server-2013-defining-normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-145">For details about editing the rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="4cbf4-146">若要複製現有的正規化規則，以做為定義新規則的起點，請反白顯示規則名稱，然後按一下 [**複製**]，然後按一下 [**貼**上]。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-146">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="4cbf4-147">如需編輯複本的詳細資訊，請參閱[在 Lync Server 2013 中定義正常化規則](lync-server-2013-defining-normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-147">For details about editing the copy, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="4cbf4-148">若要從撥號對應表中移除正規化規則，請反白顯示規則名稱，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-148">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4cbf4-149">每個撥號對應表至少必須有一個相關聯的正常化規則。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-149">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="4cbf4-150">如需如何判斷撥號對應表所需之所有正規化規則的相關資訊，請參閱規劃檔中的<A href="lync-server-2013-dial-plans-and-normalization-rules.md">Lync Server 2013 中的撥號對應表和正常化規則</A>。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-150">For information about how to determine all of the normalization rules a dial plan requires, see <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

11. <span data-ttu-id="4cbf4-151">確認撥號對應表的正規化規則依正確的順序排列。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-151">Verify that the dial plan’s normalization rules are arranged in the correct order.</span></span> <span data-ttu-id="4cbf4-152">若要變更規則在清單中的位置，請反白顯示規則名稱，然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-152">To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4cbf4-153">Lync Server 會從左上部遍歷正規化規則清單，並使用符合撥號號碼的第一個規則。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-153">Lync Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="4cbf4-154">如果您設定撥號對應表，讓已撥號的號碼可以比對多個正規化規則，請確定限制性以上的規則排序的限制性較低。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-154">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span><BR><span data-ttu-id="4cbf4-155">預設<STRONG>保持所有</STRONG>正規化規則<STRONG>^ ( \d {11}) $</STRONG>符合任何11位數的數位。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-155">The default <STRONG>Keep All</STRONG> normalization rule <STRONG>^(\d{11})$</STRONG> matches any 11-digit number.</span></span> <span data-ttu-id="4cbf4-156">例如，如果您新增的正規化規則符合11位數的開始1425的數位，請確定 [<STRONG>全部保留</STRONG>] 的排序低於較嚴格的<STRONG>^ (1425 {7}) $</STRONG> rule。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-156">For example, if you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that <STRONG>Keep All</STRONG> is sorted below the more restrictive <STRONG>^(1425\d{7})$</STRONG> rule.</span></span>

    
    </div>

12. <span data-ttu-id="4cbf4-157"> (選用) 請輸入號碼以測試撥號對應表，然後按一下 [**移至**]。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-157">(Optional) Enter a number to test the dial plan and then click **Go**.</span></span> <span data-ttu-id="4cbf4-158">測試結果會顯示在 [**輸入要測試的號碼**] 底下。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-158">The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4cbf4-159">您可以儲存尚未通過測試的撥號對應表，然後再加以重新設定。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-159">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="4cbf4-160">如需詳細資訊，請參閱<A href="lync-server-2013-test-voice-routing.md">Test voice routing In Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-160">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

13. <span data-ttu-id="4cbf4-161">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-161">Click **OK**.</span></span>

14. <span data-ttu-id="4cbf4-162">在 [**撥號**對應表] 頁面上，按一下 [**認可**]，然後按一下 [**全部認可**]。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-162">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4cbf4-163">每當您建立撥號對應表時，都必須執行「<STRONG>認可全部</STRONG>」命令來發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-163">Any time you create a dial plan, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="4cbf4-164">如需詳細資訊，請參閱 Operations 檔中的在<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中發佈擱置的變更至語音路由</A>設定。</span><span class="sxs-lookup"><span data-stu-id="4cbf4-164">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4cbf4-165">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4cbf4-165">See Also</span></span>


[<span data-ttu-id="4cbf4-166">在 Lync Server 2013 中修改撥號對應表</span><span class="sxs-lookup"><span data-stu-id="4cbf4-166">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="4cbf4-167">在 Lync Server 2013 中將擱置的變更發佈至語音路由設定</span><span class="sxs-lookup"><span data-stu-id="4cbf4-167">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="4cbf4-168">在 Lync Server 2013 中定義正常化規則</span><span class="sxs-lookup"><span data-stu-id="4cbf4-168">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

