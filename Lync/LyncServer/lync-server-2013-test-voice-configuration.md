---
title: Lync Server 2013： 測試語音組態
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725208(v=OCS.15)
ms:contentKeyID: 63969605
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3bd2e9b86ee0c14d8fd9e2bbe386d48398d2418
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-voice-configuration-in-lync-server-2013"></a><span data-ttu-id="e7fcd-102">Lync Server 2013 中的測試語音組態</span><span class="sxs-lookup"><span data-stu-id="e7fcd-102">Test voice configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7fcd-103">_**上次修改主題：** 2014年-05-20 個_</span><span class="sxs-lookup"><span data-stu-id="e7fcd-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e7fcd-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="e7fcd-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e7fcd-105">每月</span><span class="sxs-lookup"><span data-stu-id="e7fcd-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7fcd-106">測試工具</span><span class="sxs-lookup"><span data-stu-id="e7fcd-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e7fcd-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7fcd-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7fcd-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="e7fcd-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e7fcd-109">當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="e7fcd-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e7fcd-110">當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有可執行此測試 Test-csvoicetestconfiguration cmdlet 的權限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="e7fcd-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceTestConfiguration cmdlet.</span></span> <span data-ttu-id="e7fcd-111">若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e7fcd-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e7fcd-112">說明</span><span class="sxs-lookup"><span data-stu-id="e7fcd-112">Description</span></span>

<span data-ttu-id="e7fcd-113">Lync Server 包含數個 Windows PowerShell cmdlet （如測試 CsVoiceRoute 和測試 CsVoicePolicy、 測試 Test-cstrunkconfiguration），可讓您確認 Enterprise Voice 基礎結構 – 語音路由、 語音個別原則，SIP 主幹 – 如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="e7fcd-113">Lync Server includes several Windows PowerShell cmdlets (such as Test-CsVoiceRoute and Test-CsVoicePolicy, Test-CsTrunkConfiguration) that enable you to verify that the individual pieces of your Enterprise Voice infrastructure – voice routes, voice policies, SIP trunks – are working as expected.</span></span>

<span data-ttu-id="e7fcd-114">時請務必與所有的個別工作的企業語音： 很可能具有有效的語音路由、 有效的語音原則，以及有效的 SIP 主幹，但仍有使用者無法撥打或接聽電話。</span><span class="sxs-lookup"><span data-stu-id="e7fcd-114">While it’s important with Enterprise Voice that all the individual pieces work: it’s possible to have a valid voice route, a valid voice policy, and a valid SIP trunk, but still have users unable to make or receive phone calls.</span></span> <span data-ttu-id="e7fcd-115">因此，Lync Server 也會提供建立語音測試組態的能力。</span><span class="sxs-lookup"><span data-stu-id="e7fcd-115">Because of that, Lync Server also provides the ability to create voice test configurations.</span></span> <span data-ttu-id="e7fcd-116">語音測試組態代表 Enterprise Voice 的常見案例： 您可以為語音路由、 語音原則和撥號對應表，指定下列項目，然後驗證這些個別項目是否能夠一起運作，以提供電話服務的工作。</span><span class="sxs-lookup"><span data-stu-id="e7fcd-116">Voice test configurations represent common Enterprise Voice scenarios: you can specify such things as a voice route, a voice policy, and a dial plan, and then verify that those individual items are work able to work together to provide phone service.</span></span> <span data-ttu-id="e7fcd-117">此外，您可以驗證在指定的案例中您預期。</span><span class="sxs-lookup"><span data-stu-id="e7fcd-117">In addition, you can validate your expectations in a given scenario.</span></span> <span data-ttu-id="e7fcd-118">例如，假設您所預期的撥號對應表 A 和 B 的語音原則組合會導致來電路由傳送透過語音路由 c。您可以輸入語音路由 C 作為 ExpectedRoute。</span><span class="sxs-lookup"><span data-stu-id="e7fcd-118">For example, suppose that you expect that the combination of dial plan A and voice policy B would result in calls being routed over voice route C. You can enter voice route C as the ExpectedRoute.</span></span> <span data-ttu-id="e7fcd-119">當您執行測試，如果語音路由 C 不採用然後測試會被標示為具有失敗。</span><span class="sxs-lookup"><span data-stu-id="e7fcd-119">When you run the test, if voice route C is not employed then the test will be marked as having failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e7fcd-120">執行測試</span><span class="sxs-lookup"><span data-stu-id="e7fcd-120">Running the test</span></span>

