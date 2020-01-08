---
title: Lync Server 2013：建立語音路由測試案例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a98e8b9400b0a268474429ad464b1aef7bbbe56
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a><span data-ttu-id="dc1da-102">在 Lync Server 2013 中建立語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="dc1da-102">Create a voice routing test case in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc1da-103">_**主題上次修改日期：** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="dc1da-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<div>

## <a name="to-create-a-test-case"></a><span data-ttu-id="dc1da-104">建立測試案例</span><span class="sxs-lookup"><span data-stu-id="dc1da-104">To create a test case</span></span>

1.  <span data-ttu-id="dc1da-105">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="dc1da-105">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="dc1da-106">如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="dc1da-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="dc1da-107">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="dc1da-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dc1da-108">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="dc1da-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dc1da-109">在左側導覽列中，按一下 [**語音路由**]，然後按一下 [**測試語音路由**]。</span><span class="sxs-lookup"><span data-stu-id="dc1da-109">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="dc1da-110">在 [**測試語音路由**] 頁面上，按一下 [**新增**] 以建立新的測試案例。</span><span class="sxs-lookup"><span data-stu-id="dc1da-110">On the **Test Voice Routing** page, click **New** to create a new test case.</span></span>

5.  <span data-ttu-id="dc1da-111">在 [**名稱**] 中，輸入測試案例的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="dc1da-111">In **Name**, type in a unique name for the test case.</span></span>
    
    <span data-ttu-id="dc1da-112">該名稱在企業語音部署中的所有語音路由測試案例中都必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="dc1da-112">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="dc1da-113">它最多可有32個字元，而且除了反斜線（\\）、句號（.）或底線（\_）之外，也可以包含任何字母數位字元。</span><span class="sxs-lookup"><span data-stu-id="dc1da-113">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>

6.  <span data-ttu-id="dc1da-114">在 [撥入的**號碼**] 中，輸入您要用來測試您針對此測試案例指定之路由設定的撥號號碼。</span><span class="sxs-lookup"><span data-stu-id="dc1da-114">In **Dialed number to test**, type in the dialed number that you want to use to test the routing configuration that you specify for this test case.</span></span> <span data-ttu-id="dc1da-115">根據撥號方案、路由及語音原則，這個數位將會正常化並顯示為輸出。</span><span class="sxs-lookup"><span data-stu-id="dc1da-115">Based on the dial plan, route, and voice policy, this number will be normalized and displayed as output.</span></span>

7.  <span data-ttu-id="dc1da-116">在**撥號計畫**清單中，選取執行測試時要使用的撥號計畫。</span><span class="sxs-lookup"><span data-stu-id="dc1da-116">In the **Dial Plan** list, select the dial plan to use when running the test.</span></span> <span data-ttu-id="dc1da-117">預設為全域撥號方案。</span><span class="sxs-lookup"><span data-stu-id="dc1da-117">Default is the Global dial plan.</span></span>

8.  <span data-ttu-id="dc1da-118">在 [**語音原則**] 清單中，選取執行測試時要使用的語音原則。</span><span class="sxs-lookup"><span data-stu-id="dc1da-118">In the **Voice Policy** list, select the voice policy to use when running the test.</span></span> <span data-ttu-id="dc1da-119">預設為全域語音原則。</span><span class="sxs-lookup"><span data-stu-id="dc1da-119">Default is the Global voice policy.</span></span>

9.  <span data-ttu-id="dc1da-120">在 [**預期翻譯**] 中，以您想要在翻譯後看到的格式輸入電話號碼。</span><span class="sxs-lookup"><span data-stu-id="dc1da-120">In **Expected translation**, type in the phone number in the format you expect to see it after translation.</span></span> <span data-ttu-id="dc1da-121">這是您在已選取的撥號方案中符合的第一個正常化規則所轉譯之後所測試之電話號碼的值。</span><span class="sxs-lookup"><span data-stu-id="dc1da-121">This is the value of the phone number that you are testing after it has been translated by the first normalization rule that matches in the selected dial plan.</span></span> <span data-ttu-id="dc1da-122">當您執行測試案例時，如果您要測試的數位不會產生**預期轉譯**中的值，測試就會失敗。</span><span class="sxs-lookup"><span data-stu-id="dc1da-122">When you run the test case, if the number you are testing does not result in the value in **Expected translation**, the test fails.</span></span>

