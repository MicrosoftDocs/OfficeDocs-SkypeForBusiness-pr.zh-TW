---
title: Lync Server 2013：執行語音路由測試案例
description: Lync Server 2013：執行語音路由測試案例。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run voice routing test cases
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413068(v=OCS.15)
ms:contentKeyID: 48185948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e521216a12fba6b78913e7f4a79432809bb6e252
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566789"
---
# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="061a6-103">在 Lync Server 2013 中執行語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="061a6-103">Run voice routing test cases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="061a6-104">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="061a6-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="061a6-105">您可以執行語音路由測試案例套件中的所有測試案例，也可以執行一個或多個選取的測試案例。</span><span class="sxs-lookup"><span data-stu-id="061a6-105">You can run all of the test cases in your voice routing test case suite, or you can run one or more selected test cases.</span></span>

<div>

## <a name="to-run-all-voice-routing-test-cases"></a><span data-ttu-id="061a6-106">若要執行所有語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="061a6-106">To run all voice routing test cases</span></span>

1.  <span data-ttu-id="061a6-107">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="061a6-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="061a6-108">如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="061a6-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="061a6-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="061a6-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="061a6-110">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="061a6-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="061a6-111">在左側導覽列中，依序按一下 **[語音路由]** 和 **[測試語音路由]**。</span><span class="sxs-lookup"><span data-stu-id="061a6-111">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="061a6-112">在 [ **測試語音路由** ] 頁面上，按一下 [ **動作** ]，然後按一下 [ **全部執行**]。</span><span class="sxs-lookup"><span data-stu-id="061a6-112">On the **Test Voice Routing** page, click **Action** and then click **Run all**.</span></span>
    
    <span data-ttu-id="061a6-113">每個測試案例的 [通過] 或 [失敗] 狀態會顯示在 [ **通過/失敗** ] 欄中。</span><span class="sxs-lookup"><span data-stu-id="061a6-113">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="061a6-114">如果測試案例尚未執行，N/A 會顯示在 [ **通過/失敗** ] 欄中。</span><span class="sxs-lookup"><span data-stu-id="061a6-114">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

5.  <span data-ttu-id="061a6-115"> (選用) 若要查看每個測試案例的詳細結果，請按兩下測試案例名稱。</span><span class="sxs-lookup"><span data-stu-id="061a6-115">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="061a6-116">結果會顯示在 [ **編輯測試案例** ] 頁面右邊的陰影區域中：</span><span class="sxs-lookup"><span data-stu-id="061a6-116">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="061a6-117">**測試結果：** 測試案例執行的整體通過或失敗狀態。</span><span class="sxs-lookup"><span data-stu-id="061a6-117">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="061a6-118">正規化**規則：** 為此測試案例選取的撥號對應表中符合撥號號碼的第一個正規化規則 (數值**to test** field) 。</span><span class="sxs-lookup"><span data-stu-id="061a6-118">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="061a6-119">**正規化數目：** 正規化規則轉譯之後的撥號號碼值。</span><span class="sxs-lookup"><span data-stu-id="061a6-119">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="061a6-120">**第一個 PSTN 使用方式：** 為此測試案例選取的語音原則中，第一部公用交換電話網路 (PSTN) 使用方式記錄符合撥號號碼。</span><span class="sxs-lookup"><span data-stu-id="061a6-120">**First PSTN usage:** The first public switched telephone network (PSTN) usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="061a6-121">**第一個路由：** 第一個 PSTN 使用方式記錄中符合撥號號碼的第一個語音路由。</span><span class="sxs-lookup"><span data-stu-id="061a6-121">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="061a6-122"><STRONG>預期的 PSTN 使用方式記錄</STRONG>和<STRONG>預期路由</STRONG>欄位在語音路由測試案例設定中是選用的。</span><span class="sxs-lookup"><span data-stu-id="061a6-122">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="061a6-123">如果測試案例未指定這些值，測試結果中的對應欄位將會是空的。</span><span class="sxs-lookup"><span data-stu-id="061a6-123">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a><span data-ttu-id="061a6-124">若要執行一或多個選取的語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="061a6-124">To run one or more selected voice routing test cases</span></span>