<span data-ttu-id="e7fcd-121">之前測試使用 Windows PowerShell 的語音組態集合，您必須先使用 Get-Test-csvoicetestconfiguration cmdlet 來擷取這些組態設定執行個體。</span><span class="sxs-lookup"><span data-stu-id="e7fcd-121">Before testing Voice configuration collections using Windows PowerShell, you must first use the Get-CsVoiceTestConfiguration cmdlet to retrieve an instance of these configuration settings.</span></span> <span data-ttu-id="e7fcd-122">該執行個體必須接著會以管線傳輸至測試 Test-csvoicetestconfiguration。</span><span class="sxs-lookup"><span data-stu-id="e7fcd-122">That instance must then be piped to the Test-CsVoiceTestConfiguration.</span></span> <span data-ttu-id="e7fcd-123">例如：</span><span class="sxs-lookup"><span data-stu-id="e7fcd-123">For example:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="e7fcd-124">若要在同一時間驗證所有語音測試組態設定，請改為使用此命令：</span><span class="sxs-lookup"><span data-stu-id="e7fcd-124">To validate all the voice test configuration settings at the same time, use this command instead:</span></span>

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

<span data-ttu-id="e7fcd-125">如需詳細資訊，請參閱 < 測試 Test-csvoicetestconfiguration cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="e7fcd-125">For more information, see the Help documentation for the Test-CsVoiceTestConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e7fcd-126">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="e7fcd-126">Determining success or failure</span></span>

<span data-ttu-id="e7fcd-127">測試 Test-csvoicetestconfiguration cmdlet 會報告測試失敗，或已成功完成，並提供每個成功的測試，例如轉譯規則、 語音路由]，以及用來完成工作的 PSTN 使用方式相關的其他資訊：</span><span class="sxs-lookup"><span data-stu-id="e7fcd-127">The Test-CsVoiceTestConfiguration cmdlet reports whether a test failed or succeeded, and provides additional information about each successful test, such as the translation rule, voice route, and PSTN usage used to complete the task:</span></span>

<span data-ttu-id="e7fcd-128">結果： 成功</span><span class="sxs-lookup"><span data-stu-id="e7fcd-128">Result:             Success</span></span>

<span data-ttu-id="e7fcd-129">TranslatedNumber: +15551234</span><span class="sxs-lookup"><span data-stu-id="e7fcd-129">TranslatedNumber:   +15551234</span></span>

<span data-ttu-id="e7fcd-130">MatchingRule: Description =;圖樣 = ^ (\\d{4}) $;翻譯 = + 1\\d;名稱 = 測試; IsInternalExtension = False</span><span class="sxs-lookup"><span data-stu-id="e7fcd-130">MatchingRule:       Description=;Pattern=^(\\d{4})$;Translation=+1\\d;Name=Test;IsInternalExtension=False</span></span>

<span data-ttu-id="e7fcd-131">FirstMatchingRoute： 為 site: Redmond</span><span class="sxs-lookup"><span data-stu-id="e7fcd-131">FirstMatchingRoute: site:Redmond</span></span>

<span data-ttu-id="e7fcd-132">MatchingUsage： 本機</span><span class="sxs-lookup"><span data-stu-id="e7fcd-132">MatchingUsage:      Local</span></span>

<span data-ttu-id="e7fcd-133">如果測試失敗結果是會回報為失敗：</span><span class="sxs-lookup"><span data-stu-id="e7fcd-133">If the test fails then the result is reported as Fail:</span></span>

<span data-ttu-id="e7fcd-134">結果： 失敗</span><span class="sxs-lookup"><span data-stu-id="e7fcd-134">Result:             Fail</span></span>

<span data-ttu-id="e7fcd-135">TranslatedNumber:</span><span class="sxs-lookup"><span data-stu-id="e7fcd-135">TranslatedNumber:</span></span>   

<span data-ttu-id="e7fcd-136">FirstMatchingRoute:</span><span class="sxs-lookup"><span data-stu-id="e7fcd-136">FirstMatchingRoute:</span></span>

