---
title: Lync Server 2013：測試語音設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725208(v=OCS.15)
ms:contentKeyID: 63969605
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbe9be7e0f7962bbab546822e7ce6cd47e063540
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-configuration-in-lync-server-2013"></a><span data-ttu-id="92b7c-102">在 Lync Server 2013 中測試語音設定</span><span class="sxs-lookup"><span data-stu-id="92b7c-102">Test voice configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92b7c-103">_**主題上次修改日期：** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="92b7c-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92b7c-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="92b7c-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="92b7c-105">次</span><span class="sxs-lookup"><span data-stu-id="92b7c-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92b7c-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="92b7c-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="92b7c-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="92b7c-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92b7c-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="92b7c-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="92b7c-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="92b7c-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="92b7c-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsVoiceTestConfiguration Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="92b7c-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceTestConfiguration cmdlet.</span></span> <span data-ttu-id="92b7c-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="92b7c-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="92b7c-112">描述</span><span class="sxs-lookup"><span data-stu-id="92b7c-112">Description</span></span>

<span data-ttu-id="92b7c-113">Lync Server 包含數個 Windows PowerShell Cmdlet （例如 Test CsVoiceRoute 和 Test CsVoicePolicy、Test New-cstrunkconfiguration），可讓您驗證企業語音結構的個別元件-語音路線、語音原則，SIP trunks –如期運作。</span><span class="sxs-lookup"><span data-stu-id="92b7c-113">Lync Server includes several Windows PowerShell cmdlets (such as Test-CsVoiceRoute and Test-CsVoicePolicy, Test-CsTrunkConfiguration) that enable you to verify that the individual pieces of your Enterprise Voice infrastructure – voice routes, voice policies, SIP trunks – are working as expected.</span></span>

<span data-ttu-id="92b7c-114">雖然所有個別元件都能正常運作，但在企業語音都能起作用：您可以使用有效的語音路線、有效的語音原則，以及有效的 SIP 幹線，但仍有使用者無法撥打或接聽電話。</span><span class="sxs-lookup"><span data-stu-id="92b7c-114">While it’s important with Enterprise Voice that all the individual pieces work: it’s possible to have a valid voice route, a valid voice policy, and a valid SIP trunk, but still have users unable to make or receive phone calls.</span></span> <span data-ttu-id="92b7c-115">因此，Lync Server 也提供建立語音測試設定的功能。</span><span class="sxs-lookup"><span data-stu-id="92b7c-115">Because of that, Lync Server also provides the ability to create voice test configurations.</span></span> <span data-ttu-id="92b7c-116">語音測試設定代表常見的企業語音案例：您可以指定語音路線、語音原則和撥號方案等專案，然後確認這些個別專案能共同作業以提供電話語音。</span><span class="sxs-lookup"><span data-stu-id="92b7c-116">Voice test configurations represent common Enterprise Voice scenarios: you can specify such things as a voice route, a voice policy, and a dial plan, and then verify that those individual items are work able to work together to provide phone service.</span></span> <span data-ttu-id="92b7c-117">此外，您也可以在指定案例中驗證您的預期。</span><span class="sxs-lookup"><span data-stu-id="92b7c-117">In addition, you can validate your expectations in a given scenario.</span></span> <span data-ttu-id="92b7c-118">例如，假設您預計 [撥入方案 A] 和 [語音原則 B] 的組合會導致呼叫以語音路由 C 路由。您可以輸入語音路由 C 做為 ExpectedRoute。</span><span class="sxs-lookup"><span data-stu-id="92b7c-118">For example, suppose that you expect that the combination of dial plan A and voice policy B would result in calls being routed over voice route C. You can enter voice route C as the ExpectedRoute.</span></span> <span data-ttu-id="92b7c-119">當您執行測試時，如果沒有使用語音路由 C，則測試將會標示為失敗。</span><span class="sxs-lookup"><span data-stu-id="92b7c-119">When you run the test, if voice route C is not employed then the test will be marked as having failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="92b7c-120">執行測試</span><span class="sxs-lookup"><span data-stu-id="92b7c-120">Running the test</span></span>

