---
title: Lync Server 2013：執行非正式語音路由測試
description: Lync Server 2013：執行非正式語音路由測試。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run informal voice routing tests
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399049(v=OCS.15)
ms:contentKeyID: 48185904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6029be34f4e4e7b366cb73f56ca611b4773331fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545029"
---
# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a><span data-ttu-id="e86f7-103">在 Lync Server 2013 中執行非正式語音路由測試</span><span class="sxs-lookup"><span data-stu-id="e86f7-103">Run informal voice routing tests in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e86f7-104">_**主題上次修改日期：** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="e86f7-104">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="e86f7-105">您可以使用 [ **建立語音路由測試案例資訊** ] 對話方塊來執行非正式測試，然後再建立實際的測試案例。</span><span class="sxs-lookup"><span data-stu-id="e86f7-105">You can use the **Create voice routing test case information** dialog box to run informal tests before creating an actual test case.</span></span> <span data-ttu-id="e86f7-106">當您對測試結果滿意時，您可以選擇將其儲存為正式的測試案例。</span><span class="sxs-lookup"><span data-stu-id="e86f7-106">When you are satisfied with the outcome of a test, you have the option of saving it as a formal test case.</span></span>

<div>

## <a name="to-run-an-informal-voice-routing-test"></a><span data-ttu-id="e86f7-107">執行非正式語音路由測試</span><span class="sxs-lookup"><span data-stu-id="e86f7-107">To run an informal voice routing test</span></span>

1.  <span data-ttu-id="e86f7-108">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="e86f7-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="e86f7-109">如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="e86f7-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="e86f7-110">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="e86f7-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e86f7-111">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="e86f7-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e86f7-112">在左導覽列中，按一下 [ **語音路由**]，然後按一下 [ **測試語音路由**]。</span><span class="sxs-lookup"><span data-stu-id="e86f7-112">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="e86f7-113">在 [ **測試語音路由** ] 頁面上，按一下 [ **建立語音路由測試案例資訊**]。</span><span class="sxs-lookup"><span data-stu-id="e86f7-113">On the **Test Voice Routing** page, click **Create voice routing test case information**.</span></span>

5.  <span data-ttu-id="e86f7-114">在 [ **撥打號碼** ] 欄位中，輸入您要用於此測試的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="e86f7-114">In the **Dialed number** field, type in the phone number you want to use for this test.</span></span> <span data-ttu-id="e86f7-115">這個數目會正規化並顯示在 [**結果**] 窗格的 [**正規化數位**] 欄位中。</span><span class="sxs-lookup"><span data-stu-id="e86f7-115">This number will be normalized and displayed in the **Normalized number** field of the **Results** pane.</span></span>

6.  <span data-ttu-id="e86f7-116">在 [ **撥號** 對應表] 清單中，選取要用來測試撥號對應表的撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="e86f7-116">In the **Dial plan** list, select the dial plan to use for testing the dialed number.</span></span> <span data-ttu-id="e86f7-117">預設是 [全域] 撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="e86f7-117">Default is the Global dial plan.</span></span>
    
    <span data-ttu-id="e86f7-118">當您執行測試時，此撥號對應表中符合撥號號碼的第一個正規化規則會顯示在 [**結果**] 窗格的 [正規化**規則**] 欄位中。</span><span class="sxs-lookup"><span data-stu-id="e86f7-118">When you run the test, the first normalization rule in this dial plan that matches the dialed number will be displayed in the **Normalization rule** field of the **Results** pane.</span></span>

7.  <span data-ttu-id="e86f7-119">在 [ **語音原則** ] 清單中，選取用來測試撥號號碼的語音原則。</span><span class="sxs-lookup"><span data-stu-id="e86f7-119">In the **Voice Policy** list, select the voice policy to use for testing the dialed number.</span></span> <span data-ttu-id="e86f7-120">預設是通用語音原則。</span><span class="sxs-lookup"><span data-stu-id="e86f7-120">Default is the Global voice policy.</span></span>
    
    <span data-ttu-id="e86f7-121">當您執行測試時，這個語音原則中第一個相符的 PSTN 使用方式記錄會顯示在 [**結果**] 窗格的 [**第一個 PSTN 使用狀況**] 欄位中。</span><span class="sxs-lookup"><span data-stu-id="e86f7-121">When you run the test, the first matching PSTN usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane.</span></span> <span data-ttu-id="e86f7-122">此外，與此 PSTN 使用方式記錄相關聯的第一個相符語音路由會顯示在 **第一個路由** 欄位中。</span><span class="sxs-lookup"><span data-stu-id="e86f7-122">Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