<span data-ttu-id="e7fcd-137">MatchingUsage:</span><span class="sxs-lookup"><span data-stu-id="e7fcd-137">MatchingUsage:</span></span>      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e7fcd-138">測試可能有為何失敗的原因</span><span class="sxs-lookup"><span data-stu-id="e7fcd-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="e7fcd-139">因為語音測試組態測試測試數個不同的項目 – 包括語音原則、 撥號對應表計劃、 語音路由、 等等 – 有幾個不同的因素，可能會導致測試失敗。</span><span class="sxs-lookup"><span data-stu-id="e7fcd-139">Because voice test configuration testing tests several different items – including voice policies, dial plans, voice routes, and so on – there are several different factors that could result in a failed test.</span></span> <span data-ttu-id="e7fcd-140">如果測試失敗，您必須先應該使用 Get-Test-csvoicetestconfiguration cmdlet 來檢閱本身的組態設定：</span><span class="sxs-lookup"><span data-stu-id="e7fcd-140">If a test fails, your first step should be to review the configuration settings themselves by using the Get-CsVoiceTestConfiguration cmdlet:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

<span data-ttu-id="e7fcd-141">如果設定正確，重新執行測試時包括 Verbose 參數：</span><span class="sxs-lookup"><span data-stu-id="e7fcd-141">If the settings seem to be configured correctly, re-run the test while including the Verbose parameter:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="e7fcd-142">Verbose 參數會提供每個所採取的動作測試 Test-csvoicetestconfiguration 在這個範例所示的逐步帳戶：</span><span class="sxs-lookup"><span data-stu-id="e7fcd-142">The Verbose parameter will provide a step-by-step account of each action taken by Test-CsVoiceTestConfiguration as shown in this example:</span></span>

<span data-ttu-id="e7fcd-143">VERBOSE： 載入撥號對應表:"Global"</span><span class="sxs-lookup"><span data-stu-id="e7fcd-143">VERBOSE: Loading dial plan: "Global"</span></span>

<span data-ttu-id="e7fcd-144">VERBOSE： 載入語音原則: 「 RedmondDialPlan 」</span><span class="sxs-lookup"><span data-stu-id="e7fcd-144">VERBOSE: Loading voice policy: "RedmondDialPlan"</span></span>

<span data-ttu-id="e7fcd-145">此逐步帳戶可能會提供測試實際失敗的有用線索。</span><span class="sxs-lookup"><span data-stu-id="e7fcd-145">This step-by-step account might provide a useful clue as to where the test actually failed.</span></span> <span data-ttu-id="e7fcd-146">如果沒有，您可以再使用其他的 Windows PowerShell cmdlet （如測試 CsVoicePolicy)，並有條不紊開始驗證個別元件所隨附的語音測試組態設定。</span><span class="sxs-lookup"><span data-stu-id="e7fcd-146">If not, you can then use other Windows PowerShell cmdlets (such as Test-CsVoicePolicy) and methodically begin to verify the individual components that are included in the voice test configuration settings.</span></span>

<span data-ttu-id="e7fcd-147">所，請注意，它可能會用於測試，若要能夠將通話路由傳送並仍尚未被標示為失敗;如果 ExpectedRoute、 ExpectedTranslatedNumber，及 ExpectedUsage，輸入值，並不符合任何這些期望，可能發生的項目。</span><span class="sxs-lookup"><span data-stu-id="e7fcd-147">In addition to that, be aware that it’s possible for a test to be able to route a call and yet still be marked as a failure; that can occur if you enter values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage, and any of those expectations are not met.</span></span> <span data-ttu-id="e7fcd-148">例如，假設為您預期的語音路由] 中，輸入語音路由 C，但測試實際完成的呼叫中使用語音路由 d。在此情況下測試將會被標示為 「 失敗因為不使用預期的語音路由。</span><span class="sxs-lookup"><span data-stu-id="e7fcd-148">For example, suppose that you enter voice route C as your expected voice route, but the test actually completes the call using voice route D. In that case the test will be marked as Failed because the expected voice route was not used.</span></span> <span data-ttu-id="e7fcd-149">如果測試失敗，您可能 ExpectedRoute、 ExpectedTranslatedNumber，及 ExpectedUsage 移除值，然後再重新執行測試。</span><span class="sxs-lookup"><span data-stu-id="e7fcd-149">If a test fails, you might remove the values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage and then re-run the test.</span></span> <span data-ttu-id="e7fcd-150">可協助您決定是否失敗是因為無法完成電話，或是您預期一件事，以及實際接收到另一個。</span><span class="sxs-lookup"><span data-stu-id="e7fcd-150">That will help you determine whether the failure was because the call couldn't be completed, or because you expect one thing and actually received another.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e7fcd-151">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e7fcd-151">See Also</span></span>


[<span data-ttu-id="e7fcd-152">測試 Test-csvoicetestconfiguration</span><span class="sxs-lookup"><span data-stu-id="e7fcd-152">Test-CsVoiceTestConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

