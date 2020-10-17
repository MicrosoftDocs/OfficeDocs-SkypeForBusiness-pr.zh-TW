---
title: Lync Server 2013：測試撥號對應表
description: Lync Server 2013：測試撥號對應表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the dial plan
ms:assetid: 70eec03c-aca3-4106-86a7-77ae96b53779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690130(v=OCS.15)
ms:contentKeyID: 63969616
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0ef2e3fce9d1fbbb0186b1b7aef608834145d3e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556169"
---
# <a name="testing-the-dial-plan-in-lync-server-2013"></a><span data-ttu-id="92d26-103">在 Lync Server 2013 中測試撥號對應表</span><span class="sxs-lookup"><span data-stu-id="92d26-103">Testing the dial plan in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92d26-104">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="92d26-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92d26-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="92d26-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="92d26-106">每日</span><span class="sxs-lookup"><span data-stu-id="92d26-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92d26-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="92d26-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="92d26-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="92d26-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92d26-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="92d26-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="92d26-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="92d26-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="92d26-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsDialPlan Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="92d26-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialPlan cmdlet.</span></span> <span data-ttu-id="92d26-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="92d26-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="92d26-113">描述</span><span class="sxs-lookup"><span data-stu-id="92d26-113">Description</span></span>

<span data-ttu-id="92d26-114">Test-CsDialPlan Cmdlet 可讓您查看將撥號對應表套用至指定電話號碼的結果。</span><span class="sxs-lookup"><span data-stu-id="92d26-114">The Test-CsDialPlan cmdlet enables you to see the results of applying a dial plan to a given telephone number.</span></span> <span data-ttu-id="92d26-115">撥號對應表提供的資訊（例如，如何套用正規化規則），讓企業語音使用者撥打電話是必要的。</span><span class="sxs-lookup"><span data-stu-id="92d26-115">Dial plans provide information, such as how normalization rules are applied, required to enable Enterprise Voice users to make telephone calls.</span></span> <span data-ttu-id="92d26-116">根據撥打的號碼和撥號對應表，此 Cmdlet 將會確認套用撥號對應表內的哪個正規化規則，以及翻譯後的號碼將是什麼。</span><span class="sxs-lookup"><span data-stu-id="92d26-116">Given a dialed number and a dial plan, this cmdlet will verify which normalization rule within the dial plan will be applied and what the translated number will be.</span></span>

<span data-ttu-id="92d26-117">您可以使用此 Cmdlet 來疑難排解數位翻譯的問題，或驗證如何套用規則的特定數位。</span><span class="sxs-lookup"><span data-stu-id="92d26-117">You can use this cmdlet for troubleshooting issues with number translations, or for verifying how to apply rules against certain numbers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="92d26-118">執行測試</span><span class="sxs-lookup"><span data-stu-id="92d26-118">Running the test</span></span>

<span data-ttu-id="92d26-119">Test-CsDialPlan 指令指令需要您執行兩項作業。</span><span class="sxs-lookup"><span data-stu-id="92d26-119">The Test-CsDialPlan cmdlet requires you to do two things.</span></span> <span data-ttu-id="92d26-120">首先，您必須取得所測試之撥號對應表的實例;可以使用 Get-CsDialPlan Cmdlet 來完成。</span><span class="sxs-lookup"><span data-stu-id="92d26-120">First, you must obtain an instance of the dial plan being tested; that can be done by using the Get-CsDialPlan cmdlet.</span></span> <span data-ttu-id="92d26-121">其次，您必須指定必須正規化的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="92d26-121">Second, you must specify the phone number that has to be normalized.</span></span> <span data-ttu-id="92d26-122">電話號碼所用的格式應符合使用者撥打/輸入的號碼。</span><span class="sxs-lookup"><span data-stu-id="92d26-122">The format that is used for the phone number should match the number as dialed/entered by a user.</span></span> <span data-ttu-id="92d26-123">例如，此命令會檢索撥號對應表的實例，RedmondDialPlan，並檢查電話號碼12065551219是否可以正規化：</span><span class="sxs-lookup"><span data-stu-id="92d26-123">For example, this command retrieves an instance of the dial plan, RedmondDialPlan, and checks whether the phone number 12065551219 can be normalized:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

<span data-ttu-id="92d26-124">如果您有一個會自動在此範例中新增 country 代碼 (的正規化規則，則會有1個) 和區號 (206) ，您可能想要檢查電話號碼5551219，如下所示：</span><span class="sxs-lookup"><span data-stu-id="92d26-124">If you have a normalization rule that automatically adds the country code (in this example, 1) and the area code (206), then you might want to check the phone number 5551219, as follows:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