8.  <span data-ttu-id="e86f7-123"> (選用) 若您想要依據指派給特定使用者的語音原則來測試撥號號碼，請選取 [ **從使用者填入** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e86f7-123">(Optional) Select the **Populate from user** check box if you want to test the dialed number against the voice policy assigned to a particular user.</span></span>
    
    1.  <span data-ttu-id="e86f7-124">按一下 **[流覽]** 以顯示 [ **選取企業語音使用者** ] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="e86f7-124">Click **Browse** to display the **Select Enterprise Voice Users** dialog box.</span></span>
    
    2.  <span data-ttu-id="e86f7-125">按一下 [ **尋找** ]，顯示已啟用 Enterprise Voice 之使用者的清單。</span><span class="sxs-lookup"><span data-stu-id="e86f7-125">Click **Find** to display the list of users who are enabled for Enterprise Voice.</span></span>
    
    3.  <span data-ttu-id="e86f7-126">按兩下您要用於此測試的指派語音原則的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="e86f7-126">Double-click the user name whose assigned voice policy you want to use for this test.</span></span> <span data-ttu-id="e86f7-127">[ **原則** ] 欄位現在會填入指派給選取之使用者的語音原則。</span><span class="sxs-lookup"><span data-stu-id="e86f7-127">The **Policy** field is now populated with the voice policy assigned to the selected user.</span></span>
    
    <span data-ttu-id="e86f7-128">當您執行測試時，這個語音原則中第一個相符的公用交換電話網路 (PSTN) 使用方式記錄會顯示在 [**結果**] 窗格的 [**第一個 PSTN 使用狀況**] 欄位中。</span><span class="sxs-lookup"><span data-stu-id="e86f7-128">When you run the test, the first matching public switched telephone network (PSTN) usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane.</span></span> <span data-ttu-id="e86f7-129">此外，與此 PSTN 使用方式記錄相關聯的第一個相符語音路由會顯示在 **第一個路由** 欄位中。</span><span class="sxs-lookup"><span data-stu-id="e86f7-129">Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

9.  <span data-ttu-id="e86f7-130">按一下 [ **執行** ] 以執行測試案例。</span><span class="sxs-lookup"><span data-stu-id="e86f7-130">Click **Run** to run the test case.</span></span> <span data-ttu-id="e86f7-131">結果會顯示在對話方塊的右窗格中。</span><span class="sxs-lookup"><span data-stu-id="e86f7-131">The results are shown in the right panel of the dialog box.</span></span>

10. <span data-ttu-id="e86f7-132"> (選用) 按一下 [ **另存** 新檔]，即可將此測試設定儲存為正式測試案例。</span><span class="sxs-lookup"><span data-stu-id="e86f7-132">(Optional) Click **Save as** if you want to save this test configuration as a formal test case.</span></span>
    
    1.  <span data-ttu-id="e86f7-133">在 [**儲存語音路由測試案例資訊**] 對話方塊的 [**名稱**] 欄位中，輸入測試案例的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="e86f7-133">In the **Name** field of the **Save Voice Routing Test Case Information** dialog box, type a unique name for the test case.</span></span>
        
        <span data-ttu-id="e86f7-134">在您的企業語音部署中，所有語音路由測試案例的名稱都必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="e86f7-134">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="e86f7-135">它的長度最多為32個字元，而且可以包含任何字母元字元，除了反斜線 (\\) 、句點 ( ) 或底線 (\_) 。</span><span class="sxs-lookup"><span data-stu-id="e86f7-135">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>
    
    2.  <span data-ttu-id="e86f7-136">請注意，[ **儲存語音路由測試案例資訊** ] 對話方塊中的其餘欄位是唯讀的，而且會從非正式測試設定 *和* 結果中預先填入。</span><span class="sxs-lookup"><span data-stu-id="e86f7-136">Note that the remaining fields on the **Save Voice Routing Test Case Information** dialog box are read-only, and are prepopulated from the informal test configuration *and* results.</span></span> <span data-ttu-id="e86f7-137">請確認這是您要為測試案例儲存的設定。</span><span class="sxs-lookup"><span data-stu-id="e86f7-137">Verify that this is the configuration that you want to save for the test case.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e86f7-138">測試結果中的值可用於預先填入 [ <STRONG>儲存語音路由測試案例資訊</STRONG> ] 對話方塊上的欄位，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e86f7-138">Values from the test results are used to prepopulate fields on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box as follows:</span></span> 
        > <UL>
        > <LI>
        > <P><span data-ttu-id="e86f7-139"><STRONG>預期的轉譯</STRONG> 會預先填入 [ <STRONG>正規化數位</STRONG> ] 欄位中的值。</span><span class="sxs-lookup"><span data-stu-id="e86f7-139"><STRONG>Expected translation</STRONG> is prepopulated with the value in the <STRONG>Normalized number</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="e86f7-140"><STRONG>預期的路由</STRONG> 會預先填入 <STRONG>第一個路由</STRONG> 欄位中的值。</span><span class="sxs-lookup"><span data-stu-id="e86f7-140"><STRONG>Expected route</STRONG> is prepopulated with the value in the <STRONG>First route</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="e86f7-141"><STRONG>預期的 pstn 使用方式記錄</STRONG> 已預先填入 <STRONG>第一個 PSTN 使用狀況</STRONG> 欄位中的值。</span><span class="sxs-lookup"><span data-stu-id="e86f7-141"><STRONG>Expected PSTN usage record</STRONG> is prepopulated with the value in the <STRONG>First PSTN usage</STRONG> field.</span></span></P></LI></UL><span data-ttu-id="e86f7-142">如果在測試執行期間找不到任何這些值的相符專案，則 [ <STRONG>儲存語音路由測試案例資訊</STRONG> ] 對話方塊上的對應欄位會是空的。</span><span class="sxs-lookup"><span data-stu-id="e86f7-142">If matches for any of these values were not found during the test run, the corresponding field is empty on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box.</span></span>

        
        </div>
    
    3.  <span data-ttu-id="e86f7-143">按一下 **[確定]** 儲存測試案例，或按一下 [ **取消** ] 回到 [ **查看語音路由測試案例資訊** ] 對話方塊，以在儲存之前進一步開發測試。</span><span class="sxs-lookup"><span data-stu-id="e86f7-143">Click **Ok** to save the test case, or click **Cancel** to return to return to the **View voice routing test case information** dialog box to further develop the test before saving it.</span></span>

11. <span data-ttu-id="e86f7-144">依序按一下 **[認可]** 和 **[全部認可]**。</span><span class="sxs-lookup"><span data-stu-id="e86f7-144">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e86f7-145">每當您建立語音路由測試案例時，都必須執行「 <STRONG>認可所有</STRONG> 」命令來發佈測試案例。</span><span class="sxs-lookup"><span data-stu-id="e86f7-145">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="e86f7-146">如需詳細資訊，請參閱 Operations 檔中的在 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中發佈擱置的變更至語音路由</A> 設定。</span><span class="sxs-lookup"><span data-stu-id="e86f7-146">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e86f7-147">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e86f7-147">See Also</span></span>


[<span data-ttu-id="e86f7-148">在 Lync Server 2013 中建立語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="e86f7-148">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)  
[<span data-ttu-id="e86f7-149">在 Lync Server 2013 中執行語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="e86f7-149">Run voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-run-voice-routing-test-cases.md)  
[<span data-ttu-id="e86f7-150">在 Lync Server 2013 中匯出語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="e86f7-150">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="e86f7-151">在 Lync Server 2013 中匯入語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="e86f7-151">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="e86f7-152">在 Lync Server 2013 中設定撥號對應表</span><span class="sxs-lookup"><span data-stu-id="e86f7-152">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="e86f7-153">在 Lync Server 2013 中設定語音原則、PSTN 使用方式記錄和語音路由</span><span class="sxs-lookup"><span data-stu-id="e86f7-153">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