<span data-ttu-id="92b7c-121">在使用 Windows PowerShell 測試語音組態集合之前，您必須先使用 CsVoiceTestConfiguration Cmdlet 來檢索這些設定設定的實例。</span><span class="sxs-lookup"><span data-stu-id="92b7c-121">Before testing Voice configuration collections using Windows PowerShell, you must first use the Get-CsVoiceTestConfiguration cmdlet to retrieve an instance of these configuration settings.</span></span> <span data-ttu-id="92b7c-122">該實例必須接著以管道傳送到測試 CsVoiceTestConfiguration。</span><span class="sxs-lookup"><span data-stu-id="92b7c-122">That instance must then be piped to the Test-CsVoiceTestConfiguration.</span></span> <span data-ttu-id="92b7c-123">例如：</span><span class="sxs-lookup"><span data-stu-id="92b7c-123">For example:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="92b7c-124">若要同時驗證所有的語音測試設定，請改為使用此命令：</span><span class="sxs-lookup"><span data-stu-id="92b7c-124">To validate all the voice test configuration settings at the same time, use this command instead:</span></span>

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

<span data-ttu-id="92b7c-125">如需詳細資訊，請參閱 Test CsVoiceTestConfiguration Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="92b7c-125">For more information, see the Help documentation for the Test-CsVoiceTestConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="92b7c-126">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="92b7c-126">Determining success or failure</span></span>

<span data-ttu-id="92b7c-127">Test CsVoiceTestConfiguration Cmdlet 會報告測試是否失敗或成功，並提供每個成功測試的其他相關資訊，例如翻譯規則、語音路線，以及用來完成工作的 PSTN 使用方式：</span><span class="sxs-lookup"><span data-stu-id="92b7c-127">The Test-CsVoiceTestConfiguration cmdlet reports whether a test failed or succeeded, and provides additional information about each successful test, such as the translation rule, voice route, and PSTN usage used to complete the task:</span></span>

<span data-ttu-id="92b7c-128">結果：成功</span><span class="sxs-lookup"><span data-stu-id="92b7c-128">Result:             Success</span></span>

<span data-ttu-id="92b7c-129">TranslatedNumber： + 15551234</span><span class="sxs-lookup"><span data-stu-id="92b7c-129">TranslatedNumber:   +15551234</span></span>

<span data-ttu-id="92b7c-130">MatchingRule： Description =;Pattern = ^ （\\d{4}） $;譯文 = + 1\\d;Name = Test; IsInternalExtension = False</span><span class="sxs-lookup"><span data-stu-id="92b7c-130">MatchingRule:       Description=;Pattern=^(\\d{4})$;Translation=+1\\d;Name=Test;IsInternalExtension=False</span></span>

<span data-ttu-id="92b7c-131">FirstMatchingRoute：網站：雷蒙德</span><span class="sxs-lookup"><span data-stu-id="92b7c-131">FirstMatchingRoute: site:Redmond</span></span>

<span data-ttu-id="92b7c-132">MatchingUsage： Local</span><span class="sxs-lookup"><span data-stu-id="92b7c-132">MatchingUsage:      Local</span></span>

<span data-ttu-id="92b7c-133">如果測試失敗，則會將結果報告為失敗：</span><span class="sxs-lookup"><span data-stu-id="92b7c-133">If the test fails then the result is reported as Fail:</span></span>

<span data-ttu-id="92b7c-134">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="92b7c-134">Result:             Fail</span></span>

<span data-ttu-id="92b7c-135">TranslatedNumber:</span><span class="sxs-lookup"><span data-stu-id="92b7c-135">TranslatedNumber:</span></span>   

<span data-ttu-id="92b7c-136">FirstMatchingRoute:</span><span class="sxs-lookup"><span data-stu-id="92b7c-136">FirstMatchingRoute:</span></span>

<span data-ttu-id="92b7c-137">MatchingUsage:</span><span class="sxs-lookup"><span data-stu-id="92b7c-137">MatchingUsage:</span></span>      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="92b7c-138">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="92b7c-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="92b7c-139">因為語音測試組態測試會測試數個不同的專案，包括語音原則、撥號方案、語音路由等等，因此可能會造成測試失敗的幾個不同因素。</span><span class="sxs-lookup"><span data-stu-id="92b7c-139">Because voice test configuration testing tests several different items – including voice policies, dial plans, voice routes, and so on – there are several different factors that could result in a failed test.</span></span> <span data-ttu-id="92b7c-140">如果測試失敗，您的第一個步驟就是使用 CsVoiceTestConfiguration Cmdlet 來查看設定設定本身：</span><span class="sxs-lookup"><span data-stu-id="92b7c-140">If a test fails, your first step should be to review the configuration settings themselves by using the Get-CsVoiceTestConfiguration cmdlet:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