10. <span data-ttu-id="dc1da-123">可選在 [**預期 PSTN 使用量**] 清單中，您可以根據指定的撥號方案和語音原則，選取您在執行測試案例時預期要使用的公用交換電話網絡（PSTN）使用記錄。</span><span class="sxs-lookup"><span data-stu-id="dc1da-123">(Optional) In the **Expected PSTN usage** list, you can select the public switched telephone network (PSTN) usage record that you expect to be used when you run the test case, based on the specified dial plan and voice policy.</span></span> <span data-ttu-id="dc1da-124">如果使用不同的 PSTN 使用記錄，測試就會失敗。</span><span class="sxs-lookup"><span data-stu-id="dc1da-124">If a different PSTN usage record is used, the test fails.</span></span>

11. <span data-ttu-id="dc1da-125">可選在 [**預期的路線**] 清單中，您可以根據指定的撥號方案和語音原則，選取您在執行測試案例時預期要使用的語音路線。</span><span class="sxs-lookup"><span data-stu-id="dc1da-125">(Optional) In the **Expected route** list, you can select the voice route that you expect to be used when you run the test case, based on the specified dial plan and voice policy.</span></span> <span data-ttu-id="dc1da-126">如果使用不同的語音路由，測試就會失敗。</span><span class="sxs-lookup"><span data-stu-id="dc1da-126">If a different voice route is used, the test fails.</span></span>

12. <span data-ttu-id="dc1da-127">可選按一下 [**執行**] 以執行測試案例。</span><span class="sxs-lookup"><span data-stu-id="dc1da-127">(Optional) Click **Run** to run the test case.</span></span> <span data-ttu-id="dc1da-128">結果會顯示在頁面的右側面板中。</span><span class="sxs-lookup"><span data-stu-id="dc1da-128">The results are shown in the right panel of the page.</span></span>

13. <span data-ttu-id="dc1da-129">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dc1da-129">Click **OK**.</span></span>

14. <span data-ttu-id="dc1da-130">按一下 [**認可**]，然後按一下 [**全部確認**]。</span><span class="sxs-lookup"><span data-stu-id="dc1da-130">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dc1da-131">每當您建立語音路由測試案例時，您都必須執行 [<STRONG>全部提交</STRONG>] 命令來發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="dc1da-131">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="dc1da-132">如需詳細資訊，請參閱在 Operations 檔中<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">發佈 Lync Server 2013 中的語音路由設定的未決變更</A>。</span><span class="sxs-lookup"><span data-stu-id="dc1da-132">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="dc1da-133">如果在測試中使用的撥號方案是正常化以加號（例如 + 12065551219）開頭的電話號碼，該方案可能會造成語音路由測試失敗。</span><span class="sxs-lookup"><span data-stu-id="dc1da-133">If the dial plan being employed in the test normalizes phone numbers that begin with a plus sign (for example, +12065551219), that plan might cause the voice routing test to fail.</span></span> <span data-ttu-id="dc1da-134">（撥號規劃和語音路由都可以運作; 事實上，測試 CsDialPlan 會成功。</span><span class="sxs-lookup"><span data-stu-id="dc1da-134">(The dial plan and the voice route will work; in fact, Test-CsDialPlan will succeed.</span></span> <span data-ttu-id="dc1da-135">不過，語音路由測試可能失敗。在測試語音路由時，請務必記住這一點。</span><span class="sxs-lookup"><span data-stu-id="dc1da-135">However, the voice routing test might fail.) This is something to keep in mind when testing voice routes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dc1da-136">請參閱</span><span class="sxs-lookup"><span data-stu-id="dc1da-136">See Also</span></span>


[<span data-ttu-id="dc1da-137">在 Lync Server 2013 中匯出語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="dc1da-137">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="dc1da-138">在 Lync Server 2013 中改善語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="dc1da-138">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="dc1da-139">在 Lync Server 2013 中設定撥號對應表</span><span class="sxs-lookup"><span data-stu-id="dc1da-139">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="dc1da-140">在 Lync Server 2013 中設定語音原則、PSTN 使用方式記錄及語音路由</span><span class="sxs-lookup"><span data-stu-id="dc1da-140">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

