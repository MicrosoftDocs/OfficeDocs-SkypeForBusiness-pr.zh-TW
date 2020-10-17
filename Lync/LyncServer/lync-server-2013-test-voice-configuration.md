---
title: Lync Server 2013：測試語音設定
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
ms.openlocfilehash: 1491aa1d28de238bcadd2a024021fabf16e9128a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527900"
---
# <a name="test-voice-configuration-in-lync-server-2013"></a><span data-ttu-id="89374-102">在 Lync Server 2013 中測試語音設定</span><span class="sxs-lookup"><span data-stu-id="89374-102">Test voice configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89374-103">_**主題上次修改日期：** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="89374-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="89374-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="89374-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="89374-105">每月</span><span class="sxs-lookup"><span data-stu-id="89374-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89374-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="89374-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="89374-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="89374-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89374-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="89374-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="89374-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="89374-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="89374-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsVoiceTestConfiguration Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="89374-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceTestConfiguration cmdlet.</span></span> <span data-ttu-id="89374-111">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="89374-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="89374-112">描述</span><span class="sxs-lookup"><span data-stu-id="89374-112">Description</span></span>

<span data-ttu-id="89374-113">Lync Server 包含數個 Windows PowerShell Cmdlet (例如 Test-CsVoiceRoute 和 Set-csvoicepolicy，Test-CsTrunkConfiguration) ，可讓您驗證企業語音基礎結構的個別元件–語音路由、語音原則、SIP 主幹–如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="89374-113">Lync Server includes several Windows PowerShell cmdlets (such as Test-CsVoiceRoute and Test-CsVoicePolicy, Test-CsTrunkConfiguration) that enable you to verify that the individual pieces of your Enterprise Voice infrastructure – voice routes, voice policies, SIP trunks – are working as expected.</span></span>

<span data-ttu-id="89374-114">雖然所有個別片段都運作的 Enterprise Voice 很重要，但仍然可以有有效的語音路由、有效的語音原則和有效的 SIP 主幹，但仍然有使用者無法撥打或接聽電話。</span><span class="sxs-lookup"><span data-stu-id="89374-114">While it’s important with Enterprise Voice that all the individual pieces work: it’s possible to have a valid voice route, a valid voice policy, and a valid SIP trunk, but still have users unable to make or receive phone calls.</span></span> <span data-ttu-id="89374-115">因此，Lync Server 也會提供建立語音測試設定的能力。</span><span class="sxs-lookup"><span data-stu-id="89374-115">Because of that, Lync Server also provides the ability to create voice test configurations.</span></span> <span data-ttu-id="89374-116">語音測試設定代表常見的 Enterprise Voice 案例：您可以指定語音路由、語音原則和撥號對應表等事項，然後驗證各項專案是否可以一起運作，以提供電話語音。</span><span class="sxs-lookup"><span data-stu-id="89374-116">Voice test configurations represent common Enterprise Voice scenarios: you can specify such things as a voice route, a voice policy, and a dial plan, and then verify that those individual items are work able to work together to provide phone service.</span></span> <span data-ttu-id="89374-117">此外，您也可以在特定案例中驗證您的預期。</span><span class="sxs-lookup"><span data-stu-id="89374-117">In addition, you can validate your expectations in a given scenario.</span></span> <span data-ttu-id="89374-118">例如，假設您預期撥號對應表 A 和 voice policy B 的組合會導致通話透過語音路由 C 路由傳送。您可以輸入語音路由 C 做為 ExpectedRoute。</span><span class="sxs-lookup"><span data-stu-id="89374-118">For example, suppose that you expect that the combination of dial plan A and voice policy B would result in calls being routed over voice route C. You can enter voice route C as the ExpectedRoute.</span></span> <span data-ttu-id="89374-119">當您執行測試時，如果沒有採用 voice route C，測試就會標示為已失敗。</span><span class="sxs-lookup"><span data-stu-id="89374-119">When you run the test, if voice route C is not employed then the test will be marked as having failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="89374-120">執行測試</span><span class="sxs-lookup"><span data-stu-id="89374-120">Running the test</span></span>

