---
title: Lync Server 2013：執行語音路由測試案例
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
ms.openlocfilehash: 14f2df8a04c5efbf8c62bc4e17bbdd156913daae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="8a316-102">在 Lync Server 2013 中執行語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="8a316-102">Run voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a316-103">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="8a316-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="8a316-104">您可以在語音路由測試案例套件中執行所有測試案例，或執行一或多個選取的測試案例。</span><span class="sxs-lookup"><span data-stu-id="8a316-104">You can run all of the test cases in your voice routing test case suite, or you can run one or more selected test cases.</span></span>

<div>

## <a name="to-run-all-voice-routing-test-cases"></a><span data-ttu-id="8a316-105">若要執行所有語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="8a316-105">To run all voice routing test cases</span></span>

1.  <span data-ttu-id="8a316-106">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="8a316-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="8a316-107">如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="8a316-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="8a316-108">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="8a316-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8a316-109">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="8a316-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8a316-110">在左側導覽列中，按一下 [**語音路由**]，然後按一下 [**測試語音路由**]。</span><span class="sxs-lookup"><span data-stu-id="8a316-110">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="8a316-111">在 [**測試語音路由**] 頁面上，按一下 [**動作**]，然後按一下 [**全部執行**]。</span><span class="sxs-lookup"><span data-stu-id="8a316-111">On the **Test Voice Routing** page, click **Action** and then click **Run all**.</span></span>
    
    <span data-ttu-id="8a316-112">每個測試案例的 [通過] 或 [失敗] 狀態會顯示在 [**通過/失敗**] 欄中。</span><span class="sxs-lookup"><span data-stu-id="8a316-112">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="8a316-113">如果測試案例還沒有執行，則 [**傳遞/失敗**] 欄中會顯示 [暫缺]。</span><span class="sxs-lookup"><span data-stu-id="8a316-113">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

5.  <span data-ttu-id="8a316-114">可選若要查看每個測試案例的詳細結果，請按兩下測試案例名稱。</span><span class="sxs-lookup"><span data-stu-id="8a316-114">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="8a316-115">結果會顯示在 [**編輯測試案例**] 頁面右側的陰影區域中：</span><span class="sxs-lookup"><span data-stu-id="8a316-115">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="8a316-116">**測試結果：** 測試案例執行的整體階段或失敗狀態。</span><span class="sxs-lookup"><span data-stu-id="8a316-116">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="8a316-117">**正常化規則：** 針對此測試案例選取的撥號計畫中的第一個正常化規則，符合撥號號碼（[**要測試的號碼**] 欄位中的值）。</span><span class="sxs-lookup"><span data-stu-id="8a316-117">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="8a316-118">已**正常化的數位：** 在正常化規則轉譯之後所撥號碼的值。</span><span class="sxs-lookup"><span data-stu-id="8a316-118">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="8a316-119">**第一個 PSTN 使用量：** 在針對此測試案例所選取的語音原則中，第一個與撥號號碼相符的公用交換電話網絡（PSTN）使用量記錄。</span><span class="sxs-lookup"><span data-stu-id="8a316-119">**First PSTN usage:** The first public switched telephone network (PSTN) usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="8a316-120">**第一個路線：** 第一個與撥號號碼相符的 PSTN 使用量記錄中的第一個語音路線。</span><span class="sxs-lookup"><span data-stu-id="8a316-120">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8a316-121">在語音路由測試案例設定中，<STRONG>預期的 PSTN 使用記錄</STRONG>和<STRONG>預期路由</STRONG>欄位是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="8a316-121">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="8a316-122">如果測試案例沒有指定這些值，測試結果中的對應欄位就會是空白的。</span><span class="sxs-lookup"><span data-stu-id="8a316-122">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a><span data-ttu-id="8a316-123">執行一或多個選取的語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="8a316-123">To run one or more selected voice routing test cases</span></span>

1.  <span data-ttu-id="8a316-124">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="8a316-124">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="8a316-125">如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="8a316-125">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="8a316-126">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="8a316-126">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8a316-127">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="8a316-127">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8a316-128">在左側導覽列中，按一下 [**語音路由**]，然後按一下 [**測試語音路由**]。</span><span class="sxs-lookup"><span data-stu-id="8a316-128">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="8a316-129">在 [**測試語音路由**] 頁面上，按一下您要執行的測試案例的名稱。</span><span class="sxs-lookup"><span data-stu-id="8a316-129">On the **Test Voice Routing** page, click the names of the test cases that you want to run.</span></span>

5.  <span data-ttu-id="8a316-130">在 [**動作**] 功能表上，按一下 [**執行選取**的]。</span><span class="sxs-lookup"><span data-stu-id="8a316-130">On the **Action** menu, click **Run selected**.</span></span>
    
    <span data-ttu-id="8a316-131">每個測試案例的 [通過] 或 [失敗] 狀態會顯示在 [**通過/失敗**] 欄中。</span><span class="sxs-lookup"><span data-stu-id="8a316-131">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="8a316-132">如果測試案例還沒有執行，則 [**傳遞/失敗**] 欄中會顯示 [暫缺]。</span><span class="sxs-lookup"><span data-stu-id="8a316-132">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

6.  <span data-ttu-id="8a316-133">可選若要查看每個測試案例的詳細結果，請按兩下測試案例名稱。</span><span class="sxs-lookup"><span data-stu-id="8a316-133">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="8a316-134">結果會顯示在 [**編輯測試案例**] 頁面右側的陰影區域中：</span><span class="sxs-lookup"><span data-stu-id="8a316-134">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="8a316-135">**測試結果：** 測試案例執行的整體階段或失敗狀態。</span><span class="sxs-lookup"><span data-stu-id="8a316-135">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="8a316-136">**正常化規則：** 針對此測試案例選取的撥號計畫中的第一個正常化規則，符合撥號號碼（[**要測試的號碼**] 欄位中的值）。</span><span class="sxs-lookup"><span data-stu-id="8a316-136">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="8a316-137">已**正常化的數位：** 在正常化規則轉譯之後所撥號碼的值。</span><span class="sxs-lookup"><span data-stu-id="8a316-137">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="8a316-138">**第一個 PSTN 使用量：** 針對此測試案例所選取的語音原則中，符合撥入號碼的第一個 PSTN 使用記錄。</span><span class="sxs-lookup"><span data-stu-id="8a316-138">**First PSTN usage:** The first PSTN usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="8a316-139">**第一個路線：** 第一個與撥號號碼相符的 PSTN 使用量記錄中的第一個語音路線。</span><span class="sxs-lookup"><span data-stu-id="8a316-139">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8a316-140">在語音路由測試案例設定中，<STRONG>預期的 PSTN 使用記錄</STRONG>和<STRONG>預期路由</STRONG>欄位是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="8a316-140">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="8a316-141">如果測試案例沒有指定這些值，測試結果中的對應欄位就會是空白的。</span><span class="sxs-lookup"><span data-stu-id="8a316-141">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8a316-142">請參閱</span><span class="sxs-lookup"><span data-stu-id="8a316-142">See Also</span></span>


[<span data-ttu-id="8a316-143">在 Lync Server 2013 中測試語音路由</span><span class="sxs-lookup"><span data-stu-id="8a316-143">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
[<span data-ttu-id="8a316-144">在 Lync Server 2013 中執行語音路由測試</span><span class="sxs-lookup"><span data-stu-id="8a316-144">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