<span data-ttu-id="92d26-125">如需詳細資訊，請參閱 [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="92d26-125">For more information, see the Help documentation for the [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="92d26-126">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="92d26-126">Determining success or failure</span></span>

<span data-ttu-id="92d26-127">Test-CsDialPlan 與許多 Lync Server 測試 Cmdlet 不同，因為它只會間接指出測試是否成功或失敗。</span><span class="sxs-lookup"><span data-stu-id="92d26-127">Test-CsDialPlan differs from many of the Lync Server test cmdlets because it only indirectly indicates whether a test succeeded or failed.</span></span> <span data-ttu-id="92d26-128">使用 Test-CsDialPlan 時，您不會收到類似如下的輸出結果，並以明確標示的結果：</span><span class="sxs-lookup"><span data-stu-id="92d26-128">When using Test-CsDialPlan you do not receive back output similar to this with the Result clearly labeled:</span></span>

<span data-ttu-id="92d26-129">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="92d26-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="92d26-130">結果：成功</span><span class="sxs-lookup"><span data-stu-id="92d26-130">Result : Success</span></span>

<span data-ttu-id="92d26-131">延遲：00：00：06.8630376</span><span class="sxs-lookup"><span data-stu-id="92d26-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="92d26-132">錯誤：</span><span class="sxs-lookup"><span data-stu-id="92d26-132">Error :</span></span>

<span data-ttu-id="92d26-133">診斷：</span><span class="sxs-lookup"><span data-stu-id="92d26-133">Diagnosis :</span></span>

<span data-ttu-id="92d26-134">相反地，如果 Test-CsDialPlan 成功，則會收到可順利翻譯和使用指定電話號碼之正規化規則的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="92d26-134">Instead, if Test-CsDialPlan succeeds, then you'll receive information about the normalization rule that was able to successfully translate and use the specified phone number:</span></span>

<span data-ttu-id="92d26-135">TranslatedNumber： + 12065551219</span><span class="sxs-lookup"><span data-stu-id="92d26-135">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="92d26-136">MatchingRule： Description =;Pattern = ^ (\\ d (11) # B3 $;轉譯 = + $ 1;</span><span class="sxs-lookup"><span data-stu-id="92d26-136">MatchingRule : Description=;Pattern=^(\\d(11))$;Translation=+$1;</span></span>

<span data-ttu-id="92d26-137">Name = Prefix 全部;IsInternalExtension = False</span><span class="sxs-lookup"><span data-stu-id="92d26-137">Name=Prefix All; IsInternalExtension=False</span></span>

<span data-ttu-id="92d26-138">如果 Test-CsDialPlan 失敗 (也就是說，如果撥號對應表沒有可轉譯指定電話號碼的正規化規則) ，您只會收到「空白」輸出，如下所示：</span><span class="sxs-lookup"><span data-stu-id="92d26-138">If Test-CsDialPlan fails (that is, if the dial plan does not have a normalization rule that can translate the specified phone number), you'll just receive “empty” output as follows:</span></span>

<span data-ttu-id="92d26-139">TranslatedNumber :</span><span class="sxs-lookup"><span data-stu-id="92d26-139">TranslatedNumber :</span></span>

<span data-ttu-id="92d26-140">MatchingRule :</span><span class="sxs-lookup"><span data-stu-id="92d26-140">MatchingRule :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="92d26-141">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="92d26-141">Reasons why the test might have failed</span></span>

<span data-ttu-id="92d26-142">以下是一些 Test-CsDialPlan 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="92d26-142">Here are some common reasons why Test-CsDialPlan might fail:</span></span>

  - <span data-ttu-id="92d26-143">指定電話號碼時，您可能使用了不正確的格式。</span><span class="sxs-lookup"><span data-stu-id="92d26-143">You might have used an incorrect format when specifying the phone number.</span></span> <span data-ttu-id="92d26-144">撥號對應表包含正常化規則，可讓 Lync Server 轉譯使用者撥打或輸入的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="92d26-144">Dial plans include normalization rules that enable Lync Server to translate the phone numbers dialed or entered by a user.</span></span> <span data-ttu-id="92d26-145">因此，您的撥號對應表應該會有符合使用者可能會撥號的數量的正規化規則。</span><span class="sxs-lookup"><span data-stu-id="92d26-145">Therefore, your dial plan should have normalization rules that match the numbers users are likely to dial.</span></span> <span data-ttu-id="92d26-146">例如，如果使用者可能撥打國家/地區代碼、區號，然後輸入電話號碼，則表示您的撥號對應表應具有標準化規則來處理電話號碼，如下所示：</span><span class="sxs-lookup"><span data-stu-id="92d26-146">For example, if users might dial the country code, area code, and then the phone number itself, that means that your dial plan should have a normalization rule to handle phone numbers such as this:</span></span>
    
    <span data-ttu-id="92d26-147">12065551219</span><span class="sxs-lookup"><span data-stu-id="92d26-147">12065551219</span></span>
    
    <span data-ttu-id="92d26-148">不過，如果您輸入不正確的電話號碼 (例如，保留最後一位數) ，Test-CsDialPlan 將會失敗。</span><span class="sxs-lookup"><span data-stu-id="92d26-148">However, if you enter an incorrect phone number (for example, leaving off the final digit), then Test-CsDialPlan will fail.</span></span> <span data-ttu-id="92d26-149">這不是因為撥號對應表有問題，但您輸入的電話號碼無法轉譯。</span><span class="sxs-lookup"><span data-stu-id="92d26-149">That’s not because the dial plan is faulty but because you have entered a phone number than can’t be interpreted.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