<span data-ttu-id="89374-121">在使用 Windows PowerShell 測試語音設定集合之前，您必須先使用 Get-CsVoiceTestConfiguration Cmdlet，以取得這些設定設定的實例。</span><span class="sxs-lookup"><span data-stu-id="89374-121">Before testing Voice configuration collections using Windows PowerShell, you must first use the Get-CsVoiceTestConfiguration cmdlet to retrieve an instance of these configuration settings.</span></span> <span data-ttu-id="89374-122">然後，必須將該實例管線傳送至 Test-CsVoiceTestConfiguration。</span><span class="sxs-lookup"><span data-stu-id="89374-122">That instance must then be piped to the Test-CsVoiceTestConfiguration.</span></span> <span data-ttu-id="89374-123">例如：</span><span class="sxs-lookup"><span data-stu-id="89374-123">For example:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="89374-124">若要同時驗證所有語音測試設定，請改為使用此命令：</span><span class="sxs-lookup"><span data-stu-id="89374-124">To validate all the voice test configuration settings at the same time, use this command instead:</span></span>

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

<span data-ttu-id="89374-125">如需詳細資訊，請參閱 Test-CsVoiceTestConfiguration Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="89374-125">For more information, see the Help documentation for the Test-CsVoiceTestConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="89374-126">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="89374-126">Determining success or failure</span></span>

<span data-ttu-id="89374-127">Test-CsVoiceTestConfiguration 指令指令會報告測試是否失敗或已成功，並提供每個成功測試的詳細資訊，例如轉譯規則、語音路由，以及用來完成工作的 PSTN 使用方式：</span><span class="sxs-lookup"><span data-stu-id="89374-127">The Test-CsVoiceTestConfiguration cmdlet reports whether a test failed or succeeded, and provides additional information about each successful test, such as the translation rule, voice route, and PSTN usage used to complete the task:</span></span>

<span data-ttu-id="89374-128">結果：成功</span><span class="sxs-lookup"><span data-stu-id="89374-128">Result:             Success</span></span>

<span data-ttu-id="89374-129">TranslatedNumber： + 15551234</span><span class="sxs-lookup"><span data-stu-id="89374-129">TranslatedNumber:   +15551234</span></span>

<span data-ttu-id="89374-130">MatchingRule： Description =;Pattern = ^ (\\ d {4}) $;轉譯 = + 1 \\ d;Name = Test; IsInternalExtension = False</span><span class="sxs-lookup"><span data-stu-id="89374-130">MatchingRule:       Description=;Pattern=^(\\d{4})$;Translation=+1\\d;Name=Test;IsInternalExtension=False</span></span>

<span data-ttu-id="89374-131">FirstMatchingRoute： site： Redmond</span><span class="sxs-lookup"><span data-stu-id="89374-131">FirstMatchingRoute: site:Redmond</span></span>

<span data-ttu-id="89374-132">MatchingUsage：本機</span><span class="sxs-lookup"><span data-stu-id="89374-132">MatchingUsage:      Local</span></span>

<span data-ttu-id="89374-133">如果測試失敗，則結果會報告為 [失敗]：</span><span class="sxs-lookup"><span data-stu-id="89374-133">If the test fails then the result is reported as Fail:</span></span>

<span data-ttu-id="89374-134">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="89374-134">Result:             Fail</span></span>

<span data-ttu-id="89374-135">TranslatedNumber:</span><span class="sxs-lookup"><span data-stu-id="89374-135">TranslatedNumber:</span></span>   

<span data-ttu-id="89374-136">FirstMatchingRoute:</span><span class="sxs-lookup"><span data-stu-id="89374-136">FirstMatchingRoute:</span></span>

<span data-ttu-id="89374-137">MatchingUsage:</span><span class="sxs-lookup"><span data-stu-id="89374-137">MatchingUsage:</span></span>      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="89374-138">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="89374-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="89374-139">因為語音測試設定測試會測試數種不同的專案（包括語音原則、撥號對應表、語音路由等等），所以有許多不同的因素會導致測試失敗。</span><span class="sxs-lookup"><span data-stu-id="89374-139">Because voice test configuration testing tests several different items – including voice policies, dial plans, voice routes, and so on – there are several different factors that could result in a failed test.</span></span> <span data-ttu-id="89374-140">測試失敗時，您的第一個步驟應該是使用 Get-CsVoiceTestConfiguration Cmdlet，自行複查設定設定：</span><span class="sxs-lookup"><span data-stu-id="89374-140">If a test fails, your first step should be to review the configuration settings themselves by using the Get-CsVoiceTestConfiguration cmdlet:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

