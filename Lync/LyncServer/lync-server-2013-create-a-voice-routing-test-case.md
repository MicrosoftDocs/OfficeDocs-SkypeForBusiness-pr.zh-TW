---
title: Lync Server 2013：建立語音路由測試案例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9fac6f65d1bb1c04b8d8597454df775f8545d2a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a><span data-ttu-id="b051d-102">在 Lync Server 2013 中建立語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="b051d-102">Create a voice routing test case in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b051d-103">_**主題上次修改日期：** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="b051d-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<div>

## <a name="to-create-a-test-case"></a><span data-ttu-id="b051d-104">建立測試案例</span><span class="sxs-lookup"><span data-stu-id="b051d-104">To create a test case</span></span>

1.  <span data-ttu-id="b051d-105">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="b051d-105">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="b051d-106">如需詳細資訊，請參閱[在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="b051d-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="b051d-107">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="b051d-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b051d-108">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="b051d-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b051d-109">在左側導覽列中，依序按一下 **[語音路由]** 和 **[測試語音路由]**。</span><span class="sxs-lookup"><span data-stu-id="b051d-109">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="b051d-110">在 **[測試語音路由]** 頁面上，按一下 **[新增]** 建立新的測試案例。</span><span class="sxs-lookup"><span data-stu-id="b051d-110">On the **Test Voice Routing** page, click **New** to create a new test case.</span></span>

5.  <span data-ttu-id="b051d-111">在 **[名稱]** 欄位中，輸入測試案例的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="b051d-111">In **Name**, type in a unique name for the test case.</span></span>
    
    <span data-ttu-id="b051d-112">在您的企業語音部署中，所有語音路由測試案例的名稱都必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="b051d-112">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="b051d-113">它的長度最多為32個字元，而且可以包含任何字母元字元，除了反斜線 (\\) 、句點 ( ) 或底線 (\_) 。</span><span class="sxs-lookup"><span data-stu-id="b051d-113">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>

6.  <span data-ttu-id="b051d-p104">在 **[要測試的撥號號碼]** 欄位中，輸入要用來測試您為此測試案例指定的路由設定的撥號號碼。根據撥號對應表、路由和語音原則，此號碼會正規化並顯示為輸出。</span><span class="sxs-lookup"><span data-stu-id="b051d-p104">In **Dialed number to test**, type in the dialed number that you want to use to test the routing configuration that you specify for this test case. Based on the dial plan, route, and voice policy, this number will be normalized and displayed as output.</span></span>

7.  <span data-ttu-id="b051d-p105">在 **[撥號對應表]** 清單中，選取執行測試時要使用的撥號對應表。預設是 [全域] 撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="b051d-p105">In the **Dial Plan** list, select the dial plan to use when running the test. Default is the Global dial plan.</span></span>

8.  <span data-ttu-id="b051d-p106">在 **[語音原則]** 清單中，選取執行測試時要使用的語音原則。預設是通用語音原則。</span><span class="sxs-lookup"><span data-stu-id="b051d-p106">In the **Voice Policy** list, select the voice policy to use when running the test. Default is the Global voice policy.</span></span>

9.  <span data-ttu-id="b051d-p107">在 **[預期的轉譯]** 欄位中，以您希望在轉譯後看到的格式輸入電話號碼。這是在將電話號碼由所選撥號對應表中第一個符合的正規化規則轉譯之後，您會測試的電話號碼值。當您執行測試案例時，如果您測試的號碼未產生 **[預期的轉譯]** 欄位中的值，表示測試失敗。</span><span class="sxs-lookup"><span data-stu-id="b051d-p107">In **Expected translation**, type in the phone number in the format you expect to see it after translation. This is the value of the phone number that you are testing after it has been translated by the first normalization rule that matches in the selected dial plan. When you run the test case, if the number you are testing does not result in the value in **Expected translation**, the test fails.</span></span>

10. <span data-ttu-id="b051d-p108">(選用) 在 **[預期的 PSTN 使用方式]** 清單中，您可以根據指定的撥號對應表和語音原則，選取您執行測試案例時預期使用的 PSTN 使用方式記錄。如果使用不同的 PSTN 使用方式記錄，測試會失敗。</span><span class="sxs-lookup"><span data-stu-id="b051d-p108">(Optional) In the **Expected PSTN usage** list, you can select the public switched telephone network (PSTN) usage record that you expect to be used when you run the test case, based on the specified dial plan and voice policy. If a different PSTN usage record is used, the test fails.</span></span>

11. <span data-ttu-id="b051d-p109">(選用) 在 **[預期的路由]** 清單中，您可以根據指定的撥號對應表和語音原則，選取您執行測試案例時預期使用的語音路由。如果使用不同的語音路由，測試會失敗。</span><span class="sxs-lookup"><span data-stu-id="b051d-p109">(Optional) In the **Expected route** list, you can select the voice route that you expect to be used when you run the test case, based on the specified dial plan and voice policy. If a different voice route is used, the test fails.</span></span>

12. <span data-ttu-id="b051d-p110">(選用) 按一下 **[執行]** 來執行測試案例。結果會顯示在頁面的右側面板中。</span><span class="sxs-lookup"><span data-stu-id="b051d-p110">(Optional) Click **Run** to run the test case. The results are shown in the right panel of the page.</span></span>

13. <span data-ttu-id="b051d-129">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b051d-129">Click **OK**.</span></span>

14. <span data-ttu-id="b051d-130">依序按一下 **[認可]** 和 **[全部認可]**。</span><span class="sxs-lookup"><span data-stu-id="b051d-130">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b051d-131">每當您建立語音路由測試案例時，您必須執行 <STRONG>[全部認可]</STRONG> 命令來發行組態變更。</span><span class="sxs-lookup"><span data-stu-id="b051d-131">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="b051d-132">如需詳細資訊，請參閱 Operations 檔中的在<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中發佈擱置的變更至語音路由</A>設定。</span><span class="sxs-lookup"><span data-stu-id="b051d-132">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="b051d-133">如果測試中所使用的撥號對應表會正規化以加號 (開頭的電話號碼（例如 + 12065551219) ），該方案可能會導致語音路由測試失敗。</span><span class="sxs-lookup"><span data-stu-id="b051d-133">If the dial plan being employed in the test normalizes phone numbers that begin with a plus sign (for example, +12065551219), that plan might cause the voice routing test to fail.</span></span> <span data-ttu-id="b051d-134"> (撥號對應表，且語音路由會正常運作;實際上，Test-CsDialPlan 會成功。</span><span class="sxs-lookup"><span data-stu-id="b051d-134">(The dial plan and the voice route will work; in fact, Test-CsDialPlan will succeed.</span></span> <span data-ttu-id="b051d-135">不過，語音路由測試可能會失敗。 ) 這是在測試語音路由時必須記住的事項。</span><span class="sxs-lookup"><span data-stu-id="b051d-135">However, the voice routing test might fail.) This is something to keep in mind when testing voice routes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b051d-136">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b051d-136">See Also</span></span>


[<span data-ttu-id="b051d-137">在 Lync Server 2013 中匯出語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="b051d-137">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="b051d-138">在 Lync Server 2013 中匯入語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="b051d-138">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="b051d-139">在 Lync Server 2013 中設定撥號對應表</span><span class="sxs-lookup"><span data-stu-id="b051d-139">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="b051d-140">在 Lync Server 2013 中設定語音原則、PSTN 使用方式記錄和語音路由</span><span class="sxs-lookup"><span data-stu-id="b051d-140">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