<span data-ttu-id="92b7c-141">如果設定正確設定，請重新執行測試，包括詳細參數：</span><span class="sxs-lookup"><span data-stu-id="92b7c-141">If the settings seem to be configured correctly, re-run the test while including the Verbose parameter:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="92b7c-142">詳細的參數將提供由 Test CsVoiceTestConfiguration 所採取的每個動作的逐步帳戶，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="92b7c-142">The Verbose parameter will provide a step-by-step account of each action taken by Test-CsVoiceTestConfiguration as shown in this example:</span></span>

<span data-ttu-id="92b7c-143">詳細：載入撥號方案：「全域」</span><span class="sxs-lookup"><span data-stu-id="92b7c-143">VERBOSE: Loading dial plan: "Global"</span></span>

<span data-ttu-id="92b7c-144">詳細：載入語音原則： "RedmondDialPlan"</span><span class="sxs-lookup"><span data-stu-id="92b7c-144">VERBOSE: Loading voice policy: "RedmondDialPlan"</span></span>

<span data-ttu-id="92b7c-145">此逐步式帳戶可能會提供有用的線索來指示測試實際失敗的位置。</span><span class="sxs-lookup"><span data-stu-id="92b7c-145">This step-by-step account might provide a useful clue as to where the test actually failed.</span></span> <span data-ttu-id="92b7c-146">如果不是，您可以使用其他的 Windows PowerShell Cmdlet （例如 Test-CsVoicePolicy），並系統地開始驗證語音測試設定中所包含的個別元件。</span><span class="sxs-lookup"><span data-stu-id="92b7c-146">If not, you can then use other Windows PowerShell cmdlets (such as Test-CsVoicePolicy) and methodically begin to verify the individual components that are included in the voice test configuration settings.</span></span>

<span data-ttu-id="92b7c-147">此外，請注意，測試可以傳送通話，但仍會標示為失敗，否則可能會出現問題;如果您輸入 ExpectedRoute、ExpectedTranslatedNumber 和 ExpectedUsage 的值，而且不符合這些預期中的任何一個，就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="92b7c-147">In addition to that, be aware that it’s possible for a test to be able to route a call and yet still be marked as a failure; that can occur if you enter values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage, and any of those expectations are not met.</span></span> <span data-ttu-id="92b7c-148">例如，假設您輸入語音路由 C 作為預期的語音路線，但測試實際上是使用語音路由 D 完成通話。在這種情況下，測試將會標示為失敗，因為未使用預期的語音路由。</span><span class="sxs-lookup"><span data-stu-id="92b7c-148">For example, suppose that you enter voice route C as your expected voice route, but the test actually completes the call using voice route D. In that case the test will be marked as Failed because the expected voice route was not used.</span></span> <span data-ttu-id="92b7c-149">如果測試失敗，您可以移除 ExpectedRoute、ExpectedTranslatedNumber 和 ExpectedUsage 的值，然後重新執行測試。</span><span class="sxs-lookup"><span data-stu-id="92b7c-149">If a test fails, you might remove the values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage and then re-run the test.</span></span> <span data-ttu-id="92b7c-150">這可協助您判斷失敗是因為通話無法完成，或是因為您預期是接聽電話，而實際收到另一個。</span><span class="sxs-lookup"><span data-stu-id="92b7c-150">That will help you determine whether the failure was because the call couldn't be completed, or because you expect one thing and actually received another.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="92b7c-151">請參閱</span><span class="sxs-lookup"><span data-stu-id="92b7c-151">See Also</span></span>


[<span data-ttu-id="92b7c-152">Test-CsVoiceTestConfiguration</span><span class="sxs-lookup"><span data-stu-id="92b7c-152">Test-CsVoiceTestConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