<span data-ttu-id="89374-141">如果設定看似已正確設定，請重新執行測試，包含 Verbose 參數：</span><span class="sxs-lookup"><span data-stu-id="89374-141">If the settings seem to be configured correctly, re-run the test while including the Verbose parameter:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="89374-142">Verbose 參數會提供 Test-CsVoiceTestConfiguration 所執行之每個動作的逐步帳戶，如下列範例所示：</span><span class="sxs-lookup"><span data-stu-id="89374-142">The Verbose parameter will provide a step-by-step account of each action taken by Test-CsVoiceTestConfiguration as shown in this example:</span></span>

<span data-ttu-id="89374-143">詳細：載入撥號對應表： "Global"</span><span class="sxs-lookup"><span data-stu-id="89374-143">VERBOSE: Loading dial plan: "Global"</span></span>

<span data-ttu-id="89374-144">詳細：載入語音原則： "RedmondDialPlan"</span><span class="sxs-lookup"><span data-stu-id="89374-144">VERBOSE: Loading voice policy: "RedmondDialPlan"</span></span>

<span data-ttu-id="89374-145">這種逐步執行的帳戶可能會提供有用的線索，以供測試實際失敗的地方使用。</span><span class="sxs-lookup"><span data-stu-id="89374-145">This step-by-step account might provide a useful clue as to where the test actually failed.</span></span> <span data-ttu-id="89374-146">如果不是，您可以使用其他 Windows PowerShell Cmdlet (例如 Test-Set-csvoicepolicy) ，然後開始驗證語音測試設定中所包含的個別元件。</span><span class="sxs-lookup"><span data-stu-id="89374-146">If not, you can then use other Windows PowerShell cmdlets (such as Test-CsVoicePolicy) and methodically begin to verify the individual components that are included in the voice test configuration settings.</span></span>

<span data-ttu-id="89374-147">除了這一點，請注意，測試是否可以路由通話，但仍會標示為失敗;當您輸入 ExpectedRoute、ExpectedTranslatedNumber 和 ExpectedUsage 的值時，可能會發生這種情況，而且不會滿足任何預期。</span><span class="sxs-lookup"><span data-stu-id="89374-147">In addition to that, be aware that it’s possible for a test to be able to route a call and yet still be marked as a failure; that can occur if you enter values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage, and any of those expectations are not met.</span></span> <span data-ttu-id="89374-148">例如，假設您輸入語音路由 C 做為預期的語音路由，但測試實際上是使用語音路由 D 完成通話。在此情況下，測試會標示為「失敗」，因為未使用預期的語音路由。</span><span class="sxs-lookup"><span data-stu-id="89374-148">For example, suppose that you enter voice route C as your expected voice route, but the test actually completes the call using voice route D. In that case the test will be marked as Failed because the expected voice route was not used.</span></span> <span data-ttu-id="89374-149">如果測試失敗，您可以移除 ExpectedRoute、ExpectedTranslatedNumber 和 ExpectedUsage 的值，然後重新執行測試。</span><span class="sxs-lookup"><span data-stu-id="89374-149">If a test fails, you might remove the values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage and then re-run the test.</span></span> <span data-ttu-id="89374-150">這可協助您判斷失敗是否因為無法完成通話，或是因為您想要一件事而真的收到另一個。</span><span class="sxs-lookup"><span data-stu-id="89374-150">That will help you determine whether the failure was because the call couldn't be completed, or because you expect one thing and actually received another.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="89374-151">另請參閱</span><span class="sxs-lookup"><span data-stu-id="89374-151">See Also</span></span>


[<span data-ttu-id="89374-152">Test-CsVoiceTestConfiguration</span><span class="sxs-lookup"><span data-stu-id="89374-152">Test-CsVoiceTestConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

