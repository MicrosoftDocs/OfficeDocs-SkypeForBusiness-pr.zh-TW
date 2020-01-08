---
title: Lync Server 2013：執行非正式的語音路由測試
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Run informal voice routing tests
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399049(v=OCS.15)
ms:contentKeyID: 48185904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b47394f595926fe37df9a0809380ed96fa1dec66
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a><span data-ttu-id="11942-102">在 Lync Server 2013 中執行非正式語音路由測試</span><span class="sxs-lookup"><span data-stu-id="11942-102">Run informal voice routing tests in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11942-103">_**主題上次修改日期：** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="11942-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="11942-104">您可以在建立實際測試案例前，使用 [**建立語音路由測試案例資訊**] 對話方塊來執行非正式測試。</span><span class="sxs-lookup"><span data-stu-id="11942-104">You can use the **Create voice routing test case information** dialog box to run informal tests before creating an actual test case.</span></span> <span data-ttu-id="11942-105">當您對測試結果感到滿意時，您可以選擇將它儲存為正式測試案例。</span><span class="sxs-lookup"><span data-stu-id="11942-105">When you are satisfied with the outcome of a test, you have the option of saving it as a formal test case.</span></span>

<div>

## <a name="to-run-an-informal-voice-routing-test"></a><span data-ttu-id="11942-106">執行非正式的語音路由測試</span><span class="sxs-lookup"><span data-stu-id="11942-106">To run an informal voice routing test</span></span>

1.  <span data-ttu-id="11942-107">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="11942-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="11942-108">如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="11942-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="11942-109">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="11942-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="11942-110">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="11942-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="11942-111">在左側導覽列中，按一下 [**語音路由**]，然後按一下 [**測試語音路由**]。</span><span class="sxs-lookup"><span data-stu-id="11942-111">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="11942-112">在 [**測試語音路由**] 頁面上，按一下 [**建立語音路由測試案例資訊**]。</span><span class="sxs-lookup"><span data-stu-id="11942-112">On the **Test Voice Routing** page, click **Create voice routing test case information**.</span></span>

5.  <span data-ttu-id="11942-113">在 [**撥入號碼**] 欄位中，輸入您要用於此測試的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="11942-113">In the **Dialed number** field, type in the phone number you want to use for this test.</span></span> <span data-ttu-id="11942-114">這個數位將會正常化並顯示在 [**結果**] 窗格的 [**正常化數位**] 欄位中。</span><span class="sxs-lookup"><span data-stu-id="11942-114">This number will be normalized and displayed in the **Normalized number** field of the **Results** pane.</span></span>

6.  <span data-ttu-id="11942-115">在**撥號計畫**清單中，選取要用來測試撥入號碼的撥號計畫。</span><span class="sxs-lookup"><span data-stu-id="11942-115">In the **Dial plan** list, select the dial plan to use for testing the dialed number.</span></span> <span data-ttu-id="11942-116">預設為全域撥號方案。</span><span class="sxs-lookup"><span data-stu-id="11942-116">Default is the Global dial plan.</span></span>
    
    <span data-ttu-id="11942-117">當您執行測試時，在 [**結果**] 窗格的 [**正常化規則**] 欄位中，會顯示符合撥號號碼的第一個正常化規則。</span><span class="sxs-lookup"><span data-stu-id="11942-117">When you run the test, the first normalization rule in this dial plan that matches the dialed number will be displayed in the **Normalization rule** field of the **Results** pane.</span></span>

7.  <span data-ttu-id="11942-118">在 [**語音原則**] 清單中，選取要用來測試撥入號碼的語音原則。</span><span class="sxs-lookup"><span data-stu-id="11942-118">In the **Voice Policy** list, select the voice policy to use for testing the dialed number.</span></span> <span data-ttu-id="11942-119">預設為全域語音原則。</span><span class="sxs-lookup"><span data-stu-id="11942-119">Default is the Global voice policy.</span></span>
    
    <span data-ttu-id="11942-120">當您執行測試時，此語音原則中的第一個相符 PSTN 使用記錄會顯示在 [**結果**] 窗格的**第一個 PSTN 使用**欄位中。</span><span class="sxs-lookup"><span data-stu-id="11942-120">When you run the test, the first matching PSTN usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane.</span></span> <span data-ttu-id="11942-121">此外，與此 PSTN 使用記錄相關的第一個相符的語音路由會顯示在**第一個路由**欄位中。</span><span class="sxs-lookup"><span data-stu-id="11942-121">Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