1.  <span data-ttu-id="061a6-125">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="061a6-125">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="061a6-126">如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="061a6-126">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="061a6-127">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="061a6-127">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="061a6-128">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="061a6-128">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="061a6-129">在左導覽列中，按一下 [ **語音路由**]，然後按一下 [ **測試語音路由**]。</span><span class="sxs-lookup"><span data-stu-id="061a6-129">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="061a6-130">在 [ **測試語音路由** ] 頁面上，按一下您要執行的測試案例名稱。</span><span class="sxs-lookup"><span data-stu-id="061a6-130">On the **Test Voice Routing** page, click the names of the test cases that you want to run.</span></span>

5.  <span data-ttu-id="061a6-131">在 [ **動作** ] 功能表上，按一下 [ **執行選取**的]。</span><span class="sxs-lookup"><span data-stu-id="061a6-131">On the **Action** menu, click **Run selected**.</span></span>
    
    <span data-ttu-id="061a6-132">每個測試案例的 [通過] 或 [失敗] 狀態會顯示在 [ **通過/失敗** ] 欄中。</span><span class="sxs-lookup"><span data-stu-id="061a6-132">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="061a6-133">如果測試案例尚未執行，N/A 會顯示在 [ **通過/失敗** ] 欄中。</span><span class="sxs-lookup"><span data-stu-id="061a6-133">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

6.  <span data-ttu-id="061a6-134"> (選用) 若要查看每個測試案例的詳細結果，請按兩下測試案例名稱。</span><span class="sxs-lookup"><span data-stu-id="061a6-134">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="061a6-135">結果會顯示在 [ **編輯測試案例** ] 頁面右邊的陰影區域中：</span><span class="sxs-lookup"><span data-stu-id="061a6-135">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="061a6-136">**測試結果：** 測試案例執行的整體通過或失敗狀態。</span><span class="sxs-lookup"><span data-stu-id="061a6-136">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="061a6-137">正規化**規則：** 為此測試案例選取的撥號對應表中符合撥號號碼的第一個正規化規則 (數值**to test** field) 。</span><span class="sxs-lookup"><span data-stu-id="061a6-137">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="061a6-138">**正規化數目：** 正規化規則轉譯之後的撥號號碼值。</span><span class="sxs-lookup"><span data-stu-id="061a6-138">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="061a6-139">**第一個 PSTN 使用方式：** 為此測試案例選取的語音原則中符合撥號號碼的第一個 PSTN 使用方式記錄。</span><span class="sxs-lookup"><span data-stu-id="061a6-139">**First PSTN usage:** The first PSTN usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="061a6-140">**第一個路由：** 第一個 PSTN 使用方式記錄中符合撥號號碼的第一個語音路由。</span><span class="sxs-lookup"><span data-stu-id="061a6-140">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="061a6-141"><STRONG>預期的 PSTN 使用方式記錄</STRONG>和<STRONG>預期路由</STRONG>欄位在語音路由測試案例設定中是選用的。</span><span class="sxs-lookup"><span data-stu-id="061a6-141">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="061a6-142">如果測試案例未指定這些值，測試結果中的對應欄位將會是空的。</span><span class="sxs-lookup"><span data-stu-id="061a6-142">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="061a6-143">另請參閱</span><span class="sxs-lookup"><span data-stu-id="061a6-143">See Also</span></span>


[<span data-ttu-id="061a6-144">在 Lync Server 2013 中測試語音路由</span><span class="sxs-lookup"><span data-stu-id="061a6-144">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
[<span data-ttu-id="061a6-145">在 Lync Server 2013 中執行語音路由測試</span><span class="sxs-lookup"><span data-stu-id="061a6-145">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