8.  <span data-ttu-id="11942-122">可選如果您想要針對指派給特定使用者的語音原則測試撥入號碼，請選取 [**填入使用者**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="11942-122">(Optional) Select the **Populate from user** check box if you want to test the dialed number against the voice policy assigned to a particular user.</span></span>
    
    1.  <span data-ttu-id="11942-123">按一下 **[流覽]** 以顯示 [**選取企業語音使用者**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="11942-123">Click **Browse** to display the **Select Enterprise Voice Users** dialog box.</span></span>
    
    2.  <span data-ttu-id="11942-124">按一下 [**尋找**]，顯示已啟用企業語音的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="11942-124">Click **Find** to display the list of users who are enabled for Enterprise Voice.</span></span>
    
    3.  <span data-ttu-id="11942-125">按兩下您想要用於此測試的使用者名稱，其指派的語音原則。</span><span class="sxs-lookup"><span data-stu-id="11942-125">Double-click the user name whose assigned voice policy you want to use for this test.</span></span> <span data-ttu-id="11942-126">**原則**欄位現在已填入指派給所選使用者的語音原則。</span><span class="sxs-lookup"><span data-stu-id="11942-126">The **Policy** field is now populated with the voice policy assigned to the selected user.</span></span>
    
    <span data-ttu-id="11942-127">當您執行測試時，此語音原則中的第一個相符公用電話網絡（PSTN）使用量記錄會顯示在 [**結果**] 窗格的**第一個 PSTN 使用**欄位中。</span><span class="sxs-lookup"><span data-stu-id="11942-127">When you run the test, the first matching public switched telephone network (PSTN) usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane.</span></span> <span data-ttu-id="11942-128">此外，與此 PSTN 使用記錄相關的第一個相符的語音路由會顯示在**第一個路由**欄位中。</span><span class="sxs-lookup"><span data-stu-id="11942-128">Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

9.  <span data-ttu-id="11942-129">按一下 [**執行**] 以執行測試案例。</span><span class="sxs-lookup"><span data-stu-id="11942-129">Click **Run** to run the test case.</span></span> <span data-ttu-id="11942-130">結果會顯示在對話方塊的右面板中。</span><span class="sxs-lookup"><span data-stu-id="11942-130">The results are shown in the right panel of the dialog box.</span></span>

10. <span data-ttu-id="11942-131">可選如果您想要將此測試設定儲存為正式測試案例，請按一下 [**另存**新格式]。</span><span class="sxs-lookup"><span data-stu-id="11942-131">(Optional) Click **Save as** if you want to save this test configuration as a formal test case.</span></span>
    
    1.  <span data-ttu-id="11942-132">在 [**儲存語音路由測試案例資訊**] 對話方塊的 [**名稱**] 欄位中，輸入測試案例的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="11942-132">In the **Name** field of the **Save Voice Routing Test Case Information** dialog box, type a unique name for the test case.</span></span>
        
        <span data-ttu-id="11942-133">該名稱在企業語音部署中的所有語音路由測試案例中都必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="11942-133">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="11942-134">它最多可有32個字元，而且除了反斜線（\\）、句號（.）或底線（\_）之外，也可以包含任何字母數位字元。</span><span class="sxs-lookup"><span data-stu-id="11942-134">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>
    
    2.  <span data-ttu-id="11942-135">請注意，[**儲存語音路由測試案例資訊**] 對話方塊上的剩餘欄位是唯讀的，且是從非正式測試設定*和*結果預填的。</span><span class="sxs-lookup"><span data-stu-id="11942-135">Note that the remaining fields on the **Save Voice Routing Test Case Information** dialog box are read-only, and are prepopulated from the informal test configuration *and* results.</span></span> <span data-ttu-id="11942-136">確認這是您要儲存在測試案例中的設定。</span><span class="sxs-lookup"><span data-stu-id="11942-136">Verify that this is the configuration that you want to save for the test case.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="11942-137">來自測試結果的值會用於在 [<STRONG>儲存語音路由測試案例資訊</STRONG>] 對話方塊上預填欄位，如下所示：</span><span class="sxs-lookup"><span data-stu-id="11942-137">Values from the test results are used to prepopulate fields on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box as follows:</span></span> 
        > <UL>
        > <LI>
        > <P><span data-ttu-id="11942-138">[<STRONG>預期的翻譯</STRONG>] 會預先填入 [<STRONG>正常化數位</STRONG>] 欄位中的值。</span><span class="sxs-lookup"><span data-stu-id="11942-138"><STRONG>Expected translation</STRONG> is prepopulated with the value in the <STRONG>Normalized number</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="11942-139">[<STRONG>預期的路線</STRONG>] 會預先填入<STRONG>第一個 [路線</STRONG>] 欄位中的值。</span><span class="sxs-lookup"><span data-stu-id="11942-139"><STRONG>Expected route</STRONG> is prepopulated with the value in the <STRONG>First route</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="11942-140"><STRONG>預期的 pstn 使用記錄</STRONG>已預先填入<STRONG>第一個 pstn 使用量</STRONG>欄位中的值。</span><span class="sxs-lookup"><span data-stu-id="11942-140"><STRONG>Expected PSTN usage record</STRONG> is prepopulated with the value in the <STRONG>First PSTN usage</STRONG> field.</span></span></P></LI></UL><span data-ttu-id="11942-141">如果在測試執行期間找不到這些值的相符，則 [<STRONG>儲存語音路由測試案例資訊</STRONG>] 對話方塊上的對應欄位會是空的。</span><span class="sxs-lookup"><span data-stu-id="11942-141">If matches for any of these values were not found during the test run, the corresponding field is empty on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box.</span></span>

        
        </div>
    
    3.  <span data-ttu-id="11942-142">按一下 **[確定]** 以儲存測試案例，或按一下 [**取消**] 以回到 [**查看語音路由測試案例資訊**] 對話方塊，在儲存前，進一步開發測試。</span><span class="sxs-lookup"><span data-stu-id="11942-142">Click **Ok** to save the test case, or click **Cancel** to return to return to the **View voice routing test case information** dialog box to further develop the test before saving it.</span></span>

11. <span data-ttu-id="11942-143">按一下 [**認可**]，然後按一下 [**全部確認**]。</span><span class="sxs-lookup"><span data-stu-id="11942-143">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="11942-144">每當您建立語音路由測試案例時，您都必須執行 [<STRONG>全部提交</STRONG>] 命令來發佈測試案例。</span><span class="sxs-lookup"><span data-stu-id="11942-144">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="11942-145">如需詳細資訊，請參閱在 Operations 檔中<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">發佈 Lync Server 2013 中的語音路由設定的未決變更</A>。</span><span class="sxs-lookup"><span data-stu-id="11942-145">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="11942-146">請參閱</span><span class="sxs-lookup"><span data-stu-id="11942-146">See Also</span></span>


[<span data-ttu-id="11942-147">在 Lync Server 2013 中建立語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="11942-147">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)  
[<span data-ttu-id="11942-148">在 Lync Server 2013 中執行語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="11942-148">Run voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-run-voice-routing-test-cases.md)  
[<span data-ttu-id="11942-149">在 Lync Server 2013 中匯出語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="11942-149">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="11942-150">在 Lync Server 2013 中改善語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="11942-150">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="11942-151">在 Lync Server 2013 中設定撥號對應表</span><span class="sxs-lookup"><span data-stu-id="11942-151">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="11942-152">在 Lync Server 2013 中設定語音原則、PSTN 使用方式記錄及語音路由</span><span class="sxs-lookup"><span data-stu-id="11942-152">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

